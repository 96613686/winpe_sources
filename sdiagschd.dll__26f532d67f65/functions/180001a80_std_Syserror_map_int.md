# std::_Syserror_map(int)

- ea: `0x180001a80`
- end: `0x180001aa8`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001770`
- `0x1800018e0`
- `0x180001950`

## callees

- `0x180001a80`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  _QWORD *v1; // rax

  v1 = &unk_18000E590;
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
0x180001a80  cmp     cs:off_18000E598, 0; "address family not supported"
0x180001a88  lea     rax, unk_18000E590
0x180001a8f  jz      short loc_180001AA0
0x180001a91  cmp     [rax], ecx
0x180001a93  jz      short loc_180001AA3
0x180001a95  add     rax, 10h
0x180001a99  cmp     qword ptr [rax+8], 0
0x180001a9e  jnz     short loc_180001A91
0x180001aa0  xor     eax, eax
0x180001aa2  retn
0x180001aa3  mov     rax, [rax+8]
0x180001aa7  retn
```
