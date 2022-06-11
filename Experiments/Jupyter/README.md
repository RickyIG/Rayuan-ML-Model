# Patch Notes

CopyFIX
---------
Freeze all layers
x = tf.keras.layers.GlobalAvgPool2D(name="global_avg_pool_2d")(efficientNet.output)
x = tf.keras.layers.Dense(512, activation='relu')(x)
x = tf.keras.layers.Dropout(0.7)(x)
x = tf.keras.layers.Dense(numberOfClass,activation='softmax')(x)

Copy2FIX
---------
Unfreeze all layers 
x = tf.keras.layers.GlobalAvgPool2D(name="global_avg_pool_2d")(efficientNet.output)
x = tf.keras.layers.Dense(512, activation='relu')(x)
x = tf.keras.layers.Dropout(0.7)(x)
x = tf.keras.layers.Dense(numberOfClass,activation='softmax')(x)


CopyFIX2
----------
Freeze all layers
x = Flatten()(efficientNet.output)
x = tf.keras.layers.Dense(1024,activation='relu')(x)
x = tf.keras.layers.Dropout(0.5)(x)
x = tf.keras.layers.Dense(numberOfClass,activation='softmax')(x)


CopyFIX3 (Best Model)
----------
Freeze [:-16] layers
x = Flatten()(efficientNet.output)
x = tf.keras.layers.Dense(1024,activation='relu')(x)
x = tf.keras.layers.Dropout(0.7)(x)
x = tf.keras.layers.Dense(numberOfClass,activation='softmax')(x)

Bisa dicoba versi trainable = True dengan layer tambahan (CopyFIX4)
Bisa dicoba versi trainable = True tanpa layer tambahan (CopyFIX5)

Coba : CopyFIX3 tetapi B7 (Copy6)
Coba : CopyFIX3 tetapi Nambah layer nambah dropout 2x (Copy7)
