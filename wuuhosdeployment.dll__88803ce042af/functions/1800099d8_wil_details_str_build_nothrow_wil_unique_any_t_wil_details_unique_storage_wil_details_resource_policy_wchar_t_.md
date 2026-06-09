# wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x1800099d8`
- end: `0x180009b91`
- name: `??$str_build_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@PEB_WPEB_WPEB_WPEB_W@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W111@Z`
- size: `441`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009214`

## callees

- `0x180003950`
- `0x1800099d8`
- `0x180009b98`
- `0x180009c1c`
- `0x180009e38`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009a80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b89`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009a80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b89`

## string_xrefs

- `0x180009aa3`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x180009b67`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v6; // rsi
  _QWORD *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  void *v10; // rbx
  HANDLE ProcessHeap; // rax
  STRSAFE_LPWSTR v12; // rbx
  unsigned int v13; // edi
  wchar_t *v14; // rcx
  wchar_t *v15; // r14
  const wchar_t **v16; // rsi
  int v17; // eax
  STRSAFE_LPWSTR v18; // rbx
  HANDLE v19; // rax
  HANDLE v21; // rax
  int v22; // [rsp+20h] [rbp-50h]
  int v23; // [rsp+20h] [rbp-50h]
  STRSAFE_LPWSTR pszDest; // [rsp+30h] [rbp-40h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-38h] BYREF
  _QWORD v26[4]; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v27[2]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v26[3] = a5;
  v6 = 0;
  v26[0] = a2;
  v26[1] = a3;
  v7 = v26;
  v26[2] = a4;
  do
  {
    if ( *v7 )
    {
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)(*v7 + 2 * v8) );
    }
    else
    {
      v8 = 0;
    }
    v6 += v8;
    ++v7;
  }
  while ( v7 != v27 );
  pszDest = 0;
  v9 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
         &lpMem,
         0,
         v6);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
    &pszDest,
    v9);
  v10 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
  }
  v12 = pszDest;
  v13 = pszDest == 0 ? 0x8007000E : 0;
  if ( pszDest )
  {
    v14 = pszDest;
    v15 = &pszDest[v6 + 1];
    v16 = (const wchar_t **)v26;
    do
    {
      if ( *v16 )
      {
        v17 = StringCchCopyExW(v14, v15 - v14, *v16, &pszDest, 0, 0x100u);
        v13 = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x73F,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
            (const char *)(unsigned int)v17,
            v23);
          v21 = GetProcessHeap();
          HeapFree(v21, 0, v12);
          return v13;
        }
        v14 = pszDest;
      }
      ++v16;
    }
    while ( v16 != v27 );
    pszDest = v12;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
      a1,
      &pszDest);
    v18 = pszDest;
    if ( pszDest )
    {
      v19 = GetProcessHeap();
      HeapFree(v19, 0, v18);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x737,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)v13,
      v22);
  }
  return v13;
}

