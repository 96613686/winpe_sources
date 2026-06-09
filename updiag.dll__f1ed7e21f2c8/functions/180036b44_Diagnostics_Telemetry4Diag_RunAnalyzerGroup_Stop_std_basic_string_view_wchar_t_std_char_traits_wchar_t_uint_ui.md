# Diagnostics::Telemetry4Diag::RunAnalyzerGroup::Stop(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,uint,uint)

- ea: `0x180036b44`
- end: `0x180036f11`
- name: `?Stop@RunAnalyzerGroup@Telemetry4Diag@Diagnostics@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@II@Z`
- size: `973`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x18003c384`
- `0x180049258`
- `0x180049e38`

## callees

- `0x180001350`
- `0x180001eb0`
- `0x1800080f8`
- `0x180017ad8`
- `0x180017e80`
- `0x180036b44`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036bd8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036db1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036bd8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036db1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036df9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036df9`

## pseudocode

```c
void __fastcall Diagnostics::Telemetry4Diag::RunAnalyzerGroup::Stop(__int64 a1, __int64 *a2, int a3, int a4)
{
  _DWORD **v4; // r14
  __int64 v6; // rdi
  int v10; // eax
  __int64 v11; // rdi
  _DWORD **v12; // rbx
  RTL_SRWLOCK *v13; // rcx
  __int64 v14; // r9
  _DWORD *v15; // r8
  _DWORD *v16; // rax
  int v17; // ebx
  RTL_SRWLOCK *v18; // rcx
  __int64 v19; // rdi
  const wchar_t *v20; // rsi
  DWORD CurrentThreadId; // eax
  _DWORD *v22; // r8
  __int64 v23; // rbx
  PSRWLOCK SRWLock; // [rsp+C8h] [rbp-80h] BYREF
  int v25; // [rsp+D0h] [rbp-78h] BYREF
  DWORD v26; // [rsp+D4h] [rbp-74h] BYREF
  int v27; // [rsp+D8h] [rbp-70h] BYREF
  int v28; // [rsp+DCh] [rbp-6Ch] BYREF
  int v29; // [rsp+E0h] [rbp-68h] BYREF
  int v30; // [rsp+E4h] [rbp-64h] BYREF
  int v31; // [rsp+E8h] [rbp-60h] BYREF
  __int64 v32; // [rsp+F0h] [rbp-58h] BYREF
  __int64 v33; // [rsp+F8h] [rbp-50h] BYREF
  __int64 v34; // [rsp+100h] [rbp-48h] BYREF
  __int64 v35; // [rsp+108h] [rbp-40h] BYREF
  __int64 v36; // [rsp+110h] [rbp-38h] BYREF
  __int64 v37; // [rsp+118h] [rbp-30h] BYREF
  __int64 v38; // [rsp+120h] [rbp-28h] BYREF
  __int64 v39; // [rsp+128h] [rbp-20h] BYREF
  __int64 v40; // [rsp+130h] [rbp-18h] BYREF
  __int64 v41; // [rsp+138h] [rbp-10h] BYREF
  __int64 v42; // [rsp+140h] [rbp-8h] BYREF
  __int64 v43; // [rsp+148h] [rbp+0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v44; // [rsp+158h] [rbp+10h] BYREF
  __int64 *v45; // [rsp+178h] [rbp+30h]
  __int64 v46; // [rsp+180h] [rbp+38h]
  int *v47; // [rsp+188h] [rbp+40h]
  __int64 v48; // [rsp+190h] [rbp+48h]
  DWORD *v49; // [rsp+198h] [rbp+50h]
  __int64 v50; // [rsp+1A0h] [rbp+58h]
  const wchar_t *v51; // [rsp+1A8h] [rbp+60h]
  int v52; // [rsp+1B0h] [rbp+68h]
  int v53; // [rsp+1B4h] [rbp+6Ch]
  int *v54; // [rsp+1B8h] [rbp+70h]
  __int64 v55; // [rsp+1C0h] [rbp+78h]
  PSRWLOCK *p_SRWLock; // [rsp+1C8h] [rbp+80h]
  __int64 v57; // [rsp+1D0h] [rbp+88h]
  const char *v58; // [rsp+1D8h] [rbp+90h]
  __int64 v59; // [rsp+1E0h] [rbp+98h]

  v4 = (_DWORD **)(a1 + 272);
  v6 = *(_QWORD *)(a1 + 272);
  v10 = *(_DWORD *)(v6 + 72);
  if ( v10 < 0 && (v11 = v6 + 80, v10 == *(_DWORD *)(v11 + 8)) )
  {
    v12 = (_DWORD **)(a1 + 272);
    if ( v11 )
    {
      SRWLock = 0;
      wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        a1,
        &SRWLock);
      v13 = SRWLock;
      **v4 = 2;
      if ( v13 )
        ReleaseSRWLockExclusive(v13);
      v14 = *((_QWORD *)Diagnostics::Telemetry4Diag::Instance() + 1);
      if ( *(_DWORD *)v14 > 5u
        && (*(_QWORD *)(v14 + 16) & 0x400000000000LL) != 0
        && (*(_QWORD *)(v14 + 24) & 0x400000000000LL) == *(_QWORD *)(v14 + 24) )
      {
        v15 = *v4;
        v33 = (__int64)"1507.2603.28012.0";
        v34 = *a2;
        v35 = *(_QWORD *)(v11 + 120);
        v36 = *(_QWORD *)(v11 + 112);
        v30 = *(_DWORD *)(v11 + 104);
        v37 = *(_QWORD *)(v11 + 96);
        v38 = *(_QWORD *)(v11 + 88);
        v31 = *(_DWORD *)(v11 + 80);
        v39 = *(_QWORD *)(v11 + 72);
        v25 = *(_DWORD *)(v11 + 32);
        v40 = *(_QWORD *)(v11 + 24);
        v26 = *(_DWORD *)v11;
        v41 = *(_QWORD *)(v11 + 128);
        v27 = *(_DWORD *)(v11 + 64);
        v42 = *(_QWORD *)(v11 + 56);
        LODWORD(SRWLock) = *(_DWORD *)(v11 + 8);
        v43 = 0x1000000;
        v32 = 0x1000000;
        v28 = a4;
        v29 = a3;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v14,
          (int)&dword_180172544,
          (_DWORD)v15 + 8,
          v14,
          (__int64)&v32,
          (__int64)&v43,
          (__int64)&SRWLock,
          (const wchar_t **)&v42,
          (__int64)&v27,
          (const wchar_t **)&v41,
          (__int64)&v26,
          (const wchar_t **)&v40,
          (__int64)&v25,
          (const wchar_t **)&v39,
          (__int64)&v31,
          (const wchar_t **)&v38,
          (const wchar_t **)&v37,
          (__int64)&v30,
          (const wchar_t **)&v36,
          (const wchar_t **)&v35,
          (const wchar_t **)&v34,
          (__int64)&v29,
          (__int64)&v28,
          (const wchar_t **)&v33);
      }
      goto LABEL_22;
    }
  }
  else
  {
    v12 = (_DWORD **)(a1 + 272);
  }
  SRWLock = 0;
  wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v16 = *v12;
  v17 = 2;
  v18 = SRWLock;
  *v16 = 2;
  if ( v18 )
    ReleaseSRWLockExclusive(v18);
  v19 = *((_QWORD *)Diagnostics::Telemetry4Diag::Instance() + 1);
  if ( *(_DWORD *)v19 > 5u
    && (*(_QWORD *)(v19 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v19 + 24) & 0x400000000000LL) == *(_QWORD *)(v19 + 24) )
  {
    LODWORD(SRWLock) = a4;
    v20 = (const wchar_t *)*a2;
    v27 = a3;
    CurrentThreadId = GetCurrentThreadId();
    v22 = *v4;
    v26 = CurrentThreadId;
    v59 = 18;
    v57 = 4;
    v25 = v22[18];
    v32 = 0x1000000;
    v58 = "1507.2603.28012.0";
    p_SRWLock = &SRWLock;
    v54 = &v27;
    v55 = 4;
    if ( v20 )
    {
      v23 = -1;
      do
        ++v23;
      while ( v20[v23] );
      v17 = 2 * v23 + 2;
    }
    else
    {
      v20 = &psz;
    }
    v53 = 0;
    v49 = &v26;
    v51 = v20;
    v47 = &v25;
    v52 = v17;
    v45 = &v32;
    v50 = 4;
    v48 = 4;
    v46 = 8;
    tlgWriteTransfer_EventWriteTransfer(v19, (unsigned __int8 *)&qword_1801724C0, (const GUID *)(v22 + 2), 0, 9u, &v44);
  }
LABEL_22:
  wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x180036b44  mov     rax, rsp
0x180036b47  mov     [rax+10h], rbx
0x180036b4b  mov     [rax+18h], rsi
0x180036b4f  mov     [rax+20h], rdi
0x180036b53  push    rbp
0x180036b54  push    r12
0x180036b56  push    r13
0x180036b58  push    r14
0x180036b5a  push    r15
0x180036b5c  lea     rbp, [rax-0D8h]
0x180036b63  sub     rsp, 1F0h
0x180036b6a  mov     rax, cs:__security_cookie
0x180036b71  xor     rax, rsp
0x180036b74  mov     [rbp+0D0h+var_30], rax
0x180036b7b  lea     r14, [rcx+110h]
0x180036b82  mov     esi, r9d
0x180036b85  mov     rdi, [r14]
0x180036b88  mov     r12d, r8d
0x180036b8b  mov     r13, rdx
0x180036b8e  mov     r15, rcx
0x180036b91  mov     eax, [rdi+48h]
0x180036b94  test    eax, eax
0x180036b96  jns     loc_180036D8A
0x180036b9c  add     rdi, 50h ; 'P'
0x180036ba0  cmp     eax, [rdi+8]
0x180036ba3  jnz     loc_180036D8A
0x180036ba9  mov     rbx, r14
0x180036bac  test    rdi, rdi
0x180036baf  jz      loc_180036D8D
0x180036bb5  lea     rdx, [rbp+0D0h+SRWLock]
0x180036bb9  mov     [rbp+0D0h+SRWLock], 0
0x180036bc1  call    ?LockExclusive@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180036bc6  mov     rax, [r14]
0x180036bc9  mov     rcx, [rbp+0D0h+SRWLock]; SRWLock
0x180036bcd  mov     dword ptr [rax], 2
0x180036bd3  test    rcx, rcx
0x180036bd6  jz      short loc_180036BDE
0x180036bd8  call    cs:__imp_ReleaseSRWLockExclusive
0x180036bde  call    ?Instance@Telemetry4Diag@Diagnostics@@KAPEAV12@XZ; Diagnostics::Telemetry4Diag::Instance(void)
0x180036be3  mov     r9, [rax+8]
0x180036be7  cmp     dword ptr [r9], 5
0x180036beb  jbe     loc_180036ED9
0x180036bf1  mov     rcx, 400000000000h
0x180036bfb  test    [r9+10h], rcx
0x180036bff  jz      loc_180036ED9
0x180036c05  mov     rax, [r9+18h]
0x180036c09  and     rax, rcx
0x180036c0c  cmp     rax, [r9+18h]
0x180036c10  jnz     loc_180036ED9
0x180036c16  mov     r8, [r14]
0x180036c19  lea     rax, a15072603280120; "1507.2603.28012.0"
0x180036c20  mov     [rbp+0D0h+var_120], rax
0x180036c24  lea     rdx, dword_180172544; int
0x180036c2b  mov     rax, [r13+0]
0x180036c2f  add     r8, 8; int
0x180036c33  mov     [rbp+0D0h+var_118], rax
0x180036c37  mov     rcx, r9; int
0x180036c3a  mov     rax, [rdi+78h]
0x180036c3e  mov     [rbp+0D0h+var_110], rax
0x180036c42  mov     rax, [rdi+70h]
0x180036c46  mov     [rbp+0D0h+var_108], rax
0x180036c4a  mov     eax, [rdi+68h]
0x180036c4d  mov     dword ptr [rbp+0D0h+var_138+4], eax
0x180036c50  mov     rax, [rdi+60h]
0x180036c54  mov     [rbp+0D0h+var_100], rax
0x180036c58  mov     rax, [rdi+58h]
0x180036c5c  mov     [rbp+0D0h+var_F8], rax
0x180036c60  mov     eax, [rdi+50h]
0x180036c63  mov     [rbp+0D0h+var_130], eax
0x180036c66  mov     rax, [rdi+48h]
0x180036c6a  mov     [rbp+0D0h+var_F0], rax
0x180036c6e  mov     eax, [rdi+20h]
0x180036c71  mov     dword ptr [rbp+0D0h+var_148], eax
0x180036c74  mov     rax, [rdi+18h]
0x180036c78  mov     [rbp+0D0h+var_E8], rax
0x180036c7c  mov     eax, [rdi]
0x180036c7e  mov     dword ptr [rbp+0D0h+var_148+4], eax
0x180036c81  mov     rax, [rdi+80h]
0x180036c88  mov     [rbp+0D0h+var_E0], rax
0x180036c8c  mov     eax, [rdi+40h]
0x180036c8f  mov     dword ptr [rbp+0D0h+var_140], eax
0x180036c92  mov     rax, [rdi+38h]
0x180036c96  mov     [rbp+0D0h+var_D8], rax
0x180036c9a  mov     eax, [rdi+8]
0x180036c9d  mov     dword ptr [rbp+0D0h+SRWLock], eax
0x180036ca0  mov     eax, 1000000h
0x180036ca5  mov     [rbp+0D0h+var_D0], rax
0x180036ca9  mov     [rbp+0D0h+var_128], rax
0x180036cad  lea     rax, [rbp+0D0h+var_120]
0x180036cb1  mov     [rsp+210h+var_158], rax; __int64
0x180036cb9  lea     rax, [rbp+0D0h+var_140+4]
0x180036cbd  mov     [rsp+210h+var_160], rax; __int64
0x180036cc5  lea     rax, [rbp+0D0h+var_138]
0x180036cc9  mov     [rsp+210h+var_168], rax; __int64
0x180036cd1  lea     rax, [rbp+0D0h+var_118]
0x180036cd5  mov     [rsp+210h+var_170], rax; __int64
0x180036cdd  lea     rax, [rbp+0D0h+var_110]
0x180036ce1  mov     [rsp+210h+var_178], rax; __int64
0x180036ce9  lea     rax, [rbp+0D0h+var_108]
0x180036ced  mov     [rsp+210h+var_180], rax; __int64
0x180036cf5  lea     rax, [rbp+0D0h+var_138+4]
0x180036cf9  mov     [rsp+210h+var_188], rax; __int64
0x180036d01  lea     rax, [rbp+0D0h+var_100]
0x180036d05  mov     [rsp+210h+var_190], rax; __int64
0x180036d0d  lea     rax, [rbp+0D0h+var_F8]
0x180036d11  mov     [rsp+210h+var_198], rax; __int64
0x180036d16  lea     rax, [rbp+0D0h+var_130]
0x180036d1a  mov     [rsp+210h+var_1A0], rax; __int64
0x180036d1f  lea     rax, [rbp+0D0h+var_F0]
0x180036d23  mov     [rsp+210h+var_1A8], rax; __int64
0x180036d28  lea     rax, [rbp+0D0h+var_148]
0x180036d2c  mov     [rsp+210h+var_1B0], rax; __int64
0x180036d31  lea     rax, [rbp+0D0h+var_E8]
0x180036d35  mov     [rsp+210h+var_1B8], rax; __int64
0x180036d3a  lea     rax, [rbp+0D0h+var_148+4]
0x180036d3e  mov     [rsp+210h+var_1C0], rax; __int64
0x180036d43  lea     rax, [rbp+0D0h+var_E0]
0x180036d47  mov     [rsp+210h+var_1C8], rax; __int64
0x180036d4c  lea     rax, [rbp+0D0h+var_140]
0x180036d50  mov     [rsp+210h+var_1D0], rax; __int64
0x180036d55  lea     rax, [rbp+0D0h+var_D8]
0x180036d59  mov     [rsp+210h+var_1D8], rax; __int64
0x180036d5e  lea     rax, [rbp+0D0h+SRWLock]
0x180036d62  mov     [rsp+210h+var_1E0], rax; __int64
0x180036d67  lea     rax, [rbp+0D0h+var_D0]
0x180036d6b  mov     [rsp+210h+var_1E8], rax; __int64
0x180036d70  lea     rax, [rbp+0D0h+var_128]
0x180036d74  mov     qword ptr [rsp+210h+var_1F0], rax; __int64
0x180036d79  mov     dword ptr [rbp+0D0h+var_140+4], esi
0x180036d7c  mov     dword ptr [rbp+0D0h+var_138], r12d
0x180036d80  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@454564566445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180036d85  jmp     loc_180036ED9
0x180036d8a  mov     rbx, r14
0x180036d8d  lea     rdx, [rbp+0D0h+SRWLock]
0x180036d91  mov     [rbp+0D0h+SRWLock], 0
0x180036d99  call    ?LockExclusive@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180036d9e  mov     rax, [rbx]
0x180036da1  mov     ebx, 2
0x180036da6  mov     rcx, [rbp+0D0h+SRWLock]; SRWLock
0x180036daa  mov     [rax], ebx
0x180036dac  test    rcx, rcx
0x180036daf  jz      short loc_180036DB7
0x180036db1  call    cs:__imp_ReleaseSRWLockExclusive
0x180036db7  call    ?Instance@Telemetry4Diag@Diagnostics@@KAPEAV12@XZ; Diagnostics::Telemetry4Diag::Instance(void)
0x180036dbc  mov     rdi, [rax+8]
0x180036dc0  cmp     dword ptr [rdi], 5
0x180036dc3  jbe     loc_180036ED9
0x180036dc9  mov     rcx, 400000000000h
0x180036dd3  test    [rdi+10h], rcx
0x180036dd7  jz      loc_180036ED9
0x180036ddd  mov     rax, [rdi+18h]
0x180036de1  and     rax, rcx
0x180036de4  cmp     rax, [rdi+18h]
0x180036de8  jnz     loc_180036ED9
0x180036dee  mov     dword ptr [rbp+0D0h+SRWLock], esi
0x180036df1  mov     rsi, [r13+0]
0x180036df5  mov     dword ptr [rbp+0D0h+var_140], r12d
0x180036df9  call    cs:__imp_GetCurrentThreadId
0x180036dff  mov     r8, [r14]
0x180036e02  xor     ecx, ecx
0x180036e04  mov     dword ptr [rbp+0D0h+var_148+4], eax
0x180036e07  mov     [rbp+0D0h+var_38], 12h
0x180036e12  mov     [rbp+0D0h+var_48], 4
0x180036e1d  mov     eax, [r8+48h]
0x180036e21  mov     dword ptr [rbp+0D0h+var_148], eax
0x180036e24  mov     eax, 1000000h
0x180036e29  mov     [rbp+0D0h+var_128], rax
0x180036e2d  lea     rax, a15072603280120; "1507.2603.28012.0"
0x180036e34  mov     [rbp+0D0h+var_40], rax
0x180036e3b  lea     rax, [rbp+0D0h+SRWLock]
0x180036e3f  mov     [rbp+0D0h+var_50], rax
0x180036e46  lea     rax, [rbp+0D0h+var_140]
0x180036e4a  mov     [rbp+0D0h+var_60], rax
0x180036e4e  mov     [rbp+0D0h+var_58], 4
0x180036e56  test    rsi, rsi
0x180036e59  jz      short loc_180036E71
0x180036e5b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180036e5f  inc     rbx
0x180036e62  cmp     [rsi+rbx*2], cx
0x180036e66  jnz     short loc_180036E5F
0x180036e68  lea     ebx, ds:2[rbx*2]
0x180036e6f  jmp     short loc_180036E78
0x180036e71  lea     rsi, psz
0x180036e78  lea     rax, [rbp+0D0h+var_148+4]
0x180036e7c  mov     [rbp+0D0h+var_64], ecx
0x180036e7f  mov     [rbp+0D0h+var_80], rax
0x180036e83  lea     rdx, qword_1801724C0; int
0x180036e8a  lea     rax, [rbp+0D0h+var_148]
0x180036e8e  mov     [rbp+0D0h+var_70], rsi
0x180036e92  mov     [rbp+0D0h+var_90], rax
0x180036e96  add     r8, 8; int
0x180036e9a  lea     rax, [rbp+0D0h+var_128]
0x180036e9e  mov     [rbp+0D0h+var_68], ebx
0x180036ea1  mov     [rbp+0D0h+var_A0], rax
0x180036ea5  xor     r9d, r9d; int
0x180036ea8  lea     rax, [rbp+0D0h+var_C0]
0x180036eac  mov     [rbp+0D0h+var_78], 4
0x180036eb4  mov     [rsp+210h+var_1E8], rax; PEVENT_DATA_DESCRIPTOR
0x180036eb9  mov     rcx, rdi; int
0x180036ebc  mov     [rsp+210h+var_1F0], 9; ULONG
0x180036ec4  mov     [rbp+0D0h+var_88], 4
0x180036ecc  mov     [rbp+0D0h+var_98], 8
0x180036ed4  call    _tlgWriteTransfer_EventWriteTransfer
0x180036ed9  mov     rcx, r15
0x180036edc  call    ?IgnoreCurrentThread@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180036ee1  mov     rcx, [rbp+0D0h+var_30]
0x180036ee8  xor     rcx, rsp; StackCookie
0x180036eeb  call    __security_check_cookie
0x180036ef0  lea     r11, [rsp+210h+var_20]
0x180036ef8  mov     rbx, [r11+38h]
0x180036efc  mov     rsi, [r11+40h]
0x180036f00  mov     rdi, [r11+48h]
0x180036f04  mov     rsp, r11
0x180036f07  pop     r15
0x180036f09  pop     r14
0x180036f0b  pop     r13
0x180036f0d  pop     r12
0x180036f0f  pop     rbp
0x180036f10  retn
```
