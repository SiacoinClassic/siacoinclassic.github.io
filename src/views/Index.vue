<template>
  <div class="main index">
    <section class="wrapper">
      <div class="classic">
        <img src="@/assets/icons/logo.svg"/>
      </div>
      <div class="triangle">
        <span>Since<br/>October 31st, 2018.</span>
      </div>
      <div class="info">
        <div>
          <h1>
            <span class="bold">S</span>ia<span class="bold">c</span>oin<br/>
            <span class="bold">C</span>lassic
          </h1>
          <p>decentralized</p>
          <p>immutable</p>
          <p>unstoppable</p>
        </div>
      </div>
    </section>
    <section class="core-softwares">
      <div class="container">
        <h2>Core Softwares</h2>
        <div class="row">
          <div class="col col-lg-12 col-md-24">
            <div class="card">
              <div class="card-header">
                <div class="clearfix">
                  <span>{{ org }} UI</span>
                </div>
              </div>
              <div class="card-body">
                <p>
                  Download version {{ version }} of {{ org }}-UI
                  with a Graphical User Interface.
                </p>
                <p>Built for users who prefer to use a GUI over command line.</p>
                <div class="download">
                  <ul>
                    <li
                      v-for="(filename, os) in files.ui"
                      :key="os"
                    >
                      <a
                        :href="`${downloads.ui}/${version}/${org}-UI-${version}-${filename}`"
                        target="_blank"
                      >
                        <span>{{ os }}</span>
                        <img
                          :src="require(`@/assets/icons/core-softwares/${brand2filename(os)}.svg`)"
                        >
                      </a>
                    </li>
                  </ul>
                </div>
                <div class="float-right">
                  <a
                    :href="`${releases.ui}/releases/tag/${version}`"
                    target="_blank"
                  >
                    <span>Github</span>
                    <img src="@/assets/icons/socials/github.svg"/>
                  </a>
                </div>
              </div>
            </div>
          </div>
          <div class="col col-lg-12 col-md-24">
            <div class="card">
              <div class="card-header">
                <div class="clearfix">
                  <span>{{ org }} Daemon</span>
                </div>
              </div>
              <div class="card-body">
                <p>
                  Download version {{ version }} of {{ org }} Daemon
                  for use with your preferred CLI.
                </p>
                <p>Built for technical users comfortable with command line.</p>
                <div class="download">
                  <ul>
                    <li
                      v-for="(filename, os) in files.daemon"
                      :key="os"
                    >
                      <a
                        :href="`${downloads.daemon}/${version}/${org}-${version}-${filename}`"
                        target="_blank"
                      >
                        <span>{{ os }}</span>
                        <img
                          :src="require(`@/assets/icons/core-softwares/${brand2filename(os)}.svg`)"
                        >
                      </a>
                    </li>
                  </ul>
                </div>
                <div class="float-right">
                  <a
                    :href="`${releases.daemon}/tag/${version}`"
                    target="_blank"
                  >
                    <span>Github</span>
                    <img src="@/assets/icons/socials/github.svg"/>
                  </a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="mining-pools">
      <div class="container">
        <h2>Mining Pools</h2>
        <div class="row">
          <div
            v-for="(url, brand) in miningPools"
            :key="brand"
            class="col col-lg-6 col-md-24"
          >
            <div class="card">
              <a :href="url" target="_blank">
              <div class="card-body">
                <img :src="require(`@/assets/icons/mining-pools/${brand2filename(brand)}.png`)">
                <p>{{ brand }}</p>
              </div>
              </a>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="network-stats">
      <div class="container">
        <h2>Network Stats</h2>
        <div class="row">

        </div>
      </div>
    </section>
    <section class="exchanges">
      <div class="container">
        <h2>Exchanges</h2>
        <div class="row">

        </div>
      </div>
    </section>
    <section class="socials">
      <div class="container">
        <h2>Socials</h2>
        <div class="row">
          <div
            v-for="(url, social) in socials"
            :key="social"
            class="col col-lg-6 col-md-24"
          >
            <div class="card">
              <a :href="url" target="_blank">
              <div class="card-body">
                <img :src="require(`@/assets/icons/socials/${brand2filename(social)}.svg`)">
                <p>{{ social }}</p>
              </div>
              </a>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import {
  project,
  miningPools,
  socials,
} from '@/config';

import { brand2filename } from '@/utils';

export default {
  name: 'Index',
  data() {
    return {
      org: project.org,
      version: project.version,
      releases: project.releases,
      downloads: project.downloads,
      files: project.files,
      miningPools,
      socials,
    };
  },
  methods: {
    brand2filename,
  },
};
</script>

<style lang="scss" scoped>
.main {
  .wrapper {
    width: 100%;
    height: 100vh;
    .classic, .info, .triangle {
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
    }
    .classic {
      img {
        width: 50%;
      }
    }
    .info {
      background-color: #17122b;
      h1, p {
        color: #f38030;
      }
      h1 {
        font-size: 4em;
        margin: 0;
      }
      p {
        font-size: 1.4em;
        line-height: 1em;
        margin-block-end: 0em;
      }
      .bold {
        color: #fff;
      }
    }
    .triangle {
      background-image: url("data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='100' height='100' viewBox='0 0 100 100' preserveAspectRatio='none'%3E%3Cpolygon points='0,100 100,0 100,100' style='fill:%2317122b%3B' /%3E%3C/svg%3E");
      background-repeat: no-repeat;
      background-size: 100% 100%;
      span {
        color: #fff;
        font-size: 1em;
      }
    }
    background-color: #17122b;
    background-image: linear-gradient( rgba(#17122b, .7)),
      url('../assets/images/connectedworld.jpg');
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
  }
  .core-softwares, .mining-pools, .network-stats, .exchanges, .socials {
    padding: 3em 0;
    h2 {
      position: relative;
      color: #7f8c8d;
      font-size: 2.5em;
      font-weight: 400;
      text-align: center;
      margin-block-start: 0;
      margin-block-end: 2em;
    }
    h2::before {
      content: "";
      position: absolute;
      display: block;
      width: 2em;
      height: .1em;
      background: #EE8B2B;
      left: 50%;
      margin-left: -1em;
      bottom: -.5em;
    }
  }
  .core-softwares {
    background-color: #ecf0f1;
    .card {
      min-height: 13em;
      .card-body {
        padding-top: 0;
        a {
          color: #EE8B2B;
        }
        img {
          width: 2em;
        }
        .download {
          display: inline-block;
          ul {
            display: flex;
            list-style: none;
            margin-block-start: 0;
            margin-block-end: 0;
            padding-inline-start: 0;
            li:first-child {
              padding-left: 0;
            }
            li {
              padding: 0 1em;
              border-right: .1em solid #ecf0f1;
            }
            li:last-child {
              border-right: none;
            }
          }
        }
      }
    }
  }
  .mining-pools, .network-stats, .exchanges, .socials {
    .card {
      a {
        color: #303133;
      }
      .card-body {
        text-align: center;
        img {
          height: 4em;
        }
        p {
          margin-block-end: 0;
        }
      }
    }
  }
  .mining-pools, .exchanges {
    background-color: #f7f9f9;
  }
  .network-stats, .socials {
    background-color: #ffffff;
  }
}
</style>
