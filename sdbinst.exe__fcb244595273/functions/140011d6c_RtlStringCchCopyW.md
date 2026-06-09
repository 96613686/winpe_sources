# RtlStringCchCopyW

- ea: `0x140011d6c`
- end: `0x140011dd7`
- name: `RtlStringCchCopyW`
- size: `107`
- prototype: `__int64(_WORD *, unsigned __int64, _WORD *, ...)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f158`
- `0x14000f28c`
- `0x1400100c4`
- `0x1400103d8`
- `0x140010d44`
- `0x140011184`

## callees

- `0x140011d6c`

## pseudocode

```c
__int64 RtlStringCchCopyW(_WORD *a1, unsigned __int64 a2, _WORD *a3, ...)
{
  _WORD *v3; // r9
  __int64 result; // rax
  __int64 v5; // rax

  v3 = a1;
  if ( !a2 )
    return 3221225485LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*a3 )
        break;
      *v3++ = *a3++;
      --v5;
      --a2;
    }
    while ( a2 );
    a1 = v3 - 1;
    if ( a2 )
      a1 = v3;
    result = a2 == 0 ? 0x80000005 : 0;
  }
  else
  {
    result = 3221225485LL;
  }
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x140011d6c  xor     r10d, r10d
0x140011d6f  mov     r9, rcx
0x140011d72  test    rdx, rdx
0x140011d75  jz      short loc_140011DC8
0x140011d77  cmp     rdx, 7FFFFFFFh
0x140011d7e  jbe     short loc_140011D87
0x140011d80  mov     eax, 0C000000Dh
0x140011d85  jmp     short loc_140011DD2
0x140011d87  mov     eax, 7FFFFFFEh
0x140011d8c  test    rax, rax
0x140011d8f  jz      short loc_140011DAF
0x140011d91  movzx   ecx, word ptr [r8]
0x140011d95  test    cx, cx
0x140011d98  jz      short loc_140011DAF
0x140011d9a  mov     [r9], cx
0x140011d9e  add     r8, 2
0x140011da2  add     r9, 2
0x140011da6  dec     rax
0x140011da9  sub     rdx, 1
0x140011dad  jnz     short loc_140011D8C
0x140011daf  test    rdx, rdx
0x140011db2  lea     rcx, [r9-2]
0x140011db6  cmovnz  rcx, r9
0x140011dba  neg     rdx
0x140011dbd  sbb     eax, eax
0x140011dbf  not     eax
0x140011dc1  and     eax, 80000005h
0x140011dc6  jmp     short loc_140011DD2
0x140011dc8  mov     eax, 0C000000Dh
0x140011dcd  test    rdx, rdx
0x140011dd0  jz      short locret_140011DD6
0x140011dd2  mov     [rcx], r10w
0x140011dd6  retn
```
