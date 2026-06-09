# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000b4a0`
- end: `0x18000b515`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `117`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180003f90`
- `0x180004f90`
- `0x1800053b0`
- `0x18000c158`
- `0x18000cc64`
- `0x18000e8a8`
- `0x18000ebec`
- `0x18000f440`
- `0x18000fa10`
- `0x18000fc9c`

## callees

- `0x18000b4a0`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r9
  __int64 v4; // rax
  unsigned int v5; // r11d
  __int64 result; // rax

  v3 = a1;
  if ( !a2 )
    return 2147942487LL;
  if ( a2 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  else
  {
    v4 = 2147483646;
    v5 = 0;
    while ( v4 && *a3 )
    {
      *v3++ = *a3++;
      --v4;
      if ( !--a2 )
      {
        --v3;
        v5 = -2147024774;
        break;
      }
    }
    *v3 = 0;
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18000b4a0  mov     r9, rcx
0x18000b4a3  test    rdx, rdx
0x18000b4a6  jz      short loc_18000B503
0x18000b4a8  cmp     rdx, 7FFFFFFFh
0x18000b4af  ja      short loc_18000B4FC
0x18000b4b1  xor     r10d, r10d
0x18000b4b4  mov     eax, 7FFFFFFEh
0x18000b4b9  mov     r11d, r10d
0x18000b4bc  nop     dword ptr [rax+00h]
0x18000b4c0  test    rax, rax
0x18000b4c3  jz      short loc_18000B4F4
0x18000b4c5  movzx   ecx, word ptr [r8]
0x18000b4c9  test    cx, cx
0x18000b4cc  jz      short loc_18000B4EF
0x18000b4ce  mov     [r9], cx
0x18000b4d2  add     r8, 2
0x18000b4d6  add     r9, 2
0x18000b4da  dec     rax
0x18000b4dd  sub     rdx, 1
0x18000b4e1  jnz     short loc_18000B4C0
0x18000b4e3  sub     r9, 2
0x18000b4e7  mov     r11d, 8007007Ah
0x18000b4ed  jmp     short loc_18000B4F4
0x18000b4ef  test    rdx, rdx
0x18000b4f2  jz      short loc_18000B4E3
0x18000b4f4  mov     [r9], r10w
0x18000b4f8  mov     eax, r11d
0x18000b4fb  retn
0x18000b4fc  mov     eax, 80070057h
0x18000b501  jmp     short loc_18000B50D
0x18000b503  mov     eax, 80070057h
0x18000b508  test    rdx, rdx
0x18000b50b  jz      short locret_18000B4FB
0x18000b50d  xor     r10d, r10d
0x18000b510  mov     [rcx], r10w
0x18000b514  retn
```
