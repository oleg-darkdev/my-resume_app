<script>
  import { CurverNav } from '$entities';

  export let showSection = false, title, customClasses, anchor;
</script>

<section class="home-about group   {customClasses ? customClasses : 'mt-6'}" >
  <div class="padding-horizontal padding-small">
    <div class="grid-large">
      <div class="home-service-block content-wrap">
          <CurverNav link="#{anchor}" bind:showSection/>

          <div class="{showSection ? 'padding-top padding-large': ''} mt-2">
          <div class="padding-horizontal padding-medium">
            {#if showSection}
              <slot name='text-block'/>
            {/if}
          </div>


          <div class="home-service">
            <a name='{anchor}' />

            <div class="group-hover:transition group-hover:duration-1000 ease-in-out delay-150 transform group-hover:-translate-y-8 cursor-pointer mb-6" on:click={()=> showSection = !showSection}>
                <div  class="font-optiker" >
                    {title}
                </div>
            </div>


            <div class="{showSection ? 'padding-top padding-bottom padding-huge home-content_base': ''} ">
                <div class="home-content-block">
                    {#if showSection}
                        <slot name='content'/>
                    {/if}
                </div>
            </div>
        </div>
      </div>
    </div>
  </div>
</section>



<style>
.home-content_base {
  border-top: 1px solid #e7eeee;
}

.home-content-block {
  /* min-height: 35rem; */
  grid-column-gap: 5rem;
  grid-row-gap: 5rem;
  flex-direction: column;
  justify-content: space-between;
  display: flex;
  grid-area: span 1 / span 1 / span 1 / span 1;
}

.content-wrap {
  grid-area: 1 / 1 / 2 / 4;
}


.home-service_grid {
  grid-column-gap: 3rem;
  grid-row-gap: 0rem;
  flex-direction: column;
  grid-template-rows: auto;
  grid-template-columns: 1fr 1fr;
  grid-auto-columns: 1fr;
  align-content: stretch;
  justify-content: flex-start;
  align-items: stretch;
  margin-left: auto;
  margin-right: auto;
  /* padding-top: 6rem; */
  display: flex;
}


@media screen and (max-width: 991px) {
  .home-service_grid {
    padding-top: 2rem;
  }
  .font-optiker {
    font-family: Optiker k;
    font-size: 10em;
    margin-bottom: -80px;
    text-align: center;
  }
}
@media screen and (max-width: 767px) {
  .home-service_grid {
    padding-top: 1rem;
  }
  .font-optiker {
    font-family: Optiker k;
    font-size: 3.5em;
    margin-bottom: 2px;
    text-align: center;
  }
}

@media screen and (min-width: 991px) {
  .font-optiker {
    font-family: Optiker k;
    font-size: 17em;
    margin-bottom: -130px;
    text-align: center;
  }
}

</style>
