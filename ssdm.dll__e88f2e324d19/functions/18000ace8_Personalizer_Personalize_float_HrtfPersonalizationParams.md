# Personalizer::Personalize(float,HrtfPersonalizationParams *)

- ea: `0x18000ace8`
- end: `0x18000b1b5`
- name: `?Personalize@Personalizer@@AEAAXMPEAUHrtfPersonalizationParams@@@Z`
- size: `1229`
- prototype: `void __fastcall(Personalizer *__hidden this, float, struct HrtfPersonalizationParams *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000b1bc`

## callees

- `0x180002988`
- `0x180002ed6`
- `0x180007484`
- `0x18000a6f4`
- `0x18000ace8`
- `0x18000b328`
- `0x18000b4d4`
- `0x18000bcdc`
- `0x18000bda0`
- `0x18000be94`
- `0x18000e962`
- `0x18000e990`
- `0x180010010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000b0ee`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b0fd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b122`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b131`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b0ee`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b0fd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b122`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b131`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000adf1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000b092`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000adf1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000b092`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18000b0a0`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18000b0a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000afbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b046`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b113`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000afbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b046`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b113`
- `HrtfDspCpu!CreateHrtfDataHelper` at `0x18000ad2d`
- `HrtfDspCpu!CreateHrtfDataHelper` at `0x18000ad2d`
- `ext-ms-win-audiocore-spatial-l1-1-0!GetHrtfMinFrameCount` at `0x18000ae05`
- `ext-ms-win-audiocore-spatial-l1-1-0!GetHrtfMinFrameCount` at `0x18000ae05`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall Personalizer::Personalize(Personalize *this, float a2, struct HrtfPersonalizationParams *a3)
{
  int v4; // eax
  unsigned int HrtfMinFrameCount; // ebx
  __int64 v6; // rdx
  __int64 v7; // r9
  _QWORD *v8; // r12
  _DWORD *v9; // r13
  unsigned int v10; // r10d
  __int64 v11; // rdx
  __int64 v12; // rax
  void *v13; // rdi
  int v14; // eax
  void *v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // r15d
  __int64 v18; // r12
  __int64 v19; // r13
  __int64 v20; // rsi
  unsigned int v21; // edi
  void *v22; // rbx
  void *v23; // rcx
  _QWORD *v24; // rcx
  int v25; // [rsp+28h] [rbp-E0h]
  unsigned int v26; // [rsp+28h] [rbp-E0h]
  void *Src; // [rsp+80h] [rbp-88h] BYREF
  _QWORD *v28; // [rsp+88h] [rbp-80h] BYREF
  LARGE_INTEGER v29; // [rsp+90h] [rbp-78h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+98h] [rbp-70h] BYREF
  LARGE_INTEGER Frequency; // [rsp+A0h] [rbp-68h] BYREF
  void **p_Src; // [rsp+A8h] [rbp-60h]
  void *v33; // [rsp+B0h] [rbp-58h]
  char v34; // [rsp+B8h] [rbp-50h]
  __int128 v35; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v36; // [rsp+D0h] [rbp-38h]
  __int128 v37; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v38; // [rsp+E8h] [rbp-20h]
  __int128 v39; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v40; // [rsp+100h] [rbp-8h]
  __int128 v41; // [rsp+108h] [rbp+0h] BYREF
  __int64 v42; // [rsp+118h] [rbp+10h]
  void **v43; // [rsp+128h] [rbp+20h] BYREF
  int v44; // [rsp+130h] [rbp+28h] BYREF
  char v45; // [rsp+134h] [rbp+2Ch]
  int v46; // [rsp+158h] [rbp+50h] BYREF
  const char *v47; // [rsp+160h] [rbp+58h]
  __int64 v48; // [rsp+168h] [rbp+60h]
  char v49; // [rsp+170h] [rbp+68h]
  int v50; // [rsp+178h] [rbp+70h]
  _BYTE v51[152]; // [rsp+180h] [rbp+78h] BYREF
  __int128 v52; // [rsp+218h] [rbp+110h]
  int v53; // [rsp+228h] [rbp+120h]
  __int64 v54; // [rsp+230h] [rbp+128h]
  int *v55; // [rsp+238h] [rbp+130h]
  __int64 v56; // [rsp+240h] [rbp+138h]
  __int64 v57; // [rsp+248h] [rbp+140h]
  void ***v58; // [rsp+250h] [rbp+148h]
  __int64 v59; // [rsp+258h] [rbp+150h]
  int v60; // [rsp+260h] [rbp+158h]
  int *v61; // [rsp+268h] [rbp+160h]
  char v62; // [rsp+270h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2D0h] [rbp+1C8h]

  v28 = 0;
  v4 = CreateHrtfDataHelper(&v28);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\spatialsoundpersonalizer.cpp",
      (const char *)(unsigned int)v4,
      v25);
  v44 = 0;
  v45 = 0;
  v49 = 0;
  v46 = 0;
  v47 = "PersonalizationDuration";
  v48 = 0;
  v50 = 0;
  v52 = 0;
  memset_0(v51, 0, sizeof(v51));
  v53 = 1;
  v54 = 0;
  v55 = &v44;
  v56 = 0;
  v57 = 0;
  v58 = &v43;
  v59 = 0;
  v60 = 0;
  v61 = &v46;
  v62 = 0;
  v43 = &SsdmTelemetryProvider::PersonalizationDuration::`vftable';
  SsdmTelemetryProvider::PersonalizationDuration::StartActivity((SsdmTelemetryProvider::PersonalizationDuration *)&v43);
  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  HrtfMinFrameCount = 1024;
  if ( (unsigned __int8)IsGetHrtfMinFrameCountPresent() )
    HrtfMinFrameCount = GetHrtfMinFrameCount();
  v39 = 0;
  v40 = 0;
  std::vector<unsigned char *>::resize(
    &v39,
    0x6DB6DB6DB6DB6DB7LL * ((__int64)(*((_QWORD *)a3 + 8) - *((_QWORD *)a3 + 7)) >> 3));
  v41 = 0;
  v42 = 0;
  std::vector<unsigned long>::resize(
    &v41,
    0x6DB6DB6DB6DB6DB7LL * ((__int64)(*((_QWORD *)a3 + 8) - *((_QWORD *)a3 + 7)) >> 3));
  v6 = *((_QWORD *)a3 + 8);
  v7 = *((_QWORD *)a3 + 7);
  v8 = (_QWORD *)v39;
  v9 = (_DWORD *)v41;
  if ( 0x6DB6DB6DB6DB6DB7LL * ((v6 - v7) >> 3) )
  {
    v10 = 0;
    do
    {
      v11 = 56LL * v10;
      v8[v10] = *(_QWORD *)(v11 + v7 + 8);
      v9[v10++] = *(_DWORD *)(*((_QWORD *)a3 + 7) + v11 + 16) - *(_DWORD *)(*((_QWORD *)a3 + 7) + v11 + 8);
      v6 = *((_QWORD *)a3 + 8);
      v7 = *((_QWORD *)a3 + 7);
    }
    while ( v10 < (unsigned __int64)(0x6DB6DB6DB6DB6DB7LL * ((v6 - v7) >> 3)) );
  }
  Src = 0;
  v35 = 0;
  v36 = 0;
  std::vector<unsigned long>::resize(&v35, 0x6DB6DB6DB6DB6DB7LL * ((v6 - v7) >> 3));
  v37 = 0;
  v38 = 0;
  std::vector<unsigned char *>::resize(
    &v37,
    0x6DB6DB6DB6DB6DB7LL * ((__int64)(*((_QWORD *)a3 + 8) - *((_QWORD *)a3 + 7)) >> 3));
  v12 = *v28;
  p_Src = &Src;
  v33 = 0;
  v34 = 1;
  v13 = (void *)v35;
  v26 = *((_DWORD *)a3 + 4) - *((_QWORD *)a3 + 1);
  v14 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD))(v12 + 24))(v28, v26, HrtfMinFrameCount);
  if ( v14 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x4E,
      (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\spatialsoundpersonalizer.cpp",
      (const char *)(unsigned int)v14,
      v26);
  if ( v34 )
  {
    v15 = *p_Src;
    *p_Src = v33;
    if ( v15 )
      CoTaskMemFree(v15);
  }
  std::vector<unsigned char,AlignedStore::AlignedAllocator<unsigned char,16>>::resize((char *)a3 + 32, 0);
  memcpy_0(*((void **)a3 + 4), Src, 0);
  v16 = *((_QWORD *)a3 + 7);
  if ( 0x6DB6DB6DB6DB6DB7LL * ((*((_QWORD *)a3 + 8) - v16) >> 3) )
  {
    v17 = 0;
    v18 = v35;
    v19 = v37;
    do
    {
      v20 = 56LL * v17;
      v21 = *(_DWORD *)(v18 + 4LL * v17);
      std::vector<unsigned char,AlignedStore::AlignedAllocator<unsigned char,16>>::resize(v20 + v16 + 32, v21);
      v22 = *(void **)(v19 + 8LL * v17);
      memcpy_0(*(void **)(*((_QWORD *)a3 + 7) + v20 + 32), v22, v21);
      if ( v22 )
        CoTaskMemFree(v22);
      ++v17;
      v16 = *((_QWORD *)a3 + 7);
    }
    while ( v17 < (unsigned __int64)(0x6DB6DB6DB6DB6DB7LL * ((*((_QWORD *)a3 + 8) - v16) >> 3)) );
    v8 = (_QWORD *)v39;
    v9 = (_DWORD *)v41;
    v13 = (void *)v35;
  }
  *(float *)a3 = a2;
  *((_BYTE *)a3 + 80) = 1;
  v29.QuadPart = 0;
  QueryPerformanceCounter(&v29);
  Frequency.QuadPart = 0;
  QueryPerformanceFrequency(&Frequency);
  SsdmTelemetryProvider::PersonalizationDuration::Stop(
    (SsdmTelemetryProvider::PersonalizationDuration *)&v43,
    (v29.QuadPart - PerformanceCount.QuadPart) / (Frequency.QuadPart / 1000));
  if ( (_QWORD)v37 )
    operator delete((void *)v37);
  if ( v13 )
    operator delete(v13);
  v23 = Src;
  Src = 0;
  if ( v23 )
    CoTaskMemFree(v23);
  if ( v9 )
    operator delete(v9);
  if ( v8 )
    operator delete(v8);
  SsdmTelemetryProvider::PersonalizationDuration::~PersonalizationDuration((SsdmTelemetryProvider::PersonalizationDuration *)&v43);
  v24 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v24 + 16LL))(v24);
  }
}

```

