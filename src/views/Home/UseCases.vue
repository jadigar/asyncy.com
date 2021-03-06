<template>
  <a-layout
    :padding="['3x5', 'large']"
    foreground="light"
    rounded
  >
    <a-container vh-centered>
      <a-div
        :padding="['normal', 'min']"
        size="full"
      >
        <h4 class="is-size-4 has-text-weight-semibold has-text-gray-2">Use Cases</h4>
      </a-div>
      <a-div
        :padding="['none', 'normal']"
        size="8"
      >
        <p class="is-size-6 has-text-gray-2">Build robust, cloud-native application backends in a fraction of the time powered by Kubernetes and microservices.</p>
      </a-div>
      <a-div size="4" />
      <a-div
        v-for="(uc, idx) of usecases"
        :key="`list-usecases-${_uid}-${uc}`"
        size="one-quarter"
        padding="1x"
        class="a-usecase-box-container"
      >
        <div class="a-usecase-box">
          <div class="icon">
            <icon-use-cases :idx="idx" />
          </div>
          <p class="is-size-7 has-text-weight-semibold has-text-uppercase">
            {{ uc }}
          </p>
        </div>
      </a-div>
    </a-container>
  </a-layout>
</template>

<script>
import IconUseCases from '@/components/IconUseCases'

export default {
  name: 'UseCases',
  components: { IconUseCases },
  data: () => ({ usecases: ['Cron Jobs', 'Websockets', 'API\'s', 'Automations', 'Integrations', 'Backends', 'Http Endpoints', 'CI/CD Pipelines'] })
}
</script>

<style lang="scss">
.a-usecase-box-container {
  @for $i from 1 through 5 {
    &:nth-child(#{1 + 2 * $i}) {
      @include desktop {
        margin-top: 1rem;
        margin-bottom: -1rem;
      }
    }
  }
}
.a-usecase-box {
  background-color: $white;
  background-image: url("data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzVweCIgaGVpZ2h0PSI2MXB4IiB2aWV3Qm94PSIwIDAgMzUgNjEiIHZlcnNpb249IjEuMSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayI+PGcgZmlsbD0iI0M2QzdEQyI+PGVsbGlwc2UgY3g9IjEuNTkwOTA5MDkiIGN5PSIxLjUiIHJ4PSIxLjU5MDkwOTA5IiByeT0iMS41IiAvPjxlbGxpcHNlIGN4PSIxNy41IiBjeT0iMS41IiByeD0iMS41OTA5MDkwOSIgcnk9IjEuNSIgLz48ZWxsaXBzZSBjeD0iMzMuNDA5MDkwOSIgY3k9IjEuNSIgcng9IjEuNTkwOTA5MDkiIHJ5PSIxLjUiIC8+PGVsbGlwc2UgY3g9IjEuNTkwOTA5MDkiIGN5PSIyMC41IiByeD0iMS41OTA5MDkwOSIgcnk9IjEuNSIgLz48ZWxsaXBzZSBjeD0iMTcuNSIgY3k9IjIwLjUiIHJ4PSIxLjU5MDkwOTA5IiByeT0iMS41IiAvPjxlbGxpcHNlIGN4PSIzMy40MDkwOTA5IiBjeT0iMjAuNSIgcng9IjEuNTkwOTA5MDkiIHJ5PSIxLjUiIC8+PGVsbGlwc2UgY3g9IjEuNTkwOTA5MDkiIGN5PSI0MC41IiByeD0iMS41OTA5MDkwOSIgcnk9IjEuNSIgLz48ZWxsaXBzZSBjeD0iMTcuNSIgY3k9IjQwLjUiIHJ4PSIxLjU5MDkwOTA5IiByeT0iMS41IiAvPjxlbGxpcHNlIGN4PSIzMy40MDkwOTA5IiBjeT0iNDAuNSIgcng9IjEuNTkwOTA5MDkiIHJ5PSIxLjUiIC8+PGVsbGlwc2UgY3g9IjEuNTkwOTA5MDkiIGN5PSI1OS41IiByeD0iMS41OTA5MDkwOSIgcnk9IjEuNSIgLz48ZWxsaXBzZSBjeD0iMTcuNSIgY3k9IjU5LjUiIHJ4PSIxLjU5MDkwOTA5IiByeT0iMS41IiAvPjxlbGxpcHNlIGN4PSIzMy40MDkwOTA5IiBjeT0iNTkuNSIgcng9IjEuNTkwOTA5MDkiIHJ5PSIxLjUiIC8+PC9nPjwvc3ZnPg==");
  background-position: calc(100% - 1rem) 1rem;
  background-repeat: no-repeat;
  border-radius: 0.625rem;
  box-shadow: 0 5px 15px 0 rgba(0, 0, 0, 0.09);
  padding: 2rem 2rem 2rem 1rem;
  display: flex;
  align-items: center;
  flex-wrap: nowrap;
  cursor: pointer;
  p {
    color: #110e24;
    word-break: normal;
    @include touch {
      word-break: break-all;
    }
  }
  .icon {
    background-color: rgba($info, 0.35);
    border-radius: 2rem;
    width: 4rem;
    min-width: 4rem;
    height: 4rem;
    margin-right: 1rem;
    @include desktop-only {
      margin-right: 0.2rem;
    }
    @include widescreen-only {
      margin-right: 0.2rem;
    }
    svg {
      fill: nth($grays, 2);
    }
  }
  &:hover {
    .icon {
      background-color: $white;
    }
    background-color: #722bff;
    p {
      color: $white;
    }
  }
}
</style>
