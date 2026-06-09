# RtlpUnwindEpilogue<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT_FOR_STACKWALK *>(unsigned __int64,unsigned __int64,ulong,CDirectFnEnt,_CONTEXT_FOR_STACKWALK *,_AMD64_UNWIND_PARAMS *)

- ea: `0x1400deb54`
- end: `0x1400df031`
- name: `??$RtlpUnwindEpilogue@VCDirectFnEnt@@VCDirectUnwindInfo@@VCDirectMemoryAccessors@@PEAU_CONTEXT_FOR_STACKWALK@@@@YAJ_K0KVCDirectFnEnt@@PEAU_CONTEXT_FOR_STACKWALK@@PEAU_AMD64_UNWIND_PARAMS@@@Z`
- size: `1245`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400e1000`

## callees

- `0x14002c6a8`
- `0x1400442ac`
- `0x1400de58c`
- `0x1400deb54`

## pseudocode

```c
__int64 __fastcall RtlpUnwindEpilogue<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT_FOR_STACKWALK *>(
        __int64 a1,
        unsigned __int64 a2,
        unsigned int a3,
        _BYTE *a4,
        _QWORD *a5,
        __int64 a6)
{
  int v6; // r12d
  int v7; // r13d
  _BYTE *v8; // rbx
  unsigned int v9; // edx
  unsigned int v10; // edi
  unsigned int v11; // r14d
  char v12; // al
  __int64 result; // rax
  __int64 v14; // r8
  _QWORD *v15; // r11
  unsigned int v16; // r12d
  unsigned int v17; // r10d
  _QWORD *v18; // r9
  __int64 v19; // r9
  __int64 v20; // rcx
  _QWORD *v21; // rbx
  _QWORD *v22; // r14
  _QWORD *v23; // rbx
  _QWORD *v24; // [rsp+48h] [rbp-70h]
  __int64 v25; // [rsp+C0h] [rbp+8h]
  __int16 v26; // [rsp+C0h] [rbp+8h]
  unsigned int v29; // [rsp+D8h] [rbp+20h]

  v25 = a1;
  v6 = 0;
  v7 = 0;
  while ( 1 )
  {
    v8 = (_BYTE *)(a1 + *((unsigned int *)a4 + 2));
    v9 = (unsigned __int8)v8[2];
    v29 = v9;
    v10 = v9;
    v11 = 0;
    if ( v8[2] )
    {
      do
      {
        v12 = HIBYTE(*(_WORD *)&v8[2 * v11 + 4]) & 0xF;
        if ( !v12 || v12 == 10 )
          break;
        if ( v12 != 2 || (*(_WORD *)&v8[2 * v11 + 4] & 0xF000u) != 0 )
        {
          if ( v10 != v9 )
            v10 = -1;
        }
        else
        {
          v10 = v11;
        }
        if ( (unsigned __int8)(v12 - 1) <= 1u )
          ++v7;
        v11 += RtlpUnwindOpSlots();
        v9 = v29;
      }
      while ( v11 < v29 );
    }
    if ( v11 < v9 || (*v8 & 0x20) == 0 )
      break;
    if ( (unsigned int)++v6 > 0x20 )
      return 3221225727LL;
    a4 = &v8[2 * (unsigned __int8)v8[2] + 4 + 2 * (v8[2] & 1)];
    a1 = v25;
  }
  v14 = a6;
  v15 = (_QWORD *)a6;
  if ( v10 < v9 && v7 == 2 && v11 == v9 )
    v11 = v10;
  v16 = 0;
  while ( 1 )
  {
    if ( v11 >= v9 )
      goto LABEL_62;
    v26 = *(_WORD *)&v8[2 * v11 + 4];
    v17 = HIBYTE(v26) >> 4;
    if ( (v26 & 0xF00) != 0 )
      break;
    if ( v16 >= a3 )
    {
      v18 = (_QWORD *)a5[1];
      v24 = v18;
      if ( a2 < 0x7FFFFFFF0000LL )
      {
        ProbeForRead(v18, 1u, 4u);
        v18 = v24;
        v17 = HIBYTE(v26) >> 4;
        v14 = a6;
        v15 = (_QWORD *)a6;
      }
      if ( *v15 && ((unsigned __int64)v18 < *(_QWORD *)*v15 || (unsigned __int64)v18 > **(_QWORD **)(v14 + 8) - 8LL) )
        return 3221225512LL;
      a5[1] += 8LL;
      RtlpAmd64SetContextGp<_CONTEXT_FOR_STACKWALK *>(a5, v17, *v18);
      v14 = a6;
      v20 = *(_QWORD *)(a6 + 16);
      v9 = v29;
      if ( v20 )
        *(_QWORD *)(v20 + 8LL * v17 + 128) = v19;
    }
    if ( v17 < 8 )
      ++v16;
    else
      v16 += 2;
    ++v11;
  }
  if ( v11 >= v9 )
    goto LABEL_62;
  if ( (HIBYTE(v26) & 0xF) == 2 && !v17 )
  {
    if ( v16 >= a3 )
      a5[1] += 8LL;
    ++v11;
  }
  if ( v11 >= v9 || (v8[2 * v11 + 5] & 0xF) != 0xA )
  {
LABEL_62:
    v23 = (_QWORD *)a5[1];
    if ( a2 < 0x7FFFFFFF0000LL )
    {
      ProbeForRead(v23, 1u, 4u);
      v14 = a6;
      v15 = (_QWORD *)a6;
    }
    if ( !*v15 || (unsigned __int64)v23 >= *(_QWORD *)*v15 && (unsigned __int64)v23 <= **(_QWORD **)(v14 + 8) - 8LL )
    {
      *a5 = *v23;
      a5[1] += 8LL;
      return 0;
    }
    return 3221225512LL;
  }
  v21 = (_QWORD *)a5[1];
  if ( a2 < 0x7FFFFFFF0000LL )
  {
    ProbeForRead(v21, 1u, 4u);
    v14 = a6;
    v15 = (_QWORD *)a6;
  }
  if ( *v15 && ((unsigned __int64)v21 < *(_QWORD *)*v15 || (unsigned __int64)v21 > **(_QWORD **)(v14 + 8) - 8LL) )
    result = 3221225512LL;
  else
    result = 0;
  v22 = v21 + 3;
  if ( (int)result >= 0 )
  {
    if ( a2 < 0x7FFFFFFF0000LL )
      ProbeForRead(v21 + 3, 1u, 4u);
    if ( !*(_QWORD *)a6
      || (unsigned __int64)v22 >= **(_QWORD **)a6 && (unsigned __int64)v22 <= **(_QWORD **)(a6 + 8) - 8LL )
    {
      *a5 = *v21;
      a5[1] = *v22;
      return 0;
    }
    return 3221225512LL;
  }
  return result;
}

