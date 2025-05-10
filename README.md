# `value.json` - Idea Value Chain

> A value chain refers to the full lifecycle of a product or process, including material sourcing, production, consumption and disposal/recycling processes.”

For every new implementation/system

- what is added value compared to other pre-existing systems?
- what were the inspirations that lead to the creation of this new system?
- who/what does the author attribute the most value to, including him/itself?
- which inspirations/dependencies are obvious and therefore not attributed explicitly?

What if this can be estimated on a per-repo basis and turned into a structured format? This could be `value.json`, and could have the following datastructure:

```ts
type Value = {
  allocation: {
    /**
     * a URL linking to the origin of the value. should be as specific as possible
     *
     * Examples of sources include:
     *
     * - https://github.com/janwilmake (myself)
     * - https://openapis.org (an orginisation)
     * - https://claude.ai (a tool)
     */
    url: string;
    /**
     * the value would be a numeric relative representation of attributed value
     */
    value: number;
    /** The description is additional information of why the 'value' is attributed to the 'source'. This is useful for fairer down-stream value allocation.*/
    description: string;
  }[];
};
```

If every system would attribute its sources - or if we estimate this based on other information - we could calculate the optimal generated value distribution by finding these attributions/estimations all the way down the value chain.

To participate with the `value.json` convention, manually or automatically create a JSON file called `value.json` at the root of your repo/website and fill it according to the spec.

```json
{
  "$schema": "https://valuejson.com/value.schema.json",
  "sources": []
}
```

# TODO

- Turn this into a LLM filter+analysis that is done for any repo in a very cheap way.
- Make this accessible at https://github.valuejson.com/owner/repo
- Turn this into a plugin for uithub.
