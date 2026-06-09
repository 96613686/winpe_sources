# IsCandidateUser(uchar *)

- ea: `0x14000e3cc`
- end: `0x14000e547`
- name: `?IsCandidateUser@@YAJPEAE@Z`
- size: `379`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140012f54`

## callees

- `0x140003164`
- `0x1400045a0`
- `0x140004ba4`
- `0x14000813c`
- `0x14000815c`
- `0x14000cfe4`
- `0x14000e044`
- `0x14000e3cc`
- `0x14000f774`

## import_xrefs

- `ADVAPI32!ConvertStringSidToSidW` at `0x14000e46a`
- `ADVAPI32!ConvertStringSidToSidW` at `0x14000e46a`
- `KERNEL32!LocalFree` at `0x14000e445`
- `KERNEL32!LocalFree` at `0x14000e445`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsEphemeralCandidateUser` at `0x14000e500`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsEphemeralCandidateUser` at `0x14000e500`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x14000e4c8`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x14000e4c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall IsCandidateUser(unsigned __int8 *a1)
{
  void *v2; // rcx
  int UserSidFromToken; // eax
  unsigned int LastError; // ebx
  HLOCAL v5; // rbx
  const char *v6; // r9
  int v8; // eax
  int IsEphemeralCandidateUser; // eax
  int v10[4]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  int v12; // [rsp+50h] [rbp+20h] BYREF
  int v13; // [rsp+58h] [rbp+28h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp+30h] BYREF
  LPCWSTR StringSid; // [rsp+68h] [rbp+38h] BYREF

  *a1 = 0;
  if ( !(unsigned __int8)IsCamIsEphemeralCandidateUserPresent()
    || !(unsigned __int8)IsCamIsEphemeralCandidateUserPresent() )
  {
    return 0;
  }
  hMem = 0;
  StringSid = 0;
  UserSidFromToken = GetUserSidFromToken(v2, (unsigned __int16 **)&StringSid);
  LastError = UserSidFromToken;
  if ( UserSidFromToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecore\\internal\\shell\\inc\\private\\candidateuserhelpers.h",
      (const char *)(unsigned int)UserSidFromToken,
      v10[0]);
LABEL_9:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
    return LastError;
  }
  v5 = hMem;
  if ( hMem )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v10);
    LocalFree(v5);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v10);
  }
  hMem = 0;
  if ( !ConvertStringSidToSidW(StringSid, &hMem) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2F,
                  (unsigned int)"onecore\\internal\\shell\\inc\\private\\candidateuserhelpers.h",
                  v6);
    goto LABEL_9;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  v12 = 0;
  v13 = 0;
  v8 = CamIsCandidateUser(hMem, &v12);
  if ( v8 >= 0 )
  {
    if ( v12 )
      goto LABEL_16;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecore\\internal\\shell\\inc\\private\\candidateuserhelpers.h",
      (const char *)(unsigned int)v8,
      v10[0]);
  }
  IsEphemeralCandidateUser = CamIsEphemeralCandidateUser(hMem, &v13);
  if ( IsEphemeralCandidateUser >= 0 )
  {
    if ( !v13 )
      goto LABEL_17;
LABEL_16:
    *a1 = 1;
    goto LABEL_17;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x35,
    (unsigned int)"onecore\\internal\\shell\\inc\\private\\candidateuserhelpers.h",
    (const char *)(unsigned int)IsEphemeralCandidateUser,
    v10[0]);
LABEL_17:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
  return 0;
}

