# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180007cdc`
- end: `0x180007d47`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180005fec`
- `0x18000b82c`
- `0x18000f834`
- `0x18000fc94`
- `0x1800113fc`
- `0x180015658`
- `0x18001664c`

## callees

- `0x180007cdc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r9
  __int64 result; // rax
  __int64 v5; // rax

  v3 = a1;
  if ( !a2 )
    return 2147942487LL;
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
    result = a2 == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = 2147942487LL;
  }
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180007cdc  xor     r10d, r10d
0x180007cdf  mov     r9, rcx
0x180007ce2  test    rdx, rdx
0x180007ce5  jz      short loc_180007D38
0x180007ce7  cmp     rdx, 7FFFFFFFh
0x180007cee  jbe     short loc_180007CF7
0x180007cf0  mov     eax, 80070057h
0x180007cf5  jmp     short loc_180007D42
0x180007cf7  mov     eax, 7FFFFFFEh
0x180007cfc  test    rax, rax
0x180007cff  jz      short loc_180007D1F
0x180007d01  movzx   ecx, word ptr [r8]
0x180007d05  test    cx, cx
0x180007d08  jz      short loc_180007D1F
0x180007d0a  mov     [r9], cx
0x180007d0e  add     r8, 2
0x180007d12  add     r9, 2
0x180007d16  dec     rax
0x180007d19  sub     rdx, 1
0x180007d1d  jnz     short loc_180007CFC
0x180007d1f  test    rdx, rdx
0x180007d22  lea     rcx, [r9-2]
0x180007d26  cmovnz  rcx, r9
0x180007d2a  neg     rdx
0x180007d2d  sbb     eax, eax
0x180007d2f  not     eax
0x180007d31  and     eax, 8007007Ah
0x180007d36  jmp     short loc_180007D42
0x180007d38  mov     eax, 80070057h
0x180007d3d  test    rdx, rdx
0x180007d40  jz      short locret_180007D46
0x180007d42  mov     [rcx], r10w
0x180007d46  retn
```
