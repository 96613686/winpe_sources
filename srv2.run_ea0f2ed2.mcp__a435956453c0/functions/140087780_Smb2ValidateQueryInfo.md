# Smb2ValidateQueryInfo

- ea: `0x140087780`
- end: `0x14008844f`
- name: `Smb2ValidateQueryInfo`
- size: `3279`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter4)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140073ab0`

## callees

- `0x140007400`
- `0x14001c8ec`
- `0x14001cef0`
- `0x14001d5e8`
- `0x1400222ec`
- `0x140022958`
- `0x1400229ac`
- `0x14002ad2c`
- `0x14003344c`
- `0x14005c600`
- `0x14006e588`
- `0x1400860c0`
- `0x140087780`
- `0x140088460`

## import_xrefs

- `ntoskrnl!IoCheckFunctionAccess` at `0x140087f2e`
- `ntoskrnl!IoCheckFunctionAccess` at `0x14008800c`
- `ntoskrnl!IoCheckFunctionAccess` at `0x140088227`
- `ntoskrnl!IoCheckFunctionAccess` at `0x140087f2e`
- `ntoskrnl!IoCheckFunctionAccess` at `0x14008800c`
- `ntoskrnl!IoCheckFunctionAccess` at `0x140088227`
- `ntoskrnl!IoCheckQuerySetFileInformation` at `0x1400880be`
- `ntoskrnl!IoCheckQuerySetFileInformation` at `0x1400880be`
- `ntoskrnl!IoCheckQuerySetVolumeInformation` at `0x140087f8e`
- `ntoskrnl!IoCheckQuerySetVolumeInformation` at `0x140087f8e`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140087d11`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140087d11`
- `srvnet!SrvNetAllocateBuffer` at `0x140087d97`
- `srvnet!SrvNetAllocateBuffer` at `0x140087d97`

## pseudocode

```c
__int64 __fastcall Smb2ValidateQueryInfo(ULONG_PTR BugCheckParameter4)
{
  __int64 v1; // r14
  __int64 v3; // r13
  unsigned int v4; // r8d
  __int64 v5; // rdx
  __int64 v7; // r14
  __int64 v8; // r12
  NTSTATUS EaList; // ebx
  __int64 v10; // r9
  __int64 v11; // rdx
  int v12; // ebx
  __int64 v13; // r8
  __int64 v14; // r8
  int v15; // r15d
  unsigned int v16; // ecx
  int v17; // eax
  int v18; // edx
  __int64 v19; // r9
  unsigned int v20; // ecx
  unsigned int v21; // r8d
  __int64 v22; // r9
  __int64 v23; // rcx
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rcx
  unsigned __int64 v26; // r9
  signed int v27; // eax
  __int64 v28; // r12
  __int64 v29; // r10
  unsigned int v30; // r8d
  __int64 v31; // r8
  ULONG v32; // ebx
  int v33; // ecx
  int v34; // edx
  __int64 v35; // r8
  __int64 v36; // rcx
  unsigned int v37; // eax
  __int64 Buffer; // rax
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  unsigned __int64 v42; // rdx
  unsigned __int64 v43; // r8
  signed int v44; // eax
  __int64 v45; // rcx
  _QWORD *v46; // rax
  __int64 *v47; // rdx
  __int64 v48; // rcx
  __int64 *v49; // r11
  __int64 v50; // rcx
  __int64 *v51; // r10
  __int64 v52; // rcx
  __int64 v53; // rax
  __int64 v54; // r9
  __int64 v55; // [rsp+88h] [rbp-80h]

  v1 = *(_QWORD *)(BugCheckParameter4 + 304);
  v3 = *(_QWORD *)(BugCheckParameter4 + 560);
  v4 = *(_DWORD *)(v1 + 36);
  if ( v4 < 0x68 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          &WPP_03d80664418738de4d4c12d6c892b627_Traceguids,
          BugCheckParameter4,
          v4);
    }
    Smb2SetError(
      BugCheckParameter4,
      3221225485LL,
      "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\getinfo.c",
      464);
    v5 = 1;
    goto LABEL_7;
  }
  v7 = *(_QWORD *)(v1 + 24);
  if ( *(_WORD *)(v7 + 64) != 41 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        &WPP_03d80664418738de4d4c12d6c892b627_Traceguids,
        BugCheckParameter4);
    }
    Smb2SetError(
      BugCheckParameter4,
      3221225485LL,
      "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\getinfo.c",
      480);
    v5 = 2;
    goto LABEL_7;
  }
  v8 = *(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 96) + 496LL);
  EaList = Smb2VerifySessionExEx(BugCheckParameter4, *(_QWORD *)(v7 + 40), v7, 0, 1, 0);
  if ( EaList < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        &WPP_03d80664418738de4d4c12d6c892b627_Traceguids,
        BugCheckParameter4);
    }
    v10 = 495;
