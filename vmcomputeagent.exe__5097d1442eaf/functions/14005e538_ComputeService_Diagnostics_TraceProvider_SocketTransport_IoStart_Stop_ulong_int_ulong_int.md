# ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::Stop<ulong &,int>(ulong &,int &&)

- ea: `0x14005e538`
- end: `0x14005e86a`
- name: `??$Stop@AEAKH@SocketTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@QEAAXAEAK$$QEAH@Z`
- size: `818`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140061d80`
- `0x140062050`

## callees

- `0x140001f4c`
- `0x140002410`
- `0x14000aeec`
- `0x140031be8`
- `0x14003407c`
- `0x14005e538`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005e5aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005e79d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005e5aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005e79d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005e7df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005e7df`

## pseudocode

```c
void __fastcall ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::Stop<unsigned long &,int>(
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
        (int)&word_1401352F2,
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
        (unsigned int)byte_1401359A3,
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
0x14005e538  mov     [rsp-8+arg_8], rbx
0x14005e53d  mov     [rsp-8+arg_10], rsi
0x14005e542  push    rbp
0x14005e543  push    rdi
0x14005e544  push    r14
0x14005e546  lea     rbp, [rsp-10h]
0x14005e54b  sub     rsp, 160h
0x14005e552  mov     rsi, r8
0x14005e555  mov     r14, rdx
0x14005e558  mov     rbx, rcx
0x14005e55b  mov     rdi, [rcx+110h]
0x14005e562  mov     eax, [rdi+48h]
0x14005e565  test    eax, eax
0x14005e567  jns     loc_14005E776
0x14005e56d  add     rdi, 50h ; 'P'
0x14005e571  cmp     eax, [rdi+8]
0x14005e574  jnz     loc_14005E776
0x14005e57a  test    rdi, rdi
0x14005e57d  jz      loc_14005E776
0x14005e583  mov     [rbp+20h+SRWLock], 0
0x14005e58b  lea     rdx, [rbp+20h+SRWLock]
0x14005e58f  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14005e594  mov     rax, [rbx+110h]
0x14005e59b  mov     dword ptr [rax], 2
0x14005e5a1  mov     rcx, [rbp+20h+SRWLock]; SRWLock
0x14005e5a5  test    rcx, rcx
0x14005e5a8  jz      short loc_14005E5B0
0x14005e5aa  call    cs:__imp_ReleaseSRWLockExclusive
0x14005e5b0  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x14005e5b5  mov     r9, [rax+8]
0x14005e5b9  mov     eax, [r9]
0x14005e5bc  cmp     eax, 4
0x14005e5bf  jbe     loc_14005E83F
0x14005e5c5  mov     rdx, [r9+18h]
0x14005e5c9  mov     rax, [r9+10h]
0x14005e5cd  mov     ecx, 200h
0x14005e5d2  test    rcx, rax
0x14005e5d5  jz      loc_14005E83F
0x14005e5db  mov     rax, rdx
0x14005e5de  and     rax, rcx
0x14005e5e1  cmp     rax, rdx
0x14005e5e4  jnz     loc_14005E83F
0x14005e5ea  mov     eax, [rsi]
0x14005e5ec  mov     dword ptr [rbp+20h+var_90+4], eax
0x14005e5ef  mov     eax, [r14]
0x14005e5f2  mov     dword ptr [rbp+20h+var_88], eax
0x14005e5f5  mov     rax, [rdi+30h]
0x14005e5f9  mov     [rbp+20h+var_68], rax
0x14005e5fd  mov     eax, [rdi+44h]
0x14005e600  mov     dword ptr [rbp+20h+var_88+4], eax
0x14005e603  mov     eax, [rdi+10h]
0x14005e606  mov     [rbp+20h+var_80], eax
0x14005e609  mov     rax, [rdi+78h]
0x14005e60d  mov     [rbp+20h+var_60], rax
0x14005e611  mov     rax, [rdi+70h]
0x14005e615  mov     [rbp+20h+var_58], rax
0x14005e619  mov     eax, [rdi+68h]
0x14005e61c  mov     [rbp+20h+var_7C], eax
0x14005e61f  mov     rax, [rdi+60h]
0x14005e623  mov     [rbp+20h+var_50], rax
0x14005e627  mov     rax, [rdi+58h]
0x14005e62b  mov     [rbp+20h+var_48], rax
0x14005e62f  mov     eax, [rdi+50h]
0x14005e632  mov     [rbp+20h+var_78], eax
0x14005e635  mov     rax, [rdi+48h]
0x14005e639  mov     [rbp+20h+var_40], rax
0x14005e63d  mov     eax, [rdi+20h]
0x14005e640  mov     dword ptr [rbp+20h+var_98], eax
0x14005e643  mov     rax, [rdi+18h]
0x14005e647  mov     [rbp+20h+var_38], rax
0x14005e64b  mov     eax, [rdi]
0x14005e64d  mov     dword ptr [rbp+20h+var_98+4], eax
0x14005e650  mov     rax, [rdi+80h]
0x14005e657  mov     [rbp+20h+var_30], rax
0x14005e65b  mov     eax, [rdi+40h]
0x14005e65e  mov     dword ptr [rbp+20h+var_90], eax
0x14005e661  mov     rax, [rdi+38h]
0x14005e665  mov     [rbp+20h+var_28], rax
0x14005e669  mov     eax, [rdi+8]
0x14005e66c  mov     dword ptr [rbp+20h+SRWLock], eax
0x14005e66f  mov     [rbp+20h+var_20], 1000000h
0x14005e677  mov     [rbp+20h+var_70], 0
0x14005e67f  mov     r8, [rbx+110h]
0x14005e686  add     r8, 8; int
0x14005e68a  lea     rax, [rbp+20h+var_90+4]
0x14005e68e  mov     [rsp+170h+var_B0], rax; __int64
0x14005e696  lea     rax, [rbp+20h+var_88]
0x14005e69a  mov     [rsp+170h+var_B8], rax; __int64
0x14005e6a2  lea     rax, [rbp+20h+var_68]
0x14005e6a6  mov     [rsp+170h+var_C0], rax; __int64
0x14005e6ae  lea     rax, [rbp+20h+var_88+4]
0x14005e6b2  mov     [rsp+170h+var_C8], rax; __int64
0x14005e6ba  lea     rax, [rbp+20h+var_80]
0x14005e6be  mov     [rsp+170h+var_D0], rax; __int64
0x14005e6c6  lea     rax, [rbp+20h+var_60]
0x14005e6ca  mov     [rsp+170h+var_D8], rax; __int64
0x14005e6d2  lea     rax, [rbp+20h+var_58]
0x14005e6d6  mov     [rsp+170h+var_E0], rax; __int64
0x14005e6de  lea     rax, [rbp+20h+var_7C]
0x14005e6e2  mov     [rsp+170h+var_E8], rax; __int64
0x14005e6ea  lea     rax, [rbp+20h+var_50]
0x14005e6ee  mov     [rsp+170h+var_F0], rax; __int64
0x14005e6f6  lea     rax, [rbp+20h+var_48]
0x14005e6fa  mov     [rsp+170h+var_F8], rax; __int64
0x14005e6ff  lea     rax, [rbp+20h+var_78]
0x14005e703  mov     [rsp+170h+var_100], rax; __int64
0x14005e708  lea     rax, [rbp+20h+var_40]
0x14005e70c  mov     [rsp+170h+var_108], rax; __int64
0x14005e711  lea     rax, [rbp+20h+var_98]
0x14005e715  mov     [rsp+170h+var_110], rax; __int64
0x14005e71a  lea     rax, [rbp+20h+var_38]
0x14005e71e  mov     [rsp+170h+var_118], rax; __int64
0x14005e723  lea     rax, [rbp+20h+var_98+4]
0x14005e727  mov     [rsp+170h+var_120], rax; __int64
0x14005e72c  lea     rax, [rbp+20h+var_30]
0x14005e730  mov     [rsp+170h+var_128], rax; __int64
0x14005e735  lea     rax, [rbp+20h+var_90]
0x14005e739  mov     [rsp+170h+var_130], rax; __int64
0x14005e73e  lea     rax, [rbp+20h+var_28]
0x14005e742  mov     [rsp+170h+var_138], rax; __int64
0x14005e747  lea     rax, [rbp+20h+SRWLock]
0x14005e74b  mov     [rsp+170h+var_140], rax; __int64
0x14005e750  lea     rax, [rbp+20h+var_20]
0x14005e754  mov     [rsp+170h+var_148], rax; __int64
0x14005e759  lea     rax, [rbp+20h+var_70]
0x14005e75d  mov     [rsp+170h+var_150], rax; __int64
0x14005e762  lea     rdx, word_1401352F2; int
0x14005e769  mov     rcx, r9; int
0x14005e76c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645644544@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14005e771  jmp     loc_14005E83F
0x14005e776  mov     [rbp+20h+SRWLock], 0
0x14005e77e  lea     rdx, [rbp+20h+SRWLock]
0x14005e782  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14005e787  mov     rax, [rbx+110h]
0x14005e78e  mov     dword ptr [rax], 2
0x14005e794  mov     rcx, [rbp+20h+SRWLock]; SRWLock
0x14005e798  test    rcx, rcx
0x14005e79b  jz      short loc_14005E7A3
0x14005e79d  call    cs:__imp_ReleaseSRWLockExclusive
0x14005e7a3  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x14005e7a8  mov     rdi, [rax+8]
0x14005e7ac  mov     eax, [rdi]
0x14005e7ae  cmp     eax, 4
0x14005e7b1  jbe     loc_14005E83F
0x14005e7b7  mov     rdx, [rdi+18h]
0x14005e7bb  mov     rax, [rdi+10h]
0x14005e7bf  mov     ecx, 200h
0x14005e7c4  test    rcx, rax
0x14005e7c7  jz      short loc_14005E83F
0x14005e7c9  mov     rax, rdx
0x14005e7cc  and     rax, rcx
0x14005e7cf  cmp     rax, rdx
0x14005e7d2  jnz     short loc_14005E83F
0x14005e7d4  mov     eax, [rsi]
0x14005e7d6  mov     dword ptr [rbp+20h+SRWLock], eax
0x14005e7d9  mov     eax, [r14]
0x14005e7dc  mov     dword ptr [rbp+20h+var_90], eax
0x14005e7df  call    cs:__imp_GetCurrentThreadId
0x14005e7e5  mov     dword ptr [rbp+20h+var_98+4], eax
0x14005e7e8  mov     r8, [rbx+110h]
0x14005e7ef  mov     eax, [r8+48h]
0x14005e7f3  mov     dword ptr [rbp+20h+var_98], eax
0x14005e7f6  mov     [rbp+20h+var_70], 0
0x14005e7fe  add     r8, 8
0x14005e802  lea     rax, [rbp+20h+SRWLock]
0x14005e806  mov     [rsp+170h+var_130], rax
0x14005e80b  lea     rax, [rbp+20h+var_90]
0x14005e80f  mov     [rsp+170h+var_138], rax
0x14005e814  lea     rax, [rbp+20h+var_98+4]
0x14005e818  mov     [rsp+170h+var_140], rax
0x14005e81d  lea     rax, [rbp+20h+var_98]
0x14005e821  mov     [rsp+170h+var_148], rax
0x14005e826  lea     rax, [rbp+20h+var_70]
0x14005e82a  mov     [rsp+170h+var_150], rax
0x14005e82f  lea     rdx, byte_1401359A3
0x14005e836  mov     rcx, rdi
0x14005e839  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14005e83e  nop
0x14005e83f  lea     rcx, [rbx+120h]; this
0x14005e846  cmp     dword ptr [rcx+18h], 0
0x14005e84a  jz      short loc_14005E852
0x14005e84c  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14005e851  nop
0x14005e852  lea     r11, [rsp+170h+var_10]
0x14005e85a  mov     rbx, [r11+28h]
0x14005e85e  mov     rsi, [r11+30h]
0x14005e862  mov     rsp, r11
0x14005e865  pop     r14
0x14005e867  pop     rdi
0x14005e868  pop     rbp
0x14005e869  retn
```
