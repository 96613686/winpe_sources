# cxl::SecurityDescriptor::GetObjectSecurity(wchar_t const *,_SE_OBJECT_TYPE,ulong,cxl::Sid *,cxl::Sid *,cxl::Acl *,cxl::Acl *)

- ea: `0x1800155b4`
- end: `0x1800156e4`
- name: `?GetObjectSecurity@SecurityDescriptor@cxl@@QEAAXPEB_WW4_SE_OBJECT_TYPE@@KPEAVSid@2@2PEAVAcl@2@3@Z`
- size: `304`
- prototype: `void(cxl::SecurityDescriptor *__hidden this, const wchar_t *, enum _SE_OBJECT_TYPE, unsigned int, struct cxl::Sid *, struct cxl::Sid *, struct cxl::Acl *, struct cxl::Acl *)`
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005f9a4`
- `0x18005fb10`
- `0x180060d28`
- `0x180061784`
- `0x180061b48`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x18000d298`
- `0x18000d33c`
- `0x18000ecb4`
- `0x180012028`
- `0x180012660`
- `0x1800155b4`
- `0x1800156ec`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180015631`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180015631`

## string_xrefs

- `0x1800156a4`: `GetSecurityInfo failed`

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
    cxl::TextWriter::Write<23>((__int64)v18, (__int64)"GetSecurityInfo failed");
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
0x1800155b4  mov     [rsp-8+arg_10], rbx
0x1800155b9  push    rbp
0x1800155ba  push    rsi
0x1800155bb  push    rdi
0x1800155bc  lea     rbp, [rsp-20h]
0x1800155c1  sub     rsp, 120h
0x1800155c8  mov     rax, cs:__security_cookie
0x1800155cf  xor     rax, rsp
0x1800155d2  mov     [rbp+30h+var_20], rax
0x1800155d6  mov     rbx, rdx
0x1800155d9  mov     rdi, rcx
0x1800155dc  mov     rsi, [rbp+30h+arg_30]
0x1800155e0  mov     rax, [rcx]
0x1800155e3  mov     rax, [rax+8]
0x1800155e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155ec  mov     [rsp+130h+var_F0], 0
0x1800155f5  mov     [rsp+130h+var_D8], 0
0x1800155fe  lea     rax, [rsp+130h+var_F0]
0x180015603  mov     [rsp+130h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180015608  mov     [rsp+130h+ppSacl], 0; ppSacl
0x180015611  mov     [rsp+130h+ppDacl], 0; struct cxl::Sid *
0x18001561a  mov     [rsp+130h+ppsidGroup], 0; struct cxl::Sid *
0x180015623  xor     r9d, r9d; ppsidOwner
0x180015626  lea     edx, [r9+1]; ObjectType
0x18001562a  lea     r8d, [r9+4]; SecurityInfo
0x18001562e  mov     rcx, rbx; pObjectName
0x180015631  call    cs:__imp_GetNamedSecurityInfoW
0x180015637  mov     ebx, eax
0x180015639  test    eax, eax
0x18001563b  jnz     short loc_18001568B
0x18001563d  mov     rbx, [rsp+130h+var_F0]
0x180015642  lea     rcx, [rsp+130h+var_E0]
0x180015647  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x18001564c  mov     [rsp+130h+var_D8], rbx
0x180015651  mov     r8, rsi; struct cxl::Acl *
0x180015654  mov     rdx, [rsp+130h+var_F0]; void *
0x180015659  mov     rcx, rdi; this
0x18001565c  call    ?MakeSecurityDescriptor@SecurityDescriptor@cxl@@QEAAXPEAXPEAVAcl@2@1PEAVSid@2@2@Z; cxl::SecurityDescriptor::MakeSecurityDescriptor(void *,cxl::Acl *,cxl::Acl *,cxl::Sid *,cxl::Sid *)
0x180015661  nop
0x180015662  lea     rcx, [rsp+130h+var_E0]
0x180015667  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x18001566c  mov     rcx, [rbp+30h+var_20]
0x180015670  xor     rcx, rsp; StackCookie
0x180015673  call    __security_check_cookie
0x180015678  mov     rbx, [rsp+130h+arg_10]
0x180015680  add     rsp, 120h
0x180015687  pop     rdi
0x180015688  pop     rsi
0x180015689  pop     rbp
0x18001568a  retn
0x18001568b  lea     rcx, [rbp+30h+var_B0]
0x18001568f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180015694  nop
0x180015695  lea     rdx, [rbp+30h+var_B0]
0x180015699  lea     rcx, [rsp+130h+var_D0]
0x18001569e  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x1800156a3  nop
0x1800156a4  lea     rdx, aGetsecurityinf_0; "GetSecurityInfo failed"
0x1800156ab  lea     rcx, [rsp+130h+var_D0]
0x1800156b0  call    ??$Write@$0BH@@TextWriter@cxl@@QEAAAEAV01@AEAY0BH@$$CBD@Z; cxl::TextWriter::Write<23>(char const (&)[23])
0x1800156b5  mov     [rsp+130h+var_E8], ebx
0x1800156b9  mov     [rsp+130h+var_E4], 0
0x1800156c1  lea     r8, [rbp+30h+var_B0]
0x1800156c5  lea     rdx, [rsp+130h+var_E8]
0x1800156ca  lea     rcx, [rbp+30h+pExceptionObject]
0x1800156ce  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800156d3  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800156da  lea     rcx, [rbp+30h+pExceptionObject]; pExceptionObject
0x1800156de  call    _CxxThrowException_0
```
