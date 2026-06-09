# __crt_stdio_output::formatting_buffer::ensure_buffer_is_big_enough<wchar_t>(unsigned __int64,__crt_cached_ptd_host &)

- ea: `0x10042b240`
- end: `0x10042b2ec`
- name: `??$ensure_buffer_is_big_enough@_W@formatting_buffer@__crt_stdio_output@@QEAA_N_KAEAV__crt_cached_ptd_host@@@Z`
- size: `172`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x10042bab4`
- `0x10042bcc4`
- `0x10042bed4`

## callees

- `0x10042b240`
- `0x10042e7dc`
- `0x10043171c`

## pseudocode

```c
char __fastcall __crt_stdio_output::formatting_buffer::ensure_buffer_is_big_enough<wchar_t>(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3)
{
  char result; // al
  char v5; // di
  unsigned __int64 v6; // rsi
  void *v7; // rbx

  if ( a2 <= 0x3FFFFFFFFFFFFFFFLL )
  {
    v5 = 0;
    v6 = 4 * a2;
    if ( (*(_QWORD *)(a1 + 1032) || v6 > 0x400) && v6 > *(_QWORD *)(a1 + 1024) )
    {
      v7 = malloc_base(4 * a2);
      if ( v7 )
      {
        free_base(*(void **)(a1 + 1032));
        *(_QWORD *)(a1 + 1032) = v7;
        v5 = 1;
        *(_QWORD *)(a1 + 1024) = v6;
      }
      free_base(0);
      return v5;
    }
    else
    {
      return 1;
    }
  }
  else
  {
    *(_BYTE *)(a3 + 48) = 1;
    result = 0;
    *(_DWORD *)(a3 + 44) = 12;
  }
  return result;
}

```

## disassembly

```asm
0x10042b240  mov     [rsp+arg_0], rbx
0x10042b245  mov     [rsp+arg_8], rbp
0x10042b24a  mov     [rsp+arg_10], rsi
0x10042b24f  push    rdi
0x10042b250  sub     rsp, 20h
0x10042b254  mov     rax, 3FFFFFFFFFFFFFFFh
0x10042b25e  mov     rbp, rcx
0x10042b261  cmp     rdx, rax
0x10042b264  jbe     short loc_10042B277
0x10042b266  mov     byte ptr [r8+30h], 1
0x10042b26b  xor     al, al
0x10042b26d  mov     dword ptr [r8+2Ch], 0Ch
0x10042b275  jmp     short loc_10042B2D7
0x10042b277  xor     edi, edi
0x10042b279  lea     rsi, ds:0[rdx*4]
0x10042b281  cmp     [rcx+408h], rdi
0x10042b288  jnz     short loc_10042B293
0x10042b28a  cmp     rsi, 400h
0x10042b291  jbe     short loc_10042B29C
0x10042b293  cmp     rsi, [rcx+400h]
0x10042b29a  ja      short loc_10042B2A0
0x10042b29c  mov     al, 1
0x10042b29e  jmp     short loc_10042B2D7
0x10042b2a0  mov     rcx, rsi; Size
0x10042b2a3  call    _malloc_base
0x10042b2a8  mov     rbx, rax
0x10042b2ab  test    rax, rax
0x10042b2ae  jz      short loc_10042B2CD
0x10042b2b0  mov     rcx, [rbp+408h]; Block
0x10042b2b7  call    _free_base
0x10042b2bc  mov     [rbp+408h], rbx
0x10042b2c3  mov     dil, 1
0x10042b2c6  mov     [rbp+400h], rsi
0x10042b2cd  xor     ecx, ecx; Block
0x10042b2cf  call    _free_base
0x10042b2d4  mov     al, dil
0x10042b2d7  mov     rbx, [rsp+28h+arg_0]
0x10042b2dc  mov     rbp, [rsp+28h+arg_8]
0x10042b2e1  mov     rsi, [rsp+28h+arg_10]
0x10042b2e6  add     rsp, 20h
0x10042b2ea  pop     rdi
0x10042b2eb  retn
```
