# CLocalDisconnectPlugin::DisconnectLocalUser(IUserData * *)

- ea: `0x180059ba8`
- end: `0x18005a096`
- name: `?DisconnectLocalUser@CLocalDisconnectPlugin@@AEAAJPEAPEAUIUserData@@@Z`
- size: `1262`
- prototype: `__int64 __fastcall(CLocalDisconnectPlugin *__hidden this, struct IUserData **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005a0d0`

## callees

- `0x180006a74`
- `0x1800594ac`
- `0x180059ba8`
- `0x18005a8f0`
- `0x18005acac`
- `0x180069000`
- `0x1800753b0`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059d31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059e31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059ee4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a024`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059d31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059e31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059ee4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a024`
- `OLEAUT32!__imp_SysFreeString` at `0x180059dbb`
- `OLEAUT32!__imp_SysFreeString` at `0x180059e62`
- `OLEAUT32!__imp_SysFreeString` at `0x180059edb`
- `OLEAUT32!__imp_SysFreeString` at `0x180059fb2`
- `OLEAUT32!__imp_SysFreeString` at `0x180059dbb`
- `OLEAUT32!__imp_SysFreeString` at `0x180059e62`
- `OLEAUT32!__imp_SysFreeString` at `0x180059edb`
- `OLEAUT32!__imp_SysFreeString` at `0x180059fb2`

## string_xrefs

- `0x180059c51`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`
- `0x180059cd8`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`
- `0x180059d14`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`
- `0x180059d9e`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`
- `0x180059e40`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`
- `0x180059ebe`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`
- `0x180059f2a`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`
- `0x180059fed`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`

## pseudocode

