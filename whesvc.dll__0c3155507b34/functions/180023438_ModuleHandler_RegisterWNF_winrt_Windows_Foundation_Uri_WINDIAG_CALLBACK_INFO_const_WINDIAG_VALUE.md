# ModuleHandler::RegisterWNF(winrt::Windows::Foundation::Uri,_WINDIAG_CALLBACK_INFO const *,_WINDIAG_VALUE *)

- ea: `0x180023438`
- end: `0x18002365a`
- name: `?RegisterWNF@ModuleHandler@@AEAAJUUri@Foundation@Windows@winrt@@PEBU_WINDIAG_CALLBACK_INFO@@PEAU_WINDIAG_VALUE@@@Z`
- size: `546`
- prototype: `__int64(__int64, __int64 *, __int64, ...)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800214d8`

## callees

- `0x180003e10`
- `0x180003e34`
- `0x1800066dc`
- `0x180009044`
- `0x180012194`
- `0x1800142e0`
- `0x18001997c`
- `0x18001bfec`
- `0x18002275c`
- `0x1800233d8`
- `0x180023438`
- `0x180023efc`
- `0x1800255e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180023548`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180023548`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800235a2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800235a9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800235a2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800235a9`

## pseudocode

```c
__int64 ModuleHandler::RegisterWNF(__int64 a1, __int64 *a2, __int64 a3, ...)
{
  unsigned int v5; // r12d
  int v6; // esi
  __int64 v7; // rcx
  bool v8; // r15
  void *v9; // rdi
  int v10; // eax
  HANDLE ProcessHeap; // rax
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  void *v14; // rdi
  int v15; // ecx
  HANDLE v16; // rax
  __int64 v17; // rax
  struct OrchestratorSingleton *Instance; // rax
  int v19; // edi
  __int64 v20; // rdx
  LPVOID v22; // [rsp+20h] [rbp-30h] BYREF
  __int64 *v23; // [rsp+28h] [rbp-28h] BYREF
  int v24; // [rsp+30h] [rbp-20h]
  _BYTE v25[8]; // [rsp+38h] [rbp-18h] BYREF
  int v26; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  __int64 v28; // [rsp+90h] [rbp+40h] BYREF
  LPVOID lpMem; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v30; // [rsp+A8h] [rbp+58h] BYREF
  va_list va; // [rsp+A8h] [rbp+58h]
  va_list va1; // [rsp+B0h] [rbp+60h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v30 = va_arg(va1, _QWORD);
  v28 = a1;
  if ( !a3 || !*(_QWORD *)(a3 + 16) )
  {
    v19 = -2147467261;
    v20 = 780;
    goto LABEL_39;
  }
  v5 = 0;
  winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::QueryParsed(
    a2,
    &v28);
  v23 = &v28;
  v6 = 0;
  v24 = 0;
  winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::IWwwFormUrlDecoderRuntimeClass,winrt::Windows::Foundation::IWwwFormUrlDecoderEntry>::end(
    &v28,
    v25);
  while ( v6 != v26 )
  {
    winrt::impl::fast_iterator<winrt::Windows::Foundation::IWwwFormUrlDecoderRuntimeClass>::operator*(
      &v23,
      (__int64 *)va);
    v7 = *(_QWORD *)winrt::impl::consume_Windows_Foundation_IWwwFormUrlDecoderEntry<winrt::Windows::Foundation::IWwwFormUrlDecoderEntry>::Name(
                      (__int64 *)va,
                      &lpMem);
    v8 = v7 && *(_DWORD *)(v7 + 4) == 8 && wmemcmp(*(const wchar_t **)(v7 + 16), L"scenario", 8u) == 0;
    v9 = lpMem;
    if ( lpMem )
    {
      v10 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v10 )
      {
        if ( v10 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v9);
      }
      lpMem = 0;
    }
    if ( v8 )
    {
      v12 = winrt::impl::consume_Windows_Foundation_IWwwFormUrlDecoderEntry<winrt::Windows::Foundation::IWwwFormUrlDecoderEntry>::Value(
              (__int64 *)va,
              &v22);
      v13 = *(_QWORD *)v12 ? *(const wchar_t **)(*(_QWORD *)v12 + 16LL) : &WideCharStr;
      v5 = _o__wtoi(v13);
      v14 = v22;
      if ( v22 )
      {
        v15 = _InterlockedDecrement((volatile signed __int32 *)v22 + 6);
        if ( v15 )
        {
          if ( v15 < 0 )
            abort();
        }
        else
        {
          v16 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v16, 0, v14);
        }
        v22 = 0;
      }
    }
    if ( v30 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref((__int64 *)va);
    v24 = ++v6;
  }
  if ( v28 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v28);
  if ( !v5 || (v17 = *(_QWORD *)(a3 + 16), *(_DWORD *)v17 != 2) )
  {
    v19 = -2147024809;
    v20 = 794;
    goto LABEL_39;
  }
  v30 = *(_QWORD *)(v17 + 8);
  Instance = OrchestratorSingleton::GetInstance();
  v19 = OrchestratorSingleton::AddDynamicWnf(Instance, v5, v30);
  if ( v19 < 0 )
  {
    v20 = 798;
LABEL_39:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
      (const char *)(unsigned int)v19,
      (int)v22);
    if ( *a2 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(a2);
    return (unsigned int)v19;
  }
  if ( *a2 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(a2);
  return 0;
}

```

