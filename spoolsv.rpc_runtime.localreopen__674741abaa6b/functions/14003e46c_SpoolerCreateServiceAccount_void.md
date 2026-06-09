# SpoolerCreateServiceAccount(void)

- ea: `0x14003e46c`
- end: `0x14003e5db`
- name: `?SpoolerCreateServiceAccount@@YAJXZ`
- size: `367`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14003e980`
- `0x14004c580`

## callees

- `0x14002d0a0`
- `0x14003e3b4`
- `0x14003e46c`
- `0x14003ec9c`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x14003e5ab`
- `ntdll!RtlFreeSid` at `0x14003e5ab`
- `ntdll!RtlInitializeSidEx` at `0x14003e55a`
- `ntdll!RtlInitializeSidEx` at `0x14003e55a`
- `ntdll!RtlInitUnicodeString` at `0x14003e4b9`
- `ntdll!RtlInitUnicodeString` at `0x14003e4d0`
- `ntdll!RtlInitUnicodeString` at `0x14003e4b9`
- `ntdll!RtlInitUnicodeString` at `0x14003e4d0`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14003e50c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14003e50c`

## string_xrefs

- `0x14003e49d`: `RESTRICTED SERVICES`
- `0x14003e4c5`: `PrintSpoolerService`

## pseudocode

```c
NTSTATUS SpoolerCreateServiceAccount(void)
{
  NTSTATUS result; // eax
  int updated; // ebx
  void *v2; // rcx
  PSID Sid; // [rsp+60h] [rbp+17h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+68h] [rbp+1Fh] BYREF
  struct _UNICODE_STRING v5; // [rsp+78h] [rbp+2Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+88h] [rbp+3Fh] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  DestinationString = 0;
  Sid = 0;
  v5 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  RtlInitUnicodeString(&DestinationString, L"RESTRICTED SERVICES");
  RtlInitUnicodeString(&v5, L"PrintSpoolerService");
  result = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x63u, 0, 0, 0, 0, 0, 0, 0, &Sid);
  if ( result >= 0 )
  {
    updated = RtlInitializeSidEx(
                &g_abSpoolerServiceSidBuffer,
                &IdentifierAuthority,
                6,
                99,
                216390572,
                1995538116,
                -437055781,
                -1890008784,
                -1671080067);
    if ( updated >= 0 )
    {
      updated = AddSidMappingToLsa(&DestinationString, 0, Sid);
      if ( updated >= 0 )
      {
        updated = AddSidMappingToLsa(&DestinationString, &v5, &g_abSpoolerServiceSidBuffer);
        if ( updated >= 0 )
          updated = UpdateLsaSecurityPolicy(v2);
      }
    }
    if ( Sid )
      RtlFreeSid(Sid);
    return updated;
  }
  return result;
}

