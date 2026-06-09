# ShellMessageBoxA

- ea: `0x18001e6a0`
- end: `0x18001e97a`
- name: `ShellMessageBoxA`
- size: `730`
- prototype: `int(HINSTANCE hAppInst, HWND hWnd, LPCSTR lpcText, LPCSTR lpcTitle, UINT fuStyle, ...)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180012550`
- `0x180013066`
- `0x18001e1d8`
- `0x18001e510`
- `0x18001e54c`
- `0x18001e6a0`
- `0x180035458`
- `0x180035e08`
- `0x180035e70`
- `0x1800362d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringA` at `0x18001e74d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringA` at `0x18001e74d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e955`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e955`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e793`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e793`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e926`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e926`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x18001e77c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x18001e77c`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupA` at `0x18001e822`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupA` at `0x18001e83f`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupA` at `0x18001e822`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupA` at `0x18001e83f`
- `SHCORE!__imp_SHUnicodeToAnsiCP` at `0x18001e7c1`
- `SHCORE!__imp_SHUnicodeToAnsiCP` at `0x18001e7c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e90d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e91d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e90d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e91d`
- `USER32!GetWindowTextA` at `0x18001e767`
- `USER32!GetWindowTextA` at `0x18001e767`
- `USER32!GetWindowThreadProcessId` at `0x18001e78b`
- `USER32!GetWindowThreadProcessId` at `0x18001e78b`
- `USER32!GetPropA` at `0x18001e7a7`
- `USER32!GetPropA` at `0x18001e7a7`
- `USER32!MessageBoxW` at `0x18001e8f1`
- `USER32!MessageBoxW` at `0x18001e8f1`

## pseudocode

```c
int ShellMessageBoxA(HINSTANCE hAppInst, HWND hWnd, LPCSTR lpcText, LPCSTR lpcTitle, UINT fuStyle, ...)
{
  __int64 v9; // r8
  DWORD WindowThreadProcessId; // ebx
  HANDLE PropA; // rax
  const CHAR *v13; // rax
  CHAR *v14; // r14
  char v15; // r15
  HRESULT v16; // ebx
  int *v17; // r8
  DWORD v18; // ecx
  va_list v19; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR ppwsz; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR v21; // [rsp+50h] [rbp-B0h] BYREF
  TASKDIALOGCONFIG pTaskConfig; // [rsp+60h] [rbp-A0h] BYREF
  int pnButton; // [rsp+100h] [rbp+0h] BYREF
  ULONG_PTR ulCookie; // [rsp+108h] [rbp+8h] BYREF
  CHAR Buffer[80]; // [rsp+110h] [rbp+10h] BYREF
  va_list va; // [rsp+1D8h] [rbp+D8h] BYREF

  va_start(va, fuStyle);
  v19 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
  {
    va_copy(v19, va);
    return _ShellMessageBoxImpl(hAppInst, hWnd, v9, (__int64)lpcText, lpcTitle, fuStyle, (__int64)&v19);
  }
  pnButton = 0;
  if ( (unsigned __int64)lpcTitle < 0x10000 && hAppInst )
  {
    if ( LoadStringA(hAppInst, (unsigned __int16)lpcTitle, Buffer, 80) )
    {
LABEL_12:
      lpcTitle = Buffer;
      goto LABEL_14;
    }
    if ( hWnd && GetWindowTextA(hWnd, Buffer, 80) )
    {
      if ( !lstrcmpA(Buffer, "Program Manager") )
      {
        WindowThreadProcessId = GetWindowThreadProcessId(hWnd, 0);
        if ( WindowThreadProcessId != GetCurrentThreadId() )
          goto LABEL_14;
        PropA = GetPropA(hWnd, "pszDesktopTitleW");
        if ( PropA )
          SHUnicodeToAnsiCP(0, PropA, Buffer, 80);
      }
      goto LABEL_12;
    }
    lpcTitle = (LPCSTR)&qword_18003D748;
  }
LABEL_14:
  va_copy(v19, va);
  v13 = (const CHAR *)ConstructMessageStringA(hAppInst, lpcText, &v19);
  v19 = 0;
  v14 = (CHAR *)v13;
  if ( !v13 )
  {
    v16 = -2147024882;
LABEL_34:
    pnButton = 0;
    goto LABEL_35;
  }
  ppwsz = 0;
  v21 = 0;
  v15 = 0;
  v16 = SHStrDupA(v13, &ppwsz);
  if ( v16 >= 0 )
  {
    if ( lpcTitle )
      v16 = SHStrDupA(lpcTitle, &v21);
    if ( v16 >= 0 )
    {
      memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
      pTaskConfig.pszContent = ppwsz;
      pTaskConfig.pszWindowTitle = v21;
      pTaskConfig.cbSize = 160;
      pTaskConfig.hwndParent = hWnd;
      v16 = ConfigureDialogWithMessageBoxFlags(fuStyle, &pTaskConfig);
      if ( v16 >= 0 )
      {
        ulCookie = 0;
        SHActivateContext(&ulCookie);
        v16 = TaskDialogIndirect(&pTaskConfig, &pnButton, v17, 0);
        if ( v16 < 0 )
        {
          v15 = 1;
          pnButton = MessageBoxW(hWnd, ppwsz, v21, fuStyle | 0x10000);
        }
        else if ( (fuStyle & 0xF) == 0 && pnButton == 2 )
        {
          pnButton = 1;
        }
        SHDeactivateContext(ulCookie);
      }
    }
  }
  if ( ppwsz )
    CoTaskMemFree(ppwsz);
  if ( v21 )
    CoTaskMemFree(v21);
  LocalFree(v14);
  if ( v16 >= 0 )
    return pnButton;
  if ( !v15 )
    goto LABEL_34;
LABEL_35:
  v18 = (unsigned __int16)v16;
  if ( (v16 & 0x1FFF0000) != 0x70000 )
    v18 = v16;
  SetLastError(v18);
  return pnButton;
}

```

