# LookUpTableFlushComplete

- ea: `0x18000e180`
- end: `0x18000e56b`
- name: `LookUpTableFlushComplete`
- size: `1003`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000e100`
- `0x18000f9a0`
- `0x180035410`
- `0x18003550c`

## callees

- `0x1800014a0`
- `0x18000e180`
- `0x180012880`
- `0x180035354`

## pseudocode

```c
__int64 __fastcall LookUpTableFlushComplete(const __m128i *a1, __int64 a2, __int64 a3, int a4)
{
  __int64 result; // rax
  __int64 v6; // rax
  __int64 v7; // rcx
  unsigned int i; // ebx
  char v9; // [rsp+120h] [rbp-80h] BYREF
  char v10; // [rsp+121h] [rbp-7Fh] BYREF
  char v11; // [rsp+122h] [rbp-7Eh] BYREF
  char v12; // [rsp+123h] [rbp-7Dh] BYREF
  char v13; // [rsp+124h] [rbp-7Ch] BYREF
  char v14; // [rsp+125h] [rbp-7Bh] BYREF
  char v15; // [rsp+126h] [rbp-7Ah] BYREF
  char v16; // [rsp+127h] [rbp-79h] BYREF
  char v17; // [rsp+128h] [rbp-78h] BYREF
  _BYTE v18[3]; // [rsp+129h] [rbp-77h] BYREF
  int v19; // [rsp+12Ch] [rbp-74h] BYREF
  int v20; // [rsp+130h] [rbp-70h] BYREF
  int v21; // [rsp+134h] [rbp-6Ch] BYREF
  __int64 v22; // [rsp+138h] [rbp-68h] BYREF
  __int64 v23; // [rsp+140h] [rbp-60h] BYREF
  __int64 v24; // [rsp+148h] [rbp-58h] BYREF
  __int64 v25; // [rsp+150h] [rbp-50h] BYREF
  __int64 v26; // [rsp+158h] [rbp-48h] BYREF
  __int64 v27; // [rsp+160h] [rbp-40h] BYREF
  __int64 v28; // [rsp+168h] [rbp-38h] BYREF
  __int64 v29; // [rsp+170h] [rbp-30h] BYREF
  __int128 *v30; // [rsp+178h] [rbp-28h] BYREF
  __int64 v31; // [rsp+180h] [rbp-20h] BYREF
  const wchar_t *v32; // [rsp+188h] [rbp-18h] BYREF
  __int16 v33; // [rsp+190h] [rbp-10h]
  const wchar_t *v34; // [rsp+198h] [rbp-8h] BYREF
  __int16 v35; // [rsp+1A0h] [rbp+0h]
  const wchar_t *v36; // [rsp+1A8h] [rbp+8h] BYREF
  __int16 v37; // [rsp+1B0h] [rbp+10h]
  const wchar_t *v38; // [rsp+1B8h] [rbp+18h] BYREF
  __int16 v39; // [rsp+1C0h] [rbp+20h]
  const wchar_t *v40; // [rsp+1C8h] [rbp+28h] BYREF
  __int16 v41; // [rsp+1D0h] [rbp+30h]
  const wchar_t *v42; // [rsp+1D8h] [rbp+38h] BYREF
  __int16 v43; // [rsp+1E0h] [rbp+40h]
  const wchar_t *v44; // [rsp+1E8h] [rbp+48h] BYREF
  __int16 v45; // [rsp+1F0h] [rbp+50h]
  const wchar_t *v46; // [rsp+1F8h] [rbp+58h] BYREF
  __int16 v47; // [rsp+200h] [rbp+60h]
  const wchar_t *v48; // [rsp+208h] [rbp+68h] BYREF
  __int16 v49; // [rsp+210h] [rbp+70h]
  __int128 v50; // [rsp+218h] [rbp+78h] BYREF

  result = a1[16].m128i_u32[0];
  if ( (_DWORD)result )
  {
    if ( a1[18].m128i_i32[2] > (unsigned int)result || !a1[17].m128i_i64[1] )
      a1[18].m128i_i32[2] = result;
    if ( a1[18].m128i_i32[1] < (unsigned int)result )
      a1[18].m128i_i32[1] = result;
    a1[17] = _mm_add_epi64(
               _mm_unpacklo_epi64((__m128i)(unsigned __int64)result, (__m128i)1uLL),
               _mm_loadu_si128(a1 + 17));
    if ( a1[17].m128i_i64[0] )
    {
      if ( (unsigned int)dword_180045140 > 5
        && (qword_180045150 & 0x200000000000LL) != 0
        && (qword_180045158 & 0x200000000000LL) == qword_180045158 )
      {
        v9 = 4;
        v35 = 42;
        v32 = L"SummaryCount";
        v33 = 24;
        v22 = a1[19].m128i_u32[1];
        v34 = L"NumLargeEventFailures";
        v23 = a1[19].m128i_u32[0];
        v36 = L"NumAllocationFailures";
        v24 = a1[18].m128i_u32[3];
        v38 = L"NumBucketLimitReached";
        v25 = a1[18].m128i_u32[2];
        v40 = L"MinEntriesFlushed";
        v26 = a1[18].m128i_u32[1];
        v42 = L"MaxEntriesFlushed";
        v27 = a1[17].m128i_i64[0];
        v44 = L"TotalEntriesFlushed";
        v45 = 38;
        v28 = a1[18].m128i_u32[0];
        v46 = L"MaxEntriesStored";
        v47 = 32;
        v29 = a1[17].m128i_i64[1];
        v48 = L"NumFlushes";
        v49 = 20;
        v6 = a1[20].m128i_i64[1];
        v37 = 42;
        v39 = 42;
        v19 = 1;
        v10 = 4;
        v11 = 4;
        v12 = 4;
        v13 = 4;
        v41 = 34;
        v14 = 4;
        v43 = 34;
        v15 = 4;
        v16 = 4;
        v17 = 4;
        v7 = *(_QWORD *)(v6 + 8);
        v30 = &v50;
        v50 = *(_OWORD *)(v7 - 16);
        v18[0] = 0;
        v20 = -1;
        v21 = 300;
        v31 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          v7,
          (unsigned int)word_18003E37A,
          1,
          a4,
          (__int64)&v31,
          (__int64)&v21,
          (__int64)&v20,
          (__int64)v18,
          (__int64)&v30,
          (__int64)&v48,
          (__int64)&v29,
          (__int64)&v17,
          (__int64)&v46,
          (__int64)&v28,
          (__int64)&v16,
          (__int64)&v44,
          (__int64)&v27,
          (__int64)&v15,
          (__int64)&v42,
          (__int64)&v26,
          (__int64)&v14,
          (__int64)&v40,
          (__int64)&v25,
          (__int64)&v13,
          (__int64)&v38,
          (__int64)&v24,
          (__int64)&v12,
          (__int64)&v36,
          (__int64)&v23,
          (__int64)&v11,
          (__int64)&v34,
          (__int64)&v22,
          (__int64)&v10,
          (__int64)&v32,
          (__int64)&v19,
          (__int64)&v9);
      }
      a1[17] = 0;
      a1[18] = 0;
      a1[19].m128i_i64[0] = 0;
    }
    for ( i = 0; i < 0x20; ++i )
      result = FlushLookUpTableBucket(a1, i);
  }
  return result;
}

