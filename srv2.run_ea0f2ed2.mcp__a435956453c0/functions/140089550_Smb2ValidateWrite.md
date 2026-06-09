# Smb2ValidateWrite

- ea: `0x140089550`
- end: `0x14008b200`
- name: `Smb2ValidateWrite`
- size: `7344`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter4)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140073ab0`

## callees

- `0x140003a04`
- `0x140007400`
- `0x14001c8ec`
- `0x14001cef0`
- `0x14001d664`
- `0x14002019c`
- `0x1400222ec`
- `0x140022958`
- `0x1400229ac`
- `0x14002ad2c`
- `0x14002b11c`
- `0x14005c600`
- `0x140089550`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14008a048`
- `ntoskrnl!ExAllocatePool2` at `0x14008a048`
- `ntoskrnl!IoSizeOfIrpEx` at `0x140089c03`
- `ntoskrnl!IoSizeOfIrpEx` at `0x140089d1e`
- `ntoskrnl!IoSizeOfIrpEx` at `0x14008a0e4`
- `ntoskrnl!IoSizeOfIrpEx` at `0x14008a120`
- `ntoskrnl!IoSizeOfIrpEx` at `0x140089c03`
- `ntoskrnl!IoSizeOfIrpEx` at `0x140089d1e`
- `ntoskrnl!IoSizeOfIrpEx` at `0x14008a0e4`
- `ntoskrnl!IoSizeOfIrpEx` at `0x14008a120`
- `ntoskrnl!IoInitializeIrpEx` at `0x14008a13a`
- `ntoskrnl!IoInitializeIrpEx` at `0x14008a13a`
- `srvnet!SrvNetIsRdmaConnection` at `0x140089b80`
- `srvnet!SrvNetIsRdmaConnection` at `0x14008afb8`
- `srvnet!SrvNetIsRdmaConnection` at `0x140089b80`
- `srvnet!SrvNetIsRdmaConnection` at `0x14008afb8`
- `srvnet!SrvNetValidateMrToken` at `0x14008ab21`
- `srvnet!SrvNetValidateMrToken` at `0x14008ab21`

## string_xrefs

