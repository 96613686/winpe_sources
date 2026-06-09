# GetObjectPathForProcess(ulong,ulong,ushort *,ulong,ushort *)

- ea: `0x180093cfc`
- end: `0x1800940bc`
- name: `?GetObjectPathForProcess@@YAJKKPEAGK0@Z`
- size: `960`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned __int16 *, size_t cchDest, STRSAFE_LPWSTR pszDest)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800940c4`
- `0x1801091e0`

## callees

- `0x18002f580`
- `0x180061aec`
- `0x180093850`
- `0x180093cfc`
- `0x1800946c0`
- `0x1800948b8`
- `0x180131a80`
- `0x1801334b8`
- `0x1801671e4`
- `0x1801e8320`
- `0x1802bfac4`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093db3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093db3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093d8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093e73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093d8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093e73`
- `ntdll!RtlGetAppContainerNamedObjectPath` at `0x18009403f`
- `ntdll!RtlGetAppContainerNamedObjectPath` at `0x18009403f`
- `ntdll!RtlFreeUnicodeString` at `0x18009406f`
- `ntdll!RtlFreeUnicodeString` at `0x18009406f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180093eb1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180093eb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093f31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093f5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093f31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093f5f`
- `api-ms-win-security-appcontainer-l1-1-0!GetAppContainerNamedObjectPath` at `0x180093d75`
- `api-ms-win-security-appcontainer-l1-1-0!GetAppContainerNamedObjectPath` at `0x180093d75`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180093e02`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180093e02`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180093dc8`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180093dc8`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180093fb1`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180093fb1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180093ed8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180093ed8`

## string_xrefs

