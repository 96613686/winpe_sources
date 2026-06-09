# RtlpUnwindEpilogue<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT *>(unsigned __int64,unsigned __int64,ulong,CDirectFnEnt,_CONTEXT *,_AMD64_UNWIND_PARAMS *)

- ea: `0x1400de648`
- end: `0x1400deb4e`
- name: `??$RtlpUnwindEpilogue@VCDirectFnEnt@@VCDirectUnwindInfo@@VCDirectMemoryAccessors@@PEAU_CONTEXT@@@@YAJ_K0KVCDirectFnEnt@@PEAU_CONTEXT@@PEAU_AMD64_UNWIND_PARAMS@@@Z`
- size: `1286`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400e04c8`

## callees

- `0x14002c6a8`
- `0x1400442ac`
- `0x1400de54c`
- `0x1400de648`

## pseudocode

```c
__int64 __fastcall RtlpUnwindEpilogue<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT *>(
        __int64 a1,
        unsigned __int64 a2,
        unsigned int a3,
        _BYTE *a4,
        __int64 a5,
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
  __int64 v19; // rcx
  _QWORD *v20; // rbx
  _QWORD *v21; // r14
  _QWORD *v22; // rbx
  unsigned int v23; // [rsp+20h] [rbp-98h]
  _QWORD *v24; // [rsp+40h] [rbp-78h]
  __int64 v25; // [rsp+C0h] [rbp+8h]
  __int16 v26; // [rsp+C0h] [rbp+8h]

  v25 = a1;
  v6 = 0;
  v7 = 0;
  while ( 1 )
  {
    v8 = (_BYTE *)(a1 + *((unsigned int *)a4 + 2));
    v9 = (unsigned __int8)v8[2];
    v23 = v9;
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
        v9 = v23;
      }
      while ( v11 < v23 );
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
      goto LABEL_63;
    v26 = *(_WORD *)&v8[2 * v11 + 4];
    v17 = HIBYTE(v26) >> 4;
    if ( (v26 & 0xF00) != 0 )
      break;
    if ( v16 >= a3 )
    {
      v18 = *(_QWORD **)(a5 + 152);
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
      *(_QWORD *)(a5 + 152) += 8LL;
      RtlpAmd64SetContextGp<_CONTEXT *>(a5, v17, *v18);
      v14 = a6;
      v19 = *(_QWORD *)(a6 + 16);
      v15 = (_QWORD *)a6;
      v17 = HIBYTE(v26) >> 4;
      if ( v19 )
        *(_QWORD *)(v19 + 8LL * v17 + 128) = v24;
      v9 = v23;
    }
    if ( v17 < 8 )
      ++v16;
    else
      v16 += 2;
    ++v11;
  }
  if ( v11 >= v9 )
    goto LABEL_63;
  if ( (HIBYTE(v26) & 0xF) == 2 && !v17 )
  {
    if ( v16 >= a3 )
      *(_QWORD *)(a5 + 152) += 8LL;
    ++v11;
  }
  if ( v11 >= v9 || (v8[2 * v11 + 5] & 0xF) != 0xA )
  {
LABEL_63:
    v22 = *(_QWORD **)(a5 + 152);
    if ( a2 < 0x7FFFFFFF0000LL )
    {
      ProbeForRead(v22, 1u, 4u);
      v14 = a6;
      v15 = (_QWORD *)a6;
    }
    if ( !*v15 || (unsigned __int64)v22 >= *(_QWORD *)*v15 && (unsigned __int64)v22 <= **(_QWORD **)(v14 + 8) - 8LL )
    {
      *(_QWORD *)(a5 + 248) = *v22;
      *(_QWORD *)(a5 + 152) += 8LL;
      return 0;
    }
    return 3221225512LL;
  }
  v20 = *(_QWORD **)(a5 + 152);
  if ( a2 < 0x7FFFFFFF0000LL )
  {
    ProbeForRead(v20, 1u, 4u);
    v14 = a6;
    v15 = (_QWORD *)a6;
  }
  if ( *v15 && ((unsigned __int64)v20 < *(_QWORD *)*v15 || (unsigned __int64)v20 > **(_QWORD **)(v14 + 8) - 8LL) )
    result = 3221225512LL;
  else
    result = 0;
  v21 = v20 + 3;
  if ( (int)result >= 0 )
  {
    if ( a2 < 0x7FFFFFFF0000LL )
      ProbeForRead(v20 + 3, 1u, 4u);
    if ( !*(_QWORD *)a6
      || (unsigned __int64)v21 >= **(_QWORD **)a6 && (unsigned __int64)v21 <= **(_QWORD **)(a6 + 8) - 8LL )
    {
      *(_QWORD *)(a5 + 248) = *v20;
      *(_QWORD *)(a5 + 152) = *v21;
      return 0;
    }
    return 3221225512LL;
  }
  return result;
}

