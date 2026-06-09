# Diagnostics::Telemetry4Diag::RunTranslator::Stop(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,uint,__int64,wchar_t const *)

- ea: `0x1800373a8`
- end: `0x1800377d4`
- name: `?Stop@RunTranslator@Telemetry4Diag@Diagnostics@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@I_JPEB_W@Z`
- size: `1068`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800377dc`
- `0x18004155c`

## callees

- `0x180001350`
- `0x180002204`
- `0x1800080f8`
- `0x180017ad8`
- `0x180017e80`
- `0x1800373a8`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037440`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037630`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037440`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037630`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003767d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003767d`

## pseudocode

```c
void __fastcall Diagnostics::Telemetry4Diag::RunTranslator::Stop(
        __int64 a1,
        __int64 *a2,
        int a3,
        __int64 a4,
        const wchar_t *a5)
{
  _DWORD **v5; // rdi
  __int64 v6; // rsi
  int v11; // eax
  int *v12; // rsi
  _DWORD **v13; // rbx
  RTL_SRWLOCK *v14; // rcx
  __int64 v15; // r9
  _DWORD *v16; // r8
  _DWORD *v17; // rax
  int v18; // ebx
  RTL_SRWLOCK *v19; // rcx
  __int64 v20; // r14
  const wchar_t *v21; // rsi
  DWORD CurrentThreadId; // eax
  _DWORD *v23; // r8
  const wchar_t *v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rcx
  int v27; // ecx
  PSRWLOCK SRWLock; // [rsp+D8h] [rbp-80h] BYREF
  int v29; // [rsp+E0h] [rbp-78h] BYREF
  DWORD v30; // [rsp+E4h] [rbp-74h] BYREF
  __int64 v31; // [rsp+E8h] [rbp-70h] BYREF
  int v32; // [rsp+F0h] [rbp-68h] BYREF
  int v33; // [rsp+F4h] [rbp-64h] BYREF
  int v34; // [rsp+F8h] [rbp-60h] BYREF
  int v35; // [rsp+FCh] [rbp-5Ch] BYREF
  __int64 v36; // [rsp+100h] [rbp-58h] BYREF
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
  struct _EVENT_DATA_DESCRIPTOR v49; // [rsp+168h] [rbp+10h] BYREF
  __int64 *v50; // [rsp+188h] [rbp+30h]
  __int64 v51; // [rsp+190h] [rbp+38h]
  int *v52; // [rsp+198h] [rbp+40h]
  __int64 v53; // [rsp+1A0h] [rbp+48h]
  DWORD *v54; // [rsp+1A8h] [rbp+50h]
  __int64 v55; // [rsp+1B0h] [rbp+58h]
  const wchar_t *v56; // [rsp+1B8h] [rbp+60h]
  int v57; // [rsp+1C0h] [rbp+68h]
  int v58; // [rsp+1C4h] [rbp+6Ch]
  PSRWLOCK *p_SRWLock; // [rsp+1C8h] [rbp+70h]
  __int64 v60; // [rsp+1D0h] [rbp+78h]
  __int64 *v61; // [rsp+1D8h] [rbp+80h]
  __int64 v62; // [rsp+1E0h] [rbp+88h]
  const wchar_t *v63; // [rsp+1E8h] [rbp+90h]
  int v64; // [rsp+1F0h] [rbp+98h]
  int v65; // [rsp+1F4h] [rbp+9Ch]
  const char *v66; // [rsp+1F8h] [rbp+A0h]
  __int64 v67; // [rsp+200h] [rbp+A8h]

  v5 = (_DWORD **)(a1 + 272);
  v31 = (__int64)a2;
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
        v37 = (__int64)"1507.2603.28012.0";
        v38 = (__int64)a5;
        v40 = *a2;
        v41 = *((_QWORD *)v12 + 15);
        v42 = *((_QWORD *)v12 + 14);
        v33 = v12[26];
        v43 = *((_QWORD *)v12 + 12);
        v44 = *((_QWORD *)v12 + 11);
        v34 = v12[20];
        v45 = *((_QWORD *)v12 + 9);
        v35 = v12[8];
        v46 = *((_QWORD *)v12 + 3);
        v29 = *v12;
        v47 = *((_QWORD *)v12 + 16);
        v30 = v12[16];
        v48 = *((_QWORD *)v12 + 7);
        LODWORD(SRWLock) = v12[2];
        v36 = 0x1000000;
        v31 = 0x1000000;
        v39 = a4;
        v32 = a3;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
          v15,
          (int)&byte_180172177,
          (_DWORD)v16 + 8,
          v15,
          (__int64)&v31,
          (__int64)&v36,
          (__int64)&SRWLock,
          (const wchar_t **)&v48,
          (__int64)&v30,
          (const wchar_t **)&v47,
          (__int64)&v29,
          (const wchar_t **)&v46,
          (__int64)&v35,
          (const wchar_t **)&v45,
          (__int64)&v34,
          (const wchar_t **)&v44,
          (const wchar_t **)&v43,
          (__int64)&v33,
          (const wchar_t **)&v42,
          (const wchar_t **)&v41,
          (const wchar_t **)&v40,
          (__int64)&v32,
          (__int64)&v39,
          (const wchar_t **)&v38,
          (const wchar_t **)&v37);
      }
      goto LABEL_26;
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
  v17 = *v13;
  v18 = 2;
  v19 = SRWLock;
  *v17 = 2;
  if ( v19 )
    ReleaseSRWLockExclusive(v19);
  v20 = *((_QWORD *)Diagnostics::Telemetry4Diag::Instance() + 1);
  if ( *(_DWORD *)v20 > 5u
    && (*(_QWORD *)(v20 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v20 + 24) & 0x400000000000LL) == *(_QWORD *)(v20 + 24) )
  {
    v36 = a4;
    LODWORD(SRWLock) = a3;
    v21 = *(const wchar_t **)v31;
    CurrentThreadId = GetCurrentThreadId();
    v23 = *v5;
    v24 = a5;
    v30 = CurrentThreadId;
    v67 = 18;
    v29 = v23[18];
    v31 = 0x1000000;
    v66 = "1507.2603.28012.0";
    v25 = -1;
    if ( a5 )
    {
      v26 = -1;
      do
        ++v26;
      while ( a5[v26] );
      v27 = 2 * v26 + 2;
    }
    else
    {
      v24 = &psz;
      v27 = 2;
    }
    v64 = v27;
    v61 = &v36;
    p_SRWLock = &SRWLock;
    v63 = v24;
    v65 = 0;
    v62 = 8;
    v60 = 4;
    if ( v21 )
    {
      do
        ++v25;
      while ( v21[v25] );
      v18 = 2 * v25 + 2;
    }
    else
    {
      v21 = &psz;
    }
    v56 = v21;
    v54 = &v30;
    v57 = v18;
    v52 = &v29;
    v58 = 0;
    v50 = &v31;
    v55 = 4;
    v53 = 4;
    v51 = 8;
    tlgWriteTransfer_EventWriteTransfer(v20, (unsigned __int8 *)&byte_1801720E5, (const GUID *)(v23 + 2), 0, 0xAu, &v49);
  }
LABEL_26:
  wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x1800373a8  mov     rax, rsp
0x1800373ab  mov     [rax+10h], rbx
0x1800373af  mov     [rax+18h], rsi
0x1800373b3  mov     [rax+20h], rdi
0x1800373b7  push    rbp
0x1800373b8  push    r12
0x1800373ba  push    r13
0x1800373bc  push    r14
0x1800373be  push    r15
0x1800373c0  lea     rbp, [rax-0E8h]
0x1800373c7  sub     rsp, 210h
0x1800373ce  mov     rax, cs:__security_cookie
0x1800373d5  xor     rax, rsp
0x1800373d8  mov     [rbp+0E0h+var_30], rax
0x1800373df  lea     rdi, [rcx+110h]
0x1800373e6  mov     [rbp+0E0h+var_150], rdx
0x1800373ea  mov     rsi, [rdi]
0x1800373ed  mov     r12, r9
0x1800373f0  mov     r13d, r8d
0x1800373f3  mov     r14, rdx
0x1800373f6  mov     r15, rcx
0x1800373f9  mov     eax, [rsi+48h]
0x1800373fc  test    eax, eax
0x1800373fe  jns     loc_180037609
0x180037404  add     rsi, 50h ; 'P'
0x180037408  cmp     eax, [rsi+8]
0x18003740b  jnz     loc_180037609
0x180037411  mov     rbx, rdi
0x180037414  test    rsi, rsi
0x180037417  jz      loc_18003760C
0x18003741d  lea     rdx, [rbp+0E0h+SRWLock]
0x180037421  mov     [rbp+0E0h+SRWLock], 0
0x180037429  call    ?LockExclusive@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003742e  mov     rax, [rdi]
0x180037431  mov     rcx, [rbp+0E0h+SRWLock]; SRWLock
0x180037435  mov     dword ptr [rax], 2
0x18003743b  test    rcx, rcx
0x18003743e  jz      short loc_180037446
0x180037440  call    cs:__imp_ReleaseSRWLockExclusive
0x180037446  call    ?Instance@Telemetry4Diag@Diagnostics@@KAPEAV12@XZ; Diagnostics::Telemetry4Diag::Instance(void)
0x18003744b  mov     r9, [rax+8]
0x18003744f  cmp     dword ptr [r9], 5
0x180037453  jbe     loc_18003779C
0x180037459  mov     rcx, 400000000000h
0x180037463  test    [r9+10h], rcx
0x180037467  jz      loc_18003779C
0x18003746d  mov     rax, [r9+18h]
0x180037471  and     rax, rcx
0x180037474  cmp     rax, [r9+18h]
0x180037478  jnz     loc_18003779C
0x18003747e  mov     r8, [rdi]
0x180037481  lea     rax, a15072603280120; "1507.2603.28012.0"
0x180037488  mov     [rbp+0E0h+var_130], rax
0x18003748c  add     r8, 8; int
0x180037490  mov     rax, [rbp+0E0h+arg_20]
0x180037497  mov     [rbp+0E0h+var_128], rax
0x18003749b  mov     rax, [r14]
0x18003749e  mov     [rbp+0E0h+var_118], rax
0x1800374a2  mov     rax, [rsi+78h]
0x1800374a6  mov     [rbp+0E0h+var_110], rax
0x1800374aa  mov     rax, [rsi+70h]
0x1800374ae  mov     [rbp+0E0h+var_108], rax
0x1800374b2  mov     eax, [rsi+68h]
0x1800374b5  mov     dword ptr [rbp+0E0h+var_148+4], eax
0x1800374b8  mov     rax, [rsi+60h]
0x1800374bc  mov     [rbp+0E0h+var_100], rax
0x1800374c0  mov     rax, [rsi+58h]
0x1800374c4  mov     [rbp+0E0h+var_F8], rax
0x1800374c8  mov     eax, [rsi+50h]
0x1800374cb  mov     dword ptr [rbp+0E0h+var_140], eax
0x1800374ce  mov     rax, [rsi+48h]
0x1800374d2  mov     [rbp+0E0h+var_F0], rax
0x1800374d6  mov     eax, [rsi+20h]
0x1800374d9  mov     dword ptr [rbp+0E0h+var_140+4], eax
0x1800374dc  mov     rax, [rsi+18h]
0x1800374e0  mov     [rbp+0E0h+var_E8], rax
0x1800374e4  mov     eax, [rsi]
0x1800374e6  mov     dword ptr [rbp+0E0h+var_158], eax
0x1800374e9  mov     rax, [rsi+80h]
0x1800374f0  mov     [rbp+0E0h+var_E0], rax
0x1800374f4  mov     eax, [rsi+40h]
0x1800374f7  mov     dword ptr [rbp+0E0h+var_158+4], eax
0x1800374fa  mov     rax, [rsi+38h]
0x1800374fe  mov     [rbp+0E0h+var_D8], rax
0x180037502  mov     eax, [rsi+8]
0x180037505  mov     dword ptr [rbp+0E0h+SRWLock], eax
0x180037508  mov     eax, 1000000h
0x18003750d  mov     [rbp+0E0h+var_138], rax
0x180037511  mov     [rbp+0E0h+var_150], rax
0x180037515  lea     rax, [rbp+0E0h+var_130]
0x180037519  mov     [rsp+230h+var_170], rax; __int64
0x180037521  lea     rax, [rbp+0E0h+var_128]
0x180037525  mov     [rsp+230h+var_178], rax; __int64
0x18003752d  lea     rax, [rbp+0E0h+var_120]
0x180037531  mov     [rsp+230h+var_180], rax; __int64
0x180037539  lea     rax, [rbp+0E0h+var_148]
0x18003753d  mov     [rsp+230h+var_188], rax; __int64
0x180037545  lea     rax, [rbp+0E0h+var_118]
0x180037549  mov     [rsp+230h+var_190], rax; __int64
0x180037551  lea     rax, [rbp+0E0h+var_110]
0x180037555  mov     [rsp+230h+var_198], rax; __int64
0x18003755d  lea     rax, [rbp+0E0h+var_108]
0x180037561  mov     [rsp+230h+var_1A0], rax; __int64
0x180037569  lea     rax, [rbp+0E0h+var_148+4]
0x18003756d  mov     [rsp+230h+var_1A8], rax; __int64
0x180037575  lea     rax, [rbp+0E0h+var_100]
0x180037579  mov     [rsp+230h+var_1B0], rax; __int64
0x180037581  lea     rax, [rbp+0E0h+var_F8]
0x180037585  mov     [rsp+230h+var_1B8], rax; __int64
0x18003758a  lea     rax, [rbp+0E0h+var_140]
0x18003758e  mov     [rsp+230h+var_1C0], rax; __int64
0x180037593  lea     rax, [rbp+0E0h+var_F0]
0x180037597  mov     [rsp+230h+var_1C8], rax; __int64
0x18003759c  lea     rax, [rbp+0E0h+var_140+4]
0x1800375a0  mov     [rsp+230h+var_1D0], rax; __int64
0x1800375a5  lea     rax, [rbp+0E0h+var_E8]
0x1800375a9  mov     [rsp+230h+var_1D8], rax; __int64
0x1800375ae  lea     rax, [rbp+0E0h+var_158]
0x1800375b2  mov     [rsp+230h+var_1E0], rax; __int64
0x1800375b7  lea     rax, [rbp+0E0h+var_E0]
0x1800375bb  mov     [rsp+230h+var_1E8], rax; __int64
0x1800375c0  lea     rax, [rbp+0E0h+var_158+4]
0x1800375c4  mov     [rsp+230h+var_1F0], rax; __int64
0x1800375c9  lea     rax, [rbp+0E0h+var_D8]
0x1800375cd  mov     [rsp+230h+var_1F8], rax; __int64
0x1800375d2  lea     rax, [rbp+0E0h+SRWLock]
0x1800375d6  mov     [rsp+230h+var_200], rax; __int64
0x1800375db  lea     rax, [rbp+0E0h+var_138]
0x1800375df  mov     [rsp+230h+var_208], rax; __int64
0x1800375e4  mov     [rbp+0E0h+var_120], r12
0x1800375e8  mov     dword ptr [rbp+0E0h+var_148], r13d
0x1800375ec  lea     rax, [rbp+0E0h+var_150]
0x1800375f0  mov     rcx, r9; int
0x1800375f3  lea     rdx, byte_180172177; int
0x1800375fa  mov     qword ptr [rsp+230h+var_210], rax; __int64
0x1800375ff  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U2@U1@U4@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@4545645664365@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &)
0x180037604  jmp     loc_18003779C
0x180037609  mov     rbx, rdi
0x18003760c  lea     rdx, [rbp+0E0h+SRWLock]
0x180037610  mov     [rbp+0E0h+SRWLock], 0
0x180037618  call    ?LockExclusive@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003761d  mov     rax, [rbx]
0x180037620  mov     ebx, 2
0x180037625  mov     rcx, [rbp+0E0h+SRWLock]; SRWLock
0x180037629  mov     [rax], ebx
0x18003762b  test    rcx, rcx
0x18003762e  jz      short loc_180037636
0x180037630  call    cs:__imp_ReleaseSRWLockExclusive
0x180037636  call    ?Instance@Telemetry4Diag@Diagnostics@@KAPEAV12@XZ; Diagnostics::Telemetry4Diag::Instance(void)
0x18003763b  mov     r14, [rax+8]
0x18003763f  cmp     dword ptr [r14], 5
0x180037643  jbe     loc_18003779C
0x180037649  mov     rcx, 400000000000h
0x180037653  test    [r14+10h], rcx
0x180037657  jz      loc_18003779C
0x18003765d  mov     rax, [r14+18h]
0x180037661  and     rax, rcx
0x180037664  cmp     rax, [r14+18h]
0x180037668  jnz     loc_18003779C
0x18003766e  mov     rsi, [rbp+0E0h+var_150]
0x180037672  mov     [rbp+0E0h+var_138], r12
0x180037676  mov     dword ptr [rbp+0E0h+SRWLock], r13d
0x18003767a  mov     rsi, [rsi]
0x18003767d  call    cs:__imp_GetCurrentThreadId
0x180037683  mov     r8, [rdi]
0x180037686  xor     r9d, r9d; int
0x180037689  mov     rdx, [rbp+0E0h+arg_20]
0x180037690  mov     dword ptr [rbp+0E0h+var_158+4], eax
0x180037693  mov     [rbp+0E0h+var_38], 12h
0x18003769e  mov     eax, [r8+48h]
0x1800376a2  mov     dword ptr [rbp+0E0h+var_158], eax
0x1800376a5  mov     eax, 1000000h
0x1800376aa  mov     [rbp+0E0h+var_150], rax
0x1800376ae  lea     rax, a15072603280120; "1507.2603.28012.0"
0x1800376b5  mov     [rbp+0E0h+var_40], rax
0x1800376bc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800376c0  test    rdx, rdx
0x1800376c3  jz      short loc_1800376DB
0x1800376c5  mov     rcx, rax
0x1800376c8  inc     rcx
0x1800376cb  cmp     [rdx+rcx*2], r9w
0x1800376d0  jnz     short loc_1800376C8
0x1800376d2  lea     ecx, ds:2[rcx*2]
0x1800376d9  jmp     short loc_1800376E4
0x1800376db  lea     rdx, psz
0x1800376e2  mov     ecx, ebx
0x1800376e4  mov     [rbp+0E0h+var_48], ecx
0x1800376ea  lea     rcx, [rbp+0E0h+var_138]
0x1800376ee  mov     [rbp+0E0h+var_60], rcx
0x1800376f5  lea     rcx, [rbp+0E0h+SRWLock]
0x1800376f9  mov     [rbp+0E0h+var_70], rcx
0x1800376fd  mov     [rbp+0E0h+var_50], rdx
0x180037704  mov     [rbp+0E0h+var_44], r9d
0x18003770b  mov     [rbp+0E0h+var_58], 8
0x180037716  mov     [rbp+0E0h+var_68], 4
0x18003771e  test    rsi, rsi
0x180037721  jz      short loc_180037736
0x180037723  inc     rax
0x180037726  cmp     [rsi+rax*2], r9w
0x18003772b  jnz     short loc_180037723
0x18003772d  lea     ebx, ds:2[rax*2]
0x180037734  jmp     short loc_18003773D
0x180037736  lea     rsi, psz
0x18003773d  lea     rax, [rbp+0E0h+var_158+4]
0x180037741  mov     [rbp+0E0h+var_80], rsi
0x180037745  mov     [rbp+0E0h+var_90], rax
0x180037749  lea     rdx, byte_1801720E5; int
0x180037750  lea     rax, [rbp+0E0h+var_158]
0x180037754  mov     [rbp+0E0h+var_78], ebx
0x180037757  mov     [rbp+0E0h+var_A0], rax
0x18003775b  add     r8, 8; int
0x18003775f  lea     rax, [rbp+0E0h+var_150]
0x180037763  mov     [rbp+0E0h+var_74], r9d
0x180037767  mov     [rbp+0E0h+var_B0], rax
0x18003776b  mov     rcx, r14; int
0x18003776e  lea     rax, [rbp+0E0h+var_D0]
0x180037772  mov     [rbp+0E0h+var_88], 4
0x18003777a  mov     [rsp+230h+var_208], rax; PEVENT_DATA_DESCRIPTOR
0x18003777f  mov     [rsp+230h+var_210], 0Ah; ULONG
0x180037787  mov     [rbp+0E0h+var_98], 4
0x18003778f  mov     [rbp+0E0h+var_A8], 8
0x180037797  call    _tlgWriteTransfer_EventWriteTransfer
0x18003779c  mov     rcx, r15
0x18003779f  call    ?IgnoreCurrentThread@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x1800377a4  mov     rcx, [rbp+0E0h+var_30]
0x1800377ab  xor     rcx, rsp; StackCookie
0x1800377ae  call    __security_check_cookie
0x1800377b3  lea     r11, [rsp+230h+var_20]
0x1800377bb  mov     rbx, [r11+38h]
0x1800377bf  mov     rsi, [r11+40h]
0x1800377c3  mov     rdi, [r11+48h]
0x1800377c7  mov     rsp, r11
0x1800377ca  pop     r15
0x1800377cc  pop     r14
0x1800377ce  pop     r13
0x1800377d0  pop     r12
0x1800377d2  pop     rbp
0x1800377d3  retn
```
