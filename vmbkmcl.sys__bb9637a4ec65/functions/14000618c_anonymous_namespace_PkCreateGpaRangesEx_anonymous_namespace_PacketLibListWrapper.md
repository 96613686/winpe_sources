# _anonymous_namespace_::PkCreateGpaRangesEx__anonymous_namespace_::PacketLibListWrapper_

- ea: `0x14000618c`
- end: `0x1400062d7`
- name: `_anonymous_namespace_::PkCreateGpaRangesEx__anonymous_namespace_::PacketLibListWrapper_`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005fe0`

## callees

- `0x14000618c`
- `0x140006478`

## pseudocode

```c
void __fastcall anonymous_namespace_::PkCreateGpaRangesEx__anonymous_namespace_::PacketLibListWrapper_(
        gsl::details *a1,
        __int64 *a2,
        unsigned __int64 *a3)
{
  unsigned int v4; // r9d
  unsigned __int64 v5; // r10
  unsigned int v6; // r8d
  unsigned int *v7; // r12
  unsigned int v8; // r8d
  int v9; // ebp
  unsigned __int64 v10; // rdi
  __int64 v11; // rbp
  _QWORD *v12; // rax
  _QWORD *v13; // rsi
  unsigned __int64 v14; // r9
  _QWORD *v15; // rbx
  unsigned __int64 v16; // rdi
  __int64 v17; // rbp
  unsigned __int64 v18; // rdi
  unsigned __int64 v19; // r10

  v4 = 0;
  while ( a2 )
  {
    v5 = *a3;
    if ( *a3 < 0x10 )
      goto LABEL_19;
    v6 = *((_DWORD *)a2 + 2);
    if ( v4 < v6 )
    {
      v7 = (unsigned int *)a3[1];
      v8 = v6 - v4;
      v9 = *((_DWORD *)a2 + 3);
      v10 = 0;
      *v7 = v8;
      v11 = ((_WORD)v4 + (_WORD)v9) & 0xFFF;
      v7[1] = ((_WORD)v4 + (unsigned __int16)*((_DWORD *)a2 + 3)) & 0xFFF;
      v12 = a2 + 2;
      v13 = (_QWORD *)a2[2];
      v14 = (unsigned __int64)(*((_DWORD *)a2 + 3) + v4) >> 12;
      v15 = (_QWORD *)*v13;
      while ( v10 < v14 )
      {
        if ( v13 == v12 )
          __fastfail(5u);
        v13 = v15;
        ++v10;
        v15 = (_QWORD *)*v15;
      }
      v16 = v11 + v8 + 4095LL;
      v17 = 0;
      v18 = v16 >> 12;
      if ( (_DWORD)v18 )
      {
        do
        {
          if ( v13 == v12 )
            break;
          *(_QWORD *)&v7[2 * v17 + 2] = v13[2];
          v13 = v15;
          v15 = (_QWORD *)*v15;
          v17 = (unsigned int)(v17 + 1);
        }
        while ( (unsigned int)v17 < (unsigned int)v18 );
      }
      a1 = (gsl::details *)(8LL * (unsigned int)(v18 - 1) + 16);
      if ( v5 < (unsigned __int64)a1 || (v19 = v5 - (_QWORD)a1, v19 == -1) )
      {
LABEL_19:
        gsl::details::terminate(a1);
        __debugbreak();
      }
      *a3 = v19;
      a3[1] = (unsigned __int64)a1 + (_QWORD)v7;
      v4 = 0;
    }
    else
    {
      v4 -= v6;
    }
    a2 = (__int64 *)*a2;
  }
}

