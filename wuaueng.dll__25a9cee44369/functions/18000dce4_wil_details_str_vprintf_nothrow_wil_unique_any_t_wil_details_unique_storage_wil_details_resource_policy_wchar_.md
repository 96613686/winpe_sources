# wil::details::str_vprintf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wchar_t const *,char * &)

- ea: `0x18000dce4`
- end: `0x18000de37`
- name: `??$str_vprintf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_WAEAPEAD@Z`
- size: `339`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, va_list *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d6f8`
- `0x18000dc90`

## callees

- `0x180001b44`
- `0x180003760`
- `0x1800069a0`
- `0x180008b20`
- `0x18000dce4`
- `0x18000dff8`
- `0x18000fb7a`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dd71`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dd71`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dd63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ddf3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dd63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ddf3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de0e`

## string_xrefs

- `0x18000ddc4`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

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
0x18000dce4  mov     [rsp+arg_0], rbx
0x18000dce9  mov     [rsp+arg_8], rbp
0x18000dcee  push    rsi
0x18000dcef  push    rdi
0x18000dcf0  push    r14
0x18000dcf2  sub     rsp, 40h
0x18000dcf6  mov     rdi, r8
0x18000dcf9  mov     rbp, rdx
0x18000dcfc  mov     rsi, rcx
0x18000dcff  call    __local_stdio_printf_options
0x18000dd04  mov     r9, rbp; Format
0x18000dd07  xor     r8d, r8d; BufferCount
0x18000dd0a  xor     edx, edx; Buffer
0x18000dd0c  mov     rcx, [rax]
0x18000dd0f  mov     rax, [rdi]
0x18000dd12  or      rcx, 2; Options
0x18000dd16  mov     [rsp+58h+ArgList], rax; ArgList
0x18000dd1b  mov     [rsp+58h+Locale], 0; Locale
0x18000dd24  call    _o___stdio_common_vswprintf_0
0x18000dd29  or      ecx, 0FFFFFFFFh
0x18000dd2c  mov     [rsp+58h+arg_10], 0
0x18000dd35  test    eax, eax
0x18000dd37  cmovs   eax, ecx
0x18000dd3a  xor     edx, edx
0x18000dd3c  movsxd  r14, eax
0x18000dd3f  lea     rcx, [rsp+58h+lpMem]
0x18000dd44  mov     r8, r14
0x18000dd47  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x18000dd4c  mov     rdx, rax
0x18000dd4f  lea     rcx, [rsp+58h+arg_10]
0x18000dd54  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x18000dd59  mov     rbx, [rsp+58h+lpMem]
0x18000dd5e  test    rbx, rbx
0x18000dd61  jz      short loc_18000DD77
0x18000dd63  call    cs:__imp_GetProcessHeap
0x18000dd69  mov     r8, rbx; lpMem
0x18000dd6c  xor     edx, edx; dwFlags
0x18000dd6e  mov     rcx, rax; hHeap
0x18000dd71  call    cs:__imp_HeapFree
0x18000dd77  mov     rbx, [rsp+58h+arg_10]
0x18000dd7c  test    rbx, rbx
0x18000dd7f  jnz     short loc_18000DD8D
0x18000dd81  mov     edi, 8007000Eh
0x18000dd86  mov     edx, 77Bh
0x18000dd8b  jmp     short loc_18000DDBF
0x18000dd8d  mov     rax, [rdi]
0x18000dd90  lea     rdx, [r14+1]; unsigned __int64
0x18000dd94  mov     [rsp+58h+var_28], rax; char *
0x18000dd99  xor     r9d, r9d; unsigned __int64 *
0x18000dd9c  mov     [rsp+58h+ArgList], rbp; wchar_t *
0x18000dda1  xor     r8d, r8d; wchar_t **
0x18000dda4  mov     rcx, rbx; wchar_t *
0x18000dda7  mov     dword ptr [rsp+58h+Locale], 800h; int
0x18000ddaf  call    ?StringCchVPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WPEAD@Z; StringCchVPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,char *)
0x18000ddb4  mov     edi, eax
0x18000ddb6  test    eax, eax
0x18000ddb8  jns     short loc_18000DDD5
0x18000ddba  mov     edx, 77Fh; void *
0x18000ddbf  mov     rcx, [rsp+58h]; this
0x18000ddc4  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000ddcb  mov     r9d, edi; char *
0x18000ddce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ddd3  jmp     short loc_18000DE09
0x18000ddd5  mov     [rsp+58h+arg_10], rbx
0x18000ddda  lea     rdx, [rsp+58h+arg_10]
0x18000dddf  mov     rcx, rsi
0x18000dde2  xor     ebx, ebx
0x18000dde4  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x18000dde9  mov     rdi, [rsp+58h+arg_10]
0x18000ddee  test    rdi, rdi
0x18000ddf1  jz      short loc_18000DE07
0x18000ddf3  call    cs:__imp_GetProcessHeap
0x18000ddf9  mov     r8, rdi; lpMem
0x18000ddfc  xor     edx, edx; dwFlags
0x18000ddfe  mov     rcx, rax; hHeap
0x18000de01  call    cs:__imp_HeapFree
0x18000de07  xor     edi, edi
0x18000de09  test    rbx, rbx
0x18000de0c  jz      short loc_18000DE22
0x18000de0e  call    cs:__imp_GetProcessHeap
0x18000de14  mov     r8, rbx; lpMem
0x18000de17  xor     edx, edx; dwFlags
0x18000de19  mov     rcx, rax; hHeap
0x18000de1c  call    cs:__imp_HeapFree
0x18000de22  mov     rbx, [rsp+58h+arg_0]
0x18000de27  mov     eax, edi
0x18000de29  mov     rbp, [rsp+58h+arg_8]
0x18000de2e  add     rsp, 40h
0x18000de32  pop     r14
0x18000de34  pop     rdi
0x18000de35  pop     rsi
0x18000de36  retn
```
