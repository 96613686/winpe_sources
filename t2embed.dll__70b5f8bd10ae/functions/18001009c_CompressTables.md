# CompressTables

- ea: `0x18001009c`
- end: `0x180010441`
- name: `CompressTables`
- size: `933`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800285cc`

## callees

- `0x18000edd4`
- `0x18001009c`
- `0x180011640`
- `0x180013230`
- `0x1800134a0`
- `0x180015190`
- `0x1800164a0`
- `0x180017de0`
- `0x18001d0e8`
- `0x18001d540`
- `0x18001d598`
- `0x18002738c`
- `0x1800276a4`
- `0x18002a590`

## pseudocode

```c
__int64 __fastcall CompressTables(__int64 a1, unsigned int *a2)
{
  unsigned int v2; // edi
  unsigned __int16 v3; // r15
  unsigned __int16 v5; // bx
  unsigned int v6; // r14d
  __int64 v7; // rdi
  unsigned __int16 v8; // si
  unsigned int v9; // r12d
  unsigned __int16 v10; // r14
  int v11; // ebx
  unsigned __int16 v12; // bx
  __int16 v14; // r12
  __int64 v15; // rbx
  unsigned int v16; // r12d
  int v17; // eax
  __int64 v18; // r8
  unsigned int v19; // r12d
  char v20; // al
  __int16 v21; // ax
  unsigned int v22; // ebx
  __int16 v23; // r10
  unsigned int v24; // ecx
  unsigned __int16 v25; // bx
  unsigned int v26; // r15d
  unsigned int v27; // [rsp+30h] [rbp-40h] BYREF
  _WORD v28[2]; // [rsp+34h] [rbp-3Ch] BYREF
  int v29; // [rsp+38h] [rbp-38h]
  unsigned int v30; // [rsp+3Ch] [rbp-34h]
  unsigned int *v31; // [rsp+40h] [rbp-30h]
  __int64 v32; // [rsp+48h] [rbp-28h] BYREF
  int v33; // [rsp+50h] [rbp-20h]
  __int128 v34; // [rsp+58h] [rbp-18h] BYREF

  v2 = *(_DWORD *)(a1 + 12);
  v31 = a2;
  v32 = 0;
  v33 = 0;
  v3 = 0;
  LOWORD(v27) = 0;
  v28[0] = 0;
  v34 = 0;
  if ( (unsigned __int16)ReadGeneric(
                           (__int64 *)a1,
                           (__int64)&v32,
                           0xCu,
                           (unsigned __int8 *)OFFSET_TABLE_CONTROL,
                           v2,
                           &v27) )
    return 1005;
  v5 = WORD2(v32);
  if ( (unsigned __int16)(WORD2(v32) - 1) > 0x3E7u )
    return 1006;
  v6 = v2 + (unsigned __int16)v27;
  v7 = Mem_Alloc(16LL * WORD2(v32));
  if ( !v7 )
    return 1005;
  v8 = 0;
  if ( v5 )
  {
    v9 = v6;
    while ( 1 )
    {
      v10 = ReadGeneric((__int64 *)a1, (__int64)&v34, 0x10u, (unsigned __int8 *)&DIRECTORY_CONTROL, v6, &v27);
      if ( v10 )
        break;
      v6 = v9 + (unsigned __int16)v27;
      if ( (_DWORD)v34 != 16843009 && HIDWORD(v34) && DWORD2(v34) )
        *(_OWORD *)(v7 + 16LL * v8++) = v34;
      ++v3;
      v9 = v6;
      if ( v3 >= v5 )
      {
        v3 = 0;
        goto LABEL_13;
      }
    }
  }
  else
  {
LABEL_13:
    SortByOffset(v7, v8);
    v30 = v8;
    v11 = v8 * (unsigned __int16)GetGenericSize(&DIRECTORY_CONTROL);
    v27 = *(_DWORD *)(a1 + 12) + (unsigned __int16)GetGenericSize(OFFSET_TABLE_CONTROL) + v11;
    v12 = ZeroLongWordAlign(a1, v27, &v27);
    if ( v12 )
    {
      Mem_Free(v7);
      return v12;
    }
    v29 = 0;
    v14 = 0;
    if ( v8 )
    {
      do
      {
        v15 = 16LL * v3;
        if ( v14 )
        {
          v14 = 0;
          v29 = 0;
        }
        else
        {
          v16 = v27;
          v10 = CopyBlock(a1, v27, *(unsigned int *)(v15 + v7 + 8), *(unsigned int *)(v15 + v7 + 12));
          if ( v10 )
            goto LABEL_33;
          if ( (unsigned int)v3 + 1 < v30 && *(_DWORD *)(v15 + v7 + 8) == *(_DWORD *)(v7 + 16 * (v3 + 1LL) + 8) )
          {
            v17 = *(_DWORD *)(v15 + v7 + 12);
            if ( v17 )
            {
              LOWORD(v29) = 1;
              *(_DWORD *)(v7 + 16 * (v3 + 1LL) + 8) = v16;
              *(_DWORD *)(v7 + 16 * (v3 + 1LL) + 12) = v17;
            }
          }
          v18 = *(unsigned int *)(v15 + v7 + 12);
          *(_DWORD *)(v15 + v7 + 8) = v16;
          v10 = ZeroLongWordGap(a1, v16, v18, &v27);
          if ( v10 )
            goto LABEL_33;
          v14 = v29;
        }
        v10 = CalcChecksum(a1, *(unsigned int *)(v15 + v7 + 8), *(unsigned int *)(v15 + v7 + 12), v15 + v7 + 4);
        if ( v10 )
          goto LABEL_33;
        ++v3;
      }
      while ( v3 < v8 );
    }
    v19 = v27;
    SortByTag(v7, v8);
    WORD2(v32) = v8;
    v20 = log2ui16(v8);
    HIWORD(v32) = 16 * (1 << v20);
    v21 = log2ui16((unsigned __int16)(1 << v20));
    v22 = *(_DWORD *)(a1 + 12);
    LOWORD(v33) = v21;
    HIWORD(v33) = 16 * (v8 - v23);
    v10 = WriteGeneric(a1, (__int64)&v32, 0xCu, (unsigned __int8 *)OFFSET_TABLE_CONTROL, v22, v28);
    if ( !v10 )
    {
      v24 = v22 + v28[0];
      if ( v8 )
      {
        v25 = 0;
        v26 = v24;
        while ( 1 )
        {
          v10 = WriteGeneric(a1, v7 + 16LL * v25, 0x10u, (unsigned __int8 *)&DIRECTORY_CONTROL, v24, v28);
          if ( v10 )
            break;
          ++v25;
          v24 = v26 + v28[0];
          v26 = v24;
          if ( v25 >= v8 )
            goto LABEL_32;
        }
      }
      else
      {
LABEL_32:
        *v31 = v19;
      }
    }
  }
LABEL_33:
  Mem_Free(v7);
  return v10;
}

