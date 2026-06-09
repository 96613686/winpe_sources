# SpoolerCreateServiceAccount(void)

- ea: `0x14003ae08`
- end: `0x14003af58`
- name: `?SpoolerCreateServiceAccount@@YAJXZ`
- size: `336`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14003b27c`
- `0x140048140`

## callees

- `0x14002abc0`
- `0x14003ad60`
- `0x14003ae08`
- `0x14003b53c`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x14003af2f`
- `ntdll!RtlFreeSid` at `0x14003af2f`
- `ntdll!RtlInitializeSidEx` at `0x14003aee4`
- `ntdll!RtlInitializeSidEx` at `0x14003aee4`
- `ntdll!RtlInitUnicodeString` at `0x14003ae55`
- `ntdll!RtlInitUnicodeString` at `0x14003ae66`
- `ntdll!RtlInitUnicodeString` at `0x14003ae55`
- `ntdll!RtlInitUnicodeString` at `0x14003ae66`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14003ae9c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14003ae9c`

## string_xrefs

- `0x14003ae39`: `RESTRICTED SERVICES`
- `0x14003ae5b`: `PrintSpoolerService`

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
0x14003ae08  mov     [rsp-8+arg_0], rbx
0x14003ae0d  mov     [rsp-8+arg_8], rdi
0x14003ae12  push    rbp
0x14003ae13  lea     rbp, [rsp-57h]
0x14003ae18  sub     rsp, 0A0h
0x14003ae1f  mov     rax, cs:__security_cookie
0x14003ae26  xor     rax, rsp
0x14003ae29  mov     [rbp+57h+var_10], rax
0x14003ae2d  xorps   xmm0, xmm0
0x14003ae30  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x14003ae36  xorps   xmm1, xmm1
0x14003ae39  lea     rdx, SourceString; "RESTRICTED SERVICES"
0x14003ae40  xor     edi, edi
0x14003ae42  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14003ae46  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14003ae4a  mov     [rbp+57h+var_40], rdi
0x14003ae4e  movups  xmmword ptr [rbp+57h+var_28.Length], xmm1
0x14003ae52  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], edi
0x14003ae55  call    cs:__imp_RtlInitUnicodeString
0x14003ae5b  lea     rdx, aPrintspoolerse; "PrintSpoolerService"
0x14003ae62  lea     rcx, [rbp+57h+var_28]; DestinationString
0x14003ae66  call    cs:__imp_RtlInitUnicodeString
0x14003ae6c  lea     rax, [rbp+57h+var_40]
0x14003ae70  xor     r9d, r9d; SubAuthority1
0x14003ae73  mov     [rsp+0A0h+Sid], rax; Sid
0x14003ae78  lea     ebx, [rdi+63h]
0x14003ae7b  mov     [rsp+0A0h+SubAuthority7], edi; SubAuthority7
0x14003ae7f  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x14003ae83  mov     [rsp+0A0h+SubAuthority6], edi; SubAuthority6
0x14003ae87  mov     r8d, ebx; SubAuthority0
0x14003ae8a  mov     [rsp+0A0h+SubAuthority5], edi; SubAuthority5
0x14003ae8e  mov     dl, 1; SubAuthorityCount
0x14003ae90  mov     [rsp+0A0h+SubAuthority4], edi; SubAuthority4
0x14003ae94  mov     [rsp+0A0h+SubAuthority3], edi; SubAuthority3
0x14003ae98  mov     [rsp+0A0h+SubAuthority2], edi; SubAuthority2
0x14003ae9c  call    cs:__imp_RtlAllocateAndInitializeSid
0x14003aea2  test    eax, eax
0x14003aea4  js      loc_14003AF37
0x14003aeaa  mov     [rsp+0A0h+SubAuthority6], 9C65577Dh
0x14003aeb2  lea     r8d, [rdi+6]
0x14003aeb6  mov     [rsp+0A0h+SubAuthority5], 8F58C130h
0x14003aebe  lea     rdx, [rbp+57h+IdentifierAuthority]
0x14003aec2  mov     [rsp+0A0h+SubAuthority4], 0E5F30EDBh
0x14003aeca  lea     rcx, ?g_abSpoolerServiceSidBuffer@@3PAEA; uchar near * g_abSpoolerServiceSidBuffer
0x14003aed1  mov     [rsp+0A0h+SubAuthority3], 76F17EC4h
0x14003aed9  mov     r9d, ebx
0x14003aedc  mov     [rsp+0A0h+SubAuthority2], 0CE5DBACh
0x14003aee4  call    cs:__imp_RtlInitializeSidEx
0x14003aeea  mov     ebx, eax
0x14003aeec  test    eax, eax
0x14003aeee  js      short loc_14003AF26
0x14003aef0  mov     r8, [rbp+57h+var_40]; void *
0x14003aef4  lea     rcx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x14003aef8  xor     edx, edx; struct _UNICODE_STRING *
0x14003aefa  call    ?AddSidMappingToLsa@@YAJPEAU_UNICODE_STRING@@0PEAX@Z; AddSidMappingToLsa(_UNICODE_STRING *,_UNICODE_STRING *,void *)
0x14003aeff  mov     ebx, eax
0x14003af01  test    eax, eax
0x14003af03  js      short loc_14003AF26
0x14003af05  lea     r8, ?g_abSpoolerServiceSidBuffer@@3PAEA; void *
0x14003af0c  lea     rdx, [rbp+57h+var_28]; struct _UNICODE_STRING *
0x14003af10  lea     rcx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x14003af14  call    ?AddSidMappingToLsa@@YAJPEAU_UNICODE_STRING@@0PEAX@Z; AddSidMappingToLsa(_UNICODE_STRING *,_UNICODE_STRING *,void *)
0x14003af19  mov     ebx, eax
0x14003af1b  test    eax, eax
0x14003af1d  js      short loc_14003AF26
0x14003af1f  call    ?UpdateLsaSecurityPolicy@@YAJPEAX@Z; UpdateLsaSecurityPolicy(void *)
0x14003af24  mov     ebx, eax
0x14003af26  mov     rcx, [rbp+57h+var_40]; Sid
0x14003af2a  test    rcx, rcx
0x14003af2d  jz      short loc_14003AF35
0x14003af2f  call    cs:__imp_RtlFreeSid
0x14003af35  mov     eax, ebx
0x14003af37  mov     rcx, [rbp+57h+var_10]
0x14003af3b  xor     rcx, rsp; StackCookie
0x14003af3e  call    __security_check_cookie
0x14003af43  lea     r11, [rsp+0A0h+var_s0]
0x14003af4b  mov     rbx, [r11+10h]
0x14003af4f  mov     rdi, [r11+18h]
0x14003af53  mov     rsp, r11
0x14003af56  pop     rbp
0x14003af57  retn
```
