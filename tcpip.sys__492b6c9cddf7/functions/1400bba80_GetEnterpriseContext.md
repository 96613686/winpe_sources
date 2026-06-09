# GetEnterpriseContext

- ea: `0x1400bba80`
- end: `0x1400bbf77`
- name: `GetEnterpriseContext`
- size: `1271`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400bb920`
- `0x14015062c`

## callees

- `0x1400bba80`
- `0x1400bbf80`
- `0x1400bcbe4`
- `0x1400d7e1c`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400bbd9d`
- `ntoskrnl!RtlCompareMemory` at `0x1400bbe4b`
- `ntoskrnl!RtlCompareMemory` at `0x1400bbf2b`
- `ntoskrnl!RtlCompareMemory` at `0x1400bbd9d`
- `ntoskrnl!RtlCompareMemory` at `0x1400bbe4b`
- `ntoskrnl!RtlCompareMemory` at `0x1400bbf2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbae6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbb38`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbc72`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbec1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbef5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbae6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbb38`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbc72`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbec1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbef5`
- `ntoskrnl!ExAllocatePool2` at `0x1400bbc07`
- `ntoskrnl!ExAllocatePool2` at `0x1400bbc07`

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
0x1400bba80  mov     rax, rsp
0x1400bba83  push    rbx
0x1400bba84  push    rbp
0x1400bba85  push    rsi
0x1400bba86  sub     rsp, 50h
0x1400bba8a  mov     rsi, rdx
0x1400bba8d  mov     rbp, rcx
0x1400bba90  test    rdx, rdx
0x1400bba93  jz      loc_1400BBCAA
0x1400bba99  mov     [rax+8], rdi
0x1400bba9d  lea     r8, [rax+10h]
0x1400bbaa1  mov     [rax-20h], r12
0x1400bbaa5  mov     [rax-28h], r13
0x1400bbaa9  xor     r13d, r13d
0x1400bbaac  mov     [rdx], r13
0x1400bbaaf  mov     edx, 1
0x1400bbab4  mov     [rax-30h], r14
0x1400bbab8  mov     [rax-38h], r15
0x1400bbabc  mov     [rax+10h], r13
0x1400bbac0  call    QueryAttributes
0x1400bbac5  mov     r14, [rsp+68h+P]
0x1400bbaca  mov     ebx, eax
0x1400bbacc  mov     r15d, r13d
0x1400bbacf  mov     edx, 0FFFEh
0x1400bbad4  test    eax, eax
0x1400bbad6  jns     loc_1400BBD3F
0x1400bbadc  test    r14, r14
0x1400bbadf  jz      short loc_1400BBAF2
0x1400bbae1  xor     edx, edx; Tag
0x1400bbae3  mov     rcx, r14; P
0x1400bbae6  call    cs:__imp_ExFreePoolWithTag
0x1400bbaed  nop     dword ptr [rax+rax+00h]
0x1400bbaf2  test    ebx, ebx
0x1400bbaf4  js      loc_1400BBC86
0x1400bbafa  lea     r8, [rsp+68h+P]
0x1400bbaff  mov     [rsp+68h+P], r13
0x1400bbb04  mov     edx, 8
0x1400bbb09  mov     rcx, rbp
0x1400bbb0c  call    QueryAttributes
0x1400bbb11  mov     rdi, [rsp+68h+P]
0x1400bbb16  mov     ebx, eax
0x1400bbb18  test    eax, eax
0x1400bbb1a  js      short loc_1400BBB2E
0x1400bbb1c  test    rdi, rdi
0x1400bbb1f  jz      short loc_1400BBB44
0x1400bbb21  cmp     dword ptr [rdi+4], 0
0x1400bbb25  mov     r14d, r13d
0x1400bbb28  ja      loc_1400BBDE4
0x1400bbb2e  test    rdi, rdi
0x1400bbb31  jz      short loc_1400BBB44
0x1400bbb33  xor     edx, edx; Tag
0x1400bbb35  mov     rcx, rdi; P
0x1400bbb38  call    cs:__imp_ExFreePoolWithTag
0x1400bbb3f  nop     dword ptr [rax+rax+00h]
0x1400bbb44  test    ebx, ebx
0x1400bbb46  js      loc_1400BBC86
0x1400bbb4c  lea     r8, [rsp+68h+P]
0x1400bbb51  mov     [rsp+68h+P], r13
0x1400bbb56  mov     edx, 2
0x1400bbb5b  mov     rcx, rbp
0x1400bbb5e  call    QueryAttributes
0x1400bbb63  mov     ebx, eax
0x1400bbb65  test    eax, eax
0x1400bbb67  jns     short loc_1400BBB7C
0x1400bbb69  mov     rcx, [rsp+68h+P]
0x1400bbb6e  test    rcx, rcx
0x1400bbb71  jnz     loc_1400BBEF3
0x1400bbb77  jmp     loc_1400BBC86
0x1400bbb7c  mov     rbp, [rsp+68h+P]
0x1400bbb81  mov     r12, r13
0x1400bbb84  mov     [rsp+68h+var_48], r13
0x1400bbb89  mov     [rsp+68h+arg_18], rbp
0x1400bbb91  test    rbp, rbp
0x1400bbb94  jnz     loc_1400BBCEC
0x1400bbb9a  mov     rdx, r13
0x1400bbb9d  mov     edi, r13d
0x1400bbba0  mov     [rsp+68h+arg_10], rdx
0x1400bbba8  test    edi, edi
0x1400bbbaa  jnz     loc_1400BBDC5
0x1400bbbb0  test    r15, 0FFFFFFFFFFFFFF00h
0x1400bbbb7  jnz     loc_1400BBF55
0x1400bbbbd  test    edi, edi
0x1400bbbbf  jnz     short loc_1400BBBD7
0x1400bbbc1  test    r15b, 0Ah
0x1400bbbc5  setnz   cl
0x1400bbbc8  test    r15b, 1
0x1400bbbcc  setz    al
0x1400bbbcf  test    al, cl
0x1400bbbd1  jnz     loc_1400BBDD8
0x1400bbbd7  mov     r12, r13
0x1400bbbda  test    edi, edi
0x1400bbbdc  jnz     loc_1400BBF5F
0x1400bbbe2  mov     ecx, 20h ; ' '
0x1400bbbe7  mov     [rsp+68h+arg_18], rbp
0x1400bbbef  lea     eax, [rcx-10h]
0x1400bbbf2  test    edi, edi
0x1400bbbf4  mov     r8d, 74436E45h
0x1400bbbfa  cmovz   eax, ecx
0x1400bbbfd  mov     ecx, 42h ; 'B'
0x1400bbc02  mov     edx, eax
0x1400bbc04  mov     r13d, eax
0x1400bbc07  call    cs:__imp_ExAllocatePool2
0x1400bbc0e  nop     dword ptr [rax+rax+00h]
0x1400bbc13  mov     r14, rax
0x1400bbc16  test    rax, rax
0x1400bbc19  jz      loc_1400BBF6D
0x1400bbc1f  mov     r8d, r13d; Size
0x1400bbc22  xor     edx, edx; Val
0x1400bbc24  mov     rcx, rax; void *
0x1400bbc27  xor     ebx, ebx
0x1400bbc29  mov     r12, rax
0x1400bbc2c  call    memset
0x1400bbc31  mov     r14d, edi
0x1400bbc34  mov     [r12+8], r15
0x1400bbc39  shl     r14d, 4
0x1400bbc3d  lea     r15, [r12+10h]
0x1400bbc42  add     r14, r15
0x1400bbc45  mov     dword ptr [r12], 1
0x1400bbc4d  xor     r13d, r13d
0x1400bbc50  mov     [r12+4], edi
0x1400bbc55  test    edi, edi
0x1400bbc57  jnz     short loc_1400BBCB8
0x1400bbc59  mov     rbp, [rsp+68h+arg_18]
0x1400bbc61  test    ebx, ebx
0x1400bbc63  js      short loc_1400BBC68
0x1400bbc65  mov     [rsi], r12
0x1400bbc68  test    rbp, rbp
0x1400bbc6b  jz      short loc_1400BBC7E
0x1400bbc6d  xor     edx, edx; Tag
0x1400bbc6f  mov     rcx, rbp; P
0x1400bbc72  call    cs:__imp_ExFreePoolWithTag
0x1400bbc79  nop     dword ptr [rax+rax+00h]
0x1400bbc7e  test    ebx, ebx
0x1400bbc80  js      loc_1400BBEE7
0x1400bbc86  mov     r15, [rsp+68h+var_38]
0x1400bbc8b  mov     eax, ebx
0x1400bbc8d  mov     r14, [rsp+68h+var_30]
0x1400bbc92  mov     r13, [rsp+68h+var_28]
0x1400bbc97  mov     r12, [rsp+68h+var_20]
0x1400bbc9c  mov     rdi, [rsp+68h+arg_0]
0x1400bbca1  add     rsp, 50h
0x1400bbca5  pop     rsi
0x1400bbca6  pop     rbp
0x1400bbca7  pop     rbx
0x1400bbca8  retn
0x1400bbcaa  mov     eax, 0C000000Dh
0x1400bbcaf  add     rsp, 50h
0x1400bbcb3  pop     rsi
0x1400bbcb4  pop     rbp
0x1400bbcb5  pop     rbx
0x1400bbcb6  retn
0x1400bbcb8  mov     rbp, [rsp+68h+arg_10]
0x1400bbcc0  mov     r8d, r13d
0x1400bbcc3  mov     rdx, r14; void *
0x1400bbcc6  shl     r8, 4
0x1400bbcca  mov     rcx, r15; DestinationString
0x1400bbccd  add     r8, rbp; SourceString
0x1400bbcd0  call    CopyEnterpriseId
0x1400bbcd5  mov     eax, eax
0x1400bbcd7  add     r15, 10h
0x1400bbcdb  add     r14, rax
0x1400bbcde  inc     r13d
0x1400bbce1  cmp     r13d, edi
0x1400bbce4  jnb     loc_1400BBC59
0x1400bbcea  jmp     short loc_1400BBCC0
0x1400bbcec  cmp     dword ptr [rbp+4], 0
0x1400bbcf0  jbe     loc_1400BBB9A
0x1400bbcf6  xor     edi, edi
0x1400bbcf8  mov     r12d, 0FFFEh
0x1400bbcfe  xor     edx, edx
0x1400bbd00  mov     [rsp+68h+arg_10], rdx
0x1400bbd08  mov     eax, r13d
0x1400bbd0b  lea     rcx, [rax+rax*4]
0x1400bbd0f  mov     rax, [rbp+8]
0x1400bbd13  cmp     dword ptr [rax+rcx*8+18h], 0
0x1400bbd18  lea     r14, [rax+rcx*8]
0x1400bbd1c  jz      short loc_1400BBD29
0x1400bbd1e  cmp     qword ptr [r14+20h], 0
0x1400bbd23  jnz     loc_1400BBF06
0x1400bbd29  inc     r13d
0x1400bbd2c  cmp     r13d, [rbp+4]
0x1400bbd30  jb      short loc_1400BBD08
0x1400bbd32  mov     r12, [rsp+68h+var_48]
0x1400bbd37  xor     r13d, r13d
0x1400bbd3a  jmp     loc_1400BBBA8
0x1400bbd3f  mov     r12, r13
0x1400bbd42  test    r14, r14
0x1400bbd45  jnz     short loc_1400BBD5C
0x1400bbd47  mov     r15, r13
0x1400bbd4a  test    r12, r12
0x1400bbd4d  jz      loc_1400BBADC
0x1400bbd53  mov     r15, [r12]
0x1400bbd57  jmp     loc_1400BBADC
0x1400bbd5c  cmp     [r14+4], r13d
0x1400bbd60  jbe     short loc_1400BBD47
0x1400bbd62  mov     rax, [r14+8]
0x1400bbd66  lea     rcx, [r15+r15*4]
0x1400bbd6a  cmp     dword ptr [rax+rcx*8+18h], 0
0x1400bbd6f  lea     r13, [rax+rcx*8]
0x1400bbd73  jz      short loc_1400BBDB7
0x1400bbd75  cmp     qword ptr [r13+20h], 0
0x1400bbd7a  jz      short loc_1400BBDB7
0x1400bbd7c  movzx   ecx, word ptr [r13+0]
0x1400bbd81  movzx   eax, cx
0x1400bbd84  and     ax, dx
0x1400bbd87  cmp     ax, 22h ; '"'
0x1400bbd8b  jnz     short loc_1400BBDB7
0x1400bbd8d  mov     edi, ecx
0x1400bbd8f  lea     rdx, aEdpPolicyflags; "EDP://PolicyFlags"
0x1400bbd96  mov     r8d, ecx; Length
0x1400bbd99  mov     rcx, [r13+8]; Source1
0x1400bbd9d  call    cs:__imp_RtlCompareMemory
0x1400bbda4  nop     dword ptr [rax+rax+00h]
0x1400bbda9  mov     edx, 0FFFEh
0x1400bbdae  cmp     rax, rdi
0x1400bbdb1  jnz     short loc_1400BBDB7
0x1400bbdb3  mov     r12, [r13+20h]
0x1400bbdb7  inc     r15d
0x1400bbdba  cmp     r15d, [r14+4]
0x1400bbdbe  jb      short loc_1400BBD62
0x1400bbdc0  xor     r13d, r13d
0x1400bbdc3  jmp     short loc_1400BBD47
0x1400bbdc5  test    rdx, rdx
0x1400bbdc8  jnz     loc_1400BBBB0
0x1400bbdce  mov     ebx, 0C000000Dh
0x1400bbdd3  jmp     loc_1400BBC68
0x1400bbdd8  and     r15, 0FFFFFFFFFFFFFFF5h
0x1400bbddc  mov     r12, r13
0x1400bbddf  jmp     loc_1400BBBE2
0x1400bbde4  mov     r12d, 0FFFEh
0x1400bbdea  mov     eax, r14d
0x1400bbded  lea     rcx, [rax+rax*4]
0x1400bbdf1  mov     rax, [rdi+8]
0x1400bbdf5  cmp     dword ptr [rax+rcx*8+18h], 0
0x1400bbdfa  lea     rcx, [rax+rcx*8]
0x1400bbdfe  jnz     short loc_1400BBE26
0x1400bbe00  inc     r14d
0x1400bbe03  cmp     r14d, [rdi+4]
0x1400bbe07  jnb     loc_1400BBB2E
0x1400bbe0d  jmp     short loc_1400BBDEA
0x1400bbe0f  lea     ecx, [r9+20h]
0x1400bbe13  cmp     ecx, r9d
0x1400bbe16  jnb     loc_1400BBBEF
0x1400bbe1c  mov     ebx, 0C0000095h
0x1400bbe21  jmp     loc_1400BBC61
0x1400bbe26  cmp     qword ptr [rcx+20h], 0
0x1400bbe2b  jz      short loc_1400BBE00
0x1400bbe2d  movzx   edx, word ptr [rcx]
0x1400bbe30  movzx   eax, dx
0x1400bbe33  and     ax, r12w
0x1400bbe37  cmp     ax, 2Ah ; '*'
0x1400bbe3b  jnz     short loc_1400BBE00
0x1400bbe3d  mov     rcx, [rcx+8]; Source1
0x1400bbe41  mov     r8d, edx; Length
0x1400bbe44  lea     rdx, aEdpEvaluationf; "EDP://EvaluationFlags"
0x1400bbe4b  call    cs:__imp_RtlCompareMemory
0x1400bbe52  nop     dword ptr [rax+rax+00h]
0x1400bbe57  jmp     short loc_1400BBE00
0x1400bbe59  test    ebx, ebx
0x1400bbe5b  js      short loc_1400BBEB3
0x1400bbe5d  jmp     short loc_1400BBE0F
0x1400bbe5f  mov     r9d, edi
0x1400bbe62  mov     eax, 0FFFFFFFFh
0x1400bbe67  shl     r9, 4
0x1400bbe6b  mov     r10, r13
0x1400bbe6e  cmp     r9, rax
0x1400bbe71  jbe     short loc_1400BBE7A
0x1400bbe73  mov     ebx, 0C0000095h
0x1400bbe78  jmp     short loc_1400BBEB3
0x1400bbe7a  mov     r14, [rsp+68h+arg_10]
0x1400bbe82  mov     r11d, r13d
0x1400bbe85  mov     ebx, r13d
0x1400bbe88  cmp     r11d, edi
0x1400bbe8b  jnb     short loc_1400BBE59
0x1400bbe8d  mov     ecx, r11d
0x1400bbe90  lea     r8, [rsp+68h+P]; pusResult
0x1400bbe95  add     rcx, rcx
0x1400bbe98  mov     word ptr [rsp+68h+P], r13w
0x1400bbe9e  mov     edx, 2; usAddend
0x1400bbea3  movzx   ecx, word ptr [r14+rcx*8]; usAugend
0x1400bbea8  call    RtlUShortAdd
0x1400bbead  mov     ebx, eax
0x1400bbeaf  test    eax, eax
0x1400bbeb1  jns     short loc_1400BBED2
0x1400bbeb3  test    r10, r10
0x1400bbeb6  jz      loc_1400BBC61
0x1400bbebc  xor     edx, edx; Tag
0x1400bbebe  mov     rcx, r10; P
0x1400bbec1  call    cs:__imp_ExFreePoolWithTag
0x1400bbec8  nop     dword ptr [rax+rax+00h]
0x1400bbecd  jmp     loc_1400BBC61
0x1400bbed2  movzx   ecx, word ptr [rsp+68h+P]
0x1400bbed7  add     ecx, r9d
0x1400bbeda  cmp     ecx, r9d
0x1400bbedd  jb      short loc_1400BBE73
0x1400bbedf  inc     r11d
0x1400bbee2  mov     r9d, ecx
0x1400bbee5  jmp     short loc_1400BBE85
0x1400bbee7  test    r12, r12
0x1400bbeea  jz      loc_1400BBC86
  ... truncated ...
```
