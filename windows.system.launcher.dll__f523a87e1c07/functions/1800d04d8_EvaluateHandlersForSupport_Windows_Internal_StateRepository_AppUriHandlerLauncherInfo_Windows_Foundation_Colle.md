# EvaluateHandlersForSupport<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo>(Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *> *,HSTRING__ *,Windows::System::LaunchQuerySupportStatus *)

- ea: `0x1800d04d8`
- end: `0x1800d0680`
- name: `??$EvaluateHandlersForSupport@VAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@@YAJPEAU?$IVectorView@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@PEAUHSTRING__@@PEAW4LaunchQuerySupportStatus@System@3@@Z`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180078f20`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x180021a88`
- `0x18002913c`
- `0x18002c92c`
- `0x18003ce00`
- `0x1800d04d8`
- `0x180111010`

## import_xrefs

- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x1800d0598`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x1800d0598`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d0589`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d0589`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d0557`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d05af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d05ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d0635`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d0557`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d05af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d05ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d0635`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EvaluateHandlersForSupport<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo>(
        __int64 a1,
        HSTRING a2,
        _DWORD *a3)
{
  int v5; // r13d
  HSTRING v6; // r15
  unsigned int i; // r14d
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  unsigned int v11; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v13; // rdx
  HSTRING string; // [rsp+20h] [rbp-40h] BYREF
  unsigned int v16; // [rsp+28h] [rbp-38h]
  _BYTE v17[8]; // [rsp+30h] [rbp-30h] BYREF
  int v18; // [rsp+38h] [rbp-28h]
  _BYTE v19[16]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  int v21; // [rsp+B0h] [rbp+50h] BYREF
  int v22; // [rsp+B8h] [rbp+58h] BYREF

  *a3 = 3;
  v22 = 0;
  wil::GetRangeNoThrow<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *>(v17, a1, &v22);
  wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *>>::begin(
    v17,
    &string);
  v5 = v18;
  v6 = string;
  for ( i = v16;
        ;
        wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerGroup *>>::get_at_current(
          v6,
          i) )
  {
    if ( **((int **)v6 + 2) < 0 || i == v5 )
      goto LABEL_9;
    *a3 = 2;
    string = 0;
    v8 = *((_QWORD *)v6 + 4);
    v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v8 + 112LL);
    WindowsDeleteString(0);
    string = 0;
    v10 = v9(v8, &string);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x277,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
        (const char *)(unsigned int)v10,
        (int)string);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v19);
      return v11;
    }
    v21 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( !(unsigned int)GetEffectivePackageStatusForUser(0, StringRawBuffer, &v21) && (v21 & 0x40003DF) == 0 )
      break;
    WindowsDeleteString(string);
    ++i;
  }
  *a3 = 0;
  WindowsDeleteString(string);
LABEL_9:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v19);
  if ( *a3 == 3 && a2 )
  {
    LOBYTE(v21) = 0;
    v11 = IsPackagePresent(a2, (bool *)&v21);
    if ( (v11 & 0x80000000) != 0 )
    {
      v13 = 645;
      goto LABEL_13;
    }
    if ( !(_BYTE)v21 )
      *a3 = 1;
  }
  v11 = v22;
  if ( v22 < 0 )
  {
    v13 = 652;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)v11,
      (int)string);
    return v11;
  }
  return 0;
}

