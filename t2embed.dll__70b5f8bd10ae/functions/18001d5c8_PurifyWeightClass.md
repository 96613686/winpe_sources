# PurifyWeightClass

- ea: `0x18001d5c8`
- end: `0x18001d5e0`
- name: `PurifyWeightClass`
- size: `24`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001862c`
- `0x180021394`

## callees

- `0x18001d5c8`

## pseudocode

```c
__int64 __fastcall PurifyWeightClass(unsigned __int16 a1)
{
  if ( a1 < 0xAu )
    return *((unsigned __int16 *)qword_18002C978 + a1);
  return a1;
}

```

## disassembly

```asm
0x18001d5c8  cmp     cx, 0Ah
0x18001d5cc  jnb     short loc_18001D5DC
0x18001d5ce  movzx   eax, cx
0x18001d5d1  lea     rcx, qword_18002C978
0x18001d5d8  movzx   ecx, word ptr [rcx+rax*2]
0x18001d5dc  movzx   eax, cx
0x18001d5df  retn
```
