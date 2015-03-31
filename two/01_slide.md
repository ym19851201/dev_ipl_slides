!SLIDE commandline incremental
## オブジェクト検出器

さっきめっちゃ時間かけて作ったXMLのことです(嫌な思い出)  
使います(Rubyで)  

まずは

    $ bundle init                        
    $ echo 'gem "ruby-opencv"' >> Gemfile
    $ bundle install --path vendor/bundle

!SLIDE subsection
# 何に使おうか？
## ~笑い男ごっこ編~

!SLIDE
さっきめっちゃ時間かけて作った検出器ではないものを使って顔検出  
(だって顔検出器OpenCVに入ってんだもん)  
→笑い男になれる！

<p><img src="http://bronzeback.cocolog-nifty.com/photos/uncategorized/2007/09/27/laughingman_2.gif" alt="" height="200"></p>

!SLIDE execute smaller
# これであなたも笑い男

    @@@ruby
    require 'opencv'
    include OpenCV

    def laughing_man(image, rect, laughing_man)
      image.set_roi rect
      laughing_man_resized = laughing_man.resize rect
      (image.rows * image.cols).times do |i|
        image[i] = laughing_man_resized[i] unless laughing_man_resized[i][0] == 0.0
      end
      image.reset_roi
    end

!SLIDE execute smaller
# これであなたも笑い男続き

    @@@ruby
    camera = CvCapture.open(0)
    face = CvHaarClassifierCascade::load("#{HAAR_CASCADE_PATH}/haarcascade_frontalface_default.xml")

    window = GUI::Window.new('camera')
    laughing_man_img = CvMat.load('LAUGHINGMAN_PATH/laughingman.png')

    while GUI::wait_key(50).nil?
      image = camera.query
      image = image.resize(CvSize.new(500, 350))

      face.detect_objects(image) do |face_rect|
        laughing_man(image, face_rect, laughing_man_img)
      end

      window.show image
    end

    window.destroy

!SLIDE
# 実演
## Demonstration

