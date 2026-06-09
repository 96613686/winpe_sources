# McGenEventUnregister_EventUnregister

- ea: `0x180002740`
- end: `0x18000276a`
- name: `McGenEventUnregister_EventUnregister`
- size: `42`
- prototype: `ULONG()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002460`

## callees

- `0x180002740`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180002754`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180002754`

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
0x180002740  sub     rsp, 28h
0x180002744  mov     rcx, cs:LOG_SMPHOSTPROVIDER_GUID_Context; RegHandle
0x18000274b  test    rcx, rcx
0x18000274e  jnz     short loc_180002754
0x180002750  xor     eax, eax
0x180002752  jmp     short loc_180002765
0x180002754  call    cs:__imp_EventUnregister
0x18000275a  mov     cs:LOG_SMPHOSTPROVIDER_GUID_Context, 0
0x180002765  add     rsp, 28h
0x180002769  retn
```