- `0x180093f16`: `onecore\windows\accessibletech\uiautomationcore\misc.cpp`
- `0x180093f99`: `onecore\windows\accessibletech\uiautomationcore\misc.cpp`
- `0x180093fd0`: `OpenProcessTokenHelper`
- `0x180093f7d`: `GetTokenInformation`
- `0x180094089`: `GetTokenInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetObjectPathForProcess(
        unsigned int a1,
        unsigned int a2,
        unsigned __int16 *a3,
        size_t cchDest,
        STRSAFE_LPWSTR pszDest)
{
  size_t v5; // rsi
  unsigned __int64 v7; // rdi
  void *v8; // rbx
  int LastError; // esi
  int v11; // edx
  int v12; // r8d
  IErrorInfo *v13; // rax
  IErrorInfo *v14; // rdi
  ICreateErrorInfo *v15; // rcx
  size_t *v16; // r8
  HRESULT v17; // ebx
  int v18; // edi
  PDWORD ReturnLength; // [rsp+20h] [rbp-81h]
  ICreateErrorInfo *pperrinfo[2]; // [rsp+30h] [rbp-71h] BYREF
  int v21; // [rsp+40h] [rbp-61h] BYREF
  DWORD v22; // [rsp+48h] [rbp-59h] BYREF
  _QWORD v23[2]; // [rsp+50h] [rbp-51h] BYREF
  PSID TokenInformation[10]; // [rsp+60h] [rbp-41h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v5 = (unsigned int)cchDest;
  v7 = a2;
  v8 = OpenProcessTokenHelper(a1, a2, a1);
  v23[0] = v8;
  if ( v8 )
  {
    v21 = 0;
    if ( !BasicUiaUtils::s_isDesktopDetermined )
    {
      BasicUiaUtils::s_isDesktop = GetSystemMetrics(6144) != 0;
      BasicUiaUtils::s_isDesktopDetermined = 1;
    }
    if ( BasicUiaUtils::s_isDesktop )
    {
      if ( !(unsigned int)GetAppContainerNamedObjectPath(v8, 0, (unsigned int)v7, a3, &v21) )
        goto LABEL_6;
    }
    else
    {
      *(_OWORD *)pperrinfo = 0;
      RtlGetAppContainerNamedObjectPath(v8, 0, 0, pperrinfo);
      if ( !pperrinfo[1]
        || (v21 = LOWORD(pperrinfo[0]),
            v18 = StringCchCopyNW(a3, v7, (const unsigned __int16 *)pperrinfo[1], LOWORD(pperrinfo[0])),
            RtlFreeUnicodeString((PUNICODE_STRING)pperrinfo),
            v18 < 0) )
      {
LABEL_6:
        if ( v8 != (void *)-1LL )
          CloseHandle(v8);
        return 2147500037LL;
      }
    }
    if ( !v21 )
      goto LABEL_6;
    if ( !pszDest )
      goto LABEL_38;
    v22 = 76;
    if ( GetTokenInformation(v8, TokenAppContainerSid, TokenInformation, 0x4Cu, &v22) )
    {
      if ( TokenInformation[0] )
      {
        pperrinfo[0] = 0;
        if ( !ConvertSidToStringSidW(TokenInformation[0], (LPWSTR *)pperrinfo) )
        {
          v17 = Error::Win32Error(L"GetTokenInformation", L"Hooking into LowBox server");
LABEL_33:
          if ( pperrinfo[0] )
            LocalFree(pperrinfo[0]);
          goto LABEL_35;
        }
        if ( !(_DWORD)v5 )
        {
          v17 = -2147024809;
          goto LABEL_32;
        }
        if ( (unsigned int)v5 > 0x7FFFFFFF )
        {
          v17 = -2147024809;
          *pszDest = 0;
          goto LABEL_32;
        }
        v17 = StringCopyWorkerW(pszDest, v5, v16, (STRSAFE_PCNZWCH)pperrinfo[0], (size_t)ReturnLength);
        if ( v17 < 0 )
        {
LABEL_32:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x242,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\misc.cpp",
            (const char *)(unsigned int)v17,
            (int)ReturnLength);
          goto LABEL_33;
        }
        if ( pperrinfo[0] )
          LocalFree(pperrinfo[0]);
LABEL_38:
        AutoCleanupInfo<void *>::SafeRelease(v23);
        return 0;
      }
      v17 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23A,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\misc.cpp",
        (const char *)0x8007000ELL,
        (int)ReturnLength);
    }
    else
    {
      v17 = Error::Win32Error(L"GetTokenInformation", L"Hooking into LowBox server");
    }
LABEL_35:
    AutoCleanupInfo<void *>::SafeRelease(v23);
    return (unsigned int)v17;
  }
  LastError = GetLastError();
  pperrinfo[0] = 0;
  if ( CreateErrorInfo(pperrinfo) >= 0 )
  {
    ((void (__fastcall *)(ICreateErrorInfo *, const unsigned __int16 *))pperrinfo[0]->lpVtbl->SetDescription)(
      pperrinfo[0],
      L"Hooking into LowBox server");
    v13 = (IErrorInfo *)QI<IErrorInfo>(pperrinfo[0]);
    v14 = v13;
    if ( v13 )
      SetErrorInfo(0, v13);
    if ( v14 )
      ((void (__fastcall *)(IErrorInfo *))v14->lpVtbl->Release)(v14);
  }
  v15 = pperrinfo[0];
  if ( pperrinfo[0] )
    ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo[0]->lpVtbl->Release)(pperrinfo[0]);
  if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 1) != 0 )
  {
    v22 = LastError;
    TokenInformation[2] = (PSID)L"OpenProcessTokenHelper";
    TokenInformation[3] = (PSID)46;
    TokenInformation[4] = &v22;
    TokenInformation[5] = (PSID)4;
    TokenInformation[6] = (PSID)L"Hooking into LowBox server";
    TokenInformation[7] = (PSID)54;
    McGenEventWrite_EventWriteTransfer(v15, Error_OtherError);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, LastError, (__int64)L"Hooking into LowBox server");
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180093cfc  push    rbp
0x180093cfe  push    rbx
0x180093cff  push    rsi
0x180093d00  push    rdi
0x180093d01  push    r14
0x180093d03  push    r15
0x180093d05  lea     rbp, [rsp-27h]
0x180093d0a  sub     rsp, 0C8h
0x180093d11  mov     rax, cs:__security_cookie
0x180093d18  xor     rax, rsp
0x180093d1b  mov     [rbp+4Fh+var_40], rax
0x180093d1f  mov     esi, r9d
0x180093d22  mov     r15, r8
0x180093d25  mov     edi, edx
0x180093d27  mov     r14, [rbp+4Fh+pszDest]
0x180093d2b  mov     r8d, ecx; unsigned int
0x180093d2e  call    ?OpenProcessTokenHelper@@YAPEAXKHK@Z; OpenProcessTokenHelper(ulong,int,ulong)
0x180093d33  mov     rbx, rax
0x180093d36  mov     [rbp+4Fh+var_A0], rax
0x180093d3a  test    rax, rax
0x180093d3d  jz      short loc_180093DB3
0x180093d3f  mov     [rbp+4Fh+var_B0], 0
0x180093d46  mov     al, cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x180093d4c  nop
0x180093d4d  test    al, al
0x180093d4f  jz      loc_180093FAC
0x180093d55  xor     edx, edx
0x180093d57  mov     rcx, rbx
0x180093d5a  cmp     cs:?s_isDesktop@BasicUiaUtils@@2_NA, dl; bool BasicUiaUtils::s_isDesktop
0x180093d60  jz      loc_180094031
0x180093d66  lea     rax, [rbp+4Fh+var_B0]
0x180093d6a  mov     [rsp+0F0h+ReturnLength], rax
0x180093d6f  mov     r9, r15
0x180093d72  mov     r8d, edi
0x180093d75  call    cs:__imp_GetAppContainerNamedObjectPath
0x180093d7b  test    eax, eax
0x180093d7d  jnz     loc_180093E80
0x180093d83  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180093d87  jz      short loc_180093D92
0x180093d89  mov     rcx, rbx; hObject
0x180093d8c  call    cs:__imp_CloseHandle
0x180093d92  mov     eax, 80004005h
0x180093d97  mov     rcx, [rbp+4Fh+var_40]
0x180093d9b  xor     rcx, rsp; StackCookie
0x180093d9e  call    __security_check_cookie
0x180093da3  add     rsp, 0C8h
0x180093daa  pop     r15
0x180093dac  pop     r14
0x180093dae  pop     rdi
0x180093daf  pop     rsi
0x180093db0  pop     rbx
0x180093db1  pop     rbp
0x180093db2  retn
0x180093db3  call    cs:__imp_GetLastError
0x180093db9  nop
0x180093dba  mov     esi, eax
0x180093dbc  mov     [rbp+4Fh+pperrinfo], 0
0x180093dc4  lea     rcx, [rbp+4Fh+pperrinfo]; pperrinfo
0x180093dc8  call    cs:__imp_CreateErrorInfo
0x180093dce  lea     r14, aHookingIntoLow; "Hooking into LowBox server"
0x180093dd5  test    eax, eax
0x180093dd7  js      short loc_180093E1E
0x180093dd9  mov     rcx, [rbp+4Fh+pperrinfo]
0x180093ddd  mov     rax, [rcx]
0x180093de0  mov     rdx, r14
0x180093de3  mov     rax, [rax+28h]
0x180093de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093dec  mov     rcx, [rbp+4Fh+pperrinfo]
0x180093df0  call    ??$QI@UIErrorInfo@@@@YAPEAUIErrorInfo@@PEAUIUnknown@@@Z; QI<IErrorInfo>(IUnknown *)
0x180093df5  mov     rdi, rax
0x180093df8  test    rax, rax
0x180093dfb  jz      short loc_180093E09
0x180093dfd  mov     rdx, rax; perrinfo
0x180093e00  xor     ecx, ecx; dwReserved
0x180093e02  call    cs:__imp_SetErrorInfo
0x180093e08  nop
0x180093e09  test    rdi, rdi
0x180093e0c  jz      short loc_180093E1E
0x180093e0e  mov     rax, [rdi]
0x180093e11  mov     rcx, rdi
0x180093e14  mov     rax, [rax+10h]
0x180093e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093e1d  nop
0x180093e1e  mov     rcx, [rbp+4Fh+pperrinfo]
0x180093e22  test    rcx, rcx
0x180093e25  jz      short loc_180093E34
0x180093e27  mov     rax, [rcx]
0x180093e2a  mov     rax, [rax+10h]
0x180093e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093e33  nop
0x180093e34  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 1
0x180093e3b  jnz     loc_180093FCD
0x180093e41  lea     rax, WPP_GLOBAL_Control
0x180093e48  mov     rcx, cs:WPP_GLOBAL_Control
0x180093e4f  cmp     rcx, rax
0x180093e52  jz      short loc_180093E5E
0x180093e54  test    byte ptr [rcx+1Ch], 2
0x180093e58  jnz     loc_18009401B
0x180093e5e  test    esi, esi
0x180093e60  jg      loc_180093F48
0x180093e66  lea     rcx, [rbx-1]
0x180093e6a  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180093e6e  ja      short loc_180093E79
0x180093e70  mov     rcx, rbx; hObject
0x180093e73  call    cs:__imp_CloseHandle
0x180093e79  mov     eax, esi
0x180093e7b  jmp     loc_180093D97
0x180093e80  cmp     [rbp+4Fh+var_B0], 0
0x180093e84  jz      loc_180093D83
0x180093e8a  test    r14, r14
0x180093e8d  jz      loc_180093F66
0x180093e93  mov     r9d, 4Ch ; 'L'; TokenInformationLength
0x180093e99  mov     [rbp+4Fh+var_A8], r9d
0x180093e9d  lea     rax, [rbp+4Fh+var_A8]
0x180093ea1  mov     [rsp+0F0h+ReturnLength], rax; int
0x180093ea6  lea     r8, [rbp+4Fh+TokenInformation]; TokenInformation
0x180093eaa  lea     edx, [r9-2Dh]; TokenInformationClass
0x180093eae  mov     rcx, rbx; TokenHandle
0x180093eb1  call    cs:__imp_GetTokenInformation
0x180093eb7  test    eax, eax
0x180093eb9  jz      loc_180094082
0x180093ebf  mov     rcx, [rbp+4Fh+TokenInformation]; Sid
0x180093ec3  test    rcx, rcx
0x180093ec6  jz      loc_180093F8D
0x180093ecc  mov     [rbp+4Fh+pperrinfo], 0
0x180093ed4  lea     rdx, [rbp+4Fh+pperrinfo]; StringSid
0x180093ed8  call    cs:__imp_ConvertSidToStringSidW
0x180093ede  test    eax, eax
0x180093ee0  jz      loc_180093F76
0x180093ee6  test    esi, esi
0x180093ee8  jz      loc_1800940A3
0x180093eee  cmp     esi, 7FFFFFFFh
0x180093ef4  ja      loc_18009409C
0x180093efa  mov     rdx, rsi; cchDest
0x180093efd  mov     r9, [rbp+4Fh+pperrinfo]; pszSrc
0x180093f01  mov     rcx, r14; pszDest
0x180093f04  call    StringCopyWorkerW
0x180093f09  mov     ebx, eax
0x180093f0b  test    eax, eax
0x180093f0d  jns     short loc_180093F56
0x180093f0f  mov     rcx, [rbp+57h]; this
0x180093f13  mov     r9d, ebx; char *
0x180093f16  lea     r8, aOnecoreWindows_140; "onecore\\windows\\accessibletech\\uiaut"...
0x180093f1d  mov     edx, 242h; void *
0x180093f22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180093f27  nop
0x180093f28  mov     rcx, [rbp+4Fh+pperrinfo]; hMem
0x180093f2c  test    rcx, rcx
0x180093f2f  jz      short loc_180093F38
0x180093f31  call    cs:__imp_LocalFree
0x180093f37  nop
0x180093f38  lea     rcx, [rbp+4Fh+var_A0]
0x180093f3c  call    ?SafeRelease@?$AutoCleanupInfo@PEAX@@SAXAEAPEAX@Z; AutoCleanupInfo<void *>::SafeRelease(void * &)
0x180093f41  mov     eax, ebx
0x180093f43  jmp     loc_180093D97
0x180093f48  movzx   esi, si
0x180093f4b  or      esi, 80070000h
0x180093f51  jmp     loc_180093E66
0x180093f56  mov     rcx, [rbp+4Fh+pperrinfo]; hMem
0x180093f5a  test    rcx, rcx
0x180093f5d  jz      short loc_180093F66
0x180093f5f  call    cs:__imp_LocalFree
0x180093f65  nop
0x180093f66  lea     rcx, [rbp+4Fh+var_A0]
0x180093f6a  call    ?SafeRelease@?$AutoCleanupInfo@PEAX@@SAXAEAPEAX@Z; AutoCleanupInfo<void *>::SafeRelease(void * &)
0x180093f6f  xor     eax, eax
0x180093f71  jmp     loc_180093D97
0x180093f76  lea     rdx, aHookingIntoLow; "Hooking into LowBox server"
0x180093f7d  lea     rcx, aGettokeninform; "GetTokenInformation"
0x180093f84  call    ?Win32Error@Error@@SAJPEBG0@Z; Error::Win32Error(ushort const *,ushort const *)
0x180093f89  mov     ebx, eax
0x180093f8b  jmp     short loc_180093F28
0x180093f8d  mov     rcx, [rbp+57h]; this
0x180093f91  mov     ebx, 8007000Eh
0x180093f96  mov     r9d, ebx; char *
0x180093f99  lea     r8, aOnecoreWindows_140; "onecore\\windows\\accessibletech\\uiaut"...
0x180093fa0  mov     edx, 23Ah; void *
0x180093fa5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180093faa  jmp     short loc_180093F38
0x180093fac  mov     ecx, 1800h; nIndex
0x180093fb1  call    cs:__imp_GetSystemMetrics
0x180093fb7  test    eax, eax
0x180093fb9  setnz   cs:?s_isDesktop@BasicUiaUtils@@2_NA; bool BasicUiaUtils::s_isDesktop
0x180093fc0  nop
0x180093fc1  mov     cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A, 1; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x180093fc8  jmp     loc_180093D55
0x180093fcd  mov     [rbp+4Fh+var_A8], esi
0x180093fd0  lea     rax, aOpenprocesstok; "OpenProcessTokenHelper"
0x180093fd7  mov     [rbp+4Fh+var_80], rax
0x180093fdb  mov     [rbp+4Fh+var_78], 2Eh ; '.'
0x180093fe3  lea     rax, [rbp+4Fh+var_A8]
0x180093fe7  mov     [rbp+4Fh+var_70], rax
0x180093feb  mov     r9d, 4
0x180093ff1  mov     [rbp+4Fh+var_68], r9
0x180093ff5  mov     [rbp+4Fh+var_60], r14
0x180093ff9  mov     [rbp+4Fh+var_58], 36h ; '6'
0x180094001  lea     rax, [rbp+4Fh+TokenInformation]
0x180094005  mov     [rsp+0F0h+ReturnLength], rax
0x18009400a  lea     rdx, Error_OtherError
0x180094011  call    McGenEventWrite_EventWriteTransfer
0x180094016  jmp     loc_180093E41
0x18009401b  mov     [rsp+0F0h+ReturnLength], r14
0x180094020  mov     r9d, esi
0x180094023  mov     rcx, [rcx+10h]
0x180094027  call    WPP_SF_dS
0x18009402c  jmp     loc_180093E5E
0x180094031  xorps   xmm0, xmm0
0x180094034  movups  xmmword ptr [rbp+4Fh+pperrinfo], xmm0
0x180094038  lea     r9, [rbp+4Fh+pperrinfo]
0x18009403c  xor     r8d, r8d
0x18009403f  call    cs:__imp_RtlGetAppContainerNamedObjectPath
0x180094045  mov     r8, [rbp+4Fh+pperrinfo+8]; unsigned __int16 *
0x180094049  test    r8, r8
0x18009404c  jz      loc_180093D83
0x180094052  movzx   eax, word ptr [rbp+4Fh+pperrinfo]
0x180094056  mov     [rbp+4Fh+var_B0], eax
0x180094059  movzx   r9d, word ptr [rbp+4Fh+pperrinfo]; unsigned __int64
0x18009405e  mov     rdx, rdi; unsigned __int64
0x180094061  mov     rcx, r15; unsigned __int16 *
0x180094064  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180094069  mov     edi, eax
0x18009406b  lea     rcx, [rbp+4Fh+pperrinfo]; UnicodeString
0x18009406f  call    cs:__imp_RtlFreeUnicodeString
0x180094075  test    edi, edi
0x180094077  js      loc_180093D83
0x18009407d  jmp     loc_180093E80
0x180094082  lea     rdx, aHookingIntoLow; "Hooking into LowBox server"
0x180094089  lea     rcx, aGettokeninform; "GetTokenInformation"
0x180094090  call    ?Win32Error@Error@@SAJPEBG0@Z; Error::Win32Error(ushort const *,ushort const *)
0x180094095  mov     ebx, eax
0x180094097  jmp     loc_180093F38
0x18009409c  mov     ebx, 80070057h
0x1800940a1  jmp     short loc_1800940B0
0x1800940a3  mov     ebx, 80070057h
0x1800940a8  test    esi, esi
0x1800940aa  jz      loc_180093F0F
0x1800940b0  xor     eax, eax
0x1800940b2  mov     [r14], ax
0x1800940b6  jmp     loc_180093F0F
```
