# SlbNatIpsDetachProviderCompleteWorkerRoutine

- ea: `0x14002f370`
- end: `0x14002f3ae`
- name: `SlbNatIpsDetachProviderCompleteWorkerRoutine`
- size: `62`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000caa0`
- `0x14002f370`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14002f387`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14002f387`
- `NETIO!NmrClientDetachProviderComplete` at `0x14002f39b`
- `NETIO!NmrClientDetachProviderComplete` at `0x14002f39b`

## pseudocode

```c
void __fastcall SlbNatIpsDetachProviderCompleteWorkerRoutine(
        PDEVICE_OBJECT DeviceObject,
        PEX_RUNDOWN_REF_CACHE_AWARE *Context,
        __int64 a3,
        __int64 a4)
{
  PEX_RUNDOWN_REF_CACHE_AWARE v5; // rcx

  if ( !Context )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(DeviceObject, 0, a3, a4);
  ExWaitForRundownProtectionReleaseCacheAware(Context[1]);
  v5 = Context[4];
  *((_BYTE *)Context + 2) = 0;
  NmrClientDetachProviderComplete(v5);
}

```

## disassembly

```asm
0x14002f370  push    rbx
0x14002f372  sub     rsp, 20h
0x14002f376  mov     rbx, rdx
0x14002f379  test    rdx, rdx
0x14002f37c  jnz     short loc_14002F383
0x14002f37e  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002f383  mov     rcx, [rbx+8]; RunRef
0x14002f387  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x14002f38e  nop     dword ptr [rax+rax+00h]
0x14002f393  mov     rcx, [rbx+20h]; NmrBindingHandle
0x14002f397  mov     byte ptr [rbx+2], 0
0x14002f39b  call    cs:__imp_NmrClientDetachProviderComplete
0x14002f3a2  nop     dword ptr [rax+rax+00h]
0x14002f3a7  add     rsp, 20h
0x14002f3ab  pop     rbx
0x14002f3ac  retn
```
