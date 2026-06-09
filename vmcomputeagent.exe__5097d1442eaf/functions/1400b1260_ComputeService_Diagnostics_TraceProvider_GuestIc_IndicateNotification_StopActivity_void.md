# ComputeService::Diagnostics::TraceProvider::GuestIc_IndicateNotification::StopActivity(void)

- ea: `0x1400b1260`
- end: `0x1400b1543`
- name: `?StopActivity@GuestIc_IndicateNotification@TraceProvider@Diagnostics@ComputeService@@MEAAXXZ`
- size: `739`
- prototype: `void __fastcall(ComputeService::Diagnostics::TraceProvider::GuestIc_IndicateNotification *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400017a8`
- `0x140001abc`
- `0x14000aeec`
- `0x140031be8`
- `0x14003407c`
- `0x1400b1260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400b12c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400b1497`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400b12c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400b1497`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400b14ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400b14ca`

## pseudocode

```c
void __fastcall ComputeService::Diagnostics::TraceProvider::GuestIc_IndicateNotification::StopActivity(
        ComputeService::Diagnostics::TraceProvider::GuestIc_IndicateNotification *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // r9
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
    if ( *(_DWORD *)v5 > 4u
      && (*(_QWORD *)(v5 + 16) & 0x4000LL) != 0
      && (*(_QWORD *)(v5 + 24) & 0x4000LL) == *(_QWORD *)(v5 + 24) )
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
        (int)&byte_14013A7FD,
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
    if ( *(_DWORD *)v6 > 4u
      && (*(_QWORD *)(v6 + 16) & 0x4000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x4000LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v9 = *(_DWORD *)(v7 + 72);
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)&dword_14013A954,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeService::Diagnostics::TraceProvider::GuestIc_IndicateNotification *)((char *)this + 288));
}

```

## disassembly

