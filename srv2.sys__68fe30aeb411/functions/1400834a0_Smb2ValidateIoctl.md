# Smb2ValidateIoctl

- ea: `0x1400834a0`
- end: `0x14008470f`
- name: `Smb2ValidateIoctl`
- size: `4719`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter4)`
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x140073a60`

## callees

- `0x140004ba0`
- `0x140007400`
- `0x140011ed0`
- `0x140012790`
- `0x140014d60`
- `0x14001a150`
- `0x14001c8ec`
- `0x14001cef0`
- `0x14001d704`
- `0x14002019c`
- `0x1400222ec`
- `0x140022958`
- `0x1400229ac`
- `0x14002b11c`
- `0x140038680`
- `0x140038980`
- `0x14005c600`
- `0x140078de0`
- `0x1400834a0`
- `0x140084720`
- `0x1400847a8`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x140084107`
- `ntoskrnl!IoBuildPartialMdl` at `0x140084107`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140099f5b`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140099f5b`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400846ca`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400846ca`
- `ntoskrnl!IoCheckFunctionAccess` at `0x1400836d4`
- `ntoskrnl!IoCheckFunctionAccess` at `0x14009a08b`
- `ntoskrnl!IoCheckFunctionAccess` at `0x1400836d4`
- `ntoskrnl!IoCheckFunctionAccess` at `0x14009a08b`
- `ntoskrnl!FsRtlGetSupportedFeatures` at `0x140099f6e`
- `ntoskrnl!FsRtlGetSupportedFeatures` at `0x140099f6e`
- `srvnet!SrvNetFreeBuffer` at `0x140083a03`
- `srvnet!SrvNetFreeBuffer` at `0x140083a03`
- `srvnet!SrvNetAllocateBuffer` at `0x140083792`
- `srvnet!SrvNetAllocateBuffer` at `0x140083924`
- `srvnet!SrvNetAllocateBuffer` at `0x140083b72`
- `srvnet!SrvNetAllocateBuffer` at `0x140083e68`
- `srvnet!SrvNetAllocateBuffer` at `0x14009a7b2`
- `srvnet!SrvNetAllocateBuffer` at `0x140083792`
- `srvnet!SrvNetAllocateBuffer` at `0x140083924`
- `srvnet!SrvNetAllocateBuffer` at `0x140083b72`
- `srvnet!SrvNetAllocateBuffer` at `0x140083e68`
- `srvnet!SrvNetAllocateBuffer` at `0x14009a7b2`
- `srvnet!SrvAdminIsScopedName` at `0x140083f7e`
- `srvnet!SrvAdminIsScopedName` at `0x140083f7e`
- `srvnet!SrvAdminIsFsctlAllowedForSmb2` at `0x14008353c`
- `srvnet!SrvAdminIsFsctlAllowedForSmb2` at `0x14008353c`

## pseudocode

```c
__int64 __fastcall Smb2ValidateIoctl(ULONG_PTR BugCheckParameter4)
{
  __int64 v1; // rbx
  __int64 v3; // r14
  unsigned int v4; // r8d
  __int64 v5; // rbx
  __int64 v6; // r15
  int v7; // edi
  int v8; // eax
  bool v9; // r9
  int v10; // eax
  __int64 v11; // rdx
  unsigned int *v12; // r12
  unsigned int v13; // r8d
  ULONG *v14; // r13
  unsigned int v15; // ecx
  unsigned int v16; // eax
  unsigned int v17; // ecx
  unsigned int v18; // eax
  unsigned int v19; // ecx
  unsigned int v20; // r8d
  unsigned __int64 v21; // r8
  unsigned __int64 v22; // rdx
  int v23; // eax
  NTSTATUS SupportedFeatures; // edi
  unsigned int v25; // ecx
  size_t v26; // rdi
  unsigned int v27; // eax
  int v28; // eax
  int v29; // eax
  __int64 v30; // rax
  __int64 v31; // rcx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  __int64 v36; // rdx
  int v37; // eax
  int v38; // eax
  __int64 v39; // rax
  void *v40; // rcx
  __int64 v41; // rdi
  unsigned int v42; // eax
  __int64 v43; // r9
  __int64 v44; // rdx
  unsigned int v45; // eax
  int v46; // eax
  int v47; // eax
  unsigned int v48; // ecx
  unsigned int v49; // eax
  bool v50; // cf
  unsigned int v51; // ecx
  unsigned int v52; // edx
  unsigned int v53; // edi
  __int64 v54; // rax
  __int64 v55; // rdi
  unsigned int v56; // eax
  _QWORD *v57; // rax
  __int64 *v58; // rdx
  __int64 v59; // rcx
  __int64 *v60; // r11
  __int64 v61; // rcx
  __int64 *v62; // r10
  __int64 v63; // rcx
  __int64 v64; // rax
  __int64 v65; // r9
  unsigned int v66; // eax
  __int64 v67; // r12
  size_t v68; // rdi
  __int64 v69; // rax
  unsigned __int64 v70; // rcx
  unsigned int v71; // edx
  __int64 v72; // r8
  __int64 v73; // r9
  unsigned __int128 v74; // xmm0
  __int64 v75; // r8
  __int64 v76; // rdx
  unsigned __int16 v77; // cx
  unsigned __int64 v78; // r8
  __int64 v79; // r10
  ULONG v80; // r13d
  void *v81; // r12
  __int64 v82; // rdi
  unsigned int v83; // ecx
  unsigned int v84; // ebx
  __int64 v85; // r9
  int v86; // edx
  __int64 v87; // rcx
  int v88; // r8d
  __int64 v89; // rdx
  __int64 v90; // rcx
  unsigned int v91; // eax
  int v92; // ecx
  __int64 v93; // rdx
  unsigned int v94; // r8d
  __int64 v95; // rcx
  __int64 v96; // rdi
  __int64 v97; // rax
  PVOID v98; // rcx
  unsigned int v99; // r8d
  _QWORD *v100; // rdi
  __int64 FileHandle; // rax
  PVOID v102; // rcx
  __int64 v103; // rcx
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  unsigned __int64 v105; // rdx
  __int64 v106; // rax
  __int64 v107; // rcx
  _DWORD *v108; // rcx
  int v109; // eax
  int v110; // edx
  unsigned __int16 *v111; // rdi
  unsigned __int16 v112; // ax
  __int64 Buffer; // rax
  unsigned __int128 v114; // [rsp+98h] [rbp+7h] BYREF
  PMDL SourceMdl; // [rsp+F8h] [rbp+67h] BYREF
  PVOID P; // [rsp+100h] [rbp+6Fh] BYREF
  _QWORD *v117; // [rsp+110h] [rbp+7Fh]

  v1 = *(_QWORD *)(BugCheckParameter4 + 304);
  v3 = *(_QWORD *)(BugCheckParameter4 + 560);
  v4 = *(_DWORD *)(v1 + 36);
  if ( v4 < 0x78 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        32,
        WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
        BugCheckParameter4,
        v4);
    }
    Smb2SetError(BugCheckParameter4, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c", 1010);
    Smb2LkmdTelCollectParsingFailureIoctlHelper(v3, 0);
    return 0;
  }
  else
  {
    v5 = *(_QWORD *)(v1 + 24);
    if ( *(_WORD *)(v5 + 64) == 57 )
    {
      if ( (*(_BYTE *)(v5 + 112) & 1) != 0 )
      {
        v6 = *(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 96) + 496LL);
        v7 = Smb2VerifySessionExEx(BugCheckParameter4, *(_QWORD *)(v5 + 40), v5, 0, 1, 0);
        if ( v7 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              35,
              WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
              BugCheckParameter4);
          }
          v85 = 1056;
        }
        else
        {
          v7 = Smb2VerifyTreeConnect_Old(BugCheckParameter4, *(unsigned int *)(v5 + 36), v5);
          if ( v7 >= 0 )
          {
            if ( !(unsigned __int8)SrvAdminIsFsctlAllowedForSmb2(*(unsigned int *)(v5 + 68))
              && (!*(_BYTE *)(*(_QWORD *)(v3 + 32) + 285LL)
               || (*(_DWORD *)(*(_QWORD *)(v3 + 56) + 84LL) & 0x1000000) == 0
               || (*(_DWORD *)(v5 + 68) & 0x2000) == 0) )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                WPP_SF_qD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  37,
                  WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                  BugCheckParameter4,
                  *(_DWORD *)(v5 + 68));
              }
              Smb2SetError(
                BugCheckParameter4,
                3221225659LL,
                "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                1114);
              return 0;
            }
            v8 = *(_DWORD *)(v5 + 68);
            *(_DWORD *)(v3 + 192) = v8;
            v9 = v8 == 1114136 || v8 == 1311236 || v8 == 393620 || v8 == 1311228 || v8 == 393648;
            *(_BYTE *)(v3 + 196) = v9;
            v10 = v8 & 3;
            if ( v10 )
            {
              v46 = v10 - 1;
              if ( v46 && (v47 = v46 - 1) != 0 )
              {
                if ( v47 != 1 )
                  goto LABEL_96;
                v12 = (unsigned int *)(v5 + 92);
                v11 = *(unsigned int *)(v5 + 92);
                v14 = (ULONG *)(v5 + 108);
                v13 = *(_DWORD *)(v5 + 108);
                v48 = *(_DWORD *)(v5 + 92);
                if ( (unsigned int)v11 <= *(_DWORD *)(v5 + 96) )
                  v48 = *(_DWORD *)(v5 + 96);
                v49 = v13 + v48;
                v50 = v13 + v48 < v48;
              }
              else
              {
                v11 = *(unsigned int *)(v5 + 92);
                v12 = (unsigned int *)(v5 + 92);
                v13 = *(_DWORD *)(v5 + 108);
                v14 = (ULONG *)(v5 + 108);
                v49 = v13 + v11;
                v50 = v13 + (unsigned int)v11 < (unsigned int)v11;
              }
              if ( v50 )
                goto LABEL_96;
              v15 = v49 + 8;
              if ( v49 + 8 < v49 )
                goto LABEL_96;
            }
            else
            {
              v11 = *(unsigned int *)(v5 + 92);
              v12 = (unsigned int *)(v5 + 92);
              v13 = *(_DWORD *)(v5 + 108);
              v14 = (ULONG *)(v5 + 108);
              v15 = v11;
              if ( (unsigned int)v11 <= v13 )
                v15 = *(_DWORD *)(v5 + 108);
            }
            v16 = *(_DWORD *)(v6 + 36);
            if ( v15 <= v16 && (unsigned int)v11 <= v16 )
            {
              v17 = *(_DWORD *)(v5 + 96);
              if ( v17 <= v16 && v13 <= v16 )
              {
                if ( (*(_BYTE *)(v6 + 49) & 2) != 0 )
                {
                  v18 = v17 + v13;
                  if ( v17 + v13 < v17 )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) )
                    {
                      WPP_SF_q(
                        WPP_GLOBAL_Control->AttachedDevice,
                        39,
                        WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                        BugCheckParameter4);
                    }
                    Smb2SetError(
                      BugCheckParameter4,
                      3221225485LL,
                      "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                      1168);
                    v36 = 3;
                    goto LABEL_70;
                  }
                  if ( (unsigned int)v11 > v18 )
                    v18 = v11;
                  v19 = v18 ? ((v18 - 1) >> 16) + 1 : 1;
                  v20 = *(unsigned __int16 *)(BugCheckParameter4 + 488);
                  if ( v20 < v19 )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) )
                    {
                      WPP_SF_qDD(
                        WPP_GLOBAL_Control->AttachedDevice,
                        40,
                        WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                        BugCheckParameter4,
                        v20,
                        v19);
                    }
                    Smb2SetError(
                      BugCheckParameter4,
                      3221225485LL,
                      "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                      1185);
                    v36 = 4;
                    goto LABEL_70;
                  }
                }
                if ( (_DWORD)v11 )
                {
                  v21 = *(unsigned int *)(v5 + 88);
                  if ( v21 - 120 > 0x40
                    || ((v22 = v21 + v11, v22 >= v21)
                     && v22 <= 0xFFFFFFFF
                     && v22 <= *(unsigned int *)(*(_QWORD *)(BugCheckParameter4 + 304) + 36LL)
                     && (((_BYTE)v21 + (_BYTE)v5) & 7) == 0
                      ? (v23 = 0)
                      : (v23 = -1073741811),
                        v23 < 0) )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) )
                    {
                      WPP_SF_q(
                        WPP_GLOBAL_Control->AttachedDevice,
                        41,
                        WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                        BugCheckParameter4);
                    }
                    Smb2SetError(
                      BugCheckParameter4,
                      3221225485LL,
                      "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                      1213);
                    v36 = 5;
                    goto LABEL_70;
                  }
                }
                if ( v9 )
                {
                  if ( *(_QWORD *)(v5 + 72) != -1 || *(_QWORD *)(v5 + 80) != -1 )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) )
                    {
                      WPP_SF_q(
                        WPP_GLOBAL_Control->AttachedDevice,
                        42,
                        WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                        BugCheckParameter4);
                    }
                    Smb2SetError(
                      BugCheckParameter4,
                      3221225485LL,
                      "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                      1230);
                    v36 = 6;
                    goto LABEL_70;
                  }
                }
                else
                {
                  v114 = *(_OWORD *)(v5 + 72);
                  SupportedFeatures = Smb2VerifyFileEx(BugCheckParameter4);
                  if ( SupportedFeatures < 0 )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) )
                    {
                      WPP_SF_q(
                        WPP_GLOBAL_Control->AttachedDevice,
                        43,
                        WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                        BugCheckParameter4);
                    }
                    v43 = 1252;
                    goto LABEL_82;
                  }
                  SupportedFeatures = IoCheckFunctionAccess(
                                        *(_DWORD *)(*(_QWORD *)(v3 + 72) + 184LL),
                                        0xDu,
                                        0,
                                        *(_DWORD *)(v3 + 192),
                                        0,
                                        0);
                  if ( SupportedFeatures < 0 )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) )
                    {
                      WPP_SF_q(
                        WPP_GLOBAL_Control->AttachedDevice,
                        44,
                        WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                        BugCheckParameter4);
                    }
                    v43 = 1269;
                    goto LABEL_82;
                  }
                }
                v25 = *(_DWORD *)(v3 + 192);
                if ( v25 <= 0x98208 )
                {
                  if ( v25 == 623112 )
                  {
                    if ( *v12 < 0x18 )
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) )
                      {
                        WPP_SF_q(
                          WPP_GLOBAL_Control->AttachedDevice,
                          46,
                          WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                          BugCheckParameter4);
                      }
                      Smb2SetError(
                        BugCheckParameter4,
                        3221225485LL,
                        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                        1335);
                      v36 = 7;
                      goto LABEL_70;
                    }
                    v93 = *(unsigned int *)(v5 + 88);
                    if ( *(_DWORD *)(v93 + v5) )
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) )
                      {
                        WPP_SF_q(
                          WPP_GLOBAL_Control->AttachedDevice,
                          47,
                          WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                          BugCheckParameter4);
                      }
                      Smb2SetError(
                        BugCheckParameter4,
                        3221225485LL,
                        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                        1348);
                      v36 = 8;
                      goto LABEL_70;
                    }
                    *(_DWORD *)(v93 + v5) = *(_DWORD *)(*(_QWORD *)(v3 + 72) + 252LL);
                    goto LABEL_44;
                  }
                  if ( v25 > 0x902AF )
                  {
                    if ( v25 == 590700 || v25 == 590704 || v25 == 590776 )
                    {
                      if ( **(_BYTE **)(BugCheckParameter4 + 64) != 1 )
                      {
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                          && BYTE1(WPP_GLOBAL_Control->Timer) )
                        {
                          WPP_SF_qD(
                            WPP_GLOBAL_Control->AttachedDevice,
                            71,
                            WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                            BugCheckParameter4,
                            v25);
                        }
                        Smb2SetError(
                          BugCheckParameter4,
                          3221225659LL,
                          "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                          1933);
                        v36 = 23;
                        goto LABEL_70;
                      }
                      goto LABEL_44;
                    }
                    if ( v25 != 606820 )
                      goto LABEL_44;
                    goto LABEL_406;
                  }
                  if ( v25 == 590511 )
                  {
                    if ( !*(_BYTE *)(*(_QWORD *)(v3 + 32) + 285LL) )
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) )
                      {
                        WPP_SF_q(
                          WPP_GLOBAL_Control->AttachedDevice,
                          68,
                          WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                          BugCheckParameter4);
                      }
                      v43 = 1876;
                      v44 = 3221225659LL;
                      goto LABEL_83;
                    }
                    if ( *v12 < 8 )
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) )
                      {
                        WPP_SF_q(
                          WPP_GLOBAL_Control->AttachedDevice,
                          69,
                          WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                          BugCheckParameter4);
                      }
                      Smb2SetError(
                        BugCheckParameter4,
                        3221225485LL,
                        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                        1886);
                      v36 = 22;
                      goto LABEL_70;
                    }
                    v90 = *(unsigned int *)(v5 + 88);
                    if ( (unsigned int)(*(_DWORD *)(v90 + v5) - 1) > 1
                      || (v91 = *(_DWORD *)(v90 + v5 + 4), v91 > 0xD)
                      || (v92 = 8445, !_bittest(&v92, v91)) )
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) )
                      {
                        WPP_SF_q(
                          WPP_GLOBAL_Control->AttachedDevice,
                          70,
                          WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                          BugCheckParameter4);
                      }
                      Smb2SetError(
                        BugCheckParameter4,
                        3221225485LL,
                        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                        1911);
                      v36 = 23;
                      goto LABEL_70;
                    }
                  }
                  else
                  {
                    v33 = v25 - 393620;
                    if ( v33 )
                    {
                      v34 = v33 - 28;
                      if ( v34 )
                      {
                        v35 = v34 - 196340;
                        if ( !v35 )
                        {
                          v83 = *v12;
                          if ( *v12 )
                          {
                            if ( v83 >= 8 )
                            {
                              v89 = *(unsigned int *)(v5 + 88);
                              if ( *(unsigned __int16 *)(v89 + v5 + 4) <= v83 )
                              {
                                if ( *(_DWORD *)(v89 + v5) == -1610612724 || *(_BYTE *)(*(_QWORD *)(v3 + 32) + 272LL) )
                                  goto LABEL_44;
                                v84 = -1073741790;
                              }
                              else
                              {
                                v84 = -1073741192;
                              }
                            }
                            else
                            {
                              v84 = -1073741192;
                            }
                          }
                          else
                          {
                            v84 = -1073741306;
                          }
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) )
                          {
                            WPP_SF_q(
                              WPP_GLOBAL_Control->AttachedDevice,
                              45,
                              WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                              BugCheckParameter4);
                          }
                          v43 = 1318;
                          v44 = v84;
                          goto LABEL_83;
                        }
                        if ( v35 == 88 )
                        {
                          v86 = *(unsigned __int16 *)(v6 + 44);
                          if ( (unsigned __int16)v86 < 0x311u )
                          {
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                              && BYTE1(WPP_GLOBAL_Control->Timer) )
                            {
                              WPP_SF_qD(
                                WPP_GLOBAL_Control->AttachedDevice,
                                78,
                                WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                                BugCheckParameter4,
                                v86);
                            }
                            v43 = 2126;
                            v44 = 3221225659LL;
                            goto LABEL_83;
                          }
                          if ( *v12 < 0x18 )
                          {
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                              && BYTE1(WPP_GLOBAL_Control->Timer) )
                            {
                              WPP_SF_qD(
                                WPP_GLOBAL_Control->AttachedDevice,
                                79,
                                WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                                BugCheckParameter4,
                                *v12);
                            }
                            Smb2SetError(
                              BugCheckParameter4,
                              3221225485LL,
                              "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                              2140);
                            v36 = 26;
                            goto LABEL_70;
                          }
                          v87 = *(unsigned int *)(v5 + 88);
                          v88 = *(_DWORD *)(v87 + v5 + 16);
                          if ( v88 != 128 && v88 != 256 )
                          {
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                              && BYTE1(WPP_GLOBAL_Control->Timer) )
                            {
                              WPP_SF_qD(
                                WPP_GLOBAL_Control->AttachedDevice,
                                80,
                                WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                                BugCheckParameter4,
                                v88);
                            }
                            v43 = 2173;
                            v44 = 3221225659LL;
                            goto LABEL_83;
                          }
                          *(_DWORD *)(v3 + 336) = *(_DWORD *)(v87 + v5);
                          *(_QWORD *)(v3 + 344) = 0;
                          *(_DWORD *)(v3 + 352) = *(_DWORD *)(v87 + v5 + 16);
                        }
                      }
                      else if ( !*v12 )
                      {
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                          && BYTE1(WPP_GLOBAL_Control->Timer) )
                        {
                          WPP_SF_q(
                            WPP_GLOBAL_Control->AttachedDevice,
                            57,
                            WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                            BugCheckParameter4);
                        }
                        Smb2SetError(
                          BugCheckParameter4,
                          3221225485LL,
                          "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                          1629);
                        v36 = 15;
                        goto LABEL_70;
                      }
                    }
                    else
                    {
                      v70 = *v12;
                      if ( (unsigned int)v70 < 2 )
                      {
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                          && BYTE1(WPP_GLOBAL_Control->Timer) )
                        {
                          WPP_SF_q(
                            WPP_GLOBAL_Control->AttachedDevice,
                            55,
                            WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                            BugCheckParameter4);
                        }
                        Smb2SetError(
                          BugCheckParameter4,
                          3221225485LL,
                          "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                          1519);
                        v36 = 14;
                        goto LABEL_70;
                      }
                      v71 = 0;
                      v72 = v5 + *(unsigned int *)(v5 + 88) + 2LL;
                      v73 = (unsigned int)v70;
                      *(_QWORD *)&v114 = 0;
                      *((_QWORD *)&v114 + 1) = v72;
                      if ( v70 > 4 )
                      {
                        do
                        {
                          if ( !*(_WORD *)(v72 + 2 * ((unsigned __int64)v71 >> 1)) )
                            break;
                          v71 += 2;
                        }
                        while ( (unsigned int)v70 > (unsigned __int64)(v71 + 2) + 2 );
                        if ( v71 > 0xFFFE || (v71 & 1) != 0 )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) )
                          {
                            WPP_SF_q(
                              WPP_GLOBAL_Control->AttachedDevice,
                              56,
                              WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                              BugCheckParameter4);
                          }
                          Smb2SetError(
                            BugCheckParameter4,
                            3221225485LL,
                            "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                            1564);
                          v36 = 14;
                          goto LABEL_70;
                        }
                      }
                      LOWORD(v114) = v71;
                      WORD1(v114) = v71;
                      v74 = v114;
                      *(_BYTE *)(v3 + 352) = 0;
                      *(_OWORD *)(v3 + 336) = v74;
                      if ( *(unsigned __int16 *)(v3 + 336) > 2u )
                      {
                        v75 = *(unsigned __int16 *)(v3 + 336);
                        v76 = *(_QWORD *)(v3 + 344) + 2LL;
                        v77 = 0;
                        v114 = __PAIR128__(v76, 0);
                        v78 = v75 - 2;
                        if ( v78 )
                        {
                          LOWORD(v114) = 0;
                          do
                          {
                            if ( *(_WORD *)(v76 + 2 * ((unsigned __int64)v77 >> 1)) == 92 )
                              break;
                            v77 += 2;
                            LOWORD(v114) = v77;
                          }
                          while ( v77 < v78 );
                        }
                        WORD1(v114) = v77;
                        if ( v77 && (unsigned __int8)SrvAdminIsScopedName(&v114, v76, v78, v73) )
                          *(_BYTE *)(v3 + 352) = 1;
                      }
                    }
                  }
                }
                else
                {
                  if ( v25 > 0x1400EC )
                  {
                    switch ( v25 )
                    {
                      case 0x1401D4u:
                        if ( *(_DWORD *)(v5 + 92) < 8u )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) )
                          {
                            WPP_SF_q(
                              WPP_GLOBAL_Control->AttachedDevice,
                              49,
                              WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                              BugCheckParameter4);
                          }
                          Smb2SetError(
                            BugCheckParameter4,
                            3221225485LL,
                            "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                            1396);
                          v36 = 10;
                          goto LABEL_70;
                        }
                        if ( *(_DWORD *)(*(unsigned int *)(v5 + 88) + v5) / 0x3E8u > Smb2ResilientMaxTimeoutInSec )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) )
                          {
                            WPP_SF_q(
                              WPP_GLOBAL_Control->AttachedDevice,
                              50,
                              WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                              BugCheckParameter4);
                          }
                          Smb2SetError(
                            BugCheckParameter4,
                            3221225485LL,
                            "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                            1409);
                          v36 = 11;
                          goto LABEL_70;
                        }
                        goto LABEL_44;
                      case 0x140370u:
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                          && BYTE1(WPP_GLOBAL_Control->Timer) )
                        {
                          WPP_SF_q(
                            WPP_GLOBAL_Control->AttachedDevice,
                            81,
                            WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                            BugCheckParameter4);
                        }
                        v43 = 2190;
                        v44 = 3221225659LL;
                        goto LABEL_83;
                      case 0x144064u:
                        if ( !Smb2TimewarpEnabled )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) )
                          {
                            WPP_SF_qD(
                              WPP_GLOBAL_Control->AttachedDevice,
                              54,
                              WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                              BugCheckParameter4,
                              1327204);
                          }
                          v43 = 1498;
                          v44 = 3221225659LL;
                          goto LABEL_83;
                        }
                        goto LABEL_44;
                    }
                    if ( v25 != 1327547 )
                      goto LABEL_44;
                    v106 = *(_QWORD *)(v3 + 56);
                    if ( v106 )
                    {
                      v107 = *(_QWORD *)(v106 + 96);
                      if ( v107 )
                      {
                        if ( *(_BYTE *)(v107 + 280) )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) )
                          {
                            WPP_SF_q(
                              WPP_GLOBAL_Control->AttachedDevice,
                              59,
                              WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                              BugCheckParameter4);
                          }
                          v43 = 1701;
                          v44 = 3221266688LL;
                          goto LABEL_83;
                        }
                      }
                    }
                    if ( Smb2HashCacheLevel )
                    {
                      if ( Smb2HashCacheLevel != 2 )
                      {
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                          && BYTE1(WPP_GLOBAL_Control->Timer) )
                        {
                          WPP_SF_q(
                            WPP_GLOBAL_Control->AttachedDevice,
                            62,
                            WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                            BugCheckParameter4);
                        }
                        v43 = 1739;
                        v44 = 3221266688LL;
                        goto LABEL_83;
                      }
                    }
                    else
                    {
                      if ( !v106 )
                      {
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                          && BYTE1(WPP_GLOBAL_Control->Timer) )
                        {
                          WPP_SF_q(
                            WPP_GLOBAL_Control->AttachedDevice,
                            61,
                            WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                            BugCheckParameter4);
                        }
                        Smb2SetError(
                          BugCheckParameter4,
                          3221225485LL,
                          "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                          1725);
                        v36 = 16;
                        goto LABEL_70;
                      }
                      if ( (*(_DWORD *)(v106 + 80) & 0x2000) == 0 )
                      {
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                          && BYTE1(WPP_GLOBAL_Control->Timer) )
                        {
                          WPP_SF_q(
                            WPP_GLOBAL_Control->AttachedDevice,
                            60,
                            WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                            BugCheckParameter4);
                        }
                        v43 = 1715;
                        v44 = 3221266688LL;
                        goto LABEL_83;
                      }
                    }
                    if ( *(_DWORD *)(v5 + 92) < 0x18u )
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) )
                      {
                        WPP_SF_q(
                          WPP_GLOBAL_Control->AttachedDevice,
                          63,
                          WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                          BugCheckParameter4);
                      }
                      Smb2SetError(
                        BugCheckParameter4,
                        3221225507LL,
                        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                        1750);
                      v36 = 17;
                      goto LABEL_70;
                    }
                    v108 = (_DWORD *)(v5 + *(unsigned int *)(v5 + 88));
                    v109 = v108[1];
                    if ( v109 == 1 )
                    {
                      ++*(_DWORD *)(Srv2Statistics + 152);
                    }
                    else if ( v109 == 2 )
                    {
                      ++*(_DWORD *)(Srv2Statistics + 192);
                    }
                    v110 = v108[2];
                    if ( v110 == 1 )
                    {
                      if ( *(_DWORD *)(v5 + 108) >= 0x18u )
                        goto LABEL_469;
                    }
                    else if ( v110 != 2 || *(_DWORD *)(v5 + 108) >= 0x20u )
                    {
LABEL_469:
                      if ( Smb2HashSupportVersion == 1 )
                      {
                        if ( v108[1] != 1 )
                          goto LABEL_471;
                      }
                      else if ( Smb2HashSupportVersion == 2 )
                      {
                        if ( v108[1] != 2 )
                          goto LABEL_471;
                      }
                      else if ( Smb2HashSupportVersion == 3 && (unsigned int)(v108[1] - 1) > 1 )
                      {
                        goto LABEL_471;
                      }
                      if ( *v108 == 1 )
                      {
                        if ( v110 == 1 )
                        {
                          if ( v108[1] == 2 )
                          {
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                              && BYTE1(WPP_GLOBAL_Control->Timer) )
                            {
                              WPP_SF_q(
                                WPP_GLOBAL_Control->AttachedDevice,
                                67,
                                WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                                BugCheckParameter4);
                            }
                            Smb2SetError(
                              BugCheckParameter4,
                              3221225485LL,
                              "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                              1842);
                            v36 = 21;
                            goto LABEL_70;
                          }
                          goto LABEL_44;
                        }
                        if ( v110 == 2 )
                        {
                          if ( v108[1] == 1 )
                          {
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                              && BYTE1(WPP_GLOBAL_Control->Timer) )
                            {
                              WPP_SF_q(
                                WPP_GLOBAL_Control->AttachedDevice,
                                66,
                                WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                                BugCheckParameter4);
                            }
                            Smb2SetError(
                              BugCheckParameter4,
                              3221225485LL,
                              "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                              1827);
                            v36 = 20;
                            goto LABEL_70;
                          }
                          goto LABEL_44;
                        }
                      }
LABEL_471:
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) )
                      {
                        WPP_SF_q(
                          WPP_GLOBAL_Control->AttachedDevice,
                          65,
                          WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                          BugCheckParameter4);
                      }
                      Smb2SetError(
                        BugCheckParameter4,
                        3221225485LL,
                        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                        1812);
                      v36 = 19;
                      goto LABEL_70;
                    }
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) )
                    {
                      WPP_SF_q(
                        WPP_GLOBAL_Control->AttachedDevice,
                        64,
                        WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                        BugCheckParameter4);
                    }
                    Smb2SetError(
                      BugCheckParameter4,
                      3221225507LL,
                      "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                      1775);
                    v36 = 18;
                    goto LABEL_70;
                  }
                  if ( v25 != 1310956 )
                  {
                    if ( v25 != 623208 )
                    {
                      if ( v25 == 623428 )
                      {
                        v99 = *(_DWORD *)(v5 + 92);
                        P = 0;
                        if ( v99 < 0x28 )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) )
                          {
                            WPP_SF_qD(
                              WPP_GLOBAL_Control->AttachedDevice,
                              72,
                              WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                              BugCheckParameter4,
                              v99);
                          }
                          Smb2SetError(
                            BugCheckParameter4,
                            3221225485LL,
                            "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                            1956);
                          v36 = 24;
                          goto LABEL_70;
                        }
                        v100 = (_QWORD *)(v5 + *(unsigned int *)(v5 + 88));
                        LODWORD(SourceMdl) = Smb2SessionFindFile(*(_QWORD *)(v3 + 32), v100, &P);
                        if ( (int)SourceMdl < 0 )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) )
                          {
                            WPP_SF_qiiD(
                              WPP_GLOBAL_Control->AttachedDevice,
                              73,
                              WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                              BugCheckParameter4,
                              v100[1],
                              *v100,
                              (_DWORD)SourceMdl);
                          }
                          v43 = 1981;
                          v44 = 3221225480LL;
                          goto LABEL_83;
                        }
                        FileHandle = Smb2GetFileHandle(P);
                        v102 = P;
                        *(_QWORD *)(v3 + 336) = FileHandle;
                        Smb2DereferenceFile(v102);
                        if ( !*(_QWORD *)(v3 + 336) )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) )
                          {
                            WPP_SF_qiiD(
                              WPP_GLOBAL_Control->AttachedDevice,
                              74,
                              WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                              BugCheckParameter4,
                              v100[1],
                              *v100,
                              (_DWORD)SourceMdl);
                          }
                          v43 = 2008;
                          v44 = 3221225480LL;
                          goto LABEL_83;
                        }
                        *(_QWORD *)(v3 + 344) = v100[2];
                        *(_QWORD *)(v3 + 352) = v100[3];
                        *(_QWORD *)(v3 + 360) = v100[4];
                      }
                      else if ( v25 == 623592 )
                      {
                        v94 = *(_DWORD *)(v5 + 92);
                        P = 0;
                        if ( v94 < 0x38 )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) )
                          {
                            WPP_SF_qD(
                              WPP_GLOBAL_Control->AttachedDevice,
                              75,
                              WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                              BugCheckParameter4,
                              v94);
                          }
                          Smb2SetError(
                            BugCheckParameter4,
                            3221225485LL,
                            "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                            2039);
                          v36 = 25;
                          goto LABEL_70;
                        }
                        v95 = *(_QWORD *)(v3 + 32);
                        v96 = v5 + *(unsigned int *)(v5 + 88);
                        v117 = (_QWORD *)(v96 + 8);
                        LODWORD(SourceMdl) = Smb2SessionFindFile(v95, v96 + 8, &P);
                        if ( (int)SourceMdl < 0 )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) )
                          {
                            WPP_SF_qiiD(
                              WPP_GLOBAL_Control->AttachedDevice,
                              76,
                              WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                              BugCheckParameter4,
                              *(_QWORD *)(v96 + 16),
                              *(_QWORD *)(v96 + 8),
                              (_DWORD)SourceMdl);
                          }
                          v43 = 2064;
                          v44 = 3221225480LL;
                          goto LABEL_83;
                        }
                        v97 = Smb2GetFileHandle(P);
                        v98 = P;
                        *(_QWORD *)(v3 + 344) = v97;
                        Smb2DereferenceFile(v98);
                        if ( !*(_QWORD *)(v3 + 344) )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) )
                          {
                            WPP_SF_qiiD(
                              WPP_GLOBAL_Control->AttachedDevice,
                              77,
                              WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                              BugCheckParameter4,
                              *(_QWORD *)(v96 + 16),
                              *v117,
                              (_DWORD)SourceMdl);
                          }
                          v43 = 2091;
                          v44 = 3221225480LL;
                          goto LABEL_83;
                        }
                        *(_QWORD *)(v3 + 336) = *(_QWORD *)v96;
                        *(_QWORD *)(v3 + 352) = *(_QWORD *)(v96 + 24);
                        *(_QWORD *)(v3 + 360) = *(_QWORD *)(v96 + 32);
                        *(_QWORD *)(v3 + 368) = *(_QWORD *)(v96 + 40);
                        *(_DWORD *)(v3 + 376) = *(_DWORD *)(v96 + 48);
                      }
                      else if ( v25 == 1310840 && *(_DWORD *)(v5 + 108) < 0x20u )
                      {
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                          && BYTE1(WPP_GLOBAL_Control->Timer) )
                        {
                          WPP_SF_q(
                            WPP_GLOBAL_Control->AttachedDevice,
                            48,
                            WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                            BugCheckParameter4);
                        }
                        Smb2SetError(
                          BugCheckParameter4,
                          3221225485LL,
                          "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                          1378);
                        v36 = 9;
                        goto LABEL_70;
                      }
                      goto LABEL_44;
                    }
