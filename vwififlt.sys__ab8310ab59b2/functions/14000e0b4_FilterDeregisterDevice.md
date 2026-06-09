# FilterDeregisterDevice

- ea: `0x14000e0b4`
- end: `0x14000e0e1`
- name: `FilterDeregisterDevice`
- size: `45`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ca14`
- `0x14000d690`
- `0x140019078`

## callees

- `0x14000e0b4`

## import_xrefs

- `NDIS!NdisDeregisterDeviceEx` at `0x14000e0c4`
- `NDIS!NdisDeregisterDeviceEx` at `0x14000e0c4`

## pseudocode

```c
void FilterDeregisterDevice()
{
  if ( NdisFilterDeviceHandle )
    NdisDeregisterDeviceEx(NdisFilterDeviceHandle);
  NdisFilterDeviceHandle = 0;
}

```

## disassembly

```asm
0x14000e0b4  sub     rsp, 28h
0x14000e0b8  mov     rcx, cs:NdisFilterDeviceHandle; NdisDeviceHandle
0x14000e0bf  test    rcx, rcx
0x14000e0c2  jz      short loc_14000E0D0
0x14000e0c4  call    cs:__imp_NdisDeregisterDeviceEx
0x14000e0cb  nop     dword ptr [rax+rax+00h]
0x14000e0d0  mov     cs:NdisFilterDeviceHandle, 0
0x14000e0db  add     rsp, 28h
0x14000e0df  retn
```
