# Smb2ValidateSetInfo

- ea: `0x14005b5d0`
- end: `0x14005c009`
- name: `Smb2ValidateSetInfo`
- size: `2617`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter4)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140073a60`

## callees

- `0x140007400`
- `0x14001c8ec`
- `0x14001cef0`
- `0x14001d5c8`
- `0x1400222ec`
- `0x140022958`
- `0x1400229ac`
- `0x14002ad2c`
- `0x140033604`
- `0x14005b5d0`
- `0x14005c600`
- `0x14006e5c8`
- `0x140081b40`

## import_xrefs

- `ntoskrnl!IoCheckFunctionAccess` at `0x14005bba9`
- `ntoskrnl!IoCheckFunctionAccess` at `0x14005bcf2`
- `ntoskrnl!IoCheckFunctionAccess` at `0x14005be08`
- `ntoskrnl!IoCheckFunctionAccess` at `0x14005bba9`
- `ntoskrnl!IoCheckFunctionAccess` at `0x14005bcf2`
- `ntoskrnl!IoCheckFunctionAccess` at `0x14005be08`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x14005bb70`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x14005bb70`
- `ntoskrnl!IoCheckQuerySetFileInformation` at `0x14005bd80`
- `ntoskrnl!IoCheckQuerySetFileInformation` at `0x14005bd80`
- `ntoskrnl!IoCheckQuerySetVolumeInformation` at `0x14005bc60`
- `ntoskrnl!IoCheckQuerySetVolumeInformation` at `0x14005bc60`
- `ntoskrnl!IoCheckQuotaBufferValidity` at `0x14005bae9`
- `ntoskrnl!IoCheckQuotaBufferValidity` at `0x14005bae9`

## pseudocode

```c
__int64 __fastcall Smb2ValidateSetInfo(ULONG_PTR BugCheckParameter4)
{
  __int64 v1; // r14
  __int64 v3; // rbp
  unsigned __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // r14
  unsigned __int64 v7; // rcx
  __int64 v8; // r9
  unsigned __int64 v9; // rdx
  signed int v10; // eax
  __int64 v11; // r9
  int v12; // r12d
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // r8
  int v16; // r13d
  __int64 v17; // r8
  unsigned int v18; // r8d
  int v19; // edx
  __int64 v20; // r9
  unsigned int v21; // r8d
  unsigned int v22; // r9d
  ULONG v23; // edx
  struct _FILE_QUOTA_INFORMATION *v24; // rcx
  NTSTATUS v25; // r15d
  __int64 v26; // rcx
  NTSTATUS v27; // ebp
  NTSTATUS v28; // r15d
  __int64 v29; // rcx
  int v30; // eax
  NTSTATUS v31; // r12d
  UCHAR v32; // dl
  _QWORD *v33; // rax
  __int64 *v34; // rdx
  __int64 v35; // rcx
  __int64 *v36; // r11
  __int64 v37; // rcx
  __int64 *v38; // r10
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // r9
  __int64 v43; // [rsp+88h] [rbp-80h]
  __int64 ErrorOffset; // [rsp+110h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(BugCheckParameter4 + 304);
  v3 = *(_QWORD *)(BugCheckParameter4 + 560);
  v4 = *(unsigned int *)(v1 + 36);
  if ( (unsigned int)v4 < 0x61 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000000) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids,
          BugCheckParameter4,
          v4);
    }
    Smb2SetError(
      BugCheckParameter4,
      3221225485LL,
      "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\setinfo.c",
      433);
    v5 = 7;
    goto LABEL_154;
  }
  v6 = *(_QWORD *)(v1 + 24);
  if ( *(_WORD *)(v6 + 64) != 33 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids,
        BugCheckParameter4);
    }
    Smb2SetError(
      BugCheckParameter4,
      3221225485LL,
      "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\setinfo.c",
      449);
    v5 = 8;
    goto LABEL_154;
  }
  v7 = *(unsigned __int16 *)(v6 + 72);
  if ( v7 - 96 > 0x40
    || ((v8 = *(unsigned int *)(v6 + 68), v9 = v8 + v7, v8 + v7 < v7) || v9 > 0xFFFFFFFF || v9 > v4
      ? (v10 = -1073741811)
      : (v10 = (((_BYTE)v7 + (_BYTE)v6) & 7) != 0 ? 0xC000000D : 0),
        v10 < 0) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
        WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids,
        BugCheckParameter4);
    }
    Smb2SetError(
      BugCheckParameter4,
      3221225485LL,
      "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\setinfo.c",
      471);
    v5 = 9;
    goto LABEL_154;
  }
  ErrorOffset = *(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 96) + 496LL);
  if ( (unsigned int)v8 > *(_DWORD *)(ErrorOffset + 36) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        20,
        WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids,
        BugCheckParameter4);
    }
    v11 = 485;
