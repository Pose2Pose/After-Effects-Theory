var myPoints = points();

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

