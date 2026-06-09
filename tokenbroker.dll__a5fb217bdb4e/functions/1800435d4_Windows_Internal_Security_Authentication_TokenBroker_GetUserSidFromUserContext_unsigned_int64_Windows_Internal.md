# Windows::Internal::Security::Authentication::TokenBroker::GetUserSidFromUserContext(unsigned __int64,Windows::Internal::String &)

- ea: `0x1800435d4`
- end: `0x1800437d6`
- name: `?GetUserSidFromUserContext@TokenBroker@Authentication@Security@Internal@Windows@@YAJ_KAEAVString@45@@Z`
- size: `514`
- prototype: `__int64 __fastcall(Windows::Internal::Security::Authentication::TokenBroker *__hidden this, unsigned __int64, struct Windows::Internal::String *)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180070660`
- `0x1800734e8`
- `0x1800f0260`

## callees

- `0x18000bd40`
- `0x18001a510`
- `0x180024000`
- `0x1800286a4`
- `0x18003df30`
- `0x1800435d4`
- `0x1800437e0`
- `0x1800565a0`
- `0x18008e690`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180043686`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180043686`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043690`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043704`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043690`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043704`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043781`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043781`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043722`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043722`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180043614`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180043614`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800436f6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800436f6`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18004363b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18004363b`

## string_xrefs

- `0x180043734`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800437ad`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::GetUserSidFromUserContext(
        Windows::Internal::Security::Authentication::TokenBroker *this,
        __int64 a2,
        struct Windows::Internal::String *a3)
{
  int v5; // eax
  unsigned __int64 *v6; // rdx
  unsigned int v7; // ebx
  __int64 v8; // rcx
  signed int LastError; // eax
  HANDLE v10; // rcx
  bool v11; // cc
  void *v13; // rbx
  signed int v14; // eax
  int v15; // eax
  int ReturnLength; // [rsp+20h] [rbp-59h]
  int ReturnLengtha; // [rsp+20h] [rbp-59h]
  HANDLE hObject; // [rsp+30h] [rbp-49h] BYREF
  Windows::Internal::Security::Authentication::TokenBroker *v19; // [rsp+38h] [rbp-41h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-39h] BYREF
  DWORD v21; // [rsp+48h] [rbp-31h] BYREF
  void *TokenInformation; // [rsp+50h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  LODWORD(v19) = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v19, 0);
  hObject = 0;
  v5 = UMgrQueryUserToken(this, &hObject);
  v7 = v5;
  if ( v5 != -2147023584 )
  {
    if ( v5 >= 0 )
      goto LABEL_3;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA23,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)v7,
      ReturnLength);
    v10 = hObject;
    v11 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_9:
    if ( v11 )
      CloseHandle(v10);
    return v7;
  }
  v19 = 0;
  if ( (int)Windows::Internal::Security::Authentication::TokenBroker::GetCurrentUserContext(
              (Windows::Internal::Security::Authentication::TokenBroker *)&v19,
              v6) < 0
    || this != v19 )
  {
    goto LABEL_17;
  }
LABEL_3:
  v21 = 0;
  v8 = (__int64)hObject;
  if ( !hObject )
    v8 = -6;
  if ( !GetTokenInformation((HANDLE)v8, TokenUser, &TokenInformation, 0x54u, &v21) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
LABEL_8:
    v10 = hObject;
    v11 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
    goto LABEL_9;
  }
  v13 = TokenInformation;
  StringSid = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  if ( !ConvertSidToStringSidW(v13, &StringSid) )
  {
    v14 = GetLastError();
    v7 = v14;
    if ( v14 > 0 )
      v7 = (unsigned __int16)v14 | 0x80070000;
    if ( StringSid )
      LocalFree(StringSid);
    goto LABEL_8;
  }
  v19 = (Windows::Internal::Security::Authentication::TokenBroker *)StringSid;
  v15 = Windows::Internal::String::Initialize<unsigned short *>(a2, &v19);
  v7 = v15;
  if ( v15 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA32,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)(unsigned int)v15,
      ReturnLengtha);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
  Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&hObject);
  return v7;
}

```

## disassembly

