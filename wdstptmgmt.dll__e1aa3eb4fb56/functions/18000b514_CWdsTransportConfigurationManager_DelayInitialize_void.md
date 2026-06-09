# CWdsTransportConfigurationManager::DelayInitialize(void)

- ea: `0x18000b514`
- end: `0x18000b615`
- name: `?DelayInitialize@CWdsTransportConfigurationManager@@QEAAJXZ`
- size: `257`
- prototype: `__int64 __fastcall(CWdsTransportConfigurationManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009720`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180009608`
- `0x18000b514`
- `0x18000c478`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000b559`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000b5e5`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000b559`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000b5e5`

## string_xrefs

- `0x18000b546`: `-> CWdsTransportConfigurationManager::DelayInitialize(0x%p)`
- `0x18000b5d2`: `<- CWdsTransportConfigurationManager::DelayInitialize(0x%p) =%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWdsTransportConfigurationManager::DelayInitialize(CWdsTransportConfigurationManager *this)
{
  int v2; // edi
  __int64 v3; // rsi
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // r8
  int v9; // [rsp+20h] [rbp-28h]
  _BYTE v10[24]; // [rsp+30h] [rbp-18h] BYREF
  __int16 v11; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  LODWORD(v3) = 0;
  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v10, (char *)this + 80);
  v11 = 0;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportConfigurationManager::DelayInitialize(0x%p)",
    this);
  if ( !*((_DWORD *)this + 31) )
  {
    v3 = (unsigned int)CWdsTransportServer::VerifyTransportServerConfigured(*((CWdsTransportServer **)this + 8));
    if ( (int)ElValidateHr_3(v3, v4, v5, 237) >= 0 )
    {
      v3 = (*(unsigned int (__fastcall **)(CWdsTransportConfigurationManager *, __int64, __int16 *))(*(_QWORD *)this + 72LL))(
             this,
             0xFFFFFFFFLL,
             &v11);
      if ( (int)ElValidateHr_3(v3, v6, v7, 245) >= 0 )
      {
        LOBYTE(v2) = v11 == -1;
        *((_DWORD *)this + 32) = v2;
        *((_DWORD *)this + 31) = 1;
      }
    }
  }
  v9 = v3;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportConfigurationManager::DelayInitialize(0x%p) =%x",
    this,
    v9);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v10);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000b514  mov     rax, rsp
0x18000b517  mov     [rax+10h], rbx
0x18000b51b  mov     [rax+18h], rsi
0x18000b51f  mov     [rax+20h], rdi
0x18000b523  push    r14
0x18000b525  sub     rsp, 40h
0x18000b529  mov     rbx, rcx
0x18000b52c  xor     edi, edi
0x18000b52e  mov     esi, edi
0x18000b530  lea     rdx, [rcx+50h]
0x18000b534  lea     rcx, [rax-18h]
0x18000b538  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000b53d  nop
0x18000b53e  mov     [rsp+48h+arg_0], di
0x18000b543  mov     r9, rbx
0x18000b546  lea     r8, aCwdstransportc_29; "-> CWdsTransportConfigurationManager::D"...
0x18000b54d  mov     edx, 10000h
0x18000b552  lea     rcx, qword_18003B770
0x18000b559  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000b560  nop     dword ptr [rax+rax+00h]
0x18000b565  cmp     [rbx+7Ch], edi
0x18000b568  jnz     short loc_18000B5CB
0x18000b56a  mov     rcx, [rbx+40h]; this
0x18000b56e  call    ?VerifyTransportServerConfigured@CWdsTransportServer@@QEAAJXZ; CWdsTransportServer::VerifyTransportServerConfigured(void)
0x18000b573  mov     esi, eax
0x18000b575  mov     r9d, 0EDh
0x18000b57b  mov     ecx, eax
0x18000b57d  call    ElValidateHr_3
0x18000b582  test    eax, eax
0x18000b584  js      short loc_18000B5CB
0x18000b586  mov     rax, [rbx]
0x18000b589  or      r14d, 0FFFFFFFFh
0x18000b58d  mov     edx, r14d
0x18000b590  lea     r8, [rsp+48h+arg_0]
0x18000b595  mov     rcx, rbx
0x18000b598  mov     rax, [rax+48h]
0x18000b59c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5a1  mov     esi, eax
0x18000b5a3  mov     r9d, 0F5h
0x18000b5a9  mov     ecx, eax
0x18000b5ab  call    ElValidateHr_3
0x18000b5b0  test    eax, eax
0x18000b5b2  js      short loc_18000B5CB
0x18000b5b4  cmp     [rsp+48h+arg_0], r14w
0x18000b5ba  setz    dil
0x18000b5be  mov     [rbx+80h], edi
0x18000b5c4  mov     dword ptr [rbx+7Ch], 1
0x18000b5cb  mov     [rsp+48h+var_28], esi
0x18000b5cf  mov     r9, rbx
0x18000b5d2  lea     r8, aCwdstransportc_14; "<- CWdsTransportConfigurationManager::D"...
0x18000b5d9  mov     edx, 10000h
0x18000b5de  lea     rcx, qword_18003B770
0x18000b5e5  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000b5ec  nop     dword ptr [rax+rax+00h]
0x18000b5f1  nop
0x18000b5f2  lea     rcx, [rsp+48h+var_18]
0x18000b5f7  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000b5fc  mov     eax, esi
0x18000b5fe  mov     rbx, [rsp+48h+arg_8]
0x18000b603  mov     rsi, [rsp+48h+arg_10]
0x18000b608  mov     rdi, [rsp+48h+arg_18]
0x18000b60d  add     rsp, 40h
0x18000b611  pop     r14
0x18000b613  retn
```
