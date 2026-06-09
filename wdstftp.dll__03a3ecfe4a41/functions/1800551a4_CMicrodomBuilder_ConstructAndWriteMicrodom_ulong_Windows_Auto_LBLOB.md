# CMicrodomBuilder::ConstructAndWriteMicrodom(ulong,Windows::Auto<_LBLOB> *)

- ea: `0x1800551a4`
- end: `0x180055517`
- name: `?ConstructAndWriteMicrodom@CMicrodomBuilder@@QEAAJKPEAV?$Auto@U_LBLOB@@@Windows@@@Z`
- size: `883`
- prototype: `__int64 __fastcall(CMicrodomBuilder *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800575e8`

## callees

- `0x180037054`
- `0x1800370f4`
- `0x1800371a4`
- `0x1800542cc`
- `0x180054428`
- `0x1800551a4`
- `0x180056384`
- `0x180056570`
- `0x1800566f0`
- `0x180057088`
- `0x180057270`
- `0x180060e5a`

## string_xrefs

- `0x1800552ac`: `onecore\base\xml\udom_builder.cpp`
- `0x18005536d`: `onecore\base\xml\udom_builder.cpp`
- `0x1800553da`: `onecore\base\xml\udom_builder.cpp`
- `0x18005542c`: `onecore\base\xml\udom_builder.cpp`
- `0x18005548f`: `onecore\base\xml\udom_builder.cpp`
- `0x1800554c7`: `onecore\base\xml\udom_builder.cpp`
- `0x1800552c2`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x18005537f`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x1800553ec`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x18005543e`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x1800554a5`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x1800554dd`: `CMicrodomBuilder::ConstructAndWriteMicrodom`
- `0x18005538a`: `BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulOffsetToDomLayout)`
- `0x1800553f7`: `BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulOffsetToDoctypeData)`
- `0x180055449`: `BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulOffsetToPositionData)`
- `0x1800554b3`: `BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulTotalSize)`

## pseudocode

```c
__int64 __fastcall CMicrodomBuilder::ConstructAndWriteMicrodom(CMicrodomBuilder *this, __int64 a2, __m128i *a3)
{
  unsigned __int64 v5; // r15
  unsigned __int64 v6; // rbx
  __int64 v7; // r14
  unsigned int v8; // eax
  unsigned __int64 v9; // r14
  __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rax
  __int64 result; // rax
  _DWORD *v17; // xmm0_8
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  unsigned int v23; // ebx
  __m128i v24; // [rsp+20h] [rbp-30h] BYREF
  void *v25; // [rsp+30h] [rbp-20h]
  const char *v26; // [rsp+38h] [rbp-18h]
  int v27; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 v28; // [rsp+48h] [rbp-8h] BYREF

  v5 = ((unsigned int)CMicrodomBuilder::DetermineStringTableSize(this) + 3) & 0xFFFFFFFC;
  v6 = ((unsigned int)CMicrodomBuilder::GetXmlDomSize(this) + 3) & 0xFFFFFFFC;
  v28 = 0;
  v7 = (unsigned int)CMicrodomBuilder::GetDoctypeDataSize(this) + 3;
  v8 = *((_DWORD *)this + 325);
  v9 = v7 & 0xFFFFFFFFFFFFFFFCuLL;
  if ( v8 > 0xFF )
  {
    v10 = 12;
    if ( v8 <= 0xFFFF )
      v10 = 8;
  }
  else
  {
    v10 = 4;
  }
  BUCL::Implementation::Multiply<BUCL::Rtl::CCallDisposition,unsigned __int64>(&v27, v10, *((_QWORD *)this + 161), &v28);
  if ( v27 < 0 || (v11 = v28 + 12, v28 + 12 < v28) || v11 < 0xC )
    LODWORD(v11) = 0;
  v12 = ((_DWORD)v11 + 3) & 0xFFFFFFFC;
  v13 = v5 + 24;
  if ( v5 + 24 < v5
    || (v14 = v13 + v6, v13 + v6 < v13)
    || v14 < v6
    || (v15 = v14 + v12, v14 + v12 < v14)
    || v15 < v12
    || (v12 = v15 + v9, v15 + v9 < v15)
    || v12 < v9 )
  {
    LODWORD(v25) = 1024;
    v24.m128i_i64[0] = (__int64)"onecore\\base\\xml\\udom_builder.cpp";
    v24.m128i_i64[1] = (__int64)"CMicrodomBuilder::ConstructAndWriteMicrodom";
    v26 = "BUCL::Rtl::Add<SIZE_T>( sizeof(MICRODOM_HEADER), cbStringPoolSize, cbDomLayoutSize, cbPositionDataSize, cbDoct"
          "ypeDataSize, cbRequiredSize)";
    RtlReportErrorOrigination(&v24, v12, 3221225621LL);
    return 3221225621LL;
  }
  else
  {
    if ( v12 > 0xFFFFFFFF )
    {
      LODWORD(v25) = 1026;
      v24.m128i_i64[0] = (__int64)"onecore\\base\\xml\\udom_builder.cpp";
      v24.m128i_i64[1] = (__int64)"CMicrodomBuilder::ConstructAndWriteMicrodom";
      v26 = "cbRequiredSize <= BUCL::CMaximumInteger<ULONG>::Value";
      RtlReportErrorOrigination(&v24, v12, 3221226539LL);
      return 3221226539LL;
    }
    if ( a3->m128i_i64[1] >= v12 || (result = RtlReallocateLBlob(v14, v12, a3), (int)result >= 0) )
    {
      v17 = (_DWORD *)a3[1].m128i_i64[0];
      v24 = *a3;
      v25 = v17;
      memset_0(v17, 0, _mm_srli_si128(v24, 8).m128i_u64[0]);
      *v17 = 1682465869;
      v24.m128i_i64[0] = 24;
      v17[2] = 24;
      result = CMicrodomBuilder::ProduceStringTable(this, (struct _LBLOB *)&v24);
      if ( (int)result >= 0 )
      {
        v18 = (v24.m128i_i32[0] + 3) & 0xFFFFFFFC;
        v24.m128i_i64[0] = v18;
        v17[3] = v18;
        result = CMicrodomBuilder::WriteXmlDom(this, (struct _LBLOB *)&v24);
        if ( (int)result >= 0 )
        {
          v19 = (v24.m128i_i32[0] + 3) & 0xFFFFFFFC;
          v24.m128i_i64[0] = v19;
          v17[5] = v19;
          result = CMicrodomBuilder::WriteDoctypeData(this, (struct _LBLOB *)&v24);
          if ( (int)result >= 0 )
          {
            v20 = (v24.m128i_i32[0] + 3) & 0xFFFFFFFC;
            v24.m128i_i64[0] = v20;
            v17[4] = v20;
            result = CMicrodomBuilder::WriteLocationData(this, (struct _LBLOB *)&v24);
            if ( (int)result >= 0 )
            {
              v22 = v24.m128i_i64[0];
              if ( v24.m128i_i64[0] > 0xFFFFFFFFuLL )
              {
                v23 = -1073741675;
              }
              else
              {
                v17[1] = v24.m128i_i32[0];
                if ( v22 == (unsigned int)v22 )
                {
                  a3->m128i_i64[0] = v22;
                  return 0;
                }
                v23 = -1073741595;
              }
              LODWORD(v25) = 1089;
              v24.m128i_i64[0] = (__int64)"onecore\\base\\xml\\udom_builder.cpp";
              v24.m128i_i64[1] = (__int64)"CMicrodomBuilder::ConstructAndWriteMicrodom";
              v26 = "BUCL::Rtl::ConvertInteger(WriteBlock.Length, pHeader->ulTotalSize)";
              RtlReportErrorOrigination(&v24, v21, v23);
              return v23;
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800551a4  mov     [rsp-28h+arg_8], rbx
0x1800551a9  push    rbp
0x1800551aa  push    rsi
0x1800551ab  push    rdi
0x1800551ac  push    r14
0x1800551ae  push    r15
0x1800551b0  mov     rbp, rsp
0x1800551b3  sub     rsp, 50h
0x1800551b7  mov     rsi, r8
0x1800551ba  mov     rdi, rcx
0x1800551bd  call    ?DetermineStringTableSize@CMicrodomBuilder@@AEBA_KXZ; CMicrodomBuilder::DetermineStringTableSize(void)
0x1800551c2  mov     rcx, rdi; this
0x1800551c5  lea     r15d, [rax+3]
0x1800551c9  and     r15, 0FFFFFFFFFFFFFFFCh
0x1800551cd  call    ?GetXmlDomSize@CMicrodomBuilder@@AEBA_KXZ; CMicrodomBuilder::GetXmlDomSize(void)
0x1800551d2  mov     rcx, rdi; this
0x1800551d5  lea     ebx, [rax+3]
0x1800551d8  and     rbx, 0FFFFFFFFFFFFFFFCh
0x1800551dc  call    ?GetDoctypeDataSize@CMicrodomBuilder@@AEBA_KXZ; CMicrodomBuilder::GetDoctypeDataSize(void)
0x1800551e1  and     [rbp+var_8], 0
0x1800551e6  lea     r14d, [rax+3]
0x1800551ea  mov     eax, [rdi+514h]
0x1800551f0  and     r14, 0FFFFFFFFFFFFFFFCh
0x1800551f4  cmp     eax, 0FFh
0x1800551f9  ja      short loc_180055202
0x1800551fb  mov     edx, 4
0x180055200  jmp     short loc_180055212
0x180055202  mov     edx, 0Ch
0x180055207  cmp     eax, 0FFFFh
0x18005520c  lea     ecx, [rdx-4]
0x18005520f  cmovbe  edx, ecx
0x180055212  mov     r8, [rdi+508h]
0x180055219  lea     r9, [rbp+var_8]
0x18005521d  lea     rcx, [rbp+var_10]
0x180055221  call    ??$Multiply@VCCallDisposition@Rtl@BUCL@@_K@Implementation@BUCL@@YA?AVCCallDisposition@Rtl@1@_K0AEA_K@Z; BUCL::Implementation::Multiply<BUCL::Rtl::CCallDisposition,unsigned __int64>(unsigned __int64,unsigned __int64,unsigned __int64 &)
0x180055226  cmp     [rbp+var_10], 0
0x18005522a  jl      short loc_18005523F
0x18005522c  mov     rax, [rbp+var_8]
0x180055230  lea     rcx, [rax+0Ch]
0x180055234  cmp     rcx, rax
0x180055237  jb      short loc_18005523F
0x180055239  cmp     rcx, 0Ch
0x18005523d  jnb     short loc_180055241
0x18005523f  xor     ecx, ecx
0x180055241  lea     edx, [rcx+3]
0x180055244  and     rdx, 0FFFFFFFFFFFFFFFCh
0x180055248  lea     rax, [r15+18h]
0x18005524c  cmp     rax, 18h
0x180055250  jb      loc_1800554C7
0x180055256  cmp     rax, r15
0x180055259  jb      loc_1800554C7
0x18005525f  lea     rcx, [rax+rbx]
0x180055263  cmp     rcx, rax
0x180055266  jb      loc_1800554C7
0x18005526c  cmp     rcx, rbx
0x18005526f  jb      loc_1800554C7
0x180055275  lea     rax, [rcx+rdx]
0x180055279  cmp     rax, rcx
0x18005527c  jb      loc_1800554C7
0x180055282  cmp     rax, rdx
0x180055285  jb      loc_1800554C7
0x18005528b  lea     rdx, [rax+r14]
0x18005528f  cmp     rdx, rax
0x180055292  jb      loc_1800554C7
0x180055298  cmp     rdx, r14
0x18005529b  jb      loc_1800554C7
0x1800552a1  mov     r14d, 0FFFFFFFFh
0x1800552a7  cmp     rdx, r14
0x1800552aa  jbe     short loc_1800552ED
0x1800552ac  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x1800552b3  mov     dword ptr [rbp+var_20], 402h
0x1800552ba  mov     qword ptr [rbp+var_30], rax
0x1800552be  lea     rcx, [rbp+var_30]
0x1800552c2  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x1800552c9  mov     r8d, 0C000042Bh
0x1800552cf  mov     qword ptr [rbp+var_30+8], rax
0x1800552d3  lea     rax, aCbrequiredsize; "cbRequiredSize <= BUCL::CMaximumInteger"...
0x1800552da  mov     [rbp+var_18], rax
0x1800552de  call    RtlReportErrorOrigination
0x1800552e3  mov     eax, 0C000042Bh
0x1800552e8  jmp     loc_180055503
0x1800552ed  cmp     [rsi+8], rdx
0x1800552f1  jnb     short loc_180055303
0x1800552f3  mov     r8, rsi
0x1800552f6  call    RtlReallocateLBlob
0x1800552fb  test    eax, eax
0x1800552fd  js      loc_180055503
0x180055303  movups  xmm1, xmmword ptr [rsi]
0x180055306  xor     edx, edx; Val
0x180055308  movsd   xmm0, qword ptr [rsi+10h]
0x18005530d  movups  [rbp+var_30], xmm1
0x180055311  movsd   [rbp+var_20], xmm0
0x180055316  mov     rbx, [rbp+var_20]
0x18005531a  psrldq  xmm1, 8
0x18005531f  mov     rcx, rbx; void *
0x180055322  movq    r8, xmm1; Size
0x180055327  call    memset_0
0x18005532c  mov     dword ptr [rbx], 6448644Dh
0x180055332  lea     rdx, [rbp+var_30]; struct _LBLOB *
0x180055336  mov     rcx, rdi; this
0x180055339  mov     qword ptr [rbp+var_30], 18h
0x180055341  mov     dword ptr [rbx+8], 18h
0x180055348  call    ?ProduceStringTable@CMicrodomBuilder@@AEBAJPEAU_LBLOB@@@Z; CMicrodomBuilder::ProduceStringTable(_LBLOB *)
0x18005534d  test    eax, eax
0x18005534f  js      loc_180055503
0x180055355  mov     ecx, dword ptr [rbp+var_30]
0x180055358  add     ecx, 3
0x18005535b  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18005535f  mov     eax, ecx
0x180055361  mov     qword ptr [rbp+var_30], rcx
0x180055365  mov     [rbx+0Ch], eax
0x180055368  cmp     rcx, rax
0x18005536b  jz      short loc_1800553AE
0x18005536d  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x180055374  mov     dword ptr [rbp+var_20], 428h
0x18005537b  mov     qword ptr [rbp+var_30], rax
0x18005537f  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x180055386  mov     qword ptr [rbp+var_30+8], rax
0x18005538a  lea     rax, aBuclRtlConvert_1; "BUCL::Rtl::ConvertInteger(WriteBlock.Le"...
0x180055391  mov     r8d, 0C00000E5h
0x180055397  mov     [rbp+var_18], rax
0x18005539b  lea     rcx, [rbp+var_30]
0x18005539f  call    RtlReportErrorOrigination
0x1800553a4  mov     eax, 0C00000E5h
0x1800553a9  jmp     loc_180055503
0x1800553ae  lea     rdx, [rbp+var_30]; struct _LBLOB *
0x1800553b2  mov     rcx, rdi; this
0x1800553b5  call    ?WriteXmlDom@CMicrodomBuilder@@AEAAJPEAU_LBLOB@@@Z; CMicrodomBuilder::WriteXmlDom(_LBLOB *)
0x1800553ba  test    eax, eax
0x1800553bc  js      loc_180055503
0x1800553c2  mov     ecx, dword ptr [rbp+var_30]
0x1800553c5  add     ecx, 3
0x1800553c8  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1800553cc  mov     eax, ecx
0x1800553ce  mov     qword ptr [rbp+var_30], rcx
0x1800553d2  mov     [rbx+14h], eax
0x1800553d5  cmp     rcx, rax
0x1800553d8  jz      short loc_180055400
0x1800553da  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x1800553e1  mov     dword ptr [rbp+var_20], 431h
0x1800553e8  mov     qword ptr [rbp+var_30], rax
0x1800553ec  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x1800553f3  mov     qword ptr [rbp+var_30+8], rax
0x1800553f7  lea     rax, aBuclRtlConvert_5; "BUCL::Rtl::ConvertInteger(WriteBlock.Le"...
0x1800553fe  jmp     short loc_180055391
0x180055400  lea     rdx, [rbp+var_30]; struct _LBLOB *
0x180055404  mov     rcx, rdi; this
0x180055407  call    ?WriteDoctypeData@CMicrodomBuilder@@AEAAJPEAU_LBLOB@@@Z; CMicrodomBuilder::WriteDoctypeData(_LBLOB *)
0x18005540c  test    eax, eax
0x18005540e  js      loc_180055503
0x180055414  mov     ecx, dword ptr [rbp+var_30]
0x180055417  add     ecx, 3
0x18005541a  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18005541e  mov     eax, ecx
0x180055420  mov     qword ptr [rbp+var_30], rcx
0x180055424  mov     [rbx+10h], eax
0x180055427  cmp     rcx, rax
0x18005542a  jz      short loc_180055455
0x18005542c  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x180055433  mov     dword ptr [rbp+var_20], 43Ah
0x18005543a  mov     qword ptr [rbp+var_30], rax
0x18005543e  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x180055445  mov     qword ptr [rbp+var_30+8], rax
0x180055449  lea     rax, aBuclRtlConvert_0; "BUCL::Rtl::ConvertInteger(WriteBlock.Le"...
0x180055450  jmp     loc_180055391
0x180055455  lea     rdx, [rbp+var_30]; struct _LBLOB *
0x180055459  mov     rcx, rdi; this
0x18005545c  call    ?WriteLocationData@CMicrodomBuilder@@AEAAJPEAU_LBLOB@@@Z; CMicrodomBuilder::WriteLocationData(_LBLOB *)
0x180055461  test    eax, eax
0x180055463  js      loc_180055503
0x180055469  mov     rcx, qword ptr [rbp+var_30]
0x18005546d  cmp     rcx, r14
0x180055470  ja      short loc_18005548A
0x180055472  mov     eax, ecx
0x180055474  mov     [rbx+4], eax
0x180055477  cmp     rcx, rax
0x18005547a  jz      short loc_180055483
0x18005547c  mov     ebx, 0C00000E5h
0x180055481  jmp     short loc_18005548F
0x180055483  mov     [rsi], rcx
0x180055486  xor     eax, eax
0x180055488  jmp     short loc_180055503
0x18005548a  mov     ebx, 0C0000095h
0x18005548f  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x180055496  mov     dword ptr [rbp+var_20], 441h
0x18005549d  mov     qword ptr [rbp+var_30], rax
0x1800554a1  lea     rcx, [rbp+var_30]
0x1800554a5  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x1800554ac  mov     r8d, ebx
0x1800554af  mov     qword ptr [rbp+var_30+8], rax
0x1800554b3  lea     rax, aBuclRtlConvert_4; "BUCL::Rtl::ConvertInteger(WriteBlock.Le"...
0x1800554ba  mov     [rbp+var_18], rax
0x1800554be  call    RtlReportErrorOrigination
0x1800554c3  mov     eax, ebx
0x1800554c5  jmp     short loc_180055503
0x1800554c7  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x1800554ce  mov     dword ptr [rbp+var_20], 400h
0x1800554d5  mov     qword ptr [rbp+var_30], rax
0x1800554d9  lea     rcx, [rbp+var_30]
0x1800554dd  lea     rax, aCmicrodombuild_13; "CMicrodomBuilder::ConstructAndWriteMicr"...
0x1800554e4  mov     r8d, 0C0000095h
0x1800554ea  mov     qword ptr [rbp+var_30+8], rax
0x1800554ee  lea     rax, aBuclRtlAddSize_2; "BUCL::Rtl::Add<SIZE_T>( sizeof(MICRODOM"...
0x1800554f5  mov     [rbp+var_18], rax
0x1800554f9  call    RtlReportErrorOrigination
0x1800554fe  mov     eax, 0C0000095h
0x180055503  mov     rbx, [rsp+50h+arg_8]
0x18005550b  add     rsp, 50h
0x18005550f  pop     r15
0x180055511  pop     r14
0x180055513  pop     rdi
0x180055514  pop     rsi
0x180055515  pop     rbp
0x180055516  retn
```