- `0x1400895cd`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008964a`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x1400896f4`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x140089807`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x1400898ae`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x1400898cf`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008996b`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x1400899d8`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x140089a45`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x140089adc`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x140089b57`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x140089bc9`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x140089d99`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x140089def`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x140089e45`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x140089ea3`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x140089f46`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x140089fa4`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008a007`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008a09d`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008a21e`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008a30c`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008a370`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008a3ed`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008a513`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008a674`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008a6ca`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008a733`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008a791`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008a7f7`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008a85a`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008a8b8`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008a911`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008a96f`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008a9cd`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008aaac`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008ab71`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008ac0c`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008acee`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008ad7f`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008b032`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008b090`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008b0ee`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008b14c`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14008b1a7`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`

## pseudocode

```c
__int64 __fastcall Smb2ValidateWrite(_QWORD *BugCheckParameter4)
{
  __int64 v1; // r13
  ULONG_PTR v2; // r15
  __int64 v3; // rbx
  unsigned int v4; // r8d
  __int64 v6; // r13
  __int64 v7; // r14
  __int64 v8; // rsi
  int v9; // edi
  int v10; // edi
  __int64 v11; // r8
  int v12; // ebp
  __int64 v13; // r8
  __int64 v14; // rcx
  char v15; // dl
  char v16; // dl
  int v17; // ecx
  __int64 v18; // rax
  int v19; // ecx
  char v20; // r12
  __int64 v21; // rdx
  char v22; // al
  unsigned int v23; // r8d
  char *v24; // rcx
  int v25; // r10d
  unsigned int v26; // r11d
  __int64 v27; // rdi
  unsigned int v28; // ebp
  unsigned int v29; // r8d
  __int64 i; // rcx
  __int64 v31; // rcx
  unsigned __int64 v32; // r8
  __int64 v33; // r8
  __int64 v34; // rax
  __int64 v35; // r9
  unsigned int v36; // eax
  __int64 Pool2; // rax
  __int64 v38; // r15
  __int64 v39; // r14
  unsigned __int64 v40; // rdi
  unsigned __int16 v41; // ax
  __int64 v42; // rbp
  unsigned __int64 v43; // rax
  __int64 v44; // rsi
  unsigned __int8 v45; // di
  unsigned __int16 v46; // ax
  __int64 v47; // rdx
  __int64 v48; // rcx
  unsigned __int64 v49; // rcx
  __int64 v50; // r9
  __int64 v51; // rdx
  int v52; // eax
  int v53; // eax
  unsigned __int16 *v54; // r9
  int v55; // eax
  char *v56; // rcx
  unsigned __int64 v57; // r10
  __int64 v58; // rdx
  unsigned __int64 v59; // rcx
  unsigned __int64 v60; // rax
  unsigned __int64 v61; // rdx
  int v62; // eax
  unsigned __int64 v63; // rax
  unsigned int v64; // eax
  int v65; // ecx
  __int64 v66; // rdx
  unsigned __int64 v67; // rcx
  unsigned __int64 v68; // rdx
  unsigned __int64 v69; // r8
  unsigned __int64 v70; // r11
  unsigned __int64 v71; // r10
  unsigned __int64 v72; // r8
  signed int v73; // r8d
  bool v74; // zf
  __int64 v75; // r8
  unsigned __int64 v76; // rax
  __int64 v77; // rax
  unsigned int v78; // r8d
  char v79; // dl
  int v80; // r8d
  char v81; // al
  char v82; // dl
  char v83; // al
  _QWORD *v84; // rax
  __int64 *v85; // rdx
  __int64 v86; // rcx
  __int64 *v87; // r10
  __int64 v88; // rcx
  __int64 *v89; // r9
  __int64 v90; // rcx
  __int64 v91; // rax
  __int64 v92; // r11
  __int64 v93; // [rsp+98h] [rbp-B0h]
  unsigned int v94; // [rsp+C4h] [rbp-84h]
  char *v95; // [rsp+C8h] [rbp-80h]
  __int64 v96; // [rsp+D0h] [rbp-78h]
  __int64 v97; // [rsp+E0h] [rbp-68h]
  unsigned __int64 v98; // [rsp+E0h] [rbp-68h]
  __int64 v99; // [rsp+F0h] [rbp-58h]
  int v101; // [rsp+150h] [rbp+8h]
  unsigned int v102; // [rsp+150h] [rbp+8h]
  int v103; // [rsp+158h] [rbp+10h]
  int v104; // [rsp+158h] [rbp+10h]
  unsigned int v105; // [rsp+160h] [rbp+18h]
  __int64 v106; // [rsp+160h] [rbp+18h]
  int v107; // [rsp+160h] [rbp+18h]
  unsigned int v108; // [rsp+168h] [rbp+20h]

  v1 = BugCheckParameter4[38];
  v2 = (ULONG_PTR)BugCheckParameter4;
  v3 = BugCheckParameter4[70];
  v96 = 0;
  v4 = *(_DWORD *)(v1 + 36);
  if ( v4 < 0x70 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
          BugCheckParameter4,
          v4);
    }
    Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 567);
    Smb2LkmdTelCollectParsingFailureWriteHelper(v3, 0);
    return 0;
  }
  v6 = *(_QWORD *)(v1 + 24);
  v7 = v6 + 64;
  if ( *(_WORD *)(v6 + 64) != 49 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
        BugCheckParameter4);
    }
    Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 583);
    Smb2LkmdTelCollectParsingFailureWriteHelper(v3, 1);
    return 0;
  }
  v8 = *(_QWORD *)(BugCheckParameter4[12] + 496LL);
  v99 = v8;
  v9 = Smb2VerifySessionExEx((_DWORD)BugCheckParameter4, *(_QWORD *)(v6 + 40), v6, 0, 1, 0);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 13, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, v2);
    }
    Smb2SetError(v2, (unsigned int)v9, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 598);
    return 0;
  }
  v10 = Smb2VerifyFileEx(v2);
  if ( v10 >= 0 )
    goto LABEL_25;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_hq(WPP_GLOBAL_Control->AttachedDevice, 91, v11, *(unsigned __int16 *)(v6 + 12), v2);
  }
  if ( v10 == -1073741528 )
  {
LABEL_25:
    v12 = Smb2VerifyTreeConnect_Old(v2, *(unsigned int *)(v6 + 36), v6);
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_hq(WPP_GLOBAL_Control->AttachedDevice, 92, v13, *(unsigned __int16 *)(v6 + 12), v2);
      }
      goto LABEL_35;
    }
    if ( v10 == -1073741528 && *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v2 + 560) + 56LL) + 154LL) )
      *(_BYTE *)(v2 + 474) = 1;
  }
  if ( v10 < 0 )
  {
    v12 = v10;
LABEL_35:
    Smb2SetError(v2, (unsigned int)v12, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 611);
    return 0;
  }
  v14 = *(_QWORD *)(v3 + 56);
  v15 = 0;
  if ( *(_DWORD *)(v14 + 76) == 1 )
    v15 = 8;
  v16 = *(_BYTE *)(v3 + 280) & 0xF7 | v15;
  *(_BYTE *)(v3 + 280) = v16;
  if ( *(_QWORD *)(*(_QWORD *)(v14 + 96) + 392LL) )
  {
    if ( *(_WORD *)(v8 + 44) >= 0x300u )
    {
      Smb2SetError(v2, 3221226624LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 632);
      return 0;
    }
    v16 |= 4u;
    *(_BYTE *)(v3 + 280) = v16;
  }
  v17 = *(_DWORD *)(*(_QWORD *)(v3 + 72) + 224LL);
  if ( (v17 & 2) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 14, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, v2);
    }
    Smb2SetError(v2, 3221225506LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 646);
    return 0;
  }
  v18 = *(_QWORD *)(v3 + 88);
  *(_BYTE *)(v3 + 280) = v16 ^ (v16 ^ (16 * BYTE1(v17))) & 0x10;
  v19 = *(_DWORD *)(v6 + 108) & *(_DWORD *)(v8 + 40);
  v20 = (*(_DWORD *)(v18 + 80) & 8) != 0;
  *(_DWORD *)(v6 + 108) = v19;
  if ( (*(_BYTE *)(v3 + 280) & 8) != 0 )
  {
    if ( (v19 & 7) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 15, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, v2);
      }
      Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 681);
      v21 = 3;
LABEL_388:
      Smb2LkmdTelCollectParsingFailureWriteHelper(v3, v21);
      return 0;
    }
  }
  else
  {
    v22 = v20 | ((v19 & 2) != 0);
    v20 = v22;
    if ( (v19 & 1) != 0 && !v22 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, v2);
      }
      Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 700);
      v21 = 4;
      goto LABEL_388;
    }
  }
  if ( *(_WORD *)(v8 + 44) < 0x300u )
  {
    *(_DWORD *)(v6 + 96) = 0;
  }
  else
  {
    v23 = *(_DWORD *)(v6 + 96);
    if ( v23 > *(_DWORD *)(v8 + 32) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 17, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, v2, v23);
      }
      Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 720);
      v21 = 5;
      goto LABEL_388;
    }
  }
  v24 = 0;
  v25 = 0;
  v26 = 1;
  v95 = 0;
  *(_DWORD *)(v3 + 272) = 1;
  v103 = 0;
  if ( (unsigned int)(*(_DWORD *)(v6 + 96) - 1) <= 2 )
  {
    if ( (unsigned __int8)SrvNetIsRdmaConnection(*(_QWORD *)(*(_QWORD *)(v2 + 96) + 480LL)) )
    {
      v27 = *(unsigned int *)(v6 + 100);
      v28 = *(_DWORD *)(v6 + 100);
      v94 = v28;
      v108 = v28;
      v29 = (unsigned __int16)IoSizeOfIrpEx(*(_QWORD *)(v3 + 96), *(unsigned __int8 *)(*(_QWORD *)(v3 + 96) + 76LL))
          + 48
          + 8 * ((unsigned __int64)(v27 + 8190) >> 12);
      for ( i = v6 + 64; ; i = v97 )
      {
        v105 = v29;
        if ( (*(_BYTE *)(i + 44) & 4) == 0 )
          break;
        ++*(_DWORD *)(v3 + 272);
        v31 = i + 48;
        v97 = v31;
        v32 = *(unsigned int *)(*(_QWORD *)(v2 + 304) + 36LL);
        if ( v31 - v7 + 112 > v32 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 19, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, v2, v32);
          }
          Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 783);
          v21 = 0;
          goto LABEL_388;
        }
        if ( *(_WORD *)v31 != 49 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 20, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, v2);
          }
          Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 797);
          v21 = 1;
          goto LABEL_388;
        }
        v33 = *(unsigned int *)(v31 + 36);
        if ( !(_DWORD)v33 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, v2);
          }
          Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 812);
          v21 = 7;
          goto LABEL_388;
        }
        if ( *(_WORD *)(v31 + 2) || *(_DWORD *)(v31 + 4) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 22, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, v2);
          }
          v35 = 828;
