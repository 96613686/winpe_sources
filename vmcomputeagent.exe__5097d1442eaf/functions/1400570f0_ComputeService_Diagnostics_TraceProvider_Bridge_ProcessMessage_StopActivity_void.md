# ComputeService::Diagnostics::TraceProvider::Bridge_ProcessMessage::StopActivity(void)

- ea: `0x1400570f0`
- end: `0x1400573c3`
- name: `?StopActivity@Bridge_ProcessMessage@TraceProvider@Diagnostics@ComputeService@@MEAAXXZ`
- size: `723`
- prototype: `void __fastcall(ComputeService::Diagnostics::TraceProvider::Bridge_ProcessMessage *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400017a8`
- `0x140001abc`
- `0x14000aeec`
- `0x140031be8`
- `0x14003407c`
- `0x1400570f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140057157`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005731d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140057157`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005731d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005734a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005734a`

## pseudocode

```c
void __fastcall ComputeService::Diagnostics::TraceProvider::Bridge_ProcessMessage::StopActivity(
        ComputeService::Diagnostics::TraceProvider::Bridge_ProcessMessage *this)
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
    if ( *(_DWORD *)v5 > 5u && (*(_QWORD *)(v5 + 16) & 4) != 0 && (*(_QWORD *)(v5 + 24) & 4LL) == *(_QWORD *)(v5 + 24) )
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
        (int)&word_14013476E,
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
    if ( *(_DWORD *)v6 > 5u && (*(_QWORD *)(v6 + 16) & 4) != 0 && (*(_QWORD *)(v6 + 24) & 4LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v9 = *(_DWORD *)(v7 + 72);
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)&dword_140134DA4,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeService::Diagnostics::TraceProvider::Bridge_ProcessMessage *)((char *)this + 288));
}

```

## disassembly

