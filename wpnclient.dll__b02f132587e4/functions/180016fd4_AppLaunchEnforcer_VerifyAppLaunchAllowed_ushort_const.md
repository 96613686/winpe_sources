# AppLaunchEnforcer::VerifyAppLaunchAllowed(ushort const *)

- ea: `0x180016fd4`
- end: `0x18001713a`
- name: `?VerifyAppLaunchAllowed@AppLaunchEnforcer@@QEAA_NPEBG@Z`
- size: `358`
- prototype: `bool __fastcall(AppLaunchEnforcer *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180016e44`

## callees

- `0x180016fd4`
- `0x18001b848`
- `0x18001b9e0`
- `0x18001cb0c`
- `0x18001cc24`
- `0x18001ff00`
- `0x180024a84`

## import_xrefs

- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180017036`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180017036`
- `ntdll!RtlInitUnicodeString` at `0x180017009`
- `ntdll!RtlInitUnicodeString` at `0x180017009`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x1800170c5`
- `api-ms-win-appmodel-identity-l1-2-0!AppXGetPackageCapabilities` at `0x180017086`
- `api-ms-win-appmodel-identity-l1-2-0!AppXGetPackageCapabilities` at `0x180017086`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800170f9`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800170f9`

## string_xrefs

- `0x180016ffe`: `storeAppInstall`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall AppLaunchEnforcer::VerifyAppLaunchAllowed(AppLaunchEnforcer *this, const unsigned __int16 *a2)
{
  int v3; // eax
  void *v4; // rdx
  unsigned int v5; // r8d
  int v6; // eax
  unsigned int i; // ebx
  int v9; // [rsp+20h] [rbp-59h] BYREF
  unsigned int v10; // [rsp+24h] [rbp-55h] BYREF
  __int64 v11; // [rsp+28h] [rbp-51h] BYREF
  __int64 v12; // [rsp+30h] [rbp-49h] BYREF
  __int64 v13; // [rsp+38h] [rbp-41h] BYREF
  __int64 *v14; // [rsp+40h] [rbp-39h] BYREF
  __int64 v15; // [rsp+48h] [rbp-31h] BYREF
  char v16; // [rsp+50h] [rbp-29h]
  _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-21h] BYREF
  _OWORD pSid2[3]; // [rsp+68h] [rbp-11h] BYREF
  _OWORD v19[3]; // [rsp+98h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"storeAppInstall");
  memset(v19, 0, 44);
  memset(pSid2, 0, sizeof(pSid2));
  v3 = RtlDeriveCapabilitySidsFromName(&DestinationString, v19, pSid2);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(retaddr, v4, v5, (const char *)(unsigned int)v3, v9);
  v9 = 0;
  v11 = 0;
  v10 = 0;
  v14 = &v11;
  v15 = 0;
  v16 = 1;
  v6 = AppXGetPackageCapabilities(a2, &v9, &v15, &v10);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\applaunchenforcer.cpp",
      (const char *)(unsigned int)v6,
      v9);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SID_AND_ATTRIBUTES *,void (void *),&void AppXFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_SID_AND_ATTRIBUTES *,_SID_AND_ATTRIBUTES *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SID_AND_ATTRIBUTES *,void (void *),&void AppXFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_SID_AND_ATTRIBUTES *,_SID_AND_ATTRIBUTES *,0,std::nullptr_t>>>>(&v14);
  if ( v9 )
  {
    if ( v11 )
    {
      v12 = v11;
      v13 = AppXFreeMemory;
      wistd::invoke<void (*)(void *),_SID_AND_ATTRIBUTES * &>(&v13, &v12);
    }
    return 1;
  }
  else
  {
    for ( i = 0; i < v10; ++i )
    {
      if ( EqualSid(*(PSID *)(v11 + 16LL * i), pSid2) )
      {
        wil::details::unique_storage<wil::details::resource_policy<_SID_AND_ATTRIBUTES *,void (void *),&void AppXFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_SID_AND_ATTRIBUTES *,_SID_AND_ATTRIBUTES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SID_AND_ATTRIBUTES *,void (void *),&void AppXFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_SID_AND_ATTRIBUTES *,_SID_AND_ATTRIBUTES *,0,std::nullptr_t>>(&v11);
        return 1;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_SID_AND_ATTRIBUTES *,void (void *),&void AppXFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_SID_AND_ATTRIBUTES *,_SID_AND_ATTRIBUTES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SID_AND_ATTRIBUTES *,void (void *),&void AppXFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_SID_AND_ATTRIBUTES *,_SID_AND_ATTRIBUTES *,0,std::nullptr_t>>(&v11);
    return 0;
  }
}

```

## disassembly

