# ComputeService::Diagnostics::TraceProvider::BridgeClient_ProcessConnect::StopActivity(void)

- ea: `0x140056b30`
- end: `0x140056e03`
- name: `?StopActivity@BridgeClient_ProcessConnect@TraceProvider@Diagnostics@ComputeService@@MEAAXXZ`
- size: `723`
- prototype: `void __fastcall(ComputeService::Diagnostics::TraceProvider::BridgeClient_ProcessConnect *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400017a8`
- `0x140001abc`
- `0x14000aeec`
- `0x140031be8`
- `0x14003407c`
- `0x140056b30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140056b97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140056d5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140056b97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140056d5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140056d8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140056d8a`

## pseudocode

```c
void __fastcall ComputeService::Diagnostics::TraceProvider::BridgeClient_ProcessConnect::StopActivity(
        ComputeService::Diagnostics::TraceProvider::BridgeClient_ProcessConnect *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // r8
  PSRWLOCK SRWLock; // [rsp+C0h] [rbp-80h] BYREF
  int v9; // [rsp+C8h] [rbp-78h] BYREF
  int v10; // [rsp+CCh] [rbp-74h] BYREF
  int v11; // [rsp+D0h] [rbp-70h] BYREF
  int v12; // [rsp+D4h] [rbp-6Ch] BYREF
  int v13; // [rsp+D8h] [rbp-68h] BYREF
  int v14; // [rsp+DCh] [rbp-64h] BYREF
  int v15; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v16; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v17; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v18; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v19; // [rsp+100h] [rbp-40h] BYREF
  __int64 v20; // [rsp+108h] [rbp-38h] BYREF
  __int64 v21; // [rsp+110h] [rbp-30h] BYREF
  __int64 v22; // [rsp+118h] [rbp-28h] BYREF
  __int64 v23; // [rsp+120h] [rbp-20h] BYREF
  __int64 v24; // [rsp+128h] [rbp-18h] BYREF
  __int64 v25; // [rsp+130h] [rbp-10h] BYREF
  __int64 v26; // [rsp+138h] [rbp-8h] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    SRWLock = 0;
    wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = *((_QWORD *)ComputeService::Diagnostics::TraceProvider::Instance() + 1);
    if ( *(_DWORD *)v5 > 5u && (*(_QWORD *)(v5 + 16) & 2) != 0 && (*(_QWORD *)(v5 + 24) & 2LL) == *(_QWORD *)(v5 + 24) )
    {
      v17 = *((_QWORD *)v4 + 6);
      v10 = v4[17];
      v11 = v4[4];
      v18 = *((_QWORD *)v4 + 15);
      v19 = *((_QWORD *)v4 + 14);
      v12 = v4[26];
      v20 = *((_QWORD *)v4 + 12);
      v21 = *((_QWORD *)v4 + 11);
      v13 = v4[20];
      v22 = *((_QWORD *)v4 + 9);
      v14 = v4[8];
      v23 = *((_QWORD *)v4 + 3);
      v15 = *v4;
      v24 = *((_QWORD *)v4 + 16);
      v9 = v4[16];
      v25 = *((_QWORD *)v4 + 7);
      LODWORD(SRWLock) = v4[2];
      v26 = 0x1000000;
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v5,
        (int)&byte_14013434B,
        *((_QWORD *)this + 34) + 8,
        (__int64)&v16,
        (__int64)&v26,
        (__int64)&SRWLock,
        (__int64)&v25,
        (__int64)&v9,
        (__int64)&v24,
        (__int64)&v15,
        (__int64)&v23,
        (__int64)&v14,
        (__int64)&v22,
        (__int64)&v13,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v12,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v11,
        (__int64)&v10,
        (__int64)&v17);
    }
  }
  else
  {
    SRWLock = 0;
    wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = *((_QWORD *)ComputeService::Diagnostics::TraceProvider::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u && (*(_QWORD *)(v6 + 16) & 2) != 0 && (*(_QWORD *)(v6 + 24) & 2LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v9 = *(_DWORD *)(v7 + 72);
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)&byte_14013425F,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeService::Diagnostics::TraceProvider::BridgeClient_ProcessConnect *)((char *)this + 288));
}

```

## disassembly