LABEL_406:
                    v103 = *(_QWORD *)(v3 + 80);
                    LODWORD(SourceMdl) = 0;
                    RelatedDeviceObject = IoGetRelatedDeviceObject(*(PFILE_OBJECT *)(v103 + 96));
                    SupportedFeatures = FsRtlGetSupportedFeatures(RelatedDeviceObject, &SourceMdl);
                    if ( SupportedFeatures >= 0 )
                    {
                      if ( *(_DWORD *)(v3 + 192) == 606820 )
                      {
                        if ( ((unsigned __int8)SourceMdl & 1) != 0 )
                          goto LABEL_44;
                        SupportedFeatures = -1073700191;
                      }
                      else
                      {
                        if ( ((unsigned __int8)SourceMdl & 2) != 0 )
                          goto LABEL_44;
                        SupportedFeatures = -1073700190;
                      }
                    }
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                    {
                      WPP_SF_qD(
                        WPP_GLOBAL_Control->AttachedDevice,
                        58,
                        WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                        BugCheckParameter4,
                        SupportedFeatures);
                    }
                    v43 = 1683;
                    goto LABEL_82;
                  }
                  v105 = *(unsigned int *)(v5 + 92);
                  LODWORD(SourceMdl) = 36;
                  if ( (unsigned int)v105 < 0xC )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) )
                    {
                      WPP_SF_q(
                        WPP_GLOBAL_Control->AttachedDevice,
                        51,
                        WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                        BugCheckParameter4);
                    }
                    Smb2SetError(
                      BugCheckParameter4,
                      3221225485LL,
                      "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                      1434);
                    v36 = 12;
                    goto LABEL_70;
                  }
                  if ( *(unsigned int *)(*(unsigned int *)(v5 + 88) + v5 + 8) > 0xFFFFFFF3uLL
                    || (unsigned __int64)*(unsigned int *)(*(unsigned int *)(v5 + 88) + v5 + 8) + 12 > v105 )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) )
                    {
                      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids);
                    }
                    Smb2SetError(
                      BugCheckParameter4,
                      3221225485LL,
                      "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                      1460);
                    v36 = 13;
                    goto LABEL_70;
                  }
                  SupportedFeatures = IoCheckFunctionAccess(
                                        *(_DWORD *)(*(_QWORD *)(v3 + 72) + 184LL),
                                        6u,
                                        0,
                                        0,
                                        &SourceMdl,
                                        0);
                  if ( SupportedFeatures < 0 )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) )
                    {
                      WPP_SF_q(
                        WPP_GLOBAL_Control->AttachedDevice,
                        53,
                        WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                        BugCheckParameter4);
                    }
                    v43 = 1479;
                    goto LABEL_82;
                  }
                }
