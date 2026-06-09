# RtlStringCchCopyW

- ea: `0x180001110`
- end: `0x18000117d`
- name: `RtlStringCchCopyW`
- size: `109`
- prototype: `__int64 __fastcall(_WORD *, unsigned __int64, _WORD *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001190`
- `0x180008d20`
- `0x1800126cc`
- `0x180013cd0`
- `0x180014a84`
- `0x1800156c0`

## callees

- `0x180001110`

## pseudocode

```c
__int64 __fastcall RtlStringCchCopyW(_WORD *a1, unsigned __int64 a2, _WORD *a3)
{
  _WORD *v3; // r9
  __int64 v4; // rax
  _WORD *v5; // rax
  __int64 result; // rax

  v3 = a1;
  if ( !a2 )
    return 3221225485LL;
  if ( a2 > 0x7FFFFFFF )
  {
    result = 3221225485LL;
    *a1 = 0;
  }
  else
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*a3 )
        break;
      *v3++ = *a3++;
      --v4;
      --a2;
    }
    while ( a2 );
    v5 = v3 - 1;
    if ( a2 )
      v5 = v3;
    *v5 = 0;
    result = 2147483653LL;
    if ( a2 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001110  mov     r9, rcx
0x180001113  test    rdx, rdx
0x180001116  jz      short loc_18000116C
0x180001118  cmp     rdx, 7FFFFFFFh
0x18000111f  ja      short loc_180001165
0x180001121  mov     eax, 7FFFFFFEh
0x180001126  test    rax, rax
0x180001129  jz      short loc_180001149
0x18000112b  movzx   ecx, word ptr [r8]
0x18000112f  test    cx, cx
0x180001132  jz      short loc_180001149
0x180001134  mov     [r9], cx
0x180001138  add     r8, 2
0x18000113c  add     r9, 2
0x180001140  dec     rax
0x180001143  sub     rdx, 1
0x180001147  jnz     short loc_180001126
0x180001149  test    rdx, rdx
0x18000114c  lea     rax, [r9-2]
0x180001150  cmovnz  rax, r9
0x180001154  xor     ecx, ecx
0x180001156  test    rdx, rdx
0x180001159  mov     [rax], cx
0x18000115c  mov     eax, 80000005h
0x180001161  cmovnz  eax, ecx
0x180001164  retn
0x180001165  mov     eax, 0C000000Dh
0x18000116a  jmp     short loc_180001176
0x18000116c  mov     eax, 0C000000Dh
0x180001171  test    rdx, rdx
0x180001174  jz      short locret_180001164
0x180001176  xor     ecx, ecx
0x180001178  mov     [r9], cx
0x18000117c  retn
```
