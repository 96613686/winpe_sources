# Smb2ValidateChangeNotify

- ea: `0x14005c010`
- end: `0x14005c5f9`
- name: `Smb2ValidateChangeNotify`
- size: `1513`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter4)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140073ab0`

## callees

- `0x140007400`
- `0x14001c8ec`
- `0x14001cef0`
- `0x1400222ec`
- `0x140022958`
- `0x1400229ac`
- `0x140027430`
- `0x1400275c0`
- `0x14002ad2c`
- `0x14005c010`
- `0x14005c600`

## import_xrefs

- `ntoskrnl!IoCheckFunctionAccess` at `0x14005c414`
- `ntoskrnl!IoCheckFunctionAccess` at `0x14005c414`
- `srvnet!SrvNetAllocateBuffer` at `0x14005c48d`
- `srvnet!SrvNetAllocateBuffer` at `0x14005c48d`

## pseudocode

```c
__int64 __fastcall Smb2ValidateChangeNotify(ULONG_PTR BugCheckParameter4)
{
  __int64 v1; // rbp
  __int64 v3; // r14
  unsigned int v4; // r8d
  __int64 v5; // rdx
  __int64 v7; // rbp
  __int64 v8; // r13
  NTSTATUS v9; // r15d
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // r15d
  __int64 v14; // r8
  int v15; // r12d
  unsigned int v16; // ecx
  int v17; // eax
  int v18; // edx
  __int64 v19; // r9
  unsigned int v20; // ecx
  unsigned int v21; // r8d
  __int64 Buffer; // rax
  _QWORD *v23; // rax
  __int64 *v24; // rdx
  __int64 v25; // rcx
  __int64 *v26; // r11
  __int64 v27; // rcx
  __int64 *v28; // r10
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // r9
  __int64 v32; // [rsp+78h] [rbp-80h]

  v1 = *(_QWORD *)(BugCheckParameter4 + 304);
  v3 = *(_QWORD *)(BugCheckParameter4 + 560);
  v4 = *(_DWORD *)(v1 + 36);
  if ( v4 < 0x60 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          &WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids,
          BugCheckParameter4,
          v4);
    }
    Smb2SetError(BugCheckParameter4, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\notify.c", 95);
    v5 = 0;
    goto LABEL_7;
  }
  v7 = *(_QWORD *)(v1 + 24);
  if ( *(_WORD *)(v7 + 64) != 32 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        &WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids,
        BugCheckParameter4);
    }
    Smb2SetError(BugCheckParameter4, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\notify.c", 111);
    v5 = 1;
    goto LABEL_7;
  }
  v8 = *(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 96) + 496LL);
  v9 = Smb2VerifySessionExEx(BugCheckParameter4, *(_QWORD *)(v7 + 40), v7, 0, 1, 0);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        &WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids,
        BugCheckParameter4);
    }
    v10 = 126;
LABEL_21:
    v11 = (unsigned int)v9;
LABEL_22:
    Smb2SetError(BugCheckParameter4, v11, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\notify.c", v10);
    return 0;
  }
  v13 = Smb2VerifyFileEx(BugCheckParameter4);
  if ( v13 >= 0 )
    goto LABEL_29;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_hq(WPP_GLOBAL_Control->AttachedDevice, 91, v12, *(unsigned __int16 *)(v7 + 12), BugCheckParameter4);
  }
  if ( v13 == -1073741528 )
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
    if ( v13 == -1073741528 && *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 560) + 56LL) + 154LL) )
      *(_BYTE *)(BugCheckParameter4 + 474) = 1;
  }
  if ( v13 < 0 )
  {
    v15 = v13;
LABEL_39:
    v10 = 136;
    v11 = (unsigned int)v15;
    goto LABEL_22;
  }
  v16 = *(_DWORD *)(v7 + 68);
  if ( v16 > *(_DWORD *)(v8 + 36) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        &WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids,
        BugCheckParameter4);
    }
    Smb2SetError(BugCheckParameter4, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\notify.c", 149);
    v5 = 2;
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
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          &WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids,
          BugCheckParameter4,
          v18);
      }
      v19 = 178;