```c
__int64 __fastcall CLocalDisconnectPlugin::DisconnectLocalUser(CLocalDisconnectPlugin *this, struct IUserData **a2)
{
  struct IUserManager *v4; // rcx
  struct IUserManager *v5; // rbx
  int v6; // eax
  CLocalDisconnectPlugin *v7; // rcx
  unsigned int v8; // ebx
  void (*v9)(void); // rax
  void (*v10)(void); // rax
  int CurrentConnectedUser; // eax
  CLocalDisconnectPlugin *v13; // rcx
  void *v14; // rbx
  int v15; // edi
  int ConnectedUserProperties; // eax
  int v17; // eax
  __int64 v18; // r8
  const char *v19; // r9
  LPVOID *v20; // rax
  void *v21; // rdi
  int v22; // eax
  __int64 v23; // rdx
  struct IConnectedUser *v24; // rcx
  int v25; // eax
  struct IUserData *v26; // rax
  struct IUserData *v27; // rcx
  int v28; // [rsp+20h] [rbp-29h]
  int v29; // [rsp+20h] [rbp-29h]
  int v30; // [rsp+20h] [rbp-29h]
  struct IUserManager *v31; // [rsp+30h] [rbp-19h] BYREF
  struct IUserData *v32; // [rsp+38h] [rbp-11h] BYREF
  struct IConnectedUser *v33; // [rsp+40h] [rbp-9h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-1h] BYREF
  int v35[2]; // [rsp+50h] [rbp+7h] BYREF
  LPVOID pv; // [rsp+58h] [rbp+Fh] BYREF
  int v37; // [rsp+60h] [rbp+17h] BYREF
  LPVOID v38; // [rsp+68h] [rbp+1Fh] BYREF
  GUID pguid; // [rsp+70h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  *a2 = 0;
  v31 = 0;
  if ( CBasePlugin::RetrieveUserManagerFromStream((CLocalDisconnectPlugin *)((char *)this + 56), &v31) >= 0 )
    goto LABEL_6;
  v4 = (struct IUserManager *)*((_QWORD *)this + 8);
  v5 = v31;
  v31 = v4;
  if ( v4 )
  {
    (*(void (__fastcall **)(struct IUserManager *))(*(_QWORD *)v4 + 8LL))(v4);
    v4 = v31;
  }
  if ( v5 )
  {
    (*(void (__fastcall **)(struct IUserManager *))(*(_QWORD *)v5 + 16LL))(v5);
LABEL_6:
    v4 = v31;
  }
  v32 = 0;
  v6 = (*(__int64 (__fastcall **)(struct IUserManager *, struct IUserData **))(*(_QWORD *)v4 + 48LL))(v4, &v32);
  v8 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x264,
      (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
      (const char *)(unsigned int)v6,
      v28);
    if ( !v32 )
    {
LABEL_11:
      if ( !v31 )
        return v8;
      v10 = *(void (**)(void))(*(_QWORD *)v31 + 16LL);
LABEL_13:
      v10();
      return v8;
    }
    v9 = *(void (**)(void))(*(_QWORD *)v32 + 16LL);
LABEL_10:
    v9();
    goto LABEL_11;
  }
  v33 = 0;
  CurrentConnectedUser = CLocalDisconnectPlugin::GetCurrentConnectedUser(v7, v32, &v33);
  v14 = 0;
  pv = 0;
  v15 = CurrentConnectedUser;
  pguid = 0;
  if ( CurrentConnectedUser == -805305819 || CurrentConnectedUser == -805306268 )
  {
    v37 = 0;
    bstrString = 0;
    v17 = (*(__int64 (__fastcall **)(struct IUserData *, const WCHAR *, BSTR *, int *))(*(_QWORD *)v32 + 88LL))(
            v32,
            L"ConnectedInfo",
            &bstrString,
            &v37);
    v15 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x270,
        (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
        (const char *)(unsigned int)v17,
        v28);
      if ( bstrString )
        SysFreeString(bstrString);
      goto LABEL_30;
    }
    v20 = (LPVOID *)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                      &v38,
                      (char *)bstrString,
                      v18,
                      v19);
    v21 = 0;
    if ( &pv != v20 )
    {
      v14 = *v20;
      *v20 = 0;
      v21 = v14;
    }
    if ( v38 )
      CoTaskMemFree(v38);
    if ( !v21 )
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x272,
        (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
        (const char *)0x8007000ELL,
        v28);
      if ( bstrString )
        SysFreeString(bstrString);
      if ( v33 )
        (*(void (__fastcall **)(struct IConnectedUser *))(*(_QWORD *)v33 + 16LL))(v33);
      if ( v32 )
        (*(void (__fastcall **)(struct IUserData *))(*(_QWORD *)v32 + 16LL))(v32);
      if ( !v31 )
        return v8;
      v10 = *(void (**)(void))(*(_QWORD *)v31 + 16LL);
      goto LABEL_13;
    }
    v22 = SHGetConnectedIdentityProviderForCurrentUser(&pguid);
    v15 = v22;
    if ( v22 >= 0 )
    {
      *(_QWORD *)v35 = 0;
      v15 = (*(__int64 (__fastcall **)(struct IUserManager *, BSTR, _QWORD, GUID *))(*(_QWORD *)v31 + 64LL))(
              v31,
              bstrString,
              0,
              &pguid);
      if ( v15 >= 0 )
      {
        v24 = v33;
        v33 = 0;
        if ( v24 )
          (*(void (__fastcall **)(struct IConnectedUser *))(*(_QWORD *)v24 + 16LL))(v24);
        v15 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, struct IConnectedUser **))v35)(
                *(_QWORD *)v35,
                &GUID_9d5f2149_de8c_45f2_b313_6587a04f771d,
                &v33);
        if ( v15 >= 0 )
        {
          if ( *(_QWORD *)v35 )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v35 + 16LL))(*(_QWORD *)v35);
          if ( bstrString )
            SysFreeString(bstrString);
          goto LABEL_67;
        }
        v23 = 632;
      }
      else
      {
        v23 = 631;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
        (const char *)(unsigned int)v15,
        (int)v35);
      if ( *(_QWORD *)v35 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v35 + 16LL))(*(_QWORD *)v35);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x274,
        (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
        (const char *)(unsigned int)v22,
        v28);
    }
    if ( bstrString )
      SysFreeString(bstrString);
LABEL_54:
    CoTaskMemFree(v14);
    goto LABEL_30;
  }
  if ( CurrentConnectedUser < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27C,
      (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
      (const char *)(unsigned int)CurrentConnectedUser,
      v28);
LABEL_30:
    if ( v33 )
      (*(void (__fastcall **)(struct IConnectedUser *))(*(_QWORD *)v33 + 16LL))(v33);
    if ( v32 )
      (*(void (__fastcall **)(struct IUserData *))(*(_QWORD *)v32 + 16LL))(v32);
    if ( v31 )
      (*(void (__fastcall **)(struct IUserManager *))(*(_QWORD *)v31 + 16LL))(v31);
    return (unsigned int)v15;
  }
  ConnectedUserProperties = CLocalDisconnectPlugin::GetConnectedUserProperties(
                              v13,
                              v33,
                              (unsigned __int16 **)&pv,
                              0,
                              &pguid);
  v8 = ConnectedUserProperties;
  if ( ConnectedUserProperties < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27E,
      (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
      (const char *)(unsigned int)ConnectedUserProperties,
      v29);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v33 )
      (*(void (__fastcall **)(struct IConnectedUser *))(*(_QWORD *)v33 + 16LL))(v33);
    if ( !v32 )
      goto LABEL_11;
    v9 = *(void (**)(void))(*(_QWORD *)v32 + 16LL);
    goto LABEL_10;
  }
  v14 = pv;
LABEL_67:
  v30 = *((_DWORD *)this + 28);
  v25 = (*(__int64 (__fastcall **)(struct IConnectedUser *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v33 + 40LL))(
          v33,
          *((_QWORD *)this + 16),
          *((_QWORD *)this + 17),
          *((_QWORD *)this + 13));
  v15 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x281,
      (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
      (const char *)(unsigned int)v25,
      v30);
    if ( !v14 )
      goto LABEL_30;
    goto LABEL_54;
  }
  v26 = v32;
  v27 = 0;
  v32 = 0;
  *a2 = v26;
  if ( v14 )
  {
    CoTaskMemFree(v14);
    v27 = v32;
  }
  if ( v33 )
  {
    (*(void (__fastcall **)(struct IConnectedUser *))(*(_QWORD *)v33 + 16LL))(v33);
    v27 = v32;
  }
  if ( v27 )
    (*(void (__fastcall **)(struct IUserData *))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v31 )
    (*(void (__fastcall **)(struct IUserManager *))(*(_QWORD *)v31 + 16LL))(v31);
  return 0;
}

```

