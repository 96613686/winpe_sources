# Smb2ValidateQueryDirectory

- ea: `0x14005a9c0`
- end: `0x14005b1ab`
- name: `Smb2ValidateQueryDirectory`
- size: `2027`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter4)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140073a60`

## callees

- `0x140007400`
- `0x14001c8ec`
- `0x14001cef0`
- `0x14001d644`
- `0x14001e54c`
- `0x1400222ec`
- `0x140022958`
- `0x1400229ac`
- `0x14002ad2c`
- `0x14005a9c0`
- `0x14005c600`

## import_xrefs

- `ntoskrnl!IoCheckFunctionAccess` at `0x14005af4c`
- `ntoskrnl!IoCheckFunctionAccess` at `0x14005af4c`
- `srvnet!SrvNetAllocateBuffer` at `0x14005afef`
- `srvnet!SrvNetAllocateBuffer` at `0x14005afef`

## pseudocode

```c
__int64 __fastcall Smb2ValidateQueryDirectory(ULONG_PTR BugCheckParameter4)
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
  __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  signed int v18; // eax
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // r8d
  __int64 v22; // rcx
  __int64 v23; // rax
  unsigned int v24; // ecx
  __int16 v25; // cx
  __int64 v26; // rax
  __int64 Buffer; // rax
  char v28; // al
  _QWORD *v29; // rax
  __int64 *v30; // r9
  __int64 v31; // rcx
  __int64 *v32; // rdi
  __int64 v33; // rcx
  __int64 *v34; // r11
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // r10
  __int64 v38; // [rsp+90h] [rbp-78h]

  v1 = *(_QWORD *)(BugCheckParameter4 + 304);
  v3 = *(_QWORD *)(BugCheckParameter4 + 560);
  v4 = *(_DWORD *)(v1 + 36);
  if ( v4 < 0x61 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          WPP_afea1950ba7935c3d0422396ce336f53_Traceguids,
          BugCheckParameter4,
          v4);
    }
    Smb2SetError(
      BugCheckParameter4,
      3221225485LL,
      "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\querydir.c",
      137);
    v5 = 0;
LABEL_7:
    Smb2LkmdTelCollectParsingFailureQuerydirHelper(v3, v5);
    return 0;
  }
  v7 = *(_QWORD *)(v1 + 24);
  if ( *(_WORD *)(v7 + 64) != 33 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_afea1950ba7935c3d0422396ce336f53_Traceguids,
        BugCheckParameter4);
    }
    Smb2SetError(
      BugCheckParameter4,
      3221225485LL,
      "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\querydir.c",
      153);
    v5 = 1;
    goto LABEL_7;
  }
  v8 = *(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 96) + 496LL);
  v9 = Smb2VerifySessionExEx(BugCheckParameter4, *(_QWORD *)(v7 + 40), v7, 0, 1, 0);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        WPP_afea1950ba7935c3d0422396ce336f53_Traceguids,
        BugCheckParameter4);
    }
    v10 = 168;
LABEL_21:
    v11 = (unsigned int)v9;
