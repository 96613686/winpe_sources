# cxl::Acl::UpdateAccessAllowedAce(ulong,_SID const *,ulong,bool)

- ea: `0x180018658`
- end: `0x18001892f`
- name: `?UpdateAccessAllowedAce@Acl@cxl@@QEAAXKPEBU_SID@@K_N@Z`
- size: `727`
- prototype: `void __fastcall(cxl::Acl *__hidden this, unsigned int, const struct _SID *, unsigned int, bool)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180061f58`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x18000d600`
- `0x18000d6a4`
- `0x18000f094`
- `0x18000f238`
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
- `0x180018658`
- `0x180018c20`
- `0x18001913c`
- `0x180019740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001871c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001880e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001889c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001871c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001880e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001889c`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800187cb`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800187cb`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800186e7`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800186e7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800186bf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800186bf`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180018860`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180018860`

## string_xrefs

- `0x18001888b`: `AddAccessAllowedAceEx failed`

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
    cxl::TextWriter::Write<21>(v18);
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
      cxl::TextWriter::Write<14>(v18, "AddAce failed");
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
    cxl::TextWriter::WriteFmt<29>(v18, "AddAccessAllowedAceEx failed");
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
0x180018658  mov     [rsp-8+arg_18], rbx
0x18001865d  push    rbp
0x18001865e  push    rsi
0x18001865f  push    rdi
0x180018660  push    r12
0x180018662  push    r13
0x180018664  push    r14
0x180018666  push    r15
0x180018668  lea     rbp, [rsp-10h]
0x18001866d  sub     rsp, 110h
0x180018674  mov     rax, cs:__security_cookie
0x18001867b  xor     rax, rsp
0x18001867e  mov     [rbp+40h+var_40], rax
0x180018682  mov     r15, r8
0x180018685  mov     [rsp+140h+AccessMask], edx
0x180018689  mov     rsi, rcx
0x18001868c  mov     rcx, r8; struct _SID *
0x18001868f  call    ?VerifySid@SidBase@cxl@@SAXPEBU_SID@@@Z; cxl::SidBase::VerifySid(_SID const *)
0x180018694  mov     rcx, rsi; this
0x180018697  call    ?ReportErrorIfEmpty@AclBase@cxl@@IEBAXXZ; cxl::AclBase::ReportErrorIfEmpty(void)
0x18001869c  mov     rcx, rsi; this
0x18001869f  call    ?GetAclRevision@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclRevision(void)
0x1800186a4  mov     r12d, eax
0x1800186a7  mov     rcx, rsi; this
0x1800186aa  call    ?GetAclAceCount@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclAceCount(void)
0x1800186af  mov     r13d, eax
0x1800186b2  mov     rcx, rsi; this
0x1800186b5  call    ?GetAclUsedBytes@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclUsedBytes(void)
0x1800186ba  mov     ebx, eax
0x1800186bc  mov     rcx, r15; pSid
0x1800186bf  call    cs:__imp_GetLengthSid
0x1800186c6  nop     dword ptr [rax+rax+00h]
0x1800186cb  add     eax, 10h
0x1800186ce  add     ebx, eax
0x1800186d0  mov     ecx, ebx; uBytes
0x1800186d2  call    ?Alloc@LocalHeap@cxl@@SAPEAX_KK@Z; cxl::LocalHeap::Alloc(unsigned __int64,ulong)
0x1800186d7  mov     r14, rax
0x1800186da  mov     [rsp+140h+var_100], rax
0x1800186df  mov     r8d, r12d; dwAclRevision
0x1800186e2  mov     edx, ebx; nAclLength
0x1800186e4  mov     rcx, rax; pAcl
0x1800186e7  call    cs:__imp_InitializeAcl
0x1800186ee  nop     dword ptr [rax+rax+00h]
0x1800186f3  test    eax, eax
0x1800186f5  jnz     short loc_180018758
0x1800186f7  lea     rcx, [rsp+140h+var_D8]
0x1800186fc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180018701  nop
0x180018702  lea     rdx, [rsp+140h+var_D8]
0x180018707  lea     rcx, [rsp+140h+var_F8]
0x18001870c  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180018711  nop
0x180018712  lea     rcx, [rsp+140h+var_F8]
0x180018717  call    ??$Write@$0BF@@TextWriter@cxl@@QEAAAEAV01@AEAY0BF@$$CBD@Z; cxl::TextWriter::Write<21>(char const (&)[21])
0x18001871c  call    cs:__imp_GetLastError
0x180018723  nop     dword ptr [rax+rax+00h]
0x180018728  mov     [rsp+140h+AccessMask], eax
0x18001872c  mov     [rsp+140h+var_10C], 0
0x180018734  lea     r8, [rsp+140h+var_D8]
0x180018739  lea     rdx, [rsp+140h+AccessMask]
0x18001873e  lea     rcx, [rbp+40h+pExceptionObject]
0x180018742  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180018747  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001874e  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x180018752  call    _CxxThrowException_0
0x180018758  xor     ebx, ebx
0x18001875a  cmp     ebx, r13d
0x18001875d  jnb     loc_18001884A
0x180018763  mov     edx, ebx; unsigned int
0x180018765  mov     rcx, rsi; this
0x180018768  call    ?GetAce@AclBase@cxl@@QEBAPEBU_ACE_HEADER@@K@Z; cxl::AclBase::GetAce(ulong)
0x18001876d  mov     rdi, rax
0x180018770  test    byte ptr [rax+1], 10h
0x180018774  jnz     loc_18001884A
0x18001877a  cmp     byte ptr [rax], 0
0x18001877d  jnz     short loc_1800187B6
0x18001877f  lea     rax, ??_7SidBase@cxl@@6B@; const cxl::SidBase::`vftable'
0x180018786  mov     [rsp+140h+var_D8], rax
0x18001878b  mov     [rsp+140h+var_C8], 0
0x180018794  mov     r8d, ebx; unsigned int
0x180018797  lea     rdx, [rsp+140h+var_D8]; struct cxl::SidBase *
0x18001879c  mov     rcx, rsi; this
0x18001879f  call    ?GetAclSid@AclBase@cxl@@QEBAXAEAVSidBase@2@K@Z; cxl::AclBase::GetAclSid(cxl::SidBase &,ulong)
0x1800187a4  mov     rdx, r15; struct _SID *
0x1800187a7  lea     rcx, [rsp+140h+var_D8]; this
0x1800187ac  call    ?IsEqual@SidBase@cxl@@QEBA_NPEBU_SID@@@Z; cxl::SidBase::IsEqual(_SID const *)
0x1800187b1  nop
0x1800187b2  test    al, al
0x1800187b4  jnz     short loc_1800187DB
0x1800187b6  movzx   eax, word ptr [rdi+2]
0x1800187ba  mov     [rsp+140h+nAceListLength], eax; nAceListLength
0x1800187be  mov     r9, rdi; pAceList
0x1800187c1  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x1800187c5  mov     edx, r12d; dwAceRevision
0x1800187c8  mov     rcx, r14; pAcl
0x1800187cb  call    cs:__imp_AddAce
0x1800187d2  nop     dword ptr [rax+rax+00h]
0x1800187d7  test    eax, eax
0x1800187d9  jz      short loc_1800187E2
0x1800187db  inc     ebx
0x1800187dd  jmp     loc_18001875A
0x1800187e2  lea     rcx, [rsp+140h+var_D8]
0x1800187e7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800187ec  nop
0x1800187ed  lea     rdx, [rsp+140h+var_D8]
0x1800187f2  lea     rcx, [rsp+140h+var_F8]
0x1800187f7  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x1800187fc  nop
0x1800187fd  lea     rdx, aAddaceFailed; "AddAce failed"
0x180018804  lea     rcx, [rsp+140h+var_F8]
0x180018809  call    ??$Write@$0O@@TextWriter@cxl@@QEAAAEAV01@AEAY0O@$$CBD@Z; cxl::TextWriter::Write<14>(char const (&)[14])
0x18001880e  call    cs:__imp_GetLastError
0x180018815  nop     dword ptr [rax+rax+00h]
0x18001881a  mov     [rsp+140h+AccessMask], eax
0x18001881e  mov     [rsp+140h+var_10C], 0
0x180018826  lea     r8, [rsp+140h+var_D8]
0x18001882b  lea     rdx, [rsp+140h+AccessMask]
0x180018830  lea     rcx, [rbp+40h+pExceptionObject]
0x180018834  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180018839  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180018840  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x180018844  call    _CxxThrowException_0
0x18001884a  mov     qword ptr [rsp+140h+nAceListLength], r15; pSid
0x18001884f  mov     r9d, [rsp+140h+AccessMask]; AccessMask
0x180018854  mov     r8d, 3; AceFlags
0x18001885a  mov     edx, r12d; dwAceRevision
0x18001885d  mov     rcx, r14; pAcl
0x180018860  call    cs:__imp_AddAccessAllowedAceEx
0x180018867  nop     dword ptr [rax+rax+00h]
0x18001886c  test    eax, eax
0x18001886e  jnz     short loc_1800188D8
0x180018870  lea     rcx, [rsp+140h+var_D8]
0x180018875  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001887a  nop
0x18001887b  lea     rdx, [rsp+140h+var_D8]
0x180018880  lea     rcx, [rsp+140h+var_F8]
0x180018885  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001888a  nop
0x18001888b  lea     rdx, aAddaccessallow; "AddAccessAllowedAceEx failed"
0x180018892  lea     rcx, [rsp+140h+var_F8]
0x180018897  call    ??$WriteFmt@$0BN@@TextWriter@cxl@@QEAAAEAV01@AEAY0BN@$$CBDAEBUFormat@1@@Z; cxl::TextWriter::WriteFmt<29>(char const (&)[29],cxl::Format const &)
0x18001889c  call    cs:__imp_GetLastError
0x1800188a3  nop     dword ptr [rax+rax+00h]
0x1800188a8  mov     [rsp+140h+AccessMask], eax
0x1800188ac  mov     [rsp+140h+var_10C], 0
0x1800188b4  lea     r8, [rsp+140h+var_D8]
0x1800188b9  lea     rdx, [rsp+140h+AccessMask]
0x1800188be  lea     rcx, [rbp+40h+pExceptionObject]
0x1800188c2  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800188c7  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800188ce  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x1800188d2  call    _CxxThrowException_0
0x1800188d8  mov     rcx, r14; struct _ACL *
0x1800188db  call    ?VerifyAcl@AclBase@cxl@@KAXPEBU_ACL@@@Z; cxl::AclBase::VerifyAcl(_ACL const *)
0x1800188e0  mov     [rsp+140h+var_100], 0
0x1800188e9  mov     rdx, r14; struct _ACL *
0x1800188ec  mov     rcx, rsi; this
0x1800188ef  call    ?Attach@Acl@cxl@@QEAAXPEAU_ACL@@@Z; cxl::Acl::Attach(_ACL *)
0x1800188f4  mov     rcx, rsi; this
0x1800188f7  call    ?Repack@Acl@cxl@@AEAAXXZ; cxl::Acl::Repack(void)
0x1800188fc  nop
0x1800188fd  lea     rcx, [rsp+140h+var_108]
0x180018902  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180018907  mov     rcx, [rbp+40h+var_40]
0x18001890b  xor     rcx, rsp; StackCookie
0x18001890e  call    __security_check_cookie
0x180018913  mov     rbx, [rsp+140h+arg_18]
0x18001891b  add     rsp, 110h
0x180018922  pop     r15
0x180018924  pop     r14
0x180018926  pop     r13
0x180018928  pop     r12
0x18001892a  pop     rdi
0x18001892b  pop     rsi
0x18001892c  pop     rbp
0x18001892d  retn
```
