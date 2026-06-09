# HMEHelpers::ModifyObjectPermissions

- ea: `0x180016b34`
- end: `0x180016cf9`
- name: `HMEHelpers::ModifyObjectPermissions`
- size: `453`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001699c`
- `0x180016b34`

## callees

- `0x180016b34`

## import_xrefs

- `ADVAPI32!ConvertStringSidToSidW` at `0x180016bfa`
- `ADVAPI32!ConvertStringSidToSidW` at `0x180016bfa`
- `ADVAPI32!SetEntriesInAclW` at `0x180016c52`
- `ADVAPI32!SetEntriesInAclW` at `0x180016c52`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180016cb0`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180016cb0`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x180016bc1`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x180016bc1`
- `KERNEL32!HeapFree` at `0x180016cdd`
- `KERNEL32!HeapFree` at `0x180016cdd`
- `KERNEL32!GetProcessHeap` at `0x180016ccf`
- `KERNEL32!GetProcessHeap` at `0x180016ccf`
- `KERNEL32!LocalFree` at `0x180016c71`
- `KERNEL32!LocalFree` at `0x180016c80`
- `KERNEL32!LocalFree` at `0x180016c71`
- `KERNEL32!LocalFree` at `0x180016c80`
- `KERNEL32!GetLastError` at `0x180016c04`
- `KERNEL32!GetLastError` at `0x180016c04`

## pseudocode

```c
__int64 __fastcall HMEHelpers::ModifyObjectPermissions(WCHAR *a1, __int64 a2, __int64 a3, __int64 a4, ACCESS_MODE a5)
{
  ACCESS_MODE v5; // r14d
  unsigned int v7; // edi
  signed int v8; // ebx
  signed int NamedSecurityInfoW; // eax
  signed int LastError; // eax
  signed int v11; // eax
  signed int v12; // eax
  PACL v13; // rbx
  HANDLE ProcessHeap; // rax
  PACL OldAcl; // [rsp+40h] [rbp-41h] BYREF
  PSID Sid; // [rsp+48h] [rbp-39h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+50h] [rbp-31h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+58h] [rbp-29h] BYREF
  PACL NewAcl; // [rsp+F0h] [rbp+6Fh] BYREF

  v5 = a5;
  NewAcl = 0;
  v7 = 1;
  if ( a5 == GRANT_ACCESS )
    HMEHelpers::ModifyObjectPermissions(
      (_DWORD)a1,
      4,
      (unsigned int)L"S-1-5-80-2375682873-768044350-3534595160-1005545032-2873800392",
      0x80000000,
      4);
  Sid = 0;
  hMem = 0;
  OldAcl = 0;
  v8 = 0;
  NewAcl = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(a1, SE_REGISTRY_KEY, 4u, 0, 0, &OldAcl, 0, &hMem);
  if ( NamedSecurityInfoW )
  {
    if ( NamedSecurityInfoW > 0 )
      v8 = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
    else
      v8 = NamedSecurityInfoW;
    goto LABEL_17;
  }
  if ( OldAcl )
  {
    if ( !ConvertStringSidToSidW(L"S-1-5-80-2375682873-768044350-3534595160-1005545032-2873800392", &Sid) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( v8 >= 0 )
    {
      pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)Sid;
      memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 28);
      pListOfExplicitEntries.grfAccessPermissions = 0x80000000;
      pListOfExplicitEntries.grfAccessMode = v5;
      pListOfExplicitEntries.grfInheritance = 3;
      v11 = SetEntriesInAclW(1u, &pListOfExplicitEntries, OldAcl, &NewAcl);
      if ( v11 )
      {
        if ( v11 > 0 )
          v8 = (unsigned __int16)v11 | 0x80070000;
        else
          v8 = v11;
      }
    }
LABEL_17:
    if ( hMem )
      LocalFree(hMem);
    if ( Sid )
      LocalFree(Sid);
    v7 = v8;
    if ( v8 < 0 )
      goto LABEL_27;
  }
  if ( !NewAcl )
    return v7;
  v12 = SetNamedSecurityInfoW(a1, SE_REGISTRY_KEY, 4u, 0, 0, NewAcl, 0);
  if ( v12 )
  {
    if ( v12 > 0 )
      v7 = (unsigned __int16)v12 | 0x80070000;
    else
      v7 = v12;
  }
