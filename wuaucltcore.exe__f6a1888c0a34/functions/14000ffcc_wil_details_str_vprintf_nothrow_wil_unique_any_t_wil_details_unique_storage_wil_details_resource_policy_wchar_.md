# wil::details::str_vprintf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wchar_t const *,char * &)

- ea: `0x14000ffcc`
- end: `0x14001011f`
- name: `??$str_vprintf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_WAEAPEAD@Z`
- size: `339`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000f9d0`
- `0x14000ff78`

## callees

- `0x140001dd4`
- `0x140002ac0`
- `0x1400092bc`
- `0x14000b224`
- `0x14000ffcc`
- `0x1400102e8`
- `0x14001a8ef`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010059`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400100e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010104`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010059`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400100e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010104`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001004b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400100db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400100f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001004b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400100db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400100f6`

## string_xrefs

- `0x1400100ac`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

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
0x14000ffcc  mov     [rsp+arg_0], rbx
0x14000ffd1  mov     [rsp+arg_8], rbp
0x14000ffd6  push    rsi
0x14000ffd7  push    rdi
0x14000ffd8  push    r14
0x14000ffda  sub     rsp, 40h
0x14000ffde  mov     rdi, r8
0x14000ffe1  mov     rbp, rdx
0x14000ffe4  mov     rsi, rcx
0x14000ffe7  call    __local_stdio_printf_options
0x14000ffec  mov     r9, rbp; Format
0x14000ffef  xor     r8d, r8d; BufferCount
0x14000fff2  xor     edx, edx; Buffer
0x14000fff4  mov     rcx, [rax]
0x14000fff7  mov     rax, [rdi]
0x14000fffa  or      rcx, 2; Options
0x14000fffe  mov     [rsp+58h+ArgList], rax; ArgList
0x140010003  mov     [rsp+58h+Locale], 0; Locale
0x14001000c  call    _o___stdio_common_vswprintf_0
0x140010011  or      ecx, 0FFFFFFFFh
0x140010014  mov     [rsp+58h+arg_10], 0
0x14001001d  test    eax, eax
0x14001001f  cmovs   eax, ecx
0x140010022  xor     edx, edx
0x140010024  movsxd  r14, eax
0x140010027  lea     rcx, [rsp+58h+lpMem]
0x14001002c  mov     r8, r14
0x14001002f  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x140010034  mov     rdx, rax
0x140010037  lea     rcx, [rsp+58h+arg_10]
0x14001003c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x140010041  mov     rbx, [rsp+58h+lpMem]
0x140010046  test    rbx, rbx
0x140010049  jz      short loc_14001005F
0x14001004b  call    cs:__imp_GetProcessHeap
0x140010051  mov     r8, rbx; lpMem
0x140010054  xor     edx, edx; dwFlags
0x140010056  mov     rcx, rax; hHeap
0x140010059  call    cs:__imp_HeapFree
0x14001005f  mov     rbx, [rsp+58h+arg_10]
0x140010064  test    rbx, rbx
0x140010067  jnz     short loc_140010075
0x140010069  mov     edi, 8007000Eh
0x14001006e  mov     edx, 77Bh
0x140010073  jmp     short loc_1400100A7
0x140010075  mov     rax, [rdi]
0x140010078  lea     rdx, [r14+1]; unsigned __int64
0x14001007c  mov     [rsp+58h+var_28], rax; char *
0x140010081  xor     r9d, r9d; unsigned __int64 *
0x140010084  mov     [rsp+58h+ArgList], rbp; wchar_t *
0x140010089  xor     r8d, r8d; wchar_t **
0x14001008c  mov     rcx, rbx; wchar_t *
0x14001008f  mov     dword ptr [rsp+58h+Locale], 800h; int
0x140010097  call    ?StringCchVPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WPEAD@Z; StringCchVPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,char *)
0x14001009c  mov     edi, eax
0x14001009e  test    eax, eax
0x1400100a0  jns     short loc_1400100BD
0x1400100a2  mov     edx, 77Fh; void *
0x1400100a7  mov     rcx, [rsp+58h]; this
0x1400100ac  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1400100b3  mov     r9d, edi; char *
0x1400100b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400100bb  jmp     short loc_1400100F1
0x1400100bd  mov     [rsp+58h+arg_10], rbx
0x1400100c2  lea     rdx, [rsp+58h+arg_10]
0x1400100c7  mov     rcx, rsi
0x1400100ca  xor     ebx, ebx
0x1400100cc  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x1400100d1  mov     rdi, [rsp+58h+arg_10]
0x1400100d6  test    rdi, rdi
0x1400100d9  jz      short loc_1400100EF
0x1400100db  call    cs:__imp_GetProcessHeap
0x1400100e1  mov     r8, rdi; lpMem
0x1400100e4  xor     edx, edx; dwFlags
0x1400100e6  mov     rcx, rax; hHeap
0x1400100e9  call    cs:__imp_HeapFree
0x1400100ef  xor     edi, edi
0x1400100f1  test    rbx, rbx
0x1400100f4  jz      short loc_14001010A
0x1400100f6  call    cs:__imp_GetProcessHeap
0x1400100fc  mov     r8, rbx; lpMem
0x1400100ff  xor     edx, edx; dwFlags
0x140010101  mov     rcx, rax; hHeap
0x140010104  call    cs:__imp_HeapFree
0x14001010a  mov     rbx, [rsp+58h+arg_0]
0x14001010f  mov     eax, edi
0x140010111  mov     rbp, [rsp+58h+arg_8]
0x140010116  add     rsp, 40h
0x14001011a  pop     r14
0x14001011c  pop     rdi
0x14001011d  pop     rsi
0x14001011e  retn
```
