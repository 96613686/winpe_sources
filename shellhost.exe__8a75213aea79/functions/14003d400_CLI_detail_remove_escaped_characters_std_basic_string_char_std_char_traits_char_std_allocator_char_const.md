# CLI::detail::remove_escaped_characters(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x14003d400`
- end: `0x14003daca`
- name: `?remove_escaped_characters@detail@CLI@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@@Z`
- size: `1738`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: ``

## callers

- `0x14001aec0`
- `0x14002df60`
- `0x14003ca60`
- `0x14003de60`

## callees

- `0x1400085d0`
- `0x140008810`
- `0x1400088d0`
- `0x14000f290`
- `0x14000f7e0`
- `0x140010668`
- `0x140010da0`
- `0x140010db0`
- `0x14001a3d0`
- `0x14001aea0`
- `0x1400290c0`
- `0x14003d400`
- `0x14003e210`
- `0x140044efc`
- `0x14004e1b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall CLI::detail::remove_escaped_characters(_QWORD *a1, char *a2)
{
  char *v4; // rbx
  char *v5; // rsi
  char *v6; // rax
  unsigned __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r9
  char *v10; // rax
  void **v11; // r14
  char *v12; // rdi
  __int64 trivial_1; // rax
  __int64 v14; // rcx
  void **v15; // rax
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  __int64 v18; // rax
  char v19; // al
  char *v20; // rcx
  int v21; // ecx
  unsigned int v22; // r8d
  unsigned int v23; // r8d
  int v24; // ecx
  unsigned int v25; // edx
  unsigned int v26; // edx
  int v27; // ecx
  unsigned int v28; // ecx
  int v29; // ecx
  int v30; // r9d
  unsigned int v31; // eax
  char *v32; // rcx
  int v33; // ecx
  unsigned int v34; // edi
  unsigned int v35; // edi
  int v36; // ecx
  unsigned int v37; // r11d
  unsigned int v38; // r11d
  int v39; // ecx
  unsigned int v40; // r10d
  unsigned int v41; // r10d
  int v42; // ecx
  unsigned int v43; // r9d
  unsigned int v44; // r9d
  int v45; // ecx
  unsigned int v46; // r8d
  unsigned int v47; // r8d
  int v48; // ecx
  unsigned int v49; // edx
  unsigned int v50; // edx
  int v51; // ecx
  unsigned int v52; // ecx
  int v53; // ecx
  char *v54; // rsi
  int v55; // ebx
  unsigned int v56; // eax
  unsigned __int64 v57; // rcx
  unsigned __int64 v58; // rdx
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rbx
  __int64 v66; // rax
  unsigned __int8 *v67; // rax
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rax
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-91h] BYREF
  _QWORD v72[2]; // [rsp+40h] [rbp-79h] BYREF
  char v73[8]; // [rsp+50h] [rbp-69h] BYREF
  _BYTE v74[32]; // [rsp+58h] [rbp-61h] BYREF
  _BYTE v75[32]; // [rsp+78h] [rbp-41h] BYREF
  char v76[32]; // [rsp+98h] [rbp-21h] BYREF
  char v77[32]; // [rsp+B8h] [rbp-1h] BYREF

  v72[1] = a1;
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 15;
  *(_BYTE *)a1 = 0;
  std::string::reserve(a1);
  v4 = a2;
  if ( *((_QWORD *)a2 + 3) > 0xFu )
    v4 = *(char **)a2;
  while ( 1 )
  {
    v5 = v4;
    v72[0] = v4;
    v6 = a2;
    v7 = *((_QWORD *)a2 + 3);
    if ( v7 > 0xF )
      v6 = *(char **)a2;
    v8 = *((_QWORD *)a2 + 2);
    if ( v4 >= &v6[v8] )
      return a1;
    v9 = (unsigned __int8)*v4;
    if ( (_BYTE)v9 != 92 )
      goto LABEL_18;
    v10 = a2;
    if ( v7 > 0xF )
      v10 = *(char **)a2;
    if ( (__int64)&v10[v8 - (_QWORD)v4] < 2 )
    {
      v60 = std::operator+<char>(v75, "invalid escape sequence ", a2);
      std::invalid_argument::invalid_argument(pExceptionObject, v60);
      throw (std::invalid_argument *)pExceptionObject;
    }
    v5 = v4 + 1;
    v11 = &qword_1400800C8;
    if ( (unsigned __int64)qword_1400800E0 > 0xF )
      v11 = (void **)qword_1400800C8;
    if ( !qword_1400800D8
      || (v12 = (char *)v11 + qword_1400800D8,
          trivial_1 = _std_find_trivial_1(v11, (char *)v11 + qword_1400800D8, (unsigned __int8)*v5),
          (char *)trivial_1 == v12)
      || (v14 = trivial_1 - (_QWORD)v11, trivial_1 - (_QWORD)v11 == -1) )
    {
      v19 = *v5;
      if ( *v5 == 117 )
      {
        if ( *((_QWORD *)a2 + 3) <= 0xFu )
          v20 = a2;
        else
          v20 = *(char **)a2;
        if ( (__int64)&v20[*((_QWORD *)a2 + 2) - (_QWORD)v4] < 6 )
        {
          v62 = std::operator+<char>(v74, "unicode sequence must have 4 hex codes ", a2);
          std::invalid_argument::invalid_argument(pExceptionObject, v62);
          throw (std::invalid_argument *)pExceptionObject;
        }
        v21 = v4[2];
        if ( (unsigned __int8)(v4[2] - 48) > 9u )
        {
          if ( (unsigned __int8)(v21 - 65) > 5u )
          {
            if ( (unsigned __int8)(v21 - 97) > 5u )
              goto LABEL_129;
            v22 = v21 - 87;
          }
          else
          {
            v22 = v21 - 55;
          }
        }
        else
        {
          v22 = v21 - 48;
        }
        if ( v22 > 0xF )
          goto LABEL_129;
        v23 = v22 << 12;
        v24 = v4[3];
        if ( (unsigned __int8)(v4[3] - 48) > 9u )
        {
          if ( (unsigned __int8)(v24 - 65) > 5u )
          {
            if ( (unsigned __int8)(v24 - 97) > 5u )
              goto LABEL_129;
            v25 = v24 - 87;
          }
          else
          {
            v25 = v24 - 55;
          }
        }
        else
        {
          v25 = v24 - 48;
        }
        if ( v25 > 0xF )
          goto LABEL_129;
        v26 = v25 << 8;
        v27 = v4[4];
        if ( (unsigned __int8)(v4[4] - 48) > 9u )
        {
          if ( (unsigned __int8)(v27 - 65) > 5u )
          {
            if ( (unsigned __int8)(v27 - 97) > 5u )
              goto LABEL_129;
            v28 = v27 - 87;
          }
          else
          {
            v28 = v27 - 55;
          }
        }
        else
        {
          v28 = v27 - 48;
        }
        if ( v28 > 0xF )
          goto LABEL_129;
        v29 = 16 * v28;
        v30 = v4[5];
        if ( (unsigned __int8)(v4[5] - 48) > 9u )
        {
          if ( (unsigned __int8)(v30 - 65) > 5u )
          {
            if ( (unsigned __int8)(v30 - 97) > 5u )
              goto LABEL_129;
            v31 = v30 - 87;
          }
          else
          {
            v31 = v30 - 55;
          }
        }
        else
        {
          v31 = v30 - 48;
        }
        if ( v31 > 0xF )
        {
LABEL_129:
          v61 = std::operator+<char>(v74, "unicode sequence must have 4 hex codes ", a2);
          std::invalid_argument::invalid_argument(pExceptionObject, v61);
          throw (std::invalid_argument *)pExceptionObject;
        }
        CLI::detail::append_codepoint(a1, v31 + v23 + v29 + v26);
        v4 += 6;
      }
      else if ( v19 == 85 )
      {
        if ( *((_QWORD *)a2 + 3) <= 0xFu )
          v32 = a2;
        else
          v32 = *(char **)a2;
        if ( (__int64)&v32[*((_QWORD *)a2 + 2) - (_QWORD)v4] < 10 )
        {
          v64 = std::operator+<char>(v74, "unicode sequence must have 8 hex codes ", a2);
          std::invalid_argument::invalid_argument(pExceptionObject, v64);
          throw (std::invalid_argument *)pExceptionObject;
        }
        v33 = v4[2];
        if ( (unsigned __int8)(v4[2] - 48) > 9u )
        {
          if ( (unsigned __int8)(v33 - 65) > 5u )
          {
            if ( (unsigned __int8)(v33 - 97) > 5u )
              goto LABEL_131;
            v34 = v33 - 87;
          }
          else
          {
            v34 = v33 - 55;
          }
        }
        else
        {
          v34 = v33 - 48;
        }
        if ( v34 > 0xF )
          goto LABEL_131;
        v35 = v34 << 28;
        v36 = v4[3];
        if ( (unsigned __int8)(v4[3] - 48) > 9u )
        {
          if ( (unsigned __int8)(v36 - 65) > 5u )
          {
            if ( (unsigned __int8)(v36 - 97) > 5u )
              goto LABEL_131;
            v37 = v36 - 87;
          }
          else
          {
            v37 = v36 - 55;
          }
        }
        else
        {
          v37 = v36 - 48;
        }
        if ( v37 > 0xF )
          goto LABEL_131;
        v38 = v37 << 24;
        v39 = v4[4];
        if ( (unsigned __int8)(v4[4] - 48) > 9u )
        {
          if ( (unsigned __int8)(v39 - 65) > 5u )
          {
            if ( (unsigned __int8)(v39 - 97) > 5u )
              goto LABEL_131;
            v40 = v39 - 87;
          }
          else
          {
            v40 = v39 - 55;
          }
        }
        else
        {
          v40 = v39 - 48;
        }
        if ( v40 > 0xF )
          goto LABEL_131;
        v41 = v40 << 20;
        v42 = v4[5];
        if ( (unsigned __int8)(v4[5] - 48) > 9u )
        {
          if ( (unsigned __int8)(v42 - 65) > 5u )
          {
            if ( (unsigned __int8)(v42 - 97) > 5u )
              goto LABEL_131;
            v43 = v42 - 87;
          }
          else
          {
            v43 = v42 - 55;
          }
        }
        else
        {
          v43 = v42 - 48;
        }
        if ( v43 > 0xF )
          goto LABEL_131;
        v44 = v43 << 16;
        v45 = v4[6];
        if ( (unsigned __int8)(v4[6] - 48) > 9u )
        {
          if ( (unsigned __int8)(v45 - 65) > 5u )
          {
            if ( (unsigned __int8)(v45 - 97) > 5u )
              goto LABEL_131;
            v46 = v45 - 87;
          }
          else
          {
            v46 = v45 - 55;
          }
        }
        else
        {
          v46 = v45 - 48;
        }
        if ( v46 > 0xF )
          goto LABEL_131;
        v47 = v46 << 12;
        v48 = v4[7];
        if ( (unsigned __int8)(v4[7] - 48) > 9u )
        {
          if ( (unsigned __int8)(v48 - 65) > 5u )
          {
            if ( (unsigned __int8)(v48 - 97) > 5u )
              goto LABEL_131;
            v49 = v48 - 87;
          }
          else
          {
            v49 = v48 - 55;
          }
        }
        else
        {
          v49 = v48 - 48;
        }
        if ( v49 > 0xF )
          goto LABEL_131;
        v50 = v49 << 8;
        v51 = v4[8];
        if ( (unsigned __int8)(v4[8] - 48) > 9u )
        {
          if ( (unsigned __int8)(v51 - 65) > 5u )
          {
            if ( (unsigned __int8)(v51 - 97) > 5u )
              goto LABEL_131;
            v52 = v51 - 87;
          }
          else
          {
            v52 = v51 - 55;
          }
        }
        else
        {
          v52 = v51 - 48;
        }
        if ( v52 > 0xF )
          goto LABEL_131;
        v53 = 16 * v52;
        v54 = v4 + 9;
        v55 = v4[9];
        if ( (unsigned __int8)(v55 - 48) > 9u )
        {
          if ( (unsigned __int8)(v55 - 65) > 5u )
          {
            if ( (unsigned __int8)(v55 - 97) > 5u )
              goto LABEL_131;
            v56 = v55 - 87;
          }
          else
          {
            v56 = v55 - 55;
          }
        }
        else
        {
          v56 = v55 - 48;
        }
        if ( v56 > 0xF )
        {
LABEL_131:
          v63 = std::operator+<char>(v74, "unicode sequence must have 8 hex codes ", a2);
          std::invalid_argument::invalid_argument(pExceptionObject, v63);
          throw (std::invalid_argument *)pExceptionObject;
        }
        CLI::detail::append_codepoint(a1, v56 + v35 + v38 + v41 + v44 + v47 + v53 + v50);
        v4 = v54 + 1;
      }
      else
      {
        if ( v19 != 48 )
        {
          v65 = std::string::string(v74, "unrecognized escape sequence \\");
          v66 = std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>::operator+(v72, v73, 1);
          v67 = (unsigned __int8 *)std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>::operator*(v66);
          v68 = std::operator+<char>(v76, v65, *v67);
          v69 = std::operator+<char>(v77, v68, " in ");
          v70 = std::operator+<char>(v75, v69, a2);
          std::invalid_argument::invalid_argument(pExceptionObject, v70);
          throw (std::invalid_argument *)pExceptionObject;
        }
        v57 = a1[2];
        v58 = a1[3];
        if ( v57 >= v58 )
        {
          v9 = 0;
LABEL_125:
          std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(a1, 1, 0, v9);
          v4 = v5 + 1;
        }
        else
        {
          a1[2] = v57 + 1;
          if ( v58 <= 0xF )
            *(_WORD *)((char *)a1 + v57) = 0;
          else
            *(_WORD *)(*a1 + v57) = 0;
          v4 += 2;
        }
      }
    }
    else
    {
      v15 = &qword_1400800A8;
      if ( (unsigned __int64)qword_1400800C0 > 0xF )
        v15 = (void **)qword_1400800A8;
      v9 = *((unsigned __int8 *)v15 + v14);
LABEL_18:
      v16 = a1[2];
      v17 = a1[3];
      if ( v16 >= v17 )
        goto LABEL_125;
      a1[2] = v16 + 1;
      if ( v17 <= 0xF )
      {
        *((_BYTE *)a1 + v16 + 1) = 0;
        *((_BYTE *)a1 + v16) = v9;
      }
      else
      {
        v18 = *a1;
        *(_BYTE *)(v16 + v18 + 1) = 0;
        *(_BYTE *)(v16 + v18) = v9;
      }
      v4 = v5 + 1;
    }
  }
}

```

