# OF_WriteString

- ea: `0x180009620`
- end: `0x180009641`
- name: `OF_WriteString`
- size: `33`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180007a1c`
- `0x180007f40`
- `0x1800080e0`
- `0x180009b98`
- `0x18000b1f0`

## callees

- `0x18000957c`
- `0x180022604`

## pseudocode

```c
_BOOL8 __fastcall OF_WriteString(__int64 a1, __int64 a2)
{
  DWORD v2; // eax
  const void *v3; // rcx
  HANDLE *v4; // r10

  v2 = SizeOfStringW(a2);
  return OF_WriteBinaryData(v4, v3, v2);
}

```

## disassembly

```asm
0x180009620  sub     rsp, 28h
0x180009624  mov     r10, rcx
0x180009627  mov     rcx, rdx
0x18000962a  call    SizeOfStringW
0x18000962f  mov     rdx, rcx
0x180009632  mov     r8d, eax
0x180009635  mov     rcx, r10
0x180009638  add     rsp, 28h
0x18000963c  jmp     OF_WriteBinaryData
```