```asm
0x1400570f0  mov     [rsp-8+arg_8], rbx
0x1400570f5  mov     [rsp-8+arg_10], rdi
0x1400570fa  push    rbp
0x1400570fb  mov     rbp, rsp
0x1400570fe  sub     rsp, 140h
0x140057105  mov     rbx, rcx
0x140057108  mov     rdi, [rcx+110h]
0x14005710f  mov     eax, [rdi+48h]
0x140057112  test    eax, eax
0x140057114  jns     loc_1400572F6
0x14005711a  add     rdi, 50h ; 'P'
0x14005711e  cmp     eax, [rdi+8]
0x140057121  jnz     loc_1400572F6
0x140057127  test    rdi, rdi
0x14005712a  jz      loc_1400572F6
0x140057130  mov     [rbp+SRWLock], 0
0x140057138  lea     rdx, [rbp+SRWLock]
0x14005713c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140057141  mov     rax, [rbx+110h]
0x140057148  mov     dword ptr [rax], 2
0x14005714e  mov     rcx, [rbp+SRWLock]; SRWLock
0x140057152  test    rcx, rcx
0x140057155  jz      short loc_14005715D
0x140057157  call    cs:__imp_ReleaseSRWLockExclusive
0x14005715d  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x140057162  mov     rcx, [rax+8]; int
0x140057166  mov     eax, [rcx]
0x140057168  cmp     eax, 5
0x14005716b  jbe     loc_14005739B
0x140057171  mov     rdx, [rcx+18h]
0x140057175  mov     rax, [rcx+10h]
0x140057179  test    al, 4
0x14005717b  jz      loc_14005739B
0x140057181  mov     rax, rdx
0x140057184  and     eax, 4
0x140057187  cmp     rax, rdx
0x14005718a  jnz     loc_14005739B
0x140057190  mov     rax, [rdi+30h]
0x140057194  mov     [rbp+var_50], rax
0x140057198  mov     eax, [rdi+44h]
0x14005719b  mov     dword ptr [rbp+var_78+4], eax
0x14005719e  mov     eax, [rdi+10h]
0x1400571a1  mov     dword ptr [rbp+var_70], eax
0x1400571a4  mov     rax, [rdi+78h]
0x1400571a8  mov     [rbp+var_48], rax
0x1400571ac  mov     rax, [rdi+70h]
0x1400571b0  mov     [rbp+var_40], rax
0x1400571b4  mov     eax, [rdi+68h]
0x1400571b7  mov     dword ptr [rbp+var_70+4], eax
0x1400571ba  mov     rax, [rdi+60h]
0x1400571be  mov     [rbp+var_38], rax
0x1400571c2  mov     rax, [rdi+58h]
0x1400571c6  mov     [rbp+var_30], rax
0x1400571ca  mov     eax, [rdi+50h]
0x1400571cd  mov     dword ptr [rbp+var_68], eax
0x1400571d0  mov     rax, [rdi+48h]
0x1400571d4  mov     [rbp+var_28], rax
0x1400571d8  mov     eax, [rdi+20h]
0x1400571db  mov     dword ptr [rbp+var_68+4], eax
0x1400571de  mov     rax, [rdi+18h]
0x1400571e2  mov     [rbp+var_20], rax
0x1400571e6  mov     eax, [rdi]
0x1400571e8  mov     [rbp+var_60], eax
0x1400571eb  mov     rax, [rdi+80h]
0x1400571f2  mov     [rbp+var_18], rax
0x1400571f6  mov     eax, [rdi+40h]
0x1400571f9  mov     dword ptr [rbp+var_78], eax
0x1400571fc  mov     rax, [rdi+38h]
0x140057200  mov     [rbp+var_10], rax
0x140057204  mov     eax, [rdi+8]
0x140057207  mov     dword ptr [rbp+SRWLock], eax
0x14005720a  mov     [rbp+var_8], 1000000h
0x140057212  mov     [rbp+var_58], 0
0x14005721a  mov     r8, [rbx+110h]
0x140057221  add     r8, 8; int
0x140057225  lea     rax, [rbp+var_50]
0x140057229  mov     [rsp+140h+var_90], rax; __int64
0x140057231  lea     rax, [rbp+var_78+4]
0x140057235  mov     [rsp+140h+var_98], rax; __int64
0x14005723d  lea     rax, [rbp+var_70]
0x140057241  mov     [rsp+140h+var_A0], rax; __int64
0x140057249  lea     rax, [rbp+var_48]
0x14005724d  mov     [rsp+140h+var_A8], rax; __int64
0x140057255  lea     rax, [rbp+var_40]
0x140057259  mov     [rsp+140h+var_B0], rax; __int64
0x140057261  lea     rax, [rbp+var_70+4]
0x140057265  mov     [rsp+140h+var_B8], rax; __int64
0x14005726d  lea     rax, [rbp+var_38]
0x140057271  mov     [rsp+140h+var_C0], rax; __int64
0x140057279  lea     rax, [rbp+var_30]
0x14005727d  mov     [rsp+140h+var_C8], rax; __int64
0x140057282  lea     rax, [rbp+var_68]
0x140057286  mov     [rsp+140h+var_D0], rax; __int64
0x14005728b  lea     rax, [rbp+var_28]
0x14005728f  mov     [rsp+140h+var_D8], rax; __int64
0x140057294  lea     rax, [rbp+var_68+4]
0x140057298  mov     [rsp+140h+var_E0], rax; __int64
0x14005729d  lea     rax, [rbp+var_20]
0x1400572a1  mov     [rsp+140h+var_E8], rax; __int64
0x1400572a6  lea     rax, [rbp+var_60]
0x1400572aa  mov     [rsp+140h+var_F0], rax; __int64
0x1400572af  lea     rax, [rbp+var_18]
0x1400572b3  mov     [rsp+140h+var_F8], rax; __int64
0x1400572b8  lea     rax, [rbp+var_78]
0x1400572bc  mov     [rsp+140h+var_100], rax; __int64
0x1400572c1  lea     rax, [rbp+var_10]
0x1400572c5  mov     [rsp+140h+var_108], rax; __int64
0x1400572ca  lea     rax, [rbp+SRWLock]
0x1400572ce  mov     [rsp+140h+var_110], rax; __int64
0x1400572d3  lea     rax, [rbp+var_8]
0x1400572d7  mov     [rsp+140h+var_118], rax; __int64
0x1400572dc  lea     rax, [rbp+var_58]
0x1400572e0  mov     [rsp+140h+var_120], rax; __int64
0x1400572e5  lea     rdx, word_14013476E; int
0x1400572ec  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400572f1  jmp     loc_14005739B
0x1400572f6  mov     [rbp+SRWLock], 0
0x1400572fe  lea     rdx, [rbp+SRWLock]
0x140057302  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140057307  mov     rax, [rbx+110h]
0x14005730e  mov     dword ptr [rax], 2
0x140057314  mov     rcx, [rbp+SRWLock]; SRWLock
0x140057318  test    rcx, rcx
0x14005731b  jz      short loc_140057323
0x14005731d  call    cs:__imp_ReleaseSRWLockExclusive
0x140057323  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x140057328  mov     rdi, [rax+8]
0x14005732c  mov     eax, [rdi]
0x14005732e  cmp     eax, 5
0x140057331  jbe     short loc_14005739B
0x140057333  mov     rcx, [rdi+18h]
0x140057337  mov     rax, [rdi+10h]
0x14005733b  test    al, 4
0x14005733d  jz      short loc_14005739B
0x14005733f  mov     rax, rcx
0x140057342  and     eax, 4
0x140057345  cmp     rax, rcx
0x140057348  jnz     short loc_14005739B
0x14005734a  call    cs:__imp_GetCurrentThreadId
0x140057350  mov     dword ptr [rbp+SRWLock], eax
0x140057353  mov     r8, [rbx+110h]
0x14005735a  mov     eax, [r8+48h]
0x14005735e  mov     dword ptr [rbp+var_78], eax
0x140057361  mov     [rbp+var_58], 0
0x140057369  add     r8, 8
0x14005736d  lea     rax, [rbp+SRWLock]
0x140057371  mov     [rsp+140h+var_110], rax
0x140057376  lea     rax, [rbp+var_78]
0x14005737a  mov     [rsp+140h+var_118], rax
0x14005737f  lea     rax, [rbp+var_58]
0x140057383  mov     [rsp+140h+var_120], rax
0x140057388  xor     r9d, r9d
0x14005738b  lea     rdx, dword_140134DA4
0x140057392  mov     rcx, rdi
0x140057395  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14005739a  nop
0x14005739b  lea     rcx, [rbx+120h]; this
0x1400573a2  cmp     dword ptr [rcx+18h], 0
0x1400573a6  jz      short loc_1400573AE
0x1400573a8  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1400573ad  nop
0x1400573ae  lea     r11, [rsp+140h+var_s0]
0x1400573b6  mov     rbx, [r11+18h]
0x1400573ba  mov     rdi, [r11+20h]
0x1400573be  mov     rsp, r11
0x1400573c1  pop     rbp
0x1400573c2  retn
```
