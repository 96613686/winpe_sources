# CWdsTransportConfigurationManager::RestartWdsTransportServices(void)

- ea: `0x18000bd30`
- end: `0x18000be2c`
- name: `?RestartWdsTransportServices@CWdsTransportConfigurationManager@@UEAAJXZ`
- size: `252`
- prototype: `__int64 __fastcall(CWdsTransportConfigurationManager *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000bd30`
- `0x18000c478`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000bd6c`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000be03`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000bd6c`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000be03`

## string_xrefs

- `0x18000bd59`: `-> CWdsTransportConfigurationManager::RestartWdsTransportServices(0x%p)`
- `0x18000bdf0`: `<- CWdsTransportConfigurationManager::RestartWdsTransportServices(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportConfigurationManager::RestartWdsTransportServices(
        CWdsTransportConfigurationManager *this)
{
  __int64 v2; // rbx
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  int v10; // [rsp+20h] [rbp-28h]
  _BYTE v11[24]; // [rsp+30h] [rbp-18h] BYREF
  __int16 v12; // [rsp+50h] [rbp+8h] BYREF

  v12 = 0;
  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v11, (char *)this + 80);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportConfigurationManager::RestartWdsTransportServices(0x%p)",
    this);
  v2 = (*(unsigned int (__fastcall **)(CWdsTransportConfigurationManager *, __int64, __int16 *))(*(_QWORD *)this + 72LL))(
         this,
         0xFFFFFFFFLL,
         &v12);
  if ( (int)ElValidateHr_3(v2, v3, v4, 800) >= 0 )
  {
    if ( v12 )
    {
      v2 = (*(unsigned int (__fastcall **)(CWdsTransportConfigurationManager *))(*(_QWORD *)this + 104LL))(this);
      if ( (int)ElValidateHr_3(v2, v5, v6, 808) >= 0 )
      {
        v2 = (*(unsigned int (__fastcall **)(CWdsTransportConfigurationManager *))(*(_QWORD *)this + 96LL))(this);
        ElValidateHr_3(v2, v7, v8, 811);
      }
    }
  }
  v10 = v2;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportConfigurationManager::RestartWdsTransportServices(0x%p) =%x",
    this,
    v10);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v11);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000bd30  mov     rax, rsp
0x18000bd33  mov     [rax+10h], rbx
0x18000bd37  mov     [rax+18h], rsi
0x18000bd3b  push    rdi
0x18000bd3c  sub     rsp, 40h
0x18000bd40  mov     rdi, rcx
0x18000bd43  lea     rdx, [rcx+50h]
0x18000bd47  xor     esi, esi
0x18000bd49  lea     rcx, [rax-18h]
0x18000bd4d  mov     [rax+8], si
0x18000bd51  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000bd56  mov     r9, rdi
0x18000bd59  lea     r8, aCwdstransportc_5; "-> CWdsTransportConfigurationManager::R"...
0x18000bd60  mov     edx, 10000h
0x18000bd65  lea     rcx, qword_18003B770
0x18000bd6c  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000bd73  nop     dword ptr [rax+rax+00h]
0x18000bd78  mov     rax, [rdi]
0x18000bd7b  lea     r8, [rsp+48h+arg_0]
0x18000bd80  or      edx, 0FFFFFFFFh
0x18000bd83  mov     rcx, rdi
0x18000bd86  mov     rax, [rax+48h]
0x18000bd8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd8f  mov     r9d, 320h
0x18000bd95  mov     ecx, eax
0x18000bd97  mov     ebx, eax
0x18000bd99  call    ElValidateHr_3
0x18000bd9e  test    eax, eax
0x18000bda0  js      short loc_18000BDE9
0x18000bda2  cmp     [rsp+48h+arg_0], si
0x18000bda7  jz      short loc_18000BDE9
0x18000bda9  mov     rax, [rdi]
0x18000bdac  mov     rcx, rdi
0x18000bdaf  mov     rax, [rax+68h]
0x18000bdb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdb8  mov     r9d, 328h
0x18000bdbe  mov     ecx, eax
0x18000bdc0  mov     ebx, eax
0x18000bdc2  call    ElValidateHr_3
0x18000bdc7  test    eax, eax
0x18000bdc9  js      short loc_18000BDE9
0x18000bdcb  mov     rax, [rdi]
0x18000bdce  mov     rcx, rdi
0x18000bdd1  mov     rax, [rax+60h]
0x18000bdd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdda  mov     r9d, 32Bh
0x18000bde0  mov     ecx, eax
0x18000bde2  mov     ebx, eax
0x18000bde4  call    ElValidateHr_3
0x18000bde9  mov     r9, rdi
0x18000bdec  mov     [rsp+48h+var_28], ebx
0x18000bdf0  lea     r8, aCwdstransportc_47; "<- CWdsTransportConfigurationManager::R"...
0x18000bdf7  mov     edx, 10000h
0x18000bdfc  lea     rcx, qword_18003B770
0x18000be03  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000be0a  nop     dword ptr [rax+rax+00h]
0x18000be0f  lea     rcx, [rsp+48h+var_18]
0x18000be14  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000be19  mov     rsi, [rsp+48h+arg_10]
0x18000be1e  mov     eax, ebx
0x18000be20  mov     rbx, [rsp+48h+arg_8]
0x18000be25  add     rsp, 40h
0x18000be29  pop     rdi
0x18000be2a  retn
```
