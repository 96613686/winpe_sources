# LogSystemMetadata(wchar_t const *,...)

- ea: `0x100440760`
- end: `0x10044084b`
- name: `?LogSystemMetadata@@YAXPEB_WZZ`
- size: `235`
- prototype: `void(const wchar_t *, ...)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x100411910`
- `0x1004119c0`
- `0x100415f50`
- `0x100416770`
- `0x1004187d0`

## callees

- `0x100401580`
- `0x100401b60`
- `0x100402ec0`
- `0x100440760`

## import_xrefs

- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10044079d`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10044079d`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1004407f6`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1004407f6`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x1004407cf`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x1004407cf`

## pseudocode

```c
void LogSystemMetadata(const wchar_t *a1, ...)
{
  __crt_locale_pointers *Locale; // rbx
  unsigned __int64 *v2; // rax
  int v3; // eax
  struct IErrorReportingManager *ErrorReportingManager; // rax
  __int64 v5; // r9
  __int64 v6; // r8
  wchar_t Buffer[2048]; // [rsp+30h] [rbp-1028h] BYREF
  __int64 ArgList; // [rsp+1068h] [rbp+10h] BYREF
  va_list va; // [rsp+1068h] [rbp+10h]
  __int64 v11; // [rsp+1070h] [rbp+18h]
  __int64 v12; // [rsp+1078h] [rbp+20h]
  va_list va1; // [rsp+1080h] [rbp+28h] BYREF

  va_start(va1, a1);
  va_start(va, a1);
  ArgList = va_arg(va1, _QWORD);
  v11 = va_arg(va1, _QWORD);
  v12 = va_arg(va1, _QWORD);
  Locale = GetDefaultLocale();
  v2 = _local_stdio_printf_options();
  v3 = __stdio_common_vswprintf(*v2 | 1, Buffer, 0x7FFu, a1, Locale, va);
  if ( v3 < 0 )
    v3 = -1;
  if ( (unsigned int)v3 > 0x7FE )
    Buffer[2047] = 0;
  ErrorReportingManager = GetErrorReportingManager();
  v6 = -1;
  do
    ++v6;
  while ( Buffer[v6] );
  LOBYTE(v5) = 1;
  (*(void (__fastcall **)(struct IErrorReportingManager *, wchar_t *, __int64, __int64, int))(*(_QWORD *)ErrorReportingManager
                                                                                            + 168LL))(
    ErrorReportingManager,
    Buffer,
    v6,
    v5,
    -1);
}

```

## disassembly

```asm
0x100440760  mov     [rsp+Format], rcx
0x100440765  mov     [rsp+arg_8], rdx
0x10044076a  mov     [rsp+arg_10], r8
0x10044076f  mov     [rsp+arg_18], r9
0x100440774  push    rbx
0x100440775  push    rdi
0x100440776  mov     eax, 1048h
0x10044077b  call    _alloca_probe
0x100440780  sub     rsp, rax
0x100440783  mov     rax, cs:__security_cookie
0x10044078a  xor     rax, rsp
0x10044078d  mov     [rsp+1058h+var_28], rax
0x100440795  lea     rdi, [rsp+1058h+arg_8]
0x10044079d  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x1004407a3  mov     rbx, rax
0x1004407a6  call    __local_stdio_printf_options
0x1004407ab  mov     r9, [rsp+1058h+Format]; Format
0x1004407b3  lea     rdx, [rsp+1058h+Buffer]; Buffer
0x1004407b8  mov     [rsp+1058h+ArgList], rdi; ArgList
0x1004407bd  mov     r8d, 7FFh; BufferCount
0x1004407c3  mov     [rsp+1058h+Locale], rbx; Locale
0x1004407c8  mov     rcx, [rax]
0x1004407cb  or      rcx, 1; Options
0x1004407cf  call    cs:__imp___stdio_common_vswprintf
0x1004407d5  test    eax, eax
0x1004407d7  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1004407de  cmovs   eax, ebx
0x1004407e1  test    eax, eax
0x1004407e3  js      short loc_1004407EC
0x1004407e5  cmp     eax, 7FFh
0x1004407ea  jb      short loc_1004407F6
0x1004407ec  xor     eax, eax
0x1004407ee  mov     [rsp+1058h+var_2A], ax
0x1004407f6  call    cs:__imp_?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ; GetErrorReportingManager(void)
0x1004407fc  lea     rcx, [rsp+1058h+Buffer]
0x100440801  mov     r8, rbx
0x100440804  mov     r10, [rax]
0x100440807  nop     word ptr [rax+rax+00000000h]
0x100440810  inc     r8
0x100440813  cmp     word ptr [rcx+r8*2], 0
0x100440819  jnz     short loc_100440810
0x10044081b  mov     r9b, 1
0x10044081e  mov     dword ptr [rsp+1058h+Locale], ebx
0x100440822  lea     rdx, [rsp+1058h+Buffer]
0x100440827  mov     rcx, rax
0x10044082a  call    qword ptr [r10+0A8h]
0x100440831  mov     rcx, [rsp+1058h+var_28]
0x100440839  xor     rcx, rsp; StackCookie
0x10044083c  call    __security_check_cookie
0x100440841  add     rsp, 1048h
0x100440848  pop     rdi
0x100440849  pop     rbx
0x10044084a  retn
```
