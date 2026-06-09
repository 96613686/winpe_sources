# traceprint(wchar_t const *,...)

- ea: `0x1004c7570`
- end: `0x1004c763e`
- name: `?traceprint@@YAXPEB_WZZ`
- size: `206`
- prototype: `void(const wchar_t *, ...)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x10043ef50`
- `0x10083c790`

## callees

- `0x100401170`
- `0x1004024b0`
- `0x10041db30`

## import_xrefs

- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1004c7606`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1004c7606`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1004c75ad`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1004c75ad`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x1004c75df`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x1004c75df`

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
0x1004c7570  mov     [rsp+Format], rcx
0x1004c7575  mov     qword ptr [rsp+arg_8], rdx
0x1004c757a  mov     [rsp+arg_10], r8
0x1004c757f  mov     [rsp+arg_18], r9
0x1004c7584  push    rbx
0x1004c7585  push    rdi
0x1004c7586  mov     eax, 1058h
0x1004c758b  call    _alloca_probe
0x1004c7590  sub     rsp, rax
0x1004c7593  mov     rax, cs:__security_cookie
0x1004c759a  xor     rax, rsp
0x1004c759d  mov     [rsp+1068h+var_28], rax
0x1004c75a5  lea     rdi, [rsp+1068h+arg_8]
0x1004c75ad  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x1004c75b3  mov     rbx, rax
0x1004c75b6  call    __local_stdio_printf_options
0x1004c75bb  mov     r9, [rsp+1068h+Format]; Format
0x1004c75c3  lea     rdx, [rsp+1068h+Buffer]; Buffer
0x1004c75c8  mov     [rsp+1068h+ArgList], rdi; ArgList
0x1004c75cd  mov     r8d, 801h; BufferCount
0x1004c75d3  mov     [rsp+1068h+Locale], rbx; Locale
0x1004c75d8  mov     rcx, [rax]
0x1004c75db  or      rcx, 1; Options
0x1004c75df  call    cs:__imp___stdio_common_vswprintf
0x1004c75e5  mov     ebx, eax
0x1004c75e7  mov     eax, 0FFFFFFFFh
0x1004c75ec  test    ebx, ebx
0x1004c75ee  cmovs   ebx, eax
0x1004c75f1  xor     eax, eax
0x1004c75f3  mov     [rsp+1068h+var_38], ax
0x1004c75fb  cmp     ebx, 0FFFFFFFFh
0x1004c75fe  mov     eax, 800h
0x1004c7603  cmovz   ebx, eax
0x1004c7606  call    cs:__imp_?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ; GetErrorReportingManager(void)
0x1004c760c  mov     r9b, 1
0x1004c760f  lea     rdx, [rsp+1068h+Buffer]
0x1004c7614  mov     r8d, ebx
0x1004c7617  mov     rcx, rax
0x1004c761a  mov     r10, [rax]
0x1004c761d  call    qword ptr [r10+0A0h]
0x1004c7624  mov     rcx, [rsp+1068h+var_28]
0x1004c762c  xor     rcx, rsp; StackCookie
0x1004c762f  call    __security_check_cookie
0x1004c7634  add     rsp, 1058h
0x1004c763b  pop     rdi
0x1004c763c  pop     rbx
0x1004c763d  retn
```
