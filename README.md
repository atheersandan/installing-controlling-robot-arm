# installing-controlling-robot-arm
المهمة الاولى:
تثبيت وتشغيل الذراع الالية على نظام روز
قمت بتحميل برنامج virtual box 
ثم اضافة ubuntu melodic لجهازي 
قمت بفتح برنامج virtual box 
تسجيل الدخول ومن ثما فتح خانة treminal 
كتابة الاكواد التالية:
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
لتهيئة الجهاز لتثبيت نظام روز
sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
لكي نستطيع فتح keyserver بالجهاز 
sudo apt-get update
لتحديث النظام 
sudo apt-get install ros-melodic-desktop-full
apt-cache search ros-melodic
يختص الامران بتحميل نظام الروز والبحث عنه بالجهاز 
echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
source ~/.bashrc
sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential
sudo apt install python-rosdep
sudo rosdep init
rosdep update
تتعلق الاوامر التي في الاعلى بتثبيت وتحديث ros dependency
المهمة الثانية :
تثبيت وتشغيل الذراع الالي على ROS noetic 
sudo apt-get install ros-noetic-catkin
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/
catkin_make
cd ~/catkin_ws/src
git clone https://github.com/smart-methods/arduino_robot_arm.git
cd ~/catkin_ws
اما الاوامر هذه فهي مسؤوله عن تحميل catkin بالاضافه الي فتح مساحة للمشروع واضافة باكج الذراع
المهمة الثالثة:
ربط نظام ROS مع لوحة التحكم 
rosdep install --from-paths src --ignore-src -r -y
sudo apt-get install ros-melodic-moveit
sudo apt-get install ros-melodic-joint-state-publisher ros-melodic-joint-state-publisher-gui
sudo apt-get install ros-melodic-gazebo-ros-control joint-state-publisher
udo apt-get install ros-melodic-ros-controllers ros-melodic-ros-control
هذه الاوامر تقوم بتشغيل البرنامج الذي يجعلنا نشغل الذراع ونقوم بتحريكه وذلك بعدة اوامر منها اظهار الذراع ثلاثي الابعاد واظهار لوحة التحكم 
sudo nano ~/.bashrc
تفتح لنا صفحة في اسفلها وضعت الامر التالي
source /home/atheer/catkin_ws/devel/setup.bash
then ctrl+o then ctrl+x to sign out
اخيرا لفتح البرنامج قمت بوضع الامريين التاليين بخانة الترمينال 
source ~/.bashrc
roslaunch robot_arm_pkg check_motors.launch
الصعوبات التي واجهتني:
كانت كل البرامج جديدة تماما علي مما اخذ مني وقتا لتعلمه ومعرفة الكثير عن نظام الروز 
صعوبة اللصق في التريمنال لانه لايمكن اللصق من خارج virtual box 
قمت بكتابة الاكواد بطريقة خطأ مما جعلني اكرر اوامر واتفقد سبب المشكلة 
تحميل نسخ من البرامج لا تتطابق مع الاكواد التي وضعتها او نظام الروز المطلوب 
قمت بتغير من نظام الروز الكيناتيك الى الميلوديك 
واجهة صعوبة في عدم القدرة على التحكم بالذراع وذلك لاني اخطأت عندما اخترت نظام الروز الكيناتيك 
ايضا صعوبة التعامل مع github لاول مرة 
الانجاز/الهدف:
استطعت تحريك الذراع الالية
تعلم نظام ros
تعلم virtual box 
