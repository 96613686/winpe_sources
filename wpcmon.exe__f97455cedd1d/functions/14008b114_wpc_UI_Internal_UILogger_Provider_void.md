# wpc::UI::Internal::UILogger::Provider(void)

- ea: `0x14008b114`
- end: `0x14008b1fd`
- name: `?Provider@UILogger@Internal@UI@wpc@@SAPEBU_tlgProvider_t@@XZ`
- size: `233`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `8`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400896b8`
- `0x14008997c`
- `0x14008a48c`
- `0x14008ada0`
- `0x14008b350`
- `0x14008b47c`
- `0x14008b5d0`
- `0x14008c3e0`

## callees

- `0x140001cf8`
- `0x140005a84`
- `0x14008b114`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x14008b1e8`
- `KERNEL32!InitOnceComplete` at `0x14008b1e8`
- `KERNEL32!InitOnceBeginInitialize` at `0x14008b13c`
- `KERNEL32!InitOnceBeginInitialize` at `0x14008b13c`

## pseudocode

```c
const struct _tlgProvider_t *wpc::UI::Internal::UILogger::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( __std_init_once_begin_initialize(&`wpc::UI::Internal::UILogger::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2)
    && v1 )
  {
    qword_1401111A0 = 0;
    v2 = &qword_140111198;
    qword_140111198 = (__int64)&wpc::UI::Internal::UILogger::`vftable';
    byte_1401111A8 = 0;
    dword_1401111AC = 0;
    qword_1401111B0 = &`wpc::UI::Internal::UILogger::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_56a6f58ae4213208320cc1d58f41052a_::_lambda_invoker_cdecl_);
    qword_1401111A0 = (__int64)qword_1401111B0;
    byte_1401111A8 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(qword_1401111B0);
    dword_1401111AC = 1;
    (*(void (__fastcall **)(__int64 *))(qword_140111198 + 8))(&qword_140111198);
    InitOnceComplete(&`wpc::UI::Internal::UILogger::Instance'::`2'::wrapper, 0, &qword_140111198);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x14008b114  mov     rax, rsp
0x14008b117  push    rbx
0x14008b118  sub     rsp, 20h
0x14008b11c  lea     r9, [rax+10h]; lpContext
0x14008b120  mov     qword ptr [rax+10h], 0
0x14008b128  lea     r8, [rax+8]; fPending
0x14008b12c  mov     dword ptr [rax+8], 0
0x14008b133  xor     edx, edx; dwFlags
0x14008b135  lea     rcx, ?wrapper@?1??Instance@UILogger@Internal@UI@wpc@@KAPEAV2345@XZ@4V?$static_lazy@VUILogger@Internal@UI@wpc@@@details@wil@@A; lpInitOnce
0x14008b13c  call    cs:__imp___std_init_once_begin_initialize
0x14008b142  test    eax, eax
0x14008b144  jz      loc_14008B1EE
0x14008b14a  cmp     [rsp+28h+arg_0], 0
0x14008b14f  jz      loc_14008B1EE
0x14008b155  lea     rbx, qword_140111198
0x14008b15c  mov     cs:qword_1401111A0, 0
0x14008b167  lea     rax, ??_7UILogger@Internal@UI@wpc@@6B@; const wpc::UI::Internal::UILogger::`vftable'
0x14008b16e  mov     [rsp+28h+arg_8], rbx
0x14008b173  mov     cs:qword_140111198, rax
0x14008b17a  mov     cs:byte_1401111A8, 0
0x14008b181  mov     cs:dword_1401111AC, 0
0x14008b18b  lea     rax, ?__hInner@?1???0StaticHandle@UILogger@Internal@UI@wpc@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wpc::UI::Internal::UILogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x14008b192  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_56a6f58ae4213208320cc1d58f41052a_@@CA@XZ; void (__cdecl *)()
0x14008b199  mov     cs:qword_1401111B0, rax
0x14008b1a0  call    atexit
0x14008b1a5  mov     rcx, cs:qword_1401111B0; CallbackContext
0x14008b1ac  mov     cs:qword_1401111A0, rcx
0x14008b1b3  mov     cs:byte_1401111A8, 1
0x14008b1ba  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14008b1bf  mov     rax, cs:qword_140111198
0x14008b1c6  mov     rcx, rbx
0x14008b1c9  mov     cs:dword_1401111AC, 1
0x14008b1d3  mov     rax, [rax+8]
0x14008b1d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b1dc  mov     r8, rbx; lpContext
0x14008b1df  lea     rcx, ?wrapper@?1??Instance@UILogger@Internal@UI@wpc@@KAPEAV2345@XZ@4V?$static_lazy@VUILogger@Internal@UI@wpc@@@details@wil@@A; lpInitOnce
0x14008b1e6  xor     edx, edx; dwFlags
0x14008b1e8  call    cs:__imp_InitOnceComplete
0x14008b1ee  mov     rax, [rsp+28h+arg_8]
0x14008b1f3  mov     rax, [rax+8]
0x14008b1f7  add     rsp, 20h
0x14008b1fb  pop     rbx
0x14008b1fc  retn
```