LABEL_22:
    Smb2SetError(BugCheckParameter4, v11, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\querydir.c", v10);
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
    v10 = 178;
    v11 = (unsigned int)v15;
    goto LABEL_22;
  }
  v16 = *(unsigned __int16 *)(v7 + 90);
  if ( (_WORD)v16 )
  {
    v17 = *(unsigned __int16 *)(v7 + 88);
    if ( v17 - 96 > 0x40
      || (v17 + v16 < v17 || v17 + v16 > *(unsigned int *)(*(_QWORD *)(BugCheckParameter4 + 304) + 36LL)
        ? (v18 = -1073741811)
        : (v18 = (((_BYTE)v17 + (_BYTE)v7) & 1) != 0 ? 0xC000000D : 0),
          v18 < 0) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          13,
          WPP_afea1950ba7935c3d0422396ce336f53_Traceguids,
          BugCheckParameter4);
      }
      Smb2SetError(
        BugCheckParameter4,
        3221225485LL,
        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\querydir.c",
        204);
      v5 = 2;
      goto LABEL_7;
    }
    if ( *(unsigned __int16 *)(v7 + 90) == 0xFFFF || (*(_WORD *)(v7 + 90) & 1) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_afea1950ba7935c3d0422396ce336f53_Traceguids,
          BugCheckParameter4);
      }
      Smb2SetError(
        BugCheckParameter4,
        3221225485LL,
        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\querydir.c",
        221);
      v5 = 3;
      goto LABEL_7;
    }
  }
  v19 = *(_DWORD *)(v7 + 92);
  if ( v19 > *(_DWORD *)(v8 + 36) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        WPP_afea1950ba7935c3d0422396ce336f53_Traceguids,
        BugCheckParameter4);
    }
    Smb2SetError(
      BugCheckParameter4,
      3221225485LL,
      "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\querydir.c",
      236);
    v5 = 4;
    goto LABEL_7;
  }
  if ( (*(_BYTE *)(v8 + 49) & 2) != 0 )
  {
    v20 = v19 ? ((v19 - 1) >> 16) + 1 : 1;
    v21 = *(unsigned __int16 *)(BugCheckParameter4 + 488);
    if ( v21 < v20 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qDD(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          WPP_afea1950ba7935c3d0422396ce336f53_Traceguids,
          BugCheckParameter4,
          v21,
          v20);
      }
      Smb2SetError(
        BugCheckParameter4,
        3221225485LL,
        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\querydir.c",
        263);
      v5 = 5;
      goto LABEL_7;
    }
  }
  v22 = *(unsigned __int8 *)(v7 + 66);
  if ( (unsigned __int8)v22 >= 0x54u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        WPP_afea1950ba7935c3d0422396ce336f53_Traceguids,
        BugCheckParameter4);
    }
    v10 = 281;
