00:00 After we login to Contentful, first thing we need to do is create a space. This will hold all our content. We can pick one of the free spaces that we have, and we can name this `jamstack tutorials`, because we're building a website about JAMstack tutorials.

![Create Space modal in contentful website](https://res.cloudinary.com/dg3gyk0gu/image/upload/v1562190183/transcript-images/javascript-model-content-in-the-contentful-web-app-create-space.png)

00:18 For our website, we need a lesson, and every lesson is assigned to an instructor. We can define the structure of that website simply by creating content types. The first one is `Lesson`, and for Lesson, we need a `Title`. This will be a text field.

![Create lesson type modal in Contentful](https://res.cloudinary.com/dg3gyk0gu/image/upload/v1562190182/transcript-images/javascript-model-content-in-the-contentful-web-app-title.png)

00:46 We'll need a `Slug` field. This will help us define human-readable URLs, and it will be autogenerated from the title automatically. We can configure it, and we tell Contentful, "Hey, this is a slug field." Now, we hit save.

01:04 After that, we need a rich text field. This will be the `Body` of the lesson, so this is the content of the lesson. We said we want to assign a lesson to an instructor. We need to create a reference field, and we call it `Instructor`.

01:25 This will link to a different content type that we will define later. A lesson also should have an image, so we can pick a media field, and we can call this `Image`. We only need one file, but we can list many files.

01:43 For some search engine optimizations, we can actually link another content type that will define just the metadata that we want to show to Google, meaning we will put them in the header of the HTML. Let's add that field. It will be another reference field, and we can call it simply `SEO`.

02:03 We hit create and save. Our first content type is done.

![Finished Content Type and is shown in Contentful](https://res.cloudinary.com/dg3gyk0gu/image/upload/v1562190182/transcript-images/javascript-model-content-in-the-contentful-web-app-finished-content-type.png)

Now, we need to create the `Instructor` content type. Our instructors will have `Full Name`. It will be short text. Also, we want to have an instructor page, so we can use again a slug field to define human-readable URLs.

02:38 This will be called `Slug`, and we configure it to be a slug field. Instructor has a `Bio` field, so we know something about them. Also, the instructor can have a `website`. We can configure this to be a URL field. Also, for `Twitter`, we will do the same.

03:13 Why not link the `GitHub` account also? Finally, we want to see the face of our instructor, so we can actually have an `Avatar` for that. We save. We go back to the content type list, and we'll add our last content type. This will be called `SEO`.

03:44 For SEO, we can have the first field be `Title`. We can also have some `Description`, and lastly, `Keywords`, making a field for each one of those. They will all be of text fields. We save, we'll go back to our content type list. We need to change the lesson content type, to make sure our editors always link instructors and not any other content type.

04:23 For example, we can go to Settings and Validations, and we tell it only accept Instructor. We can do the same for SEO, and we only accept SEO content types. We hit save.
