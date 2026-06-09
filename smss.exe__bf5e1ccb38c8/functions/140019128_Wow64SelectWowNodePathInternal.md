# Wow64SelectWowNodePathInternal

- ea: `0x140019128`
- end: `0x14001914b`
- name: `Wow64SelectWowNodePathInternal`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b21c`

## callees

- `0x140019128`

## pseudocode

```c
__int64 *__fastcall Wow64SelectWowNodePathInternal(__int16 a1)
{
  if ( a1 == 332 )
    return &Wowx86NodeString;
  if ( a1 == 452 )
    return &WowArmNodeString;
  return 0;
}

```

## disassembly

```asm
0x140019128  movzx   edx, cx
0x14001912b  sub     edx, 14Ch
0x140019131  jz      short loc_140019143
0x140019133  cmp     edx, 78h ; 'x'
0x140019136  jz      short loc_14001913B
0x140019138  xor     eax, eax
0x14001913a  retn
0x14001913b  lea     rax, WowArmNodeString
0x140019142  retn
0x140019143  lea     rax, Wowx86NodeString
0x14001914a  retn
```
