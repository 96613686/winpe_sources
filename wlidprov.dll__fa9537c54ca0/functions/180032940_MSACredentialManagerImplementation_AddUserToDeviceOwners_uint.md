# MSACredentialManagerImplementation::AddUserToDeviceOwners(uint)

- ea: `0x180032940`
- end: `0x180032b36`
- name: `?AddUserToDeviceOwners@MSACredentialManagerImplementation@@UEAAJI@Z`
- size: `502`
- prototype: `__int64 __fastcall(MSACredentialManagerImplementation *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180016758`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180021e84`
- `0x180028630`
- `0x180028670`
- `0x180032940`
- `0x180034440`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800329e6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800329e6`
- `samcli!NetLocalGroupAddMembers` at `0x180032aa8`
- `samcli!NetLocalGroupAddMembers` at `0x180032aa8`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180032a76`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180032a76`

## pseudocode

```c
__int64 __fastcall MSACredentialManagerImplementation::AddUserToDeviceOwners(
        MSACredentialManagerImplementation *this,
        unsigned int a2)
{
  int UserSidFromUserId; // eax
  unsigned int LastError; // ebx
  const char *v4; // r9
  __int64 v5; // rdx
  signed int v6; // eax
  __int64 v7; // rdx
  int nSubAuthority2; // [rsp+20h] [rbp-E0h]
  int nSubAuthority2a; // [rsp+20h] [rbp-E0h]
  PSID Sid; // [rsp+60h] [rbp-A0h] BYREF
  _SID_NAME_USE peUse; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchReferencedDomainName; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-90h] BYREF
  void *v15; // [rsp+78h] [rbp-88h] BYREF
  BYTE buf[8]; // [rsp+80h] [rbp-80h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+88h] [rbp-78h] BYREF
  WCHAR ReferencedDomainName[8]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v19; // [rsp+A0h] [rbp-60h]
  WCHAR Name[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v15 = 0;
  UserSidFromUserId = GetUserSidFromUserId(a2, &v15);
  LastError = UserSidFromUserId;
  if ( UserSidFromUserId >= 0 )
  {
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
    Sid = 0;
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x247u, 0, 0, 0, 0, 0, 0, &Sid) )
    {
      cchName = 256;
      memset_0(Name, 0, 0x202u);
      cchReferencedDomainName = 15;
      peUse = 0;
      *(_OWORD *)ReferencedDomainName = 0;
      v19 = 0;
      if ( LookupAccountSidW(0, Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
      {
        *(_QWORD *)buf = v15;
        v6 = NetLocalGroupAddMembers(0, Name, 0, buf, 1u);
        LastError = v6;
        if ( v6 == 2220 )
        {
          LastError = -2147023728;
          v7 = 1046;
        }
        else
        {
          if ( !v6 )
          {
            wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
            LastError = 0;
            goto LABEL_18;
          }
          if ( v6 > 0 )
            LastError = (unsigned __int16)v6 | 0x80070000;
          if ( (LastError & 0x80000000) == 0 )
            goto LABEL_6;
          v7 = 1047;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v7,
          (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
          (const char *)LastError,
          nSubAuthority2a);
LABEL_6:
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
        goto LABEL_18;
      }
      v5 = 1040;
    }
    else
    {
      v5 = 1032;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v5,
                  (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
                  v4);
    goto LABEL_6;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3FB,
    (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
    (const char *)(unsigned int)UserSidFromUserId,
    nSubAuthority2);
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
  return LastError;
}

```

## disassembly

