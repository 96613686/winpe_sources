# tson::output_archive::write_name(bool)

- ea: `0x180018f64`
- end: `0x180019170`
- name: `?write_name@output_archive@tson@@AEAA_N_N@Z`
- size: `524`
- prototype: `bool __fastcall(tson::output_archive *__hidden this, bool)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x18000dd04`
- `0x18000ddb4`
- `0x18000ecd0`
- `0x18000ef64`
- `0x18000f15c`
- `0x18000f1ec`
- `0x180017d40`
- `0x180018360`
- `0x180018760`
- `0x1800188c0`
- `0x1800189d8`

## callees

- `0x180017a40`
- `0x180017c40`
- `0x180018f64`

## pseudocode

```c
char __fastcall tson::output_archive::write_name(tson::output_archive *this, char a2)
{
  char *v2; // rsi
  __int64 v4; // rax
  __int64 v6; // rbx
  __int64 v7; // rbx
  tson::write_buffer *v8; // rbx
  char *v10; // rsi
  tson::write_buffer **v11; // r14
  tson::write_buffer *v12; // rbx
  tson::write_buffer **v13; // rbp
  char *v14; // r15
  tson::write_buffer *v15; // rbx
  char v16; // cl

  v2 = (char *)this + 24;
  v4 = *((_QWORD *)this + 16);
  if ( v4 )
    v2 = &v2[4 * v4 - 4];
  else
    *v2 = 1;
  if ( *((_DWORD *)v2 + 1) == 2 )
  {
    *((_DWORD *)v2 + 1) = 3;
    v6 = *((_QWORD *)this + 18);
    if ( *(_QWORD *)(v6 + 2072) < *(_QWORD *)(v6 + 2080)
      || tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 1u) )
    {
      *(_BYTE *)(*(_QWORD *)(v6 + 2072))++ = 3;
    }
    tson::write_buffer::push_back(*((tson::write_buffer **)this + 18), (char *)this + 10, 2u);
    *((_WORD *)this + 5) = 0;
  }
  else if ( !*((_DWORD *)v2 + 1) )
  {
    *((_DWORD *)v2 + 1) = 1;
    v7 = *((_QWORD *)this + 18);
    if ( *(_QWORD *)(v7 + 2072) < *(_QWORD *)(v7 + 2080)
      || tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 1u) )
    {
      *(_BYTE *)(*(_QWORD *)(v7 + 2072))++ = 1;
    }
  }
  *((_QWORD *)this + 2) = 0;
  if ( *((_DWORD *)v2 + 1) == 3 )
    return 1;
  if ( !a2 )
  {
    v10 = (char *)this + 8;
    if ( !*(_QWORD *)this )
    {
      *v10 = 1;
      *(_QWORD *)this = "-";
    }
    v11 = (tson::write_buffer **)((char *)this + 144);
    v12 = (tson::write_buffer *)*((_QWORD *)this + 18);
    *((_QWORD *)this + 2) = *((_QWORD *)v12 + 259) - *((_QWORD *)v12 + 258);
    if ( *((_QWORD *)v12 + 259) < *((_QWORD *)v12 + 260) || tson::write_buffer::reserve(v12, 1u) )
    {
      v14 = (char *)this + 8;
      v13 = (tson::write_buffer **)((char *)this + 144);
      *(_BYTE *)(*((_QWORD *)v12 + 259))++ = 5;
    }
    else
    {
      v13 = (tson::write_buffer **)((char *)this + 144);
      v14 = (char *)this + 8;
    }
    v15 = *v11;
    if ( *((_QWORD *)*v11 + 259) < *((_QWORD *)*v11 + 260) || tson::write_buffer::reserve(*v11, 1u) )
    {
      v16 = *v10;
      v11 = v13;
      v10 = v14;
      *(_BYTE *)(*((_QWORD *)v15 + 259))++ = v16;
    }
    tson::write_buffer::push_back(*v11, *(const void **)this, (unsigned __int8)*v10);
    *(_QWORD *)this = 0;
    return 1;
  }
  v8 = (tson::write_buffer *)*((_QWORD *)this + 18);
  *(_QWORD *)this = 0;
  if ( *((_QWORD *)v8 + 259) < *((_QWORD *)v8 + 260) || tson::write_buffer::reserve(v8, 1u) )
    *(_BYTE *)(*((_QWORD *)v8 + 259))++ = 6;
  return 0;
}

```

## disassembly

