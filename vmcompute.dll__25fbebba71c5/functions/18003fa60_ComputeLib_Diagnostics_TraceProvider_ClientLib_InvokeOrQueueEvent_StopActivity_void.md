# ComputeLib::Diagnostics::TraceProvider::ClientLib_InvokeOrQueueEvent::StopActivity(void)

- ea: `0x18003fa60`
- end: `0x18003fd53`
- name: `?StopActivity@ClientLib_InvokeOrQueueEvent@TraceProvider@Diagnostics@ComputeLib@@MEAAXXZ`
- size: `755`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::ClientLib_InvokeOrQueueEvent *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18001c384`
- `0x18001ed48`
- `0x180021d1c`
- `0x18003fa60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003fac7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003fc9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003fac7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003fc9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003fcd3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003fcd3`

## pseudocode

```c
void __fastcall ComputeLib::Diagnostics::TraceProvider::ClientLib_InvokeOrQueueEvent::StopActivity(
        ComputeLib::Diagnostics::TraceProvider::ClientLib_InvokeOrQueueEvent *this)
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
    if ( *(_DWORD *)v5 > 5u )
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
          (int)&unk_1800A0540,
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
    if ( *(_DWORD *)v8 > 5u )
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
          (unsigned int)word_1800A0D6A,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLib::Diagnostics::TraceProvider::ClientLib_InvokeOrQueueEvent *)((char *)this + 288));
}

