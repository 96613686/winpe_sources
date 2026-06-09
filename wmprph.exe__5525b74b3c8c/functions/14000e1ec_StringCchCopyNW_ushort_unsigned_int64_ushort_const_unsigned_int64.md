# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x14000e1ec`
- end: `0x14000e269`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `125`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000dcf8`

## callees

- `0x14000e1ec`

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
0x14000e1ec  mov     [rsp+arg_0], rbx
0x14000e1f1  xor     ebx, ebx
0x14000e1f3  mov     r10, rdx
0x14000e1f6  mov     r11, rcx
0x14000e1f9  test    rdx, rdx
0x14000e1fc  jz      short loc_14000E254
0x14000e1fe  cmp     rdx, 7FFFFFFFh
0x14000e205  jbe     short loc_14000E20E
0x14000e207  mov     edx, 80070057h
0x14000e20c  jmp     short loc_14000E25E
0x14000e20e  cmp     r9, 7FFFFFFEh
0x14000e215  ja      short loc_14000E207
0x14000e217  test    r9, r9
0x14000e21a  jz      short loc_14000E23A
0x14000e21c  movzx   eax, word ptr [r8]
0x14000e220  test    ax, ax
0x14000e223  jz      short loc_14000E23A
0x14000e225  mov     [r11], ax
0x14000e229  add     r8, 2
0x14000e22d  add     r11, 2
0x14000e231  dec     r9
0x14000e234  sub     r10, 1
0x14000e238  jnz     short loc_14000E217
0x14000e23a  test    r10, r10
0x14000e23d  lea     rcx, [r11-2]
0x14000e241  cmovnz  rcx, r11
0x14000e245  neg     r10
0x14000e248  sbb     edx, edx
0x14000e24a  not     edx
0x14000e24c  and     edx, 8007007Ah
0x14000e252  jmp     short loc_14000E25E
0x14000e254  mov     edx, 80070057h
0x14000e259  test    r10, r10
0x14000e25c  jz      short loc_14000E261
0x14000e25e  mov     [rcx], bx
0x14000e261  mov     rbx, [rsp+arg_0]
0x14000e266  mov     eax, edx
0x14000e268  retn
```
