# LookUpTableFlushComplete

- ea: `0x14002eaac`
- end: `0x14002ee1d`
- name: `LookUpTableFlushComplete`
- size: `881`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140022cf0`
- `0x140022f00`
- `0x14002ea30`
- `0x14002f200`

## callees

- `0x140001008`
- `0x1400010d4`
- `0x140007588`
- `0x140007c60`
- `0x140022d74`
- `0x14002eaac`

## pseudocode

```c
void __fastcall LookUpTableFlushComplete(__int64 a1)
{
  unsigned int v1; // edi
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
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
      if ( (unsigned int)dword_14000E098 > 5 && tlgKeywordOn((__int64)&dword_14000E098, 0x200000000000LL) )
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
          (__int64)&dword_14000BEB4,
          v4,
          v5,
          (__int64)&v30,
          (__int64)&v20,
          (__int64)&v19,
          (__int64)v17,
          (__int64 *)&v29,
          (__int64 *)&v47,
          (__int64)&v28,
          (__int64)&v16,
          (__int64 *)&v45,
          (__int64)&v27,
          (__int64)&v15,
          (__int64 *)&v43,
          (__int64)&v26,
          (__int64)&v14,
          (__int64 *)&v41,
          (__int64)&v25,
          (__int64)&v13,
          (__int64 *)&v39,
          (__int64)&v24,
          (__int64)&v12,
          (__int64 *)&v37,
          (__int64)&v23,
          (__int64)&v11,
          (__int64 *)&v35,
          (__int64)&v22,
          (__int64)&v10,
          (__int64 *)&v33,
          (__int64)&v21,
          (__int64)&v9,
          (__int64 *)&v31,
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
0x14002eaac  push    rbp
0x14002eaae  push    rbx
0x14002eaaf  push    rsi
0x14002eab0  push    rdi
0x14002eab1  lea     rbp, [rsp-98h]
0x14002eab9  sub     rsp, 238h
0x14002eac0  mov     rax, cs:__security_cookie
0x14002eac7  xor     rax, rsp
0x14002eaca  mov     [rbp+0B0h+var_28], rax
0x14002ead1  mov     edx, [rcx+100h]
0x14002ead7  xor     edi, edi
0x14002ead9  mov     rbx, rcx
0x14002eadc  test    edx, edx
0x14002eade  jz      loc_14002EE01
0x14002eae4  call    UpdateInternalStatsOnFlush
0x14002eae9  lea     esi, [rdi+20h]
0x14002eaec  cmp     [rcx+120h], rdi
0x14002eaf3  jz      loc_14002EDF1
0x14002eaf9  mov     eax, cs:dword_14000E098
0x14002eaff  cmp     eax, 5
0x14002eb02  jbe     loc_14002EDD7
0x14002eb08  mov     rdx, 200000000000h
0x14002eb12  lea     rcx, dword_14000E098
0x14002eb19  call    _tlgKeywordOn
0x14002eb1e  test    al, al
0x14002eb20  jz      loc_14002EDD7
0x14002eb26  lea     ecx, [rdi+2Ah]
0x14002eb29  mov     [rbp+0B0h+var_130], 4
0x14002eb2d  lea     rax, aSummarycount; "SummaryCount"
0x14002eb34  mov     [rbp+0B0h+var_B0], cx
0x14002eb38  mov     [rbp+0B0h+var_C8], rax
0x14002eb3c  lea     eax, [rdi+18h]
0x14002eb3f  mov     [rbp+0B0h+var_C0], ax
0x14002eb43  mov     eax, [rbx+144h]
0x14002eb49  mov     [rbp+0B0h+var_118], rax
0x14002eb4d  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x14002eb54  mov     [rbp+0B0h+var_B8], rax
0x14002eb58  mov     eax, [rbx+140h]
0x14002eb5e  mov     [rbp+0B0h+var_110], rax
0x14002eb62  lea     rax, aNumallocationf; "NumAllocationFailures"
0x14002eb69  mov     [rbp+0B0h+var_A8], rax
0x14002eb6d  mov     eax, [rbx+13Ch]
0x14002eb73  mov     [rbp+0B0h+var_108], rax
0x14002eb77  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x14002eb7e  mov     [rbp+0B0h+var_98], rax
0x14002eb82  mov     eax, [rbx+138h]
0x14002eb88  mov     [rbp+0B0h+var_100], rax
0x14002eb8c  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x14002eb93  mov     [rbp+0B0h+var_88], rax
0x14002eb97  mov     eax, [rbx+134h]
0x14002eb9d  mov     [rbp+0B0h+var_F8], rax
0x14002eba1  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x14002eba8  mov     [rbp+0B0h+var_78], rax
0x14002ebac  mov     rax, [rbx+120h]
0x14002ebb3  mov     [rbp+0B0h+var_F0], rax
0x14002ebb7  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x14002ebbe  mov     [rbp+0B0h+var_68], rax
0x14002ebc2  lea     eax, [rdi+26h]
0x14002ebc5  mov     [rbp+0B0h+var_60], ax
0x14002ebc9  mov     eax, [rbx+130h]
0x14002ebcf  mov     [rbp+0B0h+var_E8], rax
0x14002ebd3  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x14002ebda  mov     [rbp+0B0h+var_58], rax
0x14002ebde  mov     rax, [rbx+128h]
0x14002ebe5  mov     [rbp+0B0h+var_E0], rax
0x14002ebe9  lea     rax, aNumflushes; "NumFlushes"
0x14002ebf0  mov     [rbp+0B0h+var_48], rax
0x14002ebf4  lea     eax, [rdi+14h]
0x14002ebf7  mov     [rbp+0B0h+var_40], ax
0x14002ebfb  mov     rax, [rbx+158h]
0x14002ec02  mov     [rbp+0B0h+var_A0], cx
0x14002ec06  mov     [rbp+0B0h+var_90], cx
0x14002ec0a  lea     ecx, [rdi+22h]
0x14002ec0d  mov     [rbp+0B0h+var_124], 1
0x14002ec14  mov     [rbp+0B0h+var_12F], 4
0x14002ec18  mov     [rbp+0B0h+var_12E], 4
0x14002ec1c  mov     [rbp+0B0h+var_12D], 4
0x14002ec20  mov     [rbp+0B0h+var_12C], 4
0x14002ec24  mov     [rbp+0B0h+var_80], cx
0x14002ec28  mov     [rbp+0B0h+var_12B], 4
0x14002ec2c  mov     [rbp+0B0h+var_70], cx
0x14002ec30  mov     [rbp+0B0h+var_12A], 4
0x14002ec34  mov     [rbp+0B0h+var_129], 4
0x14002ec38  mov     [rbp+0B0h+var_50], si
0x14002ec3c  mov     [rbp+0B0h+var_128], 4
0x14002ec40  mov     rcx, [rax+8]
0x14002ec44  lea     rax, [rbp+0B0h+var_38]
0x14002ec48  mov     [rbp+0B0h+var_D8], rax
0x14002ec4c  lea     rax, [rbp+0B0h+var_130]
0x14002ec50  mov     [rsp+250h+var_138], rax
0x14002ec58  lea     rax, [rbp+0B0h+var_124]
0x14002ec5c  mov     [rsp+250h+var_140], rax
0x14002ec64  lea     rax, [rbp+0B0h+var_C8]
0x14002ec68  movups  xmm0, xmmword ptr [rcx-10h]
0x14002ec6c  mov     [rsp+250h+var_148], rax
0x14002ec74  lea     rax, [rbp+0B0h+var_12F]
0x14002ec78  mov     [rsp+250h+var_150], rax
0x14002ec80  lea     rax, [rbp+0B0h+var_118]
0x14002ec84  mov     [rsp+250h+var_158], rax
0x14002ec8c  lea     rax, [rbp+0B0h+var_B8]
0x14002ec90  mov     [rsp+250h+var_160], rax
0x14002ec98  lea     rax, [rbp+0B0h+var_12E]
0x14002ec9c  movdqu  [rbp+0B0h+var_38], xmm0
0x14002eca1  mov     [rbp+0B0h+var_127], dil
0x14002eca5  mov     [rbp+0B0h+var_120], 0FFFFFFFFh
0x14002ecac  mov     [rbp+0B0h+var_11C], 12Ch
0x14002ecb3  mov     [rbp+0B0h+var_D0], 1000000h
0x14002ecbb  mov     [rsp+250h+var_168], rax
0x14002ecc3  lea     rdx, dword_14000BEB4
0x14002ecca  lea     rax, [rbp+0B0h+var_110]
0x14002ecce  mov     [rsp+250h+var_170], rax
0x14002ecd6  lea     rax, [rbp+0B0h+var_A8]
0x14002ecda  mov     [rsp+250h+var_178], rax
0x14002ece2  lea     rax, [rbp+0B0h+var_12D]
0x14002ece6  mov     [rsp+250h+var_180], rax
0x14002ecee  lea     rax, [rbp+0B0h+var_108]
0x14002ecf2  mov     [rsp+250h+var_188], rax
0x14002ecfa  lea     rax, [rbp+0B0h+var_98]
0x14002ecfe  mov     [rsp+250h+var_190], rax
0x14002ed06  lea     rax, [rbp+0B0h+var_12C]
0x14002ed0a  mov     [rsp+250h+var_198], rax
0x14002ed12  lea     rax, [rbp+0B0h+var_100]
0x14002ed16  mov     [rsp+250h+var_1A0], rax
0x14002ed1e  lea     rax, [rbp+0B0h+var_88]
0x14002ed22  mov     [rsp+250h+var_1A8], rax
0x14002ed2a  lea     rax, [rbp+0B0h+var_12B]
0x14002ed2e  mov     [rsp+250h+var_1B0], rax
0x14002ed36  lea     rax, [rbp+0B0h+var_F8]
0x14002ed3a  mov     [rsp+250h+var_1B8], rax
0x14002ed42  lea     rax, [rbp+0B0h+var_78]
0x14002ed46  mov     [rsp+250h+var_1C0], rax
0x14002ed4e  lea     rax, [rbp+0B0h+var_12A]
0x14002ed52  mov     [rsp+250h+var_1C8], rax
0x14002ed5a  lea     rax, [rbp+0B0h+var_F0]
0x14002ed5e  mov     [rsp+250h+var_1D0], rax
0x14002ed66  lea     rax, [rbp+0B0h+var_68]
0x14002ed6a  mov     [rsp+250h+var_1D8], rax
0x14002ed6f  lea     rax, [rbp+0B0h+var_129]
0x14002ed73  mov     [rsp+250h+var_1E0], rax
0x14002ed78  lea     rax, [rbp+0B0h+var_E8]
0x14002ed7c  mov     [rsp+250h+var_1E8], rax
0x14002ed81  lea     rax, [rbp+0B0h+var_58]
0x14002ed85  mov     [rsp+250h+var_1F0], rax
0x14002ed8a  lea     rax, [rbp+0B0h+var_128]
0x14002ed8e  mov     [rsp+250h+var_1F8], rax
0x14002ed93  lea     rax, [rbp+0B0h+var_E0]
0x14002ed97  mov     [rsp+250h+var_200], rax
0x14002ed9c  lea     rax, [rbp+0B0h+var_48]
0x14002eda0  mov     [rsp+250h+var_208], rax
0x14002eda5  lea     rax, [rbp+0B0h+var_D8]
0x14002eda9  mov     [rsp+250h+var_210], rax
0x14002edae  lea     rax, [rbp+0B0h+var_127]
0x14002edb2  mov     [rsp+250h+var_218], rax
0x14002edb7  lea     rax, [rbp+0B0h+var_120]
0x14002edbb  mov     [rsp+250h+var_220], rax
0x14002edc0  lea     rax, [rbp+0B0h+var_11C]
0x14002edc4  mov     [rsp+250h+var_228], rax
0x14002edc9  lea     rax, [rbp+0B0h+var_D0]
0x14002edcd  mov     [rsp+250h+var_230], rax
0x14002edd2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x14002edd7  xorps   xmm0, xmm0
0x14002edda  xor     eax, eax
0x14002eddc  movups  xmmword ptr [rbx+120h], xmm0
0x14002ede3  movups  xmmword ptr [rbx+130h], xmm0
0x14002edea  mov     [rbx+140h], rax
0x14002edf1  mov     edx, edi
0x14002edf3  mov     rcx, rbx
0x14002edf6  call    FlushLookUpTableBucket
0x14002edfb  inc     edi
0x14002edfd  cmp     edi, esi
0x14002edff  jb      short loc_14002EDF1
0x14002ee01  mov     rcx, [rbp+0B0h+var_28]
0x14002ee08  xor     rcx, rsp; StackCookie
0x14002ee0b  call    __security_check_cookie
0x14002ee10  add     rsp, 238h
0x14002ee17  pop     rdi
0x14002ee18  pop     rsi
0x14002ee19  pop     rbx
0x14002ee1a  pop     rbp
0x14002ee1b  retn
```
