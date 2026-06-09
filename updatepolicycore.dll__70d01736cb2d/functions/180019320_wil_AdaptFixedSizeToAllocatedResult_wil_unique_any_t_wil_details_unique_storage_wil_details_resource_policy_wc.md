# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)

- ea: `0x180019320`
- end: `0x1800194e9`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z`
- size: `457`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018bc4`

## callees

- `0x18000aac0`
- `0x180019320`
- `0x180019560`
- `0x1800196e0`
- `0x180019f14`
- `0x18002fda9`
- `0x18002ffd0`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019454`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800194a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019454`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800194a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019446`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019498`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019446`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019498`

## string_xrefs

- `0x18001947b`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
        __int64 a1,
        __int64 a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  unsigned __int64 v7; // rax
  int v8; // esi
  __int64 v9; // rdx
  void *v10; // rbx
  unsigned __int64 v11; // r14
  void *v12; // rbx
  HANDLE v13; // rax
  __int64 v14; // rcx
  HANDLE ProcessHeap; // rax
  __int64 v16; // rcx
  LPVOID lpMem; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v18; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v19[512]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  lpMem = 0;
  memset_0(v19, 0, sizeof(v19));
  v18 = 0;
  v4 = wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v19, 256, &v18);
  if ( v4 < 0 )
  {
    v5 = *(_QWORD *)(a2 + 112);
    if ( v5 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v5 + 24LL))(*(_QWORD *)(a2 + 112));
    return (unsigned int)v4;
  }
  v7 = v18;
  if ( v18 > 0x100 )
  {
    while ( 1 )
    {
      v11 = v7;
      v8 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(
             &lpMem,
             0,
             v7 - 1);
      if ( v8 < 0 )
        break;
      v10 = lpMem;
      v8 = wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(a2, lpMem, v11, &v18);
      if ( v8 < 0 )
        goto LABEL_19;
      v7 = v18;
      if ( v18 <= v11 )
        goto LABEL_12;
    }
    v9 = 362;
    goto LABEL_18;
  }
  v8 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(
         &lpMem,
         v19,
         v18 - 1);
  if ( v8 < 0 )
  {
    v9 = 351;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\win32_helpers.h",
      (const char *)(unsigned int)v8,
      (int)lpMem);
    v10 = lpMem;
LABEL_19:
    if ( v10 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v10);
    }
    v16 = *(_QWORD *)(a2 + 112);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 24LL))(v16);
    return (unsigned int)v8;
  }
  v10 = lpMem;
LABEL_12:
  lpMem = v10;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
    a1,
    &lpMem);
  v12 = lpMem;
  if ( lpMem )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v12);
  }
  v14 = *(_QWORD *)(a2 + 112);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
  return 0;
}

