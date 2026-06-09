# VmpIsVolumeDead

- ea: `0x140016990`
- end: `0x1400169af`
- name: `VmpIsVolumeDead`
- size: `31`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1400046a4`
- `0x14000e010`
- `0x140012fa0`
- `0x1400132f8`
- `0x140016130`
- `0x140016540`
- `0x140016760`

## callees

- `0x140016990`

## pseudocode

```c
bool __fastcall VmpIsVolumeDead(__int64 a1)
{
  if ( *(_BYTE *)(a1 + 426) )
    return *(_QWORD *)(a1 + 432) == 0;
  else
    return *(_QWORD *)(a1 + 344) == 0;
}

```

## disassembly

```asm
0x140016990  xor     eax, eax
0x140016992  cmp     [rcx+1AAh], al
0x140016998  jnz     short loc_1400169A6
0x14001699a  cmp     [rcx+158h], rax
0x1400169a1  setz    al
0x1400169a4  retn
0x1400169a6  cmp     [rcx+1B0h], rax
0x1400169ad  jmp     short loc_1400169A1
```