```

## disassembly

```asm
0x18001009c  mov     [rsp-38h+arg_10], rbx
0x1800100a1  push    rbp
0x1800100a2  push    rsi
0x1800100a3  push    rdi
0x1800100a4  push    r12
0x1800100a6  push    r13
0x1800100a8  push    r14
0x1800100aa  push    r15
0x1800100ac  mov     rbp, rsp
0x1800100af  sub     rsp, 70h
0x1800100b3  mov     rax, cs:__security_cookie
0x1800100ba  xor     rax, rsp
0x1800100bd  mov     [rbp+var_8], rax
0x1800100c1  mov     edi, [rcx+0Ch]
0x1800100c4  lea     r9, OFFSET_TABLE_CONTROL
0x1800100cb  xor     eax, eax
0x1800100cd  mov     [rbp+var_30], rdx
0x1800100d1  mov     [rbp+var_28], rax
0x1800100d5  lea     rdx, [rbp+var_28]
0x1800100d9  mov     [rbp+var_20], eax
0x1800100dc  xor     r15d, r15d
0x1800100df  xorps   xmm0, xmm0
0x1800100e2  mov     word ptr [rbp+var_40], r15w
0x1800100e7  lea     r8d, [rax+0Ch]
0x1800100eb  mov     [rbp+var_3C], r15w
0x1800100f0  lea     rax, [rbp+var_40]
0x1800100f4  mov     r13, rcx
0x1800100f7  mov     [rsp+70h+var_48], rax
0x1800100fc  mov     [rsp+70h+var_50], edi
0x180010100  movups  [rbp+var_18], xmm0
0x180010104  call    ReadGeneric
0x180010109  test    ax, ax
0x18001010c  jnz     loc_180010418
0x180010112  movzx   ebx, word ptr [rbp+var_28+4]
0x180010116  mov     ecx, 3E7h
0x18001011b  lea     eax, [rbx-1]
0x18001011e  cmp     ax, cx
0x180010121  ja      loc_180010411
0x180010127  movzx   r14d, word ptr [rbp+var_40]
0x18001012c  mov     ecx, ebx
0x18001012e  shl     rcx, 4; Size
0x180010132  add     r14d, edi
0x180010135  call    Mem_Alloc
0x18001013a  mov     rdi, rax
0x18001013d  test    rax, rax
0x180010140  jz      loc_180010418
0x180010146  mov     esi, r15d
0x180010149  cmp     r15w, bx
0x18001014d  jnb     loc_1800101D3
0x180010153  mov     r12d, r14d
0x180010156  lea     rax, [rbp+var_40]
0x18001015a  mov     r8d, 10h
0x180010160  mov     [rsp+70h+var_48], rax
0x180010165  lea     r9, DIRECTORY_CONTROL
0x18001016c  lea     rdx, [rbp+var_18]
0x180010170  mov     [rsp+70h+var_50], r14d
0x180010175  mov     rcx, r13
0x180010178  call    ReadGeneric
0x18001017d  xor     ecx, ecx
0x18001017f  movzx   r14d, ax
0x180010183  test    ax, ax
0x180010186  jnz     loc_180010403
0x18001018c  movzx   r14d, word ptr [rbp+var_40]
0x180010191  add     r14d, r12d
0x180010194  cmp     dword ptr [rbp+var_18], 1010101h
0x18001019b  jz      short loc_1800101BE
0x18001019d  cmp     dword ptr [rbp+var_18+0Ch], ecx
0x1800101a0  jz      short loc_1800101BE
0x1800101a2  cmp     dword ptr [rbp+var_18+8], ecx
0x1800101a5  jz      short loc_1800101BE
0x1800101a7  movups  xmm0, [rbp+var_18]
0x1800101ab  movzx   eax, si
0x1800101ae  add     rax, rax
0x1800101b1  movdqu  xmmword ptr [rdi+rax*8], xmm0
0x1800101b6  lea     eax, [rcx+1]
0x1800101b9  add     si, ax
0x1800101bc  jmp     short loc_1800101C3
0x1800101be  mov     eax, 1
0x1800101c3  add     r15w, ax
0x1800101c7  mov     r12d, r14d
0x1800101ca  cmp     r15w, bx
0x1800101ce  jb      short loc_180010156
0x1800101d0  xor     r15d, r15d
0x1800101d3  movzx   edx, si
0x1800101d6  mov     rcx, rdi
0x1800101d9  call    SortByOffset
0x1800101de  movzx   r14d, si
0x1800101e2  lea     rcx, DIRECTORY_CONTROL
0x1800101e9  mov     [rbp+var_34], r14d
0x1800101ed  call    GetGenericSize
0x1800101f2  movzx   ebx, ax
0x1800101f5  lea     rcx, OFFSET_TABLE_CONTROL
0x1800101fc  imul    ebx, r14d
0x180010200  call    GetGenericSize
0x180010205  movzx   eax, ax
0x180010208  lea     r8, [rbp+var_40]
0x18001020c  add     ebx, eax
0x18001020e  mov     rcx, r13
0x180010211  add     ebx, [r13+0Ch]
0x180010215  mov     edx, ebx
0x180010217  mov     [rbp+var_40], ebx
0x18001021a  call    ZeroLongWordAlign
0x18001021f  movzx   ebx, ax
0x180010222  test    ax, ax
0x180010225  jz      short loc_180010237
0x180010227  mov     rcx, rdi
0x18001022a  call    Mem_Free
0x18001022f  movzx   eax, bx
0x180010232  jmp     loc_18001041D
0x180010237  xor     ecx, ecx
0x180010239  mov     [rbp+var_38], r15d
0x18001023d  mov     r12d, r15d
0x180010240  cmp     cx, si
0x180010243  jnb     loc_180010320
0x180010249  movzx   ebx, r15w
0x18001024d  shl     rbx, 4
0x180010251  test    r12w, r12w
0x180010255  jnz     loc_1800102E5
0x18001025b  mov     r12d, [rbp+var_40]
0x18001025f  mov     rcx, r13
0x180010262  mov     r9d, [rbx+rdi+0Ch]
0x180010267  mov     edx, r12d
0x18001026a  mov     r8d, [rbx+rdi+8]
0x18001026f  call    CopyBlock
0x180010274  movzx   r14d, ax
0x180010278  test    ax, ax
0x18001027b  jnz     loc_180010403
0x180010281  movzx   ecx, r15w
0x180010285  lea     eax, [rcx+1]
0x180010288  cmp     eax, [rbp+var_34]
0x18001028b  jnb     short loc_1800102B9
0x18001028d  mov     r8d, 1
0x180010293  add     rcx, r8
0x180010296  add     rcx, rcx
0x180010299  mov     eax, [rdi+rcx*8+8]
0x18001029d  cmp     [rbx+rdi+8], eax
0x1800102a1  jnz     short loc_1800102B9
0x1800102a3  mov     eax, [rbx+rdi+0Ch]
0x1800102a7  test    eax, eax
0x1800102a9  jz      short loc_1800102B9
0x1800102ab  mov     word ptr [rbp+var_38], r8w
0x1800102b0  mov     [rdi+rcx*8+8], r12d
0x1800102b5  mov     [rdi+rcx*8+0Ch], eax
0x1800102b9  mov     r8d, [rbx+rdi+0Ch]
0x1800102be  lea     r9, [rbp+var_40]
0x1800102c2  mov     edx, r12d
0x1800102c5  mov     [rbx+rdi+8], r12d
0x1800102ca  mov     rcx, r13
0x1800102cd  call    ZeroLongWordGap
0x1800102d2  movzx   r14d, ax
0x1800102d6  test    ax, ax
0x1800102d9  jnz     loc_180010403
0x1800102df  mov     r12d, [rbp+var_38]
0x1800102e3  jmp     short loc_1800102EB
0x1800102e5  mov     r12d, ecx
0x1800102e8  mov     [rbp+var_38], ecx
0x1800102eb  mov     r8d, [rbx+rdi+0Ch]
0x1800102f0  lea     r9, [rdi+4]
0x1800102f4  mov     edx, [rbx+rdi+8]
0x1800102f8  add     r9, rbx
0x1800102fb  mov     rcx, r13
0x1800102fe  call    CalcChecksum
0x180010303  xor     ecx, ecx
0x180010305  movzx   r14d, ax
0x180010309  test    ax, ax
0x18001030c  jnz     loc_180010403
0x180010312  inc     r15w
0x180010316  cmp     r15w, si
0x18001031a  jb      loc_180010249
0x180010320  mov     r12d, [rbp+var_40]
0x180010324  movzx   edx, si
0x180010327  mov     rcx, rdi
0x18001032a  call    SortByTag
0x18001032f  movzx   ecx, si
0x180010332  mov     word ptr [rbp+var_28+4], si
0x180010336  call    log2ui16
0x18001033b  movzx   ecx, ax
0x18001033e  mov     r10d, 1
0x180010344  shl     r10w, cl
0x180010348  movzx   eax, r10w
0x18001034c  movzx   ecx, r10w
0x180010350  shl     ax, 4
0x180010354  mov     word ptr [rbp+var_28+6], ax
0x180010358  call    log2ui16
0x18001035d  mov     ebx, [r13+0Ch]
0x180010361  lea     r9, OFFSET_TABLE_CONTROL
0x180010368  mov     word ptr [rbp+var_20], ax
0x18001036c  lea     rdx, [rbp+var_28]
0x180010370  movzx   eax, si
0x180010373  mov     r8d, 0Ch
0x180010379  sub     ax, r10w
0x18001037d  mov     rcx, r13
0x180010380  shl     ax, 4
0x180010384  mov     word ptr [rbp+var_20+2], ax
0x180010388  lea     rax, [rbp+var_3C]
0x18001038c  mov     [rsp+70h+var_48], rax
0x180010391  mov     [rsp+70h+var_50], ebx
0x180010395  call    WriteGeneric
0x18001039a  xor     edx, edx
0x18001039c  movzx   r14d, ax
0x1800103a0  test    ax, ax
0x1800103a3  jnz     short loc_180010403
0x1800103a5  movzx   ecx, [rbp+var_3C]
0x1800103a9  add     ecx, ebx
0x1800103ab  cmp     dx, si
0x1800103ae  jnb     short loc_1800103FC
0x1800103b0  mov     ebx, edx
0x1800103b2  mov     r15d, ecx
0x1800103b5  lea     rax, [rbp+var_3C]
0x1800103b9  movzx   edx, bx
0x1800103bc  shl     rdx, 4
0x1800103c0  lea     r9, DIRECTORY_CONTROL
0x1800103c7  mov     [rsp+70h+var_48], rax
0x1800103cc  add     rdx, rdi
0x1800103cf  mov     [rsp+70h+var_50], ecx
0x1800103d3  mov     r8d, 10h
0x1800103d9  mov     rcx, r13
0x1800103dc  call    WriteGeneric
0x1800103e1  movzx   r14d, ax
0x1800103e5  test    ax, ax
0x1800103e8  jnz     short loc_180010403
0x1800103ea  movzx   ecx, [rbp+var_3C]
0x1800103ee  inc     bx
0x1800103f1  add     ecx, r15d
0x1800103f4  mov     r15d, ecx
0x1800103f7  cmp     bx, si
0x1800103fa  jb      short loc_1800103B5
0x1800103fc  mov     rax, [rbp+var_30]
0x180010400  mov     [rax], r12d
0x180010403  mov     rcx, rdi
0x180010406  call    Mem_Free
0x18001040b  movzx   eax, r14w
0x18001040f  jmp     short loc_18001041D
0x180010411  mov     eax, 3EEh
0x180010416  jmp     short loc_18001041D
0x180010418  mov     eax, 3EDh
0x18001041d  mov     rcx, [rbp+var_8]
0x180010421  xor     rcx, rsp; StackCookie
0x180010424  call    __security_check_cookie
0x180010429  mov     rbx, [rsp+70h+arg_10]
0x180010431  add     rsp, 70h
0x180010435  pop     r15
0x180010437  pop     r14
0x180010439  pop     r13
0x18001043b  pop     r12
0x18001043d  pop     rdi
0x18001043e  pop     rsi
0x18001043f  pop     rbp
0x180010440  retn
```
