# ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::StopActivity(void)

- ea: `0x180040060`
- end: `0x180040353`
- name: `?StopActivity@ClientLib_SyncOperationCompletion@TraceProvider@Diagnostics@ComputeLib@@MEAAXXZ`
- size: `755`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18001c384`
- `0x18001ed48`
- `0x180021d1c`
- `0x180040060`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800400c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004029b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800400c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004029b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800402d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800402d3`

## pseudocode

```c
void __fastcall ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::StopActivity(
        ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion *this)
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
          (int)&byte_1800A0019,
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
          (unsigned int)&dword_1800A0A04,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion *)((char *)this + 288));
}

```

## disassembly

```asm
0x180040060  mov     [rsp-8+arg_8], rbx
0x180040065  mov     [rsp-8+arg_10], rdi
0x18004006a  push    rbp
0x18004006b  mov     rbp, rsp
0x18004006e  sub     rsp, 140h
0x180040075  mov     rbx, rcx
0x180040078  mov     rdi, [rcx+110h]
0x18004007f  mov     eax, [rdi+48h]
0x180040082  test    eax, eax
0x180040084  jns     loc_180040274
0x18004008a  add     rdi, 50h ; 'P'
0x18004008e  cmp     eax, [rdi+8]
0x180040091  jnz     loc_180040274
0x180040097  test    rdi, rdi
0x18004009a  jz      loc_180040274
0x1800400a0  mov     [rbp+SRWLock], 0
0x1800400a8  lea     rdx, [rbp+SRWLock]
0x1800400ac  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800400b1  mov     rax, [rbx+110h]
0x1800400b8  mov     dword ptr [rax], 2
0x1800400be  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800400c2  test    rcx, rcx
0x1800400c5  jz      short loc_1800400D3
0x1800400c7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800400ce  nop     dword ptr [rax+rax+00h]
0x1800400d3  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x1800400d8  mov     r9, rax
0x1800400db  mov     ecx, [rax]
0x1800400dd  cmp     ecx, 4
0x1800400e0  jbe     loc_18004032A
0x1800400e6  mov     rax, [rax+18h]
0x1800400ea  mov     rcx, [r9+10h]
0x1800400ee  mov     edx, 10000h
0x1800400f3  test    rdx, rcx
0x1800400f6  jz      loc_18004032A
0x1800400fc  mov     rcx, rax
0x1800400ff  and     rcx, rdx
0x180040102  cmp     rcx, rax
0x180040105  jnz     loc_18004032A
0x18004010b  mov     rax, [rdi+30h]
0x18004010f  mov     [rbp+var_50], rax
0x180040113  mov     eax, [rdi+44h]
0x180040116  mov     dword ptr [rbp+var_78+4], eax
0x180040119  mov     eax, [rdi+10h]
0x18004011c  mov     dword ptr [rbp+var_70], eax
0x18004011f  mov     rax, [rdi+78h]
0x180040123  mov     [rbp+var_48], rax
0x180040127  mov     rax, [rdi+70h]
0x18004012b  mov     [rbp+var_40], rax
0x18004012f  mov     eax, [rdi+68h]
0x180040132  mov     dword ptr [rbp+var_70+4], eax
0x180040135  mov     rax, [rdi+60h]
0x180040139  mov     [rbp+var_38], rax
0x18004013d  mov     rax, [rdi+58h]
0x180040141  mov     [rbp+var_30], rax
0x180040145  mov     eax, [rdi+50h]
0x180040148  mov     dword ptr [rbp+var_68], eax
0x18004014b  mov     rax, [rdi+48h]
0x18004014f  mov     [rbp+var_28], rax
0x180040153  mov     eax, [rdi+20h]
0x180040156  mov     dword ptr [rbp+var_68+4], eax
0x180040159  mov     rax, [rdi+18h]
0x18004015d  mov     [rbp+var_20], rax
0x180040161  mov     eax, [rdi]
0x180040163  mov     [rbp+var_60], eax
0x180040166  mov     rax, [rdi+80h]
0x18004016d  mov     [rbp+var_18], rax
0x180040171  mov     eax, [rdi+40h]
0x180040174  mov     dword ptr [rbp+var_78], eax
0x180040177  mov     rax, [rdi+38h]
0x18004017b  mov     [rbp+var_10], rax
0x18004017f  mov     eax, [rdi+8]
0x180040182  mov     dword ptr [rbp+SRWLock], eax
0x180040185  mov     [rbp+var_8], 1000000h
0x18004018d  mov     [rbp+var_58], 0
0x180040195  mov     r8, [rbx+110h]
0x18004019c  add     r8, 8; int
0x1800401a0  lea     rax, [rbp+var_50]
0x1800401a4  mov     [rsp+140h+var_90], rax; __int64
0x1800401ac  lea     rax, [rbp+var_78+4]
0x1800401b0  mov     [rsp+140h+var_98], rax; __int64
0x1800401b8  lea     rax, [rbp+var_70]
0x1800401bc  mov     [rsp+140h+var_A0], rax; __int64
0x1800401c4  lea     rax, [rbp+var_48]
0x1800401c8  mov     [rsp+140h+var_A8], rax; __int64
0x1800401d0  lea     rax, [rbp+var_40]
0x1800401d4  mov     [rsp+140h+var_B0], rax; __int64
0x1800401dc  lea     rax, [rbp+var_70+4]
0x1800401e0  mov     [rsp+140h+var_B8], rax; __int64
0x1800401e8  lea     rax, [rbp+var_38]
0x1800401ec  mov     [rsp+140h+var_C0], rax; __int64
0x1800401f4  lea     rax, [rbp+var_30]
0x1800401f8  mov     [rsp+140h+var_C8], rax; __int64
0x1800401fd  lea     rax, [rbp+var_68]
0x180040201  mov     [rsp+140h+var_D0], rax; __int64
0x180040206  lea     rax, [rbp+var_28]
0x18004020a  mov     [rsp+140h+var_D8], rax; __int64
0x18004020f  lea     rax, [rbp+var_68+4]
0x180040213  mov     [rsp+140h+var_E0], rax; __int64
0x180040218  lea     rax, [rbp+var_20]
0x18004021c  mov     [rsp+140h+var_E8], rax; __int64
0x180040221  lea     rax, [rbp+var_60]
0x180040225  mov     [rsp+140h+var_F0], rax; __int64
0x18004022a  lea     rax, [rbp+var_18]
0x18004022e  mov     [rsp+140h+var_F8], rax; __int64
0x180040233  lea     rax, [rbp+var_78]
0x180040237  mov     [rsp+140h+var_100], rax; __int64
0x18004023c  lea     rax, [rbp+var_10]
0x180040240  mov     [rsp+140h+var_108], rax; __int64
0x180040245  lea     rax, [rbp+SRWLock]
0x180040249  mov     [rsp+140h+var_110], rax; __int64
0x18004024e  lea     rax, [rbp+var_8]
0x180040252  mov     [rsp+140h+var_118], rax; __int64
0x180040257  lea     rax, [rbp+var_58]
0x18004025b  mov     [rsp+140h+var_120], rax; __int64
0x180040260  lea     rdx, byte_1800A0019; int
0x180040267  mov     rcx, r9; int
0x18004026a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18004026f  jmp     loc_18004032A
0x180040274  mov     [rbp+SRWLock], 0
0x18004027c  lea     rdx, [rbp+SRWLock]
0x180040280  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180040285  mov     rax, [rbx+110h]
0x18004028c  mov     dword ptr [rax], 2
0x180040292  mov     rcx, [rbp+SRWLock]; SRWLock
0x180040296  test    rcx, rcx
0x180040299  jz      short loc_1800402A7
0x18004029b  call    cs:__imp_ReleaseSRWLockExclusive
0x1800402a2  nop     dword ptr [rax+rax+00h]
0x1800402a7  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x1800402ac  mov     rdi, rax
0x1800402af  mov     ecx, [rax]
0x1800402b1  cmp     ecx, 4
0x1800402b4  jbe     short loc_18004032A
0x1800402b6  mov     rax, [rax+18h]
0x1800402ba  mov     rcx, [rdi+10h]
0x1800402be  mov     edx, 10000h
0x1800402c3  test    rdx, rcx
0x1800402c6  jz      short loc_18004032A
0x1800402c8  mov     rcx, rax
0x1800402cb  and     rcx, rdx
0x1800402ce  cmp     rcx, rax
0x1800402d1  jnz     short loc_18004032A
0x1800402d3  call    cs:__imp_GetCurrentThreadId
0x1800402da  nop     dword ptr [rax+rax+00h]
0x1800402df  mov     dword ptr [rbp+SRWLock], eax
0x1800402e2  mov     r8, [rbx+110h]
0x1800402e9  mov     eax, [r8+48h]
0x1800402ed  mov     dword ptr [rbp+var_78], eax
0x1800402f0  mov     [rbp+var_58], 0
0x1800402f8  add     r8, 8
0x1800402fc  lea     rax, [rbp+SRWLock]
0x180040300  mov     [rsp+140h+var_110], rax
0x180040305  lea     rax, [rbp+var_78]
0x180040309  mov     [rsp+140h+var_118], rax
0x18004030e  lea     rax, [rbp+var_58]
0x180040312  mov     [rsp+140h+var_120], rax
0x180040317  xor     r9d, r9d
0x18004031a  lea     rdx, dword_1800A0A04
0x180040321  mov     rcx, rdi
0x180040324  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180040329  nop
0x18004032a  lea     rcx, [rbx+120h]; this
0x180040331  cmp     dword ptr [rcx+18h], 0
0x180040335  jz      short loc_18004033D
0x180040337  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18004033c  nop
0x18004033d  lea     r11, [rsp+140h+var_s0]
0x180040345  mov     rbx, [r11+18h]
0x180040349  mov     rdi, [r11+20h]
0x18004034d  mov     rsp, r11
0x180040350  pop     rbp
0x180040351  retn
```
