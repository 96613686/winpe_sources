# std::_Syserror_map(int)

- ea: `0x1800023f0`
- end: `0x180002418`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800020e0`
- `0x180002250`
- `0x1800022c0`

## callees

- `0x1800023f0`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_1800125A0;
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
0x1800023f0  cmp     cs:off_1800125A8, 0; "address family not supported"
0x1800023f8  lea     rax, qword_1800125A0
0x1800023ff  jz      short loc_180002410
0x180002401  cmp     [rax], ecx
0x180002403  jz      short loc_180002413
0x180002405  add     rax, 10h
0x180002409  cmp     qword ptr [rax+8], 0
0x18000240e  jnz     short loc_180002401
0x180002410  xor     eax, eax
0x180002412  retn
0x180002413  mov     rax, [rax+8]
0x180002417  retn
```
