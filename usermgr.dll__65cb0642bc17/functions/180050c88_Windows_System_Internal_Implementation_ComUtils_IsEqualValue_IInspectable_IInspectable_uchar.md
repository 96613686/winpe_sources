# Windows::System::Internal::Implementation::ComUtils::IsEqualValue(IInspectable *,IInspectable *,uchar *)

- ea: `0x180050c88`
- end: `0x1800510df`
- name: `?IsEqualValue@ComUtils@Implementation@Internal@System@Windows@@SAJPEAUIInspectable@@0PEAE@Z`
- size: `1111`
- prototype: `__int64 __fastcall(struct IInspectable *, struct IInspectable *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800504dc`

## callees

- `0x18000ce48`
- `0x180050c88`
- `0x180051220`
- `0x180074aa0`
- `0x1800755e8`
- `0x1800b763c`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050e7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050ee1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050eef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050efe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050e7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050ee1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050eef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050efe`

## string_xrefs

- `0x180050cfe`: `onecore\ds\security\umstartup\usermgr\lib\comutils.h`
- `0x180050d75`: `onecore\ds\security\umstartup\usermgr\lib\comutils.h`
- `0x180050dbd`: `onecore\ds\security\umstartup\usermgr\lib\comutils.h`
- `0x180050e08`: `onecore\ds\security\umstartup\usermgr\lib\comutils.h`
- `0x180050eac`: `onecore\ds\security\umstartup\usermgr\lib\comutils.h`
- `0x180050f2c`: `onecore\ds\security\umstartup\usermgr\lib\comutils.h`
- `0x180050f92`: `onecore\ds\security\umstartup\usermgr\lib\comutils.h`
- `0x180050fe0`: `onecore\ds\security\umstartup\usermgr\lib\comutils.h`
- `0x18005103e`: `onecore\ds\security\umstartup\usermgr\lib\comutils.h`
- `0x180051085`: `onecore\ds\security\umstartup\usermgr\lib\comutils.h`
- `0x180050d93`: `IFC(onecore\ds\security\umstartup\usermgr\lib\comutils.h_469)`
- `0x180050d1c`: `IFC(onecore\ds\security\umstartup\usermgr\lib\comutils.h_468)`
- `0x180050e26`: `IFC(onecore\ds\security\umstartup\usermgr\lib\comutils.h_472)`
- `0x180050ddb`: `IFC(onecore\ds\security\umstartup\usermgr\lib\comutils.h_471)`
- `0x180050f46`: `IFC(onecore\ds\security\umstartup\usermgr\lib\comutils.h_486)`
- `0x180050ec6`: `IFC(onecore\ds\security\umstartup\usermgr\lib\comutils.h_485)`
- `0x180050ffe`: `IFC(onecore\ds\security\umstartup\usermgr\lib\comutils.h_493)`
- `0x180050fb0`: `IFC(onecore\ds\security\umstartup\usermgr\lib\comutils.h_492)`
- `0x18005109f`: `IFC(onecore\ds\security\umstartup\usermgr\lib\comutils.h_499)`
- `0x180051058`: `IFC(onecore\ds\security\umstartup\usermgr\lib\comutils.h_498)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::System::Internal::Implementation::ComUtils::IsEqualValue(
        struct IInspectable *a1,
        struct IInspectable *a2,
        unsigned __int8 *a3)
{
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rcx
  const wchar_t *v10; // r8
  HRESULT (__stdcall *v12)(IInspectable *, const IID *const, void **); // rbx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  unsigned __int8 IsEqualObject; // al
  int v17; // eax
  __int64 v18; // rcx
  const wchar_t *v19; // r8
  int v20; // eax
  int v21; // eax
  int v22; // eax
  bool v23; // zf
  int v24; // eax
  int v25; // eax
  int v26; // [rsp+20h] [rbp-30h] BYREF
  int v27; // [rsp+24h] [rbp-2Ch] BYREF
  int v28; // [rsp+28h] [rbp-28h] BYREF
  HSTRING string; // [rsp+30h] [rbp-20h] BYREF
  struct IUnknown *v30; // [rsp+38h] [rbp-18h] BYREF
  struct IUnknown *v31; // [rsp+40h] [rbp-10h] BYREF
  HSTRING v32; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  char v34; // [rsp+80h] [rbp+30h] BYREF
  char v35; // [rsp+90h] [rbp+40h] BYREF
  int v36; // [rsp+98h] [rbp+48h] BYREF

  *a3 = 0;
  if ( !a1 )
  {
    if ( !a2 )
      goto LABEL_3;
    return 0;
  }
  if ( !a2 )
    return 0;
LABEL_3:
  v36 = 0;
  v26 = 0;
  v31 = 0;
  v30 = 0;
  QueryInterface = a1->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  v7 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, struct IUnknown **))QueryInterface)(
         a1,
         &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
         &v31);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v12 = a2->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    v13 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, struct IUnknown **))v12)(
            a2,
            &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
            &v30);
    v8 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1D5,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h",
        (const char *)(unsigned int)v13,
        v26);
      if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) == 0 )
        goto LABEL_50;
      v10 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h_469)";
      goto LABEL_6;
    }
    v14 = ((__int64 (__fastcall *)(struct IUnknown *, int *))v31->lpVtbl[2].QueryInterface)(v31, &v36);
    v8 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1D7,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h",
        (const char *)(unsigned int)v14,
        v26);
      if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) == 0 )
        goto LABEL_50;
      v10 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h_471)";
      goto LABEL_6;
    }
    v15 = ((__int64 (__fastcall *)(struct IUnknown *, int *))v30->lpVtbl[2].QueryInterface)(v30, &v26);
    v8 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1D8,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h",
        (const char *)(unsigned int)v15,
        v26);
      if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) == 0 )
        goto LABEL_50;
      v10 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h_472)";
      goto LABEL_6;
    }
    if ( v36 != v26 )
    {
      v8 = 0;
      goto LABEL_50;
    }
    switch ( v36 )
    {
      case 5:
        v28 = 0;
        v27 = 0;
        v24 = ((__int64 (__fastcall *)(struct IUnknown *, int *))v31->lpVtbl[4].QueryInterface)(v31, &v28);
        v8 = v24;
        if ( v24 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1F2,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h",
            (const char *)(unsigned int)v24,
            v26);
          if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) == 0 )
            goto LABEL_50;
          v10 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h_498)";
          goto LABEL_6;
        }
        v25 = ((__int64 (__fastcall *)(struct IUnknown *, int *))v30->lpVtbl[4].QueryInterface)(v30, &v27);
        v8 = v25;
        if ( v25 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1F3,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h",
            (const char *)(unsigned int)v25,
            v26);
          if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) == 0 )
            goto LABEL_50;
          v10 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h_499)";
          goto LABEL_6;
        }
        v23 = v28 == v27;
        break;
      case 11:
        v35 = 0;
        v34 = 0;
        v21 = ((__int64 (__fastcall *)(struct IUnknown *, char *))v31->lpVtbl[6].QueryInterface)(v31, &v35);
        v8 = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1EC,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h",
            (const char *)(unsigned int)v21,
            v26);
          if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) == 0 )
            goto LABEL_50;
          v10 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h_492)";
          goto LABEL_6;
        }
        v22 = ((__int64 (__fastcall *)(struct IUnknown *, char *))v30->lpVtbl[6].QueryInterface)(v30, &v34);
        v8 = v22;
        if ( v22 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1ED,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h",
            (const char *)(unsigned int)v22,
            v26);
          if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) == 0 )
            goto LABEL_50;
          v10 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h_493)";
          goto LABEL_6;
        }
        v23 = v35 == v34;
        break;
      case 12:
        v32 = 0;
        string = 0;
        WindowsDeleteString(0);
        v32 = 0;
        v17 = ((__int64 (__fastcall *)(struct IUnknown *, HSTRING *))v31->lpVtbl[6].AddRef)(v31, &v32);
        v8 = v17;
        if ( v17 >= 0 )
        {
          WindowsDeleteString(string);
          string = 0;
          v20 = ((__int64 (__fastcall *)(struct IUnknown *, HSTRING *))v30->lpVtbl[6].AddRef)(v30, &string);
          v8 = v20;
          if ( v20 >= 0 )
          {
            *a3 = Windows::System::Internal::Implementation::ComUtils::IsEqualString(v32, string);
            goto LABEL_29;
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1E6,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h",
            (const char *)(unsigned int)v20,
            v26);
          if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) != 0 )
          {
            v19 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h_486)";
            goto LABEL_28;
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1E5,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h",
            (const char *)(unsigned int)v17,
            v26);
          if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) != 0 )
          {
            v19 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h_485)";
