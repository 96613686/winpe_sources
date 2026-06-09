# Windows::Telemetry::Art::Validate::Stop(wistd::unique_ptr<_PFIU_HISTORY_ENTRY,wil::process_heap_deleter> const &,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &,unsigned __int64,std::chrono::duration<int,std::ratio<60,1>>,bool,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &,uchar,bool,uchar,std::chrono::duration<int,std::ratio<60,1>>)

- ea: `0x1800bd8ec`
- end: `0x1800bdfc4`
- name: `?Stop@Validate@Art@Telemetry@Windows@@QEAAXAEBV?$unique_ptr@T_PFIU_HISTORY_ENTRY@@Uprocess_heap_deleter@wil@@@wistd@@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@_KV?$duration@HU?$ratio@$0DM@$00@std@@@89@_N1E4E3@Z`
- size: `1752`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1800bebb4`

## callees

- `0x180001350`
- `0x180003050`
- `0x180062ef8`
- `0x180062fbc`
- `0x180085644`
- `0x18008c454`
- `0x1800b781c`
- `0x1800bd8ec`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bd9a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bdccf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bd9a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bdccf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800bdddf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800bdddf`

## pseudocode

```c
__int64 __fastcall Windows::Telemetry::Art::Validate::Stop(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 a4,
        int a5,
        char a6,
        __int64 a7,
        char a8,
        char a9,
        char a10,
        int a11)
{
  int v12; // r12d
  _DWORD **v13; // r14
  __int64 v14; // r15
  int v15; // eax
  __int64 v16; // r15
  _DWORD **v17; // rsi
  RTL_SRWLOCK *v18; // rcx
  const struct _tlgProvider_t *v19; // rax
  int v20; // esi
  __int128 v21; // xmm0
  const struct _SYSTEMTIME *v22; // r8
  __int128 v23; // xmm0
  __int128 v24; // xmm0
  const struct _SYSTEMTIME *v25; // r8
  struct _SYSTEMTIME v26; // xmm0
  _DWORD *v27; // r8
  RTL_SRWLOCK *v28; // rcx
  const struct _tlgProvider_t *v29; // rax
  __int64 v30; // rsi
  const struct _SYSTEMTIME *v31; // r8
  __int128 v32; // xmm0
  const struct _SYSTEMTIME *v33; // r8
  __int128 v34; // xmm0
  DWORD CurrentThreadId; // eax
  _DWORD *v36; // r8
  char v38; // [rsp+100h] [rbp-80h] BYREF
  char v39; // [rsp+101h] [rbp-7Fh] BYREF
  char v40; // [rsp+102h] [rbp-7Eh] BYREF
  _BYTE v41[5]; // [rsp+103h] [rbp-7Dh] BYREF
  __int64 v42; // [rsp+108h] [rbp-78h] BYREF
  int v43; // [rsp+110h] [rbp-70h] BYREF
  DWORD v44; // [rsp+114h] [rbp-6Ch] BYREF
  __int64 v45; // [rsp+118h] [rbp-68h] BYREF
  __int64 v46; // [rsp+120h] [rbp-60h] BYREF
  __int64 v47; // [rsp+128h] [rbp-58h] BYREF
  int v48; // [rsp+130h] [rbp-50h] BYREF
  int v49; // [rsp+134h] [rbp-4Ch] BYREF
  int v50; // [rsp+138h] [rbp-48h] BYREF
  int v51; // [rsp+13Ch] [rbp-44h] BYREF
  __int64 v52; // [rsp+140h] [rbp-40h] BYREF
  __int64 v53; // [rsp+148h] [rbp-38h] BYREF
  unsigned __int16 v54; // [rsp+150h] [rbp-30h] BYREF
  __int64 v55; // [rsp+158h] [rbp-28h] BYREF
  __int64 v56; // [rsp+160h] [rbp-20h] BYREF
  __int64 v57; // [rsp+168h] [rbp-18h] BYREF
  __int64 v58; // [rsp+170h] [rbp-10h] BYREF
  __int64 v59; // [rsp+178h] [rbp-8h] BYREF
  __int64 v60; // [rsp+180h] [rbp+0h] BYREF
  __int64 v61; // [rsp+188h] [rbp+8h] BYREF
  __int64 v62; // [rsp+190h] [rbp+10h] BYREF
  __int64 v63; // [rsp+198h] [rbp+18h] BYREF
  __int64 v64; // [rsp+1A0h] [rbp+20h] BYREF
  __int64 v65; // [rsp+1A8h] [rbp+28h] BYREF
  __int128 v66; // [rsp+1B0h] [rbp+30h] BYREF
  struct _SYSTEMTIME v67; // [rsp+1C0h] [rbp+40h] BYREF
  __int128 v68; // [rsp+1D0h] [rbp+50h] BYREF
  __int128 v69; // [rsp+1E0h] [rbp+60h] BYREF
  struct _SYSTEMTIME v70; // [rsp+1F0h] [rbp+70h] BYREF
  struct _SYSTEMTIME v71; // [rsp+200h] [rbp+80h] BYREF
  __int64 v72; // [rsp+210h] [rbp+90h] BYREF
  __int16 v73; // [rsp+218h] [rbp+98h]
  struct _SYSTEMTIME SystemTime; // [rsp+220h] [rbp+A0h] BYREF
  struct _SYSTEMTIME v75; // [rsp+230h] [rbp+B0h] BYREF
  struct _SYSTEMTIME LocalTime; // [rsp+240h] [rbp+C0h] BYREF
  struct _SYSTEMTIME v77; // [rsp+250h] [rbp+D0h] BYREF
  struct _SYSTEMTIME v78; // [rsp+260h] [rbp+E0h] BYREF
  struct _SYSTEMTIME v79; // [rsp+270h] [rbp+F0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v80; // [rsp+280h] [rbp+100h] BYREF
  __int64 *v81; // [rsp+2A0h] [rbp+120h]
  __int64 v82; // [rsp+2A8h] [rbp+128h]
  int *v83; // [rsp+2B0h] [rbp+130h]
  __int64 v84; // [rsp+2B8h] [rbp+138h]
  DWORD *v85; // [rsp+2C0h] [rbp+140h]
  __int64 v86; // [rsp+2C8h] [rbp+148h]
  unsigned __int16 *v87; // [rsp+2D0h] [rbp+150h]
  __int64 v88; // [rsp+2D8h] [rbp+158h]
  __int64 v89; // [rsp+2E0h] [rbp+160h]
  int v90; // [rsp+2E8h] [rbp+168h]
  int v91; // [rsp+2ECh] [rbp+16Ch]
  __int128 *v92; // [rsp+2F0h] [rbp+170h]
  __int64 v93; // [rsp+2F8h] [rbp+178h]
  struct _SYSTEMTIME *v94; // [rsp+300h] [rbp+180h]
  __int64 v95; // [rsp+308h] [rbp+188h]
  __int64 *v96; // [rsp+310h] [rbp+190h]
  __int64 v97; // [rsp+318h] [rbp+198h]
  char *v98; // [rsp+320h] [rbp+1A0h]
  __int64 v99; // [rsp+328h] [rbp+1A8h]
  __int64 *v100; // [rsp+330h] [rbp+1B0h]
  __int64 v101; // [rsp+338h] [rbp+1B8h]
  char *v102; // [rsp+340h] [rbp+1C0h]
  __int64 v103; // [rsp+348h] [rbp+1C8h]
  __int128 *v104; // [rsp+350h] [rbp+1D0h]
  __int64 v105; // [rsp+358h] [rbp+1D8h]
  __int128 *v106; // [rsp+360h] [rbp+1E0h]
  __int64 v107; // [rsp+368h] [rbp+1E8h]
  char *v108; // [rsp+370h] [rbp+1F0h]
  __int64 v109; // [rsp+378h] [rbp+1F8h]
  _BYTE *v110; // [rsp+380h] [rbp+200h]
  __int64 v111; // [rsp+388h] [rbp+208h]
  const char *v112; // [rsp+390h] [rbp+210h]
  __int64 v113; // [rsp+398h] [rbp+218h]

  LOWORD(v12) = a4;
  v46 = a7;
  v47 = a2;
  v13 = (_DWORD **)(a1 + 272);
  v14 = *(_QWORD *)(a1 + 272);
  v15 = *(_DWORD *)(v14 + 72);
  if ( a4 > 10080 / a5 )
    v12 = 10080 / a5;
  if ( v15 < 0 && (v16 = v14 + 80, v15 == *(_DWORD *)(v16 + 8)) )
  {
    v17 = (_DWORD **)(a1 + 272);
    if ( v16 )
    {
      v42 = 0;
      wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        a1,
        &v42);
      v18 = (RTL_SRWLOCK *)v42;
      **v13 = 2;
      if ( v18 )
        ReleaseSRWLockExclusive(v18);
      v19 = Windows::Telemetry::Base::Provider();
      v20 = (int)v19;
      if ( *(_DWORD *)v19 > 5u
        && (*((_QWORD *)v19 + 2) & 0x400000000000LL) != 0
        && (*((_QWORD *)v19 + 3) & 0x400000000000LL) == *((_QWORD *)v19 + 3) )
      {
        v64 = (__int64)"1507.2603.28012.0";
        v38 = a9;
        v39 = a8;
        v21 = *(_OWORD *)Windows::Time::to_systemtime(&SystemTime);
        v65 = (__int64)&v66;
        v66 = v21;
        v67 = *(struct _SYSTEMTIME *)Windows::Time::to_systemtime(&v75);
        v23 = (__int128)*Windows::Time::to_local(&LocalTime, &v67, v22);
        v49 = a5;
        v46 = (__int64)&v68;
        v40 = a6;
        v48 = a11;
        v41[0] = a10;
        v68 = v23;
        v24 = *(_OWORD *)Windows::Time::to_systemtime(&v77);
        v55 = (__int64)&v69;
        v69 = v24;
        v70 = *(struct _SYSTEMTIME *)Windows::Time::to_systemtime(&v78);
        v26 = *Windows::Time::to_local(&v79, &v70, v25);
        v73 = v12;
        v56 = (__int64)&v71;
        v71 = v26;
        v72 = *(_QWORD *)v47;
        v47 = *(_QWORD *)(v16 + 120);
        v57 = *(_QWORD *)(v16 + 112);
        v50 = *(_DWORD *)(v16 + 104);
        v58 = *(_QWORD *)(v16 + 96);
        v59 = *(_QWORD *)(v16 + 88);
        v51 = *(_DWORD *)(v16 + 80);
        v60 = *(_QWORD *)(v16 + 72);
        v43 = *(_DWORD *)(v16 + 32);
        v61 = *(_QWORD *)(v16 + 24);
        v44 = *(_DWORD *)v16;
        v62 = *(_QWORD *)(v16 + 128);
        LODWORD(v45) = *(_DWORD *)(v16 + 64);
        v63 = *(_QWORD *)(v16 + 56);
        v27 = *v13;
        LODWORD(v42) = *(_DWORD *)(v16 + 8);
        v53 = 0x1000000;
        v52 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperArray<2>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<char>>(
          v20,
          (int)&byte_180131C01,
          (_DWORD)v27 + 8,
          (__int64)&v52,
          (__int64)&v53,
          (__int64)&v42,
          (__int64)&v63,
          (__int64)&v45,
          (__int64)&v62,
          (__int64)&v44,
          (__int64)&v61,
          (__int64)&v43,
          (__int64)&v60,
          (__int64)&v51,
          (__int64)&v59,
          (__int64)&v58,
          (__int64)&v50,
          (__int64)&v57,
          (__int64)&v47,
          (__int64)&v72,
          (__int64)&v56,
          (__int64)&v55,
          (__int64)&v49,
          (__int64)v41,
          (__int64)&v48,
          (__int64)&v40,
          (__int64)&v46,
          (__int64)&v65,
          (__int64)&v39,
          (__int64)&v38,
          (__int64)&v64);
      }
      return wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
    }
  }
  else
  {
    v17 = (_DWORD **)(a1 + 272);
  }
  v42 = 0;
  wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v42);
  v28 = (RTL_SRWLOCK *)v42;
  **v17 = 2;
  if ( v28 )
    ReleaseSRWLockExclusive(v28);
  v29 = Windows::Telemetry::Base::Provider();
  v30 = (__int64)v29;
  if ( *(_DWORD *)v29 > 5u
    && (*((_QWORD *)v29 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v29 + 3) & 0x400000000000LL) == *((_QWORD *)v29 + 3) )
  {
    v41[0] = a9;
    v40 = a8;
    v69 = *(_OWORD *)Windows::Time::to_systemtime(&v79);
    v71 = *(struct _SYSTEMTIME *)Windows::Time::to_systemtime(&v78);
    v32 = (__int128)*Windows::Time::to_local(&v77, &v71, v31);
    v39 = a6;
    LODWORD(v42) = a11;
    v38 = a10;
    v68 = v32;
    LODWORD(v45) = a5;
    v67 = *(struct _SYSTEMTIME *)Windows::Time::to_systemtime(&LocalTime);
    v70 = *(struct _SYSTEMTIME *)Windows::Time::to_systemtime(&v75);
    v34 = (__int128)*Windows::Time::to_local(&SystemTime, &v70, v33);
    v54 = v12;
    v66 = v34;
    v53 = *(_QWORD *)v47;
    CurrentThreadId = GetCurrentThreadId();
    v36 = *v13;
    v44 = CurrentThreadId;
    v113 = 18;
    v111 = 1;
    v43 = v36[18];
    v52 = 0x1000000;
    v112 = "1507.2603.28012.0";
    v110 = v41;
    v108 = &v40;
    v106 = &v69;
    v104 = &v68;
    v102 = &v39;
    v100 = &v42;
    v98 = &v38;
    v96 = &v45;
    v109 = 1;
    v107 = 16;
    v105 = 16;
    v103 = 1;
    v101 = 4;
    v99 = 1;
    v97 = 4;
    v95 = 16;
    v94 = &v67;
    v93 = 16;
    v92 = &v66;
    v88 = 2;
    v87 = &v54;
    v89 = v53;
    v91 = 0;
    v90 = 2 * v54;
    v85 = &v44;
    v83 = &v43;
    v81 = &v52;
    v86 = 4;
    v84 = 4;
    v82 = 8;
    tlgWriteTransfer_EventWriteTransfer(
      v30,
      (unsigned __int8 *)&byte_180131ACF,
      (const GUID *)(v36 + 2),
      0,
      0x12u,
      &v80);
  }
  return wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x1800bd8ec  mov     [rsp-8+arg_8], rbx
0x1800bd8f1  push    rbp
0x1800bd8f2  push    rsi
0x1800bd8f3  push    rdi
0x1800bd8f4  push    r12
0x1800bd8f6  push    r13
0x1800bd8f8  push    r14
0x1800bd8fa  push    r15
0x1800bd8fc  lea     rbp, [rsp-230h]
0x1800bd904  sub     rsp, 3B0h
0x1800bd90b  mov     rax, cs:__security_cookie
0x1800bd912  xor     rax, rsp
0x1800bd915  mov     [rbp+260h+var_40], rax
0x1800bd91c  mov     rax, [rbp+260h+arg_30]
0x1800bd923  mov     rdi, rcx
0x1800bd926  mov     ebx, [rbp+260h+arg_20]
0x1800bd92c  mov     r12, r9
0x1800bd92f  mov     [rbp+260h+var_2C0], rax
0x1800bd933  mov     r13, r8
0x1800bd936  mov     [rbp+260h+var_2B8], rdx
0x1800bd93a  mov     eax, 2760h
0x1800bd93f  cdq
0x1800bd940  lea     r14, [rdi+110h]
0x1800bd947  mov     r15, [r14]
0x1800bd94a  idiv    ebx
0x1800bd94c  movsxd  rcx, eax
0x1800bd94f  mov     eax, [r15+48h]
0x1800bd953  cmp     r9, rcx
0x1800bd956  cmova   r12, rcx
0x1800bd95a  test    eax, eax
0x1800bd95c  jns     loc_1800BDCA6
0x1800bd962  add     r15, 50h ; 'P'
0x1800bd966  cmp     eax, [r15+8]
0x1800bd96a  jnz     loc_1800BDCA6
0x1800bd970  mov     rsi, r14
0x1800bd973  test    r15, r15
0x1800bd976  jz      loc_1800BDCA9
0x1800bd97c  lea     rdx, [rbp+260h+var_2D8]
0x1800bd980  mov     [rbp+260h+var_2D8], 0
0x1800bd988  mov     rcx, rdi
0x1800bd98b  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800bd990  mov     rax, [r14]
0x1800bd993  mov     rcx, [rbp+260h+var_2D8]; SRWLock
0x1800bd997  mov     dword ptr [rax], 2
0x1800bd99d  test    rcx, rcx
0x1800bd9a0  jz      short loc_1800BD9A8
0x1800bd9a2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800bd9a8  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1800bd9ad  mov     rsi, rax
0x1800bd9b0  cmp     dword ptr [rax], 5
0x1800bd9b3  jbe     loc_1800BDF92
0x1800bd9b9  mov     rdx, 400000000000h
0x1800bd9c3  test    [rax+10h], rdx
0x1800bd9c7  jz      loc_1800BDF92
0x1800bd9cd  mov     rcx, [rax+18h]
0x1800bd9d1  and     rcx, rdx
0x1800bd9d4  cmp     rcx, [rax+18h]
0x1800bd9d8  jnz     loc_1800BDF92
0x1800bd9de  mov     rdx, [rbp+260h+var_2C0]
0x1800bd9e2  lea     rax, a15072603280120; "1507.2603.28012.0"
0x1800bd9e9  mov     [rbp+260h+var_240], rax
0x1800bd9ed  lea     rcx, [rbp+260h+SystemTime]; lpSystemTime
0x1800bd9f4  mov     al, [rbp+260h+arg_40]
0x1800bd9fa  mov     byte ptr [rbp+260h+var_2E0], al
0x1800bd9fd  mov     al, [rbp+260h+arg_38]
0x1800bda03  mov     byte ptr [rbp+260h+var_2E0+1], al
0x1800bda06  call    ?to_systemtime@Time@Windows@@YA?AU_SYSTEMTIME@@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; Windows::Time::to_systemtime(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x1800bda0b  mov     rdx, [rbp+260h+var_2C0]
0x1800bda0f  lea     rcx, [rbp+260h+var_1B0]; lpSystemTime
0x1800bda16  movups  xmm0, xmmword ptr [rax]
0x1800bda19  lea     rax, [rbp+260h+var_230]
0x1800bda1d  mov     [rbp+260h+var_238], rax
0x1800bda21  movdqu  [rbp+260h+var_230], xmm0
0x1800bda26  call    ?to_systemtime@Time@Windows@@YA?AU_SYSTEMTIME@@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; Windows::Time::to_systemtime(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x1800bda2b  lea     rdx, [rbp+260h+var_220]; retstr
0x1800bda2f  lea     rcx, [rbp+260h+LocalTime]; lpLocalTime
0x1800bda36  movups  xmm0, xmmword ptr [rax]
0x1800bda39  movdqu  xmmword ptr [rbp+260h+var_220.wYear], xmm0
0x1800bda3e  call    ?to_local@Time@Windows@@YA?AU_SYSTEMTIME@@AEBU3@@Z; Windows::Time::to_local(_SYSTEMTIME const &)
0x1800bda43  mov     rdx, r13
0x1800bda46  lea     rcx, [rbp+260h+var_190]; lpSystemTime
0x1800bda4d  movups  xmm0, xmmword ptr [rax]
0x1800bda50  lea     rax, [rbp+260h+var_210]
0x1800bda54  mov     dword ptr [rbp+260h+var_2B0+4], ebx
0x1800bda57  mov     [rbp+260h+var_2C0], rax
0x1800bda5b  mov     al, [rbp+260h+arg_28]
0x1800bda61  mov     byte ptr [rbp+260h+var_2E0+2], al
0x1800bda64  mov     eax, [rbp+260h+arg_50]
0x1800bda6a  mov     dword ptr [rbp+260h+var_2B0], eax
0x1800bda6d  mov     al, [rbp+260h+arg_48]
0x1800bda73  mov     byte ptr [rbp+260h+var_2E0+3], al
0x1800bda76  movdqu  [rbp+260h+var_210], xmm0
0x1800bda7b  call    ?to_systemtime@Time@Windows@@YA?AU_SYSTEMTIME@@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; Windows::Time::to_systemtime(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x1800bda80  mov     rdx, r13
0x1800bda83  lea     rcx, [rbp+260h+var_180]; lpSystemTime
0x1800bda8a  movups  xmm0, xmmword ptr [rax]
0x1800bda8d  lea     rax, [rbp+260h+var_200]
0x1800bda91  mov     [rbp+260h+var_288], rax
0x1800bda95  movdqu  [rbp+260h+var_200], xmm0
0x1800bda9a  call    ?to_systemtime@Time@Windows@@YA?AU_SYSTEMTIME@@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; Windows::Time::to_systemtime(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x1800bda9f  lea     rdx, [rbp+260h+var_1F0]; retstr
0x1800bdaa3  lea     rcx, [rbp+260h+var_170]; lpLocalTime
0x1800bdaaa  movups  xmm0, xmmword ptr [rax]
0x1800bdaad  movdqu  xmmword ptr [rbp+260h+var_1F0.wYear], xmm0
0x1800bdab2  call    ?to_local@Time@Windows@@YA?AU_SYSTEMTIME@@AEBU3@@Z; Windows::Time::to_local(_SYSTEMTIME const &)
0x1800bdab7  movups  xmm0, xmmword ptr [rax]
0x1800bdaba  lea     rax, [rbp+260h+var_1E0]
0x1800bdac1  mov     [rbp+260h+var_1C8], r12w
0x1800bdac9  mov     [rbp+260h+var_280], rax
0x1800bdacd  mov     rax, [rbp+260h+var_2B8]
0x1800bdad1  movdqu  xmmword ptr [rbp+260h+var_1E0.wYear], xmm0
0x1800bdad9  mov     rax, [rax]
0x1800bdadc  mov     [rbp+260h+var_1D0], rax
0x1800bdae3  mov     rax, [r15+78h]
0x1800bdae7  mov     [rbp+260h+var_2B8], rax
0x1800bdaeb  mov     rax, [r15+70h]
0x1800bdaef  mov     [rbp+260h+var_278], rax
0x1800bdaf3  mov     eax, [r15+68h]
0x1800bdaf7  mov     dword ptr [rbp+260h+var_2A8], eax
0x1800bdafa  mov     rax, [r15+60h]
0x1800bdafe  mov     [rbp+260h+var_270], rax
0x1800bdb02  mov     rax, [r15+58h]
0x1800bdb06  mov     [rbp+260h+var_268], rax
0x1800bdb0a  mov     eax, [r15+50h]
0x1800bdb0e  mov     dword ptr [rbp+260h+var_2A8+4], eax
0x1800bdb11  mov     rax, [r15+48h]
0x1800bdb15  mov     [rbp+260h+var_260], rax
0x1800bdb19  mov     eax, [r15+20h]
0x1800bdb1d  mov     dword ptr [rbp+260h+var_2D0], eax
0x1800bdb20  mov     rax, [r15+18h]
0x1800bdb24  mov     [rbp+260h+var_258], rax
0x1800bdb28  mov     eax, [r15]
0x1800bdb2b  mov     dword ptr [rbp+260h+var_2D0+4], eax
0x1800bdb2e  mov     rax, [r15+80h]
0x1800bdb35  mov     [rbp+260h+var_250], rax
0x1800bdb39  mov     eax, [r15+40h]
0x1800bdb3d  mov     dword ptr [rbp+260h+var_2C8], eax
0x1800bdb40  mov     rax, [r15+38h]
0x1800bdb44  mov     [rbp+260h+var_248], rax
0x1800bdb48  mov     eax, [r15+8]
0x1800bdb4c  lea     rdx, byte_180131C01; int
0x1800bdb53  mov     r8, [r14]
0x1800bdb56  mov     rcx, rsi; int
0x1800bdb59  mov     dword ptr [rbp+260h+var_2D8], eax
0x1800bdb5c  add     r8, 8; int
0x1800bdb60  mov     eax, 1000000h
0x1800bdb65  mov     [rbp+260h+var_298], rax
0x1800bdb69  mov     [rbp+260h+var_2A0], rax
0x1800bdb6d  lea     rax, [rbp+260h+var_240]
0x1800bdb71  mov     [rsp+3E0h+var_2E8], rax; __int64
0x1800bdb79  lea     rax, [rbp+260h+var_2E0]
0x1800bdb7d  mov     [rsp+3E0h+var_2F0], rax; __int64
0x1800bdb85  lea     rax, [rbp+260h+var_2E0+1]
0x1800bdb89  mov     [rsp+3E0h+var_2F8], rax; __int64
0x1800bdb91  lea     rax, [rbp+260h+var_238]
0x1800bdb95  mov     [rsp+3E0h+var_300], rax; __int64
0x1800bdb9d  lea     rax, [rbp+260h+var_2C0]
0x1800bdba1  mov     [rsp+3E0h+var_308], rax; __int64
0x1800bdba9  lea     rax, [rbp+260h+var_2E0+2]
0x1800bdbad  mov     [rsp+3E0h+var_310], rax; __int64
0x1800bdbb5  lea     rax, [rbp+260h+var_2B0]
0x1800bdbb9  mov     [rsp+3E0h+var_318], rax; __int64
0x1800bdbc1  lea     rax, [rbp+260h+var_2E0+3]
0x1800bdbc5  mov     [rsp+3E0h+var_320], rax; __int64
0x1800bdbcd  lea     rax, [rbp+260h+var_2B0+4]
0x1800bdbd1  mov     [rsp+3E0h+var_328], rax; __int64
0x1800bdbd9  lea     rax, [rbp+260h+var_288]
0x1800bdbdd  mov     [rsp+3E0h+var_330], rax; __int64
0x1800bdbe5  lea     rax, [rbp+260h+var_280]
0x1800bdbe9  mov     [rsp+3E0h+var_338], rax; __int64
0x1800bdbf1  lea     rax, [rbp+260h+var_1D0]
0x1800bdbf8  mov     [rsp+3E0h+var_340], rax; __int64
0x1800bdc00  lea     rax, [rbp+260h+var_2B8]
0x1800bdc04  mov     [rsp+3E0h+var_348], rax; __int64
0x1800bdc0c  lea     rax, [rbp+260h+var_278]
0x1800bdc10  mov     [rsp+3E0h+var_350], rax; __int64
0x1800bdc18  lea     rax, [rbp+260h+var_2A8]
0x1800bdc1c  mov     [rsp+3E0h+var_358], rax; __int64
0x1800bdc24  lea     rax, [rbp+260h+var_270]
0x1800bdc28  mov     [rsp+3E0h+var_360], rax; __int64
0x1800bdc30  lea     rax, [rbp+260h+var_268]
0x1800bdc34  mov     [rsp+3E0h+var_368], rax; __int64
0x1800bdc39  lea     rax, [rbp+260h+var_2A8+4]
0x1800bdc3d  mov     [rsp+3E0h+var_370], rax; __int64
0x1800bdc42  lea     rax, [rbp+260h+var_260]
0x1800bdc46  mov     [rsp+3E0h+var_378], rax; __int64
0x1800bdc4b  lea     rax, [rbp+260h+var_2D0]
0x1800bdc4f  mov     [rsp+3E0h+var_380], rax; __int64
0x1800bdc54  lea     rax, [rbp+260h+var_258]
0x1800bdc58  mov     [rsp+3E0h+var_388], rax; __int64
0x1800bdc5d  lea     rax, [rbp+260h+var_2D0+4]
0x1800bdc61  mov     [rsp+3E0h+var_390], rax; __int64
0x1800bdc66  lea     rax, [rbp+260h+var_250]
0x1800bdc6a  mov     [rsp+3E0h+var_398], rax; __int64
0x1800bdc6f  lea     rax, [rbp+260h+var_2C8]
0x1800bdc73  mov     [rsp+3E0h+var_3A0], rax; __int64
0x1800bdc78  lea     rax, [rbp+260h+var_248]
0x1800bdc7c  mov     [rsp+3E0h+var_3A8], rax; __int64
0x1800bdc81  lea     rax, [rbp+260h+var_2D8]
0x1800bdc85  mov     [rsp+3E0h+var_3B0], rax; __int64
0x1800bdc8a  lea     rax, [rbp+260h+var_298]
0x1800bdc8e  mov     [rsp+3E0h+var_3B8], rax; __int64
0x1800bdc93  lea     rax, [rbp+260h+var_2A0]
0x1800bdc97  mov     qword ptr [rsp+3E0h+var_3C0], rax; __int64
0x1800bdc9c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U?$_tlgWrapperArray@$01@@U?$_tlgWrapperByRef@$0BA@@@U6@U2@U?$_tlgWrapperByVal@$00@@U2@U7@U6@U6@U7@U7@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456AEBU?$_tlgWrapperArray@$01@@AEBU?$_tlgWrapperByRef@$0BA@@@84AEBU?$_tlgWrapperByVal@$00@@4988995@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperArray<2>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperArray<2> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<char> const &)
0x1800bdca1  jmp     loc_1800BDF92
0x1800bdca6  mov     rsi, r14
0x1800bdca9  lea     rdx, [rbp+260h+var_2D8]
0x1800bdcad  mov     [rbp+260h+var_2D8], 0
0x1800bdcb5  mov     rcx, rdi
0x1800bdcb8  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800bdcbd  mov     rax, [rsi]
0x1800bdcc0  mov     rcx, [rbp+260h+var_2D8]; SRWLock
0x1800bdcc4  mov     dword ptr [rax], 2
0x1800bdcca  test    rcx, rcx
0x1800bdccd  jz      short loc_1800BDCD5
0x1800bdccf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800bdcd5  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1800bdcda  mov     rsi, rax
0x1800bdcdd  cmp     dword ptr [rax], 5
0x1800bdce0  jbe     loc_1800BDF92
0x1800bdce6  mov     rdx, 400000000000h
0x1800bdcf0  test    [rax+10h], rdx
0x1800bdcf4  jz      loc_1800BDF92
0x1800bdcfa  mov     rcx, [rax+18h]
0x1800bdcfe  and     rcx, rdx
0x1800bdd01  cmp     rcx, [rax+18h]
0x1800bdd05  jnz     loc_1800BDF92
0x1800bdd0b  mov     al, [rbp+260h+arg_40]
0x1800bdd11  lea     rcx, [rbp+260h+var_170]; lpSystemTime
0x1800bdd18  mov     rdx, [rbp+260h+var_2C0]
0x1800bdd1c  mov     byte ptr [rbp+260h+var_2E0+3], al
0x1800bdd1f  mov     al, [rbp+260h+arg_38]
0x1800bdd25  mov     byte ptr [rbp+260h+var_2E0+2], al
0x1800bdd28  call    ?to_systemtime@Time@Windows@@YA?AU_SYSTEMTIME@@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; Windows::Time::to_systemtime(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x1800bdd2d  mov     rdx, [rbp+260h+var_2C0]
0x1800bdd31  lea     rcx, [rbp+260h+var_180]; lpSystemTime
0x1800bdd38  movups  xmm0, xmmword ptr [rax]
0x1800bdd3b  movdqu  [rbp+260h+var_200], xmm0
0x1800bdd40  call    ?to_systemtime@Time@Windows@@YA?AU_SYSTEMTIME@@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; Windows::Time::to_systemtime(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x1800bdd45  lea     rdx, [rbp+260h+var_1E0]; retstr
0x1800bdd4c  lea     rcx, [rbp+260h+var_190]; lpLocalTime
0x1800bdd53  movups  xmm0, xmmword ptr [rax]
0x1800bdd56  movdqu  xmmword ptr [rbp+260h+var_1E0.wYear], xmm0
0x1800bdd5e  call    ?to_local@Time@Windows@@YA?AU_SYSTEMTIME@@AEBU3@@Z; Windows::Time::to_local(_SYSTEMTIME const &)
0x1800bdd63  mov     rdx, r13
0x1800bdd66  lea     rcx, [rbp+260h+LocalTime]; lpSystemTime
0x1800bdd6d  movups  xmm0, xmmword ptr [rax]
0x1800bdd70  mov     al, [rbp+260h+arg_28]
0x1800bdd76  mov     byte ptr [rbp+260h+var_2E0+1], al
0x1800bdd79  mov     eax, [rbp+260h+arg_50]
0x1800bdd7f  mov     dword ptr [rbp+260h+var_2D8], eax
0x1800bdd82  mov     al, [rbp+260h+arg_48]
0x1800bdd88  mov     byte ptr [rbp+260h+var_2E0], al
0x1800bdd8b  movdqu  [rbp+260h+var_210], xmm0
0x1800bdd90  mov     dword ptr [rbp+260h+var_2C8], ebx
0x1800bdd93  call    ?to_systemtime@Time@Windows@@YA?AU_SYSTEMTIME@@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; Windows::Time::to_systemtime(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x1800bdd98  mov     rdx, r13
0x1800bdd9b  lea     rcx, [rbp+260h+var_1B0]; lpSystemTime
0x1800bdda2  movups  xmm0, xmmword ptr [rax]
0x1800bdda5  movdqu  xmmword ptr [rbp+260h+var_220.wYear], xmm0
0x1800bddaa  call    ?to_systemtime@Time@Windows@@YA?AU_SYSTEMTIME@@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; Windows::Time::to_systemtime(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x1800bddaf  lea     rdx, [rbp+260h+var_1F0]; retstr
0x1800bddb3  lea     rcx, [rbp+260h+SystemTime]; lpLocalTime
0x1800bddba  movups  xmm0, xmmword ptr [rax]
0x1800bddbd  movdqu  xmmword ptr [rbp+260h+var_1F0.wYear], xmm0
0x1800bddc2  call    ?to_local@Time@Windows@@YA?AU_SYSTEMTIME@@AEBU3@@Z; Windows::Time::to_local(_SYSTEMTIME const &)
0x1800bddc7  movups  xmm0, xmmword ptr [rax]
0x1800bddca  mov     rax, [rbp+260h+var_2B8]
0x1800bddce  mov     [rbp+260h+var_290], r12w
0x1800bddd3  movdqu  [rbp+260h+var_230], xmm0
0x1800bddd8  mov     rax, [rax]
0x1800bdddb  mov     [rbp+260h+var_298], rax
0x1800bdddf  call    cs:__imp_GetCurrentThreadId
0x1800bdde5  mov     r8, [r14]
0x1800bdde8  mov     r10d, 12h
0x1800bddee  mov     dword ptr [rbp+260h+var_2D0+4], eax
0x1800bddf1  xor     r11d, r11d
0x1800bddf4  mov     [rbp+260h+var_48], r10
0x1800bddfb  mov     [rbp+260h+var_58], 1
0x1800bde06  mov     eax, [r8+48h]
0x1800bde0a  mov     dword ptr [rbp+260h+var_2D0], eax
0x1800bde0d  mov     eax, 1000000h
0x1800bde12  mov     [rbp+260h+var_2A0], rax
0x1800bde16  lea     rax, a15072603280120; "1507.2603.28012.0"
0x1800bde1d  mov     [rbp+260h+var_50], rax
0x1800bde24  lea     rax, [rbp+260h+var_2E0+3]
0x1800bde28  mov     [rbp+260h+var_60], rax
0x1800bde2f  lea     rax, [rbp+260h+var_2E0+2]
0x1800bde33  mov     [rbp+260h+var_70], rax
0x1800bde3a  lea     rax, [rbp+260h+var_200]
0x1800bde3e  mov     [rbp+260h+var_80], rax
0x1800bde45  lea     rax, [rbp+260h+var_210]
0x1800bde49  mov     [rbp+260h+var_90], rax
0x1800bde50  lea     rax, [rbp+260h+var_2E0+1]
0x1800bde54  mov     [rbp+260h+var_A0], rax
0x1800bde5b  lea     rax, [rbp+260h+var_2D8]
0x1800bde5f  mov     [rbp+260h+var_B0], rax
0x1800bde66  lea     rax, [rbp+260h+var_2E0]
0x1800bde6a  mov     [rbp+260h+var_C0], rax
  ... truncated ...
```
