# WinHvpSpecialListRepHypercall

- ea: `0x140003b70`
- end: `0x1400040b4`
- name: `WinHvpSpecialListRepHypercall`
- size: `1348`
- prototype: `__int64 __fastcall(int, unsigned __int64, const void *, unsigned int, _QWORD *, __int64, char *, unsigned int, void (__fastcall *)(char *, char *, _QWORD), __int64 (__fastcall *)(char *, _QWORD), char *, unsigned int, void (__fastcall *)(const void *, char *, _QWORD), _BYTE *, _QWORD *)`
- caller_count: `25`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140003750`
- `0x1400037d0`
- `0x140003910`
- `0x140003a50`
- `0x140003ae0`
- `0x1400047f0`
- `0x140004c40`
- `0x140004cc0`
- `0x140004da0`
- `0x140004e40`
- `0x140004f00`
- `0x140004f80`
- `0x140005000`
- `0x1400050a0`
- `0x1400052b0`
- `0x140005330`
- `0x140008a20`
- `0x140008b70`
- `0x14001b570`
- `0x14001da70`
- `0x14001fc90`
- `0x140020d80`
- `0x1400231a4`
- `0x140023a70`
- `0x14002670c`

## callees

- `0x140003b70`
- `0x140009c90`
- `0x140009d40`
- `0x14000a040`
- `0x14001b350`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140003c4a`
- `ntoskrnl!KeGetCurrentIrql` at `0x140003fe5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140003c4a`
- `ntoskrnl!KeGetCurrentIrql` at `0x140003fe5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140003c8b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140003c8b`
- `ntoskrnl!ExAcquireFastMutex` at `0x140003fff`
- `ntoskrnl!ExAcquireFastMutex` at `0x140003fff`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000401b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000401b`
- `ntoskrnl!HvlInvokeHypercall` at `0x140003d83`
- `ntoskrnl!HvlInvokeHypercall` at `0x140003d83`

## pseudocode

```c
__int64 __fastcall WinHvpSpecialListRepHypercall(
        int a1,
        unsigned __int64 a2,
        const void *a3,
        unsigned int a4,
        _QWORD *a5,
        __int64 a6,
        char *a7,
        unsigned int a8,
        void (__fastcall *a9)(char *, char *, _QWORD),
        __int64 (__fastcall *a10)(char *, _QWORD),
        char *a11,
        unsigned int a12,
        void (__fastcall *a13)(const void *, char *, _QWORD),
        _BYTE *a14,
        _QWORD *a15)
{
  size_t v16; // r12
  unsigned int v17; // ecx
  unsigned int v18; // r8d
  unsigned int v19; // eax
  unsigned int v20; // edi
  _BYTE *v21; // rbx
  char *v22; // r15
  const void *v23; // r13
  unsigned __int16 v24; // dx
  struct _NPAGED_LOOKASIDE_LIST *v25; // rcx
  __int64 *v26; // rax
  unsigned int v27; // eax
  unsigned int v28; // ebp
  unsigned int v29; // esi
  _QWORD *v30; // rax
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // rax
  unsigned int v34; // edi
  __int64 (__fastcall *v35)(); // rax
  __int64 v36; // rcx
  char *v38; // rcx
  unsigned int v39; // eax
  KIRQL CurrentIrql; // al
  unsigned int v41[4]; // [rsp+30h] [rbp-88h] BYREF
  _BYTE v42[64]; // [rsp+40h] [rbp-78h] BYREF
  unsigned int v44; // [rsp+C8h] [rbp+10h]

  v16 = a4;
  memset(v42, 0, sizeof(v42));
  *a15 = 0;
  if ( !a2 )
    return (unsigned int)(WinHvpConnected != 0) - 1070268414;
  v17 = 4096 - v16;
  if ( a8 )
    v18 = v17 / a8;
  else
    v18 = 4095;
  if ( a12 )
    v19 = 0x1000 / a12;
  else
    v19 = 4095;
  if ( v18 >= v19 )
  {
    if ( a12 )
    {
      v20 = 0x1000 / a12;
      goto LABEL_9;
    }
  }
  else if ( a8 )
  {
    v20 = v17 / a8;
    goto LABEL_9;
  }
  v20 = 4095;
LABEL_9:
  v21 = v42;
  v44 = v20;
  v22 = 0;
  v23 = 0;
  if ( a14 )
    v21 = a14;
  KeGetCurrentIrql();
  while ( 1 )
  {
    if ( !*(_QWORD *)v21 )
    {
      v24 = *(_WORD *)(WinHvpProcessorToNode + 2LL * HIDWORD(KeGetPcr()[1].LockArray));
      *((_WORD *)v21 + 16) = v24;
      v25 = (struct _NPAGED_LOOKASIDE_LIST *)(WinHvpNodeToHypercallLookaside + ((unsigned __int64)v24 << 7));
      *((_QWORD *)v21 + 5) = 0;
      v26 = (__int64 *)ExAllocateFromNPagedLookasideList(v25);
      *((_QWORD *)v21 + 5) = v26;
      *((_QWORD *)v21 + 7) = WinHvpReleasePoolBuffers;
      if ( !v26 )
      {
        CurrentIrql = KeGetCurrentIrql();
        v21[48] = CurrentIrql;
        if ( CurrentIrql >= 2u )
        {
          v21[48] = KeAcquireSpinLockRaiseToDpc(&WinHvpFallbackSpinLock);
          v26 = WinHvpFallbackBuffer;
        }
        else
        {
          ExAcquireFastMutex(&WinHvpFallbackMutex);
          v26 = WinHvpFallbackBuffer2;
        }
        *((_QWORD *)v21 + 5) = v26;
        *((_QWORD *)v21 + 7) = WinHvpReleaseFallbackBuffers;
      }
      v22 = (char *)v26[2];
      *((_QWORD *)v21 + 1) = v22;
      v23 = (const void *)v26[4];
      *((_QWORD *)v21 + 2) = v23;
      *(_QWORD *)v21 = v21;
    }
    v41[0] = 0;
    v27 = -1;
    v28 = 0;
    if ( a2 < 0xFFFFFFFF )
      v27 = a2;
    if ( v20 < v27 )
    {
      v29 = v20;
    }
    else
    {
      v29 = -1;
      if ( a2 < 0xFFFFFFFF )
        v29 = a2;
    }
    if ( (_DWORD)v16 )
      memmove(v22, a3, v16);
    if ( a8 )
    {
      v38 = &v22[v16];
      if ( a9 )
        a9(v38, a7, v29);
      else
        memmove(v38, a7, a8 * v29);
    }
    v30 = *(_QWORD **)v21;
    if ( *(_BYTE *)(*(_QWORD *)v21 + 24LL) )
    {
      v39 = WinHvpSlowHypercallRemote(a1, v29, v30[1], v30[2], (__int64)v41);
      v28 = v41[0];
      v34 = v39;
    }
    else
    {
      if ( v30[2] )
        v31 = *(_QWORD *)(v30[5] + 40LL);
      else
        v31 = 0;
      if ( v30[1] )
        v32 = *(_QWORD *)(v30[5] + 24LL);
      else
        v32 = 0;
      if ( WinHvpConnected )
      {
        v33 = HvlInvokeHypercall(
                -(__int64)(WinHvpNested != 0) & 0x80000000LL
              | (unsigned __int16)a1
              | ((unsigned __int64)(v29 & 0xFFF) << 32),
                v32,
                v31);
        v28 = WORD2(v33) & 0xFFF;
        if ( (_WORD)v33 )
          v34 = (unsigned __int16)v33 | 0xC0350000;
        else
          v34 = 0;
      }
      else
      {
        v34 = -1070264320;
      }
    }
    *a15 += v28;
    if ( v28 > a2 )
      v34 = -2147483643;
    if ( a12 && v28 )
    {
      if ( a13 )
        a13(v23, a11, v28);
      else
        memmove(a11, v23, a12 * v28);
    }
    v35 = (__int64 (__fastcall *)())*((_QWORD *)v21 + 7);
    v36 = *(_QWORD *)v21;
    if ( v35 == WinHvpReleaseFallbackBuffers )
    {
      ((void (__fastcall *)(__int64))v35)(v36);
      v36 = 0;
      *(_QWORD *)v21 = 0;
    }
    if ( v34 )
      break;
    a2 -= v28;
    if ( !a2 )
      break;
    v20 = v44;
    if ( v28 )
    {
      if ( a8 )
      {
        if ( a10 )
          a7 = (char *)a10(a7, v28);
        else
          a7 += a8 * v28;
      }
      if ( a12 && a11 )
        a11 += a12 * v28;
      v20 = v44;
      if ( a5 )
        *a5 += a6 * v28;
    }
  }
  if ( !a14 )
  {
    if ( v36 )
      (*((void (**)(void))v21 + 7))();
  }
  return v34;
}

