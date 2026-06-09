# cxl::SecurityDescriptor::GetObjectSecurity(wchar_t const *,_SE_OBJECT_TYPE,ulong,cxl::Sid *,cxl::Sid *,cxl::Acl *,cxl::Acl *)

- ea: `0x180015ccc`
- end: `0x180015e03`
- name: `?GetObjectSecurity@SecurityDescriptor@cxl@@QEAAXPEB_WW4_SE_OBJECT_TYPE@@KPEAVSid@2@2PEAVAcl@2@3@Z`
- size: `311`
- prototype: `void(cxl::SecurityDescriptor *__hidden this, const wchar_t *, enum _SE_OBJECT_TYPE, unsigned int, struct cxl::Sid *, struct cxl::Sid *, struct cxl::Acl *, struct cxl::Acl *)`
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180060bc4`
- `0x180060d40`
- `0x180061f58`
- `0x1800629d4`
- `0x180062d98`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x18000d600`
- `0x18000d6a4`
- `0x18000f0f4`
- `0x1800124ac`
- `0x180012b00`
- `0x180015ccc`
- `0x180015e0c`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180015d49`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180015d49`

## string_xrefs

- `0x180015dc3`: `GetSecurityInfo failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall cxl::SecurityDescriptor::GetObjectSecurity(
        cxl::SecurityDescriptor *this,
        const wchar_t *a2,
        __int64 a3,
        __int64 a4,
        struct cxl::Sid *a5,
        struct cxl::Sid *a6,
        struct cxl::Acl *a7)
{
  DWORD NamedSecurityInfoW; // ebx
  PSECURITY_DESCRIPTOR v10; // rbx
  struct cxl::Acl *v11; // r9
  PSID *ppsidGroup; // [rsp+20h] [rbp-E0h]
  PACL *ppDacl; // [rsp+28h] [rbp-D8h]
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v15[2]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v16[8]; // [rsp+50h] [rbp-B0h] BYREF
  PSECURITY_DESCRIPTOR v17; // [rsp+58h] [rbp-A8h]
  _BYTE v18[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v19[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+A0h] [rbp-60h] BYREF

  (*(void (__fastcall **)(cxl::SecurityDescriptor *, const wchar_t *, __int64))(*(_QWORD *)this + 8LL))(this, a2, a3);
  ppSecurityDescriptor = 0;
  v17 = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(a2, SE_FILE_OBJECT, 4u, 0, 0, 0, 0, &ppSecurityDescriptor);
  if ( NamedSecurityInfoW )
  {
    std::wstring::wstring(v19);
    cxl::StringWriter::StringWriter(v18, v19);
    cxl::TextWriter::Write<23>(v18, "GetSecurityInfo failed");
    v15[0] = NamedSecurityInfoW;
    v15[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v15, v19);
    throw (cxl::Exception *)pExceptionObject;
  }
  v10 = ppSecurityDescriptor;
  cxl::LocalHeapPtr<unsigned char>::Clear(v16);
  v17 = v10;
  cxl::SecurityDescriptor::MakeSecurityDescriptor(
    this,
    ppSecurityDescriptor,
    a7,
    v11,
    (struct cxl::Sid *)ppsidGroup,
    (struct cxl::Sid *)ppDacl);
  cxl::LocalHeapPtr<unsigned char>::Clear(v16);
}

```

## disassembly

```asm
0x180015ccc  mov     [rsp-8+arg_10], rbx
0x180015cd1  push    rbp
0x180015cd2  push    rsi
0x180015cd3  push    rdi
0x180015cd4  lea     rbp, [rsp-20h]
0x180015cd9  sub     rsp, 120h
0x180015ce0  mov     rax, cs:__security_cookie
0x180015ce7  xor     rax, rsp
0x180015cea  mov     [rbp+30h+var_20], rax
0x180015cee  mov     rbx, rdx
0x180015cf1  mov     rdi, rcx
0x180015cf4  mov     rsi, [rbp+30h+arg_30]
0x180015cf8  mov     rax, [rcx]
0x180015cfb  mov     rax, [rax+8]
0x180015cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d04  mov     [rsp+130h+var_F0], 0
0x180015d0d  mov     [rsp+130h+var_D8], 0
0x180015d16  lea     rax, [rsp+130h+var_F0]
0x180015d1b  mov     [rsp+130h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180015d20  mov     [rsp+130h+ppSacl], 0; ppSacl
0x180015d29  mov     [rsp+130h+ppDacl], 0; struct cxl::Sid *
0x180015d32  mov     [rsp+130h+ppsidGroup], 0; struct cxl::Sid *
0x180015d3b  xor     r9d, r9d; ppsidOwner
0x180015d3e  lea     edx, [r9+1]; ObjectType
0x180015d42  lea     r8d, [r9+4]; SecurityInfo
0x180015d46  mov     rcx, rbx; pObjectName
0x180015d49  call    cs:__imp_GetNamedSecurityInfoW
0x180015d50  nop     dword ptr [rax+rax+00h]
0x180015d55  mov     ebx, eax
0x180015d57  test    eax, eax
0x180015d59  jnz     short loc_180015DAA
0x180015d5b  mov     rbx, [rsp+130h+var_F0]
0x180015d60  lea     rcx, [rsp+130h+var_E0]
0x180015d65  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180015d6a  mov     [rsp+130h+var_D8], rbx
0x180015d6f  mov     r8, rsi; struct cxl::Acl *
0x180015d72  mov     rdx, [rsp+130h+var_F0]; void *
0x180015d77  mov     rcx, rdi; this
0x180015d7a  call    ?MakeSecurityDescriptor@SecurityDescriptor@cxl@@QEAAXPEAXPEAVAcl@2@1PEAVSid@2@2@Z; cxl::SecurityDescriptor::MakeSecurityDescriptor(void *,cxl::Acl *,cxl::Acl *,cxl::Sid *,cxl::Sid *)
0x180015d7f  nop
0x180015d80  lea     rcx, [rsp+130h+var_E0]
0x180015d85  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180015d8a  mov     rcx, [rbp+30h+var_20]
0x180015d8e  xor     rcx, rsp; StackCookie
0x180015d91  call    __security_check_cookie
0x180015d96  mov     rbx, [rsp+130h+arg_10]
0x180015d9e  add     rsp, 120h
0x180015da5  pop     rdi
0x180015da6  pop     rsi
0x180015da7  pop     rbp
0x180015da8  retn
0x180015daa  lea     rcx, [rbp+30h+var_B0]
0x180015dae  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180015db3  nop
0x180015db4  lea     rdx, [rbp+30h+var_B0]
0x180015db8  lea     rcx, [rsp+130h+var_D0]
0x180015dbd  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180015dc2  nop
0x180015dc3  lea     rdx, aGetsecurityinf_0; "GetSecurityInfo failed"
0x180015dca  lea     rcx, [rsp+130h+var_D0]
0x180015dcf  call    ??$Write@$0BH@@TextWriter@cxl@@QEAAAEAV01@AEAY0BH@$$CBD@Z; cxl::TextWriter::Write<23>(char const (&)[23])
0x180015dd4  mov     [rsp+130h+var_E8], ebx
0x180015dd8  mov     [rsp+130h+var_E4], 0
0x180015de0  lea     r8, [rbp+30h+var_B0]
0x180015de4  lea     rdx, [rsp+130h+var_E8]
0x180015de9  lea     rcx, [rbp+30h+pExceptionObject]
0x180015ded  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180015df2  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180015df9  lea     rcx, [rbp+30h+pExceptionObject]; pExceptionObject
0x180015dfd  call    _CxxThrowException_0
```
