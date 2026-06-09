# cxl::Acl::UpdateAccessDeniedAce(ulong,_SID const *,ulong,bool)

- ea: `0x1800180fc`
- end: `0x1800183b0`
- name: `?UpdateAccessDeniedAce@Acl@cxl@@QEAAXKPEBU_SID@@K_N@Z`
- size: `692`
- prototype: `void __fastcall(cxl::Acl *__hidden this, unsigned int, const struct _SID *, unsigned int, bool)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18005f9a4`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x18000d298`
- `0x18000d33c`
- `0x18000ec54`
- `0x18000edcc`
- `0x18000f048`
- `0x180012028`
- `0x180012660`
- `0x1800153e4`
- `0x180015440`
- `0x18001780c`
- `0x1800178c0`
- `0x180017904`
- `0x1800179d0`
- `0x180017b70`
- `0x180017ce0`
- `0x180017df4`
- `0x1800180fc`
- `0x1800183b8`
- `0x180018890`
- `0x180018e0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800181b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018324`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800181b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018324`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800182e7`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800182e7`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180018181`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180018181`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001815f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001815f`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x1800181fd`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x1800181fd`

## string_xrefs

- `0x180018222`: `AddAccessDeniedAceEx failed`

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
    cxl::TextWriter::Write<21>((__int64)v18);
    LastError = GetLastError();
    v15 = 0;
    cxl::Exception::Exception(pExceptionObject, &LastError, v19);
    throw (cxl::Exception *)pExceptionObject;
  }
  if ( !AddAccessDeniedAceEx(v10, AclRevision, 3u, 0x10000000u, a3) )
  {
    std::wstring::wstring(v19);
    cxl::StringWriter::StringWriter(v18, v19);
    cxl::TextWriter::Write<28>((__int64)v18, (__int64)"AddAccessDeniedAceEx failed");
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
      cxl::TextWriter::Write<14>((__int64)v18, (__int64)"AddAce failed");
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
0x1800180fc  mov     [rsp-8+arg_8], rbx
0x180018101  push    rbp
0x180018102  push    rsi
0x180018103  push    rdi
0x180018104  push    r12
0x180018106  push    r13
0x180018108  push    r14
0x18001810a  push    r15
0x18001810c  lea     rbp, [rsp-10h]
0x180018111  sub     rsp, 110h
0x180018118  mov     rax, cs:__security_cookie
0x18001811f  xor     rax, rsp
0x180018122  mov     [rbp+40h+var_40], rax
0x180018126  mov     r15, r8
0x180018129  mov     rsi, rcx
0x18001812c  mov     rcx, r8; struct _SID *
0x18001812f  call    ?VerifySid@SidBase@cxl@@SAXPEBU_SID@@@Z; cxl::SidBase::VerifySid(_SID const *)
0x180018134  mov     rcx, rsi; this
0x180018137  call    ?ReportErrorIfEmpty@AclBase@cxl@@IEBAXXZ; cxl::AclBase::ReportErrorIfEmpty(void)
0x18001813c  mov     rcx, rsi; this
0x18001813f  call    ?GetAclRevision@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclRevision(void)
0x180018144  mov     r12d, eax
0x180018147  mov     rcx, rsi; this
0x18001814a  call    ?GetAclAceCount@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclAceCount(void)
0x18001814f  mov     r13d, eax
0x180018152  mov     rcx, rsi; this
0x180018155  call    ?GetAclUsedBytes@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclUsedBytes(void)
0x18001815a  mov     ebx, eax
0x18001815c  mov     rcx, r15; pSid
0x18001815f  call    cs:__imp_GetLengthSid
0x180018165  add     eax, 10h
0x180018168  add     ebx, eax
0x18001816a  mov     ecx, ebx; uBytes
0x18001816c  call    ?Alloc@LocalHeap@cxl@@SAPEAX_KK@Z; cxl::LocalHeap::Alloc(unsigned __int64,ulong)
0x180018171  mov     r14, rax
0x180018174  mov     [rsp+140h+var_100], rax
0x180018179  mov     r8d, r12d; dwAclRevision
0x18001817c  mov     edx, ebx; nAclLength
0x18001817e  mov     rcx, rax; pAcl
0x180018181  call    cs:__imp_InitializeAcl
0x180018187  test    eax, eax
0x180018189  jnz     short loc_1800181E6
0x18001818b  lea     rcx, [rsp+140h+var_D8]
0x180018190  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180018195  nop
0x180018196  lea     rdx, [rsp+140h+var_D8]
0x18001819b  lea     rcx, [rsp+140h+var_F8]
0x1800181a0  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x1800181a5  nop
0x1800181a6  lea     rcx, [rsp+140h+var_F8]
0x1800181ab  call    ??$Write@$0BF@@TextWriter@cxl@@QEAAAEAV01@AEAY0BF@$$CBD@Z; cxl::TextWriter::Write<21>(char const (&)[21])
0x1800181b0  call    cs:__imp_GetLastError
0x1800181b6  mov     [rsp+140h+var_110], eax
0x1800181ba  mov     [rsp+140h+var_10C], 0
0x1800181c2  lea     r8, [rsp+140h+var_D8]
0x1800181c7  lea     rdx, [rsp+140h+var_110]
0x1800181cc  lea     rcx, [rbp+40h+pExceptionObject]
0x1800181d0  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800181d5  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800181dc  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x1800181e0  call    _CxxThrowException_0
0x1800181e6  mov     [rsp+140h+pSid], r15; pSid
0x1800181eb  mov     r9d, 10000000h; AccessMask
0x1800181f1  mov     r8d, 3; AceFlags
0x1800181f7  mov     edx, r12d; dwAceRevision
0x1800181fa  mov     rcx, r14; pAcl
0x1800181fd  call    cs:__imp_AddAccessDeniedAceEx
0x180018203  test    eax, eax
0x180018205  jnz     short loc_180018269
0x180018207  lea     rcx, [rsp+140h+var_D8]
0x18001820c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180018211  nop
0x180018212  lea     rdx, [rsp+140h+var_D8]
0x180018217  lea     rcx, [rsp+140h+var_F8]
0x18001821c  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180018221  nop
0x180018222  lea     rdx, aAddaccessdenie; "AddAccessDeniedAceEx failed"
0x180018229  lea     rcx, [rsp+140h+var_F8]
0x18001822e  call    ??$Write@$0BM@@TextWriter@cxl@@QEAAAEAV01@AEAY0BM@$$CBD@Z; cxl::TextWriter::Write<28>(char const (&)[28])
0x180018233  call    cs:__imp_GetLastError
0x180018239  mov     [rsp+140h+var_110], eax
0x18001823d  mov     [rsp+140h+var_10C], 0
0x180018245  lea     r8, [rsp+140h+var_D8]
0x18001824a  lea     rdx, [rsp+140h+var_110]
0x18001824f  lea     rcx, [rbp+40h+pExceptionObject]
0x180018253  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180018258  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001825f  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x180018263  call    _CxxThrowException_0
0x180018269  xor     ebx, ebx
0x18001826b  cmp     ebx, r13d
0x18001826e  jnb     loc_18001835A
0x180018274  mov     edx, ebx; unsigned int
0x180018276  mov     rcx, rsi; this
0x180018279  call    ?GetAce@AclBase@cxl@@QEBAPEBU_ACE_HEADER@@K@Z; cxl::AclBase::GetAce(ulong)
0x18001827e  mov     rdi, rax
0x180018281  cmp     byte ptr [rax], 1
0x180018284  jnz     short loc_1800182C8
0x180018286  movzx   ecx, byte ptr [rax+1]
0x18001828a  not     ecx
0x18001828c  test    cl, 10h
0x18001828f  jz      short loc_1800182C8
0x180018291  lea     rax, ??_7SidBase@cxl@@6B@; const cxl::SidBase::`vftable'
0x180018298  mov     [rsp+140h+var_D8], rax
0x18001829d  mov     [rsp+140h+var_C8], 0
0x1800182a6  mov     r8d, ebx; unsigned int
0x1800182a9  lea     rdx, [rsp+140h+var_D8]; struct cxl::SidBase *
0x1800182ae  mov     rcx, rsi; this
0x1800182b1  call    ?GetAclSid@AclBase@cxl@@QEBAXAEAVSidBase@2@K@Z; cxl::AclBase::GetAclSid(cxl::SidBase &,ulong)
0x1800182b6  mov     rdx, r15; struct _SID *
0x1800182b9  lea     rcx, [rsp+140h+var_D8]; this
0x1800182be  call    ?IsEqual@SidBase@cxl@@QEBA_NPEBU_SID@@@Z; cxl::SidBase::IsEqual(_SID const *)
0x1800182c3  nop
0x1800182c4  test    al, al
0x1800182c6  jnz     short loc_1800182F1
0x1800182c8  test    byte ptr [rdi+1], 10h
0x1800182cc  jnz     loc_18001835A
0x1800182d2  movzx   eax, word ptr [rdi+2]
0x1800182d6  mov     dword ptr [rsp+140h+pSid], eax; nAceListLength
0x1800182da  mov     r9, rdi; pAceList
0x1800182dd  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x1800182e1  mov     edx, r12d; dwAceRevision
0x1800182e4  mov     rcx, r14; pAcl
0x1800182e7  call    cs:__imp_AddAce
0x1800182ed  test    eax, eax
0x1800182ef  jz      short loc_1800182F8
0x1800182f1  inc     ebx
0x1800182f3  jmp     loc_18001826B
0x1800182f8  lea     rcx, [rsp+140h+var_D8]
0x1800182fd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180018302  nop
0x180018303  lea     rdx, [rsp+140h+var_D8]
0x180018308  lea     rcx, [rsp+140h+var_F8]
0x18001830d  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180018312  nop
0x180018313  lea     rdx, aAddaceFailed; "AddAce failed"
0x18001831a  lea     rcx, [rsp+140h+var_F8]
0x18001831f  call    ??$Write@$0O@@TextWriter@cxl@@QEAAAEAV01@AEAY0O@$$CBD@Z; cxl::TextWriter::Write<14>(char const (&)[14])
0x180018324  call    cs:__imp_GetLastError
0x18001832a  mov     [rsp+140h+var_110], eax
0x18001832e  mov     [rsp+140h+var_10C], 0
0x180018336  lea     r8, [rsp+140h+var_D8]
0x18001833b  lea     rdx, [rsp+140h+var_110]
0x180018340  lea     rcx, [rbp+40h+pExceptionObject]
0x180018344  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180018349  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180018350  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x180018354  call    _CxxThrowException_0
0x18001835a  mov     rcx, r14; struct _ACL *
0x18001835d  call    ?VerifyAcl@AclBase@cxl@@KAXPEBU_ACL@@@Z; cxl::AclBase::VerifyAcl(_ACL const *)
0x180018362  mov     [rsp+140h+var_100], 0
0x18001836b  mov     rdx, r14; struct _ACL *
0x18001836e  mov     rcx, rsi; this
0x180018371  call    ?Attach@Acl@cxl@@QEAAXPEAU_ACL@@@Z; cxl::Acl::Attach(_ACL *)
0x180018376  mov     rcx, rsi; this
0x180018379  call    ?Repack@Acl@cxl@@AEAAXXZ; cxl::Acl::Repack(void)
0x18001837e  nop
0x18001837f  lea     rcx, [rsp+140h+var_108]
0x180018384  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180018389  mov     rcx, [rbp+40h+var_40]
0x18001838d  xor     rcx, rsp; StackCookie
0x180018390  call    __security_check_cookie
0x180018395  mov     rbx, [rsp+140h+arg_8]
0x18001839d  add     rsp, 110h
0x1800183a4  pop     r15
0x1800183a6  pop     r14
0x1800183a8  pop     r13
0x1800183aa  pop     r12
0x1800183ac  pop     rdi
0x1800183ad  pop     rsi
0x1800183ae  pop     rbp
0x1800183af  retn
```
