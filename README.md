def Connect_Fbx_to_Rigging():


    
    nsA = cmds.ls(sl=1)
    
    nsGet=[nsA[1]]
    print
    nsGet
    for i in nsGet:
########탬플릿 불러오고####
        mel.eval('file -import -type "mayaBinary"  -ignoreVersion -ra true -mergeNamespacesOnClash true -namespace ":" -options "v=0;"  -pr  -importFrameRate true "P:/tools/maya/2019/packages/rig_default/pythons/autoRigBiped/bipedautorig/test.mb";')

        if ":" in i :
            
            ns = i.split(":")[0]
            
            global ns
            
            cmds.connectAttr (ns+':'+'Ctl_world_C.scale', 'Ctl_world_LMOC.scale',f=1)
            cmds.disconnectAttr (ns+':'+'Ctl_world_C.scale', 'Ctl_world_LMOC.scale')

########템플릿 조인트 BJT연결하고 끊기                    
        WorldCTLs_List = nsA
        
        
        if len(WorldCTLs_List) ==2:
        
                    
            if 'Ctl_world_C' in WorldCTLs_List[1] and 'MOC' in WorldCTLs_List[0]:
              
                
                LMOC_List=['LMOC_thumb03_L', 'LMOC_thumb02_L', 'LMOCn_thumb02_L', 'LMOC_thumb01_L', 'LMOCn_thumb01_L', 'LMOC_thumb00_L', 'LMOCn_thumb00_L', 'LMOC_index04_L', 'LMOC_index03_L', 'LMOCn_index03_L', 'LMOC_index02_L', 'LMOCn_index02_L', 'LMOC_index01_L', 'LMOCn_index01_L', 'LMOC_index00_L', 'LMOCn_index00_L', 'LMOC_middle04_L', 'LMOC_middle03_L', 'LMOCn_middle03_L', 'LMOC_middle02_L', 'LMOCn_middle02_L', 'LMOC_middle01_L', 'LMOCn_middle01_L', 'LMOC_middle00_L', 'LMOCn_middle00_L', 'LMOC_ring04_L', 'LMOC_ring03_L', 'LMOCn_ring03_L', 'LMOC_ring02_L', 'LMOCn_ring02_L', 'LMOC_ring01_L', 'LMOCn_ring01_L', 'LMOC_ring00_L', 'LMOCn_ring00_L', 'LMOC_pinky04_L', 'LMOC_pinky03_L', 'LMOCn_pinky03_L', 'LMOC_pinky02_L', 'LMOCn_pinky02_L', 'LMOC_pinky01_L', 'LMOCn_pinky01_L', 'LMOC_pinky00_L', 'LMOCn_pinky00_L', 'LMOC_wrist_L', 'LMOC_foreArm02_L', 'LMOC_foreArm01_L', 'LMOC_foreArm00_L', 'LMOC_elbow_L', 'LMOCn_elbow_L', 'LMOC_biceps02_L', 'LMOC_biceps01_L', 'LMOC_biceps00_L', 'LMOC_shld_L', 'LMOCn_clav02_L', 'LMOC_clav01_L', 'LMOC_clav00_L', 'LMOCn_clav00_L', 'LMOC_index04_R', 'LMOC_index03_R', 'LMOCn_index03_R', 'LMOC_index02_R', 'LMOCn_index02_R', 'LMOC_index01_R', 'LMOCn_index01_R', 'LMOC_index00_R', 'LMOCn_index00_R', 'LMOC_middle04_R', 'LMOC_middle03_R', 'LMOCn_middle03_R', 'LMOC_middle02_R', 'LMOCn_middle02_R', 'LMOC_middle01_R', 'LMOCn_middle01_R', 'LMOC_middle00_R', 'LMOCn_middle00_R', 'LMOC_ring04_R', 'LMOC_ring03_R', 'LMOCn_ring03_R', 'LMOC_ring02_R', 'LMOCn_ring02_R', 'LMOC_ring01_R', 'LMOCn_ring01_R', 'LMOC_ring00_R', 'LMOCn_ring00_R', 'LMOC_pinky04_R', 'LMOC_pinky03_R', 'LMOCn_pinky03_R', 'LMOC_pinky02_R', 'LMOCn_pinky02_R', 'LMOC_pinky01_R', 'LMOCn_pinky01_R', 'LMOC_pinky00_R', 'LMOCn_pinky00_R', 'LMOC_thumb03_R', 'LMOC_thumb02_R', 'LMOCn_thumb02_R', 'LMOC_thumb01_R', 'LMOCn_thumb01_R', 'LMOC_thumb00_R', 'LMOCn_thumb00_R', 'LMOC_wrist_R', 'LMOC_foreArm02_R', 'LMOC_foreArm01_R', 'LMOC_foreArm00_R', 'LMOC_elbow_R', 'LMOCn_elbow_R', 'LMOC_biceps02_R', 'LMOC_biceps01_R', 'LMOC_biceps00_R', 'LMOC_shld_R', 'LMOCn_clav02_R', 'LMOC_clav01_R', 'LMOC_clav00_R', 'LMOCn_clav00_R', 'LMOCn_eye01_L', 'LMOC_eye00_L', 'LMOCn_eye01_R', 'LMOC_eye00_R', 'LMOC_head', 'LMOCn_neck03', 'LMOC_neck02', 'LMOC_neck01', 'LMOC_neck00', 'LMOCn_chest01', 'LMOC_chest', 'LMOCn_spine04', 'LMOC_spine03', 'LMOCn_spine03', 'LMOC_spine02', 'LMOCn_spine02', 'LMOC_spine01', 'LMOCn_spine01', 'LMOC_spine00_add', 'LMOCn_spine00', 'LMOC_toe_L', 'LMOC_ball_L', 'LMOC_ankle_L', 'LMOC_heel_L', 'LMOCn_heel_L', 'LMOCn_ankle_L', 'LMOC_calf02_L', 'LMOC_calf01_L', 'LMOC_calf00_L', 'LMOC_knee_L', 'LMOCn_knee_L', 'LMOC_thigh02_L', 'LMOC_thigh01_L', 'LMOC_thigh00_L', 'LMOC_hip_L', 'LMOCn_hip_L', 'LMOC_hip_L_pos', 'LMOC_toe_R', 'LMOC_ball_R', 'LMOC_ankle_R', 'LMOC_heel_R', 'LMOCn_heel_R', 'LMOCn_ankle_R_ofs', 'LMOCn_ankle_R', 'LMOC_calf02_R', 'LMOC_calf01_R', 'LMOC_calf00_R', 'LMOC_knee_R', 'LMOCn_knee_R', 'LMOC_thigh02_R', 'LMOC_thigh01_R', 'LMOC_thigh00_R', 'LMOC_hip_R', 'LMOCn_hip_R', 'LMOC_hip_R_pos', 'LMOC_spine00']
                print len(LMOC_List)
                BJT_List=['Bjt_thumb03_L', 'Bjt_thumb02_L', 'Bjtn_thumb02_L', 'Bjt_thumb01_L', 'Bjtn_thumb01_L', 'Bjt_thumb00_L', 'Bjtn_thumb00_L', 'Bjt_index04_L', 'Bjt_index03_L', 'Bjtn_index03_L', 'Bjt_index02_L', 'Bjtn_index02_L', 'Bjt_index01_L', 'Bjtn_index01_L', 'Bjt_index00_L', 'Bjtn_index00_L', 'Bjt_middle04_L', 'Bjt_middle03_L', 'Bjtn_middle03_L', 'Bjt_middle02_L', 'Bjtn_middle02_L', 'Bjt_middle01_L', 'Bjtn_middle01_L', 'Bjt_middle00_L', 'Bjtn_middle00_L', 'Bjt_ring04_L', 'Bjt_ring03_L', 'Bjtn_ring03_L', 'Bjt_ring02_L', 'Bjtn_ring02_L', 'Bjt_ring01_L', 'Bjtn_ring01_L', 'Bjt_ring00_L', 'Bjtn_ring00_L', 'Bjt_pinky04_L', 'Bjt_pinky03_L', 'Bjtn_pinky03_L', 'Bjt_pinky02_L', 'Bjtn_pinky02_L', 'Bjt_pinky01_L', 'Bjtn_pinky01_L', 'Bjt_pinky00_L', 'Bjtn_pinky00_L', 'Bjt_wrist_L', 'Bjt_foreArm02_L', 'Bjt_foreArm01_L', 'Bjt_foreArm00_L', 'Bjt_elbow_L', 'Bjtn_elbow_L', 'Bjt_biceps02_L', 'Bjt_biceps01_L', 'Bjt_biceps00_L', 'Bjt_shld_L', 'Bjtn_clav02_L', 'Bjt_clav01_L', 'Bjt_clav00_L', 'Bjtn_clav00_L', 'Bjt_index04_R', 'Bjt_index03_R', 'Bjtn_index03_R', 'Bjt_index02_R', 'Bjtn_index02_R', 'Bjt_index01_R', 'Bjtn_index01_R', 'Bjt_index00_R', 'Bjtn_index00_R', 'Bjt_middle04_R', 'Bjt_middle03_R', 'Bjtn_middle03_R', 'Bjt_middle02_R', 'Bjtn_middle02_R', 'Bjt_middle01_R', 'Bjtn_middle01_R', 'Bjt_middle00_R', 'Bjtn_middle00_R', 'Bjt_ring04_R', 'Bjt_ring03_R', 'Bjtn_ring03_R', 'Bjt_ring02_R', 'Bjtn_ring02_R', 'Bjt_ring01_R', 'Bjtn_ring01_R', 'Bjt_ring00_R', 'Bjtn_ring00_R', 'Bjt_pinky04_R', 'Bjt_pinky03_R', 'Bjtn_pinky03_R', 'Bjt_pinky02_R', 'Bjtn_pinky02_R', 'Bjt_pinky01_R', 'Bjtn_pinky01_R', 'Bjt_pinky00_R', 'Bjtn_pinky00_R', 'Bjt_thumb03_R', 'Bjt_thumb02_R', 'Bjtn_thumb02_R', 'Bjt_thumb01_R', 'Bjtn_thumb01_R', 'Bjt_thumb00_R', 'Bjtn_thumb00_R', 'Bjt_wrist_R', 'Bjt_foreArm02_R', 'Bjt_foreArm01_R', 'Bjt_foreArm00_R', 'Bjt_elbow_R', 'Bjtn_elbow_R', 'Bjt_biceps02_R', 'Bjt_biceps01_R', 'Bjt_biceps00_R', 'Bjt_shld_R', 'Bjtn_clav02_R', 'Bjt_clav01_R', 'Bjt_clav00_R', 'Bjtn_clav00_R', 'Bjtn_eye01_L', 'Bjt_eye00_L', 'Bjtn_eye01_R', 'Bjt_eye00_R', 'Bjt_head', 'Bjtn_neck03', 'Bjt_neck02', 'Bjt_neck01', 'Bjt_neck00', 'Bjtn_chest01', 'Bjt_chest', 'Bjtn_spine04', 'Bjt_spine03', 'Bjtn_spine03', 'Bjt_spine02', 'Bjtn_spine02', 'Bjt_spine01', 'Bjtn_spine01', 'Bjt_spine00_add', 'Bjtn_spine00', 'Bjt_toe_L', 'Bjt_ball_L', 'Bjt_ankle_L', 'Bjt_heel_L', 'Bjtn_heel_L', 'Bjtn_ankle_L', 'Bjt_calf02_L', 'Bjt_calf01_L', 'Bjt_calf00_L', 'Bjt_knee_L', 'Bjtn_knee_L', 'Bjt_thigh02_L', 'Bjt_thigh01_L', 'Bjt_thigh00_L', 'Bjt_hip_L', 'Bjtn_hip_L', 'Bjt_hip_L_pos', 'Bjt_toe_R', 'Bjt_ball_R', 'Bjt_ankle_R', 'Bjt_heel_R', 'Bjtn_heel_R', 'Bjtn_ankle_R_ofs', 'Bjtn_ankle_R', 'Bjt_calf02_R', 'Bjt_calf01_R', 'Bjt_calf00_R', 'Bjt_knee_R', 'Bjtn_knee_R', 'Bjt_thigh02_R', 'Bjt_thigh01_R', 'Bjt_thigh00_R', 'Bjt_hip_R', 'Bjtn_hip_R', 'Bjt_hip_R_pos', 'Bjt_spine00']
                print len(BJT_List)
                                           
                for i in range(len(BJT_List)):
          
    
                 
                    cmds.connectAttr (ns+':'+BJT_List[i]+'.translate', LMOC_List[i]+'.translate',f=1)
                
                    cmds.connectAttr (ns+':'+BJT_List[i]+'.rotate', LMOC_List[i]+'.rotate',f=1)
                    
                    cmds.setAttr (LMOC_List[i]+".jointOrientX" ,0)
                    cmds.setAttr (LMOC_List[i]+".jointOrientY" ,0)
                    cmds.setAttr (LMOC_List[i]+".jointOrientZ" ,0)
                
      
                

                                     

      