```asm
0x1800435d4  mov     [rsp-8+arg_10], rbx
0x1800435d9  push    rbp
0x1800435da  push    rsi
0x1800435db  push    rdi
0x1800435dc  lea     rbp, [rsp-47h]
0x1800435e1  sub     rsp, 0C0h
0x1800435e8  mov     rax, cs:__security_cookie
0x1800435ef  xor     rax, rsp
0x1800435f2  mov     [rbp+57h+var_20], rax
0x1800435f6  mov     rsi, rdx
0x1800435f9  mov     rdi, rcx
0x1800435fc  mov     [rbp+57h+hObject], 0
0x180043604  mov     dword ptr [rbp+57h+var_98], 0
0x18004360b  xor     r8d, r8d
0x18004360e  lea     rdx, [rbp+57h+var_98]
0x180043612  xor     ecx, ecx
0x180043614  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18004361a  mov     rcx, [rbp+57h+hObject]; hObject
0x18004361e  lea     rax, [rcx-1]
0x180043622  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180043626  jbe     loc_180043757
0x18004362c  mov     [rbp+57h+hObject], 0
0x180043634  lea     rdx, [rbp+57h+hObject]
0x180043638  mov     rcx, rdi
0x18004363b  call    cs:__imp_UMgrQueryUserToken
0x180043641  mov     ebx, eax
0x180043643  cmp     eax, 80070520h
0x180043648  jz      loc_180043761
0x18004364e  test    eax, eax
0x180043650  js      loc_18004372D
0x180043656  mov     [rbp+57h+var_88], 0
0x18004365d  mov     rcx, [rbp+57h+hObject]
0x180043661  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180043668  test    rcx, rcx
0x18004366b  cmovz   rcx, rax; TokenHandle
0x18004366f  lea     rax, [rbp+57h+var_88]
0x180043673  mov     qword ptr [rsp+0D0h+ReturnLength], rax; int
0x180043678  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18004367e  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180043682  lea     edx, [r9-53h]; TokenInformationClass
0x180043686  call    cs:__imp_GetTokenInformation
0x18004368c  test    eax, eax
0x18004368e  jnz     short loc_1800436D8
0x180043690  call    cs:__imp_GetLastError
0x180043696  mov     ebx, eax
0x180043698  test    eax, eax
0x18004369a  jle     short loc_1800436A5
0x18004369c  movzx   ebx, ax
0x18004369f  or      ebx, 80070000h
0x1800436a5  mov     rcx, [rbp+57h+hObject]; hObject
0x1800436a9  lea     rdx, [rcx-1]
0x1800436ad  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800436b1  jbe     loc_180043781
0x1800436b7  mov     eax, ebx
0x1800436b9  mov     rcx, [rbp+57h+var_20]
0x1800436bd  xor     rcx, rsp; StackCookie
0x1800436c0  call    __security_check_cookie
0x1800436c5  mov     rbx, [rsp+0D0h+arg_10]
0x1800436cd  add     rsp, 0C0h
0x1800436d4  pop     rdi
0x1800436d5  pop     rsi
0x1800436d6  pop     rbp
0x1800436d7  retn
0x1800436d8  mov     rbx, [rbp+57h+TokenInformation]
0x1800436dc  mov     [rbp+57h+StringSid], 0
0x1800436e4  xor     edx, edx
0x1800436e6  lea     rcx, [rbp+57h+StringSid]
0x1800436ea  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800436ef  lea     rdx, [rbp+57h+StringSid]; StringSid
0x1800436f3  mov     rcx, rbx; Sid
0x1800436f6  call    cs:__imp_ConvertSidToStringSidW
0x1800436fc  test    eax, eax
0x1800436fe  jnz     loc_18004378C
0x180043704  call    cs:__imp_GetLastError
0x18004370a  mov     ebx, eax
0x18004370c  test    eax, eax
0x18004370e  jle     short loc_180043719
0x180043710  movzx   ebx, ax
0x180043713  or      ebx, 80070000h
0x180043719  mov     rcx, [rbp+57h+StringSid]; hMem
0x18004371d  test    rcx, rcx
0x180043720  jz      short loc_1800436A5
0x180043722  call    cs:__imp_LocalFree
0x180043728  jmp     loc_1800436A5
0x18004372d  mov     rcx, [rbp+5Fh]; this
0x180043731  mov     r9d, ebx; char *
0x180043734  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18004373b  mov     edx, 0A23h; void *
0x180043740  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043745  nop
0x180043746  mov     rcx, [rbp+57h+hObject]
0x18004374a  lea     rax, [rcx-1]
0x18004374e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180043752  jmp     loc_1800436B1
0x180043757  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18004375c  jmp     loc_18004362C
0x180043761  mov     [rbp+57h+var_98], 0
0x180043769  lea     rcx, [rbp+57h+var_98]; this
0x18004376d  call    ?GetCurrentUserContext@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEA_K@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCurrentUserContext(unsigned __int64 *)
0x180043772  test    eax, eax
0x180043774  js      short loc_18004372D
0x180043776  cmp     rdi, [rbp+57h+var_98]
0x18004377a  jnz     short loc_18004372D
0x18004377c  jmp     loc_180043656
0x180043781  call    cs:__imp_CloseHandle
0x180043787  jmp     loc_1800436B7
0x18004378c  mov     rax, [rbp+57h+StringSid]
0x180043790  mov     [rbp+57h+var_98], rax
0x180043794  lea     rdx, [rbp+57h+var_98]
0x180043798  mov     rcx, rsi
0x18004379b  call    ??$Initialize@PEAG@String@Internal@Windows@@QEAAJAEBQEAGUdummy_t@_StringDetail@12@@Z; Windows::Internal::String::Initialize<ushort *>(ushort * const &,Windows::Internal::_StringDetail::dummy_t)
0x1800437a0  mov     ebx, eax
0x1800437a2  test    eax, eax
0x1800437a4  jns     short loc_1800437BE
0x1800437a6  mov     rcx, [rbp+5Fh]; this
0x1800437aa  mov     r9d, eax; char *
0x1800437ad  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800437b4  mov     edx, 0A32h; void *
0x1800437b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800437be  lea     rcx, [rbp+57h+StringSid]
0x1800437c2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800437c7  nop
0x1800437c8  lea     rcx, [rbp+57h+hObject]; this
0x1800437cc  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x1800437d1  jmp     loc_1800436B7
```
