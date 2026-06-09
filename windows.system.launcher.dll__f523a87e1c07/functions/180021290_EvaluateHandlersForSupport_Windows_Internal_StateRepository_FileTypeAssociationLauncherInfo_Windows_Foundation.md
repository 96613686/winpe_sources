# EvaluateHandlersForSupport<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo>(Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo *> *,HSTRING__ *,Windows::System::LaunchQuerySupportStatus *)

- ea: `0x180021290`
- end: `0x18002148b`
- name: `??$EvaluateHandlersForSupport@VFileTypeAssociationLauncherInfo@StateRepository@Internal@Windows@@@@YAJPEAU?$IVectorView@PEAVFileTypeAssociationLauncherInfo@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@PEAUHSTRING__@@PEAW4LaunchQuerySupportStatus@System@3@@Z`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020800`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x180021290`
- `0x180021a88`
- `0x18002c92c`
- `0x180111010`

## import_xrefs

- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x1800213cf`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x1800213cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800213c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800213c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021397`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800213e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800213f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002142d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021397`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800213e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800213f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002142d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EvaluateHandlersForSupport<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo>(
        __int64 a1,
        HSTRING a2,
        _DWORD *a3)
{
  int v5; // eax
  __int64 (__fastcall *v6)(__int64, _QWORD, _QWORD *); // rbx
  int v7; // eax
  int v8; // esi
  int v9; // r15d
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  int v15; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v17; // [rsp+20h] [rbp-30h] BYREF
  int v18; // [rsp+28h] [rbp-28h] BYREF
  char **v19; // [rsp+30h] [rbp-20h]
  int v20; // [rsp+38h] [rbp-18h]
  _QWORD v21[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  int v23; // [rsp+90h] [rbp+40h] BYREF
  char *v24; // [rsp+A0h] [rbp+50h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+58h] BYREF

  *a3 = 3;
  LODWORD(v24) = 0;
  v17 = a1;
  v19 = &v24;
  v20 = 0;
  v21[0] = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a1 + 56LL))(a1, &v18);
  *(_DWORD *)v19 = v5;
  if ( v5 >= 0 && v18 )
  {
    v6 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v17 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v21);
    v7 = v6(v17, 0, v21);
    *(_DWORD *)v19 = v7;
  }
  v8 = 0;
  v9 = v18;
  while ( 1 )
  {
    if ( *(int *)v19 < 0 || v8 == v9 )
      goto LABEL_6;
    *a3 = 2;
    string = 0;
    v13 = v21[0];
    v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v21[0] + 120LL);
    WindowsDeleteString(0);
    string = 0;
    v15 = v14(v13, &string);
    v10 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x277,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
        (const char *)(unsigned int)v15,
        v17);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v21);
      return v10;
    }
    v23 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( !(unsigned int)GetEffectivePackageStatusForUser(0, StringRawBuffer, &v23) && (v23 & 0x40003DF) == 0 )
      break;
    WindowsDeleteString(string);
    wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerGroup *>>::get_at_current(
      &v17,
      (unsigned int)++v8);
  }
  *a3 = 0;
  WindowsDeleteString(string);
LABEL_6:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v21);
  if ( *a3 == 3 && a2 )
  {
    LOBYTE(v23) = 0;
    v10 = IsPackagePresent(a2, (bool *)&v23);
    if ( (v10 & 0x80000000) != 0 )
    {
      v11 = 645;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
        (const char *)v10,
        v17);
      return v10;
    }
    if ( !(_BYTE)v23 )
      *a3 = 1;
  }
  v10 = (unsigned int)v24;
  if ( (int)v24 < 0 )
  {
    v11 = 652;
    goto LABEL_9;
  }
  return 0;
}

```

## disassembly

