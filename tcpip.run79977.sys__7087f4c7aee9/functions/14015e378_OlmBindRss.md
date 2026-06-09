# OlmBindRss

- ea: `0x14015e378`
- end: `0x14015e4da`
- name: `OlmBindRss`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14015eb90`

## callees

- `0x14015e378`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14015e4ad`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14015e4c5`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14015e4ad`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14015e4c5`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14015e3a0`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14015e3ba`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14015e3a0`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14015e3ba`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14015e3de`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14015e3f1`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14015e3de`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14015e3f1`
- `NETIO!NmrRegisterClient` at `0x14015e40d`
- `NETIO!NmrRegisterClient` at `0x14015e42f`
- `NETIO!NmrRegisterClient` at `0x14015e40d`
- `NETIO!NmrRegisterClient` at `0x14015e42f`
- `NETIO!NmrDeregisterClient` at `0x14015e457`
- `NETIO!NmrDeregisterClient` at `0x14015e482`
- `NETIO!NmrDeregisterClient` at `0x14015e457`
- `NETIO!NmrDeregisterClient` at `0x14015e482`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14015e46a`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14015e495`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14015e46a`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14015e495`

## pseudocode

```c
NTSTATUS OlmBindRss()
{
  struct _EX_RUNDOWN_REF_CACHE_AWARE *CacheAwareRundownProtection; // rax
  NTSTATUS v1; // ebx
  NTSTATUS result; // eax

  OlmRssControlBindingHandle = 0;
  OlmRssHashBindingHandle = 0;
  OlmRssControlRundown = ExAllocateCacheAwareRundownProtection((POOL_TYPE)512, 0x676D6C4Fu);
  CacheAwareRundownProtection = ExAllocateCacheAwareRundownProtection((POOL_TYPE)512, 0x676D6C4Fu);
  OlmRssHashRundown = CacheAwareRundownProtection;
  if ( OlmRssControlRundown && CacheAwareRundownProtection )
  {
    ExWaitForRundownProtectionReleaseCacheAware(OlmRssControlRundown);
    ExWaitForRundownProtectionReleaseCacheAware(OlmRssHashRundown);
    v1 = NmrRegisterClient(&OlmRssControlClientNotify, 0, &OlmRssControlBindingHandle);
    if ( v1 >= 0 )
    {
      result = NmrRegisterClient(&OlmRssHashClientNotify, 0, &OlmRssHashBindingHandle);
      v1 = result;
      if ( result >= 0 )
        return result;
    }
  }
  else
  {
    v1 = -1073741801;
  }
  if ( OlmRssControlBindingHandle )
  {
    NmrDeregisterClient(OlmRssControlBindingHandle);
    NmrWaitForClientDeregisterComplete(OlmRssControlBindingHandle);
  }
  if ( OlmRssHashBindingHandle )
  {
    NmrDeregisterClient(OlmRssHashBindingHandle);
    NmrWaitForClientDeregisterComplete(OlmRssHashBindingHandle);
  }
  if ( OlmRssControlRundown )
    ExFreeCacheAwareRundownProtection(OlmRssControlRundown);
  if ( OlmRssHashRundown )
    ExFreeCacheAwareRundownProtection(OlmRssHashRundown);
  return v1;
}

```

## disassembly

```asm
0x14015e378  push    rbx
0x14015e37a  sub     rsp, 20h
0x14015e37e  mov     ebx, 200h
0x14015e383  mov     cs:OlmRssControlBindingHandle, 0
0x14015e38e  mov     ecx, ebx; PoolType
0x14015e390  mov     cs:OlmRssHashBindingHandle, 0
0x14015e39b  mov     edx, 676D6C4Fh; PoolTag
0x14015e3a0  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x14015e3a7  nop     dword ptr [rax+rax+00h]
0x14015e3ac  mov     edx, 676D6C4Fh; PoolTag
0x14015e3b1  mov     ecx, ebx; PoolType
0x14015e3b3  mov     cs:OlmRssControlRundown, rax
0x14015e3ba  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x14015e3c1  nop     dword ptr [rax+rax+00h]
0x14015e3c6  mov     rcx, cs:OlmRssControlRundown; RunRef
0x14015e3cd  mov     cs:OlmRssHashRundown, rax
0x14015e3d4  test    rcx, rcx
0x14015e3d7  jz      short loc_14015E446
0x14015e3d9  test    rax, rax
0x14015e3dc  jz      short loc_14015E446
0x14015e3de  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x14015e3e5  nop     dword ptr [rax+rax+00h]
0x14015e3ea  mov     rcx, cs:OlmRssHashRundown; RunRef
0x14015e3f1  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x14015e3f8  nop     dword ptr [rax+rax+00h]
0x14015e3fd  lea     r8, OlmRssControlBindingHandle; NmrClientHandle
0x14015e404  xor     edx, edx; ClientContext
0x14015e406  lea     rcx, OlmRssControlClientNotify; ClientCharacteristics
0x14015e40d  call    cs:__imp_NmrRegisterClient
0x14015e414  nop     dword ptr [rax+rax+00h]
0x14015e419  mov     ebx, eax
0x14015e41b  test    eax, eax
0x14015e41d  js      short loc_14015E44B
0x14015e41f  lea     r8, OlmRssHashBindingHandle; NmrClientHandle
0x14015e426  xor     edx, edx; ClientContext
0x14015e428  lea     rcx, OlmRssHashClientNotify; ClientCharacteristics
0x14015e42f  call    cs:__imp_NmrRegisterClient
0x14015e436  nop     dword ptr [rax+rax+00h]
0x14015e43b  mov     ebx, eax
0x14015e43d  test    eax, eax
0x14015e43f  js      short loc_14015E44B
0x14015e441  jmp     loc_14015E4D3
0x14015e446  mov     ebx, 0C0000017h
0x14015e44b  mov     rcx, cs:OlmRssControlBindingHandle; NmrClientHandle
0x14015e452  test    rcx, rcx
0x14015e455  jz      short loc_14015E476
0x14015e457  call    cs:__imp_NmrDeregisterClient
0x14015e45e  nop     dword ptr [rax+rax+00h]
0x14015e463  mov     rcx, cs:OlmRssControlBindingHandle; NmrClientHandle
0x14015e46a  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x14015e471  nop     dword ptr [rax+rax+00h]
0x14015e476  mov     rcx, cs:OlmRssHashBindingHandle; NmrClientHandle
0x14015e47d  test    rcx, rcx
0x14015e480  jz      short loc_14015E4A1
0x14015e482  call    cs:__imp_NmrDeregisterClient
0x14015e489  nop     dword ptr [rax+rax+00h]
0x14015e48e  mov     rcx, cs:OlmRssHashBindingHandle; NmrClientHandle
0x14015e495  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x14015e49c  nop     dword ptr [rax+rax+00h]
0x14015e4a1  mov     rcx, cs:OlmRssControlRundown; RunRefCacheAware
0x14015e4a8  test    rcx, rcx
0x14015e4ab  jz      short loc_14015E4B9
0x14015e4ad  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14015e4b4  nop     dword ptr [rax+rax+00h]
0x14015e4b9  mov     rcx, cs:OlmRssHashRundown; RunRefCacheAware
0x14015e4c0  test    rcx, rcx
0x14015e4c3  jz      short loc_14015E4D1
0x14015e4c5  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14015e4cc  nop     dword ptr [rax+rax+00h]
0x14015e4d1  mov     eax, ebx
0x14015e4d3  add     rsp, 20h
0x14015e4d7  pop     rbx
0x14015e4d8  retn
```
