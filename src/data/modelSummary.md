__
Layer (type)                     Output Shape          Param #     Connected to                     
====================================================================================================
convolution2d_6 (Convolution2D)  (None, 64, 44, 44)    1664        convolution2d_input_2[0][0]      
____________________________________________________________________________________________________
prelu_8 (PReLU)                  (None, 64, 44, 44)    123904      convolution2d_6[0][0]            
____________________________________________________________________________________________________
zeropadding2d_7 (ZeroPadding2D)  (None, 64, 48, 48)    0           prelu_8[0][0]                    
____________________________________________________________________________________________________
maxpooling2d_2 (MaxPooling2D)    (None, 64, 22, 22)    0           zeropadding2d_7[0][0]            
____________________________________________________________________________________________________
zeropadding2d_8 (ZeroPadding2D)  (None, 64, 24, 24)    0           maxpooling2d_2[0][0]             
____________________________________________________________________________________________________
convolution2d_7 (Convolution2D)  (None, 64, 22, 22)    36928       zeropadding2d_8[0][0]            
____________________________________________________________________________________________________
prelu_9 (PReLU)                  (None, 64, 22, 22)    30976       convolution2d_7[0][0]            
____________________________________________________________________________________________________
zeropadding2d_9 (ZeroPadding2D)  (None, 64, 24, 24)    0           prelu_9[0][0]                    
____________________________________________________________________________________________________
convolution2d_8 (Convolution2D)  (None, 64, 22, 22)    36928       zeropadding2d_9[0][0]            
____________________________________________________________________________________________________
prelu_10 (PReLU)                 (None, 64, 22, 22)    30976       convolution2d_8[0][0]            
____________________________________________________________________________________________________
averagepooling2d_3 (AveragePoolin(None, 64, 10, 10)    0           prelu_10[0][0]                   
____________________________________________________________________________________________________
zeropadding2d_10 (ZeroPadding2D) (None, 64, 12, 12)    0           averagepooling2d_3[0][0]         
____________________________________________________________________________________________________
convolution2d_9 (Convolution2D)  (None, 128, 10, 10)   73856       zeropadding2d_10[0][0]           
____________________________________________________________________________________________________
prelu_11 (PReLU)                 (None, 128, 10, 10)   12800       convolution2d_9[0][0]            
____________________________________________________________________________________________________
zeropadding2d_11 (ZeroPadding2D) (None, 128, 12, 12)   0           prelu_11[0][0]                   
____________________________________________________________________________________________________
convolution2d_10 (Convolution2D) (None, 128, 10, 10)   147584      zeropadding2d_11[0][0]           
____________________________________________________________________________________________________
prelu_12 (PReLU)                 (None, 128, 10, 10)   12800       convolution2d_10[0][0]           
____________________________________________________________________________________________________
zeropadding2d_12 (ZeroPadding2D) (None, 128, 12, 12)   0           prelu_12[0][0]                   
____________________________________________________________________________________________________
averagepooling2d_4 (AveragePoolin(None, 128, 5, 5)     0           zeropadding2d_12[0][0]           
____________________________________________________________________________________________________
flatten_2 (Flatten)              (None, 3200)          0           averagepooling2d_4[0][0]         
____________________________________________________________________________________________________
dense_4 (Dense)                  (None, 1024)          3277824     flatten_2[0][0]                  
____________________________________________________________________________________________________
prelu_13 (PReLU)                 (None, 1024)          1024        dense_4[0][0]                    
____________________________________________________________________________________________________
dropout_3 (Dropout)              (None, 1024)          0           prelu_13[0][0]                   
____________________________________________________________________________________________________
dense_5 (Dense)                  (None, 1024)          1049600     dropout_3[0][0]                  
____________________________________________________________________________________________________
prelu_14 (PReLU)                 (None, 1024)          1024        dense_5[0][0]                    
____________________________________________________________________________________________________
dropout_4 (Dropout)              (None, 1024)          0           prelu_14[0][0]                   
____________________________________________________________________________________________________
dense_6 (Dense)                  (None, 7)             7175        dropout_4[0][0]                  
____________________________________________________________________________________________________
activation_2 (Activation)        (None, 7)             0           dense_6[0][0]                    
____________________________________________________________________________________________________
Total params: 4845063
____________________________________________________________________________________________________