```

## disassembly

```asm
0x1400deb54  mov     [rsp+arg_10], r8d
0x1400deb59  mov     [rsp+arg_8], rdx
0x1400deb5e  mov     [rsp+arg_0], rcx
0x1400deb63  push    rbx
0x1400deb64  push    rsi
0x1400deb65  push    rdi
0x1400deb66  push    r12
0x1400deb68  push    r13
0x1400deb6a  push    r14
0x1400deb6c  push    r15
0x1400deb6e  sub     rsp, 80h
0x1400deb75  xor     esi, esi
0x1400deb77  mov     r12d, esi
0x1400deb7a  mov     r13d, esi
0x1400deb7d  lea     r15d, [rsi+1]
0x1400deb81  mov     ebx, [r9+8]
0x1400deb85  add     rbx, rcx
0x1400deb88  mov     [rsp+0B8h+var_60], rbx
0x1400deb8d  movzx   edx, byte ptr [rbx+2]
0x1400deb91  mov     dword ptr [rsp+0B8h+arg_18], edx
0x1400deb98  mov     edi, edx
0x1400deb9a  mov     r14d, esi
0x1400deb9d  test    edx, edx
0x1400deb9f  jz      short loc_1400DEBF5
0x1400deba1  mov     ecx, r14d
0x1400deba4  movzx   ecx, word ptr [rbx+rcx*2+4]
0x1400deba9  movzx   r8d, cx
0x1400debad  shr     r8w, 8
0x1400debb2  mov     al, r8b
0x1400debb5  and     al, 0Fh
0x1400debb7  jz      short loc_1400DEBF5
0x1400debb9  cmp     al, 0Ah
0x1400debbb  jz      short loc_1400DEBF5
0x1400debbd  cmp     al, 2
0x1400debbf  jnz     short loc_1400DEBCC
0x1400debc1  test    r8b, 0F0h
0x1400debc5  jnz     short loc_1400DEBCC
0x1400debc7  mov     edi, r14d
0x1400debca  jmp     short loc_1400DEBD6
0x1400debcc  or      r8d, 0FFFFFFFFh
0x1400debd0  cmp     edi, edx
0x1400debd2  cmovnz  edi, r8d
0x1400debd6  sub     al, r15b
0x1400debd9  cmp     al, r15b
0x1400debdc  ja      short loc_1400DEBE1
0x1400debde  add     r13d, r15d
0x1400debe1  call    RtlpUnwindOpSlots
0x1400debe6  add     r14d, eax
0x1400debe9  mov     edx, dword ptr [rsp+0B8h+arg_18]
0x1400debf0  cmp     r14d, edx
0x1400debf3  jb      short loc_1400DEBA1
0x1400debf5  cmp     r14d, edx
0x1400debf8  jb      short loc_1400DEC34
0x1400debfa  test    byte ptr [rbx], 20h
0x1400debfd  jz      short loc_1400DEC34
0x1400debff  add     r12d, r15d
0x1400dec02  cmp     r12d, 20h ; ' '
0x1400dec06  ja      short loc_1400DEC2A
0x1400dec08  movzx   eax, byte ptr [rbx+2]
0x1400dec0c  mov     r9d, eax
0x1400dec0f  and     r9d, r15d
0x1400dec12  add     r9d, eax
0x1400dec15  add     r9, 2
0x1400dec19  lea     r9, [rbx+r9*2]
0x1400dec1d  mov     rcx, [rsp+0B8h+arg_0]
0x1400dec25  jmp     loc_1400DEB81
0x1400dec2a  mov     eax, 0C00000FFh
0x1400dec2f  jmp     loc_1400DF01D
0x1400dec34  mov     r8, [rsp+0B8h+arg_28]
0x1400dec3c  mov     r11, r8
0x1400dec3f  mov     [rsp+0B8h+var_80], r8
0x1400dec44  cmp     edi, edx
0x1400dec46  jnb     short loc_1400DEC55
0x1400dec48  cmp     r13d, 2
0x1400dec4c  jnz     short loc_1400DEC55
0x1400dec4e  cmp     r14d, edx
0x1400dec51  cmovz   r14d, edi
0x1400dec55  mov     r12d, esi
0x1400dec58  mov     [rsp+0B8h+var_98], esi
0x1400dec5c  mov     word ptr [rsp+0B8h+arg_0], si
0x1400dec64  mov     r10d, esi
0x1400dec67  mov     r13, [rsp+0B8h+arg_20]
0x1400dec6f  mov     [rsp+0B8h+var_84], r14d
0x1400dec74  cmp     r14d, edx
0x1400dec77  jnb     loc_1400DEF76
0x1400dec7d  mov     eax, r14d
0x1400dec80  movzx   ecx, word ptr [rbx+rax*2+4]
0x1400dec85  mov     word ptr [rsp+0B8h+arg_0], cx
0x1400dec8d  shr     cx, 8
0x1400dec91  movzx   eax, cl
0x1400dec94  mov     r10d, eax
0x1400dec97  shr     r10d, 4
0x1400dec9b  mov     [rsp+0B8h+var_88], r10d
0x1400deca0  test    al, 0Fh
0x1400deca2  jnz     loc_1400DEDCB
0x1400deca8  cmp     r12d, [rsp+0B8h+arg_10]
0x1400decb0  jb      loc_1400DEDAF
0x1400decb6  lea     rax, [r13+8]
0x1400decba  mov     [rsp+0B8h+var_90], rax
0x1400decbf  mov     r9, [rax]
0x1400decc2  mov     [rsp+0B8h+var_70], r9
0x1400decc7  mov     [rsp+0B8h+var_68], r9
0x1400deccc  mov     rax, 7FFFFFFF0000h
0x1400decd6  cmp     [rsp+0B8h+arg_8], rax
0x1400decde  jnb     short loc_1400DED14
0x1400dece0  mov     [rsp+0B8h+var_78], 8
0x1400dece9  mov     [rsp+0B8h+var_78], r15
0x1400decee  mov     r8d, 4; Alignment
0x1400decf4  mov     rdx, r15; Length
0x1400decf7  mov     rcx, r9; Address
0x1400decfa  call    ProbeForRead
0x1400decff  mov     r9, [rsp+0B8h+var_70]
0x1400ded04  mov     r10d, [rsp+0B8h+var_88]
0x1400ded09  mov     r8, [rsp+0B8h+arg_28]
0x1400ded11  mov     r11, r8
0x1400ded14  mov     rax, [r11]
0x1400ded17  test    rax, rax
0x1400ded1a  jz      short loc_1400DED38
0x1400ded1c  cmp     r9, [rax]
0x1400ded1f  jb      short loc_1400DED31
0x1400ded21  mov     rax, [r8+8]
0x1400ded25  mov     rcx, [rax]
0x1400ded28  sub     rcx, 8
0x1400ded2c  cmp     r9, rcx
0x1400ded2f  jbe     short loc_1400DED38
0x1400ded31  mov     edi, 0C0000028h
0x1400ded36  jmp     short loc_1400DED6E
0x1400ded38  mov     edi, esi
0x1400ded3a  jmp     short loc_1400DED6A
0x1400ded3c  mov     edi, eax
0x1400ded3e  xor     esi, esi
0x1400ded40  lea     r15d, [rsi+1]
0x1400ded44  mov     r13, [rsp+0B8h+arg_20]
0x1400ded4c  mov     r12d, [rsp+0B8h+var_98]
0x1400ded51  mov     r14d, [rsp+0B8h+var_84]
0x1400ded56  mov     r9, [rsp+0B8h+var_68]
0x1400ded5b  mov     r10d, [rsp+0B8h+var_88]
0x1400ded60  mov     rbx, [rsp+0B8h+var_60]
0x1400ded65  mov     r11, [rsp+0B8h+var_80]
0x1400ded6a  test    edi, edi
0x1400ded6c  jns     short loc_1400DED75
0x1400ded6e  mov     eax, edi
0x1400ded70  jmp     loc_1400DF01D
0x1400ded75  mov     rax, [rsp+0B8h+var_90]
0x1400ded7a  add     qword ptr [rax], 8
0x1400ded7e  mov     r8, [r9]
0x1400ded81  mov     edx, r10d
0x1400ded84  mov     rcx, r13
0x1400ded87  call    ??$RtlpAmd64SetContextGp@PEAU_CONTEXT_FOR_STACKWALK@@@@YAXPEAU_CONTEXT_FOR_STACKWALK@@K_KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64SetContextGp<_CONTEXT_FOR_STACKWALK *>(_CONTEXT_FOR_STACKWALK *,ulong,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x1400ded8c  mov     r8, [rsp+0B8h+arg_28]
0x1400ded94  mov     rcx, [r8+10h]
0x1400ded98  mov     edx, dword ptr [rsp+0B8h+arg_18]
0x1400ded9f  test    rcx, rcx
0x1400deda2  jz      short loc_1400DEDAF
0x1400deda4  mov     eax, r10d
0x1400deda7  mov     [rcx+rax*8+80h], r9
0x1400dedaf  cmp     r10d, 8
0x1400dedb3  jb      short loc_1400DEDBB
0x1400dedb5  add     r12d, 2
0x1400dedb9  jmp     short loc_1400DEDBE
0x1400dedbb  add     r12d, r15d
0x1400dedbe  mov     [rsp+0B8h+var_98], r12d
0x1400dedc3  add     r14d, r15d
0x1400dedc6  jmp     loc_1400DEC6F
0x1400dedcb  cmp     r14d, edx
0x1400dedce  jnb     loc_1400DEF76
0x1400dedd4  mov     al, byte ptr [rsp+0B8h+arg_0+1]
0x1400deddb  and     al, 0Fh
0x1400deddd  cmp     al, 2
0x1400deddf  jnz     short loc_1400DEDF8
0x1400dede1  test    r10d, r10d
0x1400dede4  jnz     short loc_1400DEDF8
0x1400dede6  cmp     r12d, [rsp+0B8h+arg_10]
0x1400dedee  jb      short loc_1400DEDF5
0x1400dedf0  add     qword ptr [r13+8], 8
0x1400dedf5  add     r14d, r15d
0x1400dedf8  cmp     r14d, edx
0x1400dedfb  jnb     loc_1400DEF76
0x1400dee01  mov     eax, r14d
0x1400dee04  mov     cl, [rbx+rax*2+5]
0x1400dee08  and     cl, 0Fh
0x1400dee0b  cmp     cl, 0Ah
0x1400dee0e  jnz     loc_1400DEF76
0x1400dee14  lea     r12, [r13+8]
0x1400dee18  mov     [rsp+0B8h+var_90], r12
0x1400dee1d  mov     rbx, [r12]
0x1400dee21  mov     [rsp+0B8h+arg_0], rbx
0x1400dee29  mov     r9, 7FFFFFFF0000h
0x1400dee33  cmp     [rsp+0B8h+arg_8], r9
0x1400dee3b  jnb     short loc_1400DEE71
0x1400dee3d  mov     [rsp+0B8h+var_58], 8
0x1400dee46  mov     [rsp+0B8h+var_58], r15
0x1400dee4b  mov     r8d, 4; Alignment
0x1400dee51  mov     rdx, r15; Length
0x1400dee54  mov     rcx, rbx; Address
0x1400dee57  call    ProbeForRead
0x1400dee5c  mov     r8, [rsp+0B8h+arg_28]
0x1400dee64  mov     r11, r8
0x1400dee67  mov     r9, 7FFFFFFF0000h
0x1400dee71  mov     rax, [r11]
0x1400dee74  test    rax, rax
0x1400dee77  jz      short loc_1400DEE97
0x1400dee79  cmp     rbx, [rax]
0x1400dee7c  jb      short loc_1400DEE8E
0x1400dee7e  mov     rax, [r8+8]
0x1400dee82  mov     rcx, [rax]
0x1400dee85  sub     rcx, 8
0x1400dee89  cmp     rbx, rcx
0x1400dee8c  jbe     short loc_1400DEE97
0x1400dee8e  mov     edi, 0C0000028h
0x1400dee93  mov     eax, edi
0x1400dee95  jmp     short loc_1400DEECA
0x1400dee97  mov     eax, esi
0x1400dee99  mov     edi, 0C0000028h
0x1400dee9e  jmp     short loc_1400DEECA
0x1400deea0  xor     esi, esi
0x1400deea2  mov     edi, 0C0000028h
0x1400deea7  lea     r15d, [rsi+1]
0x1400deeab  mov     r9, 7FFFFFFF0000h
0x1400deeb5  mov     r13, [rsp+0B8h+arg_20]
0x1400deebd  mov     r12, [rsp+0B8h+var_90]
0x1400deec2  mov     rbx, [rsp+0B8h+arg_0]
0x1400deeca  lea     r14, [rbx+18h]
0x1400deece  mov     [rsp+0B8h+arg_18], r14
0x1400deed6  test    eax, eax
0x1400deed8  js      loc_1400DF01D
0x1400deede  cmp     [rsp+0B8h+arg_8], r9
0x1400deee6  jnb     short loc_1400DEF08
0x1400deee8  mov     [rsp+0B8h+var_50], 8
0x1400deef1  mov     [rsp+0B8h+var_50], r15
0x1400deef6  mov     r8d, 4; Alignment
0x1400deefc  mov     rdx, r15; Length
0x1400deeff  mov     rcx, r14; Address
0x1400def02  call    ProbeForRead
0x1400def07  nop
0x1400def08  mov     rax, [rsp+0B8h+var_80]
0x1400def0d  mov     rax, [rax]
0x1400def10  test    rax, rax
0x1400def13  jz      short loc_1400DEF3A
0x1400def15  cmp     r14, [rax]
0x1400def18  jb      loc_1400DED6E
0x1400def1e  mov     rax, [rsp+0B8h+arg_28]
0x1400def26  mov     rax, [rax+8]
0x1400def2a  mov     rcx, [rax]
0x1400def2d  sub     rcx, 8
0x1400def31  cmp     r14, rcx
0x1400def34  ja      loc_1400DED6E
0x1400def3a  mov     eax, esi
0x1400def3c  jmp     short loc_1400DEF5B
0x1400def3e  mov     r13, [rsp+0B8h+arg_20]
0x1400def46  mov     r12, [rsp+0B8h+var_90]
0x1400def4b  mov     rbx, [rsp+0B8h+arg_0]
0x1400def53  mov     r14, [rsp+0B8h+arg_18]
0x1400def5b  test    eax, eax
0x1400def5d  js      loc_1400DF01D
0x1400def63  mov     rax, [rbx]
0x1400def66  mov     [r13+0], rax
0x1400def6a  mov     rax, [r14]
0x1400def6d  mov     [r12], rax
0x1400def71  jmp     loc_1400DF01B
0x1400def76  lea     r14, [r13+8]
0x1400def7a  mov     [rsp+0B8h+var_90], r14
0x1400def7f  mov     rbx, [r14]
0x1400def82  mov     [rsp+0B8h+arg_0], rbx
0x1400def8a  mov     rax, 7FFFFFFF0000h
0x1400def94  cmp     [rsp+0B8h+arg_8], rax
0x1400def9c  jnb     short loc_1400DEFC8
0x1400def9e  mov     [rsp+0B8h+var_48], 8
0x1400defa7  mov     [rsp+0B8h+var_48], r15
0x1400defac  mov     r8d, 4; Alignment
0x1400defb2  mov     rdx, r15; Length
0x1400defb5  mov     rcx, rbx; Address
0x1400defb8  call    ProbeForRead
0x1400defbd  mov     r8, [rsp+0B8h+arg_28]
0x1400defc5  mov     r11, r8
0x1400defc8  mov     rax, [r11]
0x1400defcb  test    rax, rax
0x1400defce  jz      short loc_1400DEFED
0x1400defd0  cmp     rbx, [rax]
0x1400defd3  jb      loc_1400DED31
0x1400defd9  mov     rax, [r8+8]
0x1400defdd  mov     rcx, [rax]
0x1400defe0  sub     rcx, 8
0x1400defe4  cmp     rbx, rcx
0x1400defe7  ja      loc_1400DED31
0x1400defed  mov     edi, esi
0x1400defef  jmp     short loc_1400DF008
0x1400deff1  mov     edi, eax
0x1400deff3  mov     r13, [rsp+0B8h+arg_20]
0x1400deffb  mov     r14, [rsp+0B8h+var_90]
0x1400df000  mov     rbx, [rsp+0B8h+arg_0]
0x1400df008  test    edi, edi
0x1400df00a  js      loc_1400DED6E
0x1400df010  mov     rax, [rbx]
0x1400df013  mov     [r13+0], rax
0x1400df017  add     qword ptr [r14], 8
0x1400df01b  xor     eax, eax
0x1400df01d  add     rsp, 80h
0x1400df024  pop     r15
0x1400df026  pop     r14
  ... truncated ...
```
