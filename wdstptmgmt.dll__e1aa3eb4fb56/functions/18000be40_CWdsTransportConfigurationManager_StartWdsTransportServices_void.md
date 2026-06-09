# CWdsTransportConfigurationManager::StartWdsTransportServices(void)

- ea: `0x18000be40`
- end: `0x18000bf55`
- name: `?StartWdsTransportServices@CWdsTransportConfigurationManager@@UEAAJXZ`
- size: `277`
- prototype: `__int64 __fastcall(CWdsTransportConfigurationManager *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000be40`
- `0x18000c59c`

## import_xrefs

- `WdsCommonLib!??1CService@@QEAA@XZ` at `0x18000bf2c`
- `WdsCommonLib!??1CService@@QEAA@XZ` at `0x18000bf2c`
- `WdsCommonLib!??0CService@@QEAA@XZ` at `0x18000be67`
- `WdsCommonLib!??0CService@@QEAA@XZ` at `0x18000be67`
- `WdsCommonLib!?Initialize@CService@@QEAAKPEBG@Z` at `0x18000bea2`
- `WdsCommonLib!?Initialize@CService@@QEAAKPEBG@Z` at `0x18000bea2`
- `WdsCommonLib!?Start@CService@@QEAAKPEBGW4WDS_SERVICE_WAIT_TYPE@@@Z` at `0x18000bed1`
- `WdsCommonLib!?Start@CService@@QEAAKPEBGW4WDS_SERVICE_WAIT_TYPE@@@Z` at `0x18000bed1`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000be89`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000bf1b`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000be89`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000bf1b`

## string_xrefs

- `0x18000be76`: `-> CWdsTransportConfigurationManager::StartWdsTransportServices(0x%p)`
- `0x18000bf08`: `<- CWdsTransportConfigurationManager::StartWdsTransportServices(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportConfigurationManager::StartWdsTransportServices(
        CWdsTransportConfigurationManager *this)
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
    L"-> CWdsTransportConfigurationManager::StartWdsTransportServices(0x%p)",
    this);
  v3 = CService::Initialize((CService *)&v11, *(const unsigned __int16 **)(*((_QWORD *)this + 8) + 112LL));
  if ( (unsigned int)ElValidateWin32_3(v3, v4, v5, 698)
    || (v3 = (unsigned int)CService::Start(&v11, L"WDSServer", 1), (unsigned int)ElValidateWin32_3(v3, v6, v7, 704)) )
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
    L"<- CWdsTransportConfigurationManager::StartWdsTransportServices(0x%p) =%x",
    this,
    v9);
  CService::~CService((CService *)&v11);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v10);
  return v2;
}

```

## disassembly

```asm
0x18000be40  mov     [rsp+arg_8], rbx
0x18000be45  mov     [rsp+arg_10], rsi
0x18000be4a  push    rdi
0x18000be4b  sub     rsp, 40h
0x18000be4f  mov     rsi, rcx
0x18000be52  lea     rdx, [rcx+50h]
0x18000be56  lea     rcx, [rsp+48h+var_18]
0x18000be5b  xor     ebx, ebx
0x18000be5d  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000be62  lea     rcx, [rsp+48h+arg_0]
0x18000be67  call    cs:__imp_??0CService@@QEAA@XZ; CService::CService(void)
0x18000be6e  nop     dword ptr [rax+rax+00h]
0x18000be73  mov     r9, rsi
0x18000be76  lea     r8, aCwdstransportc_9; "-> CWdsTransportConfigurationManager::S"...
0x18000be7d  mov     edx, 10000h
0x18000be82  lea     rcx, qword_18003B770
0x18000be89  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000be90  nop     dword ptr [rax+rax+00h]
0x18000be95  mov     rdx, [rsi+40h]
0x18000be99  lea     rcx, [rsp+48h+arg_0]
0x18000be9e  mov     rdx, [rdx+70h]
0x18000bea2  call    cs:__imp_?Initialize@CService@@QEAAKPEBG@Z; CService::Initialize(ushort const *)
0x18000bea9  nop     dword ptr [rax+rax+00h]
0x18000beae  mov     ecx, eax
0x18000beb0  mov     r9d, 2BAh
0x18000beb6  mov     edi, eax
0x18000beb8  call    ElValidateWin32_3
0x18000bebd  test    eax, eax
0x18000bebf  jnz     short loc_18000BEF0
0x18000bec1  lea     r8d, [rbx+1]
0x18000bec5  lea     rdx, aWdsserver; "WDSServer"
0x18000becc  lea     rcx, [rsp+48h+arg_0]
0x18000bed1  call    cs:__imp_?Start@CService@@QEAAKPEBGW4WDS_SERVICE_WAIT_TYPE@@@Z; CService::Start(ushort const *,WDS_SERVICE_WAIT_TYPE)
0x18000bed8  nop     dword ptr [rax+rax+00h]
0x18000bedd  mov     ecx, eax
0x18000bedf  mov     r9d, 2C0h
0x18000bee5  mov     edi, eax
0x18000bee7  call    ElValidateWin32_3
0x18000beec  test    eax, eax
0x18000beee  jz      short loc_18000BF01
0x18000bef0  test    edi, edi
0x18000bef2  jg      short loc_18000BEF8
0x18000bef4  mov     ebx, edi
0x18000bef6  jmp     short loc_18000BF01
0x18000bef8  movzx   ebx, di
0x18000befb  or      ebx, 80070000h
0x18000bf01  mov     r9, rsi
0x18000bf04  mov     [rsp+48h+var_28], ebx
0x18000bf08  lea     r8, aCwdstransportc_22; "<- CWdsTransportConfigurationManager::S"...
0x18000bf0f  mov     edx, 10000h
0x18000bf14  lea     rcx, qword_18003B770
0x18000bf1b  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000bf22  nop     dword ptr [rax+rax+00h]
0x18000bf27  lea     rcx, [rsp+48h+arg_0]
0x18000bf2c  call    cs:__imp_??1CService@@QEAA@XZ; CService::~CService(void)
0x18000bf33  nop     dword ptr [rax+rax+00h]
0x18000bf38  lea     rcx, [rsp+48h+var_18]
0x18000bf3d  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000bf42  mov     rsi, [rsp+48h+arg_10]
0x18000bf47  mov     eax, ebx
0x18000bf49  mov     rbx, [rsp+48h+arg_8]
0x18000bf4e  add     rsp, 40h
0x18000bf52  pop     rdi
0x18000bf53  retn
```
