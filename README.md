# grid_legend


```
# use gTree
grid.newpage()
mylegend<-frameGrob()
mylegend<-packGrob(mylegend,textGrob("Legend 1"),row=1,col=1)
mylegend<-packGrob(mylegend,gTree(
  name="myplot",children=gList(
    rectGrob(name = "box", gp = gpar(col = "grey")),
    pointsGrob(x=0.5,y=0.5,name="xaxis"))),width=unit(1,"inch"),row=1,col=2)
mylegend<-packGrob(mylegend,textGrob("Legend 2"),row=2,col=1)
mylegend<-packGrob(mylegend,gTree(
  name="myplot",children=gList(
    rectGrob(name = "box", gp = gpar(col = "grey")),
    pointsGrob(x=0.5,y=0.5,name="xaxis"))),width=unit(1,"inch"),row=2,col=2)
mylegend<-packGrob(mylegend,textGrob("Legend 3"),row=3,col=1)
mylegend<-packGrob(mylegend,textGrob("Legend 4"),row=4,col=1)
mylegend<-packGrob(mylegend,textGrob("Legend 5"),row=5,col=1)
grid.draw(mylegend)



# completely Grob
mylegend<-frameGrob()
mylegend<-packGrob(mylegend,textGrob("Legend 1"),row=1,col=1,height=unit(1.25,"lines"))
mylegend<-packGrob(mylegend,textGrob("Legend 2"),row=2,col=1,height=unit(1.25,"lines"))
mylegend<-packGrob(mylegend,textGrob("Legend 3"),row=3,col=1,height=unit(1.25,"lines"))
mylegend<-packGrob(mylegend,textGrob("Legend 4"),row=4,col=1,height=unit(1.25,"lines"))
mylegend<-packGrob(mylegend,textGrob("Legend 5"),row=5,col=1,height=unit(1.25,"lines"))

mylegend<-packGrob(mylegend,nullGrob(),row=3,col=2,width=unit(1,"char"))

mylegend<-packGrob(mylegend,pointsGrob(x=0.5,y=0.5,size=unit(5,"points")),row=1,col=3,width=unit(3,"lines"))
mylegend<-packGrob(mylegend,linesGrob(x=c(0,1),y=c(0.5,0.5)),row=1,col=3,width=unit(3,"lines"))
mylegend<-packGrob(mylegend,pointsGrob(x=0.5,y=0.5,size=unit(5,"points")),row=2,col=3,width=unit(3,"lines"))
mylegend<-packGrob(mylegend,linesGrob(x=c(0,1),y=c(0.5,0.5)),row=2,col=3,width=unit(3,"lines"))
mylegend<-packGrob(mylegend,pointsGrob(x=0.5,y=0.5,size=unit(5,"points")),row=3,col=3,width=unit(3,"lines"))
mylegend<-packGrob(mylegend,pointsGrob(x=0.5,y=0.5,size=unit(5,"points")),row=4,col=3,width=unit(3,"lines"))
mylegend<-packGrob(mylegend,pointsGrob(x=0.5,y=0.5,size=unit(5,"points")),row=5,col=3,width=unit(3,"lines"))



grid.newpage()
pushViewport(viewport(width=0.9,height=0.9,gp=gpar(fontsize=5)))
grid.rect()

pushViewport(viewport(
  x=0,y=0,
  width=unit(1,"grobwidth",mylegend)+unit(2,"lines"),
  height=unit(1,"grobheight",mylegend)+unit(1,"lines"),
  just=c(0,0)))
grid.rect()
grid.draw(mylegend)

```


```
# completely placeGrob
mylegend<-frameGrob(layout=grid.layout(
  5,3,
  widths=unit(c(5,2,3),c("lines","char","lines")),
  heights=unit(rep(1.25,5),"lines")))
mylegend<-placeGrob(mylegend,textGrob("Legend 1"),row=1,col=1)
mylegend<-placeGrob(mylegend,textGrob("Legend 2"),row=2,col=1)
mylegend<-placeGrob(mylegend,textGrob("Legend 3"),row=3,col=1)
mylegend<-placeGrob(mylegend,textGrob("Legend 4"),row=4,col=1)
mylegend<-placeGrob(mylegend,textGrob("Legend 5"),row=5,col=1)

mylegend<-placeGrob(mylegend,pointsGrob(x=0.5,y=0.5,size=unit(5,"points")),row=1,col=3)
mylegend<-placeGrob(mylegend,linesGrob(x=c(0,1),y=c(0.5,0.5)),row=1,col=3)
mylegend<-placeGrob(mylegend,pointsGrob(x=0.5,y=0.5,size=unit(5,"points")),row=2,col=3)
mylegend<-placeGrob(mylegend,linesGrob(x=c(0,1),y=c(0.5,0.5)),row=2,col=3)
mylegend<-placeGrob(mylegend,pointsGrob(x=0.5,y=0.5,size=unit(5,"points")),row=3,col=3)
mylegend<-placeGrob(mylegend,pointsGrob(x=0.5,y=0.5,size=unit(5,"points")),row=4,col=3)
mylegend<-placeGrob(mylegend,pointsGrob(x=0.5,y=0.5,size=unit(5,"points")),row=5,col=3)


# test

grid.newpage()
pushViewport(viewport(width=0.9,height=0.9,gp=gpar(fontsize=5)))
grid.rect()

pushViewport(viewport(
  x=0,y=0,
  width=unit(1,"grobwidth",mylegend)+unit(2,"lines"),
  height=unit(1,"grobheight",mylegend)+unit(1,"lines"),
  just=c(0,0)))
grid.rect()
grid.draw(mylegend)
```


