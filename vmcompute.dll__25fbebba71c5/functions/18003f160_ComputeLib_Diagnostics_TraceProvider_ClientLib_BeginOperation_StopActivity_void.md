# ComputeLib::Diagnostics::TraceProvider::ClientLib_BeginOperation::StopActivity(void)

- ea: `0x18003f160`
- end: `0x18003f453`
- name: `?StopActivity@ClientLib_BeginOperation@TraceProvider@Diagnostics@ComputeLib@@MEAAXXZ`
- size: `755`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::ClientLib_BeginOperation *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18001c384`
- `0x18001ed48`
- `0x180021d1c`
- `0x18003f160`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003f1c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003f39b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003f1c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003f39b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f3d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f3d3`

## pseudocode

```c
void __fastcall ComputeLib::Diagnostics::TraceProvider::ClientLib_BeginOperation::StopActivity(
        ComputeLib::Diagnostics::TraceProvider::ClientLib_BeginOperation *this)
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
      if ( (*((_QWORD *)v6 + 2) & 0x10000LL) != 0 && (v7 & 0x10000) == v7 )
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
          (int)&byte_1800A0C17,
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
      if ( (*((_QWORD *)v9 + 2) & 0x10000LL) != 0 && (v10 & 0x10000) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v13 = *(_DWORD *)(v11 + 72);
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v9,
          (unsigned int)&dword_1800A0ABC,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLib::Diagnostics::TraceProvider::ClientLib_BeginOperation *)((char *)this + 288));
}

```

## disassembly