```

## disassembly

```asm
0x18003fa60  mov     [rsp-8+arg_8], rbx
0x18003fa65  mov     [rsp-8+arg_10], rdi
0x18003fa6a  push    rbp
0x18003fa6b  mov     rbp, rsp
0x18003fa6e  sub     rsp, 140h
0x18003fa75  mov     rbx, rcx
0x18003fa78  mov     rdi, [rcx+110h]
0x18003fa7f  mov     eax, [rdi+48h]
0x18003fa82  test    eax, eax
0x18003fa84  jns     loc_18003FC74
0x18003fa8a  add     rdi, 50h ; 'P'
0x18003fa8e  cmp     eax, [rdi+8]
0x18003fa91  jnz     loc_18003FC74
0x18003fa97  test    rdi, rdi
0x18003fa9a  jz      loc_18003FC74
0x18003faa0  mov     [rbp+SRWLock], 0
0x18003faa8  lea     rdx, [rbp+SRWLock]
0x18003faac  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003fab1  mov     rax, [rbx+110h]
0x18003fab8  mov     dword ptr [rax], 2
0x18003fabe  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003fac2  test    rcx, rcx
0x18003fac5  jz      short loc_18003FAD3
0x18003fac7  call    cs:__imp_ReleaseSRWLockExclusive
0x18003face  nop     dword ptr [rax+rax+00h]
0x18003fad3  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18003fad8  mov     r9, rax
0x18003fadb  mov     ecx, [rax]
0x18003fadd  cmp     ecx, 5
0x18003fae0  jbe     loc_18003FD2A
0x18003fae6  mov     rax, [rax+18h]
0x18003faea  mov     rcx, [r9+10h]
0x18003faee  mov     edx, 10000h
0x18003faf3  test    rdx, rcx
0x18003faf6  jz      loc_18003FD2A
0x18003fafc  mov     rcx, rax
0x18003faff  and     rcx, rdx
0x18003fb02  cmp     rcx, rax
0x18003fb05  jnz     loc_18003FD2A
0x18003fb0b  mov     rax, [rdi+30h]
0x18003fb0f  mov     [rbp+var_50], rax
0x18003fb13  mov     eax, [rdi+44h]
0x18003fb16  mov     dword ptr [rbp+var_78+4], eax
0x18003fb19  mov     eax, [rdi+10h]
0x18003fb1c  mov     dword ptr [rbp+var_70], eax
0x18003fb1f  mov     rax, [rdi+78h]
0x18003fb23  mov     [rbp+var_48], rax
0x18003fb27  mov     rax, [rdi+70h]
0x18003fb2b  mov     [rbp+var_40], rax
0x18003fb2f  mov     eax, [rdi+68h]
0x18003fb32  mov     dword ptr [rbp+var_70+4], eax
0x18003fb35  mov     rax, [rdi+60h]
0x18003fb39  mov     [rbp+var_38], rax
0x18003fb3d  mov     rax, [rdi+58h]
0x18003fb41  mov     [rbp+var_30], rax
0x18003fb45  mov     eax, [rdi+50h]
0x18003fb48  mov     dword ptr [rbp+var_68], eax
0x18003fb4b  mov     rax, [rdi+48h]
0x18003fb4f  mov     [rbp+var_28], rax
0x18003fb53  mov     eax, [rdi+20h]
0x18003fb56  mov     dword ptr [rbp+var_68+4], eax
0x18003fb59  mov     rax, [rdi+18h]
0x18003fb5d  mov     [rbp+var_20], rax
0x18003fb61  mov     eax, [rdi]
0x18003fb63  mov     [rbp+var_60], eax
0x18003fb66  mov     rax, [rdi+80h]
0x18003fb6d  mov     [rbp+var_18], rax
0x18003fb71  mov     eax, [rdi+40h]
0x18003fb74  mov     dword ptr [rbp+var_78], eax
0x18003fb77  mov     rax, [rdi+38h]
0x18003fb7b  mov     [rbp+var_10], rax
0x18003fb7f  mov     eax, [rdi+8]
0x18003fb82  mov     dword ptr [rbp+SRWLock], eax
0x18003fb85  mov     [rbp+var_8], 1000000h
0x18003fb8d  mov     [rbp+var_58], 0
0x18003fb95  mov     r8, [rbx+110h]
0x18003fb9c  add     r8, 8; int
0x18003fba0  lea     rax, [rbp+var_50]
0x18003fba4  mov     [rsp+140h+var_90], rax; __int64
0x18003fbac  lea     rax, [rbp+var_78+4]
0x18003fbb0  mov     [rsp+140h+var_98], rax; __int64
0x18003fbb8  lea     rax, [rbp+var_70]
0x18003fbbc  mov     [rsp+140h+var_A0], rax; __int64
0x18003fbc4  lea     rax, [rbp+var_48]
0x18003fbc8  mov     [rsp+140h+var_A8], rax; __int64
0x18003fbd0  lea     rax, [rbp+var_40]
0x18003fbd4  mov     [rsp+140h+var_B0], rax; __int64
0x18003fbdc  lea     rax, [rbp+var_70+4]
0x18003fbe0  mov     [rsp+140h+var_B8], rax; __int64
0x18003fbe8  lea     rax, [rbp+var_38]
0x18003fbec  mov     [rsp+140h+var_C0], rax; __int64
0x18003fbf4  lea     rax, [rbp+var_30]
0x18003fbf8  mov     [rsp+140h+var_C8], rax; __int64
0x18003fbfd  lea     rax, [rbp+var_68]
0x18003fc01  mov     [rsp+140h+var_D0], rax; __int64
0x18003fc06  lea     rax, [rbp+var_28]
0x18003fc0a  mov     [rsp+140h+var_D8], rax; __int64
0x18003fc0f  lea     rax, [rbp+var_68+4]
0x18003fc13  mov     [rsp+140h+var_E0], rax; __int64
0x18003fc18  lea     rax, [rbp+var_20]
0x18003fc1c  mov     [rsp+140h+var_E8], rax; __int64
0x18003fc21  lea     rax, [rbp+var_60]
0x18003fc25  mov     [rsp+140h+var_F0], rax; __int64
0x18003fc2a  lea     rax, [rbp+var_18]
0x18003fc2e  mov     [rsp+140h+var_F8], rax; __int64
0x18003fc33  lea     rax, [rbp+var_78]
0x18003fc37  mov     [rsp+140h+var_100], rax; __int64
0x18003fc3c  lea     rax, [rbp+var_10]
0x18003fc40  mov     [rsp+140h+var_108], rax; __int64
0x18003fc45  lea     rax, [rbp+SRWLock]
0x18003fc49  mov     [rsp+140h+var_110], rax; __int64
0x18003fc4e  lea     rax, [rbp+var_8]
0x18003fc52  mov     [rsp+140h+var_118], rax; __int64
0x18003fc57  lea     rax, [rbp+var_58]
0x18003fc5b  mov     [rsp+140h+var_120], rax; __int64
0x18003fc60  lea     rdx, unk_1800A0540; int
0x18003fc67  mov     rcx, r9; int
0x18003fc6a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003fc6f  jmp     loc_18003FD2A
0x18003fc74  mov     [rbp+SRWLock], 0
0x18003fc7c  lea     rdx, [rbp+SRWLock]
0x18003fc80  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003fc85  mov     rax, [rbx+110h]
0x18003fc8c  mov     dword ptr [rax], 2
0x18003fc92  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003fc96  test    rcx, rcx
0x18003fc99  jz      short loc_18003FCA7
0x18003fc9b  call    cs:__imp_ReleaseSRWLockExclusive
0x18003fca2  nop     dword ptr [rax+rax+00h]
0x18003fca7  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18003fcac  mov     rdi, rax
0x18003fcaf  mov     ecx, [rax]
0x18003fcb1  cmp     ecx, 5
0x18003fcb4  jbe     short loc_18003FD2A
0x18003fcb6  mov     rax, [rax+18h]
0x18003fcba  mov     rcx, [rdi+10h]
0x18003fcbe  mov     edx, 10000h
0x18003fcc3  test    rdx, rcx
0x18003fcc6  jz      short loc_18003FD2A
0x18003fcc8  mov     rcx, rax
0x18003fccb  and     rcx, rdx
0x18003fcce  cmp     rcx, rax
0x18003fcd1  jnz     short loc_18003FD2A
0x18003fcd3  call    cs:__imp_GetCurrentThreadId
0x18003fcda  nop     dword ptr [rax+rax+00h]
0x18003fcdf  mov     dword ptr [rbp+SRWLock], eax
0x18003fce2  mov     r8, [rbx+110h]
0x18003fce9  mov     eax, [r8+48h]
0x18003fced  mov     dword ptr [rbp+var_78], eax
0x18003fcf0  mov     [rbp+var_58], 0
0x18003fcf8  add     r8, 8
0x18003fcfc  lea     rax, [rbp+SRWLock]
0x18003fd00  mov     [rsp+140h+var_110], rax
0x18003fd05  lea     rax, [rbp+var_78]
0x18003fd09  mov     [rsp+140h+var_118], rax
0x18003fd0e  lea     rax, [rbp+var_58]
0x18003fd12  mov     [rsp+140h+var_120], rax
0x18003fd17  xor     r9d, r9d
0x18003fd1a  lea     rdx, word_1800A0D6A
0x18003fd21  mov     rcx, rdi
0x18003fd24  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003fd29  nop
0x18003fd2a  lea     rcx, [rbx+120h]; this
0x18003fd31  cmp     dword ptr [rcx+18h], 0
0x18003fd35  jz      short loc_18003FD3D
0x18003fd37  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18003fd3c  nop
0x18003fd3d  lea     r11, [rsp+140h+var_s0]
0x18003fd45  mov     rbx, [r11+18h]
0x18003fd49  mov     rdi, [r11+20h]
0x18003fd4d  mov     rsp, r11
0x18003fd50  pop     rbp
0x18003fd51  retn
```
