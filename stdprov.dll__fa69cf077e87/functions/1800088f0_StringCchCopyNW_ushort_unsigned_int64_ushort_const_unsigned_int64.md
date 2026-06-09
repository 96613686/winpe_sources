# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x1800088f0`
- end: `0x180008961`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `113`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d330`
- `0x18000e110`
- `0x1800147e4`

## callees

- `0x1800088f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StringCchCopyNW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        unsigned __int64 a4)
{
  unsigned __int16 *v4; // rax
  __int64 result; // rax

  if ( !a2 )
    return 2147942487LL;
  if ( a2 > 0x7FFFFFFF || a4 > 0x7FFFFFFE )
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  else
  {
    do
    {
      if ( !a4 )
        break;
      if ( !*a3 )
        break;
      *a1++ = *a3++;
      --a4;
      --a2;
    }
    while ( a2 );
    v4 = a1 - 1;
    if ( a2 )
      v4 = a1;
    *v4 = 0;
    result = 2147942522LL;
    if ( a2 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800088f0  test    rdx, rdx
0x1800088f3  jz      short loc_18000894F
0x1800088f5  cmp     rdx, 7FFFFFFFh
0x1800088fc  ja      short loc_180008948
0x1800088fe  cmp     r9, 7FFFFFFEh
0x180008905  ja      short loc_180008948
0x180008907  test    r9, r9
0x18000890a  jz      short loc_180008929
0x18000890c  movzx   eax, word ptr [r8]
0x180008910  test    ax, ax
0x180008913  jz      short loc_180008929
0x180008915  mov     [rcx], ax
0x180008918  add     r8, 2
0x18000891c  add     rcx, 2
0x180008920  dec     r9
0x180008923  sub     rdx, 1
0x180008927  jnz     short loc_180008907
0x180008929  test    rdx, rdx
0x18000892c  lea     rax, [rcx-2]
0x180008930  cmovnz  rax, rcx
0x180008934  xor     r8d, r8d
0x180008937  test    rdx, rdx
0x18000893a  mov     [rax], r8w
0x18000893e  mov     eax, 8007007Ah
0x180008943  cmovnz  eax, r8d
0x180008947  retn
0x180008948  mov     eax, 80070057h
0x18000894d  jmp     short loc_180008959
0x18000894f  mov     eax, 80070057h
0x180008954  test    rdx, rdx
0x180008957  jz      short locret_180008947
0x180008959  xor     r8d, r8d
0x18000895c  mov     [rcx], r8w
0x180008960  retn
```
