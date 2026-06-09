# __imp_load_EventWriteTransfer

- ea: `0x14001a876`
- end: `0x14001a882`
- name: `__imp_load_EventWriteTransfer`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x14001a7c1`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14001a876`

## pseudocode

```c
__int64 load_EventWriteTransfer()
{
  return _tailMerge_api_ms_win_eventing_provider_l1_1_0_dll();
}

```

## disassembly

```asm
0x14001a876  lea     rax, __imp_EventWriteTransfer
0x14001a87d  jmp     __tailMerge_api_ms_win_eventing_provider_l1_1_0_dll
```