```asm
0x180021290  mov     [rsp-38h+arg_8], rbx
0x180021295  push    rbp
0x180021296  push    rsi
0x180021297  push    rdi
0x180021298  push    r12
0x18002129a  push    r13
0x18002129c  push    r14
0x18002129e  push    r15
0x1800212a0  mov     rbp, rsp
0x1800212a3  sub     rsp, 50h
0x1800212a7  mov     r14, r8
0x1800212aa  mov     r12, rdx
0x1800212ad  xor     r13d, r13d
0x1800212b0  mov     dword ptr [r8], 3
0x1800212b7  mov     dword ptr [rbp+arg_10], r13d
0x1800212bb  mov     [rbp+var_30], rcx
0x1800212bf  lea     rax, [rbp+arg_10]
0x1800212c3  mov     [rbp+var_20], rax
0x1800212c7  mov     [rbp+var_18], r13d
0x1800212cb  mov     [rbp+var_10], r13
0x1800212cf  mov     rax, [rcx]
0x1800212d2  lea     rdx, [rbp+var_28]
0x1800212d6  mov     rax, [rax+38h]
0x1800212da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212df  mov     rcx, [rbp+var_20]
0x1800212e3  mov     [rcx], eax
0x1800212e5  test    eax, eax
0x1800212e7  js      short loc_18002131A
0x1800212e9  cmp     [rbp+var_28], r13d
0x1800212ed  jbe     short loc_18002131A
0x1800212ef  mov     rdi, [rbp+var_30]
0x1800212f3  mov     rax, [rdi]
0x1800212f6  mov     rbx, [rax+30h]
0x1800212fa  lea     rcx, [rbp+var_10]
0x1800212fe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180021303  lea     r8, [rbp+var_10]
0x180021307  xor     edx, edx
0x180021309  mov     rcx, rdi
0x18002130c  mov     rax, rbx
0x18002130f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021314  mov     rcx, [rbp+var_20]
0x180021318  mov     [rcx], eax
0x18002131a  mov     esi, r13d
0x18002131d  mov     r15d, [rbp+var_28]
0x180021321  mov     rax, [rbp+var_20]
0x180021325  cmp     [rax], r13d
0x180021328  jge     short loc_18002137A
0x18002132a  lea     rcx, [rbp+var_10]
0x18002132e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180021333  cmp     dword ptr [r14], 3
0x180021337  jz      loc_180021445
0x18002133d  mov     ebx, dword ptr [rbp+arg_10]
0x180021340  test    ebx, ebx
0x180021342  jns     loc_180021484
0x180021348  mov     edx, 28Ch; void *
0x18002134d  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x180021354  mov     r9d, ebx; char *
0x180021357  mov     rcx, [rbp+38h]; this
0x18002135b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021360  mov     eax, ebx
0x180021362  mov     rbx, [rsp+50h+arg_8]
0x18002136a  add     rsp, 50h
0x18002136e  pop     r15
0x180021370  pop     r14
0x180021372  pop     r13
0x180021374  pop     r12
0x180021376  pop     rdi
0x180021377  pop     rsi
0x180021378  pop     rbp
0x180021379  retn
0x18002137a  cmp     esi, r15d
0x18002137d  jz      short loc_18002132A
0x18002137f  mov     dword ptr [r14], 2
0x180021386  mov     [rbp+string], r13
0x18002138a  mov     rdi, [rbp+var_10]
0x18002138e  mov     rax, [rdi]
0x180021391  mov     rbx, [rax+78h]
0x180021395  xor     ecx, ecx; string
0x180021397  call    cs:__imp_WindowsDeleteString
0x18002139d  mov     [rbp+string], r13
0x1800213a1  lea     rdx, [rbp+string]
0x1800213a5  mov     rcx, rdi
0x1800213a8  mov     rax, rbx
0x1800213ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213b0  mov     ebx, eax
0x1800213b2  test    eax, eax
0x1800213b4  js      short loc_180021410
0x1800213b6  mov     [rbp+arg_0], r13d
0x1800213ba  xor     edx, edx; length
0x1800213bc  mov     rcx, [rbp+string]; string
0x1800213c0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800213c6  lea     r8, [rbp+arg_0]
0x1800213ca  mov     rdx, rax
0x1800213cd  xor     ecx, ecx
0x1800213cf  call    cs:__imp_GetEffectivePackageStatusForUser
0x1800213d5  test    eax, eax
0x1800213d7  jnz     short loc_1800213F4
0x1800213d9  test    [rbp+arg_0], 40003DFh
0x1800213e0  jnz     short loc_1800213F4
0x1800213e2  mov     [r14], r13d
0x1800213e5  mov     rcx, [rbp+string]; string
0x1800213e9  call    cs:__imp_WindowsDeleteString
0x1800213ef  jmp     loc_18002132A
0x1800213f4  mov     rcx, [rbp+string]; string
0x1800213f8  call    cs:__imp_WindowsDeleteString
0x1800213fe  inc     esi
0x180021400  mov     edx, esi
0x180021402  lea     rcx, [rbp+var_30]
0x180021406  call    ?get_at_current@?$vector_range_nothrow@U?$IVectorView@PEAVAppUriHandlerGroup@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@@wil@@QEAAXI@Z; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerGroup *>>::get_at_current(uint)
0x18002140b  jmp     loc_180021321
0x180021410  mov     rcx, [rbp+38h]; this
0x180021414  mov     r9d, ebx; char *
0x180021417  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18002141e  mov     edx, 277h; void *
0x180021423  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021428  nop
0x180021429  mov     rcx, [rbp+string]; string
0x18002142d  call    cs:__imp_WindowsDeleteString
0x180021433  mov     [rbp+string], r13
0x180021437  lea     rcx, [rbp+var_10]
0x18002143b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180021440  jmp     loc_180021360
0x180021445  test    r12, r12
0x180021448  jz      loc_18002133D
0x18002144e  mov     byte ptr [rbp+arg_0], r13b
0x180021452  lea     rdx, [rbp+arg_0]; bool *
0x180021456  mov     rcx, r12; HSTRING
0x180021459  call    ?IsPackagePresent@@YAJPEAUHSTRING__@@PEA_N@Z; IsPackagePresent(HSTRING__ *,bool *)
0x18002145e  mov     ebx, eax
0x180021460  test    eax, eax
0x180021462  jns     short loc_18002146E
0x180021464  mov     edx, 285h
0x180021469  jmp     loc_18002134D
0x18002146e  cmp     byte ptr [rbp+arg_0], r13b
0x180021472  jnz     loc_18002133D
0x180021478  mov     dword ptr [r14], 1
0x18002147f  jmp     loc_18002133D
0x180021484  xor     eax, eax
0x180021486  jmp     loc_180021362
```
