# BuildUserPolicyACL

- ea: `0x180012b88`
- end: `0x180012ca2`
- name: `BuildUserPolicyACL`
- size: `282`
- prototype: `__int64 __fastcall(unsigned int, WCHAR *, struct _ACL *, HLOCAL *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800137a0`
- `0x18001396c`

## callees

- `0x18000a192`
- `0x180012b88`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012c7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012c7b`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180012c5e`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180012c5e`

## pseudocode

```c
__int64 __fastcall BuildUserPolicyACL(unsigned int a1, WCHAR *a2, struct _ACL *a3, HLOCAL *a4)
{
  __int64 v4; // rbx
  DWORD v8; // eax
  ULONG v9; // r10d
  unsigned int v10; // eax
  DWORD v11; // ebx
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+20h] [rbp-60h] BYREF
  unsigned int v14; // [rsp+50h] [rbp-30h]
  __int64 v15; // [rsp+54h] [rbp-2Ch]
  int v16; // [rsp+6Ch] [rbp-14h]
  int v17; // [rsp+70h] [rbp-10h]
  WCHAR *v18; // [rsp+78h] [rbp-8h]
  PACL NewAcl; // [rsp+A8h] [rbp+28h] BYREF

  v4 = a1;
  NewAcl = 0;
  *a4 = 0;
  if ( !a2 || a1 > 7 )
    return 87;
  memset_0(&pListOfExplicitEntries, 0, 0x60u);
  pListOfExplicitEntries.Trustee.ptstrName = a2;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_USER;
  if ( (_DWORD)v4 )
  {
    if ( (_DWORD)v4 != 7 )
    {
      v9 = 2;
      pListOfExplicitEntries.grfAccessPermissions = StorageDeviceAccess[v4];
      v10 = HIDWORD(StorageDeviceAccess[v4]) & 0xFFEDFFFF;
      pListOfExplicitEntries.grfAccessMode = SET_ACCESS;
      v14 = v10;
      v15 = 3;
      v16 = 0;
      v17 = 1;
      v18 = a2;
      goto LABEL_9;
    }
    v8 = HIDWORD(StorageDeviceAccess[v4]) & 0xFFEDFFFF;
    pListOfExplicitEntries.grfAccessMode = DENY_ACCESS;
  }
  else
  {
    v8 = StorageDeviceAccess[v4];
    pListOfExplicitEntries.grfAccessMode = SET_ACCESS;
  }
  v9 = 1;
  pListOfExplicitEntries.grfAccessPermissions = v8;
LABEL_9:
  v11 = SetEntriesInAclW(v9, &pListOfExplicitEntries, a3, &NewAcl);
  if ( v11 )
  {
    if ( *a4 )
      LocalFree(*a4);
  }
  else
  {
    *a4 = NewAcl;
  }
  return v11;
}

```

## disassembly

```asm
0x180012b88  mov     [rsp-18h+arg_0], rbx
0x180012b8d  mov     [rsp-18h+arg_10], rsi
0x180012b92  push    rbp
0x180012b93  push    rdi
0x180012b94  push    r14
0x180012b96  mov     rbp, rsp
0x180012b99  sub     rsp, 80h
0x180012ba0  mov     ebx, ecx
0x180012ba2  mov     rdi, r9
0x180012ba5  mov     [rbp+NewAcl], 0
0x180012bad  mov     r14, r8
0x180012bb0  mov     qword ptr [r9], 0
0x180012bb7  mov     rsi, rdx
0x180012bba  test    rdx, rdx
0x180012bbd  jz      loc_180012C85
0x180012bc3  cmp     ebx, 7
0x180012bc6  ja      loc_180012C85
0x180012bcc  xor     edx, edx; Val
0x180012bce  lea     rcx, [rbp+pListOfExplicitEntries]; void *
0x180012bd2  lea     r8d, [rdx+60h]; Size
0x180012bd6  call    memset_0
0x180012bdb  mov     [rbp+pListOfExplicitEntries.Trustee.ptstrName], rsi
0x180012bdf  mov     r8d, 1
0x180012be5  mov     [rbp+pListOfExplicitEntries.Trustee.TrusteeType], r8d
0x180012be9  lea     rcx, StorageDeviceAccess
0x180012bf0  test    ebx, ebx
0x180012bf2  jnz     short loc_180012C00
0x180012bf4  mov     eax, [rcx+rbx*8]
0x180012bf7  mov     [rbp+pListOfExplicitEntries.grfAccessMode], 2
0x180012bfe  jmp     short loc_180012C15
0x180012c00  cmp     ebx, 7
0x180012c03  jnz     short loc_180012C1D
0x180012c05  mov     eax, [rcx+rbx*8+4]
0x180012c09  and     eax, 0FFEDFFFFh
0x180012c0e  mov     [rbp+pListOfExplicitEntries.grfAccessMode], 3
0x180012c15  mov     r10d, r8d
0x180012c18  mov     [rbp+pListOfExplicitEntries.grfAccessPermissions], eax
0x180012c1b  jmp     short loc_180012C50
0x180012c1d  mov     eax, [rcx+rbx*8]
0x180012c20  mov     r10d, 2
0x180012c26  mov     [rbp+pListOfExplicitEntries.grfAccessPermissions], eax
0x180012c29  mov     eax, [rcx+rbx*8+4]
0x180012c2d  and     eax, 0FFEDFFFFh
0x180012c32  mov     [rbp+pListOfExplicitEntries.grfAccessMode], r10d
0x180012c36  mov     [rbp+var_30], eax
0x180012c39  mov     [rbp+var_2C], 3
0x180012c41  mov     [rbp+var_14], 0
0x180012c48  mov     [rbp+var_10], r8d
0x180012c4c  mov     [rbp+var_8], rsi
0x180012c50  lea     r9, [rbp+NewAcl]; NewAcl
0x180012c54  mov     r8, r14; OldAcl
0x180012c57  lea     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x180012c5b  mov     ecx, r10d; cCountOfExplicitEntries
0x180012c5e  call    cs:__imp_SetEntriesInAclW
0x180012c64  mov     ebx, eax
0x180012c66  test    eax, eax
0x180012c68  jnz     short loc_180012C73
0x180012c6a  mov     rax, [rbp+NewAcl]
0x180012c6e  mov     [rdi], rax
0x180012c71  jmp     short loc_180012C81
0x180012c73  mov     rcx, [rdi]; hMem
0x180012c76  test    rcx, rcx
0x180012c79  jz      short loc_180012C81
0x180012c7b  call    cs:__imp_LocalFree
0x180012c81  mov     eax, ebx
0x180012c83  jmp     short loc_180012C8A
0x180012c85  mov     eax, 57h ; 'W'
0x180012c8a  lea     r11, [rsp+80h+var_s0]
0x180012c92  mov     rbx, [r11+20h]
0x180012c96  mov     rsi, [r11+30h]
0x180012c9a  mov     rsp, r11
0x180012c9d  pop     r14
0x180012c9f  pop     rdi
0x180012ca0  pop     rbp
0x180012ca1  retn
```
