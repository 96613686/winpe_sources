# std::_Uninitialized_move<uchar *,wil::secure_allocator<uchar>>(uchar * const,uchar * const,uchar *,wil::secure_allocator<uchar> &)

- ea: `0x180006474`
- end: `0x18000648b`
- name: `??$_Uninitialized_move@PEAEU?$secure_allocator@E@wil@@@std@@YAPEAEQEAE0PEAEAEAU?$secure_allocator@E@wil@@@Z`
- size: `23`
- prototype: `_BYTE *__fastcall(_BYTE *, _BYTE *, _BYTE *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180034fb7`
- `0x18003502a`

## callees

- `0x180006474`

## pseudocode

```c
_BYTE *__fastcall std::_Uninitialized_move<unsigned char *,wil::secure_allocator<unsigned char>>(
        _BYTE *a1,
        _BYTE *a2,
        _BYTE *a3)
{
  _BYTE *result; // rax

  result = a3;
  while ( a1 != a2 )
    *result++ = *a1++;
  return result;
}

```

## disassembly

```asm
0x180006474  mov     rax, r8
0x180006477  jmp     short loc_180006485
0x180006479  mov     r8b, [rcx]
0x18000647c  mov     [rax], r8b
0x18000647f  inc     rax
0x180006482  inc     rcx
0x180006485  cmp     rcx, rdx
0x180006488  jnz     short loc_180006479
0x18000648a  retn
```
