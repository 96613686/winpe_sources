# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005280`
- end: `0x1800052ee`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `110`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cb2c`
- `0x18000d384`
- `0x18000d870`
- `0x1800105bc`
- `0x180014cc0`
- `0x180016e10`
- `0x18001a854`

## callees

- `0x180005280`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r9
  __int64 v4; // rax
  unsigned __int16 *v5; // rax
  __int64 result; // rax

  v3 = a1;
  if ( !a2 )
    return 2147942487LL;
  if ( a2 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
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
    result = 2147942522LL;
    if ( a2 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005280  mov     r9, rcx
0x180005283  test    rdx, rdx
0x180005286  jz      short loc_1800052DD
0x180005288  cmp     rdx, 7FFFFFFFh
0x18000528f  ja      short loc_1800052D6
0x180005291  mov     eax, 7FFFFFFEh
0x180005296  test    rax, rax
0x180005299  jz      short loc_1800052B9
0x18000529b  movzx   ecx, word ptr [r8]
0x18000529f  test    cx, cx
0x1800052a2  jz      short loc_1800052B9
0x1800052a4  mov     [r9], cx
0x1800052a8  add     r8, 2
0x1800052ac  add     r9, 2
0x1800052b0  dec     rax
0x1800052b3  sub     rdx, 1
0x1800052b7  jnz     short loc_180005296
0x1800052b9  test    rdx, rdx
0x1800052bc  lea     rax, [r9-2]
0x1800052c0  cmovnz  rax, r9
0x1800052c4  xor     ecx, ecx
0x1800052c6  test    rdx, rdx
0x1800052c9  mov     [rax], cx
0x1800052cc  mov     eax, 8007007Ah
0x1800052d1  cmovnz  eax, ecx
0x1800052d4  retn
0x1800052d6  mov     eax, 80070057h
0x1800052db  jmp     short loc_1800052E7
0x1800052dd  mov     eax, 80070057h
0x1800052e2  test    rdx, rdx
0x1800052e5  jz      short locret_1800052D4
0x1800052e7  xor     ecx, ecx
0x1800052e9  mov     [r9], cx
0x1800052ed  retn
```
