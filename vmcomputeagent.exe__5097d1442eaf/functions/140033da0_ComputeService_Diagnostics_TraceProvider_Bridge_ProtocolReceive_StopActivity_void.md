# ComputeService::Diagnostics::TraceProvider::Bridge_ProtocolReceive::StopActivity(void)

- ea: `0x140033da0`
- end: `0x140034073`
- name: `?StopActivity@Bridge_ProtocolReceive@TraceProvider@Diagnostics@ComputeService@@MEAAXXZ`
- size: `723`
- prototype: `void __fastcall(ComputeService::Diagnostics::TraceProvider::Bridge_ProtocolReceive *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400017a8`
- `0x140001abc`
- `0x14000aeec`
- `0x140031be8`
- `0x140033da0`
- `0x14003407c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140033e07`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140033fcd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140033e07`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140033fcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140033ffa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140033ffa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ComputeService::Diagnostics::TraceProvider::Bridge_ProtocolReceive::StopActivity(
        ComputeService::Diagnostics::TraceProvider::Bridge_ProtocolReceive *this)
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
        (int)&byte_140133CA1,
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
        (unsigned int)word_140133C4A,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeService::Diagnostics::TraceProvider::Bridge_ProtocolReceive *)((char *)this + 288));
}

```

## disassembly

