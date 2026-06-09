# LookUpTableFlushComplete

- ea: `0x18000b280`
- end: `0x18000b602`
- name: `LookUpTableFlushComplete`
- size: `898`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000b230`
- `0x18000b6b0`
- `0x18000b710`
- `0x18000b8dc`

## callees

- `0x180001270`
- `0x180001dc0`
- `0x18000b16c`
- `0x18000b280`
- `0x18000b788`

## pseudocode

```c
__int64 __fastcall LookUpTableFlushComplete(__int64 a1)
{
  unsigned int v1; // edi
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 result; // rax
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

  v1 = 0;
  if ( *(_DWORD *)(a1 + 256) )
  {
    UpdateInternalStatsOnFlush();
    if ( *(_QWORD *)(v5 + 272) )
    {
      if ( (unsigned int)dword_180013038 > 5
        && (qword_180013048 & 0x200000000000LL) != 0
        && (qword_180013050 & 0x200000000000LL) == qword_180013050 )
      {
        v9 = 4;
        v35 = 42;
        v32 = L"SummaryCount";
        v33 = 24;
        v22 = *(unsigned int *)(a1 + 308);
        v34 = L"NumLargeEventFailures";
        v23 = *(unsigned int *)(a1 + 304);
        v36 = L"NumAllocationFailures";
        v24 = *(unsigned int *)(a1 + 300);
        v38 = L"NumBucketLimitReached";
        v25 = *(unsigned int *)(a1 + 296);
        v40 = L"MinEntriesFlushed";
        v26 = *(unsigned int *)(a1 + 292);
        v42 = L"MaxEntriesFlushed";
        v27 = *(_QWORD *)(a1 + 272);
        v44 = L"TotalEntriesFlushed";
        v45 = 38;
        v28 = *(unsigned int *)(a1 + 288);
        v46 = L"MaxEntriesStored";
        v29 = *(_QWORD *)(a1 + 280);
        v48 = L"NumFlushes";
        v49 = 20;
        v6 = *(_QWORD *)(a1 + 328);
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
        v7 = *(_QWORD *)(v6 + 8);
        v30 = &v50;
        v50 = *(_OWORD *)(v7 - 16);
        v18[0] = 0;
        v20 = -1;
        v21 = 300;
        v31 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          v7,
          (__int64)word_18000F902,
          v3,
          v4,
          (__int64)&v31,
          (__int64)&v21,
          (__int64)&v20,
          (__int64)v18,
          (__int64 *)&v30,
          (__int64 *)&v48,
          (__int64)&v29,
          (__int64)&v17,
          (__int64 *)&v46,
          (__int64)&v28,
          (__int64)&v16,
          (__int64 *)&v44,
          (__int64)&v27,
          (__int64)&v15,
          (__int64 *)&v42,
          (__int64)&v26,
          (__int64)&v14,
          (__int64 *)&v40,
          (__int64)&v25,
          (__int64)&v13,
          (__int64 *)&v38,
          (__int64)&v24,
          (__int64)&v12,
          (__int64 *)&v36,
          (__int64)&v23,
          (__int64)&v11,
          (__int64 *)&v34,
          (__int64)&v22,
          (__int64)&v10,
          (__int64 *)&v32,
          (__int64)&v19,
          (__int64)&v9);
      }
      *(_OWORD *)(a1 + 272) = 0;
      *(_OWORD *)(a1 + 288) = 0;
      *(_QWORD *)(a1 + 304) = 0;
    }
    do
      result = FlushLookUpTableBucket(a1, v1++);
    while ( v1 < 0x20 );
  }
  return result;
}

