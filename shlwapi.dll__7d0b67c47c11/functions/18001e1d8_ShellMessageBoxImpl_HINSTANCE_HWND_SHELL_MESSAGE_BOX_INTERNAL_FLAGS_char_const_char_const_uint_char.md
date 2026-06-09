# _ShellMessageBoxImpl(HINSTANCE__ *,HWND__ *,SHELL_MESSAGE_BOX_INTERNAL_FLAGS,char const *,char const *,uint,char * *)

- ea: `0x18001e1d8`
- end: `0x18001e4ce`
- name: `?_ShellMessageBoxImpl@@YAHPEAUHINSTANCE__@@PEAUHWND__@@W4SHELL_MESSAGE_BOX_INTERNAL_FLAGS@@PEBD3IPEAPEAD@Z`
- size: `758`
- prototype: `int __high(HINSTANCE, HWND, enum SHELL_MESSAGE_BOX_INTERNAL_FLAGS, const char *, const char *, unsigned int, char **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e6a0`

## callees

- `0x180012550`
- `0x180013066`
- `0x18001d4f4`
- `0x18001e1d8`
- `0x18001e510`
- `0x18001e54c`
- `0x180035458`
- `0x180035e08`
- `0x180035e70`
- `0x1800362d0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringA` at `0x18001e240`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringA` at `0x18001e240`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e3b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e3b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e4a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e4a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e285`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e285`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e478`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e478`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18001e39e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18001e39e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x18001e26e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x18001e26e`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupA` at `0x18001e2fd`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupA` at `0x18001e31a`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupA` at `0x18001e2fd`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupA` at `0x18001e31a`
- `SHCORE!__imp_SHUnicodeToAnsiCP` at `0x18001e2b3`
- `SHCORE!__imp_SHUnicodeToAnsiCP` at `0x18001e2b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e45f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e46f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e45f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e46f`
- `USER32!GetWindowTextA` at `0x18001e259`
- `USER32!GetWindowTextA` at `0x18001e259`
- `USER32!GetWindowThreadProcessId` at `0x18001e27d`
- `USER32!GetWindowThreadProcessId` at `0x18001e27d`
- `USER32!GetPropA` at `0x18001e299`
- `USER32!GetPropA` at `0x18001e299`
- `USER32!MessageBoxW` at `0x18001e443`
- `USER32!MessageBoxW` at `0x18001e443`

## string_xrefs

- `0x18001e397`: `comctl32.dll`
- `0x18001e3ae`: `TaskDialogInternal`

## pseudocode

