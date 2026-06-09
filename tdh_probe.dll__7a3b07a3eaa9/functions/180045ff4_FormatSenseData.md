# FormatSenseData

- ea: `0x180045ff4`
- end: `0x180046847`
- name: `FormatSenseData`
- size: `2131`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180043390`

## callees

- `0x180045ff4`
- `0x180046ecc`

## string_xrefs

- `0x180046450`: `Command-specific information`
- `0x1800465fe`: `Field replaceable unit code`

## pseudocode

```c
void __fastcall FormatSenseData(__m128i *a1, __int64 a2, wchar_t *a3, unsigned int a4)
{
  __int16 v4; // r14
  __m128i v5; // xmm6
  unsigned int v6; // ebx
  int v7; // eax
  unsigned __int8 v8; // bl
  int v9; // r10d
  __int64 v10; // rcx
  int v11; // eax
  unsigned __int8 v12; // cl
  char v13; // si
  wchar_t *v14; // r10
  char v15; // bl
  wchar_t *v16; // rcx
  const char *v17; // rax
  int v18; // ecx
  int v19; // eax
  __int64 v20; // [rsp+38h] [rbp-31h]
  __int64 v21; // [rsp+38h] [rbp-31h]
  __int64 v22; // [rsp+38h] [rbp-31h]
  __int64 v23; // [rsp+38h] [rbp-31h]
  __int64 v24; // [rsp+38h] [rbp-31h]
  __int64 v25; // [rsp+38h] [rbp-31h]
  __int64 v26; // [rsp+38h] [rbp-31h]
  __int64 v27; // [rsp+38h] [rbp-31h]
  __int64 v28; // [rsp+38h] [rbp-31h]
  __int64 v29; // [rsp+38h] [rbp-31h]
  __int64 v30; // [rsp+38h] [rbp-31h]
  __int64 v31; // [rsp+38h] [rbp-31h]
  __int64 v32; // [rsp+38h] [rbp-31h]
  __int64 v33; // [rsp+38h] [rbp-31h]
  __int64 v34; // [rsp+38h] [rbp-31h]
  __int64 v35; // [rsp+38h] [rbp-31h]
  __int64 v36; // [rsp+40h] [rbp-29h]
  __int64 v37; // [rsp+40h] [rbp-29h]
  __int64 v38; // [rsp+48h] [rbp-21h]
  unsigned __int64 v39; // [rsp+50h] [rbp-19h] BYREF
  STRSAFE_LPWSTR pszDest[3]; // [rsp+58h] [rbp-11h] BYREF
  __int16 v41; // [rsp+70h] [rbp+7h]

  if ( !a1 )
    return;
  pszDest[0] = a3;
  v39 = 0;
  if ( !a3 )
    return;
  if ( !a4 )
    return;
  v4 = a1[1].m128i_i16[0];
  v5 = *a1;
  a3[a4 - 1] = 0;
  v41 = v4;
  if ( (unsigned int)StringCchPrintfExW(a3, a4, pszDest, &v39, 0, L"%hs", "\nREQUEST SENSE DATA...") )
    return;
  v6 = (unsigned __int8)_mm_cvtsi128_si32(v5);
  if ( (v6 & 0x7F) == 0x70 )
  {
    v7 = StringCchPrintfExW(pszDest[0], v39, pszDest, &v39, 0, L"\n%33hs: 0x%X current errors", "Response code", 112);
  }
  else if ( (v6 & 0x7F) == 0x71 )
  {
    v7 = StringCchPrintfExW(pszDest[0], v39, pszDest, &v39, 0, L"\n%33hs: 0x%X deferred errors", "Response code", 113);
  }
  else
  {
    v7 = (v6 & 0x7F) == 0x7F
       ? StringCchPrintfExW(
           pszDest[0],
           v39,
           pszDest,
           &v39,
           0,
           L"\n%33hs: 0x%X vendor specific sense data format",
           "Response code",
           127)
       : StringCchPrintfExW(
           pszDest[0],
           v39,
           pszDest,
           &v39,
           0,
           L"\n%33hs: 0x%X unexpected response code",
           "Response code",
           v6 & 0x7F);
  }
  if ( v7 )
    return;
  LODWORD(v20) = v6 >> 7;
  if ( (unsigned int)StringCchPrintfExW(pszDest[0], v39, pszDest, &v39, 0, L"\n%33hs: 0x%X", "Valid", v20) )
    return;
  LODWORD(v21) = (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v5, 1));
  if ( (unsigned int)StringCchPrintfExW(pszDest[0], v39, pszDest, &v39, 0, L"\n%33hs: 0x%X", "Segment number", v21) )
    return;
  v8 = _mm_cvtsi128_si32(_mm_srli_si128(v5, 2));
  LODWORD(v22) = v8 & 0xF;
  if ( (unsigned int)StringCchPrintfExW(
                       pszDest[0],
                       v39,
                       pszDest,
                       &v39,
                       0,
                       L"\n%33hs: 0x%X %s",
                       "Sense key",
                       v22,
                       off_180050530[v8 & 0xF]) )
    return;
  LODWORD(v23) = (v8 >> 5) & 1;
  if ( (unsigned int)StringCchPrintfExW(pszDest[0], v39, pszDest, &v39, 0, L"\n%33hs: 0x%X", "ILI", v23) )
    return;
  LODWORD(v24) = (v8 >> 6) & 1;
  if ( (unsigned int)StringCchPrintfExW(pszDest[0], v39, pszDest, &v39, 0, L"\n%33hs: 0x%X", "EOM", v24) )
    return;
  LODWORD(v25) = v8 >> 7;
  if ( (unsigned int)StringCchPrintfExW(pszDest[0], v39, pszDest, &v39, 0, L"\n%33hs: 0x%X", "FileMark", v25) )
    return;
  LODWORD(v26) = v8 >> 7;
  if ( (unsigned int)StringCchPrintfExW(pszDest[0], v39, pszDest, &v39, 0, L"\n%33hs: 0x%X", "FileMark", v26) )
    return;
  LODWORD(v27) = (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v5, 6))
               | (((unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v5, 5))
                 | (((unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v5, 4))
                   | ((unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v5, 3)) << 8)) << 8)) << 8);
  if ( (unsigned int)StringCchPrintfExW(pszDest[0], v39, pszDest, &v39, 0, L"\n%33hs: 0x%08X", "Information", v27) )
    return;
  LODWORD(v28) = (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v5, 7));
  if ( (unsigned int)StringCchPrintfExW(
                       pszDest[0],
                       v39,
                       pszDest,
                       &v39,
                       0,
                       L"\n%33hs: 0x%02X",
                       "Additional sense length",
                       v28) )
    return;
  LODWORD(v29) = (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v5, 11))
               | (((unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v5, 10))
                 | (((unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v5, 9))
                   | ((unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v5, 8)) << 8)) << 8)) << 8);
  if ( (unsigned int)StringCchPrintfExW(
                       pszDest[0],
                       v39,
                       pszDest,
                       &v39,
                       0,
                       L"\n%33hs: 0x%08X",
                       "Command-specific information",
                       v29) )
    return;
  v9 = _mm_cvtsi128_si32(_mm_srli_si128(v5, 12));
  if ( (unsigned __int8)v9 >= 0x74u )
  {
    LODWORD(v36) = (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v5, 13));
    LODWORD(v30) = (unsigned __int8)v9;
    goto LABEL_32;
  }
  if ( (unsigned __int8)(v9 - 64) > 0x30u || (v10 = 0x1000020002001LL, !_bittest64(&v10, (unsigned int)(v9 - 64))) )
  {
    v12 = _mm_cvtsi128_si32(_mm_srli_si128(v5, 13));
    if ( v12 < 0x19u && v12 < *((_BYTE *)&unk_1800506C0 + 208 * (unsigned __int8)v9) )
    {
      LODWORD(v36) = v12;
      LODWORD(v30) = (unsigned __int8)v9;
      v11 = StringCchPrintfExW(
              pszDest[0],
              v39,
              pszDest,
              &v39,
              0,
              L"\n%33hs: (%02X/%02X) %hs",
              "ASC/ASQ",
              v30,
              v36,
              (&off_1800506C8[26 * (unsigned __int8)v9])[v12]);
      goto LABEL_33;
    }
    LODWORD(v36) = v12;
    LODWORD(v30) = (unsigned __int8)v9;
LABEL_32:
    v11 = StringCchPrintfExW(pszDest[0], v39, pszDest, &v39, 0, L"\n%33hs: (%02X/%02X) no mapping", "ASC/ASQ", v30, v36);
    goto LABEL_33;
  }
  LODWORD(v36) = (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v5, 13));
  LODWORD(v30) = (unsigned __int8)v9;
  v11 = StringCchPrintfExW(
          pszDest[0],
          v39,
          pszDest,
          &v39,
          0,
          L"\n%33hs: (%02X/%02X) %hs",
          "ASC/ASQ",
          v30,
          v36,
          off_1800506C8[26 * (unsigned __int8)v9]);
