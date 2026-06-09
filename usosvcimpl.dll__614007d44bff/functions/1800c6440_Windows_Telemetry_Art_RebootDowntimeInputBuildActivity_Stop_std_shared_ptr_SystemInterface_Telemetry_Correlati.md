# Windows::Telemetry::Art::RebootDowntimeInputBuildActivity::Stop(std::shared_ptr<SystemInterface::Telemetry::CorrelationVector>)

- ea: `0x1800c6440`
- end: `0x1800c6825`
- name: `?Stop@RebootDowntimeInputBuildActivity@Art@Telemetry@Windows@@QEAAXV?$shared_ptr@VCorrelationVector@Telemetry@SystemInterface@@@std@@@Z`
- size: `997`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1800c7aac`

## callees

- `0x180001350`
- `0x180003828`
- `0x18002ea8c`
- `0x180085644`
- `0x18008c454`
- `0x1800b781c`
- `0x1800c6440`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c64c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c6691`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c64c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c6691`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c66ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c66ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Telemetry::Art::RebootDowntimeInputBuildActivity::Stop(__int64 a1, _QWORD *a2)
{
  _DWORD **v4; // rbx
  __int64 v5; // rsi
  int v6; // eax
  __int64 v7; // rsi
  const struct _tlgProvider_t *v8; // rax
  int v9; // r15d
  _QWORD *v10; // rax
  __int64 v11; // r9
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // rsi
  __int64 v14; // rax
  const wchar_t *v15; // rbx
  __int64 v16; // r8
  __int64 v17; // rax
  int v18; // eax
  volatile signed __int32 *v19; // rbx
  PSRWLOCK SRWLock; // [rsp+B0h] [rbp-80h] BYREF
  int v21; // [rsp+B8h] [rbp-78h] BYREF
  int v22; // [rsp+BCh] [rbp-74h] BYREF
  int v23; // [rsp+C0h] [rbp-70h] BYREF
  int v24; // [rsp+C4h] [rbp-6Ch] BYREF
  __int64 v25; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v26; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v27; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v28; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v29; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v30; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v31; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v32; // [rsp+100h] [rbp-30h] BYREF
  __int64 v33; // [rsp+108h] [rbp-28h] BYREF
  __int64 v34; // [rsp+110h] [rbp-20h] BYREF
  __int64 v35; // [rsp+118h] [rbp-18h] BYREF
  __int64 v36; // [rsp+120h] [rbp-10h] BYREF
  __int64 v37; // [rsp+128h] [rbp-8h] BYREF
  _BYTE v38[32]; // [rsp+130h] [rbp+0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v39; // [rsp+150h] [rbp+20h] BYREF
  __int64 *v40; // [rsp+170h] [rbp+40h]
  __int64 v41; // [rsp+178h] [rbp+48h]
  int *v42; // [rsp+180h] [rbp+50h]
  __int64 v43; // [rsp+188h] [rbp+58h]
  PSRWLOCK *p_SRWLock; // [rsp+190h] [rbp+60h]
  __int64 v45; // [rsp+198h] [rbp+68h]
  const wchar_t *v46; // [rsp+1A0h] [rbp+70h]
  int v47; // [rsp+1A8h] [rbp+78h]
  int v48; // [rsp+1ACh] [rbp+7Ch]
  const char *v49; // [rsp+1B0h] [rbp+80h]
  __int64 v50; // [rsp+1B8h] [rbp+88h]

  v27 = (__int64)a2;
  v4 = (_DWORD **)(a1 + 272);
  v5 = *(_QWORD *)(a1 + 272);
  v6 = *(_DWORD *)(v5 + 72);
  if ( v6 < 0 && (v7 = v5 + 80, v6 == *(_DWORD *)(v7 + 8)) && v7 )
  {
    SRWLock = 0;
    wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &SRWLock);
    **v4 = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v8 = Windows::Telemetry::Base::Provider();
    v9 = (int)v8;
    if ( *(_DWORD *)v8 > 5u
      && (*((_QWORD *)v8 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v8 + 3) & 0x400000000000LL) == *((_QWORD *)v8 + 3) )
    {
      v28 = (__int64)"1507.2603.28012.0";
      v10 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a2 + 8LL))(*a2, v38);
      if ( v10[3] > 0xFu )
        v10 = (_QWORD *)*v10;
      v29 = (__int64)v10;
      v30 = *(_QWORD *)(v7 + 120);
      v31 = *(_QWORD *)(v7 + 112);
      v22 = *(_DWORD *)(v7 + 104);
      v32 = *(_QWORD *)(v7 + 96);
      v33 = *(_QWORD *)(v7 + 88);
      v23 = *(_DWORD *)(v7 + 80);
      v34 = *(_QWORD *)(v7 + 72);
      v24 = *(_DWORD *)(v7 + 32);
      v35 = *(_QWORD *)(v7 + 24);
      LODWORD(v25) = *(_DWORD *)v7;
      v36 = *(_QWORD *)(v7 + 128);
      v21 = *(_DWORD *)(v7 + 64);
      v27 = *(_QWORD *)(v7 + 56);
      LODWORD(SRWLock) = *(_DWORD *)(v7 + 8);
      v37 = 0x1000000;
      v26 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v9,
        (int)&byte_180132BD3,
        *(_DWORD *)v4 + 8,
        v11,
        (__int64)&v26,
        (__int64)&v37,
        (__int64)&SRWLock,
        (const wchar_t **)&v27,
        (__int64)&v21,
        (const wchar_t **)&v36,
        (__int64)&v25,
        (const OLECHAR **)&v35,
        (__int64)&v24,
        (const wchar_t **)&v34,
        (__int64)&v23,
        (const wchar_t **)&v33,
        (const OLECHAR **)&v32,
        (__int64)&v22,
        (const wchar_t **)&v31,
        (const OLECHAR **)&v30,
        (const wchar_t **)&v29,
        (const wchar_t **)&v28);
LABEL_25:
      std::string::~string((__int64)v38);
    }
  }
  else
  {
    SRWLock = 0;
    wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &SRWLock);
    **v4 = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v12 = Windows::Telemetry::Base::Provider();
    v13 = (__int64)v12;
    if ( *(_DWORD *)v12 > 5u
      && (*((_QWORD *)v12 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v12 + 3) & 0x400000000000LL) == *((_QWORD *)v12 + 3) )
    {
      v14 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a2 + 8LL))(*a2, v38);
      v15 = (const wchar_t *)v14;
      if ( *(_QWORD *)(v14 + 24) > 0xFu )
        v15 = *(const wchar_t **)v14;
      LODWORD(SRWLock) = GetCurrentThreadId();
      v16 = *(_QWORD *)(a1 + 272);
      v21 = *(_DWORD *)(v16 + 72);
      v26 = 0x1000000;
      v49 = "1507.2603.28012.0";
      v50 = 18;
      if ( v15 )
      {
        v17 = -1;
        do
          ++v17;
        while ( *((_BYTE *)v15 + v17) );
        v18 = v17 + 1;
      }
      else
      {
        v15 = &byte_1800F555A;
        v18 = 1;
      }
      v46 = v15;
      v47 = v18;
      v48 = 0;
      p_SRWLock = &SRWLock;
      v45 = 4;
      v42 = &v21;
      v43 = 4;
      v40 = &v26;
      v41 = 8;
      tlgWriteTransfer_EventWriteTransfer(v13, (unsigned __int8 *)&byte_180132B5B, (const GUID *)(v16 + 8), 0, 7u, &v39);
      goto LABEL_25;
    }
  }
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
  v19 = (volatile signed __int32 *)a2[1];
  if ( v19 && _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
    if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
  }
}

```