```asm
0x180018f64  push    rbx
0x180018f66  push    rbp
0x180018f67  push    rsi
0x180018f68  push    rdi
0x180018f69  push    r12
0x180018f6b  push    r14
0x180018f6d  push    r15
0x180018f6f  sub     rsp, 20h
0x180018f73  lea     rsi, [rcx+18h]
0x180018f77  mov     bpl, dl
0x180018f7a  mov     rax, [rsi+68h]
0x180018f7e  mov     rdi, rcx
0x180018f81  mov     r12d, 1
0x180018f87  test    rax, rax
0x180018f8a  jz      short loc_180018F96
0x180018f8c  lea     rsi, [rsi+rax*4]
0x180018f90  add     rsi, 0FFFFFFFFFFFFFFFCh
0x180018f94  jmp     short loc_180018F99
0x180018f96  mov     [rsi], r12b
0x180018f99  cmp     dword ptr [rsi+4], 2
0x180018f9d  jnz     short loc_180018FFB
0x180018f9f  mov     dword ptr [rsi+4], 3
0x180018fa6  mov     rbx, [rcx+90h]
0x180018fad  mov     rax, [rbx+820h]
0x180018fb4  cmp     [rbx+818h], rax
0x180018fbb  jb      short loc_180018FCC
0x180018fbd  mov     rdx, r12; unsigned __int64
0x180018fc0  mov     rcx, rbx; this
0x180018fc3  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x180018fc8  test    al, al
0x180018fca  jz      short loc_180018FDD
0x180018fcc  mov     rax, [rbx+818h]
0x180018fd3  mov     byte ptr [rax], 3
0x180018fd6  add     [rbx+818h], r12
0x180018fdd  mov     rcx, [rdi+90h]; this
0x180018fe4  lea     rdx, [rdi+0Ah]; void *
0x180018fe8  mov     r8d, 2; unsigned __int64
0x180018fee  call    ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
0x180018ff3  xor     eax, eax
0x180018ff5  mov     [rdi+0Ah], ax
0x180018ff9  jmp     short loc_18001903C
0x180018ffb  cmp     dword ptr [rsi+4], 0
0x180018fff  jnz     short loc_18001903C
0x180019001  mov     [rsi+4], r12d
0x180019005  mov     rbx, [rcx+90h]
0x18001900c  mov     rax, [rbx+820h]
0x180019013  cmp     [rbx+818h], rax
0x18001901a  jb      short loc_18001902B
0x18001901c  mov     rdx, r12; unsigned __int64
0x18001901f  mov     rcx, rbx; this
0x180019022  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x180019027  test    al, al
0x180019029  jz      short loc_18001903C
0x18001902b  mov     rax, [rbx+818h]
0x180019032  mov     [rax], r12b
0x180019035  add     [rbx+818h], r12
0x18001903c  mov     qword ptr [rdi+10h], 0
0x180019044  cmp     dword ptr [rsi+4], 3
0x180019048  jz      loc_18001915E
0x18001904e  test    bpl, bpl
0x180019051  jz      short loc_180019098
0x180019053  mov     rbx, [rdi+90h]
0x18001905a  mov     qword ptr [rdi], 0
0x180019061  mov     rax, [rbx+820h]
0x180019068  cmp     [rbx+818h], rax
0x18001906f  jb      short loc_180019080
0x180019071  mov     rdx, r12; unsigned __int64
0x180019074  mov     rcx, rbx; this
0x180019077  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18001907c  test    al, al
0x18001907e  jz      short loc_180019091
0x180019080  mov     rax, [rbx+818h]
0x180019087  mov     byte ptr [rax], 6
0x18001908a  add     [rbx+818h], r12
0x180019091  xor     al, al
0x180019093  jmp     loc_180019161
0x180019098  cmp     qword ptr [rdi], 0
0x18001909c  lea     rsi, [rdi+8]
0x1800190a0  jnz     short loc_1800190AF
0x1800190a2  lea     rax, asc_18001DA6C; "-"
0x1800190a9  mov     [rsi], r12b
0x1800190ac  mov     [rdi], rax
0x1800190af  lea     r14, [rdi+90h]
0x1800190b6  mov     rbx, [r14]
0x1800190b9  mov     rax, [rbx+818h]
0x1800190c0  sub     rax, [rbx+810h]
0x1800190c7  mov     [rdi+10h], rax
0x1800190cb  mov     rax, [rbx+820h]
0x1800190d2  cmp     [rbx+818h], rax
0x1800190d9  jb      short loc_1800190F2
0x1800190db  mov     rdx, r12; unsigned __int64
0x1800190de  mov     rcx, rbx; this
0x1800190e1  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x1800190e6  test    al, al
0x1800190e8  jnz     short loc_1800190F2
0x1800190ea  mov     rbp, r14
0x1800190ed  mov     r15, rsi
0x1800190f0  jmp     short loc_18001910E
0x1800190f2  mov     rax, [rbx+818h]
0x1800190f9  lea     r15, [rdi+8]
0x1800190fd  lea     rbp, [rdi+90h]
0x180019104  mov     byte ptr [rax], 5
0x180019107  add     [rbx+818h], r12
0x18001910e  mov     rbx, [r14]
0x180019111  mov     rax, [rbx+820h]
0x180019118  cmp     [rbx+818h], rax
0x18001911f  jb      short loc_180019130
0x180019121  mov     rdx, r12; unsigned __int64
0x180019124  mov     rcx, rbx; this
0x180019127  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18001912c  test    al, al
0x18001912e  jz      short loc_180019148
0x180019130  mov     cl, [rsi]
0x180019132  mov     r14, rbp
0x180019135  mov     rdx, [rbx+818h]
0x18001913c  mov     rsi, r15
0x18001913f  mov     [rdx], cl
0x180019141  add     [rbx+818h], r12
0x180019148  movzx   r8d, byte ptr [rsi]; unsigned __int64
0x18001914c  mov     rdx, [rdi]; void *
0x18001914f  mov     rcx, [r14]; this
0x180019152  call    ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
0x180019157  mov     qword ptr [rdi], 0
0x18001915e  mov     al, r12b
0x180019161  add     rsp, 20h
0x180019165  pop     r15
0x180019167  pop     r14
0x180019169  pop     r12
0x18001916b  pop     rdi
0x18001916c  pop     rsi
0x18001916d  pop     rbp
0x18001916e  pop     rbx
0x18001916f  retn
```
