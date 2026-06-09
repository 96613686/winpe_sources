# Windows::Telemetry::Service::Svc::StopActivity(void)

- ea: `0x180053160`
- end: `0x1800533e4`
- name: `?StopActivity@Svc@Service@Telemetry@Windows@@MEAAXXZ`
- size: `644`
- prototype: `void __fastcall(Windows::Telemetry::Service::Svc *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x1800013a4`
- `0x1800020d8`
- `0x180041ba0`
- `0x180041c1c`
- `0x180041cd8`
- `0x180053160`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800531ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005334c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800531ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005334c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053384`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053384`

## pseudocode

```c
void __fastcall Windows::Telemetry::Service::Svc::StopActivity(Windows::Telemetry::Service::Svc *this)
{
  __int64 v1; // rdi
  int v3; // eax
  __int64 v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  __int64 v6; // r9
  __int64 v7; // r8
  RTL_SRWLOCK *v8; // rcx
  __int64 v9; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  int v12; // r9d
  int v13; // [rsp+A0h] [rbp-19h] BYREF
  int v14; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v15; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v16; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v17; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v18; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v19; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v20; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v21; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v22; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v23; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v24[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  __int64 v26; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+130h] [rbp+77h] BYREF
  __int64 v28; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = v1 + 80, v3 == *(_DWORD *)(v4 + 8)) && v4 )
  {
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = *((_QWORD *)Windows::Telemetry::Base::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x400000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      v7 = *((_QWORD *)this + 34);
      v15 = *(_QWORD *)(v4 + 120);
      v16 = *(_QWORD *)(v4 + 112);
      LODWORD(SRWLock) = *(_DWORD *)(v4 + 104);
      v17 = *(_QWORD *)(v4 + 96);
      v18 = *(_QWORD *)(v4 + 88);
      LODWORD(v26) = *(_DWORD *)(v4 + 80);
      v19 = *(_QWORD *)(v4 + 72);
      LODWORD(v27) = *(_DWORD *)(v4 + 32);
      v20 = *(_QWORD *)(v4 + 24);
      LODWORD(v28) = *(_DWORD *)v4;
      v21 = *(_QWORD *)(v4 + 128);
      v13 = *(_DWORD *)(v4 + 64);
      v22 = *(_QWORD *)(v4 + 56);
      v14 = *(_DWORD *)(v4 + 8);
      v23 = 0x1000000;
      v24[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v6,
        (int)&unk_180081FB0,
        v7 + 8,
        (__int64)v24,
        (__int64)&v23,
        (__int64)&v14,
        (__int64)&v22,
        (__int64)&v13,
        (__int64)&v21,
        (__int64)&v28,
        (__int64)&v20,
        (__int64)&v27,
        (__int64)&v19,
        (__int64)&v26,
        (__int64)&v18,
        (__int64)&v17,
        (__int64)&SRWLock,
        (__int64)&v16,
        (__int64)&v15);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v8 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
    v9 = *((_QWORD *)Windows::Telemetry::Base::Instance() + 1);
    if ( *(_DWORD *)v9 > 5u
      && (*(_QWORD *)(v9 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v9 + 24) & 0x400000000000LL) == *(_QWORD *)(v9 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      LODWORD(v26) = *(_DWORD *)(v11 + 72);
      v27 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)&dword_180081F6C,
        v11 + 8,
        v12,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180053160  push    rbp
0x180053162  push    rbx
0x180053163  push    rdi
0x180053164  lea     rbp, [rsp-47h]
0x180053169  sub     rsp, 100h
0x180053170  mov     rdi, [rcx+110h]
0x180053177  mov     rbx, rcx
0x18005317a  mov     eax, [rdi+48h]
0x18005317d  test    eax, eax
0x18005317f  jns     loc_18005332D
0x180053185  add     rdi, 50h ; 'P'
0x180053189  cmp     eax, [rdi+8]
0x18005318c  jnz     loc_18005332D
0x180053192  test    rdi, rdi
0x180053195  jz      loc_18005332D
0x18005319b  lea     rdx, [rbp+57h+SRWLock]
0x18005319f  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800531a4  mov     rax, [rbx+110h]
0x1800531ab  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800531af  mov     dword ptr [rax], 2
0x1800531b5  test    rcx, rcx
0x1800531b8  jz      short loc_1800531C0
0x1800531ba  call    cs:__imp_ReleaseSRWLockExclusive
0x1800531c0  call    ?Instance@Base@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::Base::Instance(void)
0x1800531c5  mov     r9, [rax+8]
0x1800531c9  mov     eax, [r9]
0x1800531cc  cmp     eax, 5
0x1800531cf  jbe     loc_1800533D2
0x1800531d5  mov     rdx, [r9+18h]
0x1800531d9  mov     rcx, 400000000000h
0x1800531e3  mov     rax, [r9+10h]
0x1800531e7  test    rcx, rax
0x1800531ea  jz      loc_1800533D2
0x1800531f0  mov     rax, rdx
0x1800531f3  and     rax, rcx
0x1800531f6  cmp     rax, rdx
0x1800531f9  jnz     loc_1800533D2
0x1800531ff  mov     rax, [rdi+78h]
0x180053203  lea     rdx, unk_180081FB0; int
0x18005320a  mov     r8, [rbx+110h]
0x180053211  mov     rcx, r9; int
0x180053214  mov     [rbp+57h+var_68], rax
0x180053218  add     r8, 8; int
0x18005321c  mov     rax, [rdi+70h]
0x180053220  mov     [rbp+57h+var_60], rax
0x180053224  mov     eax, [rdi+68h]
0x180053227  mov     dword ptr [rbp+57h+SRWLock], eax
0x18005322a  mov     rax, [rdi+60h]
0x18005322e  mov     [rbp+57h+var_58], rax
0x180053232  mov     rax, [rdi+58h]
0x180053236  mov     [rbp+57h+var_50], rax
0x18005323a  mov     eax, [rdi+50h]
0x18005323d  mov     dword ptr [rbp+57h+arg_8], eax
0x180053240  mov     rax, [rdi+48h]
0x180053244  mov     [rbp+57h+var_48], rax
0x180053248  mov     eax, [rdi+20h]
0x18005324b  mov     dword ptr [rbp+57h+arg_10], eax
0x18005324e  mov     rax, [rdi+18h]
0x180053252  mov     [rbp+57h+var_40], rax
0x180053256  mov     eax, [rdi]
0x180053258  mov     dword ptr [rbp+57h+arg_18], eax
0x18005325b  mov     rax, [rdi+80h]
0x180053262  mov     [rbp+57h+var_38], rax
0x180053266  mov     eax, [rdi+40h]
0x180053269  mov     dword ptr [rbp+57h+var_70], eax
0x18005326c  mov     rax, [rdi+38h]
0x180053270  mov     [rbp+57h+var_30], rax
0x180053274  mov     eax, [rdi+8]
0x180053277  mov     dword ptr [rbp+57h+var_70+4], eax
0x18005327a  mov     eax, 1000000h
0x18005327f  mov     [rbp+57h+var_28], rax
0x180053283  mov     [rbp+57h+var_20], rax
0x180053287  lea     rax, [rbp+57h+var_68]
0x18005328b  mov     [rsp+110h+var_78], rax; __int64
0x180053293  lea     rax, [rbp+57h+var_60]
0x180053297  mov     [rsp+110h+var_80], rax; __int64
0x18005329f  lea     rax, [rbp+57h+SRWLock]
0x1800532a3  mov     [rsp+110h+var_88], rax; __int64
0x1800532ab  lea     rax, [rbp+57h+var_58]
0x1800532af  mov     [rsp+110h+var_90], rax; __int64
0x1800532b7  lea     rax, [rbp+57h+var_50]
0x1800532bb  mov     [rsp+110h+var_98], rax; __int64
0x1800532c0  lea     rax, [rbp+57h+arg_8]
0x1800532c4  mov     [rsp+110h+var_A0], rax; __int64
0x1800532c9  lea     rax, [rbp+57h+var_48]
0x1800532cd  mov     [rsp+110h+var_A8], rax; __int64
0x1800532d2  lea     rax, [rbp+57h+arg_10]
0x1800532d6  mov     [rsp+110h+var_B0], rax; __int64
0x1800532db  lea     rax, [rbp+57h+var_40]
0x1800532df  mov     [rsp+110h+var_B8], rax; __int64
0x1800532e4  lea     rax, [rbp+57h+arg_18]
0x1800532e8  mov     [rsp+110h+var_C0], rax; __int64
0x1800532ed  lea     rax, [rbp+57h+var_38]
0x1800532f1  mov     [rsp+110h+var_C8], rax; __int64
0x1800532f6  lea     rax, [rbp+57h+var_70]
0x1800532fa  mov     [rsp+110h+var_D0], rax; __int64
0x1800532ff  lea     rax, [rbp+57h+var_30]
0x180053303  mov     [rsp+110h+var_D8], rax; __int64
0x180053308  lea     rax, [rbp+57h+var_70+4]
0x18005330c  mov     [rsp+110h+var_E0], rax; __int64
0x180053311  lea     rax, [rbp+57h+var_28]
0x180053315  mov     [rsp+110h+var_E8], rax; __int64
0x18005331a  lea     rax, [rbp+57h+var_20]
0x18005331e  mov     [rsp+110h+var_F0], rax; __int64
0x180053323  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180053328  jmp     loc_1800533D2
0x18005332d  lea     rdx, [rbp+57h+SRWLock]
0x180053331  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180053336  mov     rax, [rbx+110h]
0x18005333d  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180053341  mov     dword ptr [rax], 2
0x180053347  test    rcx, rcx
0x18005334a  jz      short loc_180053352
0x18005334c  call    cs:__imp_ReleaseSRWLockExclusive
0x180053352  call    ?Instance@Base@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::Base::Instance(void)
0x180053357  mov     rdi, [rax+8]
0x18005335b  mov     eax, [rdi]
0x18005335d  cmp     eax, 5
0x180053360  jbe     short loc_1800533D2
0x180053362  mov     rdx, [rdi+18h]
0x180053366  mov     rcx, 400000000000h
0x180053370  mov     rax, [rdi+10h]
0x180053374  test    rcx, rax
0x180053377  jz      short loc_1800533D2
0x180053379  mov     rax, rdx
0x18005337c  and     rax, rcx
0x18005337f  cmp     rax, rdx
0x180053382  jnz     short loc_1800533D2
0x180053384  call    cs:__imp_GetCurrentThreadId
0x18005338a  mov     r8, [rbx+110h]
0x180053391  lea     rdx, dword_180081F6C
0x180053398  mov     dword ptr [rbp+57h+SRWLock], eax
0x18005339b  mov     rcx, rdi
0x18005339e  mov     eax, [r8+48h]
0x1800533a2  add     r8, 8
0x1800533a6  mov     dword ptr [rbp+57h+arg_8], eax
0x1800533a9  mov     eax, 1000000h
0x1800533ae  mov     [rbp+57h+arg_10], rax
0x1800533b2  lea     rax, [rbp+57h+SRWLock]
0x1800533b6  mov     [rsp+110h+var_E0], rax
0x1800533bb  lea     rax, [rbp+57h+arg_8]
0x1800533bf  mov     [rsp+110h+var_E8], rax
0x1800533c4  lea     rax, [rbp+57h+arg_10]
0x1800533c8  mov     [rsp+110h+var_F0], rax
0x1800533cd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800533d2  mov     rcx, rbx
0x1800533d5  add     rsp, 100h
0x1800533dc  pop     rdi
0x1800533dd  pop     rbx
0x1800533de  pop     rbp
0x1800533df  jmp     ?IgnoreCurrentThread@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
