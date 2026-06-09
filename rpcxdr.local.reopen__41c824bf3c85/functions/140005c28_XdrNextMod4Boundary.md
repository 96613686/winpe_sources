# XdrNextMod4Boundary

- ea: `0x140005c28`
- end: `0x140005c4a`
- name: `XdrNextMod4Boundary`
- size: `34`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x140002514`
- `0x140002b30`
- `0x140003f80`
- `0x1400042c4`
- `0x140004388`
- `0x140004558`
- `0x140004958`
- `0x140005a94`
- `0x140005bac`
- `0x140008988`
- `0x140009700`
- `0x14000993c`
- `0x14000d154`
- `0x140015408`

## callees

- `0x140005c28`

## pseudocode

```c
__int64 __fastcall XdrNextMod4Boundary(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v2; // rax
  __int64 v3; // rcx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 72);
  if ( v1 )
  {
    v2 = *(_QWORD *)(v1 + 56);
    v3 = *(_QWORD *)(v1 + 64);
  }
  else
  {
    LOBYTE(v2) = 0;
    LOBYTE(v3) = 0;
  }
  result = ((_BYTE)v2 - (_BYTE)v3) & 3;
  *(_QWORD *)(v1 + 64) += result;
  return result;
}

```

## disassembly

```asm
0x140005c28  mov     rdx, [rcx+48h]
0x140005c2c  test    rdx, rdx
0x140005c2f  jnz     short loc_140005C37
0x140005c31  xor     eax, eax
0x140005c33  xor     ecx, ecx
0x140005c35  jmp     short loc_140005C3F
0x140005c37  mov     rax, [rdx+38h]
0x140005c3b  mov     rcx, [rdx+40h]
0x140005c3f  sub     rax, rcx
0x140005c42  and     eax, 3
0x140005c45  add     [rdx+40h], rax
0x140005c49  retn
```
