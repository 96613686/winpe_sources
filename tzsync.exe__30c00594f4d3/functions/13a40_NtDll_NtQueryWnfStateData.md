# NtDll::NtQueryWnfStateData

- ea: `0x13a40`
- end: `0x13a53`
- name: `NtDll::NtQueryWnfStateData`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x128f0`

## callees

- `0x152d0`
- `0x15520`

## pseudocode

```c

```

## disassembly

```asm
0x13a40  call     class NtQueryWnfStateDataFn NativeMethods::get_NtQueryWnfStateData()
0x13a45  ldarg.0
0x13a46  ldarg.1
0x13a47  ldarg.2
0x13a48  ldarg.3
0x13a49  ldarg.s  4
0x13a4b  ldarg.s  5
0x13a4d  callvirt instance valuetype NTSTATUS NtQueryWnfStateDataFn::Invoke(valuetype WIL_WNF_STATE_NAME& StateName, native int TypeId, native int ExplicitScope, int32& ChangeStamp, native int Buffer, int32& BufferSize)
0x13a52  ret
```