LABEL_387:
          Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", v35);
          v21 = 8;
          goto LABEL_388;
        }
        if ( *(_WORD *)(v31 + 40) || *(_WORD *)(v31 + 42) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 23, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, v2);
          }
          Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 844);
          v21 = 9;
          goto LABEL_388;
        }
        v34 = *(_QWORD *)(v31 + 8);
        if ( v34 < 0 || v34 + v33 < (unsigned __int64)v34 || (unsigned __int64)(v34 + v33) > 0x7FFFFFFFFFFFFFFFLL )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids);
          }
          Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 856);
          v21 = 26;
          goto LABEL_388;
        }
        if ( *(_QWORD *)(v31 + 16) != *(_QWORD *)(v6 + 80) || *(_QWORD *)(v31 + 24) != *(_QWORD *)(v6 + 88) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids);
          }
          Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 868);
          return 0;
        }
        *(_DWORD *)(v31 + 44) &= *(_DWORD *)(v8 + 40);
        if ( (*(_DWORD *)(v31 + 44) | 4) != *(_DWORD *)(v6 + 108) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids);
          }
          Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 882);
          return 0;
        }
        v28 += v33;
        v108 = v28;
        v29 = v105
            + (unsigned __int16)IoSizeOfIrpEx(*(_QWORD *)(v3 + 96), *(unsigned __int8 *)(*(_QWORD *)(v3 + 96) + 76LL))
            + 8 * ((((unsigned __int64)(unsigned int)v33 + 8190) >> 12) + 6);
      }
      v36 = *(_DWORD *)(v3 + 272);
      if ( v36 != 1 )
      {
        Pool2 = ExAllocatePool2(64, v29 + 32LL * v36, 607277900);
        *(_QWORD *)(v3 + 240) = Pool2;
        if ( !Pool2 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids);
          }
          Smb2SetError(v2, 3221225989LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 903);
          return 0;
        }
        v38 = v6 + 64;
        v39 = Pool2;
        v40 = Pool2 + 32LL * *(unsigned int *)(v3 + 272);
        do
        {
          *(_QWORD *)(v39 + 16) = *(_QWORD *)(v38 + 8);
          *(_DWORD *)(v39 + 24) = *(_DWORD *)(v38 + 36);
          *(_QWORD *)v39 = v40;
          v41 = IoSizeOfIrpEx(*(_QWORD *)(v3 + 96), *(unsigned __int8 *)(*(_QWORD *)(v3 + 96) + 76LL));
          v42 = *(_QWORD *)v39;
          v43 = v40 + v41;
          *(_QWORD *)(v39 + 8) = v43;
          v98 = v43;
          v44 = *(_QWORD *)(v3 + 96);
          v106 = *(unsigned int *)(v38 + 36);
          v45 = *(_BYTE *)(v44 + 76);
          v46 = IoSizeOfIrpEx(v44, v45);
          IoInitializeIrpEx(v42, v44, v46, v45);
          v47 = *(unsigned int *)(v38 + 36);
          v48 = *(_QWORD *)(v39 + 8);
          *(_QWORD *)v48 = 0;
          *(_WORD *)(v48 + 8) = 8 * (((unsigned __int64)(v47 + 8190) >> 12) + 6);
          *(_WORD *)(v48 + 10) = 0;
          *(_QWORD *)(v48 + 32) = 0;
          *(_DWORD *)(v48 + 44) = 4095;
          *(_DWORD *)(v48 + 40) = v47;
          if ( (*(_BYTE *)(v38 + 44) & 4) == 0 )
            break;
          v39 += 32;
          v40 = v98 + 48 + 8 * ((unsigned __int64)(v106 + 8190) >> 12);
          v38 += 48;
        }
        while ( v38 );
        v2 = (ULONG_PTR)BugCheckParameter4;
        v7 = v6 + 64;
        v8 = v99;
        LODWORD(v27) = v94;
        v28 = v108;
      }
      if ( (_DWORD)v27 )
      {
        if ( *(_WORD *)(v7 + 2) || *(_DWORD *)(v7 + 4) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 29, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, v2);
          }
          v35 = 965;
          goto LABEL_387;
        }
        v49 = *(unsigned __int16 *)(v7 + 40);
        if ( (_WORD)v49 && (v50 = *(unsigned __int16 *)(v7 + 42), (_WORD)v50) )
        {
          v51 = *(unsigned __int16 *)(v7 + 40);
          if ( v49 - 112 > 0x4000
            || (v49 + v50 < v49
             || v49 + v50 > *(unsigned int *)(*(_QWORD *)(v2 + 304) + 36LL)
             || (((_BYTE)v51 + (_BYTE)v6) & 7) != 0
              ? (v52 = -1073741811)
              : (v52 = 0),
                v52 < 0) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 31, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, v2);
            }
            Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 1006);
            v21 = 10;
          }
          else if ( *(_DWORD *)(v7 + 32) == 3 )
          {
            v53 = *(_DWORD *)(v8 + 156);
            if ( (v53 & 1) != 0 || (v53 & 2) != 0 )
            {
              if ( (unsigned int)v50 >= 0x10 )
              {
                v54 = (unsigned __int16 *)(v51 + v6);
                v55 = 0;
                v96 = v51 + v6;
                if ( *(_WORD *)(v51 + v6 + 8) )
                {
                  v56 = 0;
                  v57 = ((unsigned __int64)v54 + 23) & 0xFFFFFFFFFFFFFFF8uLL;
                  v58 = 0;
                  while ( 1 )
                  {
                    v107 = v55;
                    if ( (unsigned __int16)v55 >= v54[4] )
                      break;
                    v59 = (unsigned int)(v57 - (_DWORD)v54);
                    v60 = v59 + 2;
                    if ( v59 + 2 < v59
                      || v60 > 0xFFFFFFFF
                      || (v61 = *(unsigned __int16 *)(v7 + 42), v60 > v61)
                      || (((_BYTE)v59 + (_BYTE)v54) & 7) != 0 )
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) )
                      {
                        WPP_SF_q(
                          WPP_GLOBAL_Control->AttachedDevice,
                          35,
                          &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
                          v2);
                      }
                      Smb2SetError(
                        v2,
                        3221225485LL,
                        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c",
                        1092);
                      v21 = 14;
                      goto LABEL_388;
                    }
                    v101 = *(unsigned __int16 *)v57;
                    if ( v101 != 1 && v101 != 2 )
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) )
                      {
                        WPP_SF_q(
                          WPP_GLOBAL_Control->AttachedDevice,
                          45,
                          &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
                          v2);
                      }
                      Smb2SetError(v2, 0, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 1271);
                      return 0;
                    }
                    v62 = *(_DWORD *)(v3 + 268);
                    v104 = v62;
                    if ( (v62 & 1) != 0 || (v62 & 2) != 0 )
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) )
                      {
                        WPP_SF_q(
                          WPP_GLOBAL_Control->AttachedDevice,
                          36,
                          &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
                          v2);
                      }
                      Smb2SetError(
                        v2,
                        3221225485LL,
                        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c",
                        1115);
                      v21 = 15;
                      goto LABEL_388;
                    }
                    if ( (_WORD)v101 == 1 )
                    {
                      if ( (*(_DWORD *)(v2 + 484) & 0x1000) == 0 )
                      {
                        if ( (*(_DWORD *)(v8 + 156) & 1) != 0 )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) )
                          {
                            WPP_SF_q(
                              WPP_GLOBAL_Control->AttachedDevice,
                              38,
                              &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
                              v2);
                          }
                          Smb2SetError(
                            v2,
                            3221225485LL,
                            "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c",
                            1145);
                          v21 = 17;
                        }
                        else
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) )
                          {
                            WPP_SF_q(
                              WPP_GLOBAL_Control->AttachedDevice,
                              37,
                              &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
                              v2);
                          }
                          Smb2SetError(
                            v2,
                            3221225485LL,
                            "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c",
                            1134);
                          v21 = 16;
                        }
                        goto LABEL_388;
                      }
                    }
                    else if ( (_WORD)v101 == 2 && (*(_BYTE *)(v6 + 16) & 8) == 0 )
                    {
                      if ( (*(_DWORD *)(v8 + 156) & 2) != 0 )
                      {
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                          && BYTE1(WPP_GLOBAL_Control->Timer) )
                        {
                          WPP_SF_q(
                            WPP_GLOBAL_Control->AttachedDevice,
                            40,
                            &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
                            v2);
                        }
                        Smb2SetError(
                          v2,
                          3221225485LL,
                          "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c",
                          1173);
                        v21 = 19;
                      }
                      else
                      {
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                          && BYTE1(WPP_GLOBAL_Control->Timer) )
                        {
                          WPP_SF_q(
                            WPP_GLOBAL_Control->AttachedDevice,
                            39,
                            &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
                            v2);
                        }
                        Smb2SetError(
                          v2,
                          3221225485LL,
                          "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c",
                          1162);
                        v21 = 18;
                      }
                      goto LABEL_388;
                    }
                    v63 = v59 + 8;
                    if ( v59 + 8 < v59 || v63 > 0xFFFFFFFF || v63 > v61 )
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) )
                      {
                        WPP_SF_q(
                          WPP_GLOBAL_Control->AttachedDevice,
                          41,
                          &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
                          v2);
                      }
                      Smb2SetError(
                        v2,
                        3221225485LL,
                        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c",
                        1193);
                      v21 = 20;
                      goto LABEL_388;
                    }
                    v64 = *(unsigned __int16 *)(v57 + 2) + 8;
                    v65 = *(unsigned __int16 *)(v57 + 4);
                    v66 = v65 + v64;
                    if ( (unsigned int)v66 < v64 )
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) )
                      {
                        WPP_SF_qD(
                          WPP_GLOBAL_Control->AttachedDevice,
                          43,
                          &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
                          v2,
                          v65);
                      }
                      Smb2SetError(
                        v2,
                        3221225621LL,
                        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c",
                        1233);
                      return 0;
                    }
                    v67 = (unsigned int)(v57 - (_DWORD)v54);
                    v68 = v67 + v66;
                    if ( v68 < v67 || v68 > 0xFFFFFFFF || v68 > *(unsigned __int16 *)(v7 + 42) || (v57 & 7) != 0 )
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) )
                      {
                        WPP_SF_qD(
                          WPP_GLOBAL_Control->AttachedDevice,
                          44,
                          &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
                          v2,
                          -1073741811);
                      }
                      Smb2SetError(
                        v2,
                        3221225485LL,
                        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c",
                        1252);
                      v21 = 21;
                      goto LABEL_388;
                    }
                    if ( (v101 & v104) == 0 )
                      *(_DWORD *)(v3 + 268) = v104 | (1 << (v101 - 1));
                    HIWORD(v55) = HIWORD(v107);
                    *(_QWORD *)(v3 + 224) = v57;
                    v57 += ((*(unsigned __int16 *)(v57 + 4) + 7LL + *(unsigned __int16 *)(v57 + 2))
                          & 0xFFFFFFFFFFFFFFF8uLL)
                         + 8;
                    v56 = (char *)v54 + *v54;
                    v58 = v54[1];
                    LOWORD(v55) = v107 + 1;
                    v103 = v54[1];
                    v95 = v56;
                  }
                  v69 = (unsigned int)(v57 - (_DWORD)v54);
                  v70 = v69 + (unsigned int)((_DWORD)v54 - v57 + 0x4000);
                  if ( v70 < v69 || (v71 = *v54, v71 < v69) || v71 > v70 )
                  {
                    v73 = -1073741811;
                    v102 = -1073741811;
                  }
                  else
                  {
                    v72 = v71 + v54[1];
                    if ( v72 < v71 || v72 > *(unsigned __int16 *)(v7 + 42) )
                      v73 = -1073741811;
                    else
                      v73 = (((_BYTE)v71 + (_BYTE)v54) & 7) != 0 ? 0xC000000D : 0;
                    v102 = v73;
                    if ( v73 >= 0 )
                      goto LABEL_294;
                  }
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) )
                  {
                    WPP_SF_qD(
                      WPP_GLOBAL_Control->AttachedDevice,
                      46,
                      &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
                      v2,
                      v73);
                  }
                  Smb2SetError(v2, v102, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 1302);
                  v21 = 22;
                }
                else
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) )
                  {
                    WPP_SF_qD(
                      WPP_GLOBAL_Control->AttachedDevice,
                      34,
                      &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
                      v2,
                      *(_DWORD *)(v3 + 268));
                  }
                  Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 1061);
                  v21 = 13;
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) )
                {
                  WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 33, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, v2);
                }
                Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 1042);
                v21 = 12;
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 32, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, v2);
              }
              Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 1028);
              v21 = 11;
            }
          }
          else if ( (Smb2DirectDataPlacementSecurity == 1
                  || Smb2DirectDataPlacementSecurity == 2 && !*(_BYTE *)(*(_QWORD *)(v3 + 56) + 92LL))
                 && ((*(_DWORD *)(v2 + 484) & 0x1000) != 0 || (*(_BYTE *)(v6 + 16) & 8) != 0) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 47, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, v2);
            }
            Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 1326);
            v21 = 13;
          }
          else
          {
            v56 = (char *)(v51 + v6);
            v58 = *(unsigned __int16 *)(v7 + 42);
            v103 = *(unsigned __int16 *)(v7 + 42);
            v95 = v56;
LABEL_294:
            if ( (int)SrvNetValidateMrToken(v56, v58, v28, v2 + 552) >= 0 )
            {
              if ( v96 )
                v74 = *(_DWORD *)(v96 + 4) == 2;
              else
                v74 = *(_DWORD *)(v7 + 32) == 2;
              v24 = v95;
              v25 = v103;
              v26 = 1;
              *(_BYTE *)(v2 + 556) = v74;
              goto LABEL_304;
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 48, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, v2);
            }
            Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 1346);
            v21 = 23;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 30, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, v2);
          }
          Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 981);
          v21 = 9;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 28, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, v2);
        }
        Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 949);
        v21 = 7;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, v2);
      }
      Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 754);
      v21 = 6;
    }
    goto LABEL_388;
  }
  if ( (*(_BYTE *)(v6 + 108) & 4) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 49, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, v2);
    }
    Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 1378);
    return 0;
  }
  LODWORD(v27) = *(_DWORD *)(v6 + 68);
  if ( !(_DWORD)v27 )
    *(_WORD *)(v6 + 66) = 112;
  if ( (unsigned __int16)(*(_WORD *)(v6 + 66) - 112) > 0x3F90u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 50, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, v2);
    }
    Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 1415);
    v21 = 24;
    goto LABEL_388;
  }
  v28 = v27;