```

## disassembly

```asm
0x14000618c  mov     [rsp+arg_8], rbx
0x140006191  mov     [rsp+arg_10], rbp
0x140006196  mov     [rsp+arg_0], rcx
0x14000619b  push    rsi
0x14000619c  push    rdi
0x14000619d  push    r12
0x14000619f  push    r14
0x1400061a1  push    r15
0x1400061a3  sub     rsp, 20h
0x1400061a7  xor     r11d, r11d
0x1400061aa  mov     r14, r8
0x1400061ad  xor     r9d, r9d
0x1400061b0  test    rdx, rdx
0x1400061b3  jz      loc_1400062BF
0x1400061b9  mov     r10, [r14]
0x1400061bc  cmp     r10, 10h
0x1400061c0  jb      loc_1400062B9
0x1400061c6  mov     r8d, [rdx+8]
0x1400061ca  cmp     r9d, r8d
0x1400061cd  jb      short loc_1400061D7
0x1400061cf  sub     r9d, r8d
0x1400061d2  jmp     loc_1400062AA
0x1400061d7  mov     r12, [r14+8]
0x1400061db  sub     r8d, r9d
0x1400061de  mov     [rsp+48h+arg_0], 0
0x1400061e7  test    r11d, r11d
0x1400061ea  jz      short loc_1400061F4
0x1400061ec  cmp     r11d, r8d
0x1400061ef  jbe     short loc_140006242
0x1400061f1  sub     r11d, r8d
0x1400061f4  mov     r15b, byte ptr [rsp+48h+arg_0+4]
0x1400061f9  mov     ebp, [rdx+0Ch]
0x1400061fc  xor     edi, edi
0x1400061fe  mov     [r12], r8d
0x140006202  add     ebp, r9d
0x140006205  mov     eax, [rdx+0Ch]
0x140006208  and     ebp, 0FFFh
0x14000620e  add     eax, r9d
0x140006211  and     eax, 0FFFh
0x140006216  mov     [r12+4], eax
0x14000621b  lea     rax, [rdx+10h]
0x14000621f  mov     rsi, [rax]
0x140006222  add     r9d, [rdx+0Ch]
0x140006226  shr     r9, 0Ch
0x14000622a  mov     rbx, [rsi]
0x14000622d  cmp     rdi, r9
0x140006230  jnb     short loc_14000624A
0x140006232  cmp     rsi, rax
0x140006235  jz      short loc_1400062B2
0x140006237  mov     rsi, rbx
0x14000623a  inc     rdi
0x14000623d  mov     rbx, [rbx]
0x140006240  jmp     short loc_14000622D
0x140006242  mov     r15b, 1
0x140006245  mov     r8d, r11d
0x140006248  jmp     short loc_1400061F9
0x14000624a  mov     edi, r8d
0x14000624d  add     rdi, 0FFFh
0x140006254  add     rdi, rbp
0x140006257  xor     ebp, ebp
0x140006259  shr     rdi, 0Ch
0x14000625d  test    edi, edi
0x14000625f  jz      short loc_14000627E
0x140006261  cmp     rsi, rax
0x140006264  jz      short loc_14000627E
0x140006266  mov     rcx, [rsi+10h]
0x14000626a  mov     r9, rbx
0x14000626d  mov     [r12+rbp*8+8], rcx
0x140006272  mov     rsi, r9
0x140006275  mov     rbx, [rbx]
0x140006278  inc     ebp
0x14000627a  cmp     ebp, edi
0x14000627c  jb      short loc_140006261
0x14000627e  lea     eax, [rdi-1]
0x140006281  lea     rcx, ds:10h[rax*8]
0x140006289  cmp     r10, rcx
0x14000628c  jb      short loc_1400062B9
0x14000628e  sub     r10, rcx
0x140006291  cmp     r10, 0FFFFFFFFFFFFFFFFh
0x140006295  jz      short loc_1400062B9
0x140006297  mov     [r14], r10
0x14000629a  lea     rax, [r12+rcx]
0x14000629e  mov     [r14+8], rax
0x1400062a2  test    r15b, r15b
0x1400062a5  jnz     short loc_1400062BF
0x1400062a7  xor     r9d, r9d
0x1400062aa  mov     rdx, [rdx]
0x1400062ad  jmp     loc_1400061B0
0x1400062b2  mov     ecx, 5; this
0x1400062b7  int     29h; Win8: RtlFailFast(ecx)
0x1400062b9  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x1400062be  int     3; Trap to Debugger
0x1400062bf  mov     rbx, [rsp+48h+arg_8]
0x1400062c4  mov     rbp, [rsp+48h+arg_10]
0x1400062c9  add     rsp, 20h
0x1400062cd  pop     r15
0x1400062cf  pop     r14
0x1400062d1  pop     r12
0x1400062d3  pop     rdi
0x1400062d4  pop     rsi
0x1400062d5  retn
```
