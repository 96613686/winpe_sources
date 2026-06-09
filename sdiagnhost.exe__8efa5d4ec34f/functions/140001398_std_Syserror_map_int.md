# std::_Syserror_map(int)

- ea: `0x140001398`
- end: `0x1400013c0`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400071c0`
- `0x140007340`
- `0x1400073b0`

## callees

- `0x140001398`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_1400094D0;
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
0x140001398  cmp     cs:off_1400094D8, 0; "address family not supported"
0x1400013a0  lea     rax, qword_1400094D0
0x1400013a7  jz      short loc_1400013B8
0x1400013a9  cmp     [rax], ecx
0x1400013ab  jz      short loc_1400013BB
0x1400013ad  add     rax, 10h
0x1400013b1  cmp     qword ptr [rax+8], 0
0x1400013b6  jnz     short loc_1400013A9
0x1400013b8  xor     eax, eax
0x1400013ba  retn
0x1400013bb  mov     rax, [rax+8]
0x1400013bf  retn
```
