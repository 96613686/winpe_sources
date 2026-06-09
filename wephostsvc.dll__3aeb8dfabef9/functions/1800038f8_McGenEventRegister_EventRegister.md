# McGenEventRegister_EventRegister

- ea: `0x1800038f8`
- end: `0x18000392a`
- name: `McGenEventRegister_EventRegister`
- size: `50`
- prototype: `ULONG()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800030b8`

## callees

- `0x1800038f8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000391f`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000391f`

## pseudocode

```c
ULONG McGenEventRegister_EventRegister()
{
  ULONG result; // eax

  result = 0;
  if ( !Microsoft_Windows_WEPHOSTSVC_Context )
    return EventRegister(
             &Microsoft_Windows_WEPHOSTSVC,
             (PENABLECALLBACK)McGenControlCallbackV2,
             &Microsoft_Windows_WEPHOSTSVC_Context,
             &Microsoft_Windows_WEPHOSTSVC_Context);
  return result;
}

```

## disassembly

```asm
0x1800038f8  sub     rsp, 28h
0x1800038fc  xor     eax, eax
0x1800038fe  cmp     cs:Microsoft_Windows_WEPHOSTSVC_Context, rax
0x180003905  jnz     short loc_180003925
0x180003907  lea     r8, Microsoft_Windows_WEPHOSTSVC_Context; CallbackContext
0x18000390e  mov     r9, r8; RegHandle
0x180003911  lea     rdx, McGenControlCallbackV2; EnableCallback
0x180003918  lea     rcx, Microsoft_Windows_WEPHOSTSVC; ProviderId
0x18000391f  call    cs:__imp_EventRegister
0x180003925  add     rsp, 28h
0x180003929  retn
```
