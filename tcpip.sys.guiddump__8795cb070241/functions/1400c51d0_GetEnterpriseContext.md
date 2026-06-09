# GetEnterpriseContext

- ea: `0x1400c51d0`
- end: `0x1400c56c7`
- name: `GetEnterpriseContext`
- size: `1271`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400c5070`
- `0x14015236c`

## callees

- `0x1400663fc`
- `0x1400c51d0`
- `0x1400c56d0`
- `0x1400c6334`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400c54ed`
- `ntoskrnl!RtlCompareMemory` at `0x1400c559b`
- `ntoskrnl!RtlCompareMemory` at `0x1400c567b`
- `ntoskrnl!RtlCompareMemory` at `0x1400c54ed`
- `ntoskrnl!RtlCompareMemory` at `0x1400c559b`
- `ntoskrnl!RtlCompareMemory` at `0x1400c567b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c5236`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c5288`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c53c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c5611`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c5645`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c5236`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c5288`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c53c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c5611`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c5645`
- `ntoskrnl!ExAllocatePool2` at `0x1400c5357`
- `ntoskrnl!ExAllocatePool2` at `0x1400c5357`

## pseudocode

```c
__int64 __fastcall GetEnterpriseContext(_QWORD *a1, struct _UNICODE_STRING **a2)
{
  unsigned int v4; // r13d
  int v5; // eax
  _QWORD *v6; // r14
  int v7; // ebx
  WCHAR *v8; // r15
  int v9; // eax
  _QWORD *v10; // rdi
  unsigned int v11; // r14d
  PVOID v12; // rcx
  _QWORD *v13; // rbp
  struct _UNICODE_STRING *v14; // r12
  __int64 v15; // rdx
  unsigned int v16; // edi
  int v17; // ecx
  unsigned int v18; // eax
  unsigned int v19; // r13d
  struct _UNICODE_STRING *Pool2; // rax
  struct _UNICODE_STRING *v21; // r15
  struct _UNICODE_STRING *v22; // r14
  unsigned int v23; // r13d
  __int64 v25; // rbp
  unsigned int v26; // eax
  unsigned __int16 *v27; // r14
  WCHAR **v28; // r12
  unsigned __int16 *v29; // r13
  int v30; // ecx
  unsigned __int16 *v31; // rcx
  unsigned __int64 v32; // r9
  void *v33; // r10
  __int64 v34; // r14
  unsigned int v35; // r11d
  unsigned int v36; // r9d
  int v37; // r11d
  int v38; // ecx
  PVOID P; // [rsp+78h] [rbp+10h] BYREF
  __int64 v40; // [rsp+80h] [rbp+18h]
  PVOID v41; // [rsp+88h] [rbp+20h]

  if ( a2 )
  {
    v4 = 0;
    *a2 = 0;
    P = 0;
    v5 = QueryAttributes(a1, 1, &P);
    v6 = P;
    v7 = v5;
    v8 = 0;
    if ( v5 >= 0 )
    {
      v28 = 0;
      if ( P && *((_DWORD *)P + 1) )
      {
        do
        {
          v29 = (unsigned __int16 *)(v6[1] + 40LL * (_QWORD)v8);
          if ( *((_DWORD *)v29 + 6) )
          {
            if ( *((_QWORD *)v29 + 4) )
            {
              v30 = *v29;
              if ( (v30 & 0xFFFE) == 0x22
                && RtlCompareMemory(*((const void **)v29 + 1), L"EDP://PolicyFlags", *v29) == v30 )
              {
                v28 = (WCHAR **)*((_QWORD *)v29 + 4);
              }
            }
          }
          v8 = (WCHAR *)(unsigned int)((_DWORD)v8 + 1);
        }
        while ( (unsigned int)v8 < *((_DWORD *)v6 + 1) );
        v4 = 0;
      }
      v8 = 0;
      if ( v28 )
        v8 = *v28;
    }
    if ( v6 )
      ExFreePoolWithTag(v6, 0);
    if ( v7 < 0 )
      return (unsigned int)v7;
    P = 0;
    v9 = QueryAttributes(a1, 8, &P);
    v10 = P;
    v7 = v9;
    if ( v9 >= 0 )
    {
      if ( !P )
        goto LABEL_11;
      v11 = 0;
      if ( *((_DWORD *)P + 1) )
      {
        do
        {
          v31 = (unsigned __int16 *)(v10[1] + 40LL * v11);
          if ( *((_DWORD *)v31 + 6) && *((_QWORD *)v31 + 4) && (*v31 & 0xFFFE) == 0x2A )
            RtlCompareMemory(*((const void **)v31 + 1), L"EDP://EvaluationFlags", *v31);
          ++v11;
        }
        while ( v11 < *((_DWORD *)v10 + 1) );
      }
    }
    if ( v10 )
      ExFreePoolWithTag(v10, 0);
LABEL_11:
    if ( v7 < 0 )
      return (unsigned int)v7;
    P = 0;
    v7 = QueryAttributes(a1, 2, &P);
    if ( v7 < 0 )
    {
      v12 = P;
      if ( !P )
        return (unsigned int)v7;
      goto LABEL_78;
    }
    v13 = P;
    v14 = 0;
    v41 = P;
    if ( P && *((_DWORD *)P + 1) )
    {
      v16 = 0;
      v15 = 0;
      v40 = 0;
      do
      {
        v27 = (unsigned __int16 *)(v13[1] + 40LL * v4);
        if ( *((_DWORD *)v27 + 6) )
        {
          if ( *((_QWORD *)v27 + 4) )
          {
            v38 = *v27;
            if ( (v38 & 0xFFFE) == 0x26 )
            {
              if ( RtlCompareMemory(*((const void **)v27 + 1), L"EDP://EnterpriseIds", *v27) == v38 )
              {
                v15 = *((_QWORD *)v27 + 4);
                v16 = *((_DWORD *)v27 + 6);
                v40 = v15;
              }
              else
              {
                v15 = v40;
              }
            }
          }
        }
        ++v4;
      }
      while ( v4 < *((_DWORD *)v13 + 1) );
      v14 = 0;
    }
    else
    {
      v15 = 0;
      v16 = 0;
      v40 = 0;
    }
    if ( v16 && !v15 )
    {
      v7 = -1073741811;
LABEL_30:
      if ( v13 )
        ExFreePoolWithTag(v13, 0);
      if ( v7 >= 0 || !v14 )
        return (unsigned int)v7;
      v12 = v14;
LABEL_78:
      ExFreePoolWithTag(v12, 0);
      return (unsigned int)v7;
    }
    if ( ((unsigned __int64)v8 & 0xFFFFFFFFFFFFFF00uLL) != 0 )
    {
      v7 = -1073741811;
      goto LABEL_30;
    }
    if ( !v16 && ((unsigned __int8)v8 & 0xA) != 0 && ((unsigned __int8)v8 & 1) == 0 )
    {
      v8 = (WCHAR *)((unsigned __int64)v8 & 0xFFFFFFFFFFFFFFF5uLL);
      v14 = 0;
    }
    else
    {
      v14 = 0;
      if ( v16 && v15 )
      {
        v32 = 16LL * v16;
        v33 = 0;
        if ( v32 > 0xFFFFFFFF )
        {
LABEL_68:
          v7 = -1073741675;
LABEL_72:
          if ( v33 )
            ExFreePoolWithTag(v33, 0);
          goto LABEL_28;
        }
        v34 = v40;
        v35 = 0;
        while ( v35 < v16 )
        {
          LOWORD(P) = 0;
          v7 = RtlUShortAdd(*(_WORD *)(v34 + 16LL * v35), 2u, (USHORT *)&P);
          if ( v7 < 0 )
            goto LABEL_72;
          if ( v36 + (unsigned __int16)P < v36 )
            goto LABEL_68;
          v35 = v37 + 1;
          LODWORD(v32) = v36 + (unsigned __int16)P;
        }
        v17 = v32 + 32;
        if ( (int)v32 + 32 < (unsigned int)v32 )
        {
          v7 = -1073741675;
LABEL_28:
          if ( v7 >= 0 )
            *a2 = v14;
          goto LABEL_30;
        }
LABEL_23:
        v18 = v17 - 16;
        if ( !v16 )
          v18 = v17;
        v19 = v18;
        Pool2 = (struct _UNICODE_STRING *)ExAllocatePool2(66, v18, 1950576197);
        if ( Pool2 )
        {
          v7 = 0;
          v14 = Pool2;
          memset(Pool2, 0, v19);
          v14->Buffer = v8;
          v21 = v14 + 1;
          v22 = &v14[v16 + 1];
          *(_DWORD *)&v14->Length = 1;
          v23 = 0;
          *(_DWORD *)(&v14->MaximumLength + 1) = v16;
          if ( v16 )
          {
            v25 = v40;
            do
            {
              v26 = CopyEnterpriseId(v21++, v22, (PCUNICODE_STRING)(v25 + 16LL * v23));
              v22 = (struct _UNICODE_STRING *)((char *)v22 + v26);
              ++v23;
            }
            while ( v23 < v16 );
          }
          v13 = v41;
        }
        else
        {
          v7 = -1073741801;
        }
        goto LABEL_28;
      }
    }
    v17 = 32;
    v41 = v13;
    goto LABEL_23;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x1400c51d0  mov     rax, rsp
0x1400c51d3  push    rbx
0x1400c51d4  push    rbp
0x1400c51d5  push    rsi
0x1400c51d6  sub     rsp, 50h
0x1400c51da  mov     rsi, rdx
0x1400c51dd  mov     rbp, rcx
0x1400c51e0  test    rdx, rdx
0x1400c51e3  jz      loc_1400C53FA
0x1400c51e9  mov     [rax+8], rdi
0x1400c51ed  lea     r8, [rax+10h]
0x1400c51f1  mov     [rax-20h], r12
0x1400c51f5  mov     [rax-28h], r13
0x1400c51f9  xor     r13d, r13d
0x1400c51fc  mov     [rdx], r13
0x1400c51ff  mov     edx, 1
0x1400c5204  mov     [rax-30h], r14
0x1400c5208  mov     [rax-38h], r15
0x1400c520c  mov     [rax+10h], r13
0x1400c5210  call    QueryAttributes
0x1400c5215  mov     r14, [rsp+68h+P]
0x1400c521a  mov     ebx, eax
0x1400c521c  mov     r15d, r13d
0x1400c521f  mov     edx, 0FFFEh
0x1400c5224  test    eax, eax
0x1400c5226  jns     loc_1400C548F
0x1400c522c  test    r14, r14
0x1400c522f  jz      short loc_1400C5242
0x1400c5231  xor     edx, edx; Tag
0x1400c5233  mov     rcx, r14; P
0x1400c5236  call    cs:__imp_ExFreePoolWithTag
0x1400c523d  nop     dword ptr [rax+rax+00h]
0x1400c5242  test    ebx, ebx
0x1400c5244  js      loc_1400C53D6
0x1400c524a  lea     r8, [rsp+68h+P]
0x1400c524f  mov     [rsp+68h+P], r13
0x1400c5254  mov     edx, 8
0x1400c5259  mov     rcx, rbp
0x1400c525c  call    QueryAttributes
0x1400c5261  mov     rdi, [rsp+68h+P]
0x1400c5266  mov     ebx, eax
0x1400c5268  test    eax, eax
0x1400c526a  js      short loc_1400C527E
0x1400c526c  test    rdi, rdi
0x1400c526f  jz      short loc_1400C5294
0x1400c5271  cmp     dword ptr [rdi+4], 0
0x1400c5275  mov     r14d, r13d
0x1400c5278  ja      loc_1400C5534
0x1400c527e  test    rdi, rdi
0x1400c5281  jz      short loc_1400C5294
0x1400c5283  xor     edx, edx; Tag
0x1400c5285  mov     rcx, rdi; P
0x1400c5288  call    cs:__imp_ExFreePoolWithTag
0x1400c528f  nop     dword ptr [rax+rax+00h]
0x1400c5294  test    ebx, ebx
0x1400c5296  js      loc_1400C53D6
0x1400c529c  lea     r8, [rsp+68h+P]
0x1400c52a1  mov     [rsp+68h+P], r13
0x1400c52a6  mov     edx, 2
0x1400c52ab  mov     rcx, rbp
0x1400c52ae  call    QueryAttributes
0x1400c52b3  mov     ebx, eax
0x1400c52b5  test    eax, eax
0x1400c52b7  jns     short loc_1400C52CC
0x1400c52b9  mov     rcx, [rsp+68h+P]
0x1400c52be  test    rcx, rcx
0x1400c52c1  jnz     loc_1400C5643
0x1400c52c7  jmp     loc_1400C53D6
0x1400c52cc  mov     rbp, [rsp+68h+P]
0x1400c52d1  mov     r12, r13
0x1400c52d4  mov     [rsp+68h+var_48], r13
0x1400c52d9  mov     [rsp+68h+arg_18], rbp
0x1400c52e1  test    rbp, rbp
0x1400c52e4  jnz     loc_1400C543C
0x1400c52ea  mov     rdx, r13
0x1400c52ed  mov     edi, r13d
0x1400c52f0  mov     [rsp+68h+arg_10], rdx
0x1400c52f8  test    edi, edi
0x1400c52fa  jnz     loc_1400C5515
0x1400c5300  test    r15, 0FFFFFFFFFFFFFF00h
0x1400c5307  jnz     loc_1400C56A5
0x1400c530d  test    edi, edi
0x1400c530f  jnz     short loc_1400C5327
0x1400c5311  test    r15b, 0Ah
0x1400c5315  setnz   cl
0x1400c5318  test    r15b, 1
0x1400c531c  setz    al
0x1400c531f  test    al, cl
0x1400c5321  jnz     loc_1400C5528
0x1400c5327  mov     r12, r13
0x1400c532a  test    edi, edi
0x1400c532c  jnz     loc_1400C56AF
0x1400c5332  mov     ecx, 20h ; ' '
0x1400c5337  mov     [rsp+68h+arg_18], rbp
0x1400c533f  lea     eax, [rcx-10h]
0x1400c5342  test    edi, edi
0x1400c5344  mov     r8d, 74436E45h
0x1400c534a  cmovz   eax, ecx
0x1400c534d  mov     ecx, 42h ; 'B'
0x1400c5352  mov     edx, eax
0x1400c5354  mov     r13d, eax
0x1400c5357  call    cs:__imp_ExAllocatePool2
0x1400c535e  nop     dword ptr [rax+rax+00h]
0x1400c5363  mov     r14, rax
0x1400c5366  test    rax, rax
0x1400c5369  jz      loc_1400C56BD
0x1400c536f  mov     r8d, r13d; Size
0x1400c5372  xor     edx, edx; Val
0x1400c5374  mov     rcx, rax; void *
0x1400c5377  xor     ebx, ebx
0x1400c5379  mov     r12, rax
0x1400c537c  call    memset
0x1400c5381  mov     r14d, edi
0x1400c5384  mov     [r12+8], r15
0x1400c5389  shl     r14d, 4
0x1400c538d  lea     r15, [r12+10h]
0x1400c5392  add     r14, r15
0x1400c5395  mov     dword ptr [r12], 1
0x1400c539d  xor     r13d, r13d
0x1400c53a0  mov     [r12+4], edi
0x1400c53a5  test    edi, edi
0x1400c53a7  jnz     short loc_1400C5408
0x1400c53a9  mov     rbp, [rsp+68h+arg_18]
0x1400c53b1  test    ebx, ebx
0x1400c53b3  js      short loc_1400C53B8
0x1400c53b5  mov     [rsi], r12
0x1400c53b8  test    rbp, rbp
0x1400c53bb  jz      short loc_1400C53CE
0x1400c53bd  xor     edx, edx; Tag
0x1400c53bf  mov     rcx, rbp; P
0x1400c53c2  call    cs:__imp_ExFreePoolWithTag
0x1400c53c9  nop     dword ptr [rax+rax+00h]
0x1400c53ce  test    ebx, ebx
0x1400c53d0  js      loc_1400C5637
0x1400c53d6  mov     r15, [rsp+68h+var_38]
0x1400c53db  mov     eax, ebx
0x1400c53dd  mov     r14, [rsp+68h+var_30]
0x1400c53e2  mov     r13, [rsp+68h+var_28]
0x1400c53e7  mov     r12, [rsp+68h+var_20]
0x1400c53ec  mov     rdi, [rsp+68h+arg_0]
0x1400c53f1  add     rsp, 50h
0x1400c53f5  pop     rsi
0x1400c53f6  pop     rbp
0x1400c53f7  pop     rbx
0x1400c53f8  retn
0x1400c53fa  mov     eax, 0C000000Dh
0x1400c53ff  add     rsp, 50h
0x1400c5403  pop     rsi
0x1400c5404  pop     rbp
0x1400c5405  pop     rbx
0x1400c5406  retn
0x1400c5408  mov     rbp, [rsp+68h+arg_10]
0x1400c5410  mov     r8d, r13d
0x1400c5413  mov     rdx, r14; void *
0x1400c5416  shl     r8, 4
0x1400c541a  mov     rcx, r15; DestinationString
0x1400c541d  add     r8, rbp; SourceString
0x1400c5420  call    CopyEnterpriseId
0x1400c5425  mov     eax, eax
0x1400c5427  add     r15, 10h
0x1400c542b  add     r14, rax
0x1400c542e  inc     r13d
0x1400c5431  cmp     r13d, edi
0x1400c5434  jnb     loc_1400C53A9
0x1400c543a  jmp     short loc_1400C5410
0x1400c543c  cmp     dword ptr [rbp+4], 0
0x1400c5440  jbe     loc_1400C52EA
0x1400c5446  xor     edi, edi
0x1400c5448  mov     r12d, 0FFFEh
0x1400c544e  xor     edx, edx
0x1400c5450  mov     [rsp+68h+arg_10], rdx
0x1400c5458  mov     eax, r13d
0x1400c545b  lea     rcx, [rax+rax*4]
0x1400c545f  mov     rax, [rbp+8]
0x1400c5463  cmp     dword ptr [rax+rcx*8+18h], 0
0x1400c5468  lea     r14, [rax+rcx*8]
0x1400c546c  jz      short loc_1400C5479
0x1400c546e  cmp     qword ptr [r14+20h], 0
0x1400c5473  jnz     loc_1400C5656
0x1400c5479  inc     r13d
0x1400c547c  cmp     r13d, [rbp+4]
0x1400c5480  jb      short loc_1400C5458
0x1400c5482  mov     r12, [rsp+68h+var_48]
0x1400c5487  xor     r13d, r13d
0x1400c548a  jmp     loc_1400C52F8
0x1400c548f  mov     r12, r13
0x1400c5492  test    r14, r14
0x1400c5495  jnz     short loc_1400C54AC
0x1400c5497  mov     r15, r13
0x1400c549a  test    r12, r12
0x1400c549d  jz      loc_1400C522C
0x1400c54a3  mov     r15, [r12]
0x1400c54a7  jmp     loc_1400C522C
0x1400c54ac  cmp     [r14+4], r13d
0x1400c54b0  jbe     short loc_1400C5497
0x1400c54b2  mov     rax, [r14+8]
0x1400c54b6  lea     rcx, [r15+r15*4]
0x1400c54ba  cmp     dword ptr [rax+rcx*8+18h], 0
0x1400c54bf  lea     r13, [rax+rcx*8]
0x1400c54c3  jz      short loc_1400C5507
0x1400c54c5  cmp     qword ptr [r13+20h], 0
0x1400c54ca  jz      short loc_1400C5507
0x1400c54cc  movzx   ecx, word ptr [r13+0]
0x1400c54d1  movzx   eax, cx
0x1400c54d4  and     ax, dx
0x1400c54d7  cmp     ax, 22h ; '"'
0x1400c54db  jnz     short loc_1400C5507
0x1400c54dd  mov     edi, ecx
0x1400c54df  lea     rdx, aEdpPolicyflags; "EDP://PolicyFlags"
0x1400c54e6  mov     r8d, ecx; Length
0x1400c54e9  mov     rcx, [r13+8]; Source1
0x1400c54ed  call    cs:__imp_RtlCompareMemory
0x1400c54f4  nop     dword ptr [rax+rax+00h]
0x1400c54f9  mov     edx, 0FFFEh
0x1400c54fe  cmp     rax, rdi
0x1400c5501  jnz     short loc_1400C5507
0x1400c5503  mov     r12, [r13+20h]
0x1400c5507  inc     r15d
0x1400c550a  cmp     r15d, [r14+4]
0x1400c550e  jb      short loc_1400C54B2
0x1400c5510  xor     r13d, r13d
0x1400c5513  jmp     short loc_1400C5497
0x1400c5515  test    rdx, rdx
0x1400c5518  jnz     loc_1400C5300
0x1400c551e  mov     ebx, 0C000000Dh
0x1400c5523  jmp     loc_1400C53B8
0x1400c5528  and     r15, 0FFFFFFFFFFFFFFF5h
0x1400c552c  mov     r12, r13
0x1400c552f  jmp     loc_1400C5332
0x1400c5534  mov     r12d, 0FFFEh
0x1400c553a  mov     eax, r14d
0x1400c553d  lea     rcx, [rax+rax*4]
0x1400c5541  mov     rax, [rdi+8]
0x1400c5545  cmp     dword ptr [rax+rcx*8+18h], 0
0x1400c554a  lea     rcx, [rax+rcx*8]
0x1400c554e  jnz     short loc_1400C5576
0x1400c5550  inc     r14d
0x1400c5553  cmp     r14d, [rdi+4]
0x1400c5557  jnb     loc_1400C527E
0x1400c555d  jmp     short loc_1400C553A
0x1400c555f  lea     ecx, [r9+20h]
0x1400c5563  cmp     ecx, r9d
0x1400c5566  jnb     loc_1400C533F
0x1400c556c  mov     ebx, 0C0000095h
0x1400c5571  jmp     loc_1400C53B1
0x1400c5576  cmp     qword ptr [rcx+20h], 0
0x1400c557b  jz      short loc_1400C5550
0x1400c557d  movzx   edx, word ptr [rcx]
0x1400c5580  movzx   eax, dx
0x1400c5583  and     ax, r12w
0x1400c5587  cmp     ax, 2Ah ; '*'
0x1400c558b  jnz     short loc_1400C5550
0x1400c558d  mov     rcx, [rcx+8]; Source1
0x1400c5591  mov     r8d, edx; Length
0x1400c5594  lea     rdx, aEdpEvaluationf; "EDP://EvaluationFlags"
0x1400c559b  call    cs:__imp_RtlCompareMemory
0x1400c55a2  nop     dword ptr [rax+rax+00h]
0x1400c55a7  jmp     short loc_1400C5550
0x1400c55a9  test    ebx, ebx
0x1400c55ab  js      short loc_1400C5603
0x1400c55ad  jmp     short loc_1400C555F
0x1400c55af  mov     r9d, edi
0x1400c55b2  mov     eax, 0FFFFFFFFh
0x1400c55b7  shl     r9, 4
0x1400c55bb  mov     r10, r13
0x1400c55be  cmp     r9, rax
0x1400c55c1  jbe     short loc_1400C55CA
0x1400c55c3  mov     ebx, 0C0000095h
0x1400c55c8  jmp     short loc_1400C5603
0x1400c55ca  mov     r14, [rsp+68h+arg_10]
0x1400c55d2  mov     r11d, r13d
0x1400c55d5  mov     ebx, r13d
0x1400c55d8  cmp     r11d, edi
0x1400c55db  jnb     short loc_1400C55A9
0x1400c55dd  mov     ecx, r11d
0x1400c55e0  lea     r8, [rsp+68h+P]; pusResult
0x1400c55e5  add     rcx, rcx
0x1400c55e8  mov     word ptr [rsp+68h+P], r13w
0x1400c55ee  mov     edx, 2; usAddend
0x1400c55f3  movzx   ecx, word ptr [r14+rcx*8]; usAugend
0x1400c55f8  call    RtlUShortAdd
0x1400c55fd  mov     ebx, eax
0x1400c55ff  test    eax, eax
0x1400c5601  jns     short loc_1400C5622
0x1400c5603  test    r10, r10
0x1400c5606  jz      loc_1400C53B1
0x1400c560c  xor     edx, edx; Tag
0x1400c560e  mov     rcx, r10; P
0x1400c5611  call    cs:__imp_ExFreePoolWithTag
0x1400c5618  nop     dword ptr [rax+rax+00h]
0x1400c561d  jmp     loc_1400C53B1
0x1400c5622  movzx   ecx, word ptr [rsp+68h+P]
0x1400c5627  add     ecx, r9d
0x1400c562a  cmp     ecx, r9d
0x1400c562d  jb      short loc_1400C55C3
0x1400c562f  inc     r11d
0x1400c5632  mov     r9d, ecx
0x1400c5635  jmp     short loc_1400C55D5
0x1400c5637  test    r12, r12
0x1400c563a  jz      loc_1400C53D6
  ... truncated ...
```
