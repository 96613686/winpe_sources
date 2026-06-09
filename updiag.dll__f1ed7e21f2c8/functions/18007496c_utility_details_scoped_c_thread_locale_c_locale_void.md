# utility::details::scoped_c_thread_locale::c_locale(void)

- ea: `0x18007496c`
- end: `0x180074a7d`
- name: `?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ`
- size: `273`
- prototype: `struct __crt_locale_pointers *(void)`
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18006f590`
- `0x18006f884`
- `0x180073c60`
- `0x180073df0`

## callees

- `0x18006932c`
- `0x18007496c`
- `0x18007e220`
- `0x18008fa77`
- `0x18008fc40`
- `0x18008fe00`
- `0x1800957dc`
- `0x180095af0`
- `0x180096170`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180074a22`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180074a22`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800749a1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800749a1`

## string_xrefs

- `0x180074a5a`: `Unable to create 'C' locale.`

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
  BOOL fPending; // [rsp+48h] [rbp-20h] BYREF

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
    v3 = qword_1801825E0;
    qword_1801825E0 = (__int64)v0;
    if ( v3 )
      ((void (__fastcall *)(__int64, __int64))utility::details::g_c_locale)(v3, v2);
    utility::details::g_c_locale = (__int64 (__fastcall *)())lambda_41ecd71de5d8b60bfbea6452d600c7b3_::_lambda_invoker_cdecl_;
    if ( !InitOnceComplete(&utility::details::g_c_localeFlag, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v5, v4);
  }
  return *(struct __crt_locale_pointers **)qword_1801825E0;
}

```

## disassembly

```asm
0x18007496c  mov     [rsp+arg_0], rbx
0x180074971  push    rdi
0x180074972  sub     rsp, 60h
0x180074976  mov     rax, cs:__security_cookie
0x18007497d  xor     rax, rsp
0x180074980  mov     [rsp+68h+var_18], rax
0x180074985  mov     [rsp+68h+fPending], 0
0x18007498d  xor     r9d, r9d; lpContext
0x180074990  lea     r8, [rsp+68h+fPending]; fPending
0x180074995  xor     edx, edx; dwFlags
0x180074997  lea     rdi, ?g_c_localeFlag@details@utility@@3Uonce_flag@std@@A; std::once_flag utility::details::g_c_localeFlag
0x18007499e  mov     rcx, rdi; lpInitOnce
0x1800749a1  call    cs:__imp___std_init_once_begin_initialize
0x1800749a7  test    eax, eax
0x1800749a9  jz      loc_180074A54
0x1800749af  cmp     [rsp+68h+fPending], 0
0x1800749b4  jz      short loc_180074A2C
0x1800749b6  mov     [rsp+68h+var_48], rdi
0x1800749bb  mov     [rsp+68h+var_40], 4
0x1800749c4  mov     ecx, 8; Size
0x1800749c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800749ce  mov     rbx, rax
0x1800749d1  xor     eax, eax
0x1800749d3  mov     [rbx], rax
0x1800749d6  lea     rdx, Locale; "C"
0x1800749dd  xor     ecx, ecx; Category
0x1800749df  call    _create_locale
0x1800749e4  mov     [rbx], rax
0x1800749e7  test    rax, rax
0x1800749ea  jz      short loc_180074A5A
0x1800749ec  mov     rcx, cs:qword_1801825E0
0x1800749f3  mov     cs:qword_1801825E0, rbx
0x1800749fa  test    rcx, rcx
0x1800749fd  jz      short loc_180074A0C
0x1800749ff  mov     rax, cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x180074a06  call    _guard_dispatch_icall
0x180074a0b  nop
0x180074a0c  lea     rax, _lambda_41ecd71de5d8b60bfbea6452d600c7b3____lambda_invoker_cdecl_
0x180074a13  mov     cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A, rax; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x180074a1a  xor     r8d, r8d; lpContext
0x180074a1d  xor     edx, edx; dwFlags
0x180074a1f  mov     rcx, rdi; lpInitOnce
0x180074a22  call    cs:__imp_InitOnceComplete
0x180074a28  test    eax, eax
0x180074a2a  jz      short loc_180074A4E
0x180074a2c  mov     rax, cs:qword_1801825E0
0x180074a33  mov     rax, [rax]
0x180074a36  mov     rcx, [rsp+68h+var_18]
0x180074a3b  xor     rcx, rsp; StackCookie
0x180074a3e  call    __security_check_cookie
0x180074a43  mov     rbx, [rsp+68h+arg_0]
0x180074a48  add     rsp, 60h
0x180074a4c  pop     rdi
0x180074a4d  retn
0x180074a4e  call    __std_init_once_link_alternate_names_and_abort
0x180074a54  call    abort
0x180074a5a  lea     rdx, aUnableToCreate; "Unable to create 'C' locale."
0x180074a61  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180074a66  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180074a6b  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180074a72  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180074a77  call    _CxxThrowException
```
