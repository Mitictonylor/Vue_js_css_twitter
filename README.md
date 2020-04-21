# homework

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

Twitter - Multi Components Lab/HW
Learning Objectives
Be able to create a Vue app with multiple components and templates
Brief
Your task is to create an app that displays a list of tweets and their details.

The following tweet data should be stored in App.vue and passed to a list component as props.

data() {
  return {
    tweets:[
      {
        id: 1,
        name: 'James',
        handle: '@jokerjames',
        img: 'https://semantic-ui.com/images/avatar2/large/matthew.png',
        tweet: "If you don't succeed, dust yourself off and try again.",
        likes: 10,
      },
      {
        id: 2,
        name: 'Fatima',
        handle: '@fantasticfatima',
        img: 'https://semantic-ui.com/images/avatar2/large/molly.png',
        tweet: 'Better late than never but never late is better.',
        likes: 12,
      },
      {
        id: 3,
        name: 'Xin',
        handle: '@xeroxin',
        img: 'https://semantic-ui.com/images/avatar2/large/elyse.png',
        tweet: 'Beauty in the struggle, ugliness in the success.',
        likes: 18,
      }
    ]
  }
}
MVP
Display a list of tweets with all the details.
Display the user avatar along with the tweet
Use computed property to display the total number of likes for all tweets.
Extensions
Allow user to add a new tweet. Use an existing avatar links. (Add the Form to the App component)
Filter the tweets to only display ones with over 10 likes
Change the styling for tweets with over 10 likes
Planning
Draw a diagram of your files, detailing:

the data, props, components and methods for each component.
the flow of data throughout the application.
Expected Components for MVP

TweetListItem
Published with GitHub Pages