```

## disassembly

```asm
0x140003b70  mov     [rsp+Src], r8
0x140003b75  mov     [rsp+arg_0], ecx
0x140003b79  push    rsi
0x140003b7a  push    r12
0x140003b7c  push    r14
0x140003b7e  sub     rsp, 0A0h
0x140003b85  mov     r14, rdx
0x140003b88  mov     r12d, r9d
0x140003b8b  xor     edx, edx; Val
0x140003b8d  lea     rcx, [rsp+0B8h+var_78]; void *
0x140003b92  mov     r8d, 40h ; '@'; Size
0x140003b98  call    memset
0x140003b9d  mov     rax, [rsp+0B8h+arg_70]
0x140003ba5  xor     esi, esi
0x140003ba7  mov     [rax], rsi
0x140003baa  test    r14, r14
0x140003bad  jz      loc_140003EEE
0x140003bb3  mov     r9d, [rsp+0B8h+arg_38]
0x140003bbb  mov     ecx, 1000h
0x140003bc0  mov     [rsp+0B8h+arg_18], rbx
0x140003bc8  sub     ecx, r12d
0x140003bcb  mov     [rsp+0B8h+var_20], rbp
0x140003bd3  mov     [rsp+0B8h+var_28], rdi
0x140003bdb  mov     [rsp+0B8h+var_30], r13
0x140003be3  mov     [rsp+0B8h+var_38], r15
0x140003beb  test    r9d, r9d
0x140003bee  jnz     loc_140003E91
0x140003bf4  mov     r8d, 0FFFh
0x140003bfa  mov     edi, [rsp+0B8h+arg_58]
0x140003c01  test    edi, edi
0x140003c03  jz      loc_140003F1A
0x140003c09  xor     edx, edx
0x140003c0b  mov     eax, 1000h
0x140003c10  div     edi
0x140003c12  cmp     r8d, eax
0x140003c15  jnb     loc_140003EC8
0x140003c1b  test    r9d, r9d
0x140003c1e  jnz     loc_140003EE0
0x140003c24  mov     edi, 0FFFh
0x140003c29  mov     rax, [rsp+0B8h+arg_68]
0x140003c31  lea     rbx, [rsp+0B8h+var_78]
0x140003c36  test    rax, rax
0x140003c39  mov     [rsp+0B8h+arg_8], edi
0x140003c40  mov     r15, rsi
0x140003c43  mov     r13, rsi
0x140003c46  cmovnz  rbx, rax
0x140003c4a  call    cs:__imp_KeGetCurrentIrql
0x140003c51  nop     dword ptr [rax+rax+00h]
0x140003c56  mov     ecx, 0FFFFFFFFh
0x140003c5b  cmp     qword ptr [rbx], 0
0x140003c5f  jnz     short loc_140003CC7
0x140003c61  mov     eax, gs:1A4h
0x140003c69  mov     ecx, eax
0x140003c6b  mov     rax, cs:WinHvpProcessorToNode
0x140003c72  movzx   edx, word ptr [rax+rcx*2]
0x140003c76  mov     ecx, edx
0x140003c78  mov     [rbx+20h], dx
0x140003c7c  shl     rcx, 7
0x140003c80  add     rcx, cs:WinHvpNodeToHypercallLookaside; Lookaside
0x140003c87  mov     [rbx+28h], rsi
0x140003c8b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140003c92  nop     dword ptr [rax+rax+00h]
0x140003c97  mov     [rbx+28h], rax
0x140003c9b  lea     rcx, WinHvpReleasePoolBuffers
0x140003ca2  mov     [rbx+38h], rcx
0x140003ca6  test    rax, rax
0x140003ca9  jz      loc_140003FE5
0x140003caf  mov     r15, [rax+10h]
0x140003cb3  mov     ecx, 0FFFFFFFFh
0x140003cb8  mov     [rbx+8], r15
0x140003cbc  mov     r13, [rax+20h]
0x140003cc0  mov     [rbx+10h], r13
0x140003cc4  mov     [rbx], rbx
0x140003cc7  cmp     r14, rcx
0x140003cca  mov     [rsp+0B8h+var_88], esi
0x140003cce  mov     rax, rcx
0x140003cd1  mov     ebp, esi
0x140003cd3  cmovb   rax, r14
0x140003cd7  cmp     edi, eax
0x140003cd9  jb      loc_140003E67
0x140003cdf  cmp     r14, rcx
0x140003ce2  mov     esi, ecx
0x140003ce4  cmovb   esi, r14d
0x140003ce8  mov     rdi, r12
0x140003ceb  test    r12d, r12d
0x140003cee  jz      short loc_140003D03
0x140003cf0  mov     rdx, [rsp+0B8h+Src]; Src
0x140003cf8  mov     r8, r12; Size
0x140003cfb  mov     rcx, r15; void *
0x140003cfe  call    memmove
0x140003d03  mov     edx, [rsp+0B8h+arg_38]
0x140003d0a  test    edx, edx
0x140003d0c  jnz     loc_140003EA0
0x140003d12  mov     rax, [rbx]
0x140003d15  cmp     byte ptr [rax+18h], 0
0x140003d19  jnz     loc_140003FB3
0x140003d1f  cmp     qword ptr [rax+10h], 0
0x140003d24  jz      loc_140003E89
0x140003d2a  mov     r8, [rax+28h]
0x140003d2e  mov     r8, [r8+28h]
0x140003d32  cmp     qword ptr [rax+8], 0
0x140003d37  jz      loc_140003FDE
0x140003d3d  mov     rdx, [rax+28h]
0x140003d41  mov     rdx, [rdx+18h]
0x140003d45  movzx   eax, cs:WinHvpNested
0x140003d4c  neg     al
0x140003d4e  mov     eax, 80000000h
0x140003d53  sbb     r10, r10
0x140003d56  and     r10, rax
0x140003d59  cmp     cs:WinHvpConnected, 0
0x140003d60  jz      loc_140004045
0x140003d66  mov     eax, [rsp+0B8h+arg_0]
0x140003d6d  mov     ecx, esi
0x140003d6f  and     ecx, 0FFFh
0x140003d75  movzx   r9d, ax
0x140003d79  shl     rcx, 20h
0x140003d7d  or      rcx, r9
0x140003d80  or      rcx, r10
0x140003d83  call    cs:__imp_HvlInvokeHypercall
0x140003d8a  nop     dword ptr [rax+rax+00h]
0x140003d8f  mov     rbp, rax
0x140003d92  shr     rbp, 20h
0x140003d96  and     ebp, 0FFFh
0x140003d9c  test    ax, ax
0x140003d9f  jnz     loc_140003F0C
0x140003da5  xor     edi, edi
0x140003da7  mov     rax, [rsp+0B8h+arg_70]
0x140003daf  mov     ecx, [rsp+0B8h+arg_58]
0x140003db6  mov     esi, ebp
0x140003db8  add     [rax], rsi
0x140003dbb  mov     eax, 80000005h
0x140003dc0  cmp     rsi, r14
0x140003dc3  cmova   edi, eax
0x140003dc6  test    ecx, ecx
0x140003dc8  jz      short loc_140003DF6
0x140003dca  test    ebp, ebp
0x140003dcc  jz      short loc_140003DF6
0x140003dce  mov     rax, [rsp+0B8h+arg_60]
0x140003dd6  mov     r8d, ebp
0x140003dd9  test    rax, rax
0x140003ddc  jnz     loc_14000404F
0x140003de2  imul    r8d, ecx; Size
0x140003de6  mov     rdx, r13; Src
0x140003de9  mov     rcx, [rsp+0B8h+arg_50]; void *
0x140003df1  call    memmove
0x140003df6  mov     rax, [rbx+38h]
0x140003dfa  lea     rcx, WinHvpReleaseFallbackBuffers
0x140003e01  cmp     rax, rcx
0x140003e04  mov     rcx, [rbx]
0x140003e07  jz      loc_140004064
0x140003e0d  test    edi, edi
0x140003e0f  jnz     short loc_140003E16
0x140003e11  sub     r14, rsi
0x140003e14  jnz     short loc_140003E6E
0x140003e16  cmp     [rsp+0B8h+arg_68], 0
0x140003e1f  mov     r15, [rsp+0B8h+var_38]
0x140003e27  mov     r13, [rsp+0B8h+var_30]
0x140003e2f  mov     rbp, [rsp+0B8h+var_20]
0x140003e37  jnz     short loc_140003E47
0x140003e39  test    rcx, rcx
0x140003e3c  jz      short loc_140003E47
0x140003e3e  mov     rax, [rbx+38h]
0x140003e42  call    _guard_dispatch_icall
0x140003e47  mov     rbx, [rsp+0B8h+arg_18]
0x140003e4f  mov     eax, edi
0x140003e51  mov     rdi, [rsp+0B8h+var_28]
0x140003e59  add     rsp, 0A0h
0x140003e60  pop     r14
0x140003e62  pop     r12
0x140003e64  pop     rsi
0x140003e65  retn
0x140003e67  mov     esi, edi
0x140003e69  jmp     loc_140003CE8
0x140003e6e  mov     edi, [rsp+0B8h+arg_8]
0x140003e75  mov     ecx, 0FFFFFFFFh
0x140003e7a  test    ebp, ebp
0x140003e7c  jnz     loc_140003F3E
0x140003e82  xor     esi, esi
0x140003e84  jmp     loc_140003C5B
0x140003e89  xor     r8d, r8d
0x140003e8c  jmp     loc_140003D32
0x140003e91  xor     edx, edx
0x140003e93  mov     eax, ecx
0x140003e95  div     r9d
0x140003e98  mov     r8d, eax
0x140003e9b  jmp     loc_140003BFA
0x140003ea0  cmp     [rsp+0B8h+arg_40], 0
0x140003ea9  lea     rcx, [rdi+r15]; void *
0x140003ead  mov     r8d, esi
0x140003eb0  jnz     short loc_140003F24
0x140003eb2  imul    r8d, edx; Size
0x140003eb6  mov     rdx, [rsp+0B8h+arg_30]; Src
0x140003ebe  call    memmove
0x140003ec3  jmp     loc_140003D12
0x140003ec8  test    edi, edi
0x140003eca  jz      loc_140003C24
0x140003ed0  xor     edx, edx
0x140003ed2  mov     eax, 1000h
0x140003ed7  div     edi
0x140003ed9  mov     edi, eax
0x140003edb  jmp     loc_140003C29
0x140003ee0  xor     edx, edx
0x140003ee2  mov     eax, ecx
0x140003ee4  div     r9d
0x140003ee7  mov     edi, eax
0x140003ee9  jmp     loc_140003C29
0x140003eee  mov     eax, esi
0x140003ef0  cmp     cs:WinHvpConnected, al
0x140003ef6  setnz   al
0x140003ef9  add     eax, 0C0350002h
0x140003efe  add     rsp, 0A0h
0x140003f05  pop     r14
0x140003f07  pop     r12
0x140003f09  pop     rsi
0x140003f0a  retn
0x140003f0c  movzx   edi, ax
0x140003f0f  or      edi, 0C0350000h
0x140003f15  jmp     loc_140003DA7
0x140003f1a  mov     eax, 0FFFh
0x140003f1f  jmp     loc_140003C12
0x140003f24  mov     rdx, [rsp+0B8h+arg_30]
0x140003f2c  mov     rax, [rsp+0B8h+arg_40]
0x140003f34  call    _guard_dispatch_icall
0x140003f39  jmp     loc_140003D12
0x140003f3e  cmp     [rsp+0B8h+arg_38], 0
0x140003f46  jbe     short loc_140003F76
0x140003f48  cmp     [rsp+0B8h+arg_48], 0
0x140003f51  jz      loc_140004077
0x140003f57  mov     rcx, [rsp+0B8h+arg_30]
0x140003f5f  mov     edx, ebp
0x140003f61  mov     rax, [rsp+0B8h+arg_48]
0x140003f69  call    _guard_dispatch_icall
0x140003f6e  mov     [rsp+0B8h+arg_30], rax
0x140003f76  mov     edi, [rsp+0B8h+arg_58]
0x140003f7d  test    edi, edi
0x140003f7f  jnz     loc_14000408E
0x140003f85  mov     rax, [rsp+0B8h+arg_20]
0x140003f8d  mov     ecx, 0FFFFFFFFh
0x140003f92  mov     edi, [rsp+0B8h+arg_8]
0x140003f99  test    rax, rax
0x140003f9c  jz      loc_140003E82
0x140003fa2  imul    rsi, [rsp+0B8h+arg_28]
0x140003fab  add     [rax], rsi
0x140003fae  jmp     loc_140003E82
0x140003fb3  mov     r9, [rax+10h]
0x140003fb7  lea     rcx, [rsp+0B8h+var_88]
0x140003fbc  mov     r8, [rax+8]
0x140003fc0  mov     edx, esi
0x140003fc2  mov     [rsp+0B8h+var_98], rcx
0x140003fc7  mov     ecx, [rsp+0B8h+arg_0]
0x140003fce  call    WinHvpSlowHypercallRemote
0x140003fd3  mov     ebp, [rsp+0B8h+var_88]
0x140003fd7  mov     edi, eax
0x140003fd9  jmp     loc_140003DA7
0x140003fde  xor     edx, edx
0x140003fe0  jmp     loc_140003D45
0x140003fe5  call    cs:__imp_KeGetCurrentIrql
0x140003fec  nop     dword ptr [rax+rax+00h]
0x140003ff1  mov     [rbx+30h], al
0x140003ff4  cmp     al, 2
0x140003ff6  jnb     short loc_140004014
0x140003ff8  lea     rcx, WinHvpFallbackMutex; FastMutex
0x140003fff  call    cs:__imp_ExAcquireFastMutex
0x140004006  nop     dword ptr [rax+rax+00h]
0x14000400b  lea     rax, WinHvpFallbackBuffer2
0x140004012  jmp     short loc_140004031
0x140004014  lea     rcx, WinHvpFallbackSpinLock; SpinLock
0x14000401b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004022  nop     dword ptr [rax+rax+00h]
0x140004027  mov     [rbx+30h], al
0x14000402a  lea     rax, WinHvpFallbackBuffer
0x140004031  lea     rcx, WinHvpReleaseFallbackBuffers
0x140004038  mov     [rbx+28h], rax
0x14000403c  mov     [rbx+38h], rcx
0x140004040  jmp     loc_140003CAF
0x140004045  mov     edi, 0C0351000h
0x14000404a  jmp     loc_140003DA7
0x14000404f  mov     rdx, [rsp+0B8h+arg_50]
0x140004057  mov     rcx, r13
0x14000405a  call    _guard_dispatch_icall
0x14000405f  jmp     loc_140003DF6
0x140004064  call    _guard_dispatch_icall
0x140004069  xor     ecx, ecx
0x14000406b  mov     qword ptr [rbx], 0
0x140004072  jmp     loc_140003E0D
0x140004077  mov     eax, ebp
0x140004079  imul    eax, [rsp+0B8h+arg_38]
0x140004081  add     [rsp+0B8h+arg_30], rax
0x140004089  jmp     loc_140003F76
0x14000408e  mov     rcx, [rsp+0B8h+arg_50]
0x140004096  test    rcx, rcx
0x140004099  jz      loc_140003F85
0x14000409f  imul    ebp, edi
0x1400040a2  mov     eax, ebp
0x1400040a4  add     rcx, rax
0x1400040a7  mov     [rsp+0B8h+arg_50], rcx
0x1400040af  jmp     loc_140003F85
```
