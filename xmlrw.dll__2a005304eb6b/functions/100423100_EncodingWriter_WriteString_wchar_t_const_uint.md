# EncodingWriter::WriteString(wchar_t const *,uint)

- ea: `0x100423100`
- end: `0x10042325a`
- name: `?WriteString@EncodingWriter@@QEAAJPEB_WI@Z`
- size: `346`
- prototype: `__int64 __fastcall(EncodingWriter *__hidden this, const wchar_t *, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x100421d00`
- `0x1004228c0`
- `0x100423260`

## callees

- `0x100423100`
- `0x100423260`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall EncodingWriter::WriteString(EncodingWriter *this, const wchar_t *a2, unsigned int a3)
{
  unsigned int v3; // edi
  char v6; // bp
  unsigned int v7; // eax
  unsigned int v8; // edx
  __int64 result; // rax
  unsigned int v10; // [rsp+80h] [rbp+18h] BYREF
  unsigned int v11; // [rsp+88h] [rbp+20h] BYREF

  v3 = a3;
  v6 = 1;
  if ( !a3 )
    return 0;
  while ( 1 )
  {
    v11 = *((_DWORD *)this + 12) - *((_DWORD *)this + 14);
    v7 = v11 / *((_DWORD *)this + 7);
    v10 = v7;
    v8 = v7;
    if ( v7 > v3 )
    {
      v7 = v3;
      v6 = 0;
      v10 = v3;
      v8 = v3;
    }
    if ( (unsigned __int16)(a2[v7 - 1] + 10240) <= 0x3FFu )
      v10 = v8 - 1;
    result = (*((__int64 (__fastcall **)(char *, _QWORD, const wchar_t *, unsigned int *, _QWORD, unsigned int *))this
              + 12))(
               (char *)this + 32,
               *((unsigned int *)this + 6),
               a2,
               &v10,
               *((_QWORD *)this + 7),
               &v11);
    if ( (int)result < 0 )
      break;
    if ( (_DWORD)result == 1 )
    {
      _mm_lfence();
      result = EncodingWriter::ResolveErrors(this, a2, v10, *((const unsigned __int8 **)this + 7), v11);
    }
    else
    {
      *((_QWORD *)this + 7) += v11;
      if ( !v6 )
        goto LABEL_12;
      _mm_lfence();
      result = (***((__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))this + 10))(
                 *((_QWORD *)this + 10),
                 *((_QWORD *)this + 5),
                 (unsigned int)(*((_DWORD *)this + 14) - *((_DWORD *)this + 10)));
      *((_QWORD *)this + 7) = *((_QWORD *)this + 5);
    }
    if ( (int)result < 0 )
      break;
LABEL_12:
    a2 += v10;
    v3 -= v10;
    if ( !v3 )
      return 0;
  }
  _mm_lfence();
  return result;
}

```

## disassembly

```asm
0x100423100  mov     [rsp+arg_0], rbx
0x100423105  mov     [rsp+arg_8], rbp
0x10042310a  push    rsi
0x10042310b  push    rdi
0x10042310c  push    r12
0x10042310e  push    r14
0x100423110  push    r15
0x100423112  sub     rsp, 40h
0x100423116  mov     edi, r8d
0x100423119  mov     rsi, rdx
0x10042311c  mov     rbx, rcx
0x10042311f  mov     bpl, 1
0x100423122  test    r8d, r8d
0x100423125  jz      loc_10042323C
0x10042312b  mov     r15d, 2800h
0x100423131  mov     r12d, 3FFh
0x100423137  nop     word ptr [rax+rax+00000000h]
0x100423140  mov     eax, [rbx+30h]
0x100423143  xor     edx, edx
0x100423145  sub     eax, [rbx+38h]
0x100423148  mov     [rsp+68h+arg_18], eax
0x10042314f  div     dword ptr [rbx+1Ch]
0x100423152  mov     [rsp+68h+arg_10], eax
0x100423159  mov     edx, eax
0x10042315b  cmp     eax, edi
0x10042315d  jbe     short loc_10042316D
0x10042315f  mov     eax, edi
0x100423161  xor     bpl, bpl
0x100423164  mov     [rsp+68h+arg_10], eax
0x10042316b  mov     edx, edi
0x10042316d  lea     eax, [rax-1]
0x100423170  movzx   eax, word ptr [rsi+rax*2]
0x100423174  add     ax, r15w
0x100423178  cmp     ax, r12w
0x10042317c  ja      short loc_100423188
0x10042317e  lea     eax, [rdx-1]
0x100423181  mov     [rsp+68h+arg_10], eax
0x100423188  mov     rcx, [rbx+38h]
0x10042318c  lea     rax, [rsp+68h+arg_18]
0x100423194  mov     edx, [rbx+18h]
0x100423197  lea     r9, [rsp+68h+arg_10]
0x10042319f  mov     [rsp+68h+var_40], rax
0x1004231a4  mov     r8, rsi
0x1004231a7  mov     rax, [rbx+60h]
0x1004231ab  mov     qword ptr [rsp+68h+var_48], rcx
0x1004231b0  lea     rcx, [rbx+20h]
0x1004231b4  call    cs:__guard_dispatch_icall_fptr
0x1004231ba  test    eax, eax
0x1004231bc  js      loc_100423255
0x1004231c2  cmp     eax, 1
0x1004231c5  jnz     short loc_1004231EE
0x1004231c7  lfence
0x1004231ca  mov     eax, [rsp+68h+arg_18]
0x1004231d1  mov     rdx, rsi; wchar_t *
0x1004231d4  mov     r9, [rbx+38h]; unsigned __int8 *
0x1004231d8  mov     rcx, rbx; this
0x1004231db  mov     r8d, [rsp+68h+arg_10]; unsigned int
0x1004231e3  mov     [rsp+68h+var_48], eax; unsigned int
0x1004231e7  call    ?ResolveErrors@EncodingWriter@@IEAAJPEB_WIPEBEI@Z; EncodingWriter::ResolveErrors(wchar_t const *,uint,uchar const *,uint)
0x1004231ec  jmp     short loc_100423225
0x1004231ee  mov     eax, [rsp+68h+arg_18]
0x1004231f5  add     [rbx+38h], rax
0x1004231f9  test    bpl, bpl
0x1004231fc  jz      short loc_100423229
0x1004231fe  lfence
0x100423201  mov     rcx, [rbx+50h]
0x100423205  mov     r8d, [rbx+38h]
0x100423209  sub     r8d, [rbx+28h]
0x10042320d  mov     rdx, [rbx+28h]
0x100423211  mov     rax, [rcx]
0x100423214  mov     rax, [rax]
0x100423217  call    cs:__guard_dispatch_icall_fptr
0x10042321d  mov     rcx, [rbx+28h]
0x100423221  mov     [rbx+38h], rcx
0x100423225  test    eax, eax
0x100423227  js      short loc_100423255
0x100423229  mov     ecx, [rsp+68h+arg_10]
0x100423230  lea     rsi, [rsi+rcx*2]
0x100423234  sub     edi, ecx
0x100423236  jnz     loc_100423140
0x10042323c  xor     eax, eax
0x10042323e  mov     rbx, [rsp+68h+arg_0]
0x100423243  mov     rbp, [rsp+68h+arg_8]
0x100423248  add     rsp, 40h
0x10042324c  pop     r15
0x10042324e  pop     r14
0x100423250  pop     r12
0x100423252  pop     rdi
0x100423253  pop     rsi
0x100423254  retn
0x100423255  lfence
0x100423258  jmp     short loc_10042323E
```
