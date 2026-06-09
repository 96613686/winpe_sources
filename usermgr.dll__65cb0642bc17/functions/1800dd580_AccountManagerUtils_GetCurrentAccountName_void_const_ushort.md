# AccountManagerUtils::GetCurrentAccountName(void * const,ushort * *)

- ea: `0x1800dd580`
- end: `0x1800dd75f`
- name: `?GetCurrentAccountName@AccountManagerUtils@@YAJQEAXPEAPEAG@Z`
- size: `479`
- prototype: `__int64 __fastcall(PSID Sid, void *const, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013500`
- `0x180066c08`

## callees

- `0x1800088e8`
- `0x180014e7c`
- `0x180014e9c`
- `0x18004aa68`
- `0x180061e1c`
- `0x1800d72bc`
- `0x1800dd580`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd5f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd5f8`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800dd5cc`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800dd6d4`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800dd5cc`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800dd6d4`

## string_xrefs

- `0x1800dd5da`: `onecore\ds\security\umstartup\accountmanagerutils\accountmanagerutils.cpp`
- `0x1800dd607`: `onecore\ds\security\umstartup\accountmanagerutils\accountmanagerutils.cpp`
- `0x1800dd649`: `onecore\ds\security\umstartup\accountmanagerutils\accountmanagerutils.cpp`
- `0x1800dd68e`: `onecore\ds\security\umstartup\accountmanagerutils\accountmanagerutils.cpp`
- `0x1800dd6e2`: `onecore\ds\security\umstartup\accountmanagerutils\accountmanagerutils.cpp`
- `0x1800dd71b`: `onecore\ds\security\umstartup\accountmanagerutils\accountmanagerutils.cpp`

## pseudocode

```c
__int64 __fastcall AccountManagerUtils::GetCurrentAccountName(PSID Sid, LPWSTR *a2, unsigned __int16 **a3)
{
  unsigned int LastError; // ebx
  const char *v6; // r9
  __int64 v8; // r8
  const char *v9; // r9
  int v10; // eax
  __int64 v11; // r8
  const char *v12; // r9
  int v13; // eax
  LPWSTR v14; // rbx
  const char *v15; // r9
  int cchReferencedDomainName; // [rsp+20h] [rbp-20h]
  const char *peUse; // [rsp+28h] [rbp-18h]
  LPWSTR ReferencedDomainName; // [rsp+30h] [rbp-10h] BYREF
  LPWSTR Name; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD v21; // [rsp+68h] [rbp+28h] BYREF
  DWORD cchName; // [rsp+70h] [rbp+30h] BYREF
  enum _SID_NAME_USE v23; // [rsp+78h] [rbp+38h] BYREF

  *a2 = 0;
  cchName = 0;
  v21 = 0;
  v23 = 0;
  if ( !LookupAccountSidLocalW(Sid, 0, &cchName, 0, &v21, &v23) )
  {
    if ( GetLastError() != 122 )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x1A,
               (unsigned int)"onecore\\ds\\security\\umstartup\\accountmanagerutils\\accountmanagerutils.cpp",
               v6);
    Name = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &Name,
      0);
    v10 = CamAllocBuffer<unsigned short>(2LL * cchName, (char **)&Name, v8, v9);
    LastError = v10;
    if ( v10 >= 0 )
    {
      ReferencedDomainName = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &ReferencedDomainName,
        0);
      v13 = CamAllocBuffer<unsigned short>(2LL * v21, (char **)&ReferencedDomainName, v11, v12);
      LastError = v13;
      if ( v13 >= 0 )
      {
        v14 = Name;
        if ( LookupAccountSidLocalW(Sid, Name, &cchName, ReferencedDomainName, &v21, &v23) )
        {
          if ( v23 != SidTypeWellKnownGroup )
          {
            Name = 0;
            *a2 = v14;
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ReferencedDomainName);
            LastError = 0;
            goto LABEL_15;
          }
          LastError = -2147418113;
          LODWORD(peUse) = 5;
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x23,
            (unsigned int)"onecore\\ds\\security\\umstartup\\accountmanagerutils\\accountmanagerutils.cpp",
            (const char *)0x8000FFFFLL,
            (int)"unexpected account type (%x)",
            peUse);
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x22,
                        (unsigned int)"onecore\\ds\\security\\umstartup\\accountmanagerutils\\accountmanagerutils.cpp",
                        v15);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x20,
          (unsigned int)"onecore\\ds\\security\\umstartup\\accountmanagerutils\\accountmanagerutils.cpp",
          (const char *)(unsigned int)v13,
          cchReferencedDomainName);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ReferencedDomainName);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D,
        (unsigned int)"onecore\\ds\\security\\umstartup\\accountmanagerutils\\accountmanagerutils.cpp",
        (const char *)(unsigned int)v10,
        cchReferencedDomainName);
    }
LABEL_15:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Name);
    return LastError;
  }
  LastError = -2147418113;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x19,
    (unsigned int)"onecore\\ds\\security\\umstartup\\accountmanagerutils\\accountmanagerutils.cpp",
    (const char *)0x8000FFFFLL,
    cchReferencedDomainName);
  return LastError;
}

```

## disassembly

```asm
0x1800dd580  mov     [rsp-18h+arg_0], rbx
0x1800dd585  push    rbp
0x1800dd586  push    rsi
0x1800dd587  push    rdi
0x1800dd588  mov     rbp, rsp
0x1800dd58b  sub     rsp, 40h
0x1800dd58f  lea     rax, [rbp+arg_18]
0x1800dd593  mov     qword ptr [rdx], 0
0x1800dd59a  mov     [rsp+40h+peUse], rax; peUse
0x1800dd59f  lea     r8, [rbp+cchName]; cchName
0x1800dd5a3  lea     rax, [rbp+arg_8]
0x1800dd5a7  mov     [rbp+cchName], 0
0x1800dd5ae  mov     rdi, rdx
0x1800dd5b1  mov     [rsp+40h+cchReferencedDomainName], rax; int
0x1800dd5b6  xor     r9d, r9d; ReferencedDomainName
0x1800dd5b9  mov     [rbp+arg_8], 0
0x1800dd5c0  xor     edx, edx; Name
0x1800dd5c2  mov     [rbp+arg_18], 0
0x1800dd5c9  mov     rsi, rcx
0x1800dd5cc  call    cs:__imp_LookupAccountSidLocalW
0x1800dd5d2  test    eax, eax
0x1800dd5d4  jz      short loc_1800DD5F8
0x1800dd5d6  mov     rcx, [rbp+18h]; this
0x1800dd5da  lea     r8, aOnecoreDsSecur_78; "onecore\\ds\\security\\umstartup\\accou"...
0x1800dd5e1  mov     ebx, 8000FFFFh
0x1800dd5e6  mov     edx, 19h; void *
0x1800dd5eb  mov     r9d, ebx; char *
0x1800dd5ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dd5f3  jmp     loc_1800DD750
0x1800dd5f8  call    cs:__imp_GetLastError
0x1800dd5fe  cmp     eax, 7Ah ; 'z'
0x1800dd601  jz      short loc_1800DD61D
0x1800dd603  mov     rcx, [rbp+18h]; this
0x1800dd607  lea     r8, aOnecoreDsSecur_78; "onecore\\ds\\security\\umstartup\\accou"...
0x1800dd60e  mov     edx, 1Ah; void *
0x1800dd613  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800dd618  jmp     loc_1800DD752
0x1800dd61d  xor     edx, edx
0x1800dd61f  mov     [rbp+Name], 0
0x1800dd627  lea     rcx, [rbp+Name]
0x1800dd62b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800dd630  mov     ecx, [rbp+cchName]
0x1800dd633  lea     rdx, [rbp+Name]
0x1800dd637  add     rcx, rcx
0x1800dd63a  call    ??$CamAllocBuffer@G@@YAJ_KPEAPEAG@Z; CamAllocBuffer<ushort>(unsigned __int64,ushort * *)
0x1800dd63f  mov     ebx, eax
0x1800dd641  test    eax, eax
0x1800dd643  jns     short loc_1800DD662
0x1800dd645  mov     rcx, [rbp+18h]; this
0x1800dd649  lea     r8, aOnecoreDsSecur_78; "onecore\\ds\\security\\umstartup\\accou"...
0x1800dd650  mov     r9d, eax; char *
0x1800dd653  mov     edx, 1Dh; void *
0x1800dd658  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dd65d  jmp     loc_1800DD747
0x1800dd662  xor     edx, edx
0x1800dd664  mov     [rbp+ReferencedDomainName], 0
0x1800dd66c  lea     rcx, [rbp+ReferencedDomainName]
0x1800dd670  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800dd675  mov     ecx, [rbp+arg_8]
0x1800dd678  lea     rdx, [rbp+ReferencedDomainName]
0x1800dd67c  add     rcx, rcx
0x1800dd67f  call    ??$CamAllocBuffer@G@@YAJ_KPEAPEAG@Z; CamAllocBuffer<ushort>(unsigned __int64,ushort * *)
0x1800dd684  mov     ebx, eax
0x1800dd686  test    eax, eax
0x1800dd688  jns     short loc_1800DD6B0
0x1800dd68a  mov     rcx, [rbp+18h]; this
0x1800dd68e  lea     r8, aOnecoreDsSecur_78; "onecore\\ds\\security\\umstartup\\accou"...
0x1800dd695  mov     r9d, eax; char *
0x1800dd698  mov     edx, 20h ; ' '; void *
0x1800dd69d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dd6a2  lea     rcx, [rbp+ReferencedDomainName]
0x1800dd6a6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800dd6ab  jmp     loc_1800DD747
0x1800dd6b0  mov     rbx, [rbp+Name]
0x1800dd6b4  lea     rax, [rbp+arg_18]
0x1800dd6b8  mov     r9, [rbp+ReferencedDomainName]; ReferencedDomainName
0x1800dd6bc  lea     r8, [rbp+cchName]; cchName
0x1800dd6c0  mov     [rsp+40h+peUse], rax; peUse
0x1800dd6c5  mov     rdx, rbx; Name
0x1800dd6c8  lea     rax, [rbp+arg_8]
0x1800dd6cc  mov     rcx, rsi; Sid
0x1800dd6cf  mov     [rsp+40h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800dd6d4  call    cs:__imp_LookupAccountSidLocalW
0x1800dd6da  test    eax, eax
0x1800dd6dc  jnz     short loc_1800DD6F5
0x1800dd6de  mov     rcx, [rbp+18h]; this
0x1800dd6e2  lea     r8, aOnecoreDsSecur_78; "onecore\\ds\\security\\umstartup\\accou"...
0x1800dd6e9  lea     edx, [rax+22h]; void *
0x1800dd6ec  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800dd6f1  mov     ebx, eax
0x1800dd6f3  jmp     short loc_1800DD6A2
0x1800dd6f5  cmp     [rbp+arg_18], 5
0x1800dd6f9  jnz     short loc_1800DD731
0x1800dd6fb  mov     rcx, [rbp+18h]; this
0x1800dd6ff  lea     rax, aUnexpectedAcco; "unexpected account type (%x)"
0x1800dd706  mov     ebx, 8000FFFFh
0x1800dd70b  mov     dword ptr [rsp+40h+peUse], 5; char *
0x1800dd713  mov     r9d, ebx; char *
0x1800dd716  mov     [rsp+40h+cchReferencedDomainName], rax; int
0x1800dd71b  lea     r8, aOnecoreDsSecur_78; "onecore\\ds\\security\\umstartup\\accou"...
0x1800dd722  mov     edx, 23h ; '#'; void *
0x1800dd727  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800dd72c  jmp     loc_1800DD6A2
0x1800dd731  lea     rcx, [rbp+ReferencedDomainName]
0x1800dd735  mov     [rbp+Name], 0
0x1800dd73d  mov     [rdi], rbx
0x1800dd740  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800dd745  xor     ebx, ebx
0x1800dd747  lea     rcx, [rbp+Name]
0x1800dd74b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800dd750  mov     eax, ebx
0x1800dd752  mov     rbx, [rsp+40h+arg_0]
0x1800dd757  add     rsp, 40h
0x1800dd75b  pop     rdi
0x1800dd75c  pop     rsi
0x1800dd75d  pop     rbp
0x1800dd75e  retn
```
