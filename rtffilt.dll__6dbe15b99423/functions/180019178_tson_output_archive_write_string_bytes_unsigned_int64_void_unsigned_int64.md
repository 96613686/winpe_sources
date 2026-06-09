# tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)

- ea: `0x180019178`
- end: `0x180019293`
- name: `?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z`
- size: `283`
- prototype: `void(tson::output_archive *__hidden this, unsigned __int64, void *, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f15c`
- `0x18000f1ec`
- `0x180017d40`
- `0x180018360`
- `0x180018760`
- `0x1800189d8`

## callees

- `0x180017a40`
- `0x180017c40`
- `0x180019178`

## pseudocode

```c
void __fastcall tson::output_archive::write_string_bytes(tson::output_archive *this, __int64 a2, void *a3, size_t a4)
{
  unsigned __int64 v4; // rdi
  tson::write_buffer **v7; // r14
  tson::write_buffer *v8; // rbx
  char v9; // bp
  __int16 v10; // di
  __int64 v11; // rbx

  v4 = a2 + 1;
  if ( (unsigned __int64)(a2 + 1) > 0x7F )
  {
    if ( v4 > 0x7FFF && *((int *)this + 34) >= 0 )
      *((_DWORD *)this + 34) = -2147483637;
    v7 = (tson::write_buffer **)((char *)this + 144);
    v10 = v4 | 0x8000;
    v11 = *((_QWORD *)this + 18);
    if ( *(_QWORD *)(v11 + 2072) < *(_QWORD *)(v11 + 2080)
      || tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 1u) )
    {
      *(_BYTE *)(*(_QWORD *)(v11 + 2072))++ = HIBYTE(v10);
    }
    v8 = *v7;
    if ( *((_QWORD *)*v7 + 259) < *((_QWORD *)*v7 + 260) || tson::write_buffer::reserve(*v7, 1u) )
    {
      **((_BYTE **)v8 + 259) = v10;
      goto LABEL_14;
    }
  }
  else
  {
    v7 = (tson::write_buffer **)((char *)this + 144);
    v8 = (tson::write_buffer *)*((_QWORD *)this + 18);
    v9 = a3 != 0 ? v4 : 0;
    if ( *((_QWORD *)v8 + 259) < *((_QWORD *)v8 + 260)
      || tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 1u) )
    {
      **((_BYTE **)v8 + 259) = v9;
LABEL_14:
      ++*((_QWORD *)v8 + 259);
    }
  }
  tson::write_buffer::push_back(*v7, a3, a4);
}

```

## disassembly

```asm
0x180019178  push    rbx
0x18001917a  push    rbp
0x18001917b  push    rdi
0x18001917c  push    r12
0x18001917e  push    r14
0x180019180  push    r15
0x180019182  sub     rsp, 28h
0x180019186  lea     rdi, [rdx+1]
0x18001918a  mov     r12, r9
0x18001918d  mov     r15, r8
0x180019190  cmp     rdi, 7Fh
0x180019194  ja      short loc_1800191E0
0x180019196  mov     rax, r8
0x180019199  lea     r14, [rcx+90h]
0x1800191a0  mov     rbx, [r14]
0x1800191a3  neg     rax
0x1800191a6  sbb     bpl, bpl
0x1800191a9  and     bpl, dil
0x1800191ac  mov     rax, [rbx+820h]
0x1800191b3  cmp     [rbx+818h], rax
0x1800191ba  jb      short loc_1800191D1
0x1800191bc  mov     edx, 1; unsigned __int64
0x1800191c1  mov     rcx, rbx; this
0x1800191c4  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x1800191c9  test    al, al
0x1800191cb  jz      loc_180019278
0x1800191d1  mov     rax, [rbx+818h]
0x1800191d8  mov     [rax], bpl
0x1800191db  jmp     loc_180019271
0x1800191e0  cmp     rdi, 7FFFh
0x1800191e7  jbe     short loc_1800191FC
0x1800191e9  cmp     dword ptr [rcx+88h], 0
0x1800191f0  jl      short loc_1800191FC
0x1800191f2  mov     dword ptr [rcx+88h], 8000000Bh
0x1800191fc  lea     r14, [rcx+90h]
0x180019203  bts     rdi, 0Fh
0x180019208  mov     rbx, [r14]
0x18001920b  mov     rax, [rbx+820h]
0x180019212  cmp     [rbx+818h], rax
0x180019219  jb      short loc_18001922C
0x18001921b  mov     edx, 1; unsigned __int64
0x180019220  mov     rcx, rbx; this
0x180019223  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x180019228  test    al, al
0x18001922a  jz      short loc_180019243
0x18001922c  mov     rax, [rbx+818h]
0x180019233  mov     rcx, rdi
0x180019236  shr     rcx, 8
0x18001923a  mov     [rax], cl
0x18001923c  inc     qword ptr [rbx+818h]
0x180019243  mov     rbx, [r14]
0x180019246  mov     rax, [rbx+820h]
0x18001924d  cmp     [rbx+818h], rax
0x180019254  jb      short loc_180019267
0x180019256  mov     edx, 1; unsigned __int64
0x18001925b  mov     rcx, rbx; this
0x18001925e  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x180019263  test    al, al
0x180019265  jz      short loc_180019278
0x180019267  mov     rax, [rbx+818h]
0x18001926e  mov     [rax], dil
0x180019271  inc     qword ptr [rbx+818h]
0x180019278  mov     rcx, [r14]; this
0x18001927b  mov     r8, r12; unsigned __int64
0x18001927e  mov     rdx, r15; void *
0x180019281  add     rsp, 28h
0x180019285  pop     r15
0x180019287  pop     r14
0x180019289  pop     r12
0x18001928b  pop     rdi
0x18001928c  pop     rbp
0x18001928d  pop     rbx
0x18001928e  jmp     ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
```
