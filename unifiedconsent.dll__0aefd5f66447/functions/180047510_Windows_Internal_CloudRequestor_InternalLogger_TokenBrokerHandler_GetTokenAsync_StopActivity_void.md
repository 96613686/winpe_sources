# Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_GetTokenAsync::StopActivity(void)

- ea: `0x180047510`
- end: `0x1800477b1`
- name: `?StopActivity@TokenBrokerHandler_GetTokenAsync@InternalLogger@CloudRequestor@Internal@Windows@@MEAAXXZ`
- size: `673`
- prototype: `void __fastcall(Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_GetTokenAsync *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800013a4`
- `0x180001a6c`
- `0x18004453c`
- `0x18004460c`
- `0x180045c98`
- `0x180047510`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004756a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004770a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004756a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004770a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047751`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047751`

## pseudocode

```c
void __fastcall Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_GetTokenAsync::StopActivity(
        Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_GetTokenAsync *this)
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
        (unsigned int)byte_18008D8F9,
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
        (unsigned int)&unk_18008D898,
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
0x180047510  push    rbp
0x180047512  push    rbx
0x180047513  push    rdi
0x180047514  lea     rbp, [rsp-47h]
0x180047519  sub     rsp, 100h
0x180047520  mov     rdi, [rcx+110h]
0x180047527  mov     rbx, rcx
0x18004752a  mov     eax, [rdi+48h]
0x18004752d  test    eax, eax
0x18004752f  jns     loc_1800476EB
0x180047535  add     rdi, 50h ; 'P'
0x180047539  cmp     eax, [rdi+8]
0x18004753c  jnz     loc_1800476EB
0x180047542  test    rdi, rdi
0x180047545  jz      loc_1800476EB
0x18004754b  lea     rdx, [rbp+57h+SRWLock]
0x18004754f  call    ?LockExclusive@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180047554  mov     rax, [rbx+110h]
0x18004755b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18004755f  mov     dword ptr [rax], 2
0x180047565  test    rcx, rcx
0x180047568  jz      short loc_180047570
0x18004756a  call    cs:__imp_ReleaseSRWLockExclusive
0x180047570  call    ?Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV1234@XZ; Windows::Internal::CloudRequestor::InternalLogger::Instance(void)
0x180047575  test    rax, rax
0x180047578  mov     edx, 8
0x18004757d  lea     rcx, [rax+10h]
0x180047581  cmovz   rcx, rdx
0x180047585  mov     r9, [rcx]
0x180047588  mov     eax, [r9]
0x18004758b  cmp     eax, 5
0x18004758e  jbe     loc_18004779F
0x180047594  mov     r8, [r9+18h]
0x180047598  mov     rcx, 200000000000h
0x1800475a2  mov     rax, [r9+10h]
0x1800475a6  test    rcx, rax
0x1800475a9  jz      loc_18004779F
0x1800475af  mov     rax, r8
0x1800475b2  and     rax, rcx
0x1800475b5  cmp     rax, r8
0x1800475b8  jnz     loc_18004779F
0x1800475be  mov     rax, [rdi+78h]
0x1800475c2  mov     rcx, r9
0x1800475c5  mov     r8, [rbx+110h]
0x1800475cc  mov     [rbp+57h+var_68], rax
0x1800475d0  add     r8, rdx
0x1800475d3  mov     rax, [rdi+70h]
0x1800475d7  lea     rdx, byte_18008D8F9
0x1800475de  mov     [rbp+57h+var_60], rax
0x1800475e2  mov     eax, [rdi+68h]
0x1800475e5  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800475e8  mov     rax, [rdi+60h]
0x1800475ec  mov     [rbp+57h+var_58], rax
0x1800475f0  mov     rax, [rdi+58h]
0x1800475f4  mov     [rbp+57h+var_50], rax
0x1800475f8  mov     eax, [rdi+50h]
0x1800475fb  mov     [rbp+57h+arg_8], eax
0x1800475fe  mov     rax, [rdi+48h]
0x180047602  mov     [rbp+57h+var_48], rax
0x180047606  mov     eax, [rdi+20h]
0x180047609  mov     dword ptr [rbp+57h+arg_10], eax
0x18004760c  mov     rax, [rdi+18h]
0x180047610  mov     [rbp+57h+var_40], rax
0x180047614  mov     eax, [rdi]
0x180047616  mov     [rbp+57h+arg_18], eax
0x180047619  mov     rax, [rdi+80h]
0x180047620  mov     [rbp+57h+var_38], rax
0x180047624  mov     eax, [rdi+40h]
0x180047627  mov     [rbp+57h+var_70], eax
0x18004762a  mov     rax, [rdi+38h]
0x18004762e  mov     [rbp+57h+var_30], rax
0x180047632  mov     eax, [rdi+8]
0x180047635  mov     [rbp+57h+var_6C], eax
0x180047638  mov     eax, 1000000h
0x18004763d  mov     [rbp+57h+var_28], rax
0x180047641  mov     [rbp+57h+var_20], rax
0x180047645  lea     rax, [rbp+57h+var_68]
0x180047649  mov     [rsp+110h+var_78], rax
0x180047651  lea     rax, [rbp+57h+var_60]
0x180047655  mov     [rsp+110h+var_80], rax
0x18004765d  lea     rax, [rbp+57h+SRWLock]
0x180047661  mov     [rsp+110h+var_88], rax
0x180047669  lea     rax, [rbp+57h+var_58]
0x18004766d  mov     [rsp+110h+var_90], rax
0x180047675  lea     rax, [rbp+57h+var_50]
0x180047679  mov     [rsp+110h+var_98], rax
0x18004767e  lea     rax, [rbp+57h+arg_8]
0x180047682  mov     [rsp+110h+var_A0], rax
0x180047687  lea     rax, [rbp+57h+var_48]
0x18004768b  mov     [rsp+110h+var_A8], rax
0x180047690  lea     rax, [rbp+57h+arg_10]
0x180047694  mov     [rsp+110h+var_B0], rax
0x180047699  lea     rax, [rbp+57h+var_40]
0x18004769d  mov     [rsp+110h+var_B8], rax
0x1800476a2  lea     rax, [rbp+57h+arg_18]
0x1800476a6  mov     [rsp+110h+var_C0], rax
0x1800476ab  lea     rax, [rbp+57h+var_38]
0x1800476af  mov     [rsp+110h+var_C8], rax
0x1800476b4  lea     rax, [rbp+57h+var_70]
0x1800476b8  mov     [rsp+110h+var_D0], rax
0x1800476bd  lea     rax, [rbp+57h+var_30]
0x1800476c1  mov     [rsp+110h+var_D8], rax
0x1800476c6  lea     rax, [rbp+57h+var_6C]
0x1800476ca  mov     [rsp+110h+var_E0], rax
0x1800476cf  lea     rax, [rbp+57h+var_28]
0x1800476d3  mov     [rsp+110h+var_E8], rax
0x1800476d8  lea     rax, [rbp+57h+var_20]
0x1800476dc  mov     [rsp+110h+var_F0], rax
0x1800476e1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800476e6  jmp     loc_18004779F
0x1800476eb  lea     rdx, [rbp+57h+SRWLock]
0x1800476ef  call    ?LockExclusive@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800476f4  mov     rax, [rbx+110h]
0x1800476fb  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800476ff  mov     dword ptr [rax], 2
0x180047705  test    rcx, rcx
0x180047708  jz      short loc_180047710
0x18004770a  call    cs:__imp_ReleaseSRWLockExclusive
0x180047710  call    ?Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV1234@XZ; Windows::Internal::CloudRequestor::InternalLogger::Instance(void)
0x180047715  test    rax, rax
0x180047718  mov     edx, 8
0x18004771d  lea     rcx, [rax+10h]
0x180047721  cmovz   rcx, rdx
0x180047725  mov     rdi, [rcx]
0x180047728  mov     eax, [rdi]
0x18004772a  cmp     eax, 5
0x18004772d  jbe     short loc_18004779F
0x18004772f  mov     rdx, [rdi+18h]
0x180047733  mov     rcx, 200000000000h
0x18004773d  mov     rax, [rdi+10h]
0x180047741  test    rcx, rax
0x180047744  jz      short loc_18004779F
0x180047746  mov     rax, rdx
0x180047749  and     rax, rcx
0x18004774c  cmp     rax, rdx
0x18004774f  jnz     short loc_18004779F
0x180047751  call    cs:__imp_GetCurrentThreadId
0x180047757  mov     r8, [rbx+110h]
0x18004775e  lea     rdx, unk_18008D898
0x180047765  mov     dword ptr [rbp+57h+SRWLock], eax
0x180047768  mov     rcx, rdi
0x18004776b  mov     eax, [r8+48h]
0x18004776f  add     r8, 8
0x180047773  mov     [rbp+57h+arg_8], eax
0x180047776  mov     eax, 1000000h
0x18004777b  mov     [rbp+57h+arg_10], rax
0x18004777f  lea     rax, [rbp+57h+SRWLock]
0x180047783  mov     [rsp+110h+var_E0], rax
0x180047788  lea     rax, [rbp+57h+arg_8]
0x18004778c  mov     [rsp+110h+var_E8], rax
0x180047791  lea     rax, [rbp+57h+arg_10]
0x180047795  mov     [rsp+110h+var_F0], rax
0x18004779a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004779f  mov     rcx, rbx
0x1800477a2  add     rsp, 100h
0x1800477a9  pop     rdi
0x1800477aa  pop     rbx
0x1800477ab  pop     rbp
0x1800477ac  jmp     ?IgnoreCurrentThread@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
