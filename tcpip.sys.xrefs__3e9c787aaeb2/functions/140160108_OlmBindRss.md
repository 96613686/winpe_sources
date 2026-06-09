# OlmBindRss

- ea: `0x140160108`
- end: `0x14016026a`
- name: `OlmBindRss`
- size: `354`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140160920`

## callees

- `0x140160108`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14016023d`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140160255`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14016023d`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140160255`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140160130`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14016014a`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140160130`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14016014a`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14016016e`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140160181`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14016016e`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140160181`
- `NETIO!NmrRegisterClient` at `0x14016019d`
- `NETIO!NmrRegisterClient` at `0x1401601bf`
- `NETIO!NmrRegisterClient` at `0x14016019d`
- `NETIO!NmrRegisterClient` at `0x1401601bf`
- `NETIO!NmrDeregisterClient` at `0x1401601e7`
- `NETIO!NmrDeregisterClient` at `0x140160212`
- `NETIO!NmrDeregisterClient` at `0x1401601e7`
- `NETIO!NmrDeregisterClient` at `0x140160212`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x1401601fa`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x140160225`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x1401601fa`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x140160225`

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
0x140160108  push    rbx
0x14016010a  sub     rsp, 20h
0x14016010e  mov     ebx, 200h
0x140160113  mov     cs:OlmRssControlBindingHandle, 0
0x14016011e  mov     ecx, ebx; PoolType
0x140160120  mov     cs:OlmRssHashBindingHandle, 0
0x14016012b  mov     edx, 676D6C4Fh; PoolTag
0x140160130  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x140160137  nop     dword ptr [rax+rax+00h]
0x14016013c  mov     edx, 676D6C4Fh; PoolTag
0x140160141  mov     ecx, ebx; PoolType
0x140160143  mov     cs:OlmRssControlRundown, rax
0x14016014a  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x140160151  nop     dword ptr [rax+rax+00h]
0x140160156  mov     rcx, cs:OlmRssControlRundown; RunRef
0x14016015d  mov     cs:OlmRssHashRundown, rax
0x140160164  test    rcx, rcx
0x140160167  jz      short loc_1401601D6
0x140160169  test    rax, rax
0x14016016c  jz      short loc_1401601D6
0x14016016e  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x140160175  nop     dword ptr [rax+rax+00h]
0x14016017a  mov     rcx, cs:OlmRssHashRundown; RunRef
0x140160181  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x140160188  nop     dword ptr [rax+rax+00h]
0x14016018d  lea     r8, OlmRssControlBindingHandle; NmrClientHandle
0x140160194  xor     edx, edx; ClientContext
0x140160196  lea     rcx, OlmRssControlClientNotify; ClientCharacteristics
0x14016019d  call    cs:__imp_NmrRegisterClient
0x1401601a4  nop     dword ptr [rax+rax+00h]
0x1401601a9  mov     ebx, eax
0x1401601ab  test    eax, eax
0x1401601ad  js      short loc_1401601DB
0x1401601af  lea     r8, OlmRssHashBindingHandle; NmrClientHandle
0x1401601b6  xor     edx, edx; ClientContext
0x1401601b8  lea     rcx, OlmRssHashClientNotify; ClientCharacteristics
0x1401601bf  call    cs:__imp_NmrRegisterClient
0x1401601c6  nop     dword ptr [rax+rax+00h]
0x1401601cb  mov     ebx, eax
0x1401601cd  test    eax, eax
0x1401601cf  js      short loc_1401601DB
0x1401601d1  jmp     loc_140160263
0x1401601d6  mov     ebx, 0C0000017h
0x1401601db  mov     rcx, cs:OlmRssControlBindingHandle; NmrClientHandle
0x1401601e2  test    rcx, rcx
0x1401601e5  jz      short loc_140160206
0x1401601e7  call    cs:__imp_NmrDeregisterClient
0x1401601ee  nop     dword ptr [rax+rax+00h]
0x1401601f3  mov     rcx, cs:OlmRssControlBindingHandle; NmrClientHandle
0x1401601fa  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x140160201  nop     dword ptr [rax+rax+00h]
0x140160206  mov     rcx, cs:OlmRssHashBindingHandle; NmrClientHandle
0x14016020d  test    rcx, rcx
0x140160210  jz      short loc_140160231
0x140160212  call    cs:__imp_NmrDeregisterClient
0x140160219  nop     dword ptr [rax+rax+00h]
0x14016021e  mov     rcx, cs:OlmRssHashBindingHandle; NmrClientHandle
0x140160225  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x14016022c  nop     dword ptr [rax+rax+00h]
0x140160231  mov     rcx, cs:OlmRssControlRundown; RunRefCacheAware
0x140160238  test    rcx, rcx
0x14016023b  jz      short loc_140160249
0x14016023d  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140160244  nop     dword ptr [rax+rax+00h]
0x140160249  mov     rcx, cs:OlmRssHashRundown; RunRefCacheAware
0x140160250  test    rcx, rcx
0x140160253  jz      short loc_140160261
0x140160255  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14016025c  nop     dword ptr [rax+rax+00h]
0x140160261  mov     eax, ebx
0x140160263  add     rsp, 20h
0x140160267  pop     rbx
0x140160268  retn
```
