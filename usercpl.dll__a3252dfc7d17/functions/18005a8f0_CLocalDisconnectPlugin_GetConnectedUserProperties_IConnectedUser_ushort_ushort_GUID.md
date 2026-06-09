# CLocalDisconnectPlugin::GetConnectedUserProperties(IConnectedUser *,ushort * *,ushort * *,_GUID *)

- ea: `0x18005a8f0`
- end: `0x18005aca5`
- name: `?GetConnectedUserProperties@CLocalDisconnectPlugin@@AEAAJPEAUIConnectedUser@@PEAPEAG1PEAU_GUID@@@Z`
- size: `949`
- prototype: `__int64 __fastcall(CLocalDisconnectPlugin *__hidden this, struct IConnectedUser *, unsigned __int16 **, unsigned __int16 **, struct _GUID *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180059ba8`
- `0x18005a6f0`
- `0x18005b6d0`

## callees

- `0x180006a74`
- `0x1800594ac`
- `0x18005a8f0`
- `0x18006dd30`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a9cd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005aa54`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005aacd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005aad7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005ab02`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005ab5e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005ab68`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005ac01`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005ac0b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005ac3a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005ac6a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a9cd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005aa54`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005aacd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005aad7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005ab02`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005ab5e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005ab68`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005ac01`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005ac0b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005ac3a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005ac6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005aa2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005aae0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ab71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005abd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ac14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ac60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005aa2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005aae0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ab71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005abd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ac14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ac60`

## string_xrefs

- `0x18005a953`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`
- `0x18005a9b5`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`
- `0x18005aa39`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`
- `0x18005aab5`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`
- `0x18005ab46`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`
- `0x18005abe6`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`

## pseudocode

```c
__int64 __fastcall CLocalDisconnectPlugin::GetConnectedUserProperties(
        CLocalDisconnectPlugin *this,
        struct IConnectedUser *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4,
        struct _GUID *a5)
{
  __int64 v7; // rax
  int v8; // eax
  unsigned int v9; // ebx
  void (*v10)(void); // rax
  int v12; // eax
  __int64 v13; // r8
  const char *v14; // r9
  void *v15; // rdi
  char *v16; // rdx
  int *v17; // rax
  void (*v18)(void); // rax
  struct _GUID *v19; // r14
  struct _GUID v20; // xmm6
  int v21; // eax
  unsigned __int16 *v22; // rbx
  int v23; // eax
  __int64 v24; // r8
  const char *v25; // r9
  unsigned int v26; // r15d
  char *v27; // rdx
  char *v28; // rax
  int v29; // [rsp+20h] [rbp-50h] BYREF
  char v30; // [rsp+28h] [rbp-48h] BYREF
  PROPVARIANT pvar[2]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v32; // [rsp+40h] [rbp-30h]
  PROPVARIANT v33[2]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v34; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  CLocalDisconnectPlugin *v36; // [rsp+A0h] [rbp+30h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp+38h] BYREF

