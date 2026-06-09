# BuildSystemAndAdminSecurityAttributes(_SECURITY_DESCRIPTOR *,_SECURITY_ATTRIBUTES *)

- ea: `0x14000a750`
- end: `0x14000a8d1`
- name: `?BuildSystemAndAdminSecurityAttributes@@YAHPEAU_SECURITY_DESCRIPTOR@@PEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `385`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14000ff24`

## callees

- `0x140003611`
- `0x14000a750`

## import_xrefs

- `ADVAPI32!InitializeSecurityDescriptor` at `0x14000a84e`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x14000a84e`
- `ADVAPI32!CreateWellKnownSid` at `0x14000a7c1`
- `ADVAPI32!CreateWellKnownSid` at `0x14000a7df`
- `ADVAPI32!CreateWellKnownSid` at `0x14000a7c1`
- `ADVAPI32!CreateWellKnownSid` at `0x14000a7df`
- `ADVAPI32!SetEntriesInAclW` at `0x14000a83a`
- `ADVAPI32!SetEntriesInAclW` at `0x14000a83a`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14000a865`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14000a865`
- `KERNEL32!LocalFree` at `0x14000a891`
- `KERNEL32!LocalFree` at `0x14000a89f`
- `KERNEL32!LocalFree` at `0x14000a8ad`
- `KERNEL32!LocalFree` at `0x14000a891`
- `KERNEL32!LocalFree` at `0x14000a89f`
- `KERNEL32!LocalFree` at `0x14000a8ad`
- `KERNEL32!LocalAlloc` at `0x14000a788`
- `KERNEL32!LocalAlloc` at `0x14000a796`
- `KERNEL32!LocalAlloc` at `0x14000a788`
- `KERNEL32!LocalAlloc` at `0x14000a796`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BuildSystemAndAdminSecurityAttributes(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        struct _SECURITY_ATTRIBUTES *a2)
{
  unsigned int v4; // esi
  WCHAR *v5; // rdi
  HLOCAL v6; // rax
  void *v7; // rbx
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+20h] [rbp-60h] BYREF
  int v10; // [rsp+50h] [rbp-30h]
  __int64 v11; // [rsp+54h] [rbp-2Ch]
  int v12; // [rsp+6Ch] [rbp-14h]
  int v13; // [rsp+70h] [rbp-10h]
  void *v14; // [rsp+78h] [rbp-8h]
  DWORD cbSid; // [rsp+C0h] [rbp+40h] BYREF
  PACL NewAcl; // [rsp+C8h] [rbp+48h] BYREF

  NewAcl = 0;
  v4 = 53;
  v5 = (WCHAR *)LocalAlloc(0, 0x44u);
  v6 = LocalAlloc(0, 0x44u);
  v7 = v6;
  if ( v5 )
  {
    if ( v6 )
    {
      cbSid = 68;
      if ( CreateWellKnownSid(WinLocalSystemSid, 0, v5, &cbSid) )
      {
        cbSid = 68;
        if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v7, &cbSid) )
        {
          memset_0(&pListOfExplicitEntries, 0, 0x60u);
          pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
          pListOfExplicitEntries.grfAccessPermissions = -1;
          v10 = -1;
          *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
          pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
          pListOfExplicitEntries.Trustee.ptstrName = v5;
          v11 = 2;
          v12 = 0;
          v13 = 5;
          v14 = v7;
          if ( !SetEntriesInAclW(2u, &pListOfExplicitEntries, 0, &NewAcl)
            && InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
            && SetSecurityDescriptorDacl(pSecurityDescriptor, 1, NewAcl, 0) )
          {
            a2->nLength = 24;
            v4 = 0;
            a2->lpSecurityDescriptor = pSecurityDescriptor;
            a2->bInheritHandle = 0;
          }
        }
      }
    }
  }
  if ( NewAcl && v4 )
    LocalFree(NewAcl);
  if ( v5 )
    LocalFree(v5);
  if ( v7 )
    LocalFree(v7);
  return v4;
}

```

## disassembly

