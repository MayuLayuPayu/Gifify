# Gifify
[Preview](https://imgur.com/1LTvFPn)

# How to use

```cs
private IEnumerator Gifify(GameObject background)
{
    var gificon = Gif.GetGifFrameFromURL("https://i.ibb.co/VgQKbBP/933301673391161344-1.gif");
    RawImage rawr_x3 = null;

    while (true)
    {
        if (!background.activeInHierarchy)
            yield return new WaitForEndOfFrame();
        else 
        {
            if (!background.GetComponent<RawImage>())
                rawr_x3 = background.AddComponent<RawImage>();
            for (int i = 0; i < gificon.Length; i++) 
            {
                rawr_x3.texture = gificon[i];
                yield return new WaitForSeconds(0.1f); //change depending on gif frame
            }
        }
    }
}
```