LABEL_26:
    Smb2SetError(
      BugCheckParameter4,
      3221225485LL,
      "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\setinfo.c",
      v11);
    v5 = 10;
LABEL_154:
    Smb2LkmdTelCollectParsingFailureSetInfoHelper(v3, v5);
    return 0;
  }
  *(_QWORD *)(v3 + 200) = v6 + v7;
  *(_DWORD *)(v3 + 208) = *(_DWORD *)(v6 + 68);
  v12 = Smb2VerifySessionExEx(BugCheckParameter4, *(_QWORD *)(v6 + 40), v6, 0, 1, 0);
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids,
        BugCheckParameter4);
    }
    v13 = 506;
    goto LABEL_33;
  }
  v16 = Smb2VerifyFileEx(BugCheckParameter4);
  if ( v16 >= 0 )
    goto LABEL_41;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_hq(WPP_GLOBAL_Control->AttachedDevice, 91, v15, *(unsigned __int16 *)(v6 + 12), BugCheckParameter4);
  }
  if ( v16 == -1073741528 )
  {
LABEL_41:
    v12 = Smb2VerifyTreeConnect_Old(BugCheckParameter4, *(unsigned int *)(v6 + 36), v6);
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_hq(WPP_GLOBAL_Control->AttachedDevice, 92, v17, *(unsigned __int16 *)(v6 + 12), BugCheckParameter4);
      }
      goto LABEL_51;
    }
    if ( v16 == -1073741528 && *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 560) + 56LL) + 154LL) )
      *(_BYTE *)(BugCheckParameter4 + 474) = 1;
  }
  if ( v16 < 0 )
  {
    v12 = v16;
LABEL_51:
    v13 = 516;
LABEL_33:
    v14 = (unsigned int)v12;
LABEL_34:
    Smb2SetError(BugCheckParameter4, v14, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\setinfo.c", v13);
    return 0;
  }
  if ( (*(_BYTE *)(ErrorOffset + 49) & 2) != 0 )
  {
    v18 = *(_DWORD *)(v6 + 68);
    if ( Smb2SingleCreditChargePerSpecifiedRequest )
    {
      if ( v18 > 0x11000 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            22,
            WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids,
            BugCheckParameter4,
            v18);
        }
        v11 = 537;
        goto LABEL_26;
      }
      v19 = *(unsigned __int16 *)(BugCheckParameter4 + 488);
      if ( (_WORD)v19 != 1 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            23,
            WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids,
            BugCheckParameter4,
            v19);
        }
        v20 = 549;
