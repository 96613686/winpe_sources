# ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_GrantAccess::StopActivity(void)

- ea: `0x1800337c0`
- end: `0x180033aa6`
- name: `?StopActivity@GraphDriver_ProcessImage_GrantAccess@TraceProvider@Diagnostics@ComputeLegacy@@MEAAXXZ`
- size: `742`
- prototype: `void __fastcall(ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_GrantAccess *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18000a41c`
- `0x18001c384`
- `0x180021d1c`
- `0x1800337c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033827`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800339f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033827`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800339f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033a26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033a26`

## pseudocode

```c
void __fastcall ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_GrantAccess::StopActivity(
        ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_GrantAccess *this)
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
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = *((_QWORD *)ComputeLegacy::Diagnostics::TraceProvider::Instance() + 1);
    if ( *(_DWORD *)v5 > 4u
      && (*(_QWORD *)(v5 + 16) & 0x40) != 0
      && (*(_QWORD *)(v5 + 24) & 0x40LL) == *(_QWORD *)(v5 + 24) )
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
        (int)&byte_18009E5C9,
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
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = *((_QWORD *)ComputeLegacy::Diagnostics::TraceProvider::Instance() + 1);
    if ( *(_DWORD *)v6 > 4u
      && (*(_QWORD *)(v6 + 16) & 0x40) != 0
      && (*(_QWORD *)(v6 + 24) & 0x40LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v9 = *(_DWORD *)(v7 + 72);
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)&byte_18009F98F,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_GrantAccess *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800337c0  mov     [rsp-8+arg_8], rbx
0x1800337c5  mov     [rsp-8+arg_10], rdi
0x1800337ca  push    rbp
0x1800337cb  mov     rbp, rsp
0x1800337ce  sub     rsp, 140h
0x1800337d5  mov     rbx, rcx
0x1800337d8  mov     rdi, [rcx+110h]
0x1800337df  mov     eax, [rdi+48h]
0x1800337e2  test    eax, eax
0x1800337e4  jns     loc_1800339CC
0x1800337ea  add     rdi, 50h ; 'P'
0x1800337ee  cmp     eax, [rdi+8]
0x1800337f1  jnz     loc_1800339CC
0x1800337f7  test    rdi, rdi
0x1800337fa  jz      loc_1800339CC
0x180033800  mov     [rbp+SRWLock], 0
0x180033808  lea     rdx, [rbp+SRWLock]
0x18003380c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180033811  mov     rax, [rbx+110h]
0x180033818  mov     dword ptr [rax], 2
0x18003381e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180033822  test    rcx, rcx
0x180033825  jz      short loc_180033833
0x180033827  call    cs:__imp_ReleaseSRWLockExclusive
0x18003382e  nop     dword ptr [rax+rax+00h]
0x180033833  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180033838  mov     rcx, [rax+8]; int
0x18003383c  mov     eax, [rcx]
0x18003383e  cmp     eax, 4
0x180033841  jbe     loc_180033A7D
0x180033847  mov     rdx, [rcx+18h]
0x18003384b  mov     rax, [rcx+10h]
0x18003384f  test    al, 40h
0x180033851  jz      loc_180033A7D
0x180033857  mov     rax, rdx
0x18003385a  and     eax, 40h
0x18003385d  cmp     rax, rdx
0x180033860  jnz     loc_180033A7D
0x180033866  mov     rax, [rdi+30h]
0x18003386a  mov     [rbp+var_50], rax
0x18003386e  mov     eax, [rdi+44h]
0x180033871  mov     dword ptr [rbp+var_78+4], eax
0x180033874  mov     eax, [rdi+10h]
0x180033877  mov     dword ptr [rbp+var_70], eax
0x18003387a  mov     rax, [rdi+78h]
0x18003387e  mov     [rbp+var_48], rax
0x180033882  mov     rax, [rdi+70h]
0x180033886  mov     [rbp+var_40], rax
0x18003388a  mov     eax, [rdi+68h]
0x18003388d  mov     dword ptr [rbp+var_70+4], eax
0x180033890  mov     rax, [rdi+60h]
0x180033894  mov     [rbp+var_38], rax
0x180033898  mov     rax, [rdi+58h]
0x18003389c  mov     [rbp+var_30], rax
0x1800338a0  mov     eax, [rdi+50h]
0x1800338a3  mov     dword ptr [rbp+var_68], eax
0x1800338a6  mov     rax, [rdi+48h]
0x1800338aa  mov     [rbp+var_28], rax
0x1800338ae  mov     eax, [rdi+20h]
0x1800338b1  mov     dword ptr [rbp+var_68+4], eax
0x1800338b4  mov     rax, [rdi+18h]
0x1800338b8  mov     [rbp+var_20], rax
0x1800338bc  mov     eax, [rdi]
0x1800338be  mov     [rbp+var_60], eax
0x1800338c1  mov     rax, [rdi+80h]
0x1800338c8  mov     [rbp+var_18], rax
0x1800338cc  mov     eax, [rdi+40h]
0x1800338cf  mov     dword ptr [rbp+var_78], eax
0x1800338d2  mov     rax, [rdi+38h]
0x1800338d6  mov     [rbp+var_10], rax
0x1800338da  mov     eax, [rdi+8]
0x1800338dd  mov     dword ptr [rbp+SRWLock], eax
0x1800338e0  mov     [rbp+var_8], 1000000h
0x1800338e8  mov     [rbp+var_58], 0
0x1800338f0  mov     r8, [rbx+110h]
0x1800338f7  add     r8, 8; int
0x1800338fb  lea     rax, [rbp+var_50]
0x1800338ff  mov     [rsp+140h+var_90], rax; __int64
0x180033907  lea     rax, [rbp+var_78+4]
0x18003390b  mov     [rsp+140h+var_98], rax; __int64
0x180033913  lea     rax, [rbp+var_70]
0x180033917  mov     [rsp+140h+var_A0], rax; __int64
0x18003391f  lea     rax, [rbp+var_48]
0x180033923  mov     [rsp+140h+var_A8], rax; __int64
0x18003392b  lea     rax, [rbp+var_40]
0x18003392f  mov     [rsp+140h+var_B0], rax; __int64
0x180033937  lea     rax, [rbp+var_70+4]
0x18003393b  mov     [rsp+140h+var_B8], rax; __int64
0x180033943  lea     rax, [rbp+var_38]
0x180033947  mov     [rsp+140h+var_C0], rax; __int64
0x18003394f  lea     rax, [rbp+var_30]
0x180033953  mov     [rsp+140h+var_C8], rax; __int64
0x180033958  lea     rax, [rbp+var_68]
0x18003395c  mov     [rsp+140h+var_D0], rax; __int64
0x180033961  lea     rax, [rbp+var_28]
0x180033965  mov     [rsp+140h+var_D8], rax; __int64
0x18003396a  lea     rax, [rbp+var_68+4]
0x18003396e  mov     [rsp+140h+var_E0], rax; __int64
0x180033973  lea     rax, [rbp+var_20]
0x180033977  mov     [rsp+140h+var_E8], rax; __int64
0x18003397c  lea     rax, [rbp+var_60]
0x180033980  mov     [rsp+140h+var_F0], rax; __int64
0x180033985  lea     rax, [rbp+var_18]
0x180033989  mov     [rsp+140h+var_F8], rax; __int64
0x18003398e  lea     rax, [rbp+var_78]
0x180033992  mov     [rsp+140h+var_100], rax; __int64
0x180033997  lea     rax, [rbp+var_10]
0x18003399b  mov     [rsp+140h+var_108], rax; __int64
0x1800339a0  lea     rax, [rbp+SRWLock]
0x1800339a4  mov     [rsp+140h+var_110], rax; __int64
0x1800339a9  lea     rax, [rbp+var_8]
0x1800339ad  mov     [rsp+140h+var_118], rax; __int64
0x1800339b2  lea     rax, [rbp+var_58]
0x1800339b6  mov     [rsp+140h+var_120], rax; __int64
0x1800339bb  lea     rdx, byte_18009E5C9; int
0x1800339c2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800339c7  jmp     loc_180033A7D
0x1800339cc  mov     [rbp+SRWLock], 0
0x1800339d4  lea     rdx, [rbp+SRWLock]
0x1800339d8  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800339dd  mov     rax, [rbx+110h]
0x1800339e4  mov     dword ptr [rax], 2
0x1800339ea  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800339ee  test    rcx, rcx
0x1800339f1  jz      short loc_1800339FF
0x1800339f3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800339fa  nop     dword ptr [rax+rax+00h]
0x1800339ff  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180033a04  mov     rdi, [rax+8]
0x180033a08  mov     eax, [rdi]
0x180033a0a  cmp     eax, 4
0x180033a0d  jbe     short loc_180033A7D
0x180033a0f  mov     rcx, [rdi+18h]
0x180033a13  mov     rax, [rdi+10h]
0x180033a17  test    al, 40h
0x180033a19  jz      short loc_180033A7D
0x180033a1b  mov     rax, rcx
0x180033a1e  and     eax, 40h
0x180033a21  cmp     rax, rcx
0x180033a24  jnz     short loc_180033A7D
0x180033a26  call    cs:__imp_GetCurrentThreadId
0x180033a2d  nop     dword ptr [rax+rax+00h]
0x180033a32  mov     dword ptr [rbp+SRWLock], eax
0x180033a35  mov     r8, [rbx+110h]
0x180033a3c  mov     eax, [r8+48h]
0x180033a40  mov     dword ptr [rbp+var_78], eax
0x180033a43  mov     [rbp+var_58], 0
0x180033a4b  add     r8, 8
0x180033a4f  lea     rax, [rbp+SRWLock]
0x180033a53  mov     [rsp+140h+var_110], rax
0x180033a58  lea     rax, [rbp+var_78]
0x180033a5c  mov     [rsp+140h+var_118], rax
0x180033a61  lea     rax, [rbp+var_58]
0x180033a65  mov     [rsp+140h+var_120], rax
0x180033a6a  xor     r9d, r9d
0x180033a6d  lea     rdx, byte_18009F98F
0x180033a74  mov     rcx, rdi
0x180033a77  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180033a7c  nop
0x180033a7d  lea     rcx, [rbx+120h]; this
0x180033a84  cmp     dword ptr [rcx+18h], 0
0x180033a88  jz      short loc_180033A90
0x180033a8a  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180033a8f  nop
0x180033a90  lea     r11, [rsp+140h+var_s0]
0x180033a98  mov     rbx, [r11+18h]
0x180033a9c  mov     rdi, [r11+20h]
0x180033aa0  mov     rsp, r11
0x180033aa3  pop     rbp
0x180033aa4  retn
```
