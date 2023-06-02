# Adding more networks in the code
## 1. To display the downloaded image of the network go to the  SnapShotService/src/assets folder and save  your image of the network
## 2. Go to the features.astro file which is present in SnapShotService/src/components. Over there you see all the code with respect to the networks also import the picture that you stored .Now to display the image and the link to a external file just make the required changes on the sample format :
```bash
   <Picture
      src={Quicksilver}
      alt="image"
      widths={[700,700, 700]}
      aspectRatio="1:1"
      sizes="(max-width: 300px) 30vw, 400px"
      loading="eager"
      format="avif"
      class="img"
      
      
    />
    <br>
     <span style="margin-left: 100px;font-weight: bold;"><a href ="/quicksilver">Quicksilver</a> </span>
              
    </a>
```

## 3. Now go to the following file SnapShotService/src/pages/  and add a file with the name of your network with any extension like html or astro

## 4.Now copy any other network files present
## 5. Open your file and just change the chain name to the name of your chain present in the file that you are trying to fetch data from.
```bash
 if (c['chain-name'] === 'desmos')
 ```
 ## 6.Whereever you find the other network name replace it with the new network