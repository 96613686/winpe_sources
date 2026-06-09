# std::_Winerror_map(int)

- ea: `0x180001990`
- end: `0x1800019b8`
- name: `?_Winerror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800018c0`

## callees

- `0x180001990`

## pseudocode

```c
const char *__fastcall std::_Winerror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_1800060E0;
  if ( !"permission denied" )
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
0x180001990  cmp     cs:off_1800060E8, 0; "permission denied"
0x180001998  lea     rax, qword_1800060E0
0x18000199f  jz      short loc_1800019B0
0x1800019a1  cmp     [rax], ecx
0x1800019a3  jz      short loc_1800019B3
0x1800019a5  add     rax, 10h
0x1800019a9  cmp     qword ptr [rax+8], 0
0x1800019ae  jnz     short loc_1800019A1
0x1800019b0  xor     eax, eax
0x1800019b2  retn
0x1800019b3  mov     rax, [rax+8]
0x1800019b7  retn
```
