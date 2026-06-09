# Windows::Telemetry::Art::Schedule::Stop(Windows::ARTSmartScheduler::ActiveHoursQueryResult &,bool,wchar_t const *,uchar,std::chrono::duration<int,std::ratio<60,1>>,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x1800bcdf8`
- end: `0x1800bd4f7`
- name: `?Stop@Schedule@Art@Telemetry@Windows@@QEAAXAEAUActiveHoursQueryResult@ARTSmartScheduler@4@_NPEB_WEV?$duration@HU?$ratio@$0DM@$00@std@@@chrono@std@@AEBV?$vector@EV?$allocator@E@std@@@9@@Z`
- size: `1791`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `service_task`

## callers

- `0x1800be518`

## callees

- `0x180001350`
- `0x180002be8`
- `0x180011680`
- `0x18007b230`
- `0x18007cac0`
- `0x18007cbd8`
- `0x18007d1c0`
- `0x18007d30c`
- `0x18007e25c`
- `0x18007fb58`
- `0x180085644`
- `0x18008c27c`
- `0x18008c454`
- `0x1800a94d8`
- `0x1800b781c`
- `0x1800bcdf8`
- `0x1800dd930`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bcf1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bd1f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bcf1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bd1f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800bd2b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800bd2b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Telemetry::Art::Schedule::Stop(
        __int64 a1,
        int *a2,
        char a3,
        const OLECHAR *a4,
        char a5,
        int a6,
        _QWORD *a7)
{
  __int64 v9; // r13
  unsigned __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // r15
  __int64 v15; // r12
  int v16; // eax
  int *v17; // r12
  _DWORD **v18; // rbx
  const struct _tlgProvider_t *v19; // rax
  int v20; // esi
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  const wchar_t *v24; // rbx
  _QWORD *v25; // rax
  int v26; // esi
  const struct _tlgProvider_t *v27; // rax
  __int64 v28; // r13
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  const wchar_t *v32; // rbx
  __int64 v33; // rax
  const OLECHAR *v34; // rdi
  _DWORD *v35; // r8
  __int64 v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  __int64 v39; // rax
  char v40; // [rsp+108h] [rbp-80h] BYREF
  char v41; // [rsp+109h] [rbp-7Fh] BYREF
  _BYTE v42[6]; // [rsp+10Ah] [rbp-7Eh] BYREF
  __int64 v43; // [rsp+110h] [rbp-78h] BYREF
  int v44; // [rsp+118h] [rbp-70h] BYREF
  DWORD CurrentThreadId; // [rsp+11Ch] [rbp-6Ch] BYREF
  int v46; // [rsp+120h] [rbp-68h] BYREF
  int v47; // [rsp+124h] [rbp-64h] BYREF
  int v48; // [rsp+128h] [rbp-60h] BYREF
  int v49; // [rsp+12Ch] [rbp-5Ch] BYREF
  int v50; // [rsp+130h] [rbp-58h] BYREF
  int v51; // [rsp+134h] [rbp-54h] BYREF
  __int64 v52; // [rsp+138h] [rbp-50h] BYREF
  __int64 v53; // [rsp+140h] [rbp-48h] BYREF
  __int64 v54; // [rsp+148h] [rbp-40h] BYREF
  __int64 v55; // [rsp+150h] [rbp-38h] BYREF
  __int64 v56; // [rsp+158h] [rbp-30h] BYREF
  __int64 v57; // [rsp+160h] [rbp-28h] BYREF
  __int64 v58; // [rsp+168h] [rbp-20h] BYREF
  __int64 v59; // [rsp+170h] [rbp-18h] BYREF
  __int64 v60; // [rsp+178h] [rbp-10h] BYREF
  __int64 v61; // [rsp+180h] [rbp-8h] BYREF
  __int64 v62; // [rsp+188h] [rbp+0h] BYREF
  __int64 v63; // [rsp+190h] [rbp+8h] BYREF
  __int64 v64; // [rsp+198h] [rbp+10h] BYREF
  __int64 v65; // [rsp+1A0h] [rbp+18h] BYREF
  __int64 v66; // [rsp+1A8h] [rbp+20h] BYREF
  _BYTE v67[40]; // [rsp+1B0h] [rbp+28h] BYREF
  _QWORD v68[30]; // [rsp+1D8h] [rbp+50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v69; // [rsp+2C8h] [rbp+140h] BYREF
  __int64 *v70; // [rsp+2E8h] [rbp+160h]
  __int64 v71; // [rsp+2F0h] [rbp+168h]
  int *v72; // [rsp+2F8h] [rbp+170h]
  __int64 v73; // [rsp+300h] [rbp+178h]
  DWORD *p_CurrentThreadId; // [rsp+308h] [rbp+180h]
  __int64 v75; // [rsp+310h] [rbp+188h]
  const OLECHAR *v76; // [rsp+318h] [rbp+190h]
  int v77; // [rsp+320h] [rbp+198h]
  int v78; // [rsp+324h] [rbp+19Ch]
  char *v79; // [rsp+328h] [rbp+1A0h]
  __int64 v80; // [rsp+330h] [rbp+1A8h]
  int *v81; // [rsp+338h] [rbp+1B0h]
  __int64 v82; // [rsp+340h] [rbp+1B8h]
  int *v83; // [rsp+348h] [rbp+1C0h]
  __int64 v84; // [rsp+350h] [rbp+1C8h]
  __int64 *v85; // [rsp+358h] [rbp+1D0h]
  __int64 v86; // [rsp+360h] [rbp+1D8h]
  char *v87; // [rsp+368h] [rbp+1E0h]
  __int64 v88; // [rsp+370h] [rbp+1E8h]
  const wchar_t *v89; // [rsp+378h] [rbp+1F0h]
  int v90; // [rsp+380h] [rbp+1F8h]
  int v91; // [rsp+384h] [rbp+1FCh]
  _BYTE *v92; // [rsp+388h] [rbp+200h]
  __int64 v93; // [rsp+390h] [rbp+208h]
  const wchar_t *v94; // [rsp+398h] [rbp+210h]
  __int64 v95; // [rsp+3A0h] [rbp+218h]
  const OLECHAR *v96; // [rsp+3A8h] [rbp+220h]
  int v97; // [rsp+3B0h] [rbp+228h]
  int v98; // [rsp+3B4h] [rbp+22Ch]
  const char *v99; // [rsp+3B8h] [rbp+230h]
  __int64 v100; // [rsp+3C0h] [rbp+238h]

  v40 = a3;
  v9 = a1;
  v52 = a1;
  memset(v68, 0, 0xE8u);
  std::wostringstream::wostringstream(v68);
  v10 = 0;
  if ( a7[1] != *a7 )
  {
    do
    {
      v11 = std::wostream::operator<<(v68, v10);
      v12 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v11, L"=");
      if ( a7[1] - *a7 <= v10 )
        std::vector<std::wstring>::_Xrange();
      v13 = std::wostream::operator<<(v12, *(unsigned __int8 *)(*a7 + v10));
      std::operator<<<wchar_t,std::char_traits<wchar_t>>(v13, ", ");
      ++v10;
    }
    while ( v10 < a7[1] - *a7 );
  }
  v14 = v9 + 272;
  v15 = *(_QWORD *)(v9 + 272);
  v16 = *(_DWORD *)(v15 + 72);
  if ( v16 < 0 && (v17 = (int *)(v15 + 80), v16 == v17[2]) )
  {
    v18 = (_DWORD **)(v9 + 272);
    if ( v17 )
    {
      v43 = 0;
      wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        v9,
        &v43);
      **(_DWORD **)v14 = 2;
      if ( v43 )
        ReleaseSRWLockExclusive((PSRWLOCK)v43);
      v19 = Windows::Telemetry::Base::Provider();
      v20 = (int)v19;
      if ( *(_DWORD *)v19 > 5u
        && (*((_QWORD *)v19 + 2) & 0x400000000000LL) != 0
        && (*((_QWORD *)v19 + 3) & 0x400000000000LL) == *((_QWORD *)v19 + 3) )
      {
        v54 = (__int64)"1507.2603.28012.0";
        v55 = (__int64)a4;
        v56 = (__int64)L"Active hours";
        v21 = a2[3];
        if ( v21 )
        {
          v22 = v21 - 1;
          if ( v22 )
          {
            v23 = v22 - 1;
            if ( v23 )
            {
              if ( v23 == 1 )
                v24 = L"Confidence Not Met";
              else
                v24 = L"Invalid";
            }
            else
            {
              v24 = L"Not Enough Data";
            }
          }
          else
          {
            v24 = L"All Conditions Met";
          }
        }
        else
        {
          v24 = L"No Conditions Met";
        }
        v57 = (__int64)v24;
        v41 = *((_BYTE *)a2 + 8);
        v48 = a2[1];
        v49 = *a2;
        v50 = a6;
        v42[0] = a5;
        v25 = (_QWORD *)std::wostringstream::str(v68, v67);
        if ( v25[3] > 7u )
          v25 = (_QWORD *)*v25;
        v58 = (__int64)v25;
        v59 = *((_QWORD *)v17 + 15);
        v60 = *((_QWORD *)v17 + 14);
        v51 = v17[26];
        v61 = *((_QWORD *)v17 + 12);
        v62 = *((_QWORD *)v17 + 11);
        v44 = v17[20];
        v63 = *((_QWORD *)v17 + 9);
        CurrentThreadId = v17[8];
        v64 = *((_QWORD *)v17 + 3);
        v46 = *v17;
        v65 = *((_QWORD *)v17 + 16);
        v47 = v17[16];
        v66 = *((_QWORD *)v17 + 7);
        LODWORD(v43) = v17[2];
        v52 = 0x1000000;
        v53 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
          v20,
          (int)&word_18013209A,
          *(_DWORD *)v14 + 8,
          (__int64)&v53,
          (__int64)&v52,
          (__int64)&v43,
          (__int64)&v66,
          (__int64)&v47,
          (__int64)&v65,
          (__int64)&v46,
          (__int64)&v64,
          (__int64)&CurrentThreadId,
          (__int64)&v63,
          (__int64)&v44,
          (__int64)&v62,
          (__int64)&v61,
          (__int64)&v51,
          (__int64)&v60,
          (__int64)&v59,
          (__int64)&v58,
          (__int64)v42,
          (__int64)&v50,
          (__int64)&v49,
          (__int64)&v48,
          (__int64)&v41,
          (__int64)&v57,
          (__int64)&v40,
          (__int64)&v56,
          (__int64)&v55,
          (__int64)&v54);
        std::wstring::~wstring(v67);
      }
      goto LABEL_54;
    }
  }
  else
  {
    v18 = (_DWORD **)(v9 + 272);
  }
  v43 = 0;
  wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    v9,
    &v43);
  v26 = 2;
  **v18 = 2;
  if ( v43 )
    ReleaseSRWLockExclusive((PSRWLOCK)v43);
  v27 = Windows::Telemetry::Base::Provider();
  v28 = (__int64)v27;
  if ( *(_DWORD *)v27 > 5u
    && (*((_QWORD *)v27 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v27 + 3) & 0x400000000000LL) == *((_QWORD *)v27 + 3) )
  {
    v42[0] = v40;
    v29 = a2[3];
    if ( v29 )
    {
      v30 = v29 - 1;
      if ( v30 )
      {
        v31 = v30 - 1;
        if ( v31 )
        {
          if ( v31 == 1 )
            v32 = L"Confidence Not Met";
          else
            v32 = L"Invalid";
        }
        else
        {
          v32 = L"Not Enough Data";
        }
      }
      else
      {
        v32 = L"All Conditions Met";
      }
    }
    else
    {
      v32 = L"No Conditions Met";
    }
    v41 = *((_BYTE *)a2 + 8);
    LODWORD(v43) = a2[1];
    v47 = *a2;
    v46 = a6;
    v40 = a5;
    v33 = std::wostringstream::str(v68, v67);
    v34 = (const OLECHAR *)v33;
    if ( *(_QWORD *)(v33 + 24) > 7u )
      v34 = *(const OLECHAR **)v33;
    CurrentThreadId = GetCurrentThreadId();
    v35 = *(_DWORD **)v14;
    v44 = *(_DWORD *)(*(_QWORD *)v14 + 72LL);
    v53 = 0x1000000;
    v99 = "1507.2603.28012.0";
    v100 = 18;
    v36 = -1;
    if ( a4 )
    {
      v37 = -1;
      do
        ++v37;
      while ( a4[v37] );
      v38 = 2 * v37 + 2;
    }
    else
    {
      a4 = &S1;
      v38 = 2;
    }
    v96 = a4;
    v97 = v38;
    v98 = 0;
    v94 = L"Active hours";
    v95 = 26;
    v92 = v42;
    v93 = 1;
    v39 = -1;
    do
      ++v39;
    while ( v32[v39] );
    v89 = v32;
    v90 = 2 * v39 + 2;
    v91 = 0;
    v87 = &v41;
    v88 = 1;
    v85 = &v43;
    v86 = 4;
    v83 = &v47;
    v84 = 4;
    v81 = &v46;
    v82 = 4;
    v79 = &v40;
    v80 = 1;
    if ( v34 )
    {
      do
        ++v36;
      while ( v34[v36] );
      v26 = 2 * v36 + 2;
    }
    else
    {
      v34 = &S1;
    }
    v76 = v34;
    v77 = v26;
    v78 = 0;
    p_CurrentThreadId = &CurrentThreadId;
    v75 = 4;
    v72 = &v44;
    v73 = 4;
    v70 = &v53;
    v71 = 8;
    tlgWriteTransfer_EventWriteTransfer(
      v28,
      (unsigned __int8 *)&byte_180131FB3,
      (const GUID *)(v35 + 2),
      0,
      0x10u,
      &v69);
    std::wstring::~wstring(v67);
  }
  v9 = v52;
