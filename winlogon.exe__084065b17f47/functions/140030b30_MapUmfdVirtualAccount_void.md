# MapUmfdVirtualAccount(void)

- ea: `0x140030b30`
- end: `0x140030cc5`
- name: `?MapUmfdVirtualAccount@@YAJXZ`
- size: `405`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140030590`

## callees

- `0x14000d4e0`
- `0x140030b30`
- `0x14003c0b8`
- `0x140053720`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x140030c8d`
- `ntdll!RtlFreeSid` at `0x140030c9c`
- `ntdll!RtlFreeSid` at `0x140030c8d`
- `ntdll!RtlFreeSid` at `0x140030c9c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140030bf9`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140030c48`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140030bf9`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140030c48`
- `ntdll!RtlInitUnicodeString` at `0x140030bb4`
- `ntdll!RtlInitUnicodeString` at `0x140030bc5`
- `ntdll!RtlInitUnicodeString` at `0x140030bb4`
- `ntdll!RtlInitUnicodeString` at `0x140030bc5`

## pseudocode

```c
__int64 MapUmfdVirtualAccount(void)
{
  int v0; // ebx
  NTSTATUS v1; // ebx
  int v3; // [rsp+60h] [rbp+7h] BYREF
  PSID v4; // [rsp+68h] [rbp+Fh] BYREF
  PSID Sid; // [rsp+70h] [rbp+17h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp+1Fh] BYREF
  struct _UNICODE_STRING v7; // [rsp+88h] [rbp+2Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+98h] [rbp+3Fh] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  Sid = 0;
  v4 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  DestinationString = 0;
  v3 = 0;
  v7 = 0;
  v0 = StringCchPrintfW(&gwszUmfdAccountName, 0x20u, L"UMFD-%d", NtCurrentPeb()->SessionId);
  if ( v0 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"Font Driver Host");
    RtlInitUnicodeString(&v7, &gwszUmfdAccountName);
    v1 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x60u, 0, 0, 0, 0, 0, 0, 0, &Sid);
    if ( v1 < 0
      || (v1 = RtlAllocateAndInitializeSid(
                 &IdentifierAuthority,
                 3u,
                 0x60u,
                 0,
                 NtCurrentPeb()->SessionId,
                 0,
                 0,
                 0,
                 0,
                 0,
                 &v4),
          v1 < 0) )
    {
      v0 = v1 | 0x10000000;
    }
    else
    {
      v0 = AddSidMappingToLsa(&DestinationString, 0, Sid, (enum _LSA_SID_NAME_MAPPING_OPERATION_ERROR *)&v3);
      if ( v0 >= 0 )
        v0 = AddSidMappingToLsa(&DestinationString, &v7, v4, (enum _LSA_SID_NAME_MAPPING_OPERATION_ERROR *)&v3);
    }
  }
  if ( v4 )
    RtlFreeSid(v4);
  if ( Sid )
    RtlFreeSid(Sid);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x140030b30  mov     [rsp-8+arg_0], rbx
