# Smb2XmrCtlCreateRdmaMapping

- ea: `0x1400700a8`
- end: `0x1400703f5`
- name: `Smb2XmrCtlCreateRdmaMapping`
- size: `845`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140082290`

## callees

- `0x140038680`
- `0x140059174`
- `0x1400591e8`
- `0x14005e940`
- `0x14005ea7c`
- `0x14005ecc4`
- `0x14005edc4`
- `0x1400700a8`
- `0x140082f60`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140070215`
- `ntoskrnl!ExAllocatePool2` at `0x140070215`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400703b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400703b6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14007032a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14007032a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140070360`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140070360`
- `ntoskrnl!MmBadPointer` at `0x14007018c`
- `srvnet!SrvNetRdmaRegisterMr` at `0x140070256`
- `srvnet!SrvNetRdmaRegisterMr` at `0x140070256`
- `srvnet!SrvNetRdmaGetMrToken` at `0x140070278`
- `srvnet!SrvNetRdmaGetMrToken` at `0x140070278`

## pseudocode

```c
__int64 __fastcall Smb2XmrCtlCreateRdmaMapping(_QWORD *a1)
{
  __int64 v1; // r9
  void *v2; // r15
  void *v3; // rsi
  __int64 v4; // r14
  int v5; // r12d
  int MrToken; // ebx
  __int64 v8; // r8
  int v9; // eax
  int v10; // edx
  int v11; // ecx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rax
  unsigned __int64 v17; // r8
  __int64 *Pool2; // rax
  __int64 *v19; // rdi
  int v20; // eax
  __int64 v21; // rbx
  __int64 v22; // rax
  __int64 **v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  unsigned int v27; // eax
  __int64 v29; // [rsp+30h] [rbp-38h] BYREF
  __int64 v30; // [rsp+38h] [rbp-30h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-28h] BYREF
  int v32; // [rsp+B0h] [rbp+48h] BYREF
  int v33; // [rsp+B8h] [rbp+50h]
  void *v34; // [rsp+C0h] [rbp+58h] BYREF
  void *v35; // [rsp+C8h] [rbp+60h] BYREF

  v1 = a1[70];
  v2 = 0;
  v3 = 0;
  v30 = v1;
  v35 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v4 = *(_QWORD *)(v1 + 216);
  v5 = 0;
  v34 = 0;
  v32 = 0;
  v29 = 0;
  if ( *(_DWORD *)v4 != 1 )
  {
    MrToken = -1073741736;
    goto LABEL_38;
  }
  v8 = *(unsigned int *)(v4 + 4);
  v9 = *(_DWORD *)(v4 + 4) & 0xC;
  if ( v9 == 12 )
  {
    MrToken = -1073741776;
    goto LABEL_38;
  }
  if ( (v8 & 1) == 0 )
  {
    MrToken = -1073741637;
    goto LABEL_38;
  }
  if ( !v9 )
  {
    MrToken = -1073741811;
    goto LABEL_38;
  }
  v10 = *(_DWORD *)(v4 + 8) & 1 | 2;
  if ( (*(_BYTE *)(v4 + 8) & 2) == 0 )
    v10 = *(_DWORD *)(v4 + 8) & 1;
  v11 = v10 | 4;
  if ( (v8 & 2) == 0 )
    v11 = v10;
  v33 = v11;
  if ( (v8 & 4) == 0 )
  {
    MrToken = -1073741822;
    if ( (v8 & 8) != 0 )
      goto LABEL_38;
    goto LABEL_37;
  }
  v12 = Srv2QueryDaxPhysicalExtents(&v35, *(_QWORD *)(*(_QWORD *)(v1 + 80) + 96LL), v8, *(_QWORD *)(v4 + 24));
  v2 = v35;
  MrToken = v12;
  if ( v12 < 0 )
    goto LABEL_38;
  v13 = Srv2PhysExtentsToMdlChain((unsigned int)&v34, (unsigned int)&v32, (unsigned int)&v29, (_DWORD)v35);
  v3 = v34;
  MrToken = v13;
  if ( v13 < 0 )
    goto LABEL_38;
  v14 = Srv2SumMdlByteCount(v34);
  v15 = v29;
  if ( v14 != v29 )
    __int2c();
  if ( v29 != *(_QWORD *)(v4 + 24) )
    __int2c();
  v16 = Srv2SumPhysExtentsPages(v2);
  if ( (v17 >> 12) + ((v17 & 0xFFF) != 0) != v16 )
    __int2c();
  if ( !v3 )
  {
LABEL_37:
    MrToken = -1073741823;
    goto LABEL_38;
  }
  Pool2 = (__int64 *)ExAllocatePool2(64, 72, 1685607244);
  v19 = Pool2;
  if ( !Pool2 )
  {
    MrToken = -1073741670;
    goto LABEL_38;
  }
  Pool2[1] = (__int64)Pool2;
  *Pool2 = (__int64)Pool2;
  MrToken = SrvNetRdmaRegisterMr(Pool2 + 5, *(_QWORD *)(a1[12] + 480LL), v3, v15, v33);
  if ( MrToken < 0 )
    goto LABEL_35;
  MrToken = SrvNetRdmaGetMrToken(v19[5], v19 + 8, (char *)v19 + 60);
  if ( MrToken < 0 )
    goto LABEL_35;
  if ( !v19[8] || (v20 = *((_DWORD *)v19 + 15)) == 0 )
  {
    MrToken = -1073741255;
    goto LABEL_35;
  }
  v21 = v30;
  if ( *(_DWORD *)(v30 + 200) < (unsigned int)(v20 + 32) )
  {
    MrToken = -1073741789;
LABEL_35:
    Smb2FreeRdmaMapping(v19);
    goto LABEL_38;
  }
  *((_DWORD *)v19 + 4) = _InterlockedIncrement(&Smb2RdmaMappingIdGenerator);
  v19[3] = *(_QWORD *)(v4 + 16);
  v19[4] = *(_QWORD *)(v4 + 24);
  v19[6] = (__int64)v3;
  v3 = 0;
  *((_DWORD *)v19 + 14) = 0;
  *(_DWORD *)v4 = 1;
  *(_DWORD *)(v4 + 24) = *((_DWORD *)v19 + 4);
  *(_QWORD *)(v4 + 8) = v19[3];
  *(_QWORD *)(v4 + 16) = v19[4];
  *(_DWORD *)(v4 + 28) = *((_DWORD *)v19 + 15);
  memmove((void *)(v4 + 32), (const void *)v19[8], *((unsigned int *)v19 + 15));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(*(_QWORD *)(v21 + 72) + 112LL), &LockHandle);
  v22 = *(_QWORD *)(v21 + 80) + 136LL;
  v23 = *(__int64 ***)(*(_QWORD *)(v21 + 80) + 144LL);
  if ( *v23 != (__int64 *)v22 )
    __fastfail(3u);
  v19[1] = (__int64)v23;
  *v19 = v22;
  *v23 = v19;
  *(_QWORD *)(v22 + 8) = v19;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  _InterlockedAdd(&Smb2XmrActiveMappingCount, 1u);
  v5 = *(_DWORD *)(v4 + 28) + 32;
  MrToken = 0;
LABEL_38:
  Srv2FreeMdlChain(v3);
  if ( v2 )
    ExFreePoolWithTag(v2, 0x7065534Cu);
  *(_DWORD *)(a1[15] + 48LL) = MrToken;
  v27 = 0;
  if ( MrToken >= 0 )
    v27 = v5;
  *(_QWORD *)(a1[15] + 56LL) = v27;
  return Smb2ContinueIoctl(a1, v24, v25, v26);
}

```

