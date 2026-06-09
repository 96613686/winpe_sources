# McGenEventUnregister_EtwUnregister

- ea: `0x1400098f8`
- end: `0x140009929`
- name: `McGenEventUnregister_EtwUnregister`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140012490`
- `0x14001303c`

## callees

- `0x1400098f8`

## import_xrefs

- `ntoskrnl!EtwUnregister` at `0x14000990c`
- `ntoskrnl!EtwUnregister` at `0x14000990c`

## pseudocode

```c
NTSTATUS McGenEventUnregister_EtwUnregister()
{
  NTSTATUS result; // eax

  if ( !USB_Redirector_Event_Provider_Context )
    return 0;
  result = EtwUnregister(USB_Redirector_Event_Provider_Context);
  USB_Redirector_Event_Provider_Context = 0;
  return result;
}

```

## disassembly

```asm
0x1400098f8  sub     rsp, 28h
0x1400098fc  mov     rcx, cs:USB_Redirector_Event_Provider_Context; RegHandle
0x140009903  test    rcx, rcx
0x140009906  jnz     short loc_14000990C
0x140009908  xor     eax, eax
0x14000990a  jmp     short loc_140009923
0x14000990c  call    cs:__imp_EtwUnregister
0x140009913  nop     dword ptr [rax+rax+00h]
0x140009918  mov     cs:USB_Redirector_Event_Provider_Context, 0
0x140009923  add     rsp, 28h
0x140009927  retn
```