## disassembly

```asm
0x180059ba8  mov     [rsp-8+arg_10], rbx
0x180059bad  mov     [rsp-8+arg_18], rsi
0x180059bb2  push    rbp
0x180059bb3  push    rdi
0x180059bb4  push    r14
0x180059bb6  lea     rbp, [rsp-47h]
0x180059bbb  sub     rsp, 90h
0x180059bc2  mov     rax, cs:__security_cookie
0x180059bc9  xor     rax, rsp
0x180059bcc  mov     [rbp+57h+var_20], rax
0x180059bd0  mov     r14, rdx
0x180059bd3  mov     qword ptr [rdx], 0
0x180059bda  mov     rsi, rcx
0x180059bdd  mov     [rbp+57h+var_70], 0
0x180059be5  add     rcx, 38h ; '8'; this
0x180059be9  lea     rdx, [rbp+57h+var_70]; struct IUserManager **
0x180059bed  call    ?RetrieveUserManagerFromStream@CBasePlugin@@MEAAJPEAPEAUIUserManager@@@Z; CBasePlugin::RetrieveUserManagerFromStream(IUserManager * *)
0x180059bf2  test    eax, eax
0x180059bf4  jns     short loc_180059C2B
0x180059bf6  mov     rcx, [rsi+40h]
0x180059bfa  mov     rbx, [rbp+57h+var_70]
0x180059bfe  mov     [rbp+57h+var_70], rcx
0x180059c02  test    rcx, rcx
0x180059c05  jz      short loc_180059C17
0x180059c07  mov     rax, [rcx]
0x180059c0a  mov     rax, [rax+8]
0x180059c0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059c13  mov     rcx, [rbp+57h+var_70]
0x180059c17  test    rbx, rbx
0x180059c1a  jz      short loc_180059C2F
0x180059c1c  mov     rax, [rbx]
0x180059c1f  mov     rcx, rbx
0x180059c22  mov     rax, [rax+10h]
0x180059c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059c2b  mov     rcx, [rbp+57h+var_70]
0x180059c2f  mov     [rbp+57h+var_68], 0
0x180059c37  lea     rdx, [rbp+57h+var_68]
0x180059c3b  mov     rax, [rcx]
0x180059c3e  mov     rax, [rax+30h]
0x180059c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059c47  mov     ebx, eax
0x180059c49  test    eax, eax
0x180059c4b  jns     short loc_180059C96
0x180059c4d  mov     rcx, [rbp+5Fh]; this
0x180059c51  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x180059c58  mov     r9d, eax; char *
0x180059c5b  mov     edx, 264h; void *
0x180059c60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059c65  mov     rcx, [rbp+57h+var_68]
0x180059c69  test    rcx, rcx
0x180059c6c  jz      short loc_180059C7A
0x180059c6e  mov     rdx, [rcx]
0x180059c71  mov     rax, [rdx+10h]
0x180059c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059c7a  mov     rcx, [rbp+57h+var_70]
0x180059c7e  test    rcx, rcx
0x180059c81  jz      short loc_180059C8F
0x180059c83  mov     rax, [rcx]
0x180059c86  mov     rax, [rax+10h]
0x180059c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059c8f  mov     eax, ebx
0x180059c91  jmp     loc_18005A072
0x180059c96  mov     rdx, [rbp+57h+var_68]; struct IUserData *
0x180059c9a  lea     r8, [rbp+57h+var_60]; struct IConnectedUser **
0x180059c9e  mov     [rbp+57h+var_60], 0
0x180059ca6  call    ?GetCurrentConnectedUser@CLocalDisconnectPlugin@@AEAAJPEAUIUserData@@PEAPEAUIConnectedUser@@@Z; CLocalDisconnectPlugin::GetCurrentConnectedUser(IUserData *,IConnectedUser * *)
0x180059cab  xor     ebx, ebx
0x180059cad  xorps   xmm0, xmm0
0x180059cb0  mov     [rbp+57h+pv], rbx
0x180059cb4  mov     edi, eax
0x180059cb6  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x180059cba  cmp     eax, 0D0000225h
0x180059cbf  jz      loc_180059D6E
0x180059cc5  cmp     eax, 0D0000064h
0x180059cca  jz      loc_180059D6E
0x180059cd0  test    eax, eax
0x180059cd2  jns     short loc_180059CF1
0x180059cd4  mov     rcx, [rbp+5Fh]; this
0x180059cd8  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x180059cdf  mov     r9d, eax; char *
0x180059ce2  mov     edx, 27Ch; void *
0x180059ce7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059cec  jmp     loc_180059DC1
0x180059cf1  mov     rdx, [rbp+57h+var_60]; struct IConnectedUser *
0x180059cf5  lea     rax, [rbp+57h+pguid]
0x180059cf9  xor     r9d, r9d; unsigned __int16 **
0x180059cfc  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x180059d01  lea     r8, [rbp+57h+pv]; unsigned __int16 **
0x180059d05  call    ?GetConnectedUserProperties@CLocalDisconnectPlugin@@AEAAJPEAUIConnectedUser@@PEAPEAG1PEAU_GUID@@@Z; CLocalDisconnectPlugin::GetConnectedUserProperties(IConnectedUser *,ushort * *,ushort * *,_GUID *)
0x180059d0a  mov     ebx, eax
0x180059d0c  test    eax, eax
0x180059d0e  jns     short loc_180059D65
0x180059d10  mov     rcx, [rbp+5Fh]; this
0x180059d14  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x180059d1b  mov     r9d, eax; char *
0x180059d1e  mov     edx, 27Eh; void *
0x180059d23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059d28  mov     rcx, [rbp+57h+pv]; pv
0x180059d2c  test    rcx, rcx
0x180059d2f  jz      short loc_180059D37
0x180059d31  call    cs:__imp_CoTaskMemFree
0x180059d37  mov     rcx, [rbp+57h+var_60]
0x180059d3b  test    rcx, rcx
0x180059d3e  jz      short loc_180059D4C
0x180059d40  mov     rax, [rcx]
0x180059d43  mov     rax, [rax+10h]
0x180059d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059d4c  mov     rcx, [rbp+57h+var_68]
0x180059d50  test    rcx, rcx
0x180059d53  jz      loc_180059C7A
0x180059d59  mov     rax, [rcx]
0x180059d5c  mov     rax, [rax+10h]
0x180059d60  jmp     loc_180059C75
0x180059d65  mov     rbx, [rbp+57h+pv]
0x180059d69  jmp     loc_180059FB8
0x180059d6e  mov     rcx, [rbp+57h+var_68]
0x180059d72  lea     r9, [rbp+57h+var_40]
0x180059d76  mov     [rbp+57h+var_40], ebx
0x180059d79  lea     r8, [rbp+57h+bstrString]
0x180059d7d  mov     [rbp+57h+bstrString], rbx
0x180059d81  lea     rdx, aConnectedinfo_0; "ConnectedInfo"
0x180059d88  mov     rax, [rcx]
0x180059d8b  mov     rax, [rax+58h]
0x180059d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059d94  mov     edi, eax
0x180059d96  test    eax, eax
0x180059d98  jns     short loc_180059E07
0x180059d9a  mov     rcx, [rbp+5Fh]; this
0x180059d9e  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x180059da5  mov     r9d, eax; char *
0x180059da8  mov     edx, 270h; void *
0x180059dad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059db2  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180059db6  test    rcx, rcx
0x180059db9  jz      short loc_180059DC1
0x180059dbb  call    cs:__imp_SysFreeString
0x180059dc1  mov     rcx, [rbp+57h+var_60]
0x180059dc5  test    rcx, rcx
0x180059dc8  jz      short loc_180059DD6
0x180059dca  mov     rax, [rcx]
0x180059dcd  mov     rax, [rax+10h]
0x180059dd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059dd6  mov     rcx, [rbp+57h+var_68]
0x180059dda  test    rcx, rcx
0x180059ddd  jz      short loc_180059DEB
0x180059ddf  mov     rax, [rcx]
0x180059de2  mov     rax, [rax+10h]
0x180059de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059deb  mov     rcx, [rbp+57h+var_70]
0x180059def  test    rcx, rcx
0x180059df2  jz      short loc_180059E00
0x180059df4  mov     rax, [rcx]
0x180059df7  mov     rax, [rax+10h]
0x180059dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059e00  mov     eax, edi
0x180059e02  jmp     loc_18005A072
0x180059e07  mov     rdx, [rbp+57h+bstrString]
0x180059e0b  lea     rcx, [rbp+57h+var_38]
0x180059e0f  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180059e14  lea     rcx, [rbp+57h+pv]
0x180059e18  xor     edi, edi
0x180059e1a  cmp     rcx, rax
0x180059e1d  jz      short loc_180059E28
0x180059e1f  mov     rbx, [rax]
0x180059e22  mov     [rax], rdi
0x180059e25  mov     rdi, rbx
0x180059e28  mov     rcx, [rbp+57h+var_38]; pv
0x180059e2c  test    rcx, rcx
0x180059e2f  jz      short loc_180059E37
0x180059e31  call    cs:__imp_CoTaskMemFree
0x180059e37  test    rdi, rdi
0x180059e3a  jnz     short loc_180059EAB
0x180059e3c  mov     rcx, [rbp+5Fh]; this
0x180059e40  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x180059e47  mov     ebx, 8007000Eh
0x180059e4c  mov     edx, 272h; void *
0x180059e51  mov     r9d, ebx; char *
0x180059e54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059e59  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180059e5d  test    rcx, rcx
0x180059e60  jz      short loc_180059E68
0x180059e62  call    cs:__imp_SysFreeString
0x180059e68  mov     rcx, [rbp+57h+var_60]
0x180059e6c  test    rcx, rcx
0x180059e6f  jz      short loc_180059E7D
0x180059e71  mov     rax, [rcx]
0x180059e74  mov     rax, [rax+10h]
0x180059e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059e7d  mov     rcx, [rbp+57h+var_68]
0x180059e81  test    rcx, rcx
0x180059e84  jz      short loc_180059E92
0x180059e86  mov     rax, [rcx]
0x180059e89  mov     rax, [rax+10h]
0x180059e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059e92  mov     rcx, [rbp+57h+var_70]
0x180059e96  test    rcx, rcx
0x180059e99  jz      loc_180059C8F
0x180059e9f  mov     rdx, [rcx]
0x180059ea2  mov     rax, [rdx+10h]
0x180059ea6  jmp     loc_180059C8A
0x180059eab  lea     rcx, [rbp+57h+pguid]; pguid
0x180059eaf  call    ?SHGetConnectedIdentityProviderForCurrentUser@@YAJPEAU_GUID@@@Z; SHGetConnectedIdentityProviderForCurrentUser(_GUID *)
0x180059eb4  mov     edi, eax
0x180059eb6  test    eax, eax
0x180059eb8  jns     short loc_180059EEF
0x180059eba  mov     rcx, [rbp+5Fh]; this
0x180059ebe  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x180059ec5  mov     r9d, eax; char *
0x180059ec8  mov     edx, 274h; void *
0x180059ecd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059ed2  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180059ed6  test    rcx, rcx
0x180059ed9  jz      short loc_180059EE1
0x180059edb  call    cs:__imp_SysFreeString
0x180059ee1  mov     rcx, rbx; pv
0x180059ee4  call    cs:__imp_CoTaskMemFree
0x180059eea  jmp     loc_180059DC1
0x180059eef  mov     rcx, [rbp+57h+var_70]
0x180059ef3  lea     rdx, [rbp+57h+var_50]
0x180059ef7  mov     qword ptr [rbp+57h+var_50], 0
0x180059eff  lea     r9, [rbp+57h+pguid]
0x180059f03  mov     qword ptr [rsp+0A0h+var_80], rdx; int
0x180059f08  xor     r8d, r8d
0x180059f0b  mov     rdx, [rbp+57h+bstrString]
0x180059f0f  mov     rax, [rcx]
0x180059f12  mov     rax, [rax+40h]
0x180059f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f1b  mov     edi, eax
0x180059f1d  test    eax, eax
0x180059f1f  jns     short loc_180059F50
0x180059f21  mov     edx, 277h; void *
0x180059f26  mov     rcx, [rbp+5Fh]; this
0x180059f2a  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x180059f31  mov     r9d, edi; char *
0x180059f34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059f39  mov     rcx, qword ptr [rbp+57h+var_50]
0x180059f3d  test    rcx, rcx
0x180059f40  jz      short loc_180059ED2
0x180059f42  mov     rdx, [rcx]
0x180059f45  mov     rax, [rdx+10h]
0x180059f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f4e  jmp     short loc_180059ED2
0x180059f50  mov     rcx, [rbp+57h+var_60]
0x180059f54  mov     [rbp+57h+var_60], 0
0x180059f5c  test    rcx, rcx
0x180059f5f  jz      short loc_180059F6D
0x180059f61  mov     rax, [rcx]
0x180059f64  mov     rax, [rax+10h]
0x180059f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f6d  mov     rcx, qword ptr [rbp+57h+var_50]
0x180059f71  lea     r8, [rbp+57h+var_60]
0x180059f75  lea     rdx, _GUID_9d5f2149_de8c_45f2_b313_6587a04f771d
0x180059f7c  mov     rax, [rcx]
0x180059f7f  mov     rax, [rax]
0x180059f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f87  mov     edi, eax
0x180059f89  test    eax, eax
0x180059f8b  jns     short loc_180059F94
0x180059f8d  mov     edx, 278h
0x180059f92  jmp     short loc_180059F26
0x180059f94  mov     rcx, qword ptr [rbp+57h+var_50]
0x180059f98  test    rcx, rcx
0x180059f9b  jz      short loc_180059FA9
0x180059f9d  mov     rax, [rcx]
0x180059fa0  mov     rax, [rax+10h]
0x180059fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059fa9  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180059fad  test    rcx, rcx
0x180059fb0  jz      short loc_180059FB8
0x180059fb2  call    cs:__imp_SysFreeString
0x180059fb8  mov     r8d, [rsi+70h]
0x180059fbc  mov     rcx, [rbp+57h+var_60]
0x180059fc0  mov     r9, [rsi+68h]
0x180059fc4  mov     rdx, [rsi+80h]
0x180059fcb  mov     [rsp+0A0h+var_80], r8d; int
0x180059fd0  mov     rax, [rcx]
0x180059fd3  mov     r8, [rsi+88h]
0x180059fda  mov     rax, [rax+28h]
0x180059fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059fe3  mov     edi, eax
0x180059fe5  test    eax, eax
0x180059fe7  jns     short loc_18005A00F
0x180059fe9  mov     rcx, [rbp+5Fh]; this
0x180059fed  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x180059ff4  mov     r9d, eax; char *
0x180059ff7  mov     edx, 281h; void *
0x180059ffc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a001  test    rbx, rbx
0x18005a004  jz      loc_180059DC1
0x18005a00a  jmp     loc_180059EE1
0x18005a00f  mov     rax, [rbp+57h+var_68]
0x18005a013  xor     ecx, ecx
0x18005a015  mov     [rbp+57h+var_68], rcx
0x18005a019  mov     [r14], rax
0x18005a01c  test    rbx, rbx
0x18005a01f  jz      short loc_18005A02E
0x18005a021  mov     rcx, rbx; pv
0x18005a024  call    cs:__imp_CoTaskMemFree
0x18005a02a  mov     rcx, [rbp+57h+var_68]
0x18005a02e  mov     rdx, [rbp+57h+var_60]
  ... truncated ...
```