LABEL_54:
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(v9);
  std::wostringstream::~wostringstream(&v68[17]);
  v68[17] = &std::wios::`vftable';
  std::ios_base::~ios_base((std::ios_base *)&v68[17]);
}

```

## disassembly

```asm
0x1800bcdf8  mov     rax, rsp
0x1800bcdfb  mov     [rax+10h], rbx
0x1800bcdff  mov     [rax+18h], rsi
0x1800bce03  mov     [rax+20h], rdi
0x1800bce07  push    rbp
0x1800bce08  push    r12
0x1800bce0a  push    r13
0x1800bce0c  push    r14
0x1800bce0e  push    r15
0x1800bce10  lea     rbp, [rax-278h]
0x1800bce17  sub     rsp, 3D0h
0x1800bce1e  mov     rax, cs:__security_cookie
0x1800bce25  xor     rax, rsp
0x1800bce28  mov     [rbp+270h+var_30], rax
0x1800bce2f  mov     r14, r9
0x1800bce32  mov     byte ptr [rbp+270h+var_2F0], r8b
0x1800bce36  mov     rdi, rdx
0x1800bce39  mov     r13, rcx
0x1800bce3c  mov     [rbp+270h+var_2C0], rcx
0x1800bce40  mov     rsi, [rbp+270h+arg_30]
0x1800bce47  xor     edx, edx; Val
0x1800bce49  mov     r8d, 0E8h; Size
0x1800bce4f  lea     rcx, [rbp+270h+var_220]; void *
0x1800bce53  call    memset
0x1800bce58  lea     rcx, [rbp+270h+var_220]
0x1800bce5c  call    ??0?$basic_ostringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wostringstream::wostringstream(void)
0x1800bce61  nop
0x1800bce62  xor     ebx, ebx
0x1800bce64  mov     rax, [rsi+8]
0x1800bce68  cmp     rax, [rsi]
0x1800bce6b  jz      short loc_1800BCEC5
0x1800bce6d  mov     rdx, rbx
0x1800bce70  lea     rcx, [rbp+270h+var_220]
0x1800bce74  call    ??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z; std::wostream::operator<<(unsigned __int64)
0x1800bce79  mov     rcx, rax
0x1800bce7c  lea     rdx, asc_18012482C; "="
0x1800bce83  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1800bce88  mov     rdx, [rsi]
0x1800bce8b  mov     rcx, [rsi+8]
0x1800bce8f  sub     rcx, rdx
0x1800bce92  cmp     rcx, rbx
0x1800bce95  jbe     loc_1800BD4F1
0x1800bce9b  movzx   edx, byte ptr [rdx+rbx]
0x1800bce9f  mov     rcx, rax
0x1800bcea2  call    ??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@H@Z; std::wostream::operator<<(int)
0x1800bcea7  mov     rcx, rax
0x1800bceaa  lea     rdx, asc_1801284B4; ", "
0x1800bceb1  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEBD@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,char const *)
0x1800bceb6  inc     rbx
0x1800bceb9  mov     rax, [rsi+8]
0x1800bcebd  sub     rax, [rsi]
0x1800bcec0  cmp     rbx, rax
0x1800bcec3  jb      short loc_1800BCE6D
0x1800bcec5  lea     r15, [r13+110h]
0x1800bcecc  mov     r12, [r15]
0x1800bcecf  mov     eax, [r12+48h]
0x1800bced4  test    eax, eax
0x1800bced6  jns     loc_1800BD1C7
0x1800bcedc  add     r12, 50h ; 'P'
0x1800bcee0  cmp     eax, [r12+8]
0x1800bcee5  jnz     loc_1800BD1C7
0x1800bceeb  mov     rbx, r15
0x1800bceee  test    r12, r12
0x1800bcef1  jz      loc_1800BD1CA
0x1800bcef7  mov     [rbp+270h+var_2E8], 0
0x1800bceff  lea     rdx, [rbp+270h+var_2E8]
0x1800bcf03  mov     rcx, r13
0x1800bcf06  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800bcf0b  mov     rax, [r15]
0x1800bcf0e  mov     dword ptr [rax], 2
0x1800bcf14  mov     rcx, [rbp+270h+var_2E8]; SRWLock
0x1800bcf18  test    rcx, rcx
0x1800bcf1b  jz      short loc_1800BCF23
0x1800bcf1d  call    cs:__imp_ReleaseSRWLockExclusive
0x1800bcf23  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1800bcf28  mov     rsi, rax
0x1800bcf2b  cmp     dword ptr [rax], 5
0x1800bcf2e  jbe     loc_1800BD492
0x1800bcf34  mov     rdx, 400000000000h
0x1800bcf3e  test    [rax+10h], rdx
0x1800bcf42  jz      loc_1800BD492
0x1800bcf48  mov     rcx, [rax+18h]
0x1800bcf4c  and     rcx, rdx
0x1800bcf4f  cmp     rcx, [rax+18h]
0x1800bcf53  jnz     loc_1800BD492
0x1800bcf59  lea     rax, a15072603280120; "1507.2603.28012.0"
0x1800bcf60  mov     [rbp+270h+var_2B0], rax
0x1800bcf64  mov     [rbp+270h+var_2A8], r14
0x1800bcf68  lea     rax, aActiveHours; "Active hours"
0x1800bcf6f  mov     [rbp+270h+var_2A0], rax
0x1800bcf73  mov     al, byte ptr [rbp+270h+var_2F0]
0x1800bcf76  mov     byte ptr [rbp+270h+var_2F0], al
0x1800bcf79  mov     ecx, [rdi+0Ch]
0x1800bcf7c  test    ecx, ecx
0x1800bcf7e  jz      short loc_1800BCFB3
0x1800bcf80  sub     ecx, 1
0x1800bcf83  jz      short loc_1800BCFAA
0x1800bcf85  sub     ecx, 1
0x1800bcf88  jz      short loc_1800BCFA1
0x1800bcf8a  cmp     ecx, 1
0x1800bcf8d  jz      short loc_1800BCF98
0x1800bcf8f  lea     rbx, aInvalid; "Invalid"
0x1800bcf96  jmp     short loc_1800BCFBA
0x1800bcf98  lea     rbx, aConfidenceNotM; "Confidence Not Met"
0x1800bcf9f  jmp     short loc_1800BCFBA
0x1800bcfa1  lea     rbx, aNotEnoughData; "Not Enough Data"
0x1800bcfa8  jmp     short loc_1800BCFBA
0x1800bcfaa  lea     rbx, aAllConditionsM; "All Conditions Met"
0x1800bcfb1  jmp     short loc_1800BCFBA
0x1800bcfb3  lea     rbx, aNoConditionsMe; "No Conditions Met"
0x1800bcfba  mov     [rbp+270h+var_298], rbx
0x1800bcfbe  mov     al, [rdi+8]
0x1800bcfc1  mov     byte ptr [rbp+270h+var_2F0+1], al
0x1800bcfc4  mov     eax, [rdi+4]
0x1800bcfc7  mov     dword ptr [rbp+270h+var_2D0], eax
0x1800bcfca  mov     eax, [rdi]
0x1800bcfcc  mov     dword ptr [rbp+270h+var_2D0+4], eax
0x1800bcfcf  mov     eax, [rbp+270h+arg_28]
0x1800bcfd5  mov     [rbp+270h+var_2C8], eax
0x1800bcfd8  mov     al, [rbp+270h+arg_20]
0x1800bcfde  mov     byte ptr [rbp+270h+var_2F0+2], al
0x1800bcfe1  lea     rdx, [rbp+270h+var_248]
0x1800bcfe5  lea     rcx, [rbp+270h+var_220]
0x1800bcfe9  call    ?str@?$basic_ostringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEGBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::wostringstream::str(void)
0x1800bcfee  cmp     qword ptr [rax+18h], 7
0x1800bcff3  jbe     short loc_1800BCFF8
0x1800bcff5  mov     rax, [rax]
0x1800bcff8  mov     [rbp+270h+var_290], rax
0x1800bcffc  mov     rax, [r12+78h]
0x1800bd001  mov     [rbp+270h+var_288], rax
0x1800bd005  mov     rax, [r12+70h]
0x1800bd00a  mov     [rbp+270h+var_280], rax
0x1800bd00e  mov     eax, [r12+68h]
0x1800bd013  mov     [rbp+270h+var_2C4], eax
0x1800bd016  mov     rax, [r12+60h]
0x1800bd01b  mov     [rbp+270h+var_278], rax
0x1800bd01f  mov     rax, [r12+58h]
0x1800bd024  mov     [rbp+270h+var_270], rax
0x1800bd028  mov     eax, [r12+50h]
0x1800bd02d  mov     dword ptr [rbp+270h+var_2E0], eax
0x1800bd030  mov     rax, [r12+48h]
0x1800bd035  mov     [rbp+270h+var_268], rax
0x1800bd039  mov     eax, [r12+20h]
0x1800bd03e  mov     dword ptr [rbp+270h+var_2E0+4], eax
0x1800bd041  mov     rax, [r12+18h]
0x1800bd046  mov     [rbp+270h+var_260], rax
0x1800bd04a  mov     eax, [r12]
0x1800bd04e  mov     dword ptr [rbp+270h+var_2D8], eax
0x1800bd051  mov     rax, [r12+80h]
0x1800bd059  mov     [rbp+270h+var_258], rax
0x1800bd05d  mov     eax, [r12+40h]
0x1800bd062  mov     dword ptr [rbp+270h+var_2D8+4], eax
0x1800bd065  mov     rax, [r12+38h]
0x1800bd06a  mov     [rbp+270h+var_250], rax
0x1800bd06e  mov     eax, [r12+8]
0x1800bd073  mov     dword ptr [rbp+270h+var_2E8], eax
0x1800bd076  mov     eax, 1000000h
0x1800bd07b  mov     [rbp+270h+var_2C0], rax
0x1800bd07f  mov     [rbp+270h+var_2B8], rax
0x1800bd083  mov     r8, [r15]
0x1800bd086  add     r8, 8; int
0x1800bd08a  lea     rax, [rbp+270h+var_2B0]
0x1800bd08e  mov     [rsp+3F0h+var_300], rax; __int64
0x1800bd096  lea     rax, [rbp+270h+var_2A8]
0x1800bd09a  mov     [rsp+3F0h+var_308], rax; __int64
0x1800bd0a2  lea     rax, [rbp+270h+var_2A0]
0x1800bd0a6  mov     [rsp+3F0h+var_310], rax; __int64
0x1800bd0ae  lea     rax, [rbp+270h+var_2F0]
0x1800bd0b2  mov     [rsp+3F0h+var_318], rax; __int64
0x1800bd0ba  lea     rax, [rbp+270h+var_298]
0x1800bd0be  mov     [rsp+3F0h+var_320], rax; __int64
0x1800bd0c6  lea     rax, [rbp+270h+var_2F0+1]
0x1800bd0ca  mov     [rsp+3F0h+var_328], rax; __int64
0x1800bd0d2  lea     rax, [rbp+270h+var_2D0]
0x1800bd0d6  mov     [rsp+3F0h+var_330], rax; __int64
0x1800bd0de  lea     rax, [rbp+270h+var_2D0+4]
0x1800bd0e2  mov     [rsp+3F0h+var_338], rax; __int64
0x1800bd0ea  lea     rax, [rbp+270h+var_2C8]
0x1800bd0ee  mov     [rsp+3F0h+var_340], rax; __int64
0x1800bd0f6  lea     rax, [rbp+270h+var_2F0+2]
0x1800bd0fa  mov     [rsp+3F0h+var_348], rax; __int64
0x1800bd102  lea     rax, [rbp+270h+var_290]
0x1800bd106  mov     [rsp+3F0h+var_350], rax; __int64
0x1800bd10e  lea     rax, [rbp+270h+var_288]
0x1800bd112  mov     [rsp+3F0h+var_358], rax; __int64
0x1800bd11a  lea     rax, [rbp+270h+var_280]
0x1800bd11e  mov     [rsp+3F0h+var_360], rax; __int64
0x1800bd126  lea     rax, [rbp+270h+var_2C4]
0x1800bd12a  mov     [rsp+3F0h+var_368], rax; __int64
0x1800bd132  lea     rax, [rbp+270h+var_278]
0x1800bd136  mov     [rsp+3F0h+var_370], rax; __int64
0x1800bd13e  lea     rax, [rbp+270h+var_270]
0x1800bd142  mov     [rsp+3F0h+var_378], rax; __int64
0x1800bd147  lea     rax, [rbp+270h+var_2E0]
0x1800bd14b  mov     [rsp+3F0h+var_380], rax; __int64
0x1800bd150  lea     rax, [rbp+270h+var_268]
0x1800bd154  mov     [rsp+3F0h+var_388], rax; __int64
0x1800bd159  lea     rax, [rbp+270h+var_2E0+4]
0x1800bd15d  mov     [rsp+3F0h+var_390], rax; __int64
0x1800bd162  lea     rax, [rbp+270h+var_260]
0x1800bd166  mov     [rsp+3F0h+var_398], rax; __int64
0x1800bd16b  lea     rax, [rbp+270h+var_2D8]
0x1800bd16f  mov     [rsp+3F0h+var_3A0], rax; __int64
0x1800bd174  lea     rax, [rbp+270h+var_258]
0x1800bd178  mov     [rsp+3F0h+var_3A8], rax; __int64
0x1800bd17d  lea     rax, [rbp+270h+var_2D8+4]
0x1800bd181  mov     [rsp+3F0h+var_3B0], rax; __int64
0x1800bd186  lea     rax, [rbp+270h+var_250]
0x1800bd18a  mov     [rsp+3F0h+var_3B8], rax; __int64
0x1800bd18f  lea     rax, [rbp+270h+var_2E8]
0x1800bd193  mov     [rsp+3F0h+var_3C0], rax; __int64
0x1800bd198  lea     rax, [rbp+270h+var_2C0]
0x1800bd19c  mov     [rsp+3F0h+var_3C8], rax; __int64
0x1800bd1a1  lea     rax, [rbp+270h+var_2B8]
0x1800bd1a5  mov     qword ptr [rsp+3F0h+var_3D0], rax; __int64
0x1800bd1aa  lea     rdx, word_18013209A; int
0x1800bd1b1  mov     rcx, rsi; int
0x1800bd1b4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U?$_tlgWrapperByVal@$00@@U2@U2@U2@U5@U4@U5@U4@U4@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@454564566AEBU?$_tlgWrapperByVal@$00@@444767665@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &)
0x1800bd1b9  lea     rcx, [rbp+270h+var_248]; void *
0x1800bd1bd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800bd1c2  jmp     loc_1800BD492
0x1800bd1c7  mov     rbx, r15
0x1800bd1ca  xor     r12d, r12d
0x1800bd1cd  mov     [rbp+270h+var_2E8], r12
0x1800bd1d1  lea     rdx, [rbp+270h+var_2E8]
0x1800bd1d5  mov     rcx, r13
0x1800bd1d8  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800bd1dd  mov     rax, [rbx]
0x1800bd1e0  lea     esi, [r12+2]
0x1800bd1e5  mov     [rax], esi
0x1800bd1e7  mov     rcx, [rbp+270h+var_2E8]; SRWLock
0x1800bd1eb  test    rcx, rcx
0x1800bd1ee  jz      short loc_1800BD1F6
0x1800bd1f0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800bd1f6  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1800bd1fb  mov     r13, rax
0x1800bd1fe  cmp     dword ptr [rax], 5
0x1800bd201  jbe     loc_1800BD48E
0x1800bd207  mov     rdx, 400000000000h
0x1800bd211  test    [rax+10h], rdx
0x1800bd215  jz      loc_1800BD48E
0x1800bd21b  mov     rcx, [rax+18h]
0x1800bd21f  and     rcx, rdx
0x1800bd222  cmp     rcx, [rax+18h]
0x1800bd226  jnz     loc_1800BD48E
0x1800bd22c  mov     al, byte ptr [rbp+270h+var_2F0]
0x1800bd22f  mov     byte ptr [rbp+270h+var_2F0+2], al
0x1800bd232  mov     ecx, [rdi+0Ch]
0x1800bd235  test    ecx, ecx
0x1800bd237  jz      short loc_1800BD26C
0x1800bd239  sub     ecx, 1
0x1800bd23c  jz      short loc_1800BD263
0x1800bd23e  sub     ecx, 1
0x1800bd241  jz      short loc_1800BD25A
0x1800bd243  cmp     ecx, 1
0x1800bd246  jz      short loc_1800BD251
0x1800bd248  lea     rbx, aInvalid; "Invalid"
0x1800bd24f  jmp     short loc_1800BD273
0x1800bd251  lea     rbx, aConfidenceNotM; "Confidence Not Met"
0x1800bd258  jmp     short loc_1800BD273
0x1800bd25a  lea     rbx, aNotEnoughData; "Not Enough Data"
0x1800bd261  jmp     short loc_1800BD273
0x1800bd263  lea     rbx, aAllConditionsM; "All Conditions Met"
0x1800bd26a  jmp     short loc_1800BD273
0x1800bd26c  lea     rbx, aNoConditionsMe; "No Conditions Met"
0x1800bd273  mov     al, [rdi+8]
0x1800bd276  mov     byte ptr [rbp+270h+var_2F0+1], al
0x1800bd279  mov     eax, [rdi+4]
0x1800bd27c  mov     dword ptr [rbp+270h+var_2E8], eax
0x1800bd27f  mov     eax, [rdi]
0x1800bd281  mov     dword ptr [rbp+270h+var_2D8+4], eax
0x1800bd284  mov     eax, [rbp+270h+arg_28]
0x1800bd28a  mov     dword ptr [rbp+270h+var_2D8], eax
0x1800bd28d  mov     al, [rbp+270h+arg_20]
0x1800bd293  mov     byte ptr [rbp+270h+var_2F0], al
0x1800bd296  lea     rdx, [rbp+270h+var_248]
0x1800bd29a  lea     rcx, [rbp+270h+var_220]
0x1800bd29e  call    ?str@?$basic_ostringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEGBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::wostringstream::str(void)
0x1800bd2a3  mov     rdi, rax
0x1800bd2a6  cmp     qword ptr [rax+18h], 7
0x1800bd2ab  jbe     short loc_1800BD2B0
0x1800bd2ad  mov     rdi, [rax]
0x1800bd2b0  call    cs:__imp_GetCurrentThreadId
0x1800bd2b6  mov     dword ptr [rbp+270h+var_2E0+4], eax
0x1800bd2b9  mov     r8, [r15]
0x1800bd2bc  mov     ecx, [r8+48h]
0x1800bd2c0  mov     dword ptr [rbp+270h+var_2E0], ecx
0x1800bd2c3  mov     eax, 1000000h
0x1800bd2c8  mov     [rbp+270h+var_2B8], rax
0x1800bd2cc  lea     rax, a15072603280120; "1507.2603.28012.0"
0x1800bd2d3  mov     [rbp+270h+var_40], rax
0x1800bd2da  mov     [rbp+270h+var_38], 12h
0x1800bd2e5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800bd2e9  test    r14, r14
0x1800bd2ec  jz      short loc_1800BD304
0x1800bd2ee  mov     rax, rcx
0x1800bd2f1  inc     rax
0x1800bd2f4  cmp     [r14+rax*2], r12w
0x1800bd2f9  jnz     short loc_1800BD2F1
0x1800bd2fb  lea     eax, ds:2[rax*2]
  ... truncated ...
```
