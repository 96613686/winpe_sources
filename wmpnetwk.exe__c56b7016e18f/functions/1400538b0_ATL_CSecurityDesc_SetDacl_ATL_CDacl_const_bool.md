# ATL::CSecurityDesc::SetDacl(ATL::CDacl const &,bool)

- ea: `0x1400538b0`
- end: `0x140053a77`
- name: `?SetDacl@CSecurityDesc@ATL@@QEAAXAEBVCDacl@2@_N@Z`
- size: `455`
- prototype: `void(ATL::CSecurityDesc *__hidden this, const struct ATL::CDacl *, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140051db0`

## callees

- `0x140038f58`
- `0x1400396dc`
- `0x140045f20`
- `0x14004bb5c`
- `0x14004ddd0`
- `0x14004f410`
- `0x1400538b0`
- `0x140054390`
- `0x14009e010`

## import_xrefs

- `ADVAPI32!GetAclInformation` at `0x1400539bc`
- `ADVAPI32!GetAclInformation` at `0x1400539bc`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x140053919`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x140053919`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140053a1d`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140053a1d`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140053946`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140053946`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14005395b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140053a31`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140053a44`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14005395b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140053a31`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140053a44`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14005392e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400539d5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14005392e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400539d5`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::SetDacl(void **this, const struct ATL::CDacl *a2)
{
  void *v4; // rcx
  BOOL v5; // ebp
  void *v6; // rax
  int Error; // ebx
  struct _ACL *PACL; // rax
  unsigned int v9; // eax
  unsigned int v10; // r14d
  ATL::Checked *v11; // rsi
  const struct _ACL *v12; // rax
  int v13; // ebx
  unsigned __int64 bDaclDefaulted; // [rsp+20h] [rbp-48h] BYREF
  PACL pDacl; // [rsp+28h] [rbp-40h] BYREF
  __int64 pAclInformation; // [rsp+30h] [rbp-38h] BYREF
  int v17; // [rsp+38h] [rbp-30h]

  if ( this[1] )
    ATL::CSecurityDesc::MakeAbsolute((ATL::CSecurityDesc *)this);
  v4 = this[1];
  v5 = 1;
  pDacl = 0;
  if ( v4 )
  {
    bDaclDefaulted = 0;
    if ( !GetSecurityDescriptorDacl(v4, (LPBOOL)&bDaclDefaulted + 1, &pDacl, (LPBOOL)&bDaclDefaulted) )
      ATL::AtlThrowLastWin32();
  }
  else
  {
    v6 = malloc(0x28u);
    this[1] = v6;
    if ( !v6 )
      goto LABEL_25;
    if ( !InitializeSecurityDescriptor(v6, 1u) )
    {
      Error = ATL::AtlHresultFromLastError();
      free(this[1]);
      this[1] = 0;
      ATL::AtlThrowImpl(Error);
    }
  }
  if ( *((_BYTE *)a2 + 16) || !(*(unsigned int (__fastcall **)(const struct ATL::CDacl *))(*(_QWORD *)a2 + 8LL))(a2) )
  {
    v11 = 0;
    goto LABEL_19;
  }
  PACL = (struct _ACL *)ATL::CAcl::GetPACL(a2);
  pAclInformation = 0;
  v17 = 0;
  if ( *((_BYTE *)a2 + 16) )
  {
    v9 = 0;
  }
  else
  {
    if ( !GetAclInformation(PACL, &pAclInformation, 0xCu, AclSizeInformation) )
      ATL::AtlThrowLastWin32();
    v9 = HIDWORD(pAclInformation);
  }
  v10 = v9;
  v11 = (ATL::Checked *)malloc(v9);
  if ( !v11 )
LABEL_25:
    ATL::AtlThrowImpl(-2147024882);
  v12 = ATL::CAcl::GetPACL(a2);
  ATL::Checked::memcpy_s(v11, (void *)v10, (unsigned __int64)v12, (const void *)v10, bDaclDefaulted);
LABEL_19:
  if ( !*((_BYTE *)a2 + 16) && !v11 )
    v5 = 0;
  if ( !SetSecurityDescriptorDacl(this[1], v5, (PACL)v11, 0) )
  {
    v13 = ATL::AtlHresultFromLastError();
    free(v11);
    ATL::AtlThrowImpl(v13);
  }
  free(pDacl);
}

```

## disassembly

