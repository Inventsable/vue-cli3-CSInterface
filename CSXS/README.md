## CSXS/manifest.xml:

``` xml
<DispatchInfo>
  <Resources>
    <!-- Default (no hot reload) -->
    <!-- <MainPath>./index.html</MainPath> -->

    <!-- Dev build w/ hot reload -->
    <MainPath>./index-dev.html</MainPath>

    <CEFCommandLine>
      <Parameter>--enable-nodejs</Parameter>
      <!-- Doesn't show in Window > Extensions unless mixed content is enabled -->
      <Parameter>--mixed-context</Parameter>
    </CEFCommandLine>
  </Resources>
```