```asm
0x180032940  mov     [rsp-8+arg_0], rbx
0x180032945  mov     [rsp-8+arg_10], rdi
0x18003294a  push    rbp
0x18003294b  lea     rbp, [rsp-1D0h]
0x180032953  sub     rsp, 2D0h
0x18003295a  mov     rax, cs:__security_cookie
0x180032961  xor     rax, rsp
0x180032964  mov     [rbp+1D0h+var_10], rax
0x18003296b  mov     ecx, edx; unsigned int
0x18003296d  xor     edi, edi
0x18003296f  lea     rdx, [rsp+2D0h+var_258]; void **
0x180032974  mov     [rsp+2D0h+var_258], rdi
0x180032979  call    ?GetUserSidFromUserId@@YAJIPEAPEAX@Z; GetUserSidFromUserId(uint,void * *)
0x18003297e  mov     ebx, eax
0x180032980  test    eax, eax
0x180032982  jns     short loc_1800329A4
0x180032984  mov     rcx, [rbp+1D8h]; this
0x18003298b  lea     r8, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180032992  mov     r9d, eax; char *
0x180032995  mov     edx, 3FBh; void *
0x18003299a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003299f  jmp     loc_180032B06
0x1800329a4  lea     rax, [rsp+2D0h+Sid]
0x1800329a9  mov     dword ptr [rbp+1D0h+pIdentifierAuthority.Value], edi
0x1800329ac  mov     [rsp+2D0h+pSid], rax; pSid
0x1800329b1  lea     rcx, [rbp+1D0h+pIdentifierAuthority]; pIdentifierAuthority
0x1800329b5  mov     [rsp+2D0h+nSubAuthority7], edi; nSubAuthority7
0x1800329b9  mov     r9d, 247h; nSubAuthority1
0x1800329bf  mov     [rsp+2D0h+nSubAuthority6], edi; nSubAuthority6
0x1800329c3  mov     r8d, 20h ; ' '; nSubAuthority0
0x1800329c9  mov     [rsp+2D0h+nSubAuthority5], edi; nSubAuthority5
0x1800329cd  mov     dl, 2; nSubAuthorityCount
0x1800329cf  mov     [rsp+2D0h+nSubAuthority4], edi; nSubAuthority4
0x1800329d3  mov     [rsp+2D0h+nSubAuthority3], edi; nSubAuthority3
0x1800329d7  mov     [rsp+2D0h+nSubAuthority2], edi; nSubAuthority2
0x1800329db  mov     word ptr [rbp+1D0h+pIdentifierAuthority.Value+4], 500h
0x1800329e1  mov     [rsp+2D0h+Sid], rdi
0x1800329e6  call    cs:__imp_AllocateAndInitializeSid
0x1800329ec  test    eax, eax
0x1800329ee  jnz     short loc_180032A19
0x1800329f0  mov     edx, 408h; void *
0x1800329f5  mov     rcx, [rbp+1D8h]; this
0x1800329fc  lea     r8, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180032a03  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180032a08  mov     ebx, eax
0x180032a0a  lea     rcx, [rsp+2D0h+Sid]
0x180032a0f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180032a14  jmp     loc_180032B06
0x180032a19  xor     edx, edx; Val
0x180032a1b  mov     [rsp+2D0h+cchName], 100h
0x180032a23  mov     r8d, 202h; Size
0x180032a29  lea     rcx, [rbp+1D0h+Name]; void *
0x180032a2d  call    memset_0
0x180032a32  mov     rdx, [rsp+2D0h+Sid]; Sid
0x180032a37  lea     rax, [rsp+2D0h+peUse]
0x180032a3c  mov     qword ptr [rsp+2D0h+nSubAuthority4], rax; peUse
0x180032a41  lea     r9, [rsp+2D0h+cchName]; cchName
0x180032a46  xorps   xmm0, xmm0
0x180032a49  mov     [rsp+2D0h+cchReferencedDomainName], 0Fh
0x180032a51  lea     rax, [rsp+2D0h+cchReferencedDomainName]
0x180032a56  mov     [rsp+2D0h+peUse], edi
0x180032a5a  mov     qword ptr [rsp+2D0h+nSubAuthority3], rax; cchReferencedDomainName
0x180032a5f  lea     r8, [rbp+1D0h+Name]; Name
0x180032a63  lea     rax, [rbp+1D0h+ReferencedDomainName]
0x180032a67  xor     ecx, ecx; lpSystemName
0x180032a69  mov     qword ptr [rsp+2D0h+nSubAuthority2], rax; ReferencedDomainName
0x180032a6e  movups  xmmword ptr [rbp+1D0h+ReferencedDomainName], xmm0
0x180032a72  movups  [rbp+1D0h+var_230], xmm0
0x180032a76  call    cs:__imp_LookupAccountSidW
0x180032a7c  test    eax, eax
0x180032a7e  jnz     short loc_180032A8A
0x180032a80  mov     edx, 410h
0x180032a85  jmp     loc_1800329F5
0x180032a8a  mov     rax, [rsp+2D0h+var_258]
0x180032a8f  lea     r9, [rbp+1D0h+buf]; buf
0x180032a93  xor     r8d, r8d; level
0x180032a96  mov     qword ptr [rbp+1D0h+buf], rax
0x180032a9a  lea     rdx, [rbp+1D0h+Name]; groupname
0x180032a9e  mov     [rsp+2D0h+nSubAuthority2], 1; int
0x180032aa6  xor     ecx, ecx; servername
0x180032aa8  call    cs:__imp_NetLocalGroupAddMembers
0x180032aae  mov     ebx, eax
0x180032ab0  cmp     eax, 8ACh
0x180032ab5  jnz     short loc_180032ADC
0x180032ab7  mov     ebx, 80070490h
0x180032abc  mov     edx, 416h; void *
0x180032ac1  mov     rcx, [rbp+1D8h]; this
0x180032ac8  lea     r8, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180032acf  mov     r9d, ebx; char *
0x180032ad2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032ad7  jmp     loc_180032A0A
0x180032adc  test    eax, eax
0x180032ade  jz      short loc_180032AFA
0x180032ae0  jle     short loc_180032AEB
0x180032ae2  movzx   ebx, ax
0x180032ae5  or      ebx, 80070000h
0x180032aeb  test    ebx, ebx
0x180032aed  jns     loc_180032A0A
0x180032af3  mov     edx, 417h
0x180032af8  jmp     short loc_180032AC1
0x180032afa  lea     rcx, [rsp+2D0h+Sid]
0x180032aff  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180032b04  mov     ebx, edi
0x180032b06  lea     rcx, [rsp+2D0h+var_258]
0x180032b0b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180032b10  mov     eax, ebx
0x180032b12  mov     rcx, [rbp+1D0h+var_10]
0x180032b19  xor     rcx, rsp; StackCookie
0x180032b1c  call    __security_check_cookie
0x180032b21  lea     r11, [rsp+2D0h+var_s0]
0x180032b29  mov     rbx, [r11+10h]
0x180032b2d  mov     rdi, [r11+20h]
0x180032b31  mov     rsp, r11
0x180032b34  pop     rbp
0x180032b35  retn
```
