# Fast-R-CNN
##R-CNN
*각각의 warped image를 convolutional net에 통과 => 계산량 많음
*svm사용=>backpropagation 안 됨
*region proposal에서 뽑아낸 feature들을 disk에 써야함
##SPPnet
*R-CNN의 약점을 보완하기 위해 convolutional net에 통과시키도 난 뒤 region proposal 각각의 coordinate 부분을 찾아감
*그럼에도 svm 사용으로 backpropagation 사용 불가능
*SPP(Spatial Pyramid Pooling)는 fine tuning할 때 업데이트가 불가능해서 정확도에 한계가 있음
##Fast R-CNN
*single stage tast ==> classification과 regression을 하나의 loss에 넣어서 backpropagation을 할 수 있다.
*convolutional net을 통과면 마지막 max pooling layer에 ROI pooling을 함
*SGD할 때 hierarchical sampling 방식 채택 => 각 ROI가 feature를 많이 공유해서 계산이 쉬움
*정확성과 시간 측면에서 R-CNN과 SPPnet보다 강점을 보임
