# ProfNotif_CreateStringCopy(wchar_t const *,wchar_t * *)

- ea: `0x180003ab8`
- end: `0x180003b74`
- name: `?ProfNotif_CreateStringCopy@@YAJPEB_WPEAPEA_W@Z`
- size: `188`
- prototype: `__int64 __fastcall(const wchar_t *, wchar_t **, __int64, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180007768`
- `0x1800080a0`
- `0x1800081e0`

## callees

- `0x180003ab8`
- `0x180003b7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProfNotif_CreateStringCopy(const wchar_t *a1, wchar_t **a2, __int64 a3, void *a4)
{
  __int64 v4; // rbx
  const wchar_t *v6; // rdi
  unsigned __int64 v7; // rbx
  int v8; // ecx
  _WORD *v9; // rdx
  __int64 v10; // rax
  _WORD *v11; // rcx

  v4 = -1;
  v6 = a1;
  do
    ++v4;
  while ( a1[v4] );
  v7 = v4 + 1;
  *a2 = 0;
  if ( is_mul_ok(v7, 2u) )
  {
    v8 = ProfNotif_HeapAlloc(2 * v7, (v7 * (unsigned __int128)2uLL) >> 64, (void **)a2, a4);
    if ( v8 >= 0 )
    {
      v9 = *a2;
      if ( v7 )
      {
        if ( v7 <= 0x7FFFFFFF )
        {
          v10 = 2147483646;
          do
          {
            if ( !v10 )
              break;
            if ( !*v6 )
              break;
            *v9++ = *v6++;
            --v10;
            --v7;
          }
          while ( v7 );
          v11 = v9 - 1;
          if ( v7 )
            v11 = v9;
          *v11 = 0;
          return v7 == 0 ? 0x8007007A : 0;
        }
        else
        {
          v8 = -2147024809;
          *v9 = 0;
        }
      }
      else
      {
        return (unsigned int)-2147024809;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024362;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180003ab8  push    rbx
0x180003aba  push    rbp
0x180003abb  push    rsi
0x180003abc  push    rdi
0x180003abd  sub     rsp, 28h
0x180003ac1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003ac5  mov     rsi, rdx
0x180003ac8  xor     ebp, ebp
0x180003aca  mov     rdi, rcx
0x180003acd  inc     rbx
0x180003ad0  cmp     [rcx+rbx*2], bp
0x180003ad4  jnz     short loc_180003ACD
0x180003ad6  inc     rbx
0x180003ad9  mov     [rdx], rbp
0x180003adc  mov     eax, 2
0x180003ae1  mul     rbx
0x180003ae4  test    rdx, rdx
0x180003ae7  jnz     short loc_180003B64
0x180003ae9  mov     r8, rsi; void **
0x180003aec  mov     rcx, rax; dwBytes
0x180003aef  call    ?ProfNotif_HeapAlloc@@YAJ_KHPEAPEAXPEAX@Z; ProfNotif_HeapAlloc(unsigned __int64,int,void * *,void *)
0x180003af4  mov     ecx, eax
0x180003af6  test    eax, eax
0x180003af8  js      short loc_180003B69
0x180003afa  mov     rdx, [rsi]
0x180003afd  test    rbx, rbx
0x180003b00  jz      short loc_180003B55
0x180003b02  cmp     rbx, 7FFFFFFFh
0x180003b09  jbe     short loc_180003B12
0x180003b0b  mov     ecx, 80070057h
0x180003b10  jmp     short loc_180003B5F
0x180003b12  mov     eax, 7FFFFFFEh
0x180003b17  test    rax, rax
0x180003b1a  jz      short loc_180003B38
0x180003b1c  movzx   ecx, word ptr [rdi]
0x180003b1f  test    cx, cx
0x180003b22  jz      short loc_180003B38
0x180003b24  mov     [rdx], cx
0x180003b27  add     rdi, 2
0x180003b2b  add     rdx, 2
0x180003b2f  dec     rax
0x180003b32  sub     rbx, 1
0x180003b36  jnz     short loc_180003B17
0x180003b38  test    rbx, rbx
0x180003b3b  lea     rcx, [rdx-2]
0x180003b3f  cmovnz  rcx, rdx
0x180003b43  neg     rbx
0x180003b46  mov     [rcx], bp
0x180003b49  sbb     ecx, ecx
0x180003b4b  not     ecx
0x180003b4d  and     ecx, 8007007Ah
0x180003b53  jmp     short loc_180003B69
0x180003b55  mov     ecx, 80070057h
0x180003b5a  test    rbx, rbx
0x180003b5d  jz      short loc_180003B69
0x180003b5f  mov     [rdx], bp
0x180003b62  jmp     short loc_180003B69
0x180003b64  mov     ecx, 80070216h
0x180003b69  mov     eax, ecx
0x180003b6b  add     rsp, 28h
0x180003b6f  pop     rdi
0x180003b70  pop     rsi
0x180003b71  pop     rbp
0x180003b72  pop     rbx
0x180003b73  retn
```