LABEL_44:
                if ( (*(_DWORD *)(v3 + 192) & 3) == 0 )
                {
                  v26 = *(unsigned int *)(v5 + 108);
                  v27 = *(_DWORD *)(v5 + 92);
                  if ( v27 > (unsigned int)v26 )
                    v26 = v27;
                  goto LABEL_47;
                }
                v26 = 0;
                if ( (*(_DWORD *)(v3 + 192) & 3) == 1 || (*(_DWORD *)(v3 + 192) & 3) == 2 )
                {
                  v51 = *(_DWORD *)(v5 + 92);
                }
                else
                {
                  if ( (*(_DWORD *)(v3 + 192) & 3) != 3 )
                  {
LABEL_47:
                    if ( (Microsoft_Windows_SMBServerEnableBits & 1) != 0 )
                    {
                      v57 = *(_QWORD **)(BugCheckParameter4 + 560);
                      v58 = &Srv2ZeroGuid;
                      v59 = v57[9];
                      if ( v59 )
                        v60 = (__int64 *)(v59 + 96);
                      else
                        v60 = &Srv2ZeroGuid;
                      v61 = v57[7];
                      if ( v61 )
                        v62 = (__int64 *)(v61 + 24);
                      else
                        v62 = &Srv2ZeroGuid;
                      v63 = v57[4];
                      if ( v63 )
                        v58 = (__int64 *)(v63 + 72);
                      v64 = *(_QWORD *)(BugCheckParameter4 + 416);
                      if ( v64 )
                        v65 = *(_QWORD *)(*(_QWORD *)(v64 + 560) + 176LL);
                      else
                        LOBYTE(v65) = -1;
                      McTemplateK0xqqxxhhqxqqjjjj_EtwWriteTransfer(
                        *(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 96) + 496LL) + 72,
                        (_DWORD)v58,
                        BugCheckParameter4 + 584,
                        *(_QWORD *)(v5 + 40),
                        *(_DWORD *)(v5 + 32),
                        *(_DWORD *)(v5 + 36),
                        *(_QWORD *)(v5 + 24),
                        v65,
                        *(_WORD *)(v5 + 12),
                        *(_WORD *)(v5 + 14),
                        *(_DWORD *)(v5 + 16),
                        *(_QWORD *)(v5 + 72),
                        *(_DWORD *)(v5 + 68),
                        *(_DWORD *)(v5 + 112),
                        *(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 96) + 496LL) + 72LL,
                        (__int64)v58,
                        (__int64)v62,
                        (__int64)v60);
                    }
                    v28 = *(_DWORD *)(v3 + 192);
                    if ( v28 != 393648 )
                    {
                      if ( v28 != 393620 )
                      {
                        v29 = *(_DWORD *)(v3 + 192) & 3;
                        if ( v29 )
                        {
                          v37 = v29 - 1;
                          if ( !v37 || (v38 = v37 - 1) == 0 )
                          {
                            Buffer = SrvNetAllocateBuffer(v26, 0);
                            *(_QWORD *)(v3 + 160) = Buffer;
                            if ( !Buffer )
                            {
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                                && BYTE1(WPP_GLOBAL_Control->Timer) )
                              {
                                WPP_SF_q(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  93,
                                  WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                                  BugCheckParameter4);
                              }
                              v43 = 2539;
                              v44 = 3221225989LL;
                              goto LABEL_83;
                            }
                            memset(*(void **)(Buffer + 24), 0, v26);
                            memmove(
                              *(void **)(*(_QWORD *)(v3 + 160) + 24LL),
                              (const void *)(v5 + *(unsigned int *)(v5 + 88)),
                              *v12);
                            v79 = *(_QWORD *)(v3 + 160);
                            *(_QWORD *)(v3 + 216) = *(_QWORD *)(v79 + 24);
                            *(_DWORD *)(v3 + 204) = *v12;
                            v80 = *v14;
                            *(_DWORD *)(v3 + 200) = v80;
                            v81 = (void *)(*(_QWORD *)(v79 + 24) + ((*v12 + 7) & 0xFFFFFFF8));
                            *(_QWORD *)(v3 + 224) = v81;
                            v82 = *(_QWORD *)(v79 + 80);
                            SourceMdl = *(PMDL *)(v79 + 56);
                            if ( (*(_BYTE *)(v82 + 10) & 0x20) != 0 )
                              MmUnmapLockedPages(*(PVOID *)(v82 + 24), (PMDL)v82);
                            IoBuildPartialMdl(SourceMdl, (PMDL)v82, v81, v80);
                            *(_QWORD *)(v3 + 232) = *(_QWORD *)(*(_QWORD *)(v3 + 160) + 80LL);
                            Srv2ReleaseReceiveBuffer(BugCheckParameter4);
                            goto LABEL_53;
                          }
                          if ( v38 != 1 )
                          {
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                              && BYTE1(WPP_GLOBAL_Control->Timer) )
                            {
                              WPP_SF_q(
                                WPP_GLOBAL_Control->AttachedDevice,
                                94,
                                WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                                BugCheckParameter4);
                            }
                            Smb2SetError(
                              BugCheckParameter4,
                              3221225485LL,
                              "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                              2572);
                            Smb2LkmdTelCollectParsingFailureIoctlHelper(v3, 31);
                            return 0;
                          }
                          v39 = SrvNetAllocateBuffer(v26, 0);
                          *(_QWORD *)(v3 + 160) = v39;
                          if ( !v39 )
                          {
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                              && BYTE1(WPP_GLOBAL_Control->Timer) )
                            {
                              WPP_SF_q(
                                WPP_GLOBAL_Control->AttachedDevice,
                                91,
                                WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                                BugCheckParameter4);
                            }
                            v43 = 2482;
                            v44 = 3221225989LL;
                            goto LABEL_83;
                          }
                          memset(*(void **)(v39 + 24), 0, v26);
                          v40 = *(void **)(*(_QWORD *)(v3 + 160) + 24LL);
                          *(_QWORD *)(v3 + 216) = v40;
                          *(_DWORD *)(v3 + 204) = *v12;
                          memmove(v40, (const void *)(v5 + *(unsigned int *)(v5 + 88)), *v12);
                          *(_QWORD *)(v3 + 224) = *(_QWORD *)(*(_QWORD *)(v3 + 160) + 24LL) + ((*v12 + 7) & 0xFFFFFFF8);
                          *(_DWORD *)(v3 + 200) = *v14;
                          if ( (*(_DWORD *)(BugCheckParameter4 + 484) & 2) == 0 )
                            goto LABEL_53;
                          v41 = *(_QWORD *)(BugCheckParameter4 + 304);
                          *(_QWORD *)(BugCheckParameter4 + 304) = BugCheckParameter4 + 768;
                          v42 = *(_DWORD *)(v41 + 36);
                          if ( v42 >= *(_DWORD *)(BugCheckParameter4 + 800) )
                            v42 = *(_DWORD *)(BugCheckParameter4 + 800);
                          *(_DWORD *)(BugCheckParameter4 + 804) = v42;
                          memmove(
                            *(void **)(*(_QWORD *)(BugCheckParameter4 + 304) + 24LL),
                            *(const void **)(v41 + 24),
                            *(unsigned int *)(*(_QWORD *)(BugCheckParameter4 + 304) + 36LL));
                          if ( *(_QWORD *)(BugCheckParameter4 + 312) == v41 )
                            goto LABEL_120;
                        }
                        else
                        {
                          v30 = SrvNetAllocateBuffer(v26, 0);
                          *(_QWORD *)(v3 + 160) = v30;
                          if ( !v30 )
                          {
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                              && BYTE1(WPP_GLOBAL_Control->Timer) )
                            {
                              WPP_SF_q(
                                WPP_GLOBAL_Control->AttachedDevice,
                                92,
                                WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                                BugCheckParameter4);
                            }
                            v43 = 2512;
                            v44 = 3221225989LL;
                            goto LABEL_83;
                          }
                          memset(*(void **)(v30 + 24), 0, v26);
                          v31 = *(_QWORD *)(v3 + 160);
                          *(_QWORD *)(v3 + 216) = *(_QWORD *)(v31 + 24);
                          *(_DWORD *)(v3 + 204) = *v12;
                          *(_DWORD *)(v3 + 200) = *v14;
                          memmove(*(void **)(v31 + 24), (const void *)(v5 + *(unsigned int *)(v5 + 88)), *v12);
                          if ( (*(_DWORD *)(BugCheckParameter4 + 484) & 2) == 0 )
                            goto LABEL_53;
                          v41 = *(_QWORD *)(BugCheckParameter4 + 304);
                          *(_QWORD *)(BugCheckParameter4 + 304) = BugCheckParameter4 + 768;
                          v56 = *(_DWORD *)(v41 + 36);
                          if ( v56 >= *(_DWORD *)(BugCheckParameter4 + 800) )
                            v56 = *(_DWORD *)(BugCheckParameter4 + 800);
                          *(_DWORD *)(BugCheckParameter4 + 804) = v56;
                          memmove(
                            *(void **)(*(_QWORD *)(BugCheckParameter4 + 304) + 24LL),
                            *(const void **)(v41 + 24),
                            *(unsigned int *)(*(_QWORD *)(BugCheckParameter4 + 304) + 36LL));
                          if ( *(_QWORD *)(BugCheckParameter4 + 312) == v41 )
                            goto LABEL_120;
                        }
                        SrvNetFreeBuffer(v41);
