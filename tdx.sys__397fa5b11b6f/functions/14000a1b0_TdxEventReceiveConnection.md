# TdxEventReceiveConnection

- ea: `0x14000a1b0`
- end: `0x14000a5e4`
- name: `TdxEventReceiveConnection`
- size: `1076`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140009ad0`
- `0x14000a1b0`
- `0x140013dc0`
- `0x140013e60`
- `0x1400184b0`
- `0x140018590`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000a4c4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000a4c4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a20d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a3a8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a20d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a3a8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a2f3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a3cc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a408`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a45b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a583`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a2f3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a3cc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a408`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a45b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a583`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x14000a56f`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x14000a56f`

## pseudocode

```c
__int64 __fastcall TdxEventReceiveConnection(__int64 a1, int *a2)
{
  KIRQL v4; // al
  int v5; // r8d
  KIRQL v6; // r14
  int v7; // edx
  int v8; // r8d
  __int64 (__fastcall *v9)(__int64, __int64, _QWORD, _QWORD, _QWORD, unsigned int *, char *, __int64 *); // r13
  int v10; // ecx
  int v11; // eax
  __int64 v12; // rax
  __int64 v13; // r10
  unsigned __int64 v14; // r12
  char *v15; // r15
  char *v16; // r14
  unsigned int v17; // r14d
  KIRQL v18; // dl
  __int64 v19; // rax
  __int64 v21; // rax
  __int64 v22; // rcx
  ULONG BugCheckOnFailure[2]; // [rsp+20h] [rbp-E0h]
  unsigned int v24; // [rsp+50h] [rbp-B0h] BYREF
  KIRQL v25[4]; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v26; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v27; // [rsp+60h] [rbp-A0h]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int64 v29; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+78h] [rbp-88h]
  _OWORD v31[8]; // [rsp+80h] [rbp-80h] BYREF

  v24 = 0;
  v26 = 0;
  memset(v31, 0, sizeof(v31));
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
  v6 = v4;
  if ( (*(_DWORD *)a1 & 0x80u) != 0 || *(_QWORD *)(a1 + 296) )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v4);
    return 3221226011LL;
  }
  else
  {
    *(_QWORD *)(a1 + 296) = *((_QWORD *)a2 + 3);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_sqd(WPP_GLOBAL_Control->AttachedDevice, 30, v5, (unsigned int)"TdxEventReceiveConnection", a1, a2[6]);
    }
    v7 = *a2;
    v30 = *(_QWORD *)(a1 + 80);
    if ( (v7 & 1) != 0 )
    {
      v9 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _QWORD, unsigned int *, char *, __int64 *))(a1 + 352);
      v8 = 64;
      if ( v9 )
      {
        v21 = 360;
      }
      else
      {
        v9 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _QWORD, unsigned int *, char *, __int64 *))(a1 + 336);
        v21 = 344;
      }
      v28 = *(_QWORD *)(v21 + a1);
    }
    else
    {
      v8 = 32;
      v9 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _QWORD, unsigned int *, char *, __int64 *))(a1 + 336);
      v28 = *(_QWORD *)(a1 + 344);
    }
    v10 = v8 | 0x400;
    if ( (v7 & 2) == 0 )
      v10 = v8;
    v11 = v10 | 0x800;
    if ( (*(_BYTE *)a2 & 8) == 0 )
      v11 = v10;
    v27 = v11;
    v12 = *((_QWORD *)a2 + 2);
    v13 = *(_QWORD *)(v12 + 8);
    v14 = *(_QWORD *)(v12 + 24);
    if ( v14 >= (unsigned int)(*(_DWORD *)(v13 + 40) - *(_DWORD *)(v12 + 16)) )
      LODWORD(v14) = *(_DWORD *)(v13 + 40) - *(_DWORD *)(v12 + 16);
    if ( (*(_BYTE *)(v13 + 10) & 5) != 0 )
      v15 = *(char **)(v13 + 24);
    else
      v15 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v13, 0, MmCached, 0, 0, 0x40000000u);
    if ( v15 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v6);
      v16 = &v15[*(unsigned int *)(*((_QWORD *)a2 + 2) + 16LL)];
    }
    else
    {
      v22 = *((_QWORD *)a2 + 2);
      v29 = 0;
      if ( (unsigned int)v14 > 0x80 )
        LODWORD(v14) = 128;
      RtlCopyMdlToKernelBuffer(*(_QWORD *)(v22 + 8), *(unsigned int *)(v22 + 16), v31, (unsigned int)v14, &v29);
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v6);
      v16 = (char *)v31;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      BugCheckOnFailure[1] = HIDWORD(a1);
      WPP_SF_sqddq(WPP_GLOBAL_Control->AttachedDevice, 31);
    }
    if ( v9 )
    {
      BugCheckOnFailure[0] = a2[6];
      v17 = v9(v28, v30, v27, (unsigned int)v14, *(_QWORD *)BugCheckOnFailure, &v24, v16, &v26);
    }
    else
    {
      v17 = -1073741285;
      v24 = 0;
      v26 = 0;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_sqddq(WPP_GLOBAL_Control->AttachedDevice, 32);
    }
    v25[0] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
    v18 = v25[0];
    if ( v17 == -1073741285 )
    {
      v24 = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v25[0]);
      v19 = v24;
    }
    else
    {
      *(_QWORD *)(a1 + 296) -= v24;
      if ( v17 == -1073741802 )
      {
        TdxReceiveConnection(a1, v26, *(_QWORD *)(v26 + 184), v25);
        v17 = 0;
      }
      else
      {
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v18);
      }
      v19 = v24;
      if ( !v24 )
        v17 = -1073741285;
    }
    *((_QWORD *)a2 + 4) = v19;
    return v17;
  }
}

