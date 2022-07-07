<script>
  export let params = {}
  import {fade} from 'svelte/transition'
  import SideButton from "../components/SideButton.svelte";
  import BinProps from './topics/BinProps.svelte'
  import Software from './topics/Software.svelte'
  import { push,location } from "svelte-spa-router";
  
  
  let topics = [
    {
      title:'Bin Properties',
      href: '#/wiki/props',
      subtopics:[{
        title: 'Birth Color',
        href: '#/wiki/props/birthcolor'
      },{
        title: 'Color',
        href: '#/wiki/props/color'
      }]
    },
    {
      title:'Programs',
      href: '#/wiki/software',
      subtopics:[{
        title: 'Maya',
        href: '#/wiki/software/maya'
      },{
        title: 'obsidian',
        href: '#/wiki/software/obsidian'
      }]
    }
  ]
  $: subtopic = params['subtopic']
</script>

<style>
  .wiki{
    display:flex;
    height: 100%;
  }
  .wikinav{
    display:flex;
    flex-direction: column;
    height:100%;
    width:12rem;
    background-color: var(--gray-400);
  }
  dt{
    font-weight: 500;
    padding-left: 1rem;
    color: var(--gray-000);
  }
</style>

<div class="wiki" in:fade>
  <dl class="wikinav">
    {#each topics as topic}
      <dt>{topic.title}</dt>
      {#each topic.subtopics as subtopic}
      <dl><SideButton on:click={() => {
          push(subtopic.href);
        }}>{subtopic.title}</SideButton></dl>
      {/each}
    {/each}
  </dl>
  {#if params['topic'] == 'props'}
    <BinProps {subtopic}/>
  {:else if params['topic'] == 'software'}
    <Software {subtopic}/>
  {:else}
    no page yet
  {/if}
</div>