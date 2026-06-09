# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005d40`
- end: `0x180005daf`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `111`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001210`
- `0x18000bb60`
- `0x18000d4b8`

## callees

- `0x180005d40`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  __int64 result; // rax
  __int64 v4; // rax
  unsigned __int16 *v5; // rax

  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*a3 )
        break;
      *a1++ = *a3++;
      --v4;
      --a2;
    }
    while ( a2 );
    v5 = a1 - 1;
    if ( a2 )
      v5 = a1;
    *v5 = 0;
    result = 2147942522LL;
    if ( a2 )
      return 0;
  }
  else
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005d40  test    rdx, rdx
0x180005d43  jz      short loc_180005D9D
0x180005d45  cmp     rdx, 7FFFFFFFh
0x180005d4c  jbe     short loc_180005D55
0x180005d4e  mov     eax, 80070057h
0x180005d53  jmp     short loc_180005DA7
0x180005d55  mov     eax, 7FFFFFFEh
0x180005d5a  test    rax, rax
0x180005d5d  jz      short loc_180005D7E
0x180005d5f  movzx   r9d, word ptr [r8]
0x180005d63  test    r9w, r9w
0x180005d67  jz      short loc_180005D7E
0x180005d69  mov     [rcx], r9w
0x180005d6d  add     r8, 2
0x180005d71  add     rcx, 2
0x180005d75  dec     rax
0x180005d78  sub     rdx, 1
0x180005d7c  jnz     short loc_180005D5A
0x180005d7e  test    rdx, rdx
0x180005d81  lea     rax, [rcx-2]
0x180005d85  cmovnz  rax, rcx
0x180005d89  xor     r8d, r8d
0x180005d8c  test    rdx, rdx
0x180005d8f  mov     [rax], r8w
0x180005d93  mov     eax, 8007007Ah
0x180005d98  cmovnz  eax, r8d
0x180005d9c  retn
0x180005d9d  mov     eax, 80070057h
0x180005da2  test    rdx, rdx
0x180005da5  jz      short locret_180005DAE
0x180005da7  xor     r8d, r8d
0x180005daa  mov     [rcx], r8w
0x180005dae  retn
```
