# InterfaceMgr::EnableWFDGOMode(_TETHERING_SESSION_CONNECTION_SETTINGS *)

- ea: `0x1800110d4`
- end: `0x18001272f`
- name: `?EnableWFDGOMode@InterfaceMgr@@AEAAJPEAU_TETHERING_SESSION_CONNECTION_SETTINGS@@@Z`
- size: `5723`
- prototype: `__int64 __fastcall(InterfaceMgr *__hidden this, struct _TETHERING_SESSION_CONNECTION_SETTINGS *)`
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x180010a34`
- `0x180010e84`

## callees

- `0x180002590`
- `0x180003088`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000fae4`
- `0x18000fc24`
- `0x18000fe0c`
- `0x18000fedc`
- `0x1800107fc`
- `0x1800110d4`
- `0x180013604`
- `0x180013d98`
- `0x180014074`
- `0x180027130`
- `0x1800272c0`
- `0x180027394`
- `0x18002b1f0`
- `0x18002bc08`
- `0x18002d66c`
- `0x18002dc10`
- `0x18002e538`
- `0x180031580`
- `0x180031604`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800126ec`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800126ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800125d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800125d7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800119a2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800119a2`
- `wlanapi!WFDOpenLegacySessionInt` at `0x180011e00`
- `wlanapi!WFDOpenLegacySessionInt` at `0x180011e00`
- `wlanapi!WFDSetPropertyInt` at `0x1800114cc`
- `wlanapi!WFDSetPropertyInt` at `0x1800115d1`
- `wlanapi!WFDSetPropertyInt` at `0x18001169b`
- `wlanapi!WFDSetPropertyInt` at `0x1800119f9`
- `wlanapi!WFDSetPropertyInt` at `0x180011d39`
- `wlanapi!WFDSetPropertyInt` at `0x1800114cc`
- `wlanapi!WFDSetPropertyInt` at `0x1800115d1`
- `wlanapi!WFDSetPropertyInt` at `0x18001169b`
- `wlanapi!WFDSetPropertyInt` at `0x1800119f9`
- `wlanapi!WFDSetPropertyInt` at `0x180011d39`
- `wlanapi!WFDRegisterNotificationInt` at `0x180011413`
- `wlanapi!WFDRegisterNotificationInt` at `0x180011413`
- `wlanapi!WFDRegisterVMgrCallerInt` at `0x1800113b9`
- `wlanapi!WFDRegisterVMgrCallerInt` at `0x1800113b9`
- `wlanapi!WFDQueryPropertyInt` at `0x18001139e`
- `wlanapi!WFDQueryPropertyInt` at `0x1800116f1`
- `wlanapi!WFDQueryPropertyInt` at `0x18001139e`
- `wlanapi!WFDQueryPropertyInt` at `0x1800116f1`
- `wlanapi!WFDOpenHandleInt` at `0x1800112c5`
- `wlanapi!WFDOpenHandleInt` at `0x1800112c5`
- `wlanapi!WlanNotifyVsIeProviderInt` at `0x180011f89`
- `wlanapi!WlanNotifyVsIeProviderInt` at `0x180011f89`
- `wlanapi!WFDStartUsingGroupExInt` at `0x180011bef`
- `wlanapi!WFDStartUsingGroupExInt` at `0x180011bef`
- `wlanapi!WFDFreeMemoryInt` at `0x180011ca5`
- `wlanapi!WFDFreeMemoryInt` at `0x1800125ee`
- `wlanapi!WFDFreeMemoryInt` at `0x180012608`
- `wlanapi!WFDFreeMemoryInt` at `0x180011ca5`
- `wlanapi!WFDFreeMemoryInt` at `0x1800125ee`
- `wlanapi!WFDFreeMemoryInt` at `0x180012608`
- `wlanapi!WiFiDisplaySetSinkStateInt` at `0x180011268`
- `wlanapi!WiFiDisplaySetSinkStateInt` at `0x180011268`

## string_xrefs

- `0x18001131a`: `WFDOpenHandleInt`
- `0x180011330`: `WFDOpenHandleInt`
- `0x180011994`: `System\CurrentControlSet\Services\IcsSvc\Settings`
- `0x180011cf7`: `UpdateWFDGOSessionParams`
- `0x180011d10`: `UpdateWFDGOSessionParams`
- `0x180011e56`: `WFDOpenLegacySessionInt`
- `0x180011e6c`: `WFDOpenLegacySessionInt`

## pseudocode

