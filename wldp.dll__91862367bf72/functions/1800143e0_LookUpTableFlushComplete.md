# LookUpTableFlushComplete

- ea: `0x1800143e0`
- end: `0x18001491a`
- name: `LookUpTableFlushComplete`
- size: `1338`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800141b0`
- `0x180014360`
- `0x180018340`
- `0x18003dbe0`

## callees

- `0x1800024c0`
- `0x1800143e0`
- `0x180021ec0`
- `0x180022beb`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001482e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001482e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800147b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800147b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800148c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800148c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800148b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800148b3`

## pseudocode

```c
int __fastcall LookUpTableFlushComplete(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  unsigned __int64 v4; // rax
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 i; // r15
  __int64 v9; // rdi
  int v10; // r8d
  __int64 *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // r9
  __int64 v14; // rax
  __int64 *v15; // rcx
  REGHANDLE j; // r14
  PEVENT_DATA_DESCRIPTOR *v17; // rbx
  int v18; // eax
  __int64 v19; // rdx
  PEVENT_DATA_DESCRIPTOR v20; // rbx
  HANDLE ProcessHeap; // rax
  char v23; // [rsp+128h] [rbp-80h] BYREF
  char v24; // [rsp+129h] [rbp-7Fh] BYREF
  char v25; // [rsp+12Ah] [rbp-7Eh] BYREF
  char v26; // [rsp+12Bh] [rbp-7Dh] BYREF
  char v27; // [rsp+12Ch] [rbp-7Ch] BYREF
  char v28; // [rsp+12Dh] [rbp-7Bh] BYREF
  char v29; // [rsp+12Eh] [rbp-7Ah] BYREF
  char v30; // [rsp+12Fh] [rbp-79h] BYREF
  char v31; // [rsp+130h] [rbp-78h] BYREF
  char v32[3]; // [rsp+131h] [rbp-77h] BYREF
  int v33; // [rsp+134h] [rbp-74h] BYREF
  int v34; // [rsp+138h] [rbp-70h] BYREF
  int v35; // [rsp+13Ch] [rbp-6Ch] BYREF
  __int64 v36; // [rsp+140h] [rbp-68h] BYREF
  __int64 v37; // [rsp+148h] [rbp-60h] BYREF
  __int64 v38; // [rsp+150h] [rbp-58h] BYREF
  __int64 v39; // [rsp+158h] [rbp-50h] BYREF
  __int64 v40; // [rsp+160h] [rbp-48h] BYREF
  __int64 v41; // [rsp+168h] [rbp-40h] BYREF
  __int64 v42; // [rsp+170h] [rbp-38h] BYREF
  __int64 v43; // [rsp+178h] [rbp-30h] BYREF
  __int128 *v44; // [rsp+180h] [rbp-28h] BYREF
  __int64 v45; // [rsp+188h] [rbp-20h] BYREF
  const wchar_t *v46; // [rsp+190h] [rbp-18h] BYREF
  __int16 v47; // [rsp+198h] [rbp-10h]
  const wchar_t *v48; // [rsp+1A0h] [rbp-8h] BYREF
  __int16 v49; // [rsp+1A8h] [rbp+0h]
  const wchar_t *v50; // [rsp+1B0h] [rbp+8h] BYREF
  __int16 v51; // [rsp+1B8h] [rbp+10h]
  const wchar_t *v52; // [rsp+1C0h] [rbp+18h] BYREF
  __int16 v53; // [rsp+1C8h] [rbp+20h]
  const wchar_t *v54; // [rsp+1D0h] [rbp+28h] BYREF
  __int16 v55; // [rsp+1D8h] [rbp+30h]
  const wchar_t *v56; // [rsp+1E0h] [rbp+38h] BYREF
  __int16 v57; // [rsp+1E8h] [rbp+40h]
  const wchar_t *v58; // [rsp+1F0h] [rbp+48h] BYREF
  __int16 v59; // [rsp+1F8h] [rbp+50h]
  const wchar_t *v60; // [rsp+200h] [rbp+58h] BYREF
  __int16 v61; // [rsp+208h] [rbp+60h]
  const wchar_t *v62; // [rsp+210h] [rbp+68h] BYREF
  __int16 v63; // [rsp+218h] [rbp+70h]
  __int128 v64; // [rsp+220h] [rbp+78h] BYREF

  v4 = *(unsigned int *)(a1 + 256);
  if ( (_DWORD)v4 )
  {
    if ( *(_DWORD *)(a1 + 296) > (unsigned int)v4 || !*(_QWORD *)(a1 + 280) )
      *(_DWORD *)(a1 + 296) = v4;
    if ( *(_DWORD *)(a1 + 292) < (unsigned int)v4 )
      *(_DWORD *)(a1 + 292) = v4;
    *(__m128i *)(a1 + 272) = _mm_add_epi64(
                               _mm_unpacklo_epi64((__m128i)v4, (__m128i)1uLL),
                               _mm_loadu_si128((const __m128i *)(a1 + 272)));
    if ( *(_QWORD *)(a1 + 272) )
    {
      if ( (unsigned int)dword_18005A340 > 5
        && (qword_18005A350 & 0x200000000000LL) != 0
        && (qword_18005A358 & 0x200000000000LL) == qword_18005A358 )
      {
        v23 = 4;
        v49 = 42;
        v46 = L"SummaryCount";
        v47 = 24;
        v45 = *(unsigned int *)(a1 + 308);
        v48 = L"NumLargeEventFailures";
        v37 = *(unsigned int *)(a1 + 304);
        v50 = L"NumAllocationFailures";
        v38 = *(unsigned int *)(a1 + 300);
        v52 = L"NumBucketLimitReached";
        v39 = *(unsigned int *)(a1 + 296);
        v54 = L"MinEntriesFlushed";
        v40 = *(unsigned int *)(a1 + 292);
        v56 = L"MaxEntriesFlushed";
        v41 = *(_QWORD *)(a1 + 272);
        v58 = L"TotalEntriesFlushed";
        v59 = 38;
        v42 = *(unsigned int *)(a1 + 288);
        v60 = L"MaxEntriesStored";
        v61 = 32;
        v43 = *(_QWORD *)(a1 + 280);
        v62 = L"NumFlushes";
        v63 = 20;
        v6 = *(_QWORD *)(a1 + 328);
        v51 = 42;
        v53 = 42;
        v33 = 1;
        v24 = 4;
        v25 = 4;
        v26 = 4;
        v27 = 4;
        v55 = 34;
        v28 = 4;
        v57 = 34;
        v29 = 4;
        v30 = 4;
        v31 = 4;
        v7 = *(_QWORD *)(v6 + 8);
        v44 = &v64;
        v64 = *(_OWORD *)(v7 - 16);
        v32[0] = 0;
        v34 = -1;
        v35 = 300;
        v36 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          v7,
          (unsigned int)byte_180050139,
          1,
          a4,
          (__int64)&v36,
          (__int64)&v35,
          (__int64)&v34,
          (__int64)v32,
          (__int64)&v44,
          (__int64)&v62,
          (__int64)&v43,
          (__int64)&v31,
          (__int64)&v60,
          (__int64)&v42,
          (__int64)&v30,
          (__int64)&v58,
          (__int64)&v41,
          (__int64)&v29,
          (__int64)&v56,
          (__int64)&v40,
          (__int64)&v28,
          (__int64)&v54,
          (__int64)&v39,
          (__int64)&v27,
          (__int64)&v52,
          (__int64)&v38,
          (__int64)&v26,
          (__int64)&v50,
          (__int64)&v37,
          (__int64)&v25,
          (__int64)&v48,
          (__int64)&v45,
          (__int64)&v24,
          (__int64)&v46,
          (__int64)&v33,
          (__int64)&v23);
      }
      LODWORD(v4) = 0;
      *(_OWORD *)(a1 + 272) = 0;
      *(_OWORD *)(a1 + 288) = 0;
      *(_QWORD *)(a1 + 304) = 0;
    }
    for ( i = 0; i != 32; ++i )
    {
      if ( *(_QWORD *)(a1 + 8 * i) )
      {
        AcquireSRWLockExclusive((PSRWLOCK)(a1 + 264));
        v9 = *(_QWORD *)(a1 + 8 * i);
        v10 = 0;
        *(_QWORD *)(a1 + 8 * i) = 0;
        v36 = v9;
        if ( v9 )
        {
          v11 = &v36;
          v12 = v9;
          do
          {
            v13 = *(_QWORD *)(v12 + 32);
            *(_QWORD *)(v12 + 32) = 0;
            v11 = (__int64 *)(*v11 + 24);
            v14 = *v11;
            if ( *v11 )
            {
              do
              {
                v15 = (__int64 *)(v14 + 32);
                v14 = *(_QWORD *)(v14 + 32);
              }
              while ( v14 );
            }
            else
            {
              v15 = v11;
            }
            *v15 = v13;
            ++v10;
            v12 = *v11;
          }
          while ( *v11 );
        }
        *(_DWORD *)(a1 + 256) -= v10;
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 264));
        v4 = *(_QWORD *)(a1 + 328);
        for ( j = *(_QWORD *)(v4 + 32); v9; LODWORD(v4) = HeapFree(ProcessHeap, 0, v20) )
        {
          v17 = (PEVENT_DATA_DESCRIPTOR *)(v9 + 16);
          v18 = 2;
          if ( (unsigned int)*(unsigned __int8 *)(v9 + 45) + 2 > 2 )
          {
            do
            {
              v19 = v18++;
              (*v17)[v19].Reserved1 = 0;
            }
            while ( v18 < *(unsigned __int8 *)(v9 + 45) + 2 );
          }
          EventWriteTransfer_0(j, (PCEVENT_DESCRIPTOR)v9, 0, 0, *(unsigned __int8 *)(v9 + 44), *v17);
          v9 = *(_QWORD *)(v9 + 24);
          v20 = *v17;
          ProcessHeap = GetProcessHeap();
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800143e0  mov     r11, rsp
0x1800143e3  push    rbp
0x1800143e4  push    rsi
0x1800143e5  lea     rbp, [r11-0B8h]
0x1800143ec  sub     rsp, 248h
0x1800143f3  mov     rax, cs:__security_cookie
0x1800143fa  xor     rax, rsp
0x1800143fd  mov     [rbp+0B0h+var_28], rax
0x180014404  mov     eax, [rcx+100h]
0x18001440a  mov     rsi, rcx
0x18001440d  test    eax, eax
0x18001440f  jz      loc_180014901
0x180014415  mov     [r11+10h], rbx
0x180014419  mov     [r11+18h], rdi
0x18001441d  mov     [r11-18h], r12
0x180014421  mov     [r11-20h], r14
0x180014425  mov     [r11-28h], r15
0x180014429  cmp     [rcx+128h], eax
0x18001442f  ja      short loc_18001443B
0x180014431  cmp     qword ptr [rcx+118h], 0
0x180014439  jnz     short loc_180014441
0x18001443b  mov     [rcx+128h], eax
0x180014441  cmp     [rcx+124h], eax
0x180014447  jnb     short loc_18001444F
0x180014449  mov     [rcx+124h], eax
0x18001444f  mov     r8d, 1
0x180014455  movq    xmm1, rax
0x18001445a  movq    xmm0, r8
0x18001445f  punpcklqdq xmm1, xmm0
0x180014463  movdqu  xmm0, xmmword ptr [rcx+110h]
0x18001446b  paddq   xmm1, xmm0
0x18001446f  movdqu  xmmword ptr [rcx+110h], xmm1
0x180014477  cmp     qword ptr [rcx+110h], 0
0x18001447f  jz      loc_18001479A
0x180014485  mov     eax, cs:dword_18005A340
0x18001448b  cmp     eax, 5
0x18001448e  jbe     loc_180014780
0x180014494  mov     rcx, cs:qword_18005A358
0x18001449b  mov     rdx, 200000000000h
0x1800144a5  mov     rax, cs:qword_18005A350
0x1800144ac  test    rdx, rax
0x1800144af  jz      loc_180014780
0x1800144b5  mov     rax, rcx
0x1800144b8  and     rax, rdx
0x1800144bb  cmp     rax, rcx
0x1800144be  jnz     loc_180014780
0x1800144c4  mov     ecx, 2Ah ; '*'
0x1800144c9  mov     [rbp+0B0h+var_130], 4
0x1800144cd  lea     rax, aSummarycount; "SummaryCount"
0x1800144d4  mov     [rbp+0B0h+var_B0], cx
0x1800144d8  mov     [rbp+0B0h+var_C8], rax
0x1800144dc  mov     eax, 18h
0x1800144e1  mov     [rbp+0B0h+var_C0], ax
0x1800144e5  mov     eax, [rsi+134h]
0x1800144eb  mov     [rbp+0B0h+var_D0], rax
0x1800144ef  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x1800144f6  mov     [rbp+0B0h+var_B8], rax
0x1800144fa  mov     eax, [rsi+130h]
0x180014500  mov     [rbp+0B0h+var_110], rax
0x180014504  lea     rax, aNumallocationf; "NumAllocationFailures"
0x18001450b  mov     [rbp+0B0h+var_A8], rax
0x18001450f  mov     eax, [rsi+12Ch]
0x180014515  mov     [rbp+0B0h+var_108], rax
0x180014519  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x180014520  mov     [rbp+0B0h+var_98], rax
0x180014524  mov     eax, [rsi+128h]
0x18001452a  mov     [rbp+0B0h+var_100], rax
0x18001452e  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x180014535  mov     [rbp+0B0h+var_88], rax
0x180014539  mov     eax, [rsi+124h]
0x18001453f  mov     [rbp+0B0h+var_F8], rax
0x180014543  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x18001454a  mov     [rbp+0B0h+var_78], rax
0x18001454e  mov     rax, [rsi+110h]
0x180014555  mov     [rbp+0B0h+var_F0], rax
0x180014559  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x180014560  mov     [rbp+0B0h+var_68], rax
0x180014564  mov     eax, 26h ; '&'
0x180014569  mov     [rbp+0B0h+var_60], ax
0x18001456d  mov     eax, [rsi+120h]
0x180014573  mov     [rbp+0B0h+var_E8], rax
0x180014577  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x18001457e  mov     [rbp+0B0h+var_58], rax
0x180014582  mov     eax, 20h ; ' '
0x180014587  mov     [rbp+0B0h+var_50], ax
0x18001458b  mov     rax, [rsi+118h]
0x180014592  mov     [rbp+0B0h+var_E0], rax
0x180014596  lea     rax, aNumflushes; "NumFlushes"
0x18001459d  mov     [rbp+0B0h+var_48], rax
0x1800145a1  mov     eax, 14h
0x1800145a6  mov     [rbp+0B0h+var_40], ax
0x1800145aa  mov     rax, [rsi+148h]
0x1800145b1  mov     [rbp+0B0h+var_A0], cx
0x1800145b5  mov     [rbp+0B0h+var_90], cx
0x1800145b9  mov     ecx, 22h ; '"'
0x1800145be  mov     [rbp+0B0h+var_124], r8d
0x1800145c2  mov     [rbp+0B0h+var_12F], 4
0x1800145c6  mov     [rbp+0B0h+var_12E], 4
0x1800145ca  mov     [rbp+0B0h+var_12D], 4
0x1800145ce  mov     [rbp+0B0h+var_12C], 4
0x1800145d2  mov     [rbp+0B0h+var_80], cx
0x1800145d6  mov     [rbp+0B0h+var_12B], 4
0x1800145da  mov     [rbp+0B0h+var_70], cx
0x1800145de  mov     [rbp+0B0h+var_12A], 4
0x1800145e2  mov     [rbp+0B0h+var_129], 4
0x1800145e6  mov     [rbp+0B0h+var_128], 4
0x1800145ea  mov     rcx, [rax+8]
0x1800145ee  lea     rax, [rbp+0B0h+var_38]
0x1800145f2  mov     [rbp+0B0h+var_D8], rax
0x1800145f6  lea     rax, [rbp+0B0h+var_130]
0x1800145fa  mov     [rsp+118h], rax
0x180014602  lea     rax, [rbp+0B0h+var_124]
0x180014606  mov     [rsp+250h+var_140], rax
0x18001460e  lea     rax, [rbp+0B0h+var_C8]
0x180014612  movups  xmm0, xmmword ptr [rcx-10h]
0x180014616  mov     [rsp+250h+var_148], rax
0x18001461e  lea     rax, [rbp+0B0h+var_12F]
0x180014622  mov     [rsp+250h+var_150], rax
0x18001462a  lea     rax, [rbp+0B0h+var_D0]
0x18001462e  mov     [rsp+250h+var_158], rax
0x180014636  lea     rax, [rbp+0B0h+var_B8]
0x18001463a  mov     [rsp+250h+var_160], rax
0x180014642  movups  [rbp+0B0h+var_38], xmm0
0x180014646  mov     [rbp+0B0h+var_127], 0
0x18001464a  mov     [rbp+0B0h+var_120], 0FFFFFFFFh
0x180014651  mov     [rbp+0B0h+var_11C], 12Ch
0x180014658  mov     [rbp+0B0h+var_118], 1000000h
0x180014660  lea     rax, [rbp+0B0h+var_12E]
0x180014664  mov     [rsp+250h+var_168], rax
0x18001466c  lea     rdx, byte_180050139
0x180014673  lea     rax, [rbp+0B0h+var_110]
0x180014677  mov     [rsp+250h+var_170], rax
0x18001467f  lea     rax, [rbp+0B0h+var_A8]
0x180014683  mov     [rsp+250h+var_178], rax
0x18001468b  lea     rax, [rbp+0B0h+var_12D]
0x18001468f  mov     [rsp+250h+var_180], rax
0x180014697  lea     rax, [rbp+0B0h+var_108]
0x18001469b  mov     [rsp+250h+var_188], rax
0x1800146a3  lea     rax, [rbp+0B0h+var_98]
0x1800146a7  mov     [rsp+250h+var_190], rax
0x1800146af  lea     rax, [rbp+0B0h+var_12C]
0x1800146b3  mov     [rsp+250h+var_198], rax
0x1800146bb  lea     rax, [rbp+0B0h+var_100]
0x1800146bf  mov     [rsp+250h+var_1A0], rax
0x1800146c7  lea     rax, [rbp+0B0h+var_88]
0x1800146cb  mov     [rsp+250h+var_1A8], rax
0x1800146d3  lea     rax, [rbp+0B0h+var_12B]
0x1800146d7  mov     [rsp+250h+var_1B0], rax
0x1800146df  lea     rax, [rbp+0B0h+var_F8]
0x1800146e3  mov     [rsp+250h+var_1B8], rax
0x1800146eb  lea     rax, [rbp+0B0h+var_78]
0x1800146ef  mov     [rsp+250h+var_1C0], rax
0x1800146f7  lea     rax, [rbp+0B0h+var_12A]
0x1800146fb  mov     [rsp+250h+var_1C8], rax
0x180014703  lea     rax, [rbp+0B0h+var_F0]
0x180014707  mov     [rsp+250h+var_1D0], rax
0x18001470f  lea     rax, [rbp+0B0h+var_68]
0x180014713  mov     [rsp+250h+var_1D8], rax
0x180014718  lea     rax, [rbp+0B0h+var_129]
0x18001471c  mov     [rsp+250h+var_1E0], rax
0x180014721  lea     rax, [rbp+0B0h+var_E8]
0x180014725  mov     [rsp+250h+var_1E8], rax
0x18001472a  lea     rax, [rbp+0B0h+var_58]
0x18001472e  mov     [rsp+250h+var_1F0], rax
0x180014733  lea     rax, [rbp+0B0h+var_128]
0x180014737  mov     [rsp+250h+var_1F8], rax
0x18001473c  lea     rax, [rbp+0B0h+var_E0]
0x180014740  mov     [rsp+250h+var_200], rax
0x180014745  lea     rax, [rbp+0B0h+var_48]
0x180014749  mov     [rsp+250h+var_208], rax
0x18001474e  lea     rax, [rbp+0B0h+var_D8]
0x180014752  mov     [rsp+250h+var_210], rax
0x180014757  lea     rax, [rbp+0B0h+var_127]
0x18001475b  mov     [rsp+250h+var_218], rax
0x180014760  lea     rax, [rbp+0B0h+var_120]
0x180014764  mov     [rsp+250h+var_220], rax
0x180014769  lea     rax, [rbp+0B0h+var_11C]
0x18001476d  mov     [rsp+250h+UserData], rax
0x180014772  lea     rax, [rbp+0B0h+var_118]
0x180014776  mov     qword ptr [rsp+250h+UserDataCount], rax
0x18001477b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x180014780  xorps   xmm0, xmm0
0x180014783  xor     eax, eax
0x180014785  movups  xmmword ptr [rsi+110h], xmm0
0x18001478c  movups  xmmword ptr [rsi+120h], xmm0
0x180014793  mov     [rsi+130h], rax
0x18001479a  xor     r12d, r12d
0x18001479d  mov     r15d, r12d
0x1800147a0  cmp     [rsi+r15*8], r12
0x1800147a4  jz      loc_1800148CC
0x1800147aa  lea     rcx, [rsi+108h]; SRWLock
0x1800147b1  call    cs:__imp_AcquireSRWLockExclusive
0x1800147b7  mov     rdi, [rsi+r15*8]
0x1800147bb  mov     r8d, r12d
0x1800147be  mov     [rsi+r15*8], r12
0x1800147c2  mov     [rbp+0B0h+var_118], rdi
0x1800147c6  test    rdi, rdi
0x1800147c9  jz      short loc_180014820
0x1800147cb  lea     rdx, [rbp+0B0h+var_118]
0x1800147cf  mov     rax, rdi
0x1800147d2  nop     dword ptr [rax+00h]
0x1800147d6  nop     word ptr [rax+rax+00000000h]
0x1800147e0  mov     r9, [rax+20h]
0x1800147e4  mov     [rax+20h], r12
0x1800147e8  mov     rdx, [rdx]
0x1800147eb  add     rdx, 18h
0x1800147ef  mov     rax, [rdx]
0x1800147f2  test    rax, rax
0x1800147f5  jz      short loc_18001480F
0x1800147f7  nop     word ptr [rax+rax+00000000h]
0x180014800  lea     rcx, [rax+20h]
0x180014804  mov     rax, [rax+20h]
0x180014808  test    rax, rax
0x18001480b  jnz     short loc_180014800
0x18001480d  jmp     short loc_180014812
0x18001480f  mov     rcx, rdx
0x180014812  mov     [rcx], r9
0x180014815  inc     r8d
0x180014818  mov     rax, [rdx]
0x18001481b  test    rax, rax
0x18001481e  jnz     short loc_1800147E0
0x180014820  sub     [rsi+100h], r8d
0x180014827  lea     rcx, [rsi+108h]; SRWLock
0x18001482e  call    cs:__imp_ReleaseSRWLockExclusive
0x180014834  mov     rax, [rsi+148h]
0x18001483b  mov     r14, [rax+20h]
0x18001483f  test    rdi, rdi
0x180014842  jz      loc_1800148CC
0x180014848  nop     dword ptr [rax+rax+00000000h]
0x180014850  movzx   ecx, byte ptr [rdi+2Dh]
0x180014854  lea     rbx, [rdi+10h]
0x180014858  mov     eax, 2
0x18001485d  add     ecx, eax
0x18001485f  cmp     ecx, eax
0x180014861  jbe     short loc_18001488B
0x180014863  nop     dword ptr [rax+00h]
0x180014867  nop     word ptr [rax+rax+00000000h]
0x180014870  mov     rcx, [rbx]
0x180014873  movsxd  rdx, eax
0x180014876  inc     eax
0x180014878  add     rdx, rdx
0x18001487b  mov     [rcx+rdx*8+0Dh], r12b
0x180014880  movzx   ecx, byte ptr [rdi+2Dh]
0x180014884  add     ecx, 2
0x180014887  cmp     eax, ecx
0x180014889  jl      short loc_180014870
0x18001488b  movzx   ecx, byte ptr [rdi+2Ch]
0x18001488f  xor     r9d, r9d; RelatedActivityId
0x180014892  mov     rax, [rbx]
0x180014895  xor     r8d, r8d; ActivityId
0x180014898  mov     [rsp+250h+UserData], rax; UserData
0x18001489d  mov     rdx, rdi; EventDescriptor
0x1800148a0  mov     [rsp+250h+UserDataCount], ecx; UserDataCount
0x1800148a4  mov     rcx, r14; RegHandle
0x1800148a7  call    EventWriteTransfer_0
0x1800148ac  mov     rdi, [rdi+18h]
0x1800148b0  mov     rbx, [rbx]
0x1800148b3  call    cs:__imp_GetProcessHeap
0x1800148b9  mov     r8, rbx; lpMem
0x1800148bc  xor     edx, edx; dwFlags
0x1800148be  mov     rcx, rax; hHeap
0x1800148c1  call    cs:__imp_HeapFree
0x1800148c7  test    rdi, rdi
0x1800148ca  jnz     short loc_180014850
0x1800148cc  inc     r15
0x1800148cf  cmp     r15, 20h ; ' '
0x1800148d3  jnz     loc_1800147A0
0x1800148d9  mov     r15, [rsp+250h+var_20]
0x1800148e1  mov     r14, [rsp+250h+var_18]
0x1800148e9  mov     r12, [rsp+240h]
0x1800148f1  mov     rdi, [rsp+250h+arg_10]
0x1800148f9  mov     rbx, [rsp+250h+arg_8]
0x180014901  mov     rcx, [rbp+0B0h+var_28]
0x180014908  xor     rcx, rsp; StackCookie
0x18001490b  call    __security_check_cookie
0x180014910  add     rsp, 248h
0x180014917  pop     rsi
0x180014918  pop     rbp
0x180014919  retn
```
