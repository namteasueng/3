>이번 과제를 진행하면서 기하학적 변환을 통한 영상처리 분야의 효과에 대해서 알아보고 이를 코드로 구현하여 보았습니다. 직접 이미지를 입력하여 입력된 이미지와 출력된 이미지를 비교하여보니 변환 후의 이미지가 반듯하여 보기에도 좋았습니다. 이런 실습을 통하여 디지털 영상처리의 기하학적 변환에 대해서 좀 더 이해한 것 같아서 너무 기쁩니다. 물론 변환 과정을 코드로 구현하는 부분이 조금 어려웠지만 결과적으로 완성되어 너무 즐겁습니다.

```
let src = cv.imread('canvasInput');
let dst = new cv.Mat();
let dsize = new cv.Size(src.rows, src.cols);
let center = new cv.Point(src.cols / 2, src.rows / 2);
// You can try more different parameters
let M = cv.getRotationMatrix2D(center, 338, 1);
cv.warpAffine(src, dst, M, dsize, cv.INTER_LINEAR, cv.BORDER_CONSTANT, new cv.Scalar());
cv.imshow('canvasOutput', dst);
src.delete(); dst.delete(); M.delete();
```