```c
__int64 __fastcall InterfaceMgr::EnableWFDGOMode(InterfaceMgr *this, struct _TETHERING_SESSION_CONNECTION_SETTINGS *a2)
{
  TetheringServiceTelemetry *v3; // rdi
  void *v4; // rbx
  _QWORD *v5; // r15
  __int64 v6; // rax
  int v7; // eax
  __int64 v8; // r8
  signed int updated; // esi
  _WORD *v10; // rdi
  __int64 v11; // rdx
  unsigned int v12; // eax
  int v13; // eax
  __int64 v14; // r8
  _WORD *v15; // rdi
  int v16; // eax
  __int64 v17; // r8
  _WORD *v18; // rdi
  _DWORD *SettingValueWithIccidInternal; // rax
  int v20; // eax
  __int64 v21; // r8
  _WORD *v22; // rdi
  int v23; // eax
  __int64 v24; // r8
  int v25; // eax
  __int64 v26; // r8
  _WORD *v27; // rdi
  _WORD *v28; // rdi
  unsigned __int64 v29; // rdx
  bool v30; // cl
  __int64 v31; // r13
  __int64 v32; // r8
  _WORD *v33; // rdi
  LSTATUS ValueW; // eax
  int v35; // eax
  __int64 v36; // r8
  _WORD *v37; // rdi
  InterfaceMgr *v38; // rax
  unsigned __int64 v39; // rdi
  char *v40; // rsi
  char *v41; // rax
  size_t v42; // rdi
  _DWORD *v43; // rdi
  struct _TETHERING_SESSION_CONNECTION_SETTINGS *v44; // rsi
  int v45; // eax
  int v46; // ecx
  int v47; // eax
  __int64 v48; // r8
  _WORD *v49; // rdi
  InterfaceMgr *v50; // rdi
  __int64 v51; // r8
  _WORD *v52; // rdi
  int v53; // eax
  __int64 v54; // r8
  _WORD *v55; // rdi
  int v56; // eax
  __int64 v57; // r8
  _WORD *v58; // rdi
  int WlanStationMacAddress; // eax
  __int64 v60; // r8
  _WORD *v61; // rdi
  signed int v62; // eax
  __int64 v63; // r8
  _WORD *v64; // rdi
  InterfaceMgr *v65; // r13
  struct TetheringSessionTelemetry *v66; // rcx
  int Session; // edi
  int v68; // edi
  int v69; // r15d
  TetheringServiceTelemetry *v70; // rcx
  _DWORD *v71; // r8
  int v72; // edx
  struct _TETHERING_SESSION_CONNECTION_SETTINGS *v73; // r9
  int v74; // ecx
  unsigned __int64 v75; // r13
  int v76; // eax
  int v77; // edx
  int v78; // edx
  __int64 v79; // rdx
  char **v80; // rcx
  unsigned __int64 v81; // rdx
  void **v82; // r9
  char *v83; // r15
  __int64 v84; // rdi
  _WORD *v85; // r9
  char **v86; // rcx
  unsigned __int64 v87; // rdx
  char *v88; // r15
  __int64 v89; // rdi
  __int64 v90; // r8
  _WORD *v91; // r9
  void **v92; // rcx
  unsigned __int64 v93; // rdx
  char *v94; // r15
  __int64 v95; // rdi
  __int64 v96; // r8
  _WORD *v97; // r9
  void **v98; // rcx
  unsigned __int64 v99; // rdx
  char *v100; // r15
  __int64 v101; // rdi
  __int64 v102; // r8
  _WORD *v103; // r9
  void **v104; // rcx
  unsigned __int64 v105; // rdx
  char *v106; // r15
  __int64 v107; // rdi
  __int64 v108; // r8
  _WORD *v109; // r9
  void **v110; // rcx
  unsigned __int64 v111; // rdx
  char *v112; // r15
  __int64 v113; // rdi
  __int64 v114; // r8
  _WORD *v115; // r9
  void **v116; // rcx
  void *v117; // r15
  int v118; // eax
  struct TetheringSessionTelemetry *v119; // rcx
  __int64; // rax
  unsigned __int64 v121; // rdi
  _WORD *v122; // rbx
  __int64 v123; // rax
  __int64 v124; // rsi
  size_t v125; // rcx
  _QWORD *v126; // rbx
  void *v127; // rax
  void *v128; // rcx
  _BYTE v129[4]; // [rsp+40h] [rbp-1168h] BYREF
  int v130; // [rsp+44h] [rbp-1164h]
  bool v131; // [rsp+48h] [rbp-1160h]
  InterfaceMgr *v132; // [rsp+50h] [rbp-1158h]
  bool v133; // [rsp+58h] [rbp-1150h]
  bool v134; // [rsp+59h] [rbp-114Fh]
  bool v135; // [rsp+5Ah] [rbp-114Eh]
  bool v136; // [rsp+5Bh] [rbp-114Dh]
  bool v137; // [rsp+5Ch] [rbp-114Ch]
  bool v138; // [rsp+5Dh] [rbp-114Bh]
  char v139; // [rsp+5Eh] [rbp-114Ah] BYREF
  char v140; // [rsp+5Fh] [rbp-1149h] BYREF
  _WORD *v141; // [rsp+60h] [rbp-1148h] BYREF
  struct TetheringSessionTelemetry *v142; // [rsp+68h] [rbp-1140h] BYREF
  int v143; // [rsp+70h] [rbp-1138h]
  int v144; // [rsp+74h] [rbp-1134h] BYREF
  int pvData; // [rsp+78h] [rbp-1130h] BYREF
  unsigned int v146; // [rsp+7Ch] [rbp-112Ch] BYREF
  struct _TETHERING_SESSION_CONNECTION_SETTINGS *v147; // [rsp+80h] [rbp-1128h]
  void *Block; // [rsp+88h] [rbp-1120h]
  __int64 v149; // [rsp+90h] [rbp-1118h] BYREF
  int v150; // [rsp+98h] [rbp-1110h] BYREF
  int v151; // [rsp+9Ch] [rbp-110Ch] BYREF
  int v152; // [rsp+A0h] [rbp-1108h] BYREF
  DWORD pcbData; // [rsp+A4h] [rbp-1104h] BYREF
  int v154; // [rsp+A8h] [rbp-1100h] BYREF
  int v155; // [rsp+ACh] [rbp-10FCh]
  void *v156[2]; // [rsp+B0h] [rbp-10F8h] BYREF
  __int64 v157; // [rsp+C0h] [rbp-10E8h]
  __int64 v158; // [rsp+C8h] [rbp-10E0h] BYREF
  InterfaceMgr *v159; // [rsp+D0h] [rbp-10D8h]
  __int128 v160; // [rsp+E0h] [rbp-10C8h] BYREF
  _BYTE v161[64]; // [rsp+F0h] [rbp-10B8h] BYREF
  _DWORD *v162; // [rsp+130h] [rbp-1078h]
  __int64 v163; // [rsp+138h] [rbp-1070h]
  void *Src[2]; // [rsp+140h] [rbp-1068h] BYREF
  unsigned __int64 v165; // [rsp+150h] [rbp-1058h]
  unsigned __int64 v166; // [rsp+158h] [rbp-1050h]
  _DWORD v167[2]; // [rsp+160h] [rbp-1048h] BYREF
  __int64 v168; // [rsp+168h] [rbp-1040h] BYREF
  unsigned __int16 v169[2048]; // [rsp+170h] [rbp-1038h] BYREF

  v147 = a2;
  v132 = this;
  v159 = this;
  *(_QWORD *)&v160 = a2;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  *(_OWORD *)Src = 0;
  v165 = 0;
  v166 = 7;
  LOWORD(Src[0]) = 0;
  memset_0(v169, 0, sizeof(v169));
  v149 = 0;
  v152 = 0;
  v139 = 1;
  v4 = 0;
  Block = 0;
  v154 = 1;
  v140 = 1;
  v138 = 0;
  v137 = 0;
  v131 = 0;
  v136 = 0;
  v135 = 0;
  v134 = 0;
  v133 = 0;
  v167[0] = 0;
  v167[1] = 2;
  v168 = 0;
  *(_OWORD *)v156 = 0;
  v157 = 0;
  v146 = 0;
  v141 = 0;
  v143 = 6;
  memset_0(v161, 0, 0x50u);
  v142 = 0;
  if ( *((_QWORD *)this + 25) || (v5 = (_QWORD *)((char *)this + 56), *((_QWORD *)this + 7)) )
  {
    updated = -2147019873;
    v130 = -2147019873;
    goto LABEL_183;
  }
  v6 = WiFiDisplaySetSinkStateInt(1);
  *((_QWORD *)this + 25) = v6;
  if ( !v6
    && WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids);
  }
  v150 = 0;
  v7 = WFDOpenHandleInt(1, &v150, (char *)this + 56);
  updated = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      updated = (unsigned __int16)v7 | 0x80070000;
    v130 = updated;
    if ( v166 < 0x10 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        Src,
        16,
        v8,
        L"WFDOpenHandleInt");
    }
    else
    {
      v10 = Src[0];
      v165 = 16;
      memmove_0(Src[0], L"WFDOpenHandleInt", 0x20u);
      v10[16] = 0;
    }
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_183;
    }
    v11 = 56;
    goto LABEL_19;
  }
  v143 = WFDQueryPropertyInt(*v5, 20, &v146, &v141);
  v155 = v143;
  v12 = WFDRegisterVMgrCallerInt(*v5, 5);
  if ( v12
    && WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids, v12);
  }
  v133 = 1;
  v13 = WFDRegisterNotificationInt(*v5, 1024, 1, InterfaceMgr::WfdNotificationCallback, v132, 0);
  updated = v13;
  if ( v13 )
  {
    if ( v13 > 0 )
      updated = (unsigned __int16)v13 | 0x80070000;
    v130 = updated;
    if ( v166 < 0x1A )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        Src,
        26,
        v14,
        L"WFDRegisterNotificationInt");
    }
    else
    {
      v15 = Src[0];
      v165 = 26;
      memmove_0(Src[0], L"WFDRegisterNotificationInt", 0x34u);
      v15[26] = 0;
    }
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_183;
    }
    v11 = 58;
    goto LABEL_19;
  }
  v16 = WFDSetPropertyInt(*v5, 6, 1, &v139);
  updated = v16;
  if ( v16 )
  {
    if ( v16 > 0 )
      updated = (unsigned __int16)v16 | 0x80070000;
    v130 = updated;
    if ( v166 < 0x31 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        Src,
        49,
        v17,
        L"WFDSetPropertyInt wfd_opcode_crossconnect_enabled");
    }
    else
    {
      v18 = Src[0];
      v165 = 49;
      memmove_0(Src[0], L"WFDSetPropertyInt wfd_opcode_crossconnect_enabled", 0x62u);
      v18[49] = 0;
    }
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_183;
    }
    v11 = 59;
    goto LABEL_19;
  }
  v134 = 1;
  v144 = 8;
  if ( *((_DWORD *)v132 + 30) == 8 )
    SettingValueWithIccidInternal = (_DWORD *)TetheringSettingsGetSettingValueWithIccidInternal(4, (char *)v132 + 128);
  else
    SettingValueWithIccidInternal = (_DWORD *)TetheringSettingsGetSettingValueGlobalInternal(14);
  Block = SettingValueWithIccidInternal;
  v4 = SettingValueWithIccidInternal;
  if ( SettingValueWithIccidInternal )
    v144 = *SettingValueWithIccidInternal;
  v20 = WFDSetPropertyInt(*v5, 9, 4, &v144);
  updated = v20;
  if ( v20 )
  {
    if ( v20 > 0 )
      updated = (unsigned __int16)v20 | 0x80070000;
    v130 = updated;
    if ( v166 < 0x29 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        Src,
        41,
        v21,
        L"WFDSetPropertyInt wfd_opcode_client_limit");
    }
    else
    {
      v22 = Src[0];
      v165 = 41;
      memmove_0(Src[0], L"WFDSetPropertyInt wfd_opcode_client_limit", 0x52u);
      v22[41] = 0;
    }
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_183;
    }
    v11 = 60;
    goto LABEL_19;
  }
  v135 = 1;
  v151 = 0;
  v23 = WFDSetPropertyInt(*v5, 8, 4, &v151);
  updated = v23;
  if ( v23 == 1168 )
  {
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids, 1168);
    }
  }
  else if ( v23 )
  {
    if ( v23 > 0 )
      updated = (unsigned __int16)v23 | 0x80070000;
    v130 = updated;
    if ( v166 < 0x2D )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        Src,
        45,
        v24,
        L"WFDSetPropertyInt wfd_opcode_reset_role_ports");
    }
    else
    {
      v28 = Src[0];
      v165 = 45;
      memmove_0(Src[0], L"WFDSetPropertyInt wfd_opcode_reset_role_ports", 0x5Au);
      v28[45] = 0;
    }
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_183;
    }
    v11 = 62;
    goto LABEL_19;
  }
  v25 = WFDQueryPropertyInt(*v5, 3, &v152, &v149);
  updated = v25;
  if ( v25 )
  {
    if ( v25 > 0 )
      updated = (unsigned __int16)v25 | 0x80070000;
    v130 = updated;
    if ( v166 < 0x33 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        Src,
        51,
        v26,
        L"WFDQueryPropertyInt wfd_opcode_current_device_state");
    }
    else
    {
      v27 = Src[0];
      v165 = 51;
      memmove_0(Src[0], L"WFDQueryPropertyInt wfd_opcode_current_device_state", 0x66u);
      v27[51] = 0;
    }
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_183;
    }
    v11 = 63;
    goto LABEL_19;
  }
  v29 = *((unsigned int *)v147 + 51);
  if ( (unsigned int)(v29 - 2) > 1 )
  {
    v30 = 0;
LABEL_81:
    LOBYTE(v29) = 0;
    goto LABEL_82;
  }
  v30 = 1;
  if ( (_DWORD)v29 != 2 )
    goto LABEL_81;
  LOBYTE(v29) = 1;
LABEL_82:
  v31 = (__int64)v147 + 4;
  updated = ((__int64 (__fastcall *)(unsigned __int16 *, unsigned __int64, unsigned __int8 (*)[6], unsigned __int16 *, wchar_t *, bool, bool))FormatWFDGOProfileString)(
              v169,
              v29,
              (unsigned __int8 (*)[6])(v149 + 4),
              (unsigned __int16 *)v147 + 2,
              (wchar_t *)v147 + 35,
              v30,
              v29);
  v130 = updated;
  if ( updated < 0 )
  {
    if ( v166 < 0x18 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        Src,
        24,
        v32,
        L"FormatWFDGOProfileString");
    }
    else
    {
      v33 = Src[0];
      v165 = 24;
      memmove_0(Src[0], L"FormatWFDGOProfileString", 0x30u);
      v33[24] = 0;
    }
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_183;
    }
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      64,
      (int)&WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids,
      updated,
      v31);
    goto LABEL_20;
  }
  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\IcsSvc\\Settings",
             L"Set80211Rate",
             0x10u,
             0,
             &pvData,
             &pcbData);
  if ( ValueW || pvData )
  {
    v35 = WFDSetPropertyInt(*v5, 14, 4, &v154);
    updated = v35;
    if ( v35 )
    {
      if ( v35 > 0 )
        updated = (unsigned __int16)v35 | 0x80070000;
      v130 = updated;
      if ( v166 < 0x2F )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          Src,
          47,
          v36,
          L"WFDSetPropertyInt wfd_opcode_enable_80211b_rate");
      }
      else
      {
        v37 = Src[0];
        v165 = 47;
        memmove_0(Src[0], L"WFDSetPropertyInt wfd_opcode_enable_80211b_rate", 0x5Eu);
        v37[47] = 0;
      }
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_183;
      }
      v11 = 65;
      goto LABEL_19;
    }
    v131 = 1;
  }
  else if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids);
  }
  v158 = 0;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v38 = v132;
    v39 = *(unsigned int *)v132;
    v40 = (char *)v156[1];
    if ( v39 >= (char *)v156[1] - (char *)v156[0] )
    {
      if ( v39 <= (char *)v156[1] - (char *)v156[0] )
      {
LABEL_115:
        v43 = v156[0];
        goto LABEL_353;
      }
      if ( v39 > v157 - (unsigned __int64)v156[0] )
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v156, v39);
LABEL_114:
        v38 = v132;
        goto LABEL_115;
      }
      v42 = v39 - ((char *)v156[1] - (char *)v156[0]);
      memset_0(v156[1], 0, v42);
      v41 = &v40[v42];
    }
    else
    {
      v41 = (char *)v156[0] + v39;
    }
    v156[1] = v41;
    goto LABEL_114;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v130 = -2147024882;
      v121 = v166;
      if ( v166 < 0xB )
      {
        if ( v166 <= 0x7FFFFFFFFFFFFFFELL - (v166 >> 1) )
        {
          v123 = 15;
          if ( v166 + (v166 >> 1) > 0xF )
            v123 = v166 + (v166 >> 1);
        }
        else
        {
          v123 = 0x7FFFFFFFFFFFFFFELL;
        }
        v124 = v123 + 1;
        if ( (unsigned __int64)(v123 + 1) > 0x7FFFFFFFFFFFFFFFLL )
          __scrt_throw_std_bad_array_new_length();
        v125 = 2 * v124;
        if ( 2 * v124 )
        {
          if ( v125 < 0x1000 )
          {
            v126 = operator new(v125);
          }
          else
          {
            if ( v125 + 39 < v125 )
              __scrt_throw_std_bad_array_new_length();
            v127 = operator new(v125 + 39);
            if ( !v127 )
              __fastfail(5u);
            v126 = (_QWORD *)(((unsigned __int64)v127 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
            *(v126 - 1) = v127;
          }
        }
        else
        {
          v126 = 0;
        }
        v165 = 11;
        v166 = v124 - 1;
        *(_OWORD *)v126 = *(_OWORD *)L"resize/data";
        *(_QWORD *)((char *)v126 + 14) = *(_QWORD *)L"data";
        *((_WORD *)v126 + 11) = 0;
        if ( v121 > 7 )
        {
          v128 = Src[0];
          if ( 2 * v121 + 2 >= 0x1000 )
          {
            if ( (unsigned __int64)Src[0] - *((_QWORD *)Src[0] - 1) - 8 > 0x1F )
              __fastfail(5u);
            v128 = (void *)*((_QWORD *)Src[0] - 1);
          }
          operator delete(v128);
        }
        Src[0] = v126;
      }
      else
      {
        v122 = Src[0];
        v165 = 11;
        memmove_0(Src[0], L"resize/data", 0x16u);
        v122[11] = 0;
      }
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids,
          2147942414LL);
      }
      updated = v130;
      v4 = Block;
      v143 = v155;
      v3 = WPP_GLOBAL_Control;
      v65 = v159;
      v132 = v159;
      v147 = (struct _TETHERING_SESSION_CONNECTION_SETTINGS *)v160;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18001204B);
LABEL_184:
      v66 = v142;
      if ( v142 )
      {
        v142 = 0;
        (*(void (__fastcall **)(struct TetheringSessionTelemetry *))(*(_QWORD *)v66 + 16LL))(v66);
        v3 = WPP_GLOBAL_Control;
      }
      if ( *(_QWORD *)&g_pTetheringSessionId.Data1 )
      {
        Session = ((int (__stdcall *)(TetheringServiceTelemetry *, struct _GUID *, struct TetheringSessionTelemetry **))TetheringServiceTelemetry::GetSession)(
                    v66,
                    *(struct _GUID **)&g_pTetheringSessionId.Data1,
                    &v142);
        if ( (Session < 0 || v142 && TetheringSessionTelemetry::Initialized((RTL_SRWLOCK *)v142)) && Session >= 0 )
        {
          v68 = 0;
          v129[0] = 0;
          if ( (int)TetheringIsFrequencySupportedInternal(3, v129) >= 0 )
            v68 = v129[0] != 0;
          v129[0] = 0;
          if ( (int)TetheringIsFrequencySupportedInternal(1, v129) >= 0 && v129[0] )
            v68 |= 2u;
          v129[0] = 0;
          if ( (int)TetheringIsFrequencySupportedInternal(2, v129) >= 0 && v129[0] )
            v68 |= 4u;
          v129[0] = 0;
          if ( (int)TetheringIsFrequencySupportedInternal(4, v129) >= 0 && v129[0] )
            v68 |= 8u;
          v69 = 0;
          v129[0] = 0;
          if ( (int)TetheringIsAuthSupportedInternal(1, v129) >= 0 )
            v69 = v129[0] != 0;
          v129[0] = 0;
          if ( (int)TetheringIsAuthSupportedInternal(2, v129) >= 0 && v129[0] )
            v69 |= 2u;
          v129[0] = 0;
          if ( (int)TetheringIsAuthSupportedInternal(3, v129) >= 0 && v129[0] )
            v69 |= 4u;
          TetheringServiceTelemetry::AcquireSessionData(
            v70,
            (RTL_SRWLOCK *)v142,
            (struct TetheringServiceTelemetry::SESSION_DATA *)v161);
          v71 = v162;
          *v162 = v68;
          v72 = 0;
          v73 = v147;
          switch ( *((_DWORD *)v147 + 50) )
          {
            case 1:
              v72 = 2;
              break;
            case 2:
              v72 = 4;
              break;
            case 3:
              v72 = 1;
              break;
            case 4:
              v72 = 8;
              break;
          }
          v71[1] = v72;
          v74 = *((_DWORD *)v65 + 29);
          v75 = -1;
          switch ( v74 )
          {
            case -1:
              v76 = 1;
              break;
            case 1:
              v76 = 2;
              break;
            case 2:
              v76 = 4;
              break;
            default:
              v76 = 0;
              if ( v74 == 5 )
                v76 = 8;
              break;
          }
          v71[2] = v76;
          v71[3] = v69;
          v77 = 0;
          switch ( *((_DWORD *)v73 + 51) )
          {
            case 1:
              v77 = 1;
              break;
            case 2:
              v77 = 2;
              break;
            case 3:
              v77 = 4;
              break;
          }
          v71[4] = v77;
          v78 = 0;
          if ( *((_DWORD *)v73 + 52) == 1 )
          {
            v78 = 1;
          }
          else if ( *((_DWORD *)v73 + 52) == 2 )
          {
            v78 = 2;
          }
          v71[9] = v78;
          v71[10] = 1;
          v79 = v163;
          *(_DWORD *)(v163 + 136) = updated;
          v80 = (char **)(v79 + 144);
          if ( (void **)(v79 + 144) != Src )
          {
            v81 = v165;
            v82 = Src;
            if ( v166 > 7 )
              v82 = (void **)Src[0];
            if ( v165 > (unsigned __int64)v80[3] )
            {
              std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                v80,
                v165,
                v71,
                v82);
            }
            else
            {
              if ( (unsigned __int64)v80[3] <= 7 )
                v83 = (char *)v80;
              else
                v83 = *v80;
              v80[2] = (char *)v165;
              v84 = 2 * v81;
              memmove_0(v83, v82, 2 * v81);
              *(_WORD *)&v83[v84] = 0;
            }
            v79 = v163;
          }
          if ( !v143 && v146 >= 0xE0C )
          {
            if ( __eh34_try(-1, 2) )
            {
              __eh34_scope_strut(2);
              v85 = v141 + 2;
              v86 = (char **)(v79 + 176);
              v87 = -1;
              do
                ++v87;
              while ( v85[v87] );
              if ( v87 > (unsigned __int64)v86[3] )
              {
                std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                  v86,
                  v87,
                  v71,
                  v85);
              }
              else
              {
                if ( (unsigned __int64)v86[3] <= 7 )
                  v88 = (char *)v86;
                else
                  v88 = *v86;
                v86[2] = (char *)v87;
                v89 = 2 * v87;
                memmove_0(v88, v85, 2 * v87);
                *(_WORD *)&v88[v89] = 0;
              }
              v91 = v141 + 258;
              v92 = (void **)(v163 + 208);
              v93 = -1;
              do
                ++v93;
              while ( v91[v93] );
              if ( v93 > *(_QWORD *)(v163 + 232) )
              {
                std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                  v92,
                  v93,
                  v90,
                  v91);
              }
              else
              {
                if ( *(_QWORD *)(v163 + 232) <= 7u )
                  v94 = (char *)(v163 + 208);
                else
                  v94 = (char *)*v92;
                *(_QWORD *)(v163 + 224) = v93;
                v95 = 2 * v93;
                memmove_0(v94, v91, 2 * v93);
                *(_WORD *)&v94[v95] = 0;
              }
              v97 = v141 + 514;
              v98 = (void **)(v163 + 240);
              v99 = -1;
              do
                ++v99;
              while ( v97[v99] );
              if ( v99 > *(_QWORD *)(v163 + 264) )
              {
                std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                  v98,
                  v99,
                  v96,
                  v97);
              }
              else
              {
                if ( *(_QWORD *)(v163 + 264) <= 7u )
                  v100 = (char *)(v163 + 240);
                else
                  v100 = (char *)*v98;
                *(_QWORD *)(v163 + 256) = v99;
                v101 = 2 * v99;
                memmove_0(v100, v97, 2 * v99);
                *(_WORD *)&v100[v101] = 0;
              }
              v103 = v141 + 770;
              v104 = (void **)(v163 + 272);
              v105 = -1;
              do
                ++v105;
              while ( v103[v105] );
              if ( v105 > *(_QWORD *)(v163 + 296) )
              {
                std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                  v104,
                  v105,
                  v102,
                  v103);
              }
              else
              {
                if ( *(_QWORD *)(v163 + 296) <= 7u )
                  v106 = (char *)(v163 + 272);
                else
                  v106 = (char *)*v104;
                *(_QWORD *)(v163 + 288) = v105;
                v107 = 2 * v105;
                memmove_0(v106, v103, 2 * v105);
                *(_WORD *)&v106[v107] = 0;
              }
              v109 = v141 + 1026;
              v110 = (void **)(v163 + 304);
              v111 = -1;
              do
                ++v111;
              while ( v109[v111] );
              if ( v111 > *(_QWORD *)(v163 + 328) )
              {
                std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                  v110,
                  v111,
                  v108,
                  v109);
              }
              else
              {
                if ( *(_QWORD *)(v163 + 328) <= 7u )
                  v112 = (char *)(v163 + 304);
                else
                  v112 = (char *)*v110;
                *(_QWORD *)(v163 + 320) = v111;
                v113 = 2 * v111;
                memmove_0(v112, v109, 2 * v111);
                *(_WORD *)&v112[v113] = 0;
              }
              v115 = v141 + 1282;
              v116 = (void **)(v163 + 336);
              do
                ++v75;
              while ( v115[v75] );
              if ( v75 > *(_QWORD *)(v163 + 360) )
              {
                std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                  v116,
                  v75,
                  v114,
                  v115);
              }
              else
              {
                if ( *(_QWORD *)(v163 + 360) <= 7u )
                  v117 = (void *)(v163 + 336);
                else
                  v117 = *v116;
                *(_QWORD *)(v163 + 352) = v75;
                memmove_0(v117, v115, 2 * v75);
                *((_WORD *)v117 + v75) = 0;
              }
            }
            if ( __eh34_catch(2) )
            {
              if ( __eh34_catch_ellipsis(2) )
              {
                if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids);
                }
                updated = v130;
                v4 = Block;
                v132 = v159;
                __eh34_try_continuation(2, &loc_1800125AE);
              }
            }
          }
          ReleaseSRWLockExclusive((PSRWLOCK)v142 + 2);
        }
        v3 = WPP_GLOBAL_Control;
      }
      if ( v141 )
      {
        WFDFreeMemoryInt(v141);
        v3 = WPP_GLOBAL_Control;
      }
      if ( v149 )
      {
        WFDFreeMemoryInt(v149);
        v3 = WPP_GLOBAL_Control;
      }
      if ( updated < 0 )
      {
        if ( (unsigned int)(updated + 2144067577) <= 1 )
        {
          updated = -2095972330;
        }
        else if ( (unsigned int)(updated + 2144067579) <= 1 )
        {
          updated = -2095972326;
        }
        else
        {
          v118 = -2095972347;
          if ( updated == -2144067575 )
            v118 = -2095972327;
          updated = v118;
        }
        InterfaceMgr::DisableWFDGOMode(v132, v138, v137, v131, v136, v135, v134, v133);
        v3 = WPP_GLOBAL_Control;
      }
      if ( v3 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)v3 + 2), 75, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids, (unsigned int)updated);
      v119 = v142;
      if ( v142 )
      {
        v142 = 0;
        (*(void (__fastcall **)(struct TetheringSessionTelemetry *))(*(_QWORD *)v119 + 16LL))(v119);
      }
      std::vector<unsigned char>::~vector<unsigned char>(v156);
      if ( v4 )
        free(v4);
      std::wstring::~wstring((char **)Src);
       = (unsigned int)updated;
    }
  }
LABEL_353:
  memset_0(v43, 0, *(unsigned int *)v38);
  *v43 = 2097409;
  *((_BYTE *)v43 + 4) = 1;
  *((_BYTE *)v43 + 6) = 1;
  v44 = v147;
  *((_BYTE *)v43 + 21) = *((_DWORD *)v147 + 52) == 2;
  if ( v131 )
    *((_BYTE *)v43 + 5) = 1;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      68,
      &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids,
      *((unsigned int *)v44 + 50));
  }
  v45 = *((_DWORD *)v44 + 50);
  if ( v45 == 3 )
  {
    v43[2] = 0;
  }
  else
  {
    if ( v45 == 2 )
    {
      v46 = 2;
    }
    else
    {
      v46 = 1;
      if ( v45 == 4 )
        v46 = 5;
    }
    v43[2] = 1;
    v43[3] = 28;
    v43[7] = v46;
    v43[8] = 0;
    v43[4] = 8;
    v43[6] = 8;
  }
  v47 = WFDStartUsingGroupExInt(*v5, v169, v43, &v158);
  updated = v47;
  if ( v47 )
  {
    if ( v47 > 0 )
      updated = (unsigned __int16)v47 | 0x80070000;
    v130 = updated;
    if ( v166 < 0x17 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        Src,
        23,
        v48,
        L"WFDStartUsingGroupExInt");
    }
    else
    {
      v49 = Src[0];
      v165 = 23;
      memmove_0(Src[0], L"WFDStartUsingGroupExInt", 0x2Eu);
      v49[23] = 0;
    }
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_183;
    }
    v11 = 69;
  }
  else
  {
    v136 = 1;
    WFDFreeMemoryInt(v158);
    v50 = v132;
    updated = InterfaceMgr::UpdateWFDGOSessionParams(v132);
    v130 = updated;
    if ( updated < 0 )
    {
      if ( v166 < 0x18 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          Src,
          24,
          v51,
          L"UpdateWFDGOSessionParams");
      }
      else
      {
        v52 = Src[0];
        v165 = 24;
        memmove_0(Src[0], L"UpdateWFDGOSessionParams", 0x30u);
        v52[24] = 0;
      }
      goto LABEL_20;
    }
    v53 = WFDSetPropertyInt(*v5, 7, 1, &v140);
    if ( v53 )
    {
      if ( v53 > 0 )
        updated = (unsigned __int16)v53 | 0x80070000;
      else
        updated = v53;
      v130 = updated;
      if ( v166 < 0x2C )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          Src,
          44,
          v54,
          L"WFDSetPropertyInt wfd_opcode_prevent_connect");
      }
      else
      {
        v55 = Src[0];
        v165 = 44;
        memmove_0(Src[0], L"WFDSetPropertyInt wfd_opcode_prevent_connect", 0x58u);
        v55[44] = 0;
      }
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_183;
      }
      v11 = 70;
    }
    else
    {
      v137 = 1;
      v56 = WFDOpenLegacySessionInt(*v5, v149 + 4, v169);
      if ( v56 )
      {
        if ( v56 > 0 )
          updated = (unsigned __int16)v56 | 0x80070000;
        else
          updated = v56;
        v130 = updated;
        if ( v166 < 0x17 )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            Src,
            23,
            v57,
            L"WFDOpenLegacySessionInt");
        }
        else
        {
          v58 = Src[0];
          v165 = 23;
          memmove_0(Src[0], L"WFDOpenLegacySessionInt", 0x2Eu);
          v58[23] = 0;
        }
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_183;
        }
        v11 = 71;
      }
      else
      {
        v138 = 1;
        WlanStationMacAddress = GetWlanStationMacAddress((GUID *)v132 + 5, (unsigned __int8 (*)[6])&v168);
        if ( !WlanStationMacAddress )
        {
          v160 = TETHERING_IE_PROVIDER_GUID;
          v62 = WlanNotifyVsIeProviderInt(&v160, 16, v167);
          if ( v62 )
          {
            updated = v62 > 0 ? (unsigned __int16)v62 | 0x80070000 : v62;
            v130 = updated;
            if ( v166 < 0x19 )
            {
              std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                Src,
                25,
                v63,
                L"WlanNotifyVsIeProviderInt");
            }
            else
            {
              v64 = Src[0];
              v165 = 25;
              memmove_0(Src[0], L"WlanNotifyVsIeProviderInt", 0x32u);
              v64[25] = 0;
              v50 = v132;
            }
            if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                73,
                &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids,
                (unsigned int)updated);
            }
          }
          *((_DWORD *)v50 + 48) = 1;
          goto LABEL_20;
        }
        if ( WlanStationMacAddress > 0 )
          updated = (unsigned __int16)WlanStationMacAddress | 0x80070000;
        else
          updated = WlanStationMacAddress;
        v130 = updated;
        if ( v166 < 0x18 )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            Src,
            24,
            v60,
            L"GetWlanStationMacAddress");
        }
        else
        {
          v61 = Src[0];
          v165 = 24;
          memmove_0(Src[0], L"GetWlanStationMacAddress", 0x30u);
          v61[24] = 0;
        }
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_183;
        }
        v11 = 72;
      }
    }
  }
LABEL_19:
  WPP_SF_d(*((_QWORD *)v3 + 2), v11, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids, (unsigned int)updated);
LABEL_20:
  v3 = WPP_GLOBAL_Control;
LABEL_183:
  v65 = v132;
  goto LABEL_184;
}

```

