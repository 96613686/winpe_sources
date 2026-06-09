# ReadByte

- ea: `0x18001cd3c`
- end: `0x18001cd64`
- name: `ReadByte`
- size: `40`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ee80`
- `0x180010448`
- `0x1800106c8`
- `0x180015190`
- `0x1800153d0`
- `0x1800164e0`
- `0x18001d5f8`

## callees

- `0x18001cd3c`

## pseudocode

```c
__int64 __fastcall ReadByte(__int64 a1, _BYTE *a2, unsigned int a3)
{
  __int64 result; // rax

  if ( !*(_QWORD *)a1 || a3 + 1 < a3 || a3 + 1 > *(_DWORD *)(a1 + 8) )
    return 1001;
  result = 0;
  *a2 = *(_BYTE *)(a3 + *(_QWORD *)a1);
  return result;
}

```

## disassembly

```asm
0x18001cd3c  mov     r9, [rcx]
0x18001cd3f  test    r9, r9
0x18001cd42  jz      short loc_18001CD5E
0x18001cd44  lea     eax, [r8+1]
0x18001cd48  cmp     eax, r8d
0x18001cd4b  jb      short loc_18001CD5E
0x18001cd4d  cmp     eax, [rcx+8]
0x18001cd50  ja      short loc_18001CD5E
0x18001cd52  mov     eax, r8d
0x18001cd55  mov     cl, [rax+r9]
0x18001cd59  xor     eax, eax
0x18001cd5b  mov     [rdx], cl
0x18001cd5d  retn
0x18001cd5e  mov     eax, 3E9h
0x18001cd63  retn
```
