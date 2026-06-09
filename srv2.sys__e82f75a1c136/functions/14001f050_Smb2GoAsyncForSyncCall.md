# Smb2GoAsyncForSyncCall

- ea: `0x14001f050`
- end: `0x14001f37d`
- name: `Smb2GoAsyncForSyncCall`
- size: `813`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140059008`
- `0x140068f48`
- `0x140078f78`
- `0x140079c30`
- `0x14007e340`
- `0x14007ea50`
- `0x140082290`

## callees

- `0x140004960`
- `0x140004eb4`
- `0x140005070`
- `0x140007400`
- `0x140008190`
- `0x140017d00`
- `0x14001f050`
- `0x1400222ec`
- `0x140038680`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001f205`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001f205`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14001f331`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14001f331`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14001f34d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14001f34d`
- `srvnet!SrvNetSendData` at `0x14001f2e3`
- `srvnet!SrvNetSendData` at `0x14001f2e3`

## string_xrefs

- `0x14001f311`: `Srv2PostToThreadPool`

## pseudocode

```c
PSLIST_ENTRY __fastcall Smb2GoAsyncForSyncCall(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  unsigned int v4; // r14d
  char v5; // r15
  __int64 v6; // rbp
  int v7; // ecx
  __int64 v8; // rbx
  __int64 *v9; // rax
  __int64 v10; // r8
  int v11; // ebx
  PSLIST_ENTRY result; // rax
  __int64 v13; // rcx
  PVOID v14; // rax
  __int64 v15; // rax
  bool v16; // zf
  __int64 v17; // rbx
  __int64 v18; // rbx
  __int64 v19; // rbx
  ULONG BugCheckOnFailure; // [rsp+20h] [rbp-48h]
  __int64 v21; // [rsp+70h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 560);
  v21 = 0;
  if ( !*(_BYTE *)(v2 + 2) )
  {
    v4 = 256;
    v5 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids, a1);
    }
    Smb2SetError(a1, 259, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\notify.c", 757);
    v6 = *(_QWORD *)(*(_QWORD *)(a1 + 312) + 24LL);
    *(_DWORD *)(v6 + 16) |= 2u;
    v7 = *(_DWORD *)(v6 + 16);
    *(_QWORD *)(v6 + 32) = *(_QWORD *)(v2 + 168);
    if ( (v7 & 8) != 0 )
    {
      v5 = 1;
      *(_DWORD *)(v6 + 16) = v7 & 0xFFFFFFF7;
    }
    *(_WORD *)(v2 + 1) = 256;
    v8 = *(_QWORD *)(a1 + 296);
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 312) + 36LL) > 0x100u )
      v4 = *(_DWORD *)(*(_QWORD *)(a1 + 312) + 36LL);
    if ( v8 )
    {
      if ( *(_DWORD *)v8 >= v4 )
      {
LABEL_25:
        v13 = *(_QWORD *)(v8 + 8);
        if ( (*(_BYTE *)(v13 + 10) & 5) != 0 )
          v14 = *(PVOID *)(v13 + 24);
        else
          v14 = MmMapLockedPagesSpecifyCache((PMDL)v13, 0, MmCached, 0, 0, 0x40000010u);
        memmove(v14, *(const void **)(*(_QWORD *)(a1 + 312) + 24LL), *(unsigned int *)(*(_QWORD *)(a1 + 312) + 36LL));
        *(_QWORD *)(v8 + 16) = &Smb2ProcAsyncSendComplete;
        *(_QWORD *)(v8 + 24) = a1;
        *(_DWORD *)(v8 + 4) = 0;
        *(_DWORD *)v8 = *(_DWORD *)(*(_QWORD *)(a1 + 312) + 36LL);
        *(_DWORD *)(v8 + 88) = 0;
        *(_QWORD *)(v8 + 104) = 0;
        *(_QWORD *)(v8 + 112) = 0;
        *(_QWORD *)(v8 + 120) = 0;
        if ( (*(_DWORD *)(a1 + 484) & 0x40) != 0 )
        {
          *(_DWORD *)(v8 + 88) = *(_DWORD *)(*(_QWORD *)(v2 + 32) + 300LL);
          v15 = *(_QWORD *)(v2 + 56);
          if ( v15 )
          {
            *(_QWORD *)(v8 + 104) = *(_QWORD *)(v15 + 104) + 624LL;
            *(_QWORD *)(v8 + 112) = *(_QWORD *)(*(_QWORD *)(v2 + 56) + 104LL) + 640LL;
            *(_QWORD *)(v8 + 120) = *(_QWORD *)(*(_QWORD *)(v2 + 56) + 104LL) + 648LL;
          }
        }
        if ( ((_InterlockedExchangeAdd64((volatile signed __int64 *)a1, 1u) + 2) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
          __int2c();
        SrvNetSendData(*(_QWORD *)(*(_QWORD *)(a1 + 96) + 480LL), v8);
        if ( v5 )
          *(_DWORD *)(v6 + 16) |= 8u;
        goto LABEL_35;
      }
      Smb2FreeResponseBufferForAsyncCall(*(PVOID *)(a1 + 296));
      *(_QWORD *)(a1 + 296) = 0;
    }
    v9 = *(__int64 **)(v2 + 32);
    if ( v9 )
      v10 = *v9;
    else
      v10 = 0;
    v11 = Smb2AllocateResponseBufferForAsyncCall(&v21, v4, v10, *(_QWORD *)(a1 + 208));
    if ( v11 < 0 )
    {
      if ( v5 )
        *(_DWORD *)(v6 + 16) |= 8u;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids, a1);
      }
      Smb2SetError(a1, (unsigned int)v11, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\notify.c", 820);
      return (PSLIST_ENTRY)Srv2CompleteWorkItem(a1, 0);
    }
    v8 = v21;
    *(_QWORD *)(a1 + 296) = v21;
    goto LABEL_25;
  }
LABEL_35:
  v16 = *(_DWORD *)(a1 + 8) == 5;
  v17 = *(int *)(a1 + 72);
  *(_DWORD *)(a1 + 72) = v17;
  if ( v16 )
  {
    LOBYTE(BugCheckOnFailure) = 1;
    LOBYTE(a2) = 1;
    SRV2_PERF_ENTER_EX(a1 + 584, a2, 391, "Srv2PostToThreadPool", BugCheckOnFailure);
  }
  v18 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8 * v17 + 136);
  v19 = *(_QWORD *)(v18 + 8LL * KeGetCurrentNodeNumber() + 8);
  result = ExpInterlockedPushEntrySList((PSLIST_HEADER)(v19 + 16), (PSLIST_ENTRY)(a1 + 32));
  if ( !result && *(_WORD *)(v19 + 66) )
    return (PSLIST_ENTRY)RfspThreadPoolNodeWakeIdleWorker(v19);
  return result;
}

```

