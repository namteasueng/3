>이번 과제를 진행하면서 영상처리 분야의 히스토그램에 대해서 알아보고 이를 코드로 구현하여 보았습니다. 직접 이미지를 입력하여 입력된 이미지와 출력된 이미지를 비교하여보니 흐릿한 이미지나 이미지의 밝기(혹은 이미지의 명암)가 큰 편차가 없는 이미지에서 히스토그램 스트래칭 및 평탄화로 완성된 이미지가 더욱 눈에 들어왔습니다. 이런 실습을 통하여 디지털영처리에 대해서 좀 더 이해한것 같아서 너무 기쁩니다. 물론 코드를 히스토그램 평탄화 과정을 코드로 구현하는 구간이 조금 어려웠지만 웹검색과 chat GPT의 도움을 받아서 결과적으로 완성되어 너무 즐겁습니다.
'''
let src = cv.imread('canvasInput');
let dst = new cv.Mat();
let dsize = new cv.Size(src.rows, src.cols);
let center = new cv.Point(src.cols / 2, src.rows / 2);
// You can try more different parameters
let M = cv.getRotationMatrix2D(center, 338, 1);
cv.warpAffine(src, dst, M, dsize, cv.INTER_LINEAR, cv.BORDER_CONSTANT, new cv.Scalar());
cv.imshow('canvasOutput', dst);
src.delete(); dst.delete(); M.delete();
'''
