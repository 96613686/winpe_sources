# wil::details::str_vprintf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wchar_t const *,char * &)

- ea: `0x18000dc70`
- end: `0x18000ddc3`
- name: `??$str_vprintf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_WAEAPEAD@Z`
- size: `339`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d684`
- `0x18000dc1c`

## callees

- `0x180001b44`
- `0x180003760`
- `0x1800087e4`
- `0x18000a198`
- `0x18000dc70`
- `0x18000df84`
- `0x18000fbca`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dcfd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dd8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dda8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dcfd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dd8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dda8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dcef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dd7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dd9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dcef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dd7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dd9a`

## string_xrefs

- `0x18000dd50`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::str_vprintf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
        __int64 a1,
        const wchar_t *a2,
        va_list *a3)
{
  unsigned __int64 *v6; // rax
  int v7; // eax
  __int64 v8; // r14
  __int64 v9; // rax
  void *v10; // rbx
  HANDLE ProcessHeap; // rax
  wchar_t *v12; // rbx
  int v13; // edi
  __int64 v14; // rdx
  wchar_t *v15; // rdi
  HANDLE v16; // rax
  HANDLE v17; // rax
  int Locale; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  wchar_t *v21; // [rsp+70h] [rbp+18h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp+20h] BYREF

  v6 = _local_stdio_printf_options();
  v7 = o___stdio_common_vswprintf_0(*v6 | 2, 0, 0, a2, 0, *a3);
  v21 = 0;
  if ( v7 < 0 )
    v7 = -1;
  v8 = v7;
  v9 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
         &lpMem,
         0,
         v7);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
    &v21,
    v9);
  v10 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
  }
  v12 = v21;
  if ( !v21 )
  {
    v13 = -2147024882;
    v14 = 1915;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v13,
      Locale);
    goto LABEL_13;
  }
  v13 = StringCchVPrintfExW(v21, v8 + 1, 0, 0, 0x800u, a2, *a3);
  if ( v13 < 0 )
  {
    v14 = 1919;
    goto LABEL_9;
  }
  v21 = v12;
  v12 = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
    a1,
    &v21);
  v15 = v21;
  if ( v21 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v15);
  }
  v13 = 0;
LABEL_13:
  if ( v12 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v12);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000dc70  mov     [rsp+arg_0], rbx
0x18000dc75  mov     [rsp+arg_8], rbp
0x18000dc7a  push    rsi
0x18000dc7b  push    rdi
0x18000dc7c  push    r14
0x18000dc7e  sub     rsp, 40h
0x18000dc82  mov     rdi, r8
0x18000dc85  mov     rbp, rdx
0x18000dc88  mov     rsi, rcx
0x18000dc8b  call    __local_stdio_printf_options
0x18000dc90  mov     r9, rbp; Format
0x18000dc93  xor     r8d, r8d; BufferCount
0x18000dc96  xor     edx, edx; Buffer
0x18000dc98  mov     rcx, [rax]
0x18000dc9b  mov     rax, [rdi]
0x18000dc9e  or      rcx, 2; Options
0x18000dca2  mov     [rsp+58h+ArgList], rax; ArgList
0x18000dca7  mov     [rsp+58h+Locale], 0; Locale
0x18000dcb0  call    _o___stdio_common_vswprintf_0
0x18000dcb5  or      ecx, 0FFFFFFFFh
0x18000dcb8  mov     [rsp+58h+arg_10], 0
0x18000dcc1  test    eax, eax
0x18000dcc3  cmovs   eax, ecx
0x18000dcc6  xor     edx, edx
0x18000dcc8  movsxd  r14, eax
0x18000dccb  lea     rcx, [rsp+58h+lpMem]
0x18000dcd0  mov     r8, r14
0x18000dcd3  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x18000dcd8  mov     rdx, rax
0x18000dcdb  lea     rcx, [rsp+58h+arg_10]
0x18000dce0  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x18000dce5  mov     rbx, [rsp+58h+lpMem]
0x18000dcea  test    rbx, rbx
0x18000dced  jz      short loc_18000DD03
0x18000dcef  call    cs:__imp_GetProcessHeap
0x18000dcf5  mov     r8, rbx; lpMem
0x18000dcf8  xor     edx, edx; dwFlags
0x18000dcfa  mov     rcx, rax; hHeap
0x18000dcfd  call    cs:__imp_HeapFree
0x18000dd03  mov     rbx, [rsp+58h+arg_10]
0x18000dd08  test    rbx, rbx
0x18000dd0b  jnz     short loc_18000DD19
0x18000dd0d  mov     edi, 8007000Eh
0x18000dd12  mov     edx, 77Bh
0x18000dd17  jmp     short loc_18000DD4B
0x18000dd19  mov     rax, [rdi]
0x18000dd1c  lea     rdx, [r14+1]; unsigned __int64
0x18000dd20  mov     [rsp+58h+var_28], rax; char *
0x18000dd25  xor     r9d, r9d; unsigned __int64 *
0x18000dd28  mov     [rsp+58h+ArgList], rbp; wchar_t *
0x18000dd2d  xor     r8d, r8d; wchar_t **
0x18000dd30  mov     rcx, rbx; wchar_t *
0x18000dd33  mov     dword ptr [rsp+58h+Locale], 800h; int
0x18000dd3b  call    ?StringCchVPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WPEAD@Z; StringCchVPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,char *)
0x18000dd40  mov     edi, eax
0x18000dd42  test    eax, eax
0x18000dd44  jns     short loc_18000DD61
0x18000dd46  mov     edx, 77Fh; void *
0x18000dd4b  mov     rcx, [rsp+58h]; this
0x18000dd50  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000dd57  mov     r9d, edi; char *
0x18000dd5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dd5f  jmp     short loc_18000DD95
0x18000dd61  mov     [rsp+58h+arg_10], rbx
0x18000dd66  lea     rdx, [rsp+58h+arg_10]
0x18000dd6b  mov     rcx, rsi
0x18000dd6e  xor     ebx, ebx
0x18000dd70  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x18000dd75  mov     rdi, [rsp+58h+arg_10]
0x18000dd7a  test    rdi, rdi
0x18000dd7d  jz      short loc_18000DD93
0x18000dd7f  call    cs:__imp_GetProcessHeap
0x18000dd85  mov     r8, rdi; lpMem
0x18000dd88  xor     edx, edx; dwFlags
0x18000dd8a  mov     rcx, rax; hHeap
0x18000dd8d  call    cs:__imp_HeapFree
0x18000dd93  xor     edi, edi
0x18000dd95  test    rbx, rbx
0x18000dd98  jz      short loc_18000DDAE
0x18000dd9a  call    cs:__imp_GetProcessHeap
0x18000dda0  mov     r8, rbx; lpMem
0x18000dda3  xor     edx, edx; dwFlags
0x18000dda5  mov     rcx, rax; hHeap
0x18000dda8  call    cs:__imp_HeapFree
0x18000ddae  mov     rbx, [rsp+58h+arg_0]
0x18000ddb3  mov     eax, edi
0x18000ddb5  mov     rbp, [rsp+58h+arg_8]
0x18000ddba  add     rsp, 40h
0x18000ddbe  pop     r14
0x18000ddc0  pop     rdi
0x18000ddc1  pop     rsi
0x18000ddc2  retn
```