LABEL_66:
        Smb2SetError(
          BugCheckParameter4,
          3221225485LL,
          "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\setinfo.c",
          v20);
        v5 = 11;
        goto LABEL_154;
      }
    }
    else
    {
      if ( v18 )
        v21 = ((v18 - 1) >> 16) + 1;
      else
        v21 = 1;
      v22 = *(unsigned __int16 *)(BugCheckParameter4 + 488);
      if ( v22 < v21 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qDD(
            WPP_GLOBAL_Control->AttachedDevice,
            24,
            WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids,
            BugCheckParameter4,
            v22,
            v21);
        }
        v20 = 566;
        goto LABEL_66;
      }
    }
  }
  *(_BYTE *)(v3 + 192) = *(_BYTE *)(v6 + 66);
  switch ( *(_BYTE *)(v6 + 66) )
  {
    case 1:
      *(_DWORD *)(v3 + 212) = *(unsigned __int8 *)(v6 + 67);
      if ( *(_BYTE *)(v6 + 67) == 15 )
      {
        v32 = 8;
      }
      else
      {
        v31 = IoCheckQuerySetFileInformation(
                (FILE_INFORMATION_CLASS)*(unsigned __int8 *)(v6 + 67),
                *(_DWORD *)(v6 + 68),
                1u);
        if ( v31 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              25,
              WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids,
              BugCheckParameter4);
          }
          Smb2SetError(
            BugCheckParameter4,
            (unsigned int)v31,
            "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\setinfo.c",
            594);
          v5 = 12;
          goto LABEL_154;
        }
        v32 = 6;
      }
      v27 = IoCheckFunctionAccess(*(_DWORD *)(*(_QWORD *)(v3 + 72) + 184LL), v32, 0, 0, (PVOID)(v3 + 212), 0);
      if ( v27 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            26,
            WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids,
            BugCheckParameter4);
        }
        v13 = 624;
        goto LABEL_99;
      }
      v30 = Smb2ValidateSetFileInfoParameters(BugCheckParameter4);
      if ( v30 >= 0 )
        goto LABEL_137;
      v13 = 631;
      goto LABEL_119;
    case 2:
      v28 = IoCheckQuerySetVolumeInformation(
              (FS_INFORMATION_CLASS)*(unsigned __int8 *)(v6 + 67),
              *(_DWORD *)(v6 + 68),
              1u);
      if ( v28 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            27,
            WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids,
            BugCheckParameter4);
        }
        Smb2SetError(
          BugCheckParameter4,
          (unsigned int)v28,
          "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\setinfo.c",
          646);
        v5 = 13;
        goto LABEL_154;
      }
      v29 = *(_QWORD *)(v3 + 72);
      *(_DWORD *)(v3 + 212) = *(unsigned __int8 *)(v6 + 67);
      v27 = IoCheckFunctionAccess(*(_DWORD *)(v29 + 184), 0xBu, 0, 0, 0, (PVOID)(v3 + 212));
      if ( v27 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            28,
            WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids,
            BugCheckParameter4);
        }
        v13 = 666;
        goto LABEL_99;
      }
      v30 = Smb2ValidateSetFsInfoParameters(BugCheckParameter4);
      if ( v30 >= 0 )
        goto LABEL_137;
      v13 = 673;
LABEL_119:
      v14 = (unsigned int)v30;
      goto LABEL_34;
    case 3:
      if ( *(_BYTE *)(v6 + 67)
        || !RtlValidRelativeSecurityDescriptor(
              *(PSECURITY_DESCRIPTOR *)(v3 + 200),
              *(_DWORD *)(v3 + 208),
              *(_DWORD *)(v6 + 76)) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            29,
            WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids,
            BugCheckParameter4);
        }
        Smb2SetError(
          BugCheckParameter4,
          3221225485LL,
          "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\setinfo.c",
          689);
        v5 = 14;
        goto LABEL_154;
      }
      v26 = *(_QWORD *)(v3 + 72);
      *(_DWORD *)(v3 + 212) = *(_DWORD *)(v6 + 76);
      v27 = IoCheckFunctionAccess(*(_DWORD *)(v26 + 184), 0x15u, 0, 0, (PVOID)(v3 + 212), 0);
      if ( v27 >= 0 )
        goto LABEL_137;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          30,
          WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids,
          BugCheckParameter4);
      }
      v13 = 709;
LABEL_99:
      v14 = (unsigned int)v27;
      goto LABEL_34;
  }
  if ( *(_BYTE *)(v6 + 66) != 4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        32,
        WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids,
        BugCheckParameter4);
    }
    v13 = 742;
    v14 = 3221225485LL;
    goto LABEL_34;
  }
  v23 = *(_DWORD *)(v3 + 208);
  v24 = *(struct _FILE_QUOTA_INFORMATION **)(v3 + 200);
  LODWORD(ErrorOffset) = 0;
  v25 = IoCheckQuotaBufferValidity(v24, v23, (PULONG)&ErrorOffset);
  if ( v25 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        31,
        WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids,
        BugCheckParameter4);
    }
    Smb2SetError(
      BugCheckParameter4,
      (unsigned int)v25,
      "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\setinfo.c",
      729);
    v5 = 15;
    goto LABEL_154;
  }
