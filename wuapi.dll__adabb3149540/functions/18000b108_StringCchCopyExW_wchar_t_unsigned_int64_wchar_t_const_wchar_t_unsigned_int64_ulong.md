# StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)

- ea: `0x18000b108`
- end: `0x18000b1e3`
- name: `?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z`
- size: `219`
- prototype: `__int64 __fastcall(wchar_t *, unsigned __int64, const wchar_t *, wchar_t **, unsigned __int64 *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ddcc`
- `0x18000e3ec`

## callees

- `0x18000b108`

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
0x18000b108  mov     [rsp+arg_10], rbx
0x18000b10d  push    rdi
0x18000b10e  xor     edi, edi
0x18000b110  mov     rbx, r9
0x18000b113  mov     r10, rdx
0x18000b116  mov     r11, rcx
0x18000b119  test    rcx, rcx
0x18000b11c  jnz     short loc_18000B123
0x18000b11e  test    rdx, rdx
0x18000b121  jnz     short loc_18000B12C
0x18000b123  cmp     r10, 7FFFFFFFh
0x18000b12a  jbe     short loc_18000B142
0x18000b12c  mov     edx, 80070057h
0x18000b131  test    r10, r10
0x18000b134  jz      loc_18000B1DA
0x18000b13a  mov     [rcx], di
0x18000b13d  jmp     loc_18000B1DA
0x18000b142  test    r8, r8
0x18000b145  lea     rcx, OutputString
0x18000b14c  mov     edx, edi
0x18000b14e  cmovnz  rcx, r8
0x18000b152  test    r10, r10
0x18000b155  jnz     short loc_18000B16F
0x18000b157  cmp     [rcx], di
0x18000b15a  jz      short loc_18000B1D2
0x18000b15c  test    r11, r11
0x18000b15f  jnz     short loc_18000B168
0x18000b161  mov     edx, 80070057h
0x18000b166  jmp     short loc_18000B1DA
0x18000b168  mov     edx, 8007007Ah
0x18000b16d  jmp     short loc_18000B1D2
0x18000b16f  mov     edx, 7FFFFFFEh
0x18000b174  mov     r8, r11
0x18000b177  sub     rdx, r10
0x18000b17a  mov     r9, rdi
0x18000b17d  sub     rcx, r11
0x18000b180  lea     rax, [rdx+r10]
0x18000b184  test    rax, rax
0x18000b187  jz      short loc_18000B1A4
0x18000b189  movzx   eax, word ptr [rcx+r8]
0x18000b18e  test    ax, ax
0x18000b191  jz      short loc_18000B1A4
0x18000b193  mov     [r8], ax
0x18000b197  inc     r9
0x18000b19a  add     r8, 2
0x18000b19e  sub     r10, 1
0x18000b1a2  jnz     short loc_18000B180
0x18000b1a4  mov     rax, r10
0x18000b1a7  mov     edx, 8007007Ah
0x18000b1ac  neg     rax
0x18000b1af  lea     rax, [r8-2]
0x18000b1b3  sbb     ecx, ecx
0x18000b1b5  not     ecx
0x18000b1b7  and     edx, ecx
0x18000b1b9  test    r10, r10
0x18000b1bc  cmovnz  rax, r8
0x18000b1c0  mov     [rax], di
0x18000b1c3  lea     rax, [r9-1]
0x18000b1c7  cmovnz  rax, r9
0x18000b1cb  lea     rcx, [r11+rax*2]
0x18000b1cf  mov     r11, rcx
0x18000b1d2  test    rbx, rbx
0x18000b1d5  jz      short loc_18000B1DA
0x18000b1d7  mov     [rbx], r11
0x18000b1da  mov     rbx, [rsp+8+arg_10]
0x18000b1df  mov     eax, edx
0x18000b1e1  pop     rdi
0x18000b1e2  retn
```
