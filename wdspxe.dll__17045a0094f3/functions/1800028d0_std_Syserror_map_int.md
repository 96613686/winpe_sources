# std::_Syserror_map(int)

- ea: `0x1800028d0`
- end: `0x1800028f8`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800025c0`
- `0x180002730`
- `0x1800027a0`

## callees

- `0x1800028d0`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_1800146E0;
  if ( !"address family not supported" )
    return 0;
  while ( *(_DWORD *)v1 != a1 )
  {
    v1 += 2;
    if ( !v1[1] )
      return 0;
  }
  return (const char *)v1[1];
}

```

## disassembly

```asm
0x1800028d0  cmp     cs:off_1800146E8, 0; "address family not supported"
0x1800028d8  lea     rax, qword_1800146E0
0x1800028df  jz      short loc_1800028F0
0x1800028e1  cmp     [rax], ecx
0x1800028e3  jz      short loc_1800028F3
0x1800028e5  add     rax, 10h
0x1800028e9  cmp     qword ptr [rax+8], 0
0x1800028ee  jnz     short loc_1800028E1
0x1800028f0  xor     eax, eax
0x1800028f2  retn
0x1800028f3  mov     rax, [rax+8]
0x1800028f7  retn
```
