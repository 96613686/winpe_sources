# GetPrimaryDomainName(ushort * *)

- ea: `0x18002b5fc`
- end: `0x18002b74b`
- name: `?GetPrimaryDomainName@@YAKPEAPEAG@Z`
- size: `335`
- prototype: `unsigned int __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002376c`

## callees

- `0x18000b440`
- `0x18001ce90`
- `0x180022e80`
- `0x18002b5fc`
- `0x1800325e4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18002b676`
- `ntdll!RtlNtStatusToDosError` at `0x18002b676`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002b6b7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002b6b7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18002b664`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18002b664`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002b647`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002b647`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002b6a9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002b6a9`

## pseudocode

```c
__int64 __fastcall GetPrimaryDomainName(unsigned __int16 **a1)
{
  int v2; // eax
  ULONG v3; // ebx
  wchar_t *v5; // rdi
  wchar_t *v6; // rax
  unsigned __int16 *v7; // rax
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  PVOID Buffer; // [rsp+60h] [rbp+10h] BYREF
  PVOID PolicyHandle; // [rsp+68h] [rbp+18h] BYREF

  *a1 = 0;
  PolicyHandle = 0;
  Buffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v2 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( v2 < 0 || (v2 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer), v2 < 0) )
  {
    v3 = RtlNtStatusToDosError(v2);
    goto LABEL_4;
  }
  v5 = 0;
  if ( *((_QWORD *)Buffer + 3) )
  {
    v6 = (wchar_t *)ldapMalloc((unsigned int)*((unsigned __int16 *)Buffer + 8) + 2, 1953712204);
    v5 = v6;
    if ( !v6 )
    {
      v3 = 90;
      goto LABEL_4;
    }
    StringCbCopyW(v6, *((unsigned __int16 *)Buffer + 8) + 2LL, *((STRSAFE_LPCWSTR *)Buffer + 3));
  }
  v7 = (unsigned __int16 *)ldap_dup_stringW(v5);
  *a1 = v7;
  v3 = 0;
  if ( v7 )
  {
    if ( !v5 )
      goto LABEL_4;
  }
  else
  {
    if ( !v5 )
      goto LABEL_4;
    v3 = 90;
  }
  ldapFree(v5, 1953712204);
LABEL_4:
  if ( Buffer )
    LsaFreeMemory(Buffer);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return v3;
}

```

## disassembly

```asm
0x18002b5fc  mov     [rsp-8+arg_10], rbx
0x18002b601  mov     [rsp-8+arg_18], rdi
0x18002b606  push    rbp
0x18002b607  mov     rbp, rsp
0x18002b60a  sub     rsp, 50h
0x18002b60e  xorps   xmm0, xmm0
0x18002b611  mov     qword ptr [rcx], 0
0x18002b618  mov     rbx, rcx
0x18002b61b  mov     [rbp+PolicyHandle], 0
0x18002b623  xor     ecx, ecx; SystemName
0x18002b625  mov     [rbp+Buffer], 0
0x18002b62d  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18002b631  mov     r8d, 1; DesiredAccess
0x18002b637  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x18002b63b  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18002b63f  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18002b643  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002b647  call    cs:__imp_LsaOpenPolicy
0x18002b64e  nop     dword ptr [rax+rax+00h]
0x18002b653  test    eax, eax
0x18002b655  js      short loc_18002B674
0x18002b657  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18002b65b  lea     r8, [rbp+Buffer]; Buffer
0x18002b65f  mov     edx, 0Ch; InformationClass
0x18002b664  call    cs:__imp_LsaQueryInformationPolicy
0x18002b66b  nop     dword ptr [rax+rax+00h]
0x18002b670  test    eax, eax
0x18002b672  jns     short loc_18002B6C5
0x18002b674  mov     ecx, eax; Status
0x18002b676  call    cs:__imp_RtlNtStatusToDosError
0x18002b67d  nop     dword ptr [rax+rax+00h]
0x18002b682  mov     ebx, eax
0x18002b684  mov     rcx, [rbp+Buffer]; Buffer
0x18002b688  test    rcx, rcx
0x18002b68b  jnz     short loc_18002B6A9
0x18002b68d  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18002b691  test    rcx, rcx
0x18002b694  jnz     short loc_18002B6B7
0x18002b696  mov     rdi, [rsp+50h+arg_18]
0x18002b69b  mov     eax, ebx
0x18002b69d  mov     rbx, [rsp+50h+arg_10]
0x18002b6a2  add     rsp, 50h
0x18002b6a6  pop     rbp
0x18002b6a7  retn
0x18002b6a9  call    cs:__imp_LsaFreeMemory
0x18002b6b0  nop     dword ptr [rax+rax+00h]
0x18002b6b5  jmp     short loc_18002B68D
0x18002b6b7  call    cs:__imp_LsaClose
0x18002b6be  nop     dword ptr [rax+rax+00h]
0x18002b6c3  jmp     short loc_18002B696
0x18002b6c5  mov     rax, [rbp+Buffer]
0x18002b6c9  xor     edi, edi
0x18002b6cb  cmp     [rax+18h], rdi
0x18002b6cf  jz      short loc_18002B708
0x18002b6d1  movzx   ecx, word ptr [rax+10h]
0x18002b6d5  mov     edx, 7473484Ch
0x18002b6da  add     ecx, 2
0x18002b6dd  call    ldapMalloc
0x18002b6e2  mov     rdi, rax
0x18002b6e5  test    rax, rax
0x18002b6e8  jnz     short loc_18002B6EF
0x18002b6ea  lea     ebx, [rax+5Ah]
0x18002b6ed  jmp     short loc_18002B684
0x18002b6ef  mov     r8, [rbp+Buffer]
0x18002b6f3  mov     rcx, rax; pszDest
0x18002b6f6  movzx   edx, word ptr [r8+10h]
0x18002b6fb  mov     r8, [r8+18h]; pszSrc
0x18002b6ff  add     rdx, 2; cbDest
0x18002b703  call    StringCbCopyW
0x18002b708  xor     edx, edx
0x18002b70a  mov     r8d, 7473484Ch
0x18002b710  mov     rcx, rdi; Src
0x18002b713  call    ldap_dup_stringW
0x18002b718  mov     [rbx], rax
0x18002b71b  xor     ebx, ebx
0x18002b71d  test    rax, rax
0x18002b720  jnz     short loc_18002B730
0x18002b722  test    rdi, rdi
0x18002b725  jz      loc_18002B684
0x18002b72b  lea     ebx, [rax+5Ah]
0x18002b72e  jmp     short loc_18002B739
0x18002b730  test    rdi, rdi
0x18002b733  jz      loc_18002B684
0x18002b739  mov     edx, 7473484Ch
0x18002b73e  mov     rcx, rdi
0x18002b741  call    ldapFree
0x18002b746  jmp     loc_18002B684
```
