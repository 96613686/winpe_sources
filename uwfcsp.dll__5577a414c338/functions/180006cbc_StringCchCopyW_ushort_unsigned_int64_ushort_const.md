# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180006cbc`
- end: `0x180006d27`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ff08`

## callees

- `0x180006cbc`

## pseudocode

```c
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
0x180006cbc  xor     r10d, r10d
0x180006cbf  mov     r9, rcx
0x180006cc2  test    rdx, rdx
0x180006cc5  jz      short loc_180006D18
0x180006cc7  cmp     rdx, 7FFFFFFFh
0x180006cce  jbe     short loc_180006CD7
0x180006cd0  mov     eax, 80070057h
0x180006cd5  jmp     short loc_180006D22
0x180006cd7  mov     eax, 7FFFFFFEh
0x180006cdc  test    rax, rax
0x180006cdf  jz      short loc_180006CFF
0x180006ce1  movzx   ecx, word ptr [r8]
0x180006ce5  test    cx, cx
0x180006ce8  jz      short loc_180006CFF
0x180006cea  mov     [r9], cx
0x180006cee  add     r8, 2
0x180006cf2  add     r9, 2
0x180006cf6  dec     rax
0x180006cf9  sub     rdx, 1
0x180006cfd  jnz     short loc_180006CDC
0x180006cff  test    rdx, rdx
0x180006d02  lea     rcx, [r9-2]
0x180006d06  cmovnz  rcx, r9
0x180006d0a  neg     rdx
0x180006d0d  sbb     eax, eax
0x180006d0f  not     eax
0x180006d11  and     eax, 8007007Ah
0x180006d16  jmp     short loc_180006D22
0x180006d18  mov     eax, 80070057h
0x180006d1d  test    rdx, rdx
0x180006d20  jz      short locret_180006D26
0x180006d22  mov     [rcx], r10w
0x180006d26  retn
```
