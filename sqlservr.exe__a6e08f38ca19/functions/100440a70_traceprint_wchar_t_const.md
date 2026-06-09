# traceprint(wchar_t const *,...)

- ea: `0x100440a70`
- end: `0x100440b3e`
- name: `?traceprint@@YAXPEB_WZZ`
- size: `206`
- prototype: `void(const wchar_t *, ...)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x100411730`
- `0x100416770`
- `0x10041a620`
- `0x100422620`

## callees

- `0x100401580`
- `0x100401b60`
- `0x100402ec0`

## import_xrefs

- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100440aad`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100440aad`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x100440b06`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x100440b06`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x100440adf`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x100440adf`

## pseudocode

```c
void traceprint(const wchar_t *a1, ...)
{
  __crt_locale_pointers *Locale; // rbx
  unsigned __int64 *v2; // rax
  int v3; // ebx
  struct IErrorReportingManager *ErrorReportingManager; // rax
  __int64 v5; // r9
  wchar_t Buffer[2056]; // [rsp+30h] [rbp-1038h] BYREF
  va_list va; // [rsp+1078h] [rbp+10h] BYREF

  va_start(va, a1);
  Locale = GetDefaultLocale();
  v2 = _local_stdio_printf_options();
  v3 = __stdio_common_vswprintf(*v2 | 1, Buffer, 0x801u, a1, Locale, va);
  if ( v3 < 0 )
    v3 = -1;
  Buffer[2048] = 0;
  if ( v3 == -1 )
    v3 = 2048;
  ErrorReportingManager = GetErrorReportingManager();
  LOBYTE(v5) = 1;
  (*(void (__fastcall **)(struct IErrorReportingManager *, wchar_t *, _QWORD, __int64))(*(_QWORD *)ErrorReportingManager
                                                                                      + 160LL))(
    ErrorReportingManager,
    Buffer,
    (unsigned int)v3,
    v5);
}

```

## disassembly

```asm
0x100440a70  mov     [rsp+Format], rcx
0x100440a75  mov     qword ptr [rsp+arg_8], rdx
0x100440a7a  mov     [rsp+arg_10], r8
0x100440a7f  mov     [rsp+arg_18], r9
0x100440a84  push    rbx
0x100440a85  push    rdi
0x100440a86  mov     eax, 1058h
0x100440a8b  call    _alloca_probe
0x100440a90  sub     rsp, rax
0x100440a93  mov     rax, cs:__security_cookie
0x100440a9a  xor     rax, rsp
0x100440a9d  mov     [rsp+1068h+var_28], rax
0x100440aa5  lea     rdi, [rsp+1068h+arg_8]
0x100440aad  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100440ab3  mov     rbx, rax
0x100440ab6  call    __local_stdio_printf_options
0x100440abb  mov     r9, [rsp+1068h+Format]; Format
0x100440ac3  lea     rdx, [rsp+1068h+Buffer]; Buffer
0x100440ac8  mov     [rsp+1068h+ArgList], rdi; ArgList
0x100440acd  mov     r8d, 801h; BufferCount
0x100440ad3  mov     [rsp+1068h+Locale], rbx; Locale
0x100440ad8  mov     rcx, [rax]
0x100440adb  or      rcx, 1; Options
0x100440adf  call    cs:__imp___stdio_common_vswprintf
0x100440ae5  mov     ebx, eax
0x100440ae7  mov     eax, 0FFFFFFFFh
0x100440aec  test    ebx, ebx
0x100440aee  cmovs   ebx, eax
0x100440af1  xor     eax, eax
0x100440af3  mov     [rsp+1068h+var_38], ax
0x100440afb  cmp     ebx, 0FFFFFFFFh
0x100440afe  mov     eax, 800h
0x100440b03  cmovz   ebx, eax
0x100440b06  call    cs:__imp_?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ; GetErrorReportingManager(void)
0x100440b0c  mov     r9b, 1
0x100440b0f  lea     rdx, [rsp+1068h+Buffer]
0x100440b14  mov     r8d, ebx
0x100440b17  mov     rcx, rax
0x100440b1a  mov     r10, [rax]
0x100440b1d  call    qword ptr [r10+0A0h]
0x100440b24  mov     rcx, [rsp+1068h+var_28]
0x100440b2c  xor     rcx, rsp; StackCookie
0x100440b2f  call    __security_check_cookie
0x100440b34  add     rsp, 1058h
0x100440b3b  pop     rdi
0x100440b3c  pop     rbx
0x100440b3d  retn
```
