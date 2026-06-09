# ShellMessageBoxW

- ea: `0x18000f1c0`
- end: `0x18000f425`
- name: `ShellMessageBoxW`
- size: `613`
- prototype: `int(HINSTANCE hAppInst, HWND hWnd, LPCWSTR lpcText, LPCWSTR lpcTitle, UINT fuStyle, ...)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x1800255c0`

## callees

- `0x18000f1c0`
- `0x18000fa38`
- `0x180012550`
- `0x180013066`
- `0x18001e510`
- `0x1800214c0`
- `0x180035458`
- `0x180035e08`
- `0x180035e70`
- `0x1800362d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000f278`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000f278`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f3fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f3fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f2bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f2bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f3ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f3ce`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x18000f2a6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x18000f2a6`
- `USER32!GetPropW` at `0x18000f2d1`
- `USER32!GetPropW` at `0x18000f2d1`
- `USER32!GetWindowThreadProcessId` at `0x18000f2b5`
- `USER32!GetWindowThreadProcessId` at `0x18000f2b5`
- `USER32!MessageBoxW` at `0x18000f3b9`
- `USER32!MessageBoxW` at `0x18000f3b9`
- `USER32!GetWindowTextW` at `0x18000f291`
- `USER32!GetWindowTextW` at `0x18000f291`

## pseudocode

```c
int ShellMessageBoxW(HINSTANCE hAppInst, HWND hWnd, LPCWSTR lpcText, LPCWSTR lpcTitle, UINT fuStyle, ...)
{
  DWORD WindowThreadProcessId; // ebx
  const WCHAR *PropW; // rax
  __int64 v12; // rax
  WCHAR *v13; // r14
  char v14; // r15
  HRESULT v15; // ebx
  int *v16; // r8
  DWORD v17; // ecx
  char v18[16]; // [rsp+40h] [rbp-C0h] BYREF
  TASKDIALOGCONFIG pTaskConfig; // [rsp+50h] [rbp-B0h] BYREF
  int pnButton; // [rsp+F0h] [rbp-10h] BYREF
  ULONG_PTR ulCookie; // [rsp+F8h] [rbp-8h] BYREF
  WCHAR Buffer[80]; // [rsp+100h] [rbp+0h] BYREF
  va_list va; // [rsp+218h] [rbp+118h] BYREF

  va_start(va, fuStyle);
  *(_QWORD *)v18 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
  {
    va_copy(v18, va);
    return _ShellMessageBoxImpl(hAppInst, hWnd, 0, (__int64)lpcText, lpcTitle, fuStyle, (__int64)v18);
  }
  pnButton = 0;
  if ( (unsigned __int64)lpcTitle < 0x10000 && hAppInst )
  {
    if ( LoadStringW(hAppInst, (unsigned __int16)lpcTitle, Buffer, 80) )
      goto LABEL_13;
    if ( !hWnd || !GetWindowTextW(hWnd, Buffer, 80) )
    {
      lpcTitle = &psz;
      goto LABEL_15;
    }
    if ( StrCmpW(Buffer, L"Program Manager") )
    {
LABEL_13:
      lpcTitle = Buffer;
      goto LABEL_15;
    }
    WindowThreadProcessId = GetWindowThreadProcessId(hWnd, 0);
    if ( WindowThreadProcessId == GetCurrentThreadId() )
    {
      PropW = (const WCHAR *)GetPropW(hWnd, L"pszDesktopTitleW");
      lpcTitle = Buffer;
      if ( PropW )
        lpcTitle = PropW;
    }
  }
LABEL_15:
  va_copy(v18, va);
  v12 = ConstructMessageStringW(hAppInst, lpcText, v18);
  *(_QWORD *)v18 = 0;
  v13 = (WCHAR *)v12;
  if ( !v12 )
  {
    v15 = -2147024882;
LABEL_27:
    pnButton = 0;
    goto LABEL_28;
  }
  v14 = 0;
  memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
  pTaskConfig.cbSize = 160;
  pTaskConfig.hwndParent = hWnd;
  pTaskConfig.pszContent = v13;
  pTaskConfig.pszWindowTitle = lpcTitle;
  v15 = ConfigureDialogWithMessageBoxFlags(fuStyle, &pTaskConfig);
  if ( v15 >= 0 )
  {
    ulCookie = 0;
    SHActivateContext(&ulCookie);
    v15 = TaskDialogIndirect(&pTaskConfig, &pnButton, v16, 0);
    if ( v15 < 0 )
    {
      v14 = 1;
      pnButton = MessageBoxW(hWnd, v13, lpcTitle, fuStyle | 0x10000);
    }
    else if ( (fuStyle & 0xF) == 0 && pnButton == 2 )
    {
      pnButton = 1;
    }
    SHDeactivateContext(ulCookie);
  }
  LocalFree(v13);
  if ( v15 >= 0 )
    return pnButton;
  if ( !v14 )
    goto LABEL_27;
LABEL_28:
  v17 = (unsigned __int16)v15;
  if ( (v15 & 0x1FFF0000) != 0x70000 )
    v17 = v15;
  SetLastError(v17);
  return pnButton;
}

