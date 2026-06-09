# ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::Stop<ulong &,ulong &>(ulong &,ulong &)

- ea: `0x14005e200`
- end: `0x14005e532`
- name: `??$Stop@AEAKAEAK@SocketTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@QEAAXAEAK0@Z`
- size: `818`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x14005f774`
- `0x14005f8f0`

## callees

- `0x140001f4c`
- `0x140002410`
- `0x14000aeec`
- `0x140031be8`
- `0x14003407c`
- `0x14005e200`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005e272`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005e465`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005e272`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005e465`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005e4a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005e4a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::Stop<unsigned long &,unsigned long &>(
        __int64 a1,
        int *a2,
        int *a3)
{
  __int64 v6; // rdi
  int v7; // eax
  __int64 v8; // rdi
  __int64 v9; // r9
  __int64 v10; // rdi
  __int64 v11; // r8
  int v12; // r9d
  PSRWLOCK SRWLock; // [rsp+D0h] [rbp-80h] BYREF
  int v14; // [rsp+D8h] [rbp-78h] BYREF
  DWORD CurrentThreadId; // [rsp+DCh] [rbp-74h] BYREF
  int v16; // [rsp+E0h] [rbp-70h] BYREF
  int v17; // [rsp+E4h] [rbp-6Ch] BYREF
  int v18; // [rsp+E8h] [rbp-68h] BYREF
  int v19; // [rsp+ECh] [rbp-64h] BYREF
  int v20; // [rsp+F0h] [rbp-60h] BYREF
  int v21; // [rsp+F4h] [rbp-5Ch] BYREF
  int v22; // [rsp+F8h] [rbp-58h] BYREF
  __int64 v23; // [rsp+100h] [rbp-50h] BYREF
  __int64 v24; // [rsp+108h] [rbp-48h] BYREF
  __int64 v25; // [rsp+110h] [rbp-40h] BYREF
  __int64 v26; // [rsp+118h] [rbp-38h] BYREF
  __int64 v27; // [rsp+120h] [rbp-30h] BYREF
  __int64 v28; // [rsp+128h] [rbp-28h] BYREF
  __int64 v29; // [rsp+130h] [rbp-20h] BYREF
  __int64 v30; // [rsp+138h] [rbp-18h] BYREF
  __int64 v31; // [rsp+140h] [rbp-10h] BYREF
  __int64 v32; // [rsp+148h] [rbp-8h] BYREF
  __int64 v33; // [rsp+150h] [rbp+0h] BYREF

  v6 = *(_QWORD *)(a1 + 272);
  v7 = *(_DWORD *)(v6 + 72);
  if ( v7 < 0 && (v8 = v6 + 80, v7 == *(_DWORD *)(v8 + 8)) && v8 )
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
      && (*(_QWORD *)(v9 + 16) & 0x200LL) != 0
      && (*(_QWORD *)(v9 + 24) & 0x200LL) == *(_QWORD *)(v9 + 24) )
    {
      v17 = *a3;
      v18 = *a2;
      v24 = *(_QWORD *)(v8 + 48);
      v19 = *(_DWORD *)(v8 + 68);
      v20 = *(_DWORD *)(v8 + 16);
      v25 = *(_QWORD *)(v8 + 120);
      v26 = *(_QWORD *)(v8 + 112);
      v21 = *(_DWORD *)(v8 + 104);
      v27 = *(_QWORD *)(v8 + 96);
      v28 = *(_QWORD *)(v8 + 88);
      v22 = *(_DWORD *)(v8 + 80);
      v29 = *(_QWORD *)(v8 + 72);
      v14 = *(_DWORD *)(v8 + 32);
      v30 = *(_QWORD *)(v8 + 24);
      CurrentThreadId = *(_DWORD *)v8;
      v31 = *(_QWORD *)(v8 + 128);
      v16 = *(_DWORD *)(v8 + 64);
      v32 = *(_QWORD *)(v8 + 56);
      LODWORD(SRWLock) = *(_DWORD *)(v8 + 8);
      v33 = 0x1000000;
      v23 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (int)&byte_140135837,
        *(_QWORD *)(a1 + 272) + 8,
        (__int64)&v23,
        (__int64)&v33,
        (__int64)&SRWLock,
        (__int64)&v32,
        (__int64)&v16,
        (__int64)&v31,
        (__int64)&CurrentThreadId,
        (__int64)&v30,
        (__int64)&v14,
        (__int64)&v29,
        (__int64)&v22,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v21,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v24,
        (__int64)&v18,
        (__int64)&v17);
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
      && (*(_QWORD *)(v10 + 16) & 0x200LL) != 0
      && (*(_QWORD *)(v10 + 24) & 0x200LL) == *(_QWORD *)(v10 + 24) )
    {
      LODWORD(SRWLock) = *a3;
      v16 = *a2;
      CurrentThreadId = GetCurrentThreadId();
      v11 = *(_QWORD *)(a1 + 272);
      v14 = *(_DWORD *)(v11 + 72);
      v23 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)byte_14013576D,
        v11 + 8,
        v12,
        (__int64)&v23,
        (__int64)&v14,
        (__int64)&CurrentThreadId,
        (__int64)&v16,
        (__int64)&SRWLock);
    }
  }
  if ( *(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x14005e200  mov     [rsp-8+arg_8], rbx
0x14005e205  mov     [rsp-8+arg_10], rsi
0x14005e20a  push    rbp
0x14005e20b  push    rdi
0x14005e20c  push    r14
0x14005e20e  lea     rbp, [rsp-10h]
0x14005e213  sub     rsp, 160h
0x14005e21a  mov     rsi, r8
0x14005e21d  mov     r14, rdx
0x14005e220  mov     rbx, rcx
0x14005e223  mov     rdi, [rcx+110h]
0x14005e22a  mov     eax, [rdi+48h]
0x14005e22d  test    eax, eax
0x14005e22f  jns     loc_14005E43E
0x14005e235  add     rdi, 50h ; 'P'
0x14005e239  cmp     eax, [rdi+8]
0x14005e23c  jnz     loc_14005E43E
0x14005e242  test    rdi, rdi
0x14005e245  jz      loc_14005E43E
0x14005e24b  mov     [rbp+20h+SRWLock], 0
0x14005e253  lea     rdx, [rbp+20h+SRWLock]
0x14005e257  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14005e25c  mov     rax, [rbx+110h]
0x14005e263  mov     dword ptr [rax], 2
0x14005e269  mov     rcx, [rbp+20h+SRWLock]; SRWLock
0x14005e26d  test    rcx, rcx
0x14005e270  jz      short loc_14005E278
0x14005e272  call    cs:__imp_ReleaseSRWLockExclusive
0x14005e278  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x14005e27d  mov     r9, [rax+8]
0x14005e281  mov     eax, [r9]
0x14005e284  cmp     eax, 4
0x14005e287  jbe     loc_14005E507
0x14005e28d  mov     rdx, [r9+18h]
0x14005e291  mov     rax, [r9+10h]
0x14005e295  mov     ecx, 200h
0x14005e29a  test    rcx, rax
0x14005e29d  jz      loc_14005E507
0x14005e2a3  mov     rax, rdx
0x14005e2a6  and     rax, rcx
0x14005e2a9  cmp     rax, rdx
0x14005e2ac  jnz     loc_14005E507
0x14005e2b2  mov     eax, [rsi]
0x14005e2b4  mov     dword ptr [rbp+20h+var_90+4], eax
0x14005e2b7  mov     eax, [r14]
0x14005e2ba  mov     dword ptr [rbp+20h+var_88], eax
0x14005e2bd  mov     rax, [rdi+30h]
0x14005e2c1  mov     [rbp+20h+var_68], rax
0x14005e2c5  mov     eax, [rdi+44h]
0x14005e2c8  mov     dword ptr [rbp+20h+var_88+4], eax
0x14005e2cb  mov     eax, [rdi+10h]
0x14005e2ce  mov     [rbp+20h+var_80], eax
0x14005e2d1  mov     rax, [rdi+78h]
0x14005e2d5  mov     [rbp+20h+var_60], rax
0x14005e2d9  mov     rax, [rdi+70h]
0x14005e2dd  mov     [rbp+20h+var_58], rax
0x14005e2e1  mov     eax, [rdi+68h]
0x14005e2e4  mov     [rbp+20h+var_7C], eax
0x14005e2e7  mov     rax, [rdi+60h]
0x14005e2eb  mov     [rbp+20h+var_50], rax
0x14005e2ef  mov     rax, [rdi+58h]
0x14005e2f3  mov     [rbp+20h+var_48], rax
0x14005e2f7  mov     eax, [rdi+50h]
0x14005e2fa  mov     [rbp+20h+var_78], eax
0x14005e2fd  mov     rax, [rdi+48h]
0x14005e301  mov     [rbp+20h+var_40], rax
0x14005e305  mov     eax, [rdi+20h]
0x14005e308  mov     dword ptr [rbp+20h+var_98], eax
0x14005e30b  mov     rax, [rdi+18h]
0x14005e30f  mov     [rbp+20h+var_38], rax
0x14005e313  mov     eax, [rdi]
0x14005e315  mov     dword ptr [rbp+20h+var_98+4], eax
0x14005e318  mov     rax, [rdi+80h]
0x14005e31f  mov     [rbp+20h+var_30], rax
0x14005e323  mov     eax, [rdi+40h]
0x14005e326  mov     dword ptr [rbp+20h+var_90], eax
0x14005e329  mov     rax, [rdi+38h]
0x14005e32d  mov     [rbp+20h+var_28], rax
0x14005e331  mov     eax, [rdi+8]
0x14005e334  mov     dword ptr [rbp+20h+SRWLock], eax
0x14005e337  mov     [rbp+20h+var_20], 1000000h
0x14005e33f  mov     [rbp+20h+var_70], 0
0x14005e347  mov     r8, [rbx+110h]
0x14005e34e  add     r8, 8; int
0x14005e352  lea     rax, [rbp+20h+var_90+4]
0x14005e356  mov     [rsp+170h+var_B0], rax; __int64
0x14005e35e  lea     rax, [rbp+20h+var_88]
0x14005e362  mov     [rsp+170h+var_B8], rax; __int64
0x14005e36a  lea     rax, [rbp+20h+var_68]
0x14005e36e  mov     [rsp+170h+var_C0], rax; __int64
0x14005e376  lea     rax, [rbp+20h+var_88+4]
0x14005e37a  mov     [rsp+170h+var_C8], rax; __int64
0x14005e382  lea     rax, [rbp+20h+var_80]
0x14005e386  mov     [rsp+170h+var_D0], rax; __int64
0x14005e38e  lea     rax, [rbp+20h+var_60]
0x14005e392  mov     [rsp+170h+var_D8], rax; __int64
0x14005e39a  lea     rax, [rbp+20h+var_58]
0x14005e39e  mov     [rsp+170h+var_E0], rax; __int64
0x14005e3a6  lea     rax, [rbp+20h+var_7C]
0x14005e3aa  mov     [rsp+170h+var_E8], rax; __int64
0x14005e3b2  lea     rax, [rbp+20h+var_50]
0x14005e3b6  mov     [rsp+170h+var_F0], rax; __int64
0x14005e3be  lea     rax, [rbp+20h+var_48]
0x14005e3c2  mov     [rsp+170h+var_F8], rax; __int64
0x14005e3c7  lea     rax, [rbp+20h+var_78]
0x14005e3cb  mov     [rsp+170h+var_100], rax; __int64
0x14005e3d0  lea     rax, [rbp+20h+var_40]
0x14005e3d4  mov     [rsp+170h+var_108], rax; __int64
0x14005e3d9  lea     rax, [rbp+20h+var_98]
0x14005e3dd  mov     [rsp+170h+var_110], rax; __int64
0x14005e3e2  lea     rax, [rbp+20h+var_38]
0x14005e3e6  mov     [rsp+170h+var_118], rax; __int64
0x14005e3eb  lea     rax, [rbp+20h+var_98+4]
0x14005e3ef  mov     [rsp+170h+var_120], rax; __int64
0x14005e3f4  lea     rax, [rbp+20h+var_30]
0x14005e3f8  mov     [rsp+170h+var_128], rax; __int64
0x14005e3fd  lea     rax, [rbp+20h+var_90]
0x14005e401  mov     [rsp+170h+var_130], rax; __int64
0x14005e406  lea     rax, [rbp+20h+var_28]
0x14005e40a  mov     [rsp+170h+var_138], rax; __int64
0x14005e40f  lea     rax, [rbp+20h+SRWLock]
0x14005e413  mov     [rsp+170h+var_140], rax; __int64
0x14005e418  lea     rax, [rbp+20h+var_20]
0x14005e41c  mov     [rsp+170h+var_148], rax; __int64
0x14005e421  lea     rax, [rbp+20h+var_70]
0x14005e425  mov     [rsp+170h+var_150], rax; __int64
0x14005e42a  lea     rdx, byte_140135837; int
0x14005e431  mov     rcx, r9; int
0x14005e434  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645644544@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14005e439  jmp     loc_14005E507
0x14005e43e  mov     [rbp+20h+SRWLock], 0
0x14005e446  lea     rdx, [rbp+20h+SRWLock]
0x14005e44a  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14005e44f  mov     rax, [rbx+110h]
0x14005e456  mov     dword ptr [rax], 2
0x14005e45c  mov     rcx, [rbp+20h+SRWLock]; SRWLock
0x14005e460  test    rcx, rcx
0x14005e463  jz      short loc_14005E46B
0x14005e465  call    cs:__imp_ReleaseSRWLockExclusive
0x14005e46b  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x14005e470  mov     rdi, [rax+8]
0x14005e474  mov     eax, [rdi]
0x14005e476  cmp     eax, 4
0x14005e479  jbe     loc_14005E507
0x14005e47f  mov     rdx, [rdi+18h]
0x14005e483  mov     rax, [rdi+10h]
0x14005e487  mov     ecx, 200h
0x14005e48c  test    rcx, rax
0x14005e48f  jz      short loc_14005E507
0x14005e491  mov     rax, rdx
0x14005e494  and     rax, rcx
0x14005e497  cmp     rax, rdx
0x14005e49a  jnz     short loc_14005E507
0x14005e49c  mov     eax, [rsi]
0x14005e49e  mov     dword ptr [rbp+20h+SRWLock], eax
0x14005e4a1  mov     eax, [r14]
0x14005e4a4  mov     dword ptr [rbp+20h+var_90], eax
0x14005e4a7  call    cs:__imp_GetCurrentThreadId
0x14005e4ad  mov     dword ptr [rbp+20h+var_98+4], eax
0x14005e4b0  mov     r8, [rbx+110h]
0x14005e4b7  mov     eax, [r8+48h]
0x14005e4bb  mov     dword ptr [rbp+20h+var_98], eax
0x14005e4be  mov     [rbp+20h+var_70], 0
0x14005e4c6  add     r8, 8
0x14005e4ca  lea     rax, [rbp+20h+SRWLock]
0x14005e4ce  mov     [rsp+170h+var_130], rax
0x14005e4d3  lea     rax, [rbp+20h+var_90]
0x14005e4d7  mov     [rsp+170h+var_138], rax
0x14005e4dc  lea     rax, [rbp+20h+var_98+4]
0x14005e4e0  mov     [rsp+170h+var_140], rax
0x14005e4e5  lea     rax, [rbp+20h+var_98]
0x14005e4e9  mov     [rsp+170h+var_148], rax
0x14005e4ee  lea     rax, [rbp+20h+var_70]
0x14005e4f2  mov     [rsp+170h+var_150], rax
0x14005e4f7  lea     rdx, byte_14013576D
0x14005e4fe  mov     rcx, rdi
0x14005e501  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14005e506  nop
0x14005e507  lea     rcx, [rbx+120h]; this
0x14005e50e  cmp     dword ptr [rcx+18h], 0
0x14005e512  jz      short loc_14005E51A
0x14005e514  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14005e519  nop
0x14005e51a  lea     r11, [rsp+170h+var_10]
0x14005e522  mov     rbx, [r11+28h]
0x14005e526  mov     rsi, [r11+30h]
0x14005e52a  mov     rsp, r11
0x14005e52d  pop     r14
0x14005e52f  pop     rdi
0x14005e530  pop     rbp
0x14005e531  retn
```