## disassembly

```asm
0x18001e6a0  push    rbp
0x18001e6a2  push    rbx
0x18001e6a3  push    rsi
0x18001e6a4  push    rdi
0x18001e6a5  push    r14
0x18001e6a7  push    r15
0x18001e6a9  lea     rbp, [rsp-78h]
0x18001e6ae  sub     rsp, 178h
0x18001e6b5  mov     rax, cs:__security_cookie
0x18001e6bc  xor     rax, rsp
0x18001e6bf  mov     [rbp+0A0h+var_40], rax
0x18001e6c3  mov     rdi, r9
0x18001e6c6  mov     r15, r8
0x18001e6c9  mov     rsi, rdx
0x18001e6cc  mov     r14, rcx
0x18001e6cf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x18001e6d6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(wil::ReportingKind)
0x18001e6db  mov     [rsp+1A0h+var_160], 0
0x18001e6e4  test    al, al
0x18001e6e6  jz      short loc_18001E720
0x18001e6e8  lea     rax, [rbp+0A0h+arg_28]
0x18001e6ef  mov     r9, r15
0x18001e6f2  mov     [rsp+1A0h+var_160], rax
0x18001e6f7  mov     rdx, rsi
0x18001e6fa  lea     rax, [rsp+1A0h+var_160]
0x18001e6ff  mov     rcx, r14
0x18001e702  mov     [rsp+1A0h+var_170], rax
0x18001e707  mov     eax, [rbp+0A0h+fuStyle]
0x18001e70d  mov     [rsp+1A0h+var_178], eax
0x18001e711  mov     [rsp+1A0h+var_180], rdi
0x18001e716  call    ?_ShellMessageBoxImpl@@YAHPEAUHINSTANCE__@@PEAUHWND__@@W4SHELL_MESSAGE_BOX_INTERNAL_FLAGS@@PEBD3IPEAPEAD@Z; _ShellMessageBoxImpl(HINSTANCE__ *,HWND__ *,SHELL_MESSAGE_BOX_INTERNAL_FLAGS,char const *,char const *,uint,char * *)
0x18001e71b  jmp     loc_18001E95E
0x18001e720  mov     [rbp+0A0h+pnButton], 0
0x18001e727  cmp     rdi, 10000h
0x18001e72e  jnb     loc_18001E7D4
0x18001e734  test    r14, r14
0x18001e737  jz      loc_18001E7D4
0x18001e73d  movzx   edx, di; uID
0x18001e740  lea     r8, [rbp+0A0h+Buffer]; lpBuffer
0x18001e744  mov     r9d, 50h ; 'P'; cchBufferMax
0x18001e74a  mov     rcx, r14; hInstance
0x18001e74d  call    cs:__imp_LoadStringA
0x18001e753  test    eax, eax
0x18001e755  jnz     short loc_18001E7C7
0x18001e757  test    rsi, rsi
0x18001e75a  jz      short loc_18001E7CD
0x18001e75c  lea     r8d, [rax+50h]; nMaxCount
0x18001e760  mov     rcx, rsi; hWnd
0x18001e763  lea     rdx, [rbp+0A0h+Buffer]; lpString
0x18001e767  call    cs:__imp_GetWindowTextA
0x18001e76d  test    eax, eax
0x18001e76f  jz      short loc_18001E7CD
0x18001e771  lea     rdx, String2; "Program Manager"
0x18001e778  lea     rcx, [rbp+0A0h+Buffer]; lpString1
0x18001e77c  call    cs:__imp_lstrcmpA
0x18001e782  test    eax, eax
0x18001e784  jnz     short loc_18001E7C7
0x18001e786  xor     edx, edx; lpdwProcessId
0x18001e788  mov     rcx, rsi; hWnd
0x18001e78b  call    cs:__imp_GetWindowThreadProcessId
0x18001e791  mov     ebx, eax
0x18001e793  call    cs:__imp_GetCurrentThreadId
0x18001e799  cmp     ebx, eax
0x18001e79b  jnz     short loc_18001E7D4
0x18001e79d  lea     rdx, aPszdesktoptitl; "pszDesktopTitleW"
0x18001e7a4  mov     rcx, rsi; hWnd
0x18001e7a7  call    cs:__imp_GetPropA
0x18001e7ad  test    rax, rax
0x18001e7b0  jz      short loc_18001E7C7
0x18001e7b2  mov     r9d, 50h ; 'P'
0x18001e7b8  lea     r8, [rbp+0A0h+Buffer]
0x18001e7bc  mov     rdx, rax
0x18001e7bf  xor     ecx, ecx
0x18001e7c1  call    cs:__imp_SHUnicodeToAnsiCP
0x18001e7c7  lea     rdi, [rbp+0A0h+Buffer]
0x18001e7cb  jmp     short loc_18001E7D4
0x18001e7cd  lea     rdi, qword_18003D748
0x18001e7d4  lea     rax, [rbp+0A0h+arg_28]
0x18001e7db  mov     rdx, r15
0x18001e7de  lea     r8, [rsp+1A0h+var_160]
0x18001e7e3  mov     [rsp+1A0h+var_160], rax
0x18001e7e8  mov     rcx, r14
0x18001e7eb  call    ConstructMessageStringA
0x18001e7f0  mov     [rsp+1A0h+var_160], 0
0x18001e7f9  mov     r14, rax
0x18001e7fc  test    rax, rax
0x18001e7ff  jz      loc_18001E937
0x18001e805  lea     rdx, [rsp+1A0h+ppwsz]; ppwsz
0x18001e80a  mov     [rsp+1A0h+ppwsz], 0
0x18001e813  mov     rcx, rax; psz
0x18001e816  mov     [rsp+1A0h+var_150], 0
0x18001e81f  xor     r15b, r15b
0x18001e822  call    cs:__imp_SHStrDupA
0x18001e828  mov     ebx, eax
0x18001e82a  test    eax, eax
0x18001e82c  js      loc_18001E903
0x18001e832  test    rdi, rdi
0x18001e835  jz      short loc_18001E847
0x18001e837  lea     rdx, [rsp+1A0h+var_150]; ppwsz
0x18001e83c  mov     rcx, rdi; psz
0x18001e83f  call    cs:__imp_SHStrDupA
0x18001e845  mov     ebx, eax
0x18001e847  test    ebx, ebx
0x18001e849  js      loc_18001E903
0x18001e84f  mov     ebx, 0A0h
0x18001e854  lea     rcx, [rsp+1A0h+pTaskConfig]; void *
0x18001e859  mov     r8d, ebx; Size
0x18001e85c  xor     edx, edx; Val
0x18001e85e  call    memset_0
0x18001e863  mov     rax, [rsp+1A0h+ppwsz]
0x18001e868  lea     rdx, [rsp+1A0h+pTaskConfig]; struct _TASKDIALOGCONFIG *
0x18001e86d  mov     ecx, [rbp+0A0h+fuStyle]; unsigned int
0x18001e873  mov     [rbp+0A0h+pTaskConfig.pszContent], rax
0x18001e877  mov     rax, [rsp+1A0h+var_150]
0x18001e87c  mov     [rsp+1A0h+pTaskConfig.pszWindowTitle], rax
0x18001e881  mov     [rsp+1A0h+pTaskConfig.cbSize], ebx
0x18001e885  mov     [rsp+1A0h+pTaskConfig.hwndParent], rsi
0x18001e88a  call    ?ConfigureDialogWithMessageBoxFlags@@YAJKPEAU_TASKDIALOGCONFIG@@@Z; ConfigureDialogWithMessageBoxFlags(ulong,_TASKDIALOGCONFIG *)
0x18001e88f  mov     ebx, eax
0x18001e891  test    eax, eax
0x18001e893  js      short loc_18001E903
0x18001e895  lea     rcx, [rbp+0A0h+ulCookie]
0x18001e899  mov     [rbp+0A0h+ulCookie], 0
0x18001e8a1  call    SHActivateContext
0x18001e8a6  xor     r9d, r9d; pfVerificationFlagChecked
0x18001e8a9  lea     rdx, [rbp+0A0h+pnButton]; pnButton
0x18001e8ad  lea     rcx, [rsp+1A0h+pTaskConfig]; pTaskConfig
0x18001e8b2  call    TaskDialogIndirect
0x18001e8b7  mov     ebx, eax
0x18001e8b9  test    eax, eax
0x18001e8bb  js      short loc_18001E8D5
0x18001e8bd  test    byte ptr [rbp+0A0h+fuStyle], 0Fh
0x18001e8c4  jnz     short loc_18001E8FA
0x18001e8c6  cmp     [rbp+0A0h+pnButton], 2
0x18001e8ca  jnz     short loc_18001E8FA
0x18001e8cc  mov     [rbp+0A0h+pnButton], 1
0x18001e8d3  jmp     short loc_18001E8FA
0x18001e8d5  mov     r9d, [rbp+0A0h+fuStyle]
0x18001e8dc  mov     rcx, rsi; hWnd
0x18001e8df  mov     r8, [rsp+1A0h+var_150]; lpCaption
0x18001e8e4  bts     r9d, 10h; uType
0x18001e8e9  mov     rdx, [rsp+1A0h+ppwsz]; lpText
0x18001e8ee  mov     r15b, 1
0x18001e8f1  call    cs:__imp_MessageBoxW
0x18001e8f7  mov     [rbp+0A0h+pnButton], eax
0x18001e8fa  mov     rcx, [rbp+0A0h+ulCookie]; ulCookie
0x18001e8fe  call    SHDeactivateContext
0x18001e903  mov     rcx, [rsp+1A0h+ppwsz]; pv
0x18001e908  test    rcx, rcx
0x18001e90b  jz      short loc_18001E913
0x18001e90d  call    cs:__imp_CoTaskMemFree
0x18001e913  mov     rcx, [rsp+1A0h+var_150]; pv
0x18001e918  test    rcx, rcx
0x18001e91b  jz      short loc_18001E923
0x18001e91d  call    cs:__imp_CoTaskMemFree
0x18001e923  mov     rcx, r14; hMem
0x18001e926  call    cs:__imp_LocalFree
0x18001e92c  test    ebx, ebx
0x18001e92e  jns     short loc_18001E95B
0x18001e930  test    r15b, r15b
0x18001e933  jnz     short loc_18001E943
0x18001e935  jmp     short loc_18001E93C
0x18001e937  mov     ebx, 8007000Eh
0x18001e93c  mov     [rbp+0A0h+pnButton], 0
0x18001e943  mov     eax, ebx
0x18001e945  movzx   ecx, bx
0x18001e948  and     eax, 1FFF0000h
0x18001e94d  cmp     eax, 70000h
0x18001e952  cmovnz  ecx, ebx; dwErrCode
0x18001e955  call    cs:__imp_SetLastError
0x18001e95b  mov     eax, [rbp+0A0h+pnButton]
0x18001e95e  mov     rcx, [rbp+0A0h+var_40]
0x18001e962  xor     rcx, rsp; StackCookie
0x18001e965  call    __security_check_cookie
0x18001e96a  add     rsp, 178h
0x18001e971  pop     r15
0x18001e973  pop     r14
0x18001e975  pop     rdi
0x18001e976  pop     rsi
0x18001e977  pop     rbx
0x18001e978  pop     rbp
0x18001e979  retn
```
