# AuthManagerImpl::LoadRequest(Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequest * *)

- ea: `0x180087c18`
- end: `0x1800881ce`
- name: `?LoadRequest@AuthManagerImpl@@AEAAJPEAPEAUIOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Z`
- size: `1462`
- prototype: `__int64 __fastcall(AuthManagerImpl *this, struct Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequest **, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180086e60`

## callees

- `0x180007440`
- `0x180008294`
- `0x18000ba54`
- `0x18000c9e4`
- `0x18000fddc`
- `0x18000fe54`
- `0x18002f808`
- `0x18008698c`
- `0x180087c18`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180087fb6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180087fb6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180087dd6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180087dd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008810f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008810f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180087d98`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180087d98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180087f9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180087f9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088132`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088155`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088132`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088155`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180087fda`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180087fda`

## string_xrefs

- `0x180087e79`: `wns.windows.com`
- `0x180087dc8`: `AuthService`
- `0x180087f96`: `Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest`

## pseudocode

```c
__int64 __fastcall AuthManagerImpl::LoadRequest(
        AuthManagerImpl *this,
        struct Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequest **a2,
        __int64 a3,
        __int64 a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  PVOID *v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  HSTRING v19; // rbx
  int ActivationFactory; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, HSTRING, HSTRING, struct Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequest **); // rbx
  int v26; // eax
  struct Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequest *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  int phkResult; // [rsp+20h] [rbp-E0h]
  struct Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequest *v33; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v35; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v36; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp-98h] BYREF
  HSTRING string; // [rsp+70h] [rbp-90h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 pvData[1024]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8C8h] [rbp+7C8h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(a4) = *((_DWORD *)this + 2) == 1;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids, a4);
  }
  hkey = 0;
  memset_0(pvData, 0, sizeof(pvData));
  pcbData = 2048;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v37 = 0;
  *a2 = 0;
  v6 = AuthManagerImpl::ConvertString(this, L"MBI_SSL", &v35);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
        (unsigned int)v6);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
      (const char *)v7,
      phkResult);
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v12 = 16;
LABEL_13:
      WPP_SF_d(v11[2], v12, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids, v7);
LABEL_61:
      v11 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_62;
    }
    goto LABEL_62;
  }
  if ( AuthManagerImpl::s_TargetService )
  {
LABEL_34:
    v15 = AuthManagerImpl::ConvertString(this, &AuthManagerImpl::s_TargetService, &v36);
    v7 = v15;
    if ( v15 >= 0 )
    {
      if ( WindowsCreateStringReference(
             L"Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest",
             0x45u,
             &hstringHeader,
             &string) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v19 = string;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37, v16, v17, v18);
      ActivationFactory = RoGetActivationFactory(v19, &GUID_bebb0a08_9e73_4077_9614_08614c0bc245, &v37);
      v7 = ActivationFactory;
      if ( ActivationFactory >= 0 )
      {
        v24 = v37;
        v25 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, struct Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequest **))(*(_QWORD *)v37 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33, v21, v22, v23);
        v26 = v25(v24, v36, v35, &v33);
        v7 = v26;
        if ( v26 >= 0 )
        {
          v27 = v33;
          v33 = 0;
          *a2 = v27;
          goto LABEL_61;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
            (unsigned int)v26);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xA9,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
          (const char *)v7,
          phkResult);
        v11 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v12 = 26;
          goto LABEL_13;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
            (unsigned int)ActivationFactory);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xA5,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
          (const char *)v7,
          phkResult);
        v11 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v12 = 24;
          goto LABEL_13;
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
          (unsigned int)v15);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
        (const char *)v7,
        phkResult);
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v12 = 22;
        goto LABEL_13;
      }
    }
    goto LABEL_62;
  }
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PushNotifications",
         0,
         0x20019u,
         &hkey)
    || RegGetValueW(hkey, 0, L"AuthService", 2u, 0, pvData, &pcbData)
    || (v13 = StringCchCopyW(&AuthManagerImpl::s_TargetService, 0x400u, pvData), v7 = v13, v13 >= 0) )
  {
    if ( !AuthManagerImpl::s_TargetService )
    {
      v14 = StringCchCopyW(&AuthManagerImpl::s_TargetService, 0x400u, L"wns.windows.com");
      v7 = v14;
      if ( v14 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
            (unsigned int)v14);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x96,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
          (const char *)v7,
          phkResult);
        v11 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v12 = 20;
          goto LABEL_13;
        }
        goto LABEL_62;
      }
    }
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
      (unsigned int)v13);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x8D,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
    (const char *)v7,
    phkResult);
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v12 = 18;
    goto LABEL_13;
  }
