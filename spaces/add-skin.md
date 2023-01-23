---
description: >-
  Learn what a custom skin is and how to use one for your space with a custom
  domain.
---

# Add a skin

## What is a skin?

A skin is a custom color scheme which you can use for your space if it has a custom domain set up. The customization will be visible only on the custom domain and will not affect the color scheme of your space on https://snapshot.org.

{% hint style="info" %}
If you haven't setup a custom domain yet, head to [add-custom-domain.md](add-custom-domain.md "mention") to learn how you can do it.&#x20;
{% endhint %}

## Add a skin to your space

Head to your space settings on Snapshot and find the `Custom domain` section.&#x20;

Select a skin by scrolling through the list of available choices or by typing the name you are looking for. If none of them work for you, you can create a custom skin following the section below: [#create-a-custom-skin](add-skin.md#create-a-custom-skin "mention")&#x20;

Don't forget that the skin will **only be applied to the custom domain URL!**

![Snapshot skin selector.](../.gitbook/assets/capture-de-cran-2020-12-30-a-09.33.58.png)

That's it! You should be able to see the custom color scheme for your space on its custom domain  :tada:

## Create a custom skin

### 1. Fork the snapshot-spaces repository

Create a fork of the snapshot-spaces repository:

{% embed url="https://github.com/snapshot-labs/snapshot-spaces" %}

### 2. Add the styling for your space

Create a new file in the `skins` directory following the `my-space.scss` naming convention:

```bash
└── skins
    └── my-space.scss
```

Add your custom `scss` to the newly created file. The class name `.my-space` should match the filename you created. Make sure that you **edit only the values** (i.e. `#384aff` on the right-hand side and **do not change the properties** (i.e. `--primary-color)`.&#x20;

```css
.my-space {
  --primary-color: #384aff;
  --bg-color: white;
  --text-color: #586069;
  --link-color: #111111;
  --heading-color: #111111;
  --border-color: #d1d5da;
  --header-bg: white;
  --block-bg: transparent;
}
```

{% hint style="info" %}
Don't forget to change the file name **my-space.scss** and css selector **.my-space** to your space name.
{% endhint %}

You can have a look at a custom skin example by following [this link](https://github.com/snapshot-labs/snapshot-spaces/blob/master/skins/uniswap.scss).

### 3. Import the scss file&#x20;

Add the import of your newly created `scss` file to the [skins/index.js](https://github.com/snapshot-labs/snapshot-spaces/blob/master/skins/index.js) file in the following format:

```css
import my-space from "./my-space.scss";
```

### 4. Create a pull request

Create a Pull Request with the above changes on the original [snapshot-spaces](https://github.com/snapshot-labs/snapshot-spaces/) repo.

The review can take the team up to 72 hours, so please be patient :pray:

After the PR has been merged, you will need to wait for the release of a new version of [Snapshot](https://github.com/snapshot-labs/snapshot) which can take a couple of days. Once it's deployed you can move on to the next step.

### 5. Update your space settings

Follow the steps from [#add-a-skin-to-your-space](add-skin.md#add-a-skin-to-your-space "mention") to use your own custom skin.
