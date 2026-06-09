# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005610`
- end: `0x18000567b`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800070b0`
- `0x180008238`
- `0x180009148`
- `0x180009600`
- `0x18000b6b4`
- `0x18000ca38`
- `0x18000cbfc`

## callees

- `0x180005610`

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
0x180005610  xor     r10d, r10d
0x180005613  mov     r9, rcx
0x180005616  test    rdx, rdx
0x180005619  jz      short loc_18000566C
0x18000561b  cmp     rdx, 7FFFFFFFh
0x180005622  jbe     short loc_18000562B
0x180005624  mov     eax, 80070057h
0x180005629  jmp     short loc_180005676
0x18000562b  mov     eax, 7FFFFFFEh
0x180005630  test    rax, rax
0x180005633  jz      short loc_180005653
0x180005635  movzx   ecx, word ptr [r8]
0x180005639  test    cx, cx
0x18000563c  jz      short loc_180005653
0x18000563e  mov     [r9], cx
0x180005642  add     r8, 2
0x180005646  add     r9, 2
0x18000564a  dec     rax
0x18000564d  sub     rdx, 1
0x180005651  jnz     short loc_180005630
0x180005653  test    rdx, rdx
0x180005656  lea     rcx, [r9-2]
0x18000565a  cmovnz  rcx, r9
0x18000565e  neg     rdx
0x180005661  sbb     eax, eax
0x180005663  not     eax
0x180005665  and     eax, 8007007Ah
0x18000566a  jmp     short loc_180005676
0x18000566c  mov     eax, 80070057h
0x180005671  test    rdx, rdx
0x180005674  jz      short locret_18000567A
0x180005676  mov     [rcx], r10w
0x18000567a  retn
```
