# McGenEventRegister_EventRegister

- ea: `0x1800027a8`
- end: `0x1800027e1`
- name: `McGenEventRegister_EventRegister`
- size: `57`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002380`

## callees

- `0x1800027a8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800027cf`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800027cf`

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
0x1800027a8  sub     rsp, 28h
0x1800027ac  xor     eax, eax
0x1800027ae  cmp     cs:LOG_SMPHOSTPROVIDER_GUID_Context, rax
0x1800027b5  jnz     short loc_1800027DB
0x1800027b7  lea     r8, LOG_SMPHOSTPROVIDER_GUID_Context; CallbackContext
0x1800027be  mov     r9, r8; RegHandle
0x1800027c1  lea     rdx, McGenControlCallbackV2; EnableCallback
0x1800027c8  lea     rcx, LOG_SMPHOSTPROVIDER_GUID; ProviderId
0x1800027cf  call    cs:__imp_EventRegister
0x1800027d6  nop     dword ptr [rax+rax+00h]
0x1800027db  add     rsp, 28h
0x1800027df  retn
```
