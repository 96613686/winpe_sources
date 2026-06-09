# TdiProviderReady

- ea: `0x140005360`
- end: `0x140005374`
- name: `TdiProviderReady`
- size: `20`
- prototype: `NTSTATUS __stdcall(HANDLE ProviderHandle)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140002f50`

## pseudocode

```c
NTSTATUS __stdcall TdiProviderReady(HANDLE ProviderHandle)
{
  return TdiHandleSerializedRequest(ProviderHandle, 19);
}

```

## disassembly

```asm
0x140005360  sub     rsp, 28h
0x140005364  mov     edx, 13h
0x140005369  call    TdiHandleSerializedRequest
0x14000536e  add     rsp, 28h
0x140005372  retn
```
