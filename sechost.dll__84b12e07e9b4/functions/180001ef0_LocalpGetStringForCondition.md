# LocalpGetStringForCondition

- ea: `0x180001ef0`
- end: `0x180002677`
- name: `LocalpGetStringForCondition`
- size: `1927`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x180003190`
- `0x180019a50`
- `0x180022490`

## callees

- `0x1800015a0`
- `0x180001b98`
- `0x180001c48`
- `0x180001e58`
- `0x180001ef0`
- `0x180002680`
- `0x180017be0`
- `0x18004f91a`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800022f4`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180002312`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180002330`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800022f4`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180002312`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180002330`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000227e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002400`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000227e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002400`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000236b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002447`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002450`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800024be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000251a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000236b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002447`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002450`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800024be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000251a`

## string_xrefs

- `0x180002326`: `@TOKEN.`

## pseudocode

```c
__int64 __fastcall LocalpGetStringForCondition(
        _DWORD *a1,
        unsigned int a2,
        void *a3,
        _DWORD *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  unsigned int v9; // r15d
  _DWORD *v10; // r12
  unsigned int PrintableAttributeName; // esi
  int v12; // r13d
  __int64 v13; // r14
  __int64 v14; // rdx
  unsigned __int8 *v15; // rdi
  unsigned __int8 v16; // bl
  bool v17; // zf
  __int64 v18; // rdx
  int OperatorIndexByToken; // eax
  __int64 v20; // rdx
  __int64 v21; // rax
  unsigned int v22; // r9d
  wchar_t *v23; // r15
  SIZE_T v24; // r12
  HLOCAL v25; // rdi
  char v26; // al
  __int64 v27; // rax
  _WORD *v28; // r12
  unsigned __int64 v29; // rcx
  unsigned int v30; // edx
  _WORD *v31; // rbx
  __int64 v32; // rax
  unsigned __int64 v33; // rcx
  SIZE_T v34; // r15
  HLOCAL v35; // rax
  _QWORD *v36; // rbx
  void *v38; // [rsp+40h] [rbp-C0h] BYREF
  int v39; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD *v40; // [rsp+50h] [rbp-B0h]
  unsigned int v41; // [rsp+58h] [rbp-A8h]
  wchar_t **v42; // [rsp+60h] [rbp-A0h]
  __int64 v43; // [rsp+68h] [rbp-98h]
  __int64 v44; // [rsp+70h] [rbp-90h]
  __int64 v45; // [rsp+78h] [rbp-88h]
  __int64 v46; // [rsp+80h] [rbp-80h]
  _DWORD *v47; // [rsp+88h] [rbp-78h]
  HLOCAL hMem[2]; // [rsp+90h] [rbp-70h]
  HLOCAL v49[256]; // [rsp+A0h] [rbp-60h] BYREF

  v45 = a5;
  v9 = a2;
  v10 = a1;
  v44 = a6;
  v41 = a2;
  v47 = a1;
  v43 = a7;
  v40 = a4;
  hMem[0] = a3;
  v38 = 0;
  memset_0(v49, 0, sizeof(v49));
  v39 = 0;
  if ( !v10 || !a3 || !v9 )
    return 87;
  if ( v9 < 6 || *v10 != 2020897377 )
    return 805;
  PrintableAttributeName = 0;
  v12 = 0;
  LODWORD(v13) = 4;
  v14 = 645;
  while ( (unsigned int)v13 < v9 )
  {
    if ( v12 == 255 )
    {
      PrintableAttributeName = 1001;
      goto LABEL_93;
    }
    v15 = (unsigned __int8 *)v10 + (unsigned int)v13;
    v16 = *v15;
    if ( *v15 == 0x93 )
    {
LABEL_35:
      if ( v40 && (unsigned __int8)(v16 + 118) <= 9u && _bittest((const int *)&v14, (unsigned __int8)(v16 + 118)) )
        *v40 |= 4u;
      if ( (unsigned __int8)(v16 + 96) <= 1u )
      {
        if ( v12 < 2 )
          goto LABEL_33;
        PrintableAttributeName = EncloseSubCondition(&v49[v12 - 1], 645);
        if ( PrintableAttributeName )
          goto LABEL_91;
        PrintableAttributeName = EncloseSubCondition(&v49[v12 - 2], v18);
        if ( PrintableAttributeName )
          goto LABEL_91;
      }
      else if ( v16 == 0xA2 )
      {
        if ( v12 < 1 )
          goto LABEL_33;
        PrintableAttributeName = EncloseSubCondition(&v49[v12 - 1], 645);
        if ( PrintableAttributeName )
          goto LABEL_91;
      }
      OperatorIndexByToken = GetOperatorIndexByToken(*v15, v14);
      if ( OperatorIndexByToken < 0 )
        goto LABEL_33;
      v20 = 3LL * OperatorIndexByToken;
      v46 = v20 * 8;
      v42 = &(&Operators)[v20];
      v21 = -1;
      do
        v17 = (&Operators)[v20][++v21] == 0;
      while ( !v17 );
      v17 = LOBYTE(qword_180052010[v20]) == 0;
      v22 = 2 * v21;
      LODWORD(v38) = 2 * v21;
      if ( v17 )
      {
        if ( v12 < 2 )
          goto LABEL_33;
        v27 = -1;
        v28 = hMem[v12 + 1];
        do
          ++v27;
        while ( v28[v27] );
        v29 = 2LL * (unsigned int)v27;
        if ( v29 > 0xFFFFFFFF )
          goto LABEL_85;
        if ( (unsigned int)v29 + v22 < v22 )
          goto LABEL_85;
        v30 = v29 + v22;
        v31 = hMem[v12];
        v32 = -1;
        do
          ++v32;
        while ( v31[v32] );
        v33 = 2LL * (unsigned int)v32;
        if ( v33 > 0xFFFFFFFF || (unsigned int)v33 + v30 < v30 )
        {
LABEL_85:
          PrintableAttributeName = 534;
          goto LABEL_93;
        }
        v34 = (unsigned int)v33 + v30 + 10;
        v35 = LocalAlloc(0x40u, v34);
        v25 = v35;
        if ( !v35 )
        {
LABEL_82:
          PrintableAttributeName = 8;
          goto LABEL_83;
        }
        if ( (int)RtlStringCchPrintfW(v35, v34 >> 1, L"(%ls %ls %ls)", v31, *v42, v28) < 0 )
        {
LABEL_56:
          PrintableAttributeName = 50;
LABEL_83:
          if ( v25 )
            LocalFree(v25);
LABEL_90:
          if ( !v12 )
            return PrintableAttributeName;
LABEL_91:
          if ( !PrintableAttributeName )
            PrintableAttributeName = 1336;
          goto LABEL_93;
        }
        LocalFree(v28);
        LocalFree(v31);
        v12 -= 2;
      }
      else
      {
        if ( !v12 )
          return 1336;
        v23 = (wchar_t *)hMem[v12 + 1];
        if ( (int)ULongAddStringSize(v22, v23, &v38) < 0 )
          goto LABEL_85;
        v24 = (unsigned int)((_DWORD)v38 + 8);
        v25 = LocalAlloc(0x40u, v24);
        if ( !v25 )
          goto LABEL_82;
        if ( v16 == 0xA2 )
        {
          if ( (int)RtlStringCchPrintfW(v25, v24 >> 1, L"(%ls%ls)", *v42, v23) < 0 )
            goto LABEL_56;
        }
        else
        {
          v26 = *((_BYTE *)&qword_180052008 + v46);
          if ( (v26 == -121 || v26 == -115)
            && (!_wcsnicmp(v23, L"@USER.", 6u) || !_wcsnicmp(v23, L"@DEVICE.", 8u) || !_wcsnicmp(v23, L"@TOKEN.", 7u)) )
          {
            PrintableAttributeName = 1336;
            goto LABEL_83;
          }
          if ( (int)RtlStringCchPrintfW(v25, v24 >> 1, L"(%ls %ls)", *v42, v23) < 0 )
            goto LABEL_56;
        }
        LocalFree(v23);
        --v12;
      }
      v9 = v41;
      v10 = v47;
      v39 = 1;
      v49[v12] = v25;
      goto LABEL_77;
    }
    if ( v16 )
    {
      if ( v16 == 0xFC )
      {
LABEL_15:
        PrintableAttributeName = GetPrintableAttributeName(
                                   (int)v10 + (int)v13,
                                   v9 - (unsigned int)v13,
                                   v16,
                                   (unsigned int)&v38,
                                   (__int64)&v39);
        if ( PrintableAttributeName )
        {
LABEL_79:
          v25 = v38;
          goto LABEL_83;
        }
        switch ( v16 )
        {
          case 0xFB:
            if ( v40 )
              *v40 |= 4u;
            break;
          case 0xF9:
            if ( v40 )
              *v40 |= 1u;
            break;
          case 0xFA:
            if ( v40 )
              *v40 |= 2u;
            break;
          default:
            if ( v16 == 0xFC && v40 )
              *v40 |= 8u;
            break;
        }
        v49[v12] = v38;
      }
      else
      {
        switch ( *v15 )
        {
          case 1u:
          case 2u:
          case 3u:
          case 4u:
          case 0x10u:
          case 0x18u:
          case 0x50u:
          case 0x51u:
            PrintableAttributeName = GetPrintableOperandValue(
                                       (int)v10 + (int)v13,
                                       v9 - (unsigned int)v13,
                                       (unsigned int)&v38,
                                       (unsigned int)&v39,
                                       v45,
                                       v44,
                                       v43,
                                       a8);
            if ( PrintableAttributeName )
              goto LABEL_79;
            v49[v12] = v38;
            break;
          case 0x80u:
          case 0x81u:
          case 0x82u:
          case 0x83u:
          case 0x84u:
          case 0x85u:
          case 0x86u:
          case 0x87u:
          case 0x88u:
          case 0x89u:
          case 0x8Au:
          case 0x8Bu:
          case 0x8Cu:
          case 0x8Du:
          case 0x8Eu:
          case 0x8Fu:
          case 0x90u:
          case 0x91u:
          case 0x92u:
          case 0xA0u:
          case 0xA1u:
          case 0xA2u:
          case 0xA3u:
            v14 = 645;
            goto LABEL_35;
          case 0xF8u:
          case 0xF9u:
          case 0xFAu:
          case 0xFBu:
            goto LABEL_15;
          default:
            goto LABEL_33;
        }
      }
LABEL_77:
      ++v12;
      v38 = 0;
      v14 = 645;
      goto LABEL_78;
    }
    while ( 1 )
    {
      v13 = (unsigned int)(v13 + 1);
      v17 = (_DWORD)v13 == v9;
      if ( (unsigned int)v13 >= v9 )
        break;
      if ( *((_BYTE *)v10 + v13) )
      {
        v17 = (_DWORD)v13 == v9;
        break;
      }
    }
    if ( !v17 )
    {
LABEL_33:
      PrintableAttributeName = 1336;
      goto LABEL_90;
    }
LABEL_78:
    LODWORD(v13) = v39 + v13;
  }
  if ( v12 != 1 )
    goto LABEL_90;
  v36 = hMem[0];
  *(_QWORD *)hMem[0] = v49[0];
  PrintableAttributeName = EncloseSubCondition(v36, 645);
  if ( !PrintableAttributeName )
    return PrintableAttributeName;
  *v36 = 0;
  do
LABEL_93:
    LocalFree(v49[--v12]);
  while ( v12 );
  return PrintableAttributeName;
}

```

