# CVssGlobalSnapshotSetId::InitializeObserver(CVssSnasphotSetIdObserver *)

- ea: `0x14003aa10`
- end: `0x14003addb`
- name: `?InitializeObserver@CVssGlobalSnapshotSetId@@SAXPEAVCVssSnasphotSetIdObserver@@@Z`
- size: `971`
- prototype: `void __fastcall(struct CVssSnasphotSetIdObserver *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14003a930`

## callees

- `0x140011440`
- `0x1400137c0`
- `0x140013cb0`
- `0x140015950`
- `0x14003aa10`
- `0x1400921dc`
- `0x14009dacc`
- `0x1400da308`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003aab7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003ac5b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003aab7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003ac5b`
- `VssTrace!__imp_VssTraceMessage` at `0x14003ab82`
- `VssTrace!__imp_VssTraceMessage` at `0x14003ad23`
- `VssTrace!__imp_VssTraceMessage` at `0x14003ab82`
- `VssTrace!__imp_VssTraceMessage` at `0x14003ad23`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003aafd`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003aca6`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003aafd`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003aca6`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003aaef`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003ac97`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003aaef`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003ac97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003ab9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003ad42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003ab9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003ad42`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CVssGlobalSnapshotSetId::InitializeObserver(struct CVssSnasphotSetIdObserver *a1)
{
  int v2; // eax
  __int64 v3; // rcx
  int v4; // edi
  int v5; // ebx
  __int64 i; // rbx
  void *v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  __int64 j; // rbx
  void *v11; // rcx
  const unsigned __int16 *v12; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v13; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v14; // [rsp+60h] [rbp-A0h]
  __int64 v15; // [rsp+68h] [rbp-98h]
  unsigned int v16; // [rsp+70h] [rbp-90h]
  int v17; // [rsp+74h] [rbp-8Ch]
  LPVOID pv; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v19; // [rsp+80h] [rbp-80h]
  DWORD v20; // [rsp+84h] [rbp-7Ch]
  int v21; // [rsp+88h] [rbp-78h]
  __int128 v22; // [rsp+90h] [rbp-70h]
  __int128 v23; // [rsp+A0h] [rbp-60h]
  __int64 v24; // [rsp+B0h] [rbp-50h]
  int v25; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v26; // [rsp+100h] [rbp+0h] BYREF
  int v27; // [rsp+108h] [rbp+8h]
  const unsigned __int16 *v28; // [rsp+110h] [rbp+10h]
  const unsigned __int16 *v29; // [rsp+118h] [rbp+18h]
  __int64 v30; // [rsp+120h] [rbp+20h]
  const wchar_t *v31; // [rsp+128h] [rbp+28h]
  unsigned int v32; // [rsp+130h] [rbp+30h]
  DWORD TickCount; // [rsp+134h] [rbp+34h]
  int v34; // [rsp+138h] [rbp+38h]
  __int128 v35; // [rsp+140h] [rbp+40h]
  __int128 v36; // [rsp+150h] [rbp+50h]
  __int64 v37; // [rsp+160h] [rbp+60h]
  LPCRITICAL_SECTION v38; // [rsp+170h] [rbp+70h] BYREF
  char v39; // [rsp+178h] [rbp+78h]
  struct _GUID v40; // [rsp+180h] [rbp+80h] BYREF
  const unsigned __int16 *v41; // [rsp+190h] [rbp+90h]
  wchar_t *v42; // [rsp+198h] [rbp+98h]
  const unsigned __int16 *v43; // [rsp+1A0h] [rbp+A0h]
  int v44; // [rsp+1A8h] [rbp+A8h]
  int v45; // [rsp+1ACh] [rbp+ACh]
  int v46; // [rsp+1B0h] [rbp+B0h]
  LPVOID v47[15]; // [rsp+1B8h] [rbp+B8h] BYREF
  int v48; // [rsp+230h] [rbp+130h]
  __int64 v49; // [rsp+278h] [rbp+178h] BYREF

  v12 = L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx";
  v13 = L"CVssGlobalSnapshotSetId::InitializeObserver";
  v14 = L"CORSNPSC";
  v15 = 0x100000A97LL;
  v16 = 255;
  v25 = 0x1000000;
  memset_0(&pv, 0, 0x78u);
  v27 = 0;
  v31 = L"CVssGlobalSnapshotSetId::InitializeObserver";
  v28 = L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx";
  v29 = L"CORSNPSC";
  v30 = 0x100000A97LL;
  TickCount = GetTickCount();
  v34 = 255;
  v26 = 0xFFFFFFFF00000000uLL;
  v37 = 0;
  v35 = 0;
  v36 = 0;
  v49 = 0;
  if ( (int)VssGetTracingContextPerThread(&v49) < 0 )
  {
    v3 = v37;
  }
  else
  {
    v2 = VssSetTracingContextPerThread(&v26);
    v3 = v37;
    if ( v2 >= 0 )
      v3 = v49;
    v37 = v3;
  }
  if ( v3 )
    v32 = *(_DWORD *)(v3 + 48) + 1;
  else
    v32 = 0;
  v4 = 160;
  v5 = 160;
  if ( v34 != 255 )
    v5 = v34;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v26) )
    VssTraceMessage(v28, v29, (unsigned int)v30, v32, HIDWORD(v30), v31, L"ENTER", v5, 0);
  if ( HIBYTE(v25) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v7 = *(&pv + i);
      if ( v7 )
      {
        CoTaskMemFree(v7);
        *(&pv + i) = 0;
      }
    }
  }
  v38 = &g_SnapshotSetCS;
  v41 = L"base\\stor\\vss\\inc\\vs_types.hxx";
  v42 = L"CVssAutomaticLock2::CVssAutomaticLock2";
  v43 = L"INCTYPEH";
  v44 = 256;
  v45 = 11;
  v46 = 255;
  v48 = 0x1000000;
  memset_0(v47, 0, sizeof(v47));
  LODWORD(v13) = 0;
  pv = v42;
  v14 = v41;
  v15 = (__int64)v43;
  v16 = v44;
  v17 = v45;
  v20 = GetTickCount();
  v21 = v46;
  v12 = (const unsigned __int16 *)0xFFFFFFFF00000000LL;
  v24 = 0;
  v22 = 0;
  v23 = 0;
  v49 = 0;
  if ( (int)VssGetTracingContextPerThread(&v49) < 0 )
  {
    v9 = v24;
  }
  else
  {
    v8 = VssSetTracingContextPerThread(&v12);
    v9 = v24;
    if ( v8 >= 0 )
      v9 = v49;
    v24 = v9;
  }
  if ( v9 )
    v19 = *(_DWORD *)(v9 + 48) + 1;
  else
    v19 = 0;
  if ( v21 != 255 )
    v4 = v21;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v12) )
    VssTraceMessage(v14, v15, v16, v19, v17, pv, L"ENTER", v4, 0);
  if ( HIBYTE(v48) )
  {
    for ( j = 0; j != 15; ++j )
    {
      v11 = v47[j];
      if ( v11 )
      {
        CoTaskMemFree(v11);
        v47[j] = 0;
      }
    }
  }
  CVssCriticalSection::Lock(&g_SnapshotSetCS);
  v39 = 1;
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v12);
  if ( memcmp_0(&CVssGlobalSnapshotSetId::m_SnapshotSetID, &GUID_NULL, 0x10u) )
  {
    v40 = CVssGlobalSnapshotSetId::m_SnapshotSetID;
    CVssSnasphotSetIdObserver::RecordSSID(a1, &v40);
  }
  CVssAutomaticLock2::~CVssAutomaticLock2(&v38);
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v26);
}

```

