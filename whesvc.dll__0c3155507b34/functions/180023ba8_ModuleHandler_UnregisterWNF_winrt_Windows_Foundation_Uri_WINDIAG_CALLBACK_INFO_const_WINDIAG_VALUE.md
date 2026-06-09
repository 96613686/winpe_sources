# ModuleHandler::UnregisterWNF(winrt::Windows::Foundation::Uri,_WINDIAG_CALLBACK_INFO const *,_WINDIAG_VALUE *)

- ea: `0x180023ba8`
- end: `0x180023ef4`
- name: `?UnregisterWNF@ModuleHandler@@AEAAJUUri@Foundation@Windows@winrt@@PEBU_WINDIAG_CALLBACK_INFO@@PEAU_WINDIAG_VALUE@@@Z`
- size: `844`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800214d8`

## callees

- `0x180003304`
- `0x180003e10`
- `0x180003e34`
- `0x1800066dc`
- `0x180009044`
- `0x1800142e0`
- `0x180014ccc`
- `0x18001997c`
- `0x18001bfec`
- `0x18002275c`
- `0x1800233d8`
- `0x180023ba8`
- `0x180023efc`
- `0x1800255e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180023ca7`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180023ca7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180023d01`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180023d08`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180023d01`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180023d08`
- `msvcp_win!_Mtx_unlock` at `0x180023e8f`
- `msvcp_win!_Mtx_unlock` at `0x180023e9a`
- `msvcp_win!_Mtx_unlock` at `0x180023e8f`
- `msvcp_win!_Mtx_unlock` at `0x180023e9a`
- `msvcp_win!_Mtx_lock` at `0x180023d6c`
- `msvcp_win!_Mtx_lock` at `0x180023d6c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180023d7b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180023d96`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180023d7b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180023d96`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 ModuleHandler::UnregisterWNF(void *a1, __int64 *a2, ...)
{
  int v3; // r15d
  int v4; // edi
  __int64 v5; // rcx
  bool v6; // r14
  void *v7; // rbx
  int v8; // eax
  HANDLE ProcessHeap; // rax
  __int64 v10; // rax
  const wchar_t *v11; // rcx
  void *v12; // rbx
  int v13; // ecx
  HANDLE v14; // rax
  struct OrchestratorSingleton *Instance; // rdi
  struct _Mtx_internal_imp_t *v17; // rbx
  __int64 v18; // rdx
  unsigned __int64 i; // rcx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r11
  _QWORD *v23; // rcx
  _QWORD *v24; // r9
  __int64 v25; // rdx
  __int64 v26; // rdx
  int v27; // eax
  int v28; // edi
  LPVOID v29; // [rsp+20h] [rbp-30h] BYREF
  va_list v30; // [rsp+28h] [rbp-28h] BYREF
  int v31; // [rsp+30h] [rbp-20h]
  char v32[8]; // [rsp+38h] [rbp-18h] BYREF
  int v33; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  LPVOID lpMem; // [rsp+80h] [rbp+30h] BYREF
  __int64 v36; // [rsp+90h] [rbp+40h] BYREF
  va_list va; // [rsp+90h] [rbp+40h]
  __int64 v38; // [rsp+98h] [rbp+48h] BYREF
  va_list va1; // [rsp+98h] [rbp+48h]
  va_list va2; // [rsp+A0h] [rbp+50h] BYREF

  va_start(va2, a2);
  va_start(va1, a2);
  va_start(va, a2);
  v36 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v38 = va_arg(va2, _QWORD);
  lpMem = a1;
  v3 = 0;
  winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::QueryParsed(
    a2,
    (__int64 *)va);
  va_copy(v30, va);
  v4 = 0;
  v31 = 0;
  winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::IWwwFormUrlDecoderRuntimeClass,winrt::Windows::Foundation::IWwwFormUrlDecoderEntry>::end(
    (__int64 *)va,
    v32);
  while ( v4 != v33 )
  {
    winrt::impl::fast_iterator<winrt::Windows::Foundation::IWwwFormUrlDecoderRuntimeClass>::operator*(
      &v30,
      (__int64 *)va1);
    v5 = *(_QWORD *)winrt::impl::consume_Windows_Foundation_IWwwFormUrlDecoderEntry<winrt::Windows::Foundation::IWwwFormUrlDecoderEntry>::Name(
                      (__int64 *)va1,
                      &lpMem);
    v6 = v5 && *(_DWORD *)(v5 + 4) == 8 && wmemcmp(*(const wchar_t **)(v5 + 16), L"scenario", 8u) == 0;
    v7 = lpMem;
    if ( lpMem )
    {
      v8 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v8 )
      {
        if ( v8 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v7);
      }
      lpMem = 0;
    }
    if ( v6 )
    {
      v10 = winrt::impl::consume_Windows_Foundation_IWwwFormUrlDecoderEntry<winrt::Windows::Foundation::IWwwFormUrlDecoderEntry>::Value(
              (__int64 *)va1,
              &v29);
      v11 = *(_QWORD *)v10 ? *(const wchar_t **)(*(_QWORD *)v10 + 16LL) : &WideCharStr;
      v3 = _o__wtoi(v11);
      v12 = v29;
      if ( v29 )
      {
        v13 = _InterlockedDecrement((volatile signed __int32 *)v29 + 6);
        if ( v13 )
        {
          if ( v13 < 0 )
            abort();
        }
        else
        {
          v14 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v14, 0, v12);
        }
        v29 = 0;
      }
    }
    if ( v38 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref((__int64 *)va1);
    v31 = ++v4;
  }
  if ( v36 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref((__int64 *)va);
  if ( v3 )
  {
    Instance = OrchestratorSingleton::GetInstance();
    LODWORD(v38) = v3;
    v17 = (struct OrchestratorSingleton *)((char *)Instance + 432);
    if ( _Mtx_lock((struct OrchestratorSingleton *)((char *)Instance + 432)) )
    {
      std::_Throw_Cpp_error(5);
      __debugbreak();
    }
    if ( *((_DWORD *)Instance + 127) == 0x7FFFFFFF )
    {
      *((_DWORD *)Instance + 127) = 2147483646;
      std::_Throw_Cpp_error(6);
      __debugbreak();
    }
    v18 = 0xCBF29CE484222325uLL;
    for ( i = 0; i < 4; ++i )
      v18 = 0x100000001B3LL * (*((unsigned __int8 *)va1 + i) ^ (unsigned __int64)v18);
    v20 = *((_QWORD *)Instance + 70) & v18;
    v21 = *((_QWORD *)Instance + 67);
    v22 = 2 * v20;
    v23 = *(_QWORD **)(v21 + 16 * v20 + 8);
    v24 = (_QWORD *)*((_QWORD *)Instance + 65);
    if ( v23 == v24 )
    {
LABEL_42:
      v23 = 0;
    }
    else
    {
      while ( v3 != *((_DWORD *)v23 + 4) )
      {
        if ( v23 == *(_QWORD **)(v21 + 16 * v20) )
          goto LABEL_42;
        v23 = (_QWORD *)v23[1];
      }
    }
    if ( v23 )
    {
      v25 = 16 * v20;
      if ( *(_QWORD **)(v21 + 8 * v22 + 8) == v23 )
      {
        if ( *(_QWORD **)(v25 + v21) == v23 )
          *(_QWORD *)(v25 + v21) = v24;
        else
          v24 = (_QWORD *)v23[1];
        *(_QWORD *)(v21 + 8 * v22 + 8) = v24;
      }
      else if ( *(_QWORD **)(v25 + v21) == v23 )
      {
        *(_QWORD *)(v25 + v21) = *v23;
      }
      v26 = *v23;
      --*((_QWORD *)Instance + 66);
      *(_QWORD *)v23[1] = v26;
      *(_QWORD *)(v26 + 8) = v23[1];
      operator delete(v23);
    }
    v27 = OrchestratorSingleton::PublishWhesvcWNF(Instance);
    v28 = v27;
    if ( v27 >= 0 )
    {
      _Mtx_unlock(v17);
      v28 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x238,
        (int)"pcshell\\base\\whesvc\\lib\\orchestrator.cpp",
        (const char *)(unsigned int)v27);
      _Mtx_unlock(v17);
    }
    if ( v28 >= 0 )
    {
      if ( *a2 )
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(a2);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x333,
        (int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
        (const char *)(unsigned int)v28);
      if ( *a2 )
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(a2);
      return (unsigned int)v28;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x330,
      (int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
      (const char *)0x80070057LL);
    if ( *a2 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(a2);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180023ba8  mov     rax, rsp
0x180023bab  mov     [rax+10h], rbx
0x180023baf  mov     [rax+20h], r9
0x180023bb3  mov     [rax+18h], r8
0x180023bb7  mov     [rax+8], rcx
0x180023bbb  push    rbp
0x180023bbc  push    rsi
0x180023bbd  push    rdi
0x180023bbe  push    r14
0x180023bc0  push    r15
0x180023bc2  mov     rbp, rsp
0x180023bc5  sub     rsp, 50h
0x180023bc9  mov     rsi, rdx
0x180023bcc  xor     r15d, r15d
0x180023bcf  lea     rdx, [rbp+arg_10]
0x180023bd3  mov     rcx, rsi
0x180023bd6  call    ?QueryParsed@?$consume_Windows_Foundation_IUriRuntimeClass@UIUriRuntimeClass@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::QueryParsed(void)
0x180023bdb  lea     rax, [rbp+arg_10]
0x180023bdf  mov     [rbp+var_28], rax
0x180023be3  xor     edi, edi
0x180023be5  mov     [rbp+var_20], edi
0x180023be8  lea     rdx, [rbp+var_18]
0x180023bec  lea     rcx, [rbp+arg_10]
0x180023bf0  call    ?end@?$consume_Windows_Foundation_Collections_IIterable@UIWwwFormUrlDecoderRuntimeClass@Foundation@Windows@winrt@@UIWwwFormUrlDecoderEntry@234@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::IWwwFormUrlDecoderRuntimeClass,winrt::Windows::Foundation::IWwwFormUrlDecoderEntry>::end(void)
0x180023bf5  cmp     edi, [rbp+var_10]
0x180023bf8  jz      loc_180023D0F
0x180023bfe  lea     rdx, [rbp+arg_18]
0x180023c02  lea     rcx, [rbp+var_28]
0x180023c06  call    ??D?$fast_iterator@UIWwwFormUrlDecoderRuntimeClass@Foundation@Windows@winrt@@@impl@winrt@@QEBA?AUIWwwFormUrlDecoderEntry@Foundation@Windows@2@XZ; winrt::impl::fast_iterator<winrt::Windows::Foundation::IWwwFormUrlDecoderRuntimeClass>::operator*(void)
0x180023c0b  lea     rdx, [rbp+lpMem]
0x180023c0f  lea     rcx, [rbp+arg_18]
0x180023c13  call    ?Name@?$consume_Windows_Foundation_IWwwFormUrlDecoderEntry@UIWwwFormUrlDecoderEntry@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IWwwFormUrlDecoderEntry<winrt::Windows::Foundation::IWwwFormUrlDecoderEntry>::Name(void)
0x180023c18  mov     rcx, [rax]
0x180023c1b  test    rcx, rcx
0x180023c1e  jz      short loc_180023C42
0x180023c20  mov     r8d, [rcx+4]; N
0x180023c24  cmp     r8, 8
0x180023c28  jnz     short loc_180023C42
0x180023c2a  lea     rdx, aScenario; "scenario"
0x180023c31  mov     rcx, [rcx+10h]; S1
0x180023c35  call    wmemcmp
0x180023c3a  test    eax, eax
0x180023c3c  setz    r14b
0x180023c40  jmp     short loc_180023C45
0x180023c42  xor     r14b, r14b
0x180023c45  mov     rbx, [rbp+lpMem]
0x180023c49  test    rbx, rbx
0x180023c4c  jz      short loc_180023C80
0x180023c4e  or      eax, 0FFFFFFFFh
0x180023c51  lock xadd [rbx+18h], eax
0x180023c56  sub     eax, 1
0x180023c59  jnz     short loc_180023C70
0x180023c5b  nop
0x180023c5c  call    WINRT_IMPL_GetProcessHeap
0x180023c61  mov     rcx, rax; hHeap
0x180023c64  mov     r8, rbx; lpMem
0x180023c67  xor     edx, edx; dwFlags
0x180023c69  call    WINRT_IMPL_HeapFree
0x180023c6e  jmp     short loc_180023C78
0x180023c70  test    eax, eax
0x180023c72  js      loc_180023D01
0x180023c78  mov     [rbp+lpMem], 0
0x180023c80  test    r14b, r14b
0x180023c83  jz      short loc_180023CE7
0x180023c85  lea     rdx, [rbp+var_30]
0x180023c89  lea     rcx, [rbp+arg_18]
0x180023c8d  call    ?Value@?$consume_Windows_Foundation_IWwwFormUrlDecoderEntry@UIWwwFormUrlDecoderEntry@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IWwwFormUrlDecoderEntry<winrt::Windows::Foundation::IWwwFormUrlDecoderEntry>::Value(void)
0x180023c92  mov     rcx, [rax]
0x180023c95  test    rcx, rcx
0x180023c98  jz      short loc_180023CA0
0x180023c9a  mov     rcx, [rcx+10h]
0x180023c9e  jmp     short loc_180023CA7
0x180023ca0  lea     rcx, WideCharStr
0x180023ca7  call    cs:__imp__o__wtoi
0x180023cad  mov     r15d, eax
0x180023cb0  mov     rbx, [rbp+var_30]
0x180023cb4  test    rbx, rbx
0x180023cb7  jz      short loc_180023CE7
0x180023cb9  or      ecx, 0FFFFFFFFh
0x180023cbc  lock xadd [rbx+18h], ecx
0x180023cc1  sub     ecx, 1
0x180023cc4  jnz     short loc_180023CDB
0x180023cc6  nop
0x180023cc7  call    WINRT_IMPL_GetProcessHeap
0x180023ccc  mov     rcx, rax; hHeap
0x180023ccf  mov     r8, rbx; lpMem
0x180023cd2  xor     edx, edx; dwFlags
0x180023cd4  call    WINRT_IMPL_HeapFree
0x180023cd9  jmp     short loc_180023CDF
0x180023cdb  test    ecx, ecx
0x180023cdd  js      short loc_180023D08
0x180023cdf  mov     [rbp+var_30], 0
0x180023ce7  cmp     [rbp+arg_18], 0
0x180023cec  jz      short loc_180023CF7
0x180023cee  lea     rcx, [rbp+arg_18]
0x180023cf2  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180023cf7  inc     edi
0x180023cf9  mov     [rbp+var_20], edi
0x180023cfc  jmp     loc_180023BF5
0x180023d01  call    cs:__imp_abort
0x180023d08  call    cs:__imp_abort
0x180023d0f  cmp     [rbp+arg_10], 0
0x180023d14  jz      short loc_180023D1F
0x180023d16  lea     rcx, [rbp+arg_10]
0x180023d1a  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180023d1f  test    r15d, r15d
0x180023d22  jnz     short loc_180023D56
0x180023d24  mov     rcx, [rbp+28h]; this
0x180023d28  mov     ebx, 80070057h
0x180023d2d  mov     r9d, ebx; char *
0x180023d30  lea     r8, aPcshellBaseWhe_2; "pcshell\\base\\whesvc\\lib\\modulehandl"...
0x180023d37  mov     edx, 330h; void *
0x180023d3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023d41  cmp     qword ptr [rsi], 0
0x180023d45  jz      short loc_180023D4F
0x180023d47  mov     rcx, rsi
0x180023d4a  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180023d4f  mov     eax, ebx
0x180023d51  jmp     loc_180023EE0
0x180023d56  call    ?GetInstance@OrchestratorSingleton@@SAAEAV1@XZ; OrchestratorSingleton::GetInstance(void)
0x180023d5b  mov     rdi, rax
0x180023d5e  mov     dword ptr [rbp+arg_18], r15d
0x180023d62  lea     rbx, [rax+1B0h]
0x180023d69  mov     rcx, rbx; _Mtx_t
0x180023d6c  call    cs:__imp__Mtx_lock
0x180023d72  test    eax, eax
0x180023d74  jz      short loc_180023D82
0x180023d76  mov     ecx, 5
0x180023d7b  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180023d81  int     3; Trap to Debugger
0x180023d82  mov     eax, [rbx+4Ch]
0x180023d85  cmp     eax, 7FFFFFFFh
0x180023d8a  jnz     short loc_180023D9D
0x180023d8c  dec     eax
0x180023d8e  mov     [rbx+4Ch], eax
0x180023d91  mov     ecx, 6
0x180023d96  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180023d9c  int     3; Trap to Debugger
0x180023d9d  mov     rdx, 0CBF29CE484222325h
0x180023da7  xor     ecx, ecx
0x180023da9  movzx   eax, byte ptr [rbp+rcx+arg_18]
0x180023dae  xor     rdx, rax
0x180023db1  mov     r8, 100000001B3h
0x180023dbb  imul    rdx, r8
0x180023dbf  inc     rcx
0x180023dc2  cmp     rcx, 4
0x180023dc6  jb      short loc_180023DA9
0x180023dc8  and     rdx, [rdi+230h]
0x180023dcf  mov     r8, [rdi+218h]
0x180023dd6  mov     r11, rdx
0x180023dd9  add     r11, r11
0x180023ddc  mov     rcx, [r8+r11*8+8]
0x180023de1  mov     r9, [rdi+208h]
0x180023de8  cmp     rcx, r9
0x180023deb  jz      short loc_180023E08
0x180023ded  mov     rax, rdx
0x180023df0  add     rax, rax
0x180023df3  mov     r10, [r8+rax*8]
0x180023df7  cmp     r15d, [rcx+10h]
0x180023dfb  jz      short loc_180023E0A
0x180023dfd  cmp     rcx, r10
0x180023e00  jz      short loc_180023E08
0x180023e02  mov     rcx, [rcx+8]
0x180023e06  jmp     short loc_180023DF7
0x180023e08  xor     ecx, ecx; void *
0x180023e0a  mov     eax, 10h
0x180023e0f  test    rcx, rcx
0x180023e12  jz      short loc_180023E66
0x180023e14  imul    rdx, rax
0x180023e18  cmp     [r8+r11*8+8], rcx
0x180023e1d  jnz     short loc_180023E36
0x180023e1f  cmp     [rdx+r8], rcx
0x180023e23  jnz     short loc_180023E2B
0x180023e25  mov     [rdx+r8], r9
0x180023e29  jmp     short loc_180023E2F
0x180023e2b  mov     r9, [rcx+8]
0x180023e2f  mov     [r8+r11*8+8], r9
0x180023e34  jmp     short loc_180023E43
0x180023e36  cmp     [rdx+r8], rcx
0x180023e3a  jnz     short loc_180023E43
0x180023e3c  mov     rax, [rcx]
0x180023e3f  mov     [rdx+r8], rax
0x180023e43  mov     rdx, [rcx]
0x180023e46  dec     qword ptr [rdi+210h]
0x180023e4d  mov     rax, [rcx+8]
0x180023e51  mov     [rax], rdx
0x180023e54  mov     rax, [rcx+8]
0x180023e58  mov     [rdx+8], rax
0x180023e5c  mov     edx, 20h ; ' '; unsigned __int64
0x180023e61  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180023e66  mov     rcx, rdi; this
0x180023e69  call    ?PublishWhesvcWNF@OrchestratorSingleton@@AEAAJXZ; OrchestratorSingleton::PublishWhesvcWNF(void)
0x180023e6e  mov     edi, eax
0x180023e70  test    eax, eax
0x180023e72  jns     short loc_180023E97
0x180023e74  mov     rcx, [rbp+28h]; this
0x180023e78  mov     r9d, eax; char *
0x180023e7b  lea     r8, aPcshellBaseWhe_0; "pcshell\\base\\whesvc\\lib\\orchestrato"...
0x180023e82  mov     edx, 238h; void *
0x180023e87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023e8c  mov     rcx, rbx; _Mtx_t
0x180023e8f  call    cs:__imp__Mtx_unlock
0x180023e95  jmp     short loc_180023EA2
0x180023e97  mov     rcx, rbx; _Mtx_t
0x180023e9a  call    cs:__imp__Mtx_unlock
0x180023ea0  xor     edi, edi
0x180023ea2  test    edi, edi
0x180023ea4  jns     short loc_180023ED0
0x180023ea6  mov     rcx, [rbp+28h]; this
0x180023eaa  mov     r9d, edi; char *
0x180023ead  lea     r8, aPcshellBaseWhe_2; "pcshell\\base\\whesvc\\lib\\modulehandl"...
0x180023eb4  mov     edx, 333h; void *
0x180023eb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023ebe  cmp     qword ptr [rsi], 0
0x180023ec2  jz      short loc_180023ECC
0x180023ec4  mov     rcx, rsi
0x180023ec7  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180023ecc  mov     eax, edi
0x180023ece  jmp     short loc_180023EE0
0x180023ed0  cmp     qword ptr [rsi], 0
0x180023ed4  jz      short loc_180023EDE
0x180023ed6  mov     rcx, rsi
0x180023ed9  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180023ede  xor     eax, eax
0x180023ee0  mov     rbx, [rsp+50h+arg_8]
0x180023ee8  add     rsp, 50h
0x180023eec  pop     r15
0x180023eee  pop     r14
0x180023ef0  pop     rdi
0x180023ef1  pop     rsi
0x180023ef2  pop     rbp
0x180023ef3  retn
```