LABEL_304:
  if ( v28 > *(_DWORD *)(v8 + 36) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 51, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, v2);
    }
    Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 1430);
    v21 = 25;
    goto LABEL_388;
  }
  v75 = *(_QWORD *)(v7 + 8);
  if ( v75 < 0 || (v76 = (unsigned int)v27 + v75, v76 < v75) || v76 > 0x7FFFFFFFFFFFFFFFLL )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids);
    }
    Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 1442);
    v21 = 26;
    goto LABEL_388;
  }
  if ( v20 )
  {
    v77 = *(unsigned __int16 *)(*(_QWORD *)(v3 + 72) + 196LL);
    if ( (_WORD)v77 )
    {
      if ( ((v77 - 1) & v75) != 0 || (((_DWORD)v77 - 1) & (unsigned int)v27) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qiiD(
            WPP_GLOBAL_Control->AttachedDevice,
            53,
            &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
            v2,
            v75,
            (unsigned int)v27,
            (unsigned __int16)v77);
        }
        Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 1470);
        return 0;
      }
      v24 = v95;
    }
  }
  if ( (*(_BYTE *)(v8 + 49) & 2) != 0 )
  {
    if ( v28 )
      v26 = ((v28 - 1) >> 16) + 1;
    v78 = *(unsigned __int16 *)(v2 + 488);
    if ( v78 < v26 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qDD(
          WPP_GLOBAL_Control->AttachedDevice,
          54,
          &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
          v2,
          v78,
          v26);
      }
      Smb2SetError(v2, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", 1493);
      v21 = 28;
      goto LABEL_388;
    }
  }
  v79 = *(_BYTE *)(v3 + 280);
  if ( !v20 )
  {
    if ( (v79 & 0x10) == 0 )
    {
      v80 = *(_DWORD *)(*(_QWORD *)(v3 + 56) + 84LL);
      if ( (v80 & 0x4000000) == 0 && (v80 & 0x1000000) == 0 )
      {
        if ( (*(_DWORD *)(*(_QWORD *)(v3 + 72) + 224LL) & 0x200) != 0
          || (*(_DWORD *)(*(_QWORD *)(v3 + 88) + 80LL) & 0x40) == 0
          || *(_DWORD *)(v7 + 32) == 3 )
        {
          v24 = v95;
        }
        else
        {
          v24 = v95;
          if ( (_DWORD)v27 == v28 )
          {
            v81 = 0;
LABEL_342:
            v79 = v81 | v79 & 0x7F;
            *(_BYTE *)(v3 + 280) = v79;
            goto LABEL_343;
          }
        }
      }
    }
    v81 = 0x80;
    goto LABEL_342;
  }
