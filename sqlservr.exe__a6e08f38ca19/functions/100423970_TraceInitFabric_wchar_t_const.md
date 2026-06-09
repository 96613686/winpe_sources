# TraceInitFabric(wchar_t const *,...)

- ea: `0x100423970`
- end: `0x100423a59`
- name: `?TraceInitFabric@@YAXPEB_WZZ`
- size: `233`
- prototype: `void(const wchar_t *, ...)`
- caller_count: `9`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x100416770`
- `0x10041a620`
- `0x100423a60`
- `0x100424800`
- `0x100424c50`
- `0x100425030`
- `0x100428eb0`
- `0x100434d10`
- `0x100434d40`

## callees

- `0x100401580`
- `0x100401b60`
- `0x100402ec0`
- `0x100423970`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vfwprintf` at `0x1004239d9`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vfwprintf` at `0x1004239d9`
- `api-ms-win-crt-stdio-l1-1-0!fflush` at `0x100423a37`
- `api-ms-win-crt-stdio-l1-1-0!fflush` at `0x100423a37`
- `api-ms-win-crt-stdio-l1-1-0!__acrt_iob_func` at `0x1004239b7`
- `api-ms-win-crt-stdio-l1-1-0!__acrt_iob_func` at `0x100423a2e`
- `api-ms-win-crt-stdio-l1-1-0!__acrt_iob_func` at `0x1004239b7`
- `api-ms-win-crt-stdio-l1-1-0!__acrt_iob_func` at `0x100423a2e`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x100423a13`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x100423a13`
- `RgThinClient!RgClient_WriteETWTrace` at `0x100423a23`
- `RgThinClient!RgClient_WriteETWTrace` at `0x100423a23`

## pseudocode

```c
void TraceInitFabric(const wchar_t *a1, ...)
{
  FILE *v2; // rbx
  unsigned __int64 *v3; // rsi
  __int64 v4; // rdx
  FILE *v5; // rax
  wchar_t Buffer[2048]; // [rsp+30h] [rbp-1038h] BYREF
  va_list va; // [rsp+1078h] [rbp+10h] BYREF

  va_start(va, a1);
  v2 = __acrt_iob_func(1u);
  v3 = _local_stdio_printf_options();
  __stdio_common_vfwprintf(*v3, v2, a1, 0, va);
  if ( *((_DWORD *)qword_10049F360 + 3626) )
  {
    __stdio_common_vswprintf(*v3, Buffer, 0x800u, a1, 0, va);
    LOBYTE(v4) = 4;
    RgClient_WriteETWTrace(Buffer, v4, 0);
  }
  v5 = __acrt_iob_func(1u);
  fflush(v5);
}

```

## disassembly

```asm
0x100423970  mov     [rsp+Format], rcx
0x100423975  mov     qword ptr [rsp+arg_8], rdx
0x10042397a  mov     [rsp+arg_10], r8
0x10042397f  mov     [rsp+arg_18], r9
0x100423984  push    rbx
0x100423985  push    rbp
0x100423986  push    rsi
0x100423987  push    rdi
0x100423988  mov     eax, 1048h
0x10042398d  call    _alloca_probe
0x100423992  sub     rsp, rax
0x100423995  mov     rax, cs:__security_cookie
0x10042399c  xor     rax, rsp
0x10042399f  mov     [rsp+1068h+var_38], rax
0x1004239a7  mov     rdi, rcx
0x1004239aa  lea     rbp, [rsp+1068h+arg_8]
0x1004239b2  mov     ecx, 1; Ix
0x1004239b7  call    cs:__imp___acrt_iob_func
0x1004239bd  mov     rbx, rax
0x1004239c0  call    __local_stdio_printf_options
0x1004239c5  xor     r9d, r9d; Locale
0x1004239c8  mov     [rsp+1068h+ArgList], rbp; ArgList
0x1004239cd  mov     r8, rdi; Format
0x1004239d0  mov     rdx, rbx; Stream
0x1004239d3  mov     rsi, rax
0x1004239d6  mov     rcx, [rax]; Options
0x1004239d9  call    cs:__imp___stdio_common_vfwprintf
0x1004239df  mov     rcx, cs:qword_10049F360
0x1004239e6  cmp     dword ptr [rcx+38A8h], 0
0x1004239ed  jz      short loc_100423A29
0x1004239ef  mov     r9, [rsp+1068h+Format]; Format
0x1004239f7  lea     rdx, [rsp+1068h+Buffer]; Buffer
0x1004239fc  mov     rcx, [rsi]; Options
0x1004239ff  mov     r8d, 800h; BufferCount
0x100423a05  mov     [rsp+1068h+var_1040], rbp; ArgList
0x100423a0a  mov     [rsp+1068h+ArgList], 0; Locale
0x100423a13  call    cs:__imp___stdio_common_vswprintf
0x100423a19  xor     r8d, r8d
0x100423a1c  lea     rcx, [rsp+1068h+Buffer]
0x100423a21  mov     dl, 4
0x100423a23  call    cs:__imp_RgClient_WriteETWTrace
0x100423a29  mov     ecx, 1; Ix
0x100423a2e  call    cs:__imp___acrt_iob_func
0x100423a34  mov     rcx, rax; Stream
0x100423a37  call    cs:__imp_fflush
0x100423a3d  mov     rcx, [rsp+1068h+var_38]
0x100423a45  xor     rcx, rsp; StackCookie
0x100423a48  call    __security_check_cookie
0x100423a4d  add     rsp, 1048h
0x100423a54  pop     rdi
0x100423a55  pop     rsi
0x100423a56  pop     rbp
0x100423a57  pop     rbx
0x100423a58  retn
```
