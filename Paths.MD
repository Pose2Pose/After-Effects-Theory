#After Effects Theory

##Rotobeziér/auto-bezier
Rotobezier is nothing more than a bezier-curve where the handles are calculated automatically. The handles of any given point are influenced by its neighbouring points and a parameter we’ll call tension.

Consider a shape made with four point A,B,C and D:

- The direction of the handles of point B will be parallel to the line connecting A and C. 

- The length of the outtangent of point B. Is equal to the length of BC multiplied by 
(1- (tension/100)

Here’s a code-snippet:

```var myPoints = points();

var p1 = points()[0];
var p2 = points()[1];
var p3 = points()[2];

var ip1 = -length(p1,p3)*normalize(p2-p3)*0.33;
var ip2 = -length(p2,p1)*normalize(p3-p1)*0.33;
var ip3 = -length(p3,p2)*normalize(p1-p2)*0.33;

var op1 = -length(p1,p2)*normalize(p3-p2)*0.33;
var op2 = -length(p2,p3)*normalize(p1-p3)*0.33;
var op3 = -length(p3,p1)*normalize(p2-p1)*0.33;

var myInTangents = [ip1,ip2,ip3];
var myOutTangents = [op1,op2,op3];
thePath = createPath(myPoints, myInTangents, myOutTangents,true);
```
