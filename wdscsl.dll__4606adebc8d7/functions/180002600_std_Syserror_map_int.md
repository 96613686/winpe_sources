# std::_Syserror_map(int)

- ea: `0x180002600`
- end: `0x180002628`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800022f0`
- `0x180002460`
- `0x1800024d0`

## callees

- `0x180002600`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_18000F5A0;
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
0x180002600  cmp     cs:off_18000F5A8, 0; "address family not supported"
0x180002608  lea     rax, qword_18000F5A0
0x18000260f  jz      short loc_180002620
0x180002611  cmp     [rax], ecx
0x180002613  jz      short loc_180002623
0x180002615  add     rax, 10h
0x180002619  cmp     qword ptr [rax+8], 0
0x18000261e  jnz     short loc_180002611
0x180002620  xor     eax, eax
0x180002622  retn
0x180002623  mov     rax, [rax+8]
0x180002627  retn
```
