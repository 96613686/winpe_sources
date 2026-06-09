# DeploymentHelperPrivate::UpdateDeploymentTelemetry::Provider(void)

- ea: `0x180026ad0`
- end: `0x180026bd7`
- name: `?Provider@UpdateDeploymentTelemetry@DeploymentHelperPrivate@@SAPEBU_tlgProvider_t@@XZ`
- size: `263`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026db4`
- `0x180026fd0`

## callees

- `0x1800016fc`
- `0x180026ad0`
- `0x180042630`
- `0x180042a04`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180026bb5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180026bb5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180026b09`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180026b09`

## pseudocode

```c
const struct _tlgProvider_t *DeploymentHelperPrivate::UpdateDeploymentTelemetry::Provider(void)
{
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  BOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(
         &`DeploymentHelperPrivate::UpdateDeploymentTelemetry::Instance'::`2'::wrapper,
         0,
         &fPending,
         &Context)
    && fPending )
  {
    qword_180076AA8 = 0;
    Context = &qword_180076AA0;
    qword_180076AA0 = (__int64)&DeploymentHelperPrivate::UpdateDeploymentTelemetry::`vftable';
    byte_180076AB0 = 0;
    dword_180076AB4 = 0;
    qword_180076AB8 = &`DeploymentHelperPrivate::UpdateDeploymentTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_0f3140eafb87bf272117671e6d7addf1_::_lambda_invoker_cdecl_);
    qword_180076AA8 = (__int64)qword_180076AB8;
    byte_180076AB0 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(qword_180076AB8);
    dword_180076AB4 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180076AA0 + 8))(&qword_180076AA0);
    InitOnceComplete(&`DeploymentHelperPrivate::UpdateDeploymentTelemetry::Instance'::`2'::wrapper, 0, &qword_180076AA0);
  }
  return (const struct _tlgProvider_t *)*((_QWORD *)Context + 1);
}

```

## disassembly

```asm
0x180026ad0  push    rbx
0x180026ad2  sub     rsp, 40h
0x180026ad6  mov     rax, cs:__security_cookie
0x180026add  xor     rax, rsp
0x180026ae0  mov     [rsp+48h+var_18], rax
0x180026ae5  lea     r9, [rsp+48h+Context]; lpContext
0x180026aea  mov     [rsp+48h+Context], 0
0x180026af3  lea     r8, [rsp+48h+fPending]; fPending
0x180026af8  mov     [rsp+48h+fPending], 0
0x180026b00  xor     edx, edx; dwFlags
0x180026b02  lea     rcx, ?wrapper@?1??Instance@UpdateDeploymentTelemetry@DeploymentHelperPrivate@@KAPEAV23@XZ@4V?$static_lazy@VUpdateDeploymentTelemetry@DeploymentHelperPrivate@@@details@wil@@A; lpInitOnce
0x180026b09  call    cs:__imp_InitOnceBeginInitialize
0x180026b0f  test    eax, eax
0x180026b11  jz      loc_180026BBB
0x180026b17  cmp     [rsp+48h+fPending], 0
0x180026b1c  jz      loc_180026BBB
0x180026b22  lea     rbx, qword_180076AA0
0x180026b29  mov     cs:qword_180076AA8, 0
0x180026b34  lea     rax, ??_7UpdateDeploymentTelemetry@DeploymentHelperPrivate@@6B@; const DeploymentHelperPrivate::UpdateDeploymentTelemetry::`vftable'
0x180026b3b  mov     [rsp+48h+Context], rbx
0x180026b40  mov     cs:qword_180076AA0, rax
0x180026b47  mov     cs:byte_180076AB0, 0
0x180026b4e  mov     cs:dword_180076AB4, 0
0x180026b58  lea     rax, ?__hInner@?1???0StaticHandle@UpdateDeploymentTelemetry@DeploymentHelperPrivate@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `DeploymentHelperPrivate::UpdateDeploymentTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180026b5f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0f3140eafb87bf272117671e6d7addf1_@@CA@XZ; void (__cdecl *)()
0x180026b66  mov     cs:qword_180076AB8, rax
0x180026b6d  call    atexit
0x180026b72  mov     rcx, cs:qword_180076AB8; CallbackContext
0x180026b79  mov     cs:qword_180076AA8, rcx
0x180026b80  mov     cs:byte_180076AB0, 1
0x180026b87  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180026b8c  mov     rax, cs:qword_180076AA0
0x180026b93  mov     rcx, rbx
0x180026b96  mov     cs:dword_180076AB4, 1
0x180026ba0  mov     rax, [rax+8]
0x180026ba4  call    _guard_dispatch_icall
0x180026ba9  mov     r8, rbx; lpContext
0x180026bac  lea     rcx, ?wrapper@?1??Instance@UpdateDeploymentTelemetry@DeploymentHelperPrivate@@KAPEAV23@XZ@4V?$static_lazy@VUpdateDeploymentTelemetry@DeploymentHelperPrivate@@@details@wil@@A; lpInitOnce
0x180026bb3  xor     edx, edx; dwFlags
0x180026bb5  call    cs:__imp_InitOnceComplete
0x180026bbb  mov     rax, [rsp+48h+Context]
0x180026bc0  mov     rax, [rax+8]
0x180026bc4  mov     rcx, [rsp+48h+var_18]
0x180026bc9  xor     rcx, rsp; StackCookie
0x180026bcc  call    __security_check_cookie
0x180026bd1  add     rsp, 40h
0x180026bd5  pop     rbx
0x180026bd6  retn
```
