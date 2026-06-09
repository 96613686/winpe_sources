# ComputeService::Diagnostics::TraceProvider::GraphDriver_FormatDisk::StopActivity(void)

- ea: `0x18005e8c0`
- end: `0x18005eba9`
- name: `?StopActivity@GraphDriver_FormatDisk@TraceProvider@Diagnostics@ComputeService@@MEAAXXZ`
- size: `745`
- prototype: `void __fastcall(ComputeService::Diagnostics::TraceProvider::GraphDriver_FormatDisk *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18001c384`
- `0x180021d1c`
- `0x18005dc20`
- `0x18005e8c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e927`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005eaf6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e927`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005eaf6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005eb29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005eb29`

## pseudocode

```c
void __fastcall ComputeService::Diagnostics::TraceProvider::GraphDriver_FormatDisk::StopActivity(
        ComputeService::Diagnostics::TraceProvider::GraphDriver_FormatDisk *this)
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
          (int)&byte_1800A266D,
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
          (unsigned int)byte_1800A235B,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeService::Diagnostics::TraceProvider::GraphDriver_FormatDisk *)((char *)this + 288));
}

```

## disassembly

```asm
0x18005e8c0  mov     [rsp-8+arg_8], rbx
0x18005e8c5  mov     [rsp-8+arg_10], rdi
0x18005e8ca  push    rbp
0x18005e8cb  mov     rbp, rsp
0x18005e8ce  sub     rsp, 140h
0x18005e8d5  mov     rbx, rcx
0x18005e8d8  mov     rdi, [rcx+110h]
0x18005e8df  mov     eax, [rdi+48h]
0x18005e8e2  test    eax, eax
0x18005e8e4  jns     loc_18005EACF
0x18005e8ea  add     rdi, 50h ; 'P'
0x18005e8ee  cmp     eax, [rdi+8]
0x18005e8f1  jnz     loc_18005EACF
0x18005e8f7  test    rdi, rdi
0x18005e8fa  jz      loc_18005EACF
0x18005e900  mov     [rbp+SRWLock], 0
0x18005e908  lea     rdx, [rbp+SRWLock]
0x18005e90c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18005e911  mov     rax, [rbx+110h]
0x18005e918  mov     dword ptr [rax], 2
0x18005e91e  mov     rcx, [rbp+SRWLock]; SRWLock
0x18005e922  test    rcx, rcx
0x18005e925  jz      short loc_18005E933
0x18005e927  call    cs:__imp_ReleaseSRWLockExclusive
0x18005e92e  nop     dword ptr [rax+rax+00h]
0x18005e933  call    ?Provider@TraceProvider@Diagnostics@ComputeService@@SAPEBU_tlgProvider_t@@XZ; ComputeService::Diagnostics::TraceProvider::Provider(void)
0x18005e938  mov     r9, rax
0x18005e93b  mov     ecx, [rax]
0x18005e93d  cmp     ecx, 4
0x18005e940  jbe     loc_18005EB80
0x18005e946  mov     rax, [rax+18h]
0x18005e94a  mov     rcx, [r9+10h]
0x18005e94e  test    cl, 40h
0x18005e951  jz      loc_18005EB80
0x18005e957  mov     rcx, rax
0x18005e95a  and     ecx, 40h
0x18005e95d  cmp     rcx, rax
0x18005e960  jnz     loc_18005EB80
0x18005e966  mov     rax, [rdi+30h]
0x18005e96a  mov     [rbp+var_50], rax
0x18005e96e  mov     eax, [rdi+44h]
0x18005e971  mov     dword ptr [rbp+var_78+4], eax
0x18005e974  mov     eax, [rdi+10h]
0x18005e977  mov     dword ptr [rbp+var_70], eax
0x18005e97a  mov     rax, [rdi+78h]
0x18005e97e  mov     [rbp+var_48], rax
0x18005e982  mov     rax, [rdi+70h]
0x18005e986  mov     [rbp+var_40], rax
0x18005e98a  mov     eax, [rdi+68h]
0x18005e98d  mov     dword ptr [rbp+var_70+4], eax
0x18005e990  mov     rax, [rdi+60h]
0x18005e994  mov     [rbp+var_38], rax
0x18005e998  mov     rax, [rdi+58h]
0x18005e99c  mov     [rbp+var_30], rax
0x18005e9a0  mov     eax, [rdi+50h]
0x18005e9a3  mov     dword ptr [rbp+var_68], eax
0x18005e9a6  mov     rax, [rdi+48h]
0x18005e9aa  mov     [rbp+var_28], rax
0x18005e9ae  mov     eax, [rdi+20h]
0x18005e9b1  mov     dword ptr [rbp+var_68+4], eax
0x18005e9b4  mov     rax, [rdi+18h]
0x18005e9b8  mov     [rbp+var_20], rax
0x18005e9bc  mov     eax, [rdi]
0x18005e9be  mov     [rbp+var_60], eax
0x18005e9c1  mov     rax, [rdi+80h]
0x18005e9c8  mov     [rbp+var_18], rax
0x18005e9cc  mov     eax, [rdi+40h]
0x18005e9cf  mov     dword ptr [rbp+var_78], eax
0x18005e9d2  mov     rax, [rdi+38h]
0x18005e9d6  mov     [rbp+var_10], rax
0x18005e9da  mov     eax, [rdi+8]
0x18005e9dd  mov     dword ptr [rbp+SRWLock], eax
0x18005e9e0  mov     [rbp+var_8], 1000000h
0x18005e9e8  mov     [rbp+var_58], 0
0x18005e9f0  mov     r8, [rbx+110h]
0x18005e9f7  add     r8, 8; int
0x18005e9fb  lea     rax, [rbp+var_50]
0x18005e9ff  mov     [rsp+140h+var_90], rax; __int64
0x18005ea07  lea     rax, [rbp+var_78+4]
0x18005ea0b  mov     [rsp+140h+var_98], rax; __int64
0x18005ea13  lea     rax, [rbp+var_70]
0x18005ea17  mov     [rsp+140h+var_A0], rax; __int64
0x18005ea1f  lea     rax, [rbp+var_48]
0x18005ea23  mov     [rsp+140h+var_A8], rax; __int64
0x18005ea2b  lea     rax, [rbp+var_40]
0x18005ea2f  mov     [rsp+140h+var_B0], rax; __int64
0x18005ea37  lea     rax, [rbp+var_70+4]
0x18005ea3b  mov     [rsp+140h+var_B8], rax; __int64
0x18005ea43  lea     rax, [rbp+var_38]
0x18005ea47  mov     [rsp+140h+var_C0], rax; __int64
0x18005ea4f  lea     rax, [rbp+var_30]
0x18005ea53  mov     [rsp+140h+var_C8], rax; __int64
0x18005ea58  lea     rax, [rbp+var_68]
0x18005ea5c  mov     [rsp+140h+var_D0], rax; __int64
0x18005ea61  lea     rax, [rbp+var_28]
0x18005ea65  mov     [rsp+140h+var_D8], rax; __int64
0x18005ea6a  lea     rax, [rbp+var_68+4]
0x18005ea6e  mov     [rsp+140h+var_E0], rax; __int64
0x18005ea73  lea     rax, [rbp+var_20]
0x18005ea77  mov     [rsp+140h+var_E8], rax; __int64
0x18005ea7c  lea     rax, [rbp+var_60]
0x18005ea80  mov     [rsp+140h+var_F0], rax; __int64
0x18005ea85  lea     rax, [rbp+var_18]
0x18005ea89  mov     [rsp+140h+var_F8], rax; __int64
0x18005ea8e  lea     rax, [rbp+var_78]
0x18005ea92  mov     [rsp+140h+var_100], rax; __int64
0x18005ea97  lea     rax, [rbp+var_10]
0x18005ea9b  mov     [rsp+140h+var_108], rax; __int64
0x18005eaa0  lea     rax, [rbp+SRWLock]
0x18005eaa4  mov     [rsp+140h+var_110], rax; __int64
0x18005eaa9  lea     rax, [rbp+var_8]
0x18005eaad  mov     [rsp+140h+var_118], rax; __int64
0x18005eab2  lea     rax, [rbp+var_58]
0x18005eab6  mov     [rsp+140h+var_120], rax; __int64
0x18005eabb  lea     rdx, byte_1800A266D; int
0x18005eac2  mov     rcx, r9; int
0x18005eac5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18005eaca  jmp     loc_18005EB80
0x18005eacf  mov     [rbp+SRWLock], 0
0x18005ead7  lea     rdx, [rbp+SRWLock]
0x18005eadb  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18005eae0  mov     rax, [rbx+110h]
0x18005eae7  mov     dword ptr [rax], 2
0x18005eaed  mov     rcx, [rbp+SRWLock]; SRWLock
0x18005eaf1  test    rcx, rcx
0x18005eaf4  jz      short loc_18005EB02
0x18005eaf6  call    cs:__imp_ReleaseSRWLockExclusive
0x18005eafd  nop     dword ptr [rax+rax+00h]
0x18005eb02  call    ?Provider@TraceProvider@Diagnostics@ComputeService@@SAPEBU_tlgProvider_t@@XZ; ComputeService::Diagnostics::TraceProvider::Provider(void)
0x18005eb07  mov     rdi, rax
0x18005eb0a  mov     ecx, [rax]
0x18005eb0c  cmp     ecx, 4
0x18005eb0f  jbe     short loc_18005EB80
0x18005eb11  mov     rax, [rax+18h]
0x18005eb15  mov     rcx, [rdi+10h]
0x18005eb19  test    cl, 40h
0x18005eb1c  jz      short loc_18005EB80
0x18005eb1e  mov     rcx, rax
0x18005eb21  and     ecx, 40h
0x18005eb24  cmp     rcx, rax
0x18005eb27  jnz     short loc_18005EB80
0x18005eb29  call    cs:__imp_GetCurrentThreadId
0x18005eb30  nop     dword ptr [rax+rax+00h]
0x18005eb35  mov     dword ptr [rbp+SRWLock], eax
0x18005eb38  mov     r8, [rbx+110h]
0x18005eb3f  mov     eax, [r8+48h]
0x18005eb43  mov     dword ptr [rbp+var_78], eax
0x18005eb46  mov     [rbp+var_58], 0
0x18005eb4e  add     r8, 8
0x18005eb52  lea     rax, [rbp+SRWLock]
0x18005eb56  mov     [rsp+140h+var_110], rax
0x18005eb5b  lea     rax, [rbp+var_78]
0x18005eb5f  mov     [rsp+140h+var_118], rax
0x18005eb64  lea     rax, [rbp+var_58]
0x18005eb68  mov     [rsp+140h+var_120], rax
0x18005eb6d  xor     r9d, r9d
0x18005eb70  lea     rdx, byte_1800A235B
0x18005eb77  mov     rcx, rdi
0x18005eb7a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005eb7f  nop
0x18005eb80  lea     rcx, [rbx+120h]; this
0x18005eb87  cmp     dword ptr [rcx+18h], 0
0x18005eb8b  jz      short loc_18005EB93
0x18005eb8d  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18005eb92  nop
0x18005eb93  lea     r11, [rsp+140h+var_s0]
0x18005eb9b  mov     rbx, [r11+18h]
0x18005eb9f  mov     rdi, [r11+20h]
0x18005eba3  mov     rsp, r11
0x18005eba6  pop     rbp
0x18005eba7  retn
```
