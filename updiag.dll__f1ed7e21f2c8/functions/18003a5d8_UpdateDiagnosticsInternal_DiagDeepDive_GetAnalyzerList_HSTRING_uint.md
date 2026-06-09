# UpdateDiagnosticsInternal::DiagDeepDive::GetAnalyzerList(HSTRING__ * * *,uint *)

- ea: `0x18003a5d8`
- end: `0x18003a7d3`
- name: `?GetAnalyzerList@DiagDeepDive@UpdateDiagnosticsInternal@@SAJPEAPEAPEAUHSTRING__@@PEAI@Z`
- size: `507`
- prototype: `__int64 __fastcall(HSTRING **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000d048`

## callees

- `0x18000ad5c`
- `0x180016fe0`
- `0x1800171e8`
- `0x180017450`
- `0x180018854`
- `0x1800194b0`
- `0x18003a4cc`
- `0x18003a5d8`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a71f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a71f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a70b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a70b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall UpdateDiagnosticsInternal::DiagDeepDive::GetAnalyzerList(HSTRING **a1, unsigned int *a2)
{
  __int64 v5; // r14
  __int64 i; // rbx
  __int64 v7; // r15
  HSTRING v8; // rcx
  HSTRING *v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r9
  HSTRING v12; // rax
  HSTRING string; // [rsp+20h] [rbp-58h] BYREF
  __int128 v14; // [rsp+28h] [rbp-50h] BYREF
  __int64 v15; // [rsp+38h] [rbp-40h]
  __int128 v16; // [rsp+40h] [rbp-38h] BYREF
  __int64 v17; // [rsp+50h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( a1 )
  {
    if ( a2 )
    {
      *a1 = 0;
      *a2 = 0;
      v16 = 0;
      v17 = 0;
      UpdateDiagnosticsInternal::DiagDeepDive::TryGetAnalyzerList(&v16);
      v5 = (unsigned int)((__int64)(*((_QWORD *)&v16 + 1) - v16) >> 4);
      v14 = 0;
      v15 = 0;
      std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reserve(
        &v14,
        v5);
      v7 = *((_QWORD *)&v16 + 1);
      for ( i = v16; i != v7; i += 16 )
      {
        string = 0;
        wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
          &string,
          *(PCNZWCH *)i,
          *(unsigned int *)(i + 8));
        if ( *((_QWORD *)&v14 + 1) == v15 )
        {
          std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
            &v14,
            *((_QWORD **)&v14 + 1),
            (__int64 *)&string);
          v8 = string;
        }
        else
        {
          **((_QWORD **)&v14 + 1) = string;
          v8 = 0;
          string = 0;
          *((_QWORD *)&v14 + 1) += 8LL;
        }
        if ( v8 )
          WindowsDeleteString(v8);
      }
      v9 = (HSTRING *)CoTaskMemAlloc(8 * v5);
      if ( v9 )
      {
        if ( (_DWORD)v5 )
        {
          v10 = 0;
          v11 = v5;
          do
          {
            v12 = *(HSTRING *)(v10 * 8 + v14);
            *(_QWORD *)(v10 * 8 + v14) = 0;
            v9[v10++] = v12;
            --v11;
          }
          while ( v11 );
        }
        *a1 = v9;
        *a2 = v5;
        std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>((__int64)&v14);
        std::vector<std::wstring_view>::~vector<std::wstring_view>((__int64)&v16);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x73,
          (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\DiagDeepDive.cpp",
          (const char *)0x8007000ELL,
          (int)string);
        std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>((__int64)&v14);
        std::vector<std::wstring_view>::~vector<std::wstring_view>((__int64)&v16);
        return 2147942414LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5C,
        (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\DiagDeepDive.cpp",
        (const char *)0x80070057LL,
        (int)string);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\DiagDeepDive.cpp",
      (const char *)0x80070057LL,
      (int)string);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18003a5d8  mov     [rsp+arg_10], rbx
0x18003a5dd  mov     [rsp+arg_18], rsi
0x18003a5e2  push    rdi
0x18003a5e3  push    r14
0x18003a5e5  push    r15
0x18003a5e7  sub     rsp, 60h
0x18003a5eb  mov     rax, cs:__security_cookie
0x18003a5f2  xor     rax, rsp
0x18003a5f5  mov     [rsp+78h+var_20], rax
0x18003a5fa  mov     rsi, rdx
0x18003a5fd  mov     rdi, rcx
0x18003a600  test    rcx, rcx
0x18003a603  jnz     short loc_18003A628
0x18003a605  mov     rcx, [rsp+78h]; this
0x18003a60a  mov     ebx, 80070057h
0x18003a60f  mov     r9d, ebx; char *
0x18003a612  lea     r8, aCW1SSrcCalliop_2; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x18003a619  lea     edx, [rdi+5Bh]; void *
0x18003a61c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a621  mov     eax, ebx
0x18003a623  jmp     loc_18003A7AF
0x18003a628  test    rsi, rsi
0x18003a62b  jnz     short loc_18003A650
0x18003a62d  mov     rcx, [rsp+78h]; this
0x18003a632  mov     ebx, 80070057h
0x18003a637  mov     r9d, ebx; char *
0x18003a63a  lea     r8, aCW1SSrcCalliop_2; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x18003a641  lea     edx, [rsi+5Ch]; void *
0x18003a644  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a649  mov     eax, ebx
0x18003a64b  jmp     loc_18003A7AF
0x18003a650  mov     qword ptr [rcx], 0
0x18003a657  mov     dword ptr [rdx], 0
0x18003a65d  xorps   xmm0, xmm0
0x18003a660  xor     eax, eax
0x18003a662  movups  [rsp+78h+var_38], xmm0
0x18003a667  mov     [rsp+78h+var_28], rax
0x18003a66c  lea     rcx, [rsp+78h+var_38]
0x18003a671  call    ?TryGetAnalyzerList@DiagDeepDive@UpdateDiagnosticsInternal@@SA?AV?$vector@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$allocator@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@@std@@XZ; UpdateDiagnosticsInternal::DiagDeepDive::TryGetAnalyzerList(void)
0x18003a676  nop
0x18003a677  mov     r14, qword ptr [rsp+78h+var_38+8]
0x18003a67c  sub     r14, qword ptr [rsp+78h+var_38]
0x18003a681  sar     r14, 4
0x18003a685  mov     r14d, r14d
0x18003a688  xor     eax, eax
0x18003a68a  xorps   xmm1, xmm1
0x18003a68d  movdqu  [rsp+78h+var_50], xmm1
0x18003a693  mov     [rsp+78h+var_40], rax
0x18003a698  mov     edx, r14d
0x18003a69b  lea     rcx, [rsp+78h+var_50]
0x18003a6a0  call    ?reserve@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAX_K@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reserve(unsigned __int64)
0x18003a6a5  mov     rbx, qword ptr [rsp+78h+var_38]
0x18003a6aa  mov     r15, qword ptr [rsp+78h+var_38+8]
0x18003a6af  cmp     rbx, r15
0x18003a6b2  jz      short loc_18003A717
0x18003a6b4  mov     [rsp+78h+string], 0
0x18003a6bd  mov     r8d, [rbx+8]; length
0x18003a6c1  mov     rdx, [rbx]; sourceString
0x18003a6c4  lea     rcx, [rsp+78h+string]; string
0x18003a6c9  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x18003a6ce  nop
0x18003a6cf  mov     rdx, qword ptr [rsp+78h+var_50+8]
0x18003a6d4  cmp     rdx, [rsp+78h+var_40]
0x18003a6d9  jz      short loc_18003A6F2
0x18003a6db  mov     rax, [rsp+78h+string]
0x18003a6e0  mov     [rdx], rax
0x18003a6e3  xor     ecx, ecx
0x18003a6e5  mov     [rsp+78h+string], rcx
0x18003a6ea  add     qword ptr [rsp+78h+var_50+8], 8
0x18003a6f0  jmp     short loc_18003A706
0x18003a6f2  lea     r8, [rsp+78h+string]
0x18003a6f7  lea     rcx, [rsp+78h+var_50]
0x18003a6fc  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &&)
0x18003a701  mov     rcx, [rsp+78h+string]; string
0x18003a706  test    rcx, rcx
0x18003a709  jz      short loc_18003A711
0x18003a70b  call    cs:__imp_WindowsDeleteString
0x18003a711  add     rbx, 10h
0x18003a715  jmp     short loc_18003A6AF
0x18003a717  lea     rcx, ds:0[r14*8]; cb
0x18003a71f  call    cs:__imp_CoTaskMemAlloc
0x18003a725  mov     r8, rax
0x18003a728  test    rax, rax
0x18003a72b  jnz     short loc_18003A763
0x18003a72d  mov     rcx, [rsp+78h]; this
0x18003a732  mov     ebx, 8007000Eh
0x18003a737  mov     r9d, ebx; char *
0x18003a73a  lea     r8, aCW1SSrcCalliop_2; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x18003a741  lea     edx, [rax+73h]; void *
0x18003a744  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a749  nop
0x18003a74a  lea     rcx, [rsp+78h+var_50]
0x18003a74f  call    ??1?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x18003a754  nop
0x18003a755  lea     rcx, [rsp+78h+var_38]
0x18003a75a  call    ??1?$vector@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$allocator@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring_view>::~vector<std::wstring_view>(void)
0x18003a75f  mov     eax, ebx
0x18003a761  jmp     short loc_18003A7AF
0x18003a763  test    r14d, r14d
0x18003a766  jz      short loc_18003A78C
0x18003a768  xor     edx, edx
0x18003a76a  mov     r9, r14
0x18003a76d  mov     rcx, qword ptr [rsp+78h+var_50]
0x18003a772  mov     rax, [rdx+rcx]
0x18003a776  mov     qword ptr [rdx+rcx], 0
0x18003a77e  mov     [rdx+r8], rax
0x18003a782  lea     rdx, [rdx+8]
0x18003a786  sub     r9, 1
0x18003a78a  jnz     short loc_18003A76D
0x18003a78c  mov     [rdi], r8
0x18003a78f  mov     [rsi], r14d
0x18003a792  lea     rcx, [rsp+78h+var_50]
0x18003a797  call    ??1?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x18003a79c  nop
0x18003a79d  lea     rcx, [rsp+78h+var_38]
0x18003a7a2  call    ??1?$vector@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$allocator@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring_view>::~vector<std::wstring_view>(void)
0x18003a7a7  xor     eax, eax
0x18003a7a9  jmp     short loc_18003A7AF
0x18003a7ab  mov     eax, dword ptr [rsp+78h+string]
0x18003a7af  mov     rcx, [rsp+78h+var_20]
0x18003a7b4  xor     rcx, rsp; StackCookie
0x18003a7b7  call    __security_check_cookie
0x18003a7bc  lea     r11, [rsp+78h+var_18]
0x18003a7c1  mov     rbx, [r11+30h]
0x18003a7c5  mov     rsi, [r11+38h]
0x18003a7c9  mov     rsp, r11
0x18003a7cc  pop     r15
0x18003a7ce  pop     r14
0x18003a7d0  pop     rdi
0x18003a7d1  retn
```