LABEL_28:
            McTemplateU0zd_EventWriteTransfer(v18, LogWarning, v19, v8);
          }
        }
LABEL_29:
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v32);
        goto LABEL_50;
      case 13:
        IsEqualObject = Windows::System::Internal::Implementation::ComUtils::IsEqualObject(v31, v30);
LABEL_49:
        *a3 = IsEqualObject;
        goto LABEL_50;
      default:
        goto LABEL_50;
    }
    IsEqualObject = v23;
    goto LABEL_49;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x1D4,
    (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h",
    (const char *)(unsigned int)v7,
    v26);
  if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) != 0 )
  {
    v10 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h_468)";
LABEL_6:
    McTemplateU0zd_EventWriteTransfer(v9, LogWarning, v10, v8);
  }
LABEL_50:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  return v8;
}

```

## disassembly

```asm
0x180050c88  mov     [rsp-28h+arg_8], rbx
0x180050c8d  push    rbp
0x180050c8e  push    rsi
0x180050c8f  push    rdi
0x180050c90  push    r14
0x180050c92  push    r15
0x180050c94  mov     rbp, rsp
0x180050c97  sub     rsp, 50h
0x180050c9b  mov     rdi, r8
0x180050c9e  mov     rsi, rdx
0x180050ca1  mov     r14, rcx
0x180050ca4  xor     r15d, r15d
0x180050ca7  mov     [r8], r15b
0x180050caa  test    rcx, rcx
0x180050cad  jnz     loc_180050D37
0x180050cb3  test    rdx, rdx
0x180050cb6  jnz     loc_180050D3C
0x180050cbc  mov     [rbp+arg_18], r15d
0x180050cc0  mov     [rbp+var_30], r15d
0x180050cc4  mov     [rbp+var_10], r15
0x180050cc8  mov     [rbp+var_18], r15
0x180050ccc  mov     rax, [rcx]
0x180050ccf  mov     rbx, [rax]
0x180050cd2  lea     rcx, [rbp+var_10]
0x180050cd6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180050cdb  lea     r8, [rbp+var_10]
0x180050cdf  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180050ce6  mov     rcx, r14
0x180050ce9  mov     rax, rbx
0x180050cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050cf1  mov     ebx, eax
0x180050cf3  mov     rcx, [rbp+28h]; this
0x180050cf7  test    eax, eax
0x180050cf9  jns     short loc_180050D43
0x180050cfb  mov     r9d, eax; char *
0x180050cfe  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\umstartup\\userm"...
0x180050d05  mov     edx, 1D4h; void *
0x180050d0a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180050d0f  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x180050d16  jz      loc_1800510B6
0x180050d1c  lea     r8, aIfcOnecoreDsSe_33; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x180050d23  mov     r9d, ebx
0x180050d26  lea     rdx, LogWarning
0x180050d2d  call    McTemplateU0zd_EventWriteTransfer
0x180050d32  jmp     loc_1800510B6
0x180050d37  test    rsi, rsi
0x180050d3a  jnz     short loc_180050CBC
0x180050d3c  xor     eax, eax
0x180050d3e  jmp     loc_1800510CB
0x180050d43  mov     rax, [rsi]
0x180050d46  mov     rbx, [rax]
0x180050d49  lea     rcx, [rbp+var_18]
0x180050d4d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180050d52  lea     r8, [rbp+var_18]
0x180050d56  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180050d5d  mov     rcx, rsi
0x180050d60  mov     rax, rbx
0x180050d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d68  mov     ebx, eax
0x180050d6a  mov     rcx, [rbp+28h]; this
0x180050d6e  test    eax, eax
0x180050d70  jns     short loc_180050D9C
0x180050d72  mov     r9d, eax; char *
0x180050d75  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\umstartup\\userm"...
0x180050d7c  mov     edx, 1D5h; void *
0x180050d81  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180050d86  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x180050d8d  jz      loc_1800510B6
0x180050d93  lea     r8, aIfcOnecoreDsSe_25; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x180050d9a  jmp     short loc_180050D23
0x180050d9c  mov     rcx, [rbp+var_10]
0x180050da0  mov     rax, [rcx]
0x180050da3  lea     rdx, [rbp+arg_18]
0x180050da7  mov     rax, [rax+30h]
0x180050dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050db0  mov     ebx, eax
0x180050db2  mov     rcx, [rbp+28h]; this
0x180050db6  test    eax, eax
0x180050db8  jns     short loc_180050DE7
0x180050dba  mov     r9d, eax; char *
0x180050dbd  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\umstartup\\userm"...
0x180050dc4  mov     edx, 1D7h; void *
0x180050dc9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180050dce  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x180050dd5  jz      loc_1800510B6
0x180050ddb  lea     r8, aIfcOnecoreDsSe_35; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x180050de2  jmp     loc_180050D23
0x180050de7  mov     rcx, [rbp+var_18]
0x180050deb  mov     rax, [rcx]
0x180050dee  lea     rdx, [rbp+var_30]
0x180050df2  mov     rax, [rax+30h]
0x180050df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050dfb  mov     ebx, eax
0x180050dfd  mov     rcx, [rbp+28h]; this
0x180050e01  test    eax, eax
0x180050e03  jns     short loc_180050E32
0x180050e05  mov     r9d, eax; char *
0x180050e08  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\umstartup\\userm"...
0x180050e0f  mov     edx, 1D8h; void *
0x180050e14  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180050e19  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x180050e20  jz      loc_1800510B6
0x180050e26  lea     r8, aIfcOnecoreDsSe_0; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x180050e2d  jmp     loc_180050D23
0x180050e32  mov     ecx, [rbp+arg_18]
0x180050e35  cmp     ecx, [rbp+var_30]
0x180050e38  jz      short loc_180050E42
0x180050e3a  mov     ebx, r15d
0x180050e3d  jmp     loc_1800510B6
0x180050e42  sub     ecx, 5
0x180050e45  jz      loc_180051015
0x180050e4b  sub     ecx, 6
0x180050e4e  jz      loc_180050F66
0x180050e54  sub     ecx, 1
0x180050e57  jz      short loc_180050E74
0x180050e59  cmp     ecx, 1
0x180050e5c  jnz     loc_1800510B6
0x180050e62  mov     rdx, [rbp+var_18]; struct IUnknown *
0x180050e66  mov     rcx, [rbp+var_10]; struct IUnknown *
0x180050e6a  call    ?IsEqualObject@ComUtils@Implementation@Internal@System@Windows@@SA_NPEAUIUnknown@@0@Z; Windows::System::Internal::Implementation::ComUtils::IsEqualObject(IUnknown *,IUnknown *)
0x180050e6f  jmp     loc_1800510B4
0x180050e74  mov     [rbp+var_8], r15
0x180050e78  mov     [rbp+string], r15
0x180050e7c  xor     ecx, ecx; string
0x180050e7e  call    cs:__imp_WindowsDeleteString
0x180050e84  mov     [rbp+var_8], r15
0x180050e88  mov     rcx, [rbp+var_10]
0x180050e8c  mov     rax, [rcx]
0x180050e8f  lea     rdx, [rbp+var_8]
0x180050e93  mov     rax, [rax+98h]
0x180050e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e9f  mov     ebx, eax
0x180050ea1  mov     rcx, [rbp+28h]; this
0x180050ea5  test    eax, eax
0x180050ea7  jns     short loc_180050EFA
0x180050ea9  mov     r9d, eax; char *
0x180050eac  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\umstartup\\userm"...
0x180050eb3  mov     edx, 1E5h; void *
0x180050eb8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180050ebd  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x180050ec4  jz      short loc_180050EDD
0x180050ec6  lea     r8, aIfcOnecoreDsSe_17; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x180050ecd  mov     r9d, ebx
0x180050ed0  lea     rdx, LogWarning
0x180050ed7  call    McTemplateU0zd_EventWriteTransfer
0x180050edc  nop
0x180050edd  mov     rcx, [rbp+string]; string
0x180050ee1  call    cs:__imp_WindowsDeleteString
0x180050ee7  mov     [rbp+string], r15
0x180050eeb  mov     rcx, [rbp+var_8]; string
0x180050eef  call    cs:__imp_WindowsDeleteString
0x180050ef5  jmp     loc_1800510B6
0x180050efa  mov     rcx, [rbp+string]; string
0x180050efe  call    cs:__imp_WindowsDeleteString
0x180050f04  mov     [rbp+string], r15
0x180050f08  mov     rcx, [rbp+var_18]
0x180050f0c  mov     rax, [rcx]
0x180050f0f  lea     rdx, [rbp+string]
0x180050f13  mov     rax, [rax+98h]
0x180050f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f1f  mov     ebx, eax
0x180050f21  mov     rcx, [rbp+28h]; this
0x180050f25  test    eax, eax
0x180050f27  jns     short loc_180050F52
0x180050f29  mov     r9d, eax; char *
0x180050f2c  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\umstartup\\userm"...
0x180050f33  mov     edx, 1E6h; void *
0x180050f38  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180050f3d  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x180050f44  jz      short loc_180050EDD
0x180050f46  lea     r8, aIfcOnecoreDsSe_18; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x180050f4d  jmp     loc_180050ECD
0x180050f52  mov     rdx, [rbp+string]; HSTRING
0x180050f56  mov     rcx, [rbp+var_8]; HSTRING
0x180050f5a  call    ?IsEqualString@ComUtils@Implementation@Internal@System@Windows@@SA_NPEAUHSTRING__@@0@Z; Windows::System::Internal::Implementation::ComUtils::IsEqualString(HSTRING__ *,HSTRING__ *)
0x180050f5f  mov     [rdi], al
0x180050f61  jmp     loc_180050EDD
0x180050f66  mov     [rbp+arg_10], r15b
0x180050f6a  mov     [rbp+arg_0], r15b
0x180050f6e  mov     rcx, [rbp+var_10]
0x180050f72  mov     rax, [rcx]
0x180050f75  lea     rdx, [rbp+arg_10]
0x180050f79  mov     rax, [rax+90h]
0x180050f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f85  mov     ebx, eax
0x180050f87  mov     rcx, [rbp+28h]; this
0x180050f8b  test    eax, eax
0x180050f8d  jns     short loc_180050FBC
0x180050f8f  mov     r9d, eax; char *
0x180050f92  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\umstartup\\userm"...
0x180050f99  mov     edx, 1ECh; void *
0x180050f9e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180050fa3  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x180050faa  jz      loc_1800510B6
0x180050fb0  lea     r8, aIfcOnecoreDsSe_32; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x180050fb7  jmp     loc_180050D23
0x180050fbc  mov     rcx, [rbp+var_18]
0x180050fc0  mov     rax, [rcx]
0x180050fc3  lea     rdx, [rbp+arg_0]
0x180050fc7  mov     rax, [rax+90h]
0x180050fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050fd3  mov     ebx, eax
0x180050fd5  mov     rcx, [rbp+28h]; this
0x180050fd9  test    eax, eax
0x180050fdb  jns     short loc_18005100A
0x180050fdd  mov     r9d, eax; char *
0x180050fe0  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\umstartup\\userm"...
0x180050fe7  mov     edx, 1EDh; void *
0x180050fec  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180050ff1  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x180050ff8  jz      loc_1800510B6
0x180050ffe  lea     r8, aIfcOnecoreDsSe_8; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x180051005  jmp     loc_180050D23
0x18005100a  mov     al, [rbp+arg_0]
0x18005100d  cmp     [rbp+arg_10], al
0x180051010  jmp     loc_1800510B1
0x180051015  mov     [rbp+var_28], r15d
0x180051019  mov     [rbp+var_2C], r15d
0x18005101d  mov     rcx, [rbp+var_10]
0x180051021  mov     rax, [rcx]
0x180051024  lea     rdx, [rbp+var_28]
0x180051028  mov     rax, [rax+60h]
0x18005102c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051031  mov     ebx, eax
0x180051033  mov     rcx, [rbp+28h]; this
0x180051037  test    eax, eax
0x180051039  jns     short loc_180051064
0x18005103b  mov     r9d, eax; char *
0x18005103e  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\umstartup\\userm"...
0x180051045  mov     edx, 1F2h; void *
0x18005104a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005104f  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x180051056  jz      short loc_1800510B6
0x180051058  lea     r8, aIfcOnecoreDsSe_42; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x18005105f  jmp     loc_180050D23
0x180051064  mov     rcx, [rbp+var_18]
0x180051068  mov     rax, [rcx]
0x18005106b  lea     rdx, [rbp+var_2C]
0x18005106f  mov     rax, [rax+60h]
0x180051073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051078  mov     ebx, eax
0x18005107a  mov     rcx, [rbp+28h]; this
0x18005107e  test    eax, eax
0x180051080  jns     short loc_1800510AB
0x180051082  mov     r9d, eax; char *
0x180051085  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\umstartup\\userm"...
0x18005108c  mov     edx, 1F3h; void *
0x180051091  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180051096  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x18005109d  jz      short loc_1800510B6
0x18005109f  lea     r8, aIfcOnecoreDsSe_10; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x1800510a6  jmp     loc_180050D23
0x1800510ab  mov     eax, [rbp+var_2C]
0x1800510ae  cmp     [rbp+var_28], eax
0x1800510b1  setz    al
0x1800510b4  mov     [rdi], al
0x1800510b6  lea     rcx, [rbp+var_18]
0x1800510ba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800510bf  nop
0x1800510c0  lea     rcx, [rbp+var_10]
0x1800510c4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800510c9  mov     eax, ebx
0x1800510cb  mov     rbx, [rsp+50h+arg_8]
0x1800510d3  add     rsp, 50h
0x1800510d7  pop     r15
0x1800510d9  pop     r14
0x1800510db  pop     rdi
0x1800510dc  pop     rsi
0x1800510dd  pop     rbp
0x1800510de  retn
```