LABEL_60:
      Smb2SetError(
        BugCheckParameter4,
        3221225485LL,
        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\notify.c",
        v19);
      v5 = 3;
LABEL_7:
      Smb2LkmdTelCollectParsingFailureNotifyHelper(v3, v5);
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
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qDD(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        &WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids,
        BugCheckParameter4,
        v21,
        v20);
    }
    v19 = 198;
    goto LABEL_60;
  }
LABEL_70:
  v9 = IoCheckFunctionAccess(*(_DWORD *)(*(_QWORD *)(v3 + 72) + 184LL), 0xCu, 0, 0, 0, 0);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        16,
        &WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids,
        BugCheckParameter4);
    }
    v10 = 218;
    goto LABEL_21;
  }
  *(_DWORD *)(v3 + 192) = *(_DWORD *)(v7 + 88);
  *(_WORD *)(v3 + 200) = *(_WORD *)(v7 + 66) & 1;
  *(_DWORD *)(v3 + 196) = *(_DWORD *)(v7 + 68);
  Buffer = SrvNetAllocateBuffer(*(unsigned int *)(v7 + 68), 0);
  *(_QWORD *)(v3 + 160) = Buffer;
  if ( !Buffer )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        &WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids,
        BugCheckParameter4);
    }
    v10 = 236;
    v11 = 3221225989LL;
    goto LABEL_22;
  }
  if ( (Microsoft_Windows_SMBServerEnableBits & 1) != 0 )
  {
    v23 = *(_QWORD **)(BugCheckParameter4 + 560);
    v24 = &Srv2ZeroGuid;
    v25 = v23[9];
    v26 = (__int64 *)(v25 + 96);
    if ( !v25 )
      v26 = &Srv2ZeroGuid;
    v27 = v23[7];
    v28 = (__int64 *)(v27 + 24);
    if ( !v27 )
      v28 = &Srv2ZeroGuid;
    v29 = v23[4];
    if ( v29 )
      v24 = (__int64 *)(v29 + 72);
    v30 = *(_QWORD *)(BugCheckParameter4 + 416);
    if ( v30 )
      v31 = *(_QWORD *)(*(_QWORD *)(v30 + 560) + 176LL);
    else
      LOBYTE(v31) = -1;
    v32 = *(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 96) + 496LL) + 72LL;
    McTemplateK0xqqxxhhqhxqqjjjj_EtwWriteTransfer(
      v32,
      (_DWORD)v24,
      BugCheckParameter4 + 584,
      *(_QWORD *)(v7 + 40),
      *(_DWORD *)(v7 + 32),
      *(_DWORD *)(v7 + 36),
      *(_QWORD *)(v7 + 24),
      v31,
      *(_WORD *)(v7 + 12),
      *(_WORD *)(v7 + 14),
      *(_DWORD *)(v7 + 16),
      *(_WORD *)(v7 + 66),
      *(_QWORD *)(v7 + 72),
      *(_DWORD *)(v7 + 68),
      *(_DWORD *)(v7 + 88),
      v32,
      (__int64)v24,
      (__int64)v28,
      (__int64)v26);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x14005c010  push    rbx
