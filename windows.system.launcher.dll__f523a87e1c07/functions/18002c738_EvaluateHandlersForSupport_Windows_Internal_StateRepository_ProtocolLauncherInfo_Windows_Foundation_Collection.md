# EvaluateHandlersForSupport<Windows::Internal::StateRepository::ProtocolLauncherInfo>(Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::ProtocolLauncherInfo *> *,HSTRING__ *,Windows::System::LaunchQuerySupportStatus *)

- ea: `0x18002c738`
- end: `0x18002c926`
- name: `??$EvaluateHandlersForSupport@VProtocolLauncherInfo@StateRepository@Internal@Windows@@@@YAJPEAU?$IVectorView@PEAVProtocolLauncherInfo@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@PEAUHSTRING__@@PEAW4LaunchQuerySupportStatus@System@3@@Z`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a700`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x180021a88`
- `0x18002c738`
- `0x18002c92c`
- `0x180111010`

## import_xrefs

- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x18002c8a1`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x18002c8a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c892`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c892`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c869`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c8af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c8e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c90c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c869`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c8af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c8e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c90c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EvaluateHandlersForSupport<Windows::Internal::StateRepository::ProtocolLauncherInfo>(
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
    if ( v8 == v9 || *(int *)v19 < 0 )
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
    if ( (v10 & 0x80000000) == 0 )
    {
      if ( !(_BYTE)v23 )
        *a3 = 1;
      goto LABEL_11;
    }
    v11 = 645;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)v10,
      v17);
    return v10;
  }
LABEL_11:
  v10 = (unsigned int)v24;
  if ( (int)v24 < 0 )
  {
    v11 = 652;
    goto LABEL_13;
  }
  return 0;
}

```

## disassembly

