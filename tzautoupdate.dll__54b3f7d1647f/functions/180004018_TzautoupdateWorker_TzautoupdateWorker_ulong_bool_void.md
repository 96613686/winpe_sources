# TzautoupdateWorker::TzautoupdateWorker(ulong,bool,void *)

- ea: `0x180004018`
- end: `0x180004172`
- name: `??0TzautoupdateWorker@@QEAA@K_NPEAX@Z`
- size: `346`
- prototype: `TzautoupdateWorker *__fastcall(TzautoupdateWorker *__hidden this, unsigned int, bool, void *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, installer_update`

## callers

- `0x1800094c0`
- `0x1800140a0`

## callees

- `0x180004018`
- `0x18000a108`
- `0x18000a27c`
- `0x18000a3f0`
- `0x18000a564`
- `0x18000a6d8`
- `0x18000ad08`
- `0x180010784`
- `0x180014c60`
- `0x1800175d0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800040af`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800040af`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180004039`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180004039`

## pseudocode

```c
TzautoupdateWorker *__fastcall TzautoupdateWorker::TzautoupdateWorker(
        TzautoupdateWorker *this,
        unsigned int a2,
        bool a3,
        void *a4)
{
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int128 v11; // [rsp+30h] [rbp-48h] BYREF
  __int64 v12; // [rsp+40h] [rbp-38h]

  InitializeSRWLock((PSRWLOCK)this);
  *((_QWORD *)this + 4) = 0;
  *((_BYTE *)this + 64) = 0;
  *((_BYTE *)this + 73) = 0;
  *((_BYTE *)this + 75) = 0;
  *((_BYTE *)this + 77) = 0;
  *((_BYTE *)this + 84) = 0;
  *((_BYTE *)this + 92) = 0;
  *((_BYTE *)this + 100) = 0;
  *((_BYTE *)this + 112) = 0;
  *((_BYTE *)this + 120) = 0;
  TzautoupdateWorker::InitializeFinders(v8, &v11, a4 == 0);
  TimezoneDeterminer::TimezoneDeterminer((char *)this + 128);
  if ( (_QWORD)v11 )
  {
    std::vector<std::unique_ptr<Finder>>::_Destroy(v9, v11, *((_QWORD *)&v11 + 1));
    operator delete((void *)v11);
    v11 = 0;
    v12 = 0;
  }
  *((_QWORD *)this + 24) = this;
  *((_QWORD *)this + 25) = (char *)this + 192;
  *((_QWORD *)this + 26) = WnfSubscription<WNF_CELL_REGISTRATION_STATUS_DETAILS_TYPE,&_WNF_STATE_NAME const WNF_CELL_REGISTRATION_STATUS_DETAILS_CAN0,MccDataSource,&private: void MccDataSource::WnfCellRegistrationStatusDetailsCallback(WNF_CELL_REGISTRATION_STATUS_DETAILS_TYPE const &)>::WnfSubscribe((char *)this + 200);
  *((_QWORD *)this + 27) = (char *)this + 192;
  *((_QWORD *)this + 28) = WnfSubscription<WNF_CELL_REGISTRATION_STATUS_DETAILS_TYPE,&_WNF_STATE_NAME const WNF_CELL_REGISTRATION_STATUS_DETAILS_CAN1,MccDataSource,&private: void MccDataSource::WnfCellRegistrationStatusDetailsCallback(WNF_CELL_REGISTRATION_STATUS_DETAILS_TYPE const &)>::WnfSubscribe((char *)this + 216);
  *((_QWORD *)this + 29) = this;
  *((_QWORD *)this + 30) = (char *)this + 232;
  *((_QWORD *)this + 31) = WnfSubscription<WNF_CELL_NITZ_INFO_TYPE,&_WNF_STATE_NAME const WNF_CELL_NITZ_INFO,NitzDataSource,&private: void NitzDataSource::WnfCellNetworkTimeCallback(WNF_CELL_NITZ_INFO_TYPE const &)>::WnfSubscribe((char *)this + 240);
  *((_QWORD *)this + 32) = (char *)this + 232;
  *((_QWORD *)this + 33) = WnfSubscription<WNF_CELL_REGISTRATION_STATUS_DETAILS_TYPE,&_WNF_STATE_NAME const WNF_CELL_REGISTRATION_STATUS_DETAILS_CAN0,NitzDataSource,&private: void NitzDataSource::WnfCellRegistrationStatusDetailsCallback(WNF_CELL_REGISTRATION_STATUS_DETAILS_TYPE const &)>::WnfSubscribe((char *)this + 256);
  *((_QWORD *)this + 34) = (char *)this + 232;
  *((_QWORD *)this + 35) = WnfSubscription<WNF_CELL_REGISTRATION_STATUS_DETAILS_TYPE,&_WNF_STATE_NAME const WNF_CELL_REGISTRATION_STATUS_DETAILS_CAN1,NitzDataSource,&private: void NitzDataSource::WnfCellRegistrationStatusDetailsCallback(WNF_CELL_REGISTRATION_STATUS_DETAILS_TYPE const &)>::WnfSubscribe((char *)this + 272);
  LocationDataSource::LocationDataSource((TzautoupdateWorker *)((char *)this + 288), this, a2, a4 == 0, a3);
  return this;
}