```

## disassembly

```asm
0x18000f1c0  push    rbp
0x18000f1c2  push    rbx
0x18000f1c3  push    rsi
0x18000f1c4  push    rdi
0x18000f1c5  push    r14
0x18000f1c7  push    r15
0x18000f1c9  lea     rbp, [rsp-0B8h]
0x18000f1d1  sub     rsp, 1B8h
0x18000f1d8  mov     rax, cs:__security_cookie
0x18000f1df  xor     rax, rsp
0x18000f1e2  mov     [rbp+0E0h+var_40], rax
0x18000f1e9  mov     rdi, r9
0x18000f1ec  mov     r15, r8
0x18000f1ef  mov     rsi, rdx
0x18000f1f2  mov     r14, rcx
0x18000f1f5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x18000f1fc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(wil::ReportingKind)
0x18000f201  mov     qword ptr [rsp+1E0h+var_1A0], 0
0x18000f20a  test    al, al
0x18000f20c  jz      short loc_18000F249
0x18000f20e  lea     rax, [rbp+0E0h+arg_28]
0x18000f215  mov     r9, r15
0x18000f218  mov     qword ptr [rsp+1E0h+var_1A0], rax
0x18000f21d  xor     r8d, r8d
0x18000f220  lea     rax, [rsp+1E0h+var_1A0]
0x18000f225  mov     rdx, rsi
0x18000f228  mov     [rsp+1E0h+var_1B0], rax
0x18000f22d  mov     rcx, r14
0x18000f230  mov     eax, [rbp+0E0h+fuStyle]
0x18000f236  mov     [rsp+1E0h+var_1B8], eax
0x18000f23a  mov     [rsp+1E0h+var_1C0], rdi
0x18000f23f  call    ?_ShellMessageBoxImpl@@YAHPEAUHINSTANCE__@@PEAUHWND__@@W4SHELL_MESSAGE_BOX_INTERNAL_FLAGS@@PEBG3IPEAPEAD@Z; _ShellMessageBoxImpl(HINSTANCE__ *,HWND__ *,SHELL_MESSAGE_BOX_INTERNAL_FLAGS,ushort const *,ushort const *,uint,char * *)
0x18000f244  jmp     loc_18000F406
0x18000f249  mov     [rbp+0E0h+pnButton], 0
0x18000f250  cmp     rdi, 10000h
0x18000f257  jnb     loc_18000F2F1
0x18000f25d  test    r14, r14
0x18000f260  jz      loc_18000F2F1
0x18000f266  mov     ebx, 50h ; 'P'
0x18000f26b  movzx   edx, di; uID
0x18000f26e  mov     r9d, ebx; cchBufferMax
0x18000f271  lea     r8, [rbp+0E0h+Buffer]; lpBuffer
0x18000f275  mov     rcx, r14; hInstance
0x18000f278  call    cs:__imp_LoadStringW
0x18000f27e  test    eax, eax
0x18000f280  jnz     short loc_18000F2E4
0x18000f282  test    rsi, rsi
0x18000f285  jz      short loc_18000F2EA
0x18000f287  mov     r8d, ebx; nMaxCount
0x18000f28a  lea     rdx, [rbp+0E0h+Buffer]; lpString
0x18000f28e  mov     rcx, rsi; hWnd
0x18000f291  call    cs:__imp_GetWindowTextW
0x18000f297  test    eax, eax
0x18000f299  jz      short loc_18000F2EA
0x18000f29b  lea     rdx, aProgramManager_0; "Program Manager"
0x18000f2a2  lea     rcx, [rbp+0E0h+Buffer]; psz1
0x18000f2a6  call    cs:__imp_StrCmpW
0x18000f2ac  test    eax, eax
0x18000f2ae  jnz     short loc_18000F2E4
0x18000f2b0  xor     edx, edx; lpdwProcessId
0x18000f2b2  mov     rcx, rsi; hWnd
0x18000f2b5  call    cs:__imp_GetWindowThreadProcessId
0x18000f2bb  mov     ebx, eax
0x18000f2bd  call    cs:__imp_GetCurrentThreadId
0x18000f2c3  cmp     ebx, eax
0x18000f2c5  jnz     short loc_18000F2F1
0x18000f2c7  lea     rdx, aPszdesktoptitl_0; "pszDesktopTitleW"
0x18000f2ce  mov     rcx, rsi; hWnd
0x18000f2d1  call    cs:__imp_GetPropW
0x18000f2d7  test    rax, rax
0x18000f2da  lea     rdi, [rbp+0E0h+Buffer]
0x18000f2de  cmovnz  rdi, rax
0x18000f2e2  jmp     short loc_18000F2F1
0x18000f2e4  lea     rdi, [rbp+0E0h+Buffer]
0x18000f2e8  jmp     short loc_18000F2F1
0x18000f2ea  lea     rdi, psz
0x18000f2f1  lea     rax, [rbp+0E0h+arg_28]
0x18000f2f8  mov     rdx, r15
0x18000f2fb  lea     r8, [rsp+1E0h+var_1A0]
0x18000f300  mov     qword ptr [rsp+1E0h+var_1A0], rax
0x18000f305  mov     rcx, r14
0x18000f308  call    ConstructMessageStringW
0x18000f30d  mov     qword ptr [rsp+1E0h+var_1A0], 0
0x18000f316  mov     r14, rax
0x18000f319  test    rax, rax
0x18000f31c  jz      loc_18000F3DF
0x18000f322  mov     ebx, 0A0h
0x18000f327  lea     rcx, [rsp+1E0h+pTaskConfig]; void *
0x18000f32c  mov     r8d, ebx; Size
0x18000f32f  xor     edx, edx; Val
0x18000f331  xor     r15b, r15b
0x18000f334  call    memset_0
0x18000f339  mov     ecx, [rbp+0E0h+fuStyle]; unsigned int
0x18000f33f  lea     rdx, [rsp+1E0h+pTaskConfig]; struct _TASKDIALOGCONFIG *
0x18000f344  mov     [rsp+1E0h+pTaskConfig.cbSize], ebx
0x18000f348  mov     [rsp+1E0h+pTaskConfig.hwndParent], rsi
0x18000f34d  mov     [rbp+0E0h+pTaskConfig.pszContent], r14
0x18000f351  mov     [rsp+1E0h+pTaskConfig.pszWindowTitle], rdi
0x18000f356  call    ?ConfigureDialogWithMessageBoxFlags@@YAJKPEAU_TASKDIALOGCONFIG@@@Z; ConfigureDialogWithMessageBoxFlags(ulong,_TASKDIALOGCONFIG *)
0x18000f35b  mov     ebx, eax
0x18000f35d  test    eax, eax
0x18000f35f  js      short loc_18000F3CB
0x18000f361  lea     rcx, [rbp+0E0h+ulCookie]
0x18000f365  mov     [rbp+0E0h+ulCookie], 0
0x18000f36d  call    SHActivateContext
0x18000f372  xor     r9d, r9d; pfVerificationFlagChecked
0x18000f375  lea     rdx, [rbp+0E0h+pnButton]; pnButton
0x18000f379  lea     rcx, [rsp+1E0h+pTaskConfig]; pTaskConfig
0x18000f37e  call    TaskDialogIndirect
0x18000f383  mov     ebx, eax
0x18000f385  test    eax, eax
0x18000f387  js      short loc_18000F3A1
0x18000f389  test    byte ptr [rbp+0E0h+fuStyle], 0Fh
0x18000f390  jnz     short loc_18000F3C2
0x18000f392  cmp     [rbp+0E0h+pnButton], 2
0x18000f396  jnz     short loc_18000F3C2
0x18000f398  mov     [rbp+0E0h+pnButton], 1
0x18000f39f  jmp     short loc_18000F3C2
0x18000f3a1  mov     r9d, [rbp+0E0h+fuStyle]
0x18000f3a8  mov     r8, rdi; lpCaption
0x18000f3ab  bts     r9d, 10h; uType
0x18000f3b0  mov     rdx, r14; lpText
0x18000f3b3  mov     rcx, rsi; hWnd
0x18000f3b6  mov     r15b, 1
0x18000f3b9  call    cs:__imp_MessageBoxW
0x18000f3bf  mov     [rbp+0E0h+pnButton], eax
0x18000f3c2  mov     rcx, [rbp+0E0h+ulCookie]; ulCookie
0x18000f3c6  call    SHDeactivateContext
0x18000f3cb  mov     rcx, r14; hMem
0x18000f3ce  call    cs:__imp_LocalFree
0x18000f3d4  test    ebx, ebx
0x18000f3d6  jns     short loc_18000F403
0x18000f3d8  test    r15b, r15b
0x18000f3db  jnz     short loc_18000F3EB
0x18000f3dd  jmp     short loc_18000F3E4
0x18000f3df  mov     ebx, 8007000Eh
0x18000f3e4  mov     [rbp+0E0h+pnButton], 0
0x18000f3eb  mov     eax, ebx
0x18000f3ed  movzx   ecx, bx
0x18000f3f0  and     eax, 1FFF0000h
0x18000f3f5  cmp     eax, 70000h
0x18000f3fa  cmovnz  ecx, ebx; dwErrCode
0x18000f3fd  call    cs:__imp_SetLastError
0x18000f403  mov     eax, [rbp+0E0h+pnButton]
0x18000f406  mov     rcx, [rbp+0E0h+var_40]
0x18000f40d  xor     rcx, rsp; StackCookie
0x18000f410  call    __security_check_cookie
0x18000f415  add     rsp, 1B8h
0x18000f41c  pop     r15
0x18000f41e  pop     r14
0x18000f420  pop     rdi
0x18000f421  pop     rsi
0x18000f422  pop     rbx
0x18000f423  pop     rbp
0x18000f424  retn
```