LABEL_33:
  if ( !v11 )
  {
    LODWORD(v31) = (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v5, 14));
    if ( !(unsigned int)StringCchPrintfExW(
                          pszDest[0],
                          v39,
                          pszDest,
                          &v39,
                          0,
                          L"\n%33hs: 0x%X",
                          "Field replaceable unit code",
                          v31) )
    {
      v13 = _mm_cvtsi128_si32(_mm_srli_si128(v5, 15));
      LODWORD(v32) = v13 < 0;
      if ( !(unsigned int)StringCchPrintfExW(pszDest[0], v39, pszDest, &v39, 0, L"\n%33hs: 0x%X", "SKSV", v32) )
      {
        v14 = pszDest[0];
        if ( v13 >= 0 )
        {
LABEL_48:
          StringCchPrintfExW(v14, v39, pszDest, &v39, 0, L"\n");
          return;
        }
        v15 = v8 & 0xF;
        if ( v15 == 5 )
        {
          LODWORD(v33) = v13 & 7;
          StringCchPrintfExW(pszDest[0], v39, pszDest, &v39, 0, L"\n%33hs: 0x%X", "Bit pointer", v33);
          LODWORD(v34) = v13 & 8;
          StringCchPrintfExW(pszDest[0], v39, pszDest, &v39, 0, L"\n%33hs: 0x%X", "BPV", v34);
          LODWORD(v35) = v13 & 0x40;
          StringCchPrintfExW(pszDest[0], v39, pszDest, &v39, 0, L"\n%33hs: 0x%X", "C/D", v35);
          v16 = pszDest[0];
          v17 = "Field pointer";
          LODWORD(v33) = HIBYTE(v41) | ((unsigned __int8)v4 << 8);
        }
        else
        {
          if ( ((v15 - 1) & 0xFC) != 0 || v15 == 2 )
          {
            if ( (v15 & 0xFD) != 0 )
            {
              LODWORD(v38) = HIBYTE(v41);
              LODWORD(v37) = (unsigned __int8)v4;
              LODWORD(v33) = v13 & 0x7F;
              v19 = StringCchPrintfExW(
                      pszDest[0],
                      v39,
                      pszDest,
                      &v39,
                      0,
                      L"\n%33hs: 0x%X 0x%X 0x%X",
                      "Sense-key specific",
                      v33,
                      v37,
                      v38);
              goto LABEL_47;
            }
            v18 = HIBYTE(v41) | ((unsigned __int8)v4 << 8);
            v17 = "Progress indication";
          }
          else
          {
            v18 = HIBYTE(v41) | ((unsigned __int8)v4 << 8);
            v17 = "Actual retry count";
          }
          LODWORD(v33) = v18;
          v16 = pszDest[0];
        }
        v19 = StringCchPrintfExW(v16, v39, pszDest, &v39, 0, L"\n%33hs: 0x%04X", v17, v33);
LABEL_47:
        v14 = pszDest[0];
        if ( v19 )
          return;
        goto LABEL_48;
      }
    }
  }
}

