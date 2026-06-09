# Windows::Telemetry::Art::Schedule::Stop(Windows::ARTSmartScheduler::QueryResult &,wchar_t const *,uchar,std::chrono::duration<int,std::ratio<60,1>>,std::optional<double>)

- ea: `0x1800bc610`
- end: `0x1800bcdf1`
- name: `?Stop@Schedule@Art@Telemetry@Windows@@QEAAXAEAUQueryResult@ARTSmartScheduler@4@PEB_WEV?$duration@HU?$ratio@$0DM@$00@std@@@chrono@std@@V?$optional@N@9@@Z`
- size: `2017`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180097020`
- `0x1800be1ec`

## callees

- `0x180001350`
- `0x180002778`
- `0x180062ef8`
- `0x180062fbc`
- `0x180085644`
- `0x18008c454`
- `0x1800b781c`
- `0x1800bc610`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bc6a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bca58`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bc6a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bca58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800bcbde`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800bcbde`

## pseudocode

```c
void __fastcall Windows::Telemetry::Art::Schedule::Stop(
        __int64 a1,
        __int64 a2,
        const OLECHAR *a3,
        char a4,
        int a5,
        __int64 a6)
{
  _DWORD **v6; // rax
  __int64 v7; // r13
  __int64 v8; // rdi
  int v11; // ecx
  int *v12; // r13
  _DWORD **v13; // rbx
  RTL_SRWLOCK *v14; // rcx
  const struct _tlgProvider_t *v15; // rax
  int v16; // r15d
  int v17; // ecx
  const wchar_t *v18; // rdi
  int v19; // ecx
  int v20; // ecx
  const wchar_t *v21; // rsi
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  __int128 v25; // xmm0
  const struct _SYSTEMTIME *v26; // r8
  __int128 v27; // xmm0
  __int128 v28; // xmm0
  const struct _SYSTEMTIME *v29; // r8
  __int64 v30; // r9
  struct _SYSTEMTIME v31; // xmm0
  __int64 v32; // xmm0_8
  __int64 v33; // r8
  int v34; // r15d
  RTL_SRWLOCK *v35; // rcx
  const struct _tlgProvider_t *v36; // rax
  __int64 v37; // r13
  int v38; // ecx
  const wchar_t *v39; // rdi
  int v40; // ecx
  int v41; // ecx
  const wchar_t *v42; // rsi
  int v43; // ecx
  int v44; // ecx
  int v45; // ecx
  const struct _SYSTEMTIME *v46; // r8
  const struct _SYSTEMTIME *v47; // r8
  __int64 v48; // xmm0_8
  __int64 v49; // r8
  __int64 v50; // rcx
  __int64 v51; // r15
  __int64 v52; // rax
  char v53; // [rsp+100h] [rbp-80h] BYREF
  char v54; // [rsp+101h] [rbp-7Fh] BYREF
  char v55; // [rsp+102h] [rbp-7Eh]
  __int64 v56; // [rsp+108h] [rbp-78h] BYREF
  int v57; // [rsp+110h] [rbp-70h] BYREF
  DWORD CurrentThreadId; // [rsp+114h] [rbp-6Ch] BYREF
  int v59; // [rsp+118h] [rbp-68h] BYREF
  int v60; // [rsp+11Ch] [rbp-64h] BYREF
  int v61; // [rsp+120h] [rbp-60h] BYREF
  int v62; // [rsp+124h] [rbp-5Ch] BYREF
  __int64 v63; // [rsp+128h] [rbp-58h]
  __int64 v64; // [rsp+130h] [rbp-50h] BYREF
  __int64 v65; // [rsp+138h] [rbp-48h] BYREF
  __int64 v66; // [rsp+140h] [rbp-40h] BYREF
  __int64 v67; // [rsp+148h] [rbp-38h] BYREF
  __int64 v68; // [rsp+150h] [rbp-30h] BYREF
  __int64 v69; // [rsp+158h] [rbp-28h] BYREF
  __int64 v70; // [rsp+160h] [rbp-20h] BYREF
  __int64 v71; // [rsp+168h] [rbp-18h] BYREF
  __int64 v72; // [rsp+170h] [rbp-10h] BYREF
  __int64 v73; // [rsp+178h] [rbp-8h] BYREF
  __int64 v74; // [rsp+180h] [rbp+0h] BYREF
  __int64 v75; // [rsp+188h] [rbp+8h] BYREF
  __int64 v76; // [rsp+190h] [rbp+10h] BYREF
  __int64 v77; // [rsp+198h] [rbp+18h] BYREF
  __int64 v78; // [rsp+1A0h] [rbp+20h] BYREF
  __int64 v79; // [rsp+1A8h] [rbp+28h] BYREF
  __int64 v80; // [rsp+1B0h] [rbp+30h] BYREF
  __int64 v81; // [rsp+1B8h] [rbp+38h] BYREF
  __int64 v82; // [rsp+1C0h] [rbp+40h] BYREF
  __int128 v83; // [rsp+1C8h] [rbp+48h] BYREF
  struct _SYSTEMTIME v84; // [rsp+1D8h] [rbp+58h] BYREF
  __int128 v85; // [rsp+1E8h] [rbp+68h] BYREF
  __int128 v86; // [rsp+1F8h] [rbp+78h] BYREF
  struct _SYSTEMTIME v87; // [rsp+208h] [rbp+88h] BYREF
  struct _SYSTEMTIME v88; // [rsp+218h] [rbp+98h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+228h] [rbp+A8h] BYREF
  struct _SYSTEMTIME v90; // [rsp+238h] [rbp+B8h] BYREF
  struct _SYSTEMTIME LocalTime; // [rsp+248h] [rbp+C8h] BYREF
  struct _SYSTEMTIME v92; // [rsp+258h] [rbp+D8h] BYREF
  struct _SYSTEMTIME v93; // [rsp+268h] [rbp+E8h] BYREF
  struct _SYSTEMTIME v94; // [rsp+278h] [rbp+F8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v95; // [rsp+290h] [rbp+110h] BYREF
  __int64 *v96; // [rsp+2B0h] [rbp+130h]
  __int64 v97; // [rsp+2B8h] [rbp+138h]
  int *v98; // [rsp+2C0h] [rbp+140h]
  __int64 v99; // [rsp+2C8h] [rbp+148h]
  DWORD *p_CurrentThreadId; // [rsp+2D0h] [rbp+150h]
  __int64 v101; // [rsp+2D8h] [rbp+158h]
  char *v102; // [rsp+2E0h] [rbp+160h]
  __int64 v103; // [rsp+2E8h] [rbp+168h]
  __int64 *v104; // [rsp+2F0h] [rbp+170h]
  __int64 v105; // [rsp+2F8h] [rbp+178h]
  __int64 *v106; // [rsp+300h] [rbp+180h]
  __int64 v107; // [rsp+308h] [rbp+188h]
  __int128 *v108; // [rsp+310h] [rbp+190h]
  __int64 v109; // [rsp+318h] [rbp+198h]
  struct _SYSTEMTIME *v110; // [rsp+320h] [rbp+1A0h]
  __int64 v111; // [rsp+328h] [rbp+1A8h]
  __int128 *v112; // [rsp+330h] [rbp+1B0h]
  __int64 v113; // [rsp+338h] [rbp+1B8h]
  __int128 *v114; // [rsp+340h] [rbp+1C0h]
  __int64 v115; // [rsp+348h] [rbp+1C8h]
  char *v116; // [rsp+350h] [rbp+1D0h]
  __int64 v117; // [rsp+358h] [rbp+1D8h]
  const wchar_t *v118; // [rsp+360h] [rbp+1E0h]
  int v119; // [rsp+368h] [rbp+1E8h]
  int v120; // [rsp+36Ch] [rbp+1ECh]
  const wchar_t *v121; // [rsp+370h] [rbp+1F0h]
  int v122; // [rsp+378h] [rbp+1F8h]
  int v123; // [rsp+37Ch] [rbp+1FCh]
  const OLECHAR *v124; // [rsp+380h] [rbp+200h]
  int v125; // [rsp+388h] [rbp+208h]
  int v126; // [rsp+38Ch] [rbp+20Ch]
  const char *v127; // [rsp+390h] [rbp+210h]
  __int64 v128; // [rsp+398h] [rbp+218h]

  v6 = (_DWORD **)(a1 + 272);
  v63 = a1;
  v7 = *(_QWORD *)(a1 + 272);
  v8 = a1;
  v55 = a4;
  v11 = *(_DWORD *)(v7 + 72);
  if ( v11 < 0 && (v12 = (int *)(v7 + 80), v11 == v12[2]) )
  {
    v13 = v6;
    if ( v12 )
    {
      v56 = 0;
      wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        v8,
        &v56);
      v14 = (RTL_SRWLOCK *)v56;
      **v13 = 2;
      if ( v14 )
        ReleaseSRWLockExclusive(v14);
      v15 = Windows::Telemetry::Base::Provider();
      v16 = (int)v15;
      if ( *(_DWORD *)v15 > 5u
        && (*((_QWORD *)v15 + 2) & 0x400000000000LL) != 0
        && (*((_QWORD *)v15 + 3) & 0x400000000000LL) == *((_QWORD *)v15 + 3) )
      {
        v17 = *(_DWORD *)(a2 + 24);
        v81 = (__int64)"1507.2603.28012.0";
        v18 = L"Invalid";
        v82 = (__int64)a3;
        if ( v17 )
        {
          v19 = v17 - 1;
          if ( v19 )
          {
            v20 = v19 - 1;
            if ( v20 )
            {
              if ( v20 == 1 )
                v21 = L"Validation run";
              else
                v21 = L"Invalid";
            }
            else
            {
              v21 = L"Active hours";
            }
          }
          else
          {
            v21 = L"Next good time";
          }
        }
        else
        {
          v21 = L"Time interval check";
        }
        v22 = *(_DWORD *)(a2 + 20);
        v66 = (__int64)v21;
        if ( v22 )
        {
          v23 = v22 - 1;
          if ( v23 )
          {
            v24 = v23 - 1;
            if ( v24 )
            {
              if ( v24 == 1 )
                v18 = L"Confidence Not Met";
            }
            else
            {
              v18 = L"Not Enough Data";
            }
          }
          else
          {
            v18 = L"All Conditions Met";
          }
        }
        else
        {
          v18 = L"No Conditions Met";
        }
        v53 = *(_BYTE *)(a2 + 16);
        v67 = (__int64)v18;
        v25 = *(_OWORD *)Windows::Time::to_systemtime(&SystemTime);
        v68 = (__int64)&v83;
        v83 = v25;
        v84 = *(struct _SYSTEMTIME *)Windows::Time::to_systemtime(&v90);
        v27 = (__int128)*Windows::Time::to_local(&LocalTime, &v84, v26);
        v69 = (__int64)&v85;
        v85 = v27;
        v28 = *(_OWORD *)Windows::Time::to_systemtime(&v92);
        v70 = (__int64)&v86;
        v86 = v28;
        v87 = *(struct _SYSTEMTIME *)Windows::Time::to_systemtime(&v93);
        v31 = *Windows::Time::to_local(&v94, &v87, v29);
        v71 = (__int64)&v88;
        v88 = v31;
        if ( *(_BYTE *)(a6 + 8) )
          v32 = *(_QWORD *)a6;
        else
          v32 = 0;
        v59 = a5;
        v54 = v55;
        v73 = *((_QWORD *)v12 + 15);
        v74 = *((_QWORD *)v12 + 14);
        v60 = v12[26];
        v75 = *((_QWORD *)v12 + 12);
        v76 = *((_QWORD *)v12 + 11);
        v8 = v63;
        v61 = v12[20];
        v77 = *((_QWORD *)v12 + 9);
        v33 = *(_QWORD *)(v63 + 272);
        v62 = v12[8];
        v78 = *((_QWORD *)v12 + 3);
        v57 = *v12;
        v79 = *((_QWORD *)v12 + 16);
        CurrentThreadId = v12[16];
        v80 = *((_QWORD *)v12 + 7);
        LODWORD(v56) = v12[2];
        v64 = 0x1000000;
        v65 = 0x1000000;
        v72 = v32;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
          v16,
          (int)&byte_1801323C5,
          v33 + 8,
          v30,
          (__int64)&v65,
          (__int64)&v64,
          (__int64)&v56,
          (const wchar_t **)&v80,
          (__int64)&CurrentThreadId,
          (const wchar_t **)&v79,
          (__int64)&v57,
          (const OLECHAR **)&v78,
          (__int64)&v62,
          (const wchar_t **)&v77,
          (__int64)&v61,
          (const wchar_t **)&v76,
          (const OLECHAR **)&v75,
          (__int64)&v60,
          (const wchar_t **)&v74,
          (const OLECHAR **)&v73,
          (__int64)&v54,
          (__int64)&v59,
          (__int64)&v72,
          &v71,
          &v70,
          &v69,
          &v68,
          (__int64)&v53,
          (const OLECHAR **)&v67,
          (const OLECHAR **)&v66,
          (const OLECHAR **)&v82,
          (const wchar_t **)&v81);
      }
      goto LABEL_66;
    }
  }
  else
  {
    v13 = v6;
  }
  v56 = 0;
  wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    v8,
    &v56);
  v34 = 2;
  v35 = (RTL_SRWLOCK *)v56;
  **v13 = 2;
  if ( v35 )
    ReleaseSRWLockExclusive(v35);
  v36 = Windows::Telemetry::Base::Provider();
  v37 = (__int64)v36;
  if ( *(_DWORD *)v36 > 5u
    && (*((_QWORD *)v36 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v36 + 3) & 0x400000000000LL) == *((_QWORD *)v36 + 3) )
  {
    v38 = *(_DWORD *)(a2 + 24);
    v39 = L"Invalid";
    if ( v38 )
    {
      v40 = v38 - 1;
      if ( v40 )
      {
        v41 = v40 - 1;
        if ( v41 )
        {
          if ( v41 == 1 )
            v42 = L"Validation run";
          else
            v42 = L"Invalid";
        }
        else
        {
          v42 = L"Active hours";
        }
      }
      else
      {
        v42 = L"Next good time";
      }
    }
    else
    {
      v42 = L"Time interval check";
    }
    v43 = *(_DWORD *)(a2 + 20);
    if ( v43 )
    {
      v44 = v43 - 1;
      if ( v44 )
      {
        v45 = v44 - 1;
        if ( v45 )
        {
          if ( v45 == 1 )
            v39 = L"Confidence Not Met";
        }
        else
        {
          v39 = L"Not Enough Data";
        }
      }
      else
      {
        v39 = L"All Conditions Met";
      }
    }
    else
    {
      v39 = L"No Conditions Met";
    }
    v54 = *(_BYTE *)(a2 + 16);
    v86 = *(_OWORD *)Windows::Time::to_systemtime(&v94);
    v88 = *(struct _SYSTEMTIME *)Windows::Time::to_systemtime(&v93);
    v85 = (__int128)*Windows::Time::to_local(&v92, &v88, v46);
    v84 = *(struct _SYSTEMTIME *)Windows::Time::to_systemtime(&LocalTime);
    v87 = *(struct _SYSTEMTIME *)Windows::Time::to_systemtime(&v90);
    v83 = (__int128)*Windows::Time::to_local(&SystemTime, &v87, v47);
    if ( *(_BYTE *)(a6 + 8) )
      v48 = *(_QWORD *)a6;
    else
      v48 = 0;
    LODWORD(v56) = a5;
    v53 = v55;
    v65 = v48;
    CurrentThreadId = GetCurrentThreadId();
    v128 = 18;
    v49 = *(_QWORD *)(v63 + 272);
    v50 = -1;
    v57 = *(_DWORD *)(v49 + 72);
    v64 = 0x1000000;
    v127 = "1507.2603.28012.0";
    if ( a3 )
    {
      v51 = -1;
      do
        ++v51;
      while ( a3[v51] );
      v34 = 2 * v51 + 2;
    }
    else
    {
      a3 = &S1;
    }
    v124 = a3;
    v52 = -1;
    v125 = v34;
    v126 = 0;
    do
      ++v52;
    while ( v42[v52] );
    v121 = v42;
    v122 = 2 * v52 + 2;
    v123 = 0;
    do
      ++v50;
    while ( v39[v50] );
    v118 = v39;
    v119 = 2 * v50 + 2;
    v120 = 0;
    v116 = &v54;
    v117 = 1;
    v114 = &v86;
    v115 = 16;
    v112 = &v85;
    v113 = 16;
    v110 = &v84;
    v108 = &v83;
    v106 = &v65;
    v104 = &v56;
    v102 = &v53;
    p_CurrentThreadId = &CurrentThreadId;
    v98 = &v57;
    v96 = &v64;
    v111 = 16;
    v109 = 16;
    v107 = 8;
    v105 = 4;
    v103 = 1;
    v101 = 4;
    v99 = 4;
    v97 = 8;
    tlgWriteTransfer_EventWriteTransfer(v37, (unsigned __int8 *)&unk_180132258, (const GUID *)(v49 + 8), 0, 0x11u, &v95);
    v8 = v63;
  }
LABEL_66:
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(v8);
}

```

