# ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart::Stop<ulong &,ulong &>(ulong &,ulong &)

- ea: `0x1400f2d88`
- end: `0x1400f30ba`
- name: `??$Stop@AEAKAEAK@PipeTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@QEAAXAEAK0@Z`
- size: `818`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400f35c8`
- `0x1400f367c`

## callees

- `0x140001f4c`
- `0x140002410`
- `0x14000aeec`
- `0x140031be8`
- `0x14003407c`
- `0x1400f2d88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f2dfa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f2fed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f2dfa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f2fed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400f302f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400f302f`

## pseudocode

```c
void __fastcall ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart::Stop<unsigned long &,unsigned long &>(
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
        (int)&unk_14013C3D8,
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
        (unsigned int)byte_14013CB9D,
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
0x1400f2d88  mov     [rsp-8+arg_8], rbx
0x1400f2d8d  mov     [rsp-8+arg_10], rsi
0x1400f2d92  push    rbp
0x1400f2d93  push    rdi
0x1400f2d94  push    r14
0x1400f2d96  lea     rbp, [rsp-10h]
0x1400f2d9b  sub     rsp, 160h
0x1400f2da2  mov     rsi, r8
0x1400f2da5  mov     r14, rdx
0x1400f2da8  mov     rbx, rcx
0x1400f2dab  mov     rdi, [rcx+110h]
0x1400f2db2  mov     eax, [rdi+48h]
0x1400f2db5  test    eax, eax
0x1400f2db7  jns     loc_1400F2FC6
0x1400f2dbd  add     rdi, 50h ; 'P'
0x1400f2dc1  cmp     eax, [rdi+8]
0x1400f2dc4  jnz     loc_1400F2FC6
0x1400f2dca  test    rdi, rdi
0x1400f2dcd  jz      loc_1400F2FC6
0x1400f2dd3  mov     [rbp+20h+SRWLock], 0
0x1400f2ddb  lea     rdx, [rbp+20h+SRWLock]
0x1400f2ddf  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400f2de4  mov     rax, [rbx+110h]
0x1400f2deb  mov     dword ptr [rax], 2
0x1400f2df1  mov     rcx, [rbp+20h+SRWLock]; SRWLock
0x1400f2df5  test    rcx, rcx
0x1400f2df8  jz      short loc_1400F2E00
0x1400f2dfa  call    cs:__imp_ReleaseSRWLockExclusive
0x1400f2e00  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x1400f2e05  mov     r9, [rax+8]
0x1400f2e09  mov     eax, [r9]
0x1400f2e0c  cmp     eax, 4
0x1400f2e0f  jbe     loc_1400F308F
0x1400f2e15  mov     rdx, [r9+18h]
0x1400f2e19  mov     rax, [r9+10h]
0x1400f2e1d  mov     ecx, 200h
0x1400f2e22  test    rcx, rax
0x1400f2e25  jz      loc_1400F308F
0x1400f2e2b  mov     rax, rdx
0x1400f2e2e  and     rax, rcx
0x1400f2e31  cmp     rax, rdx
0x1400f2e34  jnz     loc_1400F308F
0x1400f2e3a  mov     eax, [rsi]
0x1400f2e3c  mov     dword ptr [rbp+20h+var_90+4], eax
0x1400f2e3f  mov     eax, [r14]
0x1400f2e42  mov     dword ptr [rbp+20h+var_88], eax
0x1400f2e45  mov     rax, [rdi+30h]
0x1400f2e49  mov     [rbp+20h+var_68], rax
0x1400f2e4d  mov     eax, [rdi+44h]
0x1400f2e50  mov     dword ptr [rbp+20h+var_88+4], eax
0x1400f2e53  mov     eax, [rdi+10h]
0x1400f2e56  mov     [rbp+20h+var_80], eax
0x1400f2e59  mov     rax, [rdi+78h]
0x1400f2e5d  mov     [rbp+20h+var_60], rax
0x1400f2e61  mov     rax, [rdi+70h]
0x1400f2e65  mov     [rbp+20h+var_58], rax
0x1400f2e69  mov     eax, [rdi+68h]
0x1400f2e6c  mov     [rbp+20h+var_7C], eax
0x1400f2e6f  mov     rax, [rdi+60h]
0x1400f2e73  mov     [rbp+20h+var_50], rax
0x1400f2e77  mov     rax, [rdi+58h]
0x1400f2e7b  mov     [rbp+20h+var_48], rax
0x1400f2e7f  mov     eax, [rdi+50h]
0x1400f2e82  mov     [rbp+20h+var_78], eax
0x1400f2e85  mov     rax, [rdi+48h]
0x1400f2e89  mov     [rbp+20h+var_40], rax
0x1400f2e8d  mov     eax, [rdi+20h]
0x1400f2e90  mov     dword ptr [rbp+20h+var_98], eax
0x1400f2e93  mov     rax, [rdi+18h]
0x1400f2e97  mov     [rbp+20h+var_38], rax
0x1400f2e9b  mov     eax, [rdi]
0x1400f2e9d  mov     dword ptr [rbp+20h+var_98+4], eax
0x1400f2ea0  mov     rax, [rdi+80h]
0x1400f2ea7  mov     [rbp+20h+var_30], rax
0x1400f2eab  mov     eax, [rdi+40h]
0x1400f2eae  mov     dword ptr [rbp+20h+var_90], eax
0x1400f2eb1  mov     rax, [rdi+38h]
0x1400f2eb5  mov     [rbp+20h+var_28], rax
0x1400f2eb9  mov     eax, [rdi+8]
0x1400f2ebc  mov     dword ptr [rbp+20h+SRWLock], eax
0x1400f2ebf  mov     [rbp+20h+var_20], 1000000h
0x1400f2ec7  mov     [rbp+20h+var_70], 0
0x1400f2ecf  mov     r8, [rbx+110h]
0x1400f2ed6  add     r8, 8; int
0x1400f2eda  lea     rax, [rbp+20h+var_90+4]
0x1400f2ede  mov     [rsp+170h+var_B0], rax; __int64
0x1400f2ee6  lea     rax, [rbp+20h+var_88]
0x1400f2eea  mov     [rsp+170h+var_B8], rax; __int64
0x1400f2ef2  lea     rax, [rbp+20h+var_68]
0x1400f2ef6  mov     [rsp+170h+var_C0], rax; __int64
0x1400f2efe  lea     rax, [rbp+20h+var_88+4]
0x1400f2f02  mov     [rsp+170h+var_C8], rax; __int64
0x1400f2f0a  lea     rax, [rbp+20h+var_80]
0x1400f2f0e  mov     [rsp+170h+var_D0], rax; __int64
0x1400f2f16  lea     rax, [rbp+20h+var_60]
0x1400f2f1a  mov     [rsp+170h+var_D8], rax; __int64
0x1400f2f22  lea     rax, [rbp+20h+var_58]
0x1400f2f26  mov     [rsp+170h+var_E0], rax; __int64
0x1400f2f2e  lea     rax, [rbp+20h+var_7C]
0x1400f2f32  mov     [rsp+170h+var_E8], rax; __int64
0x1400f2f3a  lea     rax, [rbp+20h+var_50]
0x1400f2f3e  mov     [rsp+170h+var_F0], rax; __int64
0x1400f2f46  lea     rax, [rbp+20h+var_48]
0x1400f2f4a  mov     [rsp+170h+var_F8], rax; __int64
0x1400f2f4f  lea     rax, [rbp+20h+var_78]
0x1400f2f53  mov     [rsp+170h+var_100], rax; __int64
0x1400f2f58  lea     rax, [rbp+20h+var_40]
0x1400f2f5c  mov     [rsp+170h+var_108], rax; __int64
0x1400f2f61  lea     rax, [rbp+20h+var_98]
0x1400f2f65  mov     [rsp+170h+var_110], rax; __int64
0x1400f2f6a  lea     rax, [rbp+20h+var_38]
0x1400f2f6e  mov     [rsp+170h+var_118], rax; __int64
0x1400f2f73  lea     rax, [rbp+20h+var_98+4]
0x1400f2f77  mov     [rsp+170h+var_120], rax; __int64
0x1400f2f7c  lea     rax, [rbp+20h+var_30]
0x1400f2f80  mov     [rsp+170h+var_128], rax; __int64
0x1400f2f85  lea     rax, [rbp+20h+var_90]
0x1400f2f89  mov     [rsp+170h+var_130], rax; __int64
0x1400f2f8e  lea     rax, [rbp+20h+var_28]
0x1400f2f92  mov     [rsp+170h+var_138], rax; __int64
0x1400f2f97  lea     rax, [rbp+20h+SRWLock]
0x1400f2f9b  mov     [rsp+170h+var_140], rax; __int64
0x1400f2fa0  lea     rax, [rbp+20h+var_20]
0x1400f2fa4  mov     [rsp+170h+var_148], rax; __int64
0x1400f2fa9  lea     rax, [rbp+20h+var_70]
0x1400f2fad  mov     [rsp+170h+var_150], rax; __int64
0x1400f2fb2  lea     rdx, unk_14013C3D8; int
0x1400f2fb9  mov     rcx, r9; int
0x1400f2fbc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645644544@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400f2fc1  jmp     loc_1400F308F
0x1400f2fc6  mov     [rbp+20h+SRWLock], 0
0x1400f2fce  lea     rdx, [rbp+20h+SRWLock]
0x1400f2fd2  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400f2fd7  mov     rax, [rbx+110h]
0x1400f2fde  mov     dword ptr [rax], 2
0x1400f2fe4  mov     rcx, [rbp+20h+SRWLock]; SRWLock
0x1400f2fe8  test    rcx, rcx
0x1400f2feb  jz      short loc_1400F2FF3
0x1400f2fed  call    cs:__imp_ReleaseSRWLockExclusive
0x1400f2ff3  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x1400f2ff8  mov     rdi, [rax+8]
0x1400f2ffc  mov     eax, [rdi]
0x1400f2ffe  cmp     eax, 4
0x1400f3001  jbe     loc_1400F308F
0x1400f3007  mov     rdx, [rdi+18h]
0x1400f300b  mov     rax, [rdi+10h]
0x1400f300f  mov     ecx, 200h
0x1400f3014  test    rcx, rax
0x1400f3017  jz      short loc_1400F308F
0x1400f3019  mov     rax, rdx
0x1400f301c  and     rax, rcx
0x1400f301f  cmp     rax, rdx
0x1400f3022  jnz     short loc_1400F308F
0x1400f3024  mov     eax, [rsi]
0x1400f3026  mov     dword ptr [rbp+20h+SRWLock], eax
0x1400f3029  mov     eax, [r14]
0x1400f302c  mov     dword ptr [rbp+20h+var_90], eax
0x1400f302f  call    cs:__imp_GetCurrentThreadId
0x1400f3035  mov     dword ptr [rbp+20h+var_98+4], eax
0x1400f3038  mov     r8, [rbx+110h]
0x1400f303f  mov     eax, [r8+48h]
0x1400f3043  mov     dword ptr [rbp+20h+var_98], eax
0x1400f3046  mov     [rbp+20h+var_70], 0
0x1400f304e  add     r8, 8
0x1400f3052  lea     rax, [rbp+20h+SRWLock]
0x1400f3056  mov     [rsp+170h+var_130], rax
0x1400f305b  lea     rax, [rbp+20h+var_90]
0x1400f305f  mov     [rsp+170h+var_138], rax
0x1400f3064  lea     rax, [rbp+20h+var_98+4]
0x1400f3068  mov     [rsp+170h+var_140], rax
0x1400f306d  lea     rax, [rbp+20h+var_98]
0x1400f3071  mov     [rsp+170h+var_148], rax
0x1400f3076  lea     rax, [rbp+20h+var_70]
0x1400f307a  mov     [rsp+170h+var_150], rax
0x1400f307f  lea     rdx, byte_14013CB9D
0x1400f3086  mov     rcx, rdi
0x1400f3089  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400f308e  nop
0x1400f308f  lea     rcx, [rbx+120h]; this
0x1400f3096  cmp     dword ptr [rcx+18h], 0
0x1400f309a  jz      short loc_1400F30A2
0x1400f309c  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1400f30a1  nop
0x1400f30a2  lea     r11, [rsp+170h+var_10]
0x1400f30aa  mov     rbx, [r11+28h]
0x1400f30ae  mov     rsi, [r11+30h]
0x1400f30b2  mov     rsp, r11
0x1400f30b5  pop     r14
0x1400f30b7  pop     rdi
0x1400f30b8  pop     rbp
0x1400f30b9  retn
```
