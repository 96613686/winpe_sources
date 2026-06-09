# ValidateCallParams

- ea: `0x18001eafc`
- end: `0x18001f48d`
- name: `ValidateCallParams`
- size: `2449`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, UINT CodePage)`
- caller_count: `7`
- callee_count: `7`
- tags: ``

## callers

- `0x180008b50`
- `0x180009f50`
- `0x180010d40`
- `0x180012170`
- `0x1800166b0`
- `0x1800171f0`
- `0x18001fb28`

## callees

- `0x180001600`
- `0x180004474`
- `0x180007244`
- `0x18001ea48`
- `0x18001eafc`
- `0x18003dc84`
- `0x18003fb7c`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001f09d`
- `KERNEL32!HeapAlloc` at `0x18001f28e`
- `KERNEL32!HeapAlloc` at `0x18001f09d`
- `KERNEL32!HeapAlloc` at `0x18001f28e`
- `KERNEL32!MultiByteToWideChar` at `0x18001f41e`
- `KERNEL32!MultiByteToWideChar` at `0x18001f41e`

## pseudocode

```c
HRESULT __fastcall ValidateCallParams(_DWORD *Src, unsigned int **a2, unsigned int a3, unsigned int a4, UINT CodePage)
{
  int v8; // edi
  unsigned int v9; // r15d
  int v10; // r14d
  int v11; // edx
  HRESULT result; // eax
  size_t v13; // r12
  int v14; // r9d
  int v15; // r9d
  int v16; // r9d
  int v17; // eax
  int v18; // eax
  int v19; // r9d
  int v20; // r14d
  unsigned int v21; // r13d
  unsigned int *v22; // rax
  unsigned int *v23; // rdi
  __int64 v24; // rcx
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // eax
  unsigned int v38; // eax
  unsigned int v39; // eax
  int v40; // r9d
  int v41; // edx
  int v42; // ecx
  int v43; // r8d
  int v44; // eax
  __int64 v45; // r13
  unsigned int v46; // r14d
  unsigned int *v47; // rax
  unsigned int v48; // eax
  unsigned int v49; // eax
  unsigned int v50; // eax
  unsigned int v51; // eax
  unsigned int v52; // edx
  unsigned int v53; // eax
  unsigned int v54; // eax
  unsigned int v55; // eax
  unsigned int v56; // eax
  __int64 v57; // rbx
  unsigned int v58; // r14d
  __int64 v59; // r15
  int v60; // eax
  __int64 pulResult; // [rsp+30h] [rbp-61h] BYREF
  unsigned int v62; // [rsp+38h] [rbp-59h]
  unsigned int **v63; // [rsp+40h] [rbp-51h]
  _QWORD v64[4]; // [rsp+50h] [rbp-41h]
  __int128 v65; // [rsp+70h] [rbp-21h]
  _DWORD *v66; // [rsp+80h] [rbp-11h]
  __int64 v67; // [rsp+88h] [rbp-9h]
  char v68[24]; // [rsp+90h] [rbp-1h] BYREF

  v62 = a3;
  v63 = a2;
  strcpy(v68, "ValidateCallParams");
  HIDWORD(pulResult) = 180;
  v8 = -32;
  switch ( a3 )
  {
    case 0x10003u:
      v10 = 16760833;
      goto LABEL_12;
    case 0x10004u:
      v10 = 16744449;
LABEL_12:
      v11 = -128;
      v9 = 112;
      goto LABEL_13;
    case 0x20000u:
    case 0x20001u:
    case 0x20002u:
      v9 = 176;
      break;
    default:
      if ( a3 - 196608 > 1 )
        return -2147483576;
      v9 = 180;
      break;
  }
  v8 = -256;
  v10 = 16711681;
  v11 = -256;
LABEL_13:
  if ( a4 == 65539 || a4 == 65540 )
  {
    HIDWORD(pulResult) = 112;
  }
  else if ( a4 == 0x20000 || a4 == 131073 || a4 == 131074 )
  {
    HIDWORD(pulResult) = 176;
  }
  else if ( a4 - 196608 >= 2 )
  {
    return -2147483576;
  }
  v13 = (unsigned int)*Src;
  if ( (unsigned int)v13 < v9 )
  {
    TRACELogPrint(0x10002u, "%sbad dwTotalSize, x%x (minimum valid size=x%x)", v68, v13, v9);
    return -2147483571;
  }
  v14 = Src[1];
  if ( v14 )
  {
    if ( a3 < 0x20000 && a4 < 0x20000 )
    {
      if ( (v11 & v14) == 0 )
      {
        if ( ((v14 - 1) & v14) != 0 )
          TRACELogPrint(0x10002u, "%sbad dwBearerMode, x%x, allowed for 1.x apps/SPs", v68, v14);
        goto LABEL_33;
      }
LABEL_31:
      TRACELogPrint(0x10002u, "%sbad dwBearerMode, x%x", v68, v14);
      return -2147483626;
    }
    if ( ((v14 - 1) & v14) != 0 || (v11 & v14) != 0 )
      goto LABEL_31;
  }
  else
  {
    Src[1] = 1;
  }
LABEL_33:
  v15 = Src[4];
  if ( (v10 & v15) != 0 )
    goto LABEL_38;
  if ( a3 > 0x20001 )
    goto LABEL_40;
  if ( !v15 )
    goto LABEL_39;
  if ( ((v15 - 1) & v15) != 0 && (v15 & 2) == 0 )
  {
LABEL_38:
    if ( v15 )
    {
      TRACELogPrint(0x10002u, "%sbad dwMediaMode, x%x", v68, v15);
      return -2147483601;
    }
LABEL_39:
    Src[4] = 4;
  }
LABEL_40:
  if ( (v8 & Src[5]) != 0 )
  {
    TRACELogPrint(0x10002u, "%sbad dwCallParamFlags, x%x", v68);
    return -2147483623;
  }
  v16 = Src[6];
  if ( v16 == 1 )
  {
LABEL_47:
    v17 = 0;
    goto LABEL_48;
  }
  if ( v16 != 2 )
  {
    if ( v16 )
    {
      TRACELogPrint(0x10002u, "%sbad dwAddressMode, x%x", v68, v16);
      return -2147483630;
    }
    Src[6] = 1;
    goto LABEL_47;
  }
  v17 = 2;
LABEL_48:
  if ( guiAlignmentFaultEnabled )
    v18 = v17 != 0 ? 2 : 4;
  else
    v18 = 0;
  if ( IsBadSizeOffset(v13, v9, Src[12], Src[13], v18)
    || IsBadSizeOffset(v13, v9, Src[20], Src[21], guiAlignmentFaultEnabled != 0 ? 2 : 0)
    || IsBadSizeOffset(v13, v9, Src[22], Src[23], 0)
    || IsBadSizeOffset(v13, v9, Src[24], Src[25], 0)
    || IsBadSizeOffset(v13, v9, Src[26], Src[27], 0) )
  {
    return -2147483623;
  }
  if ( IsBadSizeOffset(v13, v9, Src[14], Src[15], guiAlignmentFaultEnabled != 0 ? 2 : 0) )
  {
    if ( a3 >= 0x20000 )
      return -2147483623;
    *((_QWORD *)Src + 7) = 0;
  }
  if ( IsBadSizeOffset(v13, v9, Src[16], Src[17], guiAlignmentFaultEnabled != 0 ? 2 : 0) )
  {
    if ( a3 >= 0x20000 )
      return -2147483623;
    *((_QWORD *)Src + 8) = 0;
  }
  if ( IsBadSizeOffset(v13, v9, Src[18], Src[19], guiAlignmentFaultEnabled != 0 ? 2 : 0) )
  {
    if ( a3 >= 0x20000 )
      return -2147483623;
    *((_QWORD *)Src + 9) = 0;
  }
  if ( a3 > 0x10004 )
  {
    if ( (Src[28] & 0xFFFF0000) != 0 )
    {
      TRACELogPrint(0x10002u, "%sbad dwPredictiveAutoTransferStates, x%x", v68);
      return -2147483623;
    }
    if ( IsBadSizeOffset(v13, v9, Src[29], Src[30], guiAlignmentFaultEnabled != 0 ? 2 : 0)
      || IsBadSizeOffset(v13, v9, Src[31], Src[32], guiAlignmentFaultEnabled != 0 ? 4 : 0)
      || IsBadSizeOffset(v13, v9, Src[33], Src[34], guiAlignmentFaultEnabled != 0 ? 4 : 0)
      || IsBadSizeOffset(v13, v9, Src[35], Src[36], 0)
      || IsBadSizeOffset(v13, v9, Src[37], Src[38], 0)
      || IsBadSizeOffset(v13, v9, Src[39], Src[40], 0)
      || IsBadSizeOffset(v13, v9, Src[42], Src[43], 0) )
    {
      return -2147483623;
    }
    if ( a3 >= 0x30000 )
    {
      v19 = Src[44];
      if ( v19 )
      {
        if ( (v19 & 0xFFFFFFE0) != 0 || ((v19 - 1) & v19) != 0 )
        {
          TRACELogPrint(0x10002u, "%sbad dwAddressType, x%x", v68);
          return -2147483623;
        }
      }
    }
  }
  if ( CodePage != -1 )
  {
    v40 = Src[18];
    v41 = Src[14];
    v42 = Src[12];
    v43 = Src[16];
    LODWORD(pulResult) = 0;
    v44 = DWordAdd4(v42, v41, v43, v40, (__int64)&pulResult);
    if ( a3 > 0x10004 )
    {
      if ( v44 < 0 )
        return -2147483580;
      v44 = DWordAdd4(pulResult, Src[29], Src[35], Src[42], (__int64)&pulResult);
    }
    if ( v44 < 0 )
      return -2147483580;
    v45 = (unsigned int)pulResult;
    v46 = HIDWORD(pulResult) - v9;
    if ( pulResult != __PAIR64__(v9, 0) )
    {
      LODWORD(pulResult) = 0;
      if ( (unsigned __int64)(2 * v45) <= 0xFFFFFFFF
        && (int)DWordAdd4(v13, v46, 2 * (int)v45, 3, (__int64)&pulResult) >= 0 )
      {
        v47 = (unsigned int *)HeapAlloc(ghTapisrvHeap, 8u, (unsigned int)pulResult);
        v23 = v47;
        if ( v47 )
        {
          if ( v46 )
          {
            memcpy_0(v47, Src, v9);
            memcpy_0((char *)v23 + HIDWORD(pulResult), &Src[v9 / 4], (unsigned int)v13 - v9);
            v48 = v23[21];
            if ( v48 )
              v23[21] = v46 + v48;
            v49 = v23[23];
            if ( v49 )
              v23[23] = v46 + v49;
            v50 = v23[25];
            if ( v50 )
              v23[25] = v46 + v50;
            v51 = v23[27];
            if ( v51 )
              v23[27] = v46 + v51;
            v52 = v62;
            if ( v62 >= 0x20000 )
            {
              v53 = v23[32];
              if ( v53 )
                v23[32] = v46 + v53;
              v54 = v23[34];
              if ( v54 )
                v23[34] = v46 + v54;
              v55 = v23[38];
              if ( v55 )
                v23[38] = v46 + v55;
              v56 = v23[40];
              if ( v56 )
                v23[40] = v46 + v56;
            }
          }
          else
          {
            memcpy_0(v47, Src, v13);
            v52 = v62;
          }
          *v23 = v13 + v46 + 2 * v45 + 3;
          if ( (_DWORD)v45 )
          {
            v64[1] = v23 + 14;
            v64[2] = v23 + 16;
            v64[3] = v23 + 18;
            v64[0] = v23 + 12;
            if ( v52 <= 0x10004 )
            {
              v66 = 0;
              v65 = 0;
            }
            else
            {
              *(_QWORD *)&v65 = v23 + 29;
              *((_QWORD *)&v65 + 1) = v23 + 35;
              v66 = v23 + 42;
            }
            v67 = 0;
            v57 = 0;
            v58 = (v13 + v46 + 3) & 0xFFFFFFFC;
            if ( v23 != (unsigned int *)-48LL )
            {
              do
              {
                v59 = v64[v57];
                if ( *(_DWORD *)v59 )
                {
                  MultiByteToWideChar(
                    CodePage,
                    1u,
                    (LPCCH)Src + *(unsigned int *)(v59 + 4),
                    *(_DWORD *)v59,
                    (LPWSTR)((char *)v23 + v58),
                    *(_DWORD *)v59);
                  v60 = 2 * *(_DWORD *)v59;
                  *(_DWORD *)(v59 + 4) = v58;
                  *(_DWORD *)v59 = v60;
                  v58 += v60;
                }
                v57 = (unsigned int)(v57 + 1);
              }
              while ( v64[v57] );
            }
          }
          goto LABEL_156;
        }
      }
      return -2147483580;
    }
LABEL_120:
    v23 = Src;
LABEL_156:
    *v63 = v23;
    return 0;
  }
  if ( v9 >= HIDWORD(pulResult) )
    goto LABEL_120;
  LODWORD(pulResult) = 0;
  result = ULongSub(HIDWORD(pulResult), v9, (ULONG *)&pulResult);
  if ( result >= 0 )
  {
    v20 = pulResult;
    v21 = pulResult + v13;
    if ( (int)pulResult + (int)v13 >= (unsigned int)v13 )
    {
      v22 = (unsigned int *)HeapAlloc(ghTapisrvHeap, 8u, v21);
      v23 = v22;
      if ( v22 )
      {
        memcpy_0(v22, Src, v9);
        v24 = HIDWORD(pulResult);
        *v23 = v21;
        memcpy_0((char *)v23 + v24, &Src[v9 / 4], (unsigned int)v13 - v9);
        v25 = v23[13];
        if ( v25 )
          v23[13] = v20 + v25;
        v26 = v23[15];
        if ( v26 )
          v23[15] = v20 + v26;
        v27 = v23[17];
        if ( v27 )
          v23[17] = v20 + v27;
        v28 = v23[19];
        if ( v28 )
          v23[19] = v20 + v28;
        v29 = v23[21];
        if ( v29 )
          v23[21] = v20 + v29;
        v30 = v23[23];
        if ( v30 )
          v23[23] = v20 + v30;
        v31 = v23[25];
        if ( v31 )
          v23[25] = v20 + v31;
        v32 = v23[27];
        if ( v32 )
          v23[27] = v20 + v32;
        if ( v62 >= 0x20000 )
        {
          v33 = v23[30];
          if ( v33 )
            v23[30] = v20 + v33;
          v34 = v23[32];
          if ( v34 )
            v23[32] = v20 + v34;
          v35 = v23[34];
          if ( v35 )
            v23[34] = v20 + v35;
          v36 = v23[36];
          if ( v36 )
            v23[36] = v20 + v36;
          v37 = v23[38];
          if ( v37 )
            v23[38] = v20 + v37;
          v38 = v23[40];
          if ( v38 )
            v23[40] = v20 + v38;
          v39 = v23[43];
          if ( v39 )
            v23[43] = v20 + v39;
        }
        goto LABEL_156;
      }
    }
    return -2147483580;
  }
  if ( (result & 0x1FFF0000) == 0x70000 )
    return (unsigned __int16)result;
  return result;
}

```

