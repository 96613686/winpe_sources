# utility::details::scoped_c_thread_locale::c_locale(void)

- ea: `0x180031b14`
- end: `0x180031c25`
- name: `?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ`
- size: `273`
- prototype: `struct __crt_locale_pointers *(void)`
- caller_count: `6`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18002ceb0`
- `0x18002d040`
- `0x18002eeb0`
- `0x18002f1a4`
- `0x18002f95c`
- `0x18002fcb4`

## callees

- `0x180029344`
- `0x180031b14`
- `0x180041cb0`
- `0x1800424c2`
- `0x180042640`
- `0x1800427d0`
- `0x180042bfc`
- `0x180044848`
- `0x180047a30`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180031bca`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180031bca`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180031b49`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180031b49`

## string_xrefs

- `0x180031c02`: `Unable to create 'C' locale.`

## pseudocode

```c
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
    v3 = qword_1800622C8;
    qword_1800622C8 = (__int64)v0;
    if ( v3 )
      ((void (__fastcall *)(__int64, __int64))utility::details::g_c_locale)(v3, v2);
    utility::details::g_c_locale = (__int64 (__fastcall *)())lambda_41ecd71de5d8b60bfbea6452d600c7b3_::_lambda_invoker_cdecl_;
    if ( !InitOnceComplete(&utility::details::g_c_localeFlag, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v5, v4);
  }
  return *(struct __crt_locale_pointers **)qword_1800622C8;
}

```

## disassembly

```asm
0x180031b14  mov     [rsp+arg_0], rbx
0x180031b19  push    rdi
0x180031b1a  sub     rsp, 60h
0x180031b1e  mov     rax, cs:__security_cookie
0x180031b25  xor     rax, rsp
0x180031b28  mov     [rsp+68h+var_18], rax
0x180031b2d  mov     [rsp+68h+fPending], 0
0x180031b35  xor     r9d, r9d; lpContext
0x180031b38  lea     r8, [rsp+68h+fPending]; fPending
0x180031b3d  xor     edx, edx; dwFlags
0x180031b3f  lea     rdi, ?g_c_localeFlag@details@utility@@3Uonce_flag@std@@A; std::once_flag utility::details::g_c_localeFlag
0x180031b46  mov     rcx, rdi; lpInitOnce
0x180031b49  call    cs:__imp___std_init_once_begin_initialize
0x180031b4f  test    eax, eax
0x180031b51  jz      loc_180031BFC
0x180031b57  cmp     [rsp+68h+fPending], 0
0x180031b5c  jz      short loc_180031BD4
0x180031b5e  mov     [rsp+68h+var_48], rdi
0x180031b63  mov     [rsp+68h+var_40], 4
0x180031b6c  mov     ecx, 8; Size
0x180031b71  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031b76  mov     rbx, rax
0x180031b79  xor     eax, eax
0x180031b7b  mov     [rbx], rax
0x180031b7e  lea     rdx, Locale; "C"
0x180031b85  xor     ecx, ecx; Category
0x180031b87  call    _create_locale
0x180031b8c  mov     [rbx], rax
0x180031b8f  test    rax, rax
0x180031b92  jz      short loc_180031C02
0x180031b94  mov     rcx, cs:qword_1800622C8
0x180031b9b  mov     cs:qword_1800622C8, rbx
0x180031ba2  test    rcx, rcx
0x180031ba5  jz      short loc_180031BB4
0x180031ba7  mov     rax, cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x180031bae  call    _guard_dispatch_icall
0x180031bb3  nop
0x180031bb4  lea     rax, _lambda_41ecd71de5d8b60bfbea6452d600c7b3____lambda_invoker_cdecl_
0x180031bbb  mov     cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A, rax; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x180031bc2  xor     r8d, r8d; lpContext
0x180031bc5  xor     edx, edx; dwFlags
0x180031bc7  mov     rcx, rdi; lpInitOnce
0x180031bca  call    cs:__imp_InitOnceComplete
0x180031bd0  test    eax, eax
0x180031bd2  jz      short loc_180031BF6
0x180031bd4  mov     rax, cs:qword_1800622C8
0x180031bdb  mov     rax, [rax]
0x180031bde  mov     rcx, [rsp+68h+var_18]
0x180031be3  xor     rcx, rsp; StackCookie
0x180031be6  call    __security_check_cookie
0x180031beb  mov     rbx, [rsp+68h+arg_0]
0x180031bf0  add     rsp, 60h
0x180031bf4  pop     rdi
0x180031bf5  retn
0x180031bf6  call    __std_init_once_link_alternate_names_and_abort
0x180031bfc  call    abort
0x180031c02  lea     rdx, aUnableToCreate; "Unable to create 'C' locale."
0x180031c09  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180031c0e  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180031c13  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180031c1a  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180031c1f  call    _CxxThrowException
```
