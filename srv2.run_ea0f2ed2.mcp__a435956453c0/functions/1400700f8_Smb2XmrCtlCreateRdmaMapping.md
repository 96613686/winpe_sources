# Smb2XmrCtlCreateRdmaMapping

- ea: `0x1400700f8`
- end: `0x140070445`
- name: `Smb2XmrCtlCreateRdmaMapping`
- size: `845`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400822e0`

## callees

- `0x140038680`
- `0x140059174`
- `0x1400591e8`
- `0x14005e940`
- `0x14005ea7c`
- `0x14005ecc4`
- `0x14005edc4`
- `0x1400700f8`
- `0x140082fb0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140070265`
- `ntoskrnl!ExAllocatePool2` at `0x140070265`
- `ntoskrnl!ExFreePoolWithTag` at `0x140070406`
- `ntoskrnl!ExFreePoolWithTag` at `0x140070406`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14007037a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14007037a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400703b0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400703b0`
- `ntoskrnl!MmBadPointer` at `0x1400701dc`
- `srvnet!SrvNetRdmaRegisterMr` at `0x1400702a6`
- `srvnet!SrvNetRdmaRegisterMr` at `0x1400702a6`
- `srvnet!SrvNetRdmaGetMrToken` at `0x1400702c8`
- `srvnet!SrvNetRdmaGetMrToken` at `0x1400702c8`

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
0x1400700f8  push    rbp
0x1400700fa  push    rbx
0x1400700fb  push    rsi
0x1400700fc  push    rdi
0x1400700fd  push    r12
0x1400700ff  push    r13
0x140070101  push    r14
0x140070103  push    r15
0x140070105  mov     rbp, rsp
0x140070108  sub     rsp, 68h
0x14007010c  mov     r9, [rcx+230h]
0x140070113  xor     eax, eax
0x140070115  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140070119  xor     r15d, r15d
0x14007011c  xor     esi, esi
0x14007011e  mov     [rbp+var_30], r9
0x140070122  xorps   xmm0, xmm0
0x140070125  mov     [rbp+arg_18], r15
0x140070129  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14007012d  mov     r14, [r9+0D8h]
0x140070134  xor     r12d, r12d
0x140070137  mov     r13, rcx
0x14007013a  mov     [rbp+arg_10], rsi
0x14007013e  mov     [rbp+arg_0], eax
0x140070141  mov     [rbp+var_38], rax
0x140070145  cmp     dword ptr [r14], 1
0x140070149  jz      short loc_140070155
0x14007014b  mov     ebx, 0C0000058h
0x140070150  jmp     loc_1400703EF
0x140070155  mov     r8d, [r14+4]
0x140070159  mov     eax, r8d
0x14007015c  and     eax, 0Ch
0x14007015f  cmp     eax, 0Ch
0x140070162  jnz     short loc_14007016E
0x140070164  mov     ebx, 0C0000030h
0x140070169  jmp     loc_1400703EF
0x14007016e  test    r8b, 1
0x140070172  jnz     short loc_14007017E
0x140070174  mov     ebx, 0C00000BBh
0x140070179  jmp     loc_1400703EF
0x14007017e  test    eax, eax
0x140070180  jnz     short loc_14007018C
0x140070182  mov     ebx, 0C000000Dh
0x140070187  jmp     loc_1400703EF
0x14007018c  mov     ecx, [r14+8]
0x140070190  and     ecx, 1
0x140070193  mov     edx, ecx
0x140070195  or      edx, 2
0x140070198  test    byte ptr [r14+8], 2
0x14007019d  cmovz   edx, ecx
0x1400701a0  mov     ecx, edx
0x1400701a2  or      ecx, 4
0x1400701a5  test    r8b, 2
0x1400701a9  cmovz   ecx, edx
0x1400701ac  mov     [rbp+arg_8], ecx
0x1400701af  test    r8b, 4
0x1400701b3  jz      loc_1400703DF
0x1400701b9  mov     rdx, [r9+50h]
0x1400701bd  lea     rcx, [rbp+arg_18]
0x1400701c1  mov     r9, [r14+18h]
0x1400701c5  mov     rdx, [rdx+60h]
0x1400701c9  call    Srv2QueryDaxPhysicalExtents
0x1400701ce  mov     r15, [rbp+arg_18]
0x1400701d2  mov     ebx, eax
0x1400701d4  test    eax, eax
0x1400701d6  js      loc_1400703EF
0x1400701dc  mov     rax, cs:MmBadPointer
0x1400701e3  lea     r8, [rbp+var_38]
0x1400701e7  mov     r9, r15
0x1400701ea  lea     rdx, [rbp+arg_0]
0x1400701ee  mov     rcx, [rax]
0x1400701f1  mov     [rsp+68h+var_40], rcx
0x1400701f6  lea     rcx, [rbp+arg_10]
0x1400701fa  call    Srv2PhysExtentsToMdlChain
0x1400701ff  mov     rsi, [rbp+arg_10]
0x140070203  mov     ebx, eax
0x140070205  test    eax, eax
0x140070207  js      loc_1400703EF
0x14007020d  mov     rcx, rsi
0x140070210  call    Srv2SumMdlByteCount
0x140070215  mov     rbx, [rbp+var_38]
0x140070219  cmp     rax, rbx
0x14007021c  jz      short loc_140070220
0x14007021e  int     2Ch; Windows NT - assertion failure
0x140070220  mov     r8, [r14+18h]
0x140070224  cmp     rbx, r8
0x140070227  jz      short loc_14007022B
0x140070229  int     2Ch; Windows NT - assertion failure
0x14007022b  mov     rcx, r15
0x14007022e  call    Srv2SumPhysExtentsPages
0x140070233  test    r8, 0FFFh
0x14007023a  mov     rcx, r12
0x14007023d  setnz   cl
0x140070240  shr     r8, 0Ch
0x140070244  add     rcx, r8
0x140070247  cmp     rcx, rax
0x14007024a  jz      short loc_14007024E
0x14007024c  int     2Ch; Windows NT - assertion failure
0x14007024e  test    rsi, rsi
0x140070251  jz      loc_1400703EA
0x140070257  mov     edx, 48h ; 'H'
0x14007025c  mov     r8d, 6478534Ch
0x140070262  lea     ecx, [rdx-8]
0x140070265  call    cs:__imp_ExAllocatePool2
0x14007026c  nop     dword ptr [rax+rax+00h]
0x140070271  mov     rdi, rax
0x140070274  test    rax, rax
0x140070277  jnz     short loc_140070283
0x140070279  mov     ebx, 0C000009Ah
0x14007027e  jmp     loc_1400703EF
0x140070283  mov     [rax+8], rdi
0x140070287  lea     rcx, [rax+28h]
0x14007028b  mov     [rax], rdi
0x14007028e  mov     r9, rbx
0x140070291  mov     rdx, [r13+60h]
0x140070295  mov     r8, rsi
0x140070298  mov     eax, [rbp+arg_8]
0x14007029b  mov     [rsp+68h+var_48], eax
0x14007029f  mov     rdx, [rdx+1E0h]
0x1400702a6  call    cs:__imp_SrvNetRdmaRegisterMr
0x1400702ad  nop     dword ptr [rax+rax+00h]
0x1400702b2  mov     ebx, eax
0x1400702b4  test    eax, eax
0x1400702b6  js      loc_1400703D5
0x1400702bc  mov     rcx, [rdi+28h]
0x1400702c0  lea     r8, [rdi+3Ch]
0x1400702c4  lea     rdx, [rdi+40h]
0x1400702c8  call    cs:__imp_SrvNetRdmaGetMrToken
0x1400702cf  nop     dword ptr [rax+rax+00h]
0x1400702d4  mov     ebx, eax
0x1400702d6  test    eax, eax
0x1400702d8  js      loc_1400703D5
0x1400702de  cmp     [rdi+40h], r12
0x1400702e2  jz      loc_1400703D0
0x1400702e8  mov     eax, [rdi+3Ch]
0x1400702eb  test    eax, eax
0x1400702ed  jz      loc_1400703D0
0x1400702f3  mov     rbx, [rbp+var_30]
0x1400702f7  add     eax, 20h ; ' '
0x1400702fa  cmp     [rbx+0C8h], eax
0x140070300  jnb     short loc_14007030C
0x140070302  mov     ebx, 0C0000023h
0x140070307  jmp     loc_1400703D5
0x14007030c  mov     r12d, 1
0x140070312  mov     eax, r12d
0x140070315  lock xadd cs:Smb2RdmaMappingIdGenerator, eax
0x14007031d  add     eax, r12d
0x140070320  lea     rcx, [r14+20h]; void *
0x140070324  mov     [rdi+10h], eax
0x140070327  mov     rax, [r14+10h]
0x14007032b  mov     [rdi+18h], rax
0x14007032f  mov     rax, [r14+18h]
0x140070333  mov     [rdi+20h], rax
0x140070337  mov     [rdi+30h], rsi
0x14007033b  xor     esi, esi
0x14007033d  mov     [rdi+38h], esi
0x140070340  mov     [r14], r12d
0x140070343  mov     eax, [rdi+10h]
0x140070346  mov     [r14+18h], eax
0x14007034a  mov     rax, [rdi+18h]
0x14007034e  mov     [r14+8], rax
0x140070352  mov     rax, [rdi+20h]
0x140070356  mov     [r14+10h], rax
0x14007035a  mov     eax, [rdi+3Ch]
0x14007035d  mov     [r14+1Ch], eax
0x140070361  mov     r8d, [rdi+3Ch]; Size
0x140070365  mov     rdx, [rdi+40h]; Src
0x140070369  call    memmove
0x14007036e  mov     rcx, [rbx+48h]
0x140070372  lea     rdx, [rbp+LockHandle]; LockHandle
0x140070376  add     rcx, 70h ; 'p'; SpinLock
0x14007037a  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140070381  nop     dword ptr [rax+rax+00h]
0x140070386  mov     rax, [rbx+50h]
0x14007038a  add     rax, 88h
0x140070390  mov     rcx, [rax+8]
0x140070394  cmp     [rcx], rax
0x140070397  jz      short loc_14007039E
0x140070399  lea     ecx, [rsi+3]
0x14007039c  int     29h; Win8: RtlFailFast(ecx)
0x14007039e  mov     [rdi+8], rcx
0x1400703a2  mov     [rdi], rax
0x1400703a5  mov     [rcx], rdi
0x1400703a8  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400703ac  mov     [rax+8], rdi
0x1400703b0  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400703b7  nop     dword ptr [rax+rax+00h]
0x1400703bc  lock add cs:Smb2XmrActiveMappingCount, r12d
0x1400703c4  mov     r12d, [r14+1Ch]
0x1400703c8  add     r12d, 20h ; ' '
0x1400703cc  xor     ebx, ebx
0x1400703ce  jmp     short loc_1400703EF
0x1400703d0  mov     ebx, 0C0000239h
0x1400703d5  mov     rcx, rdi; P
0x1400703d8  call    Smb2FreeRdmaMapping
0x1400703dd  jmp     short loc_1400703EF
0x1400703df  mov     ebx, 0C0000002h
0x1400703e4  test    r8b, 8
0x1400703e8  jnz     short loc_1400703EF
0x1400703ea  mov     ebx, 0C0000001h
0x1400703ef  xor     edx, edx
0x1400703f1  mov     rcx, rsi; P
0x1400703f4  call    Srv2FreeMdlChain
0x1400703f9  test    r15, r15
0x1400703fc  jz      short loc_140070412
0x1400703fe  mov     edx, 7065534Ch; Tag
0x140070403  mov     rcx, r15; P
0x140070406  call    cs:__imp_ExFreePoolWithTag
0x14007040d  nop     dword ptr [rax+rax+00h]
0x140070412  mov     rax, [r13+78h]
0x140070416  mov     [rax+30h], ebx
0x140070419  xor     eax, eax
0x14007041b  test    ebx, ebx
0x14007041d  cmovns  eax, r12d
0x140070421  mov     ecx, eax
0x140070423  mov     rax, [r13+78h]
0x140070427  mov     [rax+38h], rcx
0x14007042b  mov     rcx, r13
0x14007042e  call    Smb2ContinueIoctl
0x140070433  add     rsp, 68h
0x140070437  pop     r15
0x140070439  pop     r14
0x14007043b  pop     r13
0x14007043d  pop     r12
0x14007043f  pop     rdi
0x140070440  pop     rsi
0x140070441  pop     rbx
0x140070442  pop     rbp
0x140070443  retn
```