## disassembly

```asm
0x18001eafc  mov     [rsp-8+arg_10], rbx
0x18001eb01  push    rbp
0x18001eb02  push    rsi
0x18001eb03  push    rdi
0x18001eb04  push    r12
0x18001eb06  push    r13
0x18001eb08  push    r14
0x18001eb0a  push    r15
0x18001eb0c  lea     rbp, [rsp-1Fh]
0x18001eb11  sub     rsp, 0B0h
0x18001eb18  mov     rax, cs:__security_cookie
0x18001eb1f  xor     rax, rsp
0x18001eb22  mov     [rbp+4Fh+var_38], rax
0x18001eb26  mov     eax, dword ptr cs:aValidatecallpa+0Fh; "ams"
0x18001eb2c  mov     r10d, r9d
0x18001eb2f  movups  xmm0, xmmword ptr cs:aValidatecallpa; "ValidateCallParams"
0x18001eb36  mov     r9d, 0FFFCh
0x18001eb3c  mov     [rbp+4Fh+var_A8], r8d
0x18001eb40  mov     rsi, rcx
0x18001eb43  mov     [rbp+4Fh+var_A0], rdx
0x18001eb47  mov     ecx, 0B4h
0x18001eb4c  mov     r13d, r8d
0x18001eb4f  movups  xmmword ptr [rbp+4Fh+var_50], xmm0
0x18001eb53  mov     dword ptr [rbp+4Fh+var_50+0Fh], eax
0x18001eb56  lea     r12d, [r9+7]
0x18001eb5a  mov     eax, r8d
0x18001eb5d  mov     [rbp+4Fh+ulMinuend], ecx
0x18001eb60  lea     r11d, [r9+2]
0x18001eb64  mov     edi, 0FFFFFFE0h
0x18001eb69  lea     ebx, [rcx-4]
0x18001eb6c  lea     r8d, [rcx-44h]
0x18001eb70  sub     eax, r12d
0x18001eb73  jz      short loc_18001EBB2
0x18001eb75  sub     eax, 1
0x18001eb78  jz      short loc_18001EBAA
0x18001eb7a  sub     eax, r9d
0x18001eb7d  jz      short loc_18001EB98
0x18001eb7f  sub     eax, 1
0x18001eb82  jz      short loc_18001EB98
0x18001eb84  sub     eax, 1
0x18001eb87  jz      short loc_18001EB98
0x18001eb89  sub     eax, r11d
0x18001eb8c  jz      short loc_18001EB93
0x18001eb8e  cmp     eax, 1
0x18001eb91  jnz     short loc_18001EBE6
0x18001eb93  mov     r15d, ecx
0x18001eb96  jmp     short loc_18001EB9B
0x18001eb98  mov     r15d, ebx
0x18001eb9b  mov     edi, 0FFFFFF00h
0x18001eba0  mov     r14d, 0FF0001h
0x18001eba6  mov     edx, edi
0x18001eba8  jmp     short loc_18001EBC0
0x18001ebaa  mov     r14d, 0FF8001h
0x18001ebb0  jmp     short loc_18001EBB8
0x18001ebb2  mov     r14d, 0FFC001h
0x18001ebb8  mov     edx, 0FFFFFF80h
0x18001ebbd  mov     r15d, r8d
0x18001ebc0  mov     eax, r10d
0x18001ebc3  sub     eax, r12d
0x18001ebc6  jz      short loc_18001EBF5
0x18001ebc8  sub     eax, 1
0x18001ebcb  jz      short loc_18001EBF5
0x18001ebcd  sub     eax, r9d
0x18001ebd0  jz      short loc_18001EBF0
0x18001ebd2  sub     eax, 1
0x18001ebd5  jz      short loc_18001EBF0
0x18001ebd7  sub     eax, 1
0x18001ebda  jz      short loc_18001EBF0
0x18001ebdc  sub     eax, r11d
0x18001ebdf  jz      short loc_18001EBF9
0x18001ebe1  cmp     eax, 1
0x18001ebe4  jz      short loc_18001EBF9
0x18001ebe6  mov     eax, 80000048h
0x18001ebeb  jmp     loc_18001F466
0x18001ebf0  mov     [rbp+4Fh+ulMinuend], ebx
0x18001ebf3  jmp     short loc_18001EBF9
0x18001ebf5  mov     [rbp+4Fh+ulMinuend], r8d
0x18001ebf9  mov     r12d, [rsi]
0x18001ebfc  cmp     r12d, r15d
0x18001ebff  jnb     short loc_18001EC28
0x18001ec01  mov     r9d, r12d
0x18001ec04  mov     dword ptr [rsp+0E0h+lpWideCharStr], r15d
0x18001ec09  lea     r8, [rbp+4Fh+var_50]
0x18001ec0d  mov     ecx, 10002h
0x18001ec12  lea     rdx, aSbadDwtotalsiz; "%sbad dwTotalSize, x%x (minimum valid s"...
0x18001ec19  call    TRACELogPrint
0x18001ec1e  mov     eax, 8000004Dh
0x18001ec23  jmp     loc_18001F466
0x18001ec28  mov     r9d, [rsi+4]
0x18001ec2c  mov     ebx, 10002h
0x18001ec31  mov     eax, 20000h
0x18001ec36  test    r9d, r9d
0x18001ec39  jz      short loc_18001EC97
0x18001ec3b  cmp     r13d, eax
0x18001ec3e  jnb     short loc_18001EC67
0x18001ec40  cmp     r10d, eax
0x18001ec43  jnb     short loc_18001EC67
0x18001ec45  test    r9d, edx
0x18001ec48  jnz     short loc_18001EC7B
0x18001ec4a  lea     eax, [r9-1]
0x18001ec4e  test    r9d, eax
0x18001ec51  jz      short loc_18001EC9E
0x18001ec53  lea     r8, [rbp+4Fh+var_50]
0x18001ec57  mov     ecx, ebx
0x18001ec59  lea     rdx, aSbadDwbearermo; "%sbad dwBearerMode, x%x, allowed for 1."...
0x18001ec60  call    TRACELogPrint
0x18001ec65  jmp     short loc_18001EC9E
0x18001ec67  lea     eax, [r9-1]
0x18001ec6b  test    r9d, eax
0x18001ec6e  setz    cl
0x18001ec71  test    r9d, edx
0x18001ec74  setz    al
0x18001ec77  test    al, cl
0x18001ec79  jnz     short loc_18001EC9E
0x18001ec7b  lea     r8, [rbp+4Fh+var_50]
0x18001ec7f  mov     ecx, ebx
0x18001ec81  lea     rdx, aSbadDwbearermo_0; "%sbad dwBearerMode, x%x"
0x18001ec88  call    TRACELogPrint
0x18001ec8d  mov     eax, 80000016h
0x18001ec92  jmp     loc_18001F466
0x18001ec97  mov     dword ptr [rsi+4], 1
0x18001ec9e  mov     r9d, [rsi+10h]
0x18001eca2  test    r9d, r14d
0x18001eca5  jnz     short loc_18001ECC9
0x18001eca7  xor     r14d, r14d
0x18001ecaa  cmp     r13d, 20001h
0x18001ecb1  ja      short loc_18001ECDC
0x18001ecb3  test    r9d, r9d
0x18001ecb6  jz      short loc_18001ECD5
0x18001ecb8  lea     eax, [r9-1]
0x18001ecbc  test    r9d, eax
0x18001ecbf  jz      short loc_18001ECDC
0x18001ecc1  test    r9b, 2
0x18001ecc5  jnz     short loc_18001ECDC
0x18001ecc7  jmp     short loc_18001ECCC
0x18001ecc9  xor     r14d, r14d
0x18001eccc  test    r9d, r9d
0x18001eccf  jnz     loc_18001F44F
0x18001ecd5  mov     dword ptr [rsi+10h], 4
0x18001ecdc  mov     r9d, [rsi+14h]
0x18001ece0  test    r9d, edi
0x18001ece3  jz      short loc_18001ED01
0x18001ece5  lea     rdx, aSbadDwcallpara; "%sbad dwCallParamFlags, x%x"
0x18001ecec  lea     r8, [rbp+4Fh+var_50]
0x18001ecf0  mov     ecx, ebx
0x18001ecf2  call    TRACELogPrint
0x18001ecf7  mov     eax, 80000019h
0x18001ecfc  jmp     loc_18001F466
0x18001ed01  mov     r9d, [rsi+18h]
0x18001ed05  cmp     r9d, 1
0x18001ed09  jz      short loc_18001ED1D
0x18001ed0b  cmp     r9d, 2
0x18001ed0f  jz      short loc_18001ED4A
0x18001ed11  test    r9d, r9d
0x18001ed14  jnz     short loc_18001ED2E
0x18001ed16  mov     dword ptr [rsi+18h], 1
0x18001ed1d  mov     eax, r14d
0x18001ed20  cmp     cs:guiAlignmentFaultEnabled, r14d
0x18001ed27  jnz     short loc_18001ED51
0x18001ed29  mov     eax, r14d
0x18001ed2c  jmp     short loc_18001ED5B
0x18001ed2e  lea     r8, [rbp+4Fh+var_50]
0x18001ed32  mov     ecx, ebx
0x18001ed34  lea     rdx, aSbadDwaddressm; "%sbad dwAddressMode, x%x"
0x18001ed3b  call    TRACELogPrint
0x18001ed40  mov     eax, 80000012h
0x18001ed45  jmp     loc_18001F466
0x18001ed4a  mov     eax, 2
0x18001ed4f  jmp     short loc_18001ED20
0x18001ed51  neg     eax
0x18001ed53  sbb     eax, eax
0x18001ed55  and     eax, 0FFFFFFFEh
0x18001ed58  add     eax, 4
0x18001ed5b  mov     r9d, [rsi+34h]
0x18001ed5f  mov     edx, r15d
0x18001ed62  mov     r8d, [rsi+30h]
0x18001ed66  mov     ecx, r12d
0x18001ed69  mov     dword ptr [rsp+0E0h+lpWideCharStr], eax
0x18001ed6d  call    IsBadSizeOffset
0x18001ed72  test    eax, eax
0x18001ed74  jnz     short loc_18001ECF7
0x18001ed76  mov     eax, cs:guiAlignmentFaultEnabled
0x18001ed7c  mov     edx, r15d
0x18001ed7f  mov     r9d, [rsi+54h]
0x18001ed83  neg     eax
0x18001ed85  mov     r8d, [rsi+50h]
0x18001ed89  sbb     ecx, ecx
0x18001ed8b  and     ecx, 2
0x18001ed8e  mov     dword ptr [rsp+0E0h+lpWideCharStr], ecx
0x18001ed92  mov     ecx, r12d
0x18001ed95  call    IsBadSizeOffset
0x18001ed9a  test    eax, eax
0x18001ed9c  jnz     loc_18001ECF7
0x18001eda2  mov     r9d, [rsi+5Ch]
0x18001eda6  mov     edx, r15d
0x18001eda9  mov     r8d, [rsi+58h]
0x18001edad  mov     ecx, r12d
0x18001edb0  mov     dword ptr [rsp+0E0h+lpWideCharStr], r14d
0x18001edb5  call    IsBadSizeOffset
0x18001edba  test    eax, eax
0x18001edbc  jnz     loc_18001ECF7
0x18001edc2  mov     r9d, [rsi+64h]
0x18001edc6  mov     edx, r15d
0x18001edc9  mov     r8d, [rsi+60h]
0x18001edcd  mov     ecx, r12d
0x18001edd0  mov     dword ptr [rsp+0E0h+lpWideCharStr], r14d
0x18001edd5  call    IsBadSizeOffset
0x18001edda  test    eax, eax
0x18001eddc  jnz     loc_18001ECF7
0x18001ede2  mov     r9d, [rsi+6Ch]
0x18001ede6  mov     edx, r15d
0x18001ede9  mov     r8d, [rsi+68h]
0x18001eded  mov     ecx, r12d
0x18001edf0  mov     dword ptr [rsp+0E0h+lpWideCharStr], r14d
0x18001edf5  call    IsBadSizeOffset
0x18001edfa  test    eax, eax
0x18001edfc  jnz     loc_18001ECF7
0x18001ee02  mov     eax, cs:guiAlignmentFaultEnabled
0x18001ee08  mov     edx, r15d
0x18001ee0b  mov     r9d, [rsi+3Ch]
0x18001ee0f  neg     eax
0x18001ee11  mov     r8d, [rsi+38h]
0x18001ee15  sbb     ecx, ecx
0x18001ee17  and     ecx, 2
0x18001ee1a  mov     dword ptr [rsp+0E0h+lpWideCharStr], ecx
0x18001ee1e  mov     ecx, r12d
0x18001ee21  call    IsBadSizeOffset
0x18001ee26  mov     edi, 20000h
0x18001ee2b  test    eax, eax
0x18001ee2d  jz      short loc_18001EE40
0x18001ee2f  cmp     r13d, edi
0x18001ee32  jnb     loc_18001ECF7
0x18001ee38  mov     qword ptr [rsi+38h], 0
0x18001ee40  mov     eax, cs:guiAlignmentFaultEnabled
0x18001ee46  mov     edx, r15d
0x18001ee49  mov     r9d, [rsi+44h]
0x18001ee4d  neg     eax
0x18001ee4f  mov     r8d, [rsi+40h]
0x18001ee53  sbb     ecx, ecx
0x18001ee55  and     ecx, 2
0x18001ee58  mov     dword ptr [rsp+0E0h+lpWideCharStr], ecx
0x18001ee5c  mov     ecx, r12d
0x18001ee5f  call    IsBadSizeOffset
0x18001ee64  test    eax, eax
0x18001ee66  jz      short loc_18001EE79
0x18001ee68  cmp     r13d, edi
0x18001ee6b  jnb     loc_18001ECF7
0x18001ee71  mov     qword ptr [rsi+40h], 0
0x18001ee79  mov     eax, cs:guiAlignmentFaultEnabled
0x18001ee7f  mov     edx, r15d
0x18001ee82  mov     r9d, [rsi+4Ch]
0x18001ee86  neg     eax
0x18001ee88  mov     r8d, [rsi+48h]
0x18001ee8c  sbb     ecx, ecx
0x18001ee8e  and     ecx, 2
0x18001ee91  mov     dword ptr [rsp+0E0h+lpWideCharStr], ecx
0x18001ee95  mov     ecx, r12d
0x18001ee98  call    IsBadSizeOffset
0x18001ee9d  test    eax, eax
0x18001ee9f  jz      short loc_18001EEB2
0x18001eea1  cmp     r13d, edi
0x18001eea4  jnb     loc_18001ECF7
0x18001eeaa  mov     qword ptr [rsi+48h], 0
0x18001eeb2  mov     edi, 10004h
0x18001eeb7  cmp     r13d, edi
0x18001eeba  jbe     loc_18001F031
0x18001eec0  mov     r9d, [rsi+70h]
0x18001eec4  test    r9d, 0FFFF0000h
0x18001eecb  jz      short loc_18001EED9
0x18001eecd  lea     rdx, aSbadDwpredicti; "%sbad dwPredictiveAutoTransferStates, x"...
0x18001eed4  jmp     loc_18001ECEC
0x18001eed9  mov     eax, cs:guiAlignmentFaultEnabled
0x18001eedf  mov     edx, r15d
0x18001eee2  mov     r9d, [rsi+78h]
0x18001eee6  neg     eax
0x18001eee8  mov     r8d, [rsi+74h]
0x18001eeec  sbb     ecx, ecx
0x18001eeee  and     ecx, 2
0x18001eef1  mov     dword ptr [rsp+0E0h+lpWideCharStr], ecx
0x18001eef5  mov     ecx, r12d
0x18001eef8  call    IsBadSizeOffset
0x18001eefd  test    eax, eax
0x18001eeff  jnz     loc_18001ECF7
0x18001ef05  mov     eax, cs:guiAlignmentFaultEnabled
0x18001ef0b  mov     edx, r15d
0x18001ef0e  mov     r9d, [rsi+80h]
0x18001ef15  neg     eax
0x18001ef17  mov     r8d, [rsi+7Ch]
0x18001ef1b  sbb     ecx, ecx
0x18001ef1d  and     ecx, 4
0x18001ef20  mov     dword ptr [rsp+0E0h+lpWideCharStr], ecx
0x18001ef24  mov     ecx, r12d
0x18001ef27  call    IsBadSizeOffset
0x18001ef2c  test    eax, eax
0x18001ef2e  jnz     loc_18001ECF7
0x18001ef34  mov     eax, cs:guiAlignmentFaultEnabled
0x18001ef3a  mov     edx, r15d
0x18001ef3d  mov     r9d, [rsi+88h]
0x18001ef44  neg     eax
0x18001ef46  mov     r8d, [rsi+84h]
  ... truncated ...
```