```

## disassembly

```asm
0x18000b280  push    rbp
0x18000b282  push    rbx
0x18000b283  push    rsi
0x18000b284  push    rdi
0x18000b285  lea     rbp, [rsp-98h]
0x18000b28d  sub     rsp, 238h
0x18000b294  mov     rax, cs:__security_cookie
0x18000b29b  xor     rax, rsp
0x18000b29e  mov     [rbp+0B0h+var_28], rax
0x18000b2a5  mov     edx, [rcx+100h]
0x18000b2ab  xor     edi, edi
0x18000b2ad  mov     rbx, rcx
0x18000b2b0  test    edx, edx
0x18000b2b2  jz      loc_18000B5E7
0x18000b2b8  call    UpdateInternalStatsOnFlush
0x18000b2bd  lea     esi, [rdi+20h]
0x18000b2c0  cmp     [rcx+110h], rdi
0x18000b2c7  jz      loc_18000B5D7
0x18000b2cd  mov     eax, cs:dword_180013038
0x18000b2d3  cmp     eax, 5
0x18000b2d6  jbe     loc_18000B5BD
0x18000b2dc  mov     rcx, cs:qword_180013050
0x18000b2e3  mov     rdx, 200000000000h
0x18000b2ed  mov     rax, cs:qword_180013048
0x18000b2f4  test    rdx, rax
0x18000b2f7  jz      loc_18000B5BD
0x18000b2fd  mov     rax, rcx
0x18000b300  and     rax, rdx
0x18000b303  cmp     rax, rcx
0x18000b306  jnz     loc_18000B5BD
0x18000b30c  lea     ecx, [rdi+2Ah]
0x18000b30f  mov     [rbp+0B0h+var_130], 4
0x18000b313  lea     rax, aSummarycount; "SummaryCount"
0x18000b31a  mov     [rbp+0B0h+var_B0], cx
0x18000b31e  mov     [rbp+0B0h+var_C8], rax
0x18000b322  lea     eax, [rdi+18h]
0x18000b325  mov     [rbp+0B0h+var_C0], ax
0x18000b329  mov     eax, [rbx+134h]
0x18000b32f  mov     [rbp+0B0h+var_118], rax
0x18000b333  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x18000b33a  mov     [rbp+0B0h+var_B8], rax
0x18000b33e  mov     eax, [rbx+130h]
0x18000b344  mov     [rbp+0B0h+var_110], rax
0x18000b348  lea     rax, aNumallocationf; "NumAllocationFailures"
0x18000b34f  mov     [rbp+0B0h+var_A8], rax
0x18000b353  mov     eax, [rbx+12Ch]
0x18000b359  mov     [rbp+0B0h+var_108], rax
0x18000b35d  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x18000b364  mov     [rbp+0B0h+var_98], rax
0x18000b368  mov     eax, [rbx+128h]
0x18000b36e  mov     [rbp+0B0h+var_100], rax
0x18000b372  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x18000b379  mov     [rbp+0B0h+var_88], rax
0x18000b37d  mov     eax, [rbx+124h]
0x18000b383  mov     [rbp+0B0h+var_F8], rax
0x18000b387  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x18000b38e  mov     [rbp+0B0h+var_78], rax
0x18000b392  mov     rax, [rbx+110h]
0x18000b399  mov     [rbp+0B0h+var_F0], rax
0x18000b39d  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x18000b3a4  mov     [rbp+0B0h+var_68], rax
0x18000b3a8  lea     eax, [rdi+26h]
0x18000b3ab  mov     [rbp+0B0h+var_60], ax
0x18000b3af  mov     eax, [rbx+120h]
0x18000b3b5  mov     [rbp+0B0h+var_E8], rax
0x18000b3b9  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x18000b3c0  mov     [rbp+0B0h+var_58], rax
0x18000b3c4  mov     rax, [rbx+118h]
0x18000b3cb  mov     [rbp+0B0h+var_E0], rax
0x18000b3cf  lea     rax, aNumflushes; "NumFlushes"
0x18000b3d6  mov     [rbp+0B0h+var_48], rax
0x18000b3da  lea     eax, [rdi+14h]
0x18000b3dd  mov     [rbp+0B0h+var_40], ax
0x18000b3e1  mov     rax, [rbx+148h]
0x18000b3e8  mov     [rbp+0B0h+var_A0], cx
0x18000b3ec  mov     [rbp+0B0h+var_90], cx
0x18000b3f0  lea     ecx, [rdi+22h]
0x18000b3f3  mov     [rbp+0B0h+var_124], 1
0x18000b3fa  mov     [rbp+0B0h+var_12F], 4
0x18000b3fe  mov     [rbp+0B0h+var_12E], 4
0x18000b402  mov     [rbp+0B0h+var_12D], 4
0x18000b406  mov     [rbp+0B0h+var_12C], 4
0x18000b40a  mov     [rbp+0B0h+var_80], cx
0x18000b40e  mov     [rbp+0B0h+var_12B], 4
0x18000b412  mov     [rbp+0B0h+var_70], cx
0x18000b416  mov     [rbp+0B0h+var_12A], 4
0x18000b41a  mov     [rbp+0B0h+var_129], 4
0x18000b41e  mov     [rbp+0B0h+var_50], si
0x18000b422  mov     [rbp+0B0h+var_128], 4
0x18000b426  mov     rcx, [rax+8]
0x18000b42a  lea     rax, [rbp+0B0h+var_38]
0x18000b42e  mov     [rbp+0B0h+var_D8], rax
0x18000b432  lea     rax, [rbp+0B0h+var_130]
0x18000b436  mov     [rsp+250h+var_138], rax
0x18000b43e  lea     rax, [rbp+0B0h+var_124]
0x18000b442  mov     [rsp+250h+var_140], rax
0x18000b44a  lea     rax, [rbp+0B0h+var_C8]
0x18000b44e  movups  xmm0, xmmword ptr [rcx-10h]
0x18000b452  mov     [rsp+250h+var_148], rax
0x18000b45a  lea     rax, [rbp+0B0h+var_12F]
0x18000b45e  mov     [rsp+250h+var_150], rax
0x18000b466  lea     rax, [rbp+0B0h+var_118]
0x18000b46a  mov     [rsp+250h+var_158], rax
0x18000b472  lea     rax, [rbp+0B0h+var_B8]
0x18000b476  mov     [rsp+250h+var_160], rax
0x18000b47e  lea     rax, [rbp+0B0h+var_12E]
0x18000b482  movdqu  [rbp+0B0h+var_38], xmm0
0x18000b487  mov     [rbp+0B0h+var_127], dil
0x18000b48b  mov     [rbp+0B0h+var_120], 0FFFFFFFFh
0x18000b492  mov     [rbp+0B0h+var_11C], 12Ch
0x18000b499  mov     [rbp+0B0h+var_D0], 1000000h
0x18000b4a1  mov     [rsp+250h+var_168], rax
0x18000b4a9  lea     rdx, word_18000F902
0x18000b4b0  lea     rax, [rbp+0B0h+var_110]
0x18000b4b4  mov     [rsp+250h+var_170], rax
0x18000b4bc  lea     rax, [rbp+0B0h+var_A8]
0x18000b4c0  mov     [rsp+250h+var_178], rax
0x18000b4c8  lea     rax, [rbp+0B0h+var_12D]
0x18000b4cc  mov     [rsp+250h+var_180], rax
0x18000b4d4  lea     rax, [rbp+0B0h+var_108]
0x18000b4d8  mov     [rsp+250h+var_188], rax
0x18000b4e0  lea     rax, [rbp+0B0h+var_98]
0x18000b4e4  mov     [rsp+250h+var_190], rax
0x18000b4ec  lea     rax, [rbp+0B0h+var_12C]
0x18000b4f0  mov     [rsp+250h+var_198], rax
0x18000b4f8  lea     rax, [rbp+0B0h+var_100]
0x18000b4fc  mov     [rsp+250h+var_1A0], rax
0x18000b504  lea     rax, [rbp+0B0h+var_88]
0x18000b508  mov     [rsp+250h+var_1A8], rax
0x18000b510  lea     rax, [rbp+0B0h+var_12B]
0x18000b514  mov     [rsp+250h+var_1B0], rax
0x18000b51c  lea     rax, [rbp+0B0h+var_F8]
0x18000b520  mov     [rsp+250h+var_1B8], rax
0x18000b528  lea     rax, [rbp+0B0h+var_78]
0x18000b52c  mov     [rsp+250h+var_1C0], rax
0x18000b534  lea     rax, [rbp+0B0h+var_12A]
0x18000b538  mov     [rsp+250h+var_1C8], rax
0x18000b540  lea     rax, [rbp+0B0h+var_F0]
0x18000b544  mov     [rsp+250h+var_1D0], rax
0x18000b54c  lea     rax, [rbp+0B0h+var_68]
0x18000b550  mov     [rsp+250h+var_1D8], rax
0x18000b555  lea     rax, [rbp+0B0h+var_129]
0x18000b559  mov     [rsp+250h+var_1E0], rax
0x18000b55e  lea     rax, [rbp+0B0h+var_E8]
0x18000b562  mov     [rsp+250h+var_1E8], rax
0x18000b567  lea     rax, [rbp+0B0h+var_58]
0x18000b56b  mov     [rsp+250h+var_1F0], rax
0x18000b570  lea     rax, [rbp+0B0h+var_128]
0x18000b574  mov     [rsp+250h+var_1F8], rax
0x18000b579  lea     rax, [rbp+0B0h+var_E0]
0x18000b57d  mov     [rsp+250h+var_200], rax
0x18000b582  lea     rax, [rbp+0B0h+var_48]
0x18000b586  mov     [rsp+250h+var_208], rax
0x18000b58b  lea     rax, [rbp+0B0h+var_D8]
0x18000b58f  mov     [rsp+250h+var_210], rax
0x18000b594  lea     rax, [rbp+0B0h+var_127]
0x18000b598  mov     [rsp+250h+var_218], rax
0x18000b59d  lea     rax, [rbp+0B0h+var_120]
0x18000b5a1  mov     [rsp+250h+var_220], rax
0x18000b5a6  lea     rax, [rbp+0B0h+var_11C]
0x18000b5aa  mov     [rsp+250h+var_228], rax
0x18000b5af  lea     rax, [rbp+0B0h+var_D0]
0x18000b5b3  mov     [rsp+250h+var_230], rax
0x18000b5b8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x18000b5bd  xorps   xmm0, xmm0
0x18000b5c0  xor     eax, eax
0x18000b5c2  movups  xmmword ptr [rbx+110h], xmm0
0x18000b5c9  movups  xmmword ptr [rbx+120h], xmm0
0x18000b5d0  mov     [rbx+130h], rax
0x18000b5d7  mov     edx, edi
0x18000b5d9  mov     rcx, rbx
0x18000b5dc  call    FlushLookUpTableBucket
0x18000b5e1  inc     edi
0x18000b5e3  cmp     edi, esi
0x18000b5e5  jb      short loc_18000B5D7
0x18000b5e7  mov     rcx, [rbp+0B0h+var_28]
0x18000b5ee  xor     rcx, rsp; StackCookie
0x18000b5f1  call    __security_check_cookie
0x18000b5f6  add     rsp, 238h
0x18000b5fd  pop     rdi
0x18000b5fe  pop     rsi
0x18000b5ff  pop     rbx
0x18000b600  pop     rbp
0x18000b601  retn
```
