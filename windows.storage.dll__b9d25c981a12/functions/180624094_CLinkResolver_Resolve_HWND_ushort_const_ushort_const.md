# CLinkResolver::Resolve(HWND__ *,ushort const *,ushort const *)

- ea: `0x180624094`
- end: `0x1806244de`
- name: `?Resolve@CLinkResolver@@QEAAHPEAUHWND__@@PEBG1@Z`
- size: `1098`
- prototype: `__int64 __fastcall(LPARAM this, HWND hWndParent, LPCWSTR pszPath, LPCWSTR)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x18015dabc`

## callees

- `0x180117f6c`
- `0x180133f50`
- `0x1801642d4`
- `0x18027dd3c`
- `0x18027fbe8`
- `0x1802b1260`
- `0x18031d6dc`
- `0x1803b1f60`
- `0x18052dc04`
- `0x180621e8c`
- `0x180621f64`
- `0x180624094`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18062416a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18062416a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18062417a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18062417a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1806240f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1806240f6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1806240d7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1806240d7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1806240ea`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1806240ea`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180624203`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18062427b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1806242ae`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180624310`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18062433f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180624203`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18062427b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1806242ae`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180624310`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18062433f`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThreadWithHandle` at `0x18062414c`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThreadWithHandle` at `0x18062414c`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x1806242e5`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x180624379`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x1806242e5`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x180624379`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLinkResolver::Resolve(LPARAM this, HWND hWndParent, LPCWSTR pszPath, LPCWSTR a4)
{
  WCHAR *v8; // rbx
  DWORD TimeOut; // eax
  unsigned int v10; // ebx
  HINSTANCE v11; // rax
  int v12; // ecx
  int v13; // eax
  LPWSTR FileNameW; // rbx
  HINSTANCE v15; // rax
  __int64 v16; // r8
  HINSTANCE v17; // rax
  __int64 v18; // r8
  LPWSTR v19; // rbx
  HINSTANCE v20; // rax
  int v21; // eax
  LPWSTR v22; // rbx
  HINSTANCE v23; // rax
  __int64 v24; // rbx
  HINSTANCE v25; // rax
  __int64 v26; // rdx
  _OWORD *v27; // rax
  _OWORD *v28; // rsi
  __int64 v29; // rcx
  int pHandle; // [rsp+20h] [rbp-50h]
  __int64 v32; // [rsp+40h] [rbp-30h] BYREF
  HANDLE hHandle; // [rsp+48h] [rbp-28h] BYREF
  LPARAM v34; // [rsp+50h] [rbp-20h] BYREF
  LPARAM v35; // [rsp+58h] [rbp-18h]
  LPCWSTR v36; // [rsp+60h] [rbp-10h]

  v8 = (WCHAR *)(this + 2036);
  StringCchCopyW((unsigned __int16 *)(this + 2036), 0x104u, pszPath);
  if ( !PathIsRootW(v8) )
    PathRemoveFileSpecW(v8);
  *(_DWORD *)(this + 824) = GetTickCount();
  v32 = 0;
  if ( (*(_DWORD *)(this + 2032) & 0x101) == 1 )
  {
    hHandle = 0;
    _InterlockedIncrement((volatile signed __int32 *)(this + 16));
    if ( !SHCreateThreadWithHandle(
            lambda_469cb8603dcf52f8cda9d5d6a8068e20_::_lambda_invoker_cdecl_,
            (void *)this,
            0x218u,
            0,
            &hHandle) )
    {
      v10 = 2;
      CBaseTreeWalkerCB::Release((CBaseTreeWalkerCB *)(this + 8));
      goto LABEL_38;
    }
    TimeOut = CLinkResolver::_GetTimeOut((CLinkResolver *)this);
    WaitForSingleObject(hHandle, TimeOut);
    CloseHandle(hHandle);
    *(_BYTE *)(this + 828) = 0;
    v10 = 1;
  }
  else
  {
    v11 = Shell32Instance::get((Shell32Instance *)&v32);
    v10 = SHFusionDialogBoxParam(v11, (LPCWSTR)0x3EC, hWndParent, (DLGPROC)CLinkResolver::_DlgProc, this);
    if ( v10 != 1 )
      goto LABEL_38;
  }
  v12 = *(_DWORD *)(this + 840);
  if ( v12 >= 40 )
  {
    if ( !(unsigned int)PathIsUnderWinsxs((LPCWCH)(this + 888)) )
      goto LABEL_38;
    if ( (*(_BYTE *)(this + 2032) & 1) != 0 )
      goto LABEL_35;
    v34 = (LPARAM)pszPath;
    v35 = this + 888;
    v36 = a4;
    v25 = Shell32Instance::get((Shell32Instance *)&v32);
    v26 = 1009;
LABEL_37:
    v10 = SHFusionDialogBoxParam(v25, (LPCWSTR)v26, hWndParent, (DLGPROC)DeadLinkProc, (LPARAM)&v34);
    goto LABEL_38;
  }
  v13 = *(_DWORD *)(this + 2032);
  if ( (v13 & 1) != 0 )
  {
LABEL_35:
    v10 = 2;
    goto LABEL_38;
  }
  if ( (*(_BYTE *)(this + 48) & 1) != 0 )
  {
    if ( a4 )
      FileNameW = PathFindFileNameW(a4);
    else
      FileNameW = (LPWSTR)&c_szNULL;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
    {
      v15 = Shell32Instance::get((Shell32Instance *)&v32);
      v16 = 4215;
LABEL_22:
      MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short_const____1(
        v15,
        hWndParent,
        (LPCWSTR)v16,
        pHandle,
        (__int64)FileNameW);
      goto LABEL_35;
    }
    v17 = Shell32Instance::get((Shell32Instance *)&v32);
    v18 = 4215;
    goto LABEL_24;
  }
  if ( a4 || (v13 & 0x200) != 0 )
  {
    v34 = (LPARAM)pszPath;
    v35 = this + 888;
    v36 = a4;
    if ( *(_DWORD *)(this + 1436) )
      v24 = 1006;
    else
      v24 = (v12 <= 10) + 1008LL;
    v25 = Shell32Instance::get((Shell32Instance *)&v32);
    v26 = v24;
    goto LABEL_37;
  }
  if ( v12 <= 10 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
    {
      FileNameW = PathFindFileNameW(pszPath);
      v15 = Shell32Instance::get((Shell32Instance *)&v32);
      v16 = 4211;
      goto LABEL_22;
    }
    FileNameW = PathFindFileNameW(pszPath);
    v17 = Shell32Instance::get((Shell32Instance *)&v32);
    v18 = 4211;
LABEL_24:
    ShellMessageBoxW(v17, hWndParent, (LPCWSTR)v18, (LPCWSTR)0x1070, 0x30u, FileNameW);
    goto LABEL_35;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
  {
    v19 = PathFindFileNameW(pszPath);
    v20 = Shell32Instance::get((Shell32Instance *)&v32);
    v21 = MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short_const___unsigned_short___(
            v20,
            hWndParent,
            pHandle,
            (__int64)v19,
            this + 888);
  }
  else
  {
    v22 = PathFindFileNameW(pszPath);
    v23 = Shell32Instance::get((Shell32Instance *)&v32);
    v21 = ShellMessageBoxW(v23, hWndParent, (LPCWSTR)0x1074, (LPCWSTR)0x1070, 0x34u, v22, this + 888);
  }
  v10 = (v21 != 6) + 1;
LABEL_38:
  v27 = (_OWORD *)(this + 232);
  v28 = (_OWORD *)(this + 844);
  v29 = 4;
  do
  {
    *v27 = *v28;
    v27[1] = v28[1];
    v27[2] = v28[2];
    v27[3] = v28[3];
    v27[4] = v28[4];
    v27[5] = v28[5];
    v27[6] = v28[6];
    v27[7] = v28[7];
    v27 += 8;
    v28 += 8;
    --v29;
  }
  while ( v29 );
  *v27 = *v28;
  v27[1] = v28[1];
  v27[2] = v28[2];
  v27[3] = v28[3];
  v27[4] = v28[4];
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v32);
  return v10;
}

```

