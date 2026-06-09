# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x180028378`
- end: `0x1800283f5`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `125`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180026b70`

## callees

- `0x180028378`

## pseudocode

```c
__int64 __fastcall StringCchCopyNW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        unsigned __int64 a4)
{
  unsigned __int64 v4; // r10
  unsigned __int16 *v5; // r11
  unsigned int v6; // edx

  v4 = a2;
  v5 = a1;
  if ( a2 )
  {
    if ( a2 > 0x7FFFFFFF || a4 > 0x7FFFFFFE )
    {
      v6 = -2147024809;
    }
    else
    {
      do
      {
        if ( !a4 )
          break;
        if ( !*a3 )
          break;
        *v5++ = *a3++;
        --a4;
        --v4;
      }
      while ( v4 );
      a1 = v5 - 1;
      if ( v4 )
        a1 = v5;
      v6 = v4 == 0 ? 0x8007007A : 0;
    }
    *a1 = 0;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x180028378  mov     [rsp+arg_0], rbx
0x18002837d  xor     ebx, ebx
0x18002837f  mov     r10, rdx
0x180028382  mov     r11, rcx
0x180028385  test    rdx, rdx
0x180028388  jz      short loc_1800283E0
0x18002838a  cmp     rdx, 7FFFFFFFh
0x180028391  jbe     short loc_18002839A
0x180028393  mov     edx, 80070057h
0x180028398  jmp     short loc_1800283EA
0x18002839a  cmp     r9, 7FFFFFFEh
0x1800283a1  ja      short loc_180028393
0x1800283a3  test    r9, r9
0x1800283a6  jz      short loc_1800283C6
0x1800283a8  movzx   eax, word ptr [r8]
0x1800283ac  test    ax, ax
0x1800283af  jz      short loc_1800283C6
0x1800283b1  mov     [r11], ax
0x1800283b5  add     r8, 2
0x1800283b9  add     r11, 2
0x1800283bd  dec     r9
0x1800283c0  sub     r10, 1
0x1800283c4  jnz     short loc_1800283A3
0x1800283c6  test    r10, r10
0x1800283c9  lea     rcx, [r11-2]
0x1800283cd  cmovnz  rcx, r11
0x1800283d1  neg     r10
0x1800283d4  sbb     edx, edx
0x1800283d6  not     edx
0x1800283d8  and     edx, 8007007Ah
0x1800283de  jmp     short loc_1800283EA
0x1800283e0  mov     edx, 80070057h
0x1800283e5  test    r10, r10
0x1800283e8  jz      short loc_1800283ED
0x1800283ea  mov     [rcx], bx
0x1800283ed  mov     rbx, [rsp+arg_0]
0x1800283f2  mov     eax, edx
0x1800283f4  retn
```
