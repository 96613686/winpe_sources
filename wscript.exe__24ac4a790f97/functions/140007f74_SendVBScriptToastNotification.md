# SendVBScriptToastNotification

- ea: `0x140007f74`
- end: `0x140008551`
- name: `SendVBScriptToastNotification`
- size: `1501`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140007930`

## callees

- `0x140004ca8`
- `0x1400072c0`
- `0x140007db0`
- `0x140007f74`
- `0x1400085ac`
- `0x1400175a0`
- `0x1400175d0`
- `0x140018010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1400080a5`
- `msvcrt!_wcsicmp` at `0x1400080a5`
- `msvcrt!wcsrchr` at `0x140008073`
- `msvcrt!wcsrchr` at `0x140008073`
- `KERNEL32!GetLastError` at `0x14000804f`
- `KERNEL32!GetLastError` at `0x14000804f`
- `KERNEL32!GetCurrentProcessId` at `0x140007fc5`
- `KERNEL32!GetCurrentProcessId` at `0x140007fc5`
- `KERNEL32!GetModuleFileNameW` at `0x140008045`
- `KERNEL32!GetModuleFileNameW` at `0x140008045`
- `KERNEL32!ProcessIdToSessionId` at `0x140007fd2`
- `KERNEL32!ProcessIdToSessionId` at `0x140007fd2`
- `USER32!GetProcessWindowStation` at `0x140007feb`
- `USER32!GetProcessWindowStation` at `0x140007feb`
- `USER32!GetUserObjectInformationW` at `0x14000801f`
- `USER32!GetUserObjectInformationW` at `0x14000801f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140008136`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400081ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140008288`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140008379`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000842b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140008136`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400081ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140008288`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140008379`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000842b`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14000829f`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14000829f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140008154`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140008449`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140008154`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140008449`
- `SHELL32!SHGetFolderPathW` at `0x1400080d7`
- `SHELL32!SHGetFolderPathW` at `0x1400080d7`
- `SHLWAPI!__imp_IsOS` at `0x140007faa`
- `SHLWAPI!__imp_IsOS` at `0x140007faa`

## string_xrefs

- `0x14000824c`: `<toast activationType='protocol' launch='https://techcommunity.microsoft.com/blog/windows-itpro-blog/vbscript-deprecation-timelines-and-next-steps/4148301'><visual><binding template='ToastGeneric'><text>VBScript Usage Detected</text><text>VBScript will be removed and may not be supported in future versions of Windows. Go to Event Viewer > VBScriptDeprecationEvent for more details.</text></binding></visual><actions><action content='Learn More' activationType='protocol' arguments='https://techcomm`
- `0x140008281`: `Windows.Data.Xml.Dom.XmlDocument`

## pseudocode

