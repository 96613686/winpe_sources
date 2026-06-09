# ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateBaseVhd::StopActivity(void)

- ea: `0x18005e2e0`
- end: `0x18005e5c9`
- name: `?StopActivity@GraphDriver_CreateBaseVhd@TraceProvider@Diagnostics@ComputeService@@MEAAXXZ`
- size: `745`
- prototype: `void __fastcall(ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateBaseVhd *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18001c384`
- `0x180021d1c`
- `0x18005dc20`
- `0x18005e2e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e347`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e516`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e347`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e516`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e549`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e549`

## pseudocode

```c
void __fastcall ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateBaseVhd::StopActivity(
        ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateBaseVhd *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // r9
  __int64 v7; // rax
  const struct _tlgProvider_t *v8; // rax
  const struct _tlgProvider_t *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  PSRWLOCK SRWLock; // [rsp+C0h] [rbp-80h] BYREF
  int v13; // [rsp+C8h] [rbp-78h] BYREF
  int v14; // [rsp+CCh] [rbp-74h] BYREF
  int v15; // [rsp+D0h] [rbp-70h] BYREF
  int v16; // [rsp+D4h] [rbp-6Ch] BYREF
  int v17; // [rsp+D8h] [rbp-68h] BYREF
  int v18; // [rsp+DCh] [rbp-64h] BYREF
  int v19; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v20; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v21; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v22; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v23; // [rsp+100h] [rbp-40h] BYREF
  __int64 v24; // [rsp+108h] [rbp-38h] BYREF
  __int64 v25; // [rsp+110h] [rbp-30h] BYREF
  __int64 v26; // [rsp+118h] [rbp-28h] BYREF
  __int64 v27; // [rsp+120h] [rbp-20h] BYREF
  __int64 v28; // [rsp+128h] [rbp-18h] BYREF
  __int64 v29; // [rsp+130h] [rbp-10h] BYREF
  __int64 v30; // [rsp+138h] [rbp-8h] BYREF

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
    v5 = ComputeService::Diagnostics::TraceProvider::Provider();
    v6 = v5;
    if ( *(_DWORD *)v5 > 4u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v6 + 2) & 0x40) != 0 && (v7 & 0x40) == v7 )
      {
        v21 = *((_QWORD *)v4 + 6);
        v14 = v4[17];
        v15 = v4[4];
        v22 = *((_QWORD *)v4 + 15);
        v23 = *((_QWORD *)v4 + 14);
        v16 = v4[26];
        v24 = *((_QWORD *)v4 + 12);
        v25 = *((_QWORD *)v4 + 11);
        v17 = v4[20];
        v26 = *((_QWORD *)v4 + 9);
        v18 = v4[8];
        v27 = *((_QWORD *)v4 + 3);
        v19 = *v4;
        v28 = *((_QWORD *)v4 + 16);
        v13 = v4[16];
        v29 = *((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v30 = 0x1000000;
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (int)v6,
          (int)&byte_1800A2207,
          *((_QWORD *)this + 34) + 8,
          (__int64)&v20,
          (__int64)&v30,
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
          (__int64)&v15,
          (__int64)&v14,
          (__int64)&v21);
      }
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
    v8 = ComputeService::Diagnostics::TraceProvider::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 4u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x40) != 0 && (v10 & 0x40) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v13 = *(_DWORD *)(v11 + 72);
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v9,
          (unsigned int)byte_1800A1DE3,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeService::Diagnostics::TraceProvider::GraphDriver_CreateBaseVhd *)((char *)this + 288));
}

