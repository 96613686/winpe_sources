# UserIdKeyManagerImplementation::ResetPinInternal(HWND__ *,ushort const *,ushort const *,NgcContainerOptions)

- ea: `0x18002d9d0`
- end: `0x18002dbcd`
- name: `?ResetPinInternal@UserIdKeyManagerImplementation@@EEAAJPEAUHWND__@@PEBG1W4NgcContainerOptions@@@Z`
- size: `509`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180016758`
- `0x18001a0d0`
- `0x180028670`
- `0x18002d9d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002dabe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002db0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002db76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002dabe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002db0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002db76`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002daa4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002daa4`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18002db2e`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18002db99`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18002db2e`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18002db99`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002db01`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002db01`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18002daed`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18002daed`
- `dsreg!NgcRegisterKey` at `0x18002db6a`
- `dsreg!NgcRegisterKey` at `0x18002db6a`
- `dsreg!DsrGetJoinInfo` at `0x18002da0c`
- `dsreg!DsrGetJoinInfo` at `0x18002da0c`

## pseudocode

```c
__int64 __fastcall UserIdKeyManagerImplementation::ResetPinInternal(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  int JoinInfo; // eax
  unsigned int v9; // ebx
  HANDLE CurrentProcess; // rax
  struct _ACL *v12; // rbx
  HANDLE v13; // rax
  unsigned int v14; // eax
  struct _ACL *v15; // rbx
  unsigned int v16; // edi
  HANDLE v17; // rax
  int nSubAuthority2; // [rsp+20h] [rbp-81h]
  PACL ppDacl; // [rsp+60h] [rbp-41h] BYREF
  PSID pSid; // [rsp+68h] [rbp-39h] BYREF
  PACL NewAcl; // [rsp+70h] [rbp-31h] BYREF
  __int64 v22; // [rsp+78h] [rbp-29h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+80h] [rbp-21h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+88h] [rbp-19h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B8h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v22 = 0;
  JoinInfo = DsrGetJoinInfo(0, &v22);
  v9 = JoinInfo;
  if ( JoinInfo >= 0 )
  {
    *(_QWORD *)(&pListOfExplicitEntries.Trustee.TrusteeType + 1) = 0;
    HIDWORD(pListOfExplicitEntries.Trustee.ptstrName) = 0;
    memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 20);
    pListOfExplicitEntries.grfAccessPermissions = 4096;
    *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 1;
    pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_COMPUTER;
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
    pSid = 0;
    AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid);
    pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
    ppSecurityDescriptor = 0;
    ppDacl = 0;
    NewAcl = 0;
    CurrentProcess = GetCurrentProcess();
    GetSecurityInfo(CurrentProcess, SE_KERNEL_OBJECT, 4u, 0, 0, &ppDacl, 0, &ppSecurityDescriptor);
    SetEntriesInAclW(1u, &pListOfExplicitEntries, ppDacl, &NewAcl);
    v12 = NewAcl;
    v13 = GetCurrentProcess();
    SetSecurityInfo(v13, SE_KERNEL_OBJECT, 4u, 0, 0, v12, 0);
    v14 = NgcRegisterKey(a5, a3, *(_QWORD *)(v22 + 32), 0, a4, a2, 0, SmartObj<void *>::Free, 0, 0);
    v15 = ppDacl;
    v16 = v14;
    v17 = GetCurrentProcess();
    SetSecurityInfo(v17, SE_KERNEL_OBJECT, 4u, 0, 0, v15, 0);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
    return v16;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2CE,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\useridkeymanagerimplementation.cpp",
      (const char *)(unsigned int)JoinInfo,
      nSubAuthority2);
    return v9;
  }
}

```

## disassembly

