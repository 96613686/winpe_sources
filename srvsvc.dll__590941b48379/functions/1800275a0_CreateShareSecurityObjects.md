# CreateShareSecurityObjects

- ea: `0x1800275a0`
- end: `0x180027eba`
- name: `CreateShareSecurityObjects`
- size: `2330`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000a5d4`

## callees

- `0x18000aa8c`
- `0x1800259f0`
- `0x1800275a0`

## string_xrefs

- `0x180027e8e`: `SrvsvcShareAdminConnect`
- `0x180027d7d`: `SrvsvcShareAdminInfo`

## pseudocode

```c
__int64 CreateShareSecurityObjects()
{
  char v0; // di
  int v1; // ebx
  __int16 *v2; // r9
  int v3; // ecx
  char v4; // al
  __int64 result; // rax
  __int16 *v6; // r9
  char v7; // al
  __int16 *v8; // r9
  int v9; // ecx
  char v10; // al
  char v11; // al
  char v12; // bl
  char v13; // al
  unsigned int v14; // [rsp+30h] [rbp-D0h]
  unsigned int v15; // [rsp+30h] [rbp-D0h]
  unsigned int v16; // [rsp+30h] [rbp-D0h]
  unsigned int v17; // [rsp+30h] [rbp-D0h]
  unsigned int v18; // [rsp+30h] [rbp-D0h]
  unsigned int v19; // [rsp+30h] [rbp-D0h]
  __int16 v20; // [rsp+40h] [rbp-C0h] BYREF
  char v21; // [rsp+42h] [rbp-BEh]
  int v22; // [rsp+44h] [rbp-BCh]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int16 v24; // [rsp+50h] [rbp-B0h]
  char v25; // [rsp+52h] [rbp-AEh]
  int v26; // [rsp+54h] [rbp-ACh]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  __int16 v28; // [rsp+60h] [rbp-A0h]
  char v29; // [rsp+62h] [rbp-9Eh]
  int v30; // [rsp+64h] [rbp-9Ch]
  HLOCAL *v31; // [rsp+68h] [rbp-98h]
  __int16 v32; // [rsp+70h] [rbp-90h]
  char v33; // [rsp+72h] [rbp-8Eh]
  int v34; // [rsp+74h] [rbp-8Ch]
  __int64 v35; // [rsp+78h] [rbp-88h]
  __int16 v36; // [rsp+80h] [rbp-80h] BYREF
  char v37; // [rsp+82h] [rbp-7Eh]
  int v38; // [rsp+84h] [rbp-7Ch]
  __int64 v39; // [rsp+88h] [rbp-78h]
  __int16 v40; // [rsp+90h] [rbp-70h]
  char v41; // [rsp+92h] [rbp-6Eh]
  int v42; // [rsp+94h] [rbp-6Ch]
  __int64 v43; // [rsp+98h] [rbp-68h]
  __int16 v44; // [rsp+A0h] [rbp-60h]
  char v45; // [rsp+A2h] [rbp-5Eh]
  int v46; // [rsp+A4h] [rbp-5Ch]
  HLOCAL *v47; // [rsp+A8h] [rbp-58h]
  __int16 v48; // [rsp+B0h] [rbp-50h]
  char v49; // [rsp+B2h] [rbp-4Eh]
  int v50; // [rsp+B4h] [rbp-4Ch]
  __int64 v51; // [rsp+B8h] [rbp-48h]
  __int16 v52; // [rsp+C0h] [rbp-40h]
  char v53; // [rsp+C2h] [rbp-3Eh]
  int v54; // [rsp+C4h] [rbp-3Ch]
  __int64 v55; // [rsp+C8h] [rbp-38h]
  __int16 v56; // [rsp+D0h] [rbp-30h] BYREF
  char v57; // [rsp+D2h] [rbp-2Eh]
  int v58; // [rsp+D4h] [rbp-2Ch]
  __int64 v59; // [rsp+D8h] [rbp-28h]
  __int16 v60; // [rsp+E0h] [rbp-20h]
  char v61; // [rsp+E2h] [rbp-1Eh]
  int v62; // [rsp+E4h] [rbp-1Ch]
  __int64 v63; // [rsp+E8h] [rbp-18h]
  __int16 v64; // [rsp+F0h] [rbp-10h]
  char v65; // [rsp+F2h] [rbp-Eh]
  int v66; // [rsp+F4h] [rbp-Ch]
  __int64 v67; // [rsp+F8h] [rbp-8h]
  __int16 v68; // [rsp+100h] [rbp+0h]
  char v69; // [rsp+102h] [rbp+2h]
  int v70; // [rsp+104h] [rbp+4h]
  __int64 v71; // [rsp+108h] [rbp+8h]
  __int16 v72; // [rsp+110h] [rbp+10h]
  char v73; // [rsp+112h] [rbp+12h]
  int v74; // [rsp+114h] [rbp+14h]
  __int64 v75; // [rsp+118h] [rbp+18h]
  __int16 v76; // [rsp+120h] [rbp+20h] BYREF
  char v77; // [rsp+122h] [rbp+22h]
  int v78; // [rsp+124h] [rbp+24h]
  __int64 v79; // [rsp+128h] [rbp+28h]
  __int16 v80; // [rsp+130h] [rbp+30h]
  char v81; // [rsp+132h] [rbp+32h]
  int v82; // [rsp+134h] [rbp+34h]
  __int64 v83; // [rsp+138h] [rbp+38h]
  __int16 v84; // [rsp+140h] [rbp+40h]
  char v85; // [rsp+142h] [rbp+42h]
  int v86; // [rsp+144h] [rbp+44h]
  __int64 v87; // [rsp+148h] [rbp+48h]
  __int16 v88; // [rsp+150h] [rbp+50h]
  char v89; // [rsp+152h] [rbp+52h]
  int v90; // [rsp+154h] [rbp+54h]
  __int64 v91; // [rsp+158h] [rbp+58h]
  __int16 v92; // [rsp+160h] [rbp+60h]
  char v93; // [rsp+162h] [rbp+62h]
  int v94; // [rsp+164h] [rbp+64h]
  __int64 v95; // [rsp+168h] [rbp+68h]
  __int16 v96; // [rsp+170h] [rbp+70h]
  char v97; // [rsp+172h] [rbp+72h]
  int v98; // [rsp+174h] [rbp+74h]
  __int64 v99; // [rsp+178h] [rbp+78h]
  __int16 v100; // [rsp+180h] [rbp+80h] BYREF
  char v101; // [rsp+182h] [rbp+82h]
  int v102; // [rsp+184h] [rbp+84h]
  __int64 v103; // [rsp+188h] [rbp+88h]
  __int16 v104; // [rsp+190h] [rbp+90h]
  char v105; // [rsp+192h] [rbp+92h]
  int v106; // [rsp+194h] [rbp+94h]
  __int64 v107; // [rsp+198h] [rbp+98h]
  __int16 v108; // [rsp+1A0h] [rbp+A0h]
  char v109; // [rsp+1A2h] [rbp+A2h]
  int v110; // [rsp+1A4h] [rbp+A4h]
  __int64 v111; // [rsp+1A8h] [rbp+A8h]
  __int16 v112; // [rsp+1B0h] [rbp+B0h]
  char v113; // [rsp+1B2h] [rbp+B2h]
  int v114; // [rsp+1B4h] [rbp+B4h]
  HLOCAL *v115; // [rsp+1B8h] [rbp+B8h]
  __int16 v116; // [rsp+1C0h] [rbp+C0h]
  char v117; // [rsp+1C2h] [rbp+C2h]
  int v118; // [rsp+1C4h] [rbp+C4h]
  HLOCAL *v119; // [rsp+1C8h] [rbp+C8h]
  __int16 v120; // [rsp+1D0h] [rbp+D0h]
  char v121; // [rsp+1D2h] [rbp+D2h]
  int v122; // [rsp+1D4h] [rbp+D4h]
  HLOCAL *v123; // [rsp+1D8h] [rbp+D8h]
  __int16 v124; // [rsp+1E0h] [rbp+E0h] BYREF
  char v125; // [rsp+1E2h] [rbp+E2h]
  int v126; // [rsp+1E4h] [rbp+E4h]
  __int64 v127; // [rsp+1E8h] [rbp+E8h]
  __int16 v128; // [rsp+1F0h] [rbp+F0h]
  char v129; // [rsp+1F2h] [rbp+F2h]
  int v130; // [rsp+1F4h] [rbp+F4h]
  __int64 v131; // [rsp+1F8h] [rbp+F8h]
  __int16 v132; // [rsp+200h] [rbp+100h]
  char v133; // [rsp+202h] [rbp+102h]
  unsigned int v134; // [rsp+204h] [rbp+104h]
  HLOCAL *v135; // [rsp+208h] [rbp+108h]
  __int16 v136; // [rsp+210h] [rbp+110h]
  char v137; // [rsp+212h] [rbp+112h]
  int v138; // [rsp+214h] [rbp+114h]
  __int64 v139; // [rsp+218h] [rbp+118h]
  __int16 v140; // [rsp+220h] [rbp+120h]
  char v141; // [rsp+222h] [rbp+122h]
  int v142; // [rsp+224h] [rbp+124h]
  __int64 v143; // [rsp+228h] [rbp+128h]
  __int16 v144; // [rsp+230h] [rbp+130h]
  char v145; // [rsp+232h] [rbp+132h]
  int v146; // [rsp+234h] [rbp+134h]
  HLOCAL *v147; // [rsp+238h] [rbp+138h]
  __int16 v148; // [rsp+240h] [rbp+140h]
  char v149; // [rsp+242h] [rbp+142h]
  int v150; // [rsp+244h] [rbp+144h]
  HLOCAL *v151; // [rsp+248h] [rbp+148h]
  __int16 v152; // [rsp+250h] [rbp+150h]
  char v153; // [rsp+252h] [rbp+152h]
  int v154; // [rsp+254h] [rbp+154h]
  HLOCAL *v155; // [rsp+258h] [rbp+158h]
  __int16 v156; // [rsp+260h] [rbp+160h] BYREF
  char v157; // [rsp+262h] [rbp+162h]
  int v158; // [rsp+264h] [rbp+164h]
  __int64 v159; // [rsp+268h] [rbp+168h]
  __int16 v160; // [rsp+270h] [rbp+170h]
  char v161; // [rsp+272h] [rbp+172h]
  int v162; // [rsp+274h] [rbp+174h]
  __int64 v163; // [rsp+278h] [rbp+178h]
  __int16 v164; // [rsp+280h] [rbp+180h]
  char v165; // [rsp+282h] [rbp+182h]
  unsigned int v166; // [rsp+284h] [rbp+184h]
  HLOCAL *v167; // [rsp+288h] [rbp+188h]
  __int16 v168; // [rsp+290h] [rbp+190h]
  char v169; // [rsp+292h] [rbp+192h]
  int v170; // [rsp+294h] [rbp+194h]
  __int64 v171; // [rsp+298h] [rbp+198h]
  __int16 v172; // [rsp+2A0h] [rbp+1A0h]
  char v173; // [rsp+2A2h] [rbp+1A2h]
  int v174; // [rsp+2A4h] [rbp+1A4h]
  __int64 v175; // [rsp+2A8h] [rbp+1A8h]
  __int16 v176; // [rsp+2B0h] [rbp+1B0h]
  char v177; // [rsp+2B2h] [rbp+1B2h]
  int v178; // [rsp+2B4h] [rbp+1B4h]
  __int64 v179; // [rsp+2B8h] [rbp+1B8h]
  __int16 v180; // [rsp+2C0h] [rbp+1C0h]
  char v181; // [rsp+2C2h] [rbp+1C2h]
  int v182; // [rsp+2C4h] [rbp+1C4h]
  HLOCAL *v183; // [rsp+2C8h] [rbp+1C8h]
  __int16 v184; // [rsp+2D0h] [rbp+1D0h]
  char v185; // [rsp+2D2h] [rbp+1D2h]
  int v186; // [rsp+2D4h] [rbp+1D4h]
  HLOCAL *v187; // [rsp+2D8h] [rbp+1D8h]
  __int16 v188; // [rsp+2E0h] [rbp+1E0h]
  char v189; // [rsp+2E2h] [rbp+1E2h]
  int v190; // [rsp+2E4h] [rbp+1E4h]
  HLOCAL *v191; // [rsp+2E8h] [rbp+1E8h]
  __int16 v192; // [rsp+2F0h] [rbp+1F0h] BYREF
  char v193; // [rsp+2F2h] [rbp+1F2h]
  int v194; // [rsp+2F4h] [rbp+1F4h]
  __int64 v195; // [rsp+2F8h] [rbp+1F8h]
  __int16 v196; // [rsp+300h] [rbp+200h]
  char v197; // [rsp+302h] [rbp+202h]
  int v198; // [rsp+304h] [rbp+204h]
  __int64 v199; // [rsp+308h] [rbp+208h]
  __int16 v200; // [rsp+310h] [rbp+210h]
  char v201; // [rsp+312h] [rbp+212h]
  int v202; // [rsp+314h] [rbp+214h]
  __int64 v203; // [rsp+318h] [rbp+218h]
  __int16 v204; // [rsp+320h] [rbp+220h]
  char v205; // [rsp+322h] [rbp+222h]
  unsigned int v206; // [rsp+324h] [rbp+224h]
  HLOCAL *v207; // [rsp+328h] [rbp+228h]
  __int16 v208; // [rsp+330h] [rbp+230h]
  char v209; // [rsp+332h] [rbp+232h]
  int v210; // [rsp+334h] [rbp+234h]
  __int64 v211; // [rsp+338h] [rbp+238h]
  __int16 v212; // [rsp+340h] [rbp+240h]
  char v213; // [rsp+342h] [rbp+242h]
  int v214; // [rsp+344h] [rbp+244h]
  __int64 v215; // [rsp+348h] [rbp+248h]
  __int16 v216; // [rsp+350h] [rbp+250h]
  char v217; // [rsp+352h] [rbp+252h]
  int v218; // [rsp+354h] [rbp+254h]
  HLOCAL *v219; // [rsp+358h] [rbp+258h]
  __int16 v220; // [rsp+360h] [rbp+260h]
  char v221; // [rsp+362h] [rbp+262h]
  int v222; // [rsp+364h] [rbp+264h]
  HLOCAL *v223; // [rsp+368h] [rbp+268h]
  __int16 v224; // [rsp+370h] [rbp+270h]
  char v225; // [rsp+372h] [rbp+272h]
  int v226; // [rsp+374h] [rbp+274h]
  HLOCAL *v227; // [rsp+378h] [rbp+278h]
  __int16 v228; // [rsp+380h] [rbp+280h] BYREF
  char v229; // [rsp+382h] [rbp+282h]
  int v230; // [rsp+384h] [rbp+284h]
  __int64 v231; // [rsp+388h] [rbp+288h]
  __int16 v232; // [rsp+390h] [rbp+290h]
  char v233; // [rsp+392h] [rbp+292h]
  int v234; // [rsp+394h] [rbp+294h]
  __int64 v235; // [rsp+398h] [rbp+298h]
  __int16 v236; // [rsp+3A0h] [rbp+2A0h]
  char v237; // [rsp+3A2h] [rbp+2A2h]
  int v238; // [rsp+3A4h] [rbp+2A4h]
  __int64 v239; // [rsp+3A8h] [rbp+2A8h]
  __int16 v240; // [rsp+3B0h] [rbp+2B0h]
  char v241; // [rsp+3B2h] [rbp+2B2h]
  unsigned int v242; // [rsp+3B4h] [rbp+2B4h]
  HLOCAL *v243; // [rsp+3B8h] [rbp+2B8h]
  __int16 v244; // [rsp+3C0h] [rbp+2C0h]
  char v245; // [rsp+3C2h] [rbp+2C2h]
  int v246; // [rsp+3C4h] [rbp+2C4h]
  __int64 v247; // [rsp+3C8h] [rbp+2C8h]
  __int16 v248; // [rsp+3D0h] [rbp+2D0h]
  char v249; // [rsp+3D2h] [rbp+2D2h]
  int v250; // [rsp+3D4h] [rbp+2D4h]
  __int64 v251; // [rsp+3D8h] [rbp+2D8h]
  __int16 v252; // [rsp+3E0h] [rbp+2E0h]
  char v253; // [rsp+3E2h] [rbp+2E2h]
  int v254; // [rsp+3E4h] [rbp+2E4h]
  __int64 v255; // [rsp+3E8h] [rbp+2E8h]
  __int16 v256; // [rsp+3F0h] [rbp+2F0h]
  char v257; // [rsp+3F2h] [rbp+2F2h]
  int v258; // [rsp+3F4h] [rbp+2F4h]
  HLOCAL *v259; // [rsp+3F8h] [rbp+2F8h]
  __int16 v260; // [rsp+400h] [rbp+300h]
  char v261; // [rsp+402h] [rbp+302h]
  int v262; // [rsp+404h] [rbp+304h]
  HLOCAL *v263; // [rsp+408h] [rbp+308h]
  __int16 v264; // [rsp+410h] [rbp+310h]
  char v265; // [rsp+412h] [rbp+312h]
  int v266; // [rsp+414h] [rbp+314h]
  HLOCAL *v267; // [rsp+418h] [rbp+318h]

  v183 = &SsInteractiveSid;
  v156 = 0;
  v158 = 0x10000000;
  v162 = 0x10000000;
  v126 = 0x10000000;
  v0 = 1;
  v130 = 0x10000000;
  v157 = 0;
  v132 = 0;
  v133 = 0;
  v136 = 0;
  v137 = 0;
  v160 = 0;
  v161 = 0;
  v164 = 0;
  v165 = 0;
  v168 = 0;
  v169 = 0;
  v172 = 0;
  v173 = 0;
  v176 = 0;
  v177 = 0;
  v180 = 0;
  v181 = 0;
  v184 = 0;
  v185 = 0;
  v188 = 0;
  v189 = 0;
  v147 = &SsInteractiveSid;
  v191 = &SsBatchSid;
  v139 = qword_18005CDC0 + 64;
  v159 = qword_18005CDC0 + 80;
  v163 = qword_18005CDC0 + 120;
  v166 = 0x80000000;
  v167 = &SsAccessControlAssistanceOperatorsSid;
  v170 = 1;
  v171 = qword_18005CDC0 + 8;
  v174 = 1;
  v175 = qword_18005CDC0 + 72;
  v178 = 2;
  v179 = qword_18005CDC0 + 48;
  v182 = 2;
  v186 = 2;
  v187 = &SsServiceSid;
  v190 = 2;
  v124 = 0;
  v125 = 0;
  v127 = qword_18005CDC0 + 80;
  v128 = 0;
  v129 = 0;
  v131 = qword_18005CDC0 + 120;
  v134 = 0x80000000;
  v135 = &SsAccessControlAssistanceOperatorsSid;
  v138 = 1;
  v140 = 0;
  v141 = 0;
  v142 = 2;
  v143 = qword_18005CDC0 + 48;
  v144 = 0;
  v145 = 0;
  v146 = 2;
  v148 = 0;
  v149 = 0;
  v150 = 2;
  v151 = &SsServiceSid;
  v230 = 0x10000000;
  v152 = 0;
  v153 = 0;
  v228 = 0;
  v229 = 0;
  v232 = 0;
  v233 = 0;
  v236 = 0;
  v237 = 0;
  v240 = 0;
  v241 = 0;
  v244 = 0;
  v245 = 0;
  v248 = 0;
  v249 = 0;
  v252 = 0;
  v253 = 0;
  v256 = 0;
  v257 = 0;
  v259 = &SsInteractiveSid;
  v234 = 0x10000000;
  v238 = 0x10000000;
  v260 = 0;
  v261 = 0;
  v239 = qword_18005CDC0 + 128;
  v255 = qword_18005CDC0 + 48;
  v203 = qword_18005CDC0 + 128;
  v215 = qword_18005CDC0 + 48;
  v263 = &SsServiceSid;
  v154 = 2;
  v155 = &SsBatchSid;
  v231 = qword_18005CDC0 + 80;
  v235 = qword_18005CDC0 + 120;
  v242 = 0x80000000;
  v243 = &SsAccessControlAssistanceOperatorsSid;
  v246 = 1;
  v247 = qword_18005CDC0 + 8;
  v250 = 1;
  v251 = qword_18005CDC0 + 72;
  v254 = 2;
  v258 = 2;
  v262 = 2;
  v264 = 0;
  v265 = 0;
  v266 = 2;
  v267 = &SsBatchSid;
  v192 = 0;
  v193 = 0;
  v194 = 0x10000000;
  v195 = qword_18005CDC0 + 80;
  v196 = 0;
  v197 = 0;
  v198 = 0x10000000;
  v199 = qword_18005CDC0 + 120;
  v200 = 0;
  v201 = 0;
  v202 = 0x10000000;
  v204 = 0;
  v205 = 0;
  v206 = 0x80000000;
  v207 = &SsAccessControlAssistanceOperatorsSid;
  v208 = 0;
  v209 = 0;
  v210 = 1;
  v211 = qword_18005CDC0 + 64;
  v212 = 0;
  v213 = 0;
  v214 = 2;
  v216 = 0;
  v217 = 0;
  v218 = 2;
  v219 = &SsInteractiveSid;
  v220 = 0;
  v221 = 0;
  v222 = 2;
  v224 = 0;
  v225 = 0;
  v226 = 2;
  v36 = 0;
  v37 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 2;
  v44 = 0;
  v45 = 0;
  v46 = 2;
  v48 = 0;
  v49 = 0;
  v52 = 0;
  v53 = 0;
  v20 = 0;
  v21 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 2;
  v28 = 0;
  v29 = 0;
  v30 = 2;
  v32 = 0;
  v33 = 0;
  v56 = 0;
  v57 = 0;
  v60 = 0;
  v61 = 0;
  v64 = 0;
  v65 = 0;
  v67 = qword_18005CDC0 + 136;
  v68 = 0;
  v69 = 0;
  v72 = 0;
  v73 = 0;
  v100 = 0;
  v101 = 0;
  v104 = 0;
  v105 = 0;
  v108 = 0;
  v109 = 0;
  v111 = qword_18005CDC0 + 136;
  v112 = 0;
  v113 = 0;
  v223 = &SsServiceSid;
  v227 = &SsBatchSid;
  v38 = 0x10000000;
  v39 = qword_18005CDC0 + 80;
  v43 = qword_18005CDC0 + 120;
  v47 = &SsAccessControlAssistanceOperatorsSid;
  v50 = 1;
  v51 = qword_18005CDC0 + 8;
  v54 = 1;
  v55 = qword_18005CDC0 + 72;
  v22 = 0x10000000;
  v23 = qword_18005CDC0 + 80;
  v27 = qword_18005CDC0 + 120;
  v31 = &SsAccessControlAssistanceOperatorsSid;
  v34 = 1;
  v35 = qword_18005CDC0 + 64;
  v58 = 0x10000000;
  v59 = qword_18005CDC0 + 80;
  v62 = 0x10000000;
  v63 = qword_18005CDC0 + 120;
  v66 = 0x10000000;
  v70 = 1;
  v71 = qword_18005CDC0 + 8;
  v74 = 1;
  v75 = qword_18005CDC0 + 72;
  v102 = 0x10000000;
  v103 = qword_18005CDC0 + 80;
  v106 = 0x10000000;
  v107 = qword_18005CDC0 + 120;
  v110 = 0x10000000;
  v115 = &SsInteractiveSid;
  v87 = qword_18005CDC0 + 104;
  v90 = 983059;
  v94 = 983059;
  v98 = 983059;
  v91 = qword_18005CDC0 + 96;
  v114 = 0x10000000;
  v116 = 0;
  v117 = 0;
  v118 = 0x10000000;
  v119 = &SsServiceSid;
  v120 = 0;
  v121 = 0;
  v122 = 0x10000000;
  v123 = &SsBatchSid;
  v76 = 0;
  v77 = 0;
  v78 = 0x10000000;
  v79 = qword_18005CDC0 + 80;
  v80 = 0;
  v81 = 0;
  v82 = 0x10000000;
  v83 = qword_18005CDC0 + 120;
  v84 = 0;
  v85 = 0;
  v86 = 0x10000000;
  v88 = 1;
  v89 = 0;
  v92 = 1;
  v93 = 0;
  v95 = qword_18005CDC0 + 72;
  v96 = 0;
  v97 = 0;
  v99 = qword_18005CDC0 + 64;
  if ( !SsGetDefaultSdFromRegistry((__int64)L"SrvsvcDefaultShareInfo", &pSourceSecurityDescriptor) )
    pSourceSecurityDescriptor = 0;
  v1 = 9;
  if ( SsRestrictNullSessions )
  {
    v2 = &v124;
    v3 = 8;
  }
  else
  {
    v2 = &v156;
    v3 = 9;
  }
  if ( SsRegenerateSecurityDescriptors || (v4 = 0, SsRegenerateShareSecurityDescriptors) )
    v4 = 1;
  LOBYTE(v14) = v4;
  result = CreateSecurityObject(
             (const WCHAR **)SsShareFileSecurityObject,
             L"SrvsvcShareFileInfo",
             (struct _GENERIC_MAPPING *)SsShareMapping,
             (int)v2,
             v3,
             SsUpgradeSecurityDescriptors,
             v14);
  if ( !(_DWORD)result )
  {
    if ( SsRestrictNullSessions )
    {
      v6 = &v192;
    }
    else
    {
      v6 = &v228;
      v1 = 10;
    }
    if ( SsRegenerateSecurityDescriptors || (v7 = 0, SsRegenerateShareSecurityDescriptors) )
      v7 = 1;
    LOBYTE(v15) = v7;
    result = CreateSecurityObject(
               &SsSharePrintSecurityObject,
               L"SrvsvcSharePrintInfo",
               (struct _GENERIC_MAPPING *)SsShareMapping,
               (int)v6,
               v1,
               SsUpgradeSecurityDescriptors,
               v15);
    if ( !(_DWORD)result )
    {
      if ( SsRestrictNullSessions )
      {
        v8 = &v20;
        v9 = 4;
      }
      else
      {
        v8 = &v36;
        v9 = 5;
      }
      if ( SsRegenerateSecurityDescriptors || (v10 = 0, SsRegenerateShareSecurityDescriptors) )
        v10 = 1;
      LOBYTE(v16) = v10;
      result = CreateSecurityObject(
                 (const WCHAR **)SsShareAdminSecurityObject,
                 L"SrvsvcShareAdminInfo",
                 (struct _GENERIC_MAPPING *)SsShareMapping,
                 (int)v8,
                 v9,
                 SsUpgradeSecurityDescriptors,
                 v16);
      if ( !(_DWORD)result )
      {
        if ( SsRegenerateSecurityDescriptors || (v11 = 0, SsRegenerateShareSecurityDescriptors) )
          v11 = 1;
        LOBYTE(v17) = v11;
        result = CreateSecurityObject(
                   (const WCHAR **)SsShareChangeSecurityObject,
                   L"SrvsvcShareChange",
                   (struct _GENERIC_MAPPING *)SsShareMapping,
                   (int)&v76,
                   6,
                   SsUpgradeSecurityDescriptors,
                   v17);
        if ( !(_DWORD)result )
        {
          v12 = SsRestrictNullSessions;
          SsRestrictNullSessions = 0;
          if ( SsRegenerateSecurityDescriptors || (v13 = 0, SsRegenerateShareSecurityDescriptors) )
            v13 = 1;
          LOBYTE(v18) = v13;
          result = CreateSecurityObject(
                     (const WCHAR **)SsShareConnectSecurityObject,
                     L"SrvsvcShareConnect",
                     (struct _GENERIC_MAPPING *)SsShareConnectMapping,
                     (int)&v56,
                     5,
                     SsUpgradeSecurityDescriptors,
                     v18);
          if ( !(_DWORD)result )
          {
            SsRestrictNullSessions = v12;
            if ( !SsRegenerateSecurityDescriptors && !SsRegenerateShareSecurityDescriptors )
              v0 = 0;
            LOBYTE(v19) = v0;
            return CreateSecurityObject(
                     (const WCHAR **)SsShareAdmConnectSecurityObject,
                     L"SrvsvcShareAdminConnect",
                     (struct _GENERIC_MAPPING *)SsShareConnectMapping,
                     (int)&v100,
                     6,
                     SsUpgradeSecurityDescriptors,
                     v19);
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800275a0  push    rbp
0x1800275a2  push    rbx
0x1800275a3  push    rsi
0x1800275a4  push    rdi
0x1800275a5  push    r12
0x1800275a7  push    r13
0x1800275a9  push    r14
0x1800275ab  push    r15
0x1800275ad  lea     rbp, [rsp-328h]
0x1800275b5  sub     rsp, 428h
0x1800275bc  mov     rbx, cs:qword_18005CDC0
0x1800275c3  lea     rax, SsInteractiveSid
0x1800275ca  xor     r12d, r12d
0x1800275cd  mov     [rbp+360h+var_198], rax
0x1800275d4  mov     r8d, 10000000h
0x1800275da  mov     [rbp+360h+var_200], r12w
0x1800275e2  mov     [rbp+360h+var_1FC], r8d
0x1800275e9  lea     r15, SsAccessControlAssistanceOperatorsSid
0x1800275f0  mov     [rbp+360h+var_1EC], r8d
0x1800275f7  lea     r11, [rbx+50h]
0x1800275fb  lea     r14d, [r12+2]
0x180027600  mov     [rbp+360h+var_27C], r8d
0x180027607  lea     edi, [r12+1]
0x18002760c  mov     [rbp+360h+var_26C], r8d
0x180027613  xor     r8d, r8d
0x180027616  mov     [rbp+360h+var_1FE], r12b
0x18002761d  lea     r10, [rbx+78h]
0x180027621  mov     [rbp+360h+var_260], r8w
0x180027629  mov     esi, 80000000h
0x18002762e  mov     [rbp+360h+var_25E], r8b
0x180027635  lea     rcx, [rbx+30h]
0x180027639  mov     [rbp+360h+var_250], r8w
0x180027641  mov     [rbp+360h+var_24E], r8b
0x180027648  lea     rdx, [rbx+8]
0x18002764c  mov     [rbp+360h+var_1F0], r12w
0x180027654  lea     r8, [rbx+40h]
0x180027658  mov     [rbp+360h+var_1EE], r12b
0x18002765f  lea     r9, [rbx+48h]
0x180027663  mov     [rbp+360h+var_1E0], r12w
0x18002766b  lea     r13, SsServiceSid
0x180027672  mov     [rbp+360h+var_1DE], r12b
0x180027679  mov     [rbp+360h+var_1D0], r12w
0x180027681  mov     [rbp+360h+var_1CE], r12b
0x180027688  mov     [rbp+360h+var_1C0], r12w
0x180027690  mov     [rbp+360h+var_1BE], r12b
0x180027697  mov     [rbp+360h+var_1B0], r12w
0x18002769f  mov     [rbp+360h+var_1AE], r12b
0x1800276a6  mov     [rbp+360h+var_1A0], r12w
0x1800276ae  mov     [rbp+360h+var_19E], r12b
0x1800276b5  mov     [rbp+360h+var_190], r12w
0x1800276bd  mov     [rbp+360h+var_18E], r12b
0x1800276c4  mov     [rbp+360h+var_180], r12w
0x1800276cc  mov     [rbp+360h+var_17E], r12b
0x1800276d3  lea     r12, SsBatchSid
0x1800276da  mov     [rbp+360h+var_228], rax
0x1800276e1  xor     eax, eax
0x1800276e3  mov     [rbp+360h+var_178], r12
0x1800276ea  mov     [rbp+360h+var_248], r8
0x1800276f1  mov     [rbp+360h+var_1F8], r11
0x1800276f8  mov     [rbp+360h+var_1E8], r10
0x1800276ff  mov     [rbp+360h+var_1DC], esi
0x180027705  mov     [rbp+360h+var_1D8], r15
0x18002770c  mov     [rbp+360h+var_1CC], edi
0x180027712  mov     [rbp+360h+var_1C8], rdx
0x180027719  mov     [rbp+360h+var_1BC], edi
0x18002771f  mov     [rbp+360h+var_1B8], r9
0x180027726  mov     [rbp+360h+var_1AC], r14d
0x18002772d  mov     [rbp+360h+var_1A8], rcx
0x180027734  mov     [rbp+360h+var_19C], r14d
0x18002773b  mov     [rbp+360h+var_18C], r14d
0x180027742  mov     [rbp+360h+var_188], r13
0x180027749  mov     [rbp+360h+var_17C], r14d
0x180027750  mov     [rbp+360h+var_280], 0
0x180027759  mov     [rbp+360h+var_27E], 0
0x180027760  mov     [rbp+360h+var_278], r11
0x180027767  mov     [rbp+360h+var_270], 0
0x180027770  mov     [rbp+360h+var_26E], 0
0x180027777  mov     [rbp+360h+var_268], r10
0x18002777e  mov     [rbp+360h+var_25C], esi
0x180027784  mov     [rbp+360h+var_258], r15
0x18002778b  mov     [rbp+360h+var_24C], edi
0x180027791  mov     [rbp+360h+var_240], 0
0x18002779a  mov     [rbp+360h+var_23E], 0
0x1800277a1  mov     [rbp+360h+var_23C], r14d
0x1800277a8  mov     [rbp+360h+var_238], rcx
0x1800277af  mov     [rbp+360h+var_230], 0
0x1800277b8  mov     [rbp+360h+var_22E], 0
0x1800277bf  mov     [rbp+360h+var_22C], r14d
0x1800277c6  mov     [rbp+360h+var_220], ax
0x1800277cd  mov     [rbp+360h+var_21E], al
0x1800277d3  mov     [rbp+360h+var_21C], r14d
0x1800277da  mov     [rbp+360h+var_218], r13
0x1800277e1  mov     eax, 10000000h
0x1800277e6  xor     r13d, r13d
0x1800277e9  mov     [rbp+360h+var_DC], eax
0x1800277ef  mov     [rbp+360h+var_210], r13w
0x1800277f7  mov     [rbp+360h+var_20E], r13b
0x1800277fe  mov     [rbp+360h+var_E0], r13w
0x180027806  mov     [rbp+360h+var_DE], r13b
0x18002780d  mov     [rbp+360h+var_D0], r13w
0x180027815  mov     [rbp+360h+var_CE], r13b
0x18002781c  mov     [rbp+360h+var_C0], r13w
0x180027824  mov     [rbp+360h+var_BE], r13b
0x18002782b  mov     [rbp+360h+var_B0], r13w
0x180027833  mov     [rbp+360h+var_AE], r13b
0x18002783a  mov     [rbp+360h+var_A0], r13w
0x180027842  mov     [rbp+360h+var_9E], r13b
0x180027849  mov     [rbp+360h+var_90], r13w
0x180027851  mov     [rbp+360h+var_8E], r13b
0x180027858  mov     [rbp+360h+var_80], r13w
0x180027860  mov     [rbp+360h+var_7E], r13b
0x180027867  mov     [rbp+360h+var_70], r13w
0x18002786f  mov     [rbp+360h+var_6E], r13b
0x180027876  lea     r13, SsInteractiveSid
0x18002787d  mov     [rbp+360h+var_68], r13
0x180027884  xor     r13d, r13d
0x180027887  mov     [rbp+360h+var_CC], eax
0x18002788d  mov     [rbp+360h+var_BC], eax
0x180027893  lea     rax, [rbx+80h]
0x18002789a  mov     [rbp+360h+var_60], r13w
0x1800278a2  mov     [rbp+360h+var_5E], r13b
0x1800278a9  lea     r13, SsServiceSid
0x1800278b0  mov     [rbp+360h+var_B8], rax
0x1800278b7  mov     [rbp+360h+var_78], rcx
0x1800278be  mov     [rbp+360h+var_148], rax
0x1800278c5  xor     eax, eax
0x1800278c7  mov     [rbp+360h+var_118], rcx
0x1800278ce  lea     rcx, SsInteractiveSid
0x1800278d5  mov     [rbp+360h+var_58], r13
0x1800278dc  mov     [rbp+360h+var_20C], r14d
0x1800278e3  mov     [rbp+360h+var_208], r12
0x1800278ea  mov     [rbp+360h+var_D8], r11
0x1800278f1  mov     [rbp+360h+var_C8], r10
0x1800278f8  mov     [rbp+360h+var_AC], esi
0x1800278fe  mov     [rbp+360h+var_A8], r15
0x180027905  mov     [rbp+360h+var_9C], edi
0x18002790b  mov     [rbp+360h+var_98], rdx
0x180027912  mov     [rbp+360h+var_8C], edi
0x180027918  mov     [rbp+360h+var_88], r9
0x18002791f  mov     [rbp+360h+var_7C], r14d
0x180027926  mov     [rbp+360h+var_6C], r14d
0x18002792d  mov     [rbp+360h+var_5C], r14d
0x180027934  mov     [rbp+360h+var_50], 0
0x18002793d  mov     [rbp+360h+var_4E], 0
0x180027944  mov     [rbp+360h+var_4C], r14d
0x18002794b  mov     [rbp+360h+var_48], r12
0x180027952  mov     [rbp+360h+var_170], 0
0x18002795b  mov     [rbp+360h+var_16E], 0
0x180027962  mov     [rbp+360h+var_16C], 10000000h
0x18002796c  mov     [rbp+360h+var_168], r11
0x180027973  mov     [rbp+360h+var_160], 0
0x18002797c  mov     [rbp+360h+var_15E], 0
0x180027983  mov     [rbp+360h+var_15C], 10000000h
0x18002798d  mov     [rbp+360h+var_158], r10
0x180027994  mov     [rbp+360h+var_150], 0
0x18002799d  mov     [rbp+360h+var_14E], 0
0x1800279a4  mov     [rbp+360h+var_14C], 10000000h
0x1800279ae  mov     [rbp+360h+var_140], ax
0x1800279b5  mov     [rbp+360h+var_13E], al
0x1800279bb  mov     [rbp+360h+var_13C], esi
0x1800279c1  mov     [rbp+360h+var_138], r15
0x1800279c8  mov     [rbp+360h+var_130], ax
0x1800279cf  mov     [rbp+360h+var_12E], al
0x1800279d5  mov     [rbp+360h+var_12C], edi
0x1800279db  mov     [rbp+360h+var_128], r8
0x1800279e2  mov     [rbp+360h+var_120], ax
0x1800279e9  mov     [rbp+360h+var_11E], al
0x1800279ef  mov     [rbp+360h+var_11C], r14d
0x1800279f6  mov     [rbp+360h+var_110], ax
0x1800279fd  mov     [rbp+360h+var_10E], al
0x180027a03  mov     [rbp+360h+var_10C], r14d
0x180027a0a  mov     [rbp+360h+var_108], rcx
0x180027a11  mov     esi, 10000000h
0x180027a16  mov     [rbp+360h+var_100], ax
0x180027a1d  mov     [rbp+360h+var_FE], al
0x180027a23  mov     [rbp+360h+var_FC], r14d
0x180027a2a  mov     [rbp+360h+var_F0], ax
0x180027a31  mov     [rbp+360h+var_EE], al
0x180027a37  mov     [rbp+360h+var_EC], r14d
0x180027a3e  mov     [rbp+360h+var_3E0], ax
0x180027a42  mov     [rbp+360h+var_3DE], al
0x180027a45  mov     [rbp+360h+var_3D0], ax
0x180027a49  mov     [rbp+360h+var_3CE], al
0x180027a4c  mov     [rbp+360h+var_3CC], r14d
0x180027a50  mov     [rbp+360h+var_3C0], ax
0x180027a54  mov     [rbp+360h+var_3BE], al
0x180027a57  mov     [rbp+360h+var_3BC], r14d
0x180027a5b  mov     [rbp+360h+var_3B0], ax
0x180027a5f  mov     [rbp+360h+var_3AE], al
0x180027a62  mov     [rbp+360h+var_3A0], ax
0x180027a66  mov     [rbp+360h+var_39E], al
0x180027a69  mov     [rsp+460h+var_420], ax
0x180027a6e  mov     [rsp+460h+var_41E], al
0x180027a72  mov     [rsp+460h+var_410], ax
0x180027a77  mov     [rsp+460h+var_40E], al
0x180027a7b  mov     [rsp+460h+var_40C], r14d
0x180027a80  mov     [rsp+460h+var_400], ax
0x180027a85  mov     [rsp+460h+var_3FE], al
0x180027a89  lea     rax, [rbx+88h]
0x180027a90  mov     [rsp+460h+var_3FC], r14d
0x180027a95  xor     r14d, r14d
0x180027a98  mov     [rsp+460h+var_3F0], r14w
0x180027a9e  mov     [rsp+460h+var_3EE], r14b
0x180027aa3  mov     [rbp+360h+var_390], r14w
0x180027aa8  mov     [rbp+360h+var_38E], r14b
0x180027aac  mov     [rbp+360h+var_380], r14w
0x180027ab1  mov     [rbp+360h+var_37E], r14b
0x180027ab5  mov     [rbp+360h+var_370], r14w
0x180027aba  mov     [rbp+360h+var_36E], r14b
0x180027abe  mov     [rbp+360h+var_368], rax
0x180027ac2  mov     [rbp+360h+var_360], r14w
0x180027ac7  mov     [rbp+360h+var_35E], r14b
0x180027acb  mov     [rbp+360h+var_350], r14w
0x180027ad0  mov     [rbp+360h+var_34E], r14b
0x180027ad4  mov     [rbp+360h+var_2E0], r14w
0x180027adc  mov     [rbp+360h+var_2DE], r14b
0x180027ae3  mov     [rbp+360h+var_2D0], r14w
0x180027aeb  mov     [rbp+360h+var_2CE], r14b
0x180027af2  mov     [rbp+360h+var_2C0], r14w
0x180027afa  mov     [rbp+360h+var_2BE], r14b
0x180027b01  mov     [rbp+360h+var_2B8], rax
0x180027b08  mov     [rbp+360h+var_2B0], r14w
0x180027b10  mov     [rbp+360h+var_2AE], r14b
0x180027b17  mov     [rbp+360h+var_F8], r13
0x180027b1e  mov     [rbp+360h+var_E8], r12
0x180027b25  mov     [rbp+360h+var_3DC], esi
0x180027b28  mov     [rbp+360h+var_3D8], r11
0x180027b2c  mov     [rbp+360h+var_3C8], r10
0x180027b30  mov     [rbp+360h+var_3B8], r15
0x180027b34  mov     [rbp+360h+var_3AC], edi
0x180027b37  mov     [rbp+360h+var_3A8], rdx
0x180027b3b  mov     [rbp+360h+var_39C], edi
0x180027b3e  mov     [rbp+360h+var_398], r9
0x180027b42  mov     [rsp+460h+var_41C], esi
0x180027b46  mov     [rsp+460h+var_418], r11
0x180027b4b  mov     [rsp+460h+var_408], r10
0x180027b50  mov     [rsp+460h+var_3F8], r15
0x180027b55  mov     [rsp+460h+var_3EC], edi
0x180027b59  mov     [rsp+460h+var_3E8], r8
0x180027b5e  mov     [rbp+360h+var_38C], esi
0x180027b61  mov     [rbp+360h+var_388], r11
0x180027b65  mov     [rbp+360h+var_37C], esi
0x180027b68  mov     [rbp+360h+var_378], r10
0x180027b6c  mov     [rbp+360h+var_36C], esi
0x180027b6f  mov     [rbp+360h+var_35C], edi
0x180027b72  mov     [rbp+360h+var_358], rdx
0x180027b76  mov     [rbp+360h+var_34C], edi
0x180027b79  mov     [rbp+360h+var_348], r9
0x180027b7d  mov     [rbp+360h+var_2DC], esi
0x180027b83  mov     [rbp+360h+var_2D8], r11
0x180027b8a  mov     [rbp+360h+var_2CC], esi
0x180027b90  mov     [rbp+360h+var_2C8], r10
0x180027b97  mov     [rbp+360h+var_2BC], esi
0x180027b9d  mov     [rbp+360h+var_2A8], rcx
0x180027ba4  lea     rax, [rbx+68h]
0x180027ba8  mov     ecx, 0F0013h
0x180027bad  mov     [rbp+360h+var_318], rax
0x180027bb1  mov     [rbp+360h+var_30C], ecx
0x180027bb4  lea     rax, [rbx+60h]
0x180027bb8  mov     [rbp+360h+var_2FC], ecx
0x180027bbb  lea     rdx, pSourceSecurityDescriptor
0x180027bc2  mov     [rbp+360h+var_2EC], ecx
0x180027bc5  lea     rcx, aSrvsvcdefaults; "SrvsvcDefaultShareInfo"
0x180027bcc  mov     [rbp+360h+var_308], rax
0x180027bd0  mov     [rbp+360h+var_2AC], esi
0x180027bd6  mov     [rbp+360h+var_2A0], r14w
0x180027bde  mov     [rbp+360h+var_29E], r14b
0x180027be5  mov     [rbp+360h+var_29C], esi
0x180027beb  mov     [rbp+360h+var_298], r13
0x180027bf2  mov     [rbp+360h+var_290], r14w
0x180027bfa  mov     [rbp+360h+var_28E], r14b
0x180027c01  mov     [rbp+360h+var_28C], esi
0x180027c07  mov     [rbp+360h+var_288], r12
0x180027c0e  mov     [rbp+360h+var_340], r14w
0x180027c13  mov     [rbp+360h+var_33E], r14b
0x180027c17  mov     [rbp+360h+var_33C], esi
0x180027c1a  mov     [rbp+360h+var_338], r11
0x180027c1e  mov     [rbp+360h+var_330], r14w
0x180027c23  mov     [rbp+360h+var_32E], r14b
0x180027c27  mov     [rbp+360h+var_32C], esi
0x180027c2a  mov     [rbp+360h+var_328], r10
0x180027c2e  mov     [rbp+360h+var_320], r14w
0x180027c33  mov     [rbp+360h+var_31E], r14b
0x180027c37  mov     [rbp+360h+var_31C], esi
0x180027c3a  mov     [rbp+360h+var_310], di
0x180027c3e  mov     [rbp+360h+var_30E], r14b
0x180027c42  mov     [rbp+360h+var_300], di
0x180027c46  mov     [rbp+360h+var_2FE], r14b
0x180027c4a  mov     [rbp+360h+var_2F8], r9
0x180027c4e  mov     [rbp+360h+var_2F0], r14w
0x180027c53  mov     [rbp+360h+var_2EE], r14b
0x180027c57  mov     [rbp+360h+var_2E8], r8
0x180027c5b  call    SsGetDefaultSdFromRegistry
0x180027c60  test    al, al
0x180027c62  jnz     short loc_180027C6B
0x180027c64  mov     cs:pSourceSecurityDescriptor, r14
0x180027c6b  cmp     cs:SsRestrictNullSessions, r14b
0x180027c72  mov     ebx, 9
0x180027c77  jz      short loc_180027C85
0x180027c79  lea     r9, [rbp+360h+var_280]
  ... truncated ...
```
