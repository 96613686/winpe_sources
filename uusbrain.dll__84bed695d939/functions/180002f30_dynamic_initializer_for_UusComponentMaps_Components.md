# _dynamic_initializer_for__UusComponentMaps::Components__

- ea: `0x180002f30`
- end: `0x180004659`
- name: `_dynamic_initializer_for__UusComponentMaps::Components__`
- size: `5929`
- prototype: `int()`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180002f30`
- `0x180009c38`
- `0x18000f84c`
- `0x18001b030`
- `0x180028728`
- `0x180029518`
- `0x180029644`
- `0x18003a910`
- `0x18003efd8`
- `0x18003f3d0`
- `0x180042ba4`
- `0x180042bfc`
- `0x180043404`
- `0x1800479c0`

## string_xrefs

- `0x18000305f`: `updatecli`
- `0x180003594`: `WaasMedicAgent`
- `0x180003a81`: `WuStoreAuthPlugin`
- `0x180003b87`: `WuUpdatePolicy`

## pseudocode

```c
int dynamic_initializer_for__UusComponentMaps::Components__()
{
  char *v0; // rcx
  _QWORD *v1; // r12
  int *v2; // r14
  __int64 v3; // rax
  __int128 v4; // xmm6
  __int64 v5; // rdi
  char *v6; // rsi
  _BYTE *v8; // [rsp+20h] [rbp-E0h]
  int *v9; // [rsp+30h] [rbp-D0h] BYREF
  int *v10; // [rsp+38h] [rbp-C8h]
  int v11; // [rsp+40h] [rbp-C0h] BYREF
  int v12; // [rsp+44h] [rbp-BCh] BYREF
  int v13; // [rsp+48h] [rbp-B8h] BYREF
  int v14; // [rsp+4Ch] [rbp-B4h] BYREF
  __int128 v15; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v16; // [rsp+60h] [rbp-A0h]
  __int128 v17; // [rsp+70h] [rbp-90h] BYREF
  __int64 v18; // [rsp+80h] [rbp-80h]
  __int128 v19; // [rsp+88h] [rbp-78h] BYREF
  __int64 v20; // [rsp+98h] [rbp-68h]
  __int128 v21; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v22; // [rsp+B0h] [rbp-50h]
  __int128 v23; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v24; // [rsp+C8h] [rbp-38h]
  __int128 v25; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v26; // [rsp+E0h] [rbp-20h]
  __int128 v27; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v28; // [rsp+F8h] [rbp-8h]
  __int128 v29; // [rsp+100h] [rbp+0h] BYREF
  __int64 v30; // [rsp+110h] [rbp+10h]
  __int128 v31; // [rsp+118h] [rbp+18h] BYREF
  __int64 v32; // [rsp+128h] [rbp+28h]
  __int128 v33; // [rsp+130h] [rbp+30h] BYREF
  __int64 v34; // [rsp+140h] [rbp+40h]
  __int128 v35; // [rsp+148h] [rbp+48h] BYREF
  __int64 v36; // [rsp+158h] [rbp+58h]
  __int128 v37; // [rsp+160h] [rbp+60h] BYREF
  __int64 v38; // [rsp+170h] [rbp+70h]
  _OWORD v39[2]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v40[24]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v41; // [rsp+1B8h] [rbp+B8h]
  __int64 v42; // [rsp+1C0h] [rbp+C0h]
  _OWORD v43[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v44[24]; // [rsp+1F0h] [rbp+F0h] BYREF
  int v45; // [rsp+208h] [rbp+108h]
  __int64 v46; // [rsp+210h] [rbp+110h]
  _OWORD v47[2]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v48[24]; // [rsp+240h] [rbp+140h] BYREF
  int v49; // [rsp+258h] [rbp+158h]
  __int64 v50; // [rsp+260h] [rbp+160h]
  _OWORD v51[2]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v52[24]; // [rsp+290h] [rbp+190h] BYREF
  int v53; // [rsp+2A8h] [rbp+1A8h]
  __int64 v54; // [rsp+2B0h] [rbp+1B0h]
  _OWORD v55[2]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v56[24]; // [rsp+2E0h] [rbp+1E0h] BYREF
  int v57; // [rsp+2F8h] [rbp+1F8h]
  __int64 v58; // [rsp+300h] [rbp+200h]
  _OWORD v59[2]; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v60[24]; // [rsp+330h] [rbp+230h] BYREF
  int v61; // [rsp+348h] [rbp+248h]
  __int64 v62; // [rsp+350h] [rbp+250h]
  _OWORD v63[2]; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v64[24]; // [rsp+380h] [rbp+280h] BYREF
  int v65; // [rsp+398h] [rbp+298h]
  __int64 v66; // [rsp+3A0h] [rbp+2A0h]
  _OWORD v67[2]; // [rsp+3B0h] [rbp+2B0h] BYREF
  _BYTE v68[24]; // [rsp+3D0h] [rbp+2D0h] BYREF
  int v69; // [rsp+3E8h] [rbp+2E8h]
  __int64 (__fastcall *v70)(); // [rsp+3F0h] [rbp+2F0h]
  _OWORD v71[2]; // [rsp+400h] [rbp+300h] BYREF
  _BYTE v72[24]; // [rsp+420h] [rbp+320h] BYREF
  int v73; // [rsp+438h] [rbp+338h]
  __int64 (__fastcall *v74)(); // [rsp+440h] [rbp+340h]
  _OWORD v75[2]; // [rsp+450h] [rbp+350h] BYREF
  _BYTE v76[24]; // [rsp+470h] [rbp+370h] BYREF
  int v77; // [rsp+488h] [rbp+388h]
  __int64 v78; // [rsp+490h] [rbp+390h]
  _OWORD v79[2]; // [rsp+4A0h] [rbp+3A0h] BYREF
  _BYTE v80[24]; // [rsp+4C0h] [rbp+3C0h] BYREF
  int v81; // [rsp+4D8h] [rbp+3D8h]
  __int64 v82; // [rsp+4E0h] [rbp+3E0h]
  _OWORD v83[2]; // [rsp+4F0h] [rbp+3F0h] BYREF
  _BYTE v84[24]; // [rsp+510h] [rbp+410h] BYREF
  int v85; // [rsp+528h] [rbp+428h]
  __int64 v86; // [rsp+530h] [rbp+430h]
  _OWORD v87[2]; // [rsp+540h] [rbp+440h] BYREF
  _BYTE v88[24]; // [rsp+560h] [rbp+460h] BYREF
  int v89; // [rsp+578h] [rbp+478h]
  __int64 v90; // [rsp+580h] [rbp+480h]
  _OWORD v91[2]; // [rsp+590h] [rbp+490h] BYREF
  _BYTE v92[24]; // [rsp+5B0h] [rbp+4B0h] BYREF
  int v93; // [rsp+5C8h] [rbp+4C8h]
  __int64 v94; // [rsp+5D0h] [rbp+4D0h]
  _OWORD v95[2]; // [rsp+5E0h] [rbp+4E0h] BYREF
  _BYTE v96[24]; // [rsp+600h] [rbp+500h] BYREF
  int v97; // [rsp+618h] [rbp+518h]
  __int64 v98; // [rsp+620h] [rbp+520h]
  _OWORD v99[2]; // [rsp+630h] [rbp+530h] BYREF
  _BYTE v100[24]; // [rsp+650h] [rbp+550h] BYREF
  int v101; // [rsp+668h] [rbp+568h]
  __int64 (__fastcall *v102)(); // [rsp+670h] [rbp+570h]
  _OWORD v103[2]; // [rsp+680h] [rbp+580h] BYREF
  _BYTE v104[24]; // [rsp+6A0h] [rbp+5A0h] BYREF
  int v105; // [rsp+6B8h] [rbp+5B8h]
  __int64 v106; // [rsp+6C0h] [rbp+5C0h]
  _OWORD v107[2]; // [rsp+6D0h] [rbp+5D0h] BYREF
  _BYTE v108[24]; // [rsp+6F0h] [rbp+5F0h] BYREF
  int v109; // [rsp+708h] [rbp+608h]
  __int64 v110; // [rsp+710h] [rbp+610h]
  _OWORD v111[2]; // [rsp+720h] [rbp+620h] BYREF
  _BYTE v112[24]; // [rsp+740h] [rbp+640h] BYREF
  int v113; // [rsp+758h] [rbp+658h]
  __int64 (__fastcall *v114)(); // [rsp+760h] [rbp+660h]
  _OWORD v115[2]; // [rsp+770h] [rbp+670h] BYREF
  _OWORD v116[2]; // [rsp+790h] [rbp+690h] BYREF
  _OWORD v117[2]; // [rsp+7B0h] [rbp+6B0h] BYREF
  _OWORD v118[2]; // [rsp+7D0h] [rbp+6D0h] BYREF
  _OWORD v119[2]; // [rsp+7F0h] [rbp+6F0h] BYREF
  _OWORD v120[2]; // [rsp+810h] [rbp+710h] BYREF
  _OWORD v121[2]; // [rsp+830h] [rbp+730h] BYREF
  _OWORD v122[2]; // [rsp+850h] [rbp+750h] BYREF
  _OWORD v123[2]; // [rsp+870h] [rbp+770h] BYREF
  _OWORD v124[2]; // [rsp+890h] [rbp+790h] BYREF
  _OWORD v125[2]; // [rsp+8B0h] [rbp+7B0h] BYREF
  _OWORD v126[2]; // [rsp+8D0h] [rbp+7D0h] BYREF
  _OWORD v127[2]; // [rsp+8F0h] [rbp+7F0h] BYREF
  _OWORD v128[2]; // [rsp+910h] [rbp+810h] BYREF
  _OWORD v129[2]; // [rsp+930h] [rbp+830h] BYREF
  _OWORD v130[2]; // [rsp+950h] [rbp+850h] BYREF
  _OWORD v131[2]; // [rsp+970h] [rbp+870h] BYREF
  _OWORD v132[2]; // [rsp+990h] [rbp+890h] BYREF
  _OWORD v133[2]; // [rsp+9B0h] [rbp+8B0h] BYREF
  _BYTE v134[24]; // [rsp+9D0h] [rbp+8D0h] BYREF
  _BYTE v135[24]; // [rsp+9E8h] [rbp+8E8h] BYREF
  _BYTE v136[24]; // [rsp+A00h] [rbp+900h] BYREF
  _BYTE v137[24]; // [rsp+A18h] [rbp+918h] BYREF
  _BYTE v138[24]; // [rsp+A30h] [rbp+930h] BYREF
  _BYTE v139[24]; // [rsp+A48h] [rbp+948h] BYREF
  _BYTE v140[24]; // [rsp+A60h] [rbp+960h] BYREF
  _BYTE v141[24]; // [rsp+A78h] [rbp+978h] BYREF
  _BYTE v142[32]; // [rsp+A90h] [rbp+990h] BYREF
  _BYTE v143[32]; // [rsp+AB0h] [rbp+9B0h] BYREF
  _BYTE v144[24]; // [rsp+AD0h] [rbp+9D0h] BYREF
  int v145; // [rsp+AE8h] [rbp+9E8h] BYREF
  __int64 v146; // [rsp+AF0h] [rbp+9F0h]
  _BYTE v147[32]; // [rsp+AF8h] [rbp+9F8h] BYREF
  _BYTE v148[32]; // [rsp+B18h] [rbp+A18h] BYREF
  _BYTE v149[24]; // [rsp+B38h] [rbp+A38h] BYREF
  int v150; // [rsp+B50h] [rbp+A50h]
  __int64 v151; // [rsp+B58h] [rbp+A58h]
  _BYTE v152[32]; // [rsp+B60h] [rbp+A60h] BYREF
  _BYTE v153[32]; // [rsp+B80h] [rbp+A80h] BYREF
  _BYTE v154[24]; // [rsp+BA0h] [rbp+AA0h] BYREF
  int v155; // [rsp+BB8h] [rbp+AB8h]
  __int64 v156; // [rsp+BC0h] [rbp+AC0h]
  _BYTE v157[32]; // [rsp+BC8h] [rbp+AC8h] BYREF
  _BYTE v158[32]; // [rsp+BE8h] [rbp+AE8h] BYREF
  _BYTE v159[24]; // [rsp+C08h] [rbp+B08h] BYREF
  int v160; // [rsp+C20h] [rbp+B20h]
  __int64 v161; // [rsp+C28h] [rbp+B28h]
  _BYTE v162[32]; // [rsp+C30h] [rbp+B30h] BYREF
  _BYTE v163[32]; // [rsp+C50h] [rbp+B50h] BYREF
  _BYTE v164[24]; // [rsp+C70h] [rbp+B70h] BYREF
  int v165; // [rsp+C88h] [rbp+B88h]
  __int64 v166; // [rsp+C90h] [rbp+B90h]
  _BYTE v167[32]; // [rsp+C98h] [rbp+B98h] BYREF
  _BYTE v168[32]; // [rsp+CB8h] [rbp+BB8h] BYREF
  _BYTE v169[24]; // [rsp+CD8h] [rbp+BD8h] BYREF
  int v170; // [rsp+CF0h] [rbp+BF0h]
  __int64 v171; // [rsp+CF8h] [rbp+BF8h]
  _BYTE v172[32]; // [rsp+D00h] [rbp+C00h] BYREF
  _BYTE v173[32]; // [rsp+D20h] [rbp+C20h] BYREF
  _BYTE v174[24]; // [rsp+D40h] [rbp+C40h] BYREF
  int v175; // [rsp+D58h] [rbp+C58h]
  __int64 (__fastcall *v176)(); // [rsp+D60h] [rbp+C60h]
  _BYTE v177[32]; // [rsp+D68h] [rbp+C68h] BYREF
  _BYTE v178[32]; // [rsp+D88h] [rbp+C88h] BYREF
  _BYTE v179[24]; // [rsp+DA8h] [rbp+CA8h] BYREF
  int v180; // [rsp+DC0h] [rbp+CC0h]
  __int64 (__fastcall *v181)(); // [rsp+DC8h] [rbp+CC8h]
  _BYTE v182[32]; // [rsp+DD0h] [rbp+CD0h] BYREF
  _BYTE v183[32]; // [rsp+DF0h] [rbp+CF0h] BYREF
  _BYTE v184[24]; // [rsp+E10h] [rbp+D10h] BYREF
  int v185; // [rsp+E28h] [rbp+D28h]
  __int64 (__fastcall *v186)(); // [rsp+E30h] [rbp+D30h]
  _BYTE v187[32]; // [rsp+E38h] [rbp+D38h] BYREF
  _BYTE v188[32]; // [rsp+E58h] [rbp+D58h] BYREF
  _BYTE v189[24]; // [rsp+E78h] [rbp+D78h] BYREF
  int v190; // [rsp+E90h] [rbp+D90h]
  __int64 v191; // [rsp+E98h] [rbp+D98h]
  _BYTE v192[32]; // [rsp+EA0h] [rbp+DA0h] BYREF
  _BYTE v193[32]; // [rsp+EC0h] [rbp+DC0h] BYREF
  _BYTE v194[24]; // [rsp+EE0h] [rbp+DE0h] BYREF
  int v195; // [rsp+EF8h] [rbp+DF8h]
  __int64 v196; // [rsp+F00h] [rbp+E00h]
  _BYTE v197[32]; // [rsp+F08h] [rbp+E08h] BYREF
  _BYTE v198[32]; // [rsp+F28h] [rbp+E28h] BYREF
  _BYTE v199[24]; // [rsp+F48h] [rbp+E48h] BYREF
  int v200; // [rsp+F60h] [rbp+E60h]
  __int64 v201; // [rsp+F68h] [rbp+E68h]
  _BYTE v202[32]; // [rsp+F70h] [rbp+E70h] BYREF
  _BYTE v203[32]; // [rsp+F90h] [rbp+E90h] BYREF
  _BYTE v204[24]; // [rsp+FB0h] [rbp+EB0h] BYREF
  int v205; // [rsp+FC8h] [rbp+EC8h]
  __int64 v206; // [rsp+FD0h] [rbp+ED0h]
  _BYTE v207[32]; // [rsp+FD8h] [rbp+ED8h] BYREF
  _BYTE v208[32]; // [rsp+FF8h] [rbp+EF8h] BYREF
  _BYTE v209[24]; // [rsp+1018h] [rbp+F18h] BYREF
  int v210; // [rsp+1030h] [rbp+F30h]
  __int64 v211; // [rsp+1038h] [rbp+F38h]
  _BYTE v212[32]; // [rsp+1040h] [rbp+F40h] BYREF
  _BYTE v213[32]; // [rsp+1060h] [rbp+F60h] BYREF
  _BYTE v214[24]; // [rsp+1080h] [rbp+F80h] BYREF
  int v215; // [rsp+1098h] [rbp+F98h]
  __int64 v216; // [rsp+10A0h] [rbp+FA0h]
  _BYTE v217[32]; // [rsp+10A8h] [rbp+FA8h] BYREF
  _BYTE v218[32]; // [rsp+10C8h] [rbp+FC8h] BYREF
  _BYTE v219[24]; // [rsp+10E8h] [rbp+FE8h] BYREF
  int v220; // [rsp+1100h] [rbp+1000h]
  __int64 v221; // [rsp+1108h] [rbp+1008h]
  _BYTE v222[32]; // [rsp+1110h] [rbp+1010h] BYREF
  _BYTE v223[32]; // [rsp+1130h] [rbp+1030h] BYREF
  _BYTE v224[24]; // [rsp+1150h] [rbp+1050h] BYREF
  int v225; // [rsp+1168h] [rbp+1068h]
  __int64 (__fastcall *v226)(); // [rsp+1170h] [rbp+1070h]
  _BYTE v227[32]; // [rsp+1178h] [rbp+1078h] BYREF
  _BYTE v228[32]; // [rsp+1198h] [rbp+1098h] BYREF
  _BYTE v229[24]; // [rsp+11B8h] [rbp+10B8h] BYREF
  int v230; // [rsp+11D0h] [rbp+10D0h]
  __int64 v231; // [rsp+11D8h] [rbp+10D8h]
  _BYTE v232[32]; // [rsp+11E0h] [rbp+10E0h] BYREF
  _BYTE v233[32]; // [rsp+1200h] [rbp+1100h] BYREF
  _BYTE v234[24]; // [rsp+1220h] [rbp+1120h] BYREF
  int v235; // [rsp+1238h] [rbp+1138h]
  __int64 v236; // [rsp+1240h] [rbp+1140h]
  char v237; // [rsp+1248h] [rbp+1148h] BYREF
  _BYTE v238[32]; // [rsp+1250h] [rbp+1150h] BYREF
  int v239; // [rsp+12D0h] [rbp+11D0h] BYREF
  char v240; // [rsp+12D4h] [rbp+11D4h] BYREF
  int v241; // [rsp+12D8h] [rbp+11D8h] BYREF
  char v242; // [rsp+12DCh] [rbp+11DCh] BYREF
  int v243; // [rsp+12E0h] [rbp+11E0h] BYREF
  char v244; // [rsp+12E4h] [rbp+11E4h] BYREF
  int v245; // [rsp+12E8h] [rbp+11E8h] BYREF
  char v246; // [rsp+12ECh] [rbp+11ECh] BYREF

  memset(v127, 0, sizeof(v127));
  std::wstring::_Construct<1,wchar_t const *>(v127, L"MoUsoCoreWorker", 15);
  v37 = 0;
  v38 = 0;
  memset(v95, 0, sizeof(v95));
  std::wstring::_Construct<1,wchar_t const *>(v95, &qword_180050DC0, 0);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v96, &v37);
  v97 = 0;
  v98 = 0;
  std::wstring::wstring(v142, v127);
  std::wstring::wstring(v143, v95);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v144, v96);
  v145 = v97;
  v146 = v98;
  memset(v125, 0, sizeof(v125));
  std::wstring::_Construct<1,wchar_t const *>(v125, L"updatecli", 9);
  v35 = 0;
  v36 = 0;
  memset(v91, 0, sizeof(v91));
  std::wstring::_Construct<1,wchar_t const *>(v91, &qword_180050DC0, 0);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v92, &v35);
  v93 = 0;
  v94 = 0;
  std::wstring::wstring(v147, v125);
  std::wstring::wstring(v148, v91);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v149, v92);
  v150 = v93;
  v151 = v94;
  memset(v124, 0, sizeof(v124));
  std::wstring::_Construct<1,wchar_t const *>(v124, L"UsoClientImpl", 13);
  v33 = 0;
  v34 = 0;
  memset(v87, 0, sizeof(v87));
  std::wstring::_Construct<1,wchar_t const *>(v87, &qword_180050DC0, 0);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v88, &v33);
  v89 = 0;
  v90 = 0;
  std::wstring::wstring(v152, v124);
  std::wstring::wstring(v153, v87);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v154, v88);
  v155 = v89;
  v156 = v90;
  memset(v123, 0, sizeof(v123));
  std::wstring::_Construct<1,wchar_t const *>(v123, L"UsoSvcImpl", 10);
  v31 = 0;
  v32 = 0;
  memset(v83, 0, sizeof(v83));
  std::wstring::_Construct<1,wchar_t const *>(v83, &qword_180050DC0, 0);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v84, &v31);
  v85 = 0;
  v86 = 0;
  std::wstring::wstring(v157, v123);
  std::wstring::wstring(v158, v83);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v159, v84);
  v160 = v85;
  v161 = v86;
  memset(v126, 0, sizeof(v126));
  std::wstring::_Construct<1,wchar_t const *>(v126, L"UusFailover", 11);
  v29 = 0;
  v30 = 0;
  memset(v79, 0, sizeof(v79));
  std::wstring::_Construct<1,wchar_t const *>(v79, &qword_180050DC0, 0);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v80, &v29);
  v81 = 0;
  v82 = 0;
  std::wstring::wstring(v162, v126);
  std::wstring::wstring(v163, v79);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v164, v80);
  v165 = v81;
  v166 = v82;
  memset(v122, 0, sizeof(v122));
  std::wstring::_Construct<1,wchar_t const *>(v122, L"MoNotificationUx", 16);
  v27 = 0;
  v28 = 0;
  memset(v75, 0, sizeof(v75));
  std::wstring::_Construct<1,wchar_t const *>(v75, &qword_180050DC0, 0);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v76, &v27);
  v77 = 0;
  v78 = 0;
  std::wstring::wstring(v167, v122);
  std::wstring::wstring(v168, v75);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v169, v76);
  v170 = v77;
  v171 = v78;
  memset(v133, 0, sizeof(v133));
  std::wstring::_Construct<1,wchar_t const *>(v133, L"WaasMedicEngine", 15);
  v25 = 0;
  v26 = 0;
  memset(v71, 0, sizeof(v71));
  std::wstring::_Construct<1,wchar_t const *>(v71, &qword_180050DC0, 0);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v72, &v25);
  v73 = 0;
  v74 = wil::ExpiredFeatureBase<wil::details::FeatureTraitsBase,enum wil::details::EmptyVariant,0>::IsEnabled;
  std::wstring::wstring(v172, v133);
  std::wstring::wstring(v173, v71);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v174, v72);
  v175 = v73;
  v176 = v74;
  memset(v132, 0, sizeof(v132));
  std::wstring::_Construct<1,wchar_t const *>(v132, L"WaasMedicAgent", 14);
  v23 = 0;
  v24 = 0;
  memset(v99, 0, sizeof(v99));
  std::wstring::_Construct<1,wchar_t const *>(v99, &qword_180050DC0, 0);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v100, &v23);
  v101 = 0;
  v102 = wil::ExpiredFeatureBase<wil::details::FeatureTraitsBase,enum wil::details::EmptyVariant,0>::IsEnabled;
  std::wstring::wstring(v177, v132);
  std::wstring::wstring(v178, v99);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v179, v100);
  v180 = v101;
  v181 = v102;
  memset(v131, 0, sizeof(v131));
  std::wstring::_Construct<1,wchar_t const *>(v131, L"WaasMedicCapsule", 16);
  v21 = 0;
  v22 = 0;
  memset(v67, 0, sizeof(v67));
  std::wstring::_Construct<1,wchar_t const *>(v67, &qword_180050DC0, 0);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v68, &v21);
  v69 = 0;
  v70 = wil::ExpiredFeatureBase<wil::details::FeatureTraitsBase,enum wil::details::EmptyVariant,0>::IsEnabled;
  std::wstring::wstring(v182, v131);
  std::wstring::wstring(v183, v67);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v184, v68);
  v185 = v69;
  v186 = v70;
  memset(v130, 0, sizeof(v130));
  std::wstring::_Construct<1,wchar_t const *>(v130, L"WuHandler", 9);
  v239 = 1;
  v9 = &v239;
  v10 = (int *)&v240;
  std::vector<enum UusCapability>::vector<enum UusCapability>(v141, &v9);
  memset(v63, 0, sizeof(v63));
  std::wstring::_Construct<1,wchar_t const *>(v63, &qword_180050DC0, 0);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v64, v141);
  v65 = 0;
  v66 = 0;
  std::wstring::wstring(v187, v130);
  std::wstring::wstring(v188, v63);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v189, v64);
  v190 = v65;
  v191 = v66;
  memset(v129, 0, sizeof(v129));
  std::wstring::_Construct<1,wchar_t const *>(v129, L"WuCoreProxyStubs", 16);
  v241 = 1;
  v9 = &v241;
  v10 = (int *)&v242;
  std::vector<enum UusCapability>::vector<enum UusCapability>(v140, &v9);
  memset(v59, 0, sizeof(v59));
  std::wstring::_Construct<1,wchar_t const *>(v59, &qword_180050DC0, 0);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v60, v140);
  v61 = 0;
  v62 = 0;
  std::wstring::wstring(v192, v129);
  std::wstring::wstring(v193, v59);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v194, v60);
  v195 = v61;
  v196 = v62;
  memset(v128, 0, sizeof(v128));
  std::wstring::_Construct<1,wchar_t const *>(v128, L"WuCoreModules", 13);
  v243 = 1;
  v9 = &v243;
  v10 = (int *)&v244;
  std::vector<enum UusCapability>::vector<enum UusCapability>(v139, &v9);
  memset(v55, 0, sizeof(v55));
  std::wstring::_Construct<1,wchar_t const *>(v55, &qword_180050DC0, 0);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v56, v139);
  v57 = 0;
  v58 = 0;
  std::wstring::wstring(v197, v128);
  std::wstring::wstring(v198, v55);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v199, v56);
  v200 = v57;
  v201 = v58;
  memset(v115, 0, sizeof(v115));
  std::wstring::_Construct<1,wchar_t const *>(v115, L"WuStoreAuthPlugin", 17);
  v245 = 1;
  v9 = &v245;
  v10 = (int *)&v246;
  std::vector<enum UusCapability>::vector<enum UusCapability>(v138, &v9);
  memset(v51, 0, sizeof(v51));
  std::wstring::_Construct<1,wchar_t const *>(v51, &qword_180050DC0, 0);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v52, v138);
  v53 = 0;
  v54 = 0;
  std::wstring::wstring(v202, v115);
  std::wstring::wstring(v203, v51);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v204, v52);
  v205 = v53;
  v206 = v54;
  memset(v121, 0, sizeof(v121));
  std::wstring::_Construct<1,wchar_t const *>(v121, L"WuUpdatePolicy", 14);
  v11 = 1;
  v9 = &v11;
  v10 = &v12;
  std::vector<enum UusCapability>::vector<enum UusCapability>(v137, &v9);
  memset(v47, 0, sizeof(v47));
  std::wstring::_Construct<1,wchar_t const *>(v47, &qword_180050DC0, 0);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v48, v137);
  v49 = 0;
  v50 = 0;
  std::wstring::wstring(v207, v121);
  std::wstring::wstring(v208, v47);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v209, v48);
  v210 = v49;
  v211 = v50;
  memset(v120, 0, sizeof(v120));
  std::wstring::_Construct<1,wchar_t const *>(v120, L"Wuauclt", 7);
  v12 = 1;
  v9 = &v12;
  v10 = &v13;
  std::vector<enum UusCapability>::vector<enum UusCapability>(v136, &v9);
  memset(v43, 0, sizeof(v43));
  std::wstring::_Construct<1,wchar_t const *>(v43, &qword_180050DC0, 0);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v44, v136);
  v45 = 0;
  v46 = 0;
  std::wstring::wstring(v212, v120);
  std::wstring::wstring(v213, v43);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v214, v44);
  v215 = v45;
  v216 = v46;
  memset(v119, 0, sizeof(v119));
  std::wstring::_Construct<1,wchar_t const *>(v119, L"WuTrust", 7);
  v13 = 1;
  v9 = &v13;
  v10 = &v14;
  std::vector<enum UusCapability>::vector<enum UusCapability>(v135, &v9);
  memset(v39, 0, sizeof(v39));
  std::wstring::_Construct<1,wchar_t const *>(v39, &qword_180050DC0, 0);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v40, v135);
  v41 = 0;
  v42 = 0;
  std::wstring::wstring(v217, v119);
  std::wstring::wstring(v218, v39);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v219, v40);
  v220 = v41;
  v221 = v42;
  memset(v118, 0, sizeof(v118));
  std::wstring::_Construct<1,wchar_t const *>(v118, L"Sih", 3);
  v14 = 1;
  v9 = &v14;
  v10 = (int *)&v15;
  std::vector<enum UusCapability>::vector<enum UusCapability>(v134, &v9);
  memset(v111, 0, sizeof(v111));
  std::wstring::_Construct<1,wchar_t const *>(v111, &qword_180050DC0, 0);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v112, v134);
  v113 = 0;
  v114 = wil::ExpiredFeatureBase<wil::details::FeatureTraitsBase,enum wil::details::EmptyVariant,0>::IsEnabled;
  std::wstring::wstring(v222, v118);
  std::wstring::wstring(v223, v111);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v224, v112);
  v225 = v113;
  v226 = v114;
  memset(v117, 0, sizeof(v117));
  std::wstring::_Construct<1,wchar_t const *>(v117, L"MLEngine", 8);
  v19 = 0;
  v20 = 0;
  memset(v107, 0, sizeof(v107));
  std::wstring::_Construct<1,wchar_t const *>(v107, &qword_180050DC0, 0);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v108, &v19);
  v109 = 0;
  v110 = 0;
  std::wstring::wstring(v227, v117);
  std::wstring::wstring(v228, v107);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v229, v108);
  v230 = v109;
  v231 = v110;
  memset(v116, 0, sizeof(v116));
  std::wstring::_Construct<1,wchar_t const *>(v116, L"UIEOrchestrator", 15);
  v17 = 0;
  v18 = 0;
  memset(v103, 0, sizeof(v103));
  std::wstring::_Construct<1,wchar_t const *>(v103, &qword_180050DC0, 0);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v104, &v17);
  v105 = 0;
  v106 = 0;
  std::wstring::wstring(v232, v116);
  v8 = v233;
  std::wstring::wstring(v233, v103);
  std::vector<enum UusCapability>::vector<enum UusCapability>(v234, v104);
  v235 = v105;
  v236 = v106;
  UusComponentMaps::Components = 0;
  qword_180063CF8 = 0;
  v1 = operator new(0x88u);
  *v1 = v1;
  v1[1] = v1;
  v1[2] = v1;
  *((_WORD *)v1 + 12) = 257;
  UusComponentMaps::Components = (__int64)v1;
  v2 = &v145;
  do
  {
    v3 = std::_Tree<std::_Tmap_traits<std::wstring const,UusComponent,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,UusComponent>>,0>>::_Find_hint<std::wstring>(
           v0,
           v238,
           v1,
           v2 - 22,
           v8);
    v4 = *(_OWORD *)v3;
    v16 = *(_QWORD *)(v3 + 16);
    if ( !(_BYTE)v16 )
    {
      if ( qword_180063CF8 == 0x1E1E1E1E1E1E1E1LL )
        std::_Throw_tree_length_error();
      v5 = UusComponentMaps::Components;
      v9 = (int *)&UusComponentMaps::Components;
      v10 = 0;
      v6 = (char *)operator new(0x88u);
      v10 = (int *)v6;
      v8 = v6 + 32;
      std::wstring::wstring(v6 + 32, v2 - 22);
      *(_QWORD *)&v15 = v6 + 64;
      std::wstring::wstring(v6 + 64, v2 - 14);
      std::vector<enum UusCapability>::vector<enum UusCapability>(v6 + 96, v2 - 6);
      *((_DWORD *)v6 + 30) = *v2;
      *((_QWORD *)v6 + 16) = *((_QWORD *)v2 + 1);
      *(_QWORD *)v6 = v5;
      *((_QWORD *)v6 + 1) = v5;
      *((_QWORD *)v6 + 2) = v5;
      *((_WORD *)v6 + 12) = 0;
      v10 = 0;
      v15 = v4;
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Insert_node(
        &UusComponentMaps::Components,
        &v15,
        v6);
    }
    v2 += 26;
    v0 = &v237;
  }
  while ( v2 - 22 != (int *)&v237 );
  `eh vector destructor iterator'(
    v142,
    0x68u,
    0x13u,
    std::pair<std::wstring const,UusComponent>::~pair<std::wstring const,UusComponent>);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v104);
  std::wstring::_Tidy_deallocate(v103);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(&v17);
  std::wstring::_Tidy_deallocate(v116);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v108);
  std::wstring::_Tidy_deallocate(v107);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(&v19);
  std::wstring::_Tidy_deallocate(v117);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v112);
  std::wstring::_Tidy_deallocate(v111);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v134);
  std::wstring::_Tidy_deallocate(v118);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v40);
  std::wstring::_Tidy_deallocate(v39);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v135);
  std::wstring::_Tidy_deallocate(v119);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v44);
  std::wstring::_Tidy_deallocate(v43);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v136);
  std::wstring::_Tidy_deallocate(v120);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v48);
  std::wstring::_Tidy_deallocate(v47);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v137);
  std::wstring::_Tidy_deallocate(v121);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v52);
  std::wstring::_Tidy_deallocate(v51);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v138);
  std::wstring::_Tidy_deallocate(v115);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v56);
  std::wstring::_Tidy_deallocate(v55);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v139);
  std::wstring::_Tidy_deallocate(v128);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v60);
  std::wstring::_Tidy_deallocate(v59);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v140);
  std::wstring::_Tidy_deallocate(v129);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v64);
  std::wstring::_Tidy_deallocate(v63);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v141);
  std::wstring::_Tidy_deallocate(v130);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v68);
  std::wstring::_Tidy_deallocate(v67);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(&v21);
  std::wstring::_Tidy_deallocate(v131);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v100);
  std::wstring::_Tidy_deallocate(v99);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(&v23);
  std::wstring::_Tidy_deallocate(v132);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v72);
  std::wstring::_Tidy_deallocate(v71);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(&v25);
  std::wstring::_Tidy_deallocate(v133);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v76);
  std::wstring::_Tidy_deallocate(v75);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(&v27);
  std::wstring::_Tidy_deallocate(v122);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v80);
  std::wstring::_Tidy_deallocate(v79);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(&v29);
  std::wstring::_Tidy_deallocate(v126);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v84);
  std::wstring::_Tidy_deallocate(v83);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(&v31);
  std::wstring::_Tidy_deallocate(v123);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v88);
  std::wstring::_Tidy_deallocate(v87);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(&v33);
  std::wstring::_Tidy_deallocate(v124);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v92);
  std::wstring::_Tidy_deallocate(v91);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(&v35);
  std::wstring::_Tidy_deallocate(v125);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(v96);
  std::wstring::_Tidy_deallocate(v95);
  std::vector<enum UusCapability>::~vector<enum UusCapability>(&v37);
  std::wstring::_Tidy_deallocate(v127);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__UusComponentMaps::Components__);
}

```