```

## disassembly

```asm
0x180004018  mov     [rsp+arg_8], rbx
0x18000401d  mov     [rsp+arg_0], rcx
0x180004022  push    rbp
0x180004023  push    rsi
0x180004024  push    rdi
0x180004025  push    r14
0x180004027  push    r15
0x180004029  sub     rsp, 50h
0x18000402d  mov     rdi, r9
0x180004030  mov     r14b, r8b
0x180004033  mov     r15d, edx
0x180004036  mov     rsi, rcx
0x180004039  call    cs:__imp_InitializeSRWLock
0x18000403f  mov     qword ptr [rsi+20h], 0
0x180004047  mov     byte ptr [rsi+40h], 0
0x18000404b  mov     byte ptr [rsi+49h], 0
0x18000404f  mov     byte ptr [rsi+4Bh], 0
0x180004053  mov     byte ptr [rsi+4Dh], 0
0x180004057  mov     byte ptr [rsi+54h], 0
0x18000405b  mov     byte ptr [rsi+5Ch], 0
0x18000405f  mov     byte ptr [rsi+64h], 0
0x180004063  mov     byte ptr [rsi+70h], 0
0x180004067  mov     byte ptr [rsi+78h], 0
0x18000406b  test    rdi, rdi
0x18000406e  setz    bpl
0x180004072  mov     r8b, bpl
0x180004075  lea     rdx, [rsp+78h+var_48]
0x18000407a  call    ?InitializeFinders@TzautoupdateWorker@@AEAA?AV?$vector@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@V?$allocator@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@@2@@std@@_N@Z; TzautoupdateWorker::InitializeFinders(bool)
0x18000407f  nop
0x180004080  mov     r9, rdi
0x180004083  mov     r8, rax
0x180004086  mov     rdx, rsi
0x180004089  lea     rcx, [rsi+80h]; pv
0x180004090  call    ??0TimezoneDeterminer@@QEAA@AEAVCache@@$$QEAV?$vector@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@V?$allocator@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@@2@@std@@PEAX@Z; TimezoneDeterminer::TimezoneDeterminer(Cache &,std::vector<std::unique_ptr<Finder>> &&,void *)
0x180004095  nop
0x180004096  mov     rdx, qword ptr [rsp+78h+var_48]
0x18000409b  test    rdx, rdx
0x18000409e  jz      short loc_1800040C7
0x1800040a0  mov     r8, qword ptr [rsp+78h+var_48+8]
0x1800040a5  call    ?_Destroy@?$vector@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@V?$allocator@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@2@0@Z; std::vector<std::unique_ptr<Finder>>::_Destroy(std::unique_ptr<Finder> *,std::unique_ptr<Finder> *)
0x1800040aa  mov     rcx, qword ptr [rsp+78h+var_48]
0x1800040af  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800040b5  xorps   xmm0, xmm0
0x1800040b8  movdqu  [rsp+78h+var_48], xmm0
0x1800040be  mov     [rsp+78h+var_38], 0
0x1800040c7  lea     rdi, [rsi+0C0h]
0x1800040ce  mov     [rsp+78h+arg_18], rdi
0x1800040d6  mov     [rdi], rsi
0x1800040d9  mov     [rdi+8], rdi
0x1800040dd  lea     rcx, [rdi+8]
0x1800040e1  call    ?WnfSubscribe@?$WnfSubscription@UWNF_CELL_REGISTRATION_STATUS_DETAILS_TYPE@@$1?WNF_CELL_REGISTRATION_STATUS_DETAILS_CAN0@@3U_WNF_STATE_NAME@@BVMccDataSource@@$1?WnfCellRegistrationStatusDetailsCallback@4@AEAAXAEBU1@@Z@@AEAAPEAU_WNF_USER_SUBSCRIPTION@@XZ; WnfSubscription<WNF_CELL_REGISTRATION_STATUS_DETAILS_TYPE,&_WNF_STATE_NAME const WNF_CELL_REGISTRATION_STATUS_DETAILS_CAN0,MccDataSource,&MccDataSource::WnfCellRegistrationStatusDetailsCallback(WNF_CELL_REGISTRATION_STATUS_DETAILS_TYPE const &)>::WnfSubscribe(void)
0x1800040e6  mov     [rdi+10h], rax
0x1800040ea  mov     [rdi+18h], rdi
0x1800040ee  lea     rcx, [rdi+18h]
0x1800040f2  call    ?WnfSubscribe@?$WnfSubscription@UWNF_CELL_REGISTRATION_STATUS_DETAILS_TYPE@@$1?WNF_CELL_REGISTRATION_STATUS_DETAILS_CAN1@@3U_WNF_STATE_NAME@@BVMccDataSource@@$1?WnfCellRegistrationStatusDetailsCallback@4@AEAAXAEBU1@@Z@@AEAAPEAU_WNF_USER_SUBSCRIPTION@@XZ; WnfSubscription<WNF_CELL_REGISTRATION_STATUS_DETAILS_TYPE,&_WNF_STATE_NAME const WNF_CELL_REGISTRATION_STATUS_DETAILS_CAN1,MccDataSource,&MccDataSource::WnfCellRegistrationStatusDetailsCallback(WNF_CELL_REGISTRATION_STATUS_DETAILS_TYPE const &)>::WnfSubscribe(void)
0x1800040f7  mov     [rdi+20h], rax
0x1800040fb  lea     rdi, [rsi+0E8h]
0x180004102  mov     [rsp+78h+arg_18], rdi
0x18000410a  mov     [rdi], rsi
0x18000410d  mov     [rdi+8], rdi
0x180004111  lea     rcx, [rdi+8]
0x180004115  call    ?WnfSubscribe@?$WnfSubscription@UWNF_CELL_NITZ_INFO_TYPE@@$1?WNF_CELL_NITZ_INFO@@3U_WNF_STATE_NAME@@BVNitzDataSource@@$1?WnfCellNetworkTimeCallback@4@AEAAXAEBU1@@Z@@AEAAPEAU_WNF_USER_SUBSCRIPTION@@XZ; WnfSubscription<WNF_CELL_NITZ_INFO_TYPE,&_WNF_STATE_NAME const WNF_CELL_NITZ_INFO,NitzDataSource,&NitzDataSource::WnfCellNetworkTimeCallback(WNF_CELL_NITZ_INFO_TYPE const &)>::WnfSubscribe(void)
0x18000411a  mov     [rdi+10h], rax
0x18000411e  mov     [rdi+18h], rdi
0x180004122  lea     rcx, [rdi+18h]
0x180004126  call    ?WnfSubscribe@?$WnfSubscription@UWNF_CELL_REGISTRATION_STATUS_DETAILS_TYPE@@$1?WNF_CELL_REGISTRATION_STATUS_DETAILS_CAN0@@3U_WNF_STATE_NAME@@BVNitzDataSource@@$1?WnfCellRegistrationStatusDetailsCallback@4@AEAAXAEBU1@@Z@@AEAAPEAU_WNF_USER_SUBSCRIPTION@@XZ; WnfSubscription<WNF_CELL_REGISTRATION_STATUS_DETAILS_TYPE,&_WNF_STATE_NAME const WNF_CELL_REGISTRATION_STATUS_DETAILS_CAN0,NitzDataSource,&NitzDataSource::WnfCellRegistrationStatusDetailsCallback(WNF_CELL_REGISTRATION_STATUS_DETAILS_TYPE const &)>::WnfSubscribe(void)
0x18000412b  mov     [rdi+20h], rax
0x18000412f  mov     [rdi+28h], rdi
0x180004133  lea     rcx, [rdi+28h]
0x180004137  call    ?WnfSubscribe@?$WnfSubscription@UWNF_CELL_REGISTRATION_STATUS_DETAILS_TYPE@@$1?WNF_CELL_REGISTRATION_STATUS_DETAILS_CAN1@@3U_WNF_STATE_NAME@@BVNitzDataSource@@$1?WnfCellRegistrationStatusDetailsCallback@4@AEAAXAEBU1@@Z@@AEAAPEAU_WNF_USER_SUBSCRIPTION@@XZ; WnfSubscription<WNF_CELL_REGISTRATION_STATUS_DETAILS_TYPE,&_WNF_STATE_NAME const WNF_CELL_REGISTRATION_STATUS_DETAILS_CAN1,NitzDataSource,&NitzDataSource::WnfCellRegistrationStatusDetailsCallback(WNF_CELL_REGISTRATION_STATUS_DETAILS_TYPE const &)>::WnfSubscribe(void)
0x18000413c  mov     [rdi+30h], rax
0x180004140  lea     rcx, [rsi+120h]; this
0x180004147  mov     [rsp+78h+var_58], r14b; bool
0x18000414c  mov     r9b, bpl; bool
0x18000414f  mov     r8d, r15d; unsigned int
0x180004152  mov     rdx, rsi; struct Cache *
0x180004155  call    ??0LocationDataSource@@QEAA@AEAVCache@@K_N1@Z; LocationDataSource::LocationDataSource(Cache &,ulong,bool,bool)
0x18000415a  nop
0x18000415b  mov     rax, rsi
0x18000415e  mov     rbx, [rsp+78h+arg_8]
0x180004166  add     rsp, 50h
0x18000416a  pop     r15
0x18000416c  pop     r14
0x18000416e  pop     rdi
0x18000416f  pop     rsi
0x180004170  pop     rbp
0x180004171  retn
```
