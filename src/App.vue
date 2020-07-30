<template>
   <v-app>
      <v-content>
         <v-row class="primary white--text">
            <h1 class="display-4 mx-auto pa-4">Magic Markdown Previewer</h1>
         </v-row>
         <v-row justify="center">
            <v-col cols="5">
               <h1 class="display-2 font-weight-light text-center ma-10">Markdown Editor</h1>
               <v-textarea outlined rows="1" auto-grow label="Enter markdown here" id="editor" counter v-model="text"></v-textarea>
            </v-col>
            <v-col cols="5">
               <h1 class="display-2 font-weight-light text-center ma-10">Markdown Preview</h1>
               <vue-markdown id="preview" :source="text" style="line-height: 2"></vue-markdown>
            </v-col>
         </v-row>
      </v-content>
   </v-app>
</template>

<script>
import VueMarkdown from "vue-markdown";
export default {
   name: "App",
   data: () => ({
      text: `# Welcome to my Vue Markdown Previewer!

## This is a sub-heading...
### And here's some other cool stuff:
  
Heres some code, \`<div></div>\`, between 2 backticks.

\`\`\`
// this is multi-line code:

function anotherExample(firstLine, lastLine) {
  if (firstLine == '\`\`\`' && lastLine == '\`\`\`') {
    return multiLineCode;
  }
}
\`\`\`
  
You can also make text **bold**... whoa!
Or _italic_.
Or... wait for it... **_both!_**
And feel free to go crazy ~~crossing stuff out~~.

There's also [links](https://www.freecodecamp.com), and
> Block Quotes!

And if you want to get really crazy, even tables:

Wild Header | Crazy Header | Another Header?
------------ | ------------- | ------------- 
Your content can | be here, and it | can be here....
And here. | Okay. | I think we get it.

- And of course there are lists.
  - Some are bulleted.
     - With different indentation levels.
        - That look like this.


1. And there are numbererd lists too.
1. Use just 1s if you want! 
1. But the list goes on...
- Even if you use dashes or asterisks.
* And last but not least, let's not forget embedded images:

![Vue Logo w/ Text](https://vuejs.org/images/logo.png)
`,
   }),
   components: {
      VueMarkdown,
   },
};
</script>
