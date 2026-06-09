# McGenEventUnregister_EventUnregister

- ea: `0x1800027e8`
- end: `0x180002819`
- name: `McGenEventUnregister_EventUnregister`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800024f0`

## callees

- `0x1800027e8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800027fc`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800027fc`

## pseudocode

```c
ULONG McGenEventUnregister_EventUnregister()
{
  ULONG result; // eax

  if ( !LOG_SMPHOSTPROVIDER_GUID_Context )
    return 0;
  result = EventUnregister(LOG_SMPHOSTPROVIDER_GUID_Context);
  LOG_SMPHOSTPROVIDER_GUID_Context = 0;
  return result;
}

```

## disassembly

```asm
0x1800027e8  sub     rsp, 28h
0x1800027ec  mov     rcx, cs:LOG_SMPHOSTPROVIDER_GUID_Context; RegHandle
0x1800027f3  test    rcx, rcx
0x1800027f6  jnz     short loc_1800027FC
0x1800027f8  xor     eax, eax
0x1800027fa  jmp     short loc_180002813
0x1800027fc  call    cs:__imp_EventUnregister
0x180002803  nop     dword ptr [rax+rax+00h]
0x180002808  mov     cs:LOG_SMPHOSTPROVIDER_GUID_Context, 0
0x180002813  add     rsp, 28h
0x180002817  retn
```
