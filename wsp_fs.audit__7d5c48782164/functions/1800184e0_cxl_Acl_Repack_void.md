# cxl::Acl::Repack(void)

- ea: `0x1800184e0`
- end: `0x1800185f8`
- name: `?Repack@Acl@cxl@@AEAAXXZ`
- size: `280`
- prototype: `void __fastcall(cxl::Acl *__hidden this)`
- caller_count: `3`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017f00`
- `0x180018658`
- `0x180018938`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x18000d600`
- `0x18000d6a4`
- `0x18000f094`
- `0x1800124ac`
- `0x180012b00`
- `0x180015ae4`
- `0x180015b44`
- `0x180017de4`
- `0x1800180e4`
- `0x18001836c`
- `0x1800184e0`
- `0x180018c20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185bd`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180018533`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180018533`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall cxl::Acl::Repack(PACL *this)
{
  DWORD AclRevision; // edi
  DWORD AclUsedBytes; // ebx
  unsigned int v4; // edx
  struct _ACL *v5; // rsi
  _DWORD v6[2]; // [rsp+20h] [rbp-99h] BYREF
  _BYTE v7[8]; // [rsp+28h] [rbp-91h] BYREF
  struct _ACL *v8; // [rsp+30h] [rbp-89h]
  _BYTE v9[32]; // [rsp+38h] [rbp-81h] BYREF
  _BYTE v10[40]; // [rsp+58h] [rbp-61h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+80h] [rbp-39h] BYREF

  AclRevision = cxl::AclBase::GetAclRevision(this);
  AclUsedBytes = cxl::AclBase::GetAclUsedBytes((cxl::AclBase *)this);
  v5 = (struct _ACL *)cxl::LocalHeap::Alloc(AclUsedBytes, v4);
  v8 = v5;
  if ( !InitializeAcl(v5, AclUsedBytes, AclRevision) )
  {
    std::wstring::wstring(v10);
    cxl::StringWriter::StringWriter(v9, v10);
    cxl::TextWriter::Write<21>(v9);
    v6[0] = GetLastError();
    v6[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v6, v10);
    throw (cxl::Exception *)pExceptionObject;
  }
  cxl::AclBase::CopyAclTo((cxl::AclBase *)this, v5);
  cxl::AclBase::VerifyAcl(v5);
  v8 = 0;
  cxl::Acl::Attach((cxl::Acl *)this, v5);
  cxl::LocalHeapPtr<unsigned char>::Clear(v7);
}

```

## disassembly

```asm
0x1800184e0  mov     [rsp-8+arg_8], rbx
0x1800184e5  mov     [rsp-8+arg_10], rsi
0x1800184ea  push    rbp
0x1800184eb  push    rdi
0x1800184ec  push    r14
0x1800184ee  lea     rbp, [rsp-47h]
0x1800184f3  sub     rsp, 100h
0x1800184fa  mov     rax, cs:__security_cookie
0x180018501  xor     rax, rsp
0x180018504  mov     [rbp+57h+var_20], rax
0x180018508  mov     r14, rcx
0x18001850b  call    ?GetAclRevision@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclRevision(void)
0x180018510  mov     edi, eax
0x180018512  mov     rcx, r14; this
0x180018515  call    ?GetAclUsedBytes@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclUsedBytes(void)
0x18001851a  mov     ebx, eax
0x18001851c  mov     ecx, eax; uBytes
0x18001851e  call    ?Alloc@LocalHeap@cxl@@SAPEAX_KK@Z; cxl::LocalHeap::Alloc(unsigned __int64,ulong)
0x180018523  mov     rsi, rax
0x180018526  mov     [rsp+110h+var_E0], rax
0x18001852b  mov     r8d, edi; dwAclRevision
0x18001852e  mov     edx, ebx; nAclLength
0x180018530  mov     rcx, rax; pAcl
0x180018533  call    cs:__imp_InitializeAcl
0x18001853a  nop     dword ptr [rax+rax+00h]
0x18001853f  test    eax, eax
0x180018541  jz      short loc_18001859A
0x180018543  mov     rdx, rsi; pAcl
0x180018546  mov     rcx, r14; this
0x180018549  call    ?CopyAclTo@AclBase@cxl@@QEAAXPEAU_ACL@@@Z; cxl::AclBase::CopyAclTo(_ACL *)
0x18001854e  mov     rcx, rsi; struct _ACL *
0x180018551  call    ?VerifyAcl@AclBase@cxl@@KAXPEBU_ACL@@@Z; cxl::AclBase::VerifyAcl(_ACL const *)
0x180018556  mov     [rsp+110h+var_E0], 0
0x18001855f  mov     rdx, rsi; struct _ACL *
0x180018562  mov     rcx, r14; this
0x180018565  call    ?Attach@Acl@cxl@@QEAAXPEAU_ACL@@@Z; cxl::Acl::Attach(_ACL *)
0x18001856a  nop
0x18001856b  lea     rcx, [rsp+110h+var_E8]
0x180018570  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180018575  mov     rcx, [rbp+57h+var_20]
0x180018579  xor     rcx, rsp; StackCookie
0x18001857c  call    __security_check_cookie
0x180018581  lea     r11, [rsp+110h+var_10]
0x180018589  mov     rbx, [r11+28h]
0x18001858d  mov     rsi, [r11+30h]
0x180018591  mov     rsp, r11
0x180018594  pop     r14
0x180018596  pop     rdi
0x180018597  pop     rbp
0x180018598  retn
0x18001859a  lea     rcx, [rbp+57h+var_B8]
0x18001859e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800185a3  nop
0x1800185a4  lea     rdx, [rbp+57h+var_B8]
0x1800185a8  lea     rcx, [rsp+110h+var_D8]
0x1800185ad  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x1800185b2  nop
0x1800185b3  lea     rcx, [rsp+110h+var_D8]
0x1800185b8  call    ??$Write@$0BF@@TextWriter@cxl@@QEAAAEAV01@AEAY0BF@$$CBD@Z; cxl::TextWriter::Write<21>(char const (&)[21])
0x1800185bd  call    cs:__imp_GetLastError
0x1800185c4  nop     dword ptr [rax+rax+00h]
0x1800185c9  mov     [rsp+110h+var_F0], eax
0x1800185cd  mov     [rsp+110h+var_EC], 0
0x1800185d5  lea     r8, [rbp+57h+var_B8]
0x1800185d9  lea     rdx, [rsp+110h+var_F0]
0x1800185de  lea     rcx, [rbp+57h+pExceptionObject]
0x1800185e2  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800185e7  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800185ee  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800185f2  call    _CxxThrowException_0
```
