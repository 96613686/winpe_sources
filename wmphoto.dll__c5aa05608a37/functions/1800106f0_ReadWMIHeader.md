# ReadWMIHeader

- ea: `0x1800106f0`
- end: `0x180010c43`
- name: `ReadWMIHeader`
- size: `1363`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x180007340`
- `0x18000f244`
- `0x180010094`
- `0x180010148`

## callees

- `0x1800106f0`
- `0x18002d6ac`
- `0x18002d9e8`
- `0x18002f0d0`
- `0x18002f398`
- `0x180035e50`
- `0x180044010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180010764`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180010764`

## pseudocode

```c
__int64 __fastcall ReadWMIHeader(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  int v7; // ebx
  unsigned int Bit32_SB; // ecx
  int v9; // r15d
  int v10; // eax
  int v11; // r13d
  int v12; // r12d
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  unsigned int v17; // ebx
  int v18; // eax
  int v19; // ebx
  int v20; // eax
  int v21; // ecx
  __int64 v22; // r15
  unsigned int v23; // ebx
  int v24; // eax
  unsigned int v25; // eax
  __int64 v26; // r15
  unsigned int v27; // ebx
  int v28; // eax
  int v29; // r15d
  unsigned int v30; // ebx
  __int64 v31; // r11
  unsigned __int64 v32; // r9
  __int64 v33; // rbx
  unsigned __int64 v34; // r10
  unsigned __int64 v35; // rdx
  unsigned __int64 v36; // r8
  char v37; // al
  __int128 v39; // [rsp+20h] [rbp-40h] BYREF
  __int128 v40; // [rsp+30h] [rbp-30h]
  __int64 v41; // [rsp+40h] [rbp-20h]
  int v42; // [rsp+48h] [rbp-18h]
  char Str[8]; // [rsp+50h] [rbp-10h] BYREF

  v3 = *(_QWORD *)(a2 + 64);
  v41 = 0;
  *(_QWORD *)Str = 0;
  v39 = 0;
  v40 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, char *, __int64))(v3 + 64))(v3, Str, 8);
  if ( v7 >= 0 )
  {
    Str[7] = 0;
    if ( !strstr(Str, "WMPHOTO") )
    {
      v7 = -106;
      return (unsigned int)-(v7 != 0);
    }
    v7 = attach_SB(&v39, v3);
    if ( v7 < 0 )
      return (unsigned int)-(v7 != 0);
    if ( (unsigned int)getBit32_SB(&v39, 4) != 1
      || (*(_QWORD *)a3 = 1, *(_DWORD *)(a2 + 20) = getBit32_SB(&v39, 1), Bit32_SB = getBit32_SB(&v39, 3), Bit32_SB >= 2) )
    {
      v7 = -107;
LABEL_60:
      detach_SB(&v39);
      return (unsigned int)-(v7 != 0);
    }
    *(_DWORD *)(a2 + 24) = Bit32_SB == 1;
    v9 = getBit32_SB(&v39, 1);
    *(_DWORD *)(a2 + 32) = getBit32_SB(&v39, 1);
    *((_DWORD *)a1 + 29) = getBit32_SB(&v39, 3);
    *(_DWORD *)(a3 + 20) = getBit32_SB(&v39, 1);
    v10 = getBit32_SB(&v39, 2);
    if ( v10 == 3 )
    {
LABEL_9:
      v7 = -104;
      goto LABEL_60;
    }
    *(_DWORD *)(a2 + 16) = v10;
    v11 = getBit32_SB(&v39, 1);
    getBit32_SB(&v39, 1);
    *(_DWORD *)(a2 + 12) = 1;
    v42 = getBit32_SB(&v39, 1);
    *(_DWORD *)(a3 + 24) = getBit32_SB(&v39, 1);
    if ( *(_DWORD *)(a2 + 24) )
    {
      getBit32_SB(&v39, 1);
      *((_DWORD *)a1 + 11) = getBit32_SB(&v39, 1);
      v12 = 0;
      v13 = getBit32_SB(&v39, 1);
    }
    else
    {
      v12 = getBit32_SB(&v39, 1);
      getBit32_SB(&v39, 2);
      v13 = 0;
      *((_DWORD *)a1 + 11) = 0;
    }
    *((_DWORD *)a1 + 12) = v13;
    v14 = getBit32_SB(&v39, 1);
    *(_DWORD *)(a3 + 12) = v14;
    if ( !v14 )
      *((_DWORD *)a1 + 12) = 0;
    *(_DWORD *)(a2 + 32872) = *(_DWORD *)(a3 + 12);
    v15 = getBit32_SB(&v39, 4);
    *((_DWORD *)a1 + 4) = v15;
    if ( v15 == 4 || v15 <= 0 || (unsigned int)(v15 - 6) <= 2 )
    {
      v16 = getBit32_SB(&v39, 4);
      *((_DWORD *)a1 + 5) = v16;
      if ( v16 >= 11 )
      {
        if ( v16 != 15 )
          goto LABEL_20;
        *((_DWORD *)a1 + 5) = 0;
        *(_DWORD *)(a2 + 32860) = 1;
      }
      v17 = v11 != 0 ? 0xFFFFFFF0 : 0;
      *a1 = (unsigned int)getBit32_SB(&v39, v17 + 32) + 1;
      a1[1] = (unsigned int)getBit32_SB(&v39, v17 + 32) + 1;
      *(_QWORD *)(a3 + 64) = 0;
      *(_QWORD *)(a3 + 56) = 0;
      *(_QWORD *)(a3 + 48) = 0;
      *(_QWORD *)(a3 + 40) = 0;
      if ( !v42 )
      {
        if ( (*a1 & 0xF) != 0 )
          *(_QWORD *)(a3 + 64) = 16 - (*a1 & 0xF);
        if ( (a1[1] & 0xF) != 0 )
          *(_QWORD *)(a3 + 56) = 16 - (a1[1] & 0xF);
      }
      *(_DWORD *)(a2 + 16468) = 0;
      *(_DWORD *)(a2 + 80) = 0;
      if ( v9 )
      {
        v18 = getBit32_SB(&v39, 12);
        *(_DWORD *)(a2 + 80) = v18;
        v19 = v18;
        v20 = getBit32_SB(&v39, 12);
        *(_DWORD *)(a2 + 16468) = v20;
        v21 = v19;
      }
      else
      {
        v19 = 0;
        v20 = 0;
        v21 = 0;
      }
      if ( *(_DWORD *)(a3 + 20) || *(_DWORD *)(a2 + 32) != 1 && !(v19 + v20) )
      {
        *(_DWORD *)(a2 + 16472) = 0;
        LODWORD(v22) = 0;
        *(_DWORD *)(a2 + 84) = 0;
        if ( v21 )
        {
          while ( DWORD2(v39) < 0x4100 )
          {
            v23 = *(_DWORD *)(a2 + 4LL * (unsigned int)v22 + 84);
            v24 = getBit32_SB(&v39, v11 != 0 ? 8 : 16);
            v22 = (unsigned int)(v22 + 1);
            *(_DWORD *)(a2 + 4 * v22 + 84) = v24 + v23;
            if ( v24 + v23 <= v23 )
              break;
            if ( (unsigned int)v22 >= *(_DWORD *)(a2 + 80) )
              goto LABEL_38;
          }
        }
        else
        {
LABEL_38:
          v25 = *(_DWORD *)(a2 + 16468);
          LODWORD(v26) = 0;
          if ( v25 )
          {
            while ( DWORD2(v39) < 0x4100 )
            {
              v27 = *(_DWORD *)(a2 + 4LL * (unsigned int)v26 + 16472);
              v28 = getBit32_SB(&v39, v11 != 0 ? 8 : 16);
              v26 = (unsigned int)(v26 + 1);
              *(_DWORD *)(a2 + 4 * v26 + 16472) = v28 + v27;
              if ( v28 + v27 <= v27 )
                break;
              v25 = *(_DWORD *)(a2 + 16468);
              if ( (unsigned int)v26 >= v25 )
                goto LABEL_42;
            }
          }
          else
          {
LABEL_42:
            if ( v12 && (v29 = 0, (v30 = (v25 + 1) * (*(_DWORD *)(a2 + 80) + 1)) != 0) )
            {
              while ( DWORD2(v39) < 0x4100 )
              {
                getBit32_SB(&v39, 8);
                if ( ++v29 >= v30 )
                  goto LABEL_46;
              }
            }
            else
            {
LABEL_46:
              if ( v42 )
              {
                *(_QWORD *)(a3 + 40) = (unsigned __int8)getBit32_SB(&v39, 6);
                *(_QWORD *)(a3 + 48) = (unsigned __int8)getBit32_SB(&v39, 6);
                *(_QWORD *)(a3 + 56) = (unsigned __int8)getBit32_SB(&v39, 6);
                *(_QWORD *)(a3 + 64) = (unsigned __int8)getBit32_SB(&v39, 6);
              }
              v31 = *(_QWORD *)(a3 + 48);
              v32 = *(_QWORD *)(a3 + 64);
              v33 = *(_QWORD *)(a3 + 40);
              v34 = *(_QWORD *)(a3 + 56);
              v35 = *a1;
              v36 = a1[1];
              if ( (((unsigned __int8)*a1 + (_BYTE)v32 + (_BYTE)v31) & 0xF)
                 + (unsigned __int64)(((_BYTE)v36 + (_BYTE)v34 + (_BYTE)v33) & 0xF) )
              {
                if ( v31 + v33 + (a1[1] & 0xF) + (*a1 & 0xF) || v35 <= v32 || v36 <= v34 )
                  goto LABEL_9;
                *a1 = v35 - v32;
                a1[1] = v36 - *(_QWORD *)(a3 + 56);
              }
              BYTE12(v39) = 0;
              LODWORD(v40) = 0;
              if ( !(unsigned int)ReadImagePlaneHeader((__int64)a1, a2, a3, (__int64)&v39) )
              {
                v7 = 0;
                *(_QWORD *)(a2 + 72) = (unsigned int)-DWORD2(v39);
                if ( *(_DWORD *)(a3 + 12) )
                  v37 = *(_BYTE *)(a2 + 48);
                else
                  v37 = 0;
                *(_BYTE *)(a2 + 48) = v37;
                *(_QWORD *)(a2 + 40) = *(_QWORD *)(a3 + 32);
                if ( (unsigned int)(*((_DWORD *)a1 + 5) - 8) <= 2 && *(_DWORD *)(a2 + 8) > 3u )
                  v7 = -1;
                goto LABEL_60;
              }
            }
          }
        }
      }
    }
LABEL_20:
    v7 = -106;
    goto LABEL_60;
  }
  return (unsigned int)-(v7 != 0);
}

```