```

## disassembly

```asm
0x14003e46c  mov     [rsp-8+arg_0], rbx
0x14003e471  mov     [rsp-8+arg_8], rdi
0x14003e476  push    rbp
0x14003e477  lea     rbp, [rsp-57h]
0x14003e47c  sub     rsp, 0A0h
0x14003e483  mov     rax, cs:__security_cookie
0x14003e48a  xor     rax, rsp
0x14003e48d  mov     [rbp+57h+var_10], rax
0x14003e491  xorps   xmm0, xmm0
0x14003e494  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x14003e49a  xorps   xmm1, xmm1
0x14003e49d  lea     rdx, SourceString; "RESTRICTED SERVICES"
0x14003e4a4  xor     edi, edi
0x14003e4a6  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14003e4aa  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14003e4ae  mov     [rbp+57h+var_40], rdi
0x14003e4b2  movups  xmmword ptr [rbp+57h+var_28.Length], xmm1
0x14003e4b6  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], edi
0x14003e4b9  call    cs:__imp_RtlInitUnicodeString
0x14003e4c0  nop     dword ptr [rax+rax+00h]
0x14003e4c5  lea     rdx, aPrintspoolerse; "PrintSpoolerService"
0x14003e4cc  lea     rcx, [rbp+57h+var_28]; DestinationString
0x14003e4d0  call    cs:__imp_RtlInitUnicodeString
0x14003e4d7  nop     dword ptr [rax+rax+00h]
0x14003e4dc  lea     rax, [rbp+57h+var_40]
0x14003e4e0  xor     r9d, r9d; SubAuthority1
0x14003e4e3  mov     [rsp+0A0h+Sid], rax; Sid
0x14003e4e8  lea     ebx, [rdi+63h]
0x14003e4eb  mov     [rsp+0A0h+SubAuthority7], edi; SubAuthority7
0x14003e4ef  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x14003e4f3  mov     [rsp+0A0h+SubAuthority6], edi; SubAuthority6
0x14003e4f7  mov     r8d, ebx; SubAuthority0
0x14003e4fa  mov     [rsp+0A0h+SubAuthority5], edi; SubAuthority5
0x14003e4fe  mov     dl, 1; SubAuthorityCount
0x14003e500  mov     [rsp+0A0h+SubAuthority4], edi; SubAuthority4
0x14003e504  mov     [rsp+0A0h+SubAuthority3], edi; SubAuthority3
0x14003e508  mov     [rsp+0A0h+SubAuthority2], edi; SubAuthority2
0x14003e50c  call    cs:__imp_RtlAllocateAndInitializeSid
0x14003e513  nop     dword ptr [rax+rax+00h]
0x14003e518  test    eax, eax
0x14003e51a  js      loc_14003E5B9
0x14003e520  mov     [rsp+0A0h+SubAuthority6], 9C65577Dh
0x14003e528  lea     r8d, [rdi+6]
0x14003e52c  mov     [rsp+0A0h+SubAuthority5], 8F58C130h
0x14003e534  lea     rdx, [rbp+57h+IdentifierAuthority]
0x14003e538  mov     [rsp+0A0h+SubAuthority4], 0E5F30EDBh
0x14003e540  lea     rcx, ?g_abSpoolerServiceSidBuffer@@3PAEA; uchar near * g_abSpoolerServiceSidBuffer
0x14003e547  mov     [rsp+0A0h+SubAuthority3], 76F17EC4h
0x14003e54f  mov     r9d, ebx
0x14003e552  mov     [rsp+0A0h+SubAuthority2], 0CE5DBACh
0x14003e55a  call    cs:__imp_RtlInitializeSidEx
0x14003e561  nop     dword ptr [rax+rax+00h]
0x14003e566  mov     ebx, eax
0x14003e568  test    eax, eax
0x14003e56a  js      short loc_14003E5A2
0x14003e56c  mov     r8, [rbp+57h+var_40]; void *
0x14003e570  lea     rcx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x14003e574  xor     edx, edx; struct _UNICODE_STRING *
0x14003e576  call    ?AddSidMappingToLsa@@YAJPEAU_UNICODE_STRING@@0PEAX@Z; AddSidMappingToLsa(_UNICODE_STRING *,_UNICODE_STRING *,void *)
0x14003e57b  mov     ebx, eax
0x14003e57d  test    eax, eax
0x14003e57f  js      short loc_14003E5A2
0x14003e581  lea     r8, ?g_abSpoolerServiceSidBuffer@@3PAEA; void *
0x14003e588  lea     rdx, [rbp+57h+var_28]; struct _UNICODE_STRING *
0x14003e58c  lea     rcx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x14003e590  call    ?AddSidMappingToLsa@@YAJPEAU_UNICODE_STRING@@0PEAX@Z; AddSidMappingToLsa(_UNICODE_STRING *,_UNICODE_STRING *,void *)
0x14003e595  mov     ebx, eax
0x14003e597  test    eax, eax
0x14003e599  js      short loc_14003E5A2
0x14003e59b  call    ?UpdateLsaSecurityPolicy@@YAJPEAX@Z; UpdateLsaSecurityPolicy(void *)
0x14003e5a0  mov     ebx, eax
0x14003e5a2  mov     rcx, [rbp+57h+var_40]; Sid
0x14003e5a6  test    rcx, rcx
0x14003e5a9  jz      short loc_14003E5B7
0x14003e5ab  call    cs:__imp_RtlFreeSid
0x14003e5b2  nop     dword ptr [rax+rax+00h]
0x14003e5b7  mov     eax, ebx
0x14003e5b9  mov     rcx, [rbp+57h+var_10]
0x14003e5bd  xor     rcx, rsp; StackCookie
0x14003e5c0  call    __security_check_cookie
0x14003e5c5  lea     r11, [rsp+0A0h+var_s0]
0x14003e5cd  mov     rbx, [r11+10h]
0x14003e5d1  mov     rdi, [r11+18h]
0x14003e5d5  mov     rsp, r11
0x14003e5d8  pop     rbp
0x14003e5d9  retn
```
