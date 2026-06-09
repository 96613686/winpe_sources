# CWdsTransportConfigurationManager::StopWdsTransportServices(void)

- ea: `0x18000bf60`
- end: `0x18000c075`
- name: `?StopWdsTransportServices@CWdsTransportConfigurationManager@@UEAAJXZ`
- size: `277`
- prototype: `__int64 __fastcall(CWdsTransportConfigurationManager *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000bf60`
- `0x18000c59c`

## import_xrefs

- `WdsCommonLib!??1CService@@QEAA@XZ` at `0x18000c04c`
- `WdsCommonLib!??1CService@@QEAA@XZ` at `0x18000c04c`
- `WdsCommonLib!??0CService@@QEAA@XZ` at `0x18000bf87`
- `WdsCommonLib!??0CService@@QEAA@XZ` at `0x18000bf87`
- `WdsCommonLib!?Initialize@CService@@QEAAKPEBG@Z` at `0x18000bfc2`
- `WdsCommonLib!?Initialize@CService@@QEAAKPEBG@Z` at `0x18000bfc2`
- `WdsCommonLib!?Stop@CService@@QEAAKPEBGW4WDS_SERVICE_WAIT_TYPE@@@Z` at `0x18000bff1`
- `WdsCommonLib!?Stop@CService@@QEAAKPEBGW4WDS_SERVICE_WAIT_TYPE@@@Z` at `0x18000bff1`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000bfa9`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000c03b`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000bfa9`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000c03b`

## string_xrefs

- `0x18000bf96`: `-> CWdsTransportConfigurationManager::StopWdsTransportServices(0x%p)`
- `0x18000c028`: `<- CWdsTransportConfigurationManager::StopWdsTransportServices(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportConfigurationManager::StopWdsTransportServices(CWdsTransportConfigurationManager *this)
{
  unsigned int v2; // ebx
  __int64 v3; // rdi
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // r8
  unsigned int v9; // [rsp+20h] [rbp-28h]
  _BYTE v10[24]; // [rsp+30h] [rbp-18h] BYREF
  char v11; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v10, (char *)this + 80);
  CService::CService((CService *)&v11);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportConfigurationManager::StopWdsTransportServices(0x%p)",
    this);
  v3 = CService::Initialize((CService *)&v11, *(const unsigned __int16 **)(*((_QWORD *)this + 8) + 112LL));
  if ( (unsigned int)ElValidateWin32_3(v3, v4, v5, 745)
    || (v3 = (unsigned int)CService::Stop(&v11, L"WDSServer", 1), (unsigned int)ElValidateWin32_3(v3, v6, v7, 751)) )
  {
    if ( (int)v3 > 0 )
      v2 = (unsigned __int16)v3 | 0x80070000;
    else
      v2 = v3;
  }
  v9 = v2;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportConfigurationManager::StopWdsTransportServices(0x%p) =%x",
    this,
    v9);
  CService::~CService((CService *)&v11);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v10);
  return v2;
}

```

## disassembly

```asm
0x18000bf60  mov     [rsp+arg_8], rbx
0x18000bf65  mov     [rsp+arg_10], rsi
0x18000bf6a  push    rdi
0x18000bf6b  sub     rsp, 40h
0x18000bf6f  mov     rsi, rcx
0x18000bf72  lea     rdx, [rcx+50h]
0x18000bf76  lea     rcx, [rsp+48h+var_18]
0x18000bf7b  xor     ebx, ebx
0x18000bf7d  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000bf82  lea     rcx, [rsp+48h+arg_0]
0x18000bf87  call    cs:__imp_??0CService@@QEAA@XZ; CService::CService(void)
0x18000bf8e  nop     dword ptr [rax+rax+00h]
0x18000bf93  mov     r9, rsi
0x18000bf96  lea     r8, aCwdstransportc_12; "-> CWdsTransportConfigurationManager::S"...
0x18000bf9d  mov     edx, 10000h
0x18000bfa2  lea     rcx, qword_18003B770
0x18000bfa9  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000bfb0  nop     dword ptr [rax+rax+00h]
0x18000bfb5  mov     rdx, [rsi+40h]
0x18000bfb9  lea     rcx, [rsp+48h+arg_0]
0x18000bfbe  mov     rdx, [rdx+70h]
0x18000bfc2  call    cs:__imp_?Initialize@CService@@QEAAKPEBG@Z; CService::Initialize(ushort const *)
0x18000bfc9  nop     dword ptr [rax+rax+00h]
0x18000bfce  mov     ecx, eax
0x18000bfd0  mov     r9d, 2E9h
0x18000bfd6  mov     edi, eax
0x18000bfd8  call    ElValidateWin32_3
0x18000bfdd  test    eax, eax
0x18000bfdf  jnz     short loc_18000C010
0x18000bfe1  lea     r8d, [rbx+1]
0x18000bfe5  lea     rdx, aWdsserver; "WDSServer"
0x18000bfec  lea     rcx, [rsp+48h+arg_0]
0x18000bff1  call    cs:__imp_?Stop@CService@@QEAAKPEBGW4WDS_SERVICE_WAIT_TYPE@@@Z; CService::Stop(ushort const *,WDS_SERVICE_WAIT_TYPE)
0x18000bff8  nop     dword ptr [rax+rax+00h]
0x18000bffd  mov     ecx, eax
0x18000bfff  mov     r9d, 2EFh
0x18000c005  mov     edi, eax
0x18000c007  call    ElValidateWin32_3
0x18000c00c  test    eax, eax
0x18000c00e  jz      short loc_18000C021
0x18000c010  test    edi, edi
0x18000c012  jg      short loc_18000C018
0x18000c014  mov     ebx, edi
0x18000c016  jmp     short loc_18000C021
0x18000c018  movzx   ebx, di
0x18000c01b  or      ebx, 80070000h
0x18000c021  mov     r9, rsi
0x18000c024  mov     [rsp+48h+var_28], ebx
0x18000c028  lea     r8, aCwdstransportc_26; "<- CWdsTransportConfigurationManager::S"...
0x18000c02f  mov     edx, 10000h
0x18000c034  lea     rcx, qword_18003B770
0x18000c03b  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000c042  nop     dword ptr [rax+rax+00h]
0x18000c047  lea     rcx, [rsp+48h+arg_0]
0x18000c04c  call    cs:__imp_??1CService@@QEAA@XZ; CService::~CService(void)
0x18000c053  nop     dword ptr [rax+rax+00h]
0x18000c058  lea     rcx, [rsp+48h+var_18]
0x18000c05d  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000c062  mov     rsi, [rsp+48h+arg_10]
0x18000c067  mov     eax, ebx
0x18000c069  mov     rbx, [rsp+48h+arg_8]
0x18000c06e  add     rsp, 40h
0x18000c072  pop     rdi
0x18000c073  retn
```