LABEL_81:
    v11 = 3221225475LL;
    goto LABEL_22;
  }
  v23 = *(unsigned __int8 *)(v7 + 66);
  *(_DWORD *)(v3 + 216) = v22;
  v24 = MinimumOutputBufferSizeTable[v22];
  *(_DWORD *)(v3 + 220) = v24;
  *(_DWORD *)(v3 + 224) = FileNameOffsetForAbeTable[v23];
  if ( !v24 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_afea1950ba7935c3d0422396ce336f53_Traceguids,
        BugCheckParameter4);
    }
    v10 = 301;
    goto LABEL_81;
  }
  if ( *(_DWORD *)(v7 + 92) < v24 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
        WPP_afea1950ba7935c3d0422396ce336f53_Traceguids,
        BugCheckParameter4);
    }
    v10 = 318;
    v11 = 3221225476LL;
    goto LABEL_22;
  }
  v9 = IoCheckFunctionAccess(*(_DWORD *)(*(_QWORD *)(v3 + 72) + 184LL), 0xCu, 0, 0, 0, 0);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        20,
        WPP_afea1950ba7935c3d0422396ce336f53_Traceguids,
        BugCheckParameter4);
    }
    v10 = 335;
    goto LABEL_21;
  }
  *(_BYTE *)(v3 + 212) = *(_BYTE *)(v7 + 67) & 0x13;
  v25 = *(_WORD *)(v7 + 90);
  *(_WORD *)(v3 + 192) = v25;
  *(_WORD *)(v3 + 194) = *(_WORD *)(v7 + 90);
  if ( v25 )
    v26 = v7 + *(unsigned __int16 *)(v7 + 88);
  else
    v26 = 0;
  *(_QWORD *)(v3 + 200) = v26;
  *(_DWORD *)(v3 + 208) = 0;
  *(_DWORD *)(v3 + 228) = *(_DWORD *)(v7 + 92);
  Buffer = SrvNetAllocateBuffer(*(unsigned int *)(v7 + 92), 0);
  *(_QWORD *)(v3 + 160) = Buffer;
  if ( !Buffer )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        WPP_afea1950ba7935c3d0422396ce336f53_Traceguids,
        BugCheckParameter4);
    }
    v10 = 368;
    v11 = 3221225989LL;
    goto LABEL_22;
  }
  v28 = *(_BYTE *)(v3 + 212);
  if ( (v28 & 0x10) != 0 )
  {
    *(_BYTE *)(v3 + 212) = v28 & 0xEF;
    *(_DWORD *)(v3 + 232) = (*(_BYTE *)(*(_QWORD *)(v3 + 56) + 88LL) != 0) + 1;
  }
  if ( (Microsoft_Windows_SMBServerEnableBits & 1) != 0 )
  {
    v29 = *(_QWORD **)(BugCheckParameter4 + 560);
    v30 = &Srv2ZeroGuid;
    v31 = v29[9];
    v32 = (__int64 *)(v31 + 96);
    if ( !v31 )
      v32 = &Srv2ZeroGuid;
    v33 = v29[7];
    v34 = (__int64 *)(v33 + 24);
    if ( !v33 )
      v34 = &Srv2ZeroGuid;
    v35 = v29[4];
    if ( v35 )
      v30 = (__int64 *)(v35 + 72);
    v36 = *(_QWORD *)(BugCheckParameter4 + 416);
    if ( v36 )
      v37 = *(_QWORD *)(*(_QWORD *)(v36 + 560) + 176LL);
    else
      LOBYTE(v37) = -1;
    v38 = *(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 96) + 496LL) + 72LL;
    McTemplateK0xqqxxhhquuqxqhzr13jjjj_EtwWriteTransfer(
      v7 + *(unsigned __int16 *)(v7 + 88),
      v38,
      BugCheckParameter4 + 584,
      *(_QWORD *)(v7 + 40),
      *(_DWORD *)(v7 + 32),
      *(_DWORD *)(v7 + 36),
      *(_QWORD *)(v7 + 24),
      v37,
      *(_WORD *)(v7 + 12),
      *(_WORD *)(v7 + 14),
      *(_DWORD *)(v7 + 16),
      *(_BYTE *)(v7 + 66),
      *(_BYTE *)(v7 + 67),
      *(_DWORD *)(v7 + 68),
      *(_QWORD *)(v7 + 72),
      *(_DWORD *)(v7 + 92),
      *(_WORD *)(v7 + 90) >> 1,
      v7 + *(unsigned __int16 *)(v7 + 88),
      v38,
      (__int64)v30,
      (__int64)v34,
      (__int64)v32);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x14005a9c0  push    rbx
