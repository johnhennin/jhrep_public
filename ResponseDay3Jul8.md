Responses for Day 3, July 8

A. The reason we split the data into test sets and training sets is because one set (the training set) is used to create the model, whereas the test set is used to test the model on how it handles information that it hasn't seen before. If we trained the model on all the data, we'd have a model that's pretty good at predicting the training features, but probably not good at predicting any new features.

B. The relu function takes all the negative values in the model and sets them to zero, so they don't interfere with the actually helpful positive values in the model. The softmax function takes the logits outputted by the neural network and transforms them into probabilities that the input image belongs to each category. These probabilities add to 1. 10 neurons are used in the third and last layer to map to each type of clothing (since there are ten types of clothing).

C. The loss function chooses what value to minimize in the model (essentially the error quantity). The optimizer then actively adjusts the parameters of the model to minimize the loss.

D.
   1. The shape of the images training set is 60,000 images of 28 x 28 pixels (each pixel cooresponds with a number value, the computer doesn't directly work with pixels).
   
   2. The length of the labels training set is 60,000 (one for each image).
   
   3. The shape of the images test set is 10,000 images of again 28 x 28 pixels.
   
   4-6. This wasn't a question and, consequently, I'm not sure how to answer this, so here's my code if that helps:
   
      plt.figure(figsize=(6,3))
      plt.subplot(1, 2, 1)
      plt.imshow(x_test[random_int],cmap="binary")

      colors=[]
      for n in model.predict(x_test)[random_int]:
         if n==max(model.predict(x_test)[random_int]):
            colors.append("C0")
         else:
            colors.append("grey")
      plt.subplot(1, 2, 2)
      plt.bar(np.arange(0,10),model.predict(x_test)[random_int],color=colors)
      plt.xticks(np.unique(y_train))
      plt.ylim((0, max(model.predict(x_test)[random_int])+10))
      plt.yticks([]);
      