```

## disassembly

```asm
0x1400de648  mov     [rsp+arg_10], r8d
0x1400de64d  mov     [rsp+arg_8], rdx
0x1400de652  mov     [rsp+arg_0], rcx
0x1400de657  push    rbx
0x1400de658  push    rsi
0x1400de659  push    rdi
0x1400de65a  push    r12
0x1400de65c  push    r13
0x1400de65e  push    r14
0x1400de660  push    r15
0x1400de662  sub     rsp, 80h
0x1400de669  xor     esi, esi
0x1400de66b  mov     r12d, esi
0x1400de66e  mov     r13d, esi
0x1400de671  lea     r15d, [rsi+1]
0x1400de675  mov     ebx, [r9+8]
0x1400de679  add     rbx, rcx
0x1400de67c  mov     [rsp+0B8h+var_60], rbx
0x1400de681  movzx   edx, byte ptr [rbx+2]
0x1400de685  mov     [rsp+0B8h+var_98], edx
0x1400de689  mov     edi, edx
0x1400de68b  mov     r14d, esi
0x1400de68e  test    edx, edx
0x1400de690  jz      short loc_1400DE6E3
0x1400de692  mov     ecx, r14d
0x1400de695  movzx   ecx, word ptr [rbx+rcx*2+4]
0x1400de69a  movzx   r8d, cx
0x1400de69e  shr     r8w, 8
0x1400de6a3  mov     al, r8b
0x1400de6a6  and     al, 0Fh
0x1400de6a8  jz      short loc_1400DE6E3
0x1400de6aa  cmp     al, 0Ah
0x1400de6ac  jz      short loc_1400DE6E3
0x1400de6ae  cmp     al, 2
0x1400de6b0  jnz     short loc_1400DE6BD
0x1400de6b2  test    r8b, 0F0h
0x1400de6b6  jnz     short loc_1400DE6BD
0x1400de6b8  mov     edi, r14d
0x1400de6bb  jmp     short loc_1400DE6C7
0x1400de6bd  or      r8d, 0FFFFFFFFh
0x1400de6c1  cmp     edi, edx
0x1400de6c3  cmovnz  edi, r8d
0x1400de6c7  sub     al, r15b
0x1400de6ca  cmp     al, r15b
0x1400de6cd  ja      short loc_1400DE6D2
0x1400de6cf  add     r13d, r15d
0x1400de6d2  call    RtlpUnwindOpSlots
0x1400de6d7  add     r14d, eax
0x1400de6da  mov     edx, [rsp+0B8h+var_98]
0x1400de6de  cmp     r14d, edx
0x1400de6e1  jb      short loc_1400DE692
0x1400de6e3  cmp     r14d, edx
0x1400de6e6  jb      short loc_1400DE722
0x1400de6e8  test    byte ptr [rbx], 20h
0x1400de6eb  jz      short loc_1400DE722
0x1400de6ed  add     r12d, r15d
0x1400de6f0  cmp     r12d, 20h ; ' '
0x1400de6f4  ja      short loc_1400DE718
0x1400de6f6  movzx   eax, byte ptr [rbx+2]
0x1400de6fa  mov     r9d, eax
0x1400de6fd  and     r9d, r15d
0x1400de700  add     r9d, eax
0x1400de703  add     r9, 2
0x1400de707  lea     r9, [rbx+r9*2]
0x1400de70b  mov     rcx, [rsp+0B8h+arg_0]
0x1400de713  jmp     loc_1400DE675
0x1400de718  mov     eax, 0C00000FFh
0x1400de71d  jmp     loc_1400DEB3A
0x1400de722  mov     r8, [rsp+0B8h+arg_28]
0x1400de72a  mov     r11, r8
0x1400de72d  mov     [rsp+0B8h+var_90], r8
0x1400de732  cmp     edi, edx
0x1400de734  jnb     short loc_1400DE743
0x1400de736  cmp     r13d, 2
0x1400de73a  jnz     short loc_1400DE743
0x1400de73c  cmp     r14d, edx
0x1400de73f  cmovz   r14d, edi
0x1400de743  mov     r12d, esi
0x1400de746  mov     [rsp+0B8h+var_94], esi
0x1400de74a  mov     word ptr [rsp+0B8h+arg_0], si
0x1400de752  mov     r10d, esi
0x1400de755  mov     r13, [rsp+0B8h+arg_20]
0x1400de75d  mov     [rsp+0B8h+var_80], r14d
0x1400de762  cmp     r14d, edx
0x1400de765  jnb     loc_1400DEA8D
0x1400de76b  mov     eax, r14d
0x1400de76e  movzx   ecx, word ptr [rbx+rax*2+4]
0x1400de773  mov     word ptr [rsp+0B8h+arg_0], cx
0x1400de77b  shr     cx, 8
0x1400de77f  movzx   eax, cl
0x1400de782  mov     r10d, eax
0x1400de785  shr     r10d, 4
0x1400de789  mov     dword ptr [rsp+0B8h+arg_18], r10d
0x1400de791  test    al, 0Fh
0x1400de793  jnz     loc_1400DE8D9
0x1400de799  cmp     r12d, [rsp+0B8h+arg_10]
0x1400de7a1  jb      loc_1400DE8BD
0x1400de7a7  lea     rax, [r13+98h]
0x1400de7ae  mov     [rsp+0B8h+var_88], rax
0x1400de7b3  mov     r9, [rax]
0x1400de7b6  mov     [rsp+0B8h+var_78], r9
0x1400de7bb  mov     [rsp+0B8h+var_68], r9
0x1400de7c0  mov     rax, 7FFFFFFF0000h
0x1400de7ca  cmp     [rsp+0B8h+arg_8], rax
0x1400de7d2  jnb     short loc_1400DE80B
0x1400de7d4  mov     [rsp+0B8h+var_70], 8
0x1400de7dd  mov     [rsp+0B8h+var_70], r15
0x1400de7e2  mov     r8d, 4; Alignment
0x1400de7e8  mov     rdx, r15; Length
0x1400de7eb  mov     rcx, r9; Address
0x1400de7ee  call    ProbeForRead
0x1400de7f3  mov     r9, [rsp+0B8h+var_78]
0x1400de7f8  mov     r10d, dword ptr [rsp+0B8h+arg_18]
0x1400de800  mov     r8, [rsp+0B8h+arg_28]
0x1400de808  mov     r11, r8
0x1400de80b  mov     rax, [r11]
0x1400de80e  test    rax, rax
0x1400de811  jz      short loc_1400DE82F
0x1400de813  cmp     r9, [rax]
0x1400de816  jb      short loc_1400DE828
0x1400de818  mov     rax, [r8+8]
0x1400de81c  mov     rcx, [rax]
0x1400de81f  sub     rcx, 8
0x1400de823  cmp     r9, rcx
0x1400de826  jbe     short loc_1400DE82F
0x1400de828  mov     edi, 0C0000028h
0x1400de82d  jmp     short loc_1400DE868
0x1400de82f  mov     edi, esi
0x1400de831  jmp     short loc_1400DE864
0x1400de833  mov     edi, eax
0x1400de835  xor     esi, esi
0x1400de837  lea     r15d, [rsi+1]
0x1400de83b  mov     r13, [rsp+0B8h+arg_20]
0x1400de843  mov     r12d, [rsp+0B8h+var_94]
0x1400de848  mov     r14d, [rsp+0B8h+var_80]
0x1400de84d  mov     r9, [rsp+0B8h+var_68]
0x1400de852  mov     [rsp+0B8h+var_78], r9
0x1400de857  mov     r10d, dword ptr [rsp+0B8h+arg_18]
0x1400de85f  mov     rbx, [rsp+0B8h+var_60]
0x1400de864  test    edi, edi
0x1400de866  jns     short loc_1400DE86F
0x1400de868  mov     eax, edi
0x1400de86a  jmp     loc_1400DEB3A
0x1400de86f  mov     rax, [rsp+0B8h+var_88]
0x1400de874  add     qword ptr [rax], 8
0x1400de878  mov     r8, [r9]
0x1400de87b  mov     edx, r10d
0x1400de87e  mov     rcx, r13
0x1400de881  call    ??$RtlpAmd64SetContextGp@PEAU_CONTEXT@@@@YAXPEAU_CONTEXT@@K_KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64SetContextGp<_CONTEXT *>(_CONTEXT *,ulong,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x1400de886  mov     r8, [rsp+0B8h+arg_28]
0x1400de88e  mov     rcx, [r8+10h]
0x1400de892  mov     r11, r8
0x1400de895  test    rcx, rcx
0x1400de898  jz      short loc_1400DE8B1
0x1400de89a  mov     r10d, dword ptr [rsp+0B8h+arg_18]
0x1400de8a2  mov     rdx, [rsp+0B8h+var_78]
0x1400de8a7  mov     [rcx+r10*8+80h], rdx
0x1400de8af  jmp     short loc_1400DE8B9
0x1400de8b1  mov     r10d, dword ptr [rsp+0B8h+arg_18]
0x1400de8b9  mov     edx, [rsp+0B8h+var_98]
0x1400de8bd  cmp     r10d, 8
0x1400de8c1  jb      short loc_1400DE8C9
0x1400de8c3  add     r12d, 2
0x1400de8c7  jmp     short loc_1400DE8CC
0x1400de8c9  add     r12d, r15d
0x1400de8cc  mov     [rsp+0B8h+var_94], r12d
0x1400de8d1  add     r14d, r15d
0x1400de8d4  jmp     loc_1400DE75D
0x1400de8d9  cmp     r14d, edx
0x1400de8dc  jnb     loc_1400DEA8D
0x1400de8e2  mov     al, byte ptr [rsp+0B8h+arg_0+1]
0x1400de8e9  and     al, 0Fh
0x1400de8eb  cmp     al, 2
0x1400de8ed  jnz     short loc_1400DE909
0x1400de8ef  test    r10d, r10d
0x1400de8f2  jnz     short loc_1400DE909
0x1400de8f4  cmp     r12d, [rsp+0B8h+arg_10]
0x1400de8fc  jb      short loc_1400DE906
0x1400de8fe  add     qword ptr [r13+98h], 8
0x1400de906  add     r14d, r15d
0x1400de909  cmp     r14d, edx
0x1400de90c  jnb     loc_1400DEA8D
0x1400de912  mov     eax, r14d
0x1400de915  mov     cl, [rbx+rax*2+5]
0x1400de919  and     cl, 0Fh
0x1400de91c  cmp     cl, 0Ah
0x1400de91f  jnz     loc_1400DEA8D
0x1400de925  lea     r12, [r13+98h]
0x1400de92c  mov     [rsp+0B8h+var_88], r12
0x1400de931  mov     rbx, [r12]
0x1400de935  mov     [rsp+0B8h+arg_0], rbx
0x1400de93d  mov     r9, 7FFFFFFF0000h
0x1400de947  cmp     [rsp+0B8h+arg_8], r9
0x1400de94f  jnb     short loc_1400DE985
0x1400de951  mov     [rsp+0B8h+var_58], 8
0x1400de95a  mov     [rsp+0B8h+var_58], r15
0x1400de95f  mov     r8d, 4; Alignment
0x1400de965  mov     rdx, r15; Length
0x1400de968  mov     rcx, rbx; Address
0x1400de96b  call    ProbeForRead
0x1400de970  mov     r8, [rsp+0B8h+arg_28]
0x1400de978  mov     r11, r8
0x1400de97b  mov     r9, 7FFFFFFF0000h
0x1400de985  mov     rax, [r11]
0x1400de988  test    rax, rax
0x1400de98b  jz      short loc_1400DE9AB
0x1400de98d  cmp     rbx, [rax]
0x1400de990  jb      short loc_1400DE9A2
0x1400de992  mov     rax, [r8+8]
0x1400de996  mov     rcx, [rax]
0x1400de999  sub     rcx, 8
0x1400de99d  cmp     rbx, rcx
0x1400de9a0  jbe     short loc_1400DE9AB
0x1400de9a2  mov     edi, 0C0000028h
0x1400de9a7  mov     eax, edi
0x1400de9a9  jmp     short loc_1400DE9DE
0x1400de9ab  mov     eax, esi
0x1400de9ad  mov     edi, 0C0000028h
0x1400de9b2  jmp     short loc_1400DE9DE
0x1400de9b4  xor     esi, esi
0x1400de9b6  mov     edi, 0C0000028h
0x1400de9bb  lea     r15d, [rsi+1]
0x1400de9bf  mov     r9, 7FFFFFFF0000h
0x1400de9c9  mov     r13, [rsp+0B8h+arg_20]
0x1400de9d1  mov     r12, [rsp+0B8h+var_88]
0x1400de9d6  mov     rbx, [rsp+0B8h+arg_0]
0x1400de9de  lea     r14, [rbx+18h]
0x1400de9e2  mov     [rsp+0B8h+arg_18], r14
0x1400de9ea  test    eax, eax
0x1400de9ec  js      loc_1400DEB3A
0x1400de9f2  cmp     [rsp+0B8h+arg_8], r9
0x1400de9fa  jnb     short loc_1400DEA1C
0x1400de9fc  mov     [rsp+0B8h+var_50], 8
0x1400dea05  mov     [rsp+0B8h+var_50], r15
0x1400dea0a  mov     r8d, 4; Alignment
0x1400dea10  mov     rdx, r15; Length
0x1400dea13  mov     rcx, r14; Address
0x1400dea16  call    ProbeForRead
0x1400dea1b  nop
0x1400dea1c  mov     rax, [rsp+0B8h+var_90]
0x1400dea21  mov     rax, [rax]
0x1400dea24  test    rax, rax
0x1400dea27  jz      short loc_1400DEA4E
0x1400dea29  cmp     r14, [rax]
0x1400dea2c  jb      loc_1400DE868
0x1400dea32  mov     rax, [rsp+0B8h+arg_28]
0x1400dea3a  mov     rax, [rax+8]
0x1400dea3e  mov     rcx, [rax]
0x1400dea41  sub     rcx, 8
0x1400dea45  cmp     r14, rcx
0x1400dea48  ja      loc_1400DE868
0x1400dea4e  mov     eax, esi
0x1400dea50  jmp     short loc_1400DEA6F
0x1400dea52  mov     r13, [rsp+0B8h+arg_20]
0x1400dea5a  mov     r12, [rsp+0B8h+var_88]
0x1400dea5f  mov     rbx, [rsp+0B8h+arg_0]
0x1400dea67  mov     r14, [rsp+0B8h+arg_18]
0x1400dea6f  test    eax, eax
0x1400dea71  js      loc_1400DEB3A
0x1400dea77  mov     rax, [rbx]
0x1400dea7a  mov     [r13+0F8h], rax
0x1400dea81  mov     rax, [r14]
0x1400dea84  mov     [r12], rax
0x1400dea88  jmp     loc_1400DEB38
0x1400dea8d  lea     r14, [r13+98h]
0x1400dea94  mov     [rsp+0B8h+var_88], r14
0x1400dea99  mov     rbx, [r14]
0x1400dea9c  mov     [rsp+0B8h+arg_0], rbx
0x1400deaa4  mov     rax, 7FFFFFFF0000h
0x1400deaae  cmp     [rsp+0B8h+arg_8], rax
0x1400deab6  jnb     short loc_1400DEAE2
0x1400deab8  mov     [rsp+0B8h+var_48], 8
0x1400deac1  mov     [rsp+0B8h+var_48], r15
0x1400deac6  mov     r8d, 4; Alignment
0x1400deacc  mov     rdx, r15; Length
0x1400deacf  mov     rcx, rbx; Address
0x1400dead2  call    ProbeForRead
0x1400dead7  mov     r8, [rsp+0B8h+arg_28]
0x1400deadf  mov     r11, r8
0x1400deae2  mov     rax, [r11]
0x1400deae5  test    rax, rax
0x1400deae8  jz      short loc_1400DEB07
0x1400deaea  cmp     rbx, [rax]
0x1400deaed  jb      loc_1400DE828
0x1400deaf3  mov     rax, [r8+8]
0x1400deaf7  mov     rcx, [rax]
0x1400deafa  sub     rcx, 8
0x1400deafe  cmp     rbx, rcx
0x1400deb01  ja      loc_1400DE828
0x1400deb07  mov     edi, esi
0x1400deb09  jmp     short loc_1400DEB22
0x1400deb0b  mov     edi, eax
0x1400deb0d  mov     r13, [rsp+0B8h+arg_20]
0x1400deb15  mov     r14, [rsp+0B8h+var_88]
0x1400deb1a  mov     rbx, [rsp+0B8h+arg_0]
0x1400deb22  test    edi, edi
0x1400deb24  js      loc_1400DE868
0x1400deb2a  mov     rax, [rbx]
0x1400deb2d  mov     [r13+0F8h], rax
0x1400deb34  add     qword ptr [r14], 8
  ... truncated ...
```
