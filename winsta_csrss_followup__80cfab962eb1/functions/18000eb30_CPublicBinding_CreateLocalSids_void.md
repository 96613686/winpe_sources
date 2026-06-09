# CPublicBinding::CreateLocalSids(void)

- ea: `0x18000eb30`
- end: `0x18000ebc6`
- name: `?CreateLocalSids@CPublicBinding@@SAJXZ`
- size: `150`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x180006480`
- `0x1800075a0`
- `0x180007690`
- `0x180020c90`

## callees

- `0x180005b40`
- `0x18000eb30`
- `0x18000ebcc`
- `0x18000ec8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eb85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eb85`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000eb54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000eb54`

## string_xrefs

- `0x18000eba9`: `CUtils::CreateNetworkServiceSid failed: 0x%x in %s`
- `0x18000ebb0`: `CPublicBinding::CreateLocalSids`
- `0x18000eba0`: `CUtils::CreateSystemSid failed: 0x%x in %s`

## pseudocode

```c
__int64 CPublicBinding::CreateLocalSids(void)
{
  unsigned int v1; // ebx
  void **v2; // rcx
  int NetworkServiceSid; // eax
  int SystemSid; // eax

  if ( !CPublicBinding::bCritSecInitialized )
    return 2147500037LL;
  v1 = 0;
  EnterCriticalSection(&CPublicBinding::m_CritSec);
  if ( CPublicBinding::pSystemSid || (SystemSid = CUtils::CreateSystemSid(v2), v1 = SystemSid, SystemSid >= 0) )
  {
    if ( !CPublicBinding::pNetsrvSid )
    {
      NetworkServiceSid = CUtils::CreateNetworkServiceSid(v2);
      v1 = NetworkServiceSid;
      if ( NetworkServiceSid < 0 )
        _DbgPrintMessage(
          8,
          "CUtils::CreateNetworkServiceSid failed: 0x%x in %s",
          (unsigned int)NetworkServiceSid,
          "CPublicBinding::CreateLocalSids");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "CUtils::CreateSystemSid failed: 0x%x in %s",
      (unsigned int)SystemSid,
      "CPublicBinding::CreateLocalSids");
  }
  LeaveCriticalSection(&CPublicBinding::m_CritSec);
  return v1;
}

```

## disassembly

```asm
0x18000eb30  push    rbx
0x18000eb32  sub     rsp, 20h
0x18000eb36  cmp     cs:?bCritSecInitialized@CPublicBinding@@1HA, 0; int CPublicBinding::bCritSecInitialized
0x18000eb3d  jnz     short loc_18000EB4B
0x18000eb3f  mov     eax, 80004005h
0x18000eb44  add     rsp, 20h
0x18000eb48  pop     rbx
0x18000eb49  retn
0x18000eb4b  lea     rcx, ?m_CritSec@CPublicBinding@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000eb52  xor     ebx, ebx
0x18000eb54  call    cs:__imp_EnterCriticalSection
0x18000eb5b  nop     dword ptr [rax+rax+00h]
0x18000eb60  cmp     cs:?pSystemSid@CPublicBinding@@1PEAXEA, rbx; void * CPublicBinding::pSystemSid
0x18000eb67  jz      short loc_18000EB95
0x18000eb69  cmp     cs:?pNetsrvSid@CPublicBinding@@1PEAXEA, 0; void * CPublicBinding::pNetsrvSid
0x18000eb71  jnz     short loc_18000EB7E
0x18000eb73  call    ?CreateNetworkServiceSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateNetworkServiceSid(void * *)
0x18000eb78  mov     ebx, eax
0x18000eb7a  test    eax, eax
0x18000eb7c  js      short loc_18000EBA9
0x18000eb7e  lea     rcx, ?m_CritSec@CPublicBinding@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000eb85  call    cs:__imp_LeaveCriticalSection
0x18000eb8c  nop     dword ptr [rax+rax+00h]
0x18000eb91  mov     eax, ebx
0x18000eb93  jmp     short loc_18000EB44
0x18000eb95  call    ?CreateSystemSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateSystemSid(void * *)
0x18000eb9a  mov     ebx, eax
0x18000eb9c  test    eax, eax
0x18000eb9e  jns     short loc_18000EB69
0x18000eba0  lea     rdx, aCutilsCreatesy; "CUtils::CreateSystemSid failed: 0x%x in"...
0x18000eba7  jmp     short loc_18000EBB0
0x18000eba9  lea     rdx, aCutilsCreatene; "CUtils::CreateNetworkServiceSid failed:"...
0x18000ebb0  lea     r9, aCpublicbinding; "CPublicBinding::CreateLocalSids"
0x18000ebb7  mov     r8d, eax
0x18000ebba  mov     ecx, 8; int
0x18000ebbf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ebc4  jmp     short loc_18000EB7E
```