  v36 = this;
  *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v7 = *(_QWORD *)a2;
  v36 = 0;
  v8 = (*(__int64 (__fastcall **)(struct IConnectedUser *, CLocalDisconnectPlugin **))(v7 + 24))(a2, &v36);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20C,
      (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
      (const char *)(unsigned int)v8,
      v29);
    if ( !v36 )
      return v9;
    v10 = *(void (**)(void))(*(_QWORD *)v36 + 16LL);
LABEL_6:
    v10();
    return v9;
  }
  v32 = 0;
  *(_OWORD *)pvar = 0;
  v12 = (*(__int64 (__fastcall **)(CLocalDisconnectPlugin *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v36 + 40LL))(
          v36,
          &PKEY_Identity_UserName,
          pvar);
  v9 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x212,
      (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
      (const char *)(unsigned int)v12,
      v29);
    PropVariantClear(pvar);
LABEL_10:
    if ( !v36 )
      return v9;
    v10 = *(void (**)(void))(*(_QWORD *)v36 + 16LL);
    goto LABEL_6;
  }
  v15 = 0;
  if ( LOWORD(pvar[0]) != 31 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v16 = (char *)pvar[1];
  if ( !pvar[1] )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v16 = (char *)pvar[1];
  }
  v17 = (int *)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                 &pv,
                 v16,
                 v13,
                 v14);
  if ( &v29 != v17 )
  {
    v15 = *(void **)v17;
    *(_QWORD *)v17 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( !v15 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x217,
      (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
      (const char *)0x8007000ELL,
      v29);
    PropVariantClear(pvar);
    if ( v36 )
    {
      v18 = *(void (**)(void))(*(_QWORD *)v36 + 16LL);
LABEL_45:
      v18();
      return 2147942414LL;
    }
    return 2147942414LL;
  }
  v19 = a5;
  v20 = 0;
  if ( a5 )
  {
    v34 = 0;
    *(_OWORD *)v33 = 0;
    v21 = (*(__int64 (__fastcall **)(CLocalDisconnectPlugin *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v36 + 40LL))(
            v36,
            &PKEY_Identity_ProviderID,
            v33);
    v9 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21D,
        (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
        (const char *)(unsigned int)v21,
        v29);
      PropVariantClear(v33);
      PropVariantClear(pvar);
      CoTaskMemFree(v15);
      goto LABEL_10;
    }
    if ( LOWORD(v33[0]) != 72 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v20 = *(struct _GUID *)v33[1];
    PropVariantClear(v33);
  }
  v22 = 0;
  if ( a4 )
  {
    v34 = 0;
    *(_OWORD *)v33 = 0;
    v23 = (*(__int64 (__fastcall **)(CLocalDisconnectPlugin *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v36 + 40LL))(
            v36,
            &PKEY_IdentityProvider_Name,
            v33);
    v26 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x226,
        (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
        (const char *)(unsigned int)v23,
        v29);
      PropVariantClear(v33);
      PropVariantClear(pvar);
      CoTaskMemFree(v15);
      if ( v36 )
        (*(void (__fastcall **)(CLocalDisconnectPlugin *))(*(_QWORD *)v36 + 16LL))(v36);
      return v26;
    }
    if ( LOWORD(v33[0]) != 31 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v27 = (char *)v33[1];
    if ( !v33[1] )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v27 = (char *)v33[1];
    }
    v28 = (char *)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                    &pv,
                    v27,
                    v24,
                    v25);
    if ( &v30 != v28 )
    {
      v22 = *(unsigned __int16 **)v28;
      *(_QWORD *)v28 = 0;
    }
    if ( pv )
      CoTaskMemFree(pv);
    if ( !v22 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22B,
        (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
        (const char *)0x8007000ELL,
        v29);
      PropVariantClear(v33);
      PropVariantClear(pvar);
      CoTaskMemFree(v15);
      if ( v36 )
      {
        v18 = *(void (**)(void))(*(_QWORD *)v36 + 16LL);
        goto LABEL_45;
      }
      return 2147942414LL;
    }
    PropVariantClear(v33);
  }
  *a3 = (unsigned __int16 *)v15;
  if ( v19 )
    *v19 = v20;
  if ( a4 )
  {
    *a4 = v22;
  }
  else if ( v22 )
  {
    CoTaskMemFree(v22);
  }
  PropVariantClear(pvar);
  if ( v36 )
    (*(void (__fastcall **)(CLocalDisconnectPlugin *))(*(_QWORD *)v36 + 16LL))(v36);
  return 0;
}