LABEL_343:
  if ( Smb2ForceMdlWrite && *(_BYTE *)(*(_QWORD *)(v3 + 56) + 92LL) )
  {
    v20 = 0;
    v79 &= ~0x80u;
  }
  v82 = (v20 << 6) | v79 & 0xBF;
  *(_BYTE *)(v3 + 280) = v82;
  v83 = *(_BYTE *)(v7 + 44) & 1;
  *(_DWORD *)(v3 + 248) = v27;
  *(_DWORD *)(v3 + 252) = v28;
  *(_BYTE *)(v3 + 280) = v82 & 0xDF | (32 * v83);
  *(_QWORD *)(v3 + 192) = *(_QWORD *)(v7 + 8);
  *(_QWORD *)(v3 + 216) = v24;
  *(_DWORD *)(v3 + 264) = v25;
  *(_QWORD *)(v3 + 200) = 0;
  if ( (Microsoft_Windows_SMBServerEnableBits & 1) != 0 )
  {
    v84 = *(_QWORD **)(v2 + 560);
    v85 = &Srv2ZeroGuid;
    v86 = v84[9];
    v87 = (__int64 *)(v86 + 96);
    if ( !v86 )
      v87 = &Srv2ZeroGuid;
    v88 = v84[7];
    v89 = (__int64 *)(v88 + 24);
    if ( !v88 )
      v89 = &Srv2ZeroGuid;
    v90 = v84[4];
    if ( v90 )
      v85 = (__int64 *)(v90 + 72);
    v91 = *(_QWORD *)(v2 + 416);
    if ( v91 )
      v92 = *(_QWORD *)(*(_QWORD *)(v91 + 560) + 176LL);
    else
      LOBYTE(v92) = -1;
    v93 = *(_QWORD *)(*(_QWORD *)(v2 + 96) + 496LL) + 72LL;
    McTemplateK0xqqxxhhqqxxqqhhqjjjj_EtwWriteTransfer(
      v93,
      (_DWORD)v85,
      v2 + 584,
      *(_QWORD *)(v6 + 40),
      *(_DWORD *)(v6 + 32),
      *(_DWORD *)(v6 + 36),
      *(_QWORD *)(v6 + 24),
      v92,
      *(_WORD *)(v6 + 12),
      *(_WORD *)(v6 + 14),
      *(_DWORD *)(v6 + 16),
      *(_DWORD *)(v7 + 4),
      *(_QWORD *)(v7 + 8),
      *(_QWORD *)(v7 + 16),
      *(_DWORD *)(v7 + 32),
      *(_DWORD *)(v7 + 36),
      *(_WORD *)(v7 + 40),
      *(_WORD *)(v7 + 42),
      *(_DWORD *)(v7 + 44),
      v93,
      (__int64)v85,
      (__int64)v89,
      (__int64)v87);
  }
  if ( (unsigned __int8)SrvNetIsRdmaConnection(*(_QWORD *)(*(_QWORD *)(v2 + 96) + 480LL))
    && (*(_BYTE *)(v3 + 280) & 8) == 0
    && (*(_DWORD *)(*(_QWORD *)(v3 + 72) + 224LL) & 0x40) == 0 )
  {
    *(_BYTE *)(v3 + 7) = 1;
    _InterlockedIncrement((volatile signed __int32 *)(v8 + 196));
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x140089550  mov     [rsp+arg_0], rcx
0x140089555  push    rbx
0x140089556  push    r13
0x140089558  push    r15
0x14008955a  sub     rsp, 130h
0x140089561  mov     r13, [rcx+130h]
0x140089568  mov     r15, rcx
0x14008956b  mov     rbx, [rcx+230h]
0x140089572  mov     [rsp+148h+var_78], 0
0x14008957e  mov     r8d, [r13+24h]
0x140089582  cmp     r8d, 70h ; 'p'
0x140089586  jnb     short loc_1400895F2
0x140089588  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008958f  lea     rax, WPP_GLOBAL_Control
0x140089596  cmp     rcx, rax
0x140089599  jz      short loc_1400895C7
0x14008959b  test    dword ptr [rcx+2Ch], 800000h
0x1400895a2  jz      short loc_1400895C7
0x1400895a4  cmp     byte ptr [rcx+29h], 1
0x1400895a8  jb      short loc_1400895C7
0x1400895aa  mov     rcx, [rcx+18h]
0x1400895ae  mov     edx, 0Bh
0x1400895b3  mov     dword ptr [rsp+148h+var_128], r8d
0x1400895b8  mov     r9, r15
0x1400895bb  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x1400895c2  call    WPP_SF_qD
0x1400895c7  mov     r9d, 237h
0x1400895cd  lea     r8, aOnecoreBaseFsR_1; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x1400895d4  mov     edx, 0C000000Dh
0x1400895d9  mov     rcx, r15
0x1400895dc  call    _Smb2SetError
0x1400895e1  xor     edx, edx
0x1400895e3  mov     rcx, rbx
0x1400895e6  call    Smb2LkmdTelCollectParsingFailureWriteHelper
0x1400895eb  xor     eax, eax
0x1400895ed  jmp     loc_14008B1F2
0x1400895f2  mov     r13, [r13+18h]
0x1400895f6  cmp     word ptr [r13+40h], 31h ; '1'
0x1400895fc  mov     [rsp+148h+var_40], r14
0x140089604  lea     r14, [r13+40h]
0x140089608  jz      short loc_140089672
0x14008960a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140089611  lea     rax, WPP_GLOBAL_Control
0x140089618  cmp     rcx, rax
0x14008961b  jz      short loc_140089644
0x14008961d  test    dword ptr [rcx+2Ch], 800000h
0x140089624  jz      short loc_140089644
0x140089626  cmp     byte ptr [rcx+29h], 1
0x14008962a  jb      short loc_140089644
0x14008962c  mov     rcx, [rcx+18h]
0x140089630  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x140089637  mov     edx, 0Ch
0x14008963c  mov     r9, r15
0x14008963f  call    WPP_SF_q
0x140089644  mov     r9d, 247h
0x14008964a  lea     r8, aOnecoreBaseFsR_1; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140089651  mov     edx, 0C000000Dh
0x140089656  mov     rcx, r15
0x140089659  call    _Smb2SetError
0x14008965e  mov     edx, 1
0x140089663  mov     rcx, rbx
0x140089666  call    Smb2LkmdTelCollectParsingFailureWriteHelper
0x14008966b  xor     eax, eax
0x14008966d  jmp     loc_14008B1EA
0x140089672  mov     rax, [rcx+60h]
0x140089676  xor     r9d, r9d
0x140089679  mov     rdx, [r13+28h]
0x14008967d  mov     r8, r13
0x140089680  mov     [rsp+148h+var_28], rsi
0x140089688  mov     byte ptr [rsp+148h+var_120], 0
0x14008968d  mov     rsi, [rax+1F0h]
0x140089694  mov     [rsp+148h+var_58], rsi
0x14008969c  mov     [rsp+148h+var_30], rdi
0x1400896a4  mov     byte ptr [rsp+148h+var_128], 1
0x1400896a9  call    Smb2VerifySessionExEx
0x1400896ae  mov     edi, eax
0x1400896b0  test    eax, eax
0x1400896b2  jns     short loc_14008970C
0x1400896b4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400896bb  lea     rax, WPP_GLOBAL_Control
0x1400896c2  cmp     rcx, rax
0x1400896c5  jz      short loc_1400896EE
0x1400896c7  test    dword ptr [rcx+2Ch], 800000h
0x1400896ce  jz      short loc_1400896EE
0x1400896d0  cmp     byte ptr [rcx+29h], 1
0x1400896d4  jb      short loc_1400896EE
0x1400896d6  mov     rcx, [rcx+18h]
0x1400896da  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x1400896e1  mov     edx, 0Dh
0x1400896e6  mov     r9, r15
0x1400896e9  call    WPP_SF_q
0x1400896ee  mov     r9d, 256h
0x1400896f4  lea     r8, aOnecoreBaseFsR_1; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x1400896fb  mov     edx, edi
0x1400896fd  mov     rcx, r15
0x140089700  call    _Smb2SetError
0x140089705  xor     eax, eax
0x140089707  jmp     loc_14008B1DA
0x14008970c  movups  xmm0, xmmword ptr [r14+10h]
0x140089711  mov     r9b, 3
0x140089714  mov     [rsp+148h+var_20], rbp
0x14008971c  mov     r8, r13
0x14008971f  lea     rdx, [rsp+148h+var_68]
0x140089727  mov     rcx, r15; BugCheckParameter4
0x14008972a  movaps  [rsp+148h+var_68], xmm0
0x140089732  call    Smb2VerifyFileEx
0x140089737  lea     rbp, WPP_GLOBAL_Control
0x14008973e  mov     edi, eax
0x140089740  test    eax, eax
0x140089742  jns     short loc_14008977F
0x140089744  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008974b  cmp     rcx, rbp
0x14008974e  jz      short loc_140089777
0x140089750  test    dword ptr [rcx+2Ch], 800000h
0x140089757  jz      short loc_140089777
0x140089759  cmp     byte ptr [rcx+29h], 1
0x14008975d  jb      short loc_140089777
0x14008975f  movzx   r9d, word ptr [r13+0Ch]
0x140089764  mov     edx, 5Bh ; '['
0x140089769  mov     rcx, [rcx+18h]
0x14008976d  mov     [rsp+148h+var_128], r15
0x140089772  call    WPP_SF_hq
0x140089777  cmp     edi, 0C0000128h
0x14008977d  jnz     short loc_1400897FB
0x14008977f  mov     edx, [r13+24h]
0x140089783  mov     r8, r13
0x140089786  mov     rcx, r15
0x140089789  call    Smb2VerifyTreeConnect_Old
0x14008978e  mov     ebp, eax
0x140089790  test    eax, eax
0x140089792  jns     short loc_1400897D0
0x140089794  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008979b  lea     rax, WPP_GLOBAL_Control
0x1400897a2  cmp     rcx, rax
0x1400897a5  jz      short loc_140089801
0x1400897a7  test    dword ptr [rcx+2Ch], 800000h
0x1400897ae  jz      short loc_140089801
0x1400897b0  cmp     byte ptr [rcx+29h], 1
0x1400897b4  jb      short loc_140089801
0x1400897b6  movzx   r9d, word ptr [r13+0Ch]
0x1400897bb  mov     edx, 5Ch ; '\'
0x1400897c0  mov     rcx, [rcx+18h]
0x1400897c4  mov     [rsp+148h+var_128], r15
0x1400897c9  call    WPP_SF_hq
0x1400897ce  jmp     short loc_140089801
0x1400897d0  lea     rbp, WPP_GLOBAL_Control
0x1400897d7  cmp     edi, 0C0000128h
0x1400897dd  jnz     short loc_1400897FB
0x1400897df  mov     rax, [r15+230h]
0x1400897e6  mov     rcx, [rax+38h]
0x1400897ea  cmp     byte ptr [rcx+9Ah], 0
0x1400897f1  jz      short loc_1400897FB
0x1400897f3  mov     byte ptr [r15+1DAh], 1
0x1400897fb  test    edi, edi
0x1400897fd  jns     short loc_14008981F
0x1400897ff  mov     ebp, edi
0x140089801  mov     r9d, 263h
0x140089807  lea     r8, aOnecoreBaseFsR_1; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14008980e  mov     edx, ebp
0x140089810  mov     rcx, r15
0x140089813  call    _Smb2SetError
0x140089818  xor     eax, eax
0x14008981a  jmp     loc_14008B1D2
0x14008981f  mov     rcx, [rbx+38h]
0x140089823  xor     edx, edx
0x140089825  mov     eax, 8
0x14008982a  mov     r8d, 300h
0x140089830  cmp     dword ptr [rcx+4Ch], 1
0x140089834  cmovz   edx, eax
0x140089837  movzx   eax, byte ptr [rbx+118h]
0x14008983e  and     al, 0F7h
0x140089840  or      dl, al
0x140089842  mov     [rbx+118h], dl
0x140089848  mov     rax, [rcx+60h]
0x14008984c  cmp     qword ptr [rax+188h], 0
0x140089854  jz      short loc_140089866
0x140089856  cmp     [rsi+2Ch], r8w
0x14008985b  jnb     short loc_1400898C9
0x14008985d  or      dl, 4
0x140089860  mov     [rbx+118h], dl
0x140089866  mov     rax, [rbx+48h]
0x14008986a  mov     ecx, [rax+0E0h]
0x140089870  test    cl, 2
0x140089873  jnz     short loc_1400898EA
0x140089875  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008987c  cmp     rcx, rbp
0x14008987f  jz      short loc_1400898A8
0x140089881  test    dword ptr [rcx+2Ch], 800000h
0x140089888  jz      short loc_1400898A8
0x14008988a  cmp     byte ptr [rcx+29h], 1
0x14008988e  jb      short loc_1400898A8
0x140089890  mov     rcx, [rcx+18h]
0x140089894  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x14008989b  mov     edx, 0Eh
0x1400898a0  mov     r9, r15
0x1400898a3  call    WPP_SF_q
0x1400898a8  mov     r9d, 286h
0x1400898ae  lea     r8, aOnecoreBaseFsR_1; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x1400898b5  mov     edx, 0C0000022h
0x1400898ba  mov     rcx, r15
0x1400898bd  call    _Smb2SetError
0x1400898c2  xor     eax, eax
0x1400898c4  jmp     loc_14008B1D2
0x1400898c9  mov     r9d, 278h
0x1400898cf  lea     r8, aOnecoreBaseFsR_1; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x1400898d6  mov     edx, 0C0000480h
0x1400898db  mov     rcx, r15
0x1400898de  call    _Smb2SetError
0x1400898e3  xor     eax, eax
0x1400898e5  jmp     loc_14008B1D2
0x1400898ea  mov     rax, [rbx+58h]
0x1400898ee  shr     ecx, 8
0x1400898f1  shl     cl, 4
0x1400898f4  xor     cl, dl
0x1400898f6  mov     [rsp+148h+var_38], r12
0x1400898fe  and     cl, 10h
0x140089901  xor     cl, dl
0x140089903  mov     [rbx+118h], cl
0x140089909  mov     r12d, [rax+50h]
0x14008990d  mov     ecx, [rsi+28h]
0x140089910  and     ecx, [r14+2Ch]
0x140089914  shr     r12d, 3
0x140089918  and     r12b, 1
0x14008991c  mov     [r14+2Ch], ecx
0x140089920  test    byte ptr [rbx+118h], 8
0x140089927  jz      short loc_140089989
0x140089929  test    cl, 7
0x14008992c  jz      loc_1400899F6
0x140089932  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140089939  cmp     rcx, rbp
0x14008993c  jz      short loc_140089965
0x14008993e  test    dword ptr [rcx+2Ch], 800000h
0x140089945  jz      short loc_140089965
0x140089947  cmp     byte ptr [rcx+29h], 1
0x14008994b  jb      short loc_140089965
0x14008994d  mov     rcx, [rcx+18h]
0x140089951  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x140089958  mov     edx, 0Fh
0x14008995d  mov     r9, r15
0x140089960  call    WPP_SF_q
0x140089965  mov     r9d, 2A9h
0x14008996b  lea     r8, aOnecoreBaseFsR_1; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140089972  mov     edx, 0C000000Dh
0x140089977  mov     rcx, r15
0x14008997a  call    _Smb2SetError
0x14008997f  mov     edx, 3
0x140089984  jmp     loc_14008B1C0
0x140089989  mov     eax, ecx
0x14008998b  shr     eax, 1
0x14008998d  and     al, 1
0x14008998f  or      al, r12b
0x140089992  movzx   r12d, al
0x140089996  test    cl, 1
0x140089999  jz      short loc_1400899F6
0x14008999b  test    al, al
0x14008999d  jnz     short loc_1400899F6
0x14008999f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400899a6  cmp     rcx, rbp
0x1400899a9  jz      short loc_1400899D2
0x1400899ab  test    dword ptr [rcx+2Ch], 800000h
0x1400899b2  jz      short loc_1400899D2
0x1400899b4  cmp     byte ptr [rcx+29h], 1
0x1400899b8  jb      short loc_1400899D2
0x1400899ba  mov     rcx, [rcx+18h]
0x1400899be  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x1400899c5  mov     edx, 10h
0x1400899ca  mov     r9, r15
0x1400899cd  call    WPP_SF_q
0x1400899d2  mov     r9d, 2BCh
0x1400899d8  lea     r8, aOnecoreBaseFsR_1; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x1400899df  mov     edx, 0C000000Dh
0x1400899e4  mov     rcx, r15
0x1400899e7  call    _Smb2SetError
0x1400899ec  mov     edx, 4
0x1400899f1  jmp     loc_14008B1C0
0x1400899f6  cmp     [rsi+2Ch], r8w
0x1400899fb  jb      short loc_140089A63
0x1400899fd  mov     r8d, [r14+20h]
0x140089a01  cmp     r8d, [rsi+20h]
0x140089a05  jbe     short loc_140089A6B
0x140089a07  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140089a0e  cmp     rcx, rbp
0x140089a11  jz      short loc_140089A3F
0x140089a13  test    dword ptr [rcx+2Ch], 800000h
0x140089a1a  jz      short loc_140089A3F
0x140089a1c  cmp     byte ptr [rcx+29h], 1
0x140089a20  jb      short loc_140089A3F
0x140089a22  mov     rcx, [rcx+18h]
0x140089a26  mov     edx, 11h
0x140089a2b  mov     dword ptr [rsp+148h+var_128], r8d
0x140089a30  mov     r9, r15
0x140089a33  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x140089a3a  call    WPP_SF_qD
0x140089a3f  mov     r9d, 2D0h
0x140089a45  lea     r8, aOnecoreBaseFsR_1; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140089a4c  mov     edx, 0C000000Dh
0x140089a51  mov     rcx, r15
0x140089a54  call    _Smb2SetError
0x140089a59  mov     edx, 5
0x140089a5e  jmp     loc_14008B1C0
  ... truncated ...
```
