# Windows::Internal::CloudRequestor::InternalLogger::CommonNotificationsInterface_CreateOrUpdateSubscriptionAsync::StopActivity(void)

- ea: `0x18005e000`
- end: `0x18005e2a1`
- name: `?StopActivity@CommonNotificationsInterface_CreateOrUpdateSubscriptionAsync@InternalLogger@CloudRequestor@Internal@Windows@@MEAAXXZ`
- size: `673`
- prototype: `void __fastcall(Windows::Internal::CloudRequestor::InternalLogger::CommonNotificationsInterface_CreateOrUpdateSubscriptionAsync *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800013a4`
- `0x180001a6c`
- `0x18004453c`
- `0x18004460c`
- `0x180045c98`
- `0x18005e000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e05a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e1fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e05a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e1fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e241`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e241`

## pseudocode

```c
void __fastcall Windows::Internal::CloudRequestor::InternalLogger::CommonNotificationsInterface_CreateOrUpdateSubscriptionAsync::StopActivity(
        Windows::Internal::CloudRequestor::InternalLogger::CommonNotificationsInterface_CreateOrUpdateSubscriptionAsync *this)
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
        (unsigned int)&unk_18008E340,
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
        (unsigned int)byte_18008E2C3,
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
0x18005e000  push    rbp
0x18005e002  push    rbx
0x18005e003  push    rdi
0x18005e004  lea     rbp, [rsp-47h]
0x18005e009  sub     rsp, 100h
0x18005e010  mov     rdi, [rcx+110h]
0x18005e017  mov     rbx, rcx
0x18005e01a  mov     eax, [rdi+48h]
0x18005e01d  test    eax, eax
0x18005e01f  jns     loc_18005E1DB
0x18005e025  add     rdi, 50h ; 'P'
0x18005e029  cmp     eax, [rdi+8]
0x18005e02c  jnz     loc_18005E1DB
0x18005e032  test    rdi, rdi
0x18005e035  jz      loc_18005E1DB
0x18005e03b  lea     rdx, [rbp+57h+SRWLock]
0x18005e03f  call    ?LockExclusive@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18005e044  mov     rax, [rbx+110h]
0x18005e04b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18005e04f  mov     dword ptr [rax], 2
0x18005e055  test    rcx, rcx
0x18005e058  jz      short loc_18005E060
0x18005e05a  call    cs:__imp_ReleaseSRWLockExclusive
0x18005e060  call    ?Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV1234@XZ; Windows::Internal::CloudRequestor::InternalLogger::Instance(void)
0x18005e065  test    rax, rax
0x18005e068  mov     edx, 8
0x18005e06d  lea     rcx, [rax+10h]
0x18005e071  cmovz   rcx, rdx
0x18005e075  mov     r9, [rcx]
0x18005e078  mov     eax, [r9]
0x18005e07b  cmp     eax, 5
0x18005e07e  jbe     loc_18005E28F
0x18005e084  mov     r8, [r9+18h]
0x18005e088  mov     rcx, 200000000000h
0x18005e092  mov     rax, [r9+10h]
0x18005e096  test    rcx, rax
0x18005e099  jz      loc_18005E28F
0x18005e09f  mov     rax, r8
0x18005e0a2  and     rax, rcx
0x18005e0a5  cmp     rax, r8
0x18005e0a8  jnz     loc_18005E28F
0x18005e0ae  mov     rax, [rdi+78h]
0x18005e0b2  mov     rcx, r9
0x18005e0b5  mov     r8, [rbx+110h]
0x18005e0bc  mov     [rbp+57h+var_68], rax
0x18005e0c0  add     r8, rdx
0x18005e0c3  mov     rax, [rdi+70h]
0x18005e0c7  lea     rdx, unk_18008E340
0x18005e0ce  mov     [rbp+57h+var_60], rax
0x18005e0d2  mov     eax, [rdi+68h]
0x18005e0d5  mov     dword ptr [rbp+57h+SRWLock], eax
0x18005e0d8  mov     rax, [rdi+60h]
0x18005e0dc  mov     [rbp+57h+var_58], rax
0x18005e0e0  mov     rax, [rdi+58h]
0x18005e0e4  mov     [rbp+57h+var_50], rax
0x18005e0e8  mov     eax, [rdi+50h]
0x18005e0eb  mov     [rbp+57h+arg_8], eax
0x18005e0ee  mov     rax, [rdi+48h]
0x18005e0f2  mov     [rbp+57h+var_48], rax
0x18005e0f6  mov     eax, [rdi+20h]
0x18005e0f9  mov     dword ptr [rbp+57h+arg_10], eax
0x18005e0fc  mov     rax, [rdi+18h]
0x18005e100  mov     [rbp+57h+var_40], rax
0x18005e104  mov     eax, [rdi]
0x18005e106  mov     [rbp+57h+arg_18], eax
0x18005e109  mov     rax, [rdi+80h]
0x18005e110  mov     [rbp+57h+var_38], rax
0x18005e114  mov     eax, [rdi+40h]
0x18005e117  mov     [rbp+57h+var_70], eax
0x18005e11a  mov     rax, [rdi+38h]
0x18005e11e  mov     [rbp+57h+var_30], rax
0x18005e122  mov     eax, [rdi+8]
0x18005e125  mov     [rbp+57h+var_6C], eax
0x18005e128  mov     eax, 1000000h
0x18005e12d  mov     [rbp+57h+var_28], rax
0x18005e131  mov     [rbp+57h+var_20], rax
0x18005e135  lea     rax, [rbp+57h+var_68]
0x18005e139  mov     [rsp+110h+var_78], rax
0x18005e141  lea     rax, [rbp+57h+var_60]
0x18005e145  mov     [rsp+110h+var_80], rax
0x18005e14d  lea     rax, [rbp+57h+SRWLock]
0x18005e151  mov     [rsp+110h+var_88], rax
0x18005e159  lea     rax, [rbp+57h+var_58]
0x18005e15d  mov     [rsp+110h+var_90], rax
0x18005e165  lea     rax, [rbp+57h+var_50]
0x18005e169  mov     [rsp+110h+var_98], rax
0x18005e16e  lea     rax, [rbp+57h+arg_8]
0x18005e172  mov     [rsp+110h+var_A0], rax
0x18005e177  lea     rax, [rbp+57h+var_48]
0x18005e17b  mov     [rsp+110h+var_A8], rax
0x18005e180  lea     rax, [rbp+57h+arg_10]
0x18005e184  mov     [rsp+110h+var_B0], rax
0x18005e189  lea     rax, [rbp+57h+var_40]
0x18005e18d  mov     [rsp+110h+var_B8], rax
0x18005e192  lea     rax, [rbp+57h+arg_18]
0x18005e196  mov     [rsp+110h+var_C0], rax
0x18005e19b  lea     rax, [rbp+57h+var_38]
0x18005e19f  mov     [rsp+110h+var_C8], rax
0x18005e1a4  lea     rax, [rbp+57h+var_70]
0x18005e1a8  mov     [rsp+110h+var_D0], rax
0x18005e1ad  lea     rax, [rbp+57h+var_30]
0x18005e1b1  mov     [rsp+110h+var_D8], rax
0x18005e1b6  lea     rax, [rbp+57h+var_6C]
0x18005e1ba  mov     [rsp+110h+var_E0], rax
0x18005e1bf  lea     rax, [rbp+57h+var_28]
0x18005e1c3  mov     [rsp+110h+var_E8], rax
0x18005e1c8  lea     rax, [rbp+57h+var_20]
0x18005e1cc  mov     [rsp+110h+var_F0], rax
0x18005e1d1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18005e1d6  jmp     loc_18005E28F
0x18005e1db  lea     rdx, [rbp+57h+SRWLock]
0x18005e1df  call    ?LockExclusive@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18005e1e4  mov     rax, [rbx+110h]
0x18005e1eb  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18005e1ef  mov     dword ptr [rax], 2
0x18005e1f5  test    rcx, rcx
0x18005e1f8  jz      short loc_18005E200
0x18005e1fa  call    cs:__imp_ReleaseSRWLockExclusive
0x18005e200  call    ?Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV1234@XZ; Windows::Internal::CloudRequestor::InternalLogger::Instance(void)
0x18005e205  test    rax, rax
0x18005e208  mov     edx, 8
0x18005e20d  lea     rcx, [rax+10h]
0x18005e211  cmovz   rcx, rdx
0x18005e215  mov     rdi, [rcx]
0x18005e218  mov     eax, [rdi]
0x18005e21a  cmp     eax, 5
0x18005e21d  jbe     short loc_18005E28F
0x18005e21f  mov     rdx, [rdi+18h]
0x18005e223  mov     rcx, 200000000000h
0x18005e22d  mov     rax, [rdi+10h]
0x18005e231  test    rcx, rax
0x18005e234  jz      short loc_18005E28F
0x18005e236  mov     rax, rdx
0x18005e239  and     rax, rcx
0x18005e23c  cmp     rax, rdx
0x18005e23f  jnz     short loc_18005E28F
0x18005e241  call    cs:__imp_GetCurrentThreadId
0x18005e247  mov     r8, [rbx+110h]
0x18005e24e  lea     rdx, byte_18008E2C3
0x18005e255  mov     dword ptr [rbp+57h+SRWLock], eax
0x18005e258  mov     rcx, rdi
0x18005e25b  mov     eax, [r8+48h]
0x18005e25f  add     r8, 8
0x18005e263  mov     [rbp+57h+arg_8], eax
0x18005e266  mov     eax, 1000000h
0x18005e26b  mov     [rbp+57h+arg_10], rax
0x18005e26f  lea     rax, [rbp+57h+SRWLock]
0x18005e273  mov     [rsp+110h+var_E0], rax
0x18005e278  lea     rax, [rbp+57h+arg_8]
0x18005e27c  mov     [rsp+110h+var_E8], rax
0x18005e281  lea     rax, [rbp+57h+arg_10]
0x18005e285  mov     [rsp+110h+var_F0], rax
0x18005e28a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005e28f  mov     rcx, rbx
0x18005e292  add     rsp, 100h
0x18005e299  pop     rdi
0x18005e29a  pop     rbx
0x18005e29b  pop     rbp
0x18005e29c  jmp     ?IgnoreCurrentThread@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
