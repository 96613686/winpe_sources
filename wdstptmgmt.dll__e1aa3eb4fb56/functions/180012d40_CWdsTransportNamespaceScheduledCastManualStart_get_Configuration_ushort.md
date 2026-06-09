# CWdsTransportNamespaceScheduledCastManualStart::get_Configuration(ushort * *)

- ea: `0x180012d40`
- end: `0x180012d45`
- name: `?get_Configuration@CWdsTransportNamespaceScheduledCastManualStart@@UEAAJPEAPEAG@Z`
- size: `5`
- prototype: `__int64 __fastcall(CWdsTransportNamespaceScheduledCastManualStart *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180012d50`
- `0x180012d70`

## callees

- `0x180012ce0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CWdsTransportNamespaceScheduledCastManualStart::get_Configuration(
        CWdsTransportNamespaceScheduledCastManualStart *this,
        unsigned __int16 **a2)
{
  return CWdsTransportClient::get_MacAddress(this, a2);
}

```

## disassembly

```asm
0x180012d40  jmp     ?get_MacAddress@CWdsTransportClient@@UEAAJPEAPEAG@Z; CWdsTransportClient::get_MacAddress(ushort * *)
```
