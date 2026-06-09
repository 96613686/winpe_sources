# _ShellMessageBoxImpl(HINSTANCE__ *,HWND__ *,SHELL_MESSAGE_BOX_INTERNAL_FLAGS,ushort const *,ushort const *,uint,char * *)

- ea: `0x1800214c0`
- end: `0x180021757`
- name: `?_ShellMessageBoxImpl@@YAHPEAUHINSTANCE__@@PEAUHWND__@@W4SHELL_MESSAGE_BOX_INTERNAL_FLAGS@@PEBG3IPEAPEAD@Z`
- size: `663`
- prototype: `int __high(HINSTANCE, HWND, enum SHELL_MESSAGE_BOX_INTERNAL_FLAGS, const unsigned __int16 *, const unsigned __int16 *, unsigned int, char **)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f1c0`
- `0x180021760`

## callees

- `0x18000fa38`
- `0x180012550`
- `0x180013066`
- `0x18001d4f4`
- `0x18001e510`
- `0x1800214c0`
- `0x180035458`
- `0x180035e08`
- `0x180035e70`
- `0x1800362d0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180021536`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180021536`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021653`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021653`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021724`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021724`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002157b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002157b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800216f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800216f5`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180021639`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180021639`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x180021564`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x180021564`
- `USER32!GetPropW` at `0x18002158f`
- `USER32!GetPropW` at `0x18002158f`
- `USER32!GetWindowThreadProcessId` at `0x180021573`
- `USER32!GetWindowThreadProcessId` at `0x180021573`
- `USER32!MessageBoxW` at `0x1800216e0`
- `USER32!MessageBoxW` at `0x1800216e0`
- `USER32!GetWindowTextW` at `0x18002154f`
- `USER32!GetWindowTextW` at `0x18002154f`

## string_xrefs

- `0x180021649`: `TaskDialogInternal`
- `0x180021632`: `comctl32.dll`

## pseudocode

