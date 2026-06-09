# ComputeService::Diagnostics::TraceProvider::Bridge_Connect::StopActivity(void)

- ea: `0x140056e10`
- end: `0x1400570e3`
- name: `?StopActivity@Bridge_Connect@TraceProvider@Diagnostics@ComputeService@@MEAAXXZ`
- size: `723`
- prototype: `void __fastcall(ComputeService::Diagnostics::TraceProvider::Bridge_Connect *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400017a8`
- `0x140001abc`
- `0x14000aeec`
- `0x140031be8`
- `0x14003407c`
- `0x140056e10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140056e77`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005703d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140056e77`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005703d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005706a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005706a`

## pseudocode

```c
void __fastcall ComputeService::Diagnostics::TraceProvider::Bridge_Connect::StopActivity(
        ComputeService::Diagnostics::TraceProvider::Bridge_Connect *this)
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
    if ( *(_DWORD *)v5 > 4u && (*(_QWORD *)(v5 + 16) & 6) != 0 && (*(_QWORD *)(v5 + 24) & 6LL) == *(_QWORD *)(v5 + 24) )
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
        (int)&byte_140134C35,
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
    if ( *(_DWORD *)v6 > 4u && (*(_QWORD *)(v6 + 16) & 6) != 0 && (*(_QWORD *)(v6 + 24) & 6LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v9 = *(_DWORD *)(v7 + 72);
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)&word_140134BE6,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeService::Diagnostics::TraceProvider::Bridge_Connect *)((char *)this + 288));
}

```

## disassembly