LABEL_120:
                        *(_DWORD *)(BugCheckParameter4 + 484) &= ~2u;
LABEL_53:
                        if ( *(_BYTE *)(v3 + 196) )
                          return 3221225494LL;
                        if ( *(_WORD *)(v6 + 44) < 0x300u )
                          return 3221225494LL;
                        SupportedFeatures = Smb2VerifyChannelSequence(BugCheckParameter4);
                        if ( SupportedFeatures >= 0 )
                          return 3221225494LL;
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
                        {
                          if ( BYTE1(WPP_GLOBAL_Control->Timer) )
                            WPP_SF_qiiD(
                              WPP_GLOBAL_Control->AttachedDevice,
                              95,
                              WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                              BugCheckParameter4,
                              *(_QWORD *)(v5 + 80),
                              *(_QWORD *)(v5 + 72),
                              SupportedFeatures);
                        }
                        v43 = 2594;
                        goto LABEL_82;
                      }
                      v66 = v26 + 152;
                      if ( (int)v26 + 152 >= (unsigned int)v26 )
                      {
                        v67 = *(unsigned int *)(v5 + 88);
                        v68 = v66;
                        v69 = SrvNetAllocateBuffer(v66, 0);
                        *(_QWORD *)(v3 + 160) = v69;
                        if ( !v69 )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) )
                          {
                            WPP_SF_q(
                              WPP_GLOBAL_Control->AttachedDevice,
                              89,
                              WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                              BugCheckParameter4);
                          }
                          v43 = 2415;
                          v44 = 3221225989LL;
                          goto LABEL_83;
                        }
                        memset(*(void **)(v69 + 24), 0, v68);
                        v111 = *(unsigned __int16 **)(*(_QWORD *)(v3 + 160) + 24LL);
                        *(_QWORD *)(v3 + 216) = v111;
                        LODWORD(SourceMdl) = Srv2QuerySocketAddress(*(_QWORD *)(BugCheckParameter4 + 96), v111 + 12);
                        if ( (int)SourceMdl < 0 )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) )
                          {
                            WPP_SF_qD(
                              WPP_GLOBAL_Control->AttachedDevice,
                              90,
                              WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                              BugCheckParameter4,
                              (_DWORD)SourceMdl);
                          }
                          v44 = (unsigned int)SourceMdl;
                          v43 = 2433;
                          goto LABEL_83;
                        }
                        v111[8] = *(_WORD *)(v67 + v5);
                        v112 = *(_WORD *)(v3 + 336);
                        v111[1] = v112;
                        *v111 = v112;
                        *((_QWORD *)v111 + 1) = v111 + 76;
                        memmove(v111 + 76, *(const void **)(v3 + 344), *(unsigned __int16 *)(v3 + 336));
                        v111[9] = *(unsigned __int8 *)(v3 + 352);
                        *(_DWORD *)(v3 + 204) = *v111 + 152;
                        *(_DWORD *)(v3 + 200) = *v14;
                        Srv2ReleaseReceiveBuffer(BugCheckParameter4);
                        goto LABEL_53;
                      }
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) )
                      {
                        WPP_SF_q(
                          WPP_GLOBAL_Control->AttachedDevice,
                          88,
                          WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                          BugCheckParameter4);
                      }
                      Smb2SetError(
                        BugCheckParameter4,
                        3221225485LL,
                        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                        2393);
                      v36 = 30;