```

## disassembly

```asm
0x18005e2e0  mov     [rsp-8+arg_8], rbx
0x18005e2e5  mov     [rsp-8+arg_10], rdi
0x18005e2ea  push    rbp
0x18005e2eb  mov     rbp, rsp
0x18005e2ee  sub     rsp, 140h
0x18005e2f5  mov     rbx, rcx
0x18005e2f8  mov     rdi, [rcx+110h]
0x18005e2ff  mov     eax, [rdi+48h]
0x18005e302  test    eax, eax
0x18005e304  jns     loc_18005E4EF
0x18005e30a  add     rdi, 50h ; 'P'
0x18005e30e  cmp     eax, [rdi+8]
0x18005e311  jnz     loc_18005E4EF
0x18005e317  test    rdi, rdi
0x18005e31a  jz      loc_18005E4EF
0x18005e320  mov     [rbp+SRWLock], 0
0x18005e328  lea     rdx, [rbp+SRWLock]
0x18005e32c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18005e331  mov     rax, [rbx+110h]
0x18005e338  mov     dword ptr [rax], 2
0x18005e33e  mov     rcx, [rbp+SRWLock]; SRWLock
0x18005e342  test    rcx, rcx
0x18005e345  jz      short loc_18005E353
0x18005e347  call    cs:__imp_ReleaseSRWLockExclusive
0x18005e34e  nop     dword ptr [rax+rax+00h]
0x18005e353  call    ?Provider@TraceProvider@Diagnostics@ComputeService@@SAPEBU_tlgProvider_t@@XZ; ComputeService::Diagnostics::TraceProvider::Provider(void)
0x18005e358  mov     r9, rax
0x18005e35b  mov     ecx, [rax]
0x18005e35d  cmp     ecx, 4
0x18005e360  jbe     loc_18005E5A0
0x18005e366  mov     rax, [rax+18h]
0x18005e36a  mov     rcx, [r9+10h]
0x18005e36e  test    cl, 40h
0x18005e371  jz      loc_18005E5A0
0x18005e377  mov     rcx, rax
0x18005e37a  and     ecx, 40h
0x18005e37d  cmp     rcx, rax
0x18005e380  jnz     loc_18005E5A0
0x18005e386  mov     rax, [rdi+30h]
0x18005e38a  mov     [rbp+var_50], rax
0x18005e38e  mov     eax, [rdi+44h]
0x18005e391  mov     dword ptr [rbp+var_78+4], eax
0x18005e394  mov     eax, [rdi+10h]
0x18005e397  mov     dword ptr [rbp+var_70], eax
0x18005e39a  mov     rax, [rdi+78h]
0x18005e39e  mov     [rbp+var_48], rax
0x18005e3a2  mov     rax, [rdi+70h]
0x18005e3a6  mov     [rbp+var_40], rax
0x18005e3aa  mov     eax, [rdi+68h]
0x18005e3ad  mov     dword ptr [rbp+var_70+4], eax
0x18005e3b0  mov     rax, [rdi+60h]
0x18005e3b4  mov     [rbp+var_38], rax
0x18005e3b8  mov     rax, [rdi+58h]
0x18005e3bc  mov     [rbp+var_30], rax
0x18005e3c0  mov     eax, [rdi+50h]
0x18005e3c3  mov     dword ptr [rbp+var_68], eax
0x18005e3c6  mov     rax, [rdi+48h]
0x18005e3ca  mov     [rbp+var_28], rax
0x18005e3ce  mov     eax, [rdi+20h]
0x18005e3d1  mov     dword ptr [rbp+var_68+4], eax
0x18005e3d4  mov     rax, [rdi+18h]
0x18005e3d8  mov     [rbp+var_20], rax
0x18005e3dc  mov     eax, [rdi]
0x18005e3de  mov     [rbp+var_60], eax
0x18005e3e1  mov     rax, [rdi+80h]
0x18005e3e8  mov     [rbp+var_18], rax
0x18005e3ec  mov     eax, [rdi+40h]
0x18005e3ef  mov     dword ptr [rbp+var_78], eax
0x18005e3f2  mov     rax, [rdi+38h]
0x18005e3f6  mov     [rbp+var_10], rax
0x18005e3fa  mov     eax, [rdi+8]
0x18005e3fd  mov     dword ptr [rbp+SRWLock], eax
0x18005e400  mov     [rbp+var_8], 1000000h
0x18005e408  mov     [rbp+var_58], 0
0x18005e410  mov     r8, [rbx+110h]
0x18005e417  add     r8, 8; int
0x18005e41b  lea     rax, [rbp+var_50]
0x18005e41f  mov     [rsp+140h+var_90], rax; __int64
0x18005e427  lea     rax, [rbp+var_78+4]
0x18005e42b  mov     [rsp+140h+var_98], rax; __int64
0x18005e433  lea     rax, [rbp+var_70]
0x18005e437  mov     [rsp+140h+var_A0], rax; __int64
0x18005e43f  lea     rax, [rbp+var_48]
0x18005e443  mov     [rsp+140h+var_A8], rax; __int64
0x18005e44b  lea     rax, [rbp+var_40]
0x18005e44f  mov     [rsp+140h+var_B0], rax; __int64
0x18005e457  lea     rax, [rbp+var_70+4]
0x18005e45b  mov     [rsp+140h+var_B8], rax; __int64
0x18005e463  lea     rax, [rbp+var_38]
0x18005e467  mov     [rsp+140h+var_C0], rax; __int64
0x18005e46f  lea     rax, [rbp+var_30]
0x18005e473  mov     [rsp+140h+var_C8], rax; __int64
0x18005e478  lea     rax, [rbp+var_68]
0x18005e47c  mov     [rsp+140h+var_D0], rax; __int64
0x18005e481  lea     rax, [rbp+var_28]
0x18005e485  mov     [rsp+140h+var_D8], rax; __int64
0x18005e48a  lea     rax, [rbp+var_68+4]
0x18005e48e  mov     [rsp+140h+var_E0], rax; __int64
0x18005e493  lea     rax, [rbp+var_20]
0x18005e497  mov     [rsp+140h+var_E8], rax; __int64
0x18005e49c  lea     rax, [rbp+var_60]
0x18005e4a0  mov     [rsp+140h+var_F0], rax; __int64
0x18005e4a5  lea     rax, [rbp+var_18]
0x18005e4a9  mov     [rsp+140h+var_F8], rax; __int64
0x18005e4ae  lea     rax, [rbp+var_78]
0x18005e4b2  mov     [rsp+140h+var_100], rax; __int64
0x18005e4b7  lea     rax, [rbp+var_10]
0x18005e4bb  mov     [rsp+140h+var_108], rax; __int64
0x18005e4c0  lea     rax, [rbp+SRWLock]
0x18005e4c4  mov     [rsp+140h+var_110], rax; __int64
0x18005e4c9  lea     rax, [rbp+var_8]
0x18005e4cd  mov     [rsp+140h+var_118], rax; __int64
0x18005e4d2  lea     rax, [rbp+var_58]
0x18005e4d6  mov     [rsp+140h+var_120], rax; __int64
0x18005e4db  lea     rdx, byte_1800A2207; int
0x18005e4e2  mov     rcx, r9; int
0x18005e4e5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18005e4ea  jmp     loc_18005E5A0
0x18005e4ef  mov     [rbp+SRWLock], 0
0x18005e4f7  lea     rdx, [rbp+SRWLock]
0x18005e4fb  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18005e500  mov     rax, [rbx+110h]
0x18005e507  mov     dword ptr [rax], 2
0x18005e50d  mov     rcx, [rbp+SRWLock]; SRWLock
0x18005e511  test    rcx, rcx
0x18005e514  jz      short loc_18005E522
0x18005e516  call    cs:__imp_ReleaseSRWLockExclusive
0x18005e51d  nop     dword ptr [rax+rax+00h]
0x18005e522  call    ?Provider@TraceProvider@Diagnostics@ComputeService@@SAPEBU_tlgProvider_t@@XZ; ComputeService::Diagnostics::TraceProvider::Provider(void)
0x18005e527  mov     rdi, rax
0x18005e52a  mov     ecx, [rax]
0x18005e52c  cmp     ecx, 4
0x18005e52f  jbe     short loc_18005E5A0
0x18005e531  mov     rax, [rax+18h]
0x18005e535  mov     rcx, [rdi+10h]
0x18005e539  test    cl, 40h
0x18005e53c  jz      short loc_18005E5A0
0x18005e53e  mov     rcx, rax
0x18005e541  and     ecx, 40h
0x18005e544  cmp     rcx, rax
0x18005e547  jnz     short loc_18005E5A0
0x18005e549  call    cs:__imp_GetCurrentThreadId
0x18005e550  nop     dword ptr [rax+rax+00h]
0x18005e555  mov     dword ptr [rbp+SRWLock], eax
0x18005e558  mov     r8, [rbx+110h]
0x18005e55f  mov     eax, [r8+48h]
0x18005e563  mov     dword ptr [rbp+var_78], eax
0x18005e566  mov     [rbp+var_58], 0
0x18005e56e  add     r8, 8
0x18005e572  lea     rax, [rbp+SRWLock]
0x18005e576  mov     [rsp+140h+var_110], rax
0x18005e57b  lea     rax, [rbp+var_78]
0x18005e57f  mov     [rsp+140h+var_118], rax
0x18005e584  lea     rax, [rbp+var_58]
0x18005e588  mov     [rsp+140h+var_120], rax
0x18005e58d  xor     r9d, r9d
0x18005e590  lea     rdx, byte_1800A1DE3
0x18005e597  mov     rcx, rdi
0x18005e59a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005e59f  nop
0x18005e5a0  lea     rcx, [rbx+120h]; this
0x18005e5a7  cmp     dword ptr [rcx+18h], 0
0x18005e5ab  jz      short loc_18005E5B3
0x18005e5ad  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18005e5b2  nop
0x18005e5b3  lea     r11, [rsp+140h+var_s0]
0x18005e5bb  mov     rbx, [r11+18h]
0x18005e5bf  mov     rdi, [r11+20h]
0x18005e5c3  mov     rsp, r11
0x18005e5c6  pop     rbp
0x18005e5c7  retn
```