```c
__int64 __fastcall _ShellMessageBoxImpl(
        HINSTANCE a1,
        HWND a2,
        char a3,
        __int64 a4,
        LPCWSTR lpCaption,
        unsigned int a6,
        __int64 a7)
{
  WCHAR *v7; // rdi
  DWORD WindowThreadProcessId; // ebx
  WCHAR *PropW; // rax
  WCHAR *v14; // r15
  char v15; // r12
  HRESULT v16; // ebx
  int *v17; // r8
  HMODULE LibraryW; // rax
  int *v19; // r8
  FARPROC ProcAddress; // rax
  HRESULT v21; // eax
  DWORD v22; // ecx
  HMODULE v24[2]; // [rsp+30h] [rbp-D0h] BYREF
  TASKDIALOGCONFIG pTaskConfig; // [rsp+40h] [rbp-C0h] BYREF
  int pnButton; // [rsp+E0h] [rbp-20h] BYREF
  ULONG_PTR ulCookie; // [rsp+E8h] [rbp-18h] BYREF
  WCHAR Buffer[80]; // [rsp+F0h] [rbp-10h] BYREF

  v7 = (WCHAR *)lpCaption;
  pnButton = 0;
  if ( (unsigned __int64)lpCaption < 0x10000 && a1 )
  {
    if ( LoadStringW(a1, (unsigned __int16)lpCaption, Buffer, 80) )
      goto LABEL_11;
    if ( !a2 || !GetWindowTextW(a2, Buffer, 80) )
    {
      v7 = (WCHAR *)&psz;
      goto LABEL_13;
    }
    if ( StrCmpW(Buffer, L"Program Manager") )
    {
LABEL_11:
      v7 = Buffer;
      goto LABEL_13;
    }
    WindowThreadProcessId = GetWindowThreadProcessId(a2, 0);
    if ( WindowThreadProcessId == GetCurrentThreadId() )
    {
      PropW = (WCHAR *)GetPropW(a2, L"pszDesktopTitleW");
      v7 = Buffer;
      if ( PropW )
        v7 = PropW;
    }
  }
LABEL_13:
  v14 = (WCHAR *)ConstructMessageStringW(a1, a4, a7);
  if ( !v14 )
  {
    v16 = -2147024882;
    goto LABEL_32;
  }
  v15 = 0;
  memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
  pTaskConfig.cbSize = 160;
  pTaskConfig.hwndParent = a2;
  pTaskConfig.pszContent = v14;
  pTaskConfig.pszWindowTitle = v7;
  v16 = ConfigureDialogWithMessageBoxFlags(a6, &pTaskConfig);
  if ( v16 >= 0 )
  {
    ulCookie = 0;
    SHActivateContext(&ulCookie);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
    {
      LibraryW = LoadLibraryW(L"comctl32.dll");
      v24[0] = LibraryW;
      if ( LibraryW && (ProcAddress = GetProcAddress(LibraryW, "TaskDialogInternal")) != 0 )
        v21 = ((__int64 (__fastcall *)(TASKDIALOGCONFIG *, _QWORD, int *, _QWORD, _QWORD))ProcAddress)(
                &pTaskConfig,
                a3 & 1,
                &pnButton,
                0,
                0);
      else
        v21 = TaskDialogIndirect(&pTaskConfig, &pnButton, v19, 0);
      v16 = v21;
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v24);
    }
    else
    {
      v16 = TaskDialogIndirect(&pTaskConfig, &pnButton, v17, 0);
    }
    if ( v16 < 0 )
    {
      v15 = 1;
      pnButton = MessageBoxW(a2, v14, v7, a6 | 0x10000);
    }
    else if ( (a6 & 0xF) == 0 && pnButton == 2 )
    {
      pnButton = 1;
    }
    SHDeactivateContext(ulCookie);
  }
  LocalFree(v14);
  if ( v16 < 0 )
  {
    if ( v15 )
    {
LABEL_33:
      v22 = (unsigned __int16)v16;
      if ( (v16 & 0x1FFF0000) != 0x70000 )
        v22 = v16;
      SetLastError(v22);
      return (unsigned int)pnButton;
    }
LABEL_32:
    pnButton = 0;
    goto LABEL_33;
  }
  return (unsigned int)pnButton;
}

```

## disassembly

