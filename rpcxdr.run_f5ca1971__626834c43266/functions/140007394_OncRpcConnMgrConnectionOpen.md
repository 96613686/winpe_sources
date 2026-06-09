# OncRpcConnMgrConnectionOpen

- ea: `0x140007394`
- end: `0x140007639`
- name: `OncRpcConnMgrConnectionOpen`
- size: `677`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140006b40`

## callees

- `0x1400020c0`
- `0x140002170`
- `0x140006720`
- `0x140007394`
- `0x140007b48`
- `0x1400082a8`
- `0x14001f3b4`

## import_xrefs

- `ntoskrnl!RtlRandomEx` at `0x140007532`
- `ntoskrnl!RtlRandomEx` at `0x140007532`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400075a4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400075a4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400075e4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400075e4`

## pseudocode

```c
__int64 __fastcall OncRpcConnMgrConnectionOpen(_WORD *a1, char a2, __int64 a3, __int64 a4, __int64 a5, __int64 *a6)
{
  __int64 v11; // rbx
  unsigned int v12; // edi
  int v13; // r12d
  _WORD *v14; // r14
  char v15; // r8
  __int16 v16; // r8
  _QWORD *v17; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-68h] BYREF

  if ( !a6 )
    return 3221225485LL;
  v11 = OncRpcConnMgrpConnectionAlloc();
  if ( v11 )
  {
    v13 = dword_14001A400;
    if ( a4 )
    {
      *(_OWORD *)(v11 + 96) = *(_OWORD *)a4;
      *(_OWORD *)(v11 + 112) = *(_OWORD *)(a4 + 16);
      *(_QWORD *)(v11 + 128) = *(_QWORD *)(a4 + 32);
    }
    v14 = (_WORD *)(v11 + 296);
    OncRpcCopyAddress(v11 + 296, a1);
    OncRpcCopyAddress(v11 + 324, a3);
    *(_QWORD *)(v11 + 88) = a5;
    if ( a2 )
    {
      if ( (*a1 == 2 || *a1 == 23) && __ROR2__(a1[1], 8) )
        a2 = v15;
      if ( a2 )
        goto LABEL_26;
    }
    while ( 1 )
    {
      v12 = OncRpcConnMgrpWskConnectionSocketOpen((_QWORD *)v11, (unsigned __int16 *)(v11 + 296), a3);
      if ( (v12 & 0x80000000) == 0 )
        break;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_cd42a1555dae3c8c93cac586485c41cc_Traceguids, v12);
      if ( v12 == -1073741643 || v12 == -1073741258 || !a2 || (--v13, !v13) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_cd42a1555dae3c8c93cac586485c41cc_Traceguids, v12);
        *(_QWORD *)(v11 + 96) = 0;
        if ( !(unsigned int)NfsStandardHeaderDereferenceNoType(v11) )
          OncRpcConnMgrpConnectionFree(v11);
        goto LABEL_32;
      }
LABEL_26:
      v16 = RtlRandomEx(&Seed) % 0x64 + 900;
      if ( *v14 == 2 || *v14 == 23 )
        *(_WORD *)(v11 + 298) = __ROR2__(v16, 8);
    }
    *(_DWORD *)(v11 + 80) = 1;
    memset(&LockHandle, 0, sizeof(LockHandle));
    KeAcquireInStackQueuedSpinLock(&OncRpcConnMgrGlobals, &LockHandle);
    v17 = (_QWORD *)qword_14001A3A0;
    if ( *(__int64 **)qword_14001A3A0 != &qword_14001A398 )
      __fastfail(3u);
    *(_QWORD *)(v11 + 32) = qword_14001A3A0;
    *(_QWORD *)(v11 + 24) = &qword_14001A398;
    *v17 = v11 + 24;
    qword_14001A3A0 = v11 + 24;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    *a6 = v11;
  }
  else
  {
    v12 = -1073741670;
  }
LABEL_32:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_cd42a1555dae3c8c93cac586485c41cc_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x140007394  push    rbx
0x140007396  push    rbp
0x140007397  push    rsi
0x140007398  push    rdi
0x140007399  push    r12
0x14000739b  push    r13
0x14000739d  push    r14
0x14000739f  push    r15
0x1400073a1  sub     rsp, 48h
0x1400073a5  mov     r15, [rsp+88h+arg_28]
0x1400073ad  mov     rdi, r9
0x1400073b0  movzx   ebp, dl
0x1400073b3  mov     r13, r8
0x1400073b6  mov     rsi, rcx
0x1400073b9  test    r15, r15
0x1400073bc  jnz     short loc_1400073C8
0x1400073be  mov     eax, 0C000000Dh
0x1400073c3  jmp     loc_140007627
0x1400073c8  call    OncRpcConnMgrpConnectionAlloc
0x1400073cd  mov     rbx, rax
0x1400073d0  xor     r8d, r8d
0x1400073d3  lea     rax, WPP_GLOBAL_Control
0x1400073da  test    rbx, rbx
0x1400073dd  jnz     short loc_1400073E9
0x1400073df  mov     edi, 0C000009Ah
0x1400073e4  jmp     loc_1400075FA
0x1400073e9  mov     r12d, cs:dword_14001A400
0x1400073f0  test    rdi, rdi
0x1400073f3  jz      short loc_140007411
0x1400073f5  movups  xmm0, xmmword ptr [rdi]
0x1400073f8  movups  xmmword ptr [rbx+60h], xmm0
0x1400073fc  movups  xmm1, xmmword ptr [rdi+10h]
0x140007400  movups  xmmword ptr [rbx+70h], xmm1
0x140007404  movsd   xmm0, qword ptr [rdi+20h]
0x140007409  movsd   qword ptr [rbx+80h], xmm0
0x140007411  lea     r14, [rbx+128h]
0x140007418  mov     rdx, rsi
0x14000741b  mov     rcx, r14
0x14000741e  call    OncRpcCopyAddress
0x140007423  lea     rcx, [rbx+144h]
0x14000742a  mov     rdx, r13
0x14000742d  call    OncRpcCopyAddress
0x140007432  mov     rcx, [rsp+88h+arg_20]
0x14000743a  mov     [rbx+58h], rcx
0x14000743e  mov     ecx, 2
0x140007443  test    bpl, bpl
0x140007446  jz      short loc_14000746E
0x140007448  movzx   eax, word ptr [rsi]
0x14000744b  cmp     ax, cx
0x14000744e  jz      short loc_140007456
0x140007450  cmp     ax, 17h
0x140007454  jnz     short loc_140007465
0x140007456  movzx   ecx, word ptr [rcx+rsi]
0x14000745a  ror     cx, 8
0x14000745e  test    cx, cx
0x140007461  cmovnz  ebp, r8d
0x140007465  test    bpl, bpl
0x140007468  jnz     loc_140007529
0x14000746e  xor     esi, esi
0x140007470  mov     r8, r13
0x140007473  mov     rdx, r14
0x140007476  mov     rcx, rbx
0x140007479  call    OncRpcConnMgrpWskConnectionSocketOpen
0x14000747e  mov     edi, eax
0x140007480  test    eax, eax
0x140007482  jns     loc_140007582
0x140007488  mov     rcx, cs:WPP_GLOBAL_Control
0x14000748f  lea     rax, WPP_GLOBAL_Control
0x140007496  cmp     rcx, rax
0x140007499  jz      short loc_1400074C2
0x14000749b  mov     edx, [rcx+2Ch]
0x14000749e  test    dl, 8
0x1400074a1  jz      short loc_1400074C2
0x1400074a3  mov     rcx, [rcx+18h]
0x1400074a7  lea     r8, WPP_cd42a1555dae3c8c93cac586485c41cc_Traceguids
0x1400074ae  mov     edx, 11h
0x1400074b3  mov     r9d, edi
0x1400074b6  call    WPP_SF_d
0x1400074bb  lea     rax, WPP_GLOBAL_Control
0x1400074c2  cmp     edi, 0C00000B5h
0x1400074c8  jz      short loc_1400074DD
0x1400074ca  cmp     edi, 0C0000236h
0x1400074d0  jz      short loc_1400074DD
0x1400074d2  test    bpl, bpl
0x1400074d5  jz      short loc_1400074DD
0x1400074d7  add     r12d, 0FFFFFFFFh
0x1400074db  jnz     short loc_14000752B
0x1400074dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400074e4  cmp     rcx, rax
0x1400074e7  jz      short loc_140007508
0x1400074e9  mov     eax, [rcx+2Ch]
0x1400074ec  test    al, 8
0x1400074ee  jz      short loc_140007508
0x1400074f0  mov     rcx, [rcx+18h]
0x1400074f4  lea     r8, WPP_cd42a1555dae3c8c93cac586485c41cc_Traceguids
0x1400074fb  mov     edx, 12h
0x140007500  mov     r9d, edi
0x140007503  call    WPP_SF_d
0x140007508  mov     rcx, rbx
0x14000750b  mov     [rbx+60h], rsi
0x14000750f  call    NfsStandardHeaderDereferenceNoType
0x140007514  test    eax, eax
0x140007516  jnz     loc_1400075F3
0x14000751c  mov     rcx, rbx
0x14000751f  call    OncRpcConnMgrpConnectionFree
0x140007524  jmp     loc_1400075F3
0x140007529  xor     esi, esi
0x14000752b  lea     rcx, Seed; Seed
0x140007532  call    cs:__imp_RtlRandomEx
0x140007539  nop     dword ptr [rax+rax+00h]
0x14000753e  mov     r8d, eax
0x140007541  mov     eax, 51EB851Fh
0x140007546  mul     r8d
0x140007549  mov     eax, 384h
0x14000754e  shr     edx, 5
0x140007551  imul    ecx, edx, 64h ; 'd'
0x140007554  sub     r8d, ecx
0x140007557  mov     ecx, 2
0x14000755c  add     r8w, ax
0x140007560  movzx   eax, word ptr [r14]
0x140007564  cmp     ax, cx
0x140007567  jz      short loc_140007573
0x140007569  cmp     ax, 17h
0x14000756d  jnz     loc_140007470
0x140007573  ror     r8w, 8
0x140007578  mov     [r14+2], r8w
0x14000757d  jmp     loc_140007470
0x140007582  xorps   xmm0, xmm0
0x140007585  mov     dword ptr [rbx+50h], 1
0x14000758c  xor     eax, eax
0x14000758e  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x140007593  lea     rcx, OncRpcConnMgrGlobals; SpinLock
0x14000759a  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x14000759f  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x1400075a4  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400075ab  nop     dword ptr [rax+rax+00h]
0x1400075b0  mov     rcx, cs:qword_14001A3A0
0x1400075b7  lea     rdx, qword_14001A398
0x1400075be  cmp     [rcx], rdx
0x1400075c1  jz      short loc_1400075CA
0x1400075c3  mov     ecx, 3
0x1400075c8  int     29h; Win8: RtlFailFast(ecx)
0x1400075ca  lea     rax, [rbx+18h]
0x1400075ce  mov     [rax+8], rcx
0x1400075d2  mov     [rax], rdx
0x1400075d5  mov     [rcx], rax
0x1400075d8  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x1400075dd  mov     cs:qword_14001A3A0, rax
0x1400075e4  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400075eb  nop     dword ptr [rax+rax+00h]
0x1400075f0  mov     [r15], rbx
0x1400075f3  lea     rax, WPP_GLOBAL_Control
0x1400075fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140007601  cmp     rcx, rax
0x140007604  jz      short loc_140007625
0x140007606  mov     eax, [rcx+2Ch]
0x140007609  test    al, 1
0x14000760b  jz      short loc_140007625
0x14000760d  mov     rcx, [rcx+18h]
0x140007611  lea     r8, WPP_cd42a1555dae3c8c93cac586485c41cc_Traceguids
0x140007618  mov     edx, 13h
0x14000761d  mov     r9d, edi
0x140007620  call    WPP_SF_d
0x140007625  mov     eax, edi
0x140007627  add     rsp, 48h
0x14000762b  pop     r15
0x14000762d  pop     r14
0x14000762f  pop     r13
0x140007631  pop     r12
0x140007633  pop     rdi
0x140007634  pop     rsi
0x140007635  pop     rbp
0x140007636  pop     rbx
0x140007637  retn
```
