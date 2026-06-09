# LookUpTableFlushComplete

- ea: `0x140092598`
- end: `0x140092976`
- name: `LookUpTableFlushComplete`
- size: `990`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140092a10`
- `0x140092aa0`
- `0x140092b10`
- `0x140092d54`

## callees

- `0x1400010ac`
- `0x140044d2c`
- `0x140045530`
- `0x140092598`

## pseudocode

```c
__int64 __fastcall LookUpTableFlushComplete(const __m128i *a1, __int64 a2, int a3, int a4)
{
  __int64 result; // rax
  unsigned int v5; // edi
  __int64 v7; // rax
  __int64 v8; // rcx
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
  v5 = 0;
  if ( (_DWORD)result )
  {
    if ( a1[19].m128i_i32[2] > (unsigned int)result || !a1[18].m128i_i64[1] )
      a1[19].m128i_i32[2] = result;
    if ( a1[19].m128i_i32[1] < (unsigned int)result )
      a1[19].m128i_i32[1] = result;
    a1[18] = _mm_add_epi64(
               _mm_unpacklo_epi64((__m128i)(unsigned __int64)result, (__m128i)1uLL),
               _mm_loadu_si128(a1 + 18));
    if ( a1[18].m128i_i64[0] )
    {
      if ( (unsigned int)dword_14006E850 > 5
        && (qword_14006E860 & 0x200000000000LL) != 0
        && (qword_14006E868 & 0x200000000000LL) == qword_14006E868 )
      {
        v9 = 4;
        v35 = 42;
        v32 = L"SummaryCount";
        v33 = 24;
        v22 = a1[20].m128i_u32[1];
        v34 = L"NumLargeEventFailures";
        v23 = a1[20].m128i_u32[0];
        v36 = L"NumAllocationFailures";
        v24 = a1[19].m128i_u32[3];
        v38 = L"NumBucketLimitReached";
        v25 = a1[19].m128i_u32[2];
        v40 = L"MinEntriesFlushed";
        v26 = a1[19].m128i_u32[1];
        v42 = L"MaxEntriesFlushed";
        v27 = a1[18].m128i_i64[0];
        v44 = L"TotalEntriesFlushed";
        v45 = 38;
        v28 = a1[19].m128i_u32[0];
        v46 = L"MaxEntriesStored";
        v29 = a1[18].m128i_i64[1];
        v48 = L"NumFlushes";
        v49 = 20;
        v7 = a1[21].m128i_i64[1];
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
        v47 = 32;
        v17 = 4;
        v8 = *(_QWORD *)(v7 + 8);
        v30 = &v50;
        v50 = *(_OWORD *)(v8 - 16);
        v18[0] = 0;
        v20 = -1;
        v21 = 300;
        v31 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          v8,
          (unsigned int)byte_14006743B,
          a3,
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
      a1[18] = 0;
      a1[19] = 0;
      a1[20].m128i_i64[0] = 0;
    }
    do
      result = FlushLookUpTableBucket(a1, v5++);
    while ( v5 < 0x20 );
  }
  return result;
}

```

## disassembly

```asm
0x140092598  mov     [rsp-8+arg_8], rbx
0x14009259d  mov     [rsp-8+arg_10], rsi
0x1400925a2  push    rbp
0x1400925a3  push    rdi
0x1400925a4  push    r14
0x1400925a6  lea     rbp, [rsp-90h]
0x1400925ae  sub     rsp, 230h
0x1400925b5  mov     rax, cs:__security_cookie
0x1400925bc  xor     rax, rsp
0x1400925bf  mov     [rbp+0A0h+var_18], rax
0x1400925c6  mov     eax, [rcx+100h]
0x1400925cc  xor     edi, edi
0x1400925ce  mov     rbx, rcx
0x1400925d1  test    eax, eax
0x1400925d3  jz      loc_14009294E
0x1400925d9  cmp     [rcx+138h], eax
0x1400925df  ja      short loc_1400925EA
0x1400925e1  cmp     [rcx+128h], rdi
0x1400925e8  jnz     short loc_1400925F0
0x1400925ea  mov     [rcx+138h], eax
0x1400925f0  cmp     [rcx+134h], eax
0x1400925f6  jnb     short loc_1400925FE
0x1400925f8  mov     [rcx+134h], eax
0x1400925fe  mov     esi, 1
0x140092603  movq    xmm1, rax
0x140092608  movq    xmm0, rsi
0x14009260d  lea     r14d, [rsi+1Fh]
0x140092611  punpcklqdq xmm1, xmm0
0x140092615  movdqu  xmm0, xmmword ptr [rcx+120h]
0x14009261d  paddq   xmm1, xmm0
0x140092621  movdqu  xmmword ptr [rcx+120h], xmm1
0x140092629  cmp     [rcx+120h], rdi
0x140092630  jz      loc_14009293D
0x140092636  mov     eax, cs:dword_14006E850
0x14009263c  cmp     eax, 5
0x14009263f  jbe     loc_140092923
0x140092645  mov     rcx, cs:qword_14006E868
0x14009264c  mov     rdx, 200000000000h
0x140092656  mov     rax, cs:qword_14006E860
0x14009265d  test    rdx, rax
0x140092660  jz      loc_140092923
0x140092666  mov     rax, rcx
0x140092669  and     rax, rdx
0x14009266c  cmp     rax, rcx
0x14009266f  jnz     loc_140092923
0x140092675  lea     ecx, [rsi+29h]
0x140092678  mov     [rbp+0A0h+var_120], 4
0x14009267c  lea     rax, aSummarycount; "SummaryCount"
0x140092683  mov     [rbp+0A0h+var_A0], cx
0x140092687  mov     [rbp+0A0h+var_B8], rax
0x14009268b  lea     eax, [rsi+17h]
0x14009268e  mov     [rbp+0A0h+var_B0], ax
0x140092692  mov     eax, [rbx+144h]
0x140092698  mov     [rbp+0A0h+var_108], rax
0x14009269c  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x1400926a3  mov     [rbp+0A0h+var_A8], rax
0x1400926a7  mov     eax, [rbx+140h]
0x1400926ad  mov     [rbp+0A0h+var_100], rax
0x1400926b1  lea     rax, aNumallocationf; "NumAllocationFailures"
0x1400926b8  mov     [rbp+0A0h+var_98], rax
0x1400926bc  mov     eax, [rbx+13Ch]
0x1400926c2  mov     [rbp+0A0h+var_F8], rax
0x1400926c6  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x1400926cd  mov     [rbp+0A0h+var_88], rax
0x1400926d1  mov     eax, [rbx+138h]
0x1400926d7  mov     [rbp+0A0h+var_F0], rax
0x1400926db  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x1400926e2  mov     [rbp+0A0h+var_78], rax
0x1400926e6  mov     eax, [rbx+134h]
0x1400926ec  mov     [rbp+0A0h+var_E8], rax
0x1400926f0  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x1400926f7  mov     [rbp+0A0h+var_68], rax
0x1400926fb  mov     rax, [rbx+120h]
0x140092702  mov     [rbp+0A0h+var_E0], rax
0x140092706  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x14009270d  mov     [rbp+0A0h+var_58], rax
0x140092711  lea     eax, [rsi+25h]
0x140092714  mov     [rbp+0A0h+var_50], ax
0x140092718  mov     eax, [rbx+130h]
0x14009271e  mov     [rbp+0A0h+var_D8], rax
0x140092722  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x140092729  mov     [rbp+0A0h+var_48], rax
0x14009272d  mov     rax, [rbx+128h]
0x140092734  mov     [rbp+0A0h+var_D0], rax
0x140092738  lea     rax, aNumflushes; "NumFlushes"
0x14009273f  mov     [rbp+0A0h+var_38], rax
0x140092743  lea     eax, [rsi+13h]
0x140092746  mov     [rbp+0A0h+var_30], ax
0x14009274a  mov     rax, [rbx+158h]
0x140092751  mov     [rbp+0A0h+var_90], cx
0x140092755  mov     [rbp+0A0h+var_80], cx
0x140092759  lea     ecx, [rsi+21h]
0x14009275c  mov     [rbp+0A0h+var_114], esi
0x14009275f  mov     [rbp+0A0h+var_11F], 4
0x140092763  mov     [rbp+0A0h+var_11E], 4
0x140092767  mov     [rbp+0A0h+var_11D], 4
0x14009276b  mov     [rbp+0A0h+var_11C], 4
0x14009276f  mov     [rbp+0A0h+var_70], cx
0x140092773  mov     [rbp+0A0h+var_11B], 4
0x140092777  mov     [rbp+0A0h+var_60], cx
0x14009277b  mov     [rbp+0A0h+var_11A], 4
0x14009277f  mov     [rbp+0A0h+var_119], 4
0x140092783  mov     [rbp+0A0h+var_40], r14w
0x140092788  mov     [rbp+0A0h+var_118], 4
0x14009278c  mov     rcx, [rax+8]
0x140092790  lea     rax, [rbp+0A0h+var_28]
0x140092794  mov     [rbp+0A0h+var_C8], rax
0x140092798  lea     rax, [rbp+0A0h+var_120]
0x14009279c  mov     [rsp+240h+var_128], rax
0x1400927a4  lea     rax, [rbp+0A0h+var_114]
0x1400927a8  mov     [rsp+240h+var_130], rax
0x1400927b0  lea     rax, [rbp+0A0h+var_B8]
0x1400927b4  movups  xmm0, xmmword ptr [rcx-10h]
0x1400927b8  mov     [rsp+240h+var_138], rax
0x1400927c0  lea     rax, [rbp+0A0h+var_11F]
0x1400927c4  mov     [rsp+240h+var_140], rax
0x1400927cc  lea     rax, [rbp+0A0h+var_108]
0x1400927d0  mov     [rsp+240h+var_148], rax
0x1400927d8  lea     rax, [rbp+0A0h+var_A8]
0x1400927dc  mov     [rsp+240h+var_150], rax
0x1400927e4  lea     rax, [rbp+0A0h+var_11E]
0x1400927e8  movdqu  [rbp+0A0h+var_28], xmm0
0x1400927ed  mov     [rbp+0A0h+var_117], dil
0x1400927f1  mov     [rbp+0A0h+var_110], 0FFFFFFFFh
0x1400927f8  mov     [rbp+0A0h+var_10C], 12Ch
0x1400927ff  mov     [rbp+0A0h+var_C0], 1000000h
0x140092807  mov     [rsp+240h+var_158], rax
0x14009280f  lea     rdx, byte_14006743B
0x140092816  lea     rax, [rbp+0A0h+var_100]
0x14009281a  mov     [rsp+240h+var_160], rax
0x140092822  lea     rax, [rbp+0A0h+var_98]
0x140092826  mov     [rsp+240h+var_168], rax
0x14009282e  lea     rax, [rbp+0A0h+var_11D]
0x140092832  mov     [rsp+240h+var_170], rax
0x14009283a  lea     rax, [rbp+0A0h+var_F8]
0x14009283e  mov     [rsp+240h+var_178], rax
0x140092846  lea     rax, [rbp+0A0h+var_88]
0x14009284a  mov     [rsp+240h+var_180], rax
0x140092852  lea     rax, [rbp+0A0h+var_11C]
0x140092856  mov     [rsp+240h+var_188], rax
0x14009285e  lea     rax, [rbp+0A0h+var_F0]
0x140092862  mov     [rsp+240h+var_190], rax
0x14009286a  lea     rax, [rbp+0A0h+var_78]
0x14009286e  mov     [rsp+240h+var_198], rax
0x140092876  lea     rax, [rbp+0A0h+var_11B]
0x14009287a  mov     [rsp+240h+var_1A0], rax
0x140092882  lea     rax, [rbp+0A0h+var_E8]
0x140092886  mov     [rsp+240h+var_1A8], rax
0x14009288e  lea     rax, [rbp+0A0h+var_68]
0x140092892  mov     [rsp+240h+var_1B0], rax
0x14009289a  lea     rax, [rbp+0A0h+var_11A]
0x14009289e  mov     [rsp+240h+var_1B8], rax
0x1400928a6  lea     rax, [rbp+0A0h+var_E0]
0x1400928aa  mov     [rsp+240h+var_1C0], rax
0x1400928b2  lea     rax, [rbp+0A0h+var_58]
0x1400928b6  mov     [rsp+240h+var_1C8], rax
0x1400928bb  lea     rax, [rbp+0A0h+var_119]
0x1400928bf  mov     [rsp+240h+var_1D0], rax
0x1400928c4  lea     rax, [rbp+0A0h+var_D8]
0x1400928c8  mov     [rsp+240h+var_1D8], rax
0x1400928cd  lea     rax, [rbp+0A0h+var_48]
0x1400928d1  mov     [rsp+240h+var_1E0], rax
0x1400928d6  lea     rax, [rbp+0A0h+var_118]
0x1400928da  mov     [rsp+240h+var_1E8], rax
0x1400928df  lea     rax, [rbp+0A0h+var_D0]
0x1400928e3  mov     [rsp+240h+var_1F0], rax
0x1400928e8  lea     rax, [rbp+0A0h+var_38]
0x1400928ec  mov     [rsp+240h+var_1F8], rax
0x1400928f1  lea     rax, [rbp+0A0h+var_C8]
0x1400928f5  mov     [rsp+240h+var_200], rax
0x1400928fa  lea     rax, [rbp+0A0h+var_117]
0x1400928fe  mov     [rsp+240h+var_208], rax
0x140092903  lea     rax, [rbp+0A0h+var_110]
0x140092907  mov     [rsp+240h+var_210], rax
0x14009290c  lea     rax, [rbp+0A0h+var_10C]
0x140092910  mov     [rsp+240h+var_218], rax
0x140092915  lea     rax, [rbp+0A0h+var_C0]
0x140092919  mov     [rsp+240h+var_220], rax
0x14009291e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x140092923  xorps   xmm0, xmm0
0x140092926  xor     eax, eax
0x140092928  movups  xmmword ptr [rbx+120h], xmm0
0x14009292f  movups  xmmword ptr [rbx+130h], xmm0
0x140092936  mov     [rbx+140h], rax
0x14009293d  mov     edx, edi
0x14009293f  mov     rcx, rbx
0x140092942  call    FlushLookUpTableBucket
0x140092947  add     edi, esi
0x140092949  cmp     edi, r14d
0x14009294c  jb      short loc_14009293D
0x14009294e  mov     rcx, [rbp+0A0h+var_18]
0x140092955  xor     rcx, rsp; StackCookie
0x140092958  call    __security_check_cookie
0x14009295d  lea     r11, [rsp+240h+var_10]
0x140092965  mov     rbx, [r11+28h]
0x140092969  mov     rsi, [r11+30h]
0x14009296d  mov     rsp, r11
0x140092970  pop     r14
0x140092972  pop     rdi
0x140092973  pop     rbp
0x140092974  retn
```