```

## disassembly

```asm
0x180045ff4  test    rcx, rcx
0x180045ff7  jz      locret_180046846
0x180045ffd  mov     rax, rsp
0x180046000  mov     [rax+10h], rbx
0x180046004  push    rbp
0x180046005  push    rsi
0x180046006  push    rdi
0x180046007  push    r12
0x180046009  push    r13
0x18004600b  push    r14
0x18004600d  push    r15
0x18004600f  lea     rbp, [rax-5Fh]
0x180046013  sub     rsp, 90h
0x18004601a  xor     r15d, r15d
0x18004601d  movaps  xmmword ptr [rax-48h], xmm6
0x180046021  mov     [rbp+57h+pszDest], r8
0x180046025  mov     r10, r8
0x180046028  mov     [rbp+57h+var_70], r15
0x18004602c  test    r8, r8
0x18004602f  jz      loc_180046827
0x180046035  test    r9d, r9d
0x180046038  jz      loc_180046827
0x18004603e  movzx   r14d, word ptr [rcx+10h]
0x180046043  lea     eax, [r9-1]
0x180046047  movups  xmm6, xmmword ptr [rcx]
0x18004604a  mov     [r8+rax*2], r15w
0x18004604f  mov     rcx, r10; pszDest
0x180046052  lea     rax, aRequestSenseDa; "\nREQUEST SENSE DATA..."
0x180046059  mov     edx, r9d; unsigned __int64
0x18004605c  mov     [rsp+0C0h+var_90], rax
0x180046061  lea     r9, [rbp+57h+var_70]; unsigned __int64 *
0x180046065  lea     rax, aHs_4; "%hs"
0x18004606c  mov     [rbp+57h+var_50], r14w
0x180046071  mov     [rsp+0C0h+var_98], rax; unsigned __int16 *
0x180046076  lea     r8, [rbp+57h+pszDest]; unsigned __int16 **
0x18004607a  mov     qword ptr [rsp+0C0h+var_A0], r15; unsigned int
0x18004607f  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180046084  test    eax, eax
0x180046086  jnz     loc_180046827
0x18004608c  mov     rcx, [rbp+57h+pszDest]; pszDest
0x180046090  movd    eax, xmm6
0x180046094  movzx   ebx, al
0x180046097  lea     rax, aResponseCode; "Response code"
0x18004609e  mov     r8d, ebx
0x1800460a1  and     r8d, 7Fh
0x1800460a5  mov     edx, r8d
0x1800460a8  sub     edx, 70h ; 'p'
0x1800460ab  jz      short loc_1800460FE
0x1800460ad  sub     edx, 1
0x1800460b0  jz      short loc_1800460E8
0x1800460b2  cmp     edx, 0Eh
0x1800460b5  lea     r9, [rbp+57h+var_70]
0x1800460b9  mov     rdx, [rbp+57h+var_70]
0x1800460bd  jz      short loc_1800460D2
0x1800460bf  mov     dword ptr [rsp+0C0h+var_88], r8d
0x1800460c4  mov     [rsp+0C0h+var_90], rax
0x1800460c9  lea     rax, a33hs0xXUnexpec; "\n%33hs: 0x%X unexpected response code"
0x1800460d0  jmp     short loc_18004611A
0x1800460d2  mov     dword ptr [rsp+0C0h+var_88], 7Fh
0x1800460da  mov     [rsp+0C0h+var_90], rax
0x1800460df  lea     rax, a33hs0xXVendorS; "\n%33hs: 0x%X vendor specific sense dat"...
0x1800460e6  jmp     short loc_18004611A
0x1800460e8  mov     dword ptr [rsp+0C0h+var_88], 71h ; 'q'
0x1800460f0  mov     [rsp+0C0h+var_90], rax
0x1800460f5  lea     rax, a33hs0xXDeferre; "\n%33hs: 0x%X deferred errors"
0x1800460fc  jmp     short loc_180046112
0x1800460fe  mov     dword ptr [rsp+0C0h+var_88], 70h ; 'p'
0x180046106  mov     [rsp+0C0h+var_90], rax
0x18004610b  lea     rax, a33hs0xXCurrent; "\n%33hs: 0x%X current errors"
0x180046112  mov     rdx, [rbp+57h+var_70]; unsigned __int64
0x180046116  lea     r9, [rbp+57h+var_70]; unsigned __int64 *
0x18004611a  mov     [rsp+0C0h+var_98], rax; unsigned __int16 *
0x18004611f  lea     r8, [rbp+57h+pszDest]; unsigned __int16 **
0x180046123  mov     qword ptr [rsp+0C0h+var_A0], r15; unsigned int
0x180046128  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18004612d  test    eax, eax
0x18004612f  jnz     loc_180046827
0x180046135  mov     rdx, [rbp+57h+var_70]; unsigned __int64
0x180046139  lea     rax, aValid; "Valid"
0x180046140  mov     rcx, [rbp+57h+pszDest]; pszDest
0x180046144  lea     r12, a33hs0xX; "\n%33hs: 0x%X"
0x18004614b  shr     ebx, 7
0x18004614e  lea     r9, [rbp+57h+var_70]; unsigned __int64 *
0x180046152  mov     dword ptr [rsp+0C0h+var_88], ebx
0x180046156  lea     r8, [rbp+57h+pszDest]; unsigned __int16 **
0x18004615a  mov     [rsp+0C0h+var_90], rax
0x18004615f  mov     [rsp+0C0h+var_98], r12; unsigned __int16 *
0x180046164  mov     qword ptr [rsp+0C0h+var_A0], r15; unsigned int
0x180046169  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18004616e  test    eax, eax
0x180046170  jnz     loc_180046827
0x180046176  mov     rdx, [rbp+57h+var_70]; unsigned __int64
0x18004617a  lea     r9, [rbp+57h+var_70]; unsigned __int64 *
0x18004617e  mov     rcx, [rbp+57h+pszDest]; pszDest
0x180046182  lea     r8, [rbp+57h+pszDest]; unsigned __int16 **
0x180046186  movdqa  xmm0, xmm6
0x18004618a  psrldq  xmm0, 1
0x18004618f  movd    eax, xmm0
0x180046193  movzx   eax, al
0x180046196  mov     dword ptr [rsp+0C0h+var_88], eax
0x18004619a  lea     rax, aSegmentNumber; "Segment number"
0x1800461a1  mov     [rsp+0C0h+var_90], rax
0x1800461a6  mov     [rsp+0C0h+var_98], r12; unsigned __int16 *
0x1800461ab  mov     qword ptr [rsp+0C0h+var_A0], r15; unsigned int
0x1800461b0  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800461b5  test    eax, eax
0x1800461b7  jnz     loc_180046827
0x1800461bd  mov     rcx, [rbp+57h+pszDest]; pszDest
0x1800461c1  lea     r13, __ImageBase
0x1800461c8  movdqa  xmm0, xmm6
0x1800461cc  lea     r9, [rbp+57h+var_70]; unsigned __int64 *
0x1800461d0  psrldq  xmm0, 2
0x1800461d5  lea     r8, [rbp+57h+pszDest]; unsigned __int16 **
0x1800461d9  movd    ebx, xmm0
0x1800461dd  movzx   eax, bl
0x1800461e0  and     eax, 0Fh
0x1800461e3  movzx   edi, bl
0x1800461e6  mov     edx, edi
0x1800461e8  and     edx, 0Fh
0x1800461eb  mov     rax, ds:rva off_180050530[r13+rax*8]; "NO SENSE" ...
0x1800461f3  mov     [rsp+0C0h+var_80], rax
0x1800461f8  lea     rax, aSenseKey; "Sense key"
0x1800461ff  mov     dword ptr [rsp+0C0h+var_88], edx
0x180046203  mov     rdx, [rbp+57h+var_70]; unsigned __int64
0x180046207  mov     [rsp+0C0h+var_90], rax
0x18004620c  lea     rax, a33hs0xXS; "\n%33hs: 0x%X %s"
0x180046213  mov     [rsp+0C0h+var_98], rax; unsigned __int16 *
0x180046218  mov     qword ptr [rsp+0C0h+var_A0], r15; unsigned int
0x18004621d  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180046222  test    eax, eax
0x180046224  jnz     loc_180046827
0x18004622a  mov     rdx, [rbp+57h+var_70]; unsigned __int64
0x18004622e  lea     r9, [rbp+57h+var_70]; unsigned __int64 *
0x180046232  mov     rcx, [rbp+57h+pszDest]; pszDest
0x180046236  lea     r8, [rbp+57h+pszDest]; unsigned __int16 **
0x18004623a  mov     eax, edi
0x18004623c  shr     eax, 5
0x18004623f  and     eax, 1
0x180046242  mov     dword ptr [rsp+0C0h+var_88], eax
0x180046246  lea     rax, aIli; "ILI"
0x18004624d  mov     [rsp+0C0h+var_90], rax
0x180046252  mov     [rsp+0C0h+var_98], r12; unsigned __int16 *
0x180046257  mov     qword ptr [rsp+0C0h+var_A0], r15; unsigned int
0x18004625c  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180046261  test    eax, eax
0x180046263  jnz     loc_180046827
0x180046269  mov     rdx, [rbp+57h+var_70]; unsigned __int64
0x18004626d  lea     r9, [rbp+57h+var_70]; unsigned __int64 *
0x180046271  mov     rcx, [rbp+57h+pszDest]; pszDest
0x180046275  lea     r8, [rbp+57h+pszDest]; unsigned __int16 **
0x180046279  mov     eax, edi
0x18004627b  shr     eax, 6
0x18004627e  and     eax, 1
0x180046281  mov     dword ptr [rsp+0C0h+var_88], eax
0x180046285  lea     rax, aEom; "EOM"
0x18004628c  mov     [rsp+0C0h+var_90], rax
0x180046291  mov     [rsp+0C0h+var_98], r12; unsigned __int16 *
0x180046296  mov     qword ptr [rsp+0C0h+var_A0], r15; unsigned int
0x18004629b  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800462a0  test    eax, eax
0x1800462a2  jnz     loc_180046827
0x1800462a8  mov     rdx, [rbp+57h+var_70]; unsigned __int64
0x1800462ac  lea     rsi, aFilemark; "FileMark"
0x1800462b3  mov     rcx, [rbp+57h+pszDest]; pszDest
0x1800462b7  lea     r9, [rbp+57h+var_70]; unsigned __int64 *
0x1800462bb  shr     edi, 7
0x1800462be  lea     r8, [rbp+57h+pszDest]; unsigned __int16 **
0x1800462c2  mov     dword ptr [rsp+0C0h+var_88], edi
0x1800462c6  mov     [rsp+0C0h+var_90], rsi
0x1800462cb  mov     [rsp+0C0h+var_98], r12; unsigned __int16 *
0x1800462d0  mov     qword ptr [rsp+0C0h+var_A0], r15; unsigned int
0x1800462d5  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800462da  test    eax, eax
0x1800462dc  jnz     loc_180046827
0x1800462e2  mov     rdx, [rbp+57h+var_70]; unsigned __int64
0x1800462e6  lea     r9, [rbp+57h+var_70]; unsigned __int64 *
0x1800462ea  mov     rcx, [rbp+57h+pszDest]; pszDest
0x1800462ee  lea     r8, [rbp+57h+pszDest]; unsigned __int16 **
0x1800462f2  mov     dword ptr [rsp+0C0h+var_88], edi
0x1800462f6  mov     [rsp+0C0h+var_90], rsi
0x1800462fb  mov     [rsp+0C0h+var_98], r12; unsigned __int16 *
0x180046300  mov     qword ptr [rsp+0C0h+var_A0], r15; unsigned int
0x180046305  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18004630a  test    eax, eax
0x18004630c  jnz     loc_180046827
0x180046312  movdqa  xmm0, xmm6
0x180046316  lea     rdi, a33hs0x08x; "\n%33hs: 0x%08X"
0x18004631d  psrldq  xmm0, 3
0x180046322  lea     r9, [rbp+57h+var_70]; unsigned __int64 *
0x180046326  movd    eax, xmm0
0x18004632a  movdqa  xmm0, xmm6
0x18004632e  psrldq  xmm0, 4
0x180046333  movzx   r8d, al
0x180046337  movd    eax, xmm0
0x18004633b  movdqa  xmm0, xmm6
0x18004633f  shl     r8d, 8
0x180046343  psrldq  xmm0, 5
0x180046348  movzx   ecx, al
0x18004634b  or      r8d, ecx
0x18004634e  movd    eax, xmm0
0x180046352  shl     r8d, 8
0x180046356  movdqa  xmm0, xmm6
0x18004635a  psrldq  xmm0, 6
0x18004635f  movzx   ecx, al
0x180046362  or      r8d, ecx
0x180046365  movd    eax, xmm0
0x180046369  mov     rcx, [rbp+57h+pszDest]; pszDest
0x18004636d  shl     r8d, 8
0x180046371  movzx   edx, al
0x180046374  lea     rax, aInformation_0; "Information"
0x18004637b  or      r8d, edx
0x18004637e  mov     rdx, [rbp+57h+var_70]; unsigned __int64
0x180046382  mov     dword ptr [rsp+0C0h+var_88], r8d
0x180046387  lea     r8, [rbp+57h+pszDest]; unsigned __int16 **
0x18004638b  mov     [rsp+0C0h+var_90], rax
0x180046390  mov     [rsp+0C0h+var_98], rdi; unsigned __int16 *
0x180046395  mov     qword ptr [rsp+0C0h+var_A0], r15; unsigned int
0x18004639a  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18004639f  test    eax, eax
0x1800463a1  jnz     loc_180046827
0x1800463a7  mov     rdx, [rbp+57h+var_70]; unsigned __int64
0x1800463ab  lea     r9, [rbp+57h+var_70]; unsigned __int64 *
0x1800463af  mov     rcx, [rbp+57h+pszDest]; pszDest
0x1800463b3  lea     r8, [rbp+57h+pszDest]; unsigned __int16 **
0x1800463b7  movdqa  xmm0, xmm6
0x1800463bb  psrldq  xmm0, 7
0x1800463c0  movd    eax, xmm0
0x1800463c4  movzx   eax, al
0x1800463c7  mov     dword ptr [rsp+0C0h+var_88], eax
0x1800463cb  lea     rax, aAdditionalSens; "Additional sense length"
0x1800463d2  mov     [rsp+0C0h+var_90], rax
0x1800463d7  lea     rax, a33hs0x02x; "\n%33hs: 0x%02X"
0x1800463de  mov     [rsp+0C0h+var_98], rax; unsigned __int16 *
0x1800463e3  mov     qword ptr [rsp+0C0h+var_A0], r15; unsigned int
0x1800463e8  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800463ed  test    eax, eax
0x1800463ef  jnz     loc_180046827
0x1800463f5  movdqa  xmm0, xmm6
0x1800463f9  lea     r9, [rbp+57h+var_70]; unsigned __int64 *
0x1800463fd  psrldq  xmm0, 8
0x180046402  movd    eax, xmm0
0x180046406  movdqa  xmm0, xmm6
0x18004640a  psrldq  xmm0, 9
0x18004640f  movzx   r8d, al
0x180046413  movd    eax, xmm0
0x180046417  movdqa  xmm0, xmm6
0x18004641b  shl     r8d, 8
0x18004641f  psrldq  xmm0, 0Ah
0x180046424  movzx   ecx, al
0x180046427  or      r8d, ecx
0x18004642a  movd    eax, xmm0
0x18004642e  shl     r8d, 8
0x180046432  movdqa  xmm0, xmm6
0x180046436  psrldq  xmm0, 0Bh
0x18004643b  movzx   ecx, al
0x18004643e  or      r8d, ecx
0x180046441  movd    eax, xmm0
0x180046445  mov     rcx, [rbp+57h+pszDest]; pszDest
0x180046449  shl     r8d, 8
0x18004644d  movzx   edx, al
0x180046450  lea     rax, aCommandSpecifi; "Command-specific information"
0x180046457  or      r8d, edx
0x18004645a  mov     rdx, [rbp+57h+var_70]; unsigned __int64
0x18004645e  mov     dword ptr [rsp+0C0h+var_88], r8d
0x180046463  lea     r8, [rbp+57h+pszDest]; unsigned __int16 **
0x180046467  mov     [rsp+0C0h+var_90], rax
0x18004646c  mov     [rsp+0C0h+var_98], rdi; unsigned __int16 *
0x180046471  mov     qword ptr [rsp+0C0h+var_A0], r15; unsigned int
0x180046476  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18004647b  test    eax, eax
0x18004647d  jnz     loc_180046827
0x180046483  mov     r11, [rbp+57h+pszDest]
0x180046487  movdqa  xmm0, xmm6
0x18004648b  psrldq  xmm0, 0Ch
0x180046490  movd    r10d, xmm0
0x180046495  cmp     r10b, 74h ; 't'
0x180046499  jnb     loc_180046585
0x18004649f  lea     eax, [r10-40h]
0x1800464a3  cmp     al, 30h ; '0'
0x1800464a5  ja      short loc_180046522
0x1800464a7  mov     rcx, 1000020002001h
0x1800464b1  bt      rcx, rax
0x1800464b5  jnb     short loc_180046522
0x1800464b7  movzx   eax, r10b
0x1800464bb  movdqa  xmm0, xmm6
0x1800464bf  imul    r9, rax, 0D0h
0x1800464c6  psrldq  xmm0, 0Dh
0x1800464cb  movd    eax, xmm0
0x1800464cf  movzx   edx, al
0x1800464d2  movzx   r8d, r10b
0x1800464d6  mov     rax, [r9+r13+506C8h]
0x1800464de  mov     [rsp+0C0h+var_78], rax
0x1800464e3  mov     dword ptr [rsp+0C0h+var_80], edx
0x1800464e7  mov     dword ptr [rsp+0C0h+var_88], r8d
0x1800464ec  mov     rdx, [rbp+57h+var_70]; unsigned __int64
0x1800464f0  lea     rax, aAscAsq; "ASC/ASQ"
0x1800464f7  mov     [rsp+0C0h+var_90], rax
0x1800464fc  lea     r9, [rbp+57h+var_70]; unsigned __int64 *
0x180046500  lea     rax, a33hs02x02xHs; "\n%33hs: (%02X/%02X) %hs"
0x180046507  mov     rcx, r11; pszDest
  ... truncated ...
```
