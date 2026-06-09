# cxl::Acl::Repack(void)

- ea: `0x180017ce0`
- end: `0x180017deb`
- name: `?Repack@Acl@cxl@@AEAAXXZ`
- size: `267`
- prototype: `void __fastcall(cxl::Acl *__hidden this)`
- caller_count: `3`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017740`
- `0x180017e4c`
- `0x1800180fc`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x18000d298`
- `0x18000d33c`
- `0x18000ec54`
- `0x180012028`
- `0x180012660`
- `0x1800153e4`
- `0x180015440`
- `0x180017630`
- `0x180017904`
- `0x180017b70`
- `0x180017ce0`
- `0x1800183b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017db6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017db6`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180017d33`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180017d33`

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
    cxl::TextWriter::Write<21>((__int64)v9);
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
0x180017ce0  mov     [rsp-8+arg_8], rbx
0x180017ce5  mov     [rsp-8+arg_10], rsi
0x180017cea  push    rbp
0x180017ceb  push    rdi
0x180017cec  push    r14
0x180017cee  lea     rbp, [rsp-47h]
0x180017cf3  sub     rsp, 100h
0x180017cfa  mov     rax, cs:__security_cookie
0x180017d01  xor     rax, rsp
0x180017d04  mov     [rbp+57h+var_20], rax
0x180017d08  mov     r14, rcx
0x180017d0b  call    ?GetAclRevision@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclRevision(void)
0x180017d10  mov     edi, eax
0x180017d12  mov     rcx, r14; this
0x180017d15  call    ?GetAclUsedBytes@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclUsedBytes(void)
0x180017d1a  mov     ebx, eax
0x180017d1c  mov     ecx, eax; uBytes
0x180017d1e  call    ?Alloc@LocalHeap@cxl@@SAPEAX_KK@Z; cxl::LocalHeap::Alloc(unsigned __int64,ulong)
0x180017d23  mov     rsi, rax
0x180017d26  mov     [rsp+110h+var_E0], rax
0x180017d2b  mov     r8d, edi; dwAclRevision
0x180017d2e  mov     edx, ebx; nAclLength
0x180017d30  mov     rcx, rax; pAcl
0x180017d33  call    cs:__imp_InitializeAcl
0x180017d39  test    eax, eax
0x180017d3b  jz      short loc_180017D93
0x180017d3d  mov     rdx, rsi; pAcl
0x180017d40  mov     rcx, r14; this
0x180017d43  call    ?CopyAclTo@AclBase@cxl@@QEAAXPEAU_ACL@@@Z; cxl::AclBase::CopyAclTo(_ACL *)
0x180017d48  mov     rcx, rsi; struct _ACL *
0x180017d4b  call    ?VerifyAcl@AclBase@cxl@@KAXPEBU_ACL@@@Z; cxl::AclBase::VerifyAcl(_ACL const *)
0x180017d50  mov     [rsp+110h+var_E0], 0
0x180017d59  mov     rdx, rsi; struct _ACL *
0x180017d5c  mov     rcx, r14; this
0x180017d5f  call    ?Attach@Acl@cxl@@QEAAXPEAU_ACL@@@Z; cxl::Acl::Attach(_ACL *)
0x180017d64  nop
0x180017d65  lea     rcx, [rsp+110h+var_E8]
0x180017d6a  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180017d6f  mov     rcx, [rbp+57h+var_20]
0x180017d73  xor     rcx, rsp; StackCookie
0x180017d76  call    __security_check_cookie
0x180017d7b  lea     r11, [rsp+110h+var_10]
0x180017d83  mov     rbx, [r11+28h]
0x180017d87  mov     rsi, [r11+30h]
0x180017d8b  mov     rsp, r11
0x180017d8e  pop     r14
0x180017d90  pop     rdi
0x180017d91  pop     rbp
0x180017d92  retn
0x180017d93  lea     rcx, [rbp+57h+var_B8]
0x180017d97  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180017d9c  nop
0x180017d9d  lea     rdx, [rbp+57h+var_B8]
0x180017da1  lea     rcx, [rsp+110h+var_D8]
0x180017da6  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180017dab  nop
0x180017dac  lea     rcx, [rsp+110h+var_D8]
0x180017db1  call    ??$Write@$0BF@@TextWriter@cxl@@QEAAAEAV01@AEAY0BF@$$CBD@Z; cxl::TextWriter::Write<21>(char const (&)[21])
0x180017db6  call    cs:__imp_GetLastError
0x180017dbc  mov     [rsp+110h+var_F0], eax
0x180017dc0  mov     [rsp+110h+var_EC], 0
0x180017dc8  lea     r8, [rbp+57h+var_B8]
0x180017dcc  lea     rdx, [rsp+110h+var_F0]
0x180017dd1  lea     rcx, [rbp+57h+pExceptionObject]
0x180017dd5  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180017dda  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180017de1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180017de5  call    _CxxThrowException_0
```
