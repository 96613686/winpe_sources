# RtlStringCchCopyNW

- ea: `0x180001464`
- end: `0x1800014e1`
- name: `RtlStringCchCopyNW`
- size: `125`
- prototype: `__int64 __fastcall(_WORD *, unsigned __int64, _WORD *, unsigned __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001764`
- `0x18000952c`
- `0x180014fa0`

## callees

- `0x180001464`

## pseudocode

```c
__int64 __fastcall RtlStringCchCopyNW(_WORD *a1, unsigned __int64 a2, _WORD *a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // r10
  _WORD *v5; // r11
  unsigned int v6; // edx

  v4 = a2;
  v5 = a1;
  if ( a2 )
  {
    if ( a2 > 0x7FFFFFFF || a4 > 0x7FFFFFFE )
    {
      v6 = -1073741811;
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
      v6 = v4 == 0 ? 0x80000005 : 0;
    }
    *a1 = 0;
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v6;
}

```

## disassembly

```asm
0x180001464  mov     [rsp+arg_0], rbx
0x180001469  xor     ebx, ebx
0x18000146b  mov     r10, rdx
0x18000146e  mov     r11, rcx
0x180001471  test    rdx, rdx
0x180001474  jz      short loc_1800014CC
0x180001476  cmp     rdx, 7FFFFFFFh
0x18000147d  jbe     short loc_180001486
0x18000147f  mov     edx, 0C000000Dh
0x180001484  jmp     short loc_1800014D6
0x180001486  cmp     r9, 7FFFFFFEh
0x18000148d  ja      short loc_18000147F
0x18000148f  test    r9, r9
0x180001492  jz      short loc_1800014B2
0x180001494  movzx   eax, word ptr [r8]
0x180001498  test    ax, ax
0x18000149b  jz      short loc_1800014B2
0x18000149d  mov     [r11], ax
0x1800014a1  add     r8, 2
0x1800014a5  add     r11, 2
0x1800014a9  dec     r9
0x1800014ac  sub     r10, 1
0x1800014b0  jnz     short loc_18000148F
0x1800014b2  test    r10, r10
0x1800014b5  lea     rcx, [r11-2]
0x1800014b9  cmovnz  rcx, r11
0x1800014bd  neg     r10
0x1800014c0  sbb     edx, edx
0x1800014c2  not     edx
0x1800014c4  and     edx, 80000005h
0x1800014ca  jmp     short loc_1800014D6
0x1800014cc  mov     edx, 0C000000Dh
0x1800014d1  test    r10, r10
0x1800014d4  jz      short loc_1800014D9
0x1800014d6  mov     [rcx], bx
0x1800014d9  mov     rbx, [rsp+arg_0]
0x1800014de  mov     eax, edx
0x1800014e0  retn
```