```asm
0x1800214c0  mov     [rsp-8+arg_10], rbx
0x1800214c5  push    rbp
0x1800214c6  push    rsi
0x1800214c7  push    rdi
0x1800214c8  push    r12
0x1800214ca  push    r13
0x1800214cc  push    r14
0x1800214ce  push    r15
0x1800214d0  lea     rbp, [rsp-0A0h]
0x1800214d8  sub     rsp, 1A0h
0x1800214df  mov     rax, cs:__security_cookie
0x1800214e6  xor     rax, rsp
0x1800214e9  mov     [rbp+0D0h+var_40], rax
0x1800214f0  mov     rdi, [rbp+0D0h+lpCaption]
0x1800214f7  mov     r15, r9
0x1800214fa  mov     r12, [rbp+0D0h+arg_30]
0x180021501  mov     r13d, r8d
0x180021504  mov     [rbp+0D0h+pnButton], 0
0x18002150b  mov     rsi, rdx
0x18002150e  mov     r14, rcx
0x180021511  cmp     rdi, 10000h
0x180021518  jnb     loc_1800215AF
0x18002151e  test    rcx, rcx
0x180021521  jz      loc_1800215AF
0x180021527  mov     ebx, 50h ; 'P'
0x18002152c  movzx   edx, di; uID
0x18002152f  mov     r9d, ebx; cchBufferMax
0x180021532  lea     r8, [rbp+0D0h+Buffer]; lpBuffer
0x180021536  call    cs:__imp_LoadStringW
0x18002153c  test    eax, eax
0x18002153e  jnz     short loc_1800215A2
0x180021540  test    rsi, rsi
0x180021543  jz      short loc_1800215A8
0x180021545  mov     r8d, ebx; nMaxCount
0x180021548  lea     rdx, [rbp+0D0h+Buffer]; lpString
0x18002154c  mov     rcx, rsi; hWnd
0x18002154f  call    cs:__imp_GetWindowTextW
0x180021555  test    eax, eax
0x180021557  jz      short loc_1800215A8
0x180021559  lea     rdx, aProgramManager_0; "Program Manager"
0x180021560  lea     rcx, [rbp+0D0h+Buffer]; psz1
0x180021564  call    cs:__imp_StrCmpW
0x18002156a  test    eax, eax
0x18002156c  jnz     short loc_1800215A2
0x18002156e  xor     edx, edx; lpdwProcessId
0x180021570  mov     rcx, rsi; hWnd
0x180021573  call    cs:__imp_GetWindowThreadProcessId
0x180021579  mov     ebx, eax
0x18002157b  call    cs:__imp_GetCurrentThreadId
0x180021581  cmp     ebx, eax
0x180021583  jnz     short loc_1800215AF
0x180021585  lea     rdx, aPszdesktoptitl_0; "pszDesktopTitleW"
0x18002158c  mov     rcx, rsi; hWnd
0x18002158f  call    cs:__imp_GetPropW
0x180021595  test    rax, rax
0x180021598  lea     rdi, [rbp+0D0h+Buffer]
0x18002159c  cmovnz  rdi, rax
0x1800215a0  jmp     short loc_1800215AF
0x1800215a2  lea     rdi, [rbp+0D0h+Buffer]
0x1800215a6  jmp     short loc_1800215AF
0x1800215a8  lea     rdi, psz
0x1800215af  mov     r8, r12
0x1800215b2  mov     rdx, r15
0x1800215b5  mov     rcx, r14
0x1800215b8  call    ConstructMessageStringW
0x1800215bd  mov     r15, rax
0x1800215c0  test    rax, rax
0x1800215c3  jz      loc_180021706
0x1800215c9  mov     ebx, 0A0h
0x1800215ce  lea     rcx, [rsp+1D0h+pTaskConfig]; void *
0x1800215d3  mov     r8d, ebx; Size
0x1800215d6  xor     edx, edx; Val
0x1800215d8  xor     r12b, r12b
0x1800215db  call    memset_0
0x1800215e0  mov     r14d, [rbp+0D0h+arg_28]
0x1800215e7  lea     rdx, [rsp+1D0h+pTaskConfig]; struct _TASKDIALOGCONFIG *
0x1800215ec  mov     ecx, r14d; unsigned int
0x1800215ef  mov     [rsp+1D0h+pTaskConfig.cbSize], ebx
0x1800215f3  mov     [rsp+1D0h+pTaskConfig.hwndParent], rsi
0x1800215f8  mov     [rsp+1D0h+pTaskConfig.pszContent], r15
0x1800215fd  mov     [rsp+1D0h+pTaskConfig.pszWindowTitle], rdi
0x180021602  call    ?ConfigureDialogWithMessageBoxFlags@@YAJKPEAU_TASKDIALOGCONFIG@@@Z; ConfigureDialogWithMessageBoxFlags(ulong,_TASKDIALOGCONFIG *)
0x180021607  mov     ebx, eax
0x180021609  test    eax, eax
0x18002160b  js      loc_1800216F2
0x180021611  lea     rcx, [rbp+0D0h+ulCookie]
0x180021615  mov     [rbp+0D0h+ulCookie], 0
0x18002161d  call    SHActivateContext
0x180021622  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x180021629  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(wil::ReportingKind)
0x18002162e  test    al, al
0x180021630  jz      short loc_1800216A0
0x180021632  lea     rcx, aComctl32Dll_0; "comctl32.dll"
0x180021639  call    cs:__imp_LoadLibraryW
0x18002163f  mov     [rsp+1D0h+var_1A0], rax
0x180021644  test    rax, rax
0x180021647  jz      short loc_180021681
0x180021649  lea     rdx, aTaskdialoginte; "TaskDialogInternal"
0x180021650  mov     rcx, rax; hModule
0x180021653  call    cs:__imp_GetProcAddress
0x180021659  test    rax, rax
0x18002165c  jz      short loc_180021681
0x18002165e  and     r13d, 1
0x180021662  mov     [rsp+1D0h+var_1B0], 0
0x18002166b  mov     edx, r13d
0x18002166e  lea     r8, [rbp+0D0h+pnButton]
0x180021672  xor     r9d, r9d
0x180021675  lea     rcx, [rsp+1D0h+pTaskConfig]
0x18002167a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002167f  jmp     short loc_180021692
0x180021681  xor     r9d, r9d; pfVerificationFlagChecked
0x180021684  lea     rdx, [rbp+0D0h+pnButton]; pnButton
0x180021688  lea     rcx, [rsp+1D0h+pTaskConfig]; pTaskConfig
0x18002168d  call    TaskDialogIndirect
0x180021692  lea     rcx, [rsp+1D0h+var_1A0]
0x180021697  mov     ebx, eax
0x180021699  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002169e  jmp     short loc_1800216B3
0x1800216a0  xor     r9d, r9d; pfVerificationFlagChecked
0x1800216a3  lea     rdx, [rbp+0D0h+pnButton]; pnButton
0x1800216a7  lea     rcx, [rsp+1D0h+pTaskConfig]; pTaskConfig
0x1800216ac  call    TaskDialogIndirect
0x1800216b1  mov     ebx, eax
0x1800216b3  test    ebx, ebx
0x1800216b5  js      short loc_1800216CC
0x1800216b7  test    r14b, 0Fh
0x1800216bb  jnz     short loc_1800216E9
0x1800216bd  cmp     [rbp+0D0h+pnButton], 2
0x1800216c1  jnz     short loc_1800216E9
0x1800216c3  mov     [rbp+0D0h+pnButton], 1
0x1800216ca  jmp     short loc_1800216E9
0x1800216cc  bts     r14d, 10h
0x1800216d1  mov     r8, rdi; lpCaption
0x1800216d4  mov     r9d, r14d; uType
0x1800216d7  mov     rdx, r15; lpText
0x1800216da  mov     rcx, rsi; hWnd
0x1800216dd  mov     r12b, 1
0x1800216e0  call    cs:__imp_MessageBoxW
0x1800216e6  mov     [rbp+0D0h+pnButton], eax
0x1800216e9  mov     rcx, [rbp+0D0h+ulCookie]; ulCookie
0x1800216ed  call    SHDeactivateContext
0x1800216f2  mov     rcx, r15; hMem
0x1800216f5  call    cs:__imp_LocalFree
0x1800216fb  test    ebx, ebx
0x1800216fd  jns     short loc_18002172A
0x1800216ff  test    r12b, r12b
0x180021702  jnz     short loc_180021712
0x180021704  jmp     short loc_18002170B
0x180021706  mov     ebx, 8007000Eh
0x18002170b  mov     [rbp+0D0h+pnButton], 0
0x180021712  mov     eax, ebx
0x180021714  movzx   ecx, bx
0x180021717  and     eax, 1FFF0000h
0x18002171c  cmp     eax, 70000h
0x180021721  cmovnz  ecx, ebx; dwErrCode
0x180021724  call    cs:__imp_SetLastError
0x18002172a  mov     eax, [rbp+0D0h+pnButton]
0x18002172d  mov     rcx, [rbp+0D0h+var_40]
0x180021734  xor     rcx, rsp; StackCookie
0x180021737  call    __security_check_cookie
0x18002173c  mov     rbx, [rsp+1D0h+arg_10]
0x180021744  add     rsp, 1A0h
0x18002174b  pop     r15
0x18002174d  pop     r14
0x18002174f  pop     r13
0x180021751  pop     r12
0x180021753  pop     rdi
0x180021754  pop     rsi
0x180021755  pop     rbp
0x180021756  retn
```
