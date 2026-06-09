# ATL::CSecurityDesc::SetDacl(ATL::CDacl const &,bool)

- ea: `0x180097dd4`
- end: `0x180097f4b`
- name: `?SetDacl@CSecurityDesc@ATL@@QEAAXAEBVCDacl@2@_N@Z`
- size: `375`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this, const struct ATL::CDacl *, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180097894`

## callees

- `0x180024a94`
- `0x18007c2f4`
- `0x18007c408`
- `0x18008b65c`
- `0x180097dd4`
- `0x1800a3b60`
- `0x1800e8f24`
- `0x1800e921c`
- `0x1800e962c`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180097f15`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180097f28`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180097f15`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180097f28`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180097ead`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180097ead`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180097e95`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180097e95`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180097f01`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180097f01`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180097e32`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180097e32`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::SetDacl(PSECURITY_DESCRIPTOR *this, const struct ATL::CDacl *a2)
{
  PSECURITY_DESCRIPTOR v4; // rcx
  struct _ACL *PACL; // rax
  unsigned int v6; // eax
  unsigned __int64 v7; // rbp
  ATL::Checked *v8; // rdi
  const struct _ACL *v9; // rax
  BOOL v10; // edx
  int Error; // ebx
  unsigned __int64 bDaclDefaulted; // [rsp+20h] [rbp-48h] BYREF
  PACL pDacl; // [rsp+28h] [rbp-40h] BYREF
  __int64 pAclInformation; // [rsp+30h] [rbp-38h] BYREF
  int v15; // [rsp+38h] [rbp-30h]

  if ( this[1] )
    ATL::CSecurityDesc::MakeAbsolute((ATL::CSecurityDesc *)this);
  v4 = this[1];
  pDacl = 0;
  if ( v4 )
  {
    bDaclDefaulted = 0;
    if ( !GetSecurityDescriptorDacl(v4, (LPBOOL)&bDaclDefaulted + 1, &pDacl, (LPBOOL)&bDaclDefaulted) )
      ATL::AtlThrowLastWin32();
  }
  else
  {
    ATL::CSecurityDesc::AllocateAndInitializeSecurityDescriptor((ATL::CSecurityDesc *)this);
  }
  if ( *((_BYTE *)a2 + 16) || !(*(unsigned int (__fastcall **)(const struct ATL::CDacl *))(*(_QWORD *)a2 + 8LL))(a2) )
  {
    v8 = 0;
  }
  else
  {
    PACL = (struct _ACL *)ATL::CAcl::GetPACL(a2);
    pAclInformation = 0;
    v15 = 0;
    if ( *((_BYTE *)a2 + 16) )
    {
      v6 = 0;
    }
    else
    {
      if ( !GetAclInformation(PACL, &pAclInformation, 0xCu, AclSizeInformation) )
        ATL::AtlThrowLastWin32();
      v6 = HIDWORD(pAclInformation);
    }
    v7 = v6;
    v8 = (ATL::Checked *)malloc(v6);
    if ( !v8 )
      ATL::AtlThrowImpl(-2147024882);
    v9 = ATL::CAcl::GetPACL(a2);
    ATL::Checked::memcpy_s(v8, (void *)v7, (unsigned __int64)v9, (const void *)v7, bDaclDefaulted);
  }
  v10 = *((_BYTE *)a2 + 16) || v8;
  if ( !SetSecurityDescriptorDacl(this[1], v10, (PACL)v8, 0) )
  {
    Error = ATL::AtlHresultFromLastError();
    free(v8);
    ATL::AtlThrowImpl(Error);
  }
  free(pDacl);
}

```

## disassembly