```asm
0x18002d9d0  mov     [rsp-8+arg_0], rbx
0x18002d9d5  push    rbp
0x18002d9d6  push    rsi
0x18002d9d7  push    rdi
0x18002d9d8  push    r13
0x18002d9da  push    r14
0x18002d9dc  lea     rbp, [rsp-2Fh]
0x18002d9e1  sub     rsp, 0D0h
0x18002d9e8  mov     rax, cs:__security_cookie
0x18002d9ef  xor     rax, rsp
0x18002d9f2  mov     [rbp+4Fh+var_30], rax
0x18002d9f6  mov     rdi, rdx
0x18002d9f9  xor     r13d, r13d
0x18002d9fc  lea     rdx, [rbp+4Fh+var_78]
0x18002da00  mov     [rbp+4Fh+var_78], r13
0x18002da04  xor     ecx, ecx
0x18002da06  mov     r14, r9
0x18002da09  mov     rsi, r8
0x18002da0c  call    cs:__imp_DsrGetJoinInfo
0x18002da12  mov     ebx, eax
0x18002da14  test    eax, eax
0x18002da16  jns     short loc_18002DA37
0x18002da18  mov     rcx, [rbp+57h]; this
0x18002da1c  lea     r8, aOnecoreuapDsEx_12; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18002da23  mov     r9d, eax; char *
0x18002da26  mov     edx, 2CEh; void *
0x18002da2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002da30  mov     eax, ebx
0x18002da32  jmp     loc_18002DBAA
0x18002da37  mov     ebx, 1
0x18002da3c  mov     qword ptr [rbp+4Fh+pListOfExplicitEntries.Trustee+14h], r13
0x18002da40  lea     rax, [rbp+4Fh+var_88]
0x18002da44  mov     dword ptr [rbp+4Fh+pListOfExplicitEntries.Trustee.ptstrName+4], r13d
0x18002da48  mov     [rsp+0F0h+pSid], rax; pSid
0x18002da4d  lea     rcx, [rbp+4Fh+pIdentifierAuthority]; pIdentifierAuthority
0x18002da51  mov     [rsp+0F0h+nSubAuthority7], r13d; nSubAuthority7
0x18002da56  xorps   xmm0, xmm0
0x18002da59  mov     [rsp+0F0h+nSubAuthority6], r13d; nSubAuthority6
0x18002da5e  lea     r8d, [rbx+11h]; nSubAuthority0
0x18002da62  mov     [rsp+0F0h+nSubAuthority5], r13d; nSubAuthority5
0x18002da67  xor     r9d, r9d; nSubAuthority1
0x18002da6a  mov     [rsp+0F0h+nSubAuthority4], r13d; nSubAuthority4
0x18002da6f  mov     dl, bl; nSubAuthorityCount
0x18002da71  mov     [rsp+0F0h+nSubAuthority3], r13d; nSubAuthority3
0x18002da76  mov     [rsp+0F0h+nSubAuthority2], r13d; nSubAuthority2
0x18002da7b  movdqu  xmmword ptr [rbp+4Fh+pListOfExplicitEntries+0Ch], xmm0
0x18002da80  mov     [rbp+4Fh+pListOfExplicitEntries.grfAccessPermissions], 1000h
0x18002da87  mov     qword ptr [rbp+4Fh+pListOfExplicitEntries.grfAccessMode], rbx
0x18002da8b  mov     [rbp+4Fh+pListOfExplicitEntries.Trustee.TrusteeForm], r13d
0x18002da8f  mov     [rbp+4Fh+pListOfExplicitEntries.Trustee.TrusteeType], 8
0x18002da96  mov     dword ptr [rbp+4Fh+pIdentifierAuthority.Value], r13d
0x18002da9a  mov     word ptr [rbp+4Fh+pIdentifierAuthority.Value+4], 500h
0x18002daa0  mov     [rbp+4Fh+var_88], r13
0x18002daa4  call    cs:__imp_AllocateAndInitializeSid
0x18002daaa  mov     rax, [rbp+4Fh+var_88]
0x18002daae  mov     [rbp+4Fh+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18002dab2  mov     [rbp+4Fh+ppSecurityDescriptor], r13
0x18002dab6  mov     [rbp+4Fh+ppDacl], r13
0x18002daba  mov     [rbp+4Fh+NewAcl], r13
0x18002dabe  call    cs:__imp_GetCurrentProcess
0x18002dac4  xor     r9d, r9d; ppsidOwner
0x18002dac7  lea     edx, [rbx+5]; ObjectType
0x18002daca  mov     rcx, rax; handle
0x18002dacd  lea     r8d, [rbx+3]; SecurityInfo
0x18002dad1  lea     rax, [rbp+4Fh+ppSecurityDescriptor]
0x18002dad5  mov     qword ptr [rsp+0F0h+nSubAuthority5], rax; ppSecurityDescriptor
0x18002dada  lea     rax, [rbp+4Fh+ppDacl]
0x18002dade  mov     qword ptr [rsp+0F0h+nSubAuthority4], r13; ppSacl
0x18002dae3  mov     qword ptr [rsp+0F0h+nSubAuthority3], rax; ppDacl
0x18002dae8  mov     qword ptr [rsp+0F0h+nSubAuthority2], r13; ppsidGroup
0x18002daed  call    cs:__imp_GetSecurityInfo
0x18002daf3  mov     r8, [rbp+4Fh+ppDacl]; OldAcl
0x18002daf7  lea     r9, [rbp+4Fh+NewAcl]; NewAcl
0x18002dafb  lea     rdx, [rbp+4Fh+pListOfExplicitEntries]; pListOfExplicitEntries
0x18002daff  mov     ecx, ebx; cCountOfExplicitEntries
0x18002db01  call    cs:__imp_SetEntriesInAclW
0x18002db07  mov     rbx, [rbp+4Fh+NewAcl]
0x18002db0b  call    cs:__imp_GetCurrentProcess
0x18002db11  xor     r9d, r9d; psidOwner
0x18002db14  mov     qword ptr [rsp+0F0h+nSubAuthority4], r13; pSacl
0x18002db19  mov     qword ptr [rsp+0F0h+nSubAuthority3], rbx; pDacl
0x18002db1e  mov     rcx, rax; handle
0x18002db21  mov     qword ptr [rsp+0F0h+nSubAuthority2], r13; psidGroup
0x18002db26  lea     edx, [r9+6]; ObjectType
0x18002db2a  lea     r8d, [r9+4]; SecurityInfo
0x18002db2e  call    cs:__imp_SetSecurityInfo
0x18002db34  mov     r8, [rbp+4Fh+var_78]
0x18002db38  lea     rax, ?Free@?$SmartObj@PEAX@@UEAAXXZ; SmartObj<void *>::Free(void)
0x18002db3f  mov     ecx, [rbp+4Fh+arg_20]
0x18002db42  xor     r9d, r9d
0x18002db45  mov     qword ptr [rsp+0F0h+nSubAuthority7], r13
0x18002db4a  mov     rdx, rsi
0x18002db4d  mov     qword ptr [rsp+0F0h+nSubAuthority6], r13
0x18002db52  mov     r8, [r8+20h]
0x18002db56  mov     qword ptr [rsp+0F0h+nSubAuthority5], rax
0x18002db5b  mov     [rsp+0F0h+nSubAuthority4], r13d
0x18002db60  mov     qword ptr [rsp+0F0h+nSubAuthority3], rdi
0x18002db65  mov     qword ptr [rsp+0F0h+nSubAuthority2], r14
0x18002db6a  call    cs:__imp_NgcRegisterKey
0x18002db70  mov     rbx, [rbp+4Fh+ppDacl]
0x18002db74  mov     edi, eax
0x18002db76  call    cs:__imp_GetCurrentProcess
0x18002db7c  xor     r9d, r9d; psidOwner
0x18002db7f  mov     qword ptr [rsp+0F0h+nSubAuthority4], r13; pSacl
0x18002db84  mov     qword ptr [rsp+0F0h+nSubAuthority3], rbx; pDacl
0x18002db89  mov     rcx, rax; handle
0x18002db8c  mov     qword ptr [rsp+0F0h+nSubAuthority2], r13; psidGroup
0x18002db91  lea     edx, [r9+6]; ObjectType
0x18002db95  lea     r8d, [r9+4]; SecurityInfo
0x18002db99  call    cs:__imp_SetSecurityInfo
0x18002db9f  lea     rcx, [rbp+4Fh+var_88]
0x18002dba3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002dba8  mov     eax, edi
0x18002dbaa  mov     rcx, [rbp+4Fh+var_30]
0x18002dbae  xor     rcx, rsp; StackCookie
0x18002dbb1  call    __security_check_cookie
0x18002dbb6  mov     rbx, [rsp+0F0h+arg_0]
0x18002dbbe  add     rsp, 0D0h
0x18002dbc5  pop     r14
0x18002dbc7  pop     r13
0x18002dbc9  pop     rdi
0x18002dbca  pop     rsi
0x18002dbcb  pop     rbp
0x18002dbcc  retn
```
