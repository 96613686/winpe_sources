# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x18002090c`
- end: `0x18002098a`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `126`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001fa70`

## callees

- `0x18002090c`

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
0x18002090c  mov     [rsp+arg_0], rbx
0x180020911  xor     ebx, ebx
0x180020913  mov     r10, rdx
0x180020916  mov     r11, rcx
0x180020919  test    rdx, rdx
0x18002091c  jz      short loc_180020974
0x18002091e  cmp     rdx, 7FFFFFFFh
0x180020925  jbe     short loc_18002092E
0x180020927  mov     edx, 80070057h
0x18002092c  jmp     short loc_18002097E
0x18002092e  cmp     r9, 7FFFFFFEh
0x180020935  ja      short loc_180020927
0x180020937  test    r9, r9
0x18002093a  jz      short loc_18002095A
0x18002093c  movzx   eax, word ptr [r8]
0x180020940  test    ax, ax
0x180020943  jz      short loc_18002095A
0x180020945  mov     [r11], ax
0x180020949  add     r8, 2
0x18002094d  add     r11, 2
0x180020951  dec     r9
0x180020954  sub     r10, 1
0x180020958  jnz     short loc_180020937
0x18002095a  test    r10, r10
0x18002095d  lea     rcx, [r11-2]
0x180020961  cmovnz  rcx, r11
0x180020965  neg     r10
0x180020968  sbb     edx, edx
0x18002096a  not     edx
0x18002096c  and     edx, 8007007Ah
0x180020972  jmp     short loc_18002097E
0x180020974  mov     edx, 80070057h
0x180020979  test    r10, r10
0x18002097c  jz      short loc_180020981
0x18002097e  mov     [rcx], bx
0x180020981  mov     rbx, [rsp+arg_0]
0x180020986  mov     eax, edx
0x180020988  retn
```