LABEL_21:
    v11 = (unsigned int)EaList;
LABEL_22:
    Smb2SetError(BugCheckParameter4, v11, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\getinfo.c", v10);
    return 0;
  }
  v12 = Smb2VerifyFileEx(BugCheckParameter4);
  if ( v12 >= 0 )
    goto LABEL_29;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_hq(WPP_GLOBAL_Control->AttachedDevice, 91, v13, *(unsigned __int16 *)(v7 + 12), BugCheckParameter4);
  }
  if ( v12 == -1073741528 )
  {
LABEL_29:
    v15 = Smb2VerifyTreeConnect_Old(BugCheckParameter4, *(unsigned int *)(v7 + 36), v7);
    if ( v15 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_hq(WPP_GLOBAL_Control->AttachedDevice, 92, v14, *(unsigned __int16 *)(v7 + 12), BugCheckParameter4);
      }
      goto LABEL_39;
    }
    if ( v12 == -1073741528 && *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 560) + 56LL) + 154LL) )
      *(_BYTE *)(BugCheckParameter4 + 474) = 1;
  }
  if ( v12 < 0 )
  {
    v15 = v12;
LABEL_39:
    v10 = 505;
    v11 = (unsigned int)v15;
    goto LABEL_22;
  }
  v16 = *(_DWORD *)(v7 + 68);
  if ( v16 > *(_DWORD *)(v8 + 36) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        &WPP_03d80664418738de4d4c12d6c892b627_Traceguids,
        BugCheckParameter4);
    }
    Smb2SetError(
      BugCheckParameter4,
      3221225485LL,
      "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\getinfo.c",
      519);
    v5 = 3;
    goto LABEL_7;
  }
  if ( (*(_BYTE *)(v8 + 49) & 2) == 0 )
    goto LABEL_70;
  if ( Smb2SingleCreditChargePerSpecifiedRequest )
  {
    v17 = 0x10000;
    if ( v16 < 0x10000 )
    {
      *(_DWORD *)(v7 + 68) = v16;
      if ( !v16 )
        goto LABEL_54;
      v17 = v16;
    }
    else
    {
      *(_DWORD *)(v7 + 68) = 0x10000;
    }
    if ( ((v17 - 1) & 0xFFFF0000) != 0 )
      __int2c();
LABEL_54:
    v18 = *(unsigned __int16 *)(BugCheckParameter4 + 488);
    if ( (_WORD)v18 != 1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          &WPP_03d80664418738de4d4c12d6c892b627_Traceguids,
          BugCheckParameter4,
          v18);
      }
      v19 = 549;
LABEL_60:
      Smb2SetError(
        BugCheckParameter4,
        3221225485LL,
        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\getinfo.c",
        v19);
      v5 = 4;
LABEL_7:
      Smb2LkmdTelCollectParsingFailureGetInfoHelper(v3, v5);
      return 0;
    }
    goto LABEL_70;
  }
  if ( v16 )
    v20 = ((v16 - 1) >> 16) + 1;
  else
    v20 = 1;
  v21 = *(unsigned __int16 *)(BugCheckParameter4 + 488);
  if ( v21 < v20 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qDD(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        &WPP_03d80664418738de4d4c12d6c892b627_Traceguids,
        BugCheckParameter4,
        v21,
        v20);
    }
    v19 = 568;
    goto LABEL_60;
  }
