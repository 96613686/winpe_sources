# WinHvpGetVpDataPages

- ea: `0x140001440`
- end: `0x140001458`
- name: `WinHvpGetVpDataPages`
- size: `24`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140001100`
- `0x1400011c0`
- `0x140006300`
- `0x140006390`
- `0x1400067ac`
- `0x1400068c0`
- `0x14000bcd0`

## pseudocode

```c
__int64 __fastcall WinHvpGetVpDataPages()
{
  __int64 v0; // rax

  LODWORD(v0) = HIDWORD(KeGetPcr()[1].LockArray);
  return WinHvpVpDataPages + 72 * v0;
}

```

## disassembly

```asm
0x140001440  mov     eax, gs:1A4h
0x140001448  lea     rdx, [rax+rax*8]
0x14000144c  mov     rax, cs:WinHvpVpDataPages
0x140001453  lea     rax, [rax+rdx*8]
0x140001457  retn
```
