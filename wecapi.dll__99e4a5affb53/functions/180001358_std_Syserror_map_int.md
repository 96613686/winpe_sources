# std::_Syserror_map(int)

- ea: `0x180001358`
- end: `0x180001380`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800022b0`
- `0x180002420`
- `0x180002490`

## callees

- `0x180001358`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_18000E4D0;
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
0x180001358  cmp     cs:off_18000E4D8, 0; "address family not supported"
0x180001360  lea     rax, qword_18000E4D0
0x180001367  jz      short loc_180001378
0x180001369  cmp     [rax], ecx
0x18000136b  jz      short loc_18000137B
0x18000136d  add     rax, 10h
0x180001371  cmp     qword ptr [rax+8], 0
0x180001376  jnz     short loc_180001369
0x180001378  xor     eax, eax
0x18000137a  retn
0x18000137b  mov     rax, [rax+8]
0x18000137f  retn
```