```asm
0x180097dd4  mov     [rsp+arg_10], rbx
0x180097dd9  push    rbp
0x180097dda  push    rsi
0x180097ddb  push    rdi
0x180097ddc  sub     rsp, 50h
0x180097de0  mov     rax, cs:__security_cookie
0x180097de7  xor     rax, rsp
0x180097dea  mov     [rsp+68h+var_28], rax
0x180097def  cmp     qword ptr [rcx+8], 0
0x180097df4  mov     rbx, rdx
0x180097df7  mov     rsi, rcx
0x180097dfa  jz      short loc_180097E01
0x180097dfc  call    ?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ; ATL::CSecurityDesc::MakeAbsolute(void)
0x180097e01  mov     rcx, [rsi+8]; pSecurityDescriptor
0x180097e05  mov     [rsp+68h+pDacl], 0
0x180097e0e  test    rcx, rcx
0x180097e11  jz      short loc_180097E42
0x180097e13  lea     r9, [rsp+68h+bDaclDefaulted]; lpbDaclDefaulted
0x180097e18  mov     [rsp+68h+bDaclDefaulted], 0
0x180097e20  lea     r8, [rsp+68h+pDacl]; pDacl
0x180097e25  mov     [rsp+68h+bDaclPresent], 0
0x180097e2d  lea     rdx, [rsp+68h+bDaclPresent]; lpbDaclPresent
0x180097e32  call    cs:__imp_GetSecurityDescriptorDacl
0x180097e38  test    eax, eax
0x180097e3a  jnz     short loc_180097E4A
0x180097e3c  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180097e42  mov     rcx, rsi; this
0x180097e45  call    ?AllocateAndInitializeSecurityDescriptor@CSecurityDesc@ATL@@IEAAXXZ; ATL::CSecurityDesc::AllocateAndInitializeSecurityDescriptor(void)
0x180097e4a  cmp     byte ptr [rbx+10h], 0
0x180097e4e  jnz     loc_180097EE1
0x180097e54  mov     rax, [rbx]
0x180097e57  mov     rcx, rbx
0x180097e5a  mov     rax, [rax+8]
0x180097e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097e63  test    eax, eax
0x180097e65  jz      short loc_180097EE1
0x180097e67  mov     rcx, rbx; this
0x180097e6a  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x180097e6f  xor     ecx, ecx
0x180097e71  mov     [rsp+68h+pAclInformation], rcx
0x180097e76  mov     [rsp+68h+var_30], ecx
0x180097e7a  cmp     [rbx+10h], cl
0x180097e7d  jz      short loc_180097E83
0x180097e7f  xor     eax, eax
0x180097e81  jmp     short loc_180097EA9
0x180097e83  mov     r9d, 2; dwAclInformationClass
0x180097e89  lea     rdx, [rsp+68h+pAclInformation]; pAclInformation
0x180097e8e  mov     rcx, rax; pAcl
0x180097e91  lea     r8d, [r9+0Ah]; nAclInformationLength
0x180097e95  call    cs:__imp_GetAclInformation
0x180097e9b  test    eax, eax
0x180097e9d  jnz     short loc_180097EA5
0x180097e9f  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180097ea5  mov     eax, dword ptr [rsp+68h+pAclInformation+4]
0x180097ea9  mov     ecx, eax; Size
0x180097eab  mov     ebp, eax
0x180097ead  call    cs:__imp_malloc
0x180097eb3  mov     rdi, rax
0x180097eb6  test    rax, rax
0x180097eb9  jnz     short loc_180097EC6
0x180097ebb  mov     ecx, 8007000Eh; int
0x180097ec0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180097ec6  mov     rcx, rbx; this
0x180097ec9  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x180097ece  mov     r8, rax; unsigned __int64
0x180097ed1  mov     r9, rbp; void *
0x180097ed4  mov     rdx, rbp; void *
0x180097ed7  mov     rcx, rdi; this
0x180097eda  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x180097edf  jmp     short loc_180097EE3
0x180097ee1  xor     edi, edi
0x180097ee3  cmp     byte ptr [rbx+10h], 0
0x180097ee7  jnz     short loc_180097EF2
0x180097ee9  test    rdi, rdi
0x180097eec  jnz     short loc_180097EF2
0x180097eee  xor     edx, edx
0x180097ef0  jmp     short loc_180097EF7
0x180097ef2  mov     edx, 1; bDaclPresent
0x180097ef7  mov     rcx, [rsi+8]; pSecurityDescriptor
0x180097efb  xor     r9d, r9d; bDaclDefaulted
0x180097efe  mov     r8, rdi; pDacl
0x180097f01  call    cs:__imp_SetSecurityDescriptorDacl
0x180097f07  test    eax, eax
0x180097f09  jnz     short loc_180097F23
0x180097f0b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180097f10  mov     rcx, rdi; Block
0x180097f13  mov     ebx, eax
0x180097f15  call    cs:__imp_free
0x180097f1b  mov     ecx, ebx; int
0x180097f1d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180097f23  mov     rcx, [rsp+68h+pDacl]; Block
0x180097f28  call    cs:__imp_free
0x180097f2e  mov     rcx, [rsp+68h+var_28]
0x180097f33  xor     rcx, rsp; StackCookie
0x180097f36  call    __security_check_cookie
0x180097f3b  mov     rbx, [rsp+68h+arg_10]
0x180097f43  add     rsp, 50h
0x180097f47  pop     rdi
0x180097f48  pop     rsi
0x180097f49  pop     rbp
0x180097f4a  retn
```
