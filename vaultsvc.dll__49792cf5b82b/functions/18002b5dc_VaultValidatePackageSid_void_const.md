# VaultValidatePackageSid(void * const)

- ea: `0x18002b5dc`
- end: `0x18002b6e1`
- name: `?VaultValidatePackageSid@@YAKQEAX@Z`
- size: `261`
- prototype: `unsigned int __fastcall(PSID pSid)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002b3d0`
- `0x180038d84`

## callees

- `0x18002b5dc`
- `0x18003b7d8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002b661`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002b661`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002b5f6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002b5f6`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002b5e9`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002b5e9`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18002b604`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18002b604`
- `ntdll!RtlIsPackageSid` at `0x18002b610`
- `ntdll!RtlIsPackageSid` at `0x18002b610`

## pseudocode

```c
__int64 __fastcall VaultValidatePackageSid(PSID pSid)
{
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rdi
  _QWORD *v4; // rcx
  int v5; // ecx
  PDWORD SidSubAuthority; // rax
  __int64 v7; // rdx

  if ( !IsValidSid(pSid) || !*GetSidSubAuthorityCount(pSid) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return 87;
    v7 = 39;
    goto LABEL_20;
  }
  SidIdentifierAuthority = GetSidIdentifierAuthority(pSid);
  if ( (unsigned __int8)RtlIsPackageSid(pSid) )
    return 0;
  v5 = *(_DWORD *)SidIdentifierAuthority->Value;
  if ( !*(_DWORD *)SidIdentifierAuthority->Value )
    v5 = *(unsigned __int16 *)&SidIdentifierAuthority->Value[4] - 4096;
  if ( v5 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return 87;
    v7 = 40;
    goto LABEL_20;
  }
  SidSubAuthority = GetSidSubAuthority(pSid, 0);
  if ( *SidSubAuthority == 4096 || *SidSubAuthority == 0x2000 )
    return 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v7 = 41;
LABEL_20:
    WPP_SF_d(v4[2], v7, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids, 87);
  }
  return 87;
}

```

## disassembly

```asm
0x18002b5dc  mov     [rsp+arg_0], rbx
0x18002b5e1  push    rdi
0x18002b5e2  sub     rsp, 20h
0x18002b5e6  mov     rbx, rcx
0x18002b5e9  call    cs:__imp_IsValidSid
0x18002b5ef  test    eax, eax
0x18002b5f1  jz      short loc_18002B627
0x18002b5f3  mov     rcx, rbx; pSid
0x18002b5f6  call    cs:__imp_GetSidSubAuthorityCount
0x18002b5fc  cmp     byte ptr [rax], 1
0x18002b5ff  jb      short loc_18002B627
0x18002b601  mov     rcx, rbx; pSid
0x18002b604  call    cs:__imp_GetSidIdentifierAuthority
0x18002b60a  mov     rcx, rbx
0x18002b60d  mov     rdi, rax
0x18002b610  call    cs:__imp_RtlIsPackageSid
0x18002b616  test    al, al
0x18002b618  jz      short loc_18002B641
0x18002b61a  xor     eax, eax
0x18002b61c  mov     rbx, [rsp+28h+arg_0]
0x18002b621  add     rsp, 20h
0x18002b625  pop     rdi
0x18002b626  retn
0x18002b627  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b62e  lea     rax, WPP_GLOBAL_Control
0x18002b635  cmp     rcx, rax
0x18002b638  jnz     short loc_18002B6B7
0x18002b63a  mov     eax, 57h ; 'W'
0x18002b63f  jmp     short loc_18002B61C
0x18002b641  mov     ecx, [rdi]
0x18002b643  sub     ecx, cs:dword_180053C18
0x18002b649  jnz     short loc_18002B658
0x18002b64b  movzx   ecx, word ptr [rdi+4]
0x18002b64f  movzx   eax, cs:word_180053C1C
0x18002b656  sub     ecx, eax
0x18002b658  test    ecx, ecx
0x18002b65a  jnz     short loc_18002B697
0x18002b65c  xor     edx, edx; nSubAuthority
0x18002b65e  mov     rcx, rbx; pSid
0x18002b661  call    cs:__imp_GetSidSubAuthority
0x18002b667  cmp     dword ptr [rax], 1000h
0x18002b66d  jz      short loc_18002B61A
0x18002b66f  cmp     dword ptr [rax], 2000h
0x18002b675  jz      short loc_18002B61A
0x18002b677  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b67e  lea     rax, WPP_GLOBAL_Control
0x18002b685  cmp     rcx, rax
0x18002b688  jz      short loc_18002B63A
0x18002b68a  test    byte ptr [rcx+1Ch], 2
0x18002b68e  jz      short loc_18002B63A
0x18002b690  mov     edx, 29h ; ')'
0x18002b695  jmp     short loc_18002B6C6
0x18002b697  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b69e  lea     rax, WPP_GLOBAL_Control
0x18002b6a5  cmp     rcx, rax
0x18002b6a8  jz      short loc_18002B63A
0x18002b6aa  test    byte ptr [rcx+1Ch], 2
0x18002b6ae  jz      short loc_18002B63A
0x18002b6b0  mov     edx, 28h ; '('
0x18002b6b5  jmp     short loc_18002B6C6
0x18002b6b7  test    byte ptr [rcx+1Ch], 2
0x18002b6bb  jz      loc_18002B63A
0x18002b6c1  mov     edx, 27h ; '''
0x18002b6c6  mov     rcx, [rcx+10h]
0x18002b6ca  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x18002b6d1  mov     r9d, 57h ; 'W'
0x18002b6d7  call    WPP_SF_d
0x18002b6dc  jmp     loc_18002B63A
```