```

## disassembly

```asm
0x1800d04d8  mov     [rsp-38h+arg_0], rbx
0x1800d04dd  push    rbp
0x1800d04de  push    rsi
0x1800d04df  push    rdi
0x1800d04e0  push    r12
0x1800d04e2  push    r13
0x1800d04e4  push    r14
0x1800d04e6  push    r15
0x1800d04e8  mov     rbp, rsp
0x1800d04eb  sub     rsp, 60h
0x1800d04ef  mov     rsi, r8
0x1800d04f2  mov     r12, rdx
0x1800d04f5  mov     dword ptr [r8], 3
0x1800d04fc  xor     edi, edi
0x1800d04fe  mov     [rbp+arg_18], edi
0x1800d0501  lea     r8, [rbp+arg_18]
0x1800d0505  mov     rdx, rcx
0x1800d0508  lea     rcx, [rbp+var_30]
0x1800d050c  call    ??$GetRangeNoThrow@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@wil@@YA?AV?$vector_range_nothrow@U?$IVectorView@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@@0@PEAU?$IVectorView@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@PEAJ@Z; wil::GetRangeNoThrow<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *>(Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *> *,long *)
0x1800d0511  nop
0x1800d0512  lea     rdx, [rbp+string]
0x1800d0516  lea     rcx, [rbp+var_30]
0x1800d051a  call    ?begin@?$vector_range_nothrow@U?$IVectorView@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@@wil@@QEAA?AVvector_iterator_nothrow@12@XZ; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *>>::begin(void)
0x1800d051f  mov     r13d, [rbp+var_28]
0x1800d0523  mov     r15, [rbp+string]
0x1800d0527  mov     r14d, [rbp+var_38]
0x1800d052b  mov     rax, [r15+10h]
0x1800d052f  cmp     [rax], edi
0x1800d0531  jl      loc_1800D05D5
0x1800d0537  cmp     r14d, r13d
0x1800d053a  jz      loc_1800D05D5
0x1800d0540  mov     dword ptr [rsi], 2
0x1800d0546  mov     [rbp+string], rdi
0x1800d054a  mov     rdi, [r15+20h]
0x1800d054e  mov     rax, [rdi]
0x1800d0551  mov     rbx, [rax+70h]
0x1800d0555  xor     ecx, ecx; string
0x1800d0557  call    cs:__imp_WindowsDeleteString
0x1800d055d  mov     [rbp+string], 0
0x1800d0565  lea     rdx, [rbp+string]
0x1800d0569  mov     rcx, rdi
0x1800d056c  mov     rax, rbx
0x1800d056f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0574  mov     ebx, eax
0x1800d0576  xor     edi, edi
0x1800d0578  test    eax, eax
0x1800d057a  js      loc_1800D0618
0x1800d0580  mov     [rbp+arg_10], edi
0x1800d0583  xor     edx, edx; length
0x1800d0585  mov     rcx, [rbp+string]; string
0x1800d0589  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d058f  lea     r8, [rbp+arg_10]
0x1800d0593  mov     rdx, rax
0x1800d0596  xor     ecx, ecx
0x1800d0598  call    cs:__imp_GetEffectivePackageStatusForUser
0x1800d059e  test    eax, eax
0x1800d05a0  jnz     short loc_1800D05AB
0x1800d05a2  test    [rbp+arg_10], 40003DFh
0x1800d05a9  jz      short loc_1800D05C8
0x1800d05ab  mov     rcx, [rbp+string]; string
0x1800d05af  call    cs:__imp_WindowsDeleteString
0x1800d05b5  inc     r14d
0x1800d05b8  mov     edx, r14d
0x1800d05bb  mov     rcx, r15
0x1800d05be  call    ?get_at_current@?$vector_range_nothrow@U?$IVectorView@PEAVAppUriHandlerGroup@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@@wil@@QEAAXI@Z; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerGroup *>>::get_at_current(uint)
0x1800d05c3  jmp     loc_1800D052B
0x1800d05c8  mov     [rsi], edi
0x1800d05ca  mov     rcx, [rbp+string]; string
0x1800d05ce  call    cs:__imp_WindowsDeleteString
0x1800d05d4  nop
0x1800d05d5  lea     rcx, [rbp+var_10]
0x1800d05d9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d05de  cmp     dword ptr [rsi], 3
0x1800d05e1  jnz     short loc_1800D0658
0x1800d05e3  test    r12, r12
0x1800d05e6  jz      short loc_1800D0658
0x1800d05e8  mov     byte ptr [rbp+arg_10], dil
0x1800d05ec  lea     rdx, [rbp+arg_10]; bool *
0x1800d05f0  mov     rcx, r12; HSTRING
0x1800d05f3  call    ?IsPackagePresent@@YAJPEAUHSTRING__@@PEA_N@Z; IsPackagePresent(HSTRING__ *,bool *)
0x1800d05f8  mov     ebx, eax
0x1800d05fa  test    eax, eax
0x1800d05fc  jns     short loc_1800D064C
0x1800d05fe  mov     edx, 285h; void *
0x1800d0603  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x1800d060a  mov     r9d, ebx; char *
0x1800d060d  mov     rcx, [rbp+38h]; this
0x1800d0611  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d0616  jmp     short loc_1800D0648
0x1800d0618  mov     rcx, [rbp+38h]; this
0x1800d061c  mov     r9d, ebx; char *
0x1800d061f  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x1800d0626  mov     edx, 277h; void *
0x1800d062b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d0630  nop
0x1800d0631  mov     rcx, [rbp+string]; string
0x1800d0635  call    cs:__imp_WindowsDeleteString
0x1800d063b  mov     [rbp+string], rdi
0x1800d063f  lea     rcx, [rbp+var_10]
0x1800d0643  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d0648  mov     eax, ebx
0x1800d064a  jmp     short loc_1800D0668
0x1800d064c  cmp     byte ptr [rbp+arg_10], dil
0x1800d0650  jnz     short loc_1800D0658
0x1800d0652  mov     dword ptr [rsi], 1
0x1800d0658  mov     ebx, [rbp+arg_18]
0x1800d065b  test    ebx, ebx
0x1800d065d  jns     short loc_1800D0666
0x1800d065f  mov     edx, 28Ch
0x1800d0664  jmp     short loc_1800D0603
0x1800d0666  xor     eax, eax
0x1800d0668  mov     rbx, [rsp+60h+arg_0]
0x1800d0670  add     rsp, 60h
0x1800d0674  pop     r15
0x1800d0676  pop     r14
0x1800d0678  pop     r13
0x1800d067a  pop     r12
0x1800d067c  pop     rdi
0x1800d067d  pop     rsi
0x1800d067e  pop     rbp
0x1800d067f  retn
```