LABEL_27:
  v13 = NewAcl;
  if ( NewAcl )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v13);
  }
  return v7;
}

```

## disassembly

```asm
0x180016b34  mov     [rsp-8+NewAcl], r8
0x180016b39  push    rbp
0x180016b3a  push    rbx
0x180016b3b  push    rsi
0x180016b3c  push    rdi
0x180016b3d  push    r12
0x180016b3f  push    r13
0x180016b41  push    r14
0x180016b43  push    r15
0x180016b45  lea     rbp, [rsp-17h]
0x180016b4a  sub     rsp, 98h
0x180016b51  mov     r14d, [rbp+4Fh+arg_20]
0x180016b55  xor     r15d, r15d
0x180016b58  mov     rsi, rcx
0x180016b5b  mov     [rbp+4Fh+NewAcl], r15
0x180016b5f  lea     edi, [r15+1]
0x180016b63  lea     r12d, [r15+4]
0x180016b67  cmp     r14d, edi
0x180016b6a  jnz     short loc_180016B86
0x180016b6c  mov     r9d, 80000000h
0x180016b72  mov     dword ptr [rsp+0D0h+ppsidGroup], r12d
0x180016b77  lea     r8, StringSid; "S-1-5-80-2375682873-768044350-353459516"...
0x180016b7e  mov     edx, r12d
0x180016b81  call    HMEHelpers__ModifyObjectPermissions
0x180016b86  lea     rax, [rbp+4Fh+hMem]
0x180016b8a  mov     [rbp+4Fh+Sid], r15
0x180016b8e  mov     [rsp+0D0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180016b93  xor     r9d, r9d; ppsidOwner
0x180016b96  lea     rax, [rbp+4Fh+OldAcl]
0x180016b9a  mov     [rsp+0D0h+ppSacl], r15; ppSacl
0x180016b9f  mov     [rsp+0D0h+ppDacl], rax; ppDacl
0x180016ba4  mov     r8d, r12d; SecurityInfo
0x180016ba7  mov     edx, r12d; ObjectType
0x180016baa  mov     [rsp+0D0h+ppsidGroup], r15; ppsidGroup
0x180016baf  mov     rcx, rsi; pObjectName
0x180016bb2  mov     [rbp+4Fh+hMem], r15
0x180016bb6  mov     [rbp+4Fh+OldAcl], r15
0x180016bba  mov     ebx, r15d
0x180016bbd  mov     [rbp+4Fh+NewAcl], r15
0x180016bc1  call    cs:__imp_GetNamedSecurityInfoW
0x180016bc7  mov     r13d, 80070000h
0x180016bcd  test    eax, eax
0x180016bcf  jz      short loc_180016BE5
0x180016bd1  jg      short loc_180016BD7
0x180016bd3  mov     ebx, eax
0x180016bd5  jmp     short loc_180016BDD
0x180016bd7  movzx   ebx, ax
0x180016bda  or      ebx, r13d
0x180016bdd  test    ebx, ebx
0x180016bdf  js      loc_180016C68
0x180016be5  cmp     [rbp+4Fh+OldAcl], r15
0x180016be9  jz      loc_180016C8C
0x180016bef  lea     rdx, [rbp+4Fh+Sid]; Sid
0x180016bf3  lea     rcx, StringSid; "S-1-5-80-2375682873-768044350-353459516"...
0x180016bfa  call    cs:__imp_ConvertStringSidToSidW
0x180016c00  test    eax, eax
0x180016c02  jnz     short loc_180016C16
0x180016c04  call    cs:__imp_GetLastError
0x180016c0a  mov     ebx, eax
0x180016c0c  test    eax, eax
0x180016c0e  jle     short loc_180016C16
0x180016c10  movzx   ebx, ax
0x180016c13  or      ebx, r13d
0x180016c16  test    ebx, ebx
0x180016c18  js      short loc_180016C68
0x180016c1a  mov     rax, [rbp+4Fh+Sid]
0x180016c1e  lea     r9, [rbp+4Fh+NewAcl]; NewAcl
0x180016c22  mov     r8, [rbp+4Fh+OldAcl]; OldAcl
0x180016c26  lea     rdx, [rbp+4Fh+pListOfExplicitEntries]; pListOfExplicitEntries
0x180016c2a  xorps   xmm0, xmm0
0x180016c2d  mov     [rbp+4Fh+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180016c31  mov     ecx, edi; cCountOfExplicitEntries
0x180016c33  mov     qword ptr [rbp+4Fh+pListOfExplicitEntries.Trustee.TrusteeType], r15
0x180016c37  movdqu  xmmword ptr [rbp+4Fh+pListOfExplicitEntries+0Ch], xmm0
0x180016c3c  mov     [rbp+4Fh+pListOfExplicitEntries.grfAccessPermissions], 80000000h
0x180016c43  mov     [rbp+4Fh+pListOfExplicitEntries.grfAccessMode], r14d
0x180016c47  mov     [rbp+4Fh+pListOfExplicitEntries.grfInheritance], 3
0x180016c4e  mov     [rbp+4Fh+pListOfExplicitEntries.Trustee.TrusteeForm], r15d
0x180016c52  call    cs:__imp_SetEntriesInAclW
0x180016c58  test    eax, eax
0x180016c5a  jz      short loc_180016C68
0x180016c5c  jg      short loc_180016C62
0x180016c5e  mov     ebx, eax
0x180016c60  jmp     short loc_180016C68
0x180016c62  movzx   ebx, ax
0x180016c65  or      ebx, r13d
0x180016c68  mov     rcx, [rbp+4Fh+hMem]; hMem
0x180016c6c  test    rcx, rcx
0x180016c6f  jz      short loc_180016C77
0x180016c71  call    cs:__imp_LocalFree
0x180016c77  mov     rcx, [rbp+4Fh+Sid]; hMem
0x180016c7b  test    rcx, rcx
0x180016c7e  jz      short loc_180016C86
0x180016c80  call    cs:__imp_LocalFree
0x180016c86  mov     edi, ebx
0x180016c88  test    ebx, ebx
0x180016c8a  js      short loc_180016CC6
0x180016c8c  mov     rax, [rbp+4Fh+NewAcl]
0x180016c90  test    rax, rax
0x180016c93  jz      short loc_180016CE3
0x180016c95  mov     [rsp+0D0h+ppSacl], r15; pSacl
0x180016c9a  xor     r9d, r9d; psidOwner
0x180016c9d  mov     [rsp+0D0h+ppDacl], rax; pDacl
0x180016ca2  mov     r8d, r12d; SecurityInfo
0x180016ca5  mov     edx, r12d; ObjectType
0x180016ca8  mov     [rsp+0D0h+ppsidGroup], r15; psidGroup
0x180016cad  mov     rcx, rsi; pObjectName
0x180016cb0  call    cs:__imp_SetNamedSecurityInfoW
0x180016cb6  test    eax, eax
0x180016cb8  jz      short loc_180016CC6
0x180016cba  jg      short loc_180016CC0
0x180016cbc  mov     edi, eax
0x180016cbe  jmp     short loc_180016CC6
0x180016cc0  movzx   edi, ax
0x180016cc3  or      edi, r13d
0x180016cc6  mov     rbx, [rbp+4Fh+NewAcl]
0x180016cca  test    rbx, rbx
0x180016ccd  jz      short loc_180016CE3
0x180016ccf  call    cs:__imp_GetProcessHeap
0x180016cd5  mov     r8, rbx; lpMem
0x180016cd8  xor     edx, edx; dwFlags
0x180016cda  mov     rcx, rax; hHeap
0x180016cdd  call    cs:__imp_HeapFree
0x180016ce3  mov     eax, edi
0x180016ce5  add     rsp, 98h
0x180016cec  pop     r15
0x180016cee  pop     r14
0x180016cf0  pop     r13
0x180016cf2  pop     r12
0x180016cf4  pop     rdi
0x180016cf5  pop     rsi
0x180016cf6  pop     rbx
0x180016cf7  pop     rbp
0x180016cf8  retn
```