```asm
0x180016fd4  mov     [rsp-8+arg_0], rbx
0x180016fd9  push    rbp
0x180016fda  lea     rbp, [rsp-57h]
0x180016fdf  sub     rsp, 0D0h
0x180016fe6  mov     rax, cs:__security_cookie
0x180016fed  xor     rax, rsp
0x180016ff0  mov     [rbp+57h+var_8], rax
0x180016ff4  mov     rbx, rdx
0x180016ff7  xorps   xmm0, xmm0
0x180016ffa  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180016ffe  lea     rdx, SourceString; "storeAppInstall"
0x180017005  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180017009  call    cs:__imp_RtlInitUnicodeString
0x18001700f  xorps   xmm0, xmm0
0x180017012  movups  [rbp+57h+var_38], xmm0
0x180017016  movups  xmmword ptr [rbp+57h+var_28], xmm0
0x18001701a  movups  xmmword ptr [rbp+57h+var_28+0Ch], xmm0
0x18001701e  movups  [rbp+57h+pSid2], xmm0
0x180017022  movups  [rbp+57h+var_58], xmm0
0x180017026  movups  [rbp+57h+var_48], xmm0
0x18001702a  lea     r8, [rbp+57h+pSid2]
0x18001702e  lea     rdx, [rbp+57h+var_38]
0x180017032  lea     rcx, [rbp+57h+DestinationString]
0x180017036  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x18001703c  mov     rcx, [rbp+5Fh]; this
0x180017040  test    eax, eax
0x180017042  jns     short loc_18001704D
0x180017044  mov     r9d, eax; char *
0x180017047  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18001704d  mov     [rbp+57h+var_B0], 0
0x180017054  mov     [rbp+57h+var_A8], 0
0x18001705c  mov     [rbp+57h+var_AC], 0
0x180017063  lea     rax, [rbp+57h+var_A8]
0x180017067  mov     [rbp+57h+var_90], rax
0x18001706b  mov     [rbp+57h+var_88], 0
0x180017073  mov     [rbp+57h+var_80], 1
0x180017077  lea     r9, [rbp+57h+var_AC]
0x18001707b  lea     r8, [rbp+57h+var_88]
0x18001707f  lea     rdx, [rbp+57h+var_B0]
0x180017083  mov     rcx, rbx
0x180017086  call    cs:__imp_AppXGetPackageCapabilities
0x18001708c  mov     rcx, [rbp+5Fh]; this
0x180017090  test    eax, eax
0x180017092  jns     short loc_1800170A9
0x180017094  mov     r9d, eax; char *
0x180017097  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001709e  mov     edx, 1Eh; void *
0x1800170a3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800170a9  lea     rcx, [rbp+57h+var_90]
0x1800170ad  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_SID_AND_ATTRIBUTES@@$$A6AXPEAX@Z$1?AppXFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SID_AND_ATTRIBUTES *,void (void *),&AppXFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_SID_AND_ATTRIBUTES *,_SID_AND_ATTRIBUTES *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SID_AND_ATTRIBUTES *,void (void *),&AppXFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_SID_AND_ATTRIBUTES *,_SID_AND_ATTRIBUTES *,0,std::nullptr_t>>>>(void)
0x1800170b2  cmp     [rbp+57h+var_B0], 0
0x1800170b6  jz      short loc_1800170E1
0x1800170b8  mov     rcx, [rbp+57h+var_A8]
0x1800170bc  test    rcx, rcx
0x1800170bf  jz      short loc_1800170DD
0x1800170c1  mov     [rbp+57h+var_A0], rcx
0x1800170c5  mov     rcx, cs:__imp_AppXFreeMemory
0x1800170cc  mov     [rbp+57h+var_98], rcx
0x1800170d0  lea     rdx, [rbp+57h+var_A0]
0x1800170d4  lea     rcx, [rbp+57h+var_98]
0x1800170d8  call    ??$invoke@P6AXPEAX@ZAEAPEAU_SID_AND_ATTRIBUTES@@@wistd@@YAX$$QEAP6AXPEAX@ZAEAPEAU_SID_AND_ATTRIBUTES@@@Z; wistd::invoke<void (*)(void *),_SID_AND_ATTRIBUTES * &>(void (*&&)(void *),_SID_AND_ATTRIBUTES * &)
0x1800170dd  mov     al, 1
0x1800170df  jmp     short loc_18001711D
0x1800170e1  xor     ebx, ebx
0x1800170e3  cmp     ebx, [rbp+57h+var_AC]
0x1800170e6  jnb     short loc_180017112
0x1800170e8  mov     eax, ebx
0x1800170ea  add     rax, rax
0x1800170ed  lea     rdx, [rbp+57h+pSid2]; pSid2
0x1800170f1  mov     rcx, [rbp+57h+var_A8]
0x1800170f5  mov     rcx, [rcx+rax*8]; pSid1
0x1800170f9  call    cs:__imp_EqualSid
0x1800170ff  test    eax, eax
0x180017101  jnz     short loc_180017107
0x180017103  inc     ebx
0x180017105  jmp     short loc_1800170E3
0x180017107  lea     rcx, [rbp+57h+var_A8]
0x18001710b  call    ??1?$unique_storage@U?$resource_policy@PEAU_SID_AND_ATTRIBUTES@@$$A6AXPEAX@Z$1?AppXFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SID_AND_ATTRIBUTES *,void (void *),&AppXFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_SID_AND_ATTRIBUTES *,_SID_AND_ATTRIBUTES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SID_AND_ATTRIBUTES *,void (void *),&AppXFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_SID_AND_ATTRIBUTES *,_SID_AND_ATTRIBUTES *,0,std::nullptr_t>>(void)
0x180017110  jmp     short loc_1800170DD
0x180017112  lea     rcx, [rbp+57h+var_A8]
0x180017116  call    ??1?$unique_storage@U?$resource_policy@PEAU_SID_AND_ATTRIBUTES@@$$A6AXPEAX@Z$1?AppXFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SID_AND_ATTRIBUTES *,void (void *),&AppXFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_SID_AND_ATTRIBUTES *,_SID_AND_ATTRIBUTES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SID_AND_ATTRIBUTES *,void (void *),&AppXFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_SID_AND_ATTRIBUTES *,_SID_AND_ATTRIBUTES *,0,std::nullptr_t>>(void)
0x18001711b  xor     al, al
0x18001711d  mov     rcx, [rbp+57h+var_8]
0x180017121  xor     rcx, rsp; StackCookie
0x180017124  call    __security_check_cookie
0x180017129  mov     rbx, [rsp+0D0h+arg_0]
0x180017131  add     rsp, 0D0h
0x180017138  pop     rbp
0x180017139  retn
```
