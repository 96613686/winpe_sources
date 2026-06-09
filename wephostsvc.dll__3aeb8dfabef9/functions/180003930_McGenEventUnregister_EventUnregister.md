# McGenEventUnregister_EventUnregister

- ea: `0x180003930`
- end: `0x18000395a`
- name: `McGenEventUnregister_EventUnregister`
- size: `42`
- prototype: `ULONG()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800036b0`

## callees

- `0x180003930`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180003944`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180003944`

## pseudocode

```c
ULONG McGenEventUnregister_EventUnregister()
{
  ULONG result; // eax

  if ( !Microsoft_Windows_WEPHOSTSVC_Context )
    return 0;
  result = EventUnregister(Microsoft_Windows_WEPHOSTSVC_Context);
  Microsoft_Windows_WEPHOSTSVC_Context = 0;
  return result;
}

```

## disassembly

```asm
0x180003930  sub     rsp, 28h
0x180003934  mov     rcx, cs:Microsoft_Windows_WEPHOSTSVC_Context; RegHandle
0x18000393b  test    rcx, rcx
0x18000393e  jnz     short loc_180003944
0x180003940  xor     eax, eax
0x180003942  jmp     short loc_180003955
0x180003944  call    cs:__imp_EventUnregister
0x18000394a  mov     cs:Microsoft_Windows_WEPHOSTSVC_Context, 0
0x180003955  add     rsp, 28h
0x180003959  retn
```
