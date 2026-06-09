# Windows::Internal::CloudRequestor::InternalLogger::CommonHttpInterface_ProcessRequestAsync::StopActivity(void)

- ea: `0x180054ec0`
- end: `0x180055161`
- name: `?StopActivity@CommonHttpInterface_ProcessRequestAsync@InternalLogger@CloudRequestor@Internal@Windows@@MEAAXXZ`
- size: `673`
- prototype: `void __fastcall(Windows::Internal::CloudRequestor::InternalLogger::CommonHttpInterface_ProcessRequestAsync *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800013a4`
- `0x180001a6c`
- `0x18004453c`
- `0x18004460c`
- `0x180045c98`
- `0x180054ec0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054f1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800550ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054f1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800550ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180055101`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180055101`

## pseudocode

```c
void __fastcall Windows::Internal::CloudRequestor::InternalLogger::CommonHttpInterface_ProcessRequestAsync::StopActivity(
        Windows::Internal::CloudRequestor::InternalLogger::CommonHttpInterface_ProcessRequestAsync *this)
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
        (unsigned int)&unk_18008E110,
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
        (unsigned int)byte_18008E049,
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
0x180054ec0  push    rbp
0x180054ec2  push    rbx
0x180054ec3  push    rdi
0x180054ec4  lea     rbp, [rsp-47h]
0x180054ec9  sub     rsp, 100h
0x180054ed0  mov     rdi, [rcx+110h]
0x180054ed7  mov     rbx, rcx
0x180054eda  mov     eax, [rdi+48h]
0x180054edd  test    eax, eax
0x180054edf  jns     loc_18005509B
0x180054ee5  add     rdi, 50h ; 'P'
0x180054ee9  cmp     eax, [rdi+8]
0x180054eec  jnz     loc_18005509B
0x180054ef2  test    rdi, rdi
0x180054ef5  jz      loc_18005509B
0x180054efb  lea     rdx, [rbp+57h+SRWLock]
0x180054eff  call    ?LockExclusive@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180054f04  mov     rax, [rbx+110h]
0x180054f0b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180054f0f  mov     dword ptr [rax], 2
0x180054f15  test    rcx, rcx
0x180054f18  jz      short loc_180054F20
0x180054f1a  call    cs:__imp_ReleaseSRWLockExclusive
0x180054f20  call    ?Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV1234@XZ; Windows::Internal::CloudRequestor::InternalLogger::Instance(void)
0x180054f25  test    rax, rax
0x180054f28  mov     edx, 8
0x180054f2d  lea     rcx, [rax+10h]
0x180054f31  cmovz   rcx, rdx
0x180054f35  mov     r9, [rcx]
0x180054f38  mov     eax, [r9]
0x180054f3b  cmp     eax, 5
0x180054f3e  jbe     loc_18005514F
0x180054f44  mov     r8, [r9+18h]
0x180054f48  mov     rcx, 200000000000h
0x180054f52  mov     rax, [r9+10h]
0x180054f56  test    rcx, rax
0x180054f59  jz      loc_18005514F
0x180054f5f  mov     rax, r8
0x180054f62  and     rax, rcx
0x180054f65  cmp     rax, r8
0x180054f68  jnz     loc_18005514F
0x180054f6e  mov     rax, [rdi+78h]
0x180054f72  mov     rcx, r9
0x180054f75  mov     r8, [rbx+110h]
0x180054f7c  mov     [rbp+57h+var_68], rax
0x180054f80  add     r8, rdx
0x180054f83  mov     rax, [rdi+70h]
0x180054f87  lea     rdx, unk_18008E110
0x180054f8e  mov     [rbp+57h+var_60], rax
0x180054f92  mov     eax, [rdi+68h]
0x180054f95  mov     dword ptr [rbp+57h+SRWLock], eax
0x180054f98  mov     rax, [rdi+60h]
0x180054f9c  mov     [rbp+57h+var_58], rax
0x180054fa0  mov     rax, [rdi+58h]
0x180054fa4  mov     [rbp+57h+var_50], rax
0x180054fa8  mov     eax, [rdi+50h]
0x180054fab  mov     [rbp+57h+arg_8], eax
0x180054fae  mov     rax, [rdi+48h]
0x180054fb2  mov     [rbp+57h+var_48], rax
0x180054fb6  mov     eax, [rdi+20h]
0x180054fb9  mov     dword ptr [rbp+57h+arg_10], eax
0x180054fbc  mov     rax, [rdi+18h]
0x180054fc0  mov     [rbp+57h+var_40], rax
0x180054fc4  mov     eax, [rdi]
0x180054fc6  mov     [rbp+57h+arg_18], eax
0x180054fc9  mov     rax, [rdi+80h]
0x180054fd0  mov     [rbp+57h+var_38], rax
0x180054fd4  mov     eax, [rdi+40h]
0x180054fd7  mov     [rbp+57h+var_70], eax
0x180054fda  mov     rax, [rdi+38h]
0x180054fde  mov     [rbp+57h+var_30], rax
0x180054fe2  mov     eax, [rdi+8]
0x180054fe5  mov     [rbp+57h+var_6C], eax
0x180054fe8  mov     eax, 1000000h
0x180054fed  mov     [rbp+57h+var_28], rax
0x180054ff1  mov     [rbp+57h+var_20], rax
0x180054ff5  lea     rax, [rbp+57h+var_68]
0x180054ff9  mov     [rsp+110h+var_78], rax
0x180055001  lea     rax, [rbp+57h+var_60]
0x180055005  mov     [rsp+110h+var_80], rax
0x18005500d  lea     rax, [rbp+57h+SRWLock]
0x180055011  mov     [rsp+110h+var_88], rax
0x180055019  lea     rax, [rbp+57h+var_58]
0x18005501d  mov     [rsp+110h+var_90], rax
0x180055025  lea     rax, [rbp+57h+var_50]
0x180055029  mov     [rsp+110h+var_98], rax
0x18005502e  lea     rax, [rbp+57h+arg_8]
0x180055032  mov     [rsp+110h+var_A0], rax
0x180055037  lea     rax, [rbp+57h+var_48]
0x18005503b  mov     [rsp+110h+var_A8], rax
0x180055040  lea     rax, [rbp+57h+arg_10]
0x180055044  mov     [rsp+110h+var_B0], rax
0x180055049  lea     rax, [rbp+57h+var_40]
0x18005504d  mov     [rsp+110h+var_B8], rax
0x180055052  lea     rax, [rbp+57h+arg_18]
0x180055056  mov     [rsp+110h+var_C0], rax
0x18005505b  lea     rax, [rbp+57h+var_38]
0x18005505f  mov     [rsp+110h+var_C8], rax
0x180055064  lea     rax, [rbp+57h+var_70]
0x180055068  mov     [rsp+110h+var_D0], rax
0x18005506d  lea     rax, [rbp+57h+var_30]
0x180055071  mov     [rsp+110h+var_D8], rax
0x180055076  lea     rax, [rbp+57h+var_6C]
0x18005507a  mov     [rsp+110h+var_E0], rax
0x18005507f  lea     rax, [rbp+57h+var_28]
0x180055083  mov     [rsp+110h+var_E8], rax
0x180055088  lea     rax, [rbp+57h+var_20]
0x18005508c  mov     [rsp+110h+var_F0], rax
0x180055091  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180055096  jmp     loc_18005514F
0x18005509b  lea     rdx, [rbp+57h+SRWLock]
0x18005509f  call    ?LockExclusive@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800550a4  mov     rax, [rbx+110h]
0x1800550ab  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800550af  mov     dword ptr [rax], 2
0x1800550b5  test    rcx, rcx
0x1800550b8  jz      short loc_1800550C0
0x1800550ba  call    cs:__imp_ReleaseSRWLockExclusive
0x1800550c0  call    ?Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV1234@XZ; Windows::Internal::CloudRequestor::InternalLogger::Instance(void)
0x1800550c5  test    rax, rax
0x1800550c8  mov     edx, 8
0x1800550cd  lea     rcx, [rax+10h]
0x1800550d1  cmovz   rcx, rdx
0x1800550d5  mov     rdi, [rcx]
0x1800550d8  mov     eax, [rdi]
0x1800550da  cmp     eax, 5
0x1800550dd  jbe     short loc_18005514F
0x1800550df  mov     rdx, [rdi+18h]
0x1800550e3  mov     rcx, 200000000000h
0x1800550ed  mov     rax, [rdi+10h]
0x1800550f1  test    rcx, rax
0x1800550f4  jz      short loc_18005514F
0x1800550f6  mov     rax, rdx
0x1800550f9  and     rax, rcx
0x1800550fc  cmp     rax, rdx
0x1800550ff  jnz     short loc_18005514F
0x180055101  call    cs:__imp_GetCurrentThreadId
0x180055107  mov     r8, [rbx+110h]
0x18005510e  lea     rdx, byte_18008E049
0x180055115  mov     dword ptr [rbp+57h+SRWLock], eax
0x180055118  mov     rcx, rdi
0x18005511b  mov     eax, [r8+48h]
0x18005511f  add     r8, 8
0x180055123  mov     [rbp+57h+arg_8], eax
0x180055126  mov     eax, 1000000h
0x18005512b  mov     [rbp+57h+arg_10], rax
0x18005512f  lea     rax, [rbp+57h+SRWLock]
0x180055133  mov     [rsp+110h+var_E0], rax
0x180055138  lea     rax, [rbp+57h+arg_8]
0x18005513c  mov     [rsp+110h+var_E8], rax
0x180055141  lea     rax, [rbp+57h+arg_10]
0x180055145  mov     [rsp+110h+var_F0], rax
0x18005514a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005514f  mov     rcx, rbx
0x180055152  add     rsp, 100h
0x180055159  pop     rdi
0x18005515a  pop     rbx
0x18005515b  pop     rbp
0x18005515c  jmp     ?IgnoreCurrentThread@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
