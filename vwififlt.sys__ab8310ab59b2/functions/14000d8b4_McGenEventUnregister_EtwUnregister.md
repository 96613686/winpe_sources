# McGenEventUnregister_EtwUnregister

- ea: `0x14000d8b4`
- end: `0x14000d8e5`
- name: `McGenEventUnregister_EtwUnregister`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d690`
- `0x140019078`

## callees

- `0x14000d8b4`

## import_xrefs

- `ntoskrnl!EtwUnregister` at `0x14000d8c8`
- `ntoskrnl!EtwUnregister` at `0x14000d8c8`

## pseudocode

```c
NTSTATUS McGenEventUnregister_EtwUnregister()
{
  NTSTATUS result; // eax

  if ( !VWIFI_PROVIDER_ID_Context )
    return 0;
  result = EtwUnregister(VWIFI_PROVIDER_ID_Context);
  VWIFI_PROVIDER_ID_Context = 0;
  return result;
}

```

## disassembly

```asm
0x14000d8b4  sub     rsp, 28h
0x14000d8b8  mov     rcx, cs:VWIFI_PROVIDER_ID_Context; RegHandle
0x14000d8bf  test    rcx, rcx
0x14000d8c2  jnz     short loc_14000D8C8
0x14000d8c4  xor     eax, eax
0x14000d8c6  jmp     short loc_14000D8DF
0x14000d8c8  call    cs:__imp_EtwUnregister
0x14000d8cf  nop     dword ptr [rax+rax+00h]
0x14000d8d4  mov     cs:VWIFI_PROVIDER_ID_Context, 0
0x14000d8df  add     rsp, 28h
0x14000d8e3  retn
```