```asm
0x18003f160  mov     [rsp-8+arg_8], rbx
0x18003f165  mov     [rsp-8+arg_10], rdi
0x18003f16a  push    rbp
0x18003f16b  mov     rbp, rsp
0x18003f16e  sub     rsp, 140h
0x18003f175  mov     rbx, rcx
0x18003f178  mov     rdi, [rcx+110h]
0x18003f17f  mov     eax, [rdi+48h]
0x18003f182  test    eax, eax
0x18003f184  jns     loc_18003F374
0x18003f18a  add     rdi, 50h ; 'P'
0x18003f18e  cmp     eax, [rdi+8]
0x18003f191  jnz     loc_18003F374
0x18003f197  test    rdi, rdi
0x18003f19a  jz      loc_18003F374
0x18003f1a0  mov     [rbp+SRWLock], 0
0x18003f1a8  lea     rdx, [rbp+SRWLock]
0x18003f1ac  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003f1b1  mov     rax, [rbx+110h]
0x18003f1b8  mov     dword ptr [rax], 2
0x18003f1be  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003f1c2  test    rcx, rcx
0x18003f1c5  jz      short loc_18003F1D3
0x18003f1c7  call    cs:__imp_ReleaseSRWLockExclusive
0x18003f1ce  nop     dword ptr [rax+rax+00h]
0x18003f1d3  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18003f1d8  mov     r9, rax
0x18003f1db  mov     ecx, [rax]
0x18003f1dd  cmp     ecx, 4
0x18003f1e0  jbe     loc_18003F42A
0x18003f1e6  mov     rax, [rax+18h]
0x18003f1ea  mov     rcx, [r9+10h]
0x18003f1ee  mov     edx, 10000h
0x18003f1f3  test    rdx, rcx
0x18003f1f6  jz      loc_18003F42A
0x18003f1fc  mov     rcx, rax
0x18003f1ff  and     rcx, rdx
0x18003f202  cmp     rcx, rax
0x18003f205  jnz     loc_18003F42A
0x18003f20b  mov     rax, [rdi+30h]
0x18003f20f  mov     [rbp+var_50], rax
0x18003f213  mov     eax, [rdi+44h]
0x18003f216  mov     dword ptr [rbp+var_78+4], eax
0x18003f219  mov     eax, [rdi+10h]
0x18003f21c  mov     dword ptr [rbp+var_70], eax
0x18003f21f  mov     rax, [rdi+78h]
0x18003f223  mov     [rbp+var_48], rax
0x18003f227  mov     rax, [rdi+70h]
0x18003f22b  mov     [rbp+var_40], rax
0x18003f22f  mov     eax, [rdi+68h]
0x18003f232  mov     dword ptr [rbp+var_70+4], eax
0x18003f235  mov     rax, [rdi+60h]
0x18003f239  mov     [rbp+var_38], rax
0x18003f23d  mov     rax, [rdi+58h]
0x18003f241  mov     [rbp+var_30], rax
0x18003f245  mov     eax, [rdi+50h]
0x18003f248  mov     dword ptr [rbp+var_68], eax
0x18003f24b  mov     rax, [rdi+48h]
0x18003f24f  mov     [rbp+var_28], rax
0x18003f253  mov     eax, [rdi+20h]
0x18003f256  mov     dword ptr [rbp+var_68+4], eax
0x18003f259  mov     rax, [rdi+18h]
0x18003f25d  mov     [rbp+var_20], rax
0x18003f261  mov     eax, [rdi]
0x18003f263  mov     [rbp+var_60], eax
0x18003f266  mov     rax, [rdi+80h]
0x18003f26d  mov     [rbp+var_18], rax
0x18003f271  mov     eax, [rdi+40h]
0x18003f274  mov     dword ptr [rbp+var_78], eax
0x18003f277  mov     rax, [rdi+38h]
0x18003f27b  mov     [rbp+var_10], rax
0x18003f27f  mov     eax, [rdi+8]
0x18003f282  mov     dword ptr [rbp+SRWLock], eax
0x18003f285  mov     [rbp+var_8], 1000000h
0x18003f28d  mov     [rbp+var_58], 0
0x18003f295  mov     r8, [rbx+110h]
0x18003f29c  add     r8, 8; int
0x18003f2a0  lea     rax, [rbp+var_50]
0x18003f2a4  mov     [rsp+140h+var_90], rax; __int64
0x18003f2ac  lea     rax, [rbp+var_78+4]
0x18003f2b0  mov     [rsp+140h+var_98], rax; __int64
0x18003f2b8  lea     rax, [rbp+var_70]
0x18003f2bc  mov     [rsp+140h+var_A0], rax; __int64
0x18003f2c4  lea     rax, [rbp+var_48]
0x18003f2c8  mov     [rsp+140h+var_A8], rax; __int64
0x18003f2d0  lea     rax, [rbp+var_40]
0x18003f2d4  mov     [rsp+140h+var_B0], rax; __int64
0x18003f2dc  lea     rax, [rbp+var_70+4]
0x18003f2e0  mov     [rsp+140h+var_B8], rax; __int64
0x18003f2e8  lea     rax, [rbp+var_38]
0x18003f2ec  mov     [rsp+140h+var_C0], rax; __int64
0x18003f2f4  lea     rax, [rbp+var_30]
0x18003f2f8  mov     [rsp+140h+var_C8], rax; __int64
0x18003f2fd  lea     rax, [rbp+var_68]
0x18003f301  mov     [rsp+140h+var_D0], rax; __int64
0x18003f306  lea     rax, [rbp+var_28]
0x18003f30a  mov     [rsp+140h+var_D8], rax; __int64
0x18003f30f  lea     rax, [rbp+var_68+4]
0x18003f313  mov     [rsp+140h+var_E0], rax; __int64
0x18003f318  lea     rax, [rbp+var_20]
0x18003f31c  mov     [rsp+140h+var_E8], rax; __int64
0x18003f321  lea     rax, [rbp+var_60]
0x18003f325  mov     [rsp+140h+var_F0], rax; __int64
0x18003f32a  lea     rax, [rbp+var_18]
0x18003f32e  mov     [rsp+140h+var_F8], rax; __int64
0x18003f333  lea     rax, [rbp+var_78]
0x18003f337  mov     [rsp+140h+var_100], rax; __int64
0x18003f33c  lea     rax, [rbp+var_10]
0x18003f340  mov     [rsp+140h+var_108], rax; __int64
0x18003f345  lea     rax, [rbp+SRWLock]
0x18003f349  mov     [rsp+140h+var_110], rax; __int64
0x18003f34e  lea     rax, [rbp+var_8]
0x18003f352  mov     [rsp+140h+var_118], rax; __int64
0x18003f357  lea     rax, [rbp+var_58]
0x18003f35b  mov     [rsp+140h+var_120], rax; __int64
0x18003f360  lea     rdx, byte_1800A0C17; int
0x18003f367  mov     rcx, r9; int
0x18003f36a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003f36f  jmp     loc_18003F42A
0x18003f374  mov     [rbp+SRWLock], 0
0x18003f37c  lea     rdx, [rbp+SRWLock]
0x18003f380  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003f385  mov     rax, [rbx+110h]
0x18003f38c  mov     dword ptr [rax], 2
0x18003f392  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003f396  test    rcx, rcx
0x18003f399  jz      short loc_18003F3A7
0x18003f39b  call    cs:__imp_ReleaseSRWLockExclusive
0x18003f3a2  nop     dword ptr [rax+rax+00h]
0x18003f3a7  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18003f3ac  mov     rdi, rax
0x18003f3af  mov     ecx, [rax]
0x18003f3b1  cmp     ecx, 4
0x18003f3b4  jbe     short loc_18003F42A
0x18003f3b6  mov     rax, [rax+18h]
0x18003f3ba  mov     rcx, [rdi+10h]
0x18003f3be  mov     edx, 10000h
0x18003f3c3  test    rdx, rcx
0x18003f3c6  jz      short loc_18003F42A
0x18003f3c8  mov     rcx, rax
0x18003f3cb  and     rcx, rdx
0x18003f3ce  cmp     rcx, rax
0x18003f3d1  jnz     short loc_18003F42A
0x18003f3d3  call    cs:__imp_GetCurrentThreadId
0x18003f3da  nop     dword ptr [rax+rax+00h]
0x18003f3df  mov     dword ptr [rbp+SRWLock], eax
0x18003f3e2  mov     r8, [rbx+110h]
0x18003f3e9  mov     eax, [r8+48h]
0x18003f3ed  mov     dword ptr [rbp+var_78], eax
0x18003f3f0  mov     [rbp+var_58], 0
0x18003f3f8  add     r8, 8
0x18003f3fc  lea     rax, [rbp+SRWLock]
0x18003f400  mov     [rsp+140h+var_110], rax
0x18003f405  lea     rax, [rbp+var_78]
0x18003f409  mov     [rsp+140h+var_118], rax
0x18003f40e  lea     rax, [rbp+var_58]
0x18003f412  mov     [rsp+140h+var_120], rax
0x18003f417  xor     r9d, r9d
0x18003f41a  lea     rdx, dword_1800A0ABC
0x18003f421  mov     rcx, rdi
0x18003f424  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003f429  nop
0x18003f42a  lea     rcx, [rbx+120h]; this
0x18003f431  cmp     dword ptr [rcx+18h], 0
0x18003f435  jz      short loc_18003F43D
0x18003f437  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18003f43c  nop
0x18003f43d  lea     r11, [rsp+140h+var_s0]
0x18003f445  mov     rbx, [r11+18h]
0x18003f449  mov     rdi, [r11+20h]
0x18003f44d  mov     rsp, r11
0x18003f450  pop     rbp
0x18003f451  retn
```