## disassembly

```asm
0x180002f30  push    rbp
0x180002f32  push    rbx
0x180002f33  push    rsi
0x180002f34  push    rdi
0x180002f35  push    r12
0x180002f37  push    r13
0x180002f39  push    r14
0x180002f3b  push    r15
0x180002f3d  lea     rbp, [rsp-1188h]
0x180002f45  mov     eax, 1288h
0x180002f4a  call    _alloca_probe
0x180002f4f  sub     rsp, rax
0x180002f52  movaps  [rsp+12C0h+var_50], xmm6
0x180002f5a  xorps   xmm0, xmm0
0x180002f5d  movups  [rbp+11C0h+var_9D0], xmm0
0x180002f64  xorps   xmm1, xmm1
0x180002f67  movdqu  [rbp+11C0h+var_9C0], xmm1
0x180002f6f  mov     r13d, 0Fh
0x180002f75  mov     r8d, r13d
0x180002f78  lea     rdx, aMousocoreworke_0; "MoUsoCoreWorker"
0x180002f7f  lea     rcx, [rbp+11C0h+var_9D0]
0x180002f86  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002f8b  nop
0x180002f8c  xorps   xmm0, xmm0
0x180002f8f  movdqu  [rbp+11C0h+var_1160], xmm0
0x180002f94  xor     edi, edi
0x180002f96  mov     [rbp+11C0h+var_1150], rdi
0x180002f9a  movups  [rbp+11C0h+var_CE0], xmm0
0x180002fa1  xorps   xmm1, xmm1
0x180002fa4  movdqa  [rbp+11C0h+var_CD0], xmm1
0x180002fac  xor     r8d, r8d
0x180002faf  lea     r12, qword_180050DC0
0x180002fb6  mov     rdx, r12
0x180002fb9  lea     rcx, [rbp+11C0h+var_CE0]
0x180002fc0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002fc5  nop
0x180002fc6  lea     rdx, [rbp+11C0h+var_1160]
0x180002fca  lea     rcx, [rbp+11C0h+var_CC0]
0x180002fd1  call    ??0?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<UusCapability>::vector<UusCapability>(std::vector<UusCapability> const &)
0x180002fd6  mov     [rbp+11C0h+var_CA8], edi
0x180002fdc  mov     [rbp+11C0h+var_CA0], rdi
0x180002fe3  lea     rdx, [rbp+11C0h+var_9D0]
0x180002fea  lea     rcx, [rbp+11C0h+var_830]
0x180002ff1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180002ff6  nop
0x180002ff7  lea     rax, [rbp+11C0h+var_810]
0x180002ffe  mov     [rsp+12C0h+var_12A0], rax
0x180003003  lea     rdx, [rbp+11C0h+var_CE0]
0x18000300a  lea     rcx, [rbp+11C0h+var_810]
0x180003011  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180003016  nop
0x180003017  lea     rdx, [rbp+11C0h+var_CC0]
0x18000301e  lea     rcx, [rbp+11C0h+var_7F0]
0x180003025  call    ??0?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<UusCapability>::vector<UusCapability>(std::vector<UusCapability> const &)
0x18000302a  mov     eax, [rbp+11C0h+var_CA8]
0x180003030  mov     [rbp+11C0h+var_7D8], eax
0x180003036  mov     rax, [rbp+11C0h+var_CA0]
0x18000303d  mov     [rbp+11C0h+var_7D0], rax
0x180003044  xorps   xmm0, xmm0
0x180003047  movups  [rbp+11C0h+var_A10], xmm0
0x18000304e  xorps   xmm1, xmm1
0x180003051  movdqu  [rbp+11C0h+var_A00], xmm1
0x180003059  lea     esi, [rdi+9]
0x18000305c  mov     r8d, esi
0x18000305f  lea     rdx, aUpdatecli; "updatecli"
0x180003066  lea     rcx, [rbp+11C0h+var_A10]
0x18000306d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180003072  nop
0x180003073  xorps   xmm0, xmm0
0x180003076  movdqu  [rbp+11C0h+var_1178], xmm0
0x18000307b  mov     [rbp+11C0h+var_1168], rdi
0x18000307f  movups  [rbp+11C0h+var_D30], xmm0
0x180003086  xorps   xmm1, xmm1
0x180003089  movdqa  [rbp+11C0h+var_D20], xmm1
0x180003091  xor     r8d, r8d
0x180003094  mov     rdx, r12
0x180003097  lea     rcx, [rbp+11C0h+var_D30]
0x18000309e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800030a3  nop
0x1800030a4  lea     rdx, [rbp+11C0h+var_1178]
0x1800030a8  lea     rcx, [rbp+11C0h+var_D10]
0x1800030af  call    ??0?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<UusCapability>::vector<UusCapability>(std::vector<UusCapability> const &)
0x1800030b4  mov     [rbp+11C0h+var_CF8], edi
0x1800030ba  mov     [rbp+11C0h+var_CF0], rdi
0x1800030c1  lea     rdx, [rbp+11C0h+var_A10]
0x1800030c8  lea     rcx, [rbp+11C0h+var_7C8]
0x1800030cf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800030d4  nop
0x1800030d5  lea     rax, [rbp+11C0h+var_7A8]
0x1800030dc  mov     [rsp+12C0h+var_12A0], rax
0x1800030e1  lea     rdx, [rbp+11C0h+var_D30]
0x1800030e8  lea     rcx, [rbp+11C0h+var_7A8]
0x1800030ef  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800030f4  nop
0x1800030f5  lea     rdx, [rbp+11C0h+var_D10]
0x1800030fc  lea     rcx, [rbp+11C0h+var_788]
0x180003103  call    ??0?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<UusCapability>::vector<UusCapability>(std::vector<UusCapability> const &)
0x180003108  mov     eax, [rbp+11C0h+var_CF8]
0x18000310e  mov     [rbp+11C0h+var_770], eax
0x180003114  mov     rax, [rbp+11C0h+var_CF0]
0x18000311b  mov     [rbp+11C0h+var_768], rax
0x180003122  xorps   xmm0, xmm0
0x180003125  movups  [rbp+11C0h+var_A30], xmm0
0x18000312c  xorps   xmm1, xmm1
0x18000312f  movdqu  [rbp+11C0h+var_A20], xmm1
0x180003137  lea     r14d, [r13-2]
0x18000313b  mov     r8d, r14d
0x18000313e  lea     rdx, aUsoclientimpl; "UsoClientImpl"
0x180003145  lea     rcx, [rbp+11C0h+var_A30]
0x18000314c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180003151  nop
0x180003152  xorps   xmm0, xmm0
0x180003155  movdqu  [rbp+11C0h+var_1190], xmm0
0x18000315a  mov     [rbp+11C0h+var_1180], rdi
0x18000315e  movups  [rbp+11C0h+var_D80], xmm0
0x180003165  xorps   xmm1, xmm1
0x180003168  movdqa  [rbp+11C0h+var_D70], xmm1
0x180003170  xor     r8d, r8d
0x180003173  mov     rdx, r12
0x180003176  lea     rcx, [rbp+11C0h+var_D80]
0x18000317d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180003182  nop
0x180003183  lea     rdx, [rbp+11C0h+var_1190]
0x180003187  lea     rcx, [rbp+11C0h+var_D60]
0x18000318e  call    ??0?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<UusCapability>::vector<UusCapability>(std::vector<UusCapability> const &)
0x180003193  mov     [rbp+11C0h+var_D48], edi
0x180003199  mov     [rbp+11C0h+var_D40], rdi
0x1800031a0  lea     rdx, [rbp+11C0h+var_A30]
0x1800031a7  lea     rcx, [rbp+11C0h+var_760]
0x1800031ae  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800031b3  nop
0x1800031b4  lea     rax, [rbp+11C0h+var_740]
0x1800031bb  mov     [rsp+12C0h+var_12A0], rax
0x1800031c0  lea     rdx, [rbp+11C0h+var_D80]
0x1800031c7  lea     rcx, [rbp+11C0h+var_740]
0x1800031ce  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800031d3  nop
0x1800031d4  lea     rdx, [rbp+11C0h+var_D60]
0x1800031db  lea     rcx, [rbp+11C0h+var_720]
0x1800031e2  call    ??0?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<UusCapability>::vector<UusCapability>(std::vector<UusCapability> const &)
0x1800031e7  mov     eax, [rbp+11C0h+var_D48]
0x1800031ed  mov     [rbp+11C0h+var_708], eax
0x1800031f3  mov     rax, [rbp+11C0h+var_D40]
0x1800031fa  mov     [rbp+11C0h+var_700], rax
0x180003201  xorps   xmm0, xmm0
0x180003204  movups  [rbp+11C0h+var_A50], xmm0
0x18000320b  xorps   xmm1, xmm1
0x18000320e  movdqu  [rbp+11C0h+var_A40], xmm1
0x180003216  lea     r8d, [r13-5]
0x18000321a  lea     rdx, aUsosvcimpl; "UsoSvcImpl"
0x180003221  lea     rcx, [rbp+11C0h+var_A50]
0x180003228  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000322d  nop
0x18000322e  xorps   xmm0, xmm0
0x180003231  movdqu  [rbp+11C0h+var_11A8], xmm0
0x180003236  mov     [rbp+11C0h+var_1198], rdi
0x18000323a  movups  [rbp+11C0h+var_DD0], xmm0
0x180003241  xorps   xmm1, xmm1
0x180003244  movdqa  [rbp+11C0h+var_DC0], xmm1
0x18000324c  xor     r8d, r8d
0x18000324f  mov     rdx, r12
0x180003252  lea     rcx, [rbp+11C0h+var_DD0]
0x180003259  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000325e  nop
0x18000325f  lea     rdx, [rbp+11C0h+var_11A8]
0x180003263  lea     rcx, [rbp+11C0h+var_DB0]
0x18000326a  call    ??0?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<UusCapability>::vector<UusCapability>(std::vector<UusCapability> const &)
0x18000326f  mov     [rbp+11C0h+var_D98], edi
0x180003275  mov     [rbp+11C0h+var_D90], rdi
0x18000327c  lea     rdx, [rbp+11C0h+var_A50]
0x180003283  lea     rcx, [rbp+11C0h+var_6F8]
0x18000328a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000328f  nop
0x180003290  lea     rax, [rbp+11C0h+var_6D8]
0x180003297  mov     [rsp+12C0h+var_12A0], rax
0x18000329c  lea     rdx, [rbp+11C0h+var_DD0]
0x1800032a3  lea     rcx, [rbp+11C0h+var_6D8]
0x1800032aa  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800032af  nop
0x1800032b0  lea     rdx, [rbp+11C0h+var_DB0]
0x1800032b7  lea     rcx, [rbp+11C0h+var_6B8]
0x1800032be  call    ??0?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<UusCapability>::vector<UusCapability>(std::vector<UusCapability> const &)
0x1800032c3  mov     eax, [rbp+11C0h+var_D98]
0x1800032c9  mov     [rbp+11C0h+var_6A0], eax
0x1800032cf  mov     rax, [rbp+11C0h+var_D90]
0x1800032d6  mov     [rbp+11C0h+var_698], rax
0x1800032dd  xorps   xmm0, xmm0
0x1800032e0  movups  [rbp+11C0h+var_9F0], xmm0
0x1800032e7  xorps   xmm1, xmm1
0x1800032ea  movdqu  [rbp+11C0h+var_9E0], xmm1
0x1800032f2  lea     r8d, [r13-4]
0x1800032f6  lea     rdx, aUusfailover; "UusFailover"
0x1800032fd  lea     rcx, [rbp+11C0h+var_9F0]
0x180003304  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180003309  nop
0x18000330a  xorps   xmm0, xmm0
0x18000330d  movdqu  [rbp+11C0h+var_11C0], xmm0
0x180003312  mov     [rbp+11C0h+var_11B0], rdi
0x180003316  movups  [rbp+11C0h+var_E20], xmm0
0x18000331d  xorps   xmm1, xmm1
0x180003320  movdqa  [rbp+11C0h+var_E10], xmm1
0x180003328  xor     r8d, r8d
0x18000332b  mov     rdx, r12
0x18000332e  lea     rcx, [rbp+11C0h+var_E20]
0x180003335  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000333a  nop
0x18000333b  lea     rdx, [rbp+11C0h+var_11C0]
0x18000333f  lea     rcx, [rbp+11C0h+var_E00]
0x180003346  call    ??0?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<UusCapability>::vector<UusCapability>(std::vector<UusCapability> const &)
0x18000334b  mov     [rbp+11C0h+var_DE8], edi
0x180003351  mov     [rbp+11C0h+var_DE0], rdi
0x180003358  lea     rdx, [rbp+11C0h+var_9F0]
0x18000335f  lea     rcx, [rbp+11C0h+var_690]
0x180003366  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000336b  nop
0x18000336c  lea     rax, [rbp+11C0h+var_670]
0x180003373  mov     [rsp+12C0h+var_12A0], rax
0x180003378  lea     rdx, [rbp+11C0h+var_E20]
0x18000337f  lea     rcx, [rbp+11C0h+var_670]
0x180003386  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000338b  nop
0x18000338c  lea     rdx, [rbp+11C0h+var_E00]
0x180003393  lea     rcx, [rbp+11C0h+var_650]
0x18000339a  call    ??0?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<UusCapability>::vector<UusCapability>(std::vector<UusCapability> const &)
0x18000339f  mov     eax, [rbp+11C0h+var_DE8]
0x1800033a5  mov     [rbp+11C0h+var_638], eax
0x1800033ab  mov     rax, [rbp+11C0h+var_DE0]
0x1800033b2  mov     [rbp+11C0h+var_630], rax
0x1800033b9  xorps   xmm0, xmm0
0x1800033bc  movups  [rbp+11C0h+var_A70], xmm0
0x1800033c3  xorps   xmm1, xmm1
0x1800033c6  movdqu  [rbp+11C0h+var_A60], xmm1
0x1800033ce  lea     ebx, [rdi+10h]
0x1800033d1  mov     r8d, ebx
0x1800033d4  lea     rdx, aMonotification_0; "MoNotificationUx"
0x1800033db  lea     rcx, [rbp+11C0h+var_A70]
0x1800033e2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800033e7  nop
0x1800033e8  xorps   xmm0, xmm0
0x1800033eb  movdqu  [rbp+11C0h+var_11D8], xmm0
0x1800033f0  mov     [rbp+11C0h+var_11C8], rdi
0x1800033f4  movups  [rbp+11C0h+var_E70], xmm0
0x1800033fb  xorps   xmm1, xmm1
0x1800033fe  movdqa  [rbp+11C0h+var_E60], xmm1
0x180003406  xor     r8d, r8d
0x180003409  mov     rdx, r12
0x18000340c  lea     rcx, [rbp+11C0h+var_E70]
0x180003413  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180003418  nop
0x180003419  lea     rdx, [rbp+11C0h+var_11D8]
0x18000341d  lea     rcx, [rbp+11C0h+var_E50]
0x180003424  call    ??0?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<UusCapability>::vector<UusCapability>(std::vector<UusCapability> const &)
0x180003429  mov     [rbp+11C0h+var_E38], edi
0x18000342f  mov     [rbp+11C0h+var_E30], rdi
0x180003436  lea     rdx, [rbp+11C0h+var_A70]
0x18000343d  lea     rcx, [rbp+11C0h+var_628]
0x180003444  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180003449  nop
0x18000344a  lea     rax, [rbp+11C0h+var_608]
0x180003451  mov     [rsp+12C0h+var_12A0], rax
0x180003456  lea     rdx, [rbp+11C0h+var_E70]
0x18000345d  lea     rcx, [rbp+11C0h+var_608]
0x180003464  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180003469  nop
0x18000346a  lea     rdx, [rbp+11C0h+var_E50]
0x180003471  lea     rcx, [rbp+11C0h+var_5E8]
0x180003478  call    ??0?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<UusCapability>::vector<UusCapability>(std::vector<UusCapability> const &)
0x18000347d  mov     eax, [rbp+11C0h+var_E38]
0x180003483  mov     [rbp+11C0h+var_5D0], eax
0x180003489  mov     rax, [rbp+11C0h+var_E30]
0x180003490  mov     [rbp+11C0h+var_5C8], rax
0x180003497  xorps   xmm0, xmm0
0x18000349a  movups  [rbp+11C0h+var_910], xmm0
0x1800034a1  xorps   xmm1, xmm1
0x1800034a4  movdqu  [rbp+11C0h+var_900], xmm1
0x1800034ac  mov     r8d, r13d
0x1800034af  lea     rdx, aWaasmedicengin; "WaasMedicEngine"
0x1800034b6  lea     rcx, [rbp+11C0h+var_910]
0x1800034bd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800034c2  nop
0x1800034c3  xorps   xmm0, xmm0
0x1800034c6  movdqu  [rbp+11C0h+var_11F0], xmm0
0x1800034cb  mov     [rbp+11C0h+var_11E0], rdi
0x1800034cf  movups  [rbp+11C0h+var_EC0], xmm0
0x1800034d6  xorps   xmm1, xmm1
0x1800034d9  movdqa  [rbp+11C0h+var_EB0], xmm1
0x1800034e1  xor     r8d, r8d
0x1800034e4  mov     rdx, r12
0x1800034e7  lea     rcx, [rbp+11C0h+var_EC0]
0x1800034ee  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800034f3  nop
0x1800034f4  lea     rdx, [rbp+11C0h+var_11F0]
0x1800034f8  lea     rcx, [rbp+11C0h+var_EA0]
0x1800034ff  call    ??0?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<UusCapability>::vector<UusCapability>(std::vector<UusCapability> const &)
0x180003504  mov     [rbp+11C0h+var_E88], edi
0x18000350a  lea     r15, ?IsEnabled@?$ExpiredFeatureBase@UFeatureTraitsBase@details@wil@@W4EmptyVariant@23@$0A@@wil@@SA_NXZ; wil::ExpiredFeatureBase<wil::details::FeatureTraitsBase,wil::details::EmptyVariant,0>::IsEnabled(void)
0x180003511  mov     [rbp+11C0h+var_E80], r15
0x180003518  lea     rdx, [rbp+11C0h+var_910]
0x18000351f  lea     rcx, [rbp+11C0h+var_5C0]
0x180003526  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
  ... truncated ...
```