LABEL_137:
  if ( (Microsoft_Windows_SMBServerEnableBits & 1) != 0 )
  {
    v33 = *(_QWORD **)(BugCheckParameter4 + 560);
    v34 = &Srv2ZeroGuid;
    v35 = v33[9];
    v36 = (__int64 *)(v35 + 96);
    if ( !v35 )
      v36 = &Srv2ZeroGuid;
    v37 = v33[7];
    v38 = (__int64 *)(v37 + 24);
    if ( !v37 )
      v38 = &Srv2ZeroGuid;
    v39 = v33[4];
    if ( v39 )
      v34 = (__int64 *)(v39 + 72);
    v40 = *(_QWORD *)(BugCheckParameter4 + 416);
    if ( v40 )
      v41 = *(_QWORD *)(*(_QWORD *)(v40 + 560) + 176LL);
    else
      LOBYTE(v41) = -1;
    v43 = *(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 96) + 496LL) + 72LL;
    McTemplateK0xqqxxhhquuqxqbr12jjjj_EtwWriteTransfer(
      v43,
      (_DWORD)v34,
      BugCheckParameter4 + 584,
      *(_QWORD *)(v6 + 40),
      *(_DWORD *)(v6 + 32),
      *(_DWORD *)(v6 + 36),
      *(_QWORD *)(v6 + 24),
      v41,
      *(_WORD *)(v6 + 12),
      *(_WORD *)(v6 + 14),
      *(_DWORD *)(v6 + 16),
      *(_BYTE *)(v6 + 66),
      *(_BYTE *)(v6 + 67),
      *(_DWORD *)(v6 + 76),
      *(_QWORD *)(v6 + 80),
      *(_DWORD *)(v6 + 68),
      v6 + *(unsigned __int16 *)(v6 + 72),
      v43,
      (__int64)v34,
      (__int64)v38,
      (__int64)v36);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x14005b5d0  push    rbx
