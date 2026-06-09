# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x180009190`
- end: `0x180009220`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `144`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e6ec`
- `0x180010230`
- `0x1800123c0`
- `0x1800169c4`

## callees

- `0x180009190`

## pseudocode

```c
__int64 __fastcall StringCchCopyNW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        unsigned __int64 a4)
{
  __int64 result; // rax

  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    if ( a4 <= 0x7FFFFFFE )
    {
      while ( a4 && *a3 )
      {
        *a1++ = *a3++;
        --a4;
        if ( !--a2 )
        {
          result = 2147942522LL;
          *(a1 - 1) = 0;
          return result;
        }
      }
      result = 0;
      *a1 = 0;
    }
    else
    {
      result = 2147942487LL;
      *a1 = 0;
    }
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
0x180009190  mov     rax, r8
0x180009193  test    rdx, rdx
0x180009196  jz      short loc_18000920E
0x180009198  cmp     rdx, 7FFFFFFFh
0x18000919f  jbe     short loc_1800091A8
0x1800091a1  mov     eax, 80070057h
0x1800091a6  jmp     short loc_180009218
0x1800091a8  xor     r8d, r8d
0x1800091ab  cmp     r9, 7FFFFFFEh
0x1800091b2  jbe     short loc_1800091BE
0x1800091b4  mov     eax, 80070057h
0x1800091b9  mov     [rcx], r8w
0x1800091bd  retn
0x1800091be  mov     r11d, r8d
0x1800091c1  test    r9, r9
0x1800091c4  jz      short loc_180009206
0x1800091c6  movzx   r10d, word ptr [rax]
0x1800091ca  test    r10w, r10w
0x1800091ce  jz      short loc_1800091F7
0x1800091d0  mov     [rcx], r10w
0x1800091d4  add     rax, 2
0x1800091d8  add     rcx, 2
0x1800091dc  dec     r9
0x1800091df  sub     rdx, 1
0x1800091e3  jnz     short loc_1800091C1
0x1800091e5  sub     rcx, 2
0x1800091e9  mov     r11d, 8007007Ah
0x1800091ef  mov     eax, r11d
0x1800091f2  mov     [rcx], r8w
0x1800091f6  retn
0x1800091f7  test    rdx, rdx
0x1800091fa  jnz     short loc_180009206
0x1800091fc  sub     rcx, 2
0x180009200  mov     r11d, 8007007Ah
0x180009206  mov     eax, r11d
0x180009209  mov     [rcx], r8w
0x18000920d  retn
0x18000920e  mov     eax, 80070057h
0x180009213  test    rdx, rdx
0x180009216  jz      short locret_18000921F
0x180009218  xor     r8d, r8d
0x18000921b  mov     [rcx], r8w
0x18000921f  retn
```