```

## disassembly

```asm
0x14000a1b0  push    rbp
0x14000a1b2  push    rbx
0x14000a1b3  push    rsi
0x14000a1b4  push    rdi
0x14000a1b5  push    r14
0x14000a1b7  push    r15
0x14000a1b9  lea     rbp, [rsp-18h]
0x14000a1be  sub     rsp, 118h
0x14000a1c5  mov     rax, cs:__security_cookie
0x14000a1cc  xor     rax, rsp
0x14000a1cf  mov     [rbp+40h+var_40], rax
0x14000a1d3  xorps   xmm0, xmm0
0x14000a1d6  mov     rbx, rcx
0x14000a1d9  xor     r15d, r15d
0x14000a1dc  add     rcx, 8; SpinLock
0x14000a1e0  mov     [rsp+140h+var_F0], r15d
0x14000a1e5  mov     rsi, rdx
0x14000a1e8  mov     [rsp+140h+var_E8], r15
0x14000a1ed  movups  [rbp+40h+var_C0], xmm0
0x14000a1f1  movups  [rbp+40h+var_B0], xmm0
0x14000a1f5  movups  [rbp+40h+var_A0], xmm0
0x14000a1f9  movups  [rbp+40h+var_90], xmm0
0x14000a1fd  movups  [rbp+40h+var_80], xmm0
0x14000a201  movups  [rbp+40h+var_70], xmm0
0x14000a205  movups  [rbp+40h+var_60], xmm0
0x14000a209  movups  [rbp+40h+var_50], xmm0
0x14000a20d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000a214  nop     dword ptr [rax+rax+00h]
0x14000a219  mov     ecx, [rbx]
0x14000a21b  movzx   r14d, al
0x14000a21f  test    cl, cl
0x14000a221  js      loc_14000A400
0x14000a227  cmp     [rbx+128h], r15
0x14000a22e  jnz     loc_14000A400
0x14000a234  mov     rcx, [rsi+18h]
0x14000a238  mov     [rsp+140h+arg_10], r12
0x14000a240  mov     [rbx+128h], rcx
0x14000a247  mov     [rsp+140h+var_30], r13
0x14000a24f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a256  lea     rax, WPP_GLOBAL_Control
0x14000a25d  cmp     rcx, rax
0x14000a260  jz      short loc_14000A26C
0x14000a262  cmp     byte ptr [rcx+29h], 5
0x14000a266  jnb     loc_14000A4D8
0x14000a26c  mov     rax, [rbx+50h]
0x14000a270  mov     edx, [rsi]
0x14000a272  mov     [rsp+140h+var_C8], rax
0x14000a277  test    dl, 1
0x14000a27a  jnz     loc_14000A50B
0x14000a280  mov     r9, [rbx+158h]
0x14000a287  mov     r8d, 20h ; ' '
0x14000a28d  mov     r13, [rbx+150h]
0x14000a294  mov     [rsp+140h+var_D8], r9
0x14000a299  mov     ecx, r8d
0x14000a29c  bts     ecx, 0Ah
0x14000a2a0  test    dl, 2
0x14000a2a3  cmovz   ecx, r8d
0x14000a2a7  mov     eax, ecx
0x14000a2a9  bts     eax, 0Bh
0x14000a2ad  test    byte ptr [rsi], 8
0x14000a2b0  cmovz   eax, ecx
0x14000a2b3  mov     [rsp+140h+var_E0], eax
0x14000a2b7  mov     rax, [rsi+10h]
0x14000a2bb  mov     r10, [rax+8]
0x14000a2bf  mov     r12, [rax+18h]
0x14000a2c3  mov     ecx, [r10+28h]
0x14000a2c7  sub     ecx, [rax+10h]
0x14000a2ca  mov     eax, ecx
0x14000a2cc  cmp     r12, rax
0x14000a2cf  cmovnb  r12d, ecx
0x14000a2d3  test    byte ptr [r10+0Ah], 5
0x14000a2d8  jz      loc_14000A4A9
0x14000a2de  mov     r15, [r10+18h]
0x14000a2e2  test    r15, r15
0x14000a2e5  jz      loc_14000A53E
0x14000a2eb  movzx   edx, r14b; NewIrql
0x14000a2ef  lea     rcx, [rbx+8]; SpinLock
0x14000a2f3  call    cs:__imp_KeReleaseSpinLock
0x14000a2fa  nop     dword ptr [rax+rax+00h]
0x14000a2ff  mov     rax, [rsi+10h]
0x14000a303  mov     r14d, [rax+10h]
0x14000a307  add     r14, r15
0x14000a30a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a311  lea     rax, WPP_GLOBAL_Control
0x14000a318  cmp     rcx, rax
0x14000a31b  jnz     loc_14000A469
0x14000a321  mov     r15d, 0C000021Bh
0x14000a327  test    r13, r13
0x14000a32a  jz      loc_14000A598
0x14000a330  mov     ecx, [rsi+18h]
0x14000a333  lea     rax, [rsp+140h+var_E8]
0x14000a338  mov     r8d, [rsp+140h+var_E0]
0x14000a33d  mov     r9d, r12d
0x14000a340  mov     rdx, [rsp+140h+var_C8]
0x14000a345  mov     [rsp+140h+var_108], rax
0x14000a34a  lea     rax, [rsp+140h+var_F0]
0x14000a34f  mov     [rsp+140h+var_110], r14
0x14000a354  mov     qword ptr [rsp+140h+Priority], rax
0x14000a359  mov     rax, r13
0x14000a35c  mov     [rsp+140h+BugCheckOnFailure], ecx
0x14000a360  mov     rcx, [rsp+140h+var_D8]
0x14000a365  call    _guard_dispatch_icall
0x14000a36a  mov     r8d, [rsp+140h+var_F0]
0x14000a36f  mov     r14d, eax
0x14000a372  mov     r9, [rsp+140h+var_E8]
0x14000a377  mov     rax, cs:WPP_GLOBAL_Control
0x14000a37e  lea     rcx, WPP_GLOBAL_Control
0x14000a385  mov     r13, [rsp+140h+var_30]
0x14000a38d  mov     r12, [rsp+140h+arg_10]
0x14000a395  cmp     rax, rcx
0x14000a398  jz      short loc_14000A3A4
0x14000a39a  cmp     byte ptr [rax+29h], 5
0x14000a39e  jnb     loc_14000A5B0
0x14000a3a4  lea     rcx, [rbx+8]; SpinLock
0x14000a3a8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000a3af  nop     dword ptr [rax+rax+00h]
0x14000a3b4  mov     [rsp+140h+var_EC], al
0x14000a3b8  movzx   edx, al; NewIrql
0x14000a3bb  cmp     r14d, r15d
0x14000a3be  jnz     short loc_14000A41B
0x14000a3c0  lea     rcx, [rbx+8]; SpinLock
0x14000a3c4  mov     [rsp+140h+var_F0], 0
0x14000a3cc  call    cs:__imp_KeReleaseSpinLock
0x14000a3d3  nop     dword ptr [rax+rax+00h]
0x14000a3d8  mov     eax, [rsp+140h+var_F0]
0x14000a3dc  mov     [rsi+20h], rax
0x14000a3e0  mov     eax, r14d
0x14000a3e3  mov     rcx, [rbp+40h+var_40]
0x14000a3e7  xor     rcx, rsp; StackCookie
0x14000a3ea  call    __security_check_cookie
0x14000a3ef  add     rsp, 118h
0x14000a3f6  pop     r15
0x14000a3f8  pop     r14
0x14000a3fa  pop     rdi
0x14000a3fb  pop     rsi
0x14000a3fc  pop     rbx
0x14000a3fd  pop     rbp
0x14000a3fe  retn
0x14000a400  movzx   edx, r14b; NewIrql
0x14000a404  lea     rcx, [rbx+8]; SpinLock
0x14000a408  call    cs:__imp_KeReleaseSpinLock
0x14000a40f  nop     dword ptr [rax+rax+00h]
0x14000a414  mov     eax, 0C000021Bh
0x14000a419  jmp     short loc_14000A3E3
0x14000a41b  mov     eax, [rsp+140h+var_F0]
0x14000a41f  sub     [rbx+128h], rax
0x14000a426  cmp     r14d, 0C0000016h
0x14000a42d  jnz     short loc_14000A457
0x14000a42f  mov     rdx, [rsp+140h+var_E8]
0x14000a434  lea     r9, [rsp+140h+var_EC]
0x14000a439  mov     rcx, rbx
0x14000a43c  mov     r8, [rdx+0B8h]
0x14000a443  call    TdxReceiveConnection
0x14000a448  xor     r14d, r14d
0x14000a44b  mov     eax, [rsp+140h+var_F0]
0x14000a44f  test    eax, eax
0x14000a451  cmovz   r14d, r15d
0x14000a455  jmp     short loc_14000A3DC
0x14000a457  lea     rcx, [rbx+8]; SpinLock
0x14000a45b  call    cs:__imp_KeReleaseSpinLock
0x14000a462  nop     dword ptr [rax+rax+00h]
0x14000a467  jmp     short loc_14000A44B
0x14000a469  cmp     byte ptr [rcx+29h], 5
0x14000a46d  jb      loc_14000A321
0x14000a473  test    dword ptr [rcx+2Ch], 200h
0x14000a47a  jz      loc_14000A321
0x14000a480  mov     eax, [rsi+18h]
0x14000a483  mov     edx, 1Fh
0x14000a488  mov     rcx, [rcx+18h]
0x14000a48c  mov     [rsp+140h+var_108], r13
0x14000a491  mov     dword ptr [rsp+140h+var_110], eax
0x14000a495  mov     [rsp+140h+Priority], r12d
0x14000a49a  mov     qword ptr [rsp+140h+BugCheckOnFailure], rbx
0x14000a49f  call    WPP_SF_sqddq
0x14000a4a4  jmp     loc_14000A321
0x14000a4a9  mov     [rsp+140h+Priority], 40000000h; Priority
0x14000a4b1  xor     r9d, r9d; RequestedAddress
0x14000a4b4  xor     edx, edx; AccessMode
0x14000a4b6  mov     [rsp+140h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x14000a4bb  mov     r8d, 1; CacheType
0x14000a4c1  mov     rcx, r10; MemoryDescriptorList
0x14000a4c4  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000a4cb  nop     dword ptr [rax+rax+00h]
0x14000a4d0  mov     r15, rax
0x14000a4d3  jmp     loc_14000A2E2
0x14000a4d8  test    dword ptr [rcx+2Ch], 200h
0x14000a4df  jz      loc_14000A26C
0x14000a4e5  mov     eax, [rsi+18h]
0x14000a4e8  lea     r9, aTdxeventreceiv; "TdxEventReceiveConnection"
0x14000a4ef  mov     rcx, [rcx+18h]
0x14000a4f3  mov     edx, 1Eh
0x14000a4f8  mov     [rsp+140h+Priority], eax
0x14000a4fc  mov     qword ptr [rsp+140h+BugCheckOnFailure], rbx
0x14000a501  call    WPP_SF_sqd
0x14000a506  jmp     loc_14000A26C
0x14000a50b  mov     r13, [rbx+160h]
0x14000a512  mov     r8d, 40h ; '@'
0x14000a518  test    r13, r13
0x14000a51b  jnz     short loc_14000A52B
0x14000a51d  mov     r13, [rbx+150h]
0x14000a524  mov     eax, 158h
0x14000a529  jmp     short loc_14000A530
0x14000a52b  mov     eax, 168h
0x14000a530  mov     rax, [rax+rbx]
0x14000a534  mov     [rsp+140h+var_D8], rax
0x14000a539  jmp     loc_14000A299
0x14000a53e  mov     rcx, [rsi+10h]
0x14000a542  lea     r8, [rbp+40h+var_C0]
0x14000a546  mov     eax, 80h
0x14000a54b  mov     [rsp+140h+var_D0], 0
0x14000a554  cmp     r12d, eax
0x14000a557  mov     edx, [rcx+10h]
0x14000a55a  cmova   r12d, eax
0x14000a55e  mov     rcx, [rcx+8]
0x14000a562  lea     rax, [rsp+140h+var_D0]
0x14000a567  mov     r9d, r12d
0x14000a56a  mov     qword ptr [rsp+140h+BugCheckOnFailure], rax
0x14000a56f  call    cs:__imp_RtlCopyMdlToKernelBuffer
0x14000a576  nop     dword ptr [rax+rax+00h]
0x14000a57b  movzx   edx, r14b; NewIrql
0x14000a57f  lea     rcx, [rbx+8]; SpinLock
0x14000a583  call    cs:__imp_KeReleaseSpinLock
0x14000a58a  nop     dword ptr [rax+rax+00h]
0x14000a58f  lea     r14, [rbp+40h+var_C0]
0x14000a593  jmp     loc_14000A30A
0x14000a598  xor     r8d, r8d
0x14000a59b  mov     r14d, r15d
0x14000a59e  xor     r9d, r9d
0x14000a5a1  mov     [rsp+140h+var_F0], r8d
0x14000a5a6  mov     [rsp+140h+var_E8], r9
0x14000a5ab  jmp     loc_14000A377
0x14000a5b0  test    dword ptr [rax+2Ch], 200h
0x14000a5b7  jz      loc_14000A3A4
0x14000a5bd  mov     rcx, [rax+18h]
0x14000a5c1  mov     edx, 20h ; ' '
0x14000a5c6  mov     [rsp+140h+var_108], r9
0x14000a5cb  mov     dword ptr [rsp+140h+var_110], r8d
0x14000a5d0  mov     [rsp+140h+Priority], r14d
0x14000a5d5  mov     qword ptr [rsp+140h+BugCheckOnFailure], rbx
0x14000a5da  call    WPP_SF_sqddq
0x14000a5df  jmp     loc_14000A3A4
```
