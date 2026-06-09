# std::_Syserror_map(int)

- ea: `0x180001c40`
- end: `0x180001c68`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001920`
- `0x180001aa0`
- `0x180001b10`

## callees

- `0x180001c40`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_18000D590;
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
0x180001c40  cmp     cs:off_18000D598, 0; "address family not supported"
0x180001c48  lea     rax, qword_18000D590
0x180001c4f  jz      short loc_180001C60
0x180001c51  cmp     [rax], ecx
0x180001c53  jz      short loc_180001C63
0x180001c55  add     rax, 10h
0x180001c59  cmp     qword ptr [rax+8], 0
0x180001c5e  jnz     short loc_180001C51
0x180001c60  xor     eax, eax
0x180001c62  retn
0x180001c63  mov     rax, [rax+8]
0x180001c67  retn
```
