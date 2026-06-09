# FlpInitializeFlsServiceChain

- ea: `0x1400c718c`
- end: `0x1400c72be`
- name: `FlpInitializeFlsServiceChain`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400c702c`

## callees

- `0x140054138`
- `0x1400c718c`
- `0x1400c8a58`
- `0x1400c8c10`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401cbd78`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401cbd78`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1400c71f0`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1400c71f0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c7247`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c7247`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c7209`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c7209`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400c723b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400c723b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c721e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c721e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401cbd8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401cbd8c`
- `ntoskrnl!ExAllocatePool2` at `0x1400c71cb`
- `ntoskrnl!ExAllocatePool2` at `0x1400c71cb`

## string_xrefs

- `0x1400c726d`: `FLS service chain (FLNG)`
- `0x1400c729e`: `FLS service chain rundown object (FLNG)`

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
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        &TCPIP_MEMORY_FAILURES,
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
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        &TCPIP_MEMORY_FAILURES,
        v8,
        L"FLS service chain (FLNG)");
  }
  return v5;
}

```

## disassembly

```asm
0x1400c718c  push    rbx
0x1400c718e  push    rsi
0x1400c718f  push    rdi
0x1400c7190  push    r14
0x1400c7192  sub     rsp, 28h
0x1400c7196  mov     rax, [rcx+48h]
0x1400c719a  mov     r14, rdx
0x1400c719d  mov     rsi, rcx
0x1400c71a0  mov     rbx, [rax+20h]
0x1400c71a4  cmp     qword ptr [rbx+2E0h], 0
0x1400c71ac  jnz     short loc_1400C71BD
0x1400c71ae  xor     ebx, ebx
0x1400c71b0  mov     eax, ebx
0x1400c71b2  add     rsp, 28h
0x1400c71b6  pop     r14
0x1400c71b8  pop     rdi
0x1400c71b9  pop     rsi
0x1400c71ba  pop     rbx
0x1400c71bb  retn
0x1400c71bd  mov     edx, 20h ; ' '
0x1400c71c2  mov     r8d, 70534C46h
0x1400c71c8  lea     ecx, [rdx+20h]
0x1400c71cb  call    cs:__imp_ExAllocatePool2
0x1400c71d2  nop     dword ptr [rax+rax+00h]
0x1400c71d7  mov     rdi, rax
0x1400c71da  test    rax, rax
0x1400c71dd  jz      short loc_1400C725B
0x1400c71df  mov     edx, 70534C46h; PoolTag
0x1400c71e4  mov     [rax+8], rax
0x1400c71e8  mov     ecx, 200h; PoolType
0x1400c71ed  mov     [rax], rax
0x1400c71f0  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x1400c71f7  nop     dword ptr [rax+rax+00h]
0x1400c71fc  mov     [rdi+10h], rax
0x1400c7200  test    rax, rax
0x1400c7203  jz      loc_1400C728C
0x1400c7209  call    cs:__imp_KeEnterCriticalRegion
0x1400c7210  nop     dword ptr [rax+rax+00h]
0x1400c7215  xor     edx, edx
0x1400c7217  lea     rcx, [rbx+2F0h]
0x1400c721e  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400c7225  nop     dword ptr [rax+rax+00h]
0x1400c722a  mov     rdx, rdi
0x1400c722d  call    FlpDisableFlsServiceChain
0x1400c7232  xor     edx, edx
0x1400c7234  lea     rcx, [rbx+2F0h]
0x1400c723b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400c7242  nop     dword ptr [rax+rax+00h]
0x1400c7247  call    cs:__imp_KeLeaveCriticalRegion
0x1400c724e  nop     dword ptr [rax+rax+00h]
0x1400c7253  mov     [r14], rdi
0x1400c7256  jmp     loc_1400C71AE
0x1400c725b  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, 0
0x1400c7262  mov     ebx, 0C000009Ah
0x1400c7267  jge     loc_1400C71B0
0x1400c726d  lea     r9, aFlsServiceChai_0; "FLS service chain (FLNG)"
0x1400c7274  lea     rdx, TCPIP_MEMORY_FAILURES
0x1400c727b  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400c7282  call    McTemplateK0z_EtwWriteTransfer
0x1400c7287  jmp     loc_1400C71B0
0x1400c728c  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, 0
0x1400c7293  mov     ebx, 0C000009Ah
0x1400c7298  jge     loc_1401CBD64
0x1400c729e  lea     r9, aFlsServiceChai; "FLS service chain rundown object (FLNG)"
0x1400c72a5  lea     rdx, TCPIP_MEMORY_FAILURES
0x1400c72ac  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400c72b3  call    McTemplateK0z_EtwWriteTransfer
0x1400c72b8  nop
0x1400c72b9  jmp     loc_1401CBD64
0x1401cbd64  mov     rdx, rdi
0x1401cbd67  mov     rcx, rsi
0x1401cbd6a  call    FlpCleanupFlsServiceChain
0x1401cbd6f  mov     rcx, [rdi+10h]; RunRefCacheAware
0x1401cbd73  test    rcx, rcx
0x1401cbd76  jz      short loc_1401CBD84
0x1401cbd78  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1401cbd7f  nop     dword ptr [rax+rax+00h]
0x1401cbd84  mov     edx, 70534C46h; Tag
0x1401cbd89  mov     rcx, rdi; P
0x1401cbd8c  call    cs:__imp_ExFreePoolWithTag
0x1401cbd93  nop     dword ptr [rax+rax+00h]
0x1401cbd98  nop
0x1401cbd99  jmp     loc_1400C71B0
```
