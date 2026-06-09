# SlbNatIpsDetachProviderCompleteWorkerRoutine

- ea: `0x1400304a0`
- end: `0x1400304de`
- name: `SlbNatIpsDetachProviderCompleteWorkerRoutine`
- size: `62`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000caa0`
- `0x1400304a0`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1400304b7`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1400304b7`
- `NETIO!NmrClientDetachProviderComplete` at `0x1400304cb`
- `NETIO!NmrClientDetachProviderComplete` at `0x1400304cb`

## pseudocode

```c
void __fastcall SlbNatIpsDetachProviderCompleteWorkerRoutine(
        PDEVICE_OBJECT DeviceObject,
        PEX_RUNDOWN_REF_CACHE_AWARE *Context,
        __int64 a3)
{
  PEX_RUNDOWN_REF_CACHE_AWARE v4; // rcx

  if ( !Context )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(DeviceObject, 0, a3);
  ExWaitForRundownProtectionReleaseCacheAware(Context[1]);
  v4 = Context[4];
  *((_BYTE *)Context + 2) = 0;
  NmrClientDetachProviderComplete(v4);
}

```

## disassembly

```asm
0x1400304a0  push    rbx
0x1400304a2  sub     rsp, 20h
0x1400304a6  mov     rbx, rdx
0x1400304a9  test    rdx, rdx
0x1400304ac  jnz     short loc_1400304B3
0x1400304ae  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400304b3  mov     rcx, [rbx+8]; RunRef
0x1400304b7  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x1400304be  nop     dword ptr [rax+rax+00h]
0x1400304c3  mov     rcx, [rbx+20h]; NmrBindingHandle
0x1400304c7  mov     byte ptr [rbx+2], 0
0x1400304cb  call    cs:__imp_NmrClientDetachProviderComplete
0x1400304d2  nop     dword ptr [rax+rax+00h]
0x1400304d7  add     rsp, 20h
0x1400304db  pop     rbx
0x1400304dc  retn
```