```asm
0x1400b1260  mov     [rsp-8+arg_8], rbx
0x1400b1265  mov     [rsp-8+arg_10], rdi
0x1400b126a  push    rbp
0x1400b126b  mov     rbp, rsp
0x1400b126e  sub     rsp, 140h
0x1400b1275  mov     rbx, rcx
0x1400b1278  mov     rdi, [rcx+110h]
0x1400b127f  mov     eax, [rdi+48h]
0x1400b1282  test    eax, eax
0x1400b1284  jns     loc_1400B1470
0x1400b128a  add     rdi, 50h ; 'P'
0x1400b128e  cmp     eax, [rdi+8]
0x1400b1291  jnz     loc_1400B1470
0x1400b1297  test    rdi, rdi
0x1400b129a  jz      loc_1400B1470
0x1400b12a0  mov     [rbp+SRWLock], 0
0x1400b12a8  lea     rdx, [rbp+SRWLock]
0x1400b12ac  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400b12b1  mov     rax, [rbx+110h]
0x1400b12b8  mov     dword ptr [rax], 2
0x1400b12be  mov     rcx, [rbp+SRWLock]; SRWLock
0x1400b12c2  test    rcx, rcx
0x1400b12c5  jz      short loc_1400B12CD
0x1400b12c7  call    cs:__imp_ReleaseSRWLockExclusive
0x1400b12cd  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x1400b12d2  mov     r9, [rax+8]
0x1400b12d6  mov     eax, [r9]
0x1400b12d9  cmp     eax, 4
0x1400b12dc  jbe     loc_1400B151B
0x1400b12e2  mov     rdx, [r9+18h]
0x1400b12e6  mov     rax, [r9+10h]
0x1400b12ea  mov     ecx, 4000h
0x1400b12ef  test    rcx, rax
0x1400b12f2  jz      loc_1400B151B
0x1400b12f8  mov     rax, rdx
0x1400b12fb  and     rax, rcx
0x1400b12fe  cmp     rax, rdx
0x1400b1301  jnz     loc_1400B151B
0x1400b1307  mov     rax, [rdi+30h]
0x1400b130b  mov     [rbp+var_50], rax
0x1400b130f  mov     eax, [rdi+44h]
0x1400b1312  mov     dword ptr [rbp+var_78+4], eax
0x1400b1315  mov     eax, [rdi+10h]
0x1400b1318  mov     dword ptr [rbp+var_70], eax
0x1400b131b  mov     rax, [rdi+78h]
0x1400b131f  mov     [rbp+var_48], rax
0x1400b1323  mov     rax, [rdi+70h]
0x1400b1327  mov     [rbp+var_40], rax
0x1400b132b  mov     eax, [rdi+68h]
0x1400b132e  mov     dword ptr [rbp+var_70+4], eax
0x1400b1331  mov     rax, [rdi+60h]
0x1400b1335  mov     [rbp+var_38], rax
0x1400b1339  mov     rax, [rdi+58h]
0x1400b133d  mov     [rbp+var_30], rax
0x1400b1341  mov     eax, [rdi+50h]
0x1400b1344  mov     dword ptr [rbp+var_68], eax
0x1400b1347  mov     rax, [rdi+48h]
0x1400b134b  mov     [rbp+var_28], rax
0x1400b134f  mov     eax, [rdi+20h]
0x1400b1352  mov     dword ptr [rbp+var_68+4], eax
0x1400b1355  mov     rax, [rdi+18h]
0x1400b1359  mov     [rbp+var_20], rax
0x1400b135d  mov     eax, [rdi]
0x1400b135f  mov     [rbp+var_60], eax
0x1400b1362  mov     rax, [rdi+80h]
0x1400b1369  mov     [rbp+var_18], rax
0x1400b136d  mov     eax, [rdi+40h]
0x1400b1370  mov     dword ptr [rbp+var_78], eax
0x1400b1373  mov     rax, [rdi+38h]
0x1400b1377  mov     [rbp+var_10], rax
0x1400b137b  mov     eax, [rdi+8]
0x1400b137e  mov     dword ptr [rbp+SRWLock], eax
0x1400b1381  mov     [rbp+var_8], 1000000h
0x1400b1389  mov     [rbp+var_58], 0
0x1400b1391  mov     r8, [rbx+110h]
0x1400b1398  add     r8, 8; int
0x1400b139c  lea     rax, [rbp+var_50]
0x1400b13a0  mov     [rsp+140h+var_90], rax; __int64
0x1400b13a8  lea     rax, [rbp+var_78+4]
0x1400b13ac  mov     [rsp+140h+var_98], rax; __int64
0x1400b13b4  lea     rax, [rbp+var_70]
0x1400b13b8  mov     [rsp+140h+var_A0], rax; __int64
0x1400b13c0  lea     rax, [rbp+var_48]
0x1400b13c4  mov     [rsp+140h+var_A8], rax; __int64
0x1400b13cc  lea     rax, [rbp+var_40]
0x1400b13d0  mov     [rsp+140h+var_B0], rax; __int64
0x1400b13d8  lea     rax, [rbp+var_70+4]
0x1400b13dc  mov     [rsp+140h+var_B8], rax; __int64
0x1400b13e4  lea     rax, [rbp+var_38]
0x1400b13e8  mov     [rsp+140h+var_C0], rax; __int64
0x1400b13f0  lea     rax, [rbp+var_30]
0x1400b13f4  mov     [rsp+140h+var_C8], rax; __int64
0x1400b13f9  lea     rax, [rbp+var_68]
0x1400b13fd  mov     [rsp+140h+var_D0], rax; __int64
0x1400b1402  lea     rax, [rbp+var_28]
0x1400b1406  mov     [rsp+140h+var_D8], rax; __int64
0x1400b140b  lea     rax, [rbp+var_68+4]
0x1400b140f  mov     [rsp+140h+var_E0], rax; __int64
0x1400b1414  lea     rax, [rbp+var_20]
0x1400b1418  mov     [rsp+140h+var_E8], rax; __int64
0x1400b141d  lea     rax, [rbp+var_60]
0x1400b1421  mov     [rsp+140h+var_F0], rax; __int64
0x1400b1426  lea     rax, [rbp+var_18]
0x1400b142a  mov     [rsp+140h+var_F8], rax; __int64
0x1400b142f  lea     rax, [rbp+var_78]
0x1400b1433  mov     [rsp+140h+var_100], rax; __int64
0x1400b1438  lea     rax, [rbp+var_10]
0x1400b143c  mov     [rsp+140h+var_108], rax; __int64
0x1400b1441  lea     rax, [rbp+SRWLock]
0x1400b1445  mov     [rsp+140h+var_110], rax; __int64
0x1400b144a  lea     rax, [rbp+var_8]
0x1400b144e  mov     [rsp+140h+var_118], rax; __int64
0x1400b1453  lea     rax, [rbp+var_58]
0x1400b1457  mov     [rsp+140h+var_120], rax; __int64
0x1400b145c  lea     rdx, byte_14013A7FD; int
0x1400b1463  mov     rcx, r9; int
0x1400b1466  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400b146b  jmp     loc_1400B151B
0x1400b1470  mov     [rbp+SRWLock], 0
0x1400b1478  lea     rdx, [rbp+SRWLock]
0x1400b147c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400b1481  mov     rax, [rbx+110h]
0x1400b1488  mov     dword ptr [rax], 2
0x1400b148e  mov     rcx, [rbp+SRWLock]; SRWLock
0x1400b1492  test    rcx, rcx
0x1400b1495  jz      short loc_1400B149D
0x1400b1497  call    cs:__imp_ReleaseSRWLockExclusive
0x1400b149d  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x1400b14a2  mov     rdi, [rax+8]
0x1400b14a6  mov     eax, [rdi]
0x1400b14a8  cmp     eax, 4
0x1400b14ab  jbe     short loc_1400B151B
0x1400b14ad  mov     rdx, [rdi+18h]
0x1400b14b1  mov     rax, [rdi+10h]
0x1400b14b5  mov     ecx, 4000h
0x1400b14ba  test    rcx, rax
0x1400b14bd  jz      short loc_1400B151B
0x1400b14bf  mov     rax, rdx
0x1400b14c2  and     rax, rcx
0x1400b14c5  cmp     rax, rdx
0x1400b14c8  jnz     short loc_1400B151B
0x1400b14ca  call    cs:__imp_GetCurrentThreadId
0x1400b14d0  mov     dword ptr [rbp+SRWLock], eax
0x1400b14d3  mov     r8, [rbx+110h]
0x1400b14da  mov     eax, [r8+48h]
0x1400b14de  mov     dword ptr [rbp+var_78], eax
0x1400b14e1  mov     [rbp+var_58], 0
0x1400b14e9  add     r8, 8
0x1400b14ed  lea     rax, [rbp+SRWLock]
0x1400b14f1  mov     [rsp+140h+var_110], rax
0x1400b14f6  lea     rax, [rbp+var_78]
0x1400b14fa  mov     [rsp+140h+var_118], rax
0x1400b14ff  lea     rax, [rbp+var_58]
0x1400b1503  mov     [rsp+140h+var_120], rax
0x1400b1508  xor     r9d, r9d
0x1400b150b  lea     rdx, dword_14013A954
0x1400b1512  mov     rcx, rdi
0x1400b1515  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400b151a  nop
0x1400b151b  lea     rcx, [rbx+120h]; this
0x1400b1522  cmp     dword ptr [rcx+18h], 0
0x1400b1526  jz      short loc_1400B152E
0x1400b1528  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1400b152d  nop
0x1400b152e  lea     r11, [rsp+140h+var_s0]
0x1400b1536  mov     rbx, [r11+18h]
0x1400b153a  mov     rdi, [r11+20h]
0x1400b153e  mov     rsp, r11
0x1400b1541  pop     rbp
0x1400b1542  retn
```
