# ACLTempBackingStoreDir

- ea: `0x180055d7c`
- end: `0x180055e8b`
- name: `ACLTempBackingStoreDir`
- size: `271`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, unsigned int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180056b10`

## callees

- `0x180001c00`
- `0x180055d7c`
- `0x18005f394`
- `0x18005f598`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180055e56`
- `KERNEL32!LocalFree` at `0x180055e61`
- `KERNEL32!LocalFree` at `0x180055e56`
- `KERNEL32!LocalFree` at `0x180055e61`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x180055de4`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x180055de4`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180055e44`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180055e44`

## pseudocode

```c
__int64 __fastcall ACLTempBackingStoreDir(LPWSTR pObjectName, unsigned int a2, void **a3)
{
  DWORD NamedSecurityInfoW; // ebx
  PACL v4; // rdi
  unsigned int v8; // r8d
  unsigned int v9; // r9d
  PACL pDacl; // [rsp+40h] [rbp-38h] BYREF
  PACL pAcl; // [rsp+48h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-28h] BYREF

  NamedSecurityInfoW = 0;
  pAcl = 0;
  v4 = 0;
  hMem = 0;
  pDacl = 0;
  if ( a2 )
  {
    NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, &pAcl, 0, &hMem);
    if ( !NamedSecurityInfoW )
    {
      NamedSecurityInfoW = SBESecurityHelpers::CopyACL(pAcl, &pDacl);
      if ( NamedSecurityInfoW
        || (NamedSecurityInfoW = SBESecurityHelpers::BuildAndAppendAccessAllowedACL(a2, a3, v8, v9, &pDacl)) != 0 )
      {
        v4 = pDacl;
      }
      else
      {
        v4 = pDacl;
        NamedSecurityInfoW = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, pDacl, 0);
      }
    }
  }
  LocalFree(v4);
  LocalFree(hMem);
  return NamedSecurityInfoW;
}

```

## disassembly

```asm
0x180055d7c  mov     r11, rsp
0x180055d7f  mov     [r11+10h], rbx
0x180055d83  mov     [r11+20h], rbp
0x180055d87  push    rsi
0x180055d88  push    rdi
0x180055d89  push    r14
0x180055d8b  sub     rsp, 60h
0x180055d8f  mov     rax, cs:__security_cookie
0x180055d96  xor     rax, rsp
0x180055d99  mov     [rsp+78h+var_20], rax
0x180055d9e  xor     ebx, ebx
0x180055da0  mov     qword ptr [r11-30h], 0
0x180055da8  xor     edi, edi
0x180055daa  mov     [r11-28h], rbx
0x180055dae  mov     [r11-38h], rdi
0x180055db2  mov     r14, r8
0x180055db5  mov     esi, edx
0x180055db7  mov     rbp, rcx
0x180055dba  test    edx, edx
0x180055dbc  jz      loc_180055E53
0x180055dc2  lea     rax, [r11-28h]
0x180055dc6  xor     r9d, r9d; ppsidOwner
0x180055dc9  mov     [r11-40h], rax
0x180055dcd  lea     edx, [rbx+1]; ObjectType
0x180055dd0  mov     [r11-48h], rbx
0x180055dd4  lea     rax, [r11-30h]
0x180055dd8  mov     [r11-50h], rax
0x180055ddc  lea     r8d, [rbx+4]; SecurityInfo
0x180055de0  mov     [r11-58h], rbx
0x180055de4  call    cs:__imp_GetNamedSecurityInfoW
0x180055dea  mov     ebx, eax
0x180055dec  test    eax, eax
0x180055dee  jnz     short loc_180055E53
0x180055df0  mov     rcx, [rsp+78h+pAcl]; pAcl
0x180055df5  lea     rdx, [rsp+78h+var_38]; struct _ACL **
0x180055dfa  call    ?CopyACL@SBESecurityHelpers@@SAKPEAU_ACL@@PEAPEAU2@@Z; SBESecurityHelpers::CopyACL(_ACL *,_ACL * *)
0x180055dff  mov     ebx, eax
0x180055e01  test    eax, eax
0x180055e03  jnz     short loc_180055E4E
0x180055e05  lea     rax, [rsp+78h+var_38]
0x180055e0a  mov     rdx, r14; void **
0x180055e0d  mov     ecx, esi; unsigned int
0x180055e0f  mov     [rsp+78h+psidGroup], rax; struct _ACL **
0x180055e14  call    ?BuildAndAppendAccessAllowedACL@SBESecurityHelpers@@SAKKPEAPEAXKKPEAPEAU_ACL@@@Z; SBESecurityHelpers::BuildAndAppendAccessAllowedACL(ulong,void * *,ulong,ulong,_ACL * *)
0x180055e19  mov     ebx, eax
0x180055e1b  test    eax, eax
0x180055e1d  jnz     short loc_180055E4E
0x180055e1f  mov     [rsp+78h+pSacl], rdi; pSacl
0x180055e24  lea     edx, [rax+1]; ObjectType
0x180055e27  mov     rdi, [rsp+78h+var_38]
0x180055e2c  lea     r8d, [rax+4]; SecurityInfo
0x180055e30  mov     [rsp+78h+pDacl], rdi; pDacl
0x180055e35  xor     r9d, r9d; psidOwner
0x180055e38  mov     rcx, rbp; pObjectName
0x180055e3b  mov     [rsp+78h+psidGroup], 0; psidGroup
0x180055e44  call    cs:__imp_SetNamedSecurityInfoW
0x180055e4a  mov     ebx, eax
0x180055e4c  jmp     short loc_180055E53
0x180055e4e  mov     rdi, [rsp+78h+var_38]
0x180055e53  mov     rcx, rdi; hMem
0x180055e56  call    cs:__imp_LocalFree
0x180055e5c  mov     rcx, [rsp+78h+hMem]; hMem
0x180055e61  call    cs:__imp_LocalFree
0x180055e67  mov     eax, ebx
0x180055e69  mov     rcx, [rsp+78h+var_20]
0x180055e6e  xor     rcx, rsp; StackCookie
0x180055e71  call    __security_check_cookie
0x180055e76  lea     r11, [rsp+78h+var_18]
0x180055e7b  mov     rbx, [r11+28h]
0x180055e7f  mov     rbp, [r11+38h]
0x180055e83  mov     rsp, r11
0x180055e86  pop     r14
0x180055e88  pop     rdi
0x180055e89  pop     rsi
0x180055e8a  retn
```
