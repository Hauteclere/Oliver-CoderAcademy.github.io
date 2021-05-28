# Subresource Integrity Cheatsheet:

## When to apply SRI:
Because subresource integrity operates by creating a hash based on the current state of your linked resources, it's better to add the `integrity="...` attribute to your HTML `<link>` element AFTER the linked resource is complete. If you apply SRI while you're still in the drafting phase, you'll have to re-calculate the hash every time you change the code, and that's a pain.

## Steps to Applying SRI:

### 1: calculate a hash of your resource.
* If your resource is local, you can do this via bash with the following command:
    ```Bash
        shasum -b -a <HASH_TYPE> <FILENAME> | awk '{ print $1 }' | xxd -r -p | base64
    ```
    Substituting either 512, 384 or 256 in for `<HASH_TYPE>`, and the name of your file for `<FILENAME>`
<br><br>
* If your resource is live on the web, you can also use [the srihash.org hash generator](https://www.srihash.org/). 
* There are plenty of other tools out there! 

### 2: Add the `integrity` attribute to the resource `<link>` in your html.
`integrity` should be equal to a long string, where each hash is prefixed by it's hashtype

For example:
```Html
    <link rel="stylesheet" href="styles.css" integrity="sha256-<SHA256_HASH_HERE> sha384-<SHA384_HASH_HERE> sha512-<SHA_512_HASH_HERE>"/>
```

### 3: There is no step three, it's literally that simple :D