```asm
0x14000a750  mov     [rsp-28h+arg_0], rbx
0x14000a755  mov     [rsp-28h+arg_8], rsi
0x14000a75a  push    rbp
0x14000a75b  push    rdi
0x14000a75c  push    r13
0x14000a75e  push    r14
0x14000a760  push    r15
0x14000a762  mov     rbp, rsp
0x14000a765  sub     rsp, 80h
0x14000a76c  mov     r14, rdx
0x14000a76f  mov     [rbp+NewAcl], 0
0x14000a777  mov     r15, rcx
0x14000a77a  mov     esi, 35h ; '5'
0x14000a77f  xor     ecx, ecx; uFlags
0x14000a781  lea     r13d, [rsi+0Fh]
0x14000a785  mov     edx, r13d; uBytes
0x14000a788  call    cs:__imp_LocalAlloc
0x14000a78e  mov     edx, r13d; uBytes
0x14000a791  xor     ecx, ecx; uFlags
0x14000a793  mov     rdi, rax
0x14000a796  call    cs:__imp_LocalAlloc
0x14000a79c  mov     rbx, rax
0x14000a79f  test    rdi, rdi
0x14000a7a2  jz      loc_14000A884
0x14000a7a8  test    rax, rax
0x14000a7ab  jz      loc_14000A884
0x14000a7b1  lea     r9, [rbp+cbSid]; cbSid
0x14000a7b5  mov     [rbp+cbSid], r13d
0x14000a7b9  mov     r8, rdi; pSid
0x14000a7bc  lea     ecx, [rsi-1Fh]; WellKnownSidType
0x14000a7bf  xor     edx, edx; DomainSid
0x14000a7c1  call    cs:__imp_CreateWellKnownSid
0x14000a7c7  test    eax, eax
0x14000a7c9  jz      loc_14000A884
0x14000a7cf  lea     r9, [rbp+cbSid]; cbSid
0x14000a7d3  mov     [rbp+cbSid], r13d
0x14000a7d7  mov     r8, rbx; pSid
0x14000a7da  lea     ecx, [rsi-1Bh]; WellKnownSidType
0x14000a7dd  xor     edx, edx; DomainSid
0x14000a7df  call    cs:__imp_CreateWellKnownSid
0x14000a7e5  test    eax, eax
0x14000a7e7  jz      loc_14000A884
0x14000a7ed  xor     edx, edx; Val
0x14000a7ef  lea     r8d, [rsi+2Bh]; Size
0x14000a7f3  lea     rcx, [rbp+pListOfExplicitEntries]; void *
0x14000a7f7  call    memset_0
0x14000a7fc  or      edx, 0FFFFFFFFh
0x14000a7ff  mov     [rbp+pListOfExplicitEntries.Trustee.TrusteeForm], 0
0x14000a806  lea     ecx, [rsi-33h]; cCountOfExplicitEntries
0x14000a809  mov     [rbp+pListOfExplicitEntries.grfAccessPermissions], edx
0x14000a80c  lea     eax, [rsi-30h]
0x14000a80f  mov     [rbp+var_30], edx
0x14000a812  lea     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x14000a816  mov     qword ptr [rbp+pListOfExplicitEntries.grfAccessMode], rcx
0x14000a81a  lea     r9, [rbp+NewAcl]; NewAcl
0x14000a81e  mov     [rbp+pListOfExplicitEntries.Trustee.TrusteeType], eax
0x14000a821  xor     r8d, r8d; OldAcl
0x14000a824  mov     [rbp+pListOfExplicitEntries.Trustee.ptstrName], rdi
0x14000a828  mov     [rbp+var_2C], rcx
0x14000a82c  mov     [rbp+var_14], 0
0x14000a833  mov     [rbp+var_10], eax
0x14000a836  mov     [rbp+var_8], rbx
0x14000a83a  call    cs:__imp_SetEntriesInAclW
0x14000a840  test    eax, eax
0x14000a842  jnz     short loc_14000A884
0x14000a844  lea     r13d, [rsi-34h]
0x14000a848  mov     rcx, r15; pSecurityDescriptor
0x14000a84b  mov     edx, r13d; dwRevision
0x14000a84e  call    cs:__imp_InitializeSecurityDescriptor
0x14000a854  test    eax, eax
0x14000a856  jz      short loc_14000A884
0x14000a858  mov     r8, [rbp+NewAcl]; pDacl
0x14000a85c  xor     r9d, r9d; bDaclDefaulted
0x14000a85f  mov     edx, r13d; bDaclPresent
0x14000a862  mov     rcx, r15; pSecurityDescriptor
0x14000a865  call    cs:__imp_SetSecurityDescriptorDacl
0x14000a86b  test    eax, eax
0x14000a86d  jz      short loc_14000A884
0x14000a86f  mov     dword ptr [r14], 18h
0x14000a876  xor     esi, esi
0x14000a878  mov     [r14+8], r15
0x14000a87c  mov     dword ptr [r14+10h], 0
0x14000a884  mov     rcx, [rbp+NewAcl]; hMem
0x14000a888  test    rcx, rcx
0x14000a88b  jz      short loc_14000A897
0x14000a88d  test    esi, esi
0x14000a88f  jz      short loc_14000A897
0x14000a891  call    cs:__imp_LocalFree
0x14000a897  test    rdi, rdi
0x14000a89a  jz      short loc_14000A8A5
0x14000a89c  mov     rcx, rdi; hMem
0x14000a89f  call    cs:__imp_LocalFree
0x14000a8a5  test    rbx, rbx
0x14000a8a8  jz      short loc_14000A8B3
0x14000a8aa  mov     rcx, rbx; hMem
0x14000a8ad  call    cs:__imp_LocalFree
0x14000a8b3  lea     r11, [rsp+80h+var_s0]
0x14000a8bb  mov     eax, esi
0x14000a8bd  mov     rbx, [r11+30h]
0x14000a8c1  mov     rsi, [r11+38h]
0x14000a8c5  mov     rsp, r11
0x14000a8c8  pop     r15
0x14000a8ca  pop     r14
0x14000a8cc  pop     r13
0x14000a8ce  pop     rdi
0x14000a8cf  pop     rbp
0x14000a8d0  retn
```