Connect_Fbx_to_Rigging()


BJT_Relative = cmds.listRelatives('R1'+':'+"GrpBjt_rig_ofs",ad=1,typ = 'joint')
print BJT_Relative

LMOC_Relative = cmds.listRelatives('GrpLMOC_rig_ofs',ad=1,typ = 'joint')
print  LMOC_Relative                   

         
            Ctl_taget_CTL_Base= ['Ctl_clav_R', 'Ctl_shld_R_fk_ga', 'Ctl_elbow_R_fk_ga', 'Ctl_wrist_R_fk_ga', 'Ctl_thumb00_R_gf', 'Ctl_thumb01_R_gf', 'Ctl_thumb02_R_gf', 'Ctl_index00_R_gf', 
                'Ctl_index01_R_gf', 'Ctl_index02_R_gf', 'Ctl_index03_R_gf', 'Ctl_middle00_R_gf', 'Ctl_middle01_R_gf', 'Ctl_middle02_R_gf', 'Ctl_middle03_R_gf', 'Ctl_ring00_R_gf', 'Ctl_ring01_R_gf', 'Ctl_ring02_R_gf', 
                'Ctl_ring03_R_gf', 'Ctl_pinky00_R_gf', 'Ctl_pinky01_R_gf', 'Ctl_pinky02_R_gf', 'Ctl_pinky03_R_gf', 'Ctl_clav_L', 'Ctl_shld_L_fk_ga', 'Ctl_elbow_L_fk_ga', 'Ctl_wrist_L_fk_ga', 'Ctl_thumb00_L_gf', 'Ctl_thumb01_L_gf',
                 'Ctl_thumb02_L_gf', 'Ctl_index00_L_gf', 'Ctl_index01_L_gf', 'Ctl_index02_L_gf', 'Ctl_index03_L_gf', 'Ctl_middle00_L_gf', 'Ctl_middle01_L_gf', 'Ctl_middle02_L_gf', 'Ctl_middle03_L_gf', 'Ctl_ring00_L_gf', 'Ctl_ring01_L_gf', 
                 'Ctl_ring02_L_gf', 'Ctl_ring03_L_gf', 'Ctl_pinky00_L_gf', 'Ctl_pinky01_L_gf', 'Ctl_pinky02_L_gf', 'Ctl_pinky03_L_gf', 'Ctl_root_C', 'Ctl_spine01_C_fk', 'Ctl_spineMid_C_fk', 'Ctl_spine03_C_fk', 'Ctl_spine_C_chestMove', 
                 'Ctl_neck_C_gn', 'Ctl_head_C_gh', 'Ctl_hip_R_fk_gl', 'Ctl_knee_R_fk_gl', 'Ctl_ankle_R_fk_gl', 'Ctl_ball_R_fk_gl', 'Ctl_hip_L_fk_gl', 'Ctl_knee_L_fk_gl', 'Ctl_ankle_L_fk_gl', 'Ctl_ball_L_fk_gl']

            Ctl_taget_CTL = [ns+":"+x for x in Ctl_taget_CTL_Base] 
   


            for i in range(len(Ctl_taget_CTL)):
                
                
                cmds.setAttr( Ctl_taget_CTL[i]+'.rotateX',k=1,lock=0)
                cmds.setAttr( Ctl_taget_CTL[i]+'.rotateY',k=1,lock=0)
                cmds.setAttr( Ctl_taget_CTL[i]+'.rotateZ',k=1,lock=0)
                
                cmds.setAttr( Ctl_taget_CTL[i]+'.translateX',k=1,lock=0)
                cmds.setAttr( Ctl_taget_CTL[i]+'.translateY',k=1,lock=0)
                cmds.setAttr( Ctl_taget_CTL[i]+'.translateZ',k=1,lock=0)


                




cmds.connectAttr (BJT_Relative[i]+'.rotate', MOC_Relative[i]+'.rotate',f=1)


'''

