# TraceLog::Providers::Reliability::NamedCallContextActivity::StopActivity(void)

- ea: `0x1400182e0`
- end: `0x14001855a`
- name: `?StopActivity@NamedCallContextActivity@Reliability@Providers@TraceLog@@MEAAXXZ`
- size: `634`
- prototype: `void __fastcall(TraceLog::Providers::Reliability::NamedCallContextActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400012bc`
- `0x1400015d0`
- `0x140012bd4`
- `0x1400146cc`
- `0x1400182e0`
- `0x140018560`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x14001833a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400184d8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14001833a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400184d8`
- `KERNEL32!GetCurrentThreadId` at `0x1400184ed`
- `KERNEL32!GetCurrentThreadId` at `0x1400184ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall TraceLog::Providers::Reliability::NamedCallContextActivity::StopActivity(
        TraceLog::Providers::Reliability::NamedCallContextActivity *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // r9
  const struct _tlgProvider_t *v6; // rdi
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // [rsp+C0h] [rbp-80h] BYREF
  int v10; // [rsp+C4h] [rbp-7Ch] BYREF
  int v11; // [rsp+C8h] [rbp-78h] BYREF
  int v12; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v13; // [rsp+D0h] [rbp-70h] BYREF
  const WCHAR *v14; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v15; // [rsp+E0h] [rbp-60h] BYREF
  const WCHAR *v16; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v17; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v18; // [rsp+F8h] [rbp-48h] BYREF
  const WCHAR *v19; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v20; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v21; // [rsp+110h] [rbp-30h] BYREF
  __int64 v22; // [rsp+118h] [rbp-28h] BYREF
  __int64 v23[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v25; // [rsp+158h] [rbp+18h] BYREF
  __int64 v26; // [rsp+160h] [rbp+20h] BYREF
  int v27; // [rsp+168h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = TraceLog::Providers::Reliability::Provider();
    if ( *(_DWORD *)v5 > 4u )
    {
      v13 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      LODWORD(SRWLock) = v4[17];
      v25 = v4[4];
      v14 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v15 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      LODWORD(v26) = v4[26];
      v16 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v17 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v27 = v4[20];
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v9 = v4[8];
      v19 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v10 = *v4;
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v11 = v4[16];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v12 = v4[2];
      v22 = 0x1000000;
      v23[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v5,
        (__int64)byte_1400D4BF3,
        *((_QWORD *)this + 34) + 8LL,
        (__int64)v5,
        (__int64)v23,
        (__int64)&v22,
        (__int64)&v12,
        &v21,
        (__int64)&v11,
        &v20,
        (__int64)&v10,
        &v19,
        (__int64)&v9,
        &v18,
        (__int64)&v27,
        &v17,
        &v16,
        (__int64)&v26,
        &v15,
        &v14,
        (__int64)&v25,
        (__int64)&SRWLock,
        &v13);
    }
  }
  else
  {
    wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = TraceLog::Providers::Reliability::Provider();
    if ( *(_DWORD *)v6 > 4u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v25 = *(_DWORD *)(v7 + 72);
      v26 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v6,
        (__int64)byte_1400D4941,
        v7 + 8,
        v8,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((TraceLog::Providers::Reliability::NamedCallContextActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x1400182e0  push    rbp
0x1400182e2  push    rbx
0x1400182e3  push    rdi
0x1400182e4  lea     rbp, [rsp+10h]
0x1400182e9  sub     rsp, 130h
0x1400182f0  mov     rbx, rcx
0x1400182f3  mov     rdi, [rcx+110h]
0x1400182fa  mov     eax, [rdi+48h]
0x1400182fd  test    eax, eax
0x1400182ff  jns     loc_1400184B9
0x140018305  add     rdi, 50h ; 'P'
0x140018309  cmp     eax, [rdi+8]
0x14001830c  jnz     loc_1400184B9
0x140018312  test    rdi, rdi
0x140018315  jz      loc_1400184B9
0x14001831b  lea     rdx, [rbp+SRWLock]
0x14001831f  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140018324  mov     rax, [rbx+110h]
0x14001832b  mov     dword ptr [rax], 2
0x140018331  mov     rcx, [rbp+SRWLock]; SRWLock
0x140018335  test    rcx, rcx
0x140018338  jz      short loc_140018340
0x14001833a  call    cs:__imp_ReleaseSRWLockExclusive
0x140018340  call    ?Provider@Reliability@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ; TraceLog::Providers::Reliability::Provider(void)
0x140018345  mov     r9, rax
0x140018348  mov     ecx, [rax]
0x14001834a  cmp     ecx, 4
0x14001834d  jbe     loc_14001853C
0x140018353  mov     rcx, [rdi+30h]
0x140018357  mov     [rbp+var_70], rcx
0x14001835b  mov     ecx, [rdi+44h]
0x14001835e  mov     dword ptr [rbp+SRWLock], ecx
0x140018361  mov     ecx, [rdi+10h]
0x140018364  mov     [rbp+arg_8], ecx
0x140018367  mov     rcx, [rdi+78h]
0x14001836b  mov     [rbp+var_68], rcx
0x14001836f  mov     rax, [rdi+70h]
0x140018373  mov     [rbp+var_60], rax
0x140018377  mov     eax, [rdi+68h]
0x14001837a  mov     dword ptr [rbp+arg_10], eax
0x14001837d  mov     rax, [rdi+60h]
0x140018381  mov     [rbp+var_58], rax
0x140018385  mov     rax, [rdi+58h]
0x140018389  mov     [rbp+var_50], rax
0x14001838d  mov     eax, [rdi+50h]
0x140018390  mov     [rbp+arg_18], eax
0x140018393  mov     rax, [rdi+48h]
0x140018397  mov     [rbp+var_48], rax
0x14001839b  mov     eax, [rdi+20h]
0x14001839e  mov     [rbp+var_80], eax
0x1400183a1  mov     rax, [rdi+18h]
0x1400183a5  mov     [rbp+var_40], rax
0x1400183a9  mov     eax, [rdi]
0x1400183ab  mov     [rbp+var_7C], eax
0x1400183ae  mov     rax, [rdi+80h]
0x1400183b5  mov     [rbp+var_38], rax
0x1400183b9  mov     eax, [rdi+40h]
0x1400183bc  mov     [rbp+var_78], eax
0x1400183bf  mov     rax, [rdi+38h]
0x1400183c3  mov     [rbp+var_30], rax
0x1400183c7  mov     eax, [rdi+8]
0x1400183ca  mov     [rbp+var_74], eax
0x1400183cd  mov     eax, 1000000h
0x1400183d2  mov     [rbp+var_28], rax
0x1400183d6  mov     [rbp+var_20], rax
0x1400183da  mov     r8, [rbx+110h]
0x1400183e1  add     r8, 8
0x1400183e5  lea     rax, [rbp+var_70]
0x1400183e9  mov     [rsp+140h+var_90], rax
0x1400183f1  lea     rax, [rbp+SRWLock]
0x1400183f5  mov     [rsp+140h+var_98], rax
0x1400183fd  lea     rax, [rbp+arg_8]
0x140018401  mov     [rsp+140h+var_A0], rax
0x140018409  lea     rax, [rbp+var_68]
0x14001840d  mov     [rsp+140h+var_A8], rax
0x140018415  lea     rax, [rbp+var_60]
0x140018419  mov     [rsp+140h+var_B0], rax
0x140018421  lea     rax, [rbp+arg_10]
0x140018425  mov     [rsp+140h+var_B8], rax
0x14001842d  lea     rax, [rbp+var_58]
0x140018431  mov     [rsp+140h+var_C0], rax
0x140018439  lea     rax, [rbp+var_50]
0x14001843d  mov     [rsp+140h+var_C8], rax
0x140018442  lea     rax, [rbp+arg_18]
0x140018446  mov     [rsp+140h+var_D0], rax
0x14001844b  lea     rax, [rbp+var_48]
0x14001844f  mov     [rsp+140h+var_D8], rax
0x140018454  lea     rax, [rbp+var_80]
0x140018458  mov     [rsp+140h+var_E0], rax
0x14001845d  lea     rax, [rbp+var_40]
0x140018461  mov     [rsp+140h+var_E8], rax
0x140018466  lea     rax, [rbp+var_7C]
0x14001846a  mov     [rsp+140h+var_F0], rax
0x14001846f  lea     rax, [rbp+var_38]
0x140018473  mov     [rsp+140h+var_F8], rax
0x140018478  lea     rax, [rbp+var_78]
0x14001847c  mov     [rsp+140h+var_100], rax
0x140018481  lea     rax, [rbp+var_30]
0x140018485  mov     [rsp+140h+var_108], rax
0x14001848a  lea     rax, [rbp+var_74]
0x14001848e  mov     [rsp+140h+var_110], rax
0x140018493  lea     rax, [rbp+var_28]
0x140018497  mov     [rsp+140h+var_118], rax
0x14001849c  lea     rax, [rbp+var_20]
0x1400184a0  mov     [rsp+140h+var_120], rax
0x1400184a5  lea     rdx, byte_1400D4BF3
0x1400184ac  mov     rcx, r9
0x1400184af  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400184b4  jmp     loc_14001853C
0x1400184b9  lea     rdx, [rbp+SRWLock]
0x1400184bd  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400184c2  mov     rax, [rbx+110h]
0x1400184c9  mov     dword ptr [rax], 2
0x1400184cf  mov     rcx, [rbp+SRWLock]; SRWLock
0x1400184d3  test    rcx, rcx
0x1400184d6  jz      short loc_1400184DE
0x1400184d8  call    cs:__imp_ReleaseSRWLockExclusive
0x1400184de  call    ?Provider@Reliability@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ; TraceLog::Providers::Reliability::Provider(void)
0x1400184e3  mov     rdi, rax
0x1400184e6  mov     ecx, [rax]
0x1400184e8  cmp     ecx, 4
0x1400184eb  jbe     short loc_14001853C
0x1400184ed  call    cs:__imp_GetCurrentThreadId
0x1400184f3  mov     dword ptr [rbp+SRWLock], eax
0x1400184f6  mov     r8, [rbx+110h]
0x1400184fd  mov     ecx, [r8+48h]
0x140018501  mov     [rbp+arg_8], ecx
0x140018504  mov     eax, 1000000h
0x140018509  mov     [rbp+arg_10], rax
0x14001850d  add     r8, 8
0x140018511  lea     rax, [rbp+SRWLock]
0x140018515  mov     [rsp+140h+var_110], rax
0x14001851a  lea     rax, [rbp+arg_8]
0x14001851e  mov     [rsp+140h+var_118], rax
0x140018523  lea     rax, [rbp+arg_10]
0x140018527  mov     [rsp+140h+var_120], rax
0x14001852c  lea     rdx, byte_1400D4941
0x140018533  mov     rcx, rdi
0x140018536  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14001853b  nop
0x14001853c  lea     rcx, [rbx+120h]; this
0x140018543  cmp     dword ptr [rcx+18h], 0
0x140018547  jz      short loc_14001854F
0x140018549  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14001854e  nop
0x14001854f  add     rsp, 130h
0x140018556  pop     rdi
0x140018557  pop     rbx
0x140018558  pop     rbp
0x140018559  retn
```
