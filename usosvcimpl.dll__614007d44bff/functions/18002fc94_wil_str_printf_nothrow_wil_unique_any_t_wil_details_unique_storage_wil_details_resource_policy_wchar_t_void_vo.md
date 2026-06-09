# wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wchar_t const *,...)

- ea: `0x18002fc94`
- end: `0x18002fe4b`
- name: `??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_WZZ`
- size: `439`
- prototype: `__int64(__int64, const wchar_t *, ...)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002f000`
- `0x180030c78`
- `0x180064ed4`

## callees

- `0x1800074a8`
- `0x180008e64`
- `0x18002fc94`
- `0x18002feb0`
- `0x18002ff28`
- `0x1800dd4f2`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fdcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fe25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fdcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fe25`

## string_xrefs

- `0x18002fd26`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x18002fe09`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
        __int64 a1,
        const wchar_t *a2,
        ...)
{
  unsigned __int64 *v4; // r12
  int v5; // eax
  size_t v6; // rsi
  int v7; // eax
  unsigned int v8; // edi
  wchar_t *v9; // rcx
  wchar_t *v10; // rbx
  unsigned __int64 v11; // rbp
  int v12; // eax
  int Locale; // [rsp+20h] [rbp-68h]
  wchar_t *Buffer; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  va_list va; // [rsp+A0h] [rbp+18h] BYREF

  va_start(va, a2);
  Buffer = 0;
  v4 = _local_stdio_printf_options();
  v5 = o___stdio_common_vswprintf_0(*v4 | 2, 0, 0, a2, 0, va);
  Buffer = 0;
  if ( v5 < 0 )
    v5 = -1;
  v6 = v5;
  v7 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(
         &Buffer,
         0,
         v5);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x77B,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v7,
      Locale);
    v9 = Buffer;
    if ( Buffer )
      goto LABEL_23;
    return v8;
  }
  v10 = Buffer;
  v11 = v6 + 1;
  if ( v6 == -1 || v11 > 0x7FFFFFFF )
  {
    v8 = -2147024809;
    if ( v6 == -1 )
      goto LABEL_21;
  }
  else
  {
    v12 = o___stdio_common_vswprintf_0(*v4 | 1, Buffer, v6, a2, 0, va);
    if ( v12 < 0 )
      v12 = -1;
    if ( v12 >= 0 && v12 <= v6 )
    {
      if ( v12 == v6 )
        v10[v6] = 0;
      Buffer = v10;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
        a1,
        &Buffer);
      if ( Buffer )
        CoTaskMemFree(Buffer);
      return 0;
    }
    v10[v6] = 0;
    v8 = -2147024774;
    if ( (v11 & 0x7FFFFFFFFFFFFFFFLL) == 0 )
      goto LABEL_21;
  }
  *v10 = 0;
LABEL_21:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x77F,
    (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
    (const char *)v8,
    Locale);
  if ( v10 )
  {
    v9 = v10;
LABEL_23:
    CoTaskMemFree(v9);
  }
  return v8;
}

