# ComputeService::Diagnostics::TraceProvider::SocketTransport_Disconnect::Stop<SocketTransport *,bool &>(SocketTransport * &&,bool &)

- ea: `0x14005e870`
- end: `0x14005ec06`
- name: `??$Stop@PEAVSocketTransport@@AEA_N@SocketTransport_Disconnect@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEAVSocketTransport@@AEA_N@Z`
- size: `918`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140060480`

## callees

- `0x1400016ec`
- `0x140001c0c`
- `0x140005360`
- `0x14000aeec`
- `0x140031be8`
- `0x14003407c`
- `0x14005e870`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005e8f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005eaea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005e8f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005eaea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005eb35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005eb35`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ComputeService::Diagnostics::TraceProvider::SocketTransport_Disconnect::Stop<SocketTransport *,bool &>(
        __int64 a1,
        __int64 *a2,
        _BYTE *a3)
{
  __int64 v6; // rdi
  int v7; // eax
  int *v8; // rdi
  __int64 v9; // r9
  __int64 v10; // rdi
  __int64 v11; // r8
  __int64 v12; // [rsp+D0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+D8h] [rbp-78h] BYREF
  int v14; // [rsp+E0h] [rbp-70h] BYREF
  int v15; // [rsp+E4h] [rbp-6Ch] BYREF
  int v16; // [rsp+E8h] [rbp-68h] BYREF
  int v17; // [rsp+ECh] [rbp-64h] BYREF
  int v18; // [rsp+F0h] [rbp-60h] BYREF
  int v19; // [rsp+F4h] [rbp-5Ch] BYREF
  int v20; // [rsp+F8h] [rbp-58h] BYREF
  __int64 v21; // [rsp+100h] [rbp-50h] BYREF
  __int64 v22; // [rsp+108h] [rbp-48h] BYREF
  __int64 v23; // [rsp+110h] [rbp-40h] BYREF
  __int64 v24; // [rsp+118h] [rbp-38h] BYREF
  __int64 v25; // [rsp+120h] [rbp-30h] BYREF
  __int64 v26; // [rsp+128h] [rbp-28h] BYREF
  __int64 v27; // [rsp+130h] [rbp-20h] BYREF
  __int64 v28; // [rsp+138h] [rbp-18h] BYREF
  __int64 v29; // [rsp+140h] [rbp-10h] BYREF
  __int64 v30; // [rsp+148h] [rbp-8h] BYREF
  __int64 v31; // [rsp+150h] [rbp+0h] BYREF
  __int64 v32; // [rsp+158h] [rbp+8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+160h] [rbp+10h] BYREF
  __int64 *v34; // [rsp+180h] [rbp+30h]
  __int64 v35; // [rsp+188h] [rbp+38h]
  int *v36; // [rsp+190h] [rbp+40h]
  __int64 v37; // [rsp+198h] [rbp+48h]
  PSRWLOCK *p_SRWLock; // [rsp+1A0h] [rbp+50h]
  __int64 v39; // [rsp+1A8h] [rbp+58h]
  __int64 *v40; // [rsp+1B0h] [rbp+60h]
  __int64 v41; // [rsp+1B8h] [rbp+68h]
  __int64 *v42; // [rsp+1C0h] [rbp+70h]
  __int64 v43; // [rsp+1C8h] [rbp+78h]

  v6 = *(_QWORD *)(a1 + 272);
  v7 = *(_DWORD *)(v6 + 72);
  if ( v7 < 0 && (v8 = (int *)(v6 + 80), v7 == v8[2]) && v8 )
  {
    SRWLock = 0;
    wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &SRWLock);
    **(_DWORD **)(a1 + 272) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v9 = *((_QWORD *)ComputeService::Diagnostics::TraceProvider::Instance() + 1);
    if ( *(_DWORD *)v9 > 4u
      && (*(_QWORD *)(v9 + 16) & 0x100LL) != 0
      && (*(_QWORD *)(v9 + 24) & 0x100LL) == *(_QWORD *)(v9 + 24) )
    {
      LOBYTE(v12) = *a3;
      v23 = *a2;
      v24 = *((_QWORD *)v8 + 6);
      v15 = v8[17];
      v16 = v8[4];
      v25 = *((_QWORD *)v8 + 15);
      v26 = *((_QWORD *)v8 + 14);
      v17 = v8[26];
      v27 = *((_QWORD *)v8 + 12);
      v28 = *((_QWORD *)v8 + 11);
      v18 = v8[20];
      v29 = *((_QWORD *)v8 + 9);
      v19 = v8[8];
      v30 = *((_QWORD *)v8 + 3);
      v20 = *v8;
      v31 = *((_QWORD *)v8 + 16);
      v14 = v8[16];
      v32 = *((_QWORD *)v8 + 7);
      LODWORD(SRWLock) = v8[2];
      v21 = 0x1000000;
      v22 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>>(
        v9,
        (int)&byte_140134F9D,
        *(_QWORD *)(a1 + 272) + 8,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&SRWLock,
        (__int64)&v32,
        (__int64)&v14,
        (__int64)&v31,
        (__int64)&v20,
        (__int64)&v30,
        (__int64)&v19,
        (__int64)&v29,
        (__int64)&v18,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v12);
    }
  }
  else
  {
    SRWLock = 0;
    wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &SRWLock);
    **(_DWORD **)(a1 + 272) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v10 = *((_QWORD *)ComputeService::Diagnostics::TraceProvider::Instance() + 1);
    if ( *(_DWORD *)v10 > 4u
      && (*(_QWORD *)(v10 + 16) & 0x100LL) != 0
      && (*(_QWORD *)(v10 + 24) & 0x100LL) == *(_QWORD *)(v10 + 24) )
    {
      LOBYTE(v12) = *a3;
      v22 = *a2;
      LODWORD(SRWLock) = GetCurrentThreadId();
      v11 = *(_QWORD *)(a1 + 272);
      v14 = *(_DWORD *)(v11 + 72);
      v21 = 0;
      v42 = &v12;
      v43 = 1;
      v40 = &v22;
      v41 = 8;
      p_SRWLock = &SRWLock;
      v39 = 4;
      v36 = &v14;
      v37 = 4;
      v34 = &v21;
      v35 = 8;
      tlgWriteTransfer_EventWriteTransfer(v10, (unsigned __int8 *)&byte_1401356F1, (const GUID *)(v11 + 8), 0, 7u, &v33);
    }
  }
  if ( *(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x14005e870  mov     [rsp-8+arg_8], rbx
0x14005e875  mov     [rsp-8+arg_10], rsi
0x14005e87a  push    rbp
0x14005e87b  push    rdi
0x14005e87c  push    r14
0x14005e87e  lea     rbp, [rsp-90h]
0x14005e886  sub     rsp, 1E0h
0x14005e88d  mov     rax, cs:__security_cookie
0x14005e894  xor     rax, rsp
0x14005e897  mov     [rbp+0A0h+var_20], rax
0x14005e89e  mov     rsi, r8
0x14005e8a1  mov     r14, rdx
0x14005e8a4  mov     rbx, rcx
0x14005e8a7  mov     rdi, [rcx+110h]
0x14005e8ae  mov     eax, [rdi+48h]
0x14005e8b1  test    eax, eax
0x14005e8b3  jns     loc_14005EAC3
0x14005e8b9  add     rdi, 50h ; 'P'
0x14005e8bd  cmp     eax, [rdi+8]
0x14005e8c0  jnz     loc_14005EAC3
0x14005e8c6  test    rdi, rdi
0x14005e8c9  jz      loc_14005EAC3
0x14005e8cf  mov     [rbp+0A0h+SRWLock], 0
0x14005e8d7  lea     rdx, [rbp+0A0h+SRWLock]
0x14005e8db  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14005e8e0  mov     rax, [rbx+110h]
0x14005e8e7  mov     dword ptr [rax], 2
0x14005e8ed  mov     rcx, [rbp+0A0h+SRWLock]; SRWLock
0x14005e8f1  test    rcx, rcx
0x14005e8f4  jz      short loc_14005E8FC
0x14005e8f6  call    cs:__imp_ReleaseSRWLockExclusive
0x14005e8fc  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x14005e901  mov     r9, [rax+8]
0x14005e905  mov     eax, [r9]
0x14005e908  cmp     eax, 4
0x14005e90b  jbe     loc_14005EBCC
0x14005e911  mov     rdx, [r9+18h]
0x14005e915  mov     rax, [r9+10h]
0x14005e919  mov     ecx, 100h
0x14005e91e  test    rcx, rax
0x14005e921  jz      loc_14005EBCC
0x14005e927  mov     rax, rdx
0x14005e92a  and     rax, rcx
0x14005e92d  cmp     rax, rdx
0x14005e930  jnz     loc_14005EBCC
0x14005e936  mov     al, [rsi]
0x14005e938  mov     byte ptr [rbp+0A0h+var_120], al
0x14005e93b  mov     rax, [r14]
0x14005e93e  mov     [rbp+0A0h+var_E0], rax
0x14005e942  mov     rax, [rdi+30h]
0x14005e946  mov     [rbp+0A0h+var_D8], rax
0x14005e94a  mov     eax, [rdi+44h]
0x14005e94d  mov     dword ptr [rbp+0A0h+var_110+4], eax
0x14005e950  mov     eax, [rdi+10h]
0x14005e953  mov     dword ptr [rbp+0A0h+var_108], eax
0x14005e956  mov     rax, [rdi+78h]
0x14005e95a  mov     [rbp+0A0h+var_D0], rax
0x14005e95e  mov     rax, [rdi+70h]
0x14005e962  mov     [rbp+0A0h+var_C8], rax
0x14005e966  mov     eax, [rdi+68h]
0x14005e969  mov     dword ptr [rbp+0A0h+var_108+4], eax
0x14005e96c  mov     rax, [rdi+60h]
0x14005e970  mov     [rbp+0A0h+var_C0], rax
0x14005e974  mov     rax, [rdi+58h]
0x14005e978  mov     [rbp+0A0h+var_B8], rax
0x14005e97c  mov     eax, [rdi+50h]
0x14005e97f  mov     dword ptr [rbp+0A0h+var_100], eax
0x14005e982  mov     rax, [rdi+48h]
0x14005e986  mov     [rbp+0A0h+var_B0], rax
0x14005e98a  mov     eax, [rdi+20h]
0x14005e98d  mov     dword ptr [rbp+0A0h+var_100+4], eax
0x14005e990  mov     rax, [rdi+18h]
0x14005e994  mov     [rbp+0A0h+var_A8], rax
0x14005e998  mov     eax, [rdi]
0x14005e99a  mov     [rbp+0A0h+var_F8], eax
0x14005e99d  mov     rax, [rdi+80h]
0x14005e9a4  mov     [rbp+0A0h+var_A0], rax
0x14005e9a8  mov     eax, [rdi+40h]
0x14005e9ab  mov     dword ptr [rbp+0A0h+var_110], eax
0x14005e9ae  mov     rax, [rdi+38h]
0x14005e9b2  mov     [rbp+0A0h+var_98], rax
0x14005e9b6  mov     eax, [rdi+8]
0x14005e9b9  mov     dword ptr [rbp+0A0h+SRWLock], eax
0x14005e9bc  mov     [rbp+0A0h+var_F0], 1000000h
0x14005e9c4  mov     [rbp+0A0h+var_E8], 0
0x14005e9cc  mov     r8, [rbx+110h]
0x14005e9d3  add     r8, 8; int
0x14005e9d7  lea     rax, [rbp+0A0h+var_120]
0x14005e9db  mov     [rsp+1F0h+var_130], rax; __int64
0x14005e9e3  lea     rax, [rbp+0A0h+var_E0]
0x14005e9e7  mov     [rsp+1F0h+var_138], rax; __int64
0x14005e9ef  lea     rax, [rbp+0A0h+var_D8]
0x14005e9f3  mov     [rsp+1F0h+var_140], rax; __int64
0x14005e9fb  lea     rax, [rbp+0A0h+var_110+4]
0x14005e9ff  mov     [rsp+1F0h+var_148], rax; __int64
0x14005ea07  lea     rax, [rbp+0A0h+var_108]
0x14005ea0b  mov     [rsp+1F0h+var_150], rax; __int64
0x14005ea13  lea     rax, [rbp+0A0h+var_D0]
0x14005ea17  mov     [rsp+1F0h+var_158], rax; __int64
0x14005ea1f  lea     rax, [rbp+0A0h+var_C8]
0x14005ea23  mov     [rsp+1F0h+var_160], rax; __int64
0x14005ea2b  lea     rax, [rbp+0A0h+var_108+4]
0x14005ea2f  mov     [rsp+1F0h+var_168], rax; __int64
0x14005ea37  lea     rax, [rbp+0A0h+var_C0]
0x14005ea3b  mov     [rsp+1F0h+var_170], rax; __int64
0x14005ea43  lea     rax, [rbp+0A0h+var_B8]
0x14005ea47  mov     [rsp+1F0h+var_178], rax; __int64
0x14005ea4c  lea     rax, [rbp+0A0h+var_100]
0x14005ea50  mov     [rsp+1F0h+var_180], rax; __int64
0x14005ea55  lea     rax, [rbp+0A0h+var_B0]
0x14005ea59  mov     [rsp+1F0h+var_188], rax; __int64
0x14005ea5e  lea     rax, [rbp+0A0h+var_100+4]
0x14005ea62  mov     [rsp+1F0h+var_190], rax; __int64
0x14005ea67  lea     rax, [rbp+0A0h+var_A8]
0x14005ea6b  mov     [rsp+1F0h+var_198], rax; __int64
0x14005ea70  lea     rax, [rbp+0A0h+var_F8]
0x14005ea74  mov     [rsp+1F0h+var_1A0], rax; __int64
0x14005ea79  lea     rax, [rbp+0A0h+var_A0]
0x14005ea7d  mov     [rsp+1F0h+var_1A8], rax; __int64
0x14005ea82  lea     rax, [rbp+0A0h+var_110]
0x14005ea86  mov     [rsp+1F0h+var_1B0], rax; __int64
0x14005ea8b  lea     rax, [rbp+0A0h+var_98]
0x14005ea8f  mov     [rsp+1F0h+var_1B8], rax; __int64
0x14005ea94  lea     rax, [rbp+0A0h+SRWLock]
0x14005ea98  mov     [rsp+1F0h+var_1C0], rax; __int64
0x14005ea9d  lea     rax, [rbp+0A0h+var_F0]
0x14005eaa1  mov     [rsp+1F0h+var_1C8], rax; __int64
0x14005eaa6  lea     rax, [rbp+0A0h+var_E8]
0x14005eaaa  mov     qword ptr [rsp+1F0h+var_1D0], rax; __int64
0x14005eaaf  lea     rdx, byte_140134F9D; int
0x14005eab6  mov     rcx, r9; int
0x14005eab9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U1@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564453AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &)
0x14005eabe  jmp     loc_14005EBCC
0x14005eac3  mov     [rbp+0A0h+SRWLock], 0
0x14005eacb  lea     rdx, [rbp+0A0h+SRWLock]
0x14005eacf  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14005ead4  mov     rax, [rbx+110h]
0x14005eadb  mov     dword ptr [rax], 2
0x14005eae1  mov     rcx, [rbp+0A0h+SRWLock]; SRWLock
0x14005eae5  test    rcx, rcx
0x14005eae8  jz      short loc_14005EAF0
0x14005eaea  call    cs:__imp_ReleaseSRWLockExclusive
0x14005eaf0  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x14005eaf5  mov     rdi, [rax+8]
0x14005eaf9  mov     eax, [rdi]
0x14005eafb  cmp     eax, 4
0x14005eafe  jbe     loc_14005EBCC
0x14005eb04  mov     rdx, [rdi+18h]
0x14005eb08  mov     rax, [rdi+10h]
0x14005eb0c  mov     ecx, 100h
0x14005eb11  test    rcx, rax
0x14005eb14  jz      loc_14005EBCC
0x14005eb1a  mov     rax, rdx
0x14005eb1d  and     rax, rcx
0x14005eb20  cmp     rax, rdx
0x14005eb23  jnz     loc_14005EBCC
0x14005eb29  mov     al, [rsi]
0x14005eb2b  mov     byte ptr [rbp+0A0h+var_120], al
0x14005eb2e  mov     rax, [r14]
0x14005eb31  mov     [rbp+0A0h+var_E8], rax
0x14005eb35  call    cs:__imp_GetCurrentThreadId
0x14005eb3b  mov     dword ptr [rbp+0A0h+SRWLock], eax
0x14005eb3e  mov     r8, [rbx+110h]
0x14005eb45  mov     eax, [r8+48h]
0x14005eb49  mov     dword ptr [rbp+0A0h+var_110], eax
0x14005eb4c  mov     [rbp+0A0h+var_F0], 0
0x14005eb54  lea     rax, [rbp+0A0h+var_120]
0x14005eb58  mov     [rbp+0A0h+var_30], rax
0x14005eb5c  mov     [rbp+0A0h+var_28], 1
0x14005eb64  lea     rax, [rbp+0A0h+var_E8]
0x14005eb68  mov     [rbp+0A0h+var_40], rax
0x14005eb6c  mov     [rbp+0A0h+var_38], 8
0x14005eb74  lea     rax, [rbp+0A0h+SRWLock]
0x14005eb78  mov     [rbp+0A0h+var_50], rax
0x14005eb7c  mov     [rbp+0A0h+var_48], 4
0x14005eb84  lea     rax, [rbp+0A0h+var_110]
0x14005eb88  mov     [rbp+0A0h+var_60], rax
0x14005eb8c  mov     [rbp+0A0h+var_58], 4
0x14005eb94  lea     rax, [rbp+0A0h+var_F0]
0x14005eb98  mov     [rbp+0A0h+var_70], rax
0x14005eb9c  mov     [rbp+0A0h+var_68], 8
0x14005eba4  add     r8, 8; int
0x14005eba8  lea     rax, [rbp+0A0h+var_90]
0x14005ebac  mov     [rsp+1F0h+var_1C8], rax; PEVENT_DATA_DESCRIPTOR
0x14005ebb1  mov     [rsp+1F0h+var_1D0], 7; ULONG
0x14005ebb9  xor     r9d, r9d; int
0x14005ebbc  lea     rdx, byte_1401356F1; int
0x14005ebc3  mov     rcx, rdi; int
0x14005ebc6  call    _tlgWriteTransfer_EventWriteTransfer
0x14005ebcb  nop
0x14005ebcc  lea     rcx, [rbx+120h]; this
0x14005ebd3  cmp     dword ptr [rcx+18h], 0
0x14005ebd7  jz      short loc_14005EBDF
0x14005ebd9  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14005ebde  nop
0x14005ebdf  mov     rcx, [rbp+0A0h+var_20]
0x14005ebe6  xor     rcx, rsp; StackCookie
0x14005ebe9  call    __security_check_cookie
0x14005ebee  lea     r11, [rsp+1F0h+var_10]
0x14005ebf6  mov     rbx, [r11+28h]
0x14005ebfa  mov     rsi, [r11+30h]
0x14005ebfe  mov     rsp, r11
0x14005ec01  pop     r14
0x14005ec03  pop     rdi
0x14005ec04  pop     rbp
0x14005ec05  retn
```