```c
__int64 __fastcall _ShellMessageBoxImpl(
        HINSTANCE a1,
        HWND a2,
        __int64 a3,
        __int64 a4,
        LPCSTR psz,
        unsigned int a6,
        __int64 a7)
{
  CHAR *v7; // rdi
  DWORD WindowThreadProcessId; // ebx
  HANDLE PropA; // rax
  const CHAR *v13; // rax
  CHAR *v14; // r14
  char v15; // r15
  HRESULT v16; // ebx
  int *v17; // r8
  HMODULE LibraryA; // rax
  int *v19; // r8
  FARPROC ProcAddress; // rax
  HRESULT v21; // eax
  DWORD v22; // ecx
  HMODULE v24; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR ppwsz; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR v26; // [rsp+40h] [rbp-C0h] BYREF
  TASKDIALOGCONFIG pTaskConfig; // [rsp+50h] [rbp-B0h] BYREF
  int pnButton; // [rsp+F0h] [rbp-10h] BYREF
  ULONG_PTR ulCookie; // [rsp+F8h] [rbp-8h] BYREF
  CHAR Buffer[80]; // [rsp+100h] [rbp+0h] BYREF

  v7 = (CHAR *)psz;
  pnButton = 0;
  if ( (unsigned __int64)psz < 0x10000 && a1 )
  {
    if ( LoadStringA(a1, (unsigned __int16)psz, Buffer, 80) )
    {
LABEL_10:
      v7 = Buffer;
      goto LABEL_12;
    }
    if ( a2 && GetWindowTextA(a2, Buffer, 80) )
    {
      if ( !lstrcmpA(Buffer, "Program Manager") )
      {
        WindowThreadProcessId = GetWindowThreadProcessId(a2, 0);
        if ( WindowThreadProcessId != GetCurrentThreadId() )
          goto LABEL_12;
        PropA = GetPropA(a2, "pszDesktopTitleW");
        if ( PropA )
          SHUnicodeToAnsiCP(0, PropA, Buffer, 80);
      }
      goto LABEL_10;
    }
    v7 = (CHAR *)&qword_18003D748;
  }
LABEL_12:
  v13 = (const CHAR *)ConstructMessageStringA(a1, a4, a7);
  v14 = (CHAR *)v13;
  if ( !v13 )
  {
    v16 = -2147024882;
    goto LABEL_39;
  }
  ppwsz = 0;
  v26 = 0;
  v15 = 0;
  v16 = SHStrDupA(v13, &ppwsz);
  if ( v16 >= 0 )
  {
    if ( v7 )
      v16 = SHStrDupA(v7, &v26);
    if ( v16 >= 0 )
    {
      memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
      pTaskConfig.pszContent = ppwsz;
      pTaskConfig.pszWindowTitle = v26;
      pTaskConfig.cbSize = 160;
      pTaskConfig.hwndParent = a2;
      v16 = ConfigureDialogWithMessageBoxFlags(a6, &pTaskConfig);
      if ( v16 >= 0 )
      {
        ulCookie = 0;
        SHActivateContext(&ulCookie);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
        {
          LibraryA = LoadLibraryA("comctl32.dll");
          v24 = LibraryA;
          if ( LibraryA && (ProcAddress = GetProcAddress(LibraryA, "TaskDialogInternal")) != 0 )
            v21 = ((__int64 (__fastcall *)(TASKDIALOGCONFIG *, _QWORD, int *, _QWORD, _QWORD))ProcAddress)(
                    &pTaskConfig,
                    0,
                    &pnButton,
                    0,
                    0);
          else
            v21 = TaskDialogIndirect(&pTaskConfig, &pnButton, v19, 0);
          v16 = v21;
          wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v24);
        }
        else
        {
          v16 = TaskDialogIndirect(&pTaskConfig, &pnButton, v17, 0);
        }
        if ( v16 < 0 )
        {
          v15 = 1;
          pnButton = MessageBoxW(a2, ppwsz, v26, a6 | 0x10000);
        }
        else if ( (a6 & 0xF) == 0 && pnButton == 2 )
        {
          pnButton = 1;
        }
        SHDeactivateContext(ulCookie);
      }
    }
  }
  if ( ppwsz )
    CoTaskMemFree(ppwsz);
  if ( v26 )
    CoTaskMemFree(v26);
  LocalFree(v14);
  if ( v16 < 0 )
  {
    if ( v15 )
    {
LABEL_40:
      v22 = (unsigned __int16)v16;
      if ( (v16 & 0x1FFF0000) != 0x70000 )
        v22 = v16;
      SetLastError(v22);
      return (unsigned int)pnButton;
    }
LABEL_39:
    pnButton = 0;
    goto LABEL_40;
  }
  return (unsigned int)pnButton;
}

```

## disassembly

