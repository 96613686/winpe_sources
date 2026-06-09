# GetEnterpriseContext

- ea: `0x1400bb6a0`
- end: `0x1400bbb97`
- name: `GetEnterpriseContext`
- size: `1271`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400bb540`
- `0x14015076c`

## callees

- `0x1400bb6a0`
- `0x1400bbba0`
- `0x1400bc804`
- `0x1400d7bfc`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400bb9bd`
- `ntoskrnl!RtlCompareMemory` at `0x1400bba6b`
- `ntoskrnl!RtlCompareMemory` at `0x1400bbb4b`
- `ntoskrnl!RtlCompareMemory` at `0x1400bb9bd`
- `ntoskrnl!RtlCompareMemory` at `0x1400bba6b`
- `ntoskrnl!RtlCompareMemory` at `0x1400bbb4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bb706`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bb758`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bb892`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbae1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbb15`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bb706`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bb758`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bb892`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbae1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbb15`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb827`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb827`

## pseudocode

```c
__int64 __fastcall GetEnterpriseContext(__int64 a1, struct _UNICODE_STRING **a2)
{
  unsigned int v4; // r13d
  int v5; // eax
  _QWORD *v6; // r14
  NTSTATUS v7; // ebx
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
0x1400bb6a0  mov     rax, rsp
0x1400bb6a3  push    rbx
0x1400bb6a4  push    rbp
0x1400bb6a5  push    rsi
0x1400bb6a6  sub     rsp, 50h
0x1400bb6aa  mov     rsi, rdx
0x1400bb6ad  mov     rbp, rcx
0x1400bb6b0  test    rdx, rdx
0x1400bb6b3  jz      loc_1400BB8CA
0x1400bb6b9  mov     [rax+8], rdi
0x1400bb6bd  lea     r8, [rax+10h]
0x1400bb6c1  mov     [rax-20h], r12
0x1400bb6c5  mov     [rax-28h], r13
0x1400bb6c9  xor     r13d, r13d
0x1400bb6cc  mov     [rdx], r13
0x1400bb6cf  mov     edx, 1
0x1400bb6d4  mov     [rax-30h], r14
0x1400bb6d8  mov     [rax-38h], r15
0x1400bb6dc  mov     [rax+10h], r13
0x1400bb6e0  call    QueryAttributes
0x1400bb6e5  mov     r14, [rsp+68h+P]
0x1400bb6ea  mov     ebx, eax
0x1400bb6ec  mov     r15d, r13d
0x1400bb6ef  mov     edx, 0FFFEh
0x1400bb6f4  test    eax, eax
0x1400bb6f6  jns     loc_1400BB95F
0x1400bb6fc  test    r14, r14
0x1400bb6ff  jz      short loc_1400BB712
0x1400bb701  xor     edx, edx; Tag
0x1400bb703  mov     rcx, r14; P
0x1400bb706  call    cs:__imp_ExFreePoolWithTag
0x1400bb70d  nop     dword ptr [rax+rax+00h]
0x1400bb712  test    ebx, ebx
0x1400bb714  js      loc_1400BB8A6
0x1400bb71a  lea     r8, [rsp+68h+P]
0x1400bb71f  mov     [rsp+68h+P], r13
0x1400bb724  mov     edx, 8
0x1400bb729  mov     rcx, rbp
0x1400bb72c  call    QueryAttributes
0x1400bb731  mov     rdi, [rsp+68h+P]
0x1400bb736  mov     ebx, eax
0x1400bb738  test    eax, eax
0x1400bb73a  js      short loc_1400BB74E
0x1400bb73c  test    rdi, rdi
0x1400bb73f  jz      short loc_1400BB764
0x1400bb741  cmp     dword ptr [rdi+4], 0
0x1400bb745  mov     r14d, r13d
0x1400bb748  ja      loc_1400BBA04
0x1400bb74e  test    rdi, rdi
0x1400bb751  jz      short loc_1400BB764
0x1400bb753  xor     edx, edx; Tag
0x1400bb755  mov     rcx, rdi; P
0x1400bb758  call    cs:__imp_ExFreePoolWithTag
0x1400bb75f  nop     dword ptr [rax+rax+00h]
0x1400bb764  test    ebx, ebx
0x1400bb766  js      loc_1400BB8A6
0x1400bb76c  lea     r8, [rsp+68h+P]
0x1400bb771  mov     [rsp+68h+P], r13
0x1400bb776  mov     edx, 2
0x1400bb77b  mov     rcx, rbp
0x1400bb77e  call    QueryAttributes
0x1400bb783  mov     ebx, eax
0x1400bb785  test    eax, eax
0x1400bb787  jns     short loc_1400BB79C
0x1400bb789  mov     rcx, [rsp+68h+P]
0x1400bb78e  test    rcx, rcx
0x1400bb791  jnz     loc_1400BBB13
0x1400bb797  jmp     loc_1400BB8A6
0x1400bb79c  mov     rbp, [rsp+68h+P]
0x1400bb7a1  mov     r12, r13
0x1400bb7a4  mov     [rsp+68h+var_48], r13
0x1400bb7a9  mov     [rsp+68h+arg_18], rbp
0x1400bb7b1  test    rbp, rbp
0x1400bb7b4  jnz     loc_1400BB90C
0x1400bb7ba  mov     rdx, r13
0x1400bb7bd  mov     edi, r13d
0x1400bb7c0  mov     [rsp+68h+arg_10], rdx
0x1400bb7c8  test    edi, edi
0x1400bb7ca  jnz     loc_1400BB9E5
0x1400bb7d0  test    r15, 0FFFFFFFFFFFFFF00h
0x1400bb7d7  jnz     loc_1400BBB75
0x1400bb7dd  test    edi, edi
0x1400bb7df  jnz     short loc_1400BB7F7
0x1400bb7e1  test    r15b, 0Ah
0x1400bb7e5  setnz   cl
0x1400bb7e8  test    r15b, 1
0x1400bb7ec  setz    al
0x1400bb7ef  test    al, cl
0x1400bb7f1  jnz     loc_1400BB9F8
0x1400bb7f7  mov     r12, r13
0x1400bb7fa  test    edi, edi
0x1400bb7fc  jnz     loc_1400BBB7F
0x1400bb802  mov     ecx, 20h ; ' '
0x1400bb807  mov     [rsp+68h+arg_18], rbp
0x1400bb80f  lea     eax, [rcx-10h]
0x1400bb812  test    edi, edi
0x1400bb814  mov     r8d, 74436E45h
0x1400bb81a  cmovz   eax, ecx
0x1400bb81d  mov     ecx, 42h ; 'B'
0x1400bb822  mov     edx, eax
0x1400bb824  mov     r13d, eax
0x1400bb827  call    cs:__imp_ExAllocatePool2
0x1400bb82e  nop     dword ptr [rax+rax+00h]
0x1400bb833  mov     r14, rax
0x1400bb836  test    rax, rax
0x1400bb839  jz      loc_1400BBB8D
0x1400bb83f  mov     r8d, r13d; Size
0x1400bb842  xor     edx, edx; Val
0x1400bb844  mov     rcx, rax; void *
0x1400bb847  xor     ebx, ebx
0x1400bb849  mov     r12, rax
0x1400bb84c  call    memset
0x1400bb851  mov     r14d, edi
0x1400bb854  mov     [r12+8], r15
0x1400bb859  shl     r14d, 4
0x1400bb85d  lea     r15, [r12+10h]
0x1400bb862  add     r14, r15
0x1400bb865  mov     dword ptr [r12], 1
0x1400bb86d  xor     r13d, r13d
0x1400bb870  mov     [r12+4], edi
0x1400bb875  test    edi, edi
0x1400bb877  jnz     short loc_1400BB8D8
0x1400bb879  mov     rbp, [rsp+68h+arg_18]
0x1400bb881  test    ebx, ebx
0x1400bb883  js      short loc_1400BB888
0x1400bb885  mov     [rsi], r12
0x1400bb888  test    rbp, rbp
0x1400bb88b  jz      short loc_1400BB89E
0x1400bb88d  xor     edx, edx; Tag
0x1400bb88f  mov     rcx, rbp; P
0x1400bb892  call    cs:__imp_ExFreePoolWithTag
0x1400bb899  nop     dword ptr [rax+rax+00h]
0x1400bb89e  test    ebx, ebx
0x1400bb8a0  js      loc_1400BBB07
0x1400bb8a6  mov     r15, [rsp+68h+var_38]
0x1400bb8ab  mov     eax, ebx
0x1400bb8ad  mov     r14, [rsp+68h+var_30]
0x1400bb8b2  mov     r13, [rsp+68h+var_28]
0x1400bb8b7  mov     r12, [rsp+68h+var_20]
0x1400bb8bc  mov     rdi, [rsp+68h+arg_0]
0x1400bb8c1  add     rsp, 50h
0x1400bb8c5  pop     rsi
0x1400bb8c6  pop     rbp
0x1400bb8c7  pop     rbx
0x1400bb8c8  retn
0x1400bb8ca  mov     eax, 0C000000Dh
0x1400bb8cf  add     rsp, 50h
0x1400bb8d3  pop     rsi
0x1400bb8d4  pop     rbp
0x1400bb8d5  pop     rbx
0x1400bb8d6  retn
0x1400bb8d8  mov     rbp, [rsp+68h+arg_10]
0x1400bb8e0  mov     r8d, r13d
0x1400bb8e3  mov     rdx, r14; void *
0x1400bb8e6  shl     r8, 4
0x1400bb8ea  mov     rcx, r15; DestinationString
0x1400bb8ed  add     r8, rbp; SourceString
0x1400bb8f0  call    CopyEnterpriseId
0x1400bb8f5  mov     eax, eax
0x1400bb8f7  add     r15, 10h
0x1400bb8fb  add     r14, rax
0x1400bb8fe  inc     r13d
0x1400bb901  cmp     r13d, edi
0x1400bb904  jnb     loc_1400BB879
0x1400bb90a  jmp     short loc_1400BB8E0
0x1400bb90c  cmp     dword ptr [rbp+4], 0
0x1400bb910  jbe     loc_1400BB7BA
0x1400bb916  xor     edi, edi
0x1400bb918  mov     r12d, 0FFFEh
0x1400bb91e  xor     edx, edx
0x1400bb920  mov     [rsp+68h+arg_10], rdx
0x1400bb928  mov     eax, r13d
0x1400bb92b  lea     rcx, [rax+rax*4]
0x1400bb92f  mov     rax, [rbp+8]
0x1400bb933  cmp     dword ptr [rax+rcx*8+18h], 0
0x1400bb938  lea     r14, [rax+rcx*8]
0x1400bb93c  jz      short loc_1400BB949
0x1400bb93e  cmp     qword ptr [r14+20h], 0
0x1400bb943  jnz     loc_1400BBB26
0x1400bb949  inc     r13d
0x1400bb94c  cmp     r13d, [rbp+4]
0x1400bb950  jb      short loc_1400BB928
0x1400bb952  mov     r12, [rsp+68h+var_48]
0x1400bb957  xor     r13d, r13d
0x1400bb95a  jmp     loc_1400BB7C8
0x1400bb95f  mov     r12, r13
0x1400bb962  test    r14, r14
0x1400bb965  jnz     short loc_1400BB97C
0x1400bb967  mov     r15, r13
0x1400bb96a  test    r12, r12
0x1400bb96d  jz      loc_1400BB6FC
0x1400bb973  mov     r15, [r12]
0x1400bb977  jmp     loc_1400BB6FC
0x1400bb97c  cmp     [r14+4], r13d
0x1400bb980  jbe     short loc_1400BB967
0x1400bb982  mov     rax, [r14+8]
0x1400bb986  lea     rcx, [r15+r15*4]
0x1400bb98a  cmp     dword ptr [rax+rcx*8+18h], 0
0x1400bb98f  lea     r13, [rax+rcx*8]
0x1400bb993  jz      short loc_1400BB9D7
0x1400bb995  cmp     qword ptr [r13+20h], 0
0x1400bb99a  jz      short loc_1400BB9D7
0x1400bb99c  movzx   ecx, word ptr [r13+0]
0x1400bb9a1  movzx   eax, cx
0x1400bb9a4  and     ax, dx
0x1400bb9a7  cmp     ax, 22h ; '"'
0x1400bb9ab  jnz     short loc_1400BB9D7
0x1400bb9ad  mov     edi, ecx
0x1400bb9af  lea     rdx, aEdpPolicyflags; "EDP://PolicyFlags"
0x1400bb9b6  mov     r8d, ecx; Length
0x1400bb9b9  mov     rcx, [r13+8]; Source1
0x1400bb9bd  call    cs:__imp_RtlCompareMemory
0x1400bb9c4  nop     dword ptr [rax+rax+00h]
0x1400bb9c9  mov     edx, 0FFFEh
0x1400bb9ce  cmp     rax, rdi
0x1400bb9d1  jnz     short loc_1400BB9D7
0x1400bb9d3  mov     r12, [r13+20h]
0x1400bb9d7  inc     r15d
0x1400bb9da  cmp     r15d, [r14+4]
0x1400bb9de  jb      short loc_1400BB982
0x1400bb9e0  xor     r13d, r13d
0x1400bb9e3  jmp     short loc_1400BB967
0x1400bb9e5  test    rdx, rdx
0x1400bb9e8  jnz     loc_1400BB7D0
0x1400bb9ee  mov     ebx, 0C000000Dh
0x1400bb9f3  jmp     loc_1400BB888
0x1400bb9f8  and     r15, 0FFFFFFFFFFFFFFF5h
0x1400bb9fc  mov     r12, r13
0x1400bb9ff  jmp     loc_1400BB802
0x1400bba04  mov     r12d, 0FFFEh
0x1400bba0a  mov     eax, r14d
0x1400bba0d  lea     rcx, [rax+rax*4]
0x1400bba11  mov     rax, [rdi+8]
0x1400bba15  cmp     dword ptr [rax+rcx*8+18h], 0
0x1400bba1a  lea     rcx, [rax+rcx*8]
0x1400bba1e  jnz     short loc_1400BBA46
0x1400bba20  inc     r14d
0x1400bba23  cmp     r14d, [rdi+4]
0x1400bba27  jnb     loc_1400BB74E
0x1400bba2d  jmp     short loc_1400BBA0A
0x1400bba2f  lea     ecx, [r9+20h]
0x1400bba33  cmp     ecx, r9d
0x1400bba36  jnb     loc_1400BB80F
0x1400bba3c  mov     ebx, 0C0000095h
0x1400bba41  jmp     loc_1400BB881
0x1400bba46  cmp     qword ptr [rcx+20h], 0
0x1400bba4b  jz      short loc_1400BBA20
0x1400bba4d  movzx   edx, word ptr [rcx]
0x1400bba50  movzx   eax, dx
0x1400bba53  and     ax, r12w
0x1400bba57  cmp     ax, 2Ah ; '*'
0x1400bba5b  jnz     short loc_1400BBA20
0x1400bba5d  mov     rcx, [rcx+8]; Source1
0x1400bba61  mov     r8d, edx; Length
0x1400bba64  lea     rdx, aEdpEvaluationf; "EDP://EvaluationFlags"
0x1400bba6b  call    cs:__imp_RtlCompareMemory
0x1400bba72  nop     dword ptr [rax+rax+00h]
0x1400bba77  jmp     short loc_1400BBA20
0x1400bba79  test    ebx, ebx
0x1400bba7b  js      short loc_1400BBAD3
0x1400bba7d  jmp     short loc_1400BBA2F
0x1400bba7f  mov     r9d, edi
0x1400bba82  mov     eax, 0FFFFFFFFh
0x1400bba87  shl     r9, 4
0x1400bba8b  mov     r10, r13
0x1400bba8e  cmp     r9, rax
0x1400bba91  jbe     short loc_1400BBA9A
0x1400bba93  mov     ebx, 0C0000095h
0x1400bba98  jmp     short loc_1400BBAD3
0x1400bba9a  mov     r14, [rsp+68h+arg_10]
0x1400bbaa2  mov     r11d, r13d
0x1400bbaa5  mov     ebx, r13d
0x1400bbaa8  cmp     r11d, edi
0x1400bbaab  jnb     short loc_1400BBA79
0x1400bbaad  mov     ecx, r11d
0x1400bbab0  lea     r8, [rsp+68h+P]; pusResult
0x1400bbab5  add     rcx, rcx
0x1400bbab8  mov     word ptr [rsp+68h+P], r13w
0x1400bbabe  mov     edx, 2; usAddend
0x1400bbac3  movzx   ecx, word ptr [r14+rcx*8]; usAugend
0x1400bbac8  call    RtlUShortAdd
0x1400bbacd  mov     ebx, eax
0x1400bbacf  test    eax, eax
0x1400bbad1  jns     short loc_1400BBAF2
0x1400bbad3  test    r10, r10
0x1400bbad6  jz      loc_1400BB881
0x1400bbadc  xor     edx, edx; Tag
0x1400bbade  mov     rcx, r10; P
0x1400bbae1  call    cs:__imp_ExFreePoolWithTag
0x1400bbae8  nop     dword ptr [rax+rax+00h]
0x1400bbaed  jmp     loc_1400BB881
0x1400bbaf2  movzx   ecx, word ptr [rsp+68h+P]
0x1400bbaf7  add     ecx, r9d
0x1400bbafa  cmp     ecx, r9d
0x1400bbafd  jb      short loc_1400BBA93
0x1400bbaff  inc     r11d
0x1400bbb02  mov     r9d, ecx
0x1400bbb05  jmp     short loc_1400BBAA5
0x1400bbb07  test    r12, r12
0x1400bbb0a  jz      loc_1400BB8A6
  ... truncated ...
```