LABEL_70:
                      Smb2LkmdTelCollectParsingFailureIoctlHelper(v3, v36);
                      return 0;
                    }
                    v45 = v26 + 132;
                    if ( (int)v26 + 132 < (unsigned int)v26 )
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) )
                      {
                        WPP_SF_q(
                          WPP_GLOBAL_Control->AttachedDevice,
                          84,
                          WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                          BugCheckParameter4);
                      }
                      Smb2SetError(
                        BugCheckParameter4,
                        3221225485LL,
                        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                        2291);
                      Smb2LkmdTelCollectParsingFailureIoctlHelper(v3, 28);
                      return 0;
                    }
                    v53 = v26 + 132;
                    v54 = SrvNetAllocateBuffer(v45, 0);
                    *(_QWORD *)(v3 + 160) = v54;
                    if ( !v54 )
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) )
                      {
                        WPP_SF_q(
                          WPP_GLOBAL_Control->AttachedDevice,
                          85,
                          WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                          BugCheckParameter4);
                      }
                      v43 = 2314;
                      v44 = 3221225989LL;
                      goto LABEL_83;
                    }
                    memset(*(void **)(v54 + 24), 0, v53);
                    v55 = *(_QWORD *)(*(_QWORD *)(v3 + 160) + 24LL);
                    *(_QWORD *)(v3 + 216) = v55;
                    *(_DWORD *)(v55 + 128) = *v12;
                    memmove((void *)(v55 + 132), (const void *)(v5 + *(unsigned int *)(v5 + 88)), *v12);
                    SupportedFeatures = Srv2QuerySocketAddress(*(_QWORD *)(BugCheckParameter4 + 96), v55);
                    if ( SupportedFeatures < 0 )
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) )
                      {
                        WPP_SF_qD(
                          WPP_GLOBAL_Control->AttachedDevice,
                          86,
                          WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                          BugCheckParameter4,
                          SupportedFeatures);
                      }
                      v43 = 2338;
                    }
                    else
                    {
                      *(_DWORD *)(v3 + 204) = *v12 + 132;
                      *(_DWORD *)(v3 + 200) = *v14;
                      Srv2ReleaseReceiveBuffer(BugCheckParameter4);
                      SupportedFeatures = Smb2PValidateGetDfsnReferalEx(
                                            *(_QWORD *)(v3 + 216),
                                            *(_DWORD *)(v3 + 204),
                                            (int)v3 + 352,
                                            (int)v3 + 336,
                                            v3);
                      if ( SupportedFeatures >= 0 )
                        goto LABEL_53;
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) )
                      {
                        WPP_SF_qD(
                          WPP_GLOBAL_Control->AttachedDevice,
                          87,
                          WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                          BugCheckParameter4,
                          SupportedFeatures);
                      }
                      v43 = 2372;
                    }