0x14005c012  push    rbp
0x14005c013  push    rsi
0x14005c014  push    rdi
0x14005c015  push    r12
0x14005c017  push    r13
0x14005c019  push    r14
0x14005c01b  push    r15
0x14005c01d  sub     rsp, 0B8h
0x14005c024  mov     rbp, [rcx+130h]
0x14005c02b  mov     rbx, rcx
0x14005c02e  mov     r14, [rcx+230h]
0x14005c035  mov     r8d, [rbp+24h]
0x14005c039  cmp     r8d, 60h ; '`'
0x14005c03d  jnb     short loc_14005C0AC
0x14005c03f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005c046  lea     rsi, WPP_GLOBAL_Control
0x14005c04d  cmp     rcx, rsi
0x14005c050  jz      short loc_14005C081
0x14005c052  test    dword ptr [rcx+2Ch], 4000000h
0x14005c059  jz      short loc_14005C081
0x14005c05b  mov     edi, 1
0x14005c060  cmp     [rcx+29h], dil
0x14005c064  jb      short loc_14005C081
0x14005c066  mov     rcx, [rcx+18h]
0x14005c06a  lea     edx, [rdi+9]
0x14005c06d  mov     dword ptr [rsp+0F8h+Arg1], r8d
0x14005c072  mov     r9, rbx
0x14005c075  lea     r8, WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids
0x14005c07c  call    WPP_SF_qD
0x14005c081  mov     r9d, 5Fh ; '_'
0x14005c087  lea     r8, aOnecoreBaseFsR_7; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14005c08e  mov     edx, 0C000000Dh
0x14005c093  mov     rcx, rbx
0x14005c096  call    _Smb2SetError
0x14005c09b  xor     edx, edx
0x14005c09d  mov     rcx, r14
0x14005c0a0  call    Smb2LkmdTelCollectParsingFailureNotifyHelper
0x14005c0a5  xor     eax, eax
0x14005c0a7  jmp     loc_14005C5E4
0x14005c0ac  mov     rbp, [rbp+18h]
0x14005c0b0  cmp     word ptr [rbp+40h], 20h ; ' '
0x14005c0b5  jz      short loc_14005C112
0x14005c0b7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005c0be  lea     rsi, WPP_GLOBAL_Control
0x14005c0c5  mov     edi, 1
0x14005c0ca  cmp     rcx, rsi
0x14005c0cd  jz      short loc_14005C0F4
0x14005c0cf  test    dword ptr [rcx+2Ch], 4000000h
0x14005c0d6  jz      short loc_14005C0F4
0x14005c0d8  cmp     [rcx+29h], dil
0x14005c0dc  jb      short loc_14005C0F4
0x14005c0de  mov     rcx, [rcx+18h]
0x14005c0e2  lea     edx, [rdi+0Ah]
0x14005c0e5  mov     r9, rbx
0x14005c0e8  lea     r8, WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids
0x14005c0ef  call    WPP_SF_q
0x14005c0f4  mov     r9d, 6Fh ; 'o'
0x14005c0fa  lea     r8, aOnecoreBaseFsR_7; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14005c101  mov     edx, 0C000000Dh
0x14005c106  mov     rcx, rbx
0x14005c109  call    _Smb2SetError
0x14005c10e  mov     edx, edi
0x14005c110  jmp     short loc_14005C09D
0x14005c112  mov     rax, [rcx+60h]
0x14005c116  mov     edi, 1
0x14005c11b  mov     rdx, [rbp+28h]
0x14005c11f  xor     r9d, r9d
0x14005c122  mov     byte ptr [rsp+0F8h+Arg2], 0
0x14005c127  mov     r8, rbp
0x14005c12a  mov     byte ptr [rsp+0F8h+Arg1], dil
0x14005c12f  mov     r13, [rax+1F0h]
0x14005c136  call    Smb2VerifySessionExEx
0x14005c13b  mov     r15d, eax
0x14005c13e  test    eax, eax
0x14005c140  jns     short loc_14005C197
0x14005c142  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005c149  lea     rsi, WPP_GLOBAL_Control
0x14005c150  cmp     rcx, rsi
0x14005c153  jz      short loc_14005C17A
0x14005c155  test    dword ptr [rcx+2Ch], 4000000h
0x14005c15c  jz      short loc_14005C17A
0x14005c15e  cmp     [rcx+29h], dil
0x14005c162  jb      short loc_14005C17A
0x14005c164  mov     rcx, [rcx+18h]
0x14005c168  lea     edx, [rdi+0Bh]
0x14005c16b  mov     r9, rbx
0x14005c16e  lea     r8, WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids
0x14005c175  call    WPP_SF_q
0x14005c17a  mov     r9d, 7Eh ; '~'
0x14005c180  mov     edx, r15d
0x14005c183  lea     r8, aOnecoreBaseFsR_7; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14005c18a  mov     rcx, rbx
0x14005c18d  call    _Smb2SetError
0x14005c192  jmp     loc_14005C0A5
0x14005c197  movups  xmm0, xmmword ptr [rbp+48h]
0x14005c19b  mov     r9b, 2
0x14005c19e  lea     rdx, [rsp+0F8h+var_58]
0x14005c1a6  mov     r8, rbp
0x14005c1a9  mov     rcx, rbx; BugCheckParameter4
0x14005c1ac  movdqu  [rsp+0F8h+var_58], xmm0
0x14005c1b5  call    Smb2VerifyFileEx
0x14005c1ba  lea     rsi, WPP_GLOBAL_Control
0x14005c1c1  mov     r15d, eax
0x14005c1c4  test    eax, eax
0x14005c1c6  jns     short loc_14005C204
0x14005c1c8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005c1cf  cmp     rcx, rsi
0x14005c1d2  jz      short loc_14005C1FB
0x14005c1d4  test    dword ptr [rcx+2Ch], 800000h
0x14005c1db  jz      short loc_14005C1FB
0x14005c1dd  cmp     [rcx+29h], dil
0x14005c1e1  jb      short loc_14005C1FB
0x14005c1e3  movzx   r9d, word ptr [rbp+0Ch]
0x14005c1e8  mov     edx, 5Bh ; '['
0x14005c1ed  mov     rcx, [rcx+18h]
0x14005c1f1  mov     [rsp+0F8h+Arg1], rbx
0x14005c1f6  call    WPP_SF_hq
0x14005c1fb  cmp     r15d, 0C0000128h
0x14005c202  jnz     short loc_14005C272
0x14005c204  mov     edx, [rbp+24h]
0x14005c207  mov     r8, rbp
0x14005c20a  mov     rcx, rbx
0x14005c20d  call    Smb2VerifyTreeConnect_Old
0x14005c212  mov     r12d, eax
0x14005c215  test    eax, eax
0x14005c217  jns     short loc_14005C24E
0x14005c219  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005c220  cmp     rcx, rsi
0x14005c223  jz      short loc_14005C27A
0x14005c225  test    dword ptr [rcx+2Ch], 800000h
0x14005c22c  jz      short loc_14005C27A
0x14005c22e  cmp     [rcx+29h], dil
0x14005c232  jb      short loc_14005C27A
0x14005c234  movzx   r9d, word ptr [rbp+0Ch]
0x14005c239  mov     edx, 5Ch ; '\'
0x14005c23e  mov     rcx, [rcx+18h]
0x14005c242  mov     [rsp+0F8h+Arg1], rbx
0x14005c247  call    WPP_SF_hq
0x14005c24c  jmp     short loc_14005C27A
0x14005c24e  cmp     r15d, 0C0000128h
0x14005c255  jnz     short loc_14005C272
0x14005c257  mov     rax, [rbx+230h]
0x14005c25e  mov     rcx, [rax+38h]
0x14005c262  cmp     byte ptr [rcx+9Ah], 0
0x14005c269  jz      short loc_14005C272
0x14005c26b  mov     [rbx+1DAh], dil
0x14005c272  test    r15d, r15d
0x14005c275  jns     short loc_14005C288
0x14005c277  mov     r12d, r15d
0x14005c27a  mov     r9d, 88h
0x14005c280  mov     edx, r12d
0x14005c283  jmp     loc_14005C183
0x14005c288  mov     ecx, [rbp+44h]
0x14005c28b  cmp     ecx, [r13+24h]
0x14005c28f  jbe     short loc_14005C2E8
0x14005c291  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005c298  cmp     rcx, rsi
0x14005c29b  jz      short loc_14005C2C4
0x14005c29d  test    dword ptr [rcx+2Ch], 4000000h
0x14005c2a4  jz      short loc_14005C2C4
0x14005c2a6  cmp     [rcx+29h], dil
0x14005c2aa  jb      short loc_14005C2C4
0x14005c2ac  mov     rcx, [rcx+18h]
0x14005c2b0  lea     r8, WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids
0x14005c2b7  mov     edx, 0Dh
0x14005c2bc  mov     r9, rbx
0x14005c2bf  call    WPP_SF_q
0x14005c2c4  mov     r9d, 95h
0x14005c2ca  lea     r8, aOnecoreBaseFsR_7; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14005c2d1  mov     edx, 0C000000Dh
0x14005c2d6  mov     rcx, rbx
0x14005c2d9  call    _Smb2SetError
0x14005c2de  mov     edx, 2
0x14005c2e3  jmp     loc_14005C09D
0x14005c2e8  test    byte ptr [r13+31h], 2
0x14005c2ed  jz      loc_14005C3F0
0x14005c2f3  cmp     cs:Smb2SingleCreditChargePerSpecifiedRequest, 0
0x14005c2fa  jz      loc_14005C38F
0x14005c300  mov     eax, 10000h
0x14005c305  cmp     ecx, eax
0x14005c307  jb      short loc_14005C30E
0x14005c309  mov     [rbp+44h], eax
0x14005c30c  jmp     short loc_14005C317
0x14005c30e  mov     [rbp+44h], ecx
0x14005c311  test    ecx, ecx
0x14005c313  jz      short loc_14005C322
0x14005c315  mov     eax, ecx
0x14005c317  dec     eax
0x14005c319  test    eax, 0FFFF0000h
0x14005c31e  jz      short loc_14005C322
0x14005c320  int     2Ch; Windows NT - assertion failure
0x14005c322  movzx   edx, word ptr [rbx+1E8h]
0x14005c329  cmp     dx, di
0x14005c32c  jz      loc_14005C3F0
0x14005c332  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005c339  cmp     rcx, rsi
0x14005c33c  jz      short loc_14005C36B
0x14005c33e  test    dword ptr [rcx+2Ch], 4000000h
0x14005c345  jz      short loc_14005C36B
0x14005c347  cmp     [rcx+29h], dil
0x14005c34b  jb      short loc_14005C36B
0x14005c34d  mov     rcx, [rcx+18h]
0x14005c351  lea     r8, WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids
0x14005c358  mov     eax, edx
0x14005c35a  mov     r9, rbx
0x14005c35d  mov     edx, 0Eh
0x14005c362  mov     dword ptr [rsp+0F8h+Arg1], eax
0x14005c366  call    WPP_SF_qD
0x14005c36b  mov     r9d, 0B2h
0x14005c371  lea     r8, aOnecoreBaseFsR_7; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14005c378  mov     edx, 0C000000Dh
0x14005c37d  mov     rcx, rbx
0x14005c380  call    _Smb2SetError
0x14005c385  mov     edx, 3
0x14005c38a  jmp     loc_14005C09D
0x14005c38f  test    ecx, ecx
0x14005c391  jz      short loc_14005C39C
0x14005c393  dec     ecx
0x14005c395  shr     ecx, 10h
0x14005c398  add     ecx, edi
0x14005c39a  jmp     short loc_14005C39E
0x14005c39c  mov     ecx, edi
0x14005c39e  movzx   r8d, word ptr [rbx+1E8h]
0x14005c3a6  cmp     r8d, ecx
0x14005c3a9  jnb     short loc_14005C3F0
0x14005c3ab  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005c3b2  cmp     r10, rsi
0x14005c3b5  jz      short loc_14005C3E8
0x14005c3b7  test    dword ptr [r10+2Ch], 4000000h
0x14005c3bf  jz      short loc_14005C3E8
0x14005c3c1  cmp     [r10+29h], dil
0x14005c3c5  jb      short loc_14005C3E8
0x14005c3c7  mov     dword ptr [rsp+0F8h+Arg2], ecx
0x14005c3cb  mov     edx, 0Fh
0x14005c3d0  mov     rcx, [r10+18h]
0x14005c3d4  mov     r9, rbx
0x14005c3d7  mov     dword ptr [rsp+0F8h+Arg1], r8d
0x14005c3dc  lea     r8, WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids
0x14005c3e3  call    WPP_SF_qDD
0x14005c3e8  mov     r9d, 0C6h
0x14005c3ee  jmp     short loc_14005C371
0x14005c3f0  mov     rcx, [r14+48h]
0x14005c3f4  xor     r9d, r9d; IoControlCode
0x14005c3f7  mov     [rsp+0F8h+Arg2], 0; Arg2
0x14005c400  xor     r8d, r8d; MinorFunction
0x14005c403  mov     dl, 0Ch; MajorFunction
0x14005c405  mov     [rsp+0F8h+Arg1], 0; Arg1
0x14005c40e  mov     ecx, [rcx+0B8h]; GrantedAccess
0x14005c414  call    cs:__imp_IoCheckFunctionAccess
0x14005c41b  nop     dword ptr [rax+rax+00h]
0x14005c420  mov     r15d, eax
0x14005c423  test    eax, eax
0x14005c425  jns     short loc_14005C465
0x14005c427  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005c42e  cmp     rcx, rsi
0x14005c431  jz      short loc_14005C45A
0x14005c433  test    dword ptr [rcx+2Ch], 4000000h
0x14005c43a  jz      short loc_14005C45A
0x14005c43c  cmp     [rcx+29h], dil
0x14005c440  jb      short loc_14005C45A
0x14005c442  mov     rcx, [rcx+18h]
0x14005c446  lea     r8, WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids
0x14005c44d  mov     edx, 10h
0x14005c452  mov     r9, rbx
0x14005c455  call    WPP_SF_q
0x14005c45a  mov     r9d, 0DAh
0x14005c460  jmp     loc_14005C180
0x14005c465  mov     eax, [rbp+58h]
0x14005c468  xor     edx, edx
0x14005c46a  mov     [r14+0C0h], eax
0x14005c471  movzx   eax, word ptr [rbp+42h]
0x14005c475  and     ax, di
0x14005c478  mov     [r14+0C8h], ax
0x14005c480  mov     eax, [rbp+44h]
0x14005c483  mov     [r14+0C4h], eax
0x14005c48a  mov     ecx, [rbp+44h]
0x14005c48d  call    cs:__imp_SrvNetAllocateBuffer
0x14005c494  nop     dword ptr [rax+rax+00h]
0x14005c499  mov     [r14+0A0h], rax
0x14005c4a0  test    rax, rax
0x14005c4a3  jnz     short loc_14005C4E6
0x14005c4a5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005c4ac  cmp     rcx, rsi
0x14005c4af  jz      short loc_14005C4D6
0x14005c4b1  test    dword ptr [rcx+2Ch], 4000000h
0x14005c4b8  jz      short loc_14005C4D6
0x14005c4ba  cmp     [rcx+29h], dil
0x14005c4be  jb      short loc_14005C4D6
0x14005c4c0  mov     rcx, [rcx+18h]
0x14005c4c4  lea     edx, [rax+11h]
0x14005c4c7  mov     r9, rbx
0x14005c4ca  lea     r8, WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids
0x14005c4d1  call    WPP_SF_q
0x14005c4d6  mov     r9d, 0ECh
0x14005c4dc  mov     edx, 0C0000205h
0x14005c4e1  jmp     loc_14005C183
0x14005c4e6  test    cs:Microsoft_Windows_SMBServerEnableBits, dil
0x14005c4ed  jz      loc_14005C5DF
0x14005c4f3  mov     rax, [rbx+230h]
  ... truncated ...
```
