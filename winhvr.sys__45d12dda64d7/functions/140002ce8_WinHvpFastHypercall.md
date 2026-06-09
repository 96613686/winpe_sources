# WinHvpFastHypercall

- ea: `0x140002ce8`
- end: `0x140002d56`
- name: `WinHvpFastHypercall`
- size: `110`
- prototype: ``
- caller_count: `20`
- callee_count: `1`
- tags: ``

## callers

- `0x140001100`
- `0x140002420`
- `0x140002510`
- `0x140002550`
- `0x140002580`
- `0x1400025b0`
- `0x140002830`
- `0x140004680`
- `0x140004d60`
- `0x140005810`
- `0x140007310`
- `0x1400077f8`
- `0x1400093f0`
- `0x140009420`
- `0x140009460`
- `0x140009680`
- `0x14001d9e0`
- `0x14001fd00`
- `0x140021030`
- `0x140023920`

## callees

- `0x140002ce8`

## import_xrefs

- `ntoskrnl!HvlInvokeHypercall` at `0x140002d2b`
- `ntoskrnl!HvlInvokeHypercall` at `0x140002d2b`

## pseudocode

```c
__int64 __fastcall WinHvpFastHypercall(unsigned __int16 a1, _QWORD *a2)
{
  unsigned __int16 v2; // ax

  if ( !WinHvpConnected )
    return 3224702976LL;
  v2 = HvlInvokeHypercall((WinHvpNested != 0 ? -2147418112 : 0x10000) | (unsigned int)a1, *a2, a2[1]);
  if ( v2 )
    return v2 | 0xC0350000;
  else
    return 0;
}

```

## disassembly

```asm
0x140002ce8  push    rbx
0x140002cea  sub     rsp, 20h
0x140002cee  mov     al, cs:WinHvpNested
0x140002cf4  xor     ebx, ebx
0x140002cf6  movzx   r8d, cx
0x140002cfa  neg     al
0x140002cfc  mov     [rsp+28h+arg_8], rbx
0x140002d01  sbb     ecx, ecx
0x140002d03  and     ecx, 80000000h
0x140002d09  add     ecx, 10000h
0x140002d0f  or      r8d, ecx
0x140002d12  cmp     cs:WinHvpConnected, bl
0x140002d18  mov     dword ptr [rsp+28h+arg_8], r8d
0x140002d1d  jz      short loc_140002D4F
0x140002d1f  mov     r8, [rdx+8]
0x140002d23  mov     rdx, [rdx]
0x140002d26  mov     rcx, [rsp+28h+arg_8]
0x140002d2b  call    cs:__imp_HvlInvokeHypercall
0x140002d32  nop     dword ptr [rax+rax+00h]
0x140002d37  test    ax, ax
0x140002d3a  jnz     short loc_140002D45
0x140002d3c  mov     eax, ebx
0x140002d3e  add     rsp, 20h
0x140002d42  pop     rbx
0x140002d43  retn
0x140002d45  movzx   eax, ax
0x140002d48  or      eax, 0C0350000h
0x140002d4d  jmp     short loc_140002D3E
0x140002d4f  mov     eax, 0C0351000h
0x140002d54  jmp     short loc_140002D3E
```