LABEL_70:
  *(_BYTE *)(v3 + 192) = *(_BYTE *)(v7 + 66);
  *(_DWORD *)(v3 + 196) = *(_DWORD *)(v7 + 68);
  switch ( *(_BYTE *)(v7 + 66) )
  {
    case 1:
      if ( *(_BYTE *)(v7 + 67) == 15 )
      {
        *(_DWORD *)(v3 + 208) = *(_DWORD *)(v7 + 80);
        *(_DWORD *)(v3 + 204) = *(_DWORD *)(v7 + 84);
        v41 = *(unsigned int *)(v7 + 76);
        if ( (_DWORD)v41 )
        {
          v42 = *(unsigned __int16 *)(v7 + 72);
          if ( v42 - 104 > 0x40
            || ((v43 = v42 + v41, v42 + v41 < v42)
             || v43 > 0xFFFFFFFF
             || v43 > *(unsigned int *)(*(_QWORD *)(BugCheckParameter4 + 304) + 36LL)
              ? (v44 = -1073741811)
              : (v44 = (((_BYTE)v42 + (_BYTE)v7) & 7) != 0 ? 0xC000000D : 0),
                v44 < 0) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_q(
                WPP_GLOBAL_Control->AttachedDevice,
                19,
                &WPP_03d80664418738de4d4c12d6c892b627_Traceguids,
                BugCheckParameter4);
            }
            Smb2SetError(
              BugCheckParameter4,
              3221225485LL,
              "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\getinfo.c",
              626);
            v5 = 5;
            goto LABEL_7;
          }
          EaList = Smb2ValidateGetEaList(v7 + v42, (unsigned int)v41, v3);
          if ( EaList < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_q(
                WPP_GLOBAL_Control->AttachedDevice,
                20,
                &WPP_03d80664418738de4d4c12d6c892b627_Traceguids,
                BugCheckParameter4);
            }
            v10 = 641;
            goto LABEL_21;
          }
          *(_QWORD *)(v3 + 216) = v7 + *(unsigned __int16 *)(v7 + 72);
          *(_DWORD *)(v3 + 212) = *(_DWORD *)(v7 + 76);
        }
      }
      else
      {
        EaList = IoCheckQuerySetFileInformation(
                   (FILE_INFORMATION_CLASS)*(unsigned __int8 *)(v7 + 67),
                   *(_DWORD *)(v7 + 68),
                   0);
        if ( EaList < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              18,
              &WPP_03d80664418738de4d4c12d6c892b627_Traceguids,
              BugCheckParameter4);
          }
          v10 = 593;
          goto LABEL_21;
        }
      }
      v45 = *(_QWORD *)(v3 + 72);
      *(_DWORD *)(v3 + 200) = *(unsigned __int8 *)(v7 + 67);
      EaList = IoCheckFunctionAccess(*(_DWORD *)(v45 + 184), 5u, 0, 0, (PVOID)(v3 + 200), 0);
      if ( EaList < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            21,
            &WPP_03d80664418738de4d4c12d6c892b627_Traceguids,
            BugCheckParameter4);
        }
        v10 = 669;
        goto LABEL_21;
      }
      EaList = Smb2ValidateGetFileInfoParameters(BugCheckParameter4);
      if ( EaList < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            22,
            &WPP_03d80664418738de4d4c12d6c892b627_Traceguids,
            BugCheckParameter4);
        }
        v10 = 680;
        goto LABEL_21;
      }
      break;
    case 2:
      EaList = IoCheckQuerySetVolumeInformation(
                 (FS_INFORMATION_CLASS)*(unsigned __int8 *)(v7 + 67),
                 *(_DWORD *)(v7 + 68),
                 0);
      if ( EaList < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            23,
            &WPP_03d80664418738de4d4c12d6c892b627_Traceguids,
            BugCheckParameter4);
        }
        v10 = 697;
        goto LABEL_21;
      }
      v40 = *(_QWORD *)(v3 + 72);
      *(_DWORD *)(v3 + 200) = *(unsigned __int8 *)(v7 + 67);
      EaList = IoCheckFunctionAccess(*(_DWORD *)(v40 + 184), 0xAu, 0, 0, 0, (PVOID)(v3 + 200));
      if ( EaList < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            24,
            &WPP_03d80664418738de4d4c12d6c892b627_Traceguids,
            BugCheckParameter4);
        }
        v10 = 718;
        goto LABEL_21;
      }
      EaList = Smb2ValidateGetFsInfoParameters(BugCheckParameter4);
      if ( EaList < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            25,
            &WPP_03d80664418738de4d4c12d6c892b627_Traceguids,
            BugCheckParameter4);
        }
        v10 = 729;
        goto LABEL_21;
      }
      break;
    case 3:
      if ( *(_BYTE *)(v7 + 67) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            26,
            &WPP_03d80664418738de4d4c12d6c892b627_Traceguids,
            BugCheckParameter4);
        }
        Smb2SetError(
          BugCheckParameter4,
          3221225485LL,
          "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\getinfo.c",
          743);
        v5 = 6;
        goto LABEL_7;
      }
      v39 = *(_QWORD *)(v3 + 72);
      *(_DWORD *)(v3 + 200) = *(_DWORD *)(v7 + 80) & 0x1007F;
      EaList = IoCheckFunctionAccess(*(_DWORD *)(v39 + 184), 0x14u, 0, 0, (PVOID)(v3 + 200), 0);
      if ( EaList < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            27,
            &WPP_03d80664418738de4d4c12d6c892b627_Traceguids,
            BugCheckParameter4);
        }
        v10 = 774;
        goto LABEL_21;
      }
      break;
    case 4:
      v23 = *(unsigned int *)(v7 + 76);
      if ( (unsigned int)v23 < 0x10 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            28,
            &WPP_03d80664418738de4d4c12d6c892b627_Traceguids,
            BugCheckParameter4);
        }
        Smb2SetError(
          BugCheckParameter4,
          3221225485LL,
          "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\getinfo.c",
          794);
        v5 = 7;
        goto LABEL_7;
      }
      v24 = *(unsigned __int16 *)(v7 + 72);
      if ( v24 - 104 > 0x40
        || ((v25 = v24 + v23, v26 = *(unsigned int *)(*(_QWORD *)(BugCheckParameter4 + 304) + 36LL), v25 < v24)
         || v25 > v26
         || v25 > 0xFFFFFFFF
          ? (v27 = -1073741811)
          : (v27 = (((_BYTE)v24 + (_BYTE)v7) & 7) != 0 ? 0xC000000D : 0),
            v27 < 0) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            29,
            &WPP_03d80664418738de4d4c12d6c892b627_Traceguids,
            BugCheckParameter4);
        }
        Smb2SetError(
          BugCheckParameter4,
          3221225485LL,
          "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\getinfo.c",
          817);
        v5 = 8;
        goto LABEL_7;
      }
      v28 = v7 + v24;
      v29 = *(unsigned int *)(v7 + v24 + 12);
      if ( (v29 & 3) != 0
        || (v30 = *(_DWORD *)(v28 + 4), (unsigned __int64)(v30 + (unsigned int)v24) + 16 > v26)
        || v30 > (unsigned int)v26
        || (unsigned int)v29 > (unsigned int)v26
        || (v31 = *(unsigned int *)(v28 + 8), v31 + v24 + 16 > v26)
        || v31 + v29 + v24 + 16 > v26
        || (_DWORD)v31
        && ((unsigned int)v31 < 0xC
         || (v32 = *(_DWORD *)(v28 + 8), v32 < RtlLengthRequiredSid(*(unsigned __int8 *)(v29 + v28 + 17)))) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            30,
            &WPP_03d80664418738de4d4c12d6c892b627_Traceguids,
            BugCheckParameter4);
        }
        v22 = 848;
        goto LABEL_118;
      }
      *(_QWORD *)(v3 + 200) = v28 + 16;
      v33 = *(_DWORD *)(v28 + 4);
      *(_DWORD *)(v3 + 216) = v33;
      v34 = *(_DWORD *)(v28 + 8);
      *(_DWORD *)(v3 + 220) = v34;
      v35 = *(unsigned int *)(v28 + 12);
      *(_DWORD *)(v3 + 224) = v35;
      *(_BYTE *)(v3 + 228) = *(_BYTE *)v28;
      *(_BYTE *)(v3 + 229) = *(_BYTE *)(v28 + 1);
      if ( v33 || !v34 )
        v36 = 0;
      else
        v36 = v35 + v28 + 16;
      *(_QWORD *)(v3 + 208) = v36;
      break;
    default:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          31,
          &WPP_03d80664418738de4d4c12d6c892b627_Traceguids,
          BugCheckParameter4);
      }
      v22 = 885;