## disassembly

```asm
0x14003d400  mov     [rsp-8+arg_10], rbx
0x14003d405  push    rbp
0x14003d406  push    rsi
0x14003d407  push    rdi
0x14003d408  push    r12
0x14003d40a  push    r13
0x14003d40c  push    r14
0x14003d40e  push    r15
0x14003d410  lea     rbp, [rsp-27h]
0x14003d415  sub     rsp, 0E0h
0x14003d41c  mov     rax, cs:__security_cookie
0x14003d423  xor     rax, rsp
0x14003d426  mov     [rbp+57h+var_38], rax
0x14003d42a  mov     r12, rdx
0x14003d42d  mov     r15, rcx
0x14003d430  mov     [rbp+57h+var_C8], rcx
0x14003d434  xor     eax, eax
0x14003d436  mov     [rsp+110h+var_F0], eax
0x14003d43a  xorps   xmm0, xmm0
0x14003d43d  movups  xmmword ptr [rcx], xmm0
0x14003d440  mov     [rcx+10h], rax
0x14003d444  mov     qword ptr [rcx+18h], 0Fh
0x14003d44c  mov     [rcx], al
0x14003d44e  mov     [rsp+110h+var_F0], 1
0x14003d456  mov     rdx, [rdx+10h]
0x14003d45a  call    ?reserve@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K@Z; std::string::reserve(unsigned __int64)
0x14003d45f  mov     rbx, r12
0x14003d462  cmp     qword ptr [r12+18h], 0Fh
0x14003d468  jbe     short loc_14003D46E
0x14003d46a  mov     rbx, [r12]
0x14003d46e  lea     r13, qword_1400800C8
0x14003d475  mov     rsi, rbx
0x14003d478  mov     [rbp+57h+var_D0], rbx
0x14003d47c  mov     rax, r12
0x14003d47f  mov     rdx, [r12+18h]
0x14003d484  cmp     rdx, 0Fh
0x14003d488  jbe     short loc_14003D48E
0x14003d48a  mov     rax, [r12]
0x14003d48e  mov     rcx, [r12+10h]
0x14003d493  add     rax, rcx
0x14003d496  cmp     rsi, rax
0x14003d499  jnb     loc_14003D91F
0x14003d49f  movzx   r9d, byte ptr [rbx]
0x14003d4a3  cmp     r9b, 5Ch ; '\'
0x14003d4a7  jnz     loc_14003D52D
0x14003d4ad  mov     rax, r12
0x14003d4b0  cmp     rdx, 0Fh
0x14003d4b4  jbe     short loc_14003D4BA
0x14003d4b6  mov     rax, [r12]
0x14003d4ba  sub     rcx, rsi
0x14003d4bd  add     rcx, rax
0x14003d4c0  cmp     rcx, 2
0x14003d4c4  jl      loc_14003D949
0x14003d4ca  lea     rsi, [rbx+1]
0x14003d4ce  mov     r14, r13
0x14003d4d1  cmp     cs:qword_1400800E0, 0Fh
0x14003d4d9  cmova   r14, cs:qword_1400800C8
0x14003d4e1  mov     rax, cs:qword_1400800D8
0x14003d4e8  test    rax, rax
0x14003d4eb  jz      short loc_14003D565
0x14003d4ed  lea     rdi, [rax+r14]
0x14003d4f1  movzx   r8d, byte ptr [rsi]
0x14003d4f5  mov     rdx, rdi
0x14003d4f8  mov     rcx, r14
0x14003d4fb  call    __std_find_trivial_1
0x14003d500  mov     rcx, rax
0x14003d503  cmp     rax, rdi
0x14003d506  jz      short loc_14003D565
0x14003d508  sub     rcx, r14
0x14003d50b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14003d50f  jz      short loc_14003D565
0x14003d511  lea     rax, qword_1400800A8
0x14003d518  cmp     cs:qword_1400800C0, 0Fh
0x14003d520  cmova   rax, cs:qword_1400800A8
0x14003d528  movzx   r9d, byte ptr [rcx+rax]
0x14003d52d  mov     rcx, [r15+10h]
0x14003d531  mov     rdx, [r15+18h]
0x14003d535  cmp     rcx, rdx
0x14003d538  jnb     loc_14003D8F1
0x14003d53e  lea     rax, [rcx+1]
0x14003d542  mov     [r15+10h], rax
0x14003d546  cmp     rdx, 0Fh
0x14003d54a  jbe     loc_14003D90A
0x14003d550  mov     rax, [r15]
0x14003d553  mov     byte ptr [rcx+rax+1], 0
0x14003d558  mov     [rcx+rax], r9b
0x14003d55c  lea     rbx, [rsi+1]
0x14003d560  jmp     loc_14003D475
0x14003d565  movzx   eax, byte ptr [rsi]
0x14003d568  cmp     al, 75h ; 'u'
0x14003d56a  jnz     loc_14003D692
0x14003d570  cmp     qword ptr [r12+18h], 0Fh
0x14003d576  jbe     short loc_14003D57E
0x14003d578  mov     rcx, [r12]
0x14003d57c  jmp     short loc_14003D581
0x14003d57e  mov     rcx, r12
0x14003d581  mov     rax, [r12+10h]
0x14003d586  sub     rax, rbx
0x14003d589  add     rax, rcx
0x14003d58c  cmp     rax, 6
0x14003d590  jl      loc_14003D9AF
0x14003d596  movsx   ecx, byte ptr [rbx+2]
0x14003d59a  lea     eax, [rcx-30h]
0x14003d59d  cmp     al, 9
0x14003d59f  ja      short loc_14003D5A7
0x14003d5a1  lea     r8d, [rcx-30h]
0x14003d5a5  jmp     short loc_14003D5C3
0x14003d5a7  lea     eax, [rcx-41h]
0x14003d5aa  cmp     al, 5
0x14003d5ac  ja      short loc_14003D5B4
0x14003d5ae  lea     r8d, [rcx-37h]
0x14003d5b2  jmp     short loc_14003D5C3
0x14003d5b4  lea     eax, [rcx-61h]
0x14003d5b7  cmp     al, 5
0x14003d5b9  ja      loc_14003D97C
0x14003d5bf  lea     r8d, [rcx-57h]
0x14003d5c3  cmp     r8d, 0Fh
0x14003d5c7  ja      loc_14003D97C
0x14003d5cd  shl     r8d, 0Ch
0x14003d5d1  movsx   ecx, byte ptr [rbx+3]
0x14003d5d5  lea     eax, [rcx-30h]
0x14003d5d8  cmp     al, 9
0x14003d5da  ja      short loc_14003D5E1
0x14003d5dc  lea     edx, [rcx-30h]
0x14003d5df  jmp     short loc_14003D5FB
0x14003d5e1  lea     eax, [rcx-41h]
0x14003d5e4  cmp     al, 5
0x14003d5e6  ja      short loc_14003D5ED
0x14003d5e8  lea     edx, [rcx-37h]
0x14003d5eb  jmp     short loc_14003D5FB
0x14003d5ed  lea     eax, [rcx-61h]
0x14003d5f0  cmp     al, 5
0x14003d5f2  ja      loc_14003D97C
0x14003d5f8  lea     edx, [rcx-57h]
0x14003d5fb  cmp     edx, 0Fh
0x14003d5fe  ja      loc_14003D97C
0x14003d604  shl     edx, 8
0x14003d607  movsx   ecx, byte ptr [rbx+4]
0x14003d60b  lea     eax, [rcx-30h]
0x14003d60e  cmp     al, 9
0x14003d610  ja      short loc_14003D617
0x14003d612  sub     ecx, 30h ; '0'
0x14003d615  jmp     short loc_14003D631
0x14003d617  lea     eax, [rcx-41h]
0x14003d61a  cmp     al, 5
0x14003d61c  ja      short loc_14003D623
0x14003d61e  sub     ecx, 37h ; '7'
0x14003d621  jmp     short loc_14003D631
0x14003d623  lea     eax, [rcx-61h]
0x14003d626  cmp     al, 5
0x14003d628  ja      loc_14003D97C
0x14003d62e  sub     ecx, 57h ; 'W'
0x14003d631  cmp     ecx, 0Fh
0x14003d634  ja      loc_14003D97C
0x14003d63a  shl     ecx, 4
0x14003d63d  lea     rsi, [rbx+5]
0x14003d641  movsx   r9d, byte ptr [rsi]
0x14003d645  lea     eax, [r9-30h]
0x14003d649  cmp     al, 9
0x14003d64b  ja      short loc_14003D653
0x14003d64d  lea     eax, [r9-30h]
0x14003d651  jmp     short loc_14003D671
0x14003d653  lea     eax, [r9-41h]
0x14003d657  cmp     al, 5
0x14003d659  ja      short loc_14003D661
0x14003d65b  lea     eax, [r9-37h]
0x14003d65f  jmp     short loc_14003D671
0x14003d661  lea     eax, [r9-61h]
0x14003d665  cmp     al, 5
0x14003d667  ja      loc_14003D97C
0x14003d66d  lea     eax, [r9-57h]
0x14003d671  cmp     eax, 0Fh
0x14003d674  ja      loc_14003D97C
0x14003d67a  add     edx, ecx
0x14003d67c  add     edx, r8d
0x14003d67f  add     edx, eax
0x14003d681  mov     rcx, r15
0x14003d684  call    ?append_codepoint@detail@CLI@@YAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@Z; CLI::detail::append_codepoint(std::string &,uint)
0x14003d689  lea     rbx, [rsi+1]
0x14003d68d  jmp     loc_14003D475
0x14003d692  cmp     al, 55h ; 'U'
0x14003d694  jnz     loc_14003D8A7
0x14003d69a  cmp     qword ptr [r12+18h], 0Fh
0x14003d6a0  jbe     short loc_14003D6A8
0x14003d6a2  mov     rcx, [r12]
0x14003d6a6  jmp     short loc_14003D6AB
0x14003d6a8  mov     rcx, r12
0x14003d6ab  mov     rax, [r12+10h]
0x14003d6b0  sub     rax, rbx
0x14003d6b3  add     rax, rcx
0x14003d6b6  cmp     rax, 0Ah
0x14003d6ba  jl      loc_14003DA15
0x14003d6c0  movsx   ecx, byte ptr [rbx+2]
0x14003d6c4  lea     eax, [rcx-30h]
0x14003d6c7  cmp     al, 9
0x14003d6c9  ja      short loc_14003D6D0
0x14003d6cb  lea     edi, [rcx-30h]
0x14003d6ce  jmp     short loc_14003D6EA
0x14003d6d0  lea     eax, [rcx-41h]
0x14003d6d3  cmp     al, 5
0x14003d6d5  ja      short loc_14003D6DC
0x14003d6d7  lea     edi, [rcx-37h]
0x14003d6da  jmp     short loc_14003D6EA
0x14003d6dc  lea     eax, [rcx-61h]
0x14003d6df  cmp     al, 5
0x14003d6e1  ja      loc_14003D9E2
0x14003d6e7  lea     edi, [rcx-57h]
0x14003d6ea  cmp     edi, 0Fh
0x14003d6ed  ja      loc_14003D9E2
0x14003d6f3  shl     edi, 1Ch
0x14003d6f6  movsx   ecx, byte ptr [rbx+3]
0x14003d6fa  lea     eax, [rcx-30h]
0x14003d6fd  cmp     al, 9
0x14003d6ff  ja      short loc_14003D707
0x14003d701  lea     r11d, [rcx-30h]
0x14003d705  jmp     short loc_14003D723
0x14003d707  lea     eax, [rcx-41h]
0x14003d70a  cmp     al, 5
0x14003d70c  ja      short loc_14003D714
0x14003d70e  lea     r11d, [rcx-37h]
0x14003d712  jmp     short loc_14003D723
0x14003d714  lea     eax, [rcx-61h]
0x14003d717  cmp     al, 5
0x14003d719  ja      loc_14003D9E2
0x14003d71f  lea     r11d, [rcx-57h]
0x14003d723  cmp     r11d, 0Fh
0x14003d727  ja      loc_14003D9E2
0x14003d72d  shl     r11d, 18h
0x14003d731  movsx   ecx, byte ptr [rbx+4]
0x14003d735  lea     eax, [rcx-30h]
0x14003d738  cmp     al, 9
0x14003d73a  ja      short loc_14003D742
0x14003d73c  lea     r10d, [rcx-30h]
0x14003d740  jmp     short loc_14003D75E
0x14003d742  lea     eax, [rcx-41h]
0x14003d745  cmp     al, 5
0x14003d747  ja      short loc_14003D74F
0x14003d749  lea     r10d, [rcx-37h]
0x14003d74d  jmp     short loc_14003D75E
0x14003d74f  lea     eax, [rcx-61h]
0x14003d752  cmp     al, 5
0x14003d754  ja      loc_14003D9E2
0x14003d75a  lea     r10d, [rcx-57h]
0x14003d75e  cmp     r10d, 0Fh
0x14003d762  ja      loc_14003D9E2
0x14003d768  shl     r10d, 14h
0x14003d76c  movsx   ecx, byte ptr [rbx+5]
0x14003d770  lea     eax, [rcx-30h]
0x14003d773  cmp     al, 9
0x14003d775  ja      short loc_14003D77D
0x14003d777  lea     r9d, [rcx-30h]
0x14003d77b  jmp     short loc_14003D799
0x14003d77d  lea     eax, [rcx-41h]
0x14003d780  cmp     al, 5
0x14003d782  ja      short loc_14003D78A
0x14003d784  lea     r9d, [rcx-37h]
0x14003d788  jmp     short loc_14003D799
0x14003d78a  lea     eax, [rcx-61h]
0x14003d78d  cmp     al, 5
0x14003d78f  ja      loc_14003D9E2
0x14003d795  lea     r9d, [rcx-57h]
0x14003d799  cmp     r9d, 0Fh
0x14003d79d  ja      loc_14003D9E2
0x14003d7a3  shl     r9d, 10h
0x14003d7a7  movsx   ecx, byte ptr [rbx+6]
0x14003d7ab  lea     eax, [rcx-30h]
0x14003d7ae  cmp     al, 9
0x14003d7b0  ja      short loc_14003D7B8
0x14003d7b2  lea     r8d, [rcx-30h]
0x14003d7b6  jmp     short loc_14003D7D4
0x14003d7b8  lea     eax, [rcx-41h]
0x14003d7bb  cmp     al, 5
0x14003d7bd  ja      short loc_14003D7C5
0x14003d7bf  lea     r8d, [rcx-37h]
0x14003d7c3  jmp     short loc_14003D7D4
0x14003d7c5  lea     eax, [rcx-61h]
0x14003d7c8  cmp     al, 5
0x14003d7ca  ja      loc_14003D9E2
0x14003d7d0  lea     r8d, [rcx-57h]
0x14003d7d4  cmp     r8d, 0Fh
0x14003d7d8  ja      loc_14003D9E2
0x14003d7de  shl     r8d, 0Ch
0x14003d7e2  movsx   ecx, byte ptr [rbx+7]
0x14003d7e6  lea     eax, [rcx-30h]
0x14003d7e9  cmp     al, 9
0x14003d7eb  ja      short loc_14003D7F2
0x14003d7ed  lea     edx, [rcx-30h]
0x14003d7f0  jmp     short loc_14003D80C
0x14003d7f2  lea     eax, [rcx-41h]
0x14003d7f5  cmp     al, 5
0x14003d7f7  ja      short loc_14003D7FE
0x14003d7f9  lea     edx, [rcx-37h]
0x14003d7fc  jmp     short loc_14003D80C
0x14003d7fe  lea     eax, [rcx-61h]
0x14003d801  cmp     al, 5
0x14003d803  ja      loc_14003D9E2
0x14003d809  lea     edx, [rcx-57h]
0x14003d80c  cmp     edx, 0Fh
0x14003d80f  ja      loc_14003D9E2
0x14003d815  shl     edx, 8
  ... truncated ...
```
