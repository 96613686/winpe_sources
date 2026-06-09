# Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_BuildRequestMessageAsync::StopActivity(void)

- ea: `0x18004c010`
- end: `0x18004c2b1`
- name: `?StopActivity@RequestResponseHandler_BuildRequestMessageAsync@InternalLogger@CloudRequestor@Internal@Windows@@MEAAXXZ`
- size: `673`
- prototype: `void __fastcall(Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_BuildRequestMessageAsync *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x1800013a4`
- `0x180001a6c`
- `0x18004453c`
- `0x18004460c`
- `0x180045c98`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c06a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c20a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c06a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c20a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c251`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c251`

## pseudocode

```c
void __fastcall Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_BuildRequestMessageAsync::StopActivity(
        Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_BuildRequestMessageAsync *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  struct Windows::Internal::CloudRequestor::InternalLogger *v6; // rax
  __int64 v7; // rcx
  _DWORD *v8; // r9
  __int64 v9; // r8
  RTL_SRWLOCK *v10; // rcx
  struct Windows::Internal::CloudRequestor::InternalLogger *v11; // rax
  __int64 v12; // rcx
  _DWORD *v13; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // r9d
  int v17; // [rsp+A0h] [rbp-19h] BYREF
  int v18; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v19; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v20; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v21; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v22; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v23; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v24; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v25; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v26; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v27; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v28[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v30; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v31; // [rsp+130h] [rbp+77h] BYREF
  int v32; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = Windows::Internal::CloudRequestor::InternalLogger::Instance();
    v7 = (__int64)v6 + 16;
    if ( !v6 )
      v7 = 8;
    v8 = *(_DWORD **)v7;
    if ( **(_DWORD **)v7 > 5u
      && (*((_QWORD *)v8 + 2) & 0x200000000000LL) != 0
      && (*((_QWORD *)v8 + 3) & 0x200000000000LL) == *((_QWORD *)v8 + 3) )
    {
      v9 = *((_QWORD *)this + 34);
      v19 = *((_QWORD *)v4 + 15);
      v20 = *((_QWORD *)v4 + 14);
      LODWORD(SRWLock) = v4[26];
      v21 = *((_QWORD *)v4 + 12);
      v22 = *((_QWORD *)v4 + 11);
      v30 = v4[20];
      v23 = *((_QWORD *)v4 + 9);
      LODWORD(v31) = v4[8];
      v24 = *((_QWORD *)v4 + 3);
      v32 = *v4;
      v25 = *((_QWORD *)v4 + 16);
      v17 = v4[16];
      v26 = *((_QWORD *)v4 + 7);
      v18 = v4[2];
      v27 = 0x1000000;
      v28[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v8,
        (unsigned int)&unk_18008DD20,
        v9 + 8,
        (_DWORD)v8,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v18,
        (__int64)&v26,
        (__int64)&v17,
        (__int64)&v25,
        (__int64)&v32,
        (__int64)&v24,
        (__int64)&v31,
        (__int64)&v23,
        (__int64)&v30,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&SRWLock,
        (__int64)&v20,
        (__int64)&v19);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v10 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = Windows::Internal::CloudRequestor::InternalLogger::Instance();
    v12 = (__int64)v11 + 16;
    if ( !v11 )
      v12 = 8;
    v13 = *(_DWORD **)v12;
    if ( **(_DWORD **)v12 > 5u
      && (*((_QWORD *)v13 + 2) & 0x200000000000LL) != 0
      && (*((_QWORD *)v13 + 3) & 0x200000000000LL) == *((_QWORD *)v13 + 3) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v30 = *(_DWORD *)(v15 + 72);
      v31 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v13,
        (unsigned int)&unk_18008DCB0,
        v15 + 8,
        v16,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18004c010  push    rbp
0x18004c012  push    rbx
0x18004c013  push    rdi
0x18004c014  lea     rbp, [rsp-47h]
0x18004c019  sub     rsp, 100h
0x18004c020  mov     rdi, [rcx+110h]
0x18004c027  mov     rbx, rcx
0x18004c02a  mov     eax, [rdi+48h]
0x18004c02d  test    eax, eax
0x18004c02f  jns     loc_18004C1EB
0x18004c035  add     rdi, 50h ; 'P'
0x18004c039  cmp     eax, [rdi+8]
0x18004c03c  jnz     loc_18004C1EB
0x18004c042  test    rdi, rdi
0x18004c045  jz      loc_18004C1EB
0x18004c04b  lea     rdx, [rbp+57h+SRWLock]
0x18004c04f  call    ?LockExclusive@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004c054  mov     rax, [rbx+110h]
0x18004c05b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18004c05f  mov     dword ptr [rax], 2
0x18004c065  test    rcx, rcx
0x18004c068  jz      short loc_18004C070
0x18004c06a  call    cs:__imp_ReleaseSRWLockExclusive
0x18004c070  call    ?Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV1234@XZ; Windows::Internal::CloudRequestor::InternalLogger::Instance(void)
0x18004c075  test    rax, rax
0x18004c078  mov     edx, 8
0x18004c07d  lea     rcx, [rax+10h]
0x18004c081  cmovz   rcx, rdx
0x18004c085  mov     r9, [rcx]
0x18004c088  mov     eax, [r9]
0x18004c08b  cmp     eax, 5
0x18004c08e  jbe     loc_18004C29F
0x18004c094  mov     r8, [r9+18h]
0x18004c098  mov     rcx, 200000000000h
0x18004c0a2  mov     rax, [r9+10h]
0x18004c0a6  test    rcx, rax
0x18004c0a9  jz      loc_18004C29F
0x18004c0af  mov     rax, r8
0x18004c0b2  and     rax, rcx
0x18004c0b5  cmp     rax, r8
0x18004c0b8  jnz     loc_18004C29F
0x18004c0be  mov     rax, [rdi+78h]
0x18004c0c2  mov     rcx, r9
0x18004c0c5  mov     r8, [rbx+110h]
0x18004c0cc  mov     [rbp+57h+var_68], rax
0x18004c0d0  add     r8, rdx
0x18004c0d3  mov     rax, [rdi+70h]
0x18004c0d7  lea     rdx, unk_18008DD20
0x18004c0de  mov     [rbp+57h+var_60], rax
0x18004c0e2  mov     eax, [rdi+68h]
0x18004c0e5  mov     dword ptr [rbp+57h+SRWLock], eax
0x18004c0e8  mov     rax, [rdi+60h]
0x18004c0ec  mov     [rbp+57h+var_58], rax
0x18004c0f0  mov     rax, [rdi+58h]
0x18004c0f4  mov     [rbp+57h+var_50], rax
0x18004c0f8  mov     eax, [rdi+50h]
0x18004c0fb  mov     [rbp+57h+arg_8], eax
0x18004c0fe  mov     rax, [rdi+48h]
0x18004c102  mov     [rbp+57h+var_48], rax
0x18004c106  mov     eax, [rdi+20h]
0x18004c109  mov     dword ptr [rbp+57h+arg_10], eax
0x18004c10c  mov     rax, [rdi+18h]
0x18004c110  mov     [rbp+57h+var_40], rax
0x18004c114  mov     eax, [rdi]
0x18004c116  mov     [rbp+57h+arg_18], eax
0x18004c119  mov     rax, [rdi+80h]
0x18004c120  mov     [rbp+57h+var_38], rax
0x18004c124  mov     eax, [rdi+40h]
0x18004c127  mov     [rbp+57h+var_70], eax
0x18004c12a  mov     rax, [rdi+38h]
0x18004c12e  mov     [rbp+57h+var_30], rax
0x18004c132  mov     eax, [rdi+8]
0x18004c135  mov     [rbp+57h+var_6C], eax
0x18004c138  mov     eax, 1000000h
0x18004c13d  mov     [rbp+57h+var_28], rax
0x18004c141  mov     [rbp+57h+var_20], rax
0x18004c145  lea     rax, [rbp+57h+var_68]
0x18004c149  mov     [rsp+110h+var_78], rax
0x18004c151  lea     rax, [rbp+57h+var_60]
0x18004c155  mov     [rsp+110h+var_80], rax
0x18004c15d  lea     rax, [rbp+57h+SRWLock]
0x18004c161  mov     [rsp+110h+var_88], rax
0x18004c169  lea     rax, [rbp+57h+var_58]
0x18004c16d  mov     [rsp+110h+var_90], rax
0x18004c175  lea     rax, [rbp+57h+var_50]
0x18004c179  mov     [rsp+110h+var_98], rax
0x18004c17e  lea     rax, [rbp+57h+arg_8]
0x18004c182  mov     [rsp+110h+var_A0], rax
0x18004c187  lea     rax, [rbp+57h+var_48]
0x18004c18b  mov     [rsp+110h+var_A8], rax
0x18004c190  lea     rax, [rbp+57h+arg_10]
0x18004c194  mov     [rsp+110h+var_B0], rax
0x18004c199  lea     rax, [rbp+57h+var_40]
0x18004c19d  mov     [rsp+110h+var_B8], rax
0x18004c1a2  lea     rax, [rbp+57h+arg_18]
0x18004c1a6  mov     [rsp+110h+var_C0], rax
0x18004c1ab  lea     rax, [rbp+57h+var_38]
0x18004c1af  mov     [rsp+110h+var_C8], rax
0x18004c1b4  lea     rax, [rbp+57h+var_70]
0x18004c1b8  mov     [rsp+110h+var_D0], rax
0x18004c1bd  lea     rax, [rbp+57h+var_30]
0x18004c1c1  mov     [rsp+110h+var_D8], rax
0x18004c1c6  lea     rax, [rbp+57h+var_6C]
0x18004c1ca  mov     [rsp+110h+var_E0], rax
0x18004c1cf  lea     rax, [rbp+57h+var_28]
0x18004c1d3  mov     [rsp+110h+var_E8], rax
0x18004c1d8  lea     rax, [rbp+57h+var_20]
0x18004c1dc  mov     [rsp+110h+var_F0], rax
0x18004c1e1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18004c1e6  jmp     loc_18004C29F
0x18004c1eb  lea     rdx, [rbp+57h+SRWLock]
0x18004c1ef  call    ?LockExclusive@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004c1f4  mov     rax, [rbx+110h]
0x18004c1fb  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18004c1ff  mov     dword ptr [rax], 2
0x18004c205  test    rcx, rcx
0x18004c208  jz      short loc_18004C210
0x18004c20a  call    cs:__imp_ReleaseSRWLockExclusive
0x18004c210  call    ?Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV1234@XZ; Windows::Internal::CloudRequestor::InternalLogger::Instance(void)
0x18004c215  test    rax, rax
0x18004c218  mov     edx, 8
0x18004c21d  lea     rcx, [rax+10h]
0x18004c221  cmovz   rcx, rdx
0x18004c225  mov     rdi, [rcx]
0x18004c228  mov     eax, [rdi]
0x18004c22a  cmp     eax, 5
0x18004c22d  jbe     short loc_18004C29F
0x18004c22f  mov     rdx, [rdi+18h]
0x18004c233  mov     rcx, 200000000000h
0x18004c23d  mov     rax, [rdi+10h]
0x18004c241  test    rcx, rax
0x18004c244  jz      short loc_18004C29F
0x18004c246  mov     rax, rdx
0x18004c249  and     rax, rcx
0x18004c24c  cmp     rax, rdx
0x18004c24f  jnz     short loc_18004C29F
0x18004c251  call    cs:__imp_GetCurrentThreadId
0x18004c257  mov     r8, [rbx+110h]
0x18004c25e  lea     rdx, unk_18008DCB0
0x18004c265  mov     dword ptr [rbp+57h+SRWLock], eax
0x18004c268  mov     rcx, rdi
0x18004c26b  mov     eax, [r8+48h]
0x18004c26f  add     r8, 8
0x18004c273  mov     [rbp+57h+arg_8], eax
0x18004c276  mov     eax, 1000000h
0x18004c27b  mov     [rbp+57h+arg_10], rax
0x18004c27f  lea     rax, [rbp+57h+SRWLock]
0x18004c283  mov     [rsp+110h+var_E0], rax
0x18004c288  lea     rax, [rbp+57h+arg_8]
0x18004c28c  mov     [rsp+110h+var_E8], rax
0x18004c291  lea     rax, [rbp+57h+arg_10]
0x18004c295  mov     [rsp+110h+var_F0], rax
0x18004c29a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004c29f  mov     rcx, rbx
0x18004c2a2  add     rsp, 100h
0x18004c2a9  pop     rdi
0x18004c2aa  pop     rbx
0x18004c2ab  pop     rbp
0x18004c2ac  jmp     ?IgnoreCurrentThread@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