```asm
0x140056b30  mov     [rsp-8+arg_8], rbx
0x140056b35  mov     [rsp-8+arg_10], rdi
0x140056b3a  push    rbp
0x140056b3b  mov     rbp, rsp
0x140056b3e  sub     rsp, 140h
0x140056b45  mov     rbx, rcx
0x140056b48  mov     rdi, [rcx+110h]
0x140056b4f  mov     eax, [rdi+48h]
0x140056b52  test    eax, eax
0x140056b54  jns     loc_140056D36
0x140056b5a  add     rdi, 50h ; 'P'
0x140056b5e  cmp     eax, [rdi+8]
0x140056b61  jnz     loc_140056D36
0x140056b67  test    rdi, rdi
0x140056b6a  jz      loc_140056D36
0x140056b70  mov     [rbp+SRWLock], 0
0x140056b78  lea     rdx, [rbp+SRWLock]
0x140056b7c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140056b81  mov     rax, [rbx+110h]
0x140056b88  mov     dword ptr [rax], 2
0x140056b8e  mov     rcx, [rbp+SRWLock]; SRWLock
0x140056b92  test    rcx, rcx
0x140056b95  jz      short loc_140056B9D
0x140056b97  call    cs:__imp_ReleaseSRWLockExclusive
0x140056b9d  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x140056ba2  mov     rcx, [rax+8]; int
0x140056ba6  mov     eax, [rcx]
0x140056ba8  cmp     eax, 5
0x140056bab  jbe     loc_140056DDB
0x140056bb1  mov     rdx, [rcx+18h]
0x140056bb5  mov     rax, [rcx+10h]
0x140056bb9  test    al, 2
0x140056bbb  jz      loc_140056DDB
0x140056bc1  mov     rax, rdx
0x140056bc4  and     eax, 2
0x140056bc7  cmp     rax, rdx
0x140056bca  jnz     loc_140056DDB
0x140056bd0  mov     rax, [rdi+30h]
0x140056bd4  mov     [rbp+var_50], rax
0x140056bd8  mov     eax, [rdi+44h]
0x140056bdb  mov     dword ptr [rbp+var_78+4], eax
0x140056bde  mov     eax, [rdi+10h]
0x140056be1  mov     dword ptr [rbp+var_70], eax
0x140056be4  mov     rax, [rdi+78h]
0x140056be8  mov     [rbp+var_48], rax
0x140056bec  mov     rax, [rdi+70h]
0x140056bf0  mov     [rbp+var_40], rax
0x140056bf4  mov     eax, [rdi+68h]
0x140056bf7  mov     dword ptr [rbp+var_70+4], eax
0x140056bfa  mov     rax, [rdi+60h]
0x140056bfe  mov     [rbp+var_38], rax
0x140056c02  mov     rax, [rdi+58h]
0x140056c06  mov     [rbp+var_30], rax
0x140056c0a  mov     eax, [rdi+50h]
0x140056c0d  mov     dword ptr [rbp+var_68], eax
0x140056c10  mov     rax, [rdi+48h]
0x140056c14  mov     [rbp+var_28], rax
0x140056c18  mov     eax, [rdi+20h]
0x140056c1b  mov     dword ptr [rbp+var_68+4], eax
0x140056c1e  mov     rax, [rdi+18h]
0x140056c22  mov     [rbp+var_20], rax
0x140056c26  mov     eax, [rdi]
0x140056c28  mov     [rbp+var_60], eax
0x140056c2b  mov     rax, [rdi+80h]
0x140056c32  mov     [rbp+var_18], rax
0x140056c36  mov     eax, [rdi+40h]
0x140056c39  mov     dword ptr [rbp+var_78], eax
0x140056c3c  mov     rax, [rdi+38h]
0x140056c40  mov     [rbp+var_10], rax
0x140056c44  mov     eax, [rdi+8]
0x140056c47  mov     dword ptr [rbp+SRWLock], eax
0x140056c4a  mov     [rbp+var_8], 1000000h
0x140056c52  mov     [rbp+var_58], 0
0x140056c5a  mov     r8, [rbx+110h]
0x140056c61  add     r8, 8; int
0x140056c65  lea     rax, [rbp+var_50]
0x140056c69  mov     [rsp+140h+var_90], rax; __int64
0x140056c71  lea     rax, [rbp+var_78+4]
0x140056c75  mov     [rsp+140h+var_98], rax; __int64
0x140056c7d  lea     rax, [rbp+var_70]
0x140056c81  mov     [rsp+140h+var_A0], rax; __int64
0x140056c89  lea     rax, [rbp+var_48]
0x140056c8d  mov     [rsp+140h+var_A8], rax; __int64
0x140056c95  lea     rax, [rbp+var_40]
0x140056c99  mov     [rsp+140h+var_B0], rax; __int64
0x140056ca1  lea     rax, [rbp+var_70+4]
0x140056ca5  mov     [rsp+140h+var_B8], rax; __int64
0x140056cad  lea     rax, [rbp+var_38]
0x140056cb1  mov     [rsp+140h+var_C0], rax; __int64
0x140056cb9  lea     rax, [rbp+var_30]
0x140056cbd  mov     [rsp+140h+var_C8], rax; __int64
0x140056cc2  lea     rax, [rbp+var_68]
0x140056cc6  mov     [rsp+140h+var_D0], rax; __int64
0x140056ccb  lea     rax, [rbp+var_28]
0x140056ccf  mov     [rsp+140h+var_D8], rax; __int64
0x140056cd4  lea     rax, [rbp+var_68+4]
0x140056cd8  mov     [rsp+140h+var_E0], rax; __int64
0x140056cdd  lea     rax, [rbp+var_20]
0x140056ce1  mov     [rsp+140h+var_E8], rax; __int64
0x140056ce6  lea     rax, [rbp+var_60]
0x140056cea  mov     [rsp+140h+var_F0], rax; __int64
0x140056cef  lea     rax, [rbp+var_18]
0x140056cf3  mov     [rsp+140h+var_F8], rax; __int64
0x140056cf8  lea     rax, [rbp+var_78]
0x140056cfc  mov     [rsp+140h+var_100], rax; __int64
0x140056d01  lea     rax, [rbp+var_10]
0x140056d05  mov     [rsp+140h+var_108], rax; __int64
0x140056d0a  lea     rax, [rbp+SRWLock]
0x140056d0e  mov     [rsp+140h+var_110], rax; __int64
0x140056d13  lea     rax, [rbp+var_8]
0x140056d17  mov     [rsp+140h+var_118], rax; __int64
0x140056d1c  lea     rax, [rbp+var_58]
0x140056d20  mov     [rsp+140h+var_120], rax; __int64
0x140056d25  lea     rdx, byte_14013434B; int
0x140056d2c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140056d31  jmp     loc_140056DDB
0x140056d36  mov     [rbp+SRWLock], 0
0x140056d3e  lea     rdx, [rbp+SRWLock]
0x140056d42  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140056d47  mov     rax, [rbx+110h]
0x140056d4e  mov     dword ptr [rax], 2
0x140056d54  mov     rcx, [rbp+SRWLock]; SRWLock
0x140056d58  test    rcx, rcx
0x140056d5b  jz      short loc_140056D63
0x140056d5d  call    cs:__imp_ReleaseSRWLockExclusive
0x140056d63  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x140056d68  mov     rdi, [rax+8]
0x140056d6c  mov     eax, [rdi]
0x140056d6e  cmp     eax, 5
0x140056d71  jbe     short loc_140056DDB
0x140056d73  mov     rcx, [rdi+18h]
0x140056d77  mov     rax, [rdi+10h]
0x140056d7b  test    al, 2
0x140056d7d  jz      short loc_140056DDB
0x140056d7f  mov     rax, rcx
0x140056d82  and     eax, 2
0x140056d85  cmp     rax, rcx
0x140056d88  jnz     short loc_140056DDB
0x140056d8a  call    cs:__imp_GetCurrentThreadId
0x140056d90  mov     dword ptr [rbp+SRWLock], eax
0x140056d93  mov     r8, [rbx+110h]
0x140056d9a  mov     eax, [r8+48h]
0x140056d9e  mov     dword ptr [rbp+var_78], eax
0x140056da1  mov     [rbp+var_58], 0
0x140056da9  add     r8, 8
0x140056dad  lea     rax, [rbp+SRWLock]
0x140056db1  mov     [rsp+140h+var_110], rax
0x140056db6  lea     rax, [rbp+var_78]
0x140056dba  mov     [rsp+140h+var_118], rax
0x140056dbf  lea     rax, [rbp+var_58]
0x140056dc3  mov     [rsp+140h+var_120], rax
0x140056dc8  xor     r9d, r9d
0x140056dcb  lea     rdx, byte_14013425F
0x140056dd2  mov     rcx, rdi
0x140056dd5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140056dda  nop
0x140056ddb  lea     rcx, [rbx+120h]; this
0x140056de2  cmp     dword ptr [rcx+18h], 0
0x140056de6  jz      short loc_140056DEE
0x140056de8  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x140056ded  nop
0x140056dee  lea     r11, [rsp+140h+var_s0]
0x140056df6  mov     rbx, [r11+18h]
0x140056dfa  mov     rdi, [r11+20h]
0x140056dfe  mov     rsp, r11
0x140056e01  pop     rbp
0x140056e02  retn
```
