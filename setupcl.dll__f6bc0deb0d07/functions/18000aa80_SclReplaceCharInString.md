# SclReplaceCharInString

- ea: `0x18000aa80`
- end: `0x18000aaa6`
- name: `SclReplaceCharInString`
- size: `38`
- prototype: `__int64 __fastcall(_WORD *, __int16, __int16)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002010`

## callees

- `0x18000aa80`

## pseudocode

```c
__int64 __fastcall SclReplaceCharInString(_WORD *a1, __int16 a2, __int16 a3)
{
  __int64 result; // rax

  if ( !a1 )
    return 3221225485LL;
  while ( 1 )
  {
    result = 0;
    if ( !*a1 )
      break;
    if ( a2 == *a1 )
      *a1 = a3;
    ++a1;
  }
  return result;
}

```

## disassembly

```asm
0x18000aa80  test    rcx, rcx
0x18000aa83  jnz     short loc_18000AA99
0x18000aa85  mov     eax, 0C000000Dh
0x18000aa8a  retn
0x18000aa8b  cmp     dx, r9w
0x18000aa8f  jnz     short loc_18000AA95
0x18000aa91  mov     [rcx], r8w
0x18000aa95  add     rcx, 2
0x18000aa99  movzx   r9d, word ptr [rcx]
0x18000aa9d  xor     eax, eax
0x18000aa9f  cmp     ax, r9w
0x18000aaa3  jnz     short loc_18000AA8B
0x18000aaa5  retn
```
