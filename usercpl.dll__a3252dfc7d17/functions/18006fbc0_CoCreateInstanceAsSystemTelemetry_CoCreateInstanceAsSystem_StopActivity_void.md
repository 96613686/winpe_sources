# CoCreateInstanceAsSystemTelemetry::CoCreateInstanceAsSystem::StopActivity(void)

- ea: `0x18006fbc0`
- end: `0x18006fea5`
- name: `?StopActivity@CoCreateInstanceAsSystem@CoCreateInstanceAsSystemTelemetry@@MEAAXXZ`
- size: `741`
- prototype: `void __fastcall(CoCreateInstanceAsSystemTelemetry::CoCreateInstanceAsSystem *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x180001008`
- `0x1800012bc`
- `0x180003281`
- `0x180007c6c`
- `0x18006f474`
- `0x18006fbc0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006fc1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006fdad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006fc1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006fdad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006fe43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006fe43`

## string_xrefs

- `0x18006fe5e`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall CoCreateInstanceAsSystemTelemetry::CoCreateInstanceAsSystem::StopActivity(
        CoCreateInstanceAsSystemTelemetry::CoCreateInstanceAsSystem *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r9
  __int64 v8; // rax
  __int64 v9; // r8
  RTL_SRWLOCK *v10; // rcx
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rax
  DWORD CurrentThreadId_0; // eax
  __int64 v15; // r8
  char *v16; // rbx
  __int64 *v17; // rcx
  __int64 v18; // rax
  int v19; // [rsp+A0h] [rbp-19h] BYREF
  int v20; // [rsp+A4h] [rbp-15h] BYREF
  const OLECHAR *v21; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v22; // [rsp+B0h] [rbp-9h] BYREF
  const OLECHAR *v23; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v24; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v25; // [rsp+C8h] [rbp+Fh] BYREF
  const OLECHAR *v26; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v27; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v28; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v29; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v30[4]; // [rsp+F0h] [rbp+37h] BYREF
  void *retaddr; // [rsp+118h] [rbp+5Fh]
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v33; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v34; // [rsp+130h] [rbp+77h] BYREF
  int v35; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<TaskFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = CoCreateInstanceAsSystemLogging::Provider();
    v7 = (__int64)v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*(_QWORD *)(v7 + 16) & 0x200000000000LL) != 0 && (v8 & 0x200000000000LL) == v8 )
      {
        v9 = *((_QWORD *)this + 34);
        v21 = (const OLECHAR *)*((_QWORD *)v4 + 15);
        v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        LODWORD(SRWLock) = v4[26];
        v23 = (const OLECHAR *)*((_QWORD *)v4 + 12);
        v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v33 = v4[20];
        v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        LODWORD(v34) = v4[8];
        v26 = (const OLECHAR *)*((_QWORD *)v4 + 3);
        v35 = *v4;
        v27 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v19 = v4[16];
        v28 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        v20 = v4[2];
        v29 = 0x1000000;
        v30[0] = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v7,
          (__int64)&dword_18009494C,
          v9 + 8,
          v7,
          (__int64)v30,
          (__int64)&v29,
          (__int64)&v20,
          &v28,
          (__int64)&v19,
          &v27,
          (__int64)&v35,
          &v26,
          (__int64)&v34,
          &v25,
          (__int64)&v33,
          &v24,
          &v23,
          (__int64)&SRWLock,
          &v22,
          &v21);
      }
    }
  }
  else
  {
    wil::ActivityBase<TaskFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v10 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = CoCreateInstanceAsSystemLogging::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u )
    {
      v13 = *((_QWORD *)v11 + 3);
      if ( (*(_QWORD *)(v12 + 16) & 0x200000000000LL) != 0 && (v13 & 0x200000000000LL) == v13 )
      {
        CurrentThreadId_0 = GetCurrentThreadId_0();
        v15 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId_0;
        v33 = *(_DWORD *)(v15 + 72);
        v34 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v12,
          (__int64)byte_1800948A3,
          v15 + 8,
          0,
          (__int64)&v34,
          (__int64)&v33,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
  {
    v16 = (char *)this + 288;
    if ( *((_DWORD *)v16 + 6) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    v17 = *(__int64 **)v16;
    *((_DWORD *)v16 + 6) = 0;
    while ( 1 )
    {
      v18 = *v17;
      if ( !*v17 )
        break;
      if ( (char *)v18 == v16 )
      {
        *v17 = *((_QWORD *)v16 + 2);
        break;
      }
      v17 = (__int64 *)(v18 + 16);
      *(_QWORD *)v16 = v18 + 16;
    }
    *(_QWORD *)v16 = 0;
  }
}

```

## disassembly

```asm
0x18006fbc0  push    rbp
0x18006fbc2  push    rbx
0x18006fbc3  push    rdi
0x18006fbc4  lea     rbp, [rsp-47h]
0x18006fbc9  sub     rsp, 100h
0x18006fbd0  mov     rdi, [rcx+110h]
0x18006fbd7  mov     rbx, rcx
0x18006fbda  mov     eax, [rdi+48h]
0x18006fbdd  test    eax, eax
0x18006fbdf  jns     loc_18006FD8E
0x18006fbe5  add     rdi, 50h ; 'P'
0x18006fbe9  cmp     eax, [rdi+8]
0x18006fbec  jnz     loc_18006FD8E
0x18006fbf2  test    rdi, rdi
0x18006fbf5  jz      loc_18006FD8E
0x18006fbfb  lea     rdx, [rbp+57h+SRWLock]
0x18006fbff  call    ?LockExclusive@?$ActivityBase@VTaskFlowLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TaskFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18006fc04  mov     rax, [rbx+110h]
0x18006fc0b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18006fc0f  mov     dword ptr [rax], 2
0x18006fc15  test    rcx, rcx
0x18006fc18  jz      short loc_18006FC20
0x18006fc1a  call    cs:__imp_ReleaseSRWLockExclusive
0x18006fc20  call    ?Provider@CoCreateInstanceAsSystemLogging@@SAPEBU_tlgProvider_t@@XZ; CoCreateInstanceAsSystemLogging::Provider(void)
0x18006fc25  mov     r9, rax
0x18006fc28  mov     ecx, [rax]
0x18006fc2a  cmp     ecx, 5
0x18006fc2d  jbe     loc_18006FE33
0x18006fc33  mov     rax, [rax+18h]
0x18006fc37  mov     rdx, 200000000000h
0x18006fc41  mov     rcx, [r9+10h]
0x18006fc45  test    rdx, rcx
0x18006fc48  jz      loc_18006FE33
0x18006fc4e  mov     rcx, rax
0x18006fc51  and     rcx, rdx
0x18006fc54  cmp     rcx, rax
0x18006fc57  jnz     loc_18006FE33
0x18006fc5d  mov     rax, [rdi+78h]
0x18006fc61  lea     rdx, dword_18009494C
0x18006fc68  mov     r8, [rbx+110h]
0x18006fc6f  mov     rcx, r9
0x18006fc72  mov     [rbp+57h+var_68], rax
0x18006fc76  add     r8, 8
0x18006fc7a  mov     rax, [rdi+70h]
0x18006fc7e  mov     [rbp+57h+var_60], rax
0x18006fc82  mov     eax, [rdi+68h]
0x18006fc85  mov     dword ptr [rbp+57h+SRWLock], eax
0x18006fc88  mov     rax, [rdi+60h]
0x18006fc8c  mov     [rbp+57h+var_58], rax
0x18006fc90  mov     rax, [rdi+58h]
0x18006fc94  mov     [rbp+57h+var_50], rax
0x18006fc98  mov     eax, [rdi+50h]
0x18006fc9b  mov     [rbp+57h+arg_8], eax
0x18006fc9e  mov     rax, [rdi+48h]
0x18006fca2  mov     [rbp+57h+var_48], rax
0x18006fca6  mov     eax, [rdi+20h]
0x18006fca9  mov     dword ptr [rbp+57h+arg_10], eax
0x18006fcac  mov     rax, [rdi+18h]
0x18006fcb0  mov     [rbp+57h+var_40], rax
0x18006fcb4  mov     eax, [rdi]
0x18006fcb6  mov     [rbp+57h+arg_18], eax
0x18006fcb9  mov     rax, [rdi+80h]
0x18006fcc0  mov     [rbp+57h+var_38], rax
0x18006fcc4  mov     eax, [rdi+40h]
0x18006fcc7  mov     [rbp+57h+var_70], eax
0x18006fcca  mov     rax, [rdi+38h]
0x18006fcce  mov     [rbp+57h+var_30], rax
0x18006fcd2  mov     eax, [rdi+8]
0x18006fcd5  mov     [rbp+57h+var_6C], eax
0x18006fcd8  lea     rax, [rbp+57h+var_68]
0x18006fcdc  mov     [rsp+110h+var_78], rax
0x18006fce4  lea     rax, [rbp+57h+var_60]
0x18006fce8  mov     [rsp+110h+var_80], rax
0x18006fcf0  lea     rax, [rbp+57h+SRWLock]
0x18006fcf4  mov     [rsp+110h+var_88], rax
0x18006fcfc  lea     rax, [rbp+57h+var_58]
0x18006fd00  mov     [rsp+110h+var_90], rax
0x18006fd08  lea     rax, [rbp+57h+var_50]
0x18006fd0c  mov     [rsp+110h+var_98], rax
0x18006fd11  lea     rax, [rbp+57h+arg_8]
0x18006fd15  mov     [rsp+110h+var_A0], rax
0x18006fd1a  lea     rax, [rbp+57h+var_48]
0x18006fd1e  mov     [rsp+110h+var_A8], rax
0x18006fd23  lea     rax, [rbp+57h+arg_10]
0x18006fd27  mov     [rsp+110h+var_B0], rax
0x18006fd2c  lea     rax, [rbp+57h+var_40]
0x18006fd30  mov     [rsp+110h+var_B8], rax
0x18006fd35  lea     rax, [rbp+57h+arg_18]
0x18006fd39  mov     [rsp+110h+var_C0], rax
0x18006fd3e  lea     rax, [rbp+57h+var_38]
0x18006fd42  mov     [rsp+110h+var_C8], rax
0x18006fd47  lea     rax, [rbp+57h+var_70]
0x18006fd4b  mov     [rsp+110h+var_D0], rax
0x18006fd50  lea     rax, [rbp+57h+var_30]
0x18006fd54  mov     [rsp+110h+var_D8], rax
0x18006fd59  lea     rax, [rbp+57h+var_6C]
0x18006fd5d  mov     [rsp+110h+var_E0], rax
0x18006fd62  lea     rax, [rbp+57h+var_28]
0x18006fd66  mov     [rsp+110h+var_E8], rax
0x18006fd6b  lea     rax, [rbp+57h+var_20]
0x18006fd6f  mov     [rsp+110h+var_F0], rax
0x18006fd74  mov     [rbp+57h+var_28], 1000000h
0x18006fd7c  mov     [rbp+57h+var_20], 0
0x18006fd84  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18006fd89  jmp     loc_18006FE33
0x18006fd8e  lea     rdx, [rbp+57h+SRWLock]
0x18006fd92  call    ?LockExclusive@?$ActivityBase@VTaskFlowLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TaskFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18006fd97  mov     rax, [rbx+110h]
0x18006fd9e  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18006fda2  mov     dword ptr [rax], 2
0x18006fda8  test    rcx, rcx
0x18006fdab  jz      short loc_18006FDB3
0x18006fdad  call    cs:__imp_ReleaseSRWLockExclusive
0x18006fdb3  call    ?Provider@CoCreateInstanceAsSystemLogging@@SAPEBU_tlgProvider_t@@XZ; CoCreateInstanceAsSystemLogging::Provider(void)
0x18006fdb8  mov     rdi, rax
0x18006fdbb  mov     ecx, [rax]
0x18006fdbd  cmp     ecx, 5
0x18006fdc0  jbe     short loc_18006FE33
0x18006fdc2  mov     rax, [rax+18h]
0x18006fdc6  mov     rdx, 200000000000h
0x18006fdd0  mov     rcx, [rdi+10h]
0x18006fdd4  test    rdx, rcx
0x18006fdd7  jz      short loc_18006FE33
0x18006fdd9  mov     rcx, rax
0x18006fddc  and     rcx, rdx
0x18006fddf  cmp     rcx, rax
0x18006fde2  jnz     short loc_18006FE33
0x18006fde4  call    GetCurrentThreadId_0
0x18006fde9  mov     r8, [rbx+110h]
0x18006fdf0  lea     rdx, byte_1800948A3
0x18006fdf7  mov     dword ptr [rbp+57h+SRWLock], eax
0x18006fdfa  xor     r9d, r9d
0x18006fdfd  mov     rcx, rdi
0x18006fe00  mov     eax, [r8+48h]
0x18006fe04  add     r8, 8
0x18006fe08  mov     [rbp+57h+arg_8], eax
0x18006fe0b  lea     rax, [rbp+57h+SRWLock]
0x18006fe0f  mov     [rsp+110h+var_E0], rax
0x18006fe14  lea     rax, [rbp+57h+arg_8]
0x18006fe18  mov     [rsp+110h+var_E8], rax
0x18006fe1d  lea     rax, [rbp+57h+arg_10]
0x18006fe21  mov     [rsp+110h+var_F0], rax
0x18006fe26  mov     [rbp+57h+arg_10], 0
0x18006fe2e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006fe33  cmp     dword ptr [rbx+138h], 0
0x18006fe3a  jz      short loc_18006FE9A
0x18006fe3c  add     rbx, 120h
0x18006fe43  call    cs:__imp_GetCurrentThreadId
0x18006fe49  cmp     [rbx+18h], eax
0x18006fe4c  jz      short loc_18006FE6A
0x18006fe4e  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18006fe55  test    rax, rax
0x18006fe58  jz      short loc_18006FE6A
0x18006fe5a  mov     rdx, [rbp+5Fh]
0x18006fe5e  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18006fe65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fe6a  mov     rcx, [rbx]
0x18006fe6d  mov     dword ptr [rbx+18h], 0
0x18006fe74  jmp     short loc_18006FE82
0x18006fe76  cmp     rax, rbx
0x18006fe79  jz      short loc_18006FE8C
0x18006fe7b  lea     rcx, [rax+10h]
0x18006fe7f  mov     [rbx], rcx
0x18006fe82  mov     rax, [rcx]
0x18006fe85  test    rax, rax
0x18006fe88  jnz     short loc_18006FE76
0x18006fe8a  jmp     short loc_18006FE93
0x18006fe8c  mov     rax, [rbx+10h]
0x18006fe90  mov     [rcx], rax
0x18006fe93  mov     qword ptr [rbx], 0
0x18006fe9a  add     rsp, 100h
0x18006fea1  pop     rdi
0x18006fea2  pop     rbx
0x18006fea3  pop     rbp
0x18006fea4  retn
```
