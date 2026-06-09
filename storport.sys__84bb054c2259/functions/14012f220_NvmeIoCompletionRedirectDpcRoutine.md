# NvmeIoCompletionRedirectDpcRoutine

- ea: `0x14012f220`
- end: `0x14012f42f`
- name: `NvmeIoCompletionRedirectDpcRoutine`
- size: `527`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14012f220`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!PoFxIdleComponent` at `0x14012f33d`
- `ntoskrnl!PoFxIdleComponent` at `0x14012f38c`
- `ntoskrnl!PoFxIdleComponent` at `0x14012f33d`
- `ntoskrnl!PoFxIdleComponent` at `0x14012f38c`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14012f317`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14012f317`
- `ntoskrnl!IofCompleteRequest` at `0x14012f2ba`
- `ntoskrnl!IofCompleteRequest` at `0x14012f2ba`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14012f365`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14012f365`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14012f241`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14012f241`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14012f3b7`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14012f3b7`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14012f261`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14012f3ff`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14012f261`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14012f3ff`

## pseudocode

```c
void __fastcall NvmeIoCompletionRedirectDpcRoutine(
        struct _KDPC *Dpc,
        PVOID DeferredContext,
        char *SystemArgument1,
        PVOID SystemArgument2)
{
  union _SLIST_HEADER *v5; // r14
  __int64 CurrentProcessorNumber; // rbp
  PSLIST_ENTRY v7; // rax
  __int64 v8; // rcx
  struct _SLIST_ENTRY *Next; // rdi
  char *v10; // rax
  _QWORD *v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rsi
  __int64 v14; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v15; // rcx
  __int64 v16; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v17; // rcx
  __int64 v18; // rcx
  struct _KDPC_WATCHDOG_INFORMATION WatchdogInformation; // [rsp+20h] [rbp-58h] BYREF

  v5 = (union _SLIST_HEADER *)(SystemArgument1 + 192);
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  _InterlockedExchange((volatile __int32 *)SystemArgument1 + 64, 0);
  v7 = ExpInterlockedFlushSList((PSLIST_HEADER)SystemArgument1 + 12);
  if ( !v7 )
    goto LABEL_19;
  do
  {
    do
    {
      v8 = 128;
      Next = v7->Next;
      if ( !*((_BYTE *)&v7->Next + 8) )
        v8 = 120;
      v10 = (char *)v7 - v8;
      v11 = *(_QWORD **)(*((_QWORD *)v10 + 23) + 24LL);
      if ( (v10[151] & 1) != 0 )
        _InterlockedDecrement(*(volatile signed __int32 **)(v11[87] + 8 * CurrentProcessorNumber));
      IofCompleteRequest((PIRP)v10, 0);
      v12 = v11[16];
      if ( !*(_BYTE *)v12
        && _InterlockedExchangeAdd(
             *(volatile signed __int32 **)(*(_QWORD *)(v12 + 24) + 8 * CurrentProcessorNumber),
             0xFFFFFFFF) == 1 )
      {
        v13 = *(_QWORD *)(v11[2] + 128LL);
        v14 = v11[16];
        if ( v14 )
        {
          if ( *(_QWORD *)(v14 + 8) )
          {
            v15 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v14 + 40);
            if ( v15 )
            {
              if ( ExAcquireRundownProtectionCacheAware(v15) )
              {
                PoFxIdleComponent(**(_QWORD **)(v11[16] + 8LL), 0, 2);
                v16 = v11[16];
                if ( v16 )
                {
                  if ( *(_QWORD *)(v16 + 8) )
                  {
                    v17 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v16 + 40);
                    if ( v17 )
                      ExReleaseRundownProtectionCacheAware(v17);
                  }
                }
              }
            }
          }
        }
        v18 = *(_QWORD *)(v13 + 168);
        if ( *(_BYTE *)v18 == 1 )
          PoFxIdleComponent(**(_QWORD **)(v18 + 8), 0, 2);
      }
      v7 = Next;
    }
    while ( Next );
LABEL_19:
    memset(&WatchdogInformation, 0, sizeof(WatchdogInformation));
    if ( KeQueryDpcWatchdogInformation(&WatchdogInformation) >= 0
      && (WatchdogInformation.DpcWatchdogLimit
       && 100 * (unsigned __int64)WatchdogInformation.DpcWatchdogCount < 5
                                                                       * (unsigned __int64)WatchdogInformation.DpcWatchdogLimit
       || WatchdogInformation.DpcTimeLimit
       && 100 * (unsigned __int64)WatchdogInformation.DpcTimeCount < 10
                                                                   * (unsigned __int64)WatchdogInformation.DpcTimeLimit) )
    {
      break;
    }
    v7 = ExpInterlockedFlushSList(v5);
  }
  while ( v7 );
}

```