0x14005a9c2  push    rbp
0x14005a9c3  push    rsi
0x14005a9c4  push    rdi
0x14005a9c5  push    r12
0x14005a9c7  push    r13
0x14005a9c9  push    r14
0x14005a9cb  push    r15
0x14005a9cd  sub     rsp, 0C8h
0x14005a9d4  mov     rbp, [rcx+130h]
0x14005a9db  mov     rbx, rcx
0x14005a9de  mov     r14, [rcx+230h]
0x14005a9e5  mov     r8d, [rbp+24h]
0x14005a9e9  cmp     r8d, 61h ; 'a'
0x14005a9ed  jnb     short loc_14005AA5C
0x14005a9ef  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005a9f6  lea     rsi, WPP_GLOBAL_Control
0x14005a9fd  cmp     rcx, rsi
0x14005aa00  jz      short loc_14005AA31
0x14005aa02  test    dword ptr [rcx+2Ch], 2000000h
0x14005aa09  jz      short loc_14005AA31
0x14005aa0b  mov     edi, 1
0x14005aa10  cmp     [rcx+29h], dil
0x14005aa14  jb      short loc_14005AA31
0x14005aa16  mov     rcx, [rcx+18h]
0x14005aa1a  lea     edx, [rdi+9]
0x14005aa1d  mov     dword ptr [rsp+108h+Arg1], r8d
0x14005aa22  mov     r9, rbx
0x14005aa25  lea     r8, WPP_afea1950ba7935c3d0422396ce336f53_Traceguids
0x14005aa2c  call    WPP_SF_qD
0x14005aa31  mov     r9d, 89h
0x14005aa37  lea     r8, aOnecoreBaseFsR_12; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14005aa3e  mov     edx, 0C000000Dh
0x14005aa43  mov     rcx, rbx
0x14005aa46  call    _Smb2SetError
0x14005aa4b  xor     edx, edx
0x14005aa4d  mov     rcx, r14
0x14005aa50  call    Smb2LkmdTelCollectParsingFailureQuerydirHelper
0x14005aa55  xor     eax, eax
0x14005aa57  jmp     loc_14005B196
0x14005aa5c  mov     rbp, [rbp+18h]
0x14005aa60  cmp     word ptr [rbp+40h], 21h ; '!'
0x14005aa65  jz      short loc_14005AAC2
0x14005aa67  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005aa6e  lea     rsi, WPP_GLOBAL_Control
0x14005aa75  mov     edi, 1
0x14005aa7a  cmp     rcx, rsi
0x14005aa7d  jz      short loc_14005AAA4
0x14005aa7f  test    dword ptr [rcx+2Ch], 2000000h
0x14005aa86  jz      short loc_14005AAA4
0x14005aa88  cmp     [rcx+29h], dil
0x14005aa8c  jb      short loc_14005AAA4
0x14005aa8e  mov     rcx, [rcx+18h]
0x14005aa92  lea     edx, [rdi+0Ah]
0x14005aa95  mov     r9, rbx
0x14005aa98  lea     r8, WPP_afea1950ba7935c3d0422396ce336f53_Traceguids
0x14005aa9f  call    WPP_SF_q
0x14005aaa4  mov     r9d, 99h
0x14005aaaa  lea     r8, aOnecoreBaseFsR_12; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14005aab1  mov     edx, 0C000000Dh
0x14005aab6  mov     rcx, rbx
0x14005aab9  call    _Smb2SetError
0x14005aabe  mov     edx, edi
0x14005aac0  jmp     short loc_14005AA4D
0x14005aac2  mov     rax, [rcx+60h]
0x14005aac6  xor     r12d, r12d
0x14005aac9  mov     rdx, [rbp+28h]
0x14005aacd  xor     r9d, r9d
0x14005aad0  mov     byte ptr [rsp+108h+Arg2], r12b
0x14005aad5  mov     r8, rbp
0x14005aad8  mov     r13, [rax+1F0h]
0x14005aadf  lea     edi, [r12+1]
0x14005aae4  mov     byte ptr [rsp+108h+Arg1], dil
0x14005aae9  call    Smb2VerifySessionExEx
0x14005aaee  mov     r15d, eax
0x14005aaf1  test    eax, eax
0x14005aaf3  jns     short loc_14005AB4A
0x14005aaf5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005aafc  lea     rsi, WPP_GLOBAL_Control
0x14005ab03  cmp     rcx, rsi
0x14005ab06  jz      short loc_14005AB2D
0x14005ab08  test    dword ptr [rcx+2Ch], 2000000h
0x14005ab0f  jz      short loc_14005AB2D
0x14005ab11  cmp     [rcx+29h], dil
0x14005ab15  jb      short loc_14005AB2D
0x14005ab17  mov     rcx, [rcx+18h]
0x14005ab1b  lea     edx, [rdi+0Bh]
0x14005ab1e  mov     r9, rbx
0x14005ab21  lea     r8, WPP_afea1950ba7935c3d0422396ce336f53_Traceguids
0x14005ab28  call    WPP_SF_q
0x14005ab2d  mov     r9d, 0A8h
0x14005ab33  mov     edx, r15d
0x14005ab36  lea     r8, aOnecoreBaseFsR_12; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14005ab3d  mov     rcx, rbx
0x14005ab40  call    _Smb2SetError
0x14005ab45  jmp     loc_14005AA55
0x14005ab4a  movups  xmm0, xmmword ptr [rbp+48h]
0x14005ab4e  mov     r9b, dil
0x14005ab51  lea     rdx, [rsp+108h+var_58]
0x14005ab59  mov     r8, rbp
0x14005ab5c  mov     rcx, rbx; BugCheckParameter4
0x14005ab5f  movdqu  [rsp+108h+var_58], xmm0
0x14005ab68  call    Smb2VerifyFileEx
0x14005ab6d  lea     rsi, WPP_GLOBAL_Control
0x14005ab74  mov     r15d, eax
0x14005ab77  test    eax, eax
0x14005ab79  jns     short loc_14005ABB7
0x14005ab7b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005ab82  cmp     rcx, rsi
0x14005ab85  jz      short loc_14005ABAE
0x14005ab87  test    dword ptr [rcx+2Ch], 800000h
0x14005ab8e  jz      short loc_14005ABAE
0x14005ab90  cmp     [rcx+29h], dil
0x14005ab94  jb      short loc_14005ABAE
0x14005ab96  movzx   r9d, word ptr [rbp+0Ch]
0x14005ab9b  mov     edx, 5Bh ; '['
0x14005aba0  mov     rcx, [rcx+18h]
0x14005aba4  mov     [rsp+108h+Arg1], rbx
0x14005aba9  call    WPP_SF_hq
0x14005abae  cmp     r15d, 0C0000128h
0x14005abb5  jnz     short loc_14005AC28
0x14005abb7  mov     edx, [rbp+24h]
0x14005abba  mov     r8, rbp
0x14005abbd  mov     rcx, rbx
0x14005abc0  call    Smb2VerifyTreeConnect_Old
0x14005abc5  mov     r12d, eax
0x14005abc8  test    eax, eax
0x14005abca  jns     short loc_14005AC01
0x14005abcc  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005abd3  cmp     rcx, rsi
0x14005abd6  jz      short loc_14005AC30
0x14005abd8  test    dword ptr [rcx+2Ch], 800000h
0x14005abdf  jz      short loc_14005AC30
0x14005abe1  cmp     [rcx+29h], dil
0x14005abe5  jb      short loc_14005AC30
0x14005abe7  movzx   r9d, word ptr [rbp+0Ch]
0x14005abec  mov     edx, 5Ch ; '\'
0x14005abf1  mov     rcx, [rcx+18h]
0x14005abf5  mov     [rsp+108h+Arg1], rbx
0x14005abfa  call    WPP_SF_hq
0x14005abff  jmp     short loc_14005AC30
0x14005ac01  xor     r12d, r12d
0x14005ac04  cmp     r15d, 0C0000128h
0x14005ac0b  jnz     short loc_14005AC28
0x14005ac0d  mov     rax, [rbx+230h]
0x14005ac14  mov     rcx, [rax+38h]
0x14005ac18  cmp     [rcx+9Ah], r12b
0x14005ac1f  jz      short loc_14005AC28
0x14005ac21  mov     [rbx+1DAh], dil
0x14005ac28  test    r15d, r15d
0x14005ac2b  jns     short loc_14005AC3E
0x14005ac2d  mov     r12d, r15d
0x14005ac30  mov     r9d, 0B2h
0x14005ac36  mov     edx, r12d
0x14005ac39  jmp     loc_14005AB36
0x14005ac3e  movzx   ecx, word ptr [rbp+5Ah]
0x14005ac42  mov     r15d, 0C000000Dh
0x14005ac48  test    cx, cx
0x14005ac4b  jz      loc_14005AD50
0x14005ac51  movzx   edx, word ptr [rbp+58h]
0x14005ac55  lea     rax, [rdx-60h]
0x14005ac59  cmp     rax, 40h ; '@'
0x14005ac5d  ja      loc_14005ACFB
0x14005ac63  lea     r9, [rdx+rcx]
0x14005ac67  mov     r8d, ecx
0x14005ac6a  cmp     r9, rdx
0x14005ac6d  jb      short loc_14005AC8D
0x14005ac6f  mov     rax, [rbx+130h]
0x14005ac76  mov     ecx, [rax+24h]
0x14005ac79  cmp     r9, rcx
0x14005ac7c  ja      short loc_14005AC8D
0x14005ac7e  lea     eax, [rdx+rbp]
0x14005ac81  and     al, dil
0x14005ac84  neg     al
0x14005ac86  sbb     eax, eax
0x14005ac88  and     eax, r15d
0x14005ac8b  jmp     short loc_14005AC90
0x14005ac8d  mov     eax, r15d
0x14005ac90  test    eax, eax
0x14005ac92  js      short loc_14005ACFB
0x14005ac94  cmp     r8, 0FFFEh
0x14005ac9b  ja      short loc_14005ACA6
0x14005ac9d  test    dil, r8b
0x14005aca0  jz      loc_14005AD50
0x14005aca6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005acad  cmp     rcx, rsi
0x14005acb0  jz      short loc_14005ACD9
0x14005acb2  test    dword ptr [rcx+2Ch], 2000000h
0x14005acb9  jz      short loc_14005ACD9
0x14005acbb  cmp     [rcx+29h], dil
0x14005acbf  jb      short loc_14005ACD9
0x14005acc1  mov     rcx, [rcx+18h]
0x14005acc5  lea     r8, WPP_afea1950ba7935c3d0422396ce336f53_Traceguids
0x14005accc  mov     edx, 0Eh
0x14005acd1  mov     r9, rbx
0x14005acd4  call    WPP_SF_q
0x14005acd9  mov     r9d, 0DDh
0x14005acdf  lea     r8, aOnecoreBaseFsR_12; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14005ace6  mov     edx, r15d
0x14005ace9  mov     rcx, rbx
0x14005acec  call    _Smb2SetError
0x14005acf1  mov     edx, 3
0x14005acf6  jmp     loc_14005AA4D
0x14005acfb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005ad02  cmp     rcx, rsi
0x14005ad05  jz      short loc_14005AD2E
0x14005ad07  test    dword ptr [rcx+2Ch], 2000000h
0x14005ad0e  jz      short loc_14005AD2E
0x14005ad10  cmp     [rcx+29h], dil
0x14005ad14  jb      short loc_14005AD2E
0x14005ad16  mov     rcx, [rcx+18h]
0x14005ad1a  lea     r8, WPP_afea1950ba7935c3d0422396ce336f53_Traceguids
0x14005ad21  mov     edx, 0Dh
0x14005ad26  mov     r9, rbx
0x14005ad29  call    WPP_SF_q
0x14005ad2e  mov     r9d, 0CCh
0x14005ad34  lea     r8, aOnecoreBaseFsR_12; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14005ad3b  mov     edx, r15d
0x14005ad3e  mov     rcx, rbx
0x14005ad41  call    _Smb2SetError
0x14005ad46  mov     edx, 2
0x14005ad4b  jmp     loc_14005AA4D
0x14005ad50  mov     ecx, [rbp+5Ch]
0x14005ad53  cmp     ecx, [r13+24h]
0x14005ad57  jbe     short loc_14005ADAE
0x14005ad59  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005ad60  cmp     rcx, rsi
0x14005ad63  jz      short loc_14005AD8C
0x14005ad65  test    dword ptr [rcx+2Ch], 2000000h
0x14005ad6c  jz      short loc_14005AD8C
0x14005ad6e  cmp     [rcx+29h], dil
0x14005ad72  jb      short loc_14005AD8C
0x14005ad74  mov     rcx, [rcx+18h]
0x14005ad78  lea     r8, WPP_afea1950ba7935c3d0422396ce336f53_Traceguids
0x14005ad7f  mov     edx, 0Fh
0x14005ad84  mov     r9, rbx
0x14005ad87  call    WPP_SF_q
0x14005ad8c  mov     r9d, 0ECh
0x14005ad92  lea     r8, aOnecoreBaseFsR_12; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14005ad99  mov     edx, r15d
0x14005ad9c  mov     rcx, rbx
0x14005ad9f  call    _Smb2SetError
0x14005ada4  mov     edx, 4
0x14005ada9  jmp     loc_14005AA4D
0x14005adae  test    byte ptr [r13+31h], 2
0x14005adb3  jz      short loc_14005AE30
0x14005adb5  test    ecx, ecx
0x14005adb7  jz      short loc_14005ADC2
0x14005adb9  dec     ecx
0x14005adbb  shr     ecx, 10h
0x14005adbe  add     ecx, edi
0x14005adc0  jmp     short loc_14005ADC4
0x14005adc2  mov     ecx, edi
0x14005adc4  movzx   r8d, word ptr [rbx+1E8h]
0x14005adcc  cmp     r8d, ecx
0x14005adcf  jnb     short loc_14005AE30
0x14005add1  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005add8  cmp     r10, rsi
0x14005addb  jz      short loc_14005AE0E
0x14005addd  test    dword ptr [r10+2Ch], 2000000h
0x14005ade5  jz      short loc_14005AE0E
0x14005ade7  cmp     [r10+29h], dil
0x14005adeb  jb      short loc_14005AE0E
0x14005aded  mov     dword ptr [rsp+108h+Arg2], ecx
0x14005adf1  mov     edx, 10h
0x14005adf6  mov     rcx, [r10+18h]
0x14005adfa  mov     r9, rbx
0x14005adfd  mov     dword ptr [rsp+108h+Arg1], r8d
0x14005ae02  lea     r8, WPP_afea1950ba7935c3d0422396ce336f53_Traceguids
0x14005ae09  call    WPP_SF_qDD
0x14005ae0e  mov     r9d, 107h
0x14005ae14  lea     r8, aOnecoreBaseFsR_12; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14005ae1b  mov     edx, r15d
0x14005ae1e  mov     rcx, rbx
0x14005ae21  call    _Smb2SetError
0x14005ae26  mov     edx, 5
0x14005ae2b  jmp     loc_14005AA4D
0x14005ae30  movzx   ecx, byte ptr [rbp+42h]
0x14005ae34  cmp     cl, 54h ; 'T'
0x14005ae37  jb      short loc_14005AE7C
0x14005ae39  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005ae40  cmp     rcx, rsi
0x14005ae43  jz      short loc_14005AE6C
0x14005ae45  test    dword ptr [rcx+2Ch], 2000000h
0x14005ae4c  jz      short loc_14005AE6C
0x14005ae4e  cmp     [rcx+29h], dil
0x14005ae52  jb      short loc_14005AE6C
0x14005ae54  mov     rcx, [rcx+18h]
0x14005ae58  lea     r8, WPP_afea1950ba7935c3d0422396ce336f53_Traceguids
0x14005ae5f  mov     edx, 11h
0x14005ae64  mov     r9, rbx
0x14005ae67  call    WPP_SF_q
0x14005ae6c  mov     r9d, 119h
0x14005ae72  mov     edx, 0C0000003h
0x14005ae77  jmp     loc_14005AB36
0x14005ae7c  mov     rax, rcx
0x14005ae7f  mov     [r14+0D8h], ecx
0x14005ae86  lea     rdx, cs:140000000h
0x14005ae8d  mov     ecx, ds:rva MinimumOutputBufferSizeTable[rdx+rcx*4]
0x14005ae94  mov     [r14+0DCh], ecx
  ... truncated ...
```