## disassembly

```asm
0x1800c6440  mov     [rsp-8+arg_10], rbx
0x1800c6445  push    rbp
0x1800c6446  push    rsi
0x1800c6447  push    rdi
0x1800c6448  push    r14
0x1800c644a  push    r15
0x1800c644c  lea     rbp, [rsp-0A0h]
0x1800c6454  sub     rsp, 1D0h
0x1800c645b  mov     rax, cs:__security_cookie
0x1800c6462  xor     rax, rsp
0x1800c6465  mov     [rbp+0C0h+var_30], rax
0x1800c646c  mov     r14, rdx
0x1800c646f  mov     rdi, rcx
0x1800c6472  mov     [rbp+0C0h+var_118], rdx
0x1800c6476  lea     rbx, [rcx+110h]
0x1800c647d  mov     rsi, [rbx]
0x1800c6480  mov     eax, [rsi+48h]
0x1800c6483  test    eax, eax
0x1800c6485  jns     loc_1800C666E
0x1800c648b  add     rsi, 50h ; 'P'
0x1800c648f  cmp     eax, [rsi+8]
0x1800c6492  jnz     loc_1800C666E
0x1800c6498  test    rsi, rsi
0x1800c649b  jz      loc_1800C666E
0x1800c64a1  mov     [rbp+0C0h+SRWLock], 0
0x1800c64a9  lea     rdx, [rbp+0C0h+SRWLock]
0x1800c64ad  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800c64b2  mov     rax, [rbx]
0x1800c64b5  mov     dword ptr [rax], 2
0x1800c64bb  mov     rcx, [rbp+0C0h+SRWLock]; SRWLock
0x1800c64bf  test    rcx, rcx
0x1800c64c2  jz      short loc_1800C64CA
0x1800c64c4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800c64ca  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1800c64cf  mov     r15, rax
0x1800c64d2  cmp     dword ptr [rax], 5
0x1800c64d5  jbe     loc_1800C67B6
0x1800c64db  mov     rdx, 400000000000h
0x1800c64e5  test    [rax+10h], rdx
0x1800c64e9  jz      loc_1800C67B6
0x1800c64ef  mov     rcx, [rax+18h]
0x1800c64f3  and     rcx, rdx
0x1800c64f6  cmp     rcx, [rax+18h]
0x1800c64fa  jnz     loc_1800C67B6
0x1800c6500  lea     rax, a15072603280120; "1507.2603.28012.0"
0x1800c6507  mov     [rbp+0C0h+var_110], rax
0x1800c650b  mov     rcx, [r14]
0x1800c650e  mov     rax, [rcx]
0x1800c6511  lea     rdx, [rbp+0C0h+var_C0]
0x1800c6515  mov     rax, [rax+8]
0x1800c6519  call    _guard_dispatch_icall
0x1800c651e  cmp     qword ptr [rax+18h], 0Fh
0x1800c6523  jbe     short loc_1800C6528
0x1800c6525  mov     rax, [rax]
0x1800c6528  mov     [rbp+0C0h+var_108], rax
0x1800c652c  mov     rax, [rsi+78h]
0x1800c6530  mov     [rbp+0C0h+var_100], rax
0x1800c6534  mov     rax, [rsi+70h]
0x1800c6538  mov     [rbp+0C0h+var_F8], rax
0x1800c653c  mov     eax, [rsi+68h]
0x1800c653f  mov     dword ptr [rbp+0C0h+var_138+4], eax
0x1800c6542  mov     rax, [rsi+60h]
0x1800c6546  mov     [rbp+0C0h+var_F0], rax
0x1800c654a  mov     rax, [rsi+58h]
0x1800c654e  mov     [rbp+0C0h+var_E8], rax
0x1800c6552  mov     eax, [rsi+50h]
0x1800c6555  mov     dword ptr [rbp+0C0h+var_130], eax
0x1800c6558  mov     rax, [rsi+48h]
0x1800c655c  mov     [rbp+0C0h+var_E0], rax
0x1800c6560  mov     eax, [rsi+20h]
0x1800c6563  mov     dword ptr [rbp+0C0h+var_130+4], eax
0x1800c6566  mov     rax, [rsi+18h]
0x1800c656a  mov     [rbp+0C0h+var_D8], rax
0x1800c656e  mov     eax, [rsi]
0x1800c6570  mov     dword ptr [rbp+0C0h+var_128], eax
0x1800c6573  mov     rax, [rsi+80h]
0x1800c657a  mov     [rbp+0C0h+var_D0], rax
0x1800c657e  mov     eax, [rsi+40h]
0x1800c6581  mov     dword ptr [rbp+0C0h+var_138], eax
0x1800c6584  mov     rax, [rsi+38h]
0x1800c6588  mov     [rbp+0C0h+var_118], rax
0x1800c658c  mov     eax, [rsi+8]
0x1800c658f  mov     dword ptr [rbp+0C0h+SRWLock], eax
0x1800c6592  mov     eax, 1000000h
0x1800c6597  mov     [rbp+0C0h+var_C8], rax
0x1800c659b  mov     [rbp+0C0h+var_120], rax
0x1800c659f  mov     r8, [rbx]
0x1800c65a2  add     r8, 8; int
0x1800c65a6  lea     rax, [rbp+0C0h+var_110]
0x1800c65aa  mov     [rsp+1F0h+var_148], rax; __int64
0x1800c65b2  lea     rax, [rbp+0C0h+var_108]
0x1800c65b6  mov     [rsp+1F0h+var_150], rax; __int64
0x1800c65be  lea     rax, [rbp+0C0h+var_100]
0x1800c65c2  mov     [rsp+1F0h+var_158], rax; __int64
0x1800c65ca  lea     rax, [rbp+0C0h+var_F8]
0x1800c65ce  mov     [rsp+1F0h+var_160], rax; __int64
0x1800c65d6  lea     rax, [rbp+0C0h+var_138+4]
0x1800c65da  mov     [rsp+1F0h+var_168], rax; __int64
0x1800c65e2  lea     rax, [rbp+0C0h+var_F0]
0x1800c65e6  mov     [rsp+1F0h+var_170], rax; __int64
0x1800c65ee  lea     rax, [rbp+0C0h+var_E8]
0x1800c65f2  mov     [rsp+1F0h+var_178], rax; __int64
0x1800c65f7  lea     rax, [rbp+0C0h+var_130]
0x1800c65fb  mov     [rsp+1F0h+var_180], rax; __int64
0x1800c6600  lea     rax, [rbp+0C0h+var_E0]
0x1800c6604  mov     [rsp+1F0h+var_188], rax; __int64
0x1800c6609  lea     rax, [rbp+0C0h+var_130+4]
0x1800c660d  mov     [rsp+1F0h+var_190], rax; __int64
0x1800c6612  lea     rax, [rbp+0C0h+var_D8]
0x1800c6616  mov     [rsp+1F0h+var_198], rax; __int64
0x1800c661b  lea     rax, [rbp+0C0h+var_128]
0x1800c661f  mov     [rsp+1F0h+var_1A0], rax; __int64
0x1800c6624  lea     rax, [rbp+0C0h+var_D0]
0x1800c6628  mov     [rsp+1F0h+var_1A8], rax; __int64
0x1800c662d  lea     rax, [rbp+0C0h+var_138]
0x1800c6631  mov     [rsp+1F0h+var_1B0], rax; __int64
0x1800c6636  lea     rax, [rbp+0C0h+var_118]
0x1800c663a  mov     [rsp+1F0h+var_1B8], rax; __int64
0x1800c663f  lea     rax, [rbp+0C0h+SRWLock]
0x1800c6643  mov     [rsp+1F0h+var_1C0], rax; __int64
0x1800c6648  lea     rax, [rbp+0C0h+var_C8]
0x1800c664c  mov     [rsp+1F0h+var_1C8], rax; __int64
0x1800c6651  lea     rax, [rbp+0C0h+var_120]
0x1800c6655  mov     qword ptr [rsp+1F0h+var_1D0], rax; __int64
0x1800c665a  lea     rdx, byte_180132BD3; int
0x1800c6661  mov     rcx, r15; int
0x1800c6664  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@4545645655@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800c6669  jmp     loc_1800C67AD
0x1800c666e  mov     [rbp+0C0h+SRWLock], 0
0x1800c6676  lea     rdx, [rbp+0C0h+SRWLock]
0x1800c667a  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800c667f  mov     rax, [rbx]
0x1800c6682  mov     dword ptr [rax], 2
0x1800c6688  mov     rcx, [rbp+0C0h+SRWLock]; SRWLock
0x1800c668c  test    rcx, rcx
0x1800c668f  jz      short loc_1800C6697
0x1800c6691  call    cs:__imp_ReleaseSRWLockExclusive
0x1800c6697  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1800c669c  mov     rsi, rax
0x1800c669f  cmp     dword ptr [rax], 5
0x1800c66a2  jbe     loc_1800C67B6
0x1800c66a8  mov     rdx, 400000000000h
0x1800c66b2  test    [rax+10h], rdx
0x1800c66b6  jz      loc_1800C67B6
0x1800c66bc  mov     rcx, [rax+18h]
0x1800c66c0  and     rcx, rdx
0x1800c66c3  cmp     rcx, [rax+18h]
0x1800c66c7  jnz     loc_1800C67B6
0x1800c66cd  mov     rcx, [r14]
0x1800c66d0  mov     rax, [rcx]
0x1800c66d3  lea     rdx, [rbp+0C0h+var_C0]
0x1800c66d7  mov     rax, [rax+8]
0x1800c66db  call    _guard_dispatch_icall
0x1800c66e0  mov     rbx, rax
0x1800c66e3  cmp     qword ptr [rax+18h], 0Fh
0x1800c66e8  jbe     short loc_1800C66ED
0x1800c66ea  mov     rbx, [rax]
0x1800c66ed  call    cs:__imp_GetCurrentThreadId
0x1800c66f3  mov     dword ptr [rbp+0C0h+SRWLock], eax
0x1800c66f6  mov     r8, [rdi+110h]
0x1800c66fd  mov     ecx, [r8+48h]
0x1800c6701  mov     dword ptr [rbp+0C0h+var_138], ecx
0x1800c6704  mov     eax, 1000000h
0x1800c6709  mov     [rbp+0C0h+var_120], rax
0x1800c670d  lea     rax, a15072603280120; "1507.2603.28012.0"
0x1800c6714  mov     [rbp+0C0h+var_40], rax
0x1800c671b  mov     [rbp+0C0h+var_38], 12h
0x1800c6726  test    rbx, rbx
0x1800c6729  jz      short loc_1800C673C
0x1800c672b  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c672f  inc     rax
0x1800c6732  cmp     byte ptr [rbx+rax], 0
0x1800c6736  jnz     short loc_1800C672F
0x1800c6738  inc     eax
0x1800c673a  jmp     short loc_1800C6748
0x1800c673c  lea     rbx, byte_1800F555A
0x1800c6743  mov     eax, 1
0x1800c6748  mov     [rbp+0C0h+var_50], rbx
0x1800c674c  mov     [rbp+0C0h+var_48], eax
0x1800c674f  mov     [rbp+0C0h+var_44], 0
0x1800c6756  lea     rax, [rbp+0C0h+SRWLock]
0x1800c675a  mov     [rbp+0C0h+var_60], rax
0x1800c675e  mov     [rbp+0C0h+var_58], 4
0x1800c6766  lea     rax, [rbp+0C0h+var_138]
0x1800c676a  mov     [rbp+0C0h+var_70], rax
0x1800c676e  mov     [rbp+0C0h+var_68], 4
0x1800c6776  lea     rax, [rbp+0C0h+var_120]
0x1800c677a  mov     [rbp+0C0h+var_80], rax
0x1800c677e  mov     [rbp+0C0h+var_78], 8
0x1800c6786  add     r8, 8; int
0x1800c678a  lea     rax, [rbp+0C0h+var_A0]
0x1800c678e  mov     [rsp+1F0h+var_1C8], rax; PEVENT_DATA_DESCRIPTOR
0x1800c6793  mov     [rsp+1F0h+var_1D0], 7; ULONG
0x1800c679b  xor     r9d, r9d; int
0x1800c679e  lea     rdx, byte_180132B5B; int
0x1800c67a5  mov     rcx, rsi; int
0x1800c67a8  call    _tlgWriteTransfer_EventWriteTransfer
0x1800c67ad  lea     rcx, [rbp+0C0h+var_C0]
0x1800c67b1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800c67b6  mov     rcx, rdi
0x1800c67b9  call    ?IgnoreCurrentThread@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x1800c67be  nop
0x1800c67bf  mov     rbx, [r14+8]
0x1800c67c3  test    rbx, rbx
0x1800c67c6  jz      short loc_1800C67FF
0x1800c67c8  or      eax, 0FFFFFFFFh
0x1800c67cb  lock xadd [rbx+8], eax
0x1800c67d0  cmp     eax, 1
0x1800c67d3  jnz     short loc_1800C67FF
0x1800c67d5  mov     rax, [rbx]
0x1800c67d8  mov     rcx, rbx
0x1800c67db  mov     rax, [rax]
0x1800c67de  call    _guard_dispatch_icall
0x1800c67e3  or      eax, 0FFFFFFFFh
0x1800c67e6  lock xadd [rbx+0Ch], eax
0x1800c67eb  cmp     eax, 1
0x1800c67ee  jnz     short loc_1800C67FF
0x1800c67f0  mov     rax, [rbx]
0x1800c67f3  mov     rcx, rbx
0x1800c67f6  mov     rax, [rax+8]
0x1800c67fa  call    _guard_dispatch_icall
0x1800c67ff  mov     rcx, [rbp+0C0h+var_30]
0x1800c6806  xor     rcx, rsp; StackCookie
0x1800c6809  call    __security_check_cookie
0x1800c680e  mov     rbx, [rsp+1F0h+arg_10]
0x1800c6816  add     rsp, 1D0h
0x1800c681d  pop     r15
0x1800c681f  pop     r14
0x1800c6821  pop     rdi
0x1800c6822  pop     rsi
0x1800c6823  pop     rbp
0x1800c6824  retn
```
