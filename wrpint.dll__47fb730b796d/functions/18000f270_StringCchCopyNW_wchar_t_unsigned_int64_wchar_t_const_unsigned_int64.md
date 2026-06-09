# StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)

- ea: `0x18000f270`
- end: `0x18000f2ed`
- name: `?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z`
- size: `125`
- prototype: `__int64 __fastcall(wchar_t *, unsigned __int64, const wchar_t *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800138a0`
- `0x180014054`

## callees

- `0x18000f270`

## pseudocode

```c
__int64 __fastcall StringCchCopyNW(wchar_t *a1, unsigned __int64 a2, wchar_t *a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // r10
  wchar_t *v5; // r11
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
0x18000f270  mov     [rsp+arg_0], rbx
0x18000f275  xor     ebx, ebx
0x18000f277  mov     r10, rdx
0x18000f27a  mov     r11, rcx
0x18000f27d  test    rdx, rdx
0x18000f280  jz      short loc_18000F2D8
0x18000f282  cmp     rdx, 7FFFFFFFh
0x18000f289  jbe     short loc_18000F292
0x18000f28b  mov     edx, 80070057h
0x18000f290  jmp     short loc_18000F2E2
0x18000f292  cmp     r9, 7FFFFFFEh
0x18000f299  ja      short loc_18000F28B
0x18000f29b  test    r9, r9
0x18000f29e  jz      short loc_18000F2BE
0x18000f2a0  movzx   eax, word ptr [r8]
0x18000f2a4  test    ax, ax
0x18000f2a7  jz      short loc_18000F2BE
0x18000f2a9  mov     [r11], ax
0x18000f2ad  add     r8, 2
0x18000f2b1  add     r11, 2
0x18000f2b5  dec     r9
0x18000f2b8  sub     r10, 1
0x18000f2bc  jnz     short loc_18000F29B
0x18000f2be  test    r10, r10
0x18000f2c1  lea     rcx, [r11-2]
0x18000f2c5  cmovnz  rcx, r11
0x18000f2c9  neg     r10
0x18000f2cc  sbb     edx, edx
0x18000f2ce  not     edx
0x18000f2d0  and     edx, 8007007Ah
0x18000f2d6  jmp     short loc_18000F2E2
0x18000f2d8  mov     edx, 80070057h
0x18000f2dd  test    r10, r10
0x18000f2e0  jz      short loc_18000F2E5
0x18000f2e2  mov     [rcx], bx
0x18000f2e5  mov     rbx, [rsp+arg_0]
0x18000f2ea  mov     eax, edx
0x18000f2ec  retn
```
