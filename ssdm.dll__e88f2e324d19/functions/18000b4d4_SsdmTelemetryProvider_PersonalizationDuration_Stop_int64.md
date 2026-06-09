# SsdmTelemetryProvider::PersonalizationDuration::Stop(__int64)

- ea: `0x18000b4d4`
- end: `0x18000b836`
- name: `?Stop@PersonalizationDuration@SsdmTelemetryProvider@@QEAAX_J@Z`
- size: `866`
- prototype: `void __fastcall(SsdmTelemetryProvider::PersonalizationDuration *__hidden this, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000ace8`

## callees

- `0x18000163c`
- `0x1800016dc`
- `0x1800063b4`
- `0x18000a8cc`
- `0x18000b4d4`
- `0x18000e990`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b72d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b7c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b72d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b7c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b540`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b6e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b540`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b6e5`

## string_xrefs

- `0x18000b7e2`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SsdmTelemetryProvider::PersonalizationDuration::Stop(
        SsdmTelemetryProvider::PersonalizationDuration *this,
        RTL_SRWLOCK *a2)
{
  __int64 v4; // rdi
  int v5; // eax
  int *v6; // rdi
  __int64 v7; // r9
  __int64 v8; // rdi
  __int64 v9; // r8
  char *v10; // rbx
  __int64 *v11; // rcx
  __int64 v12; // rax
  int v13; // [rsp+B0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+B8h] [rbp-78h] BYREF
  PSRWLOCK v15; // [rsp+C0h] [rbp-70h] BYREF
  int v16; // [rsp+C8h] [rbp-68h] BYREF
  int v17; // [rsp+CCh] [rbp-64h] BYREF
  int v18; // [rsp+D0h] [rbp-60h] BYREF
  int v19; // [rsp+D4h] [rbp-5Ch] BYREF
  __int64 v20; // [rsp+D8h] [rbp-58h] BYREF
  RTL_SRWLOCK *v21; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v22; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v23; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v24; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v25; // [rsp+100h] [rbp-30h] BYREF
  __int64 v26; // [rsp+108h] [rbp-28h] BYREF
  __int64 v27; // [rsp+110h] [rbp-20h] BYREF
  __int64 v28; // [rsp+118h] [rbp-18h] BYREF
  __int64 v29; // [rsp+120h] [rbp-10h] BYREF
  _BYTE v30[32]; // [rsp+130h] [rbp+0h] BYREF
  __int64 *v31; // [rsp+150h] [rbp+20h]
  __int64 v32; // [rsp+158h] [rbp+28h]
  int *v33; // [rsp+160h] [rbp+30h]
  __int64 v34; // [rsp+168h] [rbp+38h]
  PSRWLOCK *p_SRWLock; // [rsp+170h] [rbp+40h]
  __int64 v36; // [rsp+178h] [rbp+48h]
  PSRWLOCK *v37; // [rsp+180h] [rbp+50h]
  __int64 v38; // [rsp+188h] [rbp+58h]
  void *retaddr; // [rsp+1C8h] [rbp+98h]

  v4 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v4 + 72);
  if ( v5 < 0 && (v6 = (int *)(v4 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<SsdmTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v7 = *((_QWORD *)SsdmTelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v7 > 5u
      && (*(_QWORD *)(v7 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v7 + 24) & 0x200000000000LL) == *(_QWORD *)(v7 + 24) )
    {
      v21 = a2;
      v22 = *((_QWORD *)v6 + 15);
      v23 = *((_QWORD *)v6 + 14);
      v16 = v6[26];
      v24 = *((_QWORD *)v6 + 12);
      v25 = *((_QWORD *)v6 + 11);
      v17 = v6[20];
      v26 = *((_QWORD *)v6 + 9);
      v18 = v6[8];
      v27 = *((_QWORD *)v6 + 3);
      v19 = *v6;
      v28 = *((_QWORD *)v6 + 16);
      v13 = v6[16];
      v29 = *((_QWORD *)v6 + 7);
      LODWORD(SRWLock) = v6[2];
      v20 = 0x1000000;
      v15 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(
        v7,
        (unsigned int)byte_1800174D9,
        *((_QWORD *)this + 34) + 8,
        v7,
        (__int64)&v15,
        (__int64)&v20,
        (__int64)&SRWLock,
        (__int64)&v29,
        (__int64)&v13,
        (__int64)&v28,
        (__int64)&v19,
        (__int64)&v27,
        (__int64)&v18,
        (__int64)&v26,
        (__int64)&v17,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v16,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v21);
    }
  }
  else
  {
    wil::ActivityBase<SsdmTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v15);
    **((_DWORD **)this + 34) = 2;
    if ( v15 )
      ReleaseSRWLockExclusive(v15);
    v8 = *((_QWORD *)SsdmTelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v8 > 5u
      && (*(_QWORD *)(v8 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v8 + 24) & 0x200000000000LL) == *(_QWORD *)(v8 + 24) )
    {
      v15 = a2;
      LODWORD(SRWLock) = GetCurrentThreadId();
      v9 = *((_QWORD *)this + 34);
      v13 = *(_DWORD *)(v9 + 72);
      v20 = 0;
      v37 = &v15;
      v38 = 8;
      p_SRWLock = &SRWLock;
      v36 = 4;
      v33 = &v13;
      v34 = 4;
      v31 = &v20;
      v32 = 8;
      tlgWriteTransfer_EventWriteTransfer(v8, byte_180017625, v9 + 8, 0, 6, v30);
    }
  }
  if ( *((_DWORD *)this + 78) )
  {
    v10 = (char *)this + 288;
    if ( *((_DWORD *)v10 + 6) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *((_DWORD *)v10 + 6) = 0;
    v11 = *(__int64 **)v10;
    while ( 1 )
    {
      v12 = *v11;
      if ( !*v11 )
        break;
      if ( (char *)v12 == v10 )
      {
        *v11 = *((_QWORD *)v10 + 2);
        break;
      }
      v11 = (__int64 *)(v12 + 16);
      *(_QWORD *)v10 = v12 + 16;
    }
    *(_QWORD *)v10 = 0;
  }
}

```

