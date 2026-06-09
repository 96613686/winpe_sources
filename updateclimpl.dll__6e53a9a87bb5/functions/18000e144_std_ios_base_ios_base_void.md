# std::ios_base::~ios_base(void)

- ea: `0x18000e144`
- end: `0x18000e233`
- name: `??1ios_base@std@@UEAA@XZ`
- size: `239`
- prototype: `void __fastcall(std::ios_base *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000e240`
- `0x18000f1dc`
- `0x18000f23c`
- `0x18000f340`
- `0x1800162b0`
- `0x180016340`

## callees

- `0x18000e144`
- `0x180010334`
- `0x1800148e0`

## pseudocode

```c
void __fastcall std::ios_base::~ios_base(std::ios_base *this)
{
  __int64 v2; // rax
  __int64 **i; // rbx
  _QWORD *v4; // rcx
  _QWORD *v5; // rbx
  _QWORD *v6; // rcx
  _QWORD *v7; // rbx
  _QWORD *v8; // rbx
  __int64 v9; // rcx
  void (__fastcall ***v10)(_QWORD, __int64); // rax

  *(_QWORD *)this = &std::ios_base::`vftable';
  v2 = *((_QWORD *)this + 1);
  if ( !v2 || (--*((_BYTE *)qword_1800201D0 + v2), *((char *)qword_1800201D0 + v2) <= 0) )
  {
    for ( i = (__int64 **)*((_QWORD *)this + 7); i; i = (__int64 **)*i )
      ((void (__fastcall *)(_QWORD, std::ios_base *, _QWORD))i[2])(0, this, *((unsigned int *)i + 2));
    v4 = (_QWORD *)*((_QWORD *)this + 6);
    if ( v4 )
    {
      do
      {
        v5 = (_QWORD *)*v4;
        operator delete(v4, 0x18u);
        v4 = v5;
      }
      while ( v5 );
    }
    *((_QWORD *)this + 6) = 0;
    v6 = (_QWORD *)*((_QWORD *)this + 7);
    if ( v6 )
    {
      do
      {
        v7 = (_QWORD *)*v6;
        operator delete(v6, 0x18u);
        v6 = v7;
      }
      while ( v7 );
    }
    *((_QWORD *)this + 7) = 0;
    v8 = (_QWORD *)*((_QWORD *)this + 8);
    if ( v8 )
    {
      v9 = v8[1];
      if ( v9 )
      {
        v10 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        if ( v10 )
          (**v10)(v10, 1);
      }
      operator delete(v8, 0x10u);
    }
  }
}

```

## disassembly

```asm
0x18000e144  mov     [rsp+arg_0], rbx
0x18000e149  push    rdi
0x18000e14a  sub     rsp, 20h
0x18000e14e  mov     rdi, rcx
0x18000e151  lea     rax, ??_7ios_base@std@@6B@; const std::ios_base::`vftable'
0x18000e158  mov     [rcx], rax
0x18000e15b  mov     rax, [rcx+8]
0x18000e15f  test    rax, rax
0x18000e162  jz      short loc_18000E178
0x18000e164  lea     rcx, qword_1800201D0
0x18000e16b  dec     byte ptr [rax+rcx]
0x18000e16e  cmp     byte ptr [rax+rcx], 0
0x18000e172  jg      loc_18000E228
0x18000e178  mov     rbx, [rdi+38h]
0x18000e17c  jmp     short loc_18000E193
0x18000e17e  mov     r8d, [rbx+8]
0x18000e182  mov     rdx, rdi
0x18000e185  xor     ecx, ecx
0x18000e187  mov     rax, [rbx+10h]
0x18000e18b  call    _guard_dispatch_icall
0x18000e190  mov     rbx, [rbx]
0x18000e193  test    rbx, rbx
0x18000e196  jnz     short loc_18000E17E
0x18000e198  mov     rcx, [rdi+30h]; void *
0x18000e19c  test    rcx, rcx
0x18000e19f  jz      short loc_18000E1B6
0x18000e1a1  mov     rbx, [rcx]
0x18000e1a4  mov     edx, 18h; unsigned __int64
0x18000e1a9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e1ae  mov     rcx, rbx
0x18000e1b1  test    rbx, rbx
0x18000e1b4  jnz     short loc_18000E1A1
0x18000e1b6  mov     qword ptr [rdi+30h], 0
0x18000e1be  mov     rcx, [rdi+38h]; void *
0x18000e1c2  test    rcx, rcx
0x18000e1c5  jz      short loc_18000E1DC
0x18000e1c7  mov     rbx, [rcx]
0x18000e1ca  mov     edx, 18h; unsigned __int64
0x18000e1cf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e1d4  mov     rcx, rbx
0x18000e1d7  test    rbx, rbx
0x18000e1da  jnz     short loc_18000E1C7
0x18000e1dc  mov     qword ptr [rdi+38h], 0
0x18000e1e4  mov     rbx, [rdi+40h]
0x18000e1e8  test    rbx, rbx
0x18000e1eb  jz      short loc_18000E228
0x18000e1ed  mov     rcx, [rbx+8]
0x18000e1f1  test    rcx, rcx
0x18000e1f4  jz      short loc_18000E21A
0x18000e1f6  mov     rax, [rcx]
0x18000e1f9  mov     rax, [rax+10h]
0x18000e1fd  call    _guard_dispatch_icall
0x18000e202  mov     rcx, rax
0x18000e205  test    rax, rax
0x18000e208  jz      short loc_18000E21A
0x18000e20a  mov     rdx, [rax]
0x18000e20d  mov     rax, [rdx]
0x18000e210  mov     edx, 1
0x18000e215  call    _guard_dispatch_icall
0x18000e21a  mov     edx, 10h; unsigned __int64
0x18000e21f  mov     rcx, rbx; void *
0x18000e222  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e227  nop
0x18000e228  mov     rbx, [rsp+28h+arg_0]
0x18000e22d  add     rsp, 20h
0x18000e231  pop     rdi
0x18000e232  retn
```