```

## disassembly

```asm
0x18000e180  mov     [rsp-8+arg_10], rdi
0x18000e185  push    rbp
0x18000e186  lea     rbp, [rsp-90h]
0x18000e18e  sub     rsp, 230h
0x18000e195  mov     rax, cs:__security_cookie
0x18000e19c  xor     rax, rsp
0x18000e19f  mov     [rbp+90h+var_8], rax
0x18000e1a6  mov     eax, [rcx+100h]
0x18000e1ac  mov     rdi, rcx
0x18000e1af  test    eax, eax
0x18000e1b1  jz      loc_18000E54B
0x18000e1b7  mov     [rsp+230h+arg_8], rbx
0x18000e1bf  cmp     [rcx+128h], eax
0x18000e1c5  ja      short loc_18000E1D1
0x18000e1c7  cmp     qword ptr [rcx+118h], 0
0x18000e1cf  jnz     short loc_18000E1D7
0x18000e1d1  mov     [rcx+128h], eax
0x18000e1d7  cmp     [rcx+124h], eax
0x18000e1dd  jnb     short loc_18000E1E5
0x18000e1df  mov     [rcx+124h], eax
0x18000e1e5  mov     r8d, 1
0x18000e1eb  movq    xmm1, rax
0x18000e1f0  movq    xmm0, r8
0x18000e1f5  punpcklqdq xmm1, xmm0
0x18000e1f9  movdqu  xmm0, xmmword ptr [rcx+110h]
0x18000e201  paddq   xmm1, xmm0
0x18000e205  movdqu  xmmword ptr [rcx+110h], xmm1
0x18000e20d  cmp     qword ptr [rcx+110h], 0
0x18000e215  jz      loc_18000E530
0x18000e21b  mov     eax, cs:dword_180045140
0x18000e221  cmp     eax, 5
0x18000e224  jbe     loc_18000E516
0x18000e22a  mov     rcx, cs:qword_180045158
0x18000e231  mov     rdx, 200000000000h
0x18000e23b  mov     rax, cs:qword_180045150
0x18000e242  test    rdx, rax
0x18000e245  jz      loc_18000E516
0x18000e24b  mov     rax, rcx
0x18000e24e  and     rax, rdx
0x18000e251  cmp     rax, rcx
0x18000e254  jnz     loc_18000E516
0x18000e25a  mov     ecx, 2Ah ; '*'
0x18000e25f  mov     [rbp+90h+var_110], 4
0x18000e263  lea     rax, aSummarycount; "SummaryCount"
0x18000e26a  mov     [rbp+90h+var_90], cx
0x18000e26e  mov     [rbp+90h+var_A8], rax
0x18000e272  mov     eax, 18h
0x18000e277  mov     [rbp+90h+var_A0], ax
0x18000e27b  mov     eax, [rdi+134h]
0x18000e281  mov     [rbp+90h+var_F8], rax
0x18000e285  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x18000e28c  mov     [rbp+90h+var_98], rax
0x18000e290  mov     eax, [rdi+130h]
0x18000e296  mov     [rbp+90h+var_F0], rax
0x18000e29a  lea     rax, aNumallocationf; "NumAllocationFailures"
0x18000e2a1  mov     [rbp+90h+var_88], rax
0x18000e2a5  mov     eax, [rdi+12Ch]
0x18000e2ab  mov     [rbp+90h+var_E8], rax
0x18000e2af  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x18000e2b6  mov     [rbp+90h+var_78], rax
0x18000e2ba  mov     eax, [rdi+128h]
0x18000e2c0  mov     [rbp+90h+var_E0], rax
0x18000e2c4  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x18000e2cb  mov     [rbp+90h+var_68], rax
0x18000e2cf  mov     eax, [rdi+124h]
0x18000e2d5  mov     [rbp+90h+var_D8], rax
0x18000e2d9  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x18000e2e0  mov     [rbp+90h+var_58], rax
0x18000e2e4  mov     rax, [rdi+110h]
0x18000e2eb  mov     [rbp+90h+var_D0], rax
0x18000e2ef  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x18000e2f6  mov     [rbp+90h+var_48], rax
0x18000e2fa  mov     eax, 26h ; '&'
0x18000e2ff  mov     [rbp+90h+var_40], ax
0x18000e303  mov     eax, [rdi+120h]
0x18000e309  mov     [rbp+90h+var_C8], rax
0x18000e30d  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x18000e314  mov     [rbp+90h+var_38], rax
0x18000e318  mov     eax, 20h ; ' '
0x18000e31d  mov     [rbp+90h+var_30], ax
0x18000e321  mov     rax, [rdi+118h]
0x18000e328  mov     [rbp+90h+var_C0], rax
0x18000e32c  lea     rax, aNumflushes; "NumFlushes"
0x18000e333  mov     [rbp+90h+var_28], rax
0x18000e337  mov     eax, 14h
0x18000e33c  mov     [rbp+90h+var_20], ax
0x18000e340  mov     rax, [rdi+148h]
0x18000e347  mov     [rbp+90h+var_80], cx
0x18000e34b  mov     [rbp+90h+var_70], cx
0x18000e34f  mov     ecx, 22h ; '"'
0x18000e354  mov     [rbp+90h+var_104], r8d
0x18000e358  mov     [rbp+90h+var_10F], 4
0x18000e35c  mov     [rbp+90h+var_10E], 4
0x18000e360  mov     [rbp+90h+var_10D], 4
0x18000e364  mov     [rbp+90h+var_10C], 4
0x18000e368  mov     [rbp+90h+var_60], cx
0x18000e36c  mov     [rbp+90h+var_10B], 4
0x18000e370  mov     [rbp+90h+var_50], cx
0x18000e374  mov     [rbp+90h+var_10A], 4
0x18000e378  mov     [rbp+90h+var_109], 4
0x18000e37c  mov     [rbp+90h+var_108], 4
0x18000e380  mov     rcx, [rax+8]
0x18000e384  lea     rax, [rbp+90h+var_18]
0x18000e388  mov     [rbp+90h+var_B8], rax
0x18000e38c  lea     rax, [rbp+90h+var_110]
0x18000e390  mov     [rsp+230h+var_118], rax
0x18000e398  lea     rax, [rbp+90h+var_104]
0x18000e39c  mov     [rsp+230h+var_120], rax
0x18000e3a4  lea     rax, [rbp+90h+var_A8]
0x18000e3a8  movups  xmm0, xmmword ptr [rcx-10h]
0x18000e3ac  mov     [rsp+230h+var_128], rax
0x18000e3b4  lea     rax, [rbp+90h+var_10F]
0x18000e3b8  mov     [rsp+230h+var_130], rax
0x18000e3c0  lea     rax, [rbp+90h+var_F8]
0x18000e3c4  mov     [rsp+230h+var_138], rax
0x18000e3cc  lea     rax, [rbp+90h+var_98]
0x18000e3d0  mov     [rsp+230h+var_140], rax
0x18000e3d8  movups  [rbp+90h+var_18], xmm0
0x18000e3dc  mov     [rbp+90h+var_107], 0
0x18000e3e0  mov     [rbp+90h+var_100], 0FFFFFFFFh
0x18000e3e7  mov     [rbp+90h+var_FC], 12Ch
0x18000e3ee  mov     [rbp+90h+var_B0], 1000000h
0x18000e3f6  lea     rax, [rbp+90h+var_10E]
0x18000e3fa  mov     [rsp+230h+var_148], rax
0x18000e402  lea     rdx, word_18003E37A
0x18000e409  lea     rax, [rbp+90h+var_F0]
0x18000e40d  mov     [rsp+230h+var_150], rax
0x18000e415  lea     rax, [rbp+90h+var_88]
0x18000e419  mov     [rsp+230h+var_158], rax
0x18000e421  lea     rax, [rbp+90h+var_10D]
0x18000e425  mov     [rsp+230h+var_160], rax
0x18000e42d  lea     rax, [rbp+90h+var_E8]
0x18000e431  mov     [rsp+230h+var_168], rax
0x18000e439  lea     rax, [rbp+90h+var_78]
0x18000e43d  mov     [rsp+230h+var_170], rax
0x18000e445  lea     rax, [rbp+90h+var_10C]
0x18000e449  mov     [rsp+230h+var_178], rax
0x18000e451  lea     rax, [rbp+90h+var_E0]
0x18000e455  mov     [rsp+230h+var_180], rax
0x18000e45d  lea     rax, [rbp+90h+var_68]
0x18000e461  mov     [rsp+230h+var_188], rax
0x18000e469  lea     rax, [rbp+90h+var_10B]
0x18000e46d  mov     [rsp+230h+var_190], rax
0x18000e475  lea     rax, [rbp+90h+var_D8]
0x18000e479  mov     [rsp+230h+var_198], rax
0x18000e481  lea     rax, [rbp+90h+var_58]
0x18000e485  mov     [rsp+230h+var_1A0], rax
0x18000e48d  lea     rax, [rbp+90h+var_10A]
0x18000e491  mov     [rsp+230h+var_1A8], rax
0x18000e499  lea     rax, [rbp+90h+var_D0]
0x18000e49d  mov     [rsp+230h+var_1B0], rax
0x18000e4a5  lea     rax, [rbp+90h+var_48]
0x18000e4a9  mov     [rsp+230h+var_1B8], rax
0x18000e4ae  lea     rax, [rbp+90h+var_109]
0x18000e4b2  mov     [rsp+230h+var_1C0], rax
0x18000e4b7  lea     rax, [rbp+90h+var_C8]
0x18000e4bb  mov     [rsp+230h+var_1C8], rax
0x18000e4c0  lea     rax, [rbp+90h+var_38]
0x18000e4c4  mov     [rsp+230h+var_1D0], rax
0x18000e4c9  lea     rax, [rbp+90h+var_108]
0x18000e4cd  mov     [rsp+230h+var_1D8], rax
0x18000e4d2  lea     rax, [rbp+90h+var_C0]
0x18000e4d6  mov     [rsp+230h+var_1E0], rax
0x18000e4db  lea     rax, [rbp+90h+var_28]
0x18000e4df  mov     [rsp+230h+var_1E8], rax
0x18000e4e4  lea     rax, [rbp+90h+var_B8]
0x18000e4e8  mov     [rsp+230h+var_1F0], rax
0x18000e4ed  lea     rax, [rbp+90h+var_107]
0x18000e4f1  mov     [rsp+230h+var_1F8], rax
0x18000e4f6  lea     rax, [rbp+90h+var_100]
0x18000e4fa  mov     [rsp+230h+var_200], rax
0x18000e4ff  lea     rax, [rbp+90h+var_FC]
0x18000e503  mov     [rsp+230h+var_208], rax
0x18000e508  lea     rax, [rbp+90h+var_B0]
0x18000e50c  mov     [rsp+230h+var_210], rax
0x18000e511  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x18000e516  xorps   xmm0, xmm0
0x18000e519  xor     eax, eax
0x18000e51b  movups  xmmword ptr [rdi+110h], xmm0
0x18000e522  movups  xmmword ptr [rdi+120h], xmm0
0x18000e529  mov     [rdi+130h], rax
0x18000e530  xor     ebx, ebx
0x18000e532  mov     edx, ebx
0x18000e534  mov     rcx, rdi
0x18000e537  call    FlushLookUpTableBucket
0x18000e53c  inc     ebx
0x18000e53e  cmp     ebx, 20h ; ' '
0x18000e541  jb      short loc_18000E532
0x18000e543  mov     rbx, [rsp+230h+arg_8]
0x18000e54b  mov     rcx, [rbp+90h+var_8]
0x18000e552  xor     rcx, rsp; StackCookie
0x18000e555  call    __security_check_cookie
0x18000e55a  mov     rdi, [rsp+230h+arg_10]
0x18000e562  add     rsp, 230h
0x18000e569  pop     rbp
0x18000e56a  retn
```
