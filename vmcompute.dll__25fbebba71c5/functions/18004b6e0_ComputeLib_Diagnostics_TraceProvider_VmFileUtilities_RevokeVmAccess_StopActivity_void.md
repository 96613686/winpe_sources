# ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_RevokeVmAccess::StopActivity(void)

- ea: `0x18004b6e0`
- end: `0x18004b9c9`
- name: `?StopActivity@VmFileUtilities_RevokeVmAccess@TraceProvider@Diagnostics@ComputeLib@@MEAAXXZ`
- size: `745`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_RevokeVmAccess *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18001c384`
- `0x18001ed48`
- `0x180021d1c`
- `0x18004b6e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b747`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b916`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b747`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b916`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004b949`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004b949`

## pseudocode

```c
void __fastcall ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_RevokeVmAccess::StopActivity(
        ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_RevokeVmAccess *this)
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
    v5 = ComputeLib::Diagnostics::TraceProvider::Provider();
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
          (int)&word_1800A14E6,
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
    v8 = ComputeLib::Diagnostics::TraceProvider::Provider();
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
          (unsigned int)&word_1800A1266,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_RevokeVmAccess *)((char *)this + 288));
}

```

## disassembly

```asm
0x18004b6e0  mov     [rsp-8+arg_8], rbx
0x18004b6e5  mov     [rsp-8+arg_10], rdi
0x18004b6ea  push    rbp
0x18004b6eb  mov     rbp, rsp
0x18004b6ee  sub     rsp, 140h
0x18004b6f5  mov     rbx, rcx
0x18004b6f8  mov     rdi, [rcx+110h]
0x18004b6ff  mov     eax, [rdi+48h]
0x18004b702  test    eax, eax
0x18004b704  jns     loc_18004B8EF
0x18004b70a  add     rdi, 50h ; 'P'
0x18004b70e  cmp     eax, [rdi+8]
0x18004b711  jnz     loc_18004B8EF
0x18004b717  test    rdi, rdi
0x18004b71a  jz      loc_18004B8EF
0x18004b720  mov     [rbp+SRWLock], 0
0x18004b728  lea     rdx, [rbp+SRWLock]
0x18004b72c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004b731  mov     rax, [rbx+110h]
0x18004b738  mov     dword ptr [rax], 2
0x18004b73e  mov     rcx, [rbp+SRWLock]; SRWLock
0x18004b742  test    rcx, rcx
0x18004b745  jz      short loc_18004B753
0x18004b747  call    cs:__imp_ReleaseSRWLockExclusive
0x18004b74e  nop     dword ptr [rax+rax+00h]
0x18004b753  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18004b758  mov     r9, rax
0x18004b75b  mov     ecx, [rax]
0x18004b75d  cmp     ecx, 4
0x18004b760  jbe     loc_18004B9A0
0x18004b766  mov     rax, [rax+18h]
0x18004b76a  mov     rcx, [r9+10h]
0x18004b76e  test    cl, 40h
0x18004b771  jz      loc_18004B9A0
0x18004b777  mov     rcx, rax
0x18004b77a  and     ecx, 40h
0x18004b77d  cmp     rcx, rax
0x18004b780  jnz     loc_18004B9A0
0x18004b786  mov     rax, [rdi+30h]
0x18004b78a  mov     [rbp+var_50], rax
0x18004b78e  mov     eax, [rdi+44h]
0x18004b791  mov     dword ptr [rbp+var_78+4], eax
0x18004b794  mov     eax, [rdi+10h]
0x18004b797  mov     dword ptr [rbp+var_70], eax
0x18004b79a  mov     rax, [rdi+78h]
0x18004b79e  mov     [rbp+var_48], rax
0x18004b7a2  mov     rax, [rdi+70h]
0x18004b7a6  mov     [rbp+var_40], rax
0x18004b7aa  mov     eax, [rdi+68h]
0x18004b7ad  mov     dword ptr [rbp+var_70+4], eax
0x18004b7b0  mov     rax, [rdi+60h]
0x18004b7b4  mov     [rbp+var_38], rax
0x18004b7b8  mov     rax, [rdi+58h]
0x18004b7bc  mov     [rbp+var_30], rax
0x18004b7c0  mov     eax, [rdi+50h]
0x18004b7c3  mov     dword ptr [rbp+var_68], eax
0x18004b7c6  mov     rax, [rdi+48h]
0x18004b7ca  mov     [rbp+var_28], rax
0x18004b7ce  mov     eax, [rdi+20h]
0x18004b7d1  mov     dword ptr [rbp+var_68+4], eax
0x18004b7d4  mov     rax, [rdi+18h]
0x18004b7d8  mov     [rbp+var_20], rax
0x18004b7dc  mov     eax, [rdi]
0x18004b7de  mov     [rbp+var_60], eax
0x18004b7e1  mov     rax, [rdi+80h]
0x18004b7e8  mov     [rbp+var_18], rax
0x18004b7ec  mov     eax, [rdi+40h]
0x18004b7ef  mov     dword ptr [rbp+var_78], eax
0x18004b7f2  mov     rax, [rdi+38h]
0x18004b7f6  mov     [rbp+var_10], rax
0x18004b7fa  mov     eax, [rdi+8]
0x18004b7fd  mov     dword ptr [rbp+SRWLock], eax
0x18004b800  mov     [rbp+var_8], 1000000h
0x18004b808  mov     [rbp+var_58], 0
0x18004b810  mov     r8, [rbx+110h]
0x18004b817  add     r8, 8; int
0x18004b81b  lea     rax, [rbp+var_50]
0x18004b81f  mov     [rsp+140h+var_90], rax; __int64
0x18004b827  lea     rax, [rbp+var_78+4]
0x18004b82b  mov     [rsp+140h+var_98], rax; __int64
0x18004b833  lea     rax, [rbp+var_70]
0x18004b837  mov     [rsp+140h+var_A0], rax; __int64
0x18004b83f  lea     rax, [rbp+var_48]
0x18004b843  mov     [rsp+140h+var_A8], rax; __int64
0x18004b84b  lea     rax, [rbp+var_40]
0x18004b84f  mov     [rsp+140h+var_B0], rax; __int64
0x18004b857  lea     rax, [rbp+var_70+4]
0x18004b85b  mov     [rsp+140h+var_B8], rax; __int64
0x18004b863  lea     rax, [rbp+var_38]
0x18004b867  mov     [rsp+140h+var_C0], rax; __int64
0x18004b86f  lea     rax, [rbp+var_30]
0x18004b873  mov     [rsp+140h+var_C8], rax; __int64
0x18004b878  lea     rax, [rbp+var_68]
0x18004b87c  mov     [rsp+140h+var_D0], rax; __int64
0x18004b881  lea     rax, [rbp+var_28]
0x18004b885  mov     [rsp+140h+var_D8], rax; __int64
0x18004b88a  lea     rax, [rbp+var_68+4]
0x18004b88e  mov     [rsp+140h+var_E0], rax; __int64
0x18004b893  lea     rax, [rbp+var_20]
0x18004b897  mov     [rsp+140h+var_E8], rax; __int64
0x18004b89c  lea     rax, [rbp+var_60]
0x18004b8a0  mov     [rsp+140h+var_F0], rax; __int64
0x18004b8a5  lea     rax, [rbp+var_18]
0x18004b8a9  mov     [rsp+140h+var_F8], rax; __int64
0x18004b8ae  lea     rax, [rbp+var_78]
0x18004b8b2  mov     [rsp+140h+var_100], rax; __int64
0x18004b8b7  lea     rax, [rbp+var_10]
0x18004b8bb  mov     [rsp+140h+var_108], rax; __int64
0x18004b8c0  lea     rax, [rbp+SRWLock]
0x18004b8c4  mov     [rsp+140h+var_110], rax; __int64
0x18004b8c9  lea     rax, [rbp+var_8]
0x18004b8cd  mov     [rsp+140h+var_118], rax; __int64
0x18004b8d2  lea     rax, [rbp+var_58]
0x18004b8d6  mov     [rsp+140h+var_120], rax; __int64
0x18004b8db  lea     rdx, word_1800A14E6; int
0x18004b8e2  mov     rcx, r9; int
0x18004b8e5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18004b8ea  jmp     loc_18004B9A0
0x18004b8ef  mov     [rbp+SRWLock], 0
0x18004b8f7  lea     rdx, [rbp+SRWLock]
0x18004b8fb  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004b900  mov     rax, [rbx+110h]
0x18004b907  mov     dword ptr [rax], 2
0x18004b90d  mov     rcx, [rbp+SRWLock]; SRWLock
0x18004b911  test    rcx, rcx
0x18004b914  jz      short loc_18004B922
0x18004b916  call    cs:__imp_ReleaseSRWLockExclusive
0x18004b91d  nop     dword ptr [rax+rax+00h]
0x18004b922  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18004b927  mov     rdi, rax
0x18004b92a  mov     ecx, [rax]
0x18004b92c  cmp     ecx, 4
0x18004b92f  jbe     short loc_18004B9A0
0x18004b931  mov     rax, [rax+18h]
0x18004b935  mov     rcx, [rdi+10h]
0x18004b939  test    cl, 40h
0x18004b93c  jz      short loc_18004B9A0
0x18004b93e  mov     rcx, rax
0x18004b941  and     ecx, 40h
0x18004b944  cmp     rcx, rax
0x18004b947  jnz     short loc_18004B9A0
0x18004b949  call    cs:__imp_GetCurrentThreadId
0x18004b950  nop     dword ptr [rax+rax+00h]
0x18004b955  mov     dword ptr [rbp+SRWLock], eax
0x18004b958  mov     r8, [rbx+110h]
0x18004b95f  mov     eax, [r8+48h]
0x18004b963  mov     dword ptr [rbp+var_78], eax
0x18004b966  mov     [rbp+var_58], 0
0x18004b96e  add     r8, 8
0x18004b972  lea     rax, [rbp+SRWLock]
0x18004b976  mov     [rsp+140h+var_110], rax
0x18004b97b  lea     rax, [rbp+var_78]
0x18004b97f  mov     [rsp+140h+var_118], rax
0x18004b984  lea     rax, [rbp+var_58]
0x18004b988  mov     [rsp+140h+var_120], rax
0x18004b98d  xor     r9d, r9d
0x18004b990  lea     rdx, word_1800A1266
0x18004b997  mov     rcx, rdi
0x18004b99a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004b99f  nop
0x18004b9a0  lea     rcx, [rbx+120h]; this
0x18004b9a7  cmp     dword ptr [rcx+18h], 0
0x18004b9ab  jz      short loc_18004B9B3
0x18004b9ad  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18004b9b2  nop
0x18004b9b3  lea     r11, [rsp+140h+var_s0]
0x18004b9bb  mov     rbx, [r11+18h]
0x18004b9bf  mov     rdi, [r11+20h]
0x18004b9c3  mov     rsp, r11
0x18004b9c6  pop     rbp
0x18004b9c7  retn
```
