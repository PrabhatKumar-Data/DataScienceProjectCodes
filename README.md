# DataScienceProjectCodes

### Here You can find the project codes that can be very helpful



For multiple images

def img_test(i, rest):
  img = image.load_img(i, target_size=(224, 224))
  x = image.img_to_array(img)
  x = np.true_divide(x, 255)
  ## Scaling
  x=x/255
  x = np.expand_dims(x, axis=0)
  x = preprocess_input(x)


  preds = rest.predict(x)
  preds=np.argmax(preds, axis=1)
  print(preds)
  if preds==0:
    preds="The leaf is diseased cotton leaf"
  elif preds==1:
    preds="The leaf is diseased cotton plant"
  elif preds==2:
    preds="The leaf is fresh cotton leaf"
  else:
    preds="The leaf is fresh cotton plant"
  print (preds)
