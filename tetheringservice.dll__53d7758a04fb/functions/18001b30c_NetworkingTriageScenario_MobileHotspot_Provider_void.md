# NetworkingTriageScenario::MobileHotspot::Provider(void)

- ea: `0x18001b30c`
- end: `0x18001b3f5`
- name: `?Provider@MobileHotspot@NetworkingTriageScenario@@SAPEBU_tlgProvider_t@@XZ`
- size: `233`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180020150`
- `0x18002035c`
- `0x180020524`
- `0x18002072c`
- `0x1800209c4`

## callees

- `0x180001720`
- `0x180002940`
- `0x18001b30c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001b334`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001b334`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001b3e0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001b3e0`

## pseudocode

```c
const struct _tlgProvider_t *NetworkingTriageScenario::MobileHotspot::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(
         &`NetworkingTriageScenario::MobileHotspot::Instance'::`2'::wrapper,
         0,
         &v1,
         (LPVOID *)&v2)
    && v1 )
  {
    qword_180042198 = 0;
    v2 = &qword_180042190;
    qword_180042190 = (__int64)&NetworkingTriageScenario::MobileHotspot::`vftable';
    byte_1800421A0 = 0;
    dword_1800421A4 = 0;
    CallbackContext = &`NetworkingTriageScenario::MobileHotspot::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_57e29497f0890ed944683efb21021fbd_::_lambda_invoker_cdecl_);
    qword_180042198 = (__int64)CallbackContext;
    byte_1800421A0 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_1800421A4 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180042190 + 8))(&qword_180042190);
    InitOnceComplete(&`NetworkingTriageScenario::MobileHotspot::Instance'::`2'::wrapper, 0, &qword_180042190);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x18001b30c  mov     rax, rsp
0x18001b30f  push    rbx
0x18001b310  sub     rsp, 20h
0x18001b314  lea     r9, [rax+10h]; lpContext
0x18001b318  mov     qword ptr [rax+10h], 0
0x18001b320  lea     r8, [rax+8]; fPending
0x18001b324  mov     dword ptr [rax+8], 0
0x18001b32b  xor     edx, edx; dwFlags
0x18001b32d  lea     rcx, ?wrapper@?1??Instance@MobileHotspot@NetworkingTriageScenario@@KAPEAV23@XZ@4V?$static_lazy@VMobileHotspot@NetworkingTriageScenario@@@details@wil@@A; lpInitOnce
0x18001b334  call    cs:__imp_InitOnceBeginInitialize
0x18001b33a  test    eax, eax
0x18001b33c  jz      loc_18001B3E6
0x18001b342  cmp     [rsp+28h+arg_0], 0
0x18001b347  jz      loc_18001B3E6
0x18001b34d  lea     rbx, qword_180042190
0x18001b354  mov     cs:qword_180042198, 0
0x18001b35f  lea     rax, ??_7MobileHotspot@NetworkingTriageScenario@@6B@; const NetworkingTriageScenario::MobileHotspot::`vftable'
0x18001b366  mov     [rsp+28h+arg_8], rbx
0x18001b36b  mov     cs:qword_180042190, rax
0x18001b372  mov     cs:byte_1800421A0, 0
0x18001b379  mov     cs:dword_1800421A4, 0
0x18001b383  lea     rax, ?__hInner@?1???0StaticHandle@MobileHotspot@NetworkingTriageScenario@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `NetworkingTriageScenario::MobileHotspot::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18001b38a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_57e29497f0890ed944683efb21021fbd_@@CA@XZ; void (__cdecl *)()
0x18001b391  mov     cs:CallbackContext, rax
0x18001b398  call    atexit
0x18001b39d  mov     rcx, cs:CallbackContext; CallbackContext
0x18001b3a4  mov     cs:qword_180042198, rcx
0x18001b3ab  mov     cs:byte_1800421A0, 1
0x18001b3b2  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001b3b7  mov     rax, cs:qword_180042190
0x18001b3be  mov     rcx, rbx
0x18001b3c1  mov     cs:dword_1800421A4, 1
0x18001b3cb  mov     rax, [rax+8]
0x18001b3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3d4  mov     r8, rbx; lpContext
0x18001b3d7  lea     rcx, ?wrapper@?1??Instance@MobileHotspot@NetworkingTriageScenario@@KAPEAV23@XZ@4V?$static_lazy@VMobileHotspot@NetworkingTriageScenario@@@details@wil@@A; lpInitOnce
0x18001b3de  xor     edx, edx; dwFlags
0x18001b3e0  call    cs:__imp_InitOnceComplete
0x18001b3e6  mov     rax, [rsp+28h+arg_8]
0x18001b3eb  mov     rax, [rax+8]
0x18001b3ef  add     rsp, 20h
0x18001b3f3  pop     rbx
0x18001b3f4  retn
```