LABEL_118:
      Smb2SetError(
        BugCheckParameter4,
        3221225485LL,
        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\getinfo.c",
        v22);
      v5 = 9;
      goto LABEL_7;
  }
  v37 = *(_DWORD *)(v7 + 68);
  if ( v37 )
  {
    Buffer = SrvNetAllocateBuffer(v37, 0);
    *(_QWORD *)(v3 + 160) = Buffer;
    if ( !Buffer )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          32,
          &WPP_03d80664418738de4d4c12d6c892b627_Traceguids,
          BugCheckParameter4);
      }
      v10 = 901;
      v11 = 3221225989LL;
      goto LABEL_22;
    }
  }
  if ( (Microsoft_Windows_SMBServerEnableBits & 1) != 0 )
  {
    v46 = *(_QWORD **)(BugCheckParameter4 + 560);
    v47 = &Srv2ZeroGuid;
    v48 = v46[9];
    v49 = (__int64 *)(v48 + 96);
    if ( !v48 )
      v49 = &Srv2ZeroGuid;
    v50 = v46[7];
    v51 = (__int64 *)(v50 + 24);
    if ( !v50 )
      v51 = &Srv2ZeroGuid;
    v52 = v46[4];
    if ( v52 )
      v47 = (__int64 *)(v52 + 72);
    v53 = *(_QWORD *)(BugCheckParameter4 + 416);
    if ( v53 )
      v54 = *(_QWORD *)(*(_QWORD *)(v53 + 560) + 176LL);
    else
      LOBYTE(v54) = -1;
    v55 = *(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 96) + 496LL) + 72LL;
    McTemplateK0xqqxxhhquuqqqxjjjj_EtwWriteTransfer(
      v55,
      (_DWORD)v47,
      BugCheckParameter4 + 584,
      *(_QWORD *)(v7 + 40),
      *(_DWORD *)(v7 + 32),
      *(_DWORD *)(v7 + 36),
      *(_QWORD *)(v7 + 24),
      v54,
      *(_WORD *)(v7 + 12),
      *(_WORD *)(v7 + 14),
      *(_DWORD *)(v7 + 16),
      *(_BYTE *)(v7 + 66),
      *(_BYTE *)(v7 + 67),
      *(_DWORD *)(v7 + 68),
      *(_DWORD *)(v7 + 80),
      *(_DWORD *)(v7 + 84),
      *(_QWORD *)(v7 + 88),
      v55,
      (__int64)v47,
      (__int64)v51,
      (__int64)v49);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x140087780  push    rbx