0x14005b5d2  push    rbp
0x14005b5d3  push    rsi
0x14005b5d4  push    rdi
0x14005b5d5  push    r12
0x14005b5d7  push    r13
0x14005b5d9  push    r14
0x14005b5db  push    r15
0x14005b5dd  sub     rsp, 0C8h
0x14005b5e4  mov     r14, [rcx+130h]
0x14005b5eb  mov     rbx, rcx
0x14005b5ee  mov     rbp, [rcx+230h]
0x14005b5f5  mov     r8d, [r14+24h]
0x14005b5f9  cmp     r8d, 61h ; 'a'
0x14005b5fd  jnb     short loc_14005B665
0x14005b5ff  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005b606  lea     rsi, WPP_GLOBAL_Control
0x14005b60d  cmp     rcx, rsi
0x14005b610  jz      short loc_14005B641
0x14005b612  test    dword ptr [rcx+2Ch], 10000000h
0x14005b619  jz      short loc_14005B641
0x14005b61b  mov     edi, 1
0x14005b620  cmp     [rcx+29h], dil
0x14005b624  jb      short loc_14005B641
0x14005b626  mov     rcx, [rcx+18h]
0x14005b62a  lea     edx, [rdi+10h]
0x14005b62d  mov     dword ptr [rsp+108h+Arg1], r8d
0x14005b632  mov     r9, rbx
0x14005b635  lea     r8, WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids
0x14005b63c  call    WPP_SF_qD
0x14005b641  mov     r9d, 1B1h
0x14005b647  lea     r8, aOnecoreBaseFsR_17; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14005b64e  mov     edx, 0C000000Dh
0x14005b653  mov     rcx, rbx
0x14005b656  call    _Smb2SetError
0x14005b65b  mov     edx, 7
0x14005b660  jmp     loc_14005BFEA
0x14005b665  mov     r14, [r14+18h]
0x14005b669  cmp     word ptr [r14+40h], 21h ; '!'
0x14005b66f  jz      short loc_14005B6D2
0x14005b671  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005b678  lea     rsi, WPP_GLOBAL_Control
0x14005b67f  cmp     rcx, rsi
0x14005b682  jz      short loc_14005B6AE
0x14005b684  test    dword ptr [rcx+2Ch], 10000000h
0x14005b68b  jz      short loc_14005B6AE
0x14005b68d  mov     edi, 1
0x14005b692  cmp     [rcx+29h], dil
0x14005b696  jb      short loc_14005B6AE
0x14005b698  mov     rcx, [rcx+18h]
0x14005b69c  lea     edx, [rdi+11h]
0x14005b69f  mov     r9, rbx
0x14005b6a2  lea     r8, WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids
0x14005b6a9  call    WPP_SF_q
0x14005b6ae  mov     r9d, 1C1h
0x14005b6b4  lea     r8, aOnecoreBaseFsR_17; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14005b6bb  mov     edx, 0C000000Dh
0x14005b6c0  mov     rcx, rbx
0x14005b6c3  call    _Smb2SetError
0x14005b6c8  mov     edx, 8
0x14005b6cd  jmp     loc_14005BFEA
0x14005b6d2  movzx   ecx, word ptr [r14+48h]
0x14005b6d7  mov     r15d, 0C000000Dh
0x14005b6dd  lea     rax, [rcx-60h]
0x14005b6e1  cmp     rax, 40h ; '@'
0x14005b6e5  ja      loc_14005BF90
0x14005b6eb  mov     r9d, [r14+44h]
0x14005b6ef  lea     rdx, [r9+rcx]
0x14005b6f3  cmp     rdx, rcx
0x14005b6f6  jb      short loc_14005B716
0x14005b6f8  mov     eax, 0FFFFFFFFh
0x14005b6fd  cmp     rdx, rax
0x14005b700  ja      short loc_14005B716
0x14005b702  cmp     rdx, r8
0x14005b705  ja      short loc_14005B716
0x14005b707  lea     eax, [rcx+r14]
0x14005b70b  and     al, 7
0x14005b70d  neg     al
0x14005b70f  sbb     eax, eax
0x14005b711  and     eax, r15d
0x14005b714  jmp     short loc_14005B719
0x14005b716  mov     eax, r15d
0x14005b719  test    eax, eax
0x14005b71b  js      loc_14005BF90
0x14005b721  mov     rax, [rbx+60h]
0x14005b725  mov     rax, [rax+1F0h]
0x14005b72c  mov     [rsp+108h+ErrorOffset], rax
0x14005b734  cmp     r9d, [rax+24h]
0x14005b738  jbe     short loc_14005B799
0x14005b73a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005b741  lea     rsi, WPP_GLOBAL_Control
0x14005b748  cmp     rcx, rsi
0x14005b74b  jz      short loc_14005B777
0x14005b74d  test    dword ptr [rcx+2Ch], 10000000h
0x14005b754  jz      short loc_14005B777
0x14005b756  mov     edi, 1
0x14005b75b  cmp     [rcx+29h], dil
0x14005b75f  jb      short loc_14005B777
0x14005b761  mov     rcx, [rcx+18h]
0x14005b765  lea     edx, [rdi+13h]
0x14005b768  mov     r9, rbx
0x14005b76b  lea     r8, WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids
0x14005b772  call    WPP_SF_q
0x14005b777  mov     r9d, 1E5h
0x14005b77d  lea     r8, aOnecoreBaseFsR_17; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14005b784  mov     edx, r15d
0x14005b787  mov     rcx, rbx
0x14005b78a  call    _Smb2SetError
0x14005b78f  mov     edx, 0Ah
0x14005b794  jmp     loc_14005BFEA
0x14005b799  lea     rax, [r14+rcx]
0x14005b79d  mov     byte ptr [rsp+108h+Arg2], 0
0x14005b7a2  mov     [rbp+0C8h], rax
0x14005b7a9  mov     edi, 1
0x14005b7ae  mov     eax, [r14+44h]
0x14005b7b2  xor     r9d, r9d
0x14005b7b5  mov     [rbp+0D0h], eax
0x14005b7bb  mov     r8, r14
0x14005b7be  mov     rdx, [r14+28h]
0x14005b7c2  mov     rcx, rbx
0x14005b7c5  mov     byte ptr [rsp+108h+Arg1], dil
0x14005b7ca  call    Smb2VerifySessionExEx
0x14005b7cf  mov     r12d, eax
0x14005b7d2  test    eax, eax
0x14005b7d4  jns     short loc_14005B82B
0x14005b7d6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005b7dd  lea     rsi, WPP_GLOBAL_Control
0x14005b7e4  cmp     rcx, rsi
0x14005b7e7  jz      short loc_14005B80E
0x14005b7e9  test    dword ptr [rcx+2Ch], 10000000h
0x14005b7f0  jz      short loc_14005B80E
0x14005b7f2  cmp     [rcx+29h], dil
0x14005b7f6  jb      short loc_14005B80E
0x14005b7f8  mov     rcx, [rcx+18h]
0x14005b7fc  lea     edx, [rdi+14h]
0x14005b7ff  mov     r9, rbx
0x14005b802  lea     r8, WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids
0x14005b809  call    WPP_SF_q
0x14005b80e  mov     r9d, 1FAh
0x14005b814  mov     edx, r12d
0x14005b817  lea     r8, aOnecoreBaseFsR_17; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14005b81e  mov     rcx, rbx
0x14005b821  call    _Smb2SetError
0x14005b826  jmp     loc_14005BFF2
0x14005b82b  movups  xmm0, xmmword ptr [r14+50h]
0x14005b830  mov     r9b, dil
0x14005b833  lea     rdx, [rsp+108h+var_58]
0x14005b83b  mov     r8, r14
0x14005b83e  mov     rcx, rbx; BugCheckParameter4
0x14005b841  movdqu  [rsp+108h+var_58], xmm0
0x14005b84a  call    Smb2VerifyFileEx
0x14005b84f  lea     rsi, WPP_GLOBAL_Control
0x14005b856  mov     r13d, eax
0x14005b859  test    eax, eax
0x14005b85b  jns     short loc_14005B899
0x14005b85d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005b864  cmp     rcx, rsi
0x14005b867  jz      short loc_14005B890
0x14005b869  test    dword ptr [rcx+2Ch], 800000h
0x14005b870  jz      short loc_14005B890
0x14005b872  cmp     [rcx+29h], dil
0x14005b876  jb      short loc_14005B890
0x14005b878  movzx   r9d, word ptr [r14+0Ch]
0x14005b87d  mov     edx, 5Bh ; '['
0x14005b882  mov     rcx, [rcx+18h]
0x14005b886  mov     [rsp+108h+Arg1], rbx
0x14005b88b  call    WPP_SF_hq
0x14005b890  cmp     r13d, 0C0000128h
0x14005b897  jnz     short loc_14005B908
0x14005b899  mov     edx, [r14+24h]
0x14005b89d  mov     r8, r14
0x14005b8a0  mov     rcx, rbx
0x14005b8a3  call    Smb2VerifyTreeConnect_Old
0x14005b8a8  mov     r12d, eax
0x14005b8ab  test    eax, eax
0x14005b8ad  jns     short loc_14005B8E4
0x14005b8af  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005b8b6  cmp     rcx, rsi
0x14005b8b9  jz      short loc_14005B910
0x14005b8bb  test    dword ptr [rcx+2Ch], 800000h
0x14005b8c2  jz      short loc_14005B910
0x14005b8c4  cmp     [rcx+29h], dil
0x14005b8c8  jb      short loc_14005B910
0x14005b8ca  movzx   r9d, word ptr [r14+0Ch]
0x14005b8cf  mov     edx, 5Ch ; '\'
0x14005b8d4  mov     rcx, [rcx+18h]
0x14005b8d8  mov     [rsp+108h+Arg1], rbx
0x14005b8dd  call    WPP_SF_hq
0x14005b8e2  jmp     short loc_14005B910
0x14005b8e4  cmp     r13d, 0C0000128h
0x14005b8eb  jnz     short loc_14005B908
0x14005b8ed  mov     rax, [rbx+230h]
0x14005b8f4  mov     rcx, [rax+38h]
0x14005b8f8  cmp     byte ptr [rcx+9Ah], 0
0x14005b8ff  jz      short loc_14005B908
0x14005b901  mov     [rbx+1DAh], dil
0x14005b908  test    r13d, r13d
0x14005b90b  jns     short loc_14005B91B
0x14005b90d  mov     r12d, r13d
0x14005b910  mov     r9d, 204h
0x14005b916  jmp     loc_14005B814
0x14005b91b  mov     rax, [rsp+108h+ErrorOffset]
0x14005b923  xor     r13d, r13d
0x14005b926  test    byte ptr [rax+31h], 2
0x14005b92a  jz      loc_14005BA60
0x14005b930  cmp     cs:Smb2SingleCreditChargePerSpecifiedRequest, r13b
0x14005b937  mov     r8d, [r14+44h]
0x14005b93b  jz      loc_14005B9F7
0x14005b941  cmp     r8d, 11000h
0x14005b948  jbe     short loc_14005B98C
0x14005b94a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005b951  cmp     rcx, rsi
0x14005b954  jz      short loc_14005B981
0x14005b956  test    dword ptr [rcx+2Ch], 10000000h
0x14005b95d  jz      short loc_14005B981
0x14005b95f  cmp     [rcx+29h], dil
0x14005b963  jb      short loc_14005B981
0x14005b965  mov     rcx, [rcx+18h]
0x14005b969  lea     edx, [r13+16h]
0x14005b96d  mov     dword ptr [rsp+108h+Arg1], r8d
0x14005b972  mov     r9, rbx
0x14005b975  lea     r8, WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids
0x14005b97c  call    WPP_SF_qD
0x14005b981  mov     r9d, 219h
0x14005b987  jmp     loc_14005B77D
0x14005b98c  movzx   edx, word ptr [rbx+1E8h]
0x14005b993  cmp     dx, di
0x14005b996  jz      loc_14005BA60
0x14005b99c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005b9a3  cmp     rcx, rsi
0x14005b9a6  jz      short loc_14005B9D5
0x14005b9a8  test    dword ptr [rcx+2Ch], 10000000h
0x14005b9af  jz      short loc_14005B9D5
0x14005b9b1  cmp     [rcx+29h], dil
0x14005b9b5  jb      short loc_14005B9D5
0x14005b9b7  mov     rcx, [rcx+18h]
0x14005b9bb  lea     r8, WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids
0x14005b9c2  mov     eax, edx
0x14005b9c4  mov     r9, rbx
0x14005b9c7  mov     edx, 17h
0x14005b9cc  mov     dword ptr [rsp+108h+Arg1], eax
0x14005b9d0  call    WPP_SF_qD
0x14005b9d5  mov     r9d, 225h
0x14005b9db  lea     r8, aOnecoreBaseFsR_17; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14005b9e2  mov     edx, r15d
0x14005b9e5  mov     rcx, rbx
0x14005b9e8  call    _Smb2SetError
0x14005b9ed  mov     edx, 0Bh
0x14005b9f2  jmp     loc_14005BFEA
0x14005b9f7  test    r8d, r8d
0x14005b9fa  jz      short loc_14005BA08
0x14005b9fc  dec     r8d
0x14005b9ff  shr     r8d, 10h
0x14005ba03  add     r8d, edi
0x14005ba06  jmp     short loc_14005BA0B
0x14005ba08  mov     r8d, edi
0x14005ba0b  movzx   r9d, word ptr [rbx+1E8h]
0x14005ba13  cmp     r9d, r8d
0x14005ba16  jnb     short loc_14005BA60
0x14005ba18  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005ba1f  cmp     rcx, rsi
0x14005ba22  jz      short loc_14005BA55
0x14005ba24  test    dword ptr [rcx+2Ch], 10000000h
0x14005ba2b  jz      short loc_14005BA55
0x14005ba2d  cmp     [rcx+29h], dil
0x14005ba31  jb      short loc_14005BA55
0x14005ba33  mov     rcx, [rcx+18h]
0x14005ba37  mov     edx, 18h
0x14005ba3c  mov     dword ptr [rsp+108h+Arg2], r8d
0x14005ba41  lea     r8, WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids
0x14005ba48  mov     dword ptr [rsp+108h+Arg1], r9d
0x14005ba4d  mov     r9, rbx
0x14005ba50  call    WPP_SF_qDD
0x14005ba55  mov     r9d, 236h
0x14005ba5b  jmp     loc_14005B9DB
0x14005ba60  mov     al, [r14+42h]
0x14005ba64  mov     [rbp+0C0h], al
0x14005ba6a  movzx   ecx, byte ptr [r14+42h]
0x14005ba6f  sub     ecx, edi
0x14005ba71  jz      loc_14005BD5F
0x14005ba77  sub     ecx, edi
0x14005ba79  jz      loc_14005BC54
0x14005ba7f  sub     ecx, edi
0x14005ba81  jz      loc_14005BB55
0x14005ba87  cmp     ecx, edi
0x14005ba89  jz      short loc_14005BACC
0x14005ba8b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005ba92  cmp     rcx, rsi
0x14005ba95  jz      short loc_14005BABE
0x14005ba97  test    dword ptr [rcx+2Ch], 10000000h
0x14005ba9e  jz      short loc_14005BABE
0x14005baa0  cmp     [rcx+29h], dil
0x14005baa4  jb      short loc_14005BABE
0x14005baa6  mov     rcx, [rcx+18h]
0x14005baaa  lea     r8, WPP_9c7b55fd885f3fb2171337ca5db22ce2_Traceguids
0x14005bab1  mov     edx, 20h ; ' '
0x14005bab6  mov     r9, rbx
0x14005bab9  call    WPP_SF_q
0x14005babe  mov     r9d, 2E6h
0x14005bac4  mov     edx, r15d
  ... truncated ...
```