## disassembly

```asm
0x18000ace8  mov     rax, rsp
0x18000aceb  mov     [rax+8], rbx
0x18000acef  push    rbp
0x18000acf0  push    rsi
0x18000acf1  push    rdi
0x18000acf2  push    r12
0x18000acf4  push    r13
0x18000acf6  push    r14
0x18000acf8  push    r15
0x18000acfa  lea     rbp, [rax-1C8h]
0x18000ad01  sub     rsp, 290h
0x18000ad08  movaps  xmmword ptr [rax-48h], xmm6
0x18000ad0c  mov     rax, cs:__security_cookie
0x18000ad13  xor     rax, rsp
0x18000ad16  mov     [rbp+1C0h+var_50], rax
0x18000ad1d  mov     r14, r8
0x18000ad20  movaps  xmm6, xmm1
0x18000ad23  xor     esi, esi
0x18000ad25  mov     [rbp+1C0h+var_240], rsi
0x18000ad29  lea     rcx, [rbp+1C0h+var_240]
0x18000ad2d  call    cs:__imp_CreateHrtfDataHelper
0x18000ad33  mov     rcx, [rbp+1C8h]; this
0x18000ad3a  test    eax, eax
0x18000ad3c  js      loc_18000B1A0
0x18000ad42  mov     [rbp+1C0h+var_198], esi
0x18000ad45  mov     [rbp+1C0h+var_194], sil
0x18000ad49  mov     [rbp+1C0h+var_158], sil
0x18000ad4d  mov     [rbp+1C0h+var_170], esi
0x18000ad50  lea     rax, aPersonalizatio; "PersonalizationDuration"
0x18000ad57  mov     [rbp+1C0h+var_168], rax
0x18000ad5b  mov     [rbp+1C0h+var_160], rsi
0x18000ad5f  mov     [rbp+1C0h+var_150], esi
0x18000ad62  xorps   xmm0, xmm0
0x18000ad65  movdqa  [rbp+1C0h+var_B0], xmm0
0x18000ad6d  xor     edx, edx; Val
0x18000ad6f  mov     r8d, 98h; Size
0x18000ad75  lea     rcx, [rbp+1C0h+var_148]; void *
0x18000ad79  call    memset_0
0x18000ad7e  mov     [rbp+1C0h+var_A0], 1
0x18000ad88  xor     eax, eax
0x18000ad8a  mov     [rbp+1C0h+var_98], rax
0x18000ad91  lea     rax, [rbp+1C0h+var_198]
0x18000ad95  mov     [rbp+1C0h+var_90], rax
0x18000ad9c  mov     [rbp+1C0h+var_88], rsi
0x18000ada3  mov     [rbp+1C0h+var_80], rsi
0x18000adaa  lea     rax, [rbp+1C0h+var_1A0]
0x18000adae  mov     [rbp+1C0h+var_78], rax
0x18000adb5  mov     [rbp+1C0h+var_70], rsi
0x18000adbc  mov     [rbp+1C0h+var_68], esi
0x18000adc2  lea     rax, [rbp+1C0h+var_170]
0x18000adc6  mov     [rbp+1C0h+var_60], rax
0x18000adcd  mov     [rbp+1C0h+var_58], sil
0x18000add4  lea     rax, ??_7PersonalizationDuration@SsdmTelemetryProvider@@6B@; const SsdmTelemetryProvider::PersonalizationDuration::`vftable'
0x18000addb  mov     [rbp+1C0h+var_1A0], rax
0x18000addf  lea     rcx, [rbp+1C0h+var_1A0]; this
0x18000ade3  call    ?StartActivity@PersonalizationDuration@SsdmTelemetryProvider@@QEAAXXZ; SsdmTelemetryProvider::PersonalizationDuration::StartActivity(void)
0x18000ade8  nop
0x18000ade9  mov     qword ptr [rbp+1C0h+PerformanceCount], rsi
0x18000aded  lea     rcx, [rbp+1C0h+PerformanceCount]; lpPerformanceCount
0x18000adf1  call    cs:__imp_QueryPerformanceCounter
0x18000adf7  mov     ebx, 400h
0x18000adfc  call    IsGetHrtfMinFrameCountPresent
0x18000ae01  test    al, al
0x18000ae03  jz      short loc_18000AE0D
0x18000ae05  call    cs:__imp_GetHrtfMinFrameCount
0x18000ae0b  mov     ebx, eax
0x18000ae0d  xorps   xmm0, xmm0
0x18000ae10  movdqu  [rbp+1C0h+var_1D8], xmm0
0x18000ae15  mov     [rbp+1C0h+var_1C8], rsi
0x18000ae19  mov     rdx, [r14+40h]
0x18000ae1d  sub     rdx, [r14+38h]
0x18000ae21  sar     rdx, 3
0x18000ae25  mov     r15, 6DB6DB6DB6DB6DB7h
0x18000ae2f  imul    rdx, r15
0x18000ae33  lea     rcx, [rbp+1C0h+var_1D8]
0x18000ae37  call    ?resize@?$vector@PEAEV?$allocator@PEAE@std@@@std@@QEAAX_K@Z; std::vector<uchar *>::resize(unsigned __int64)
0x18000ae3c  nop
0x18000ae3d  xorps   xmm0, xmm0
0x18000ae40  movdqu  [rbp+1C0h+var_1C0], xmm0
0x18000ae45  mov     [rbp+1C0h+var_1B0], rsi
0x18000ae49  mov     rdx, [r14+40h]
0x18000ae4d  sub     rdx, [r14+38h]
0x18000ae51  sar     rdx, 3
0x18000ae55  imul    rdx, r15
0x18000ae59  lea     rcx, [rbp+1C0h+var_1C0]
0x18000ae5d  call    ?resize@?$vector@KV?$allocator@K@std@@@std@@QEAAX_K@Z; std::vector<ulong>::resize(unsigned __int64)
0x18000ae62  nop
0x18000ae63  mov     rdx, [r14+40h]
0x18000ae67  mov     r9, [r14+38h]
0x18000ae6b  mov     rax, rdx
0x18000ae6e  sub     rax, r9
0x18000ae71  sar     rax, 3
0x18000ae75  imul    rax, r15
0x18000ae79  mov     r12, qword ptr [rbp+1C0h+var_1D8]
0x18000ae7d  mov     r13, qword ptr [rbp+1C0h+var_1C0]
0x18000ae81  test    rax, rax
0x18000ae84  jz      short loc_18000AECB
0x18000ae86  mov     r10d, esi
0x18000ae89  mov     r8d, r10d
0x18000ae8c  imul    rdx, r8, 38h ; '8'
0x18000ae90  mov     rax, [rdx+r9+8]
0x18000ae95  mov     [r12+r8*8], rax
0x18000ae99  mov     rcx, [r14+38h]
0x18000ae9d  mov     eax, [rcx+rdx+10h]
0x18000aea1  sub     eax, [rcx+rdx+8]
0x18000aea5  mov     [r13+r8*4+0], eax
0x18000aeaa  inc     r10d
0x18000aead  mov     rdx, [r14+40h]
0x18000aeb1  mov     r9, [r14+38h]
0x18000aeb5  mov     rcx, rdx
0x18000aeb8  sub     rcx, r9
0x18000aebb  sar     rcx, 3
0x18000aebf  imul    rcx, r15
0x18000aec3  mov     eax, r10d
0x18000aec6  cmp     rax, rcx
0x18000aec9  jb      short loc_18000AE89
0x18000aecb  mov     [rsp+2C0h+Src], rsi
0x18000aed0  mov     dword ptr [rsp+2C0h+Size], esi
0x18000aed4  xorps   xmm0, xmm0
0x18000aed7  movdqu  [rbp+1C0h+var_208], xmm0
0x18000aedc  mov     [rbp+1C0h+var_1F8], rsi
0x18000aee0  sub     rdx, r9
0x18000aee3  sar     rdx, 3
0x18000aee7  imul    rdx, r15
0x18000aeeb  lea     rcx, [rbp+1C0h+var_208]
0x18000aeef  call    ?resize@?$vector@KV?$allocator@K@std@@@std@@QEAAX_K@Z; std::vector<ulong>::resize(unsigned __int64)
0x18000aef4  nop
0x18000aef5  xorps   xmm0, xmm0
0x18000aef8  movdqu  [rbp+1C0h+var_1F0], xmm0
0x18000aefd  mov     [rbp+1C0h+var_1E0], rsi
0x18000af01  mov     rdx, [r14+40h]
0x18000af05  sub     rdx, [r14+38h]
0x18000af09  sar     rdx, 3
0x18000af0d  imul    rdx, r15
0x18000af11  lea     rcx, [rbp+1C0h+var_1F0]
0x18000af15  call    ?resize@?$vector@PEAEV?$allocator@PEAE@std@@@std@@QEAAX_K@Z; std::vector<uchar *>::resize(unsigned __int64)
0x18000af1a  nop
0x18000af1b  mov     rcx, [rbp+1C0h+var_240]
0x18000af1f  mov     rax, [rcx]
0x18000af22  lea     rdx, [rsp+2C0h+Src]
0x18000af27  mov     [rbp+1C0h+var_220], rdx
0x18000af2b  mov     [rbp+1C0h+var_218], rsi
0x18000af2f  mov     [rbp+1C0h+var_210], 1
0x18000af33  mov     r9, [r14+8]
0x18000af37  mov     r8, [r14+40h]
0x18000af3b  sub     r8, [r14+38h]
0x18000af3f  sar     r8, 3
0x18000af43  imul    r8, r15
0x18000af47  mov     edx, [r14+10h]
0x18000af4b  sub     edx, r9d
0x18000af4e  mov     rdi, qword ptr [rbp+1C0h+var_208]
0x18000af52  mov     [rsp+2C0h+var_268], rdi
0x18000af57  mov     r10, qword ptr [rbp+1C0h+var_1F0]
0x18000af5b  mov     [rsp+2C0h+var_270], r10
0x18000af60  lea     r10, [rsp+2C0h+Size]
0x18000af65  mov     [rsp+2C0h+var_278], r10
0x18000af6a  lea     r10, [rbp+1C0h+var_218]
0x18000af6e  mov     [rsp+2C0h+var_280], r10
0x18000af73  mov     dword ptr [rsp+2C0h+var_288], r8d
0x18000af78  mov     qword ptr [rsp+2C0h+var_290], r13
0x18000af7d  mov     [rsp+2C0h+var_298], r12
0x18000af82  mov     [rsp+2C0h+var_2A0], edx; int
0x18000af86  mov     r8d, ebx
0x18000af89  movaps  xmm1, xmm6
0x18000af8c  mov     rax, [rax+18h]
0x18000af90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af95  mov     rcx, [rbp+1C8h]; this
0x18000af9c  test    eax, eax
0x18000af9e  js      loc_18000B18B
0x18000afa4  cmp     [rbp+1C0h+var_210], sil
0x18000afa8  jz      short loc_18000AFC3
0x18000afaa  mov     rdx, [rbp+1C0h+var_220]
0x18000afae  mov     rcx, [rdx]; pv
0x18000afb1  mov     rax, [rbp+1C0h+var_218]
0x18000afb5  mov     [rdx], rax
0x18000afb8  test    rcx, rcx
0x18000afbb  jz      short loc_18000AFC3
0x18000afbd  call    cs:__imp_CoTaskMemFree
0x18000afc3  mov     edx, dword ptr [rsp+2C0h+Size]
0x18000afc7  lea     rcx, [r14+20h]
0x18000afcb  call    ?resize@?$vector@EV?$AlignedAllocator@E$0BA@@AlignedStore@@@std@@QEAAX_K@Z; std::vector<uchar,AlignedStore::AlignedAllocator<uchar,16>>::resize(unsigned __int64)
0x18000afd0  mov     r8d, dword ptr [rsp+2C0h+Size]; Size
0x18000afd5  mov     rdx, [rsp+2C0h+Src]; Src
0x18000afda  mov     rcx, [r14+20h]; void *
0x18000afde  call    memcpy_0
0x18000afe3  mov     rdx, [r14+38h]
0x18000afe7  mov     rax, [r14+40h]
0x18000afeb  sub     rax, rdx
0x18000afee  sar     rax, 3
0x18000aff2  imul    rax, r15
0x18000aff6  test    rax, rax
0x18000aff9  jz      loc_18000B080
0x18000afff  mov     r15d, esi
0x18000b002  mov     r12, qword ptr [rbp+1C0h+var_208]
0x18000b006  mov     r13, qword ptr [rbp+1C0h+var_1F0]
0x18000b00a  mov     ebx, r15d
0x18000b00d  imul    rsi, rbx, 38h ; '8'
0x18000b011  mov     edi, [r12+rbx*4]
0x18000b015  lea     rcx, [rdx+20h]
0x18000b019  add     rcx, rsi
0x18000b01c  mov     edx, edi
0x18000b01e  call    ?resize@?$vector@EV?$AlignedAllocator@E$0BA@@AlignedStore@@@std@@QEAAX_K@Z; std::vector<uchar,AlignedStore::AlignedAllocator<uchar,16>>::resize(unsigned __int64)
0x18000b023  mov     rbx, [r13+rbx*8+0]
0x18000b028  mov     rcx, [r14+38h]
0x18000b02c  mov     r8d, edi; Size
0x18000b02f  mov     rdx, rbx; Src
0x18000b032  mov     rcx, [rcx+rsi+20h]; void *
0x18000b037  call    memcpy_0
0x18000b03c  xor     esi, esi
0x18000b03e  test    rbx, rbx
0x18000b041  jz      short loc_18000B04C
0x18000b043  mov     rcx, rbx; pv
0x18000b046  call    cs:__imp_CoTaskMemFree
0x18000b04c  inc     r15d
0x18000b04f  mov     rdx, [r14+38h]
0x18000b053  mov     rcx, [r14+40h]
0x18000b057  sub     rcx, rdx
0x18000b05a  sar     rcx, 3
0x18000b05e  mov     rax, 6DB6DB6DB6DB6DB7h
0x18000b068  imul    rcx, rax
0x18000b06c  mov     eax, r15d
0x18000b06f  cmp     rax, rcx
0x18000b072  jb      short loc_18000B00A
0x18000b074  mov     r12, qword ptr [rbp+1C0h+var_1D8]
0x18000b078  mov     r13, qword ptr [rbp+1C0h+var_1C0]
0x18000b07c  mov     rdi, qword ptr [rbp+1C0h+var_208]
0x18000b080  movss   dword ptr [r14], xmm6
0x18000b085  mov     byte ptr [r14+50h], 1
0x18000b08a  mov     qword ptr [rbp+1C0h+var_238], rsi
0x18000b08e  lea     rcx, [rbp+1C0h+var_238]; lpPerformanceCount
0x18000b092  call    cs:__imp_QueryPerformanceCounter
0x18000b098  mov     qword ptr [rbp+1C0h+Frequency], rsi
0x18000b09c  lea     rcx, [rbp+1C0h+Frequency]; lpFrequency
0x18000b0a0  call    cs:__imp_QueryPerformanceFrequency
0x18000b0a6  mov     r10, qword ptr [rbp+1C0h+var_238]
0x18000b0aa  sub     r10, qword ptr [rbp+1C0h+PerformanceCount]
0x18000b0ae  mov     rax, 20C49BA5E353F7CFh
0x18000b0b8  imul    qword ptr [rbp+1C0h+Frequency]
0x18000b0bc  mov     r9, rdx
0x18000b0bf  sar     r9, 7
0x18000b0c3  mov     r8, r9
0x18000b0c6  shr     r8, 3Fh
0x18000b0ca  add     r9, r8
0x18000b0cd  mov     rax, r10
0x18000b0d0  cqo
0x18000b0d2  idiv    r9
0x18000b0d5  mov     rdx, rax; __int64
0x18000b0d8  lea     rcx, [rbp+1C0h+var_1A0]; this
0x18000b0dc  call    ?Stop@PersonalizationDuration@SsdmTelemetryProvider@@QEAAX_J@Z; SsdmTelemetryProvider::PersonalizationDuration::Stop(__int64)
0x18000b0e1  nop
0x18000b0e2  mov     rax, qword ptr [rbp+1C0h+var_1F0]
0x18000b0e6  test    rax, rax
0x18000b0e9  jz      short loc_18000B0F5
0x18000b0eb  mov     rcx, rax
0x18000b0ee  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b0f4  nop
0x18000b0f5  test    rdi, rdi
0x18000b0f8  jz      short loc_18000B104
0x18000b0fa  mov     rcx, rdi
0x18000b0fd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b103  nop
0x18000b104  mov     rcx, [rsp+2C0h+Src]; pv
0x18000b109  mov     [rsp+2C0h+Src], rsi
0x18000b10e  test    rcx, rcx
0x18000b111  jz      short loc_18000B11A
0x18000b113  call    cs:__imp_CoTaskMemFree
0x18000b119  nop
0x18000b11a  test    r13, r13
0x18000b11d  jz      short loc_18000B129
0x18000b11f  mov     rcx, r13
0x18000b122  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b128  nop
0x18000b129  test    r12, r12
0x18000b12c  jz      short loc_18000B138
0x18000b12e  mov     rcx, r12
0x18000b131  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b137  nop
0x18000b138  lea     rcx, [rbp+1C0h+var_1A0]; this
0x18000b13c  call    ??1PersonalizationDuration@SsdmTelemetryProvider@@QEAA@XZ; SsdmTelemetryProvider::PersonalizationDuration::~PersonalizationDuration(void)
0x18000b141  nop
0x18000b142  mov     rcx, [rbp+1C0h+var_240]
0x18000b146  test    rcx, rcx
0x18000b149  jz      short loc_18000B15C
0x18000b14b  mov     [rbp+1C0h+var_240], rsi
0x18000b14f  mov     rax, [rcx]
0x18000b152  mov     rax, [rax+10h]
0x18000b156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b15b  nop
0x18000b15c  mov     rcx, [rbp+1C0h+var_50]
0x18000b163  xor     rcx, rsp; StackCookie
0x18000b166  call    __security_check_cookie
0x18000b16b  lea     r11, [rsp+2C0h+var_30]
0x18000b173  mov     rbx, [r11+40h]
0x18000b177  movaps  xmm6, xmmword ptr [r11-10h]
0x18000b17c  mov     rsp, r11
0x18000b17f  pop     r15
0x18000b181  pop     r14
0x18000b183  pop     r13
0x18000b185  pop     r12
0x18000b187  pop     rdi
  ... truncated ...
```