0x140030b35  mov     [rsp-8+arg_8], rdi
0x140030b3a  push    rbp
0x140030b3b  lea     rbp, [rsp-57h]
0x140030b40  sub     rsp, 0B0h
0x140030b47  mov     rax, cs:__security_cookie
0x140030b4e  xor     rax, rsp
0x140030b51  mov     [rbp+57h+var_10], rax
0x140030b55  xor     edi, edi
0x140030b57  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x140030b5d  mov     [rbp+57h+var_40], rdi
0x140030b61  lea     r8, aUmfdD; "UMFD-%d"
0x140030b68  mov     [rbp+57h+var_48], rdi
0x140030b6c  lea     rcx, ?gwszUmfdAccountName@@3PAGA; unsigned __int16 *
0x140030b73  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], edi
0x140030b76  xorps   xmm0, xmm0
0x140030b79  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140030b7d  mov     [rbp+57h+var_50], edi
0x140030b80  lea     edx, [rdi+20h]; unsigned __int64
0x140030b83  xorps   xmm1, xmm1
0x140030b86  movups  xmmword ptr [rbp+57h+var_28.Length], xmm1
0x140030b8a  mov     r9, gs:60h
0x140030b93  mov     r9d, [r9+2C0h]
0x140030b9a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140030b9f  mov     ebx, eax
0x140030ba1  test    eax, eax
0x140030ba3  js      loc_140030C84
0x140030ba9  lea     rdx, aFontDriverHost; "Font Driver Host"
0x140030bb0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140030bb4  call    cs:__imp_RtlInitUnicodeString
0x140030bba  lea     rdx, ?gwszUmfdAccountName@@3PAGA; SourceString
0x140030bc1  lea     rcx, [rbp+57h+var_28]; DestinationString
0x140030bc5  call    cs:__imp_RtlInitUnicodeString
0x140030bcb  lea     rax, [rbp+57h+var_40]
0x140030bcf  xor     r9d, r9d; SubAuthority1
0x140030bd2  mov     [rsp+0B0h+Sid], rax; Sid
0x140030bd7  lea     r8d, [rdi+60h]; SubAuthority0
0x140030bdb  mov     [rsp+0B0h+SubAuthority7], edi; SubAuthority7
0x140030bdf  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x140030be3  mov     [rsp+0B0h+SubAuthority6], edi; SubAuthority6
0x140030be7  mov     dl, 1; SubAuthorityCount
0x140030be9  mov     [rsp+0B0h+SubAuthority5], edi; SubAuthority5
0x140030bed  mov     [rsp+0B0h+SubAuthority4], edi; SubAuthority4
0x140030bf1  mov     [rsp+0B0h+SubAuthority3], edi; SubAuthority3
0x140030bf5  mov     [rsp+0B0h+SubAuthority2], edi; SubAuthority2
0x140030bf9  call    cs:__imp_RtlAllocateAndInitializeSid
0x140030bff  mov     ebx, eax
0x140030c01  test    eax, eax
0x140030c03  jns     short loc_140030C0B
0x140030c05  bts     ebx, 1Ch
0x140030c09  jmp     short loc_140030C84
0x140030c0b  mov     rax, gs:60h
0x140030c14  lea     rcx, [rbp+57h+var_48]
0x140030c18  mov     [rsp+0B0h+Sid], rcx; Sid
0x140030c1d  xor     r9d, r9d; SubAuthority1
0x140030c20  mov     [rsp+0B0h+SubAuthority7], edi; SubAuthority7
0x140030c24  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x140030c28  mov     [rsp+0B0h+SubAuthority6], edi; SubAuthority6
0x140030c2c  mov     dl, 3; SubAuthorityCount
0x140030c2e  mov     eax, [rax+2C0h]
0x140030c34  mov     [rsp+0B0h+SubAuthority5], edi; SubAuthority5
0x140030c38  lea     r8d, [r9+60h]; SubAuthority0
0x140030c3c  mov     [rsp+0B0h+SubAuthority4], edi; SubAuthority4
0x140030c40  mov     [rsp+0B0h+SubAuthority3], edi; SubAuthority3
0x140030c44  mov     [rsp+0B0h+SubAuthority2], eax; SubAuthority2
0x140030c48  call    cs:__imp_RtlAllocateAndInitializeSid
0x140030c4e  mov     ebx, eax
0x140030c50  test    eax, eax
0x140030c52  js      short loc_140030C05
0x140030c54  mov     r8, [rbp+57h+var_40]; void *
0x140030c58  lea     r9, [rbp+57h+var_50]; enum _LSA_SID_NAME_MAPPING_OPERATION_ERROR *
0x140030c5c  xor     edx, edx; struct _UNICODE_STRING *
0x140030c5e  lea     rcx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x140030c62  call    ?AddSidMappingToLsa@@YAJPEAU_UNICODE_STRING@@0PEAXPEAW4_LSA_SID_NAME_MAPPING_OPERATION_ERROR@@@Z; AddSidMappingToLsa(_UNICODE_STRING *,_UNICODE_STRING *,void *,_LSA_SID_NAME_MAPPING_OPERATION_ERROR *)
0x140030c67  mov     ebx, eax
0x140030c69  test    eax, eax
0x140030c6b  js      short loc_140030C84
0x140030c6d  mov     r8, [rbp+57h+var_48]; void *
0x140030c71  lea     r9, [rbp+57h+var_50]; enum _LSA_SID_NAME_MAPPING_OPERATION_ERROR *
0x140030c75  lea     rdx, [rbp+57h+var_28]; struct _UNICODE_STRING *
0x140030c79  lea     rcx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x140030c7d  call    ?AddSidMappingToLsa@@YAJPEAU_UNICODE_STRING@@0PEAXPEAW4_LSA_SID_NAME_MAPPING_OPERATION_ERROR@@@Z; AddSidMappingToLsa(_UNICODE_STRING *,_UNICODE_STRING *,void *,_LSA_SID_NAME_MAPPING_OPERATION_ERROR *)
0x140030c82  mov     ebx, eax
0x140030c84  mov     rcx, [rbp+57h+var_48]; Sid
0x140030c88  test    rcx, rcx
0x140030c8b  jz      short loc_140030C93
0x140030c8d  call    cs:__imp_RtlFreeSid
0x140030c93  mov     rcx, [rbp+57h+var_40]; Sid
0x140030c97  test    rcx, rcx
0x140030c9a  jz      short loc_140030CA2
0x140030c9c  call    cs:__imp_RtlFreeSid
0x140030ca2  mov     eax, ebx
0x140030ca4  mov     rcx, [rbp+57h+var_10]
0x140030ca8  xor     rcx, rsp; StackCookie
0x140030cab  call    __security_check_cookie
0x140030cb0  lea     r11, [rsp+0B0h+var_s0]
0x140030cb8  mov     rbx, [r11+10h]
0x140030cbc  mov     rdi, [r11+18h]
0x140030cc0  mov     rsp, r11
0x140030cc3  pop     rbp
0x140030cc4  retn
```