```asm
0x140056e10  mov     [rsp-8+arg_8], rbx
0x140056e15  mov     [rsp-8+arg_10], rdi
0x140056e1a  push    rbp
0x140056e1b  mov     rbp, rsp
0x140056e1e  sub     rsp, 140h
0x140056e25  mov     rbx, rcx
0x140056e28  mov     rdi, [rcx+110h]
0x140056e2f  mov     eax, [rdi+48h]
0x140056e32  test    eax, eax
0x140056e34  jns     loc_140057016
0x140056e3a  add     rdi, 50h ; 'P'
0x140056e3e  cmp     eax, [rdi+8]
0x140056e41  jnz     loc_140057016
0x140056e47  test    rdi, rdi
0x140056e4a  jz      loc_140057016
0x140056e50  mov     [rbp+SRWLock], 0
0x140056e58  lea     rdx, [rbp+SRWLock]
0x140056e5c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140056e61  mov     rax, [rbx+110h]
0x140056e68  mov     dword ptr [rax], 2
0x140056e6e  mov     rcx, [rbp+SRWLock]; SRWLock
0x140056e72  test    rcx, rcx
0x140056e75  jz      short loc_140056E7D
0x140056e77  call    cs:__imp_ReleaseSRWLockExclusive
0x140056e7d  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x140056e82  mov     rcx, [rax+8]; int
0x140056e86  mov     eax, [rcx]
0x140056e88  cmp     eax, 4
0x140056e8b  jbe     loc_1400570BB
0x140056e91  mov     rdx, [rcx+18h]
0x140056e95  mov     rax, [rcx+10h]
0x140056e99  test    al, 6
0x140056e9b  jz      loc_1400570BB
0x140056ea1  mov     rax, rdx
0x140056ea4  and     eax, 6
0x140056ea7  cmp     rax, rdx
0x140056eaa  jnz     loc_1400570BB
0x140056eb0  mov     rax, [rdi+30h]
0x140056eb4  mov     [rbp+var_50], rax
0x140056eb8  mov     eax, [rdi+44h]
0x140056ebb  mov     dword ptr [rbp+var_78+4], eax
0x140056ebe  mov     eax, [rdi+10h]
0x140056ec1  mov     dword ptr [rbp+var_70], eax
0x140056ec4  mov     rax, [rdi+78h]
0x140056ec8  mov     [rbp+var_48], rax
0x140056ecc  mov     rax, [rdi+70h]
0x140056ed0  mov     [rbp+var_40], rax
0x140056ed4  mov     eax, [rdi+68h]
0x140056ed7  mov     dword ptr [rbp+var_70+4], eax
0x140056eda  mov     rax, [rdi+60h]
0x140056ede  mov     [rbp+var_38], rax
0x140056ee2  mov     rax, [rdi+58h]
0x140056ee6  mov     [rbp+var_30], rax
0x140056eea  mov     eax, [rdi+50h]
0x140056eed  mov     dword ptr [rbp+var_68], eax
0x140056ef0  mov     rax, [rdi+48h]
0x140056ef4  mov     [rbp+var_28], rax
0x140056ef8  mov     eax, [rdi+20h]
0x140056efb  mov     dword ptr [rbp+var_68+4], eax
0x140056efe  mov     rax, [rdi+18h]
0x140056f02  mov     [rbp+var_20], rax
0x140056f06  mov     eax, [rdi]
0x140056f08  mov     [rbp+var_60], eax
0x140056f0b  mov     rax, [rdi+80h]
0x140056f12  mov     [rbp+var_18], rax
0x140056f16  mov     eax, [rdi+40h]
0x140056f19  mov     dword ptr [rbp+var_78], eax
0x140056f1c  mov     rax, [rdi+38h]
0x140056f20  mov     [rbp+var_10], rax
0x140056f24  mov     eax, [rdi+8]
0x140056f27  mov     dword ptr [rbp+SRWLock], eax
0x140056f2a  mov     [rbp+var_8], 1000000h
0x140056f32  mov     [rbp+var_58], 0
0x140056f3a  mov     r8, [rbx+110h]
0x140056f41  add     r8, 8; int
0x140056f45  lea     rax, [rbp+var_50]
0x140056f49  mov     [rsp+140h+var_90], rax; __int64
0x140056f51  lea     rax, [rbp+var_78+4]
0x140056f55  mov     [rsp+140h+var_98], rax; __int64
0x140056f5d  lea     rax, [rbp+var_70]
0x140056f61  mov     [rsp+140h+var_A0], rax; __int64
0x140056f69  lea     rax, [rbp+var_48]
0x140056f6d  mov     [rsp+140h+var_A8], rax; __int64
0x140056f75  lea     rax, [rbp+var_40]
0x140056f79  mov     [rsp+140h+var_B0], rax; __int64
0x140056f81  lea     rax, [rbp+var_70+4]
0x140056f85  mov     [rsp+140h+var_B8], rax; __int64
0x140056f8d  lea     rax, [rbp+var_38]
0x140056f91  mov     [rsp+140h+var_C0], rax; __int64
0x140056f99  lea     rax, [rbp+var_30]
0x140056f9d  mov     [rsp+140h+var_C8], rax; __int64
0x140056fa2  lea     rax, [rbp+var_68]
0x140056fa6  mov     [rsp+140h+var_D0], rax; __int64
0x140056fab  lea     rax, [rbp+var_28]
0x140056faf  mov     [rsp+140h+var_D8], rax; __int64
0x140056fb4  lea     rax, [rbp+var_68+4]
0x140056fb8  mov     [rsp+140h+var_E0], rax; __int64
0x140056fbd  lea     rax, [rbp+var_20]
0x140056fc1  mov     [rsp+140h+var_E8], rax; __int64
0x140056fc6  lea     rax, [rbp+var_60]
0x140056fca  mov     [rsp+140h+var_F0], rax; __int64
0x140056fcf  lea     rax, [rbp+var_18]
0x140056fd3  mov     [rsp+140h+var_F8], rax; __int64
0x140056fd8  lea     rax, [rbp+var_78]
0x140056fdc  mov     [rsp+140h+var_100], rax; __int64
0x140056fe1  lea     rax, [rbp+var_10]
0x140056fe5  mov     [rsp+140h+var_108], rax; __int64
0x140056fea  lea     rax, [rbp+SRWLock]
0x140056fee  mov     [rsp+140h+var_110], rax; __int64
0x140056ff3  lea     rax, [rbp+var_8]
0x140056ff7  mov     [rsp+140h+var_118], rax; __int64
0x140056ffc  lea     rax, [rbp+var_58]
0x140057000  mov     [rsp+140h+var_120], rax; __int64
0x140057005  lea     rdx, byte_140134C35; int
0x14005700c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140057011  jmp     loc_1400570BB
0x140057016  mov     [rbp+SRWLock], 0
0x14005701e  lea     rdx, [rbp+SRWLock]
0x140057022  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140057027  mov     rax, [rbx+110h]
0x14005702e  mov     dword ptr [rax], 2
0x140057034  mov     rcx, [rbp+SRWLock]; SRWLock
0x140057038  test    rcx, rcx
0x14005703b  jz      short loc_140057043
0x14005703d  call    cs:__imp_ReleaseSRWLockExclusive
0x140057043  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x140057048  mov     rdi, [rax+8]
0x14005704c  mov     eax, [rdi]
0x14005704e  cmp     eax, 4
0x140057051  jbe     short loc_1400570BB
0x140057053  mov     rcx, [rdi+18h]
0x140057057  mov     rax, [rdi+10h]
0x14005705b  test    al, 6
0x14005705d  jz      short loc_1400570BB
0x14005705f  mov     rax, rcx
0x140057062  and     eax, 6
0x140057065  cmp     rax, rcx
0x140057068  jnz     short loc_1400570BB
0x14005706a  call    cs:__imp_GetCurrentThreadId
0x140057070  mov     dword ptr [rbp+SRWLock], eax
0x140057073  mov     r8, [rbx+110h]
0x14005707a  mov     eax, [r8+48h]
0x14005707e  mov     dword ptr [rbp+var_78], eax
0x140057081  mov     [rbp+var_58], 0
0x140057089  add     r8, 8
0x14005708d  lea     rax, [rbp+SRWLock]
0x140057091  mov     [rsp+140h+var_110], rax
0x140057096  lea     rax, [rbp+var_78]
0x14005709a  mov     [rsp+140h+var_118], rax
0x14005709f  lea     rax, [rbp+var_58]
0x1400570a3  mov     [rsp+140h+var_120], rax
0x1400570a8  xor     r9d, r9d
0x1400570ab  lea     rdx, word_140134BE6
0x1400570b2  mov     rcx, rdi
0x1400570b5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400570ba  nop
0x1400570bb  lea     rcx, [rbx+120h]; this
0x1400570c2  cmp     dword ptr [rcx+18h], 0
0x1400570c6  jz      short loc_1400570CE
0x1400570c8  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1400570cd  nop
0x1400570ce  lea     r11, [rsp+140h+var_s0]
0x1400570d6  mov     rbx, [r11+18h]
0x1400570da  mov     rdi, [r11+20h]
0x1400570de  mov     rsp, r11
0x1400570e1  pop     rbp
0x1400570e2  retn
```
