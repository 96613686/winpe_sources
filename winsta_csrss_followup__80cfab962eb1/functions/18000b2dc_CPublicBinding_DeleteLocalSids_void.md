# CPublicBinding::DeleteLocalSids(void)

- ea: `0x18000b2dc`
- end: `0x18000b345`
- name: `?DeleteLocalSids@CPublicBinding@@SAXXZ`
- size: `105`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18000b254`

## callees

- `0x18000b2dc`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x18000b308`
- `ntdll!RtlFreeSid` at `0x18000b308`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b320`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b320`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b333`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b333`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b2f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b2f0`

## pseudocode

```c
void CPublicBinding::DeleteLocalSids(void)
{
  if ( CPublicBinding::bCritSecInitialized )
  {
    EnterCriticalSection(&CPublicBinding::m_CritSec);
    if ( CPublicBinding::pSystemSid )
      RtlFreeSid(CPublicBinding::pSystemSid);
    if ( CPublicBinding::pNetsrvSid )
      LocalFree(CPublicBinding::pNetsrvSid);
    LeaveCriticalSection(&CPublicBinding::m_CritSec);
  }
}

```

## disassembly

```asm
0x18000b2dc  sub     rsp, 28h
0x18000b2e0  cmp     cs:?bCritSecInitialized@CPublicBinding@@1HA, 0; int CPublicBinding::bCritSecInitialized
0x18000b2e7  jz      short loc_18000B33F
0x18000b2e9  lea     rcx, ?m_CritSec@CPublicBinding@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b2f0  call    cs:__imp_EnterCriticalSection
0x18000b2f7  nop     dword ptr [rax+rax+00h]
0x18000b2fc  mov     rcx, cs:?pSystemSid@CPublicBinding@@1PEAXEA; Sid
0x18000b303  test    rcx, rcx
0x18000b306  jz      short loc_18000B314
0x18000b308  call    cs:__imp_RtlFreeSid
0x18000b30f  nop     dword ptr [rax+rax+00h]
0x18000b314  mov     rcx, cs:?pNetsrvSid@CPublicBinding@@1PEAXEA; hMem
0x18000b31b  test    rcx, rcx
0x18000b31e  jz      short loc_18000B32C
0x18000b320  call    cs:__imp_LocalFree
0x18000b327  nop     dword ptr [rax+rax+00h]
0x18000b32c  lea     rcx, ?m_CritSec@CPublicBinding@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b333  call    cs:__imp_LeaveCriticalSection
0x18000b33a  nop     dword ptr [rax+rax+00h]
0x18000b33f  add     rsp, 28h
0x18000b343  retn
```
