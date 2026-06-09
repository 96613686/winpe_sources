# SBESecurityHelpers::IsAccessAllowedACEPresent(_ACL *,ulong,void *)

- ea: `0x18005f95c`
- end: `0x18005fa10`
- name: `?IsAccessAllowedACEPresent@SBESecurityHelpers@@SAHPEAU_ACL@@KPEAX@Z`
- size: `180`
- prototype: `__int64 __fastcall(PACL pAcl, unsigned int, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005f394`

## callees

- `0x180001c00`
- `0x18005f95c`

## import_xrefs

- `ADVAPI32!EqualSid` at `0x18005f9e1`
- `ADVAPI32!EqualSid` at `0x18005f9e1`
- `ADVAPI32!GetAce` at `0x18005f9b7`
- `ADVAPI32!GetAce` at `0x18005f9b7`
- `ADVAPI32!GetAclInformation` at `0x18005f99b`
- `ADVAPI32!GetAclInformation` at `0x18005f99b`

## pseudocode

```c
__int64 __fastcall SBESecurityHelpers::IsAccessAllowedACEPresent(PACL pAcl, __int64 a2, void *a3)
{
  unsigned int v5; // edi
  DWORD i; // ebx
  LPVOID pAce; // [rsp+20h] [rbp-38h] BYREF
  __int64 v9; // [rsp+28h] [rbp-30h] BYREF
  int v10; // [rsp+30h] [rbp-28h]

  v9 = 0;
  v10 = 0;
  pAce = 0;
  v5 = 0;
  if ( GetAclInformation(pAcl, &v9, 0xCu, AclSizeInformation) )
  {
    for ( i = 0; i < (unsigned int)v9 && GetAce(pAcl, i, &pAce); ++i )
    {
      if ( !*(_BYTE *)pAce && (*((_DWORD *)pAce + 1) & 0xC0000040) == 0xC0000040 && EqualSid((char *)pAce + 8, a3) )
        return 1;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18005f95c  mov     r11, rsp
0x18005f95f  mov     [r11+10h], rbx
0x18005f963  push    rbp
0x18005f964  push    rsi
0x18005f965  push    rdi
0x18005f966  sub     rsp, 40h
0x18005f96a  mov     rax, cs:__security_cookie
0x18005f971  xor     rax, rsp
0x18005f974  mov     [rsp+58h+var_20], rax
0x18005f979  xor     eax, eax
0x18005f97b  lea     rdx, [r11-30h]; pAclInformation
0x18005f97f  mov     rbp, r8
0x18005f982  mov     [r11-30h], rax
0x18005f986  mov     rsi, rcx
0x18005f989  mov     [rsp+58h+var_28], eax
0x18005f98d  mov     [r11-38h], rax
0x18005f991  xor     edi, edi
0x18005f993  lea     r9d, [rax+2]; dwAclInformationClass
0x18005f997  lea     r8d, [rax+0Ch]; nAclInformationLength
0x18005f99b  call    cs:__imp_GetAclInformation
0x18005f9a1  test    eax, eax
0x18005f9a3  jz      short loc_18005F9F4
0x18005f9a5  xor     ebx, ebx
0x18005f9a7  cmp     ebx, dword ptr [rsp+58h+var_30]
0x18005f9ab  jnb     short loc_18005F9F4
0x18005f9ad  lea     r8, [rsp+58h+pAce]; pAce
0x18005f9b2  mov     edx, ebx; dwAceIndex
0x18005f9b4  mov     rcx, rsi; pAcl
0x18005f9b7  call    cs:__imp_GetAce
0x18005f9bd  test    eax, eax
0x18005f9bf  jz      short loc_18005F9F4
0x18005f9c1  mov     rcx, [rsp+58h+pAce]
0x18005f9c6  cmp     [rcx], dil
0x18005f9c9  jnz     short loc_18005F9EB
0x18005f9cb  mov     eax, [rcx+4]
0x18005f9ce  and     eax, 0C0000040h
0x18005f9d3  cmp     eax, 0C0000040h
0x18005f9d8  jnz     short loc_18005F9EB
0x18005f9da  add     rcx, 8; pSid1
0x18005f9de  mov     rdx, rbp; pSid2
0x18005f9e1  call    cs:__imp_EqualSid
0x18005f9e7  test    eax, eax
0x18005f9e9  jnz     short loc_18005F9EF
0x18005f9eb  inc     ebx
0x18005f9ed  jmp     short loc_18005F9A7
0x18005f9ef  mov     edi, 1
0x18005f9f4  mov     eax, edi
0x18005f9f6  mov     rcx, [rsp+58h+var_20]
0x18005f9fb  xor     rcx, rsp; StackCookie
0x18005f9fe  call    __security_check_cookie
0x18005fa03  mov     rbx, [rsp+58h+arg_8]
0x18005fa08  add     rsp, 40h
0x18005fa0c  pop     rdi
0x18005fa0d  pop     rsi
0x18005fa0e  pop     rbp
0x18005fa0f  retn
```
