# RtlStringCchCopyW

- ea: `0x180001cd4`
- end: `0x180001d3f`
- name: `RtlStringCchCopyW`
- size: `107`
- prototype: `__int64 __fastcall(_WORD *, unsigned __int64, _WORD *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002640`
- `0x1800073c4`
- `0x180007fb0`
- `0x18000bc68`
- `0x18001188c`

## callees

- `0x180001cd4`

## pseudocode

```c
__int64 __fastcall RtlStringCchCopyW(_WORD *a1, unsigned __int64 a2, _WORD *a3)
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
0x180001cd4  xor     r10d, r10d
0x180001cd7  mov     r9, rcx
0x180001cda  test    rdx, rdx
0x180001cdd  jz      short loc_180001D30
0x180001cdf  cmp     rdx, 7FFFFFFFh
0x180001ce6  jbe     short loc_180001CEF
0x180001ce8  mov     eax, 0C000000Dh
0x180001ced  jmp     short loc_180001D3A
0x180001cef  mov     eax, 7FFFFFFEh
0x180001cf4  test    rax, rax
0x180001cf7  jz      short loc_180001D17
0x180001cf9  movzx   ecx, word ptr [r8]
0x180001cfd  test    cx, cx
0x180001d00  jz      short loc_180001D17
0x180001d02  mov     [r9], cx
0x180001d06  add     r8, 2
0x180001d0a  add     r9, 2
0x180001d0e  dec     rax
0x180001d11  sub     rdx, 1
0x180001d15  jnz     short loc_180001CF4
0x180001d17  test    rdx, rdx
0x180001d1a  lea     rcx, [r9-2]
0x180001d1e  cmovnz  rcx, r9
0x180001d22  neg     rdx
0x180001d25  sbb     eax, eax
0x180001d27  not     eax
0x180001d29  and     eax, 80000005h
0x180001d2e  jmp     short loc_180001D3A
0x180001d30  mov     eax, 0C000000Dh
0x180001d35  test    rdx, rdx
0x180001d38  jz      short locret_180001D3E
0x180001d3a  mov     [rcx], r10w
0x180001d3e  retn
```