## disassembly

```asm
0x180023438  mov     [rsp-38h+arg_18], r9
0x18002343d  mov     [rsp-38h+arg_0], rcx
0x180023442  push    rbp
0x180023443  push    rbx
0x180023444  push    rsi
0x180023445  push    rdi
0x180023446  push    r12
0x180023448  push    r14
0x18002344a  push    r15
0x18002344c  mov     rbp, rsp
0x18002344f  sub     rsp, 50h
0x180023453  mov     r14, r8
0x180023456  mov     rbx, rdx
0x180023459  test    r8, r8
0x18002345c  jz      loc_18002361E
0x180023462  cmp     qword ptr [r8+10h], 0
0x180023467  jz      loc_18002361E
0x18002346d  xor     r12d, r12d
0x180023470  lea     rdx, [rbp+arg_0]
0x180023474  mov     rcx, rbx
0x180023477  call    ?QueryParsed@?$consume_Windows_Foundation_IUriRuntimeClass@UIUriRuntimeClass@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::QueryParsed(void)
0x18002347c  lea     rax, [rbp+arg_0]
0x180023480  mov     [rbp+var_28], rax
0x180023484  xor     esi, esi
0x180023486  mov     [rbp+var_20], esi
0x180023489  lea     rdx, [rbp+var_18]
0x18002348d  lea     rcx, [rbp+arg_0]
0x180023491  call    ?end@?$consume_Windows_Foundation_Collections_IIterable@UIWwwFormUrlDecoderRuntimeClass@Foundation@Windows@winrt@@UIWwwFormUrlDecoderEntry@234@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::IWwwFormUrlDecoderRuntimeClass,winrt::Windows::Foundation::IWwwFormUrlDecoderEntry>::end(void)
0x180023496  cmp     esi, [rbp+var_10]
0x180023499  jz      loc_1800235B0
0x18002349f  lea     rdx, [rbp+arg_18]
0x1800234a3  lea     rcx, [rbp+var_28]
0x1800234a7  call    ??D?$fast_iterator@UIWwwFormUrlDecoderRuntimeClass@Foundation@Windows@winrt@@@impl@winrt@@QEBA?AUIWwwFormUrlDecoderEntry@Foundation@Windows@2@XZ; winrt::impl::fast_iterator<winrt::Windows::Foundation::IWwwFormUrlDecoderRuntimeClass>::operator*(void)
0x1800234ac  lea     rdx, [rbp+lpMem]
0x1800234b0  lea     rcx, [rbp+arg_18]
0x1800234b4  call    ?Name@?$consume_Windows_Foundation_IWwwFormUrlDecoderEntry@UIWwwFormUrlDecoderEntry@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IWwwFormUrlDecoderEntry<winrt::Windows::Foundation::IWwwFormUrlDecoderEntry>::Name(void)
0x1800234b9  mov     rcx, [rax]
0x1800234bc  test    rcx, rcx
0x1800234bf  jz      short loc_1800234E3
0x1800234c1  mov     r8d, [rcx+4]; N
0x1800234c5  cmp     r8, 8
0x1800234c9  jnz     short loc_1800234E3
0x1800234cb  lea     rdx, aScenario; "scenario"
0x1800234d2  mov     rcx, [rcx+10h]; S1
0x1800234d6  call    wmemcmp
0x1800234db  test    eax, eax
0x1800234dd  setz    r15b
0x1800234e1  jmp     short loc_1800234E6
0x1800234e3  xor     r15b, r15b
0x1800234e6  mov     rdi, [rbp+lpMem]
0x1800234ea  test    rdi, rdi
0x1800234ed  jz      short loc_180023521
0x1800234ef  or      eax, 0FFFFFFFFh
0x1800234f2  lock xadd [rdi+18h], eax
0x1800234f7  sub     eax, 1
0x1800234fa  jnz     short loc_180023511
0x1800234fc  nop
0x1800234fd  call    WINRT_IMPL_GetProcessHeap
0x180023502  mov     rcx, rax; hHeap
0x180023505  mov     r8, rdi; lpMem
0x180023508  xor     edx, edx; dwFlags
0x18002350a  call    WINRT_IMPL_HeapFree
0x18002350f  jmp     short loc_180023519
0x180023511  test    eax, eax
0x180023513  js      loc_1800235A2
0x180023519  mov     [rbp+lpMem], 0
0x180023521  test    r15b, r15b
0x180023524  jz      short loc_180023588
0x180023526  lea     rdx, [rbp+var_30]
0x18002352a  lea     rcx, [rbp+arg_18]
0x18002352e  call    ?Value@?$consume_Windows_Foundation_IWwwFormUrlDecoderEntry@UIWwwFormUrlDecoderEntry@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IWwwFormUrlDecoderEntry<winrt::Windows::Foundation::IWwwFormUrlDecoderEntry>::Value(void)
0x180023533  mov     rcx, [rax]
0x180023536  test    rcx, rcx
0x180023539  jz      short loc_180023541
0x18002353b  mov     rcx, [rcx+10h]
0x18002353f  jmp     short loc_180023548
0x180023541  lea     rcx, WideCharStr
0x180023548  call    cs:__imp__o__wtoi
0x18002354e  mov     r12d, eax
0x180023551  mov     rdi, [rbp+var_30]
0x180023555  test    rdi, rdi
0x180023558  jz      short loc_180023588
0x18002355a  or      ecx, 0FFFFFFFFh
0x18002355d  lock xadd [rdi+18h], ecx
0x180023562  sub     ecx, 1
0x180023565  jnz     short loc_18002357C
0x180023567  nop
0x180023568  call    WINRT_IMPL_GetProcessHeap
0x18002356d  mov     rcx, rax; hHeap
0x180023570  mov     r8, rdi; lpMem
0x180023573  xor     edx, edx; dwFlags
0x180023575  call    WINRT_IMPL_HeapFree
0x18002357a  jmp     short loc_180023580
0x18002357c  test    ecx, ecx
0x18002357e  js      short loc_1800235A9
0x180023580  mov     [rbp+var_30], 0
0x180023588  cmp     [rbp+arg_18], 0
0x18002358d  jz      short loc_180023598
0x18002358f  lea     rcx, [rbp+arg_18]
0x180023593  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180023598  inc     esi
0x18002359a  mov     [rbp+var_20], esi
0x18002359d  jmp     loc_180023496
0x1800235a2  call    cs:__imp_abort
0x1800235a9  call    cs:__imp_abort
0x1800235b0  cmp     [rbp+arg_0], 0
0x1800235b5  jz      short loc_1800235C0
0x1800235b7  lea     rcx, [rbp+arg_0]
0x1800235bb  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800235c0  test    r12d, r12d
0x1800235c3  jz      short loc_180023612
0x1800235c5  mov     rax, [r14+10h]
0x1800235c9  cmp     dword ptr [rax], 2
0x1800235cc  jnz     short loc_180023612
0x1800235ce  mov     rax, [rax+8]
0x1800235d2  mov     rcx, rax
0x1800235d5  shr     rcx, 20h
0x1800235d9  mov     dword ptr [rbp+arg_18], eax
0x1800235dc  mov     dword ptr [rbp+arg_18+4], ecx
0x1800235df  call    ?GetInstance@OrchestratorSingleton@@SAAEAV1@XZ; OrchestratorSingleton::GetInstance(void)
0x1800235e4  mov     r8, [rbp+arg_18]
0x1800235e8  mov     edx, r12d
0x1800235eb  mov     rcx, rax
0x1800235ee  call    ?AddDynamicWnf@OrchestratorSingleton@@QEAAJW4_WHESVC_SCENARIOS@@U_WNF_STATE_NAME@@@Z; OrchestratorSingleton::AddDynamicWnf(_WHESVC_SCENARIOS,_WNF_STATE_NAME)
0x1800235f3  mov     edi, eax
0x1800235f5  test    eax, eax
0x1800235f7  jns     short loc_180023600
0x1800235f9  mov     edx, 31Eh
0x1800235fe  jmp     short loc_180023628
0x180023600  cmp     qword ptr [rbx], 0
0x180023604  jz      short loc_18002360E
0x180023606  mov     rcx, rbx
0x180023609  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18002360e  xor     eax, eax
0x180023610  jmp     short loc_18002364B
0x180023612  mov     edi, 80070057h
0x180023617  mov     edx, 31Ah
0x18002361c  jmp     short loc_180023628
0x18002361e  mov     edi, 80004003h
0x180023623  mov     edx, 30Ch; void *
0x180023628  mov     r9d, edi; char *
0x18002362b  lea     r8, aPcshellBaseWhe_2; "pcshell\\base\\whesvc\\lib\\modulehandl"...
0x180023632  mov     rcx, [rbp+38h]; this
0x180023636  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002363b  cmp     qword ptr [rbx], 0
0x18002363f  jz      short loc_180023649
0x180023641  mov     rcx, rbx
0x180023644  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180023649  mov     eax, edi
0x18002364b  add     rsp, 50h
0x18002364f  pop     r15
0x180023651  pop     r14
0x180023653  pop     r12
0x180023655  pop     rdi
0x180023656  pop     rsi
0x180023657  pop     rbx
0x180023658  pop     rbp
0x180023659  retn
```
