<template>
  <div>
    <slot />

    <footer class="footer">
      <div class="columns is-centered">
        <div class="column is-1">
          <b-button
            icon-left="github"
            tag="a"
            href="https://github.com/EgorHenek"
            target="_blank"
          >
            <span>@EgorHenek</span>
          </b-button>
        </div>
        <div class="column is-1">
          <b-button
            icon-left="vk"
            tag="a"
            href="https://vk.com/eagluhih"
            target="_blank"
            type="is-vk"
          />
        </div>
      </div>
    </footer>
  </div>
</template>