## disassembly

```asm
0x1800bc610  mov     [rsp-8+arg_10], rbx
0x1800bc615  push    rbp
0x1800bc616  push    rsi
0x1800bc617  push    rdi
0x1800bc618  push    r12
0x1800bc61a  push    r13
0x1800bc61c  push    r14
0x1800bc61e  push    r15
0x1800bc620  lea     rbp, [rsp-230h]
0x1800bc628  sub     rsp, 3B0h
0x1800bc62f  mov     rax, cs:__security_cookie
0x1800bc636  xor     rax, rsp
0x1800bc639  mov     [rbp+260h+var_40], rax
0x1800bc640  lea     rax, [rcx+110h]
0x1800bc647  mov     [rbp+260h+var_2B8], rcx
0x1800bc64b  mov     r13, [rax]
0x1800bc64e  mov     rdi, rcx
0x1800bc651  mov     byte ptr [rbp+260h+var_2E0+2], r9b
0x1800bc655  mov     r12, r8
0x1800bc658  mov     r14, rdx
0x1800bc65b  mov     ecx, [r13+48h]
0x1800bc65f  test    ecx, ecx
0x1800bc661  jns     loc_1800BCA2C
0x1800bc667  add     r13, 50h ; 'P'
0x1800bc66b  cmp     ecx, [r13+8]
0x1800bc66f  jnz     loc_1800BCA2C
0x1800bc675  mov     rbx, rax
0x1800bc678  test    r13, r13
0x1800bc67b  jz      loc_1800BCA2F
0x1800bc681  lea     rdx, [rbp+260h+var_2D8]
0x1800bc685  mov     [rbp+260h+var_2D8], 0
0x1800bc68d  mov     rcx, rdi
0x1800bc690  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800bc695  mov     rax, [rbx]
0x1800bc698  mov     rcx, [rbp+260h+var_2D8]; SRWLock
0x1800bc69c  mov     dword ptr [rax], 2
0x1800bc6a2  test    rcx, rcx
0x1800bc6a5  jz      short loc_1800BC6AD
0x1800bc6a7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800bc6ad  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1800bc6b2  mov     r15, rax
0x1800bc6b5  cmp     dword ptr [rax], 5
0x1800bc6b8  jbe     loc_1800BCDBF
0x1800bc6be  mov     rdx, 400000000000h
0x1800bc6c8  test    [rax+10h], rdx
0x1800bc6cc  jz      loc_1800BCDBF
0x1800bc6d2  mov     rcx, [rax+18h]
0x1800bc6d6  and     rcx, rdx
0x1800bc6d9  cmp     rcx, [rax+18h]
0x1800bc6dd  jnz     loc_1800BCDBF
0x1800bc6e3  mov     ecx, [r14+18h]
0x1800bc6e7  lea     rax, a15072603280120; "1507.2603.28012.0"
0x1800bc6ee  mov     [rbp+260h+var_228], rax
0x1800bc6f2  lea     rdi, aInvalid; "Invalid"
0x1800bc6f9  mov     [rbp+260h+var_220], r12
0x1800bc6fd  test    ecx, ecx
0x1800bc6ff  jz      short loc_1800BC730
0x1800bc701  sub     ecx, 1
0x1800bc704  jz      short loc_1800BC727
0x1800bc706  sub     ecx, 1
0x1800bc709  jz      short loc_1800BC71E
0x1800bc70b  cmp     ecx, 1
0x1800bc70e  jz      short loc_1800BC715
0x1800bc710  mov     rsi, rdi
0x1800bc713  jmp     short loc_1800BC737
0x1800bc715  lea     rsi, aValidationRun; "Validation run"
0x1800bc71c  jmp     short loc_1800BC737
0x1800bc71e  lea     rsi, aActiveHours; "Active hours"
0x1800bc725  jmp     short loc_1800BC737
0x1800bc727  lea     rsi, aNextGoodTime; "Next good time"
0x1800bc72e  jmp     short loc_1800BC737
0x1800bc730  lea     rsi, aTimeIntervalCh; "Time interval check"
0x1800bc737  mov     ecx, [r14+14h]
0x1800bc73b  mov     [rbp+260h+var_2A0], rsi
0x1800bc73f  test    ecx, ecx
0x1800bc741  jz      short loc_1800BC76D
0x1800bc743  sub     ecx, 1
0x1800bc746  jz      short loc_1800BC764
0x1800bc748  sub     ecx, 1
0x1800bc74b  jz      short loc_1800BC75B
0x1800bc74d  cmp     ecx, 1
0x1800bc750  jnz     short loc_1800BC774
0x1800bc752  lea     rdi, aConfidenceNotM; "Confidence Not Met"
0x1800bc759  jmp     short loc_1800BC774
0x1800bc75b  lea     rdi, aNotEnoughData; "Not Enough Data"
0x1800bc762  jmp     short loc_1800BC774
0x1800bc764  lea     rdi, aAllConditionsM; "All Conditions Met"
0x1800bc76b  jmp     short loc_1800BC774
0x1800bc76d  lea     rdi, aNoConditionsMe; "No Conditions Met"
0x1800bc774  mov     al, [r14+10h]
0x1800bc778  lea     rdx, [r14+8]
0x1800bc77c  lea     rcx, [rbp+260h+SystemTime]; lpSystemTime
0x1800bc783  mov     byte ptr [rbp+260h+var_2E0], al
0x1800bc786  mov     [rbp+260h+var_298], rdi
0x1800bc78a  call    ?to_systemtime@Time@Windows@@YA?AU_SYSTEMTIME@@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; Windows::Time::to_systemtime(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x1800bc78f  lea     rdx, [r14+8]
0x1800bc793  lea     rcx, [rbp+260h+var_1A8]; lpSystemTime
0x1800bc79a  movups  xmm0, xmmword ptr [rax]
0x1800bc79d  lea     rax, [rbp+260h+var_218]
0x1800bc7a1  mov     [rbp+260h+var_290], rax
0x1800bc7a5  movdqu  [rbp+260h+var_218], xmm0
0x1800bc7aa  call    ?to_systemtime@Time@Windows@@YA?AU_SYSTEMTIME@@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; Windows::Time::to_systemtime(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x1800bc7af  lea     rdx, [rbp+260h+var_208]; retstr
0x1800bc7b3  lea     rcx, [rbp+260h+LocalTime]; lpLocalTime
0x1800bc7ba  movups  xmm0, xmmword ptr [rax]
0x1800bc7bd  movdqu  xmmword ptr [rbp+260h+var_208.wYear], xmm0
0x1800bc7c2  call    ?to_local@Time@Windows@@YA?AU_SYSTEMTIME@@AEBU3@@Z; Windows::Time::to_local(_SYSTEMTIME const &)
0x1800bc7c7  mov     rdx, r14
0x1800bc7ca  lea     rcx, [rbp+260h+var_188]; lpSystemTime
0x1800bc7d1  movups  xmm0, xmmword ptr [rax]
0x1800bc7d4  lea     rax, [rbp+260h+var_1F8]
0x1800bc7d8  mov     [rbp+260h+var_288], rax
0x1800bc7dc  movdqu  [rbp+260h+var_1F8], xmm0
0x1800bc7e1  call    ?to_systemtime@Time@Windows@@YA?AU_SYSTEMTIME@@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; Windows::Time::to_systemtime(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x1800bc7e6  mov     rdx, r14
0x1800bc7e9  lea     rcx, [rbp+260h+var_178]; lpSystemTime
0x1800bc7f0  movups  xmm0, xmmword ptr [rax]
0x1800bc7f3  lea     rax, [rbp+260h+var_1E8]
0x1800bc7f7  mov     [rbp+260h+var_280], rax
0x1800bc7fb  movdqu  [rbp+260h+var_1E8], xmm0
0x1800bc800  call    ?to_systemtime@Time@Windows@@YA?AU_SYSTEMTIME@@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; Windows::Time::to_systemtime(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x1800bc805  lea     rdx, [rbp+260h+var_1D8]; retstr
0x1800bc80c  lea     rcx, [rbp+260h+var_168]; lpLocalTime
0x1800bc813  movups  xmm0, xmmword ptr [rax]
0x1800bc816  movdqu  xmmword ptr [rbp+260h+var_1D8.wYear], xmm0
0x1800bc81e  call    ?to_local@Time@Windows@@YA?AU_SYSTEMTIME@@AEBU3@@Z; Windows::Time::to_local(_SYSTEMTIME const &)
0x1800bc823  movups  xmm0, xmmword ptr [rax]
0x1800bc826  lea     rax, [rbp+260h+var_1C8]
0x1800bc82d  mov     [rbp+260h+var_278], rax
0x1800bc831  mov     rax, [rbp+260h+arg_28]
0x1800bc838  movdqu  xmmword ptr [rbp+260h+var_1C8.wYear], xmm0
0x1800bc840  cmp     byte ptr [rax+8], 0
0x1800bc844  jz      short loc_1800BC84C
0x1800bc846  movsd   xmm0, qword ptr [rax]
0x1800bc84a  jmp     short loc_1800BC84F
0x1800bc84c  xorps   xmm0, xmm0
0x1800bc84f  mov     eax, [rbp+260h+arg_20]
0x1800bc855  mov     dword ptr [rbp+260h+var_2C8], eax
0x1800bc858  mov     al, byte ptr [rbp+260h+var_2E0+2]
0x1800bc85b  mov     byte ptr [rbp+260h+var_2E0+1], al
0x1800bc85e  mov     rax, [r13+78h]
0x1800bc862  mov     [rbp+260h+var_268], rax
0x1800bc866  mov     rax, [r13+70h]
0x1800bc86a  mov     [rbp+260h+var_260], rax
0x1800bc86e  mov     eax, [r13+68h]
0x1800bc872  mov     dword ptr [rbp+260h+var_2C8+4], eax
0x1800bc875  mov     rax, [r13+60h]
0x1800bc879  mov     [rbp+260h+var_258], rax
0x1800bc87d  mov     rax, [r13+58h]
0x1800bc881  mov     [rbp+260h+var_250], rax
0x1800bc885  mov     eax, [r13+50h]
0x1800bc889  mov     rdi, [rbp+260h+var_2B8]
0x1800bc88d  mov     dword ptr [rbp+260h+var_2C0], eax
0x1800bc890  mov     rax, [r13+48h]
0x1800bc894  mov     [rbp+260h+var_248], rax
0x1800bc898  mov     eax, [r13+20h]
0x1800bc89c  mov     r8, [rdi+110h]
0x1800bc8a3  mov     dword ptr [rbp+260h+var_2C0+4], eax
0x1800bc8a6  add     r8, 8; int
0x1800bc8aa  mov     rax, [r13+18h]
0x1800bc8ae  mov     [rbp+260h+var_240], rax
0x1800bc8b2  mov     eax, [r13+0]
0x1800bc8b6  mov     dword ptr [rbp+260h+var_2D0], eax
0x1800bc8b9  mov     rax, [r13+80h]
0x1800bc8c0  mov     [rbp+260h+var_238], rax
0x1800bc8c4  mov     eax, [r13+40h]
0x1800bc8c8  mov     dword ptr [rbp+260h+var_2D0+4], eax
0x1800bc8cb  mov     rax, [r13+38h]
0x1800bc8cf  mov     [rbp+260h+var_230], rax
0x1800bc8d3  mov     eax, [r13+8]
0x1800bc8d7  mov     dword ptr [rbp+260h+var_2D8], eax
0x1800bc8da  mov     eax, 1000000h
0x1800bc8df  mov     [rbp+260h+var_2B0], rax
0x1800bc8e3  mov     [rbp+260h+var_2A8], rax
0x1800bc8e7  lea     rax, [rbp+260h+var_228]
0x1800bc8eb  mov     [rsp+3E0h+var_2E8], rax; __int64
0x1800bc8f3  lea     rax, [rbp+260h+var_220]
0x1800bc8f7  mov     [rsp+3E0h+var_2F0], rax; __int64
0x1800bc8ff  lea     rax, [rbp+260h+var_2A0]
0x1800bc903  mov     [rsp+3E0h+var_2F8], rax; __int64
0x1800bc90b  lea     rax, [rbp+260h+var_298]
0x1800bc90f  mov     [rsp+3E0h+var_300], rax; __int64
0x1800bc917  lea     rax, [rbp+260h+var_2E0]
0x1800bc91b  mov     [rsp+3E0h+var_308], rax; __int64
0x1800bc923  lea     rax, [rbp+260h+var_290]
0x1800bc927  mov     [rsp+3E0h+var_310], rax; __int64
0x1800bc92f  lea     rax, [rbp+260h+var_288]
0x1800bc933  mov     [rsp+3E0h+var_318], rax; __int64
0x1800bc93b  lea     rax, [rbp+260h+var_280]
0x1800bc93f  mov     [rsp+3E0h+var_320], rax; __int64
0x1800bc947  lea     rax, [rbp+260h+var_278]
0x1800bc94b  mov     [rsp+3E0h+var_328], rax; __int64
0x1800bc953  lea     rax, [rbp+260h+var_270]
0x1800bc957  mov     [rsp+3E0h+var_330], rax; __int64
0x1800bc95f  lea     rax, [rbp+260h+var_2C8]
0x1800bc963  mov     [rsp+3E0h+var_338], rax; __int64
0x1800bc96b  lea     rax, [rbp+260h+var_2E0+1]
0x1800bc96f  mov     [rsp+3E0h+var_340], rax; __int64
0x1800bc977  lea     rax, [rbp+260h+var_268]
0x1800bc97b  mov     [rsp+3E0h+var_348], rax; __int64
0x1800bc983  lea     rax, [rbp+260h+var_260]
0x1800bc987  mov     [rsp+3E0h+var_350], rax; __int64
0x1800bc98f  lea     rax, [rbp+260h+var_2C8+4]
0x1800bc993  mov     [rsp+3E0h+var_358], rax; __int64
0x1800bc99b  lea     rax, [rbp+260h+var_258]
0x1800bc99f  mov     [rsp+3E0h+var_360], rax; __int64
0x1800bc9a7  lea     rax, [rbp+260h+var_250]
0x1800bc9ab  mov     [rsp+3E0h+var_368], rax; __int64
0x1800bc9b0  lea     rax, [rbp+260h+var_2C0]
0x1800bc9b4  mov     [rsp+3E0h+var_370], rax; __int64
0x1800bc9b9  lea     rax, [rbp+260h+var_248]
0x1800bc9bd  mov     [rsp+3E0h+var_378], rax; __int64
0x1800bc9c2  lea     rax, [rbp+260h+var_2C0+4]
0x1800bc9c6  mov     [rsp+3E0h+var_380], rax; __int64
0x1800bc9cb  lea     rax, [rbp+260h+var_240]
0x1800bc9cf  mov     [rsp+3E0h+var_388], rax; __int64
0x1800bc9d4  movsd   [rbp+260h+var_270], xmm0
0x1800bc9d9  lea     rax, [rbp+260h+var_2D0]
0x1800bc9dd  mov     rcx, r15; int
0x1800bc9e0  mov     [rsp+3E0h+var_390], rax; __int64
0x1800bc9e5  lea     rdx, byte_1801323C5; int
0x1800bc9ec  lea     rax, [rbp+260h+var_238]
0x1800bc9f0  mov     [rsp+3E0h+var_398], rax; __int64
0x1800bc9f5  lea     rax, [rbp+260h+var_2D0+4]
0x1800bc9f9  mov     [rsp+3E0h+var_3A0], rax; __int64
0x1800bc9fe  lea     rax, [rbp+260h+var_230]
0x1800bca02  mov     [rsp+3E0h+var_3A8], rax; __int64
0x1800bca07  lea     rax, [rbp+260h+var_2D8]
0x1800bca0b  mov     [rsp+3E0h+var_3B0], rax; __int64
0x1800bca10  lea     rax, [rbp+260h+var_2B0]
0x1800bca14  mov     [rsp+3E0h+var_3B8], rax; __int64
0x1800bca19  lea     rax, [rbp+260h+var_2A8]
0x1800bca1d  mov     qword ptr [rsp+3E0h+var_3C0], rax; __int64
0x1800bca22  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U?$_tlgWrapperByVal@$00@@U2@U1@U?$_tlgWrapperByRef@$0BA@@@U6@U6@U6@U5@U4@U4@U4@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456AEBU?$_tlgWrapperByVal@$00@@43AEBU?$_tlgWrapperByRef@$0BA@@@88876665@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &)
0x1800bca27  jmp     loc_1800BCDBF
0x1800bca2c  mov     rbx, rax
0x1800bca2f  lea     rdx, [rbp+260h+var_2D8]
0x1800bca33  mov     [rbp+260h+var_2D8], 0
0x1800bca3b  mov     rcx, rdi
0x1800bca3e  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800bca43  mov     rax, [rbx]
0x1800bca46  mov     r15d, 2
0x1800bca4c  mov     rcx, [rbp+260h+var_2D8]; SRWLock
0x1800bca50  mov     [rax], r15d
0x1800bca53  test    rcx, rcx
0x1800bca56  jz      short loc_1800BCA5E
0x1800bca58  call    cs:__imp_ReleaseSRWLockExclusive
0x1800bca5e  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1800bca63  mov     r13, rax
0x1800bca66  cmp     dword ptr [rax], 5
0x1800bca69  jbe     loc_1800BCDBF
0x1800bca6f  mov     rdx, 400000000000h
0x1800bca79  test    [rax+10h], rdx
0x1800bca7d  jz      loc_1800BCDBF
0x1800bca83  mov     rcx, [rax+18h]
0x1800bca87  and     rcx, rdx
0x1800bca8a  cmp     rcx, [rax+18h]
0x1800bca8e  jnz     loc_1800BCDBF
0x1800bca94  mov     ecx, [r14+18h]
0x1800bca98  lea     rdi, aInvalid; "Invalid"
0x1800bca9f  test    ecx, ecx
0x1800bcaa1  jz      short loc_1800BCAD2
0x1800bcaa3  sub     ecx, 1
0x1800bcaa6  jz      short loc_1800BCAC9
0x1800bcaa8  sub     ecx, 1
0x1800bcaab  jz      short loc_1800BCAC0
0x1800bcaad  cmp     ecx, 1
0x1800bcab0  jz      short loc_1800BCAB7
0x1800bcab2  mov     rsi, rdi
0x1800bcab5  jmp     short loc_1800BCAD9
0x1800bcab7  lea     rsi, aValidationRun; "Validation run"
0x1800bcabe  jmp     short loc_1800BCAD9
0x1800bcac0  lea     rsi, aActiveHours; "Active hours"
0x1800bcac7  jmp     short loc_1800BCAD9
0x1800bcac9  lea     rsi, aNextGoodTime; "Next good time"
0x1800bcad0  jmp     short loc_1800BCAD9
0x1800bcad2  lea     rsi, aTimeIntervalCh; "Time interval check"
0x1800bcad9  mov     ecx, [r14+14h]
0x1800bcadd  test    ecx, ecx
0x1800bcadf  jz      short loc_1800BCB0B
0x1800bcae1  sub     ecx, 1
0x1800bcae4  jz      short loc_1800BCB02
0x1800bcae6  sub     ecx, 1
0x1800bcae9  jz      short loc_1800BCAF9
0x1800bcaeb  cmp     ecx, 1
0x1800bcaee  jnz     short loc_1800BCB12
0x1800bcaf0  lea     rdi, aConfidenceNotM; "Confidence Not Met"
0x1800bcaf7  jmp     short loc_1800BCB12
0x1800bcaf9  lea     rdi, aNotEnoughData; "Not Enough Data"
0x1800bcb00  jmp     short loc_1800BCB12
0x1800bcb02  lea     rdi, aAllConditionsM; "All Conditions Met"
0x1800bcb09  jmp     short loc_1800BCB12
0x1800bcb0b  lea     rdi, aNoConditionsMe; "No Conditions Met"
0x1800bcb12  mov     al, [r14+10h]
0x1800bcb16  lea     rdx, [r14+8]
0x1800bcb1a  lea     rcx, [rbp+260h+var_168]; lpSystemTime
0x1800bcb21  mov     byte ptr [rbp+260h+var_2E0+1], al
0x1800bcb24  call    ?to_systemtime@Time@Windows@@YA?AU_SYSTEMTIME@@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; Windows::Time::to_systemtime(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x1800bcb29  lea     rdx, [r14+8]
0x1800bcb2d  lea     rcx, [rbp+260h+var_178]; lpSystemTime
  ... truncated ...
```
