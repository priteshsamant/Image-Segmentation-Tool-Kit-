# Image-Segmentation-Tool-Kit-
PyQt4 GUI based app for  analysis of different image segmentation algorithm. All algorithm is in python language.

Needed library : skimage, PIL, numpy, pyqt4, python 2.7

And then use command on Linux : python cur_work.py

# Simple and Efficient Seeded Region Growth Algorithm
      Hi friends ! In my file Region_grow.py has 3 different approach for region growth algorithm.
      In first one is region_grow_point in which I take one seed point and every time key of region
      growth is the difference between this seed and another point.But it is inefficient and not gonna 
      work proper. Just think we have some point in cluster and we want to know, whether  an another point
      should be include in this cluster or not. What should be our approach ? A single point  can not 
      represent the property of whole cluster. We see many objects in our daily life ,the colour of whole
      object never looks uniform, even if the colour of whole object is uniform. So I assume our brain 
      always consider the average colour of object. This is key point for second function implementation
      region_grow_avg. Here I include the point into the cluster on the basis of difference between average 
      of cluster point and given point.   
      But it is also not very accurate in some cases like gradient colour images, hmm Its gonna some complex,
      however let us try to understand . 
      Assume if we have a gradient image ( 100 * 200 ) of red colour ,colour intensity is decreasing through
      height and   increasing through width. Now we apply 2nd algorithm for this image. lets our threshold is 
      30 and current seed is (220,23,23).
      if our region grow in direction where the intensity of our colour is lower but difference is under the 
      thresold. Then our average of cluster is being lower.  After some growth there may be a chance that average
      of point become sufficient lower that it may not include some point in cluster which should be include in 
      the cluster on the basis of before selected seed point. 
        Assume if we have a gradient image ( 100 * 200 ) of red colour ,colour intensity is decreasing through 
        height and increasing through width. Now we apply 2nd algorithm for this image. lets our threshold is 
        30 and current seed is (220,23,23).
      if our region grow in direction where the intensity of our colour is lower but difference is under the 
      thresold. Then our average of cluster is being lower.  After some growth there may be a chance that 
      average of point become sufficient lower that it may not include some point in cluster which should be
      include in the cluster on the basis of before selected seed point.  So my third approach is we should 
      have to include the point in the cluster on the basis of increasing difference of average of cluster and
      given point. For it i use priority queue ,see function #region_grow_priorityQ . This become very efficient
      algorithm I tested it in many images it give me very satisfactry result.
      
      
    
