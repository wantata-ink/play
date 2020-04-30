# play
training at local env

## Google Colab
webcam_tf1_14.ipynbを起動する  

## Requirements
Python3.7  

conda info -e #環境一覧表示
source activate (仮想環境名) #(sourceはWindowsの場合いらない)

conda install tensorflow keras numpy pillow
conda install scikit-image cython h5py scipy imgaug  
git clone ...  
python setup.py install #cocoapiのPythonAPIフォルダ下で  

mask_rcnn_coco.h5をダウンロードしてMask_RCNN下に保存  　
https://github.com/matterport/Mask_RCNN/releases  

## Error
Mask_RCNN/samples/demo.ipynbを実行すると  
AttributeError: module 'tensorflow' has no attribute 'log'  
tensorflowのバージョンが1.3を要求する.
model.pyの中身を変更
'''python
tf.log() -> tf.math.log()
tf.sets.set_intersection() -> tf.sets.intersection()
tf.sparse_tensor_to_dense() -> tf.sparse.to_dense()
tf.to_float() -> tf.cast([value], tf.float32)
'''  



https://ai-coordinator.jp/mask-r-cnn

## MAC
カーネル落ちないように対策
os.environ['KMP_DUPLICATE_LIB_OK']='TRUE'  


## Windows
Windowsの場合Cocoapiのインストールで
cl : コマンド ライン error D8021 : 数値型引数 '/Wno-cpp' は無効です。」が出たときは、pipでのinstallは諦めて
pip install git+https://github.com/philferriere/cocoapi.git#subdirectory=PythonAPI
