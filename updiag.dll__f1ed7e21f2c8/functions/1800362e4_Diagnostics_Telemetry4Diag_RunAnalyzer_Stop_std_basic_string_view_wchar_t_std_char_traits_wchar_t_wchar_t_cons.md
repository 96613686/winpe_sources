# Diagnostics::Telemetry4Diag::RunAnalyzer::Stop(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,wchar_t const *,bool,__int64)

- ea: `0x1800362e4`
- end: `0x18003672b`
- name: `?Stop@RunAnalyzer@Telemetry4Diag@Diagnostics@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEB_W_N_J@Z`
- size: `1095`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180038fe8`
- `0x18003c5a8`

## callees

- `0x180001350`
- `0x180001b20`
- `0x1800080f8`
- `0x180017ad8`
- `0x180017e80`
- `0x1800362e4`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003637c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003657a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003637c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003657a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800365de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800365de`

## pseudocode

```c
void __fastcall Diagnostics::Telemetry4Diag::RunAnalyzer::Stop(
        __int64 a1,
        __int64 *a2,
        const wchar_t *a3,
        char a4,
        __int64 a5)
{
  _DWORD **v5; // r14
  __int64 v6; // rdi
  int v11; // eax
  int *v12; // rdi
  _DWORD **v13; // rbx
  RTL_SRWLOCK *v14; // rcx
  __int64 v15; // r9
  _DWORD *v16; // r8
  const wchar_t *v17; // r12
  _DWORD *v18; // rax
  int v19; // ebx
  RTL_SRWLOCK *v20; // rcx
  __int64 v21; // rsi
  const wchar_t *v22; // rdi
  const wchar_t *v23; // r15
  DWORD CurrentThreadId; // eax
  _DWORD *v25; // r8
  __int64 v26; // rax
  __int64 v27; // rcx
  int v28; // ecx
  __int64 v29; // [rsp+D8h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+E0h] [rbp-78h] BYREF
  __int64 v31; // [rsp+E8h] [rbp-70h] BYREF
  __int64 v32; // [rsp+F0h] [rbp-68h] BYREF
  int v33; // [rsp+F8h] [rbp-60h] BYREF
  int v34; // [rsp+FCh] [rbp-5Ch] BYREF
  int v35; // [rsp+100h] [rbp-58h] BYREF
  int v36; // [rsp+104h] [rbp-54h] BYREF
  __int64 v37; // [rsp+108h] [rbp-50h] BYREF
  __int64 v38; // [rsp+110h] [rbp-48h] BYREF
  __int64 v39; // [rsp+118h] [rbp-40h] BYREF
  __int64 v40; // [rsp+120h] [rbp-38h] BYREF
  __int64 v41; // [rsp+128h] [rbp-30h] BYREF
  __int64 v42; // [rsp+130h] [rbp-28h] BYREF
  __int64 v43; // [rsp+138h] [rbp-20h] BYREF
  __int64 v44; // [rsp+140h] [rbp-18h] BYREF
  __int64 v45; // [rsp+148h] [rbp-10h] BYREF
  __int64 v46; // [rsp+150h] [rbp-8h] BYREF
  __int64 v47; // [rsp+158h] [rbp+0h] BYREF
  __int64 v48; // [rsp+160h] [rbp+8h] BYREF
  __int64 v49; // [rsp+168h] [rbp+10h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v50; // [rsp+178h] [rbp+20h] BYREF
  __int64 *v51; // [rsp+198h] [rbp+40h]
  __int64 v52; // [rsp+1A0h] [rbp+48h]
  __int64 *v53; // [rsp+1A8h] [rbp+50h]
  __int64 v54; // [rsp+1B0h] [rbp+58h]
  PSRWLOCK *p_SRWLock; // [rsp+1B8h] [rbp+60h]
  __int64 v56; // [rsp+1C0h] [rbp+68h]
  const wchar_t *v57; // [rsp+1C8h] [rbp+70h]
  int v58; // [rsp+1D0h] [rbp+78h]
  int v59; // [rsp+1D4h] [rbp+7Ch]
  const wchar_t *v60; // [rsp+1D8h] [rbp+80h]
  int v61; // [rsp+1E0h] [rbp+88h]
  int v62; // [rsp+1E4h] [rbp+8Ch]
  __int64 *v63; // [rsp+1E8h] [rbp+90h]
  __int64 v64; // [rsp+1F0h] [rbp+98h]
  __int64 *v65; // [rsp+1F8h] [rbp+A0h]
  __int64 v66; // [rsp+200h] [rbp+A8h]
  const char *v67; // [rsp+208h] [rbp+B0h]
  __int64 v68; // [rsp+210h] [rbp+B8h]

  v5 = (_DWORD **)(a1 + 272);
  v32 = (__int64)a2;
  v6 = *(_QWORD *)(a1 + 272);
  v11 = *(_DWORD *)(v6 + 72);
  if ( v11 < 0 && (v12 = (int *)(v6 + 80), v11 == v12[2]) )
  {
    v13 = (_DWORD **)(a1 + 272);
    if ( v12 )
    {
      SRWLock = 0;
      wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        a1,
        &SRWLock);
      v14 = SRWLock;
      **v5 = 2;
      if ( v14 )
        ReleaseSRWLockExclusive(v14);
      v15 = *((_QWORD *)Diagnostics::Telemetry4Diag::Instance() + 1);
      if ( *(_DWORD *)v15 > 5u
        && (*(_QWORD *)(v15 + 16) & 0x400000000000LL) != 0
        && (*(_QWORD *)(v15 + 24) & 0x400000000000LL) == *(_QWORD *)(v15 + 24) )
      {
        v16 = *v5;
        v38 = (__int64)"1507.2603.28012.0";
        v39 = a5;
        v41 = *a2;
        v42 = *((_QWORD *)v12 + 15);
        v43 = *((_QWORD *)v12 + 14);
        v33 = v12[26];
        v44 = *((_QWORD *)v12 + 12);
        v45 = *((_QWORD *)v12 + 11);
        v34 = v12[20];
        v46 = *((_QWORD *)v12 + 9);
        v35 = v12[8];
        v47 = *((_QWORD *)v12 + 3);
        v36 = *v12;
        v48 = *((_QWORD *)v12 + 16);
        LODWORD(v31) = v12[16];
        v49 = *((_QWORD *)v12 + 7);
        LODWORD(SRWLock) = v12[2];
        v37 = 0x1000000;
        v32 = 0x1000000;
        LOBYTE(v29) = a4;
        v17 = &psz;
        if ( a3 )
          v17 = a3;
        v40 = (__int64)v17;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
          v15,
          (int)&byte_1801728FF,
          (_DWORD)v16 + 8,
          v15,
          (__int64)&v32,
          (__int64)&v37,
          (__int64)&SRWLock,
          (const wchar_t **)&v49,
          (__int64)&v31,
          (const wchar_t **)&v48,
          (__int64)&v36,
          (const wchar_t **)&v47,
          (__int64)&v35,
          (const wchar_t **)&v46,
          (__int64)&v34,
          (const wchar_t **)&v45,
          (const wchar_t **)&v44,
          (__int64)&v33,
          (const wchar_t **)&v43,
          (const wchar_t **)&v42,
          (const wchar_t **)&v41,
          (const wchar_t **)&v40,
          (__int64)&v29,
          (__int64)&v39,
          (const wchar_t **)&v38);
      }
      goto LABEL_30;
    }
  }
  else
  {
    v13 = (_DWORD **)(a1 + 272);
  }
  SRWLock = 0;
  wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v18 = *v13;
  v19 = 2;
  v20 = SRWLock;
  *v18 = 2;
  if ( v20 )
    ReleaseSRWLockExclusive(v20);
  v21 = *((_QWORD *)Diagnostics::Telemetry4Diag::Instance() + 1);
  if ( *(_DWORD *)v21 > 5u
    && (*(_QWORD *)(v21 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v21 + 24) & 0x400000000000LL) == *(_QWORD *)(v21 + 24) )
  {
    LOBYTE(v29) = a4;
    v22 = &psz;
    v37 = a5;
    if ( a3 )
      v22 = a3;
    v23 = *(const wchar_t **)v32;
    CurrentThreadId = GetCurrentThreadId();
    v25 = *v5;
    LODWORD(SRWLock) = CurrentThreadId;
    v68 = 18;
    v66 = 8;
    LODWORD(v31) = v25[18];
    v32 = 0x1000000;
    v67 = "1507.2603.28012.0";
    v65 = &v37;
    v63 = &v29;
    v26 = -1;
    v64 = 1;
    if ( v22 )
    {
      v27 = -1;
      do
        ++v27;
      while ( v22[v27] );
      v28 = 2 * v27 + 2;
    }
    else
    {
      v22 = &psz;
      v28 = 2;
    }
    v60 = v22;
    v61 = v28;
    v62 = 0;
    if ( v23 )
    {
      do
        ++v26;
      while ( v23[v26] );
      v19 = 2 * v26 + 2;
    }
    else
    {
      v23 = &psz;
    }
    v59 = 0;
    p_SRWLock = &SRWLock;
    v57 = v23;
    v53 = &v31;
    v58 = v19;
    v51 = &v32;
    v56 = 4;
    v54 = 4;
    v52 = 8;
    tlgWriteTransfer_EventWriteTransfer(v21, (unsigned __int8 *)&byte_180172875, (const GUID *)(v25 + 2), 0, 0xAu, &v50);
  }
LABEL_30:
  wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x1800362e4  mov     rax, rsp
0x1800362e7  mov     [rax+10h], rbx
0x1800362eb  mov     [rax+18h], rsi
0x1800362ef  mov     [rax+20h], rdi
0x1800362f3  push    rbp
0x1800362f4  push    r12
0x1800362f6  push    r13
0x1800362f8  push    r14
0x1800362fa  push    r15
0x1800362fc  lea     rbp, [rax-0F8h]
0x180036303  sub     rsp, 220h
0x18003630a  mov     rax, cs:__security_cookie
0x180036311  xor     rax, rsp
0x180036314  mov     [rbp+0F0h+var_30], rax
0x18003631b  lea     r14, [rcx+110h]
0x180036322  mov     [rbp+0F0h+var_158], rdx
0x180036326  mov     rdi, [r14]
0x180036329  mov     r12b, r9b
0x18003632c  mov     r15, r8
0x18003632f  mov     rsi, rdx
0x180036332  mov     r13, rcx
0x180036335  mov     eax, [rdi+48h]
0x180036338  test    eax, eax
0x18003633a  jns     loc_180036553
0x180036340  add     rdi, 50h ; 'P'
0x180036344  cmp     eax, [rdi+8]
0x180036347  jnz     loc_180036553
0x18003634d  mov     rbx, r14
0x180036350  test    rdi, rdi
0x180036353  jz      loc_180036556
0x180036359  lea     rdx, [rbp+0F0h+SRWLock]
0x18003635d  mov     [rbp+0F0h+SRWLock], 0
0x180036365  call    ?LockExclusive@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003636a  mov     rax, [r14]
0x18003636d  mov     rcx, [rbp+0F0h+SRWLock]; SRWLock
0x180036371  mov     dword ptr [rax], 2
0x180036377  test    rcx, rcx
0x18003637a  jz      short loc_180036382
0x18003637c  call    cs:__imp_ReleaseSRWLockExclusive
0x180036382  call    ?Instance@Telemetry4Diag@Diagnostics@@KAPEAV12@XZ; Diagnostics::Telemetry4Diag::Instance(void)
0x180036387  mov     r9, [rax+8]
0x18003638b  cmp     dword ptr [r9], 5
0x18003638f  jbe     loc_1800366F3
0x180036395  mov     rcx, 400000000000h
0x18003639f  test    [r9+10h], rcx
0x1800363a3  jz      loc_1800366F3
0x1800363a9  mov     rax, [r9+18h]
0x1800363ad  and     rax, rcx
0x1800363b0  cmp     rax, [r9+18h]
0x1800363b4  jnz     loc_1800366F3
0x1800363ba  mov     r8, [r14]
0x1800363bd  lea     rax, a15072603280120; "1507.2603.28012.0"
0x1800363c4  mov     [rbp+0F0h+var_138], rax
0x1800363c8  test    r15, r15
0x1800363cb  mov     rax, [rbp+0F0h+arg_20]
0x1800363d2  mov     [rbp+0F0h+var_130], rax
0x1800363d6  mov     rax, [rsi]
0x1800363d9  mov     [rbp+0F0h+var_120], rax
0x1800363dd  mov     rax, [rdi+78h]
0x1800363e1  mov     [rbp+0F0h+var_118], rax
0x1800363e5  mov     rax, [rdi+70h]
0x1800363e9  mov     [rbp+0F0h+var_110], rax
0x1800363ed  mov     eax, [rdi+68h]
0x1800363f0  mov     dword ptr [rbp+0F0h+var_150], eax
0x1800363f3  mov     rax, [rdi+60h]
0x1800363f7  mov     [rbp+0F0h+var_108], rax
0x1800363fb  mov     rax, [rdi+58h]
0x1800363ff  mov     [rbp+0F0h+var_100], rax
0x180036403  mov     eax, [rdi+50h]
0x180036406  mov     dword ptr [rbp+0F0h+var_150+4], eax
0x180036409  mov     rax, [rdi+48h]
0x18003640d  mov     [rbp+0F0h+var_F8], rax
0x180036411  mov     eax, [rdi+20h]
0x180036414  mov     dword ptr [rbp+0F0h+var_148], eax
0x180036417  mov     rax, [rdi+18h]
0x18003641b  mov     [rbp+0F0h+var_F0], rax
0x18003641f  mov     eax, [rdi]
0x180036421  mov     dword ptr [rbp+0F0h+var_148+4], eax
0x180036424  mov     rax, [rdi+80h]
0x18003642b  mov     [rbp+0F0h+var_E8], rax
0x18003642f  mov     eax, [rdi+40h]
0x180036432  mov     dword ptr [rbp+0F0h+var_160], eax
0x180036435  mov     rax, [rdi+38h]
0x180036439  mov     [rbp+0F0h+var_E0], rax
0x18003643d  mov     eax, [rdi+8]
0x180036440  mov     dword ptr [rbp+0F0h+SRWLock], eax
0x180036443  mov     eax, 1000000h
0x180036448  mov     [rbp+0F0h+var_140], rax
0x18003644c  mov     [rbp+0F0h+var_158], rax
0x180036450  lea     rax, [rbp+0F0h+var_138]
0x180036454  mov     [rsp+240h+var_180], rax; __int64
0x18003645c  lea     rax, [rbp+0F0h+var_130]
0x180036460  mov     [rsp+240h+var_188], rax; __int64
0x180036468  lea     rax, [rbp+0F0h+var_170]
0x18003646c  mov     [rsp+240h+var_190], rax; __int64
0x180036474  lea     rax, [rbp+0F0h+var_128]
0x180036478  mov     [rsp+240h+var_198], rax; __int64
0x180036480  lea     rax, [rbp+0F0h+var_120]
0x180036484  mov     [rsp+240h+var_1A0], rax; __int64
0x18003648c  lea     rax, [rbp+0F0h+var_118]
0x180036490  mov     [rsp+240h+var_1A8], rax; __int64
0x180036498  lea     rax, [rbp+0F0h+var_110]
0x18003649c  mov     [rsp+240h+var_1B0], rax; __int64
0x1800364a4  lea     rax, [rbp+0F0h+var_150]
0x1800364a8  mov     [rsp+240h+var_1B8], rax; __int64
0x1800364b0  lea     rax, [rbp+0F0h+var_108]
0x1800364b4  mov     [rsp+240h+var_1C0], rax; __int64
0x1800364bc  lea     rax, [rbp+0F0h+var_100]
0x1800364c0  mov     [rsp+240h+var_1C8], rax; __int64
0x1800364c5  lea     rax, [rbp+0F0h+var_150+4]
0x1800364c9  mov     [rsp+240h+var_1D0], rax; __int64
0x1800364ce  lea     rax, [rbp+0F0h+var_F8]
0x1800364d2  mov     [rsp+240h+var_1D8], rax; __int64
0x1800364d7  lea     rax, [rbp+0F0h+var_148]
0x1800364db  mov     [rsp+240h+var_1E0], rax; __int64
0x1800364e0  lea     rax, [rbp+0F0h+var_F0]
0x1800364e4  mov     [rsp+240h+var_1E8], rax; __int64
0x1800364e9  lea     rax, [rbp+0F0h+var_148+4]
0x1800364ed  mov     [rsp+240h+var_1F0], rax; __int64
0x1800364f2  lea     rax, [rbp+0F0h+var_E8]
0x1800364f6  mov     [rsp+240h+var_1F8], rax; __int64
0x1800364fb  lea     rax, [rbp+0F0h+var_160]
0x1800364ff  mov     [rsp+240h+var_200], rax; __int64
0x180036504  lea     rax, [rbp+0F0h+var_E0]
0x180036508  mov     byte ptr [rbp+0F0h+var_170], r12b
0x18003650c  lea     r12, psz
0x180036513  cmovnz  r12, r15
0x180036517  mov     [rsp+240h+var_208], rax; __int64
0x18003651c  lea     rax, [rbp+0F0h+SRWLock]
0x180036520  mov     [rbp+0F0h+var_128], r12
0x180036524  add     r8, 8; int
0x180036528  mov     [rsp+240h+var_210], rax; __int64
0x18003652d  lea     rdx, byte_1801728FF; int
0x180036534  lea     rax, [rbp+0F0h+var_140]
0x180036538  mov     rcx, r9; int
0x18003653b  mov     [rsp+240h+var_218], rax; __int64
0x180036540  lea     rax, [rbp+0F0h+var_158]
0x180036544  mov     qword ptr [rsp+240h+var_220], rax; __int64
0x180036549  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U4@U?$_tlgWrapperByVal@$00@@U1@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@4545645666AEBU?$_tlgWrapperByVal@$00@@35@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x18003654e  jmp     loc_1800366F3
0x180036553  mov     rbx, r14
0x180036556  lea     rdx, [rbp+0F0h+SRWLock]
0x18003655a  mov     [rbp+0F0h+SRWLock], 0
0x180036562  call    ?LockExclusive@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180036567  mov     rax, [rbx]
0x18003656a  mov     ebx, 2
0x18003656f  mov     rcx, [rbp+0F0h+SRWLock]; SRWLock
0x180036573  mov     [rax], ebx
0x180036575  test    rcx, rcx
0x180036578  jz      short loc_180036580
0x18003657a  call    cs:__imp_ReleaseSRWLockExclusive
0x180036580  call    ?Instance@Telemetry4Diag@Diagnostics@@KAPEAV12@XZ; Diagnostics::Telemetry4Diag::Instance(void)
0x180036585  mov     rsi, [rax+8]
0x180036589  cmp     dword ptr [rsi], 5
0x18003658c  jbe     loc_1800366F3
0x180036592  mov     rcx, 400000000000h
0x18003659c  test    [rsi+10h], rcx
0x1800365a0  jz      loc_1800366F3
0x1800365a6  mov     rax, [rsi+18h]
0x1800365aa  and     rax, rcx
0x1800365ad  cmp     rax, [rsi+18h]
0x1800365b1  jnz     loc_1800366F3
0x1800365b7  mov     rax, [rbp+0F0h+arg_20]
0x1800365be  test    r15, r15
0x1800365c1  mov     byte ptr [rbp+0F0h+var_170], r12b
0x1800365c5  lea     r12, psz
0x1800365cc  mov     rdi, r12
0x1800365cf  mov     [rbp+0F0h+var_140], rax
0x1800365d3  cmovnz  rdi, r15
0x1800365d7  mov     r15, [rbp+0F0h+var_158]
0x1800365db  mov     r15, [r15]
0x1800365de  call    cs:__imp_GetCurrentThreadId
0x1800365e4  mov     r8, [r14]
0x1800365e7  xor     edx, edx
0x1800365e9  mov     dword ptr [rbp+0F0h+SRWLock], eax
0x1800365ec  mov     [rbp+0F0h+var_38], 12h
0x1800365f7  mov     [rbp+0F0h+var_48], 8
0x180036602  mov     eax, [r8+48h]
0x180036606  mov     dword ptr [rbp+0F0h+var_160], eax
0x180036609  mov     eax, 1000000h
0x18003660e  mov     [rbp+0F0h+var_158], rax
0x180036612  lea     rax, a15072603280120; "1507.2603.28012.0"
0x180036619  mov     [rbp+0F0h+var_40], rax
0x180036620  lea     rax, [rbp+0F0h+var_140]
0x180036624  mov     [rbp+0F0h+var_50], rax
0x18003662b  lea     rax, [rbp+0F0h+var_170]
0x18003662f  mov     [rbp+0F0h+var_60], rax
0x180036636  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003663a  mov     [rbp+0F0h+var_58], 1
0x180036645  test    rdi, rdi
0x180036648  jz      short loc_18003665F
0x18003664a  mov     rcx, rax
0x18003664d  inc     rcx
0x180036650  cmp     [rdi+rcx*2], dx
0x180036654  jnz     short loc_18003664D
0x180036656  lea     ecx, ds:2[rcx*2]
0x18003665d  jmp     short loc_180036664
0x18003665f  mov     rdi, r12
0x180036662  mov     ecx, ebx
0x180036664  mov     [rbp+0F0h+var_70], rdi
0x18003666b  mov     [rbp+0F0h+var_68], ecx
0x180036671  mov     [rbp+0F0h+var_64], edx
0x180036677  test    r15, r15
0x18003667a  jz      short loc_18003668F
0x18003667c  inc     rax
0x18003667f  cmp     [r15+rax*2], dx
0x180036684  jnz     short loc_18003667C
0x180036686  lea     ebx, ds:2[rax*2]
0x18003668d  jmp     short loc_180036692
0x18003668f  mov     r15, r12
0x180036692  lea     rax, [rbp+0F0h+SRWLock]
0x180036696  mov     [rbp+0F0h+var_74], edx
0x180036699  mov     [rbp+0F0h+var_90], rax
0x18003669d  lea     rdx, byte_180172875; int
0x1800366a4  lea     rax, [rbp+0F0h+var_160]
0x1800366a8  mov     [rbp+0F0h+var_80], r15
0x1800366ac  mov     [rbp+0F0h+var_A0], rax
0x1800366b0  add     r8, 8; int
0x1800366b4  lea     rax, [rbp+0F0h+var_158]
0x1800366b8  mov     [rbp+0F0h+var_78], ebx
0x1800366bb  mov     [rbp+0F0h+var_B0], rax
0x1800366bf  xor     r9d, r9d; int
0x1800366c2  lea     rax, [rbp+0F0h+var_D0]
0x1800366c6  mov     [rbp+0F0h+var_88], 4
0x1800366ce  mov     [rsp+240h+var_218], rax; PEVENT_DATA_DESCRIPTOR
0x1800366d3  mov     rcx, rsi; int
0x1800366d6  mov     [rsp+240h+var_220], 0Ah; ULONG
0x1800366de  mov     [rbp+0F0h+var_98], 4
0x1800366e6  mov     [rbp+0F0h+var_A8], 8
0x1800366ee  call    _tlgWriteTransfer_EventWriteTransfer
0x1800366f3  mov     rcx, r13
0x1800366f6  call    ?IgnoreCurrentThread@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x1800366fb  mov     rcx, [rbp+0F0h+var_30]
0x180036702  xor     rcx, rsp; StackCookie
0x180036705  call    __security_check_cookie
0x18003670a  lea     r11, [rsp+240h+var_20]
0x180036712  mov     rbx, [r11+38h]
0x180036716  mov     rsi, [r11+40h]
0x18003671a  mov     rdi, [r11+48h]
0x18003671e  mov     rsp, r11
0x180036721  pop     r15
0x180036723  pop     r14
0x180036725  pop     r13
0x180036727  pop     r12
0x180036729  pop     rbp
0x18003672a  retn
```