## disassembly

```asm
0x14003aa10  mov     [rsp-8+arg_0], rbx
0x14003aa15  mov     [rsp-8+arg_10], rsi
0x14003aa1a  push    rbp
0x14003aa1b  push    rdi
0x14003aa1c  push    r13
0x14003aa1e  push    r14
0x14003aa20  push    r15
0x14003aa22  lea     rbp, [rsp-140h]
0x14003aa2a  sub     rsp, 240h
0x14003aa31  mov     rsi, rcx
0x14003aa34  lea     rax, aBaseStorVssMod; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x14003aa3b  mov     [rsp+260h+var_210], rax
0x14003aa40  lea     rax, aCvssglobalsnap; "CVssGlobalSnapshotSetId::InitializeObse"...
0x14003aa47  mov     [rsp+260h+var_208], rax
0x14003aa4c  lea     rax, aCorsnpsc; "CORSNPSC"
0x14003aa53  mov     [rsp+260h+var_200], rax
0x14003aa58  mov     dword ptr [rsp+260h+var_1F8], 0A97h
0x14003aa60  mov     dword ptr [rsp+260h+var_1F8+4], 1
0x14003aa68  mov     [rsp+260h+var_1F0], 0FFh
0x14003aa70  xor     r14d, r14d
0x14003aa73  mov     [rbp+160h+var_170], 1000000h
0x14003aa7a  xor     edx, edx; Val
0x14003aa7c  lea     r8d, [r14+78h]; Size
0x14003aa80  lea     rcx, [rsp+260h+pv]; void *
0x14003aa85  call    memset_0
0x14003aa8a  mov     [rbp+160h+var_158], r14d
0x14003aa8e  mov     rax, [rsp+260h+var_208]
0x14003aa93  mov     [rbp+160h+var_138], rax
0x14003aa97  mov     rax, [rsp+260h+var_210]
0x14003aa9c  mov     [rbp+160h+var_150], rax
0x14003aaa0  mov     rax, [rsp+260h+var_200]
0x14003aaa5  mov     [rbp+160h+var_148], rax
0x14003aaa9  mov     eax, dword ptr [rsp+260h+var_1F8]
0x14003aaad  mov     dword ptr [rbp+160h+var_140], eax
0x14003aab0  mov     eax, dword ptr [rsp+260h+var_1F8+4]
0x14003aab4  mov     dword ptr [rbp+160h+var_140+4], eax
0x14003aab7  call    cs:__imp_GetTickCount
0x14003aabd  mov     [rbp+160h+var_12C], eax
0x14003aac0  mov     [rbp+160h+var_15C], 0FFFFFFFFh
0x14003aac7  mov     eax, [rsp+260h+var_1F0]
0x14003aacb  mov     [rbp+160h+var_128], eax
0x14003aace  mov     [rbp+160h+var_160], r14d
0x14003aad2  mov     [rbp+160h+var_100], r14
0x14003aad6  xorps   xmm0, xmm0
0x14003aad9  movups  [rbp+160h+var_120], xmm0
0x14003aadd  movups  [rbp+160h+var_110], xmm0
0x14003aae1  mov     [rbp+160h+arg_8], r14
0x14003aae8  lea     rcx, [rbp+160h+arg_8]
0x14003aaef  call    cs:__imp_VssGetTracingContextPerThread
0x14003aaf5  test    eax, eax
0x14003aaf7  js      short loc_14003AB17
0x14003aaf9  lea     rcx, [rbp+160h+var_160]
0x14003aafd  call    cs:__imp_VssSetTracingContextPerThread
0x14003ab03  mov     rcx, [rbp+160h+var_100]
0x14003ab07  test    eax, eax
0x14003ab09  cmovns  rcx, [rbp+160h+arg_8]
0x14003ab11  mov     [rbp+160h+var_100], rcx
0x14003ab15  jmp     short loc_14003AB1B
0x14003ab17  mov     rcx, [rbp+160h+var_100]
0x14003ab1b  test    rcx, rcx
0x14003ab1e  jz      short loc_14003AB2A
0x14003ab20  mov     eax, [rcx+30h]
0x14003ab23  inc     eax
0x14003ab25  mov     [rbp+160h+var_130], eax
0x14003ab28  jmp     short loc_14003AB2E
0x14003ab2a  mov     [rbp+160h+var_130], r14d
0x14003ab2e  mov     edi, 0A0h
0x14003ab33  mov     ebx, edi
0x14003ab35  cmp     [rbp+160h+var_128], 0FFh
0x14003ab3c  cmovnz  ebx, [rbp+160h+var_128]
0x14003ab40  lea     rcx, [rbp+160h+var_160]; this
0x14003ab44  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14003ab49  lea     r15, aEnter; "ENTER"
0x14003ab50  test    eax, eax
0x14003ab52  jz      short loc_14003AB88
0x14003ab54  mov     [rsp+260h+var_220], r14
0x14003ab59  mov     [rsp+260h+var_228], ebx
0x14003ab5d  mov     [rsp+260h+var_230], r15
0x14003ab62  mov     rax, [rbp+160h+var_138]
0x14003ab66  mov     [rsp+260h+var_238], rax
0x14003ab6b  mov     eax, dword ptr [rbp+160h+var_140+4]
0x14003ab6e  mov     [rsp+260h+var_240], eax
0x14003ab72  mov     r9d, [rbp+160h+var_130]
0x14003ab76  mov     r8d, dword ptr [rbp+160h+var_140]
0x14003ab7a  mov     rdx, [rbp+160h+var_148]
0x14003ab7e  mov     rcx, [rbp+160h+var_150]
0x14003ab82  call    cs:__imp_VssTraceMessage
0x14003ab88  cmp     byte ptr [rbp+160h+var_170+3], r14b
0x14003ab8c  jz      short loc_14003ABAF
0x14003ab8e  mov     rbx, r14
0x14003ab91  mov     rcx, [rsp+rbx*8+260h+pv]; pv
0x14003ab96  test    rcx, rcx
0x14003ab99  jz      short loc_14003ABA6
0x14003ab9b  call    cs:__imp_CoTaskMemFree
0x14003aba1  mov     [rsp+rbx*8+260h+pv], r14
0x14003aba6  inc     rbx
0x14003aba9  cmp     rbx, 0Fh
0x14003abad  jnz     short loc_14003AB91
0x14003abaf  lea     r13, ?g_SnapshotSetCS@@3VCVssCriticalSection@@A; CVssCriticalSection g_SnapshotSetCS
0x14003abb6  mov     [rbp+160h+var_F0], r13
0x14003abba  lea     rax, aBaseStorVssInc_3; "base\\stor\\vss\\inc\\vs_types.hxx"
0x14003abc1  mov     [rbp+160h+var_D0], rax
0x14003abc8  lea     rax, aCvssautomaticl_0; "CVssAutomaticLock2::CVssAutomaticLock2"
0x14003abcf  mov     [rbp+160h+var_C8], rax
0x14003abd6  lea     rax, aInctypeh; "INCTYPEH"
0x14003abdd  mov     [rbp+160h+var_C0], rax
0x14003abe4  mov     [rbp+160h+var_B8], 100h
0x14003abee  mov     [rbp+160h+var_B4], 0Bh
0x14003abf8  mov     [rbp+160h+var_B0], 0FFh
0x14003ac02  mov     [rbp+160h+var_30], 1000000h
0x14003ac0c  xor     edx, edx; Val
0x14003ac0e  lea     r8d, [rdx+78h]; Size
0x14003ac12  lea     rcx, [rbp+160h+var_A8]; void *
0x14003ac19  call    memset_0
0x14003ac1e  mov     dword ptr [rsp+260h+var_208], r14d
0x14003ac23  mov     rax, [rbp+160h+var_C8]
0x14003ac2a  mov     [rsp+260h+pv], rax
0x14003ac2f  mov     rax, [rbp+160h+var_D0]
0x14003ac36  mov     [rsp+260h+var_200], rax
0x14003ac3b  mov     rax, [rbp+160h+var_C0]
0x14003ac42  mov     [rsp+260h+var_1F8], rax
0x14003ac47  mov     eax, [rbp+160h+var_B8]
0x14003ac4d  mov     [rsp+260h+var_1F0], eax
0x14003ac51  mov     eax, [rbp+160h+var_B4]
0x14003ac57  mov     [rsp+260h+var_1EC], eax
0x14003ac5b  call    cs:__imp_GetTickCount
0x14003ac61  mov     [rbp+160h+var_1DC], eax
0x14003ac64  mov     dword ptr [rsp+260h+var_210+4], 0FFFFFFFFh
0x14003ac6c  mov     eax, [rbp+160h+var_B0]
0x14003ac72  mov     [rbp+160h+var_1D8], eax
0x14003ac75  mov     dword ptr [rsp+260h+var_210], r14d
0x14003ac7a  mov     [rbp+160h+var_1B0], r14
0x14003ac7e  xorps   xmm0, xmm0
0x14003ac81  movups  [rbp+160h+var_1D0], xmm0
0x14003ac85  movups  [rbp+160h+var_1C0], xmm0
0x14003ac89  mov     [rbp+160h+arg_8], r14
0x14003ac90  lea     rcx, [rbp+160h+arg_8]
0x14003ac97  call    cs:__imp_VssGetTracingContextPerThread
0x14003ac9d  test    eax, eax
0x14003ac9f  js      short loc_14003ACC0
0x14003aca1  lea     rcx, [rsp+260h+var_210]
0x14003aca6  call    cs:__imp_VssSetTracingContextPerThread
0x14003acac  mov     rcx, [rbp+160h+var_1B0]
0x14003acb0  test    eax, eax
0x14003acb2  cmovns  rcx, [rbp+160h+arg_8]
0x14003acba  mov     [rbp+160h+var_1B0], rcx
0x14003acbe  jmp     short loc_14003ACC4
0x14003acc0  mov     rcx, [rbp+160h+var_1B0]
0x14003acc4  test    rcx, rcx
0x14003acc7  jz      short loc_14003ACD3
0x14003acc9  mov     eax, [rcx+30h]
0x14003accc  inc     eax
0x14003acce  mov     [rbp+160h+var_1E0], eax
0x14003acd1  jmp     short loc_14003ACD7
0x14003acd3  mov     [rbp+160h+var_1E0], r14d
0x14003acd7  cmp     [rbp+160h+var_1D8], 0FFh
0x14003acde  cmovnz  edi, [rbp+160h+var_1D8]
0x14003ace2  lea     rcx, [rsp+260h+var_210]; this
0x14003ace7  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14003acec  test    eax, eax
0x14003acee  jz      short loc_14003AD29
0x14003acf0  mov     [rsp+260h+var_220], r14
0x14003acf5  mov     [rsp+260h+var_228], edi
0x14003acf9  mov     [rsp+260h+var_230], r15
0x14003acfe  mov     rax, [rsp+260h+pv]
0x14003ad03  mov     [rsp+260h+var_238], rax
0x14003ad08  mov     eax, [rsp+260h+var_1EC]
0x14003ad0c  mov     [rsp+260h+var_240], eax
0x14003ad10  mov     r9d, [rbp+160h+var_1E0]
0x14003ad14  mov     r8d, [rsp+260h+var_1F0]
0x14003ad19  mov     rdx, [rsp+260h+var_1F8]
0x14003ad1e  mov     rcx, [rsp+260h+var_200]
0x14003ad23  call    cs:__imp_VssTraceMessage
0x14003ad29  cmp     byte ptr [rbp+160h+var_30+3], r14b
0x14003ad30  jz      short loc_14003AD59
0x14003ad32  mov     rbx, r14
0x14003ad35  mov     rcx, [rbp+rbx*8+160h+var_A8]; pv
0x14003ad3d  test    rcx, rcx
0x14003ad40  jz      short loc_14003AD50
0x14003ad42  call    cs:__imp_CoTaskMemFree
0x14003ad48  mov     [rbp+rbx*8+160h+var_A8], r14
0x14003ad50  inc     rbx
0x14003ad53  cmp     rbx, 0Fh
0x14003ad57  jnz     short loc_14003AD35
0x14003ad59  mov     rcx, r13; lpCriticalSection
0x14003ad5c  call    ?Lock@CVssCriticalSection@@QEAAXXZ; CVssCriticalSection::Lock(void)
0x14003ad61  mov     [rbp+160h+var_E8], 1
0x14003ad65  lea     rcx, [rsp+260h+var_210]; this
0x14003ad6a  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14003ad6f  nop
0x14003ad70  mov     r8d, 10h; Size
0x14003ad76  lea     rdx, GUID_NULL; Buf2
0x14003ad7d  lea     rcx, ?m_SnapshotSetID@CVssGlobalSnapshotSetId@@0U_GUID@@A; Buf1
0x14003ad84  call    memcmp_0
0x14003ad89  test    eax, eax
0x14003ad8b  jz      short loc_14003ADAC
0x14003ad8d  movups  xmm0, xmmword ptr cs:?m_SnapshotSetID@CVssGlobalSnapshotSetId@@0U_GUID@@A.Data1; _GUID CVssGlobalSnapshotSetId::m_SnapshotSetID ...
0x14003ad94  movdqu  xmmword ptr [rbp+160h+var_E0.Data1], xmm0
0x14003ad9c  lea     rdx, [rbp+160h+var_E0]; struct _GUID
0x14003ada3  mov     rcx, rsi; this
0x14003ada6  call    ?RecordSSID@CVssSnasphotSetIdObserver@@QEAAXU_GUID@@@Z; CVssSnasphotSetIdObserver::RecordSSID(_GUID)
0x14003adab  nop
0x14003adac  lea     rcx, [rbp+160h+var_F0]; this
0x14003adb0  call    ??1CVssAutomaticLock2@@QEAA@XZ; CVssAutomaticLock2::~CVssAutomaticLock2(void)
0x14003adb5  nop
0x14003adb6  lea     rcx, [rbp+160h+var_160]; this
0x14003adba  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14003adbf  lea     r11, [rsp+260h+var_20]
0x14003adc7  mov     rbx, [r11+30h]
0x14003adcb  mov     rsi, [r11+40h]
0x14003adcf  mov     rsp, r11
0x14003add2  pop     r15
0x14003add4  pop     r14
0x14003add6  pop     r13
0x14003add8  pop     rdi
0x14003add9  pop     rbp
0x14003adda  retn
```