```

## disassembly

```asm
0x18005a8f0  mov     rax, rsp
0x18005a8f3  mov     [rax+18h], rbx
0x18005a8f7  mov     [rax+20h], rsi
0x18005a8fb  mov     [rax+8], rcx
0x18005a8ff  push    rbp
0x18005a900  push    rdi
0x18005a901  push    r12
0x18005a903  push    r14
0x18005a905  push    r15
0x18005a907  mov     rbp, rsp
0x18005a90a  sub     rsp, 70h
0x18005a90e  mov     rsi, r9
0x18005a911  movaps  xmmword ptr [rax-38h], xmm6
0x18005a915  mov     qword ptr [r8], 0
0x18005a91c  mov     r12, r8
0x18005a91f  mov     r9, rdx
0x18005a922  test    rsi, rsi
0x18005a925  jz      short loc_18005A92E
0x18005a927  mov     qword ptr [rsi], 0
0x18005a92e  mov     rax, [rdx]
0x18005a931  mov     rcx, r9
0x18005a934  lea     rdx, [rbp+arg_0]
0x18005a938  mov     [rbp+arg_0], 0
0x18005a940  mov     rax, [rax+18h]
0x18005a944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a949  mov     ebx, eax
0x18005a94b  test    eax, eax
0x18005a94d  jns     short loc_18005A983
0x18005a94f  mov     rcx, [rbp+28h]; this
0x18005a953  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x18005a95a  mov     r9d, eax; char *
0x18005a95d  mov     edx, 20Ch; void *
0x18005a962  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a967  mov     rcx, [rbp+arg_0]
0x18005a96b  test    rcx, rcx
0x18005a96e  jz      short loc_18005A97C
0x18005a970  mov     rdx, [rcx]
0x18005a973  mov     rax, [rdx+10h]
0x18005a977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a97c  mov     eax, ebx
0x18005a97e  jmp     loc_18005AC87
0x18005a983  mov     rcx, [rbp+arg_0]
0x18005a987  lea     r8, [rbp+pvar]
0x18005a98b  xor     eax, eax
0x18005a98d  lea     rdx, PKEY_Identity_UserName
0x18005a994  mov     [rbp+var_30], rax
0x18005a998  xorps   xmm0, xmm0
0x18005a99b  movups  xmmword ptr [rbp+pvar], xmm0
0x18005a99f  mov     rax, [rcx]
0x18005a9a2  mov     rax, [rax+28h]
0x18005a9a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a9ab  mov     ebx, eax
0x18005a9ad  test    eax, eax
0x18005a9af  jns     short loc_18005A9E5
0x18005a9b1  mov     rcx, [rbp+28h]; this
0x18005a9b5  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x18005a9bc  mov     r9d, eax; char *
0x18005a9bf  mov     edx, 212h; void *
0x18005a9c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a9c9  lea     rcx, [rbp+pvar]; pvar
0x18005a9cd  call    cs:__imp_PropVariantClear
0x18005a9d3  mov     rcx, [rbp+arg_0]
0x18005a9d7  test    rcx, rcx
0x18005a9da  jz      short loc_18005A97C
0x18005a9dc  mov     rax, [rcx]
0x18005a9df  mov     rax, [rax+10h]
0x18005a9e3  jmp     short loc_18005A977
0x18005a9e5  xor     edi, edi
0x18005a9e7  cmp     word ptr [rbp+pvar], 1Fh
0x18005a9ec  jz      short loc_18005A9F3
0x18005a9ee  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005a9f3  mov     rdx, [rbp+pvar+8]
0x18005a9f7  test    rdx, rdx
0x18005a9fa  jnz     short loc_18005AA05
0x18005a9fc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005aa01  mov     rdx, [rbp+pvar+8]
0x18005aa05  lea     rcx, [rbp+pv]
0x18005aa09  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18005aa0e  lea     rcx, [rbp+var_50]
0x18005aa12  cmp     rcx, rax
0x18005aa15  jz      short loc_18005AA21
0x18005aa17  mov     rdi, [rax]
0x18005aa1a  mov     qword ptr [rax], 0
0x18005aa21  mov     rcx, [rbp+pv]; pv
0x18005aa25  test    rcx, rcx
0x18005aa28  jz      short loc_18005AA30
0x18005aa2a  call    cs:__imp_CoTaskMemFree
0x18005aa30  test    rdi, rdi
0x18005aa33  jnz     short loc_18005AA73
0x18005aa35  mov     rcx, [rbp+28h]; this
0x18005aa39  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x18005aa40  mov     r9d, 8007000Eh; char *
0x18005aa46  mov     edx, 217h; void *
0x18005aa4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005aa50  lea     rcx, [rbp+pvar]; pvar
0x18005aa54  call    cs:__imp_PropVariantClear
0x18005aa5a  mov     rcx, [rbp+arg_0]
0x18005aa5e  test    rcx, rcx
0x18005aa61  jz      loc_18005AC2F
0x18005aa67  mov     rax, [rcx]
0x18005aa6a  mov     rax, [rax+10h]
0x18005aa6e  jmp     loc_18005AC2A
0x18005aa73  mov     r14, [rbp+arg_20]
0x18005aa77  xorps   xmm6, xmm6
0x18005aa7a  test    r14, r14
0x18005aa7d  jz      loc_18005AB08
0x18005aa83  mov     rcx, [rbp+arg_0]
0x18005aa87  lea     r8, [rbp+var_28]
0x18005aa8b  xor     eax, eax
0x18005aa8d  lea     rdx, PKEY_Identity_ProviderID
0x18005aa94  mov     [rbp+var_18], rax
0x18005aa98  xorps   xmm0, xmm0
0x18005aa9b  movups  xmmword ptr [rbp+var_28], xmm0
0x18005aa9f  mov     rax, [rcx]
0x18005aaa2  mov     rax, [rax+28h]
0x18005aaa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aaab  mov     ebx, eax
0x18005aaad  test    eax, eax
0x18005aaaf  jns     short loc_18005AAEB
0x18005aab1  mov     rcx, [rbp+28h]; this
0x18005aab5  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x18005aabc  mov     r9d, eax; char *
0x18005aabf  mov     edx, 21Dh; void *
0x18005aac4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005aac9  lea     rcx, [rbp+var_28]; pvar
0x18005aacd  call    cs:__imp_PropVariantClear
0x18005aad3  lea     rcx, [rbp+pvar]; pvar
0x18005aad7  call    cs:__imp_PropVariantClear
0x18005aadd  mov     rcx, rdi; pv
0x18005aae0  call    cs:__imp_CoTaskMemFree
0x18005aae6  jmp     loc_18005A9D3
0x18005aaeb  cmp     word ptr [rbp+var_28], 48h ; 'H'
0x18005aaf0  jz      short loc_18005AAF7
0x18005aaf2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005aaf7  mov     rax, [rbp+var_28+8]
0x18005aafb  lea     rcx, [rbp+var_28]; pvar
0x18005aaff  movups  xmm6, xmmword ptr [rax]
0x18005ab02  call    cs:__imp_PropVariantClear
0x18005ab08  xor     ebx, ebx
0x18005ab0a  test    rsi, rsi
0x18005ab0d  jz      loc_18005AC40
0x18005ab13  mov     rcx, [rbp+arg_0]
0x18005ab17  lea     r8, [rbp+var_28]
0x18005ab1b  xor     eax, eax
0x18005ab1d  lea     rdx, PKEY_IdentityProvider_Name
0x18005ab24  mov     [rbp+var_18], rax
0x18005ab28  xorps   xmm0, xmm0
0x18005ab2b  movups  xmmword ptr [rbp+var_28], xmm0
0x18005ab2f  mov     rax, [rcx]
0x18005ab32  mov     rax, [rax+28h]
0x18005ab36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ab3b  mov     r15d, eax
0x18005ab3e  test    eax, eax
0x18005ab40  jns     short loc_18005AB94
0x18005ab42  mov     rcx, [rbp+28h]; this
0x18005ab46  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x18005ab4d  mov     r9d, eax; char *
0x18005ab50  mov     edx, 226h; void *
0x18005ab55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ab5a  lea     rcx, [rbp+var_28]; pvar
0x18005ab5e  call    cs:__imp_PropVariantClear
0x18005ab64  lea     rcx, [rbp+pvar]; pvar
0x18005ab68  call    cs:__imp_PropVariantClear
0x18005ab6e  mov     rcx, rdi; pv
0x18005ab71  call    cs:__imp_CoTaskMemFree
0x18005ab77  mov     rcx, [rbp+arg_0]
0x18005ab7b  test    rcx, rcx
0x18005ab7e  jz      short loc_18005AB8C
0x18005ab80  mov     rax, [rcx]
0x18005ab83  mov     rax, [rax+10h]
0x18005ab87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ab8c  mov     eax, r15d
0x18005ab8f  jmp     loc_18005AC87
0x18005ab94  cmp     word ptr [rbp+var_28], 1Fh
0x18005ab99  jz      short loc_18005ABA0
0x18005ab9b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005aba0  mov     rdx, [rbp+var_28+8]
0x18005aba4  test    rdx, rdx
0x18005aba7  jnz     short loc_18005ABB2
0x18005aba9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005abae  mov     rdx, [rbp+var_28+8]
0x18005abb2  lea     rcx, [rbp+pv]
0x18005abb6  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18005abbb  lea     rcx, [rbp+var_48]
0x18005abbf  cmp     rcx, rax
0x18005abc2  jz      short loc_18005ABCE
0x18005abc4  mov     rbx, [rax]
0x18005abc7  mov     qword ptr [rax], 0
0x18005abce  mov     rcx, [rbp+pv]; pv
0x18005abd2  test    rcx, rcx
0x18005abd5  jz      short loc_18005ABDD
0x18005abd7  call    cs:__imp_CoTaskMemFree
0x18005abdd  test    rbx, rbx
0x18005abe0  jnz     short loc_18005AC36
0x18005abe2  mov     rcx, [rbp+28h]; this
0x18005abe6  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x18005abed  mov     r9d, 8007000Eh; char *
0x18005abf3  mov     edx, 22Bh; void *
0x18005abf8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005abfd  lea     rcx, [rbp+var_28]; pvar
0x18005ac01  call    cs:__imp_PropVariantClear
0x18005ac07  lea     rcx, [rbp+pvar]; pvar
0x18005ac0b  call    cs:__imp_PropVariantClear
0x18005ac11  mov     rcx, rdi; pv
0x18005ac14  call    cs:__imp_CoTaskMemFree
0x18005ac1a  mov     rcx, [rbp+arg_0]
0x18005ac1e  test    rcx, rcx
0x18005ac21  jz      short loc_18005AC2F
0x18005ac23  mov     rdx, [rcx]
0x18005ac26  mov     rax, [rdx+10h]
0x18005ac2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ac2f  mov     eax, 8007000Eh
0x18005ac34  jmp     short loc_18005AC87
0x18005ac36  lea     rcx, [rbp+var_28]; pvar
0x18005ac3a  call    cs:__imp_PropVariantClear
0x18005ac40  mov     [r12], rdi
0x18005ac44  test    r14, r14
0x18005ac47  jz      short loc_18005AC4E
0x18005ac49  movdqu  xmmword ptr [r14], xmm6
0x18005ac4e  test    rsi, rsi
0x18005ac51  jz      short loc_18005AC58
0x18005ac53  mov     [rsi], rbx
0x18005ac56  jmp     short loc_18005AC66
0x18005ac58  test    rbx, rbx
0x18005ac5b  jz      short loc_18005AC66
0x18005ac5d  mov     rcx, rbx; pv
0x18005ac60  call    cs:__imp_CoTaskMemFree
0x18005ac66  lea     rcx, [rbp+pvar]; pvar
0x18005ac6a  call    cs:__imp_PropVariantClear
0x18005ac70  mov     rcx, [rbp+arg_0]
0x18005ac74  test    rcx, rcx
0x18005ac77  jz      short loc_18005AC85
0x18005ac79  mov     rax, [rcx]
0x18005ac7c  mov     rax, [rax+10h]
0x18005ac80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ac85  xor     eax, eax
0x18005ac87  movaps  xmm6, [rsp+70h+var_10]
0x18005ac8c  lea     r11, [rsp+70h+var_s0]
0x18005ac91  mov     rbx, [r11+40h]
0x18005ac95  mov     rsi, [r11+48h]
0x18005ac99  mov     rsp, r11
0x18005ac9c  pop     r15
0x18005ac9e  pop     r14
0x18005aca0  pop     r12
0x18005aca2  pop     rdi
0x18005aca3  pop     rbp
0x18005aca4  retn
```
