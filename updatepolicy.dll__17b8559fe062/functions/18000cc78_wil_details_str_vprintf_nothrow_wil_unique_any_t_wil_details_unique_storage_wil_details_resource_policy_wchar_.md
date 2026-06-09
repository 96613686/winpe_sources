# wil::details::str_vprintf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wchar_t const *,char * &)

- ea: `0x18000cc78`
- end: `0x18000cdcb`
- name: `??$str_vprintf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_WAEAPEAD@Z`
- size: `339`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, va_list *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c690`
- `0x18000cc24`

## callees

- `0x1800045f8`
- `0x180005a74`
- `0x180006858`
- `0x180006ac4`
- `0x18000cc78`
- `0x18000d070`
- `0x18000ec31`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ccf7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cd87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cda2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ccf7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cd87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cda2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cd05`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cd95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cdb0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cd05`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cd95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cdb0`

## string_xrefs

- `0x18000cd58`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

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
  wchar_t *Buffer; // [rsp+70h] [rbp+18h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp+20h] BYREF

  v6 = _local_stdio_printf_options();
  v7 = o___stdio_common_vswprintf_0(*v6 | 2, 0, 0, a2, 0, *a3);
  Buffer = 0;
  if ( v7 < 0 )
    v7 = -1;
  v8 = v7;
  v9 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
         &lpMem,
         0,
         v7);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
    &Buffer,
    v9);
  v10 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
  }
  v12 = Buffer;
  if ( !Buffer )
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
  v13 = StringCchVPrintfExW(Buffer, v8 + 1, 0, 0, 0x800u, a2, *a3);
  if ( v13 < 0 )
  {
    v14 = 1919;
    goto LABEL_9;
  }
  Buffer = v12;
  v12 = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
    a1,
    &Buffer);
  v15 = Buffer;
  if ( Buffer )
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
0x18000cc78  mov     [rsp+arg_0], rbx
0x18000cc7d  mov     [rsp+arg_8], rbp
0x18000cc82  push    rsi
0x18000cc83  push    rdi
0x18000cc84  push    r14
0x18000cc86  sub     rsp, 40h
0x18000cc8a  mov     rdi, r8
0x18000cc8d  mov     rbp, rdx
0x18000cc90  mov     rsi, rcx
0x18000cc93  call    __local_stdio_printf_options
0x18000cc98  mov     r9, rbp; Format
0x18000cc9b  xor     r8d, r8d; BufferCount
0x18000cc9e  xor     edx, edx; Buffer
0x18000cca0  mov     rcx, [rax]
0x18000cca3  mov     rax, [rdi]
0x18000cca6  or      rcx, 2; Options
0x18000ccaa  mov     [rsp+58h+ArgList], rax; ArgList
0x18000ccaf  mov     [rsp+58h+Locale], 0; Locale
0x18000ccb8  call    _o___stdio_common_vswprintf_0
0x18000ccbd  or      ecx, 0FFFFFFFFh
0x18000ccc0  mov     [rsp+58h+Buffer], 0
0x18000ccc9  test    eax, eax
0x18000cccb  cmovs   eax, ecx
0x18000ccce  xor     edx, edx
0x18000ccd0  movsxd  r14, eax
0x18000ccd3  lea     rcx, [rsp+58h+lpMem]
0x18000ccd8  mov     r8, r14
0x18000ccdb  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x18000cce0  mov     rdx, rax
0x18000cce3  lea     rcx, [rsp+58h+Buffer]
0x18000cce8  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x18000cced  mov     rbx, [rsp+58h+lpMem]
0x18000ccf2  test    rbx, rbx
0x18000ccf5  jz      short loc_18000CD0B
0x18000ccf7  call    cs:__imp_GetProcessHeap
0x18000ccfd  mov     r8, rbx; lpMem
0x18000cd00  xor     edx, edx; dwFlags
0x18000cd02  mov     rcx, rax; hHeap
0x18000cd05  call    cs:__imp_HeapFree
0x18000cd0b  mov     rbx, [rsp+58h+Buffer]
0x18000cd10  test    rbx, rbx
0x18000cd13  jnz     short loc_18000CD21
0x18000cd15  mov     edi, 8007000Eh
0x18000cd1a  mov     edx, 77Bh
0x18000cd1f  jmp     short loc_18000CD53
0x18000cd21  mov     rax, [rdi]
0x18000cd24  lea     rdx, [r14+1]; unsigned __int64
0x18000cd28  mov     [rsp+58h+var_28], rax; char *
0x18000cd2d  xor     r9d, r9d; unsigned __int64 *
0x18000cd30  mov     [rsp+58h+ArgList], rbp; wchar_t *
0x18000cd35  xor     r8d, r8d; wchar_t **
0x18000cd38  mov     rcx, rbx; Buffer
0x18000cd3b  mov     dword ptr [rsp+58h+Locale], 800h; int
0x18000cd43  call    ?StringCchVPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WPEAD@Z; StringCchVPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,char *)
0x18000cd48  mov     edi, eax
0x18000cd4a  test    eax, eax
0x18000cd4c  jns     short loc_18000CD69
0x18000cd4e  mov     edx, 77Fh; void *
0x18000cd53  mov     rcx, [rsp+58h]; this
0x18000cd58  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000cd5f  mov     r9d, edi; char *
0x18000cd62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cd67  jmp     short loc_18000CD9D
0x18000cd69  mov     [rsp+58h+Buffer], rbx
0x18000cd6e  lea     rdx, [rsp+58h+Buffer]
0x18000cd73  mov     rcx, rsi
0x18000cd76  xor     ebx, ebx
0x18000cd78  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x18000cd7d  mov     rdi, [rsp+58h+Buffer]
0x18000cd82  test    rdi, rdi
0x18000cd85  jz      short loc_18000CD9B
0x18000cd87  call    cs:__imp_GetProcessHeap
0x18000cd8d  mov     r8, rdi; lpMem
0x18000cd90  xor     edx, edx; dwFlags
0x18000cd92  mov     rcx, rax; hHeap
0x18000cd95  call    cs:__imp_HeapFree
0x18000cd9b  xor     edi, edi
0x18000cd9d  test    rbx, rbx
0x18000cda0  jz      short loc_18000CDB6
0x18000cda2  call    cs:__imp_GetProcessHeap
0x18000cda8  mov     r8, rbx; lpMem
0x18000cdab  xor     edx, edx; dwFlags
0x18000cdad  mov     rcx, rax; hHeap
0x18000cdb0  call    cs:__imp_HeapFree
0x18000cdb6  mov     rbx, [rsp+58h+arg_0]
0x18000cdbb  mov     eax, edi
0x18000cdbd  mov     rbp, [rsp+58h+arg_8]
0x18000cdc2  add     rsp, 40h
0x18000cdc6  pop     r14
0x18000cdc8  pop     rdi
0x18000cdc9  pop     rsi
0x18000cdca  retn
```
