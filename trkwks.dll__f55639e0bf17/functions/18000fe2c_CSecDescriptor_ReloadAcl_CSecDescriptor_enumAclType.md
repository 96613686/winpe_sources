# CSecDescriptor::_ReloadAcl(CSecDescriptor::enumAclType)

- ea: `0x18000fe2c`
- end: `0x18000fea8`
- name: `?_ReloadAcl@CSecDescriptor@@AEAAXW4enumAclType@1@@Z`
- size: `124`
- prototype: `BOOL __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d440`

## callees

- `0x18000d038`
- `0x18000fe2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe90`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000fe51`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000fe51`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x18000fe86`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x18000fe86`

## pseudocode

```c
BOOL __fastcall CSecDescriptor::_ReloadAcl(__int64 a1, int a2)
{
  BOOL result; // eax
  DWORD LastError; // eax
  DWORD v5; // eax

  result = 1;
  if ( a2 == 1 )
  {
    if ( (*(_BYTE *)(a1 + 28) & 2) != 0 )
    {
      result = SetSecurityDescriptorDacl(*(PSECURITY_DESCRIPTOR *)(a1 + 8), 1, *(PACL *)(a1 + 16), 0);
      if ( !result )
      {
        LastError = GetLastError();
        TrkRaiseWin32Error(LastError);
      }
      *(_DWORD *)(a1 + 28) &= ~2u;
    }
  }
  else if ( !a2 && (*(_BYTE *)(a1 + 44) & 2) != 0 )
  {
    result = SetSecurityDescriptorSacl(*(PSECURITY_DESCRIPTOR *)(a1 + 8), 1, *(PACL *)(a1 + 32), 0);
    if ( !result )
    {
      v5 = GetLastError();
      TrkRaiseWin32Error(v5);
    }
    *(_DWORD *)(a1 + 44) &= ~2u;
  }
  return result;
}

```

## disassembly

```asm
0x18000fe2c  push    rbx
0x18000fe2e  sub     rsp, 20h
0x18000fe32  mov     eax, 1
0x18000fe37  mov     rbx, rcx
0x18000fe3a  cmp     edx, eax
0x18000fe3c  jnz     short loc_18000FE6F
0x18000fe3e  test    byte ptr [rcx+1Ch], 2
0x18000fe42  jz      short loc_18000FEA2
0x18000fe44  mov     r8, [rcx+10h]; pDacl
0x18000fe48  xor     r9d, r9d; bDaclDefaulted
0x18000fe4b  mov     rcx, [rcx+8]; pSecurityDescriptor
0x18000fe4f  mov     edx, eax; bDaclPresent
0x18000fe51  call    cs:__imp_SetSecurityDescriptorDacl
0x18000fe57  test    eax, eax
0x18000fe59  jnz     short loc_18000FE69
0x18000fe5b  call    cs:__imp_GetLastError
0x18000fe61  mov     ecx, eax; int
0x18000fe63  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000fe69  and     dword ptr [rbx+1Ch], 0FFFFFFFDh
0x18000fe6d  jmp     short loc_18000FEA2
0x18000fe6f  test    edx, edx
0x18000fe71  jnz     short loc_18000FEA2
0x18000fe73  test    byte ptr [rcx+2Ch], 2
0x18000fe77  jz      short loc_18000FEA2
0x18000fe79  mov     r8, [rcx+20h]; pSacl
0x18000fe7d  xor     r9d, r9d; bSaclDefaulted
0x18000fe80  mov     rcx, [rcx+8]; pSecurityDescriptor
0x18000fe84  mov     edx, eax; bSaclPresent
0x18000fe86  call    cs:__imp_SetSecurityDescriptorSacl
0x18000fe8c  test    eax, eax
0x18000fe8e  jnz     short loc_18000FE9E
0x18000fe90  call    cs:__imp_GetLastError
0x18000fe96  mov     ecx, eax; int
0x18000fe98  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000fe9e  and     dword ptr [rbx+2Ch], 0FFFFFFFDh
0x18000fea2  add     rsp, 20h
0x18000fea6  pop     rbx
0x18000fea7  retn
```