## disassembly

```asm
0x1800106f0  mov     [rsp-38h+arg_18], rbx
0x1800106f5  push    rbp
0x1800106f6  push    rsi
0x1800106f7  push    rdi
0x1800106f8  push    r12
0x1800106fa  push    r13
0x1800106fc  push    r14
0x1800106fe  push    r15
0x180010700  mov     rbp, rsp
0x180010703  sub     rsp, 60h
0x180010707  mov     rax, cs:__security_cookie
0x18001070e  xor     rax, rsp
0x180010711  mov     [rbp+var_8], rax
0x180010715  mov     r15, [rdx+40h]
0x180010719  xor     eax, eax
0x18001071b  xorps   xmm0, xmm0
0x18001071e  mov     [rbp+var_20], rax
0x180010722  mov     rsi, r8
0x180010725  mov     qword ptr [rbp+Str], rax
0x180010729  mov     rdi, rdx
0x18001072c  mov     r14, rcx
0x18001072f  lea     r8d, [rax+8]
0x180010733  mov     rcx, r15
0x180010736  movups  [rbp+var_40], xmm0
0x18001073a  lea     rdx, [rbp+Str]
0x18001073e  movups  [rbp+var_30], xmm0
0x180010742  mov     rax, [r15+40h]
0x180010746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001074b  mov     ebx, eax
0x18001074d  test    eax, eax
0x18001074f  js      loc_180010C17
0x180010755  lea     rdx, SubStr; "WMPHOTO"
0x18001075c  mov     [rbp+Str+7], 0
0x180010760  lea     rcx, [rbp+Str]; Str
0x180010764  call    cs:__imp_strstr
0x18001076a  test    rax, rax
0x18001076d  jnz     short loc_180010777
0x18001076f  lea     ebx, [rax-6Ah]
0x180010772  jmp     loc_180010C17
0x180010777  mov     rdx, r15
0x18001077a  lea     rcx, [rbp+var_40]
0x18001077e  call    attach_SB
0x180010783  mov     ebx, eax
0x180010785  test    eax, eax
0x180010787  js      loc_180010C17
0x18001078d  mov     edx, 4
0x180010792  lea     rcx, [rbp+var_40]
0x180010796  call    getBit32_SB
0x18001079b  mov     ebx, 1
0x1800107a0  cmp     eax, ebx
0x1800107a2  jz      short loc_1800107AE
0x1800107a4  mov     ebx, 0FFFFFF95h
0x1800107a9  jmp     loc_180010C0E
0x1800107ae  mov     edx, ebx
0x1800107b0  mov     [rsi], rbx
0x1800107b3  lea     rcx, [rbp+var_40]
0x1800107b7  call    getBit32_SB
0x1800107bc  mov     r12d, 3
0x1800107c2  mov     [rdi+14h], eax
0x1800107c5  mov     edx, r12d
0x1800107c8  lea     rcx, [rbp+var_40]
0x1800107cc  call    getBit32_SB
0x1800107d1  mov     ecx, eax
0x1800107d3  cmp     eax, 2
0x1800107d6  jnb     short loc_1800107A4
0x1800107d8  xor     eax, eax
0x1800107da  mov     edx, ebx
0x1800107dc  cmp     ecx, ebx
0x1800107de  lea     rcx, [rbp+var_40]
0x1800107e2  setz    al
0x1800107e5  mov     [rdi+18h], eax
0x1800107e8  call    getBit32_SB
0x1800107ed  mov     edx, ebx
0x1800107ef  lea     rcx, [rbp+var_40]
0x1800107f3  mov     r15d, eax
0x1800107f6  call    getBit32_SB
0x1800107fb  mov     edx, r12d
0x1800107fe  mov     [rdi+20h], eax
0x180010801  lea     rcx, [rbp+var_40]
0x180010805  call    getBit32_SB
0x18001080a  mov     edx, ebx
0x18001080c  mov     [r14+74h], eax
0x180010810  lea     rcx, [rbp+var_40]
0x180010814  call    getBit32_SB
0x180010819  lea     edx, [r12-1]
0x18001081e  mov     [rsi+14h], eax
0x180010821  lea     rcx, [rbp+var_40]
0x180010825  call    getBit32_SB
0x18001082a  cmp     eax, r12d
0x18001082d  jnz     short loc_180010839
0x18001082f  mov     ebx, 0FFFFFF98h
0x180010834  jmp     loc_180010C0E
0x180010839  mov     edx, ebx
0x18001083b  mov     [rdi+10h], eax
0x18001083e  lea     rcx, [rbp+var_40]
0x180010842  call    getBit32_SB
0x180010847  mov     edx, ebx
0x180010849  lea     rcx, [rbp+var_40]
0x18001084d  mov     r13d, eax
0x180010850  call    getBit32_SB
0x180010855  mov     edx, ebx
0x180010857  mov     [rdi+0Ch], ebx
0x18001085a  lea     rcx, [rbp+var_40]
0x18001085e  call    getBit32_SB
0x180010863  mov     edx, ebx
0x180010865  mov     [rbp+var_18], eax
0x180010868  lea     rcx, [rbp+var_40]
0x18001086c  call    getBit32_SB
0x180010871  mov     [rsi+18h], eax
0x180010874  lea     rcx, [rbp+var_40]
0x180010878  cmp     dword ptr [rdi+18h], 0
0x18001087c  mov     edx, ebx
0x18001087e  jz      short loc_1800108A4
0x180010880  call    getBit32_SB
0x180010885  mov     edx, ebx
0x180010887  lea     rcx, [rbp+var_40]
0x18001088b  call    getBit32_SB
0x180010890  mov     edx, ebx
0x180010892  mov     [r14+2Ch], eax
0x180010896  lea     rcx, [rbp+var_40]
0x18001089a  xor     r12d, r12d
0x18001089d  call    getBit32_SB
0x1800108a2  jmp     short loc_1800108C4
0x1800108a4  call    getBit32_SB
0x1800108a9  mov     edx, 2
0x1800108ae  lea     rcx, [rbp+var_40]
0x1800108b2  mov     r12d, eax
0x1800108b5  call    getBit32_SB
0x1800108ba  xor     eax, eax
0x1800108bc  mov     dword ptr [r14+2Ch], 0
0x1800108c4  mov     edx, ebx
0x1800108c6  mov     [r14+30h], eax
0x1800108ca  lea     rcx, [rbp+var_40]
0x1800108ce  call    getBit32_SB
0x1800108d3  mov     [rsi+0Ch], eax
0x1800108d6  test    eax, eax
0x1800108d8  jnz     short loc_1800108DE
0x1800108da  mov     [r14+30h], eax
0x1800108de  mov     eax, [rsi+0Ch]
0x1800108e1  lea     rcx, [rbp+var_40]
0x1800108e5  mov     edx, 4
0x1800108ea  mov     [rdi+8068h], eax
0x1800108f0  call    getBit32_SB
0x1800108f5  mov     [r14+10h], eax
0x1800108f9  cmp     eax, 4
0x1800108fc  jz      short loc_18001090A
0x1800108fe  test    eax, eax
0x180010900  jle     short loc_18001090A
0x180010902  add     eax, 0FFFFFFFAh
0x180010905  cmp     eax, 2
0x180010908  ja      short loc_180010926
0x18001090a  mov     edx, 4
0x18001090f  lea     rcx, [rbp+var_40]
0x180010913  call    getBit32_SB
0x180010918  mov     [r14+14h], eax
0x18001091c  cmp     eax, 0Bh
0x18001091f  jl      short loc_180010930
0x180010921  cmp     eax, 0Fh
0x180010924  jz      short loc_180010935
0x180010926  mov     ebx, 0FFFFFF96h
0x18001092b  jmp     loc_180010C0E
0x180010930  cmp     eax, 0Fh
0x180010933  jnz     short loc_180010943
0x180010935  mov     dword ptr [r14+14h], 0
0x18001093d  mov     [rdi+805Ch], ebx
0x180010943  mov     eax, r13d
0x180010946  lea     rcx, [rbp+var_40]
0x18001094a  neg     eax
0x18001094c  sbb     ebx, ebx
0x18001094e  and     ebx, 0FFFFFFF0h
0x180010951  lea     edx, [rbx+20h]
0x180010954  call    getBit32_SB
0x180010959  inc     eax
0x18001095b  lea     edx, [rbx+20h]
0x18001095e  lea     rcx, [rbp+var_40]
0x180010962  mov     [r14], rax
0x180010965  call    getBit32_SB
0x18001096a  xor     edx, edx
0x18001096c  inc     eax
0x18001096e  mov     [r14+8], rax
0x180010972  mov     [rsi+40h], rdx
0x180010976  mov     [rsi+38h], rdx
0x18001097a  mov     [rsi+30h], rdx
0x18001097e  mov     [rsi+28h], rdx
0x180010982  cmp     [rbp+var_18], edx
0x180010985  jnz     short loc_1800109AE
0x180010987  mov     rcx, [r14]
0x18001098a  and     ecx, 0Fh
0x18001098d  jz      short loc_180010999
0x18001098f  lea     eax, [rdx+10h]
0x180010992  sub     rax, rcx
0x180010995  mov     [rsi+40h], rax
0x180010999  mov     rcx, [r14+8]
0x18001099d  and     ecx, 0Fh
0x1800109a0  jz      short loc_1800109AE
0x1800109a2  mov     eax, 10h
0x1800109a7  sub     rax, rcx
0x1800109aa  mov     [rsi+38h], rax
0x1800109ae  mov     [rdi+4054h], edx
0x1800109b4  mov     [rdi+50h], edx
0x1800109b7  test    r15d, r15d
0x1800109ba  jz      short loc_1800109EB
0x1800109bc  mov     r15d, 0Ch
0x1800109c2  lea     rcx, [rbp+var_40]
0x1800109c6  mov     edx, r15d
0x1800109c9  call    getBit32_SB
0x1800109ce  mov     edx, r15d
0x1800109d1  mov     [rdi+50h], eax
0x1800109d4  lea     rcx, [rbp+var_40]
0x1800109d8  mov     ebx, eax
0x1800109da  call    getBit32_SB
0x1800109df  mov     [rdi+4054h], eax
0x1800109e5  mov     ecx, ebx
0x1800109e7  xor     edx, edx
0x1800109e9  jmp     short loc_1800109F1
0x1800109eb  mov     ebx, edx
0x1800109ed  mov     eax, edx
0x1800109ef  mov     ecx, edx
0x1800109f1  cmp     [rsi+14h], edx
0x1800109f4  jnz     short loc_180010A08
0x1800109f6  cmp     dword ptr [rdi+20h], 1
0x1800109fa  jz      loc_180010926
0x180010a00  add     eax, ebx
0x180010a02  jnz     loc_180010926
0x180010a08  mov     [rdi+4058h], edx
0x180010a0e  mov     r15d, edx
0x180010a11  mov     [rdi+54h], edx
0x180010a14  test    ecx, ecx
0x180010a16  jz      short loc_180010A5D
0x180010a18  cmp     dword ptr [rbp+var_40+8], 4100h
0x180010a1f  jnb     loc_180010926
0x180010a25  mov     eax, r15d
0x180010a28  lea     rcx, [rbp+var_40]
0x180010a2c  mov     ebx, [rdi+rax*4+54h]
0x180010a30  mov     eax, r13d
0x180010a33  neg     eax
0x180010a35  sbb     edx, edx
0x180010a37  and     edx, 0FFFFFFF8h
0x180010a3a  add     edx, 10h
0x180010a3d  call    getBit32_SB
0x180010a42  inc     r15d
0x180010a45  lea     ecx, [rax+rbx]
0x180010a48  mov     [rdi+r15*4+54h], ecx
0x180010a4d  cmp     ecx, ebx
0x180010a4f  jbe     loc_180010926
0x180010a55  cmp     r15d, [rdi+50h]
0x180010a59  jb      short loc_180010A18
0x180010a5b  xor     edx, edx
0x180010a5d  mov     eax, [rdi+4054h]
0x180010a63  mov     r15d, edx
0x180010a66  test    eax, eax
0x180010a68  jz      short loc_180010ABA
0x180010a6a  cmp     dword ptr [rbp+var_40+8], 4100h
0x180010a71  jnb     loc_180010926
0x180010a77  mov     eax, r15d
0x180010a7a  lea     rcx, [rbp+var_40]
0x180010a7e  mov     ebx, [rdi+rax*4+4058h]
0x180010a85  mov     eax, r13d
0x180010a88  neg     eax
0x180010a8a  sbb     edx, edx
0x180010a8c  and     edx, 0FFFFFFF8h
0x180010a8f  add     edx, 10h
0x180010a92  call    getBit32_SB
0x180010a97  inc     r15d
0x180010a9a  lea     ecx, [rax+rbx]
0x180010a9d  mov     [rdi+r15*4+4058h], ecx
0x180010aa5  cmp     ecx, ebx
0x180010aa7  jbe     loc_180010926
0x180010aad  mov     eax, [rdi+4054h]
0x180010ab3  cmp     r15d, eax
0x180010ab6  jb      short loc_180010A6A
0x180010ab8  xor     edx, edx
0x180010aba  test    r12d, r12d
0x180010abd  jz      short loc_180010AF5
0x180010abf  mov     ebx, [rdi+50h]
0x180010ac2  mov     r15d, edx
0x180010ac5  inc     ebx
0x180010ac7  inc     eax
0x180010ac9  imul    ebx, eax
0x180010acc  test    ebx, ebx
0x180010ace  jz      short loc_180010AF5
0x180010ad0  cmp     dword ptr [rbp+var_40+8], 4100h
0x180010ad7  jnb     loc_180010926
0x180010add  mov     edx, 8
0x180010ae2  lea     rcx, [rbp+var_40]
0x180010ae6  call    getBit32_SB
0x180010aeb  inc     r15d
0x180010aee  cmp     r15d, ebx
0x180010af1  jb      short loc_180010AD0
0x180010af3  xor     edx, edx
0x180010af5  cmp     [rbp+var_18], edx
0x180010af8  jz      short loc_180010B47
0x180010afa  mov     ebx, 6
0x180010aff  lea     rcx, [rbp+var_40]
0x180010b03  mov     edx, ebx
0x180010b05  call    getBit32_SB
0x180010b0a  movzx   ecx, al
0x180010b0d  mov     edx, ebx
0x180010b0f  mov     [rsi+28h], rcx
0x180010b13  lea     rcx, [rbp+var_40]
  ... truncated ...
```