## disassembly

```asm
0x14012f220  push    rbx
0x14012f222  push    rbp
0x14012f223  push    rsi
0x14012f224  push    rdi
0x14012f225  push    r14
0x14012f227  push    r15
0x14012f229  sub     rsp, 48h
0x14012f22d  mov     rax, cs:__security_cookie
0x14012f234  xor     rax, rsp
0x14012f237  mov     [rsp+78h+var_40], rax
0x14012f23c  xor     ecx, ecx; ProcNumber
0x14012f23e  mov     rbx, r8
0x14012f241  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14012f248  nop     dword ptr [rax+rax+00h]
0x14012f24d  xor     ecx, ecx
0x14012f24f  lea     r14, [rbx+0C0h]
0x14012f256  mov     ebp, eax
0x14012f258  xchg    ecx, [rbx+100h]
0x14012f25e  mov     rcx, r14; ListHead
0x14012f261  call    cs:__imp_ExpInterlockedFlushSList
0x14012f268  nop     dword ptr [rax+rax+00h]
0x14012f26d  mov     r15d, 78h ; 'x'
0x14012f273  test    rax, rax
0x14012f276  jz      loc_14012F3A4
0x14012f27c  nop     dword ptr [rax+00h]
0x14012f280  cmp     byte ptr [rax+8], 0
0x14012f284  mov     ecx, 80h
0x14012f289  mov     rdi, [rax]
0x14012f28c  cmovz   rcx, r15
0x14012f290  sub     rax, rcx
0x14012f293  test    byte ptr [rax+97h], 1
0x14012f29a  mov     rcx, [rax+0B8h]
0x14012f2a1  mov     rbx, [rcx+18h]
0x14012f2a5  jz      short loc_14012F2B5
0x14012f2a7  mov     rcx, [rbx+2B8h]
0x14012f2ae  mov     rdx, [rcx+rbp*8]
0x14012f2b2  lock dec dword ptr [rdx]
0x14012f2b5  xor     edx, edx; PriorityBoost
0x14012f2b7  mov     rcx, rax; Irp
0x14012f2ba  call    cs:__imp_IofCompleteRequest
0x14012f2c1  nop     dword ptr [rax+rax+00h]
0x14012f2c6  mov     rax, [rbx+80h]
0x14012f2cd  cmp     byte ptr [rax], 0
0x14012f2d0  jnz     loc_14012F398
0x14012f2d6  mov     rax, [rax+18h]
0x14012f2da  mov     rdx, [rax+rbp*8]
0x14012f2de  mov     eax, 0FFFFFFFFh
0x14012f2e3  lock xadd [rdx], eax
0x14012f2e7  cmp     eax, 1
0x14012f2ea  jnz     loc_14012F398
0x14012f2f0  mov     rax, [rbx+10h]
0x14012f2f4  mov     rsi, [rax+80h]
0x14012f2fb  mov     rax, [rbx+80h]
0x14012f302  test    rax, rax
0x14012f305  jz      short loc_14012F371
0x14012f307  cmp     qword ptr [rax+8], 0
0x14012f30c  jz      short loc_14012F371
0x14012f30e  mov     rcx, [rax+28h]; RunRefCacheAware
0x14012f312  test    rcx, rcx
0x14012f315  jz      short loc_14012F371
0x14012f317  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14012f31e  nop     dword ptr [rax+rax+00h]
0x14012f323  test    al, al
0x14012f325  jz      short loc_14012F371
0x14012f327  mov     rax, [rbx+80h]
0x14012f32e  xor     edx, edx
0x14012f330  mov     r8d, 2
0x14012f336  mov     rcx, [rax+8]
0x14012f33a  mov     rcx, [rcx]
0x14012f33d  call    cs:__imp_PoFxIdleComponent
0x14012f344  nop     dword ptr [rax+rax+00h]
0x14012f349  mov     rax, [rbx+80h]
0x14012f350  test    rax, rax
0x14012f353  jz      short loc_14012F371
0x14012f355  cmp     qword ptr [rax+8], 0
0x14012f35a  jz      short loc_14012F371
0x14012f35c  mov     rcx, [rax+28h]; RunRefCacheAware
0x14012f360  test    rcx, rcx
0x14012f363  jz      short loc_14012F371
0x14012f365  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14012f36c  nop     dword ptr [rax+rax+00h]
0x14012f371  mov     rcx, [rsi+0A8h]
0x14012f378  cmp     byte ptr [rcx], 1
0x14012f37b  jnz     short loc_14012F398
0x14012f37d  mov     rcx, [rcx+8]
0x14012f381  xor     edx, edx
0x14012f383  mov     r8d, 2
0x14012f389  mov     rcx, [rcx]
0x14012f38c  call    cs:__imp_PoFxIdleComponent
0x14012f393  nop     dword ptr [rax+rax+00h]
0x14012f398  mov     rax, rdi
0x14012f39b  test    rdi, rdi
0x14012f39e  jnz     loc_14012F280
0x14012f3a4  xorps   xmm0, xmm0
0x14012f3a7  lea     rcx, [rsp+78h+WatchdogInformation]; WatchdogInformation
0x14012f3ac  xor     eax, eax
0x14012f3ae  movups  xmmword ptr [rsp+78h+WatchdogInformation.DpcTimeLimit], xmm0
0x14012f3b3  mov     [rsp+78h+WatchdogInformation.Reserved], eax
0x14012f3b7  call    cs:__imp_KeQueryDpcWatchdogInformation
0x14012f3be  nop     dword ptr [rax+rax+00h]
0x14012f3c3  test    eax, eax
0x14012f3c5  js      short loc_14012F3FC
0x14012f3c7  mov     ecx, [rsp+78h+WatchdogInformation.DpcWatchdogLimit]
0x14012f3cb  test    ecx, ecx
0x14012f3cd  jz      short loc_14012F3E0
0x14012f3cf  mov     eax, [rsp+78h+WatchdogInformation.DpcWatchdogCount]
0x14012f3d3  lea     rcx, [rcx+rcx*4]
0x14012f3d7  imul    rdx, rax, 64h ; 'd'
0x14012f3db  cmp     rdx, rcx
0x14012f3de  jb      short loc_14012F414
0x14012f3e0  mov     ecx, [rsp+78h+WatchdogInformation.DpcTimeLimit]
0x14012f3e4  test    ecx, ecx
0x14012f3e6  jz      short loc_14012F3FC
0x14012f3e8  mov     eax, [rsp+78h+WatchdogInformation.DpcTimeCount]
0x14012f3ec  lea     rcx, [rcx+rcx*4]
0x14012f3f0  imul    rdx, rax, 64h ; 'd'
0x14012f3f4  add     rcx, rcx
0x14012f3f7  cmp     rdx, rcx
0x14012f3fa  jb      short loc_14012F414
0x14012f3fc  mov     rcx, r14; ListHead
0x14012f3ff  call    cs:__imp_ExpInterlockedFlushSList
0x14012f406  nop     dword ptr [rax+rax+00h]
0x14012f40b  test    rax, rax
0x14012f40e  jnz     loc_14012F280
0x14012f414  mov     rcx, [rsp+78h+var_40]
0x14012f419  xor     rcx, rsp; StackCookie
0x14012f41c  call    __security_check_cookie
0x14012f421  add     rsp, 48h
0x14012f425  pop     r15
0x14012f427  pop     r14
0x14012f429  pop     rdi
0x14012f42a  pop     rsi
0x14012f42b  pop     rbp
0x14012f42c  pop     rbx
0x14012f42d  retn
```