```asm
0x18001e1d8  push    rbp
0x18001e1da  push    rbx
0x18001e1db  push    rsi
0x18001e1dc  push    rdi
0x18001e1dd  push    r12
0x18001e1df  push    r14
0x18001e1e1  push    r15
0x18001e1e3  lea     rbp, [rsp-60h]
0x18001e1e8  sub     rsp, 160h
0x18001e1ef  mov     rax, cs:__security_cookie
0x18001e1f6  xor     rax, rsp
0x18001e1f9  mov     [rbp+90h+var_40], rax
0x18001e1fd  mov     rdi, [rbp+90h+psz]
0x18001e204  mov     r15, r9
0x18001e207  mov     r12, [rbp+90h+arg_30]
0x18001e20e  mov     rsi, rdx
0x18001e211  mov     [rbp+90h+pnButton], 0
0x18001e218  mov     r14, rcx
0x18001e21b  cmp     rdi, 10000h
0x18001e222  jnb     loc_18001E2C6
0x18001e228  test    rcx, rcx
0x18001e22b  jz      loc_18001E2C6
0x18001e231  mov     ebx, 50h ; 'P'
0x18001e236  movzx   edx, di; uID
0x18001e239  mov     r9d, ebx; cchBufferMax
0x18001e23c  lea     r8, [rbp+90h+Buffer]; lpBuffer
0x18001e240  call    cs:__imp_LoadStringA
0x18001e246  test    eax, eax
0x18001e248  jnz     short loc_18001E2B9
0x18001e24a  test    rsi, rsi
0x18001e24d  jz      short loc_18001E2BF
0x18001e24f  mov     r8d, ebx; nMaxCount
0x18001e252  lea     rdx, [rbp+90h+Buffer]; lpString
0x18001e256  mov     rcx, rsi; hWnd
0x18001e259  call    cs:__imp_GetWindowTextA
0x18001e25f  test    eax, eax
0x18001e261  jz      short loc_18001E2BF
0x18001e263  lea     rdx, String2; "Program Manager"
0x18001e26a  lea     rcx, [rbp+90h+Buffer]; lpString1
0x18001e26e  call    cs:__imp_lstrcmpA
0x18001e274  test    eax, eax
0x18001e276  jnz     short loc_18001E2B9
0x18001e278  xor     edx, edx; lpdwProcessId
0x18001e27a  mov     rcx, rsi; hWnd
0x18001e27d  call    cs:__imp_GetWindowThreadProcessId
0x18001e283  mov     ebx, eax
0x18001e285  call    cs:__imp_GetCurrentThreadId
0x18001e28b  cmp     ebx, eax
0x18001e28d  jnz     short loc_18001E2C6
0x18001e28f  lea     rdx, aPszdesktoptitl; "pszDesktopTitleW"
0x18001e296  mov     rcx, rsi; hWnd
0x18001e299  call    cs:__imp_GetPropA
0x18001e29f  test    rax, rax
0x18001e2a2  jz      short loc_18001E2B9
0x18001e2a4  mov     r9d, 50h ; 'P'
0x18001e2aa  lea     r8, [rbp+90h+Buffer]
0x18001e2ae  mov     rdx, rax
0x18001e2b1  xor     ecx, ecx
0x18001e2b3  call    cs:__imp_SHUnicodeToAnsiCP
0x18001e2b9  lea     rdi, [rbp+90h+Buffer]
0x18001e2bd  jmp     short loc_18001E2C6
0x18001e2bf  lea     rdi, qword_18003D748
0x18001e2c6  mov     r8, r12
0x18001e2c9  mov     rdx, r15
0x18001e2cc  mov     rcx, r14
0x18001e2cf  call    ConstructMessageStringA
0x18001e2d4  mov     r14, rax
0x18001e2d7  test    rax, rax
0x18001e2da  jz      loc_18001E489
0x18001e2e0  lea     rdx, [rsp+190h+ppwsz]; ppwsz
0x18001e2e5  mov     [rsp+190h+ppwsz], 0
0x18001e2ee  mov     rcx, rax; psz
0x18001e2f1  mov     [rsp+190h+var_150], 0
0x18001e2fa  xor     r15b, r15b
0x18001e2fd  call    cs:__imp_SHStrDupA
0x18001e303  mov     ebx, eax
0x18001e305  test    eax, eax
0x18001e307  js      loc_18001E455
0x18001e30d  test    rdi, rdi
0x18001e310  jz      short loc_18001E322
0x18001e312  lea     rdx, [rsp+190h+var_150]; ppwsz
0x18001e317  mov     rcx, rdi; psz
0x18001e31a  call    cs:__imp_SHStrDupA
0x18001e320  mov     ebx, eax
0x18001e322  test    ebx, ebx
0x18001e324  js      loc_18001E455
0x18001e32a  mov     ebx, 0A0h
0x18001e32f  lea     rcx, [rsp+190h+pTaskConfig]; void *
0x18001e334  mov     r8d, ebx; Size
0x18001e337  xor     edx, edx; Val
0x18001e339  call    memset_0
0x18001e33e  mov     rax, [rsp+190h+ppwsz]
0x18001e343  lea     rdx, [rsp+190h+pTaskConfig]; struct _TASKDIALOGCONFIG *
0x18001e348  mov     edi, [rbp+90h+arg_28]
0x18001e34e  mov     ecx, edi; unsigned int
0x18001e350  mov     [rbp+90h+pTaskConfig.pszContent], rax
0x18001e354  mov     rax, [rsp+190h+var_150]
0x18001e359  mov     [rsp+190h+pTaskConfig.pszWindowTitle], rax
0x18001e35e  mov     [rsp+190h+pTaskConfig.cbSize], ebx
0x18001e362  mov     [rsp+190h+pTaskConfig.hwndParent], rsi
0x18001e367  call    ?ConfigureDialogWithMessageBoxFlags@@YAJKPEAU_TASKDIALOGCONFIG@@@Z; ConfigureDialogWithMessageBoxFlags(ulong,_TASKDIALOGCONFIG *)
0x18001e36c  mov     ebx, eax
0x18001e36e  test    eax, eax
0x18001e370  js      loc_18001E455
0x18001e376  lea     rcx, [rbp+90h+ulCookie]
0x18001e37a  mov     [rbp+90h+ulCookie], 0
0x18001e382  call    SHActivateContext
0x18001e387  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x18001e38e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(wil::ReportingKind)
0x18001e393  test    al, al
0x18001e395  jz      short loc_18001E400
0x18001e397  lea     rcx, LibFileName; "comctl32.dll"
0x18001e39e  call    cs:__imp_LoadLibraryA
0x18001e3a4  mov     [rsp+190h+var_160], rax
0x18001e3a9  test    rax, rax
0x18001e3ac  jz      short loc_18001E3E1
0x18001e3ae  lea     rdx, aTaskdialoginte; "TaskDialogInternal"
0x18001e3b5  mov     rcx, rax; hModule
0x18001e3b8  call    cs:__imp_GetProcAddress
0x18001e3be  test    rax, rax
0x18001e3c1  jz      short loc_18001E3E1
0x18001e3c3  xor     r9d, r9d
0x18001e3c6  mov     [rsp+190h+var_170], 0
0x18001e3cf  lea     r8, [rbp+90h+pnButton]
0x18001e3d3  xor     edx, edx
0x18001e3d5  lea     rcx, [rsp+190h+pTaskConfig]
0x18001e3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3df  jmp     short loc_18001E3F2
0x18001e3e1  xor     r9d, r9d; pfVerificationFlagChecked
0x18001e3e4  lea     rdx, [rbp+90h+pnButton]; pnButton
0x18001e3e8  lea     rcx, [rsp+190h+pTaskConfig]; pTaskConfig
0x18001e3ed  call    TaskDialogIndirect
0x18001e3f2  lea     rcx, [rsp+190h+var_160]
0x18001e3f7  mov     ebx, eax
0x18001e3f9  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18001e3fe  jmp     short loc_18001E413
0x18001e400  xor     r9d, r9d; pfVerificationFlagChecked
0x18001e403  lea     rdx, [rbp+90h+pnButton]; pnButton
0x18001e407  lea     rcx, [rsp+190h+pTaskConfig]; pTaskConfig
0x18001e40c  call    TaskDialogIndirect
0x18001e411  mov     ebx, eax
0x18001e413  test    ebx, ebx
0x18001e415  js      short loc_18001E42C
0x18001e417  test    dil, 0Fh
0x18001e41b  jnz     short loc_18001E44C
0x18001e41d  cmp     [rbp+90h+pnButton], 2
0x18001e421  jnz     short loc_18001E44C
0x18001e423  mov     [rbp+90h+pnButton], 1
0x18001e42a  jmp     short loc_18001E44C
0x18001e42c  mov     r8, [rsp+190h+var_150]; lpCaption
0x18001e431  bts     edi, 10h
0x18001e435  mov     rdx, [rsp+190h+ppwsz]; lpText
0x18001e43a  mov     r9d, edi; uType
0x18001e43d  mov     rcx, rsi; hWnd
0x18001e440  mov     r15b, 1
0x18001e443  call    cs:__imp_MessageBoxW
0x18001e449  mov     [rbp+90h+pnButton], eax
0x18001e44c  mov     rcx, [rbp+90h+ulCookie]; ulCookie
0x18001e450  call    SHDeactivateContext
0x18001e455  mov     rcx, [rsp+190h+ppwsz]; pv
0x18001e45a  test    rcx, rcx
0x18001e45d  jz      short loc_18001E465
0x18001e45f  call    cs:__imp_CoTaskMemFree
0x18001e465  mov     rcx, [rsp+190h+var_150]; pv
0x18001e46a  test    rcx, rcx
0x18001e46d  jz      short loc_18001E475
0x18001e46f  call    cs:__imp_CoTaskMemFree
0x18001e475  mov     rcx, r14; hMem
0x18001e478  call    cs:__imp_LocalFree
0x18001e47e  test    ebx, ebx
0x18001e480  jns     short loc_18001E4AD
0x18001e482  test    r15b, r15b
0x18001e485  jnz     short loc_18001E495
0x18001e487  jmp     short loc_18001E48E
0x18001e489  mov     ebx, 8007000Eh
0x18001e48e  mov     [rbp+90h+pnButton], 0
0x18001e495  mov     eax, ebx
0x18001e497  movzx   ecx, bx
0x18001e49a  and     eax, 1FFF0000h
0x18001e49f  cmp     eax, 70000h
0x18001e4a4  cmovnz  ecx, ebx; dwErrCode
0x18001e4a7  call    cs:__imp_SetLastError
0x18001e4ad  mov     eax, [rbp+90h+pnButton]
0x18001e4b0  mov     rcx, [rbp+90h+var_40]
0x18001e4b4  xor     rcx, rsp; StackCookie
0x18001e4b7  call    __security_check_cookie
0x18001e4bc  add     rsp, 160h
0x18001e4c3  pop     r15
0x18001e4c5  pop     r14
0x18001e4c7  pop     r12
0x18001e4c9  pop     rdi
0x18001e4ca  pop     rsi
0x18001e4cb  pop     rbx
0x18001e4cc  pop     rbp
0x18001e4cd  retn
```
