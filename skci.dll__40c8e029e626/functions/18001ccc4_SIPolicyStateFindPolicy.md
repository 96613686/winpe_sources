# SIPolicyStateFindPolicy

- ea: `0x18001ccc4`
- end: `0x18001cd14`
- name: `SIPolicyStateFindPolicy`
- size: `80`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001961c`
- `0x18001c380`
- `0x18001caf8`
- `0x18001cfcc`
- `0x18001d1b8`
- `0x18001d258`
- `0x1800492f8`

## callees

- `0x18001ccc4`

## pseudocode

```c
_QWORD *__fastcall SIPolicyStateFindPolicy(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // r9
  _QWORD *i; // rcx
  unsigned __int64 v5; // r8
  __int64 v6; // rdx

  v2 = (_QWORD *)(a1 + 16);
  for ( i = *(_QWORD **)(a1 + 16); i != v2; i = (_QWORD *)*i )
  {
    v5 = -(__int64)(*((_DWORD *)i - 198) < 6u) & 0xFFFFFFFFFFFFFD50uLL;
    v6 = *(_QWORD *)((char *)i + v5 - 128) - *a2;
    if ( !v6 )
      v6 = *(_QWORD *)((char *)i + v5 - 120) - a2[1];
    if ( !v6 )
      return i - 104;
  }
  return 0;
}

```

## disassembly

```asm
0x18001ccc4  lea     r9, [rcx+10h]
0x18001ccc8  mov     r11, rdx
0x18001cccb  mov     rcx, [r9]
0x18001ccce  cmp     rcx, r9
0x18001ccd1  jz      short loc_18001CD11
0x18001ccd3  lea     r10, [rcx-340h]
0x18001ccda  cmp     dword ptr [r10+28h], 6
0x18001ccdf  sbb     r8, r8
0x18001cce2  and     r8, 0FFFFFFFFFFFFFD50h
0x18001cce9  mov     rdx, [r8+r10+2C0h]
0x18001ccf1  sub     rdx, [r11]
0x18001ccf4  jnz     short loc_18001CD02
0x18001ccf6  mov     rdx, [r8+r10+2C8h]
0x18001ccfe  sub     rdx, [r11+8]
0x18001cd02  test    rdx, rdx
0x18001cd05  jz      short loc_18001CD0C
0x18001cd07  mov     rcx, [rcx]
0x18001cd0a  jmp     short loc_18001CCCE
0x18001cd0c  mov     rax, r10
0x18001cd0f  retn
0x18001cd11  xor     eax, eax
0x18001cd13  retn
```