## disassembly

```asm
0x180624094  push    rbp
0x180624096  push    rbx
0x180624097  push    rsi
0x180624098  push    rdi
0x180624099  push    r12
0x18062409b  push    r14
0x18062409d  push    r15
0x18062409f  mov     rbp, rsp
0x1806240a2  sub     rsp, 70h
0x1806240a6  mov     rax, cs:__security_cookie
0x1806240ad  xor     rax, rsp
0x1806240b0  mov     [rbp+var_8], rax
0x1806240b4  mov     rdi, r9
0x1806240b7  mov     r15, r8
0x1806240ba  mov     r14, rdx
0x1806240bd  mov     rsi, rcx
0x1806240c0  lea     rbx, [rcx+7F4h]
0x1806240c7  mov     edx, 104h; unsigned __int64
0x1806240cc  mov     rcx, rbx; unsigned __int16 *
0x1806240cf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1806240d4  mov     rcx, rbx; pszPath
0x1806240d7  call    cs:__imp_PathIsRootW
0x1806240de  nop     dword ptr [rax+rax+00h]
0x1806240e3  test    eax, eax
0x1806240e5  jnz     short loc_1806240F6
0x1806240e7  mov     rcx, rbx; pszPath
0x1806240ea  call    cs:__imp_PathRemoveFileSpecW
0x1806240f1  nop     dword ptr [rax+rax+00h]
0x1806240f6  call    cs:__imp_GetTickCount
0x1806240fd  nop     dword ptr [rax+rax+00h]
0x180624102  mov     [rsi+338h], eax
0x180624108  mov     [rbp+var_30], 0
0x180624110  mov     eax, [rsi+7F0h]
0x180624116  and     eax, 101h
0x18062411b  cmp     eax, 1
0x18062411e  jnz     loc_1806241A7
0x180624124  mov     [rbp+hHandle], 0
0x18062412c  lock inc dword ptr [rsi+10h]
0x180624130  lea     rax, [rbp+hHandle]
0x180624134  mov     [rsp+70h+pHandle], rax; pHandle
0x180624139  xor     r9d, r9d; pfnCallback
0x18062413c  mov     r8d, 218h; flags
0x180624142  mov     rdx, rsi; pData
0x180624145  lea     rcx, _lambda_469cb8603dcf52f8cda9d5d6a8068e20____lambda_invoker_cdecl_; pfnThreadProc
0x18062414c  call    cs:__imp_SHCreateThreadWithHandle
0x180624153  nop     dword ptr [rax+rax+00h]
0x180624158  test    eax, eax
0x18062415a  jz      short loc_180624194
0x18062415c  mov     rcx, rsi; this
0x18062415f  call    ?_GetTimeOut@CLinkResolver@@AEAAKXZ; CLinkResolver::_GetTimeOut(void)
0x180624164  mov     edx, eax; dwMilliseconds
0x180624166  mov     rcx, [rbp+hHandle]; hHandle
0x18062416a  call    cs:__imp_WaitForSingleObject
0x180624171  nop     dword ptr [rax+rax+00h]
0x180624176  mov     rcx, [rbp+hHandle]; hObject
0x18062417a  call    cs:__imp_CloseHandle
0x180624181  nop     dword ptr [rax+rax+00h]
0x180624186  mov     byte ptr [rsi+33Ch], 0
0x18062418d  mov     ebx, 1
0x180624192  jmp     short loc_1806241D8
0x180624194  mov     ebx, 2
0x180624199  lea     rcx, [rsi+8]; this
0x18062419d  call    ?Release@CBaseTreeWalkerCB@@UEAAKXZ; CBaseTreeWalkerCB::Release(void)
0x1806241a2  jmp     loc_180624431
0x1806241a7  lea     rcx, [rbp+var_30]; this
0x1806241ab  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1806241b0  mov     rcx, rax; hInstance
0x1806241b3  mov     [rsp+70h+pHandle], rsi; int
0x1806241b8  lea     r9, ?_DlgProc@CLinkResolver@@CA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x1806241bf  mov     r8, r14; hWndParent
0x1806241c2  mov     edx, 3ECh; lpTemplateName
0x1806241c7  call    SHFusionDialogBoxParam
0x1806241cc  mov     rbx, rax
0x1806241cf  cmp     eax, 1
0x1806241d2  jnz     loc_180624431
0x1806241d8  mov     ecx, [rsi+348h]
0x1806241de  cmp     ecx, 28h ; '('
0x1806241e1  jge     loc_1806243D7
0x1806241e7  mov     eax, [rsi+7F0h]
0x1806241ed  test    al, 1
0x1806241ef  jnz     loc_1806243F3
0x1806241f5  test    byte ptr [rsi+30h], 1
0x1806241f9  jz      short loc_18062424C
0x1806241fb  test    rdi, rdi
0x1806241fe  jz      short loc_180624214
0x180624200  mov     rcx, rdi; pszPath
0x180624203  call    cs:__imp_PathFindFileNameW
0x18062420a  nop     dword ptr [rax+rax+00h]
0x18062420f  mov     rbx, rax
0x180624212  jmp     short loc_18062421B
0x180624214  lea     rbx, c_szNULL
0x18062421b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x180624222  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x180624227  lea     rcx, [rbp+var_30]; this
0x18062422b  test    al, al
0x18062422d  jz      short loc_18062423C
0x18062422f  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x180624234  mov     r8d, 1077h
0x18062423a  jmp     short loc_180624299
0x18062423c  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x180624241  mov     r8d, 1077h
0x180624247  jmp     loc_1806242CC
0x18062424c  test    rdi, rdi
0x18062424f  jnz     loc_180624397
0x180624255  bt      eax, 9
0x180624259  jb      loc_180624397
0x18062425f  cmp     ecx, 0Ah
0x180624262  jg      loc_1806242F6
0x180624268  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x18062426f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x180624274  mov     rcx, r15; pszPath
0x180624277  test    al, al
0x180624279  jz      short loc_1806242AE
0x18062427b  call    cs:__imp_PathFindFileNameW
0x180624282  nop     dword ptr [rax+rax+00h]
0x180624287  mov     rbx, rax
0x18062428a  lea     rcx, [rbp+var_30]; this
0x18062428e  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x180624293  mov     r8d, 1073h; lpcText
0x180624299  mov     rcx, rax; hAppInst
0x18062429c  mov     rdx, r14; hWnd
0x18062429f  mov     [rsp+70h+var_48], rbx; __int64
0x1806242a4  call    MessageBoxHelper__ShellMessageBoxTextScaled_unsigned_short_const____1
0x1806242a9  jmp     loc_1806243F3
0x1806242ae  call    cs:__imp_PathFindFileNameW
0x1806242b5  nop     dword ptr [rax+rax+00h]
0x1806242ba  mov     rbx, rax
0x1806242bd  lea     rcx, [rbp+var_30]; this
0x1806242c1  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1806242c6  mov     r8d, 1073h; lpcText
0x1806242cc  mov     [rsp+70h+var_48], rbx
0x1806242d1  mov     rcx, rax; hAppInst
0x1806242d4  mov     rdx, r14; hWnd
0x1806242d7  mov     r9d, 1070h; lpcTitle
0x1806242dd  mov     dword ptr [rsp+70h+pHandle], 30h ; '0'; fuStyle
0x1806242e5  call    cs:__imp_ShellMessageBoxW
0x1806242ec  nop     dword ptr [rax+rax+00h]
0x1806242f1  jmp     loc_1806243F3
0x1806242f6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x1806242fd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x180624302  lea     rdi, [rsi+378h]
0x180624309  mov     rcx, r15; pszPath
0x18062430c  test    al, al
0x18062430e  jz      short loc_18062433F
0x180624310  call    cs:__imp_PathFindFileNameW
0x180624317  nop     dword ptr [rax+rax+00h]
0x18062431c  mov     rbx, rax
0x18062431f  lea     rcx, [rbp+var_30]; this
0x180624323  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x180624328  mov     [rsp+70h+var_40], rdi; __int64
0x18062432d  mov     [rsp+70h+var_48], rbx; __int64
0x180624332  mov     rdx, r14; hWnd
0x180624335  mov     rcx, rax; hAppInst
0x180624338  call    MessageBoxHelper__ShellMessageBoxTextScaled_unsigned_short_const___unsigned_short___
0x18062433d  jmp     short loc_180624385
0x18062433f  call    cs:__imp_PathFindFileNameW
0x180624346  nop     dword ptr [rax+rax+00h]
0x18062434b  mov     rbx, rax
0x18062434e  lea     rcx, [rbp+var_30]; this
0x180624352  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x180624357  mov     [rsp+70h+var_40], rdi
0x18062435c  mov     [rsp+70h+var_48], rbx
0x180624361  mov     dword ptr [rsp+70h+pHandle], 34h ; '4'; fuStyle
0x180624369  mov     r9d, 1070h; lpcTitle
0x18062436f  lea     r8d, [r9+4]; lpcText
0x180624373  mov     rdx, r14; hWnd
0x180624376  mov     rcx, rax; hAppInst
0x180624379  call    cs:__imp_ShellMessageBoxW
0x180624380  nop     dword ptr [rax+rax+00h]
0x180624385  mov     ecx, eax
0x180624387  xor     eax, eax
0x180624389  cmp     ecx, 6
0x18062438c  setnz   al
0x18062438f  lea     ebx, [rax+1]
0x180624392  jmp     loc_180624431
0x180624397  mov     [rbp+var_20], r15
0x18062439b  lea     rax, [rsi+378h]
0x1806243a2  mov     [rbp+var_18], rax
0x1806243a6  mov     [rbp+var_10], rdi
0x1806243aa  cmp     dword ptr [rsi+59Ch], 0
0x1806243b1  jz      short loc_1806243BA
0x1806243b3  mov     ebx, 3EEh
0x1806243b8  jmp     short loc_1806243C9
0x1806243ba  xor     ebx, ebx
0x1806243bc  cmp     ecx, 0Ah
0x1806243bf  setle   bl
0x1806243c2  add     rbx, 3F0h
0x1806243c9  lea     rcx, [rbp+var_30]; this
0x1806243cd  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x1806243d2  mov     rdx, rbx
0x1806243d5  jmp     short loc_180624414
0x1806243d7  lea     r12, [rsi+378h]
0x1806243de  mov     rcx, r12; lpString1
0x1806243e1  call    PathIsUnderWinsxs
0x1806243e6  test    eax, eax
0x1806243e8  jz      short loc_180624431
0x1806243ea  test    byte ptr [rsi+7F0h], 1
0x1806243f1  jz      short loc_1806243FA
0x1806243f3  mov     ebx, 2
0x1806243f8  jmp     short loc_180624431
0x1806243fa  mov     [rbp+var_20], r15
0x1806243fe  mov     [rbp+var_18], r12
0x180624402  mov     [rbp+var_10], rdi
0x180624406  lea     rcx, [rbp+var_30]; this
0x18062440a  call    ?get@Shell32Instance@@QEAAPEAUHINSTANCE__@@XZ; Shell32Instance::get(void)
0x18062440f  mov     edx, 3F1h; lpTemplateName
0x180624414  mov     rcx, rax; hInstance
0x180624417  lea     rax, [rbp+var_20]
0x18062441b  mov     [rsp+70h+pHandle], rax; LPARAM
0x180624420  lea     r9, ?DeadLinkProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180624427  mov     r8, r14; hWndParent
0x18062442a  call    SHFusionDialogBoxParam
0x18062442f  mov     ebx, eax
0x180624431  lea     rax, [rsi+0E8h]
0x180624438  add     rsi, 34Ch
0x18062443f  mov     ecx, 4
0x180624444  lea     edx, [rcx+7Ch]
0x180624447  movups  xmm0, xmmword ptr [rsi]
0x18062444a  movups  xmmword ptr [rax], xmm0
0x18062444d  movups  xmm1, xmmword ptr [rsi+10h]
0x180624451  movups  xmmword ptr [rax+10h], xmm1
0x180624455  movups  xmm0, xmmword ptr [rsi+20h]
0x180624459  movups  xmmword ptr [rax+20h], xmm0
0x18062445d  movups  xmm1, xmmword ptr [rsi+30h]
0x180624461  movups  xmmword ptr [rax+30h], xmm1
0x180624465  movups  xmm0, xmmword ptr [rsi+40h]
0x180624469  movups  xmmword ptr [rax+40h], xmm0
0x18062446d  movups  xmm1, xmmword ptr [rsi+50h]
0x180624471  movups  xmmword ptr [rax+50h], xmm1
0x180624475  movups  xmm0, xmmword ptr [rsi+60h]
0x180624479  movups  xmmword ptr [rax+60h], xmm0
0x18062447d  movups  xmm1, xmmword ptr [rsi+70h]
0x180624481  movups  xmmword ptr [rax+70h], xmm1
0x180624485  add     rax, rdx
0x180624488  add     rsi, rdx
0x18062448b  sub     rcx, 1
0x18062448f  jnz     short loc_180624447
0x180624491  movups  xmm0, xmmword ptr [rsi]
0x180624494  movups  xmmword ptr [rax], xmm0
0x180624497  movups  xmm1, xmmword ptr [rsi+10h]
0x18062449b  movups  xmmword ptr [rax+10h], xmm1
0x18062449f  movups  xmm0, xmmword ptr [rsi+20h]
0x1806244a3  movups  xmmword ptr [rax+20h], xmm0
0x1806244a7  movups  xmm1, xmmword ptr [rsi+30h]
0x1806244ab  movups  xmmword ptr [rax+30h], xmm1
0x1806244af  movups  xmm0, xmmword ptr [rsi+40h]
0x1806244b3  movups  xmmword ptr [rax+40h], xmm0
0x1806244b7  lea     rcx, [rbp+var_30]
0x1806244bb  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1806244c0  mov     eax, ebx
0x1806244c2  mov     rcx, [rbp+var_8]
0x1806244c6  xor     rcx, rsp; StackCookie
0x1806244c9  call    __security_check_cookie
0x1806244ce  add     rsp, 70h
0x1806244d2  pop     r15
0x1806244d4  pop     r14
0x1806244d6  pop     r12
0x1806244d8  pop     rdi
0x1806244d9  pop     rsi
0x1806244da  pop     rbx
0x1806244db  pop     rbp
0x1806244dc  retn
```
