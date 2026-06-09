# McGenEventUnregister_EtwUnregister

- ea: `0x1400014c8`
- end: `0x1400014f9`
- name: `McGenEventUnregister_EtwUnregister`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x14000b5c0`
- `0x14000c614`

## callees

- `0x1400014c8`

## import_xrefs

- `ntoskrnl!EtwUnregister` at `0x1400014dc`
- `ntoskrnl!EtwUnregister` at `0x1400014dc`

## pseudocode

```c
NTSTATUS McGenEventUnregister_EtwUnregister()
{
  NTSTATUS result; // eax

  if ( !UevAgentDriver_Context )
    return 0;
  result = EtwUnregister(UevAgentDriver_Context);
  UevAgentDriver_Context = 0;
  return result;
}

```

## disassembly

```asm
0x1400014c8  sub     rsp, 28h
0x1400014cc  mov     rcx, cs:UevAgentDriver_Context; RegHandle
0x1400014d3  test    rcx, rcx
0x1400014d6  jnz     short loc_1400014DC
0x1400014d8  xor     eax, eax
0x1400014da  jmp     short loc_1400014F3
0x1400014dc  call    cs:__imp_EtwUnregister
0x1400014e3  nop     dword ptr [rax+rax+00h]
0x1400014e8  mov     cs:UevAgentDriver_Context, 0
0x1400014f3  add     rsp, 28h
0x1400014f7  retn
```
