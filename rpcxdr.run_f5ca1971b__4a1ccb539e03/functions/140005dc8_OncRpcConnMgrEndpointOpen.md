# OncRpcConnMgrEndpointOpen

- ea: `0x140005dc8`
- end: `0x14000616a`
- name: `OncRpcConnMgrEndpointOpen`
- size: `930`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140006d10`

## callees

- `0x1400020c0`
- `0x140002170`
- `0x140005830`
- `0x140005dc8`
- `0x140006170`
- `0x14000639c`
- `0x140006720`
- `0x14001f900`
- `0x14001fc68`

## import_xrefs

- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140005f5e`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140005f5e`
- `ntoskrnl!RtlRandomEx` at `0x14000607c`
- `ntoskrnl!RtlRandomEx` at `0x14000607c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400060db`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400060db`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140006128`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140006128`

## pseudocode

```c
__int64 __fastcall OncRpcConnMgrEndpointOpen(
        __int128 *a1,
        __int64 a2,
        char a3,
        int a4,
        _QWORD *a5,
        __int64 a6,
        __int64 *a7)
{
  __int128 v11; // xmm6
  __int128 v12; // xmm7
  __int64 v13; // rax
  __int64 v14; // rbx
  int v15; // edi
  __int64 v16; // xmm1_8
  __int128 v17; // xmm0
  bool v18; // zf
  _WORD *v19; // rsi
  int v20; // ecx
  int v21; // eax
  void *TableContext; // r8
  __int64 v23; // r9
  int v24; // eax
  unsigned int v25; // r12d
  __int16 v26; // r8
  __int64 *v27; // rcx
  __int64 **v28; // rdx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+68h] [rbp-70h]

  v11 = 0;
  v12 = 0;
  v31 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( !a7 || a4 == 6 && (!a5 || !a5[2] && !a5[4]) || !a6 && a5 && *a5 )
    return (unsigned int)-1073741811;
  v13 = OncRpcConnMgrpEndpointAlloc();
  v14 = v13;
  if ( !v13 )
    return (unsigned int)-1073741670;
  if ( a5 )
  {
    v11 = *(_OWORD *)a5;
    v12 = *((_OWORD *)a5 + 1);
    v16 = a5[4];
  }
  else
  {
    v16 = v31;
  }
  if ( a1 )
  {
    v17 = *a1;
    *(_DWORD *)(v13 + 224) |= 1u;
    *(_OWORD *)(v13 + 80) = v17;
  }
  *(_OWORD *)(v13 + 184) = v11;
  *(_QWORD *)(v13 + 176) = a6;
  v18 = a4 == 6;
  *(_OWORD *)(v13 + 200) = v12;
  v19 = (_WORD *)(v13 + 52);
  v20 = 0;
  *(_QWORD *)(v13 + 216) = v16;
  v21 = *(_DWORD *)(v13 + 224);
  if ( v18 )
    v20 = 2;
  *(_DWORD *)(v14 + 224) = v21 & 0xFFFFFFFD | v20;
  OncRpcCopyAddress(v14 + 52, a2);
  if ( ((unsigned __int8)*(_DWORD *)(v14 + 224) & (unsigned __int8)v23) == 0 )
  {
    v25 = dword_14001A400;
    *(_DWORD *)(v14 + 232) = (_DWORD)TableContext;
    if ( a3 && (*v19 == (_WORD)v23 || *v19 == 23) && __ROR2__(*(_WORD *)((char *)v19 + v23), 8) )
      a3 = (char)TableContext;
    if ( a3 )
      goto LABEL_37;
    while ( 1 )
    {
      v15 = OncRpcConnMgrpWskDatagramSocketOpen(v14, v14 + 52);
      if ( v15 >= 0 )
        goto LABEL_40;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_e6da9dcbba6831c1b4289775a52989f5_Traceguids, v25, v15);
      if ( !a3 )
        goto LABEL_23;
      if ( !--v25 )
        goto LABEL_23;
LABEL_37:
      v26 = RtlRandomEx(&Seed) % 0x64 + 900;
      if ( *v19 == 2 || *v19 == 23 )
        *(_WORD *)(v14 + 54) = __ROR2__(v26, 8);
    }
  }
  *(_QWORD *)(v14 + 240) = v14 + 232;
  *(_QWORD *)(v14 + 232) = v14 + 232;
  *(_QWORD *)(v14 + 256) = v14 + 248;
  *(_QWORD *)(v14 + 248) = v14 + 248;
  *(_QWORD *)(v14 + 272) = v14 + 264;
  *(_QWORD *)(v14 + 264) = v14 + 264;
  *(_DWORD *)(v14 + 280) = (_DWORD)TableContext;
  RtlInitializeGenericTableAvl(
    (PRTL_AVL_TABLE)(v14 + 288),
    OncRpcConnMgrpRemoteAddressCompare,
    OncRpcConnMgrpRemoteAddressAllocate,
    OncRpcConnMgrpRemoteAddressFree,
    TableContext);
  v24 = OncRpcConnMgrpWskListeningSocketOpen(v14, v14 + 52);
  v15 = v24;
  if ( v24 >= 0 )
  {
LABEL_40:
    *(_DWORD *)(v14 + 48) = 1;
    KeAcquireInStackQueuedSpinLock(&OncRpcConnMgrGlobals, &LockHandle);
    v27 = &qword_14001A378;
    if ( (*(_DWORD *)(v14 + 224) & 2) == 0 )
      v27 = &qword_14001A388;
    v28 = (__int64 **)v27[1];
    if ( *v28 != v27 )
      __fastfail(3u);
    *(_QWORD *)(v14 + 24) = v27;
    *(_QWORD *)(v14 + 32) = v28;
    *v28 = (__int64 *)(v14 + 24);
    v27[1] = v14 + 24;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    *a7 = v14;
    return (unsigned int)v15;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_e6da9dcbba6831c1b4289775a52989f5_Traceguids, (unsigned int)v24);
LABEL_23:
  *(_QWORD *)(v14 + 184) = 0;
  if ( !(unsigned int)NfsStandardHeaderDereferenceNoType(v14) )
    OncRpcConnMgrpEndpointFree((PVOID)v14);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140005dc8  mov     rax, rsp
0x140005dcb  push    rbx
0x140005dcc  push    rbp
0x140005dcd  push    rsi
0x140005dce  push    rdi
0x140005dcf  push    r12
0x140005dd1  push    r13
0x140005dd3  push    r14
0x140005dd5  push    r15
0x140005dd7  sub     rsp, 98h
0x140005dde  movaps  xmmword ptr [rax-58h], xmm6
0x140005de2  xorps   xmm0, xmm0
0x140005de5  movaps  xmmword ptr [rax-68h], xmm7
0x140005de9  mov     esi, r9d
0x140005dec  xor     eax, eax
0x140005dee  movzx   ebp, r8b
0x140005df2  mov     r13, rdx
0x140005df5  mov     r14, rcx
0x140005df8  xorps   xmm6, xmm6
0x140005dfb  xorps   xmm7, xmm7
0x140005dfe  mov     [rsp+0D8h+var_70], rax
0x140005e03  movups  xmmword ptr [rsp+0D8h+LockHandle.LockQueue.Next], xmm0
0x140005e08  mov     qword ptr [rsp+0D8h+LockHandle.OldIrql], rax
0x140005e0d  cmp     [rsp+0D8h+arg_30], rax
0x140005e15  jz      loc_140006141
0x140005e1b  mov     rdi, [rsp+0D8h+arg_20]
0x140005e23  cmp     r9d, 6
0x140005e27  jnz     short loc_140005E47
0x140005e29  test    rdi, rdi
0x140005e2c  jz      loc_140006141
0x140005e32  cmp     r9d, r9d
0x140005e35  jnz     short loc_140005E47
0x140005e37  cmp     [rdi+10h], rax
0x140005e3b  jnz     short loc_140005E47
0x140005e3d  cmp     [rdi+20h], rax
0x140005e41  jz      loc_140006141
0x140005e47  mov     r12, [rsp+0D8h+arg_28]
0x140005e4f  test    r12, r12
0x140005e52  jnz     short loc_140005E62
0x140005e54  test    rdi, rdi
0x140005e57  jz      short loc_140005E62
0x140005e59  cmp     [rdi], rax
0x140005e5c  jnz     loc_140006141
0x140005e62  call    OncRpcConnMgrpEndpointAlloc
0x140005e67  xor     r8d, r8d
0x140005e6a  mov     rbx, rax
0x140005e6d  test    rax, rax
0x140005e70  jnz     short loc_140005E7C
0x140005e72  mov     edi, 0C000009Ah
0x140005e77  jmp     loc_140006146
0x140005e7c  test    rdi, rdi
0x140005e7f  jz      short loc_140005E8F
0x140005e81  movups  xmm6, xmmword ptr [rdi]
0x140005e84  movups  xmm7, xmmword ptr [rdi+10h]
0x140005e88  movsd   xmm1, qword ptr [rdi+20h]
0x140005e8d  jmp     short loc_140005E95
0x140005e8f  movsd   xmm1, [rsp+0D8h+var_70]
0x140005e95  mov     r15d, 1
0x140005e9b  test    r14, r14
0x140005e9e  jz      short loc_140005EB0
0x140005ea0  movups  xmm0, xmmword ptr [r14]
0x140005ea4  or      [rax+0E0h], r15d
0x140005eab  movdqu  xmmword ptr [rax+50h], xmm0
0x140005eb0  movups  xmmword ptr [rax+0B8h], xmm6
0x140005eb7  mov     [rax+0B0h], r12
0x140005ebe  cmp     esi, 6
0x140005ec1  movups  xmmword ptr [rax+0C8h], xmm7
0x140005ec8  lea     rsi, [rbx+34h]
0x140005ecc  mov     ecx, r8d
0x140005ecf  movsd   qword ptr [rax+0D8h], xmm1
0x140005ed7  mov     r9d, 2
0x140005edd  mov     eax, [rax+0E0h]
0x140005ee3  cmovz   ecx, r9d
0x140005ee7  and     eax, 0FFFFFFFDh
0x140005eea  mov     rdx, r13
0x140005eed  or      ecx, eax
0x140005eef  mov     [rbx+0E0h], ecx
0x140005ef5  mov     rcx, rsi
0x140005ef8  call    OncRpcCopyAddress
0x140005efd  mov     ecx, [rbx+0E0h]
0x140005f03  test    r9b, cl
0x140005f06  jz      loc_140005FD8
0x140005f0c  lea     rax, [rbx+0E8h]
0x140005f13  mov     [rsp+0D8h+TableContext], r8; TableContext
0x140005f18  mov     [rax+8], rax
0x140005f1c  lea     rcx, [rbx+120h]; Table
0x140005f23  mov     [rax], rax
0x140005f26  lea     r9, OncRpcConnMgrpRemoteAddressFree; FreeRoutine
0x140005f2d  lea     rax, [rbx+0F8h]
0x140005f34  mov     [rax+8], rax
0x140005f38  lea     rdx, OncRpcConnMgrpRemoteAddressCompare; CompareRoutine
0x140005f3f  mov     [rax], rax
0x140005f42  lea     rax, [rbx+108h]
0x140005f49  mov     [rax+8], rax
0x140005f4d  mov     [rax], rax
0x140005f50  mov     [rbx+118h], r8d
0x140005f57  lea     r8, OncRpcConnMgrpRemoteAddressAllocate; AllocateRoutine
0x140005f5e  call    cs:__imp_RtlInitializeGenericTableAvl
0x140005f65  nop     dword ptr [rax+rax+00h]
0x140005f6a  mov     rdx, rsi
0x140005f6d  mov     rcx, rbx
0x140005f70  call    OncRpcConnMgrpWskListeningSocketOpen
0x140005f75  xor     r13d, r13d
0x140005f78  mov     edi, eax
0x140005f7a  test    eax, eax
0x140005f7c  jns     loc_1400060CB
0x140005f82  mov     rcx, cs:WPP_GLOBAL_Control
0x140005f89  lea     r14, WPP_GLOBAL_Control
0x140005f90  cmp     rcx, r14
0x140005f93  jz      short loc_140005FB4
0x140005f95  mov     edx, [rcx+2Ch]
0x140005f98  test    dl, 8
0x140005f9b  jz      short loc_140005FB4
0x140005f9d  mov     rcx, [rcx+18h]
0x140005fa1  lea     edx, [r13+11h]
0x140005fa5  mov     r9d, eax
0x140005fa8  lea     r8, WPP_e6da9dcbba6831c1b4289775a52989f5_Traceguids
0x140005faf  call    WPP_SF_d
0x140005fb4  mov     rcx, rbx
0x140005fb7  mov     [rbx+0B8h], r13
0x140005fbe  call    NfsStandardHeaderDereferenceNoType
0x140005fc3  test    eax, eax
0x140005fc5  jnz     loc_140006146
0x140005fcb  mov     rcx, rbx; P
0x140005fce  call    OncRpcConnMgrpEndpointFree
0x140005fd3  jmp     loc_140006146
0x140005fd8  mov     r12d, cs:dword_14001A400
0x140005fdf  mov     [rbx+0E8h], r8d
0x140005fe6  test    bpl, bpl
0x140005fe9  jz      short loc_14000600F
0x140005feb  movzx   eax, word ptr [rsi]
0x140005fee  cmp     ax, r9w
0x140005ff2  jz      short loc_140005FFA
0x140005ff4  cmp     ax, 17h
0x140005ff8  jnz     short loc_14000600F
0x140005ffa  mov     rax, r9
0x140005ffd  mov     rcx, rsi
0x140006000  movzx   ecx, word ptr [rax+rcx]
0x140006004  ror     cx, 8
0x140006008  test    cx, cx
0x14000600b  cmovnz  ebp, r8d
0x14000600f  xor     r13d, r13d
0x140006012  lea     r14, WPP_GLOBAL_Control
0x140006019  test    bpl, bpl
0x14000601c  jnz     short loc_140006075
0x14000601e  mov     rdx, rsi
0x140006021  mov     rcx, rbx
0x140006024  call    OncRpcConnMgrpWskDatagramSocketOpen
0x140006029  mov     edi, eax
0x14000602b  test    eax, eax
0x14000602d  jns     loc_1400060CB
0x140006033  mov     rcx, cs:WPP_GLOBAL_Control
0x14000603a  cmp     rcx, r14
0x14000603d  jz      short loc_140006062
0x14000603f  mov     eax, [rcx+2Ch]
0x140006042  test    al, 8
0x140006044  jz      short loc_140006062
0x140006046  mov     rcx, [rcx+18h]
0x14000604a  lea     r8, WPP_e6da9dcbba6831c1b4289775a52989f5_Traceguids
0x140006051  mov     edx, 12h
0x140006056  mov     dword ptr [rsp+0D8h+TableContext], edi
0x14000605a  mov     r9d, r12d
0x14000605d  call    WPP_SF_Dd
0x140006062  test    bpl, bpl
0x140006065  jz      loc_140005FB4
0x14000606b  add     r12d, 0FFFFFFFFh
0x14000606f  jz      loc_140005FB4
0x140006075  lea     rcx, Seed; Seed
0x14000607c  call    cs:__imp_RtlRandomEx
0x140006083  nop     dword ptr [rax+rax+00h]
0x140006088  mov     r8d, eax
0x14000608b  mov     eax, 51EB851Fh
0x140006090  mul     r8d
0x140006093  mov     eax, 384h
0x140006098  shr     edx, 5
0x14000609b  imul    ecx, edx, 64h ; 'd'
0x14000609e  sub     r8d, ecx
0x1400060a1  mov     ecx, 2
0x1400060a6  add     r8w, ax
0x1400060aa  movzx   eax, word ptr [rsi]
0x1400060ad  cmp     ax, cx
0x1400060b0  jz      short loc_1400060BC
0x1400060b2  cmp     ax, 17h
0x1400060b6  jnz     loc_14000601E
0x1400060bc  ror     r8w, 8
0x1400060c1  mov     [rsi+2], r8w
0x1400060c6  jmp     loc_14000601E
0x1400060cb  lea     rdx, [rsp+0D8h+LockHandle]; LockHandle
0x1400060d0  mov     [rbx+30h], r15d
0x1400060d4  lea     rcx, OncRpcConnMgrGlobals; SpinLock
0x1400060db  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400060e2  nop     dword ptr [rax+rax+00h]
0x1400060e7  mov     eax, [rbx+0E0h]
0x1400060ed  lea     rcx, qword_14001A378
0x1400060f4  test    al, 2
0x1400060f6  lea     rax, qword_14001A388
0x1400060fd  cmovz   rcx, rax
0x140006101  mov     rdx, [rcx+8]
0x140006105  cmp     [rdx], rcx
0x140006108  jz      short loc_140006111
0x14000610a  mov     ecx, 3
0x14000610f  int     29h; Win8: RtlFailFast(ecx)
0x140006111  lea     rax, [rbx+18h]
0x140006115  mov     [rax], rcx
0x140006118  mov     [rax+8], rdx
0x14000611c  mov     [rdx], rax
0x14000611f  mov     [rcx+8], rax
0x140006123  lea     rcx, [rsp+0D8h+LockHandle]; LockHandle
0x140006128  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000612f  nop     dword ptr [rax+rax+00h]
0x140006134  mov     rax, [rsp+0D8h+arg_30]
0x14000613c  mov     [rax], rbx
0x14000613f  jmp     short loc_140006146
0x140006141  mov     edi, 0C000000Dh
0x140006146  movaps  xmm6, [rsp+0D8h+var_58]
0x14000614e  mov     eax, edi
0x140006150  movaps  xmm7, [rsp+0D8h+var_68]
0x140006155  add     rsp, 98h
0x14000615c  pop     r15
0x14000615e  pop     r14
0x140006160  pop     r13
0x140006162  pop     r12
0x140006164  pop     rdi
0x140006165  pop     rsi
0x140006166  pop     rbp
0x140006167  pop     rbx
0x140006168  retn
```