```asm
0x140033da0  mov     [rsp-8+arg_8], rbx
0x140033da5  mov     [rsp-8+arg_10], rdi
0x140033daa  push    rbp
0x140033dab  mov     rbp, rsp
0x140033dae  sub     rsp, 140h
0x140033db5  mov     rbx, rcx
0x140033db8  mov     rdi, [rcx+110h]
0x140033dbf  mov     eax, [rdi+48h]
0x140033dc2  test    eax, eax
0x140033dc4  jns     loc_140033FA6
0x140033dca  add     rdi, 50h ; 'P'
0x140033dce  cmp     eax, [rdi+8]
0x140033dd1  jnz     loc_140033FA6
0x140033dd7  test    rdi, rdi
0x140033dda  jz      loc_140033FA6
0x140033de0  mov     [rbp+SRWLock], 0
0x140033de8  lea     rdx, [rbp+SRWLock]
0x140033dec  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140033df1  mov     rax, [rbx+110h]
0x140033df8  mov     dword ptr [rax], 2
0x140033dfe  mov     rcx, [rbp+SRWLock]; SRWLock
0x140033e02  test    rcx, rcx
0x140033e05  jz      short loc_140033E0D
0x140033e07  call    cs:__imp_ReleaseSRWLockExclusive
0x140033e0d  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x140033e12  mov     rcx, [rax+8]; int
0x140033e16  mov     eax, [rcx]
0x140033e18  cmp     eax, 5
0x140033e1b  jbe     loc_14003404B
0x140033e21  mov     rdx, [rcx+18h]
0x140033e25  mov     rax, [rcx+10h]
0x140033e29  test    al, 2
0x140033e2b  jz      loc_14003404B
0x140033e31  mov     rax, rdx
0x140033e34  and     eax, 2
0x140033e37  cmp     rax, rdx
0x140033e3a  jnz     loc_14003404B
0x140033e40  mov     rax, [rdi+30h]
0x140033e44  mov     [rbp+var_50], rax
0x140033e48  mov     eax, [rdi+44h]
0x140033e4b  mov     dword ptr [rbp+var_78+4], eax
0x140033e4e  mov     eax, [rdi+10h]
0x140033e51  mov     dword ptr [rbp+var_70], eax
0x140033e54  mov     rax, [rdi+78h]
0x140033e58  mov     [rbp+var_48], rax
0x140033e5c  mov     rax, [rdi+70h]
0x140033e60  mov     [rbp+var_40], rax
0x140033e64  mov     eax, [rdi+68h]
0x140033e67  mov     dword ptr [rbp+var_70+4], eax
0x140033e6a  mov     rax, [rdi+60h]
0x140033e6e  mov     [rbp+var_38], rax
0x140033e72  mov     rax, [rdi+58h]
0x140033e76  mov     [rbp+var_30], rax
0x140033e7a  mov     eax, [rdi+50h]
0x140033e7d  mov     dword ptr [rbp+var_68], eax
0x140033e80  mov     rax, [rdi+48h]
0x140033e84  mov     [rbp+var_28], rax
0x140033e88  mov     eax, [rdi+20h]
0x140033e8b  mov     dword ptr [rbp+var_68+4], eax
0x140033e8e  mov     rax, [rdi+18h]
0x140033e92  mov     [rbp+var_20], rax
0x140033e96  mov     eax, [rdi]
0x140033e98  mov     [rbp+var_60], eax
0x140033e9b  mov     rax, [rdi+80h]
0x140033ea2  mov     [rbp+var_18], rax
0x140033ea6  mov     eax, [rdi+40h]
0x140033ea9  mov     dword ptr [rbp+var_78], eax
0x140033eac  mov     rax, [rdi+38h]
0x140033eb0  mov     [rbp+var_10], rax
0x140033eb4  mov     eax, [rdi+8]
0x140033eb7  mov     dword ptr [rbp+SRWLock], eax
0x140033eba  mov     [rbp+var_8], 1000000h
0x140033ec2  mov     [rbp+var_58], 0
0x140033eca  mov     r8, [rbx+110h]
0x140033ed1  add     r8, 8; int
0x140033ed5  lea     rax, [rbp+var_50]
0x140033ed9  mov     [rsp+140h+var_90], rax; __int64
0x140033ee1  lea     rax, [rbp+var_78+4]
0x140033ee5  mov     [rsp+140h+var_98], rax; __int64
0x140033eed  lea     rax, [rbp+var_70]
0x140033ef1  mov     [rsp+140h+var_A0], rax; __int64
0x140033ef9  lea     rax, [rbp+var_48]
0x140033efd  mov     [rsp+140h+var_A8], rax; __int64
0x140033f05  lea     rax, [rbp+var_40]
0x140033f09  mov     [rsp+140h+var_B0], rax; __int64
0x140033f11  lea     rax, [rbp+var_70+4]
0x140033f15  mov     [rsp+140h+var_B8], rax; __int64
0x140033f1d  lea     rax, [rbp+var_38]
0x140033f21  mov     [rsp+140h+var_C0], rax; __int64
0x140033f29  lea     rax, [rbp+var_30]
0x140033f2d  mov     [rsp+140h+var_C8], rax; __int64
0x140033f32  lea     rax, [rbp+var_68]
0x140033f36  mov     [rsp+140h+var_D0], rax; __int64
0x140033f3b  lea     rax, [rbp+var_28]
0x140033f3f  mov     [rsp+140h+var_D8], rax; __int64
0x140033f44  lea     rax, [rbp+var_68+4]
0x140033f48  mov     [rsp+140h+var_E0], rax; __int64
0x140033f4d  lea     rax, [rbp+var_20]
0x140033f51  mov     [rsp+140h+var_E8], rax; __int64
0x140033f56  lea     rax, [rbp+var_60]
0x140033f5a  mov     [rsp+140h+var_F0], rax; __int64
0x140033f5f  lea     rax, [rbp+var_18]
0x140033f63  mov     [rsp+140h+var_F8], rax; __int64
0x140033f68  lea     rax, [rbp+var_78]
0x140033f6c  mov     [rsp+140h+var_100], rax; __int64
0x140033f71  lea     rax, [rbp+var_10]
0x140033f75  mov     [rsp+140h+var_108], rax; __int64
0x140033f7a  lea     rax, [rbp+SRWLock]
0x140033f7e  mov     [rsp+140h+var_110], rax; __int64
0x140033f83  lea     rax, [rbp+var_8]
0x140033f87  mov     [rsp+140h+var_118], rax; __int64
0x140033f8c  lea     rax, [rbp+var_58]
0x140033f90  mov     [rsp+140h+var_120], rax; __int64
0x140033f95  lea     rdx, byte_140133CA1; int
0x140033f9c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140033fa1  jmp     loc_14003404B
0x140033fa6  mov     [rbp+SRWLock], 0
0x140033fae  lea     rdx, [rbp+SRWLock]
0x140033fb2  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140033fb7  mov     rax, [rbx+110h]
0x140033fbe  mov     dword ptr [rax], 2
0x140033fc4  mov     rcx, [rbp+SRWLock]; SRWLock
0x140033fc8  test    rcx, rcx
0x140033fcb  jz      short loc_140033FD3
0x140033fcd  call    cs:__imp_ReleaseSRWLockExclusive
0x140033fd3  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x140033fd8  mov     rdi, [rax+8]
0x140033fdc  mov     eax, [rdi]
0x140033fde  cmp     eax, 5
0x140033fe1  jbe     short loc_14003404B
0x140033fe3  mov     rcx, [rdi+18h]
0x140033fe7  mov     rax, [rdi+10h]
0x140033feb  test    al, 2
0x140033fed  jz      short loc_14003404B
0x140033fef  mov     rax, rcx
0x140033ff2  and     eax, 2
0x140033ff5  cmp     rax, rcx
0x140033ff8  jnz     short loc_14003404B
0x140033ffa  call    cs:__imp_GetCurrentThreadId
0x140034000  mov     dword ptr [rbp+SRWLock], eax
0x140034003  mov     r8, [rbx+110h]
0x14003400a  mov     eax, [r8+48h]
0x14003400e  mov     dword ptr [rbp+var_78], eax
0x140034011  mov     [rbp+var_58], 0
0x140034019  add     r8, 8
0x14003401d  lea     rax, [rbp+SRWLock]
0x140034021  mov     [rsp+140h+var_110], rax
0x140034026  lea     rax, [rbp+var_78]
0x14003402a  mov     [rsp+140h+var_118], rax
0x14003402f  lea     rax, [rbp+var_58]
0x140034033  mov     [rsp+140h+var_120], rax
0x140034038  xor     r9d, r9d
0x14003403b  lea     rdx, word_140133C4A
0x140034042  mov     rcx, rdi
0x140034045  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14003404a  nop
0x14003404b  lea     rcx, [rbx+120h]; this
0x140034052  cmp     dword ptr [rcx+18h], 0
0x140034056  jz      short loc_14003405E
0x140034058  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14003405d  nop
0x14003405e  lea     r11, [rsp+140h+var_s0]
0x140034066  mov     rbx, [r11+18h]
0x14003406a  mov     rdi, [r11+20h]
0x14003406e  mov     rsp, r11
0x140034071  pop     rbp
0x140034072  retn
```