## disassembly

```asm
0x1800110d4  mov     [rsp+arg_10], rbx
0x1800110d9  mov     [rsp+arg_18], rsi
0x1800110de  push    rdi
0x1800110df  push    r12
0x1800110e1  push    r13
0x1800110e3  push    r14
0x1800110e5  push    r15
0x1800110e7  mov     eax, 1180h
0x1800110ec  call    _alloca_probe
0x1800110f1  sub     rsp, rax
0x1800110f4  mov     rax, cs:__security_cookie
0x1800110fb  xor     rax, rsp
0x1800110fe  mov     [rsp+11A8h+var_38], rax
0x180011106  mov     [rsp+11A8h+var_1128], rdx
0x18001110e  mov     rsi, rcx
0x180011111  mov     [rsp+11A8h+var_1158], rcx
0x180011116  mov     [rsp+11A8h+var_10D8], rcx
0x18001111e  mov     qword ptr [rsp+11A8h+var_10C8], rdx
0x180011126  lea     rax, WPP_GLOBAL_Control
0x18001112d  mov     rdi, cs:WPP_GLOBAL_Control
0x180011134  cmp     rdi, rax
0x180011137  jz      short loc_18001115B
0x180011139  test    byte ptr [rdi+1Ch], 8
0x18001113d  jz      short loc_18001115B
0x18001113f  mov     edx, 36h ; '6'
0x180011144  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x18001114b  mov     rcx, [rdi+10h]
0x18001114f  call    WPP_SF_
0x180011154  mov     rdi, cs:WPP_GLOBAL_Control
0x18001115b  xorps   xmm0, xmm0
0x18001115e  movups  xmmword ptr [rsp+11A8h+Src], xmm0
0x180011166  xor     r14d, r14d
0x180011169  mov     [rsp+11A8h+var_1058], r14
0x180011171  mov     [rsp+11A8h+var_1050], 7
0x18001117d  mov     word ptr [rsp+11A8h+Src], r14w
0x180011186  xor     edx, edx; Val
0x180011188  mov     r8d, 1000h; Size
0x18001118e  lea     rcx, [rsp+11A8h+var_1038]; void *
0x180011196  call    memset_0
0x18001119b  mov     [rsp+11A8h+var_1118], r14
0x1800111a3  mov     [rsp+11A8h+var_1108], r14d
0x1800111ab  lea     r12d, [r14+1]
0x1800111af  mov     [rsp+11A8h+var_114A], r12b
0x1800111b4  mov     ebx, r14d
0x1800111b7  mov     [rsp+11A8h+Block], rbx
0x1800111bf  mov     [rsp+11A8h+var_1100], r12d
0x1800111c7  mov     [rsp+11A8h+var_1149], r12b
0x1800111cc  mov     [rsp+11A8h+var_114B], r14b
0x1800111d1  mov     [rsp+11A8h+var_114C], r14b
0x1800111d6  mov     [rsp+11A8h+var_1160], r14b
0x1800111db  mov     [rsp+11A8h+var_114D], r14b
0x1800111e0  mov     [rsp+11A8h+var_114E], r14b
0x1800111e5  mov     [rsp+11A8h+var_114F], r14b
0x1800111ea  mov     [rsp+11A8h+var_1150], r14b
0x1800111ef  mov     [rsp+11A8h+var_1048], r14d
0x1800111f7  lea     r13d, [r14+2]
0x1800111fb  mov     [rsp+11A8h+var_1044], r13d
0x180011203  xor     eax, eax
0x180011205  mov     [rsp+11A8h+var_1040], rax
0x18001120d  xorps   xmm0, xmm0
0x180011210  movdqu  xmmword ptr [rsp+11A8h+var_10F8], xmm0
0x180011219  mov     [rsp+11A8h+var_10E8], r14
0x180011221  mov     [rsp+11A8h+var_112C], r14d
0x180011226  mov     [rsp+11A8h+var_1148], r14
0x18001122b  mov     [rsp+11A8h+var_1138], 6
0x180011233  xor     edx, edx; Val
0x180011235  lea     r8d, [r14+50h]; Size
0x180011239  lea     rcx, [rsp+11A8h+var_10B8]; void *
0x180011241  call    memset_0
0x180011246  mov     [rsp+11A8h+var_1140], r14
0x18001124b  cmp     [rsi+0C8h], r14
0x180011252  jnz     loc_18001208F
0x180011258  lea     r15, [rsi+38h]
0x18001125c  cmp     [r15], r14
0x18001125f  jnz     loc_18001208F
0x180011265  mov     ecx, r12d
0x180011268  call    cs:__imp_WiFiDisplaySetSinkStateInt
0x18001126e  mov     [rsi+0C8h], rax
0x180011275  test    rax, rax
0x180011278  jnz     short loc_1800112A8
0x18001127a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011281  lea     rdi, WPP_GLOBAL_Control
0x180011288  cmp     rcx, rdi
0x18001128b  jz      short loc_1800112AF
0x18001128d  test    [rcx+1Ch], r13b
0x180011291  jz      short loc_1800112AF
0x180011293  lea     edx, [rax+37h]
0x180011296  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x18001129d  mov     rcx, [rcx+10h]
0x1800112a1  call    WPP_SF_
0x1800112a6  jmp     short loc_1800112AF
0x1800112a8  lea     rdi, WPP_GLOBAL_Control
0x1800112af  mov     [rsp+11A8h+var_1110], r14d
0x1800112b7  mov     r8, r15
0x1800112ba  lea     rdx, [rsp+11A8h+var_1110]
0x1800112c2  mov     ecx, r12d
0x1800112c5  call    cs:__imp_WFDOpenHandleInt
0x1800112cb  mov     esi, eax
0x1800112cd  test    eax, eax
0x1800112cf  jz      loc_18001138C
0x1800112d5  jle     short loc_1800112E0
0x1800112d7  movzx   esi, ax
0x1800112da  or      esi, 80070000h
0x1800112e0  mov     [rsp+11A8h+var_1164], esi
0x1800112e4  mov     r13d, 10h
0x1800112ea  cmp     [rsp+11A8h+var_1050], r13
0x1800112f2  jb      short loc_180011330
0x1800112f4  lea     rdi, [rsp+11A8h+Src]
0x1800112fc  cmp     [rsp+11A8h+var_1050], 7
0x180011305  cmova   rdi, [rsp+11A8h+Src]
0x18001130e  mov     [rsp+11A8h+var_1058], r13
0x180011316  lea     r8d, [r13+10h]; Size
0x18001131a  lea     rdx, aWfdopenhandlei; "WFDOpenHandleInt"
0x180011321  mov     rcx, rdi; void *
0x180011324  call    memmove_0
0x180011329  mov     [rdi+20h], r14w
0x18001132e  jmp     short loc_180011347
0x180011330  lea     r9, aWfdopenhandlei; "WFDOpenHandleInt"
0x180011337  mov     rdx, r13
0x18001133a  lea     rcx, [rsp+11A8h+Src]
0x180011342  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180011347  mov     rdi, cs:WPP_GLOBAL_Control
0x18001134e  lea     rax, WPP_GLOBAL_Control
0x180011355  cmp     rdi, rax
0x180011358  jz      loc_180012098
0x18001135e  test    [rdi+1Ch], r12b
0x180011362  jz      loc_180012098
0x180011368  mov     edx, 38h ; '8'
0x18001136d  mov     r9d, esi
0x180011370  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x180011377  mov     rcx, [rdi+10h]
0x18001137b  call    WPP_SF_d
0x180011380  mov     rdi, cs:WPP_GLOBAL_Control
0x180011387  jmp     loc_180012098
0x18001138c  lea     r9, [rsp+11A8h+var_1148]
0x180011391  lea     r8, [rsp+11A8h+var_112C]
0x180011396  mov     edx, 14h
0x18001139b  mov     rcx, [r15]
0x18001139e  call    cs:__imp_WFDQueryPropertyInt
0x1800113a4  mov     [rsp+11A8h+var_1138], eax
0x1800113a8  mov     [rsp+11A8h+var_10FC], eax
0x1800113af  xor     r8d, r8d
0x1800113b2  lea     edx, [r8+5]
0x1800113b6  mov     rcx, [r15]
0x1800113b9  call    cs:__imp_WFDRegisterVMgrCallerInt
0x1800113bf  test    eax, eax
0x1800113c1  jz      short loc_1800113ED
0x1800113c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113ca  cmp     rcx, rdi
0x1800113cd  jz      short loc_1800113ED
0x1800113cf  test    [rcx+1Ch], r13b
0x1800113d3  jz      short loc_1800113ED
0x1800113d5  mov     edx, 39h ; '9'
0x1800113da  mov     r9d, eax
0x1800113dd  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x1800113e4  mov     rcx, [rcx+10h]
0x1800113e8  call    WPP_SF_d
0x1800113ed  mov     [rsp+11A8h+var_1150], r12b
0x1800113f2  mov     [rsp+11A8h+pvData], r14
0x1800113f7  mov     rcx, [rsp+11A8h+var_1158]
0x1800113fc  mov     [rsp+11A8h+pdwType], rcx
0x180011401  lea     r9, ?WfdNotificationCallback@InterfaceMgr@@CAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; InterfaceMgr::WfdNotificationCallback(_L2_NOTIFICATION_DATA *,void *)
0x180011408  mov     r8d, r12d
0x18001140b  mov     edx, 400h
0x180011410  mov     rcx, [r15]
0x180011413  call    cs:__imp_WFDRegisterNotificationInt
0x180011419  mov     esi, eax
0x18001141b  test    eax, eax
0x18001141d  jz      loc_1800114BC
0x180011423  jle     short loc_18001142E
0x180011425  movzx   esi, ax
0x180011428  or      esi, 80070000h
0x18001142e  mov     [rsp+11A8h+var_1164], esi
0x180011432  mov     edx, 1Ah
0x180011437  cmp     [rsp+11A8h+var_1050], rdx
0x18001143f  jb      short loc_18001147D
0x180011441  lea     rdi, [rsp+11A8h+Src]
0x180011449  cmp     [rsp+11A8h+var_1050], 7
0x180011452  cmova   rdi, [rsp+11A8h+Src]
0x18001145b  mov     [rsp+11A8h+var_1058], rdx
0x180011463  lea     r8d, [rdx+1Ah]; Size
0x180011467  lea     rdx, aWfdregisternot; "WFDRegisterNotificationInt"
0x18001146e  mov     rcx, rdi; void *
0x180011471  call    memmove_0
0x180011476  mov     [rdi+34h], r14w
0x18001147b  jmp     short loc_180011491
0x18001147d  lea     r9, aWfdregisternot; "WFDRegisterNotificationInt"
0x180011484  lea     rcx, [rsp+11A8h+Src]
0x18001148c  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180011491  mov     rdi, cs:WPP_GLOBAL_Control
0x180011498  lea     rax, WPP_GLOBAL_Control
0x18001149f  cmp     rdi, rax
0x1800114a2  jz      loc_180012098
0x1800114a8  test    [rdi+1Ch], r12b
0x1800114ac  jz      loc_180012098
0x1800114b2  mov     edx, 3Ah ; ':'
0x1800114b7  jmp     loc_18001136D
0x1800114bc  lea     r9, [rsp+11A8h+var_114A]
0x1800114c1  mov     r8d, r12d
0x1800114c4  mov     edx, 6
0x1800114c9  mov     rcx, [r15]
0x1800114cc  call    cs:__imp_WFDSetPropertyInt
0x1800114d2  mov     esi, eax
0x1800114d4  test    eax, eax
0x1800114d6  jz      loc_180011575
0x1800114dc  jle     short loc_1800114E7
0x1800114de  movzx   esi, ax
0x1800114e1  or      esi, 80070000h
0x1800114e7  mov     [rsp+11A8h+var_1164], esi
0x1800114eb  mov     edx, 31h ; '1'
0x1800114f0  cmp     [rsp+11A8h+var_1050], rdx
0x1800114f8  jb      short loc_180011536
0x1800114fa  lea     rdi, [rsp+11A8h+Src]
0x180011502  cmp     [rsp+11A8h+var_1050], 7
0x18001150b  cmova   rdi, [rsp+11A8h+Src]
0x180011514  mov     [rsp+11A8h+var_1058], rdx
0x18001151c  lea     r8d, [rdx+31h]; Size
0x180011520  lea     rdx, aWfdsetproperty_2; "WFDSetPropertyInt wfd_opcode_crossconne"...
0x180011527  mov     rcx, rdi; void *
0x18001152a  call    memmove_0
0x18001152f  mov     [rdi+62h], r14w
0x180011534  jmp     short loc_18001154A
0x180011536  lea     r9, aWfdsetproperty_2; "WFDSetPropertyInt wfd_opcode_crossconne"...
0x18001153d  lea     rcx, [rsp+11A8h+Src]
0x180011545  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001154a  mov     rdi, cs:WPP_GLOBAL_Control
0x180011551  lea     rax, WPP_GLOBAL_Control
0x180011558  cmp     rdi, rax
0x18001155b  jz      loc_180012098
0x180011561  test    [rdi+1Ch], r12b
0x180011565  jz      loc_180012098
0x18001156b  mov     edx, 3Bh ; ';'
0x180011570  jmp     loc_18001136D
0x180011575  mov     [rsp+11A8h+var_114F], r12b
0x18001157a  mov     [rsp+11A8h+var_1134], 8
0x180011582  mov     rax, [rsp+11A8h+var_1158]
0x180011587  cmp     dword ptr [rax+78h], 8
0x18001158b  jnz     short loc_1800115A0
0x18001158d  lea     rdx, [rax+80h]
0x180011594  mov     ecx, 4
0x180011599  call    ?TetheringSettingsGetSettingValueWithIccidInternal@@YAPEAXW4TetheringSettingPerIccid@@PEBG@Z; TetheringSettingsGetSettingValueWithIccidInternal(TetheringSettingPerIccid,ushort const *)
0x18001159e  jmp     short loc_1800115AA
0x1800115a0  mov     ecx, 0Eh
0x1800115a5  call    ?TetheringSettingsGetSettingValueGlobalInternal@@YAPEAXW4TetheringSettingGlobal@@@Z; TetheringSettingsGetSettingValueGlobalInternal(TetheringSettingGlobal)
0x1800115aa  mov     [rsp+11A8h+Block], rax
0x1800115b2  mov     rbx, rax
0x1800115b5  test    rax, rax
0x1800115b8  jz      short loc_1800115C0
0x1800115ba  mov     eax, [rax]
0x1800115bc  mov     [rsp+11A8h+var_1134], eax
0x1800115c0  lea     r9, [rsp+11A8h+var_1134]
0x1800115c5  mov     edx, 9
0x1800115ca  lea     r8d, [rdx-5]
0x1800115ce  mov     rcx, [r15]
0x1800115d1  call    cs:__imp_WFDSetPropertyInt
0x1800115d7  mov     esi, eax
0x1800115d9  test    eax, eax
0x1800115db  jz      loc_18001167A
0x1800115e1  jle     short loc_1800115EC
0x1800115e3  movzx   esi, ax
0x1800115e6  or      esi, 80070000h
0x1800115ec  mov     [rsp+11A8h+var_1164], esi
0x1800115f0  mov     edx, 29h ; ')'
0x1800115f5  cmp     [rsp+11A8h+var_1050], rdx
0x1800115fd  jb      short loc_18001163B
0x1800115ff  lea     rdi, [rsp+11A8h+Src]
0x180011607  cmp     [rsp+11A8h+var_1050], 7
0x180011610  cmova   rdi, [rsp+11A8h+Src]
0x180011619  mov     [rsp+11A8h+var_1058], rdx
0x180011621  lea     r8d, [rdx+29h]; Size
0x180011625  lea     rdx, aWfdsetproperty_0; "WFDSetPropertyInt wfd_opcode_client_lim"...
0x18001162c  mov     rcx, rdi; void *
0x18001162f  call    memmove_0
0x180011634  mov     [rdi+52h], r14w
0x180011639  jmp     short loc_18001164F
0x18001163b  lea     r9, aWfdsetproperty_0; "WFDSetPropertyInt wfd_opcode_client_lim"...
0x180011642  lea     rcx, [rsp+11A8h+Src]
0x18001164a  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001164f  mov     rdi, cs:WPP_GLOBAL_Control
0x180011656  lea     rax, WPP_GLOBAL_Control
0x18001165d  cmp     rdi, rax
0x180011660  jz      loc_180012098
0x180011666  test    [rdi+1Ch], r12b
0x18001166a  jz      loc_180012098
0x180011670  mov     edx, 3Ch ; '<'
0x180011675  jmp     loc_18001136D
0x18001167a  mov     [rsp+11A8h+var_114E], r12b
0x18001167f  mov     [rsp+11A8h+var_110C], r14d
0x180011687  lea     r9, [rsp+11A8h+var_110C]
0x18001168f  mov     edx, 8
0x180011694  lea     r8d, [rdx-4]
0x180011698  mov     rcx, [r15]
0x18001169b  call    cs:__imp_WFDSetPropertyInt
0x1800116a1  mov     esi, eax
0x1800116a3  mov     r9d, 490h
0x1800116a9  cmp     eax, r9d
0x1800116ac  jnz     loc_180011762
0x1800116b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800116b9  cmp     rcx, rdi
0x1800116bc  jz      short loc_1800116D9
  ... truncated ...
```
