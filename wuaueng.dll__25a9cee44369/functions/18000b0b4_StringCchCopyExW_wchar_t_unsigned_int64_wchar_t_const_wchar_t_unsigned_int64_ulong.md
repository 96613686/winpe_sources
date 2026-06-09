# StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)

- ea: `0x18000b0b4`
- end: `0x18000b18f`
- name: `?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z`
- size: `219`
- prototype: `__int64 __fastcall(wchar_t *, unsigned __int64, const wchar_t *, wchar_t **)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000de40`
- `0x18000e460`

## callees

- `0x18000b0b4`

## pseudocode

```c
__int64 __fastcall StringCchCopyExW(wchar_t *a1, unsigned __int64 a2, const wchar_t *a3, wchar_t **a4)
{
  unsigned __int64 v5; // r10
  wchar_t *v6; // r11
  unsigned int v7; // edx
  const WCHAR *v8; // rcx
  wchar_t *v9; // r8
  unsigned __int64 v10; // rdx
  __int64 v11; // r9
  signed __int64 v12; // rcx
  wchar_t v13; // ax
  wchar_t *v14; // rax
  __int64 v15; // rax

  v5 = a2;
  v6 = a1;
  if ( (a1 || !a2) && a2 <= 0x7FFFFFFF )
  {
    v8 = &OutputString;
    v7 = 0;
    if ( a3 )
      v8 = a3;
    if ( v5 )
    {
      v9 = v6;
      v10 = 2147483646 - v5;
      v11 = 0;
      v12 = (char *)v8 - (char *)v6;
      do
      {
        if ( !(v10 + v5) )
          break;
        v13 = *(wchar_t *)((char *)v9 + v12);
        if ( !v13 )
          break;
        *v9 = v13;
        ++v11;
        ++v9;
        --v5;
      }
      while ( v5 );
      v14 = v9 - 1;
      v7 = v5 == 0 ? 0x8007007A : 0;
      if ( v5 )
        v14 = v9;
      *v14 = 0;
      v15 = v11 - 1;
      if ( v5 )
        v15 = v11;
      v6 += v15;
    }
    else if ( *v8 )
    {
      if ( !v6 )
        return (unsigned int)-2147024809;
      v7 = -2147024774;
    }
    if ( a4 )
      *a4 = v6;
  }
  else
  {
    v7 = -2147024809;
    if ( v5 )
      *a1 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x18000b0b4  mov     [rsp+arg_10], rbx
0x18000b0b9  push    rdi
0x18000b0ba  xor     edi, edi
0x18000b0bc  mov     rbx, r9
0x18000b0bf  mov     r10, rdx
0x18000b0c2  mov     r11, rcx
0x18000b0c5  test    rcx, rcx
0x18000b0c8  jnz     short loc_18000B0CF
0x18000b0ca  test    rdx, rdx
0x18000b0cd  jnz     short loc_18000B0D8
0x18000b0cf  cmp     r10, 7FFFFFFFh
0x18000b0d6  jbe     short loc_18000B0EE
0x18000b0d8  mov     edx, 80070057h
0x18000b0dd  test    r10, r10
0x18000b0e0  jz      loc_18000B186
0x18000b0e6  mov     [rcx], di
0x18000b0e9  jmp     loc_18000B186
0x18000b0ee  test    r8, r8
0x18000b0f1  lea     rcx, OutputString
0x18000b0f8  mov     edx, edi
0x18000b0fa  cmovnz  rcx, r8
0x18000b0fe  test    r10, r10
0x18000b101  jnz     short loc_18000B11B
0x18000b103  cmp     [rcx], di
0x18000b106  jz      short loc_18000B17E
0x18000b108  test    r11, r11
0x18000b10b  jnz     short loc_18000B114
0x18000b10d  mov     edx, 80070057h
0x18000b112  jmp     short loc_18000B186
0x18000b114  mov     edx, 8007007Ah
0x18000b119  jmp     short loc_18000B17E
0x18000b11b  mov     edx, 7FFFFFFEh
0x18000b120  mov     r8, r11
0x18000b123  sub     rdx, r10
0x18000b126  mov     r9, rdi
0x18000b129  sub     rcx, r11
0x18000b12c  lea     rax, [rdx+r10]
0x18000b130  test    rax, rax
0x18000b133  jz      short loc_18000B150
0x18000b135  movzx   eax, word ptr [rcx+r8]
0x18000b13a  test    ax, ax
0x18000b13d  jz      short loc_18000B150
0x18000b13f  mov     [r8], ax
0x18000b143  inc     r9
0x18000b146  add     r8, 2
0x18000b14a  sub     r10, 1
0x18000b14e  jnz     short loc_18000B12C
0x18000b150  mov     rax, r10
0x18000b153  mov     edx, 8007007Ah
0x18000b158  neg     rax
0x18000b15b  lea     rax, [r8-2]
0x18000b15f  sbb     ecx, ecx
0x18000b161  not     ecx
0x18000b163  and     edx, ecx
0x18000b165  test    r10, r10
0x18000b168  cmovnz  rax, r8
0x18000b16c  mov     [rax], di
0x18000b16f  lea     rax, [r9-1]
0x18000b173  cmovnz  rax, r9
0x18000b177  lea     rcx, [r11+rax*2]
0x18000b17b  mov     r11, rcx
0x18000b17e  test    rbx, rbx
0x18000b181  jz      short loc_18000B186
0x18000b183  mov     [rbx], r11
0x18000b186  mov     rbx, [rsp+8+arg_10]
0x18000b18b  mov     eax, edx
0x18000b18d  pop     rdi
0x18000b18e  retn
```
