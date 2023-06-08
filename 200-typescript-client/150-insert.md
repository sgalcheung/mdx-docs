---
title: Creating records with TypeScript
navTitle: Creating data
keywords: ["typescript", "create record"]
description: Code examples for how to create a new record with the TypeScript client
slug: typescript-client/insert
published: true
---

# Creating Records

You can create a record like this:

<Tabs>
  <SnippetTabList>
    <SwiperSlide>
       <SnippetTabButton>TypeScript</SnippetTabButton>
    </SwiperSlide>
    <SwiperSlide>
        <SnippetTabButton>JSON</SnippetTabButton>
    </SwiperSlide>
  </SnippetTabList>
  <TabPanels>
    <TabPanel>
```ts
const record = await xata.db.Users.create({
  email: "keanu@example.com",
  name: "keanu@example.com"
});
```
    </TabPanel>
    <TabPanel>
```json
// POST https://tutorial-ng7s8c.us-east-1.xata.sh/db/tutorial:main/tables/users/data

{
"email": "keanu@example.com",
"name": "Keanu Reeves"
}

````
    </TabPanel>
  </TabPanels>
</Tabs>

The TypeScript SDK returns the created record. The response looks like this:

<Tabs>
  <SnippetTabList>
    <SwiperSlide>
       <SnippetTabButton>TypeScript</SnippetTabButton>
    </SwiperSlide>
    <SwiperSlide>
        <SnippetTabButton>JSON</SnippetTabButton>
    </SwiperSlide>
  </SnippetTabList>
  <TabPanels>
    <TabPanel>
```ts
{
  "email":"keanu@example.com"
  "id":"rec_cd8rqcoavc42pi67lgd0"
  "name":"keanu@example.com"
  "bio":NULL
  "address":NULL
}
````

    </TabPanel>
    <TabPanel>

```json
{
  "id": "rec_c8hnbch26un1nl0rthkg",
  "xata": {
    "version": 0,
    "createdAt": "2023-05-15T08:21:31.96526+01:00",
    "updatedAt": "2023-05-15T21:58:54.072595+01:00"
  }
}
```

    </TabPanel>

  </TabPanels>
</Tabs>

In the above:

- `id` is the ID of the record, which Xata generates automatically. The generated records are globally unique and sortable. This means that sorting by the IDs you sort by the insertion order.
- `xata.version` is the version of the record. It is automatically incremented any time the record is updated and can be used for optimistic locking.