```

## disassembly

```asm
0x14000e3cc  push    rbp
0x14000e3ce  push    rbx
0x14000e3cf  push    rdi
0x14000e3d0  mov     rbp, rsp
0x14000e3d3  sub     rsp, 30h
0x14000e3d7  mov     rdi, rcx
0x14000e3da  mov     byte ptr [rcx], 0
0x14000e3dd  call    IsCamIsEphemeralCandidateUserPresent
0x14000e3e2  test    al, al
0x14000e3e4  jz      loc_14000E53C
0x14000e3ea  call    IsCamIsEphemeralCandidateUserPresent
0x14000e3ef  test    al, al
0x14000e3f1  jz      loc_14000E53C
0x14000e3f7  mov     [rbp+hMem], 0
0x14000e3ff  mov     [rbp+StringSid], 0
0x14000e407  lea     rdx, [rbp+StringSid]; unsigned __int16 **
0x14000e40b  call    ?GetUserSidFromToken@@YAJQEAXPEAPEAG@Z; GetUserSidFromToken(void * const,ushort * *)
0x14000e410  mov     ebx, eax
0x14000e412  test    eax, eax
0x14000e414  jns     short loc_14000E430
0x14000e416  mov     rcx, [rbp+18h]; this
0x14000e41a  mov     r9d, eax; char *
0x14000e41d  lea     r8, aOnecoreInterna_2; "onecore\\internal\\shell\\inc\\private"...
0x14000e424  mov     edx, 2Eh ; '.'; void *
0x14000e429  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e42e  jmp     short loc_14000E48F
0x14000e430  mov     rbx, [rbp+hMem]
0x14000e434  test    rbx, rbx
0x14000e437  jz      short loc_14000E45A
0x14000e439  lea     rcx, [rbp+var_10]; this
0x14000e43d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000e442  mov     rcx, rbx; hMem
0x14000e445  call    cs:__imp_LocalFree
0x14000e44c  nop     dword ptr [rax+rax+00h]
0x14000e451  lea     rcx, [rbp+var_10]; this
0x14000e455  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000e45a  mov     [rbp+hMem], 0
0x14000e462  lea     rdx, [rbp+hMem]; Sid
0x14000e466  mov     rcx, [rbp+StringSid]; StringSid
0x14000e46a  call    cs:__imp_ConvertStringSidToSidW
0x14000e471  nop     dword ptr [rax+rax+00h]
0x14000e476  test    eax, eax
0x14000e478  jnz     short loc_14000E4A9
0x14000e47a  mov     rcx, [rbp+18h]; this
0x14000e47e  lea     r8, aOnecoreInterna_2; "onecore\\internal\\shell\\inc\\private"...
0x14000e485  lea     edx, [rax+2Fh]; void *
0x14000e488  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000e48d  mov     ebx, eax
0x14000e48f  lea     rcx, [rbp+StringSid]
0x14000e493  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14000e498  nop
0x14000e499  lea     rcx, [rbp+hMem]
0x14000e49d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14000e4a2  mov     eax, ebx
0x14000e4a4  jmp     loc_14000E53E
0x14000e4a9  lea     rcx, [rbp+StringSid]
0x14000e4ad  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14000e4b2  mov     [rbp+arg_0], 0
0x14000e4b9  mov     [rbp+arg_8], 0
0x14000e4c0  lea     rdx, [rbp+arg_0]
0x14000e4c4  mov     rcx, [rbp+hMem]
0x14000e4c8  call    cs:__imp_CamIsCandidateUser
0x14000e4cf  nop     dword ptr [rax+rax+00h]
0x14000e4d4  mov     rcx, [rbp+18h]; this
0x14000e4d8  test    eax, eax
0x14000e4da  jns     short loc_14000E4F2
0x14000e4dc  mov     r9d, eax; char *
0x14000e4df  lea     r8, aOnecoreInterna_2; "onecore\\internal\\shell\\inc\\private"...
0x14000e4e6  mov     edx, 34h ; '4'; void *
0x14000e4eb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000e4f0  jmp     short loc_14000E4F8
0x14000e4f2  cmp     [rbp+arg_0], 0
0x14000e4f6  jnz     short loc_14000E530
0x14000e4f8  lea     rdx, [rbp+arg_8]
0x14000e4fc  mov     rcx, [rbp+hMem]
0x14000e500  call    cs:__imp_CamIsEphemeralCandidateUser
0x14000e507  nop     dword ptr [rax+rax+00h]
0x14000e50c  mov     rcx, [rbp+18h]; this
0x14000e510  test    eax, eax
0x14000e512  jns     short loc_14000E52A
0x14000e514  mov     r9d, eax; char *
0x14000e517  lea     r8, aOnecoreInterna_2; "onecore\\internal\\shell\\inc\\private"...
0x14000e51e  mov     edx, 35h ; '5'; void *
0x14000e523  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000e528  jmp     short loc_14000E533
0x14000e52a  cmp     [rbp+arg_8], 0
0x14000e52e  jz      short loc_14000E533
0x14000e530  mov     byte ptr [rdi], 1
0x14000e533  lea     rcx, [rbp+hMem]
0x14000e537  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14000e53c  xor     eax, eax
0x14000e53e  add     rsp, 30h
0x14000e542  pop     rdi
0x14000e543  pop     rbx
0x14000e544  pop     rbp
0x14000e545  retn
```
