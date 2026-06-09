# Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_ProcessResponseMessage::StopActivity(void)

- ea: `0x18004c2c0`
- end: `0x18004c561`
- name: `?StopActivity@RequestResponseHandler_ProcessResponseMessage@InternalLogger@CloudRequestor@Internal@Windows@@MEAAXXZ`
- size: `673`
- prototype: `void __fastcall(Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_ProcessResponseMessage *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x1800013a4`
- `0x180001a6c`
- `0x18004453c`
- `0x18004460c`
- `0x180045c98`
- `0x18004c2c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c31a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c4ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c31a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c4ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c501`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c501`

## pseudocode

```c
void __fastcall Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_ProcessResponseMessage::StopActivity(
        Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_ProcessResponseMessage *this)
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
        (unsigned int)&dword_18008DB04,
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
        (unsigned int)&word_18008DA96,
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
0x18004c2c0  push    rbp
0x18004c2c2  push    rbx
0x18004c2c3  push    rdi
0x18004c2c4  lea     rbp, [rsp-47h]
0x18004c2c9  sub     rsp, 100h
0x18004c2d0  mov     rdi, [rcx+110h]
0x18004c2d7  mov     rbx, rcx
0x18004c2da  mov     eax, [rdi+48h]
0x18004c2dd  test    eax, eax
0x18004c2df  jns     loc_18004C49B
0x18004c2e5  add     rdi, 50h ; 'P'
0x18004c2e9  cmp     eax, [rdi+8]
0x18004c2ec  jnz     loc_18004C49B
0x18004c2f2  test    rdi, rdi
0x18004c2f5  jz      loc_18004C49B
0x18004c2fb  lea     rdx, [rbp+57h+SRWLock]
0x18004c2ff  call    ?LockExclusive@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004c304  mov     rax, [rbx+110h]
0x18004c30b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18004c30f  mov     dword ptr [rax], 2
0x18004c315  test    rcx, rcx
0x18004c318  jz      short loc_18004C320
0x18004c31a  call    cs:__imp_ReleaseSRWLockExclusive
0x18004c320  call    ?Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV1234@XZ; Windows::Internal::CloudRequestor::InternalLogger::Instance(void)
0x18004c325  test    rax, rax
0x18004c328  mov     edx, 8
0x18004c32d  lea     rcx, [rax+10h]
0x18004c331  cmovz   rcx, rdx
0x18004c335  mov     r9, [rcx]
0x18004c338  mov     eax, [r9]
0x18004c33b  cmp     eax, 5
0x18004c33e  jbe     loc_18004C54F
0x18004c344  mov     r8, [r9+18h]
0x18004c348  mov     rcx, 200000000000h
0x18004c352  mov     rax, [r9+10h]
0x18004c356  test    rcx, rax
0x18004c359  jz      loc_18004C54F
0x18004c35f  mov     rax, r8
0x18004c362  and     rax, rcx
0x18004c365  cmp     rax, r8
0x18004c368  jnz     loc_18004C54F
0x18004c36e  mov     rax, [rdi+78h]
0x18004c372  mov     rcx, r9
0x18004c375  mov     r8, [rbx+110h]
0x18004c37c  mov     [rbp+57h+var_68], rax
0x18004c380  add     r8, rdx
0x18004c383  mov     rax, [rdi+70h]
0x18004c387  lea     rdx, dword_18008DB04
0x18004c38e  mov     [rbp+57h+var_60], rax
0x18004c392  mov     eax, [rdi+68h]
0x18004c395  mov     dword ptr [rbp+57h+SRWLock], eax
0x18004c398  mov     rax, [rdi+60h]
0x18004c39c  mov     [rbp+57h+var_58], rax
0x18004c3a0  mov     rax, [rdi+58h]
0x18004c3a4  mov     [rbp+57h+var_50], rax
0x18004c3a8  mov     eax, [rdi+50h]
0x18004c3ab  mov     [rbp+57h+arg_8], eax
0x18004c3ae  mov     rax, [rdi+48h]
0x18004c3b2  mov     [rbp+57h+var_48], rax
0x18004c3b6  mov     eax, [rdi+20h]
0x18004c3b9  mov     dword ptr [rbp+57h+arg_10], eax
0x18004c3bc  mov     rax, [rdi+18h]
0x18004c3c0  mov     [rbp+57h+var_40], rax
0x18004c3c4  mov     eax, [rdi]
0x18004c3c6  mov     [rbp+57h+arg_18], eax
0x18004c3c9  mov     rax, [rdi+80h]
0x18004c3d0  mov     [rbp+57h+var_38], rax
0x18004c3d4  mov     eax, [rdi+40h]
0x18004c3d7  mov     [rbp+57h+var_70], eax
0x18004c3da  mov     rax, [rdi+38h]
0x18004c3de  mov     [rbp+57h+var_30], rax
0x18004c3e2  mov     eax, [rdi+8]
0x18004c3e5  mov     [rbp+57h+var_6C], eax
0x18004c3e8  mov     eax, 1000000h
0x18004c3ed  mov     [rbp+57h+var_28], rax
0x18004c3f1  mov     [rbp+57h+var_20], rax
0x18004c3f5  lea     rax, [rbp+57h+var_68]
0x18004c3f9  mov     [rsp+110h+var_78], rax
0x18004c401  lea     rax, [rbp+57h+var_60]
0x18004c405  mov     [rsp+110h+var_80], rax
0x18004c40d  lea     rax, [rbp+57h+SRWLock]
0x18004c411  mov     [rsp+110h+var_88], rax
0x18004c419  lea     rax, [rbp+57h+var_58]
0x18004c41d  mov     [rsp+110h+var_90], rax
0x18004c425  lea     rax, [rbp+57h+var_50]
0x18004c429  mov     [rsp+110h+var_98], rax
0x18004c42e  lea     rax, [rbp+57h+arg_8]
0x18004c432  mov     [rsp+110h+var_A0], rax
0x18004c437  lea     rax, [rbp+57h+var_48]
0x18004c43b  mov     [rsp+110h+var_A8], rax
0x18004c440  lea     rax, [rbp+57h+arg_10]
0x18004c444  mov     [rsp+110h+var_B0], rax
0x18004c449  lea     rax, [rbp+57h+var_40]
0x18004c44d  mov     [rsp+110h+var_B8], rax
0x18004c452  lea     rax, [rbp+57h+arg_18]
0x18004c456  mov     [rsp+110h+var_C0], rax
0x18004c45b  lea     rax, [rbp+57h+var_38]
0x18004c45f  mov     [rsp+110h+var_C8], rax
0x18004c464  lea     rax, [rbp+57h+var_70]
0x18004c468  mov     [rsp+110h+var_D0], rax
0x18004c46d  lea     rax, [rbp+57h+var_30]
0x18004c471  mov     [rsp+110h+var_D8], rax
0x18004c476  lea     rax, [rbp+57h+var_6C]
0x18004c47a  mov     [rsp+110h+var_E0], rax
0x18004c47f  lea     rax, [rbp+57h+var_28]
0x18004c483  mov     [rsp+110h+var_E8], rax
0x18004c488  lea     rax, [rbp+57h+var_20]
0x18004c48c  mov     [rsp+110h+var_F0], rax
0x18004c491  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18004c496  jmp     loc_18004C54F
0x18004c49b  lea     rdx, [rbp+57h+SRWLock]
0x18004c49f  call    ?LockExclusive@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004c4a4  mov     rax, [rbx+110h]
0x18004c4ab  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18004c4af  mov     dword ptr [rax], 2
0x18004c4b5  test    rcx, rcx
0x18004c4b8  jz      short loc_18004C4C0
0x18004c4ba  call    cs:__imp_ReleaseSRWLockExclusive
0x18004c4c0  call    ?Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV1234@XZ; Windows::Internal::CloudRequestor::InternalLogger::Instance(void)
0x18004c4c5  test    rax, rax
0x18004c4c8  mov     edx, 8
0x18004c4cd  lea     rcx, [rax+10h]
0x18004c4d1  cmovz   rcx, rdx
0x18004c4d5  mov     rdi, [rcx]
0x18004c4d8  mov     eax, [rdi]
0x18004c4da  cmp     eax, 5
0x18004c4dd  jbe     short loc_18004C54F
0x18004c4df  mov     rdx, [rdi+18h]
0x18004c4e3  mov     rcx, 200000000000h
0x18004c4ed  mov     rax, [rdi+10h]
0x18004c4f1  test    rcx, rax
0x18004c4f4  jz      short loc_18004C54F
0x18004c4f6  mov     rax, rdx
0x18004c4f9  and     rax, rcx
0x18004c4fc  cmp     rax, rdx
0x18004c4ff  jnz     short loc_18004C54F
0x18004c501  call    cs:__imp_GetCurrentThreadId
0x18004c507  mov     r8, [rbx+110h]
0x18004c50e  lea     rdx, word_18008DA96
0x18004c515  mov     dword ptr [rbp+57h+SRWLock], eax
0x18004c518  mov     rcx, rdi
0x18004c51b  mov     eax, [r8+48h]
0x18004c51f  add     r8, 8
0x18004c523  mov     [rbp+57h+arg_8], eax
0x18004c526  mov     eax, 1000000h
0x18004c52b  mov     [rbp+57h+arg_10], rax
0x18004c52f  lea     rax, [rbp+57h+SRWLock]
0x18004c533  mov     [rsp+110h+var_E0], rax
0x18004c538  lea     rax, [rbp+57h+arg_8]
0x18004c53c  mov     [rsp+110h+var_E8], rax
0x18004c541  lea     rax, [rbp+57h+arg_10]
0x18004c545  mov     [rsp+110h+var_F0], rax
0x18004c54a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004c54f  mov     rcx, rbx
0x18004c552  add     rsp, 100h
0x18004c559  pop     rdi
0x18004c55a  pop     rbx
0x18004c55b  pop     rbp
0x18004c55c  jmp     ?IgnoreCurrentThread@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