LABEL_82:
                    v44 = (unsigned int)SupportedFeatures;
LABEL_83:
                    Smb2SetError(
                      BugCheckParameter4,
                      v44,
                      "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
                      v43);
                    return 0;
                  }
                  v51 = *(_DWORD *)(v5 + 92);
                  if ( v51 <= *(_DWORD *)(v5 + 96) )
                    v51 = *(_DWORD *)(v5 + 96);
                }
                v52 = v51 + *(_DWORD *)(v5 + 108);
                if ( v52 >= v51 )
                {
                  v26 = 0xFFFFFFFFLL;
                  if ( v52 + 8 >= v52 )
                    v26 = v52 + 8;
                }
                goto LABEL_47;
              }
            }
LABEL_96:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_q(
                WPP_GLOBAL_Control->AttachedDevice,
                38,
                WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                BugCheckParameter4);
            }
            Smb2SetError(
              BugCheckParameter4,
              3221225485LL,
              "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
              1139);
            v36 = 2;
            goto LABEL_70;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              36,
              WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
              BugCheckParameter4);
          }
          v85 = 1088;
        }
        Smb2SetError(
          BugCheckParameter4,
          (unsigned int)v7,
          "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
          v85);
        return 0;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          34,
          WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
          BugCheckParameter4,
          *(_DWORD *)(v5 + 68));
      }
      Smb2SetError(
        BugCheckParameter4,
        3221225659LL,
        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
        1042);
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          33,
          WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
          BugCheckParameter4);
      }
      Smb2SetError(
        BugCheckParameter4,
        3221225485LL,
        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\ioctl.c",
        1026);
      Smb2LkmdTelCollectParsingFailureIoctlHelper(v3, 1);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x1400834a0  mov     rax, rsp
