# ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_CreateVhd::StopActivity(void)

- ea: `0x1800334d0`
- end: `0x1800337b6`
- name: `?StopActivity@GraphDriver_ProcessImage_CreateVhd@TraceProvider@Diagnostics@ComputeLegacy@@MEAAXXZ`
- size: `742`
- prototype: `void __fastcall(ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_CreateVhd *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18000a41c`
- `0x18001c384`
- `0x180021d1c`
- `0x1800334d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033537`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033703`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033537`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033703`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033736`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033736`

## pseudocode

```c
void __fastcall ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_CreateVhd::StopActivity(
        ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_CreateVhd *this)
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
        (int)&byte_18009F60D,
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
        (unsigned int)word_18009F302,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_CreateVhd *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800334d0  mov     [rsp-8+arg_8], rbx
0x1800334d5  mov     [rsp-8+arg_10], rdi
0x1800334da  push    rbp
0x1800334db  mov     rbp, rsp
0x1800334de  sub     rsp, 140h
0x1800334e5  mov     rbx, rcx
0x1800334e8  mov     rdi, [rcx+110h]
0x1800334ef  mov     eax, [rdi+48h]
0x1800334f2  test    eax, eax
0x1800334f4  jns     loc_1800336DC
0x1800334fa  add     rdi, 50h ; 'P'
0x1800334fe  cmp     eax, [rdi+8]
0x180033501  jnz     loc_1800336DC
0x180033507  test    rdi, rdi
0x18003350a  jz      loc_1800336DC
0x180033510  mov     [rbp+SRWLock], 0
0x180033518  lea     rdx, [rbp+SRWLock]
0x18003351c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180033521  mov     rax, [rbx+110h]
0x180033528  mov     dword ptr [rax], 2
0x18003352e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180033532  test    rcx, rcx
0x180033535  jz      short loc_180033543
0x180033537  call    cs:__imp_ReleaseSRWLockExclusive
0x18003353e  nop     dword ptr [rax+rax+00h]
0x180033543  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180033548  mov     rcx, [rax+8]; int
0x18003354c  mov     eax, [rcx]
0x18003354e  cmp     eax, 4
0x180033551  jbe     loc_18003378D
0x180033557  mov     rdx, [rcx+18h]
0x18003355b  mov     rax, [rcx+10h]
0x18003355f  test    al, 40h
0x180033561  jz      loc_18003378D
0x180033567  mov     rax, rdx
0x18003356a  and     eax, 40h
0x18003356d  cmp     rax, rdx
0x180033570  jnz     loc_18003378D
0x180033576  mov     rax, [rdi+30h]
0x18003357a  mov     [rbp+var_50], rax
0x18003357e  mov     eax, [rdi+44h]
0x180033581  mov     dword ptr [rbp+var_78+4], eax
0x180033584  mov     eax, [rdi+10h]
0x180033587  mov     dword ptr [rbp+var_70], eax
0x18003358a  mov     rax, [rdi+78h]
0x18003358e  mov     [rbp+var_48], rax
0x180033592  mov     rax, [rdi+70h]
0x180033596  mov     [rbp+var_40], rax
0x18003359a  mov     eax, [rdi+68h]
0x18003359d  mov     dword ptr [rbp+var_70+4], eax
0x1800335a0  mov     rax, [rdi+60h]
0x1800335a4  mov     [rbp+var_38], rax
0x1800335a8  mov     rax, [rdi+58h]
0x1800335ac  mov     [rbp+var_30], rax
0x1800335b0  mov     eax, [rdi+50h]
0x1800335b3  mov     dword ptr [rbp+var_68], eax
0x1800335b6  mov     rax, [rdi+48h]
0x1800335ba  mov     [rbp+var_28], rax
0x1800335be  mov     eax, [rdi+20h]
0x1800335c1  mov     dword ptr [rbp+var_68+4], eax
0x1800335c4  mov     rax, [rdi+18h]
0x1800335c8  mov     [rbp+var_20], rax
0x1800335cc  mov     eax, [rdi]
0x1800335ce  mov     [rbp+var_60], eax
0x1800335d1  mov     rax, [rdi+80h]
0x1800335d8  mov     [rbp+var_18], rax
0x1800335dc  mov     eax, [rdi+40h]
0x1800335df  mov     dword ptr [rbp+var_78], eax
0x1800335e2  mov     rax, [rdi+38h]
0x1800335e6  mov     [rbp+var_10], rax
0x1800335ea  mov     eax, [rdi+8]
0x1800335ed  mov     dword ptr [rbp+SRWLock], eax
0x1800335f0  mov     [rbp+var_8], 1000000h
0x1800335f8  mov     [rbp+var_58], 0
0x180033600  mov     r8, [rbx+110h]
0x180033607  add     r8, 8; int
0x18003360b  lea     rax, [rbp+var_50]
0x18003360f  mov     [rsp+140h+var_90], rax; __int64
0x180033617  lea     rax, [rbp+var_78+4]
0x18003361b  mov     [rsp+140h+var_98], rax; __int64
0x180033623  lea     rax, [rbp+var_70]
0x180033627  mov     [rsp+140h+var_A0], rax; __int64
0x18003362f  lea     rax, [rbp+var_48]
0x180033633  mov     [rsp+140h+var_A8], rax; __int64
0x18003363b  lea     rax, [rbp+var_40]
0x18003363f  mov     [rsp+140h+var_B0], rax; __int64
0x180033647  lea     rax, [rbp+var_70+4]
0x18003364b  mov     [rsp+140h+var_B8], rax; __int64
0x180033653  lea     rax, [rbp+var_38]
0x180033657  mov     [rsp+140h+var_C0], rax; __int64
0x18003365f  lea     rax, [rbp+var_30]
0x180033663  mov     [rsp+140h+var_C8], rax; __int64
0x180033668  lea     rax, [rbp+var_68]
0x18003366c  mov     [rsp+140h+var_D0], rax; __int64
0x180033671  lea     rax, [rbp+var_28]
0x180033675  mov     [rsp+140h+var_D8], rax; __int64
0x18003367a  lea     rax, [rbp+var_68+4]
0x18003367e  mov     [rsp+140h+var_E0], rax; __int64
0x180033683  lea     rax, [rbp+var_20]
0x180033687  mov     [rsp+140h+var_E8], rax; __int64
0x18003368c  lea     rax, [rbp+var_60]
0x180033690  mov     [rsp+140h+var_F0], rax; __int64
0x180033695  lea     rax, [rbp+var_18]
0x180033699  mov     [rsp+140h+var_F8], rax; __int64
0x18003369e  lea     rax, [rbp+var_78]
0x1800336a2  mov     [rsp+140h+var_100], rax; __int64
0x1800336a7  lea     rax, [rbp+var_10]
0x1800336ab  mov     [rsp+140h+var_108], rax; __int64
0x1800336b0  lea     rax, [rbp+SRWLock]
0x1800336b4  mov     [rsp+140h+var_110], rax; __int64
0x1800336b9  lea     rax, [rbp+var_8]
0x1800336bd  mov     [rsp+140h+var_118], rax; __int64
0x1800336c2  lea     rax, [rbp+var_58]
0x1800336c6  mov     [rsp+140h+var_120], rax; __int64
0x1800336cb  lea     rdx, byte_18009F60D; int
0x1800336d2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800336d7  jmp     loc_18003378D
0x1800336dc  mov     [rbp+SRWLock], 0
0x1800336e4  lea     rdx, [rbp+SRWLock]
0x1800336e8  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800336ed  mov     rax, [rbx+110h]
0x1800336f4  mov     dword ptr [rax], 2
0x1800336fa  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800336fe  test    rcx, rcx
0x180033701  jz      short loc_18003370F
0x180033703  call    cs:__imp_ReleaseSRWLockExclusive
0x18003370a  nop     dword ptr [rax+rax+00h]
0x18003370f  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180033714  mov     rdi, [rax+8]
0x180033718  mov     eax, [rdi]
0x18003371a  cmp     eax, 4
0x18003371d  jbe     short loc_18003378D
0x18003371f  mov     rcx, [rdi+18h]
0x180033723  mov     rax, [rdi+10h]
0x180033727  test    al, 40h
0x180033729  jz      short loc_18003378D
0x18003372b  mov     rax, rcx
0x18003372e  and     eax, 40h
0x180033731  cmp     rax, rcx
0x180033734  jnz     short loc_18003378D
0x180033736  call    cs:__imp_GetCurrentThreadId
0x18003373d  nop     dword ptr [rax+rax+00h]
0x180033742  mov     dword ptr [rbp+SRWLock], eax
0x180033745  mov     r8, [rbx+110h]
0x18003374c  mov     eax, [r8+48h]
0x180033750  mov     dword ptr [rbp+var_78], eax
0x180033753  mov     [rbp+var_58], 0
0x18003375b  add     r8, 8
0x18003375f  lea     rax, [rbp+SRWLock]
0x180033763  mov     [rsp+140h+var_110], rax
0x180033768  lea     rax, [rbp+var_78]
0x18003376c  mov     [rsp+140h+var_118], rax
0x180033771  lea     rax, [rbp+var_58]
0x180033775  mov     [rsp+140h+var_120], rax
0x18003377a  xor     r9d, r9d
0x18003377d  lea     rdx, word_18009F302
0x180033784  mov     rcx, rdi
0x180033787  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003378c  nop
0x18003378d  lea     rcx, [rbx+120h]; this
0x180033794  cmp     dword ptr [rcx+18h], 0
0x180033798  jz      short loc_1800337A0
0x18003379a  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18003379f  nop
0x1800337a0  lea     r11, [rsp+140h+var_s0]
0x1800337a8  mov     rbx, [r11+18h]
0x1800337ac  mov     rdi, [r11+20h]
0x1800337b0  mov     rsp, r11
0x1800337b3  pop     rbp
0x1800337b4  retn
```