```c
signed int SendVBScriptToastNotification()
{
  int v0; // edi
  DWORD CurrentProcessId; // eax
  HWINSTA ProcessWindowStation; // rax
  signed int result; // eax
  wchar_t *v4; // rax
  WCHAR *v5; // rbx
  const WCHAR *v6; // rdi
  HRESULT v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  int ActivationFactory; // ebx
  unsigned int v11; // r8d
  _QWORD *v12; // rcx
  void (*v13)(void); // rax
  _QWORD *v14; // rsi
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // rdx
  __int64 v17; // r14
  HRESULT v18; // eax
  int v19; // edx
  unsigned int v20; // r8d
  __int64 v21; // rcx
  void (*v22)(void); // rax
  _QWORD *v23; // rcx
  HRESULT v24; // eax
  int v25; // edx
  unsigned int v26; // r8d
  int v27; // eax
  __int64 (__fastcall ***v28)(_QWORD, GUID *, _QWORD **); // rcx
  void (*v29)(void); // rax
  __int64 v30; // rcx
  int v31; // edx
  unsigned int v32; // r8d
  _QWORD *v33; // rcx
  __int64 (__fastcall ***v34)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v35; // rdi
  __int64 v36; // rsi
  HRESULT v37; // eax
  int v38; // edx
  unsigned int v39; // r8d
  _QWORD *v40; // rcx
  void (*v41)(void); // rax
  __int64 (__fastcall ***v42)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 v43; // rcx
  _QWORD *v44; // rcx
  HRESULT v45; // eax
  int v46; // edx
  unsigned int v47; // r8d
  int v48; // eax
  __int64 v49; // rcx
  void (*v50)(void); // rax
  _QWORD *v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  _QWORD *v54; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v55; // [rsp+38h] [rbp-C8h] BYREF
  __int64 (__fastcall ***v56)(_QWORD, GUID *, _QWORD **); // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v57; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v58; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v59; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pSessionId; // [rsp+60h] [rbp-A0h] BYREF
  DWORD nLengthNeeded; // [rsp+64h] [rbp-9Ch] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-98h] BYREF
  HSTRING string; // [rsp+80h] [rbp-80h] BYREF
  __int64 pvInfo; // [rsp+88h] [rbp-78h] BYREF
  int v65; // [rsp+90h] [rbp-70h]
  WCHAR Filename[264]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v67[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR pszPath[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  WCHAR sourceString[2048]; // [rsp+6D0h] [rbp+5D0h] BYREF

  v0 = 1;
  if ( IsOS(0x1Du) )
    return v0;
  pSessionId = 0;
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    return v0;
  if ( !pSessionId )
    return v0;
  ProcessWindowStation = GetProcessWindowStation();
  if ( !ProcessWindowStation )
    return v0;
  nLengthNeeded = 0;
  pvInfo = 0;
  v65 = 0;
  if ( !GetUserObjectInformationW(ProcessWindowStation, 1, &pvInfo, 0xCu, &nLengthNeeded) || (v65 & 1) == 0 )
    return v0;
  if ( GetModuleFileNameW(0, Filename, 0x104u) )
  {
    v4 = wcsrchr(Filename, 0x5Cu);
    if ( v4 )
      v5 = v4 + 1;
    else
      v5 = Filename;
    if ( !(unsigned __int8)ShouldShowToastThrottled(v5) )
      return v0;
    v6 = L"Microsoft.WindowsScriptHost.CScript";
    if ( _wcsicmp(v5, L"cscript.exe") )
      v6 = L"Microsoft.WindowsScriptHost.WScript";
    if ( SHGetFolderPathW(0, 2, 0, 0, pszPath) >= 0 && (int)StringCchPrintfW(v67, 0x104u, L"%s.lnk", v5) >= 0 )
      CreateShortcutForExe(pszPath, v67, Filename, v6);
    v54 = 0;
    string = 0;
    v7 = WindowsCreateStringReference(
           L"Windows.UI.Notifications.ToastNotificationManager",
           0x31u,
           &hstringHeader,
           &string);
    if ( v7 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
      __debugbreak();
    }
    ActivationFactory = RoGetActivationFactory(string, &GUID_50ac103f_d235_4598_bbef_98fe4d1a3ad4, &v54);
    if ( ActivationFactory < 0 )
    {
      v12 = v54;
      if ( !v54 )
        return ActivationFactory;
      v54 = 0;
      v13 = *(void (**)(void))(*v12 + 16LL);
LABEL_23:
      v13();
      return ActivationFactory;
    }
    v14 = v54;
    v15 = -1;
    v55 = 0;
    v16 = -1;
    v17 = *v54;
    string = 0;
    do
      ++v16;
    while ( v6[v16] );
    if ( v16 > 0xFFFFFFFF )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v16, v11);
      __debugbreak();
    }
    if ( (int)v16 + 1 < (unsigned int)v16 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v16, v11);
      __debugbreak();
    }
    v18 = WindowsCreateStringReference(v6, v16, &hstringHeader, &string);
    if ( v18 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v18, v19, v20);
      __debugbreak();
    }
    v0 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64 *))(v17 + 56))(v14, string, &v55);
    if ( v0 < 0
      || (v0 = StringCchPrintfW(
                 sourceString,
                 0x800u,
                 L"<toast activationType='protocol' launch='https://techcommunity.microsoft.com/blog/windows-itpro-blog/vb"
                  "script-deprecation-timelines-and-next-steps/4148301'><visual><binding template='ToastGeneric'><text>VB"
                  "Script Usage Detected</text><text>VBScript will be removed and may not be supported in future versions"
                  " of Windows. Go to Event Viewer > VBScriptDeprecationEvent for more details.</text></binding></visual>"
                  "<actions><action content='Learn More' activationType='protocol' arguments='https://techcommunity.micro"
                  "soft.com/blog/windows-itpro-blog/vbscript-deprecation-timelines-and-next-steps/4148301' /><action cont"
                  "ent='Dismiss' activationType='system' arguments='dismiss' /></actions></toast>"),
          v0 < 0) )
    {
      v21 = v55;
      if ( !v55 )
        goto LABEL_34;
      v55 = 0;
      v22 = *(void (**)(void))(*(_QWORD *)v21 + 16LL);
      goto LABEL_33;
    }
    v56 = 0;
    string = 0;
    v24 = WindowsCreateStringReference(L"Windows.Data.Xml.Dom.XmlDocument", 0x20u, &hstringHeader, &string);
    if ( v24 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v24, v25, v26);
      __debugbreak();
    }
    v27 = RoActivateInstance(string, &v56);
    v28 = v56;
    v0 = v27;
    if ( v27 < 0 )
    {
      if ( !v56 )
      {
LABEL_44:
        v30 = v55;
        if ( !v55 )
        {
LABEL_34:
          v23 = v54;
          if ( v54 )
          {
            v54 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
          }
          return v0;
        }
        v55 = 0;
        v22 = *(void (**)(void))(*(_QWORD *)v30 + 16LL);
LABEL_33:
        v22();
        goto LABEL_34;
      }
      v56 = 0;
      v29 = (void (*)(void))(*v28)[2];
LABEL_43:
      v29();
      goto LABEL_44;
    }
    v57 = 0;
    v0 = (**v56)(v56, &GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637, &v57);
    if ( v0 < 0 )
    {
      v33 = v57;
      if ( v57 )
      {
        v57 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v33 + 16LL))(v33);
      }
      v34 = v56;
      if ( !v56 )
        goto LABEL_44;
      v56 = 0;
      v29 = (void (*)(void))(*v34)[2];
      goto LABEL_43;
    }
    do
      ++v15;
    while ( sourceString[v15] );
    if ( v15 > 0xFFFFFFFF )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v31, v32);
      __debugbreak();
    }
    if ( (int)v15 + 1 < (unsigned int)v15 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v31, v32);
      __debugbreak();
    }
    v35 = v57;
    v36 = *v57;
    v37 = WindowsCreateStringReference(sourceString, v15, &hstringHeader, &string);
    if ( v37 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v37, v38, v39);
      __debugbreak();
    }
    ActivationFactory = (*(__int64 (__fastcall **)(_QWORD *, HSTRING))(v36 + 48))(v35, string);
    if ( ActivationFactory < 0 )
    {
      v40 = v57;
      if ( !v57 )
      {
LABEL_59:
        v42 = v56;
        if ( v56 )
        {
          v56 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v42)[2])(v42);
        }
        v43 = v55;
        if ( v55 )
        {
          v55 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
        }
        v44 = v54;
        if ( !v54 )
          return ActivationFactory;
        v54 = 0;
        v13 = *(void (**)(void))(*v44 + 16LL);
        goto LABEL_23;
      }
      v57 = 0;
      v41 = *(void (**)(void))(*v40 + 16LL);
LABEL_58:
      v41();
      goto LABEL_59;
    }
    v58 = 0;
    string = 0;
    v45 = WindowsCreateStringReference(L"Windows.UI.Notifications.ToastNotification", 0x2Au, &hstringHeader, &string);
    if ( v45 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v45, v46, v47);
      JUMPOUT(0x140008550LL);
    }
    v48 = RoGetActivationFactory(string, &GUID_04124b20_82c6_4229_b109_fd9ed4662b53, &v58);
    v49 = v58;
    ActivationFactory = v48;
    if ( v48 >= 0 )
    {
      v59 = 0;
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v58 + 48LL))(
                            v58,
                            v56,
                            &v59);
      if ( ActivationFactory >= 0 )
        ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v55 + 48LL))(v55, v59);
      v52 = v59;
      if ( v59 )
      {
        v59 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      }
      v53 = v58;
      if ( !v58 )
        goto LABEL_70;
      v58 = 0;
      v50 = *(void (**)(void))(*(_QWORD *)v53 + 16LL);
    }
    else
    {
      if ( !v58 )
      {
LABEL_70:
        v51 = v57;
        if ( !v57 )
          goto LABEL_59;
        v57 = 0;
        v41 = *(void (**)(void))(*v51 + 16LL);
        goto LABEL_58;
      }
      v58 = 0;
      v50 = *(void (**)(void))(*(_QWORD *)v49 + 16LL);
    }
    v50();
    goto LABEL_70;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140007f74  push    rbp
0x140007f76  push    rbx
0x140007f77  push    rsi
0x140007f78  push    rdi
0x140007f79  push    r12
0x140007f7b  push    r14
0x140007f7d  push    r15
0x140007f7f  lea     rbp, [rsp-15E0h]
0x140007f87  mov     eax, 16E0h
0x140007f8c  call    _alloca_probe
0x140007f91  sub     rsp, rax
0x140007f94  mov     rax, cs:__security_cookie
0x140007f9b  xor     rax, rsp
0x140007f9e  mov     [rbp+1610h+var_40], rax
0x140007fa5  mov     ecx, 1Dh; dwOS
0x140007faa  call    cs:__imp_IsOS
0x140007fb0  xor     r15d, r15d
0x140007fb3  mov     edi, 1
0x140007fb8  test    eax, eax
0x140007fba  jnz     loc_140008229
0x140007fc0  mov     [rsp+1710h+pSessionId], r15d
0x140007fc5  call    cs:__imp_GetCurrentProcessId
0x140007fcb  mov     ecx, eax; dwProcessId
0x140007fcd  lea     rdx, [rsp+1710h+pSessionId]; pSessionId
0x140007fd2  call    cs:__imp_ProcessIdToSessionId
0x140007fd8  test    eax, eax
0x140007fda  jz      loc_140008229
0x140007fe0  cmp     [rsp+1710h+pSessionId], r15d
0x140007fe5  jz      loc_140008229
0x140007feb  call    cs:__imp_GetProcessWindowStation
0x140007ff1  test    rax, rax
0x140007ff4  jz      loc_140008229
0x140007ffa  xor     ecx, ecx
0x140007ffc  mov     [rsp+1710h+nLengthNeeded], r15d
0x140008001  mov     [rbp+1610h+pvInfo], rcx
0x140008005  lea     r9d, [rdi+0Bh]; nLength
0x140008009  mov     [rbp+1610h+var_1680], ecx
0x14000800c  lea     r8, [rbp+1610h+pvInfo]; pvInfo
0x140008010  lea     rcx, [rsp+1710h+nLengthNeeded]
0x140008015  mov     edx, edi; nIndex
0x140008017  mov     [rsp+1710h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x14000801c  mov     rcx, rax; hObj
0x14000801f  call    cs:__imp_GetUserObjectInformationW
0x140008025  test    eax, eax
0x140008027  jz      loc_140008229
0x14000802d  test    byte ptr [rbp+1610h+var_1680], dil
0x140008031  jz      loc_140008229
0x140008037  mov     esi, 104h
0x14000803c  lea     rdx, [rbp+1610h+Filename]; lpFilename
0x140008040  mov     r8d, esi; nSize
0x140008043  xor     ecx, ecx; hModule
0x140008045  call    cs:__imp_GetModuleFileNameW
0x14000804b  test    eax, eax
0x14000804d  jnz     short loc_14000806A
0x14000804f  call    cs:__imp_GetLastError
0x140008055  test    eax, eax
0x140008057  jle     loc_14000822B
0x14000805d  movzx   eax, ax
0x140008060  or      eax, 80070000h
0x140008065  jmp     loc_14000822B
0x14000806a  mov     edx, 5Ch ; '\'; Ch
0x14000806f  lea     rcx, [rbp+1610h+Filename]; Str
0x140008073  call    cs:__imp_wcsrchr
0x140008079  mov     rbx, rax
0x14000807c  test    rax, rax
0x14000807f  jz      short loc_140008087
0x140008081  add     rbx, 2
0x140008085  jmp     short loc_14000808B
0x140008087  lea     rbx, [rbp+1610h+Filename]
0x14000808b  mov     rcx, rbx
0x14000808e  call    ShouldShowToastThrottled
0x140008093  test    al, al
0x140008095  jz      loc_140008229
0x14000809b  lea     rdx, aCscriptExe; "cscript.exe"
0x1400080a2  mov     rcx, rbx; String1
0x1400080a5  call    cs:__imp__wcsicmp
0x1400080ab  test    eax, eax
0x1400080ad  lea     rcx, sourceString; "Microsoft.WindowsScriptHost.WScript"
0x1400080b4  lea     rax, [rbp+1610h+pszPath]
0x1400080bb  lea     rdi, aMicrosoftWindo_0; "Microsoft.WindowsScriptHost.CScript"
0x1400080c2  mov     [rsp+1710h+lpnLengthNeeded], rax; pszPath
0x1400080c7  cmovnz  rdi, rcx
0x1400080cb  xor     r9d, r9d; dwFlags
0x1400080ce  xor     r8d, r8d; hToken
0x1400080d1  xor     ecx, ecx; hwnd
0x1400080d3  lea     edx, [r9+2]; csidl
0x1400080d7  call    cs:__imp_SHGetFolderPathW
0x1400080dd  test    eax, eax
0x1400080df  js      short loc_140008118
0x1400080e1  mov     r9, rbx
0x1400080e4  lea     r8, aSLnk; "%s.lnk"
0x1400080eb  mov     rdx, rsi; unsigned __int64
0x1400080ee  lea     rcx, [rbp+1610h+var_1460]; unsigned __int16 *
0x1400080f5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400080fa  test    eax, eax
0x1400080fc  js      short loc_140008118
0x1400080fe  mov     r9, rdi
0x140008101  lea     r8, [rbp+1610h+Filename]
0x140008105  lea     rdx, [rbp+1610h+var_1460]
0x14000810c  lea     rcx, [rbp+1610h+pszPath]
0x140008113  call    CreateShortcutForExe
0x140008118  lea     r9, [rbp+1610h+string]; string
0x14000811c  mov     [rsp+1710h+var_16E0], r15
0x140008121  lea     r8, [rsp+1710h+hstringHeader]; hstringHeader
0x140008126  mov     [rbp+1610h+string], r15
0x14000812a  mov     edx, 31h ; '1'; length
0x14000812f  lea     rcx, ?RuntimeClass_Windows_UI_Notifications_ToastNotificationManager@@3QBGB; "Windows.UI.Notifications.ToastNotificat"...
0x140008136  call    cs:__imp_WindowsCreateStringReference
0x14000813c  test    eax, eax
0x14000813e  js      loc_140008513
0x140008144  mov     rcx, [rbp+1610h+string]
0x140008148  lea     r8, [rsp+1710h+var_16E0]
0x14000814d  lea     rdx, _GUID_50ac103f_d235_4598_bbef_98fe4d1a3ad4
0x140008154  call    cs:__imp_RoGetActivationFactory
0x14000815a  mov     ebx, eax
0x14000815c  test    eax, eax
0x14000815e  jns     short loc_140008182
0x140008160  mov     rcx, [rsp+1710h+var_16E0]
0x140008165  test    rcx, rcx
0x140008168  jz      short loc_14000817B
0x14000816a  mov     [rsp+1710h+var_16E0], r15
0x14000816f  mov     rdx, [rcx]
0x140008172  mov     rax, [rdx+10h]
0x140008176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000817b  mov     eax, ebx
0x14000817d  jmp     loc_14000822B
0x140008182  mov     rsi, [rsp+1710h+var_16E0]
0x140008187  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000818b  mov     [rsp+1710h+var_16D8], r15
0x140008190  mov     rdx, rbx
0x140008193  mov     r14, [rsi]
0x140008196  mov     [rbp+1610h+string], r15
0x14000819a  inc     rdx; int
0x14000819d  cmp     [rdi+rdx*2], r15w
0x1400081a2  jnz     short loc_14000819A
0x1400081a4  mov     r12d, 0FFFFFFFFh
0x1400081aa  cmp     rdx, r12
0x1400081ad  ja      loc_140008508
0x1400081b3  lea     eax, [rdx+1]
0x1400081b6  cmp     eax, edx
0x1400081b8  jb      loc_14000851B
0x1400081be  lea     r9, [rbp+1610h+string]; string
0x1400081c2  mov     rcx, rdi; sourceString
0x1400081c5  lea     r8, [rsp+1710h+hstringHeader]; hstringHeader
0x1400081ca  call    cs:__imp_WindowsCreateStringReference
0x1400081d0  test    eax, eax
0x1400081d2  js      loc_140008526
0x1400081d8  mov     rdx, [rbp+1610h+string]
0x1400081dc  lea     r8, [rsp+1710h+var_16D8]
0x1400081e1  mov     rax, [r14+38h]
0x1400081e5  mov     rcx, rsi
0x1400081e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400081ed  mov     edi, eax
0x1400081ef  test    eax, eax
0x1400081f1  jns     short loc_14000824C
0x1400081f3  mov     rcx, [rsp+1710h+var_16D8]
0x1400081f8  test    rcx, rcx
0x1400081fb  jz      short loc_14000820E
0x1400081fd  mov     [rsp+1710h+var_16D8], r15
0x140008202  mov     rdx, [rcx]
0x140008205  mov     rax, [rdx+10h]
0x140008209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000820e  mov     rcx, [rsp+1710h+var_16E0]
0x140008213  test    rcx, rcx
0x140008216  jz      short loc_140008229
0x140008218  mov     [rsp+1710h+var_16E0], r15
0x14000821d  mov     rax, [rcx]
0x140008220  mov     rax, [rax+10h]
0x140008224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008229  mov     eax, edi
0x14000822b  mov     rcx, [rbp+1610h+var_40]
0x140008232  xor     rcx, rsp; StackCookie
0x140008235  call    __security_check_cookie
0x14000823a  add     rsp, 16E0h
0x140008241  pop     r15
0x140008243  pop     r14
0x140008245  pop     r12
0x140008247  pop     rdi
0x140008248  pop     rsi
0x140008249  pop     rbx
0x14000824a  pop     rbp
0x14000824b  retn
0x14000824c  lea     r8, aToastActivatio; "<toast activationType='protocol' launch"...
0x140008253  mov     edx, 800h; unsigned __int64
0x140008258  lea     rcx, [rbp+1610h+sourceString]; unsigned __int16 *
0x14000825f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140008264  mov     edi, eax
0x140008266  test    eax, eax
0x140008268  js      short loc_1400081F3
0x14000826a  lea     r9, [rbp+1610h+string]; string
0x14000826e  mov     [rsp+1710h+var_16D0], r15
0x140008273  lea     r8, [rsp+1710h+hstringHeader]; hstringHeader
0x140008278  mov     [rbp+1610h+string], r15
0x14000827c  mov     edx, 20h ; ' '; length
0x140008281  lea     rcx, ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocument@@3QBGB; "Windows.Data.Xml.Dom.XmlDocument"
0x140008288  call    cs:__imp_WindowsCreateStringReference
0x14000828e  test    eax, eax
0x140008290  js      loc_14000852E
0x140008296  mov     rcx, [rbp+1610h+string]
0x14000829a  lea     rdx, [rsp+1710h+var_16D0]
0x14000829f  call    cs:__imp_RoActivateInstance
0x1400082a5  mov     rcx, [rsp+1710h+var_16D0]
0x1400082aa  mov     edi, eax
0x1400082ac  test    eax, eax
0x1400082ae  jns     short loc_1400082E5
0x1400082b0  test    rcx, rcx
0x1400082b3  jz      short loc_1400082C6
0x1400082b5  mov     [rsp+1710h+var_16D0], r15
0x1400082ba  mov     rdx, [rcx]
0x1400082bd  mov     rax, [rdx+10h]
0x1400082c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400082c6  mov     rcx, [rsp+1710h+var_16D8]
0x1400082cb  test    rcx, rcx
0x1400082ce  jz      loc_14000820E
0x1400082d4  mov     [rsp+1710h+var_16D8], r15
0x1400082d9  mov     rax, [rcx]
0x1400082dc  mov     rax, [rax+10h]
0x1400082e0  jmp     loc_140008209
0x1400082e5  mov     [rsp+1710h+var_16C8], r15
0x1400082ea  lea     r8, [rsp+1710h+var_16C8]
0x1400082ef  mov     rax, [rcx]
0x1400082f2  lea     rdx, _GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637
0x1400082f9  mov     rax, [rax]
0x1400082fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008301  mov     edi, eax
0x140008303  test    eax, eax
0x140008305  jns     short loc_14000833A
0x140008307  mov     rcx, [rsp+1710h+var_16C8]
0x14000830c  test    rcx, rcx
0x14000830f  jz      short loc_140008322
0x140008311  mov     [rsp+1710h+var_16C8], r15
0x140008316  mov     rdx, [rcx]
0x140008319  mov     rax, [rdx+10h]
0x14000831d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008322  mov     rcx, [rsp+1710h+var_16D0]
0x140008327  test    rcx, rcx
0x14000832a  jz      short loc_1400082C6
0x14000832c  mov     [rsp+1710h+var_16D0], r15
0x140008331  mov     rax, [rcx]
0x140008334  mov     rax, [rax+10h]
0x140008338  jmp     short loc_1400082C1
0x14000833a  lea     rax, [rbp+1610h+sourceString]
0x140008341  inc     rbx
0x140008344  cmp     [rax+rbx*2], r15w
0x140008349  jnz     short loc_140008341
0x14000834b  cmp     rbx, r12
0x14000834e  ja      loc_1400084FD
0x140008354  lea     eax, [rbx+1]
0x140008357  cmp     eax, ebx
0x140008359  jb      loc_140008536
0x14000835f  mov     rdi, [rsp+1710h+var_16C8]
0x140008364  lea     r9, [rbp+1610h+string]; string
0x140008368  lea     r8, [rsp+1710h+hstringHeader]; hstringHeader
0x14000836d  mov     edx, ebx; length
0x14000836f  lea     rcx, [rbp+1610h+sourceString]; sourceString
0x140008376  mov     rsi, [rdi]
0x140008379  call    cs:__imp_WindowsCreateStringReference
0x14000837f  test    eax, eax
0x140008381  js      loc_140008541
0x140008387  mov     rdx, [rbp+1610h+string]
0x14000838b  mov     rcx, rdi
0x14000838e  mov     rax, [rsi+30h]
0x140008392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008397  mov     ebx, eax
0x140008399  test    eax, eax
0x14000839b  jns     short loc_14000840D
0x14000839d  mov     rcx, [rsp+1710h+var_16C8]
0x1400083a2  test    rcx, rcx
0x1400083a5  jz      short loc_1400083B8
0x1400083a7  mov     [rsp+1710h+var_16C8], r15
0x1400083ac  mov     rdx, [rcx]
0x1400083af  mov     rax, [rdx+10h]
0x1400083b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400083b8  mov     rcx, [rsp+1710h+var_16D0]
0x1400083bd  test    rcx, rcx
0x1400083c0  jz      short loc_1400083D3
0x1400083c2  mov     [rsp+1710h+var_16D0], r15
0x1400083c7  mov     rax, [rcx]
0x1400083ca  mov     rax, [rax+10h]
0x1400083ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400083d3  mov     rcx, [rsp+1710h+var_16D8]
0x1400083d8  test    rcx, rcx
0x1400083db  jz      short loc_1400083EE
0x1400083dd  mov     [rsp+1710h+var_16D8], r15
0x1400083e2  mov     rax, [rcx]
0x1400083e5  mov     rax, [rax+10h]
0x1400083e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400083ee  mov     rcx, [rsp+1710h+var_16E0]
0x1400083f3  test    rcx, rcx
0x1400083f6  jz      loc_14000817B
0x1400083fc  mov     [rsp+1710h+var_16E0], r15
0x140008401  mov     rax, [rcx]
0x140008404  mov     rax, [rax+10h]
0x140008408  jmp     loc_140008176
0x14000840d  lea     r9, [rbp+1610h+string]; string
0x140008411  mov     [rsp+1710h+var_16C0], r15
0x140008416  lea     r8, [rsp+1710h+hstringHeader]; hstringHeader
0x14000841b  mov     [rbp+1610h+string], r15
0x14000841f  mov     edx, 2Ah ; '*'; length
0x140008424  lea     rcx, ?RuntimeClass_Windows_UI_Notifications_ToastNotification@@3QBGB; "Windows.UI.Notifications.ToastNotificat"...
  ... truncated ...
```
