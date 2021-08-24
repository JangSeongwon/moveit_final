# moveit_final

dualarm 과제를 위한 moveit final

urdf 파일을 이용해서 moveit 의 setup assistant 이용해서 config 생성 (mani1 이름으로 생성했음)  

dualarm assembly에서 바로 urdf를 만들지 못해 각각 팔을 만든 후 베이스에 연결함.

moveit assistant에서 move group 뿐 아니라 eef 그룹도 생성해주어야 함(현재는 그냥 eef link만 선택)

gripper 끝을 last position으로 잡고 플래닝 하기 위해서는 last joint coordinate를 거기에 위치시켜야 할 것 --> urdf 만들 시 주의


final_gazebo = https://github.com/eYSIP-2017/eYSIP-2017_Robotic_Arm/wiki/Interfacing-MoveIt%21-with-Gazebo
위의 링크에서 참조할 때. git에서 다운받은 폴더. (moveit setup assistant를 통해 자동으로 생성되지는 않음)
이 폴더안에 config/launch 파일들을 우리 manipulator에 맞게 수정해서 사용했었음.

move_robot = c++/c/python 이용해서 메니퓰레이터 제어하는 코드들 모음폴더


무빗과 가제보 연동 했을 때 무빗에서는 플래닝 되는데 가제보에서 execute 안 되던 이유 해결방법
(Unable to identify any set of controllers that can actuate the specified joints 라는 에러가 발생함)
: ros_controllers.yaml 의 controller list 가 []으로 남아있었기 때문인듯.
참고 링크
https://answers.ros.org/question/320990/moveit-unable-to-identify-any-set-of-controllers/   


1. roslaunch final_gazebo robotic_arm_bringup_gazebo.launch   

2. roslaunch final_gazebo robotic_arm_bringup_rviz.launch      


--------------------------------

ver2. limit   
joint 4 : +- 120   
joint 5 : +- 130

