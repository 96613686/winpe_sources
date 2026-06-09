# LookUpTableFlushComplete

- ea: `0x14003d61c`
- end: `0x14003d98d`
- name: `LookUpTableFlushComplete`
- size: `881`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000faf0`
- `0x140026070`
- `0x140026280`
- `0x14003d5a0`
- `0x14003d9f0`

## callees

- `0x140001008`
- `0x14000b72c`
- `0x14000f9d0`
- `0x140011560`
- `0x1400260f4`
- `0x14003d61c`

## pseudocode

```c
void __fastcall LookUpTableFlushComplete(__int64 a1)
{
  unsigned int v1; // edi
  __int64 v3; // rcx
  int v4; // r8d
  int v5; // r9d
  __int64 v6; // rax
  __int64 v7; // rcx
  char v8; // [rsp+120h] [rbp-80h] BYREF
  char v9; // [rsp+121h] [rbp-7Fh] BYREF
  char v10; // [rsp+122h] [rbp-7Eh] BYREF
  char v11; // [rsp+123h] [rbp-7Dh] BYREF
  char v12; // [rsp+124h] [rbp-7Ch] BYREF
  char v13; // [rsp+125h] [rbp-7Bh] BYREF
  char v14; // [rsp+126h] [rbp-7Ah] BYREF
  char v15; // [rsp+127h] [rbp-79h] BYREF
  char v16; // [rsp+128h] [rbp-78h] BYREF
  _BYTE v17[3]; // [rsp+129h] [rbp-77h] BYREF
  int v18; // [rsp+12Ch] [rbp-74h] BYREF
  int v19; // [rsp+130h] [rbp-70h] BYREF
  int v20; // [rsp+134h] [rbp-6Ch] BYREF
  __int64 v21; // [rsp+138h] [rbp-68h] BYREF
  __int64 v22; // [rsp+140h] [rbp-60h] BYREF
  __int64 v23; // [rsp+148h] [rbp-58h] BYREF
  __int64 v24; // [rsp+150h] [rbp-50h] BYREF
  __int64 v25; // [rsp+158h] [rbp-48h] BYREF
  __int64 v26; // [rsp+160h] [rbp-40h] BYREF
  __int64 v27; // [rsp+168h] [rbp-38h] BYREF
  __int64 v28; // [rsp+170h] [rbp-30h] BYREF
  __int128 *v29; // [rsp+178h] [rbp-28h] BYREF
  __int64 v30; // [rsp+180h] [rbp-20h] BYREF
  const wchar_t *v31; // [rsp+188h] [rbp-18h] BYREF
  __int16 v32; // [rsp+190h] [rbp-10h]
  const wchar_t *v33; // [rsp+198h] [rbp-8h] BYREF
  __int16 v34; // [rsp+1A0h] [rbp+0h]
  const wchar_t *v35; // [rsp+1A8h] [rbp+8h] BYREF
  __int16 v36; // [rsp+1B0h] [rbp+10h]
  const wchar_t *v37; // [rsp+1B8h] [rbp+18h] BYREF
  __int16 v38; // [rsp+1C0h] [rbp+20h]
  const wchar_t *v39; // [rsp+1C8h] [rbp+28h] BYREF
  __int16 v40; // [rsp+1D0h] [rbp+30h]
  const wchar_t *v41; // [rsp+1D8h] [rbp+38h] BYREF
  __int16 v42; // [rsp+1E0h] [rbp+40h]
  const wchar_t *v43; // [rsp+1E8h] [rbp+48h] BYREF
  __int16 v44; // [rsp+1F0h] [rbp+50h]
  const wchar_t *v45; // [rsp+1F8h] [rbp+58h] BYREF
  __int16 v46; // [rsp+200h] [rbp+60h]
  const wchar_t *v47; // [rsp+208h] [rbp+68h] BYREF
  __int16 v48; // [rsp+210h] [rbp+70h]
  __int128 v49; // [rsp+218h] [rbp+78h] BYREF

  v1 = 0;
  if ( *(_DWORD *)(a1 + 256) )
  {
    UpdateInternalStatsOnFlush();
    if ( *(_QWORD *)(v3 + 288) )
    {
      if ( (unsigned int)dword_140018048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140018048, 0x200000000000LL) )
      {
        v8 = 4;
        v34 = 42;
        v31 = L"SummaryCount";
        v32 = 24;
        v21 = *(unsigned int *)(a1 + 324);
        v33 = L"NumLargeEventFailures";
        v22 = *(unsigned int *)(a1 + 320);
        v35 = L"NumAllocationFailures";
        v23 = *(unsigned int *)(a1 + 316);
        v37 = L"NumBucketLimitReached";
        v24 = *(unsigned int *)(a1 + 312);
        v39 = L"MinEntriesFlushed";
        v25 = *(unsigned int *)(a1 + 308);
        v41 = L"MaxEntriesFlushed";
        v26 = *(_QWORD *)(a1 + 288);
        v43 = L"TotalEntriesFlushed";
        v44 = 38;
        v27 = *(unsigned int *)(a1 + 304);
        v45 = L"MaxEntriesStored";
        v28 = *(_QWORD *)(a1 + 296);
        v47 = L"NumFlushes";
        v48 = 20;
        v6 = *(_QWORD *)(a1 + 344);
        v36 = 42;
        v38 = 42;
        v18 = 1;
        v9 = 4;
        v10 = 4;
        v11 = 4;
        v12 = 4;
        v40 = 34;
        v13 = 4;
        v42 = 34;
        v14 = 4;
        v15 = 4;
        v46 = 32;
        v16 = 4;
        v7 = *(_QWORD *)(v6 + 8);
        v29 = &v49;
        v49 = *(_OWORD *)(v7 - 16);
        v17[0] = 0;
        v19 = -1;
        v20 = 300;
        v30 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          v7,
          (unsigned int)word_140014A0A,
          v4,
          v5,
          (__int64)&v30,
          (__int64)&v20,
          (__int64)&v19,
          (__int64)v17,
          (__int64)&v29,
          (__int64)&v47,
          (__int64)&v28,
          (__int64)&v16,
          (__int64)&v45,
          (__int64)&v27,
          (__int64)&v15,
          (__int64)&v43,
          (__int64)&v26,
          (__int64)&v14,
          (__int64)&v41,
          (__int64)&v25,
          (__int64)&v13,
          (__int64)&v39,
          (__int64)&v24,
          (__int64)&v12,
          (__int64)&v37,
          (__int64)&v23,
          (__int64)&v11,
          (__int64)&v35,
          (__int64)&v22,
          (__int64)&v10,
          (__int64)&v33,
          (__int64)&v21,
          (__int64)&v9,
          (__int64)&v31,
          (__int64)&v18,
          (__int64)&v8);
      }
      *(_OWORD *)(a1 + 288) = 0;
      *(_OWORD *)(a1 + 304) = 0;
      *(_QWORD *)(a1 + 320) = 0;
    }
    do
      FlushLookUpTableBucket(a1, v1++);
    while ( v1 < 0x20 );
  }
}

