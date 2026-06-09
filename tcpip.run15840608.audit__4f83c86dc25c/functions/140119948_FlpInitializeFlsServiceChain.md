# FlpInitializeFlsServiceChain

- ea: `0x140119948`
- end: `0x140119a7a`
- name: `FlpInitializeFlsServiceChain`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1401197e8`

## callees

- `0x140014a08`
- `0x140119758`
- `0x140119948`
- `0x140119a80`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401d760c`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401d760c`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1401199ac`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1401199ac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140119a03`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140119a03`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401199c5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401199c5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401199f7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401199f7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401199da`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401199da`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d7620`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d7620`
- `ntoskrnl!ExAllocatePool2` at `0x140119987`
- `ntoskrnl!ExAllocatePool2` at `0x140119987`

## string_xrefs

- `0x140119a5a`: `FLS service chain rundown object (FLNG)`
- `0x140119a29`: `FLS service chain (FLNG)`

## pseudocode

```c
__int64 __fastcall FlpInitializeFlsServiceChain(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rbx
  unsigned int v5; // ebx
  _QWORD *Pool2; // rax
  __int64 v8; // r8
  _QWORD *v9; // rdi
  PEX_RUNDOWN_REF_CACHE_AWARE CacheAwareRundownProtection; // rax
  __int64 v11; // r8
  __int64 v12; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v13; // rcx

  v4 = *(_QWORD *)(*(_QWORD *)(a1 + 72) + 32LL);
  if ( !*(_QWORD *)(v4 + 736) )
    return 0;
  Pool2 = (_QWORD *)ExAllocatePool2(64, 32, 1884507206);
  v9 = Pool2;
  if ( Pool2 )
  {
    Pool2[1] = Pool2;
    *Pool2 = Pool2;
    CacheAwareRundownProtection = ExAllocateCacheAwareRundownProtection((POOL_TYPE)512, 0x70534C46u);
    v9[2] = CacheAwareRundownProtection;
    if ( CacheAwareRundownProtection )
    {
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v4 + 752, 0);
      FlpDisableFlsServiceChain(v12, v9);
      ExReleasePushLockExclusiveEx(v4 + 752, 0);
      KeLeaveCriticalRegion();
      *a2 = v9;
      return 0;
    }
    v5 = -1073741670;
    if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        TCPIP_MEMORY_FAILURES,
        v11,
        L"FLS service chain rundown object (FLNG)");
    FlpCleanupFlsServiceChain(a1, v9);
    v13 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)v9[2];
    if ( v13 )
      ExFreeCacheAwareRundownProtection(v13);
    ExFreePoolWithTag(v9, 0x70534C46u);
  }
  else
  {
    v5 = -1073741670;
    if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        TCPIP_MEMORY_FAILURES,
        v8,
        L"FLS service chain (FLNG)");
  }
  return v5;
}

```

## disassembly

```asm
0x140119948  push    rbx
0x14011994a  push    rsi
0x14011994b  push    rdi
0x14011994c  push    r14
0x14011994e  sub     rsp, 28h
0x140119952  mov     rax, [rcx+48h]
0x140119956  mov     r14, rdx
0x140119959  mov     rsi, rcx
0x14011995c  mov     rbx, [rax+20h]
0x140119960  cmp     qword ptr [rbx+2E0h], 0
0x140119968  jnz     short loc_140119979
0x14011996a  xor     ebx, ebx
0x14011996c  mov     eax, ebx
0x14011996e  add     rsp, 28h
0x140119972  pop     r14
0x140119974  pop     rdi
0x140119975  pop     rsi
0x140119976  pop     rbx
0x140119977  retn
0x140119979  mov     edx, 20h ; ' '
0x14011997e  mov     r8d, 70534C46h
0x140119984  lea     ecx, [rdx+20h]
0x140119987  call    cs:__imp_ExAllocatePool2
0x14011998e  nop     dword ptr [rax+rax+00h]
0x140119993  mov     rdi, rax
0x140119996  test    rax, rax
0x140119999  jz      short loc_140119A17
0x14011999b  mov     edx, 70534C46h; PoolTag
0x1401199a0  mov     [rax+8], rax
0x1401199a4  mov     ecx, 200h; PoolType
0x1401199a9  mov     [rax], rax
0x1401199ac  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x1401199b3  nop     dword ptr [rax+rax+00h]
0x1401199b8  mov     [rdi+10h], rax
0x1401199bc  test    rax, rax
0x1401199bf  jz      loc_140119A48
0x1401199c5  call    cs:__imp_KeEnterCriticalRegion
0x1401199cc  nop     dword ptr [rax+rax+00h]
0x1401199d1  xor     edx, edx
0x1401199d3  lea     rcx, [rbx+2F0h]
0x1401199da  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1401199e1  nop     dword ptr [rax+rax+00h]
0x1401199e6  mov     rdx, rdi
0x1401199e9  call    FlpDisableFlsServiceChain
0x1401199ee  xor     edx, edx
0x1401199f0  lea     rcx, [rbx+2F0h]
0x1401199f7  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1401199fe  nop     dword ptr [rax+rax+00h]
0x140119a03  call    cs:__imp_KeLeaveCriticalRegion
0x140119a0a  nop     dword ptr [rax+rax+00h]
0x140119a0f  mov     [r14], rdi
0x140119a12  jmp     loc_14011996A
0x140119a17  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, 0
0x140119a1e  mov     ebx, 0C000009Ah
0x140119a23  jge     loc_14011996C
0x140119a29  lea     r9, aFlsServiceChai_0; "FLS service chain (FLNG)"
0x140119a30  lea     rdx, TCPIP_MEMORY_FAILURES
0x140119a37  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140119a3e  call    McTemplateK0z_EtwWriteTransfer
0x140119a43  jmp     loc_14011996C
0x140119a48  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, 0
0x140119a4f  mov     ebx, 0C000009Ah
0x140119a54  jge     loc_1401D75F8
0x140119a5a  lea     r9, aFlsServiceChai; "FLS service chain rundown object (FLNG)"
0x140119a61  lea     rdx, TCPIP_MEMORY_FAILURES
0x140119a68  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140119a6f  call    McTemplateK0z_EtwWriteTransfer
0x140119a74  nop
0x140119a75  jmp     loc_1401D75F8
0x1401d75f8  mov     rdx, rdi
0x1401d75fb  mov     rcx, rsi
0x1401d75fe  call    FlpCleanupFlsServiceChain
0x1401d7603  mov     rcx, [rdi+10h]; RunRefCacheAware
0x1401d7607  test    rcx, rcx
0x1401d760a  jz      short loc_1401D7618
0x1401d760c  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1401d7613  nop     dword ptr [rax+rax+00h]
0x1401d7618  mov     edx, 70534C46h; Tag
0x1401d761d  mov     rcx, rdi; P
0x1401d7620  call    cs:__imp_ExFreePoolWithTag
0x1401d7627  nop     dword ptr [rax+rax+00h]
0x1401d762c  nop
0x1401d762d  jmp     loc_14011996C
```
