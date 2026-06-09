# HUBUCX_DeleteEndpointsAndFreeResourcesForCurrentConfiguration

- ea: `0x140026570`
- end: `0x140026596`
- name: `HUBUCX_DeleteEndpointsAndFreeResourcesForCurrentConfiguration`
- size: `38`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140020840`
- `0x140020c00`
- `0x140020c30`
- `0x1400211a0`
- `0x1400211f0`
- `0x140021230`

## callees

- `0x1400264c8`
- `0x140026570`

## pseudocode

```c
__int64 __fastcall HUBUCX_DeleteEndpointsAndFreeResourcesForCurrentConfiguration(__int64 a1)
{
  __int64 result; // rax

  if ( *(_QWORD *)(a1 + 48) )
  {
    result = HUBUCX_DeleteEndpointsAndFreeResourcesForConfiguration();
    *(_QWORD *)(a1 + 48) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140026570  push    rbx
0x140026572  sub     rsp, 20h
0x140026576  mov     rdx, [rcx+30h]
0x14002657a  mov     rbx, rcx
0x14002657d  test    rdx, rdx
0x140026580  jz      short loc_14002658F
0x140026582  call    HUBUCX_DeleteEndpointsAndFreeResourcesForConfiguration
0x140026587  mov     qword ptr [rbx+30h], 0
0x14002658f  add     rsp, 20h
0x140026593  pop     rbx
0x140026594  retn
```