```asm
0x18002c738  mov     [rsp-38h+arg_8], rbx
0x18002c73d  push    rbp
0x18002c73e  push    rsi
0x18002c73f  push    rdi
0x18002c740  push    r12
0x18002c742  push    r13
0x18002c744  push    r14
0x18002c746  push    r15
0x18002c748  mov     rbp, rsp
0x18002c74b  sub     rsp, 50h
0x18002c74f  mov     r14, r8
0x18002c752  mov     r12, rdx
0x18002c755  xor     r13d, r13d
0x18002c758  mov     dword ptr [r8], 3
0x18002c75f  mov     dword ptr [rbp+arg_10], r13d
0x18002c763  mov     [rbp+var_30], rcx
0x18002c767  lea     rax, [rbp+arg_10]
0x18002c76b  mov     [rbp+var_20], rax
0x18002c76f  mov     [rbp+var_18], r13d
0x18002c773  mov     [rbp+var_10], r13
0x18002c777  mov     rax, [rcx]
0x18002c77a  lea     rdx, [rbp+var_28]
0x18002c77e  mov     rax, [rax+38h]
0x18002c782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c787  mov     rcx, [rbp+var_20]
0x18002c78b  mov     [rcx], eax
0x18002c78d  test    eax, eax
0x18002c78f  js      short loc_18002C7C2
0x18002c791  cmp     [rbp+var_28], r13d
0x18002c795  jbe     short loc_18002C7C2
0x18002c797  mov     rdi, [rbp+var_30]
0x18002c79b  mov     rax, [rdi]
0x18002c79e  mov     rbx, [rax+30h]
0x18002c7a2  lea     rcx, [rbp+var_10]
0x18002c7a6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c7ab  lea     r8, [rbp+var_10]
0x18002c7af  xor     edx, edx
0x18002c7b1  mov     rcx, rdi
0x18002c7b4  mov     rax, rbx
0x18002c7b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7bc  mov     rcx, [rbp+var_20]
0x18002c7c0  mov     [rcx], eax
0x18002c7c2  mov     esi, r13d
0x18002c7c5  mov     r15d, [rbp+var_28]
0x18002c7c9  mov     rax, [rbp+var_20]
0x18002c7cd  cmp     esi, r15d
0x18002c7d0  jnz     loc_18002C917
0x18002c7d6  lea     rcx, [rbp+var_10]
0x18002c7da  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c7df  cmp     dword ptr [r14], 3
0x18002c7e3  jnz     short loc_18002C80D
0x18002c7e5  test    r12, r12
0x18002c7e8  jz      short loc_18002C80D
0x18002c7ea  mov     byte ptr [rbp+arg_0], r13b
0x18002c7ee  lea     rdx, [rbp+arg_0]; bool *
0x18002c7f2  mov     rcx, r12; HSTRING
0x18002c7f5  call    ?IsPackagePresent@@YAJPEAUHSTRING__@@PEA_N@Z; IsPackagePresent(HSTRING__ *,bool *)
0x18002c7fa  mov     ebx, eax
0x18002c7fc  test    eax, eax
0x18002c7fe  js      short loc_18002C846
0x18002c800  cmp     byte ptr [rbp+arg_0], r13b
0x18002c804  jnz     short loc_18002C80D
0x18002c806  mov     dword ptr [r14], 1
0x18002c80d  mov     ebx, dword ptr [rbp+arg_10]
0x18002c810  test    ebx, ebx
0x18002c812  jns     short loc_18002C84D
0x18002c814  mov     edx, 28Ch; void *
0x18002c819  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18002c820  mov     r9d, ebx; char *
0x18002c823  mov     rcx, [rbp+38h]; this
0x18002c827  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c82c  mov     eax, ebx
0x18002c82e  mov     rbx, [rsp+50h+arg_8]
0x18002c836  add     rsp, 50h
0x18002c83a  pop     r15
0x18002c83c  pop     r14
0x18002c83e  pop     r13
0x18002c840  pop     r12
0x18002c842  pop     rdi
0x18002c843  pop     rsi
0x18002c844  pop     rbp
0x18002c845  retn
0x18002c846  mov     edx, 285h
0x18002c84b  jmp     short loc_18002C819
0x18002c84d  xor     eax, eax
0x18002c84f  jmp     short loc_18002C82E
0x18002c851  mov     dword ptr [r14], 2
0x18002c858  mov     [rbp+string], r13
0x18002c85c  mov     rdi, [rbp+var_10]
0x18002c860  mov     rax, [rdi]
0x18002c863  mov     rbx, [rax+78h]
0x18002c867  xor     ecx, ecx; string
0x18002c869  call    cs:__imp_WindowsDeleteString
0x18002c86f  mov     [rbp+string], r13
0x18002c873  lea     rdx, [rbp+string]
0x18002c877  mov     rcx, rdi
0x18002c87a  mov     rax, rbx
0x18002c87d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c882  mov     ebx, eax
0x18002c884  test    eax, eax
0x18002c886  js      short loc_18002C8C7
0x18002c888  mov     [rbp+arg_0], r13d
0x18002c88c  xor     edx, edx; length
0x18002c88e  mov     rcx, [rbp+string]; string
0x18002c892  call    cs:__imp_WindowsGetStringRawBuffer
0x18002c898  lea     r8, [rbp+arg_0]
0x18002c89c  mov     rdx, rax
0x18002c89f  xor     ecx, ecx
0x18002c8a1  call    cs:__imp_GetEffectivePackageStatusForUser
0x18002c8a7  test    eax, eax
0x18002c8a9  jz      short loc_18002C8FC
0x18002c8ab  mov     rcx, [rbp+string]; string
0x18002c8af  call    cs:__imp_WindowsDeleteString
0x18002c8b5  inc     esi
0x18002c8b7  mov     edx, esi
0x18002c8b9  lea     rcx, [rbp+var_30]
0x18002c8bd  call    ?get_at_current@?$vector_range_nothrow@U?$IVectorView@PEAVAppUriHandlerGroup@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@@wil@@QEAAXI@Z; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerGroup *>>::get_at_current(uint)
0x18002c8c2  jmp     loc_18002C7C9
0x18002c8c7  mov     rcx, [rbp+38h]; this
0x18002c8cb  mov     r9d, ebx; char *
0x18002c8ce  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18002c8d5  mov     edx, 277h; void *
0x18002c8da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c8df  nop
0x18002c8e0  mov     rcx, [rbp+string]; string
0x18002c8e4  call    cs:__imp_WindowsDeleteString
0x18002c8ea  mov     [rbp+string], r13
0x18002c8ee  lea     rcx, [rbp+var_10]
0x18002c8f2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c8f7  jmp     loc_18002C82C
0x18002c8fc  test    [rbp+arg_0], 40003DFh
0x18002c903  jnz     short loc_18002C8AB
0x18002c905  mov     [r14], r13d
0x18002c908  mov     rcx, [rbp+string]; string
0x18002c90c  call    cs:__imp_WindowsDeleteString
0x18002c912  jmp     loc_18002C7D6
0x18002c917  cmp     [rax], r13d
0x18002c91a  jl      loc_18002C7D6
0x18002c920  jmp     loc_18002C851
```
