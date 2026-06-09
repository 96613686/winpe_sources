# std::_Syserror_map(int)

- ea: `0x180002340`
- end: `0x180002368`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002020`
- `0x1800021a0`
- `0x180002210`

## callees

- `0x180002340`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_1800075A0;
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
0x180002340  cmp     cs:off_1800075A8, 0; "address family not supported"
0x180002348  lea     rax, qword_1800075A0
0x18000234f  jz      short loc_180002360
0x180002351  cmp     [rax], ecx
0x180002353  jz      short loc_180002363
0x180002355  add     rax, 10h
0x180002359  cmp     qword ptr [rax+8], 0
0x18000235e  jnz     short loc_180002351
0x180002360  xor     eax, eax
0x180002362  retn
0x180002363  mov     rax, [rax+8]
0x180002367  retn
```
