# ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_GrantVmAccess::StopActivity(void)

- ea: `0x18004b100`
- end: `0x18004b3e9`
- name: `?StopActivity@VmFileUtilities_GrantVmAccess@TraceProvider@Diagnostics@ComputeLib@@MEAAXXZ`
- size: `745`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_GrantVmAccess *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18001c384`
- `0x18001ed48`
- `0x180021d1c`
- `0x18004b100`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b167`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b336`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b167`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b336`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004b369`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004b369`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_GrantVmAccess::StopActivity(
        ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_GrantVmAccess *this)
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
          (int)&byte_1800A163F,
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
          (unsigned int)byte_1800A12C5,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_GrantVmAccess *)((char *)this + 288));
}

```

## disassembly

```asm
0x18004b100  mov     [rsp-8+arg_8], rbx
0x18004b105  mov     [rsp-8+arg_10], rdi
0x18004b10a  push    rbp
0x18004b10b  mov     rbp, rsp
0x18004b10e  sub     rsp, 140h
0x18004b115  mov     rbx, rcx
0x18004b118  mov     rdi, [rcx+110h]
0x18004b11f  mov     eax, [rdi+48h]
0x18004b122  test    eax, eax
0x18004b124  jns     loc_18004B30F
0x18004b12a  add     rdi, 50h ; 'P'
0x18004b12e  cmp     eax, [rdi+8]
0x18004b131  jnz     loc_18004B30F
0x18004b137  test    rdi, rdi
0x18004b13a  jz      loc_18004B30F
0x18004b140  mov     [rbp+SRWLock], 0
0x18004b148  lea     rdx, [rbp+SRWLock]
0x18004b14c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004b151  mov     rax, [rbx+110h]
0x18004b158  mov     dword ptr [rax], 2
0x18004b15e  mov     rcx, [rbp+SRWLock]; SRWLock
0x18004b162  test    rcx, rcx
0x18004b165  jz      short loc_18004B173
0x18004b167  call    cs:__imp_ReleaseSRWLockExclusive
0x18004b16e  nop     dword ptr [rax+rax+00h]
0x18004b173  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18004b178  mov     r9, rax
0x18004b17b  mov     ecx, [rax]
0x18004b17d  cmp     ecx, 4
0x18004b180  jbe     loc_18004B3C0
0x18004b186  mov     rax, [rax+18h]
0x18004b18a  mov     rcx, [r9+10h]
0x18004b18e  test    cl, 40h
0x18004b191  jz      loc_18004B3C0
0x18004b197  mov     rcx, rax
0x18004b19a  and     ecx, 40h
0x18004b19d  cmp     rcx, rax
0x18004b1a0  jnz     loc_18004B3C0
0x18004b1a6  mov     rax, [rdi+30h]
0x18004b1aa  mov     [rbp+var_50], rax
0x18004b1ae  mov     eax, [rdi+44h]
0x18004b1b1  mov     dword ptr [rbp+var_78+4], eax
0x18004b1b4  mov     eax, [rdi+10h]
0x18004b1b7  mov     dword ptr [rbp+var_70], eax
0x18004b1ba  mov     rax, [rdi+78h]
0x18004b1be  mov     [rbp+var_48], rax
0x18004b1c2  mov     rax, [rdi+70h]
0x18004b1c6  mov     [rbp+var_40], rax
0x18004b1ca  mov     eax, [rdi+68h]
0x18004b1cd  mov     dword ptr [rbp+var_70+4], eax
0x18004b1d0  mov     rax, [rdi+60h]
0x18004b1d4  mov     [rbp+var_38], rax
0x18004b1d8  mov     rax, [rdi+58h]
0x18004b1dc  mov     [rbp+var_30], rax
0x18004b1e0  mov     eax, [rdi+50h]
0x18004b1e3  mov     dword ptr [rbp+var_68], eax
0x18004b1e6  mov     rax, [rdi+48h]
0x18004b1ea  mov     [rbp+var_28], rax
0x18004b1ee  mov     eax, [rdi+20h]
0x18004b1f1  mov     dword ptr [rbp+var_68+4], eax
0x18004b1f4  mov     rax, [rdi+18h]
0x18004b1f8  mov     [rbp+var_20], rax
0x18004b1fc  mov     eax, [rdi]
0x18004b1fe  mov     [rbp+var_60], eax
0x18004b201  mov     rax, [rdi+80h]
0x18004b208  mov     [rbp+var_18], rax
0x18004b20c  mov     eax, [rdi+40h]
0x18004b20f  mov     dword ptr [rbp+var_78], eax
0x18004b212  mov     rax, [rdi+38h]
0x18004b216  mov     [rbp+var_10], rax
0x18004b21a  mov     eax, [rdi+8]
0x18004b21d  mov     dword ptr [rbp+SRWLock], eax
0x18004b220  mov     [rbp+var_8], 1000000h
0x18004b228  mov     [rbp+var_58], 0
0x18004b230  mov     r8, [rbx+110h]
0x18004b237  add     r8, 8; int
0x18004b23b  lea     rax, [rbp+var_50]
0x18004b23f  mov     [rsp+140h+var_90], rax; __int64
0x18004b247  lea     rax, [rbp+var_78+4]
0x18004b24b  mov     [rsp+140h+var_98], rax; __int64
0x18004b253  lea     rax, [rbp+var_70]
0x18004b257  mov     [rsp+140h+var_A0], rax; __int64
0x18004b25f  lea     rax, [rbp+var_48]
0x18004b263  mov     [rsp+140h+var_A8], rax; __int64
0x18004b26b  lea     rax, [rbp+var_40]
0x18004b26f  mov     [rsp+140h+var_B0], rax; __int64
0x18004b277  lea     rax, [rbp+var_70+4]
0x18004b27b  mov     [rsp+140h+var_B8], rax; __int64
0x18004b283  lea     rax, [rbp+var_38]
0x18004b287  mov     [rsp+140h+var_C0], rax; __int64
0x18004b28f  lea     rax, [rbp+var_30]
0x18004b293  mov     [rsp+140h+var_C8], rax; __int64
0x18004b298  lea     rax, [rbp+var_68]
0x18004b29c  mov     [rsp+140h+var_D0], rax; __int64
0x18004b2a1  lea     rax, [rbp+var_28]
0x18004b2a5  mov     [rsp+140h+var_D8], rax; __int64
0x18004b2aa  lea     rax, [rbp+var_68+4]
0x18004b2ae  mov     [rsp+140h+var_E0], rax; __int64
0x18004b2b3  lea     rax, [rbp+var_20]
0x18004b2b7  mov     [rsp+140h+var_E8], rax; __int64
0x18004b2bc  lea     rax, [rbp+var_60]
0x18004b2c0  mov     [rsp+140h+var_F0], rax; __int64
0x18004b2c5  lea     rax, [rbp+var_18]
0x18004b2c9  mov     [rsp+140h+var_F8], rax; __int64
0x18004b2ce  lea     rax, [rbp+var_78]
0x18004b2d2  mov     [rsp+140h+var_100], rax; __int64
0x18004b2d7  lea     rax, [rbp+var_10]
0x18004b2db  mov     [rsp+140h+var_108], rax; __int64
0x18004b2e0  lea     rax, [rbp+SRWLock]
0x18004b2e4  mov     [rsp+140h+var_110], rax; __int64
0x18004b2e9  lea     rax, [rbp+var_8]
0x18004b2ed  mov     [rsp+140h+var_118], rax; __int64
0x18004b2f2  lea     rax, [rbp+var_58]
0x18004b2f6  mov     [rsp+140h+var_120], rax; __int64
0x18004b2fb  lea     rdx, byte_1800A163F; int
0x18004b302  mov     rcx, r9; int
0x18004b305  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18004b30a  jmp     loc_18004B3C0
0x18004b30f  mov     [rbp+SRWLock], 0
0x18004b317  lea     rdx, [rbp+SRWLock]
0x18004b31b  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004b320  mov     rax, [rbx+110h]
0x18004b327  mov     dword ptr [rax], 2
0x18004b32d  mov     rcx, [rbp+SRWLock]; SRWLock
0x18004b331  test    rcx, rcx
0x18004b334  jz      short loc_18004B342
0x18004b336  call    cs:__imp_ReleaseSRWLockExclusive
0x18004b33d  nop     dword ptr [rax+rax+00h]
0x18004b342  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18004b347  mov     rdi, rax
0x18004b34a  mov     ecx, [rax]
0x18004b34c  cmp     ecx, 4
0x18004b34f  jbe     short loc_18004B3C0
0x18004b351  mov     rax, [rax+18h]
0x18004b355  mov     rcx, [rdi+10h]
0x18004b359  test    cl, 40h
0x18004b35c  jz      short loc_18004B3C0
0x18004b35e  mov     rcx, rax
0x18004b361  and     ecx, 40h
0x18004b364  cmp     rcx, rax
0x18004b367  jnz     short loc_18004B3C0
0x18004b369  call    cs:__imp_GetCurrentThreadId
0x18004b370  nop     dword ptr [rax+rax+00h]
0x18004b375  mov     dword ptr [rbp+SRWLock], eax
0x18004b378  mov     r8, [rbx+110h]
0x18004b37f  mov     eax, [r8+48h]
0x18004b383  mov     dword ptr [rbp+var_78], eax
0x18004b386  mov     [rbp+var_58], 0
0x18004b38e  add     r8, 8
0x18004b392  lea     rax, [rbp+SRWLock]
0x18004b396  mov     [rsp+140h+var_110], rax
0x18004b39b  lea     rax, [rbp+var_78]
0x18004b39f  mov     [rsp+140h+var_118], rax
0x18004b3a4  lea     rax, [rbp+var_58]
0x18004b3a8  mov     [rsp+140h+var_120], rax
0x18004b3ad  xor     r9d, r9d
0x18004b3b0  lea     rdx, byte_1800A12C5
0x18004b3b7  mov     rcx, rdi
0x18004b3ba  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004b3bf  nop
0x18004b3c0  lea     rcx, [rbx+120h]; this
0x18004b3c7  cmp     dword ptr [rcx+18h], 0
0x18004b3cb  jz      short loc_18004B3D3
0x18004b3cd  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18004b3d2  nop
0x18004b3d3  lea     r11, [rsp+140h+var_s0]
0x18004b3db  mov     rbx, [r11+18h]
0x18004b3df  mov     rdi, [r11+20h]
0x18004b3e3  mov     rsp, r11
0x18004b3e6  pop     rbp
0x18004b3e7  retn
```
