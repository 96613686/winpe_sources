# OlmBindRss

- ea: `0x14015e238`
- end: `0x14015e39a`
- name: `OlmBindRss`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14015ea50`

## callees

- `0x14015e238`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14015e36d`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14015e385`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14015e36d`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14015e385`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14015e260`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14015e27a`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14015e260`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14015e27a`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14015e29e`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14015e2b1`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14015e29e`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14015e2b1`
- `NETIO!NmrRegisterClient` at `0x14015e2cd`
- `NETIO!NmrRegisterClient` at `0x14015e2ef`
- `NETIO!NmrRegisterClient` at `0x14015e2cd`
- `NETIO!NmrRegisterClient` at `0x14015e2ef`
- `NETIO!NmrDeregisterClient` at `0x14015e317`
- `NETIO!NmrDeregisterClient` at `0x14015e342`
- `NETIO!NmrDeregisterClient` at `0x14015e317`
- `NETIO!NmrDeregisterClient` at `0x14015e342`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14015e32a`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14015e355`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14015e32a`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14015e355`

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
0x14015e238  push    rbx
0x14015e23a  sub     rsp, 20h
0x14015e23e  mov     ebx, 200h
0x14015e243  mov     cs:OlmRssControlBindingHandle, 0
0x14015e24e  mov     ecx, ebx; PoolType
0x14015e250  mov     cs:OlmRssHashBindingHandle, 0
0x14015e25b  mov     edx, 676D6C4Fh; PoolTag
0x14015e260  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x14015e267  nop     dword ptr [rax+rax+00h]
0x14015e26c  mov     edx, 676D6C4Fh; PoolTag
0x14015e271  mov     ecx, ebx; PoolType
0x14015e273  mov     cs:OlmRssControlRundown, rax
0x14015e27a  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x14015e281  nop     dword ptr [rax+rax+00h]
0x14015e286  mov     rcx, cs:OlmRssControlRundown; RunRef
0x14015e28d  mov     cs:OlmRssHashRundown, rax
0x14015e294  test    rcx, rcx
0x14015e297  jz      short loc_14015E306
0x14015e299  test    rax, rax
0x14015e29c  jz      short loc_14015E306
0x14015e29e  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x14015e2a5  nop     dword ptr [rax+rax+00h]
0x14015e2aa  mov     rcx, cs:OlmRssHashRundown; RunRef
0x14015e2b1  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x14015e2b8  nop     dword ptr [rax+rax+00h]
0x14015e2bd  lea     r8, OlmRssControlBindingHandle; NmrClientHandle
0x14015e2c4  xor     edx, edx; ClientContext
0x14015e2c6  lea     rcx, OlmRssControlClientNotify; ClientCharacteristics
0x14015e2cd  call    cs:__imp_NmrRegisterClient
0x14015e2d4  nop     dword ptr [rax+rax+00h]
0x14015e2d9  mov     ebx, eax
0x14015e2db  test    eax, eax
0x14015e2dd  js      short loc_14015E30B
0x14015e2df  lea     r8, OlmRssHashBindingHandle; NmrClientHandle
0x14015e2e6  xor     edx, edx; ClientContext
0x14015e2e8  lea     rcx, OlmRssHashClientNotify; ClientCharacteristics
0x14015e2ef  call    cs:__imp_NmrRegisterClient
0x14015e2f6  nop     dword ptr [rax+rax+00h]
0x14015e2fb  mov     ebx, eax
0x14015e2fd  test    eax, eax
0x14015e2ff  js      short loc_14015E30B
0x14015e301  jmp     loc_14015E393
0x14015e306  mov     ebx, 0C0000017h
0x14015e30b  mov     rcx, cs:OlmRssControlBindingHandle; NmrClientHandle
0x14015e312  test    rcx, rcx
0x14015e315  jz      short loc_14015E336
0x14015e317  call    cs:__imp_NmrDeregisterClient
0x14015e31e  nop     dword ptr [rax+rax+00h]
0x14015e323  mov     rcx, cs:OlmRssControlBindingHandle; NmrClientHandle
0x14015e32a  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x14015e331  nop     dword ptr [rax+rax+00h]
0x14015e336  mov     rcx, cs:OlmRssHashBindingHandle; NmrClientHandle
0x14015e33d  test    rcx, rcx
0x14015e340  jz      short loc_14015E361
0x14015e342  call    cs:__imp_NmrDeregisterClient
0x14015e349  nop     dword ptr [rax+rax+00h]
0x14015e34e  mov     rcx, cs:OlmRssHashBindingHandle; NmrClientHandle
0x14015e355  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x14015e35c  nop     dword ptr [rax+rax+00h]
0x14015e361  mov     rcx, cs:OlmRssControlRundown; RunRefCacheAware
0x14015e368  test    rcx, rcx
0x14015e36b  jz      short loc_14015E379
0x14015e36d  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14015e374  nop     dword ptr [rax+rax+00h]
0x14015e379  mov     rcx, cs:OlmRssHashRundown; RunRefCacheAware
0x14015e380  test    rcx, rcx
0x14015e383  jz      short loc_14015E391
0x14015e385  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14015e38c  nop     dword ptr [rax+rax+00h]
0x14015e391  mov     eax, ebx
0x14015e393  add     rsp, 20h
0x14015e397  pop     rbx
0x14015e398  retn
```