```

## disassembly

```asm
0x14003d61c  push    rbp
0x14003d61e  push    rbx
0x14003d61f  push    rsi
0x14003d620  push    rdi
0x14003d621  lea     rbp, [rsp-98h]
0x14003d629  sub     rsp, 238h
0x14003d630  mov     rax, cs:__security_cookie
0x14003d637  xor     rax, rsp
0x14003d63a  mov     [rbp+0B0h+var_28], rax
0x14003d641  mov     edx, [rcx+100h]
0x14003d647  xor     edi, edi
0x14003d649  mov     rbx, rcx
0x14003d64c  test    edx, edx
0x14003d64e  jz      loc_14003D971
0x14003d654  call    UpdateInternalStatsOnFlush
0x14003d659  lea     esi, [rdi+20h]
0x14003d65c  cmp     [rcx+120h], rdi
0x14003d663  jz      loc_14003D961
0x14003d669  mov     eax, cs:dword_140018048
0x14003d66f  cmp     eax, 5
0x14003d672  jbe     loc_14003D947
0x14003d678  mov     rdx, 200000000000h
0x14003d682  lea     rcx, dword_140018048
0x14003d689  call    _tlgKeywordOn
0x14003d68e  test    al, al
0x14003d690  jz      loc_14003D947
0x14003d696  lea     ecx, [rdi+2Ah]
0x14003d699  mov     [rbp+0B0h+var_130], 4
0x14003d69d  lea     rax, aSummarycount; "SummaryCount"
0x14003d6a4  mov     [rbp+0B0h+var_B0], cx
0x14003d6a8  mov     [rbp+0B0h+var_C8], rax
0x14003d6ac  lea     eax, [rdi+18h]
0x14003d6af  mov     [rbp+0B0h+var_C0], ax
0x14003d6b3  mov     eax, [rbx+144h]
0x14003d6b9  mov     [rbp+0B0h+var_118], rax
0x14003d6bd  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x14003d6c4  mov     [rbp+0B0h+var_B8], rax
0x14003d6c8  mov     eax, [rbx+140h]
0x14003d6ce  mov     [rbp+0B0h+var_110], rax
0x14003d6d2  lea     rax, aNumallocationf; "NumAllocationFailures"
0x14003d6d9  mov     [rbp+0B0h+var_A8], rax
0x14003d6dd  mov     eax, [rbx+13Ch]
0x14003d6e3  mov     [rbp+0B0h+var_108], rax
0x14003d6e7  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x14003d6ee  mov     [rbp+0B0h+var_98], rax
0x14003d6f2  mov     eax, [rbx+138h]
0x14003d6f8  mov     [rbp+0B0h+var_100], rax
0x14003d6fc  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x14003d703  mov     [rbp+0B0h+var_88], rax
0x14003d707  mov     eax, [rbx+134h]
0x14003d70d  mov     [rbp+0B0h+var_F8], rax
0x14003d711  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x14003d718  mov     [rbp+0B0h+var_78], rax
0x14003d71c  mov     rax, [rbx+120h]
0x14003d723  mov     [rbp+0B0h+var_F0], rax
0x14003d727  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x14003d72e  mov     [rbp+0B0h+var_68], rax
0x14003d732  lea     eax, [rdi+26h]
0x14003d735  mov     [rbp+0B0h+var_60], ax
0x14003d739  mov     eax, [rbx+130h]
0x14003d73f  mov     [rbp+0B0h+var_E8], rax
0x14003d743  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x14003d74a  mov     [rbp+0B0h+var_58], rax
0x14003d74e  mov     rax, [rbx+128h]
0x14003d755  mov     [rbp+0B0h+var_E0], rax
0x14003d759  lea     rax, aNumflushes; "NumFlushes"
0x14003d760  mov     [rbp+0B0h+var_48], rax
0x14003d764  lea     eax, [rdi+14h]
0x14003d767  mov     [rbp+0B0h+var_40], ax
0x14003d76b  mov     rax, [rbx+158h]
0x14003d772  mov     [rbp+0B0h+var_A0], cx
0x14003d776  mov     [rbp+0B0h+var_90], cx
0x14003d77a  lea     ecx, [rdi+22h]
0x14003d77d  mov     [rbp+0B0h+var_124], 1
0x14003d784  mov     [rbp+0B0h+var_12F], 4
0x14003d788  mov     [rbp+0B0h+var_12E], 4
0x14003d78c  mov     [rbp+0B0h+var_12D], 4
0x14003d790  mov     [rbp+0B0h+var_12C], 4
0x14003d794  mov     [rbp+0B0h+var_80], cx
0x14003d798  mov     [rbp+0B0h+var_12B], 4
0x14003d79c  mov     [rbp+0B0h+var_70], cx
0x14003d7a0  mov     [rbp+0B0h+var_12A], 4
0x14003d7a4  mov     [rbp+0B0h+var_129], 4
0x14003d7a8  mov     [rbp+0B0h+var_50], si
0x14003d7ac  mov     [rbp+0B0h+var_128], 4
0x14003d7b0  mov     rcx, [rax+8]
0x14003d7b4  lea     rax, [rbp+0B0h+var_38]
0x14003d7b8  mov     [rbp+0B0h+var_D8], rax
0x14003d7bc  lea     rax, [rbp+0B0h+var_130]
0x14003d7c0  mov     [rsp+250h+var_138], rax
0x14003d7c8  lea     rax, [rbp+0B0h+var_124]
0x14003d7cc  mov     [rsp+250h+var_140], rax
0x14003d7d4  lea     rax, [rbp+0B0h+var_C8]
0x14003d7d8  movups  xmm0, xmmword ptr [rcx-10h]
0x14003d7dc  mov     [rsp+250h+var_148], rax
0x14003d7e4  lea     rax, [rbp+0B0h+var_12F]
0x14003d7e8  mov     [rsp+250h+var_150], rax
0x14003d7f0  lea     rax, [rbp+0B0h+var_118]
0x14003d7f4  mov     [rsp+250h+var_158], rax
0x14003d7fc  lea     rax, [rbp+0B0h+var_B8]
0x14003d800  mov     [rsp+250h+var_160], rax
0x14003d808  lea     rax, [rbp+0B0h+var_12E]
0x14003d80c  movdqu  [rbp+0B0h+var_38], xmm0
0x14003d811  mov     [rbp+0B0h+var_127], dil
0x14003d815  mov     [rbp+0B0h+var_120], 0FFFFFFFFh
0x14003d81c  mov     [rbp+0B0h+var_11C], 12Ch
0x14003d823  mov     [rbp+0B0h+var_D0], 1000000h
0x14003d82b  mov     [rsp+250h+var_168], rax
0x14003d833  lea     rdx, word_140014A0A
0x14003d83a  lea     rax, [rbp+0B0h+var_110]
0x14003d83e  mov     [rsp+250h+var_170], rax
0x14003d846  lea     rax, [rbp+0B0h+var_A8]
0x14003d84a  mov     [rsp+250h+var_178], rax
0x14003d852  lea     rax, [rbp+0B0h+var_12D]
0x14003d856  mov     [rsp+250h+var_180], rax
0x14003d85e  lea     rax, [rbp+0B0h+var_108]
0x14003d862  mov     [rsp+250h+var_188], rax
0x14003d86a  lea     rax, [rbp+0B0h+var_98]
0x14003d86e  mov     [rsp+250h+var_190], rax
0x14003d876  lea     rax, [rbp+0B0h+var_12C]
0x14003d87a  mov     [rsp+250h+var_198], rax
0x14003d882  lea     rax, [rbp+0B0h+var_100]
0x14003d886  mov     [rsp+250h+var_1A0], rax
0x14003d88e  lea     rax, [rbp+0B0h+var_88]
0x14003d892  mov     [rsp+250h+var_1A8], rax
0x14003d89a  lea     rax, [rbp+0B0h+var_12B]
0x14003d89e  mov     [rsp+250h+var_1B0], rax
0x14003d8a6  lea     rax, [rbp+0B0h+var_F8]
0x14003d8aa  mov     [rsp+250h+var_1B8], rax
0x14003d8b2  lea     rax, [rbp+0B0h+var_78]
0x14003d8b6  mov     [rsp+250h+var_1C0], rax
0x14003d8be  lea     rax, [rbp+0B0h+var_12A]
0x14003d8c2  mov     [rsp+250h+var_1C8], rax
0x14003d8ca  lea     rax, [rbp+0B0h+var_F0]
0x14003d8ce  mov     [rsp+250h+var_1D0], rax
0x14003d8d6  lea     rax, [rbp+0B0h+var_68]
0x14003d8da  mov     [rsp+250h+var_1D8], rax
0x14003d8df  lea     rax, [rbp+0B0h+var_129]
0x14003d8e3  mov     [rsp+250h+var_1E0], rax
0x14003d8e8  lea     rax, [rbp+0B0h+var_E8]
0x14003d8ec  mov     [rsp+250h+var_1E8], rax
0x14003d8f1  lea     rax, [rbp+0B0h+var_58]
0x14003d8f5  mov     [rsp+250h+var_1F0], rax
0x14003d8fa  lea     rax, [rbp+0B0h+var_128]
0x14003d8fe  mov     [rsp+250h+var_1F8], rax
0x14003d903  lea     rax, [rbp+0B0h+var_E0]
0x14003d907  mov     [rsp+250h+var_200], rax
0x14003d90c  lea     rax, [rbp+0B0h+var_48]
0x14003d910  mov     [rsp+250h+var_208], rax
0x14003d915  lea     rax, [rbp+0B0h+var_D8]
0x14003d919  mov     [rsp+250h+var_210], rax
0x14003d91e  lea     rax, [rbp+0B0h+var_127]
0x14003d922  mov     [rsp+250h+var_218], rax
0x14003d927  lea     rax, [rbp+0B0h+var_120]
0x14003d92b  mov     [rsp+250h+var_220], rax
0x14003d930  lea     rax, [rbp+0B0h+var_11C]
0x14003d934  mov     [rsp+250h+var_228], rax
0x14003d939  lea     rax, [rbp+0B0h+var_D0]
0x14003d93d  mov     [rsp+250h+var_230], rax
0x14003d942  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x14003d947  xorps   xmm0, xmm0
0x14003d94a  xor     eax, eax
0x14003d94c  movups  xmmword ptr [rbx+120h], xmm0
0x14003d953  movups  xmmword ptr [rbx+130h], xmm0
0x14003d95a  mov     [rbx+140h], rax
0x14003d961  mov     edx, edi
0x14003d963  mov     rcx, rbx
0x14003d966  call    FlushLookUpTableBucket
0x14003d96b  inc     edi
0x14003d96d  cmp     edi, esi
0x14003d96f  jb      short loc_14003D961
0x14003d971  mov     rcx, [rbp+0B0h+var_28]
0x14003d978  xor     rcx, rsp; StackCookie
0x14003d97b  call    __security_check_cookie
0x14003d980  add     rsp, 238h
0x14003d987  pop     rdi
0x14003d988  pop     rsi
0x14003d989  pop     rbx
0x14003d98a  pop     rbp
0x14003d98b  retn
```