## disassembly

```asm
0x18000b4d4  push    rbp
0x18000b4d6  push    rbx
0x18000b4d7  push    rsi
0x18000b4d8  push    rdi
0x18000b4d9  lea     rbp, [rsp-78h]
0x18000b4de  sub     rsp, 1A8h
0x18000b4e5  mov     rax, cs:__security_cookie
0x18000b4ec  xor     rax, rsp
0x18000b4ef  mov     [rbp+90h+var_30], rax
0x18000b4f3  mov     rsi, rdx
0x18000b4f6  mov     rbx, rcx
0x18000b4f9  mov     rdi, [rcx+110h]
0x18000b500  mov     eax, [rdi+48h]
0x18000b503  test    eax, eax
0x18000b505  jns     loc_18000B6C6
0x18000b50b  add     rdi, 50h ; 'P'
0x18000b50f  cmp     eax, [rdi+8]
0x18000b512  jnz     loc_18000B6C6
0x18000b518  test    rdi, rdi
0x18000b51b  jz      loc_18000B6C6
0x18000b521  lea     rdx, [rbp+90h+SRWLock]
0x18000b525  call    ?LockExclusive@?$ActivityBase@VSsdmTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SsdmTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b52a  mov     rax, [rbx+110h]
0x18000b531  mov     dword ptr [rax], 2
0x18000b537  mov     rcx, [rbp+90h+SRWLock]; SRWLock
0x18000b53b  test    rcx, rcx
0x18000b53e  jz      short loc_18000B546
0x18000b540  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b546  call    ?Instance@SsdmTelemetryProvider@@KAPEAV1@XZ; SsdmTelemetryProvider::Instance(void)
0x18000b54b  mov     r9, [rax+8]
0x18000b54f  mov     eax, [r9]
0x18000b552  cmp     eax, 5
0x18000b555  jbe     loc_18000B7B4
0x18000b55b  mov     rdx, [r9+18h]
0x18000b55f  mov     rax, [r9+10h]
0x18000b563  mov     rcx, 200000000000h
0x18000b56d  test    rcx, rax
0x18000b570  jz      loc_18000B7B4
0x18000b576  mov     rax, rdx
0x18000b579  and     rax, rcx
0x18000b57c  cmp     rax, rdx
0x18000b57f  jnz     loc_18000B7B4
0x18000b585  mov     [rbp+90h+var_E0], rsi
0x18000b589  mov     rax, [rdi+78h]
0x18000b58d  mov     [rbp+90h+var_D8], rax
0x18000b591  mov     rax, [rdi+70h]
0x18000b595  mov     [rbp+90h+var_D0], rax
0x18000b599  mov     eax, [rdi+68h]
0x18000b59c  mov     [rbp+90h+var_F8], eax
0x18000b59f  mov     rax, [rdi+60h]
0x18000b5a3  mov     [rbp+90h+var_C8], rax
0x18000b5a7  mov     rax, [rdi+58h]
0x18000b5ab  mov     [rbp+90h+var_C0], rax
0x18000b5af  mov     eax, [rdi+50h]
0x18000b5b2  mov     [rbp+90h+var_F4], eax
0x18000b5b5  mov     rax, [rdi+48h]
0x18000b5b9  mov     [rbp+90h+var_B8], rax
0x18000b5bd  mov     eax, [rdi+20h]
0x18000b5c0  mov     [rbp+90h+var_F0], eax
0x18000b5c3  mov     rax, [rdi+18h]
0x18000b5c7  mov     [rbp+90h+var_B0], rax
0x18000b5cb  mov     eax, [rdi]
0x18000b5cd  mov     [rbp+90h+var_EC], eax
0x18000b5d0  mov     rax, [rdi+80h]
0x18000b5d7  mov     [rbp+90h+var_A8], rax
0x18000b5db  mov     eax, [rdi+40h]
0x18000b5de  mov     [rbp+90h+var_110], eax
0x18000b5e1  mov     rax, [rdi+38h]
0x18000b5e5  mov     [rbp+90h+var_A0], rax
0x18000b5e9  mov     eax, [rdi+8]
0x18000b5ec  mov     dword ptr [rbp+90h+SRWLock], eax
0x18000b5ef  mov     [rbp+90h+var_E8], 1000000h
0x18000b5f7  mov     [rbp+90h+var_100], 0
0x18000b5ff  mov     r8, [rbx+110h]
0x18000b606  add     r8, 8
0x18000b60a  lea     rax, [rbp+90h+var_E0]
0x18000b60e  mov     [rsp+1C0h+var_120], rax
0x18000b616  lea     rax, [rbp+90h+var_D8]
0x18000b61a  mov     [rsp+1C0h+var_128], rax
0x18000b622  lea     rax, [rbp+90h+var_D0]
0x18000b626  mov     [rsp+1C0h+var_130], rax
0x18000b62e  lea     rax, [rbp+90h+var_F8]
0x18000b632  mov     [rsp+1C0h+var_138], rax
0x18000b63a  lea     rax, [rbp+90h+var_C8]
0x18000b63e  mov     [rsp+1C0h+var_140], rax
0x18000b646  lea     rax, [rbp+90h+var_C0]
0x18000b64a  mov     [rsp+1C0h+var_148], rax
0x18000b64f  lea     rax, [rbp+90h+var_F4]
0x18000b653  mov     [rsp+1C0h+var_150], rax
0x18000b658  lea     rax, [rbp+90h+var_B8]
0x18000b65c  mov     [rsp+1C0h+var_158], rax
0x18000b661  lea     rax, [rbp+90h+var_F0]
0x18000b665  mov     [rsp+1C0h+var_160], rax
0x18000b66a  lea     rax, [rbp+90h+var_B0]
0x18000b66e  mov     [rsp+1C0h+var_168], rax
0x18000b673  lea     rax, [rbp+90h+var_EC]
0x18000b677  mov     [rsp+1C0h+var_170], rax
0x18000b67c  lea     rax, [rbp+90h+var_A8]
0x18000b680  mov     [rsp+1C0h+var_178], rax
0x18000b685  lea     rax, [rbp+90h+var_110]
0x18000b689  mov     [rsp+1C0h+var_180], rax
0x18000b68e  lea     rax, [rbp+90h+var_A0]
0x18000b692  mov     [rsp+1C0h+var_188], rax
0x18000b697  lea     rax, [rbp+90h+SRWLock]
0x18000b69b  mov     [rsp+1C0h+var_190], rax
0x18000b6a0  lea     rax, [rbp+90h+var_E8]
0x18000b6a4  mov     [rsp+1C0h+var_198], rax
0x18000b6a9  lea     rax, [rbp+90h+var_100]
0x18000b6ad  mov     [rsp+1C0h+var_1A0], rax
0x18000b6b2  lea     rdx, byte_1800174D9
0x18000b6b9  mov     rcx, r9
0x18000b6bc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@454564563@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<8> const &)
0x18000b6c1  jmp     loc_18000B7B4
0x18000b6c6  lea     rdx, [rbp+90h+var_100]
0x18000b6ca  call    ?LockExclusive@?$ActivityBase@VSsdmTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SsdmTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b6cf  mov     rax, [rbx+110h]
0x18000b6d6  mov     dword ptr [rax], 2
0x18000b6dc  mov     rcx, [rbp+90h+var_100]; SRWLock
0x18000b6e0  test    rcx, rcx
0x18000b6e3  jz      short loc_18000B6EB
0x18000b6e5  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b6eb  call    ?Instance@SsdmTelemetryProvider@@KAPEAV1@XZ; SsdmTelemetryProvider::Instance(void)
0x18000b6f0  mov     rdi, [rax+8]
0x18000b6f4  mov     eax, [rdi]
0x18000b6f6  cmp     eax, 5
0x18000b6f9  jbe     loc_18000B7B4
0x18000b6ff  mov     rdx, [rdi+18h]
0x18000b703  mov     rax, [rdi+10h]
0x18000b707  mov     rcx, 200000000000h
0x18000b711  test    rcx, rax
0x18000b714  jz      loc_18000B7B4
0x18000b71a  mov     rax, rdx
0x18000b71d  and     rax, rcx
0x18000b720  cmp     rax, rdx
0x18000b723  jnz     loc_18000B7B4
0x18000b729  mov     [rbp+90h+var_100], rsi
0x18000b72d  call    cs:__imp_GetCurrentThreadId
0x18000b733  mov     dword ptr [rbp+90h+SRWLock], eax
0x18000b736  mov     r8, [rbx+110h]
0x18000b73d  mov     eax, [r8+48h]
0x18000b741  mov     [rbp+90h+var_110], eax
0x18000b744  mov     [rbp+90h+var_E8], 0
0x18000b74c  lea     rax, [rbp+90h+var_100]
0x18000b750  mov     [rbp+90h+var_40], rax
0x18000b754  mov     [rbp+90h+var_38], 8
0x18000b75c  lea     rax, [rbp+90h+SRWLock]
0x18000b760  mov     [rbp+90h+var_50], rax
0x18000b764  mov     [rbp+90h+var_48], 4
0x18000b76c  lea     rax, [rbp+90h+var_110]
0x18000b770  mov     [rbp+90h+var_60], rax
0x18000b774  mov     [rbp+90h+var_58], 4
0x18000b77c  lea     rax, [rbp+90h+var_E8]
0x18000b780  mov     [rbp+90h+var_70], rax
0x18000b784  mov     [rbp+90h+var_68], 8
0x18000b78c  add     r8, 8
0x18000b790  lea     rax, [rbp+90h+var_90]
0x18000b794  mov     [rsp+1C0h+var_198], rax
0x18000b799  mov     dword ptr [rsp+1C0h+var_1A0], 6
0x18000b7a1  xor     r9d, r9d
0x18000b7a4  lea     rdx, byte_180017625
0x18000b7ab  mov     rcx, rdi
0x18000b7ae  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b7b3  nop
0x18000b7b4  cmp     dword ptr [rbx+138h], 0
0x18000b7bb  jz      short loc_18000B81E
0x18000b7bd  add     rbx, 120h
0x18000b7c4  call    cs:__imp_GetCurrentThreadId
0x18000b7ca  cmp     [rbx+18h], eax
0x18000b7cd  jz      short loc_18000B7EE
0x18000b7cf  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000b7d6  test    rax, rax
0x18000b7d9  jz      short loc_18000B7EE
0x18000b7db  mov     rdx, [rbp+98h]
0x18000b7e2  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000b7e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7ee  mov     dword ptr [rbx+18h], 0
0x18000b7f5  mov     rcx, [rbx]
0x18000b7f8  jmp     short loc_18000B806
0x18000b7fa  cmp     rax, rbx
0x18000b7fd  jz      short loc_18000B810
0x18000b7ff  lea     rcx, [rax+10h]
0x18000b803  mov     [rbx], rcx
0x18000b806  mov     rax, [rcx]
0x18000b809  test    rax, rax
0x18000b80c  jnz     short loc_18000B7FA
0x18000b80e  jmp     short loc_18000B817
0x18000b810  mov     rax, [rbx+10h]
0x18000b814  mov     [rcx], rax
0x18000b817  mov     qword ptr [rbx], 0
0x18000b81e  mov     rcx, [rbp+90h+var_30]
0x18000b822  xor     rcx, rsp; StackCookie
0x18000b825  call    __security_check_cookie
0x18000b82a  add     rsp, 1A8h
0x18000b831  pop     rdi
0x18000b832  pop     rsi
0x18000b833  pop     rbx
0x18000b834  pop     rbp
0x18000b835  retn
```
