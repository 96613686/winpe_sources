# cxl::Acl::UpdateAccessAllowedAce(ulong,_SID const *,ulong,bool)

- ea: `0x180017e4c`
- end: `0x1800180f5`
- name: `?UpdateAccessAllowedAce@Acl@cxl@@QEAAXKPEBU_SID@@K_N@Z`
- size: `681`
- prototype: `void __fastcall(cxl::Acl *__hidden this, unsigned int, const struct _SID *, unsigned int, bool)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180060d28`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x18000d298`
- `0x18000d33c`
- `0x18000ec54`
- `0x18000edf8`
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
- `0x180017e4c`
- `0x1800183b8`
- `0x180018890`
- `0x180018e0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017fe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018069`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017fe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018069`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180017fad`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180017fad`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180017ed5`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180017ed5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180017eb3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180017eb3`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180018033`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180018033`

## string_xrefs

- `0x180018058`: `AddAccessAllowedAceEx failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall cxl::Acl::UpdateAccessAllowedAce(cxl::Acl *this, DWORD a2, struct _SID *a3)
{
  DWORD AclRevision; // r12d
  unsigned int AclAceCount; // r13d
  unsigned int AclUsedBytes; // ebx
  DWORD v8; // ebx
  unsigned int v9; // edx
  struct _ACL *v10; // r14
  unsigned int i; // ebx
  const struct _ACE_HEADER *Ace; // rax
  unsigned __int16 *p_AceType; // rdi
  DWORD AccessMask; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+34h] [rbp-CCh]
  _BYTE v16[8]; // [rsp+38h] [rbp-C8h] BYREF
  struct _ACL *v17; // [rsp+40h] [rbp-C0h]
  _BYTE v18[32]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v19[5]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+90h] [rbp-70h] BYREF

  AccessMask = a2;
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
    AccessMask = GetLastError();
    v15 = 0;
    cxl::Exception::Exception(pExceptionObject, &AccessMask, v19);
    throw (cxl::Exception *)pExceptionObject;
  }
  for ( i = 0; i < AclAceCount; ++i )
  {
    Ace = cxl::AclBase::GetAce(this, i);
    p_AceType = (unsigned __int16 *)&Ace->AceType;
    if ( (Ace->AceFlags & 0x10) != 0 )
      break;
    if ( !Ace->AceType )
    {
      v19[0] = &cxl::SidBase::`vftable';
      v19[2] = 0;
      cxl::AclBase::GetAclSid(this, (struct cxl::SidBase *)v19, i);
      if ( cxl::SidBase::IsEqual((cxl::SidBase *)v19, a3) )
        continue;
    }
    if ( !AddAce(v10, AclRevision, 0xFFFFFFFF, p_AceType, p_AceType[1]) )
    {
      std::wstring::wstring(v19);
      cxl::StringWriter::StringWriter(v18, v19);
      cxl::TextWriter::Write<14>((__int64)v18, (__int64)"AddAce failed");
      AccessMask = GetLastError();
      v15 = 0;
      cxl::Exception::Exception(pExceptionObject, &AccessMask, v19);
      throw (cxl::Exception *)pExceptionObject;
    }
  }
  if ( !AddAccessAllowedAceEx(v10, AclRevision, 3u, AccessMask, a3) )
  {
    std::wstring::wstring(v19);
    cxl::StringWriter::StringWriter(v18, v19);
    cxl::TextWriter::WriteFmt<29>((__int64)v18, (__int64)"AddAccessAllowedAceEx failed");
    AccessMask = GetLastError();
    v15 = 0;
    cxl::Exception::Exception(pExceptionObject, &AccessMask, v19);
    throw (cxl::Exception *)pExceptionObject;
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
0x180017e4c  mov     [rsp-8+arg_18], rbx
0x180017e51  push    rbp
0x180017e52  push    rsi
0x180017e53  push    rdi
0x180017e54  push    r12
0x180017e56  push    r13
0x180017e58  push    r14
0x180017e5a  push    r15
0x180017e5c  lea     rbp, [rsp-10h]
0x180017e61  sub     rsp, 110h
0x180017e68  mov     rax, cs:__security_cookie
0x180017e6f  xor     rax, rsp
0x180017e72  mov     [rbp+40h+var_40], rax
0x180017e76  mov     r15, r8
0x180017e79  mov     [rsp+140h+AccessMask], edx
0x180017e7d  mov     rsi, rcx
0x180017e80  mov     rcx, r8; struct _SID *
0x180017e83  call    ?VerifySid@SidBase@cxl@@SAXPEBU_SID@@@Z; cxl::SidBase::VerifySid(_SID const *)
0x180017e88  mov     rcx, rsi; this
0x180017e8b  call    ?ReportErrorIfEmpty@AclBase@cxl@@IEBAXXZ; cxl::AclBase::ReportErrorIfEmpty(void)
0x180017e90  mov     rcx, rsi; this
0x180017e93  call    ?GetAclRevision@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclRevision(void)
0x180017e98  mov     r12d, eax
0x180017e9b  mov     rcx, rsi; this
0x180017e9e  call    ?GetAclAceCount@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclAceCount(void)
0x180017ea3  mov     r13d, eax
0x180017ea6  mov     rcx, rsi; this
0x180017ea9  call    ?GetAclUsedBytes@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclUsedBytes(void)
0x180017eae  mov     ebx, eax
0x180017eb0  mov     rcx, r15; pSid
0x180017eb3  call    cs:__imp_GetLengthSid
0x180017eb9  add     eax, 10h
0x180017ebc  add     ebx, eax
0x180017ebe  mov     ecx, ebx; uBytes
0x180017ec0  call    ?Alloc@LocalHeap@cxl@@SAPEAX_KK@Z; cxl::LocalHeap::Alloc(unsigned __int64,ulong)
0x180017ec5  mov     r14, rax
0x180017ec8  mov     [rsp+140h+var_100], rax
0x180017ecd  mov     r8d, r12d; dwAclRevision
0x180017ed0  mov     edx, ebx; nAclLength
0x180017ed2  mov     rcx, rax; pAcl
0x180017ed5  call    cs:__imp_InitializeAcl
0x180017edb  test    eax, eax
0x180017edd  jnz     short loc_180017F3A
0x180017edf  lea     rcx, [rsp+140h+var_D8]
0x180017ee4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180017ee9  nop
0x180017eea  lea     rdx, [rsp+140h+var_D8]
0x180017eef  lea     rcx, [rsp+140h+var_F8]
0x180017ef4  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180017ef9  nop
0x180017efa  lea     rcx, [rsp+140h+var_F8]
0x180017eff  call    ??$Write@$0BF@@TextWriter@cxl@@QEAAAEAV01@AEAY0BF@$$CBD@Z; cxl::TextWriter::Write<21>(char const (&)[21])
0x180017f04  call    cs:__imp_GetLastError
0x180017f0a  mov     [rsp+140h+AccessMask], eax
0x180017f0e  mov     [rsp+140h+var_10C], 0
0x180017f16  lea     r8, [rsp+140h+var_D8]
0x180017f1b  lea     rdx, [rsp+140h+AccessMask]
0x180017f20  lea     rcx, [rbp+40h+pExceptionObject]
0x180017f24  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180017f29  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180017f30  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x180017f34  call    _CxxThrowException_0
0x180017f3a  xor     ebx, ebx
0x180017f3c  cmp     ebx, r13d
0x180017f3f  jnb     loc_18001801D
0x180017f45  mov     edx, ebx; unsigned int
0x180017f47  mov     rcx, rsi; this
0x180017f4a  call    ?GetAce@AclBase@cxl@@QEBAPEBU_ACE_HEADER@@K@Z; cxl::AclBase::GetAce(ulong)
0x180017f4f  mov     rdi, rax
0x180017f52  test    byte ptr [rax+1], 10h
0x180017f56  jnz     loc_18001801D
0x180017f5c  cmp     byte ptr [rax], 0
0x180017f5f  jnz     short loc_180017F98
0x180017f61  lea     rax, ??_7SidBase@cxl@@6B@; const cxl::SidBase::`vftable'
0x180017f68  mov     [rsp+140h+var_D8], rax
0x180017f6d  mov     [rsp+140h+var_C8], 0
0x180017f76  mov     r8d, ebx; unsigned int
0x180017f79  lea     rdx, [rsp+140h+var_D8]; struct cxl::SidBase *
0x180017f7e  mov     rcx, rsi; this
0x180017f81  call    ?GetAclSid@AclBase@cxl@@QEBAXAEAVSidBase@2@K@Z; cxl::AclBase::GetAclSid(cxl::SidBase &,ulong)
0x180017f86  mov     rdx, r15; struct _SID *
0x180017f89  lea     rcx, [rsp+140h+var_D8]; this
0x180017f8e  call    ?IsEqual@SidBase@cxl@@QEBA_NPEBU_SID@@@Z; cxl::SidBase::IsEqual(_SID const *)
0x180017f93  nop
0x180017f94  test    al, al
0x180017f96  jnz     short loc_180017FB7
0x180017f98  movzx   eax, word ptr [rdi+2]
0x180017f9c  mov     [rsp+140h+nAceListLength], eax; nAceListLength
0x180017fa0  mov     r9, rdi; pAceList
0x180017fa3  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x180017fa7  mov     edx, r12d; dwAceRevision
0x180017faa  mov     rcx, r14; pAcl
0x180017fad  call    cs:__imp_AddAce
0x180017fb3  test    eax, eax
0x180017fb5  jz      short loc_180017FBB
0x180017fb7  inc     ebx
0x180017fb9  jmp     short loc_180017F3C
0x180017fbb  lea     rcx, [rsp+140h+var_D8]
0x180017fc0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180017fc5  nop
0x180017fc6  lea     rdx, [rsp+140h+var_D8]
0x180017fcb  lea     rcx, [rsp+140h+var_F8]
0x180017fd0  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180017fd5  nop
0x180017fd6  lea     rdx, aAddaceFailed; "AddAce failed"
0x180017fdd  lea     rcx, [rsp+140h+var_F8]
0x180017fe2  call    ??$Write@$0O@@TextWriter@cxl@@QEAAAEAV01@AEAY0O@$$CBD@Z; cxl::TextWriter::Write<14>(char const (&)[14])
0x180017fe7  call    cs:__imp_GetLastError
0x180017fed  mov     [rsp+140h+AccessMask], eax
0x180017ff1  mov     [rsp+140h+var_10C], 0
0x180017ff9  lea     r8, [rsp+140h+var_D8]
0x180017ffe  lea     rdx, [rsp+140h+AccessMask]
0x180018003  lea     rcx, [rbp+40h+pExceptionObject]
0x180018007  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18001800c  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180018013  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x180018017  call    _CxxThrowException_0
0x18001801d  mov     qword ptr [rsp+140h+nAceListLength], r15; pSid
0x180018022  mov     r9d, [rsp+140h+AccessMask]; AccessMask
0x180018027  mov     r8d, 3; AceFlags
0x18001802d  mov     edx, r12d; dwAceRevision
0x180018030  mov     rcx, r14; pAcl
0x180018033  call    cs:__imp_AddAccessAllowedAceEx
0x180018039  test    eax, eax
0x18001803b  jnz     short loc_18001809F
0x18001803d  lea     rcx, [rsp+140h+var_D8]
0x180018042  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180018047  nop
0x180018048  lea     rdx, [rsp+140h+var_D8]
0x18001804d  lea     rcx, [rsp+140h+var_F8]
0x180018052  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180018057  nop
0x180018058  lea     rdx, aAddaccessallow; "AddAccessAllowedAceEx failed"
0x18001805f  lea     rcx, [rsp+140h+var_F8]
0x180018064  call    ??$WriteFmt@$0BN@@TextWriter@cxl@@QEAAAEAV01@AEAY0BN@$$CBDAEBUFormat@1@@Z; cxl::TextWriter::WriteFmt<29>(char const (&)[29],cxl::Format const &)
0x180018069  call    cs:__imp_GetLastError
0x18001806f  mov     [rsp+140h+AccessMask], eax
0x180018073  mov     [rsp+140h+var_10C], 0
0x18001807b  lea     r8, [rsp+140h+var_D8]
0x180018080  lea     rdx, [rsp+140h+AccessMask]
0x180018085  lea     rcx, [rbp+40h+pExceptionObject]
0x180018089  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18001808e  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180018095  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x180018099  call    _CxxThrowException_0
0x18001809f  mov     rcx, r14; struct _ACL *
0x1800180a2  call    ?VerifyAcl@AclBase@cxl@@KAXPEBU_ACL@@@Z; cxl::AclBase::VerifyAcl(_ACL const *)
0x1800180a7  mov     [rsp+140h+var_100], 0
0x1800180b0  mov     rdx, r14; struct _ACL *
0x1800180b3  mov     rcx, rsi; this
0x1800180b6  call    ?Attach@Acl@cxl@@QEAAXPEAU_ACL@@@Z; cxl::Acl::Attach(_ACL *)
0x1800180bb  mov     rcx, rsi; this
0x1800180be  call    ?Repack@Acl@cxl@@AEAAXXZ; cxl::Acl::Repack(void)
0x1800180c3  nop
0x1800180c4  lea     rcx, [rsp+140h+var_108]
0x1800180c9  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x1800180ce  mov     rcx, [rbp+40h+var_40]
0x1800180d2  xor     rcx, rsp; StackCookie
0x1800180d5  call    __security_check_cookie
0x1800180da  mov     rbx, [rsp+140h+arg_18]
0x1800180e2  add     rsp, 110h
0x1800180e9  pop     r15
0x1800180eb  pop     r14
0x1800180ed  pop     r13
0x1800180ef  pop     r12
0x1800180f1  pop     rdi
0x1800180f2  pop     rsi
0x1800180f3  pop     rbp
0x1800180f4  retn
```