```asm
0x1400538b0  mov     [rsp+arg_10], rbx
0x1400538b5  mov     [rsp+arg_18], rbp
0x1400538ba  push    rsi
0x1400538bb  push    rdi
0x1400538bc  push    r14
0x1400538be  sub     rsp, 50h
0x1400538c2  mov     rax, cs:__security_cookie
0x1400538c9  xor     rax, rsp
0x1400538cc  mov     [rsp+68h+var_28], rax
0x1400538d1  cmp     qword ptr [rcx+8], 0
0x1400538d6  mov     rbx, rdx
0x1400538d9  mov     rdi, rcx
0x1400538dc  jz      short loc_1400538E3
0x1400538de  call    ?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ; ATL::CSecurityDesc::MakeAbsolute(void)
0x1400538e3  mov     rcx, [rdi+8]; pSecurityDescriptor
0x1400538e7  mov     ebp, 1
0x1400538ec  mov     [rsp+68h+pDacl], 0
0x1400538f5  test    rcx, rcx
0x1400538f8  jz      short loc_140053929
0x1400538fa  lea     r9, [rsp+68h+bDaclDefaulted]; lpbDaclDefaulted
0x1400538ff  mov     [rsp+68h+bDaclDefaulted], 0; unsigned __int64
0x140053907  lea     r8, [rsp+68h+pDacl]; pDacl
0x14005390c  mov     [rsp+68h+bDaclPresent], 0
0x140053914  lea     rdx, [rsp+68h+bDaclPresent]; lpbDaclPresent
0x140053919  call    cs:__imp_GetSecurityDescriptorDacl
0x14005391f  test    eax, eax
0x140053921  jnz     short loc_140053971
0x140053923  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x140053929  mov     ecx, 28h ; '('; Size
0x14005392e  call    cs:__imp_malloc
0x140053934  mov     [rdi+8], rax
0x140053938  test    rax, rax
0x14005393b  jz      loc_140053A6C
0x140053941  mov     edx, ebp; dwRevision
0x140053943  mov     rcx, rax; pSecurityDescriptor
0x140053946  call    cs:__imp_InitializeSecurityDescriptor
0x14005394c  test    eax, eax
0x14005394e  jnz     short loc_140053971
0x140053950  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140053955  mov     rcx, [rdi+8]; Block
0x140053959  mov     ebx, eax
0x14005395b  call    cs:__imp_free
0x140053961  mov     ecx, ebx; int
0x140053963  mov     qword ptr [rdi+8], 0
0x14005396b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140053971  cmp     byte ptr [rbx+10h], 0
0x140053975  jnz     loc_140053A02
0x14005397b  mov     rax, [rbx]
0x14005397e  mov     rcx, rbx
0x140053981  mov     rax, [rax+8]
0x140053985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005398a  test    eax, eax
0x14005398c  jz      short loc_140053A02
0x14005398e  mov     rcx, rbx; this
0x140053991  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x140053996  xor     ecx, ecx
0x140053998  mov     [rsp+68h+pAclInformation], rcx
0x14005399d  mov     [rsp+68h+var_30], ecx
0x1400539a1  cmp     [rbx+10h], cl
0x1400539a4  jz      short loc_1400539AA
0x1400539a6  xor     eax, eax
0x1400539a8  jmp     short loc_1400539D0
0x1400539aa  mov     r9d, 2; dwAclInformationClass
0x1400539b0  lea     rdx, [rsp+68h+pAclInformation]; pAclInformation
0x1400539b5  mov     rcx, rax; pAcl
0x1400539b8  lea     r8d, [r9+0Ah]; nAclInformationLength
0x1400539bc  call    cs:__imp_GetAclInformation
0x1400539c2  test    eax, eax
0x1400539c4  jnz     short loc_1400539CC
0x1400539c6  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x1400539cc  mov     eax, dword ptr [rsp+68h+pAclInformation+4]
0x1400539d0  mov     ecx, eax; Size
0x1400539d2  mov     r14d, eax
0x1400539d5  call    cs:__imp_malloc
0x1400539db  mov     rsi, rax
0x1400539de  test    rax, rax
0x1400539e1  jz      loc_140053A6C
0x1400539e7  mov     rcx, rbx; this
0x1400539ea  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x1400539ef  mov     r8, rax; unsigned __int64
0x1400539f2  mov     r9d, r14d; void *
0x1400539f5  mov     edx, r14d; void *
0x1400539f8  mov     rcx, rsi; this
0x1400539fb  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x140053a00  jmp     short loc_140053A04
0x140053a02  xor     esi, esi
0x140053a04  cmp     byte ptr [rbx+10h], 0
0x140053a08  jnz     short loc_140053A11
0x140053a0a  test    rsi, rsi
0x140053a0d  jnz     short loc_140053A11
0x140053a0f  xor     ebp, ebp
0x140053a11  mov     rcx, [rdi+8]; pSecurityDescriptor
0x140053a15  xor     r9d, r9d; bDaclDefaulted
0x140053a18  mov     r8, rsi; pDacl
0x140053a1b  mov     edx, ebp; bDaclPresent
0x140053a1d  call    cs:__imp_SetSecurityDescriptorDacl
0x140053a23  test    eax, eax
0x140053a25  jnz     short loc_140053A3F
0x140053a27  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140053a2c  mov     rcx, rsi; Block
0x140053a2f  mov     ebx, eax
0x140053a31  call    cs:__imp_free
0x140053a37  mov     ecx, ebx; int
0x140053a39  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140053a3f  mov     rcx, [rsp+68h+pDacl]; Block
0x140053a44  call    cs:__imp_free
0x140053a4a  mov     rcx, [rsp+68h+var_28]
0x140053a4f  xor     rcx, rsp; StackCookie
0x140053a52  call    __security_check_cookie
0x140053a57  lea     r11, [rsp+68h+var_18]
0x140053a5c  mov     rbx, [r11+30h]
0x140053a60  mov     rbp, [r11+38h]
0x140053a64  mov     rsp, r11
0x140053a67  pop     r14
0x140053a69  pop     rdi
0x140053a6a  pop     rsi
0x140053a6b  retn
0x140053a6c  mov     ecx, 8007000Eh; int
0x140053a71  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
