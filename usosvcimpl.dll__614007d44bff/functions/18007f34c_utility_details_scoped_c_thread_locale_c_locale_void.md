# utility::details::scoped_c_thread_locale::c_locale(void)

- ea: `0x18007f34c`
- end: `0x18007f45d`
- name: `?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ`
- size: `273`
- prototype: `struct __crt_locale_pointers *(void)`
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18007b434`
- `0x18007b728`
- `0x18007e640`
- `0x18007e7d0`

## callees

- `0x18002dd34`
- `0x180043f2c`
- `0x18007f34c`
- `0x1800dd546`
- `0x1800dd768`
- `0x1800dd930`
- `0x1800de12c`
- `0x1800dff58`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18007f381`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18007f381`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18007f402`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18007f402`

## string_xrefs

- `0x18007f43a`: `Unable to create 'C' locale.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct __crt_locale_pointers *utility::details::scoped_c_thread_locale::c_locale(void)
{
  _locale_t *v0; // rbx
  _locale_t locale; // rax
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // rcx
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-38h] BYREF
  WINBOOL fPending; // [rsp+48h] [rbp-20h] BYREF

  fPending = 0;
  if ( !__std_init_once_begin_initialize(&utility::details::g_c_localeFlag, 0, &fPending, 0) )
    abort();
  if ( fPending )
  {
    v0 = (_locale_t *)operator new(8u);
    *v0 = 0;
    locale = create_locale(0, "C");
    *v0 = locale;
    if ( !locale )
    {
      std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "Unable to create 'C' locale.");
      throw (std::runtime_error *)pExceptionObject;
    }
    v3 = qword_18014D588;
    qword_18014D588 = (__int64)v0;
    if ( v3 )
      ((void (__fastcall *)(__int64, __int64))utility::details::g_c_locale)(v3, v2);
    utility::details::g_c_locale = (__int64 (__fastcall *)())lambda_41ecd71de5d8b60bfbea6452d600c7b3_::_lambda_invoker_cdecl_;
    if ( !InitOnceComplete(&utility::details::g_c_localeFlag, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v5, v4);
  }
  return *(struct __crt_locale_pointers **)qword_18014D588;
}

```

## disassembly

```asm
0x18007f34c  mov     [rsp+arg_0], rbx
0x18007f351  push    rdi
0x18007f352  sub     rsp, 60h
0x18007f356  mov     rax, cs:__security_cookie
0x18007f35d  xor     rax, rsp
0x18007f360  mov     [rsp+68h+var_18], rax
0x18007f365  mov     [rsp+68h+fPending], 0
0x18007f36d  xor     r9d, r9d; lpContext
0x18007f370  lea     r8, [rsp+68h+fPending]; fPending
0x18007f375  xor     edx, edx; dwFlags
0x18007f377  lea     rdi, ?g_c_localeFlag@details@utility@@3Uonce_flag@std@@A; std::once_flag utility::details::g_c_localeFlag
0x18007f37e  mov     rcx, rdi; lpInitOnce
0x18007f381  call    cs:__imp___std_init_once_begin_initialize
0x18007f387  test    eax, eax
0x18007f389  jz      loc_18007F434
0x18007f38f  cmp     [rsp+68h+fPending], 0
0x18007f394  jz      short loc_18007F40C
0x18007f396  mov     [rsp+68h+var_48], rdi
0x18007f39b  mov     [rsp+68h+var_40], 4
0x18007f3a4  mov     ecx, 8; Size
0x18007f3a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007f3ae  mov     rbx, rax
0x18007f3b1  xor     eax, eax
0x18007f3b3  mov     [rbx], rax
0x18007f3b6  lea     rdx, Locale; "C"
0x18007f3bd  xor     ecx, ecx; Category
0x18007f3bf  call    _create_locale
0x18007f3c4  mov     [rbx], rax
0x18007f3c7  test    rax, rax
0x18007f3ca  jz      short loc_18007F43A
0x18007f3cc  mov     rcx, cs:qword_18014D588
0x18007f3d3  mov     cs:qword_18014D588, rbx
0x18007f3da  test    rcx, rcx
0x18007f3dd  jz      short loc_18007F3EC
0x18007f3df  mov     rax, cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x18007f3e6  call    _guard_dispatch_icall
0x18007f3eb  nop
0x18007f3ec  lea     rax, _lambda_41ecd71de5d8b60bfbea6452d600c7b3____lambda_invoker_cdecl_
0x18007f3f3  mov     cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A, rax; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x18007f3fa  xor     r8d, r8d; lpContext
0x18007f3fd  xor     edx, edx; dwFlags
0x18007f3ff  mov     rcx, rdi; lpInitOnce
0x18007f402  call    cs:__imp_InitOnceComplete
0x18007f408  test    eax, eax
0x18007f40a  jz      short loc_18007F42E
0x18007f40c  mov     rax, cs:qword_18014D588
0x18007f413  mov     rax, [rax]
0x18007f416  mov     rcx, [rsp+68h+var_18]
0x18007f41b  xor     rcx, rsp; StackCookie
0x18007f41e  call    __security_check_cookie
0x18007f423  mov     rbx, [rsp+68h+arg_0]
0x18007f428  add     rsp, 60h
0x18007f42c  pop     rdi
0x18007f42d  retn
0x18007f42e  call    __std_init_once_link_alternate_names_and_abort
0x18007f434  call    abort
0x18007f43a  lea     rdx, aUnableToCreate; "Unable to create 'C' locale."
0x18007f441  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18007f446  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18007f44b  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18007f452  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18007f457  call    _CxxThrowException
```
