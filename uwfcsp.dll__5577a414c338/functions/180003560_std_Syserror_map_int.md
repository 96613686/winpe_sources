# std::_Syserror_map(int)

- ea: `0x180003560`
- end: `0x180003588`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003240`
- `0x1800033c0`
- `0x180003430`

## callees

- `0x180003560`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_18001C590;
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
0x180003560  cmp     cs:off_18001C598, 0; "address family not supported"
0x180003568  lea     rax, qword_18001C590
0x18000356f  jz      short loc_180003580
0x180003571  cmp     [rax], ecx
0x180003573  jz      short loc_180003583
0x180003575  add     rax, 10h
0x180003579  cmp     qword ptr [rax+8], 0
0x18000357e  jnz     short loc_180003571
0x180003580  xor     eax, eax
0x180003582  retn
0x180003583  mov     rax, [rax+8]
0x180003587  retn
```