0x1400834a3  push    rbp
0x1400834a4  push    rbx
0x1400834a5  push    rsi
0x1400834a6  push    r14
0x1400834a8  lea     rbp, [rax-5Fh]
0x1400834ac  sub     rsp, 0C8h
0x1400834b3  mov     rbx, [rcx+130h]
0x1400834ba  mov     rsi, rcx
0x1400834bd  mov     r14, [rcx+230h]
0x1400834c4  mov     r8d, [rbx+24h]
0x1400834c8  cmp     r8d, 78h ; 'x'
0x1400834cc  jb      loc_140084132
0x1400834d2  mov     rbx, [rbx+18h]
0x1400834d6  cmp     word ptr [rbx+40h], 39h ; '9'
0x1400834db  jnz     loc_140084183
0x1400834e1  test    byte ptr [rbx+70h], 1
0x1400834e5  jz      loc_14009946F
0x1400834eb  mov     rdx, [rbx+28h]
0x1400834ef  xor     r9d, r9d
0x1400834f2  mov     [rax-28h], rdi
0x1400834f6  mov     r8, rbx
0x1400834f9  mov     [rax-40h], r15
0x1400834fd  mov     rax, [rcx+60h]
0x140083501  mov     byte ptr [rsp+0E0h+Arg2], 0
0x140083506  mov     byte ptr [rsp+0E0h+Arg1], 1
0x14008350b  mov     r15, [rax+1F0h]
0x140083512  call    Smb2VerifySessionExEx
0x140083517  mov     edi, eax
0x140083519  test    eax, eax
0x14008351b  js      loc_1400841CF
0x140083521  mov     edx, [rbx+24h]
0x140083524  mov     r8, rbx
0x140083527  mov     rcx, rsi
0x14008352a  call    Smb2VerifyTreeConnect_Old
0x14008352f  mov     edi, eax
0x140083531  test    eax, eax
0x140083533  js      loc_14008421B
0x140083539  mov     ecx, [rbx+44h]
0x14008353c  call    cs:__imp_SrvAdminIsFsctlAllowedForSmb2
0x140083543  nop     dword ptr [rax+rax+00h]
0x140083548  test    al, al
0x14008354a  jz      loc_140084267
0x140083550  mov     eax, [rbx+44h]
0x140083553  mov     [r14+0C0h], eax
0x14008355a  cmp     eax, 110018h
0x14008355f  jz      loc_1400838A7
0x140083565  cmp     eax, 140204h
0x14008356a  jz      loc_1400838A7
0x140083570  cmp     eax, 60194h
0x140083575  jz      loc_1400838A7
0x14008357b  cmp     eax, 1401FCh
0x140083580  jz      loc_1400838A7
0x140083586  cmp     eax, 601B0h
0x14008358b  jz      loc_1400838A7
0x140083591  xor     r9b, r9b
0x140083594  mov     [rsp+0E0h+var_28], r12
0x14008359c  mov     [rsp+0E0h+var_30], r13
0x1400835a4  mov     [r14+0C4h], r9b
0x1400835ab  and     eax, 3
0x1400835ae  jnz     loc_140083A97
0x1400835b4  mov     edx, [rbx+5Ch]
0x1400835b7  lea     r12, [rbx+5Ch]
0x1400835bb  mov     r8d, [rbx+6Ch]
0x1400835bf  lea     r13, [rbx+6Ch]
0x1400835c3  mov     ecx, edx
0x1400835c5  cmp     edx, r8d
0x1400835c8  ja      short loc_1400835CD
0x1400835ca  mov     ecx, r8d
0x1400835cd  mov     eax, [r15+24h]
0x1400835d1  cmp     ecx, eax
0x1400835d3  ja      loc_140083ADB
0x1400835d9  cmp     edx, eax
0x1400835db  ja      loc_140083ADB
0x1400835e1  mov     ecx, [rbx+60h]
0x1400835e4  cmp     ecx, eax
0x1400835e6  ja      loc_140083ADB
0x1400835ec  cmp     r8d, eax
0x1400835ef  ja      loc_140083ADB
0x1400835f5  test    byte ptr [r15+31h], 2
0x1400835fa  jz      short loc_14008362E
0x1400835fc  lea     eax, [rcx+r8]
0x140083600  cmp     eax, ecx
0x140083602  jb      loc_1400842A5
0x140083608  cmp     edx, eax
0x14008360a  cmova   eax, edx
0x14008360d  test    eax, eax
0x14008360f  jz      loc_14008429B
0x140083615  lea     ecx, [rax-1]
0x140083618  shr     ecx, 10h
0x14008361b  inc     ecx
0x14008361d  movzx   r8d, word ptr [rsi+1E8h]
0x140083625  cmp     r8d, ecx
0x140083628  jb      loc_140099559
0x14008362e  mov     r10d, 0FFFFFFFFh
0x140083634  test    edx, edx
0x140083636  jz      short loc_14008367F
0x140083638  mov     r8d, [rbx+58h]
0x14008363c  lea     rax, [r8-78h]
0x140083640  cmp     rax, 40h ; '@'
0x140083644  ja      loc_1400842F1
0x14008364a  add     rdx, r8
0x14008364d  cmp     rdx, r8
0x140083650  jb      short loc_140083672
0x140083652  cmp     rdx, r10
0x140083655  ja      short loc_140083672
0x140083657  mov     rax, [rsi+130h]
0x14008365e  mov     ecx, [rax+24h]
0x140083661  cmp     rdx, rcx
0x140083664  ja      short loc_140083672
0x140083666  lea     eax, [r8+rbx]
0x14008366a  test    al, 7
0x14008366c  jz      loc_140083C87
0x140083672  mov     eax, 0C000000Dh
0x140083677  test    eax, eax
0x140083679  js      loc_1400842F1
0x14008367f  test    r9b, r9b
0x140083682  jnz     loc_1400838AF
0x140083688  movups  xmm0, xmmword ptr [rbx+48h]
0x14008368c  mov     r9b, 5
0x14008368f  lea     rdx, [rbp+57h+var_50]
0x140083693  mov     r8, rbx
0x140083696  mov     rcx, rsi; BugCheckParameter4
0x140083699  movaps  [rbp+57h+var_50], xmm0
0x14008369d  call    Smb2VerifyFileEx
0x1400836a2  mov     edi, eax
0x1400836a4  test    eax, eax
0x1400836a6  js      loc_140084371
0x1400836ac  mov     rcx, [r14+48h]
0x1400836b0  xor     r8d, r8d; MinorFunction
0x1400836b3  mov     r9d, [r14+0C0h]; IoControlCode
0x1400836ba  mov     dl, 0Dh; MajorFunction
0x1400836bc  mov     [rsp+0E0h+Arg2], 0; Arg2
0x1400836c5  mov     [rsp+0E0h+Arg1], 0; Arg1
0x1400836ce  mov     ecx, [rcx+0B8h]; GrantedAccess
0x1400836d4  call    cs:__imp_IoCheckFunctionAccess
0x1400836db  nop     dword ptr [rax+rax+00h]
0x1400836e0  mov     edi, eax
0x1400836e2  test    eax, eax
0x1400836e4  js      loc_140083A14
0x1400836ea  mov     r10d, 0FFFFFFFFh
0x1400836f0  mov     ecx, [r14+0C0h]
0x1400836f7  cmp     ecx, 98208h
0x1400836fd  jbe     loc_140083860
0x140083703  cmp     ecx, 1400ECh
0x140083709  jbe     loc_140099B47
0x14008370f  cmp     ecx, 1401D4h
0x140083715  jz      loc_14009A588
0x14008371b  cmp     ecx, 140370h
0x140083721  jz      loc_1400844A7
0x140083727  cmp     ecx, 144064h
0x14008372d  jz      loc_14009A51B
0x140083733  cmp     ecx, 1441BBh
0x140083739  jz      loc_14009A10A
0x14008373f  mov     eax, [r14+0C0h]
0x140083746  and     eax, 3
0x140083749  jnz     loc_140083B27
0x14008374f  mov     edi, [rbx+6Ch]
0x140083752  mov     eax, [rbx+5Ch]
0x140083755  cmp     eax, edi
0x140083757  cmova   edi, eax
0x14008375a  test    cs:Microsoft_Windows_SMBServerEnableBits, 1
0x140083761  jnz     loc_140083D08
0x140083767  mov     eax, [r14+0C0h]
0x14008376e  cmp     eax, 601B0h
0x140083773  jz      loc_140083A49
0x140083779  cmp     eax, 60194h
0x14008377e  jz      loc_140083E50
0x140083784  and     eax, 3
0x140083787  jnz     loc_140083904
0x14008378d  xor     edx, edx
0x14008378f  mov     rcx, rdi
0x140083792  call    cs:__imp_SrvNetAllocateBuffer
0x140083799  nop     dword ptr [rax+rax+00h]
0x14008379e  mov     [r14+0A0h], rax
0x1400837a5  test    rax, rax
0x1400837a8  jz      loc_140083E29
0x1400837ae  mov     rcx, [rax+18h]; void *
0x1400837b2  mov     r8, rdi; Size
0x1400837b5  xor     edx, edx; Val
0x1400837b7  call    memset
0x1400837bc  mov     rcx, [r14+0A0h]
0x1400837c3  mov     rax, [rcx+18h]
0x1400837c7  mov     [r14+0D8h], rax
0x1400837ce  mov     eax, [r12]
0x1400837d2  mov     [r14+0CCh], eax
0x1400837d9  mov     eax, [r13+0]
0x1400837dd  mov     [r14+0C8h], eax
0x1400837e4  mov     edx, [rbx+58h]
0x1400837e7  mov     r8d, [r12]; Size
0x1400837eb  add     rdx, rbx; Src
0x1400837ee  mov     rcx, [rcx+18h]; void *
0x1400837f2  call    memmove
0x1400837f7  mov     eax, [rsi+1E4h]
0x1400837fd  test    al, 2
0x1400837ff  jnz     loc_140083C8E
0x140083805  cmp     byte ptr [r14+0C4h], 0
0x14008380d  jnz     short loc_14008382D
0x14008380f  mov     eax, 300h
0x140083814  cmp     [r15+2Ch], ax
0x140083819  jb      short loc_14008382D
0x14008381b  mov     rcx, rsi; BugCheckParameter4
0x14008381e  call    Smb2VerifyChannelSequence
0x140083823  mov     edi, eax
0x140083825  test    eax, eax
0x140083827  js      loc_14009A818
0x14008382d  mov     eax, 0C0000016h
0x140083832  mov     r13, [rsp+0E0h+var_30]
0x14008383a  mov     r12, [rsp+0E0h+var_28]
0x140083842  mov     rdi, [rsp+0C0h]
0x14008384a  mov     r15, [rsp+0E0h+var_38]
0x140083852  add     rsp, 0C8h
0x140083859  pop     r14
0x14008385b  pop     rsi
0x14008385c  pop     rbx
0x14008385d  pop     rbp
0x14008385e  retn
0x140083860  jz      loc_140099A69
0x140083866  cmp     ecx, 902AFh
0x14008386c  ja      loc_140084478
0x140083872  jz      loc_1400998BA
0x140083878  sub     ecx, 60194h
0x14008387e  jz      loc_140083EBB
0x140083884  sub     ecx, 1Ch
0x140083887  jz      loc_1400997F8
0x14008388d  sub     ecx, 2FEF4h
0x140083893  jz      loc_1400843F1
0x140083899  cmp     ecx, 58h ; 'X'
0x14008389c  jnz     loc_14008373F
0x1400838a2  jmp     loc_140099615
0x1400838a7  mov     r9b, 1
0x1400838aa  jmp     loc_140083594
0x1400838af  cmp     qword ptr [rbx+48h], 0FFFFFFFFFFFFFFFFh
0x1400838b4  jnz     short loc_1400838C1
0x1400838b6  cmp     qword ptr [rbx+50h], 0FFFFFFFFFFFFFFFFh
0x1400838bb  jz      loc_1400836F0
0x1400838c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400838c8  lea     rax, WPP_GLOBAL_Control
0x1400838cf  cmp     rcx, rax
0x1400838d2  jnz     loc_14008433D
0x1400838d8  mov     r9d, 4CEh
0x1400838de  lea     r8, aOnecoreBaseFsR_8; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x1400838e5  mov     edx, 0C000000Dh
0x1400838ea  mov     rcx, rsi
0x1400838ed  call    _Smb2SetError
0x1400838f2  mov     edx, 6
0x1400838f7  mov     rcx, r14
0x1400838fa  call    Smb2LkmdTelCollectParsingFailureIoctlHelper
0x1400838ff  jmp     loc_140083A42
0x140083904  sub     eax, 1
0x140083907  jz      loc_14009A7AD
0x14008390d  sub     eax, 1
0x140083910  jz      loc_14009A7AD
0x140083916  cmp     eax, 1
0x140083919  jnz     loc_140083DE6
0x14008391f  xor     edx, edx
0x140083921  mov     rcx, rdi
0x140083924  call    cs:__imp_SrvNetAllocateBuffer
0x14008392b  nop     dword ptr [rax+rax+00h]
0x140083930  mov     [r14+0A0h], rax
0x140083937  test    rax, rax
0x14008393a  jz      loc_140084677
0x140083940  mov     rcx, [rax+18h]; void *
0x140083944  mov     r8, rdi; Size
0x140083947  xor     edx, edx; Val
0x140083949  call    memset
0x14008394e  mov     rax, [r14+0A0h]
0x140083955  mov     rcx, [rax+18h]; void *
0x140083959  mov     [r14+0D8h], rcx
0x140083960  mov     eax, [r12]
0x140083964  mov     [r14+0CCh], eax
0x14008396b  mov     edx, [rbx+58h]
0x14008396e  mov     r8d, [r12]; Size
0x140083972  add     rdx, rbx; Src
0x140083975  call    memmove
0x14008397a  mov     ecx, [r12]
0x14008397e  mov     eax, 0FFFFFFF8h
0x140083983  add     ecx, 7
0x140083986  and     rcx, rax
0x140083989  mov     rax, [r14+0A0h]
0x140083990  add     rcx, [rax+18h]
0x140083994  mov     [r14+0E0h], rcx
0x14008399b  mov     eax, [r13+0]
0x14008399f  mov     [r14+0C8h], eax
0x1400839a6  mov     eax, [rsi+1E4h]
0x1400839ac  test    al, 2
0x1400839ae  jz      loc_140083805
0x1400839b4  mov     rdi, [rsi+130h]
0x1400839bb  lea     r8, [rsi+300h]
0x1400839c2  mov     [rsi+130h], r8
0x1400839c9  mov     edx, [rsi+320h]
0x1400839cf  mov     eax, [rdi+24h]
0x1400839d2  cmp     eax, edx
0x1400839d4  cmovnb  eax, edx
0x1400839d7  mov     [r8+24h], eax
0x1400839db  mov     rcx, [rsi+130h]
0x1400839e2  mov     rdx, [rdi+18h]; Src
0x1400839e6  mov     r8d, [rcx+24h]; Size
0x1400839ea  mov     rcx, [rcx+18h]; void *
0x1400839ee  call    memmove
  ... truncated ...
```