## disassembly

```asm
0x1400700a8  push    rbp
0x1400700aa  push    rbx
0x1400700ab  push    rsi
0x1400700ac  push    rdi
0x1400700ad  push    r12
0x1400700af  push    r13
0x1400700b1  push    r14
0x1400700b3  push    r15
0x1400700b5  mov     rbp, rsp
0x1400700b8  sub     rsp, 68h
0x1400700bc  mov     r9, [rcx+230h]
0x1400700c3  xor     eax, eax
0x1400700c5  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x1400700c9  xor     r15d, r15d
0x1400700cc  xor     esi, esi
0x1400700ce  mov     [rbp+var_30], r9
0x1400700d2  xorps   xmm0, xmm0
0x1400700d5  mov     [rbp+arg_18], r15
0x1400700d9  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x1400700dd  mov     r14, [r9+0D8h]
0x1400700e4  xor     r12d, r12d
0x1400700e7  mov     r13, rcx
0x1400700ea  mov     [rbp+arg_10], rsi
0x1400700ee  mov     [rbp+arg_0], eax
0x1400700f1  mov     [rbp+var_38], rax
0x1400700f5  cmp     dword ptr [r14], 1
0x1400700f9  jz      short loc_140070105
0x1400700fb  mov     ebx, 0C0000058h
0x140070100  jmp     loc_14007039F
0x140070105  mov     r8d, [r14+4]
0x140070109  mov     eax, r8d
0x14007010c  and     eax, 0Ch
0x14007010f  cmp     eax, 0Ch
0x140070112  jnz     short loc_14007011E
0x140070114  mov     ebx, 0C0000030h
0x140070119  jmp     loc_14007039F
0x14007011e  test    r8b, 1
0x140070122  jnz     short loc_14007012E
0x140070124  mov     ebx, 0C00000BBh
0x140070129  jmp     loc_14007039F
0x14007012e  test    eax, eax
0x140070130  jnz     short loc_14007013C
0x140070132  mov     ebx, 0C000000Dh
0x140070137  jmp     loc_14007039F
0x14007013c  mov     ecx, [r14+8]
0x140070140  and     ecx, 1
0x140070143  mov     edx, ecx
0x140070145  or      edx, 2
0x140070148  test    byte ptr [r14+8], 2
0x14007014d  cmovz   edx, ecx
0x140070150  mov     ecx, edx
0x140070152  or      ecx, 4
0x140070155  test    r8b, 2
0x140070159  cmovz   ecx, edx
0x14007015c  mov     [rbp+arg_8], ecx
0x14007015f  test    r8b, 4
0x140070163  jz      loc_14007038F
0x140070169  mov     rdx, [r9+50h]
0x14007016d  lea     rcx, [rbp+arg_18]
0x140070171  mov     r9, [r14+18h]
0x140070175  mov     rdx, [rdx+60h]
0x140070179  call    Srv2QueryDaxPhysicalExtents
0x14007017e  mov     r15, [rbp+arg_18]
0x140070182  mov     ebx, eax
0x140070184  test    eax, eax
0x140070186  js      loc_14007039F
0x14007018c  mov     rax, cs:MmBadPointer
0x140070193  lea     r8, [rbp+var_38]
0x140070197  mov     r9, r15
0x14007019a  lea     rdx, [rbp+arg_0]
0x14007019e  mov     rcx, [rax]
0x1400701a1  mov     [rsp+68h+var_40], rcx
0x1400701a6  lea     rcx, [rbp+arg_10]
0x1400701aa  call    Srv2PhysExtentsToMdlChain
0x1400701af  mov     rsi, [rbp+arg_10]
0x1400701b3  mov     ebx, eax
0x1400701b5  test    eax, eax
0x1400701b7  js      loc_14007039F
0x1400701bd  mov     rcx, rsi
0x1400701c0  call    Srv2SumMdlByteCount
0x1400701c5  mov     rbx, [rbp+var_38]
0x1400701c9  cmp     rax, rbx
0x1400701cc  jz      short loc_1400701D0
0x1400701ce  int     2Ch; Windows NT - assertion failure
0x1400701d0  mov     r8, [r14+18h]
0x1400701d4  cmp     rbx, r8
0x1400701d7  jz      short loc_1400701DB
0x1400701d9  int     2Ch; Windows NT - assertion failure
0x1400701db  mov     rcx, r15
0x1400701de  call    Srv2SumPhysExtentsPages
0x1400701e3  test    r8, 0FFFh
0x1400701ea  mov     rcx, r12
0x1400701ed  setnz   cl
0x1400701f0  shr     r8, 0Ch
0x1400701f4  add     rcx, r8
0x1400701f7  cmp     rcx, rax
0x1400701fa  jz      short loc_1400701FE
0x1400701fc  int     2Ch; Windows NT - assertion failure
0x1400701fe  test    rsi, rsi
0x140070201  jz      loc_14007039A
0x140070207  mov     edx, 48h ; 'H'
0x14007020c  mov     r8d, 6478534Ch
0x140070212  lea     ecx, [rdx-8]
0x140070215  call    cs:__imp_ExAllocatePool2
0x14007021c  nop     dword ptr [rax+rax+00h]
0x140070221  mov     rdi, rax
0x140070224  test    rax, rax
0x140070227  jnz     short loc_140070233
0x140070229  mov     ebx, 0C000009Ah
0x14007022e  jmp     loc_14007039F
0x140070233  mov     [rax+8], rdi
0x140070237  lea     rcx, [rax+28h]
0x14007023b  mov     [rax], rdi
0x14007023e  mov     r9, rbx
0x140070241  mov     rdx, [r13+60h]
0x140070245  mov     r8, rsi
0x140070248  mov     eax, [rbp+arg_8]
0x14007024b  mov     [rsp+68h+var_48], eax
0x14007024f  mov     rdx, [rdx+1E0h]
0x140070256  call    cs:__imp_SrvNetRdmaRegisterMr
0x14007025d  nop     dword ptr [rax+rax+00h]
0x140070262  mov     ebx, eax
0x140070264  test    eax, eax
0x140070266  js      loc_140070385
0x14007026c  mov     rcx, [rdi+28h]
0x140070270  lea     r8, [rdi+3Ch]
0x140070274  lea     rdx, [rdi+40h]
0x140070278  call    cs:__imp_SrvNetRdmaGetMrToken
0x14007027f  nop     dword ptr [rax+rax+00h]
0x140070284  mov     ebx, eax
0x140070286  test    eax, eax
0x140070288  js      loc_140070385
0x14007028e  cmp     [rdi+40h], r12
0x140070292  jz      loc_140070380
0x140070298  mov     eax, [rdi+3Ch]
0x14007029b  test    eax, eax
0x14007029d  jz      loc_140070380
0x1400702a3  mov     rbx, [rbp+var_30]
0x1400702a7  add     eax, 20h ; ' '
0x1400702aa  cmp     [rbx+0C8h], eax
0x1400702b0  jnb     short loc_1400702BC
0x1400702b2  mov     ebx, 0C0000023h
0x1400702b7  jmp     loc_140070385
0x1400702bc  mov     r12d, 1
0x1400702c2  mov     eax, r12d
0x1400702c5  lock xadd cs:Smb2RdmaMappingIdGenerator, eax
0x1400702cd  add     eax, r12d
0x1400702d0  lea     rcx, [r14+20h]; void *
0x1400702d4  mov     [rdi+10h], eax
0x1400702d7  mov     rax, [r14+10h]
0x1400702db  mov     [rdi+18h], rax
0x1400702df  mov     rax, [r14+18h]
0x1400702e3  mov     [rdi+20h], rax
0x1400702e7  mov     [rdi+30h], rsi
0x1400702eb  xor     esi, esi
0x1400702ed  mov     [rdi+38h], esi
0x1400702f0  mov     [r14], r12d
0x1400702f3  mov     eax, [rdi+10h]
0x1400702f6  mov     [r14+18h], eax
0x1400702fa  mov     rax, [rdi+18h]
0x1400702fe  mov     [r14+8], rax
0x140070302  mov     rax, [rdi+20h]
0x140070306  mov     [r14+10h], rax
0x14007030a  mov     eax, [rdi+3Ch]
0x14007030d  mov     [r14+1Ch], eax
0x140070311  mov     r8d, [rdi+3Ch]; Size
0x140070315  mov     rdx, [rdi+40h]; Src
0x140070319  call    memmove
0x14007031e  mov     rcx, [rbx+48h]
0x140070322  lea     rdx, [rbp+LockHandle]; LockHandle
0x140070326  add     rcx, 70h ; 'p'; SpinLock
0x14007032a  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140070331  nop     dword ptr [rax+rax+00h]
0x140070336  mov     rax, [rbx+50h]
0x14007033a  add     rax, 88h
0x140070340  mov     rcx, [rax+8]
0x140070344  cmp     [rcx], rax
0x140070347  jz      short loc_14007034E
0x140070349  lea     ecx, [rsi+3]
0x14007034c  int     29h; Win8: RtlFailFast(ecx)
0x14007034e  mov     [rdi+8], rcx
0x140070352  mov     [rdi], rax
0x140070355  mov     [rcx], rdi
0x140070358  lea     rcx, [rbp+LockHandle]; LockHandle
0x14007035c  mov     [rax+8], rdi
0x140070360  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140070367  nop     dword ptr [rax+rax+00h]
0x14007036c  lock add cs:Smb2XmrActiveMappingCount, r12d
0x140070374  mov     r12d, [r14+1Ch]
0x140070378  add     r12d, 20h ; ' '
0x14007037c  xor     ebx, ebx
0x14007037e  jmp     short loc_14007039F
0x140070380  mov     ebx, 0C0000239h
0x140070385  mov     rcx, rdi; P
0x140070388  call    Smb2FreeRdmaMapping
0x14007038d  jmp     short loc_14007039F
0x14007038f  mov     ebx, 0C0000002h
0x140070394  test    r8b, 8
0x140070398  jnz     short loc_14007039F
0x14007039a  mov     ebx, 0C0000001h
0x14007039f  xor     edx, edx
0x1400703a1  mov     rcx, rsi; P
0x1400703a4  call    Srv2FreeMdlChain
0x1400703a9  test    r15, r15
0x1400703ac  jz      short loc_1400703C2
0x1400703ae  mov     edx, 7065534Ch; Tag
0x1400703b3  mov     rcx, r15; P
0x1400703b6  call    cs:__imp_ExFreePoolWithTag
0x1400703bd  nop     dword ptr [rax+rax+00h]
0x1400703c2  mov     rax, [r13+78h]
0x1400703c6  mov     [rax+30h], ebx
0x1400703c9  xor     eax, eax
0x1400703cb  test    ebx, ebx
0x1400703cd  cmovns  eax, r12d
0x1400703d1  mov     ecx, eax
0x1400703d3  mov     rax, [r13+78h]
0x1400703d7  mov     [rax+38h], rcx
0x1400703db  mov     rcx, r13
0x1400703de  call    Smb2ContinueIoctl
0x1400703e3  add     rsp, 68h
0x1400703e7  pop     r15
0x1400703e9  pop     r14
0x1400703eb  pop     r13
0x1400703ed  pop     r12
0x1400703ef  pop     rdi
0x1400703f0  pop     rsi
0x1400703f1  pop     rbx
0x1400703f2  pop     rbp
0x1400703f3  retn
```