```

## disassembly

```asm
0x180019320  mov     [rsp-8+arg_10], rbx
0x180019325  push    rbp
0x180019326  push    rsi
0x180019327  push    rdi
0x180019328  push    r14
0x18001932a  push    r15
0x18001932c  lea     rbp, [rsp-140h]
0x180019334  sub     rsp, 240h
0x18001933b  mov     rax, cs:__security_cookie
0x180019342  xor     rax, rsp
0x180019345  mov     [rbp+160h+var_30], rax
0x18001934c  mov     rdi, rdx
0x18001934f  mov     r15, rcx
0x180019352  mov     [rsp+260h+lpMem], 0; int
0x18001935b  xor     edx, edx; Val
0x18001935d  mov     r8d, 200h; Size
0x180019363  lea     rcx, [rsp+260h+var_230]; void *
0x180019368  call    memset_0
0x18001936d  mov     [rsp+260h+var_238], 0
0x180019376  lea     r9, [rsp+260h+var_238]
0x18001937b  mov     esi, 100h
0x180019380  mov     r8d, esi
0x180019383  lea     rdx, [rsp+260h+var_230]
0x180019388  mov     rcx, rdi
0x18001938b  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x180019390  mov     ebx, eax
0x180019392  test    eax, eax
0x180019394  jns     short loc_1800193B5
0x180019396  mov     rdx, [rdi+70h]
0x18001939a  test    rdx, rdx
0x18001939d  jz      short loc_1800193AE
0x18001939f  mov     rcx, [rdx]
0x1800193a2  mov     rax, [rcx+18h]
0x1800193a6  mov     rcx, rdx
0x1800193a9  call    _guard_dispatch_icall
0x1800193ae  mov     eax, ebx
0x1800193b0  jmp     loc_1800194C3
0x1800193b5  mov     rax, [rsp+260h+var_238]
0x1800193ba  cmp     rax, rsi
0x1800193bd  ja      short loc_1800193E9
0x1800193bf  lea     r8, [rax-1]
0x1800193c3  lea     rdx, [rsp+260h+var_230]
0x1800193c8  lea     rcx, [rsp+260h+lpMem]
0x1800193cd  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x1800193d2  mov     esi, eax
0x1800193d4  test    eax, eax
0x1800193d6  jns     short loc_1800193E2
0x1800193d8  mov     edx, 15Fh
0x1800193dd  jmp     loc_180019478
0x1800193e2  mov     rbx, [rsp+260h+lpMem]
0x1800193e7  jmp     short loc_18001942A
0x1800193e9  mov     r14, rax
0x1800193ec  lea     r8, [rax-1]
0x1800193f0  xor     edx, edx
0x1800193f2  lea     rcx, [rsp+260h+lpMem]
0x1800193f7  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x1800193fc  mov     esi, eax
0x1800193fe  test    eax, eax
0x180019400  js      short loc_180019473
0x180019402  lea     r9, [rsp+260h+var_238]
0x180019407  mov     r8, r14
0x18001940a  mov     rbx, [rsp+260h+lpMem]
0x18001940f  mov     rdx, rbx
0x180019412  mov     rcx, rdi
0x180019415  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x18001941a  mov     esi, eax
0x18001941c  test    eax, eax
0x18001941e  js      short loc_180019493
0x180019420  mov     rax, [rsp+260h+var_238]
0x180019425  cmp     rax, r14
0x180019428  ja      short loc_1800193E9
0x18001942a  mov     [rsp+260h+lpMem], rbx
0x18001942f  lea     rdx, [rsp+260h+lpMem]
0x180019434  mov     rcx, r15
0x180019437  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x18001943c  mov     rbx, [rsp+260h+lpMem]
0x180019441  test    rbx, rbx
0x180019444  jz      short loc_18001945A
0x180019446  call    cs:__imp_GetProcessHeap
0x18001944c  mov     rcx, rax; hHeap
0x18001944f  mov     r8, rbx; lpMem
0x180019452  xor     edx, edx; dwFlags
0x180019454  call    cs:__imp_HeapFree
0x18001945a  mov     rcx, [rdi+70h]
0x18001945e  test    rcx, rcx
0x180019461  jz      short loc_18001946F
0x180019463  mov     rax, [rcx]
0x180019466  mov     rax, [rax+18h]
0x18001946a  call    _guard_dispatch_icall
0x18001946f  xor     eax, eax
0x180019471  jmp     short loc_1800194C3
0x180019473  mov     edx, 16Ah; void *
0x180019478  mov     r9d, esi; char *
0x18001947b  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180019482  mov     rcx, [rbp+168h]; this
0x180019489  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001948e  mov     rbx, [rsp+260h+lpMem]
0x180019493  test    rbx, rbx
0x180019496  jz      short loc_1800194AC
0x180019498  call    cs:__imp_GetProcessHeap
0x18001949e  mov     r8, rbx; lpMem
0x1800194a1  xor     edx, edx; dwFlags
0x1800194a3  mov     rcx, rax; hHeap
0x1800194a6  call    cs:__imp_HeapFree
0x1800194ac  mov     rcx, [rdi+70h]
0x1800194b0  test    rcx, rcx
0x1800194b3  jz      short loc_1800194C1
0x1800194b5  mov     rax, [rcx]
0x1800194b8  mov     rax, [rax+18h]
0x1800194bc  call    _guard_dispatch_icall
0x1800194c1  mov     eax, esi
0x1800194c3  mov     rcx, [rbp+160h+var_30]
0x1800194ca  xor     rcx, rsp; StackCookie
0x1800194cd  call    __security_check_cookie
0x1800194d2  mov     rbx, [rsp+260h+arg_10]
0x1800194da  add     rsp, 240h
0x1800194e1  pop     r15
0x1800194e3  pop     r14
0x1800194e5  pop     rdi
0x1800194e6  pop     rsi
0x1800194e7  pop     rbp
0x1800194e8  retn
```