```

## disassembly

```asm
0x1800099d8  mov     [rsp-28h+arg_8], rbx
0x1800099dd  mov     [rsp-28h+arg_10], rsi
0x1800099e2  push    rbp
0x1800099e3  push    rdi
0x1800099e4  push    r12
0x1800099e6  push    r14
0x1800099e8  push    r15
0x1800099ea  mov     rbp, rsp
0x1800099ed  sub     rsp, 70h
0x1800099f1  mov     rax, cs:__security_cookie
0x1800099f8  xor     rax, rsp
0x1800099fb  mov     [rbp+var_10], rax
0x1800099ff  mov     rax, [rbp+arg_20]
0x180009a03  xor     r12d, r12d
0x180009a06  mov     r15, rcx
0x180009a09  mov     [rbp+var_18], rax
0x180009a0d  mov     esi, r12d
0x180009a10  mov     [rbp+var_30], rdx
0x180009a14  mov     [rbp+var_28], r8
0x180009a18  lea     rcx, [rbp+var_30]
0x180009a1c  mov     [rbp+var_20], r9
0x180009a20  mov     rdx, [rcx]
0x180009a23  test    rdx, rdx
0x180009a26  jz      short loc_180009A38
0x180009a28  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009a2c  inc     rax
0x180009a2f  cmp     [rdx+rax*2], r12w
0x180009a34  jnz     short loc_180009A2C
0x180009a36  jmp     short loc_180009A3B
0x180009a38  mov     rax, r12
0x180009a3b  add     rsi, rax
0x180009a3e  add     rcx, 8
0x180009a42  lea     rax, [rbp+var_10]
0x180009a46  cmp     rcx, rax
0x180009a49  jnz     short loc_180009A20
0x180009a4b  mov     r8, rsi
0x180009a4e  mov     [rbp+pszDest], r12
0x180009a52  xor     edx, edx
0x180009a54  lea     rcx, [rbp+lpMem]
0x180009a58  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x180009a5d  mov     rdx, rax
0x180009a60  lea     rcx, [rbp+pszDest]
0x180009a64  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x180009a69  mov     rbx, [rbp+lpMem]
0x180009a6d  test    rbx, rbx
0x180009a70  jz      short loc_180009A86
0x180009a72  call    cs:__imp_GetProcessHeap
0x180009a78  mov     r8, rbx; lpMem
0x180009a7b  xor     edx, edx; dwFlags
0x180009a7d  mov     rcx, rax; hHeap
0x180009a80  call    cs:__imp_HeapFree
0x180009a86  mov     rbx, [rbp+pszDest]
0x180009a8a  mov     rax, rbx
0x180009a8d  neg     rax
0x180009a90  sbb     edi, edi
0x180009a92  not     edi
0x180009a94  and     edi, 8007000Eh
0x180009a9a  test    rbx, rbx
0x180009a9d  jnz     short loc_180009ABC
0x180009a9f  mov     rcx, [rbp+28h]; this
0x180009aa3  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180009aaa  mov     r9d, edi; char *
0x180009aad  mov     edx, 737h; void *
0x180009ab2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009ab7  jmp     loc_180009B3C
0x180009abc  inc     rsi
0x180009abf  mov     [rbp+pszDest], rbx
0x180009ac3  mov     rcx, rbx; pszDest
0x180009ac6  lea     r14, [rbx+rsi*2]
0x180009aca  lea     rsi, [rbp+var_30]
0x180009ace  mov     r8, [rsi]; wchar_t *
0x180009ad1  test    r8, r8
0x180009ad4  jz      short loc_180009AFF
0x180009ad6  mov     rdx, r14
0x180009ad9  mov     [rsp+70h+var_48], 100h; unsigned int
0x180009ae1  sub     rdx, rcx
0x180009ae4  mov     [rsp+70h+var_50], r12; int
0x180009ae9  sar     rdx, 1; unsigned __int64
0x180009aec  lea     r9, [rbp+pszDest]; wchar_t **
0x180009af0  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x180009af5  mov     edi, eax
0x180009af7  test    eax, eax
0x180009af9  js      short loc_180009B63
0x180009afb  mov     rcx, [rbp+pszDest]
0x180009aff  add     rsi, 8
0x180009b03  lea     rax, [rbp+var_10]
0x180009b07  cmp     rsi, rax
0x180009b0a  jnz     short loc_180009ACE
0x180009b0c  lea     rdx, [rbp+pszDest]
0x180009b10  mov     [rbp+pszDest], rbx
0x180009b14  mov     rcx, r15
0x180009b17  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x180009b1c  mov     rbx, [rbp+pszDest]
0x180009b20  test    rbx, rbx
0x180009b23  jz      short loc_180009B39
0x180009b25  call    cs:__imp_GetProcessHeap
0x180009b2b  mov     r8, rbx; lpMem
0x180009b2e  xor     edx, edx; dwFlags
0x180009b30  mov     rcx, rax; hHeap
0x180009b33  call    cs:__imp_HeapFree
0x180009b39  mov     edi, r12d
0x180009b3c  mov     eax, edi
0x180009b3e  mov     rcx, [rbp+var_10]
0x180009b42  xor     rcx, rsp; StackCookie
0x180009b45  call    __security_check_cookie
0x180009b4a  lea     r11, [rsp+70h+var_s0]
0x180009b4f  mov     rbx, [r11+38h]
0x180009b53  mov     rsi, [r11+40h]
0x180009b57  mov     rsp, r11
0x180009b5a  pop     r15
0x180009b5c  pop     r14
0x180009b5e  pop     r12
0x180009b60  pop     rdi
0x180009b61  pop     rbp
0x180009b62  retn
0x180009b63  mov     rcx, [rbp+28h]; this
0x180009b67  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180009b6e  mov     r9d, eax; char *
0x180009b71  mov     edx, 73Fh; void *
0x180009b76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009b7b  call    cs:__imp_GetProcessHeap
0x180009b81  mov     r8, rbx; lpMem
0x180009b84  xor     edx, edx; dwFlags
0x180009b86  mov     rcx, rax; hHeap
0x180009b89  call    cs:__imp_HeapFree
0x180009b8f  jmp     short loc_180009B3C
```