LABEL_62:
  if ( hkey )
  {
    RegCloseKey(hkey);
    hkey = 0;
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v35 )
  {
    WindowsDeleteString(v35);
    v35 = 0;
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v36 )
  {
    WindowsDeleteString(v36);
    v36 = 0;
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x10) != 0 && *((_BYTE *)v11 + 25) >= 6u )
    WPP_SF_d(v11[2], 27, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids, v7);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37, v8, v9, v10);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33, v28, v29, v30);
  return v7;
}

```

## disassembly

```asm
0x180087c18  mov     [rsp-8+arg_10], rbx
0x180087c1d  push    rbp
0x180087c1e  push    rsi
0x180087c1f  push    rdi
0x180087c20  push    r12
0x180087c22  push    r15
0x180087c24  lea     rbp, [rsp-7A0h]
0x180087c2c  sub     rsp, 8A0h
0x180087c33  mov     rax, cs:__security_cookie
0x180087c3a  xor     rax, rsp
0x180087c3d  mov     [rbp+7C0h+var_30], rax
0x180087c44  mov     rsi, rdx
0x180087c47  mov     rdi, rcx
0x180087c4a  lea     r15, WPP_GLOBAL_Control
0x180087c51  lea     r12, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x180087c58  mov     rcx, cs:WPP_GLOBAL_Control
0x180087c5f  cmp     rcx, r15
0x180087c62  jz      short loc_180087C89
0x180087c64  test    byte ptr [rcx+1Ch], 10h
0x180087c68  jz      short loc_180087C89
0x180087c6a  cmp     byte ptr [rcx+19h], 6
0x180087c6e  jb      short loc_180087C89
0x180087c70  cmp     dword ptr [rdi+8], 1
0x180087c74  setz    r9b
0x180087c78  mov     edx, 0Eh
0x180087c7d  mov     r8, r12
0x180087c80  mov     rcx, [rcx+10h]
0x180087c84  call    WPP_SF_c
0x180087c89  mov     [rsp+8C0h+hkey], 0
0x180087c92  mov     ebx, 800h
0x180087c97  mov     r8d, ebx; Size
0x180087c9a  xor     edx, edx; Val
0x180087c9c  lea     rcx, [rbp+7C0h+var_830]; void *
0x180087ca0  call    memset_0
0x180087ca5  mov     [rsp+8C0h+var_858], ebx
0x180087ca9  mov     [rsp+8C0h+var_870], 0
0x180087cb2  mov     [rsp+8C0h+var_868], 0
0x180087cbb  mov     [rsp+8C0h+var_880], 0
0x180087cc4  mov     [rsp+8C0h+var_860], 0
0x180087ccd  mov     qword ptr [rsi], 0
0x180087cd4  lea     r8, [rsp+8C0h+var_870]; HSTRING *
0x180087cd9  lea     rdx, aMbiSsl; "MBI_SSL"
0x180087ce0  mov     rcx, rdi; this
0x180087ce3  call    ?ConvertString@AuthManagerImpl@@AEAAJPEBGPEAPEAUHSTRING__@@@Z; AuthManagerImpl::ConvertString(ushort const *,HSTRING__ * *)
0x180087ce8  mov     ebx, eax
0x180087cea  test    eax, eax
0x180087cec  jns     short loc_180087D68
0x180087cee  mov     rcx, cs:WPP_GLOBAL_Control
0x180087cf5  cmp     rcx, r15
0x180087cf8  jz      short loc_180087D1A
0x180087cfa  test    byte ptr [rcx+1Ch], 10h
0x180087cfe  jz      short loc_180087D1A
0x180087d00  cmp     byte ptr [rcx+19h], 2
0x180087d04  jb      short loc_180087D1A
0x180087d06  mov     edx, 0Fh
0x180087d0b  mov     r9d, eax
0x180087d0e  mov     r8, r12
0x180087d11  mov     rcx, [rcx+10h]
0x180087d15  call    WPP_SF_d
0x180087d1a  mov     rcx, [rbp+7C8h]; this
0x180087d21  mov     r9d, ebx; char *
0x180087d24  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180087d2b  mov     edx, 79h ; 'y'; void *
0x180087d30  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180087d35  mov     rcx, cs:WPP_GLOBAL_Control
0x180087d3c  cmp     rcx, r15
0x180087d3f  jz      loc_180088102
0x180087d45  test    byte ptr [rcx+1Ch], 80h
0x180087d49  jz      loc_180088102
0x180087d4f  mov     edx, 10h
0x180087d54  mov     r9d, ebx
0x180087d57  mov     r8, r12
0x180087d5a  mov     rcx, [rcx+10h]
0x180087d5e  call    WPP_SF_d
0x180087d63  jmp     loc_1800880FB
0x180087d68  xor     eax, eax
0x180087d6a  cmp     ax, cs:?s_TargetService@AuthManagerImpl@@0PAGA; ushort near * AuthManagerImpl::s_TargetService
0x180087d71  jnz     loc_180087F02
0x180087d77  lea     rax, [rsp+8C0h+hkey]
0x180087d7c  mov     [rsp+8C0h+phkResult], rax; int
0x180087d81  mov     r9d, 20019h; samDesired
0x180087d87  xor     r8d, r8d; ulOptions
0x180087d8a  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180087d91  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180087d98  call    cs:__imp_RegOpenKeyExW
0x180087d9e  test    eax, eax
0x180087da0  jnz     loc_180087E6A
0x180087da6  lea     rax, [rsp+8C0h+var_858]
0x180087dab  mov     [rsp+8C0h+pcbData], rax; pcbData
0x180087db0  lea     rax, [rbp+7C0h+var_830]
0x180087db4  mov     [rsp+8C0h+pvData], rax; pvData
0x180087db9  mov     [rsp+8C0h+phkResult], 0; int
0x180087dc2  mov     r9d, 2; dwFlags
0x180087dc8  lea     r8, aAuthservice; "AuthService"
0x180087dcf  xor     edx, edx; lpSubKey
0x180087dd1  mov     rcx, [rsp+8C0h+hkey]; hkey
0x180087dd6  call    cs:__imp_RegGetValueW
0x180087ddc  test    eax, eax
0x180087dde  jnz     loc_180087E6A
0x180087de4  lea     r8, [rbp+7C0h+var_830]; unsigned __int16 *
0x180087de8  mov     edx, 400h; unsigned __int64
0x180087ded  lea     rcx, ?s_TargetService@AuthManagerImpl@@0PAGA; unsigned __int16 *
0x180087df4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180087df9  mov     ebx, eax
0x180087dfb  test    eax, eax
0x180087dfd  jns     short loc_180087E6A
0x180087dff  mov     rcx, cs:WPP_GLOBAL_Control
0x180087e06  cmp     rcx, r15
0x180087e09  jz      short loc_180087E2B
0x180087e0b  test    byte ptr [rcx+1Ch], 10h
0x180087e0f  jz      short loc_180087E2B
0x180087e11  cmp     byte ptr [rcx+19h], 2
0x180087e15  jb      short loc_180087E2B
0x180087e17  mov     edx, 11h
0x180087e1c  mov     r9d, eax
0x180087e1f  mov     r8, r12
0x180087e22  mov     rcx, [rcx+10h]
0x180087e26  call    WPP_SF_d
0x180087e2b  mov     rcx, [rbp+7C8h]; this
0x180087e32  mov     r9d, ebx; char *
0x180087e35  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180087e3c  mov     edx, 8Dh; void *
0x180087e41  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180087e46  mov     rcx, cs:WPP_GLOBAL_Control
0x180087e4d  cmp     rcx, r15
0x180087e50  jz      loc_180088102
0x180087e56  test    byte ptr [rcx+1Ch], 80h
0x180087e5a  jz      loc_180088102
0x180087e60  mov     edx, 12h
0x180087e65  jmp     loc_180087D54
0x180087e6a  xor     eax, eax
0x180087e6c  cmp     ax, cs:?s_TargetService@AuthManagerImpl@@0PAGA; ushort near * AuthManagerImpl::s_TargetService
0x180087e73  jnz     loc_180087F02
0x180087e79  lea     r8, aWnsWindowsCom; "wns.windows.com"
0x180087e80  mov     edx, 400h; unsigned __int64
0x180087e85  lea     rcx, ?s_TargetService@AuthManagerImpl@@0PAGA; unsigned __int16 *
0x180087e8c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180087e91  mov     ebx, eax
0x180087e93  test    eax, eax
0x180087e95  jns     short loc_180087F02
0x180087e97  mov     rcx, cs:WPP_GLOBAL_Control
0x180087e9e  cmp     rcx, r15
0x180087ea1  jz      short loc_180087EC3
0x180087ea3  test    byte ptr [rcx+1Ch], 10h
0x180087ea7  jz      short loc_180087EC3
0x180087ea9  cmp     byte ptr [rcx+19h], 2
0x180087ead  jb      short loc_180087EC3
0x180087eaf  mov     edx, 13h
0x180087eb4  mov     r9d, eax
0x180087eb7  mov     r8, r12
0x180087eba  mov     rcx, [rcx+10h]
0x180087ebe  call    WPP_SF_d
0x180087ec3  mov     rcx, [rbp+7C8h]; this
0x180087eca  mov     r9d, ebx; char *
0x180087ecd  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180087ed4  mov     edx, 96h; void *
0x180087ed9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180087ede  mov     rcx, cs:WPP_GLOBAL_Control
0x180087ee5  cmp     rcx, r15
0x180087ee8  jz      loc_180088102
0x180087eee  test    byte ptr [rcx+1Ch], 80h
0x180087ef2  jz      loc_180088102
0x180087ef8  mov     edx, 14h
0x180087efd  jmp     loc_180087D54
0x180087f02  lea     r8, [rsp+8C0h+var_868]; HSTRING *
0x180087f07  lea     rdx, ?s_TargetService@AuthManagerImpl@@0PAGA; unsigned __int16 *
0x180087f0e  mov     rcx, rdi; this
0x180087f11  call    ?ConvertString@AuthManagerImpl@@AEAAJPEBGPEAPEAUHSTRING__@@@Z; AuthManagerImpl::ConvertString(ushort const *,HSTRING__ * *)
0x180087f16  mov     ebx, eax
0x180087f18  test    eax, eax
0x180087f1a  jns     short loc_180087F87
0x180087f1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180087f23  cmp     rcx, r15
0x180087f26  jz      short loc_180087F48
0x180087f28  test    byte ptr [rcx+1Ch], 10h
0x180087f2c  jz      short loc_180087F48
0x180087f2e  cmp     byte ptr [rcx+19h], 2
0x180087f32  jb      short loc_180087F48
0x180087f34  mov     edx, 15h
0x180087f39  mov     r9d, eax
0x180087f3c  mov     r8, r12
0x180087f3f  mov     rcx, [rcx+10h]
0x180087f43  call    WPP_SF_d
0x180087f48  mov     rcx, [rbp+7C8h]; this
0x180087f4f  mov     r9d, ebx; char *
0x180087f52  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180087f59  mov     edx, 9Ch; void *
0x180087f5e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180087f63  mov     rcx, cs:WPP_GLOBAL_Control
0x180087f6a  cmp     rcx, r15
0x180087f6d  jz      loc_180088102
0x180087f73  test    byte ptr [rcx+1Ch], 80h
0x180087f77  jz      loc_180088102
0x180087f7d  mov     edx, 16h
0x180087f82  jmp     loc_180087D54
0x180087f87  lea     r9, [rsp+8C0h+string]; string
0x180087f8c  lea     r8, [rsp+8C0h+hstringHeader]; hstringHeader
0x180087f91  mov     edx, 45h ; 'E'; length
0x180087f96  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdServiceTicketRequest@@3QBGB; "Windows.Security.Authentication.OnlineI"...
0x180087f9d  call    cs:__imp_WindowsCreateStringReference
0x180087fa3  test    eax, eax
0x180087fa5  jns     short loc_180087FBC
0x180087fa7  xor     r9d, r9d; lpArguments
0x180087faa  xor     r8d, r8d; nNumberOfArguments
0x180087fad  lea     edx, [r9+1]; dwExceptionFlags
0x180087fb1  mov     ecx, 0C000000Dh; dwExceptionCode
0x180087fb6  call    cs:__imp_RaiseException
0x180087fbc  mov     rbx, [rsp+8C0h+string]
0x180087fc1  lea     rcx, [rsp+8C0h+var_860]
0x180087fc6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180087fcb  lea     r8, [rsp+8C0h+var_860]
0x180087fd0  lea     rdx, _GUID_bebb0a08_9e73_4077_9614_08614c0bc245
0x180087fd7  mov     rcx, rbx
0x180087fda  call    cs:__imp_RoGetActivationFactory
0x180087fe0  mov     ebx, eax
0x180087fe2  test    eax, eax
0x180087fe4  jns     short loc_180088051
0x180087fe6  mov     rcx, cs:WPP_GLOBAL_Control
0x180087fed  cmp     rcx, r15
0x180087ff0  jz      short loc_180088012
0x180087ff2  test    byte ptr [rcx+1Ch], 10h
0x180087ff6  jz      short loc_180088012
0x180087ff8  cmp     byte ptr [rcx+19h], 2
0x180087ffc  jb      short loc_180088012
0x180087ffe  mov     edx, 17h
0x180088003  mov     r9d, eax
0x180088006  mov     r8, r12
0x180088009  mov     rcx, [rcx+10h]
0x18008800d  call    WPP_SF_d
0x180088012  mov     rcx, [rbp+7C8h]; this
0x180088019  mov     r9d, ebx; char *
0x18008801c  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180088023  mov     edx, 0A5h; void *
0x180088028  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008802d  mov     rcx, cs:WPP_GLOBAL_Control
0x180088034  cmp     rcx, r15
0x180088037  jz      loc_180088102
0x18008803d  test    byte ptr [rcx+1Ch], 80h
0x180088041  jz      loc_180088102
0x180088047  mov     edx, 18h
0x18008804c  jmp     loc_180087D54
0x180088051  mov     rdi, [rsp+8C0h+var_860]
0x180088056  mov     rax, [rdi]
0x180088059  mov     rbx, [rax+30h]
0x18008805d  lea     rcx, [rsp+8C0h+var_880]
0x180088062  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180088067  lea     r9, [rsp+8C0h+var_880]
0x18008806c  mov     r8, [rsp+8C0h+var_870]
0x180088071  mov     rdx, [rsp+8C0h+var_868]
0x180088076  mov     rcx, rdi
0x180088079  mov     rax, rbx
0x18008807c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088081  mov     ebx, eax
0x180088083  test    eax, eax
0x180088085  jns     short loc_1800880EA
0x180088087  mov     rcx, cs:WPP_GLOBAL_Control
0x18008808e  cmp     rcx, r15
0x180088091  jz      short loc_1800880B3
0x180088093  test    byte ptr [rcx+1Ch], 10h
0x180088097  jz      short loc_1800880B3
0x180088099  cmp     byte ptr [rcx+19h], 2
0x18008809d  jb      short loc_1800880B3
0x18008809f  mov     edx, 19h
0x1800880a4  mov     r9d, eax
0x1800880a7  mov     r8, r12
0x1800880aa  mov     rcx, [rcx+10h]
0x1800880ae  call    WPP_SF_d
0x1800880b3  mov     rcx, [rbp+7C8h]; this
0x1800880ba  mov     r9d, ebx; char *
0x1800880bd  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800880c4  mov     edx, 0A9h; void *
0x1800880c9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800880ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800880d5  cmp     rcx, r15
0x1800880d8  jz      short loc_180088102
0x1800880da  test    byte ptr [rcx+1Ch], 80h
0x1800880de  jz      short loc_180088102
0x1800880e0  mov     edx, 1Ah
0x1800880e5  jmp     loc_180087D54
0x1800880ea  mov     rax, [rsp+8C0h+var_880]
0x1800880ef  mov     [rsp+8C0h+var_880], 0
0x1800880f8  mov     [rsi], rax
0x1800880fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180088102  mov     rax, [rsp+8C0h+hkey]
0x180088107  test    rax, rax
0x18008810a  jz      short loc_180088125
0x18008810c  mov     rcx, rax; hKey
0x18008810f  call    cs:__imp_RegCloseKey
0x180088115  mov     [rsp+8C0h+hkey], 0
0x18008811e  mov     rcx, cs:WPP_GLOBAL_Control
0x180088125  mov     rax, [rsp+8C0h+var_870]
0x18008812a  test    rax, rax
0x18008812d  jz      short loc_180088148
0x18008812f  mov     rcx, rax; string
0x180088132  call    cs:__imp_WindowsDeleteString
0x180088138  mov     [rsp+8C0h+var_870], 0
0x180088141  mov     rcx, cs:WPP_GLOBAL_Control
0x180088148  mov     rax, [rsp+8C0h+var_868]
0x18008814d  test    rax, rax
0x180088150  jz      short loc_18008816B
  ... truncated ...
```
