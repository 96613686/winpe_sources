# CTDCArr::EvalDataRow(long,CTDCFilterNode *)

- ea: `0x18000bd8c`
- end: `0x18000bf36`
- name: `?EvalDataRow@CTDCArr@@AEAAEJPEAVCTDCFilterNode@@@Z`
- size: `426`
- prototype: `unsigned __int8 __fastcall(CTDCArr *__hidden this, int, struct CTDCFilterNode *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b370`
- `0x18000baa0`
- `0x18000bd8c`

## callees

- `0x18000bd8c`
- `0x18000d1cc`
- `0x18000ed20`

## pseudocode

```c
bool __fastcall CTDCArr::EvalDataRow(CTDCArr *this, int a2, struct CTDCFilterNode *a3)
{
  int v3; // r13d
  char v7; // bl
  __int64 v8; // r15
  _QWORD *v9; // r9
  __int64 v10; // r14
  __int64 v11; // r8
  CTDCArr *v12; // rcx
  struct tagVARIANT *v13; // r10
  __int64 v14; // rdx
  struct tagVARIANT *v15; // r11
  int v16; // eax
  struct tagVARIANT *v17; // rdx
  int v19; // eax

  v3 = *(_DWORD *)a3;
  v7 = 1;
  if ( !*(_DWORD *)a3 )
  {
    if ( !CTDCArr::EvalDataRow(this, a2, *((struct CTDCFilterNode **)a3 + 1)) )
      return 0;
LABEL_37:
    if ( CTDCArr::EvalDataRow(this, a2, *((struct CTDCFilterNode **)a3 + 2)) )
      return v7;
    return 0;
  }
  if ( *(_DWORD *)a3 == 1 )
  {
    if ( CTDCArr::EvalDataRow(this, a2, *((struct CTDCFilterNode **)a3 + 1)) )
      return v7;
    goto LABEL_37;
  }
  if ( *(_DWORD *)a3 == 2
    || *(_DWORD *)a3 == 3
    || *(_DWORD *)a3 == 4
    || *(_DWORD *)a3 == 5
    || (unsigned int)(*(_DWORD *)a3 - 6) <= 1 )
  {
    v8 = *((_QWORD *)a3 + 1);
    v9 = (_QWORD *)((char *)this + 128);
    v10 = *((_QWORD *)a3 + 2);
    v11 = 8LL * a2;
    v12 = (CTDCArr *)*(unsigned int *)(v8 + 24);
    v13 = (struct tagVARIANT *)(v10 + 32);
    if ( (int)v12 <= 0 )
    {
      v15 = (struct tagVARIANT *)(v8 + 32);
    }
    else
    {
      v14 = 3LL * ((int)v12 - 1);
      v12 = *(CTDCArr **)(v11 + *v9);
      v15 = (struct tagVARIANT *)(*(_QWORD *)v12 + 8 * v14);
    }
    v16 = *(_DWORD *)(v10 + 24);
    if ( v16 > 0 )
    {
      v12 = *(CTDCArr **)(v11 + *v9);
      v13 = (struct tagVARIANT *)(*(_QWORD *)v12 + 24LL * (v16 - 1));
    }
    LOBYTE(v12) = *(_BYTE *)(v8 + 58);
    if ( ((_BYTE)v12 || *(_BYTE *)(v10 + 58)) && (unsigned int)(v3 - 2) <= 1 && v15->vt == 8 && v13->vt == 8 )
    {
      v17 = v15;
      if ( !(_BYTE)v12 )
      {
        v17 = v13;
        v13 = v15;
      }
      if ( wch_wildcardMatch(v13->bstrVal, v17->bstrVal, *((_BYTE *)this + 116)) )
        return *(_DWORD *)a3 == 2;
      else
        return *(_DWORD *)a3 == 3;
    }
    LOBYTE(v19) = CTDCArr::VariantComp(v12, v15, v13, *((_WORD *)a3 + 28), *((_BYTE *)this + 116));
    switch ( *(_DWORD *)a3 )
    {
      case 2:
        return v19 == 0;
      case 3:
        return v19 != 0;
      case 4:
        return v19 < 0;
      case 5:
        return v19 > 0;
      case 6:
        return v19 <= 0;
      case 7:
        return v19 >= 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000bd8c  push    rbx
0x18000bd8e  push    rbp
0x18000bd8f  push    rsi
0x18000bd90  push    rdi
0x18000bd91  push    r13
0x18000bd93  push    r14
0x18000bd95  push    r15
0x18000bd97  sub     rsp, 30h
0x18000bd9b  mov     r13d, [r8]
0x18000bd9e  mov     rdi, r8
0x18000bda1  movsxd  rbp, edx
0x18000bda4  mov     rsi, rcx
0x18000bda7  mov     ebx, 1
0x18000bdac  mov     r9d, r13d
0x18000bdaf  test    r13d, r13d
0x18000bdb2  jz      loc_18000BF14
0x18000bdb8  sub     r9d, ebx
0x18000bdbb  jz      loc_18000BEF1
0x18000bdc1  sub     r9d, ebx
0x18000bdc4  jz      short loc_18000BDE3
0x18000bdc6  sub     r9d, ebx
0x18000bdc9  jz      short loc_18000BDE3
0x18000bdcb  sub     r9d, ebx
0x18000bdce  jz      short loc_18000BDE3
0x18000bdd0  sub     r9d, ebx
0x18000bdd3  jz      short loc_18000BDE3
0x18000bdd5  sub     r9d, ebx
0x18000bdd8  jz      short loc_18000BDE3
0x18000bdda  cmp     r9d, ebx
0x18000bddd  jnz     loc_18000BF25
0x18000bde3  mov     r15, [r8+8]
0x18000bde7  lea     r9, [rsi+80h]
0x18000bdee  mov     r14, [r8+10h]
0x18000bdf2  lea     r8, ds:0[rbp*8]
0x18000bdfa  mov     ecx, [r15+18h]
0x18000bdfe  lea     r10, [r14+20h]
0x18000be02  test    ecx, ecx
0x18000be04  jle     short loc_18000BE20
0x18000be06  lea     eax, [rcx-1]
0x18000be09  movsxd  rcx, eax
0x18000be0c  mov     rax, [r9]
0x18000be0f  lea     rdx, [rcx+rcx*2]
0x18000be13  mov     rcx, [r8+rax]
0x18000be17  mov     rax, [rcx]
0x18000be1a  lea     r11, [rax+rdx*8]
0x18000be1e  jmp     short loc_18000BE24
0x18000be20  lea     r11, [r15+20h]
0x18000be24  mov     eax, [r14+18h]
0x18000be28  test    eax, eax
0x18000be2a  jle     short loc_18000BE43
0x18000be2c  dec     eax
0x18000be2e  movsxd  rcx, eax
0x18000be31  mov     rax, [r9]
0x18000be34  lea     rdx, [rcx+rcx*2]
0x18000be38  mov     rcx, [r8+rax]
0x18000be3c  mov     rax, [rcx]
0x18000be3f  lea     r10, [rax+rdx*8]
0x18000be43  mov     cl, [r15+3Ah]; this
0x18000be47  test    cl, cl
0x18000be49  jnz     short loc_18000BE51
0x18000be4b  cmp     [r14+3Ah], cl
0x18000be4f  jz      short loc_18000BE93
0x18000be51  lea     eax, [r13-2]
0x18000be55  cmp     eax, ebx
0x18000be57  ja      short loc_18000BE93
0x18000be59  cmp     word ptr [r11], 8
0x18000be5e  jnz     short loc_18000BE93
0x18000be60  cmp     word ptr [r10], 8
0x18000be65  jnz     short loc_18000BE93
0x18000be67  mov     r8b, [rsi+74h]; unsigned __int8
0x18000be6b  test    cl, cl
0x18000be6d  mov     rdx, r11
0x18000be70  cmovz   rdx, r10
0x18000be74  cmovz   r10, r11
0x18000be78  mov     rcx, [r10+8]; unsigned __int16 *
0x18000be7c  mov     rdx, [rdx+8]; unsigned __int16 *
0x18000be80  call    ?wch_wildcardMatch@@YAEPEAG0E@Z; wch_wildcardMatch(ushort *,ushort *,uchar)
0x18000be85  test    al, al
0x18000be87  jz      short loc_18000BE8E
0x18000be89  cmp     dword ptr [rdi], 2
0x18000be8c  jmp     short loc_18000BEEC
0x18000be8e  cmp     dword ptr [rdi], 3
0x18000be91  jmp     short loc_18000BEEC
0x18000be93  mov     al, [rsi+74h]
0x18000be96  mov     r8, r10; struct tagVARIANT *
0x18000be99  movzx   r9d, word ptr [rdi+38h]; unsigned __int16
0x18000be9e  mov     rdx, r11; struct tagVARIANT *
0x18000bea1  mov     [rsp+68h+var_48], al; char
0x18000bea5  call    ?VariantComp@CTDCArr@@AEAAHPEAUtagVARIANT@@0GE@Z; CTDCArr::VariantComp(tagVARIANT *,tagVARIANT *,ushort,uchar)
0x18000beaa  mov     edx, [rdi]
0x18000beac  mov     ecx, eax
0x18000beae  sub     edx, 2
0x18000beb1  jz      short loc_18000BEEA
0x18000beb3  sub     edx, ebx
0x18000beb5  jz      short loc_18000BEE3
0x18000beb7  sub     edx, ebx
0x18000beb9  jz      short loc_18000BEDC
0x18000bebb  sub     edx, ebx
0x18000bebd  jz      short loc_18000BED5
0x18000bebf  sub     edx, ebx
0x18000bec1  jz      short loc_18000BECE
0x18000bec3  cmp     edx, ebx
0x18000bec5  jnz     short loc_18000BF25
0x18000bec7  shr     ecx, 1Fh
0x18000beca  xor     bl, cl
0x18000becc  jmp     short loc_18000BF25
0x18000bece  test    ecx, ecx
0x18000bed0  setle   bl
0x18000bed3  jmp     short loc_18000BF25
0x18000bed5  test    ecx, ecx
0x18000bed7  setnle  bl
0x18000beda  jmp     short loc_18000BF25
0x18000bedc  shr     ecx, 1Fh
0x18000bedf  mov     bl, cl
0x18000bee1  jmp     short loc_18000BF25
0x18000bee3  test    ecx, ecx
0x18000bee5  setnz   bl
0x18000bee8  jmp     short loc_18000BF25
0x18000beea  test    ecx, ecx
0x18000beec  setz    bl
0x18000beef  jmp     short loc_18000BF25
0x18000bef1  mov     r8, [r8+8]; struct CTDCFilterNode *
0x18000bef5  mov     edx, ebp; int
0x18000bef7  call    ?EvalDataRow@CTDCArr@@AEAAEJPEAVCTDCFilterNode@@@Z; CTDCArr::EvalDataRow(long,CTDCFilterNode *)
0x18000befc  test    al, al
0x18000befe  jnz     short loc_18000BF25
0x18000bf00  mov     r8, [rdi+10h]; struct CTDCFilterNode *
0x18000bf04  mov     edx, ebp; int
0x18000bf06  mov     rcx, rsi; this
0x18000bf09  call    ?EvalDataRow@CTDCArr@@AEAAEJPEAVCTDCFilterNode@@@Z; CTDCArr::EvalDataRow(long,CTDCFilterNode *)
0x18000bf0e  test    al, al
0x18000bf10  jz      short loc_18000BF23
0x18000bf12  jmp     short loc_18000BF25
0x18000bf14  mov     r8, [r8+8]; struct CTDCFilterNode *
0x18000bf18  mov     edx, ebp; int
0x18000bf1a  call    ?EvalDataRow@CTDCArr@@AEAAEJPEAVCTDCFilterNode@@@Z; CTDCArr::EvalDataRow(long,CTDCFilterNode *)
0x18000bf1f  test    al, al
0x18000bf21  jnz     short loc_18000BF00
0x18000bf23  xor     bl, bl
0x18000bf25  mov     al, bl
0x18000bf27  add     rsp, 30h
0x18000bf2b  pop     r15
0x18000bf2d  pop     r14
0x18000bf2f  pop     r13
0x18000bf31  pop     rdi
0x18000bf32  pop     rsi
0x18000bf33  pop     rbp
0x18000bf34  pop     rbx
0x18000bf35  retn
```