```

## disassembly

```asm
0x18002fc94  mov     r11, rsp
0x18002fc97  mov     [r11+10h], rdx
0x18002fc9b  mov     [r11+18h], r8
0x18002fc9f  mov     [r11+20h], r9
0x18002fca3  push    rbx
0x18002fca4  push    rbp
0x18002fca5  push    rsi
0x18002fca6  push    rdi
0x18002fca7  push    r12
0x18002fca9  push    r13
0x18002fcab  push    r14
0x18002fcad  push    r15
0x18002fcaf  sub     rsp, 48h
0x18002fcb3  mov     rax, cs:__security_cookie
0x18002fcba  xor     rax, rsp
0x18002fcbd  mov     [rsp+88h+var_50], rax
0x18002fcc2  xor     r13d, r13d
0x18002fcc5  lea     rbx, [r11+18h]
0x18002fcc9  mov     [r11-58h], r13
0x18002fccd  mov     r15, rdx
0x18002fcd0  mov     r14, rcx
0x18002fcd3  call    __local_stdio_printf_options
0x18002fcd8  mov     [rsp+88h+ArgList], rbx; ArgList
0x18002fcdd  mov     r9, r15; Format
0x18002fce0  xor     r8d, r8d; BufferCount
0x18002fce3  mov     [rsp+88h+Locale], r13; int
0x18002fce8  xor     edx, edx; Buffer
0x18002fcea  mov     r12, rax
0x18002fced  mov     rcx, [rax]
0x18002fcf0  or      rcx, 2; Options
0x18002fcf4  call    _o___stdio_common_vswprintf_0
0x18002fcf9  or      ecx, 0FFFFFFFFh
0x18002fcfc  mov     [rsp+88h+Buffer], r13
0x18002fd01  test    eax, eax
0x18002fd03  cmovs   eax, ecx
0x18002fd06  xor     edx, edx
0x18002fd08  movsxd  rsi, eax
0x18002fd0b  lea     rcx, [rsp+88h+Buffer]
0x18002fd10  mov     r8, rsi
0x18002fd13  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x18002fd18  mov     edi, eax
0x18002fd1a  test    eax, eax
0x18002fd1c  jns     short loc_18002FD4D
0x18002fd1e  mov     rcx, [rsp+88h]; this
0x18002fd26  lea     r8, aCW1SPackagesMi_4; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18002fd2d  mov     r9d, eax; char *
0x18002fd30  mov     edx, 77Bh; void *
0x18002fd35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fd3a  mov     rcx, [rsp+88h+Buffer]
0x18002fd3f  test    rcx, rcx
0x18002fd42  jz      loc_18002FE2B
0x18002fd48  jmp     loc_18002FE25
0x18002fd4d  mov     rbx, [rsp+88h+Buffer]
0x18002fd52  lea     rbp, [rsi+1]
0x18002fd56  test    rbp, rbp
0x18002fd59  jz      loc_18002FDF3
0x18002fd5f  cmp     rbp, 7FFFFFFFh
0x18002fd66  ja      loc_18002FDF3
0x18002fd6c  mov     rcx, [r12]
0x18002fd70  lea     rax, [rsp+88h+arg_10]
0x18002fd78  mov     [rsp+88h+ArgList], rax; ArgList
0x18002fd7d  or      rcx, 1; Options
0x18002fd81  mov     r9, r15; Format
0x18002fd84  mov     [rsp+88h+Locale], r13; Locale
0x18002fd89  mov     r8, rsi; BufferCount
0x18002fd8c  mov     rdx, rbx; Buffer
0x18002fd8f  call    _o___stdio_common_vswprintf_0
0x18002fd94  test    eax, eax
0x18002fd96  mov     ecx, 0FFFFFFFFh
0x18002fd9b  cmovs   eax, ecx
0x18002fd9e  test    eax, eax
0x18002fda0  js      short loc_18002FDD8
0x18002fda2  movsxd  rdx, eax
0x18002fda5  cmp     rdx, rsi
0x18002fda8  ja      short loc_18002FDD8
0x18002fdaa  jnz     short loc_18002FDB1
0x18002fdac  mov     [rbx+rsi*2], r13w
0x18002fdb1  lea     rdx, [rsp+88h+Buffer]
0x18002fdb6  mov     [rsp+88h+Buffer], rbx
0x18002fdbb  mov     rcx, r14
0x18002fdbe  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x18002fdc3  mov     rcx, [rsp+88h+Buffer]; pv
0x18002fdc8  test    rcx, rcx
0x18002fdcb  jz      short loc_18002FDD3
0x18002fdcd  call    cs:__imp_CoTaskMemFree
0x18002fdd3  mov     edi, r13d
0x18002fdd6  jmp     short loc_18002FE2B
0x18002fdd8  mov     rax, 7FFFFFFFFFFFFFFFh
0x18002fde2  mov     [rbx+rsi*2], r13w
0x18002fde7  mov     edi, 8007007Ah
0x18002fdec  test    rax, rbp
0x18002fdef  jbe     short loc_18002FE01
0x18002fdf1  jmp     short loc_18002FDFD
0x18002fdf3  mov     edi, 80070057h
0x18002fdf8  test    rbp, rbp
0x18002fdfb  jz      short loc_18002FE01
0x18002fdfd  mov     [rbx], r13w
0x18002fe01  mov     rcx, [rsp+88h]; this
0x18002fe09  lea     r8, aCW1SPackagesMi_4; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18002fe10  mov     r9d, edi; char *
0x18002fe13  mov     edx, 77Fh; void *
0x18002fe18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fe1d  test    rbx, rbx
0x18002fe20  jz      short loc_18002FE2B
0x18002fe22  mov     rcx, rbx; pv
0x18002fe25  call    cs:__imp_CoTaskMemFree
0x18002fe2b  mov     eax, edi
0x18002fe2d  mov     rcx, [rsp+88h+var_50]
0x18002fe32  xor     rcx, rsp; StackCookie
0x18002fe35  call    __security_check_cookie
0x18002fe3a  add     rsp, 48h
0x18002fe3e  pop     r15
0x18002fe40  pop     r14
0x18002fe42  pop     r13
0x18002fe44  pop     r12
0x18002fe46  pop     rdi
0x18002fe47  pop     rsi
0x18002fe48  pop     rbp
0x18002fe49  pop     rbx
0x18002fe4a  retn
```
