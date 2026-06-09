# cxl::Acl::UpdateAccessDeniedAce(ulong,_SID const *,ulong,bool)

- ea: `0x180018938`
- end: `0x180018c17`
- name: `?UpdateAccessDeniedAce@Acl@cxl@@QEAAXKPEBU_SID@@K_N@Z`
- size: `735`
- prototype: `void __fastcall(cxl::Acl *__hidden this, unsigned int, const struct _SID *, unsigned int, bool)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180060bc4`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x18000d600`
- `0x18000d6a4`
- `0x18000f094`
- `0x18000f20c`
- `0x18000f488`
- `0x1800124ac`
- `0x180012b00`
- `0x180015ae4`
- `0x180015b44`
- `0x180017fdc`
- `0x18001809c`
- `0x1800180e4`
- `0x1800181bc`
- `0x18001836c`
- `0x1800184e0`
- `0x180018600`
- `0x180018938`
- `0x180018c20`
- `0x18001913c`
- `0x180019740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800189f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800189f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b84`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180018b41`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180018b41`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800189c3`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800189c3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001899b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001899b`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x180018a4b`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x180018a4b`

## string_xrefs

- `0x180018a76`: `AddAccessDeniedAceEx failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall cxl::Acl::UpdateAccessDeniedAce(cxl::Acl *this, __int64 a2, struct _SID *a3)
{
  DWORD AclRevision; // r12d
  unsigned int AclAceCount; // r13d
  unsigned int AclUsedBytes; // ebx
  DWORD v8; // ebx
  unsigned int v9; // edx
  struct _ACL *v10; // r14
  unsigned int i; // ebx
  const struct _ACE_HEADER *Ace; // rax
  struct _ACE_HEADER *v13; // rdi
  DWORD LastError; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+34h] [rbp-CCh]
  _BYTE v16[8]; // [rsp+38h] [rbp-C8h] BYREF
  struct _ACL *v17; // [rsp+40h] [rbp-C0h]
  _BYTE v18[32]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v19[5]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+90h] [rbp-70h] BYREF

  cxl::SidBase::VerifySid(a3);
  cxl::AclBase::ReportErrorIfEmpty(this);
  AclRevision = cxl::AclBase::GetAclRevision(this);
  AclAceCount = cxl::AclBase::GetAclAceCount(this);
  AclUsedBytes = cxl::AclBase::GetAclUsedBytes(this);
  v8 = GetLengthSid(a3) + 16 + AclUsedBytes;
  v10 = (struct _ACL *)cxl::LocalHeap::Alloc(v8, v9);
  v17 = v10;
  if ( !InitializeAcl(v10, v8, AclRevision) )
  {
    std::wstring::wstring(v19);
    cxl::StringWriter::StringWriter(v18, v19);
    cxl::TextWriter::Write<21>(v18);
    LastError = GetLastError();
    v15 = 0;
    cxl::Exception::Exception(pExceptionObject, &LastError, v19);
    throw (cxl::Exception *)pExceptionObject;
  }
  if ( !AddAccessDeniedAceEx(v10, AclRevision, 3u, 0x10000000u, a3) )
  {
    std::wstring::wstring(v19);
    cxl::StringWriter::StringWriter(v18, v19);
    cxl::TextWriter::Write<28>(v18, "AddAccessDeniedAceEx failed");
    LastError = GetLastError();
    v15 = 0;
    cxl::Exception::Exception(pExceptionObject, &LastError, v19);
    throw (cxl::Exception *)pExceptionObject;
  }
  for ( i = 0; i < AclAceCount; ++i )
  {
    Ace = cxl::AclBase::GetAce(this, i);
    v13 = (struct _ACE_HEADER *)Ace;
    if ( Ace->AceType == 1 && (~Ace->AceFlags & 0x10) != 0 )
    {
      v19[0] = &cxl::SidBase::`vftable';
      v19[2] = 0;
      cxl::AclBase::GetAclSid(this, (struct cxl::SidBase *)v19, i);
      if ( cxl::SidBase::IsEqual((cxl::SidBase *)v19, a3) )
        continue;
    }
    if ( (v13->AceFlags & 0x10) != 0 )
      break;
    if ( !AddAce(v10, AclRevision, 0xFFFFFFFF, v13, v13->AceSize) )
    {
      std::wstring::wstring(v19);
      cxl::StringWriter::StringWriter(v18, v19);
      cxl::TextWriter::Write<14>(v18, "AddAce failed");
      LastError = GetLastError();
      v15 = 0;
      cxl::Exception::Exception(pExceptionObject, &LastError, v19);
      throw (cxl::Exception *)pExceptionObject;
    }
  }
  cxl::AclBase::VerifyAcl(v10);
  v17 = 0;
  cxl::Acl::Attach(this, v10);
  cxl::Acl::Repack(this);
  cxl::LocalHeapPtr<unsigned char>::Clear(v16);
}

```

## disassembly

```asm
0x180018938  mov     [rsp-8+arg_8], rbx
0x18001893d  push    rbp
0x18001893e  push    rsi
0x18001893f  push    rdi
0x180018940  push    r12
0x180018942  push    r13
0x180018944  push    r14
0x180018946  push    r15
0x180018948  lea     rbp, [rsp-10h]
0x18001894d  sub     rsp, 110h
0x180018954  mov     rax, cs:__security_cookie
0x18001895b  xor     rax, rsp
0x18001895e  mov     [rbp+40h+var_40], rax
0x180018962  mov     r15, r8
0x180018965  mov     rsi, rcx
0x180018968  mov     rcx, r8; struct _SID *
0x18001896b  call    ?VerifySid@SidBase@cxl@@SAXPEBU_SID@@@Z; cxl::SidBase::VerifySid(_SID const *)
0x180018970  mov     rcx, rsi; this
0x180018973  call    ?ReportErrorIfEmpty@AclBase@cxl@@IEBAXXZ; cxl::AclBase::ReportErrorIfEmpty(void)
0x180018978  mov     rcx, rsi; this
0x18001897b  call    ?GetAclRevision@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclRevision(void)
0x180018980  mov     r12d, eax
0x180018983  mov     rcx, rsi; this
0x180018986  call    ?GetAclAceCount@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclAceCount(void)
0x18001898b  mov     r13d, eax
0x18001898e  mov     rcx, rsi; this
0x180018991  call    ?GetAclUsedBytes@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclUsedBytes(void)
0x180018996  mov     ebx, eax
0x180018998  mov     rcx, r15; pSid
0x18001899b  call    cs:__imp_GetLengthSid
0x1800189a2  nop     dword ptr [rax+rax+00h]
0x1800189a7  add     eax, 10h
0x1800189aa  add     ebx, eax
0x1800189ac  mov     ecx, ebx; uBytes
0x1800189ae  call    ?Alloc@LocalHeap@cxl@@SAPEAX_KK@Z; cxl::LocalHeap::Alloc(unsigned __int64,ulong)
0x1800189b3  mov     r14, rax
0x1800189b6  mov     [rsp+140h+var_100], rax
0x1800189bb  mov     r8d, r12d; dwAclRevision
0x1800189be  mov     edx, ebx; nAclLength
0x1800189c0  mov     rcx, rax; pAcl
0x1800189c3  call    cs:__imp_InitializeAcl
0x1800189ca  nop     dword ptr [rax+rax+00h]
0x1800189cf  test    eax, eax
0x1800189d1  jnz     short loc_180018A34
0x1800189d3  lea     rcx, [rsp+140h+var_D8]
0x1800189d8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800189dd  nop
0x1800189de  lea     rdx, [rsp+140h+var_D8]
0x1800189e3  lea     rcx, [rsp+140h+var_F8]
0x1800189e8  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x1800189ed  nop
0x1800189ee  lea     rcx, [rsp+140h+var_F8]
0x1800189f3  call    ??$Write@$0BF@@TextWriter@cxl@@QEAAAEAV01@AEAY0BF@$$CBD@Z; cxl::TextWriter::Write<21>(char const (&)[21])
0x1800189f8  call    cs:__imp_GetLastError
0x1800189ff  nop     dword ptr [rax+rax+00h]
0x180018a04  mov     [rsp+140h+var_110], eax
0x180018a08  mov     [rsp+140h+var_10C], 0
0x180018a10  lea     r8, [rsp+140h+var_D8]
0x180018a15  lea     rdx, [rsp+140h+var_110]
0x180018a1a  lea     rcx, [rbp+40h+pExceptionObject]
0x180018a1e  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180018a23  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180018a2a  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x180018a2e  call    _CxxThrowException_0
0x180018a34  mov     [rsp+140h+pSid], r15; pSid
0x180018a39  mov     r9d, 10000000h; AccessMask
0x180018a3f  mov     r8d, 3; AceFlags
0x180018a45  mov     edx, r12d; dwAceRevision
0x180018a48  mov     rcx, r14; pAcl
0x180018a4b  call    cs:__imp_AddAccessDeniedAceEx
0x180018a52  nop     dword ptr [rax+rax+00h]
0x180018a57  test    eax, eax
0x180018a59  jnz     short loc_180018AC3
0x180018a5b  lea     rcx, [rsp+140h+var_D8]
0x180018a60  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180018a65  nop
0x180018a66  lea     rdx, [rsp+140h+var_D8]
0x180018a6b  lea     rcx, [rsp+140h+var_F8]
0x180018a70  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180018a75  nop
0x180018a76  lea     rdx, aAddaccessdenie; "AddAccessDeniedAceEx failed"
0x180018a7d  lea     rcx, [rsp+140h+var_F8]
0x180018a82  call    ??$Write@$0BM@@TextWriter@cxl@@QEAAAEAV01@AEAY0BM@$$CBD@Z; cxl::TextWriter::Write<28>(char const (&)[28])
0x180018a87  call    cs:__imp_GetLastError
0x180018a8e  nop     dword ptr [rax+rax+00h]
0x180018a93  mov     [rsp+140h+var_110], eax
0x180018a97  mov     [rsp+140h+var_10C], 0
0x180018a9f  lea     r8, [rsp+140h+var_D8]
0x180018aa4  lea     rdx, [rsp+140h+var_110]
0x180018aa9  lea     rcx, [rbp+40h+pExceptionObject]
0x180018aad  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180018ab2  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180018ab9  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x180018abd  call    _CxxThrowException_0
0x180018ac3  xor     ebx, ebx
0x180018ac5  cmp     ebx, r13d
0x180018ac8  jnb     loc_180018BC0
0x180018ace  mov     edx, ebx; unsigned int
0x180018ad0  mov     rcx, rsi; this
0x180018ad3  call    ?GetAce@AclBase@cxl@@QEBAPEBU_ACE_HEADER@@K@Z; cxl::AclBase::GetAce(ulong)
0x180018ad8  mov     rdi, rax
0x180018adb  cmp     byte ptr [rax], 1
0x180018ade  jnz     short loc_180018B22
0x180018ae0  movzx   ecx, byte ptr [rax+1]
0x180018ae4  not     ecx
0x180018ae6  test    cl, 10h
0x180018ae9  jz      short loc_180018B22
0x180018aeb  lea     rax, ??_7SidBase@cxl@@6B@; const cxl::SidBase::`vftable'
0x180018af2  mov     [rsp+140h+var_D8], rax
0x180018af7  mov     [rsp+140h+var_C8], 0
0x180018b00  mov     r8d, ebx; unsigned int
0x180018b03  lea     rdx, [rsp+140h+var_D8]; struct cxl::SidBase *
0x180018b08  mov     rcx, rsi; this
0x180018b0b  call    ?GetAclSid@AclBase@cxl@@QEBAXAEAVSidBase@2@K@Z; cxl::AclBase::GetAclSid(cxl::SidBase &,ulong)
0x180018b10  mov     rdx, r15; struct _SID *
0x180018b13  lea     rcx, [rsp+140h+var_D8]; this
0x180018b18  call    ?IsEqual@SidBase@cxl@@QEBA_NPEBU_SID@@@Z; cxl::SidBase::IsEqual(_SID const *)
0x180018b1d  nop
0x180018b1e  test    al, al
0x180018b20  jnz     short loc_180018B51
0x180018b22  test    byte ptr [rdi+1], 10h
0x180018b26  jnz     loc_180018BC0
0x180018b2c  movzx   eax, word ptr [rdi+2]
0x180018b30  mov     dword ptr [rsp+140h+pSid], eax; nAceListLength
0x180018b34  mov     r9, rdi; pAceList
0x180018b37  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x180018b3b  mov     edx, r12d; dwAceRevision
0x180018b3e  mov     rcx, r14; pAcl
0x180018b41  call    cs:__imp_AddAce
0x180018b48  nop     dword ptr [rax+rax+00h]
0x180018b4d  test    eax, eax
0x180018b4f  jz      short loc_180018B58
0x180018b51  inc     ebx
0x180018b53  jmp     loc_180018AC5
0x180018b58  lea     rcx, [rsp+140h+var_D8]
0x180018b5d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180018b62  nop
0x180018b63  lea     rdx, [rsp+140h+var_D8]
0x180018b68  lea     rcx, [rsp+140h+var_F8]
0x180018b6d  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180018b72  nop
0x180018b73  lea     rdx, aAddaceFailed; "AddAce failed"
0x180018b7a  lea     rcx, [rsp+140h+var_F8]
0x180018b7f  call    ??$Write@$0O@@TextWriter@cxl@@QEAAAEAV01@AEAY0O@$$CBD@Z; cxl::TextWriter::Write<14>(char const (&)[14])
0x180018b84  call    cs:__imp_GetLastError
0x180018b8b  nop     dword ptr [rax+rax+00h]
0x180018b90  mov     [rsp+140h+var_110], eax
0x180018b94  mov     [rsp+140h+var_10C], 0
0x180018b9c  lea     r8, [rsp+140h+var_D8]
0x180018ba1  lea     rdx, [rsp+140h+var_110]
0x180018ba6  lea     rcx, [rbp+40h+pExceptionObject]
0x180018baa  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180018baf  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180018bb6  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x180018bba  call    _CxxThrowException_0
0x180018bc0  mov     rcx, r14; struct _ACL *
0x180018bc3  call    ?VerifyAcl@AclBase@cxl@@KAXPEBU_ACL@@@Z; cxl::AclBase::VerifyAcl(_ACL const *)
0x180018bc8  mov     [rsp+140h+var_100], 0
0x180018bd1  mov     rdx, r14; struct _ACL *
0x180018bd4  mov     rcx, rsi; this
0x180018bd7  call    ?Attach@Acl@cxl@@QEAAXPEAU_ACL@@@Z; cxl::Acl::Attach(_ACL *)
0x180018bdc  mov     rcx, rsi; this
0x180018bdf  call    ?Repack@Acl@cxl@@AEAAXXZ; cxl::Acl::Repack(void)
0x180018be4  nop
0x180018be5  lea     rcx, [rsp+140h+var_108]
0x180018bea  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180018bef  mov     rcx, [rbp+40h+var_40]
0x180018bf3  xor     rcx, rsp; StackCookie
0x180018bf6  call    __security_check_cookie
0x180018bfb  mov     rbx, [rsp+140h+arg_8]
0x180018c03  add     rsp, 110h
0x180018c0a  pop     r15
0x180018c0c  pop     r14
0x180018c0e  pop     r13
0x180018c10  pop     r12
0x180018c12  pop     rdi
0x180018c13  pop     rsi
0x180018c14  pop     rbp
0x180018c15  retn
```