0x140087782  push    rbp
0x140087783  push    rsi
0x140087784  push    rdi
0x140087785  push    r12
0x140087787  push    r13
0x140087789  push    r14
0x14008778b  push    r15
0x14008778d  sub     rsp, 0C8h
0x140087794  mov     r14, [rcx+130h]
0x14008779b  mov     rdi, rcx
0x14008779e  mov     r13, [rcx+230h]
0x1400877a5  mov     r8d, [r14+24h]
0x1400877a9  cmp     r8d, 68h ; 'h'
0x1400877ad  jnb     short loc_14008781C
0x1400877af  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400877b6  lea     rbp, WPP_GLOBAL_Control
0x1400877bd  mov     esi, 1
0x1400877c2  cmp     rcx, rbp
0x1400877c5  jz      short loc_1400877F1
0x1400877c7  test    dword ptr [rcx+2Ch], 8000000h
0x1400877ce  jz      short loc_1400877F1
0x1400877d0  cmp     [rcx+29h], sil
0x1400877d4  jb      short loc_1400877F1
0x1400877d6  mov     rcx, [rcx+18h]
0x1400877da  lea     edx, [rsi+0Bh]
0x1400877dd  mov     dword ptr [rsp+108h+Arg1], r8d
0x1400877e2  mov     r9, rdi
0x1400877e5  lea     r8, WPP_03d80664418738de4d4c12d6c892b627_Traceguids
0x1400877ec  call    WPP_SF_qD
0x1400877f1  mov     r9d, 1D0h
0x1400877f7  lea     r8, aOnecoreBaseFsR_3; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x1400877fe  mov     edx, 0C000000Dh
0x140087803  mov     rcx, rdi
0x140087806  call    _Smb2SetError
0x14008780b  mov     edx, esi
0x14008780d  mov     rcx, r13
0x140087810  call    Smb2LkmdTelCollectParsingFailureGetInfoHelper
0x140087815  xor     eax, eax
0x140087817  jmp     loc_14008843A
0x14008781c  mov     r14, [r14+18h]
0x140087820  cmp     word ptr [r14+40h], 29h ; ')'
0x140087826  jz      short loc_140087886
0x140087828  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008782f  lea     rbp, WPP_GLOBAL_Control
0x140087836  cmp     rcx, rbp
0x140087839  jz      short loc_140087865
0x14008783b  test    dword ptr [rcx+2Ch], 8000000h
0x140087842  jz      short loc_140087865
0x140087844  mov     esi, 1
0x140087849  cmp     [rcx+29h], sil
0x14008784d  jb      short loc_140087865
0x14008784f  mov     rcx, [rcx+18h]
0x140087853  lea     edx, [rsi+0Ch]
0x140087856  mov     r9, rdi
0x140087859  lea     r8, WPP_03d80664418738de4d4c12d6c892b627_Traceguids
0x140087860  call    WPP_SF_q
0x140087865  mov     r9d, 1E0h
0x14008786b  lea     r8, aOnecoreBaseFsR_3; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140087872  mov     edx, 0C000000Dh
0x140087877  mov     rcx, rdi
0x14008787a  call    _Smb2SetError
0x14008787f  mov     edx, 2
0x140087884  jmp     short loc_14008780D
0x140087886  mov     rax, [rcx+60h]
0x14008788a  mov     esi, 1
0x14008788f  mov     rdx, [r14+28h]
0x140087893  xor     r9d, r9d
0x140087896  mov     byte ptr [rsp+108h+Arg2], 0
0x14008789b  mov     r8, r14
0x14008789e  mov     byte ptr [rsp+108h+Arg1], sil
0x1400878a3  mov     r12, [rax+1F0h]
0x1400878aa  call    Smb2VerifySessionExEx
0x1400878af  mov     ebx, eax
0x1400878b1  test    eax, eax
0x1400878b3  jns     short loc_140087909
0x1400878b5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400878bc  lea     rbp, WPP_GLOBAL_Control
0x1400878c3  cmp     rcx, rbp
0x1400878c6  jz      short loc_1400878ED
0x1400878c8  test    dword ptr [rcx+2Ch], 8000000h
0x1400878cf  jz      short loc_1400878ED
0x1400878d1  cmp     [rcx+29h], sil
0x1400878d5  jb      short loc_1400878ED
0x1400878d7  mov     rcx, [rcx+18h]
0x1400878db  lea     edx, [rsi+0Dh]
0x1400878de  mov     r9, rdi
0x1400878e1  lea     r8, WPP_03d80664418738de4d4c12d6c892b627_Traceguids
0x1400878e8  call    WPP_SF_q
0x1400878ed  mov     r9d, 1EFh
0x1400878f3  mov     edx, ebx
0x1400878f5  lea     r8, aOnecoreBaseFsR_3; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x1400878fc  mov     rcx, rdi
0x1400878ff  call    _Smb2SetError
0x140087904  jmp     loc_140087815
0x140087909  movups  xmm0, xmmword ptr [r14+58h]
0x14008790e  mov     r9b, sil
0x140087911  lea     rdx, [rsp+108h+var_58]
0x140087919  mov     r8, r14
0x14008791c  mov     rcx, rdi; BugCheckParameter4
0x14008791f  movdqu  [rsp+108h+var_58], xmm0
0x140087928  call    Smb2VerifyFileEx
0x14008792d  lea     rbp, WPP_GLOBAL_Control
0x140087934  mov     ebx, eax
0x140087936  test    eax, eax
0x140087938  jns     short loc_140087975
0x14008793a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140087941  cmp     rcx, rbp
0x140087944  jz      short loc_14008796D
0x140087946  test    dword ptr [rcx+2Ch], 800000h
0x14008794d  jz      short loc_14008796D
0x14008794f  cmp     [rcx+29h], sil
0x140087953  jb      short loc_14008796D
0x140087955  movzx   r9d, word ptr [r14+0Ch]
0x14008795a  mov     edx, 5Bh ; '['
0x14008795f  mov     rcx, [rcx+18h]
0x140087963  mov     [rsp+108h+Arg1], rdi
0x140087968  call    WPP_SF_hq
0x14008796d  cmp     ebx, 0C0000128h
0x140087973  jnz     short loc_1400879E3
0x140087975  mov     edx, [r14+24h]
0x140087979  mov     r8, r14
0x14008797c  mov     rcx, rdi
0x14008797f  call    Smb2VerifyTreeConnect_Old
0x140087984  mov     r15d, eax
0x140087987  test    eax, eax
0x140087989  jns     short loc_1400879C0
0x14008798b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140087992  cmp     rcx, rbp
0x140087995  jz      short loc_1400879EA
0x140087997  test    dword ptr [rcx+2Ch], 800000h
0x14008799e  jz      short loc_1400879EA
0x1400879a0  cmp     [rcx+29h], sil
0x1400879a4  jb      short loc_1400879EA
0x1400879a6  movzx   r9d, word ptr [r14+0Ch]
0x1400879ab  mov     edx, 5Ch ; '\'
0x1400879b0  mov     rcx, [rcx+18h]
0x1400879b4  mov     [rsp+108h+Arg1], rdi
0x1400879b9  call    WPP_SF_hq
0x1400879be  jmp     short loc_1400879EA
0x1400879c0  cmp     ebx, 0C0000128h
0x1400879c6  jnz     short loc_1400879E3
0x1400879c8  mov     rax, [rdi+230h]
0x1400879cf  mov     rcx, [rax+38h]
0x1400879d3  cmp     byte ptr [rcx+9Ah], 0
0x1400879da  jz      short loc_1400879E3
0x1400879dc  mov     [rdi+1DAh], sil
0x1400879e3  test    ebx, ebx
0x1400879e5  jns     short loc_1400879F8
0x1400879e7  mov     r15d, ebx
0x1400879ea  mov     r9d, 1F9h
0x1400879f0  mov     edx, r15d
0x1400879f3  jmp     loc_1400878F5
0x1400879f8  mov     ecx, [r14+44h]
0x1400879fc  cmp     ecx, [r12+24h]
0x140087a01  jbe     short loc_140087A5A
0x140087a03  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140087a0a  cmp     rcx, rbp
0x140087a0d  jz      short loc_140087A36
0x140087a0f  test    dword ptr [rcx+2Ch], 8000000h
0x140087a16  jz      short loc_140087A36
0x140087a18  cmp     [rcx+29h], sil
0x140087a1c  jb      short loc_140087A36
0x140087a1e  mov     rcx, [rcx+18h]
0x140087a22  lea     r8, WPP_03d80664418738de4d4c12d6c892b627_Traceguids
0x140087a29  mov     edx, 0Fh
0x140087a2e  mov     r9, rdi
0x140087a31  call    WPP_SF_q
0x140087a36  mov     r9d, 207h
0x140087a3c  lea     r8, aOnecoreBaseFsR_3; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140087a43  mov     edx, 0C000000Dh
0x140087a48  mov     rcx, rdi
0x140087a4b  call    _Smb2SetError
0x140087a50  mov     edx, 3
0x140087a55  jmp     loc_14008780D
0x140087a5a  test    byte ptr [r12+31h], 2
0x140087a60  jz      loc_140087B65
0x140087a66  cmp     cs:Smb2SingleCreditChargePerSpecifiedRequest, 0
0x140087a6d  jz      loc_140087B04
0x140087a73  mov     eax, 10000h
0x140087a78  cmp     ecx, eax
0x140087a7a  jb      short loc_140087A82
0x140087a7c  mov     [r14+44h], eax
0x140087a80  jmp     short loc_140087A8C
0x140087a82  mov     [r14+44h], ecx
0x140087a86  test    ecx, ecx
0x140087a88  jz      short loc_140087A97
0x140087a8a  mov     eax, ecx
0x140087a8c  dec     eax
0x140087a8e  test    eax, 0FFFF0000h
0x140087a93  jz      short loc_140087A97
0x140087a95  int     2Ch; Windows NT - assertion failure
0x140087a97  movzx   edx, word ptr [rdi+1E8h]
0x140087a9e  cmp     dx, si
0x140087aa1  jz      loc_140087B65
0x140087aa7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140087aae  cmp     rcx, rbp
0x140087ab1  jz      short loc_140087AE0
0x140087ab3  test    dword ptr [rcx+2Ch], 8000000h
0x140087aba  jz      short loc_140087AE0
0x140087abc  cmp     [rcx+29h], sil
0x140087ac0  jb      short loc_140087AE0
0x140087ac2  mov     rcx, [rcx+18h]
0x140087ac6  lea     r8, WPP_03d80664418738de4d4c12d6c892b627_Traceguids
0x140087acd  mov     eax, edx
0x140087acf  mov     r9, rdi
0x140087ad2  mov     edx, 10h
0x140087ad7  mov     dword ptr [rsp+108h+Arg1], eax
0x140087adb  call    WPP_SF_qD
0x140087ae0  mov     r9d, 225h
0x140087ae6  lea     r8, aOnecoreBaseFsR_3; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140087aed  mov     edx, 0C000000Dh
0x140087af2  mov     rcx, rdi
0x140087af5  call    _Smb2SetError
0x140087afa  mov     edx, 4
0x140087aff  jmp     loc_14008780D
0x140087b04  test    ecx, ecx
0x140087b06  jz      short loc_140087B11
0x140087b08  dec     ecx
0x140087b0a  shr     ecx, 10h
0x140087b0d  add     ecx, esi
0x140087b0f  jmp     short loc_140087B13
0x140087b11  mov     ecx, esi
0x140087b13  movzx   r8d, word ptr [rdi+1E8h]
0x140087b1b  cmp     r8d, ecx
0x140087b1e  jnb     short loc_140087B65
0x140087b20  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140087b27  cmp     r10, rbp
0x140087b2a  jz      short loc_140087B5D
0x140087b2c  test    dword ptr [r10+2Ch], 8000000h
0x140087b34  jz      short loc_140087B5D
0x140087b36  cmp     [r10+29h], sil
0x140087b3a  jb      short loc_140087B5D
0x140087b3c  mov     dword ptr [rsp+108h+Arg2], ecx
0x140087b40  mov     edx, 11h
0x140087b45  mov     rcx, [r10+18h]
0x140087b49  mov     r9, rdi
0x140087b4c  mov     dword ptr [rsp+108h+Arg1], r8d
0x140087b51  lea     r8, WPP_03d80664418738de4d4c12d6c892b627_Traceguids
0x140087b58  call    WPP_SF_qDD
0x140087b5d  mov     r9d, 238h
0x140087b63  jmp     short loc_140087AE6
0x140087b65  mov     al, [r14+42h]
0x140087b69  mov     [r13+0C0h], al
0x140087b70  mov     eax, [r14+44h]
0x140087b74  mov     [r13+0C4h], eax
0x140087b7b  movzx   ecx, byte ptr [r14+42h]
0x140087b80  sub     ecx, esi
0x140087b82  jz      loc_1400880AC
0x140087b88  sub     ecx, esi
0x140087b8a  jz      loc_140087F82
0x140087b90  sub     ecx, esi
0x140087b92  jz      loc_140087E9E
0x140087b98  cmp     ecx, esi
0x140087b9a  jz      short loc_140087BDF
0x140087b9c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140087ba3  cmp     rcx, rbp
0x140087ba6  jz      short loc_140087BCF
0x140087ba8  test    dword ptr [rcx+2Ch], 8000000h
0x140087baf  jz      short loc_140087BCF
0x140087bb1  cmp     [rcx+29h], sil
0x140087bb5  jb      short loc_140087BCF
0x140087bb7  mov     rcx, [rcx+18h]
0x140087bbb  lea     r8, WPP_03d80664418738de4d4c12d6c892b627_Traceguids
0x140087bc2  mov     edx, 1Fh
0x140087bc7  mov     r9, rdi
0x140087bca  call    WPP_SF_q
0x140087bcf  mov     r9d, 375h
0x140087bd5  mov     edx, 0C000000Dh
0x140087bda  jmp     loc_140087E30
0x140087bdf  mov     ecx, [r14+4Ch]
0x140087be3  cmp     ecx, 10h
0x140087be6  jnb     short loc_140087C3F
0x140087be8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140087bef  cmp     rcx, rbp
0x140087bf2  jz      short loc_140087C1B
0x140087bf4  test    dword ptr [rcx+2Ch], 8000000h
0x140087bfb  jz      short loc_140087C1B
0x140087bfd  cmp     [rcx+29h], sil
0x140087c01  jb      short loc_140087C1B
0x140087c03  mov     rcx, [rcx+18h]
0x140087c07  lea     r8, WPP_03d80664418738de4d4c12d6c892b627_Traceguids
0x140087c0e  mov     edx, 1Ch
0x140087c13  mov     r9, rdi
0x140087c16  call    WPP_SF_q
0x140087c1b  mov     r9d, 31Ah
0x140087c21  lea     r8, aOnecoreBaseFsR_3; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140087c28  mov     edx, 0C000000Dh
0x140087c2d  mov     rcx, rdi
0x140087c30  call    _Smb2SetError
0x140087c35  mov     edx, 7
0x140087c3a  jmp     loc_14008780D
0x140087c3f  movzx   edx, word ptr [r14+48h]
0x140087c44  mov     r15d, 0C000000Dh
0x140087c4a  lea     rax, [rdx-68h]
0x140087c4e  cmp     rax, 40h ; '@'
0x140087c52  ja      loc_140087E49
0x140087c58  mov     rax, [rdi+130h]
0x140087c5f  add     rcx, rdx
0x140087c62  mov     r9d, [rax+24h]
  ... truncated ...
```