## disassembly

```asm
0x14001f050  push    rbx
0x14001f052  push    rbp
0x14001f053  push    rsi
0x14001f054  push    rdi
0x14001f055  push    r14
0x14001f057  push    r15
0x14001f059  sub     rsp, 38h
0x14001f05d  mov     rsi, [rcx+230h]
0x14001f064  mov     rdi, rcx
0x14001f067  mov     [rsp+68h+arg_0], 0
0x14001f070  cmp     byte ptr [rsi+2], 0
0x14001f074  jnz     loc_14001F2F8
0x14001f07a  mov     r14d, 100h
0x14001f080  xor     r15b, r15b
0x14001f083  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001f08a  lea     rax, WPP_GLOBAL_Control
0x14001f091  cmp     rcx, rax
0x14001f094  jz      short loc_14001F0BB
0x14001f096  mov     eax, [rcx+2Ch]
0x14001f099  test    al, 1
0x14001f09b  jz      short loc_14001F0BB
0x14001f09d  cmp     byte ptr [rcx+29h], 2
0x14001f0a1  jb      short loc_14001F0BB
0x14001f0a3  mov     rcx, [rcx+18h]
0x14001f0a7  lea     r8, WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids
0x14001f0ae  mov     edx, 15h
0x14001f0b3  mov     r9, rdi
0x14001f0b6  call    WPP_SF_q
0x14001f0bb  mov     r9d, 2F5h
0x14001f0c1  lea     r8, aOnecoreBaseFsR_7; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14001f0c8  mov     edx, 103h
0x14001f0cd  mov     rcx, rdi
0x14001f0d0  call    _Smb2SetError
0x14001f0d5  mov     rax, [rdi+138h]
0x14001f0dc  mov     rbp, [rax+18h]
0x14001f0e0  or      dword ptr [rbp+10h], 2
0x14001f0e4  mov     ecx, [rbp+10h]
0x14001f0e7  mov     rax, [rsi+0A8h]
0x14001f0ee  mov     [rbp+20h], rax
0x14001f0f2  test    cl, 8
0x14001f0f5  jz      short loc_14001F100
0x14001f0f7  and     ecx, 0FFFFFFF7h
0x14001f0fa  mov     r15b, 1
0x14001f0fd  mov     [rbp+10h], ecx
0x14001f100  mov     [rsi+1], r14w
0x14001f105  mov     rax, [rdi+138h]
0x14001f10c  mov     rbx, [rdi+128h]
0x14001f113  mov     ecx, [rax+24h]
0x14001f116  cmp     ecx, r14d
0x14001f119  cmova   r14d, ecx
0x14001f11d  test    rbx, rbx
0x14001f120  jz      short loc_14001F13E
0x14001f122  cmp     [rbx], r14d
0x14001f125  jnb     loc_14001F1DC
0x14001f12b  mov     rcx, rbx; P
0x14001f12e  call    Smb2FreeResponseBufferForAsyncCall
0x14001f133  mov     qword ptr [rdi+128h], 0
0x14001f13e  mov     rax, [rsi+20h]
0x14001f142  test    rax, rax
0x14001f145  jz      short loc_14001F14C
0x14001f147  mov     r8, [rax]
0x14001f14a  jmp     short loc_14001F14F
0x14001f14c  xor     r8d, r8d
0x14001f14f  mov     r9, [rdi+0D0h]
0x14001f156  lea     rcx, [rsp+68h+arg_0]
0x14001f15b  mov     edx, r14d
0x14001f15e  call    Smb2AllocateResponseBufferForAsyncCall
0x14001f163  mov     ebx, eax
0x14001f165  test    eax, eax
0x14001f167  jns     short loc_14001F1D0
0x14001f169  test    r15b, r15b
0x14001f16c  jz      short loc_14001F172
0x14001f16e  or      dword ptr [rbp+10h], 8
0x14001f172  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001f179  lea     rax, WPP_GLOBAL_Control
0x14001f180  cmp     rcx, rax
0x14001f183  jz      short loc_14001F1AA
0x14001f185  mov     eax, [rcx+2Ch]
0x14001f188  test    al, 1
0x14001f18a  jz      short loc_14001F1AA
0x14001f18c  cmp     byte ptr [rcx+29h], 1
0x14001f190  jb      short loc_14001F1AA
0x14001f192  mov     rcx, [rcx+18h]
0x14001f196  lea     r8, WPP_ee4bf590961a3aba7bda4d94b676f981_Traceguids
0x14001f19d  mov     edx, 16h
0x14001f1a2  mov     r9, rdi
0x14001f1a5  call    WPP_SF_q
0x14001f1aa  mov     r9d, 334h
0x14001f1b0  lea     r8, aOnecoreBaseFsR_7; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14001f1b7  mov     edx, ebx
0x14001f1b9  mov     rcx, rdi
0x14001f1bc  call    _Smb2SetError
0x14001f1c1  xor     edx, edx
0x14001f1c3  mov     rcx, rdi
0x14001f1c6  call    Srv2CompleteWorkItem
0x14001f1cb  jmp     loc_14001F36F
0x14001f1d0  mov     rbx, [rsp+68h+arg_0]
0x14001f1d5  mov     [rdi+128h], rbx
0x14001f1dc  mov     rcx, [rbx+8]; MemoryDescriptorList
0x14001f1e0  test    byte ptr [rcx+0Ah], 5
0x14001f1e4  jz      short loc_14001F1EC
0x14001f1e6  mov     rax, [rcx+18h]
0x14001f1ea  jmp     short loc_14001F211
0x14001f1ec  xor     r9d, r9d; RequestedAddress
0x14001f1ef  mov     [rsp+68h+Priority], 40000010h; Priority
0x14001f1f7  xor     edx, edx; AccessMode
0x14001f1f9  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14001f201  lea     r8d, [r9+1]; CacheType
0x14001f205  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001f20c  nop     dword ptr [rax+rax+00h]
0x14001f211  mov     rdx, [rdi+138h]
0x14001f218  mov     rcx, rax; void *
0x14001f21b  mov     r8d, [rdx+24h]; Size
0x14001f21f  mov     rdx, [rdx+18h]; Src
0x14001f223  call    memmove
0x14001f228  lea     rax, Smb2ProcAsyncSendComplete
0x14001f22f  mov     [rbx+10h], rax
0x14001f233  mov     [rbx+18h], rdi
0x14001f237  mov     dword ptr [rbx+4], 0
0x14001f23e  mov     rax, [rdi+138h]
0x14001f245  mov     ecx, [rax+24h]
0x14001f248  mov     [rbx], ecx
0x14001f24a  mov     dword ptr [rbx+58h], 0
0x14001f251  mov     qword ptr [rbx+68h], 0
0x14001f259  mov     qword ptr [rbx+70h], 0
0x14001f261  mov     qword ptr [rbx+78h], 0
0x14001f269  mov     eax, [rdi+1E4h]
0x14001f26f  test    al, 40h
0x14001f271  jz      short loc_14001F2BD
0x14001f273  mov     rax, [rsi+20h]
0x14001f277  mov     ecx, [rax+12Ch]
0x14001f27d  mov     [rbx+58h], ecx
0x14001f280  mov     rax, [rsi+38h]
0x14001f284  test    rax, rax
0x14001f287  jz      short loc_14001F2BD
0x14001f289  mov     rax, [rax+68h]
0x14001f28d  add     rax, 270h
0x14001f293  mov     [rbx+68h], rax
0x14001f297  mov     rax, [rsi+38h]
0x14001f29b  mov     rcx, [rax+68h]
0x14001f29f  add     rcx, 280h
0x14001f2a6  mov     [rbx+70h], rcx
0x14001f2aa  mov     rax, [rsi+38h]
0x14001f2ae  mov     rcx, [rax+68h]
0x14001f2b2  add     rcx, 288h
0x14001f2b9  mov     [rbx+78h], rcx
0x14001f2bd  mov     eax, 1
0x14001f2c2  lock xadd [rdi], rax
0x14001f2c7  add     rax, 2
0x14001f2cb  test    rax, 0FFFFFFFFFFFFFFFEh
0x14001f2d1  jnz     short loc_14001F2D5
0x14001f2d3  int     2Ch; Windows NT - assertion failure
0x14001f2d5  mov     rcx, [rdi+60h]
0x14001f2d9  mov     rdx, rbx
0x14001f2dc  mov     rcx, [rcx+1E0h]
0x14001f2e3  call    cs:__imp_SrvNetSendData
0x14001f2ea  nop     dword ptr [rax+rax+00h]
0x14001f2ef  test    r15b, r15b
0x14001f2f2  jz      short loc_14001F2F8
0x14001f2f4  or      dword ptr [rbp+10h], 8
0x14001f2f8  cmp     dword ptr [rdi+8], 5
0x14001f2fc  movsxd  rbx, dword ptr [rdi+48h]
0x14001f300  mov     [rdi+48h], ebx
0x14001f303  jnz     short loc_14001F325
0x14001f305  lea     rcx, [rdi+248h]
0x14001f30c  mov     byte ptr [rsp+68h+BugCheckOnFailure], 1
0x14001f311  lea     r9, SourceString; "Srv2PostToThreadPool"
0x14001f318  mov     r8d, 187h
0x14001f31e  mov     dl, 1
0x14001f320  call    SRV2_PERF_ENTER_EX
0x14001f325  mov     rax, [rdi+40h]
0x14001f329  mov     rbx, [rax+rbx*8+88h]
0x14001f331  call    cs:__imp_KeGetCurrentNodeNumber
0x14001f338  nop     dword ptr [rax+rax+00h]
0x14001f33d  movzx   eax, ax
0x14001f340  lea     rdx, [rdi+20h]; ListEntry
0x14001f344  mov     rbx, [rbx+rax*8+8]
0x14001f349  lea     rcx, [rbx+10h]; ListHead
0x14001f34d  call    cs:__imp_ExpInterlockedPushEntrySList
0x14001f354  nop     dword ptr [rax+rax+00h]
0x14001f359  test    rax, rax
0x14001f35c  jnz     short loc_14001F36F
0x14001f35e  movzx   edx, word ptr [rbx+42h]
0x14001f362  cmp     ax, dx
0x14001f365  jz      short loc_14001F36F
0x14001f367  mov     rcx, rbx
0x14001f36a  call    RfspThreadPoolNodeWakeIdleWorker
0x14001f36f  add     rsp, 38h
0x14001f373  pop     r15
0x14001f375  pop     r14
0x14001f377  pop     rdi
0x14001f378  pop     rsi
0x14001f379  pop     rbp
0x14001f37a  pop     rbx
0x14001f37b  retn
```