## disassembly

```asm
0x180001ef0  push    rbp
0x180001ef2  push    rbx
0x180001ef3  push    rdi
0x180001ef4  push    r12
0x180001ef6  push    r15
0x180001ef8  lea     rbp, [rsp-7D0h]
0x180001f00  sub     rsp, 8D0h
0x180001f07  mov     rax, cs:__security_cookie
0x180001f0e  xor     rax, rsp
0x180001f11  mov     [rbp+7F0h+var_50], rax
0x180001f18  mov     rax, [rbp+7F0h+arg_20]
0x180001f1f  mov     rbx, r8
0x180001f22  mov     [rsp+8F0h+var_878], rax
0x180001f27  mov     r15d, edx
0x180001f2a  mov     rax, [rbp+7F0h+arg_28]
0x180001f31  mov     r12, rcx
0x180001f34  mov     [rsp+8F0h+var_880], rax
0x180001f39  xor     edi, edi
0x180001f3b  mov     rax, [rbp+7F0h+arg_30]
0x180001f42  mov     r8d, 800h; Size
0x180001f48  mov     [rsp+8F0h+var_898], edx
0x180001f4c  xor     edx, edx; Val
0x180001f4e  mov     [rbp+7F0h+var_868], rcx
0x180001f52  lea     rcx, [rbp+7F0h+var_850]; void *
0x180001f56  mov     [rsp+8F0h+var_888], rax
0x180001f5b  mov     [rsp+8F0h+var_8A0], r9
0x180001f60  mov     [rbp+7F0h+hMem], rbx
0x180001f64  mov     [rsp+8F0h+var_8B0], rdi
0x180001f69  call    memset_0
0x180001f6e  mov     [rsp+8F0h+var_8A8], edi
0x180001f72  test    r12, r12
0x180001f75  jz      loc_180002548
0x180001f7b  test    rbx, rbx
0x180001f7e  jz      loc_180002548
0x180001f84  test    r15d, r15d
0x180001f87  jz      loc_180002548
0x180001f8d  cmp     r15d, 6
0x180001f91  jb      loc_180002541
0x180001f97  cmp     dword ptr [r12], 78747261h
0x180001f9f  jnz     loc_180002541
0x180001fa5  mov     [rsp+8F0h+var_28], rsi
0x180001fad  lea     rcx, __ImageBase
0x180001fb4  mov     [rsp+8F0h+var_30], r13
0x180001fbc  mov     esi, edi
0x180001fbe  mov     [rsp+8F0h+var_38], r14
0x180001fc6  mov     r13d, edi
0x180001fc9  mov     r14d, 4
0x180001fcf  mov     edx, 285h
0x180001fd4  cmp     r14d, r15d
0x180001fd7  jnb     loc_1800024D4
0x180001fdd  cmp     r13d, 0FFh
0x180001fe4  jz      loc_1800024CD
0x180001fea  mov     edi, r14d
0x180001fed  add     rdi, r12
0x180001ff0  movzx   ebx, byte ptr [rdi]
0x180001ff3  cmp     bl, 93h
0x180001ff6  jz      loc_180002149
0x180001ffc  test    bl, bl
0x180001ffe  jz      loc_180002120
0x180002004  cmp     bl, 0FCh
0x180002007  jz      loc_18000208E; jumptable 000000018000202F cases 248-251
0x18000200d  lea     eax, [rbx-1]; switch 251 cases
0x180002010  cmp     eax, 0FAh
0x180002015  ja      def_18000202F; jumptable 000000018000202F default case, cases 5-15,17-23,25-79,82-127,147-159,164-247
0x18000201b  cdqe
0x18000201d  movzx   eax, ds:(byte_18000257C - 180000000h)[rcx+rax]
0x180002025  mov     edx, ds:(jpt_18000202F - 180000000h)[rcx+rax*4]
0x18000202c  add     rdx, rcx
0x18000202f  jmp     rdx; switch jump
0x180002031  movzx   eax, [rbp+7F0h+arg_38]; jumptable 000000018000202F cases 1-4,16,24,80,81
0x180002038  lea     r9, [rsp+8F0h+var_8A8]
0x18000203d  mov     [rsp+8F0h+var_8B8], al
0x180002041  lea     r8, [rsp+8F0h+var_8B0]
0x180002046  mov     rax, [rsp+8F0h+var_888]
0x18000204b  mov     edx, r15d
0x18000204e  mov     [rsp+8F0h+var_8C0], rax
0x180002053  sub     edx, r14d
0x180002056  mov     rax, [rsp+8F0h+var_880]
0x18000205b  mov     rcx, rdi
0x18000205e  mov     [rsp+8F0h+var_8C8], rax
0x180002063  mov     rax, [rsp+8F0h+var_878]
0x180002068  mov     [rsp+8F0h+var_8D0], rax
0x18000206d  call    GetPrintableOperandValue
0x180002072  mov     esi, eax
0x180002074  test    eax, eax
0x180002076  jnz     loc_180002495
0x18000207c  mov     rcx, [rsp+8F0h+var_8B0]
0x180002081  movsxd  rdx, r13d
0x180002084  mov     [rbp+rdx*8+7F0h+var_850], rcx
0x180002089  jmp     loc_180002473
0x18000208e  mov     edx, r15d; jumptable 000000018000202F cases 248-251
0x180002091  lea     rax, [rsp+8F0h+var_8A8]
0x180002096  sub     edx, r14d
0x180002099  mov     [rsp+8F0h+var_8D0], rax
0x18000209e  lea     r9, [rsp+8F0h+var_8B0]
0x1800020a3  movzx   r8d, bl
0x1800020a7  mov     rcx, rdi
0x1800020aa  call    GetPrintableAttributeName
0x1800020af  mov     esi, eax
0x1800020b1  test    eax, eax
0x1800020b3  jnz     loc_180002495
0x1800020b9  cmp     bl, 0FBh
0x1800020bc  jnz     short loc_1800020CD
0x1800020be  mov     rdx, [rsp+8F0h+var_8A0]
0x1800020c3  test    rdx, rdx
0x1800020c6  jz      short loc_180002107
0x1800020c8  or      dword ptr [rdx], 4
0x1800020cb  jmp     short loc_180002107
0x1800020cd  cmp     bl, 0F9h
0x1800020d0  jnz     short loc_1800020E1
0x1800020d2  mov     rdx, [rsp+8F0h+var_8A0]
0x1800020d7  test    rdx, rdx
0x1800020da  jz      short loc_180002107
0x1800020dc  or      dword ptr [rdx], 1
0x1800020df  jmp     short loc_180002107
0x1800020e1  cmp     bl, 0FAh
0x1800020e4  jnz     short loc_1800020F5
0x1800020e6  mov     rdx, [rsp+8F0h+var_8A0]
0x1800020eb  test    rdx, rdx
0x1800020ee  jz      short loc_180002107
0x1800020f0  or      dword ptr [rdx], 2
0x1800020f3  jmp     short loc_180002107
0x1800020f5  cmp     bl, 0FCh
0x1800020f8  jnz     short loc_180002107
0x1800020fa  mov     rdx, [rsp+8F0h+var_8A0]
0x1800020ff  test    rdx, rdx
0x180002102  jz      short loc_180002107
0x180002104  or      dword ptr [rdx], 8
0x180002107  mov     rax, [rsp+8F0h+var_8B0]
0x18000210c  movsxd  rcx, r13d
0x18000210f  mov     [rbp+rcx*8+7F0h+var_850], rax
0x180002114  jmp     loc_180002473
0x180002120  inc     r14d
0x180002123  cmp     r14d, r15d
0x180002126  jnb     short loc_180002132
0x180002128  cmp     byte ptr [r14+r12], 0
0x18000212d  jz      short loc_180002120
0x18000212f  cmp     r14d, r15d
0x180002132  jz      loc_18000248B
0x180002138  mov     ebx, 538h; jumptable 000000018000202F default case, cases 5-15,17-23,25-79,82-127,147-159,164-247
0x18000213d  mov     esi, ebx
0x18000213f  jmp     loc_180002505
0x180002144  mov     edx, 285h; jumptable 000000018000202F cases 128-146,160-163
0x180002149  mov     rcx, [rsp+8F0h+var_8A0]
0x18000214e  test    rcx, rcx
0x180002151  jz      short loc_180002165
0x180002153  lea     eax, [rbx+76h]
0x180002156  cmp     al, 9
0x180002158  ja      short loc_180002165
0x18000215a  movzx   eax, al
0x18000215d  bt      edx, eax
0x180002160  jnb     short loc_180002165
0x180002162  or      dword ptr [rcx], 4
0x180002165  lea     eax, [rbx+60h]
0x180002168  cmp     al, 1
0x18000216a  jbe     short loc_18000219B
0x18000216c  cmp     bl, 0A2h
0x18000216f  jnz     short loc_1800021D5
0x180002171  cmp     r13d, 1
0x180002175  jl      short def_18000202F; jumptable 000000018000202F default case, cases 5-15,17-23,25-79,82-127,147-159,164-247
0x180002177  lea     eax, [r13-1]
0x18000217b  movsxd  rcx, eax
0x18000217e  lea     rax, [rbp+7F0h+var_850]
0x180002182  lea     rcx, [rax+rcx*8]
0x180002186  call    EncloseSubCondition
0x18000218b  mov     esi, eax
0x18000218d  test    eax, eax
0x18000218f  jz      short loc_1800021D5
0x180002191  mov     ebx, 538h
0x180002196  jmp     loc_18000250A
0x18000219b  cmp     r13d, 2
0x18000219f  jl      short def_18000202F; jumptable 000000018000202F default case, cases 5-15,17-23,25-79,82-127,147-159,164-247
0x1800021a1  lea     eax, [r13-1]
0x1800021a5  movsxd  rcx, eax
0x1800021a8  lea     rax, [rbp+7F0h+var_850]
0x1800021ac  lea     rcx, [rax+rcx*8]
0x1800021b0  call    EncloseSubCondition
0x1800021b5  mov     esi, eax
0x1800021b7  test    eax, eax
0x1800021b9  jnz     short loc_180002191
0x1800021bb  lea     eax, [r13-2]
0x1800021bf  movsxd  rcx, eax
0x1800021c2  lea     rax, [rbp+7F0h+var_850]
0x1800021c6  lea     rcx, [rax+rcx*8]
0x1800021ca  call    EncloseSubCondition
0x1800021cf  mov     esi, eax
0x1800021d1  test    eax, eax
0x1800021d3  jnz     short loc_180002191
0x1800021d5  movzx   ecx, byte ptr [rdi]
0x1800021d8  call    GetOperatorIndexByToken
0x1800021dd  test    eax, eax
0x1800021df  js      def_18000202F; jumptable 000000018000202F default case, cases 5-15,17-23,25-79,82-127,147-159,164-247
0x1800021e5  cdqe
0x1800021e7  lea     r8, __ImageBase
0x1800021ee  lea     rcx, [rax+rax*2]
0x1800021f2  lea     rdx, ds:0[rcx*8]
0x1800021fa  lea     rax, rva Operators[r8]
0x180002201  mov     [rbp+7F0h+var_870], rdx
0x180002205  add     rax, rdx
0x180002208  mov     [rsp+8F0h+var_890], rax
0x18000220d  mov     rcx, [rax]
0x180002210  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180002217  nop     word ptr [rax+rax+00000000h]
0x180002220  cmp     word ptr [rcx+rax*2+2], 0
0x180002226  lea     rax, [rax+1]
0x18000222a  jnz     short loc_180002220
0x18000222c  cmp     byte ptr [rdx+r8+52010h], 0
0x180002235  lea     r9d, [rax+rax]
0x180002239  mov     dword ptr [rsp+8F0h+var_8B0], r9d
0x18000223e  jz      loc_180002379
0x180002244  test    r13d, r13d
0x180002247  jz      loc_1800024A5
0x18000224d  movsxd  rax, r13d
0x180002250  lea     r8, [rsp+8F0h+var_8B0]
0x180002255  mov     ecx, r9d
0x180002258  mov     r15, [rbp+rax*8+7F0h+String1]
0x18000225d  mov     rdx, r15
0x180002260  call    ULongAddStringSize
0x180002265  test    eax, eax
0x180002267  js      loc_1800024C6
0x18000226d  mov     eax, dword ptr [rsp+8F0h+var_8B0]
0x180002271  mov     ecx, 40h ; '@'; uFlags
0x180002276  add     eax, 8
0x180002279  mov     edx, eax; uBytes
0x18000227b  mov     r12d, eax
0x18000227e  call    cs:__imp_LocalAlloc
0x180002284  mov     rdi, rax
0x180002287  test    rax, rax
0x18000228a  jz      loc_1800024AC
0x180002290  cmp     bl, 0A2h
0x180002293  jnz     short loc_1800022C9
0x180002295  mov     rax, [rsp+8F0h+var_890]
0x18000229a  lea     r8, aLsLs_0; "(%ls%ls)"
0x1800022a1  shr     r12, 1
0x1800022a4  mov     rcx, rdi
0x1800022a7  mov     rdx, r12
0x1800022aa  mov     [rsp+8F0h+var_8D0], r15
0x1800022af  mov     r9, [rax]
0x1800022b2  call    RtlStringCchPrintfW
0x1800022b7  test    eax, eax
0x1800022b9  jns     loc_180002368
0x1800022bf  mov     esi, 32h ; '2'
0x1800022c4  jmp     loc_1800024B1
0x1800022c9  mov     rax, [rbp+7F0h+var_870]
0x1800022cd  lea     rcx, __ImageBase
0x1800022d4  movzx   eax, byte ptr [rax+rcx+52008h]
0x1800022dc  cmp     al, 87h
0x1800022de  jz      short loc_1800022E4
0x1800022e0  cmp     al, 8Dh
0x1800022e2  jnz     short loc_18000233E
0x1800022e4  mov     r8d, 6; MaxCount
0x1800022ea  lea     rdx, aUser; "@USER."
0x1800022f1  mov     rcx, r15; String1
0x1800022f4  call    cs:__imp__wcsnicmp
0x1800022fa  test    eax, eax
0x1800022fc  jz      loc_18000249C
0x180002302  mov     r8d, 8; MaxCount
0x180002308  lea     rdx, aDevice; "@DEVICE."
0x18000230f  mov     rcx, r15; String1
0x180002312  call    cs:__imp__wcsnicmp
0x180002318  test    eax, eax
0x18000231a  jz      loc_18000249C
0x180002320  mov     r8d, 7; MaxCount
0x180002326  lea     rdx, aToken; "@TOKEN."
0x18000232d  mov     rcx, r15; String1
0x180002330  call    cs:__imp__wcsnicmp
0x180002336  test    eax, eax
0x180002338  jz      loc_18000249C
0x18000233e  mov     rax, [rsp+8F0h+var_890]
0x180002343  lea     r8, aLsLs; "(%ls %ls)"
0x18000234a  shr     r12, 1
0x18000234d  mov     rcx, rdi
0x180002350  mov     rdx, r12
0x180002353  mov     [rsp+8F0h+var_8D0], r15
0x180002358  mov     r9, [rax]
0x18000235b  call    RtlStringCchPrintfW
0x180002360  test    eax, eax
0x180002362  js      loc_1800022BF
0x180002368  mov     rcx, r15; hMem
0x18000236b  call    cs:__imp_LocalFree
0x180002371  dec     r13d
0x180002374  jmp     loc_18000245A
0x180002379  cmp     r13d, 2
0x18000237d  jl      def_18000202F; jumptable 000000018000202F default case, cases 5-15,17-23,25-79,82-127,147-159,164-247
0x180002383  movsxd  rbx, r13d
0x180002386  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000238d  mov     r12, [rbp+rbx*8+7F0h+String1]
0x180002392  inc     rax
0x180002395  cmp     word ptr [r12+rax*2], 0
0x18000239b  jnz     short loc_180002392
0x18000239d  mov     ecx, eax
0x18000239f  mov     r8d, 0FFFFFFFFh
0x1800023a5  add     rcx, rcx
0x1800023a8  cmp     rcx, r8
0x1800023ab  ja      loc_1800024C6
0x1800023b1  lea     eax, [rcx+r9]
0x1800023b5  mov     edx, r8d
0x1800023b8  cmp     eax, r9d
0x1800023bb  cmovnb  edx, eax
0x1800023be  jb      loc_1800024C6
  ... truncated ...
```
