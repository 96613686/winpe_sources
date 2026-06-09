# StringCbCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x180009430`
- end: `0x18000949b`
- name: `?StringCbCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014030`

## callees

- `0x180009430`

## pseudocode

```c
__int64 __fastcall StringCbCopyNW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // r9
  unsigned int v7; // r11d

  v4 = a2 >> 1;
  if ( v4 - 1 > 0x7FFFFFFE )
    return 2147942487LL;
  v5 = a4 >> 1;
  if ( v5 > 0x7FFFFFFE )
  {
    *a1 = 0;
    return 2147942487LL;
  }
  v7 = 0;
  while ( v5 )
  {
    if ( !*a3 )
    {
      if ( v4 )
        break;
LABEL_11:
      --a1;
      v7 = -2147024774;
      break;
    }
    *a1++ = *a3++;
    --v5;
    if ( !--v4 )
      goto LABEL_11;
  }
  *a1 = 0;
  return v7;
}

```

## disassembly

```asm
0x180009430  shr     rdx, 1
0x180009433  lea     rax, [rdx-1]
0x180009437  cmp     rax, 7FFFFFFEh
0x18000943d  ja      short loc_180009452
0x18000943f  shr     r9, 1
0x180009442  xor     r10d, r10d
0x180009445  cmp     r9, 7FFFFFFEh
0x18000944c  jbe     short loc_180009458
0x18000944e  mov     [rcx], r10w
0x180009452  mov     eax, 80070057h
0x180009457  retn
0x180009458  mov     r11d, r10d
0x18000945b  nop     dword ptr [rax+rax+00h]
0x180009460  test    r9, r9
0x180009463  jz      short loc_180009493
0x180009465  movzx   eax, word ptr [r8]
0x180009469  test    ax, ax
0x18000946c  jz      short loc_180009484
0x18000946e  mov     [rcx], ax
0x180009471  add     r8, 2
0x180009475  add     rcx, 2
0x180009479  dec     r9
0x18000947c  sub     rdx, 1
0x180009480  jnz     short loc_180009460
0x180009482  jmp     short loc_180009489
0x180009484  test    rdx, rdx
0x180009487  jnz     short loc_180009493
0x180009489  sub     rcx, 2
0x18000948d  mov     r11d, 8007007Ah
0x180009493  mov     [rcx], r10w
0x180009497  mov     eax, r11d
0x18000949a  retn
```
