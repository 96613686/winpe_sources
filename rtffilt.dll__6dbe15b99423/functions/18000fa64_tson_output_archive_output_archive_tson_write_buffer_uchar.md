# tson::output_archive::output_archive(tson::write_buffer &,uchar)

- ea: `0x18000fa64`
- end: `0x18000fb4e`
- name: `??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z`
- size: `234`
- prototype: `_QWORD(tson::output_archive *__hidden this, struct tson::write_buffer *, unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800189d8`

## callees

- `0x1800028b4`
- `0x18000fa64`
- `0x180017c40`

## pseudocode

```c
tson::output_archive *__fastcall tson::output_archive::output_archive(
        tson::output_archive *this,
        struct tson::write_buffer *a2,
        char a3)
{
  __int64 v6; // rdi
  unsigned __int64 v7; // rax

  *(_QWORD *)this = 0;
  *((_BYTE *)this + 8) = 0;
  *((_WORD *)this + 5) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_BYTE *)this + 24) = 0;
  memset_0((char *)this + 28, 0, 0x64u);
  *((_QWORD *)this + 16) = 0;
  *((_DWORD *)this + 34) = 0;
  *((_QWORD *)this + 18) = a2;
  if ( *((_QWORD *)a2 + 259) < *((_QWORD *)a2 + 260) || tson::write_buffer::reserve(a2, 1u) )
    *(_BYTE *)(*((_QWORD *)a2 + 259))++ = 0x80;
  v6 = *((_QWORD *)this + 18);
  if ( *(_QWORD *)(v6 + 2072) < *(_QWORD *)(v6 + 2080)
    || tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 1u) )
  {
    *(_BYTE *)(*(_QWORD *)(v6 + 2072))++ = a3;
  }
  v7 = *((_QWORD *)this + 16);
  if ( v7 >= 0x19 )
  {
    *((_BYTE *)this + 24) = 1;
  }
  else
  {
    *((_DWORD *)this + v7 + 7) = 1;
    ++*((_QWORD *)this + 16);
  }
  return this;
}

```

## disassembly

```asm
0x18000fa64  push    rbx
0x18000fa66  push    rbp
0x18000fa67  push    rsi
0x18000fa68  push    rdi
0x18000fa69  sub     rsp, 28h
0x18000fa6d  xor     eax, eax
0x18000fa6f  mov     qword ptr [rcx], 0
0x18000fa76  mov     sil, r8b
0x18000fa79  mov     byte ptr [rcx+8], 0
0x18000fa7d  mov     rdi, rdx
0x18000fa80  mov     [rcx+0Ah], ax
0x18000fa84  mov     rbx, rcx
0x18000fa87  mov     [rcx+10h], rax
0x18000fa8b  mov     [rcx+18h], al
0x18000fa8e  lea     r8d, [rax+64h]; Size
0x18000fa92  add     rcx, 1Ch; void *
0x18000fa96  xor     edx, edx; Val
0x18000fa98  call    memset_0
0x18000fa9d  mov     qword ptr [rbx+80h], 0
0x18000faa8  mov     ebp, 1
0x18000faad  mov     dword ptr [rbx+88h], 0
0x18000fab7  mov     [rbx+90h], rdi
0x18000fabe  mov     rax, [rdi+820h]
0x18000fac5  cmp     [rdi+818h], rax
0x18000facc  jb      short loc_18000FADC
0x18000face  mov     edx, ebp; unsigned __int64
0x18000fad0  mov     rcx, rdi; this
0x18000fad3  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000fad8  test    al, al
0x18000fada  jz      short loc_18000FAED
0x18000fadc  mov     rax, [rdi+818h]
0x18000fae3  mov     byte ptr [rax], 80h
0x18000fae6  add     [rdi+818h], rbp
0x18000faed  mov     rdi, [rbx+90h]
0x18000faf4  mov     rax, [rdi+820h]
0x18000fafb  cmp     [rdi+818h], rax
0x18000fb02  jb      short loc_18000FB13
0x18000fb04  mov     rdx, rbp; unsigned __int64
0x18000fb07  mov     rcx, rdi; this
0x18000fb0a  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000fb0f  test    al, al
0x18000fb11  jz      short loc_18000FB24
0x18000fb13  mov     rax, [rdi+818h]
0x18000fb1a  mov     [rax], sil
0x18000fb1d  add     [rdi+818h], rbp
0x18000fb24  mov     rax, [rbx+80h]
0x18000fb2b  cmp     rax, 19h
0x18000fb2f  jnb     short loc_18000FB3E
0x18000fb31  mov     [rbx+rax*4+1Ch], ebp
0x18000fb35  add     [rbx+80h], rbp
0x18000fb3c  jmp     short loc_18000FB42
0x18000fb3e  mov     [rbx+18h], bpl
0x18000fb42  mov     rax, rbx
0x18000fb45  add     rsp, 28h
0x18000fb49  pop     rdi
0x18000fb4a  pop     rsi
0x18000fb4b  pop     rbp
0x18000fb4c  pop     rbx
0x18000fb4d  retn
```
