# McGenEventRegister_EventRegister

- ea: `0x180002708`
- end: `0x18000273a`
- name: `McGenEventRegister_EventRegister`
- size: `50`
- prototype: `ULONG()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002300`

## callees

- `0x180002708`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000272f`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000272f`

## pseudocode

```c
ULONG McGenEventRegister_EventRegister()
{
  ULONG result; // eax

  result = 0;
  if ( !LOG_SMPHOSTPROVIDER_GUID_Context )
    return EventRegister(
             &LOG_SMPHOSTPROVIDER_GUID,
             (PENABLECALLBACK)McGenControlCallbackV2,
             &LOG_SMPHOSTPROVIDER_GUID_Context,
             &LOG_SMPHOSTPROVIDER_GUID_Context);
  return result;
}

```

## disassembly

```asm
0x180002708  sub     rsp, 28h
0x18000270c  xor     eax, eax
0x18000270e  cmp     cs:LOG_SMPHOSTPROVIDER_GUID_Context, rax
0x180002715  jnz     short loc_180002735
0x180002717  lea     r8, LOG_SMPHOSTPROVIDER_GUID_Context; CallbackContext
0x18000271e  mov     r9, r8; RegHandle
0x180002721  lea     rdx, McGenControlCallbackV2; EnableCallback
0x180002728  lea     rcx, LOG_SMPHOSTPROVIDER_GUID; ProviderId
0x18000272f  call    cs:__imp_EventRegister
0x180002735  add     rsp, 28h
0x180002739  retn
```
