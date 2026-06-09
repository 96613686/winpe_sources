# FlpInitializeFlsServiceChain

- ea: `0x1400c73ac`
- end: `0x1400c74de`
- name: `FlpInitializeFlsServiceChain`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400c724c`

## callees

- `0x140053e98`
- `0x1400c73ac`
- `0x1400c8c78`
- `0x1400c8e30`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401cbc54`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401cbc54`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1400c7410`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1400c7410`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c7467`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c7467`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c7429`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c7429`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400c745b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400c745b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c743e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c743e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401cbc68`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401cbc68`
- `ntoskrnl!ExAllocatePool2` at `0x1400c73eb`
- `ntoskrnl!ExAllocatePool2` at `0x1400c73eb`

## string_xrefs

- `0x1400c748d`: `FLS service chain (FLNG)`
- `0x1400c74be`: `FLS service chain rundown object (FLNG)`

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
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
0x1400c73ac  push    rbx
0x1400c73ae  push    rsi
0x1400c73af  push    rdi
0x1400c73b0  push    r14
0x1400c73b2  sub     rsp, 28h
0x1400c73b6  mov     rax, [rcx+48h]
0x1400c73ba  mov     r14, rdx
0x1400c73bd  mov     rsi, rcx
0x1400c73c0  mov     rbx, [rax+20h]
0x1400c73c4  cmp     qword ptr [rbx+2E0h], 0
0x1400c73cc  jnz     short loc_1400C73DD
0x1400c73ce  xor     ebx, ebx
0x1400c73d0  mov     eax, ebx
0x1400c73d2  add     rsp, 28h
0x1400c73d6  pop     r14
0x1400c73d8  pop     rdi
0x1400c73d9  pop     rsi
0x1400c73da  pop     rbx
0x1400c73db  retn
0x1400c73dd  mov     edx, 20h ; ' '
0x1400c73e2  mov     r8d, 70534C46h
0x1400c73e8  lea     ecx, [rdx+20h]
0x1400c73eb  call    cs:__imp_ExAllocatePool2
0x1400c73f2  nop     dword ptr [rax+rax+00h]
0x1400c73f7  mov     rdi, rax
0x1400c73fa  test    rax, rax
0x1400c73fd  jz      short loc_1400C747B
0x1400c73ff  mov     edx, 70534C46h; PoolTag
0x1400c7404  mov     [rax+8], rax
0x1400c7408  mov     ecx, 200h; PoolType
0x1400c740d  mov     [rax], rax
0x1400c7410  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x1400c7417  nop     dword ptr [rax+rax+00h]
0x1400c741c  mov     [rdi+10h], rax
0x1400c7420  test    rax, rax
0x1400c7423  jz      loc_1400C74AC
0x1400c7429  call    cs:__imp_KeEnterCriticalRegion
0x1400c7430  nop     dword ptr [rax+rax+00h]
0x1400c7435  xor     edx, edx
0x1400c7437  lea     rcx, [rbx+2F0h]
0x1400c743e  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400c7445  nop     dword ptr [rax+rax+00h]
0x1400c744a  mov     rdx, rdi
0x1400c744d  call    FlpDisableFlsServiceChain
0x1400c7452  xor     edx, edx
0x1400c7454  lea     rcx, [rbx+2F0h]
0x1400c745b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400c7462  nop     dword ptr [rax+rax+00h]
0x1400c7467  call    cs:__imp_KeLeaveCriticalRegion
0x1400c746e  nop     dword ptr [rax+rax+00h]
0x1400c7473  mov     [r14], rdi
0x1400c7476  jmp     loc_1400C73CE
0x1400c747b  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, 0
0x1400c7482  mov     ebx, 0C000009Ah
0x1400c7487  jge     loc_1400C73D0
0x1400c748d  lea     r9, aFlsServiceChai_0; "FLS service chain (FLNG)"
0x1400c7494  lea     rdx, TCPIP_MEMORY_FAILURES
0x1400c749b  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400c74a2  call    McTemplateK0z_EtwWriteTransfer
0x1400c74a7  jmp     loc_1400C73D0
0x1400c74ac  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, 0
0x1400c74b3  mov     ebx, 0C000009Ah
0x1400c74b8  jge     loc_1401CBC40
0x1400c74be  lea     r9, aFlsServiceChai; "FLS service chain rundown object (FLNG)"
0x1400c74c5  lea     rdx, TCPIP_MEMORY_FAILURES
0x1400c74cc  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400c74d3  call    McTemplateK0z_EtwWriteTransfer
0x1400c74d8  nop
0x1400c74d9  jmp     loc_1401CBC40
0x1401cbc40  mov     rdx, rdi
0x1401cbc43  mov     rcx, rsi
0x1401cbc46  call    FlpCleanupFlsServiceChain
0x1401cbc4b  mov     rcx, [rdi+10h]; RunRefCacheAware
0x1401cbc4f  test    rcx, rcx
0x1401cbc52  jz      short loc_1401CBC60
0x1401cbc54  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1401cbc5b  nop     dword ptr [rax+rax+00h]
0x1401cbc60  mov     edx, 70534C46h; Tag
0x1401cbc65  mov     rcx, rdi; P
0x1401cbc68  call    cs:__imp_ExFreePoolWithTag
0x1401cbc6f  nop     dword ptr [rax+rax+00h]
0x1401cbc74  nop
0x1401cbc75  jmp     loc_1400C73D0
```
