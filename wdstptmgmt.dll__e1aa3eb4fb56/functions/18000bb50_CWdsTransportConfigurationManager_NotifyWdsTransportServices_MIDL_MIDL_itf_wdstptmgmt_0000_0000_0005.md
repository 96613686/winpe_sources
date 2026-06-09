# CWdsTransportConfigurationManager::NotifyWdsTransportServices(__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0005)

- ea: `0x18000bb50`
- end: `0x18000bc8f`
- name: `?NotifyWdsTransportServices@CWdsTransportConfigurationManager@@UEAAJW4__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0005@@@Z`
- size: `319`
- prototype: `__int64 __fastcall(CWdsTransportConfigurationManager *__hidden this, enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0005)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000bb50`
- `0x18000c59c`

## import_xrefs

- `WdsCommonLib!??1CService@@QEAA@XZ` at `0x18000bc66`
- `WdsCommonLib!??1CService@@QEAA@XZ` at `0x18000bc66`
- `WdsCommonLib!??0CService@@QEAA@XZ` at `0x18000bb77`
- `WdsCommonLib!??0CService@@QEAA@XZ` at `0x18000bb77`
- `WdsCommonLib!?Initialize@CService@@QEAAKPEBG@Z` at `0x18000bbb2`
- `WdsCommonLib!?Initialize@CService@@QEAAKPEBG@Z` at `0x18000bbb2`
- `WdsCommonLib!?Notify@CService@@QEAAKPEBGKW4WDS_SERVICE_WAIT_TYPE@@@Z` at `0x18000bbfc`
- `WdsCommonLib!?Notify@CService@@QEAAKPEBGKW4WDS_SERVICE_WAIT_TYPE@@@Z` at `0x18000bbfc`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000bb99`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000bc2f`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000bc55`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000bb99`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000bc2f`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000bc55`

## string_xrefs

- `0x18000bb86`: `-> CWdsTransportConfigurationManager::NotifyWdsTransportServices(0x%p)`
- `0x18000bc17`: `Encountered an invalid service notification type: %u.\n`
- `0x18000bc42`: `<- CWdsTransportConfigurationManager::NotifyWdsTransportServices(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportConfigurationManager::NotifyWdsTransportServices(
        CWdsTransportConfigurationManager *this,
        unsigned int a2)
{
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // eax
  _BYTE v9[24]; // [rsp+30h] [rbp-18h] BYREF
  char v10; // [rsp+50h] [rbp+8h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v9, (char *)this + 80);
  CService::CService((CService *)&v10);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportConfigurationManager::NotifyWdsTransportServices(0x%p)",
    this);
  v4 = CService::Initialize((CService *)&v10, *(const unsigned __int16 **)(*((_QWORD *)this + 8) + 112LL));
  if ( !(unsigned int)ElValidateWin32_3(v4, v5, v6, 858) )
  {
    if ( a2 != 1 )
    {
      LODWORD(v4) = -2147024809;
      CTrace::Trace((CTrace *)qword_18003B770, 0x80000u, L"Encountered an invalid service notification type: %u.\n", a2);
      goto LABEL_9;
    }
    v7 = CService::Notify(&v10, L"WDSServer", 128, 1);
    LODWORD(v4) = 0;
    if ( v7 != 1062 )
      LODWORD(v4) = v7;
  }
  if ( (int)v4 > 0 )
    LODWORD(v4) = (unsigned __int16)v4 | 0x80070000;
LABEL_9:
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportConfigurationManager::NotifyWdsTransportServices(0x%p) =%x",
    this,
    v4);
  CService::~CService((CService *)&v10);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000bb50  mov     [rsp+arg_8], rbx
0x18000bb55  mov     [rsp+arg_10], rsi
0x18000bb5a  push    rdi
0x18000bb5b  sub     rsp, 40h
0x18000bb5f  mov     edi, edx
0x18000bb61  mov     rsi, rcx
0x18000bb64  lea     rdx, [rcx+50h]
0x18000bb68  lea     rcx, [rsp+48h+var_18]
0x18000bb6d  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000bb72  lea     rcx, [rsp+48h+arg_0]
0x18000bb77  call    cs:__imp_??0CService@@QEAA@XZ; CService::CService(void)
0x18000bb7e  nop     dword ptr [rax+rax+00h]
0x18000bb83  mov     r9, rsi
0x18000bb86  lea     r8, aCwdstransportc_21; "-> CWdsTransportConfigurationManager::N"...
0x18000bb8d  mov     edx, 10000h
0x18000bb92  lea     rcx, qword_18003B770
0x18000bb99  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000bba0  nop     dword ptr [rax+rax+00h]
0x18000bba5  mov     rdx, [rsi+40h]
0x18000bba9  lea     rcx, [rsp+48h+arg_0]
0x18000bbae  mov     rdx, [rdx+70h]
0x18000bbb2  call    cs:__imp_?Initialize@CService@@QEAAKPEBG@Z; CService::Initialize(ushort const *)
0x18000bbb9  nop     dword ptr [rax+rax+00h]
0x18000bbbe  mov     ecx, eax
0x18000bbc0  mov     r9d, 35Ah
0x18000bbc6  mov     ebx, eax
0x18000bbc8  call    ElValidateWin32_3
0x18000bbcd  test    eax, eax
0x18000bbcf  jz      short loc_18000BBE0
0x18000bbd1  test    ebx, ebx
0x18000bbd3  jle     short loc_18000BC3B
0x18000bbd5  movzx   ebx, bx
0x18000bbd8  or      ebx, 80070000h
0x18000bbde  jmp     short loc_18000BC3B
0x18000bbe0  test    edi, edi
0x18000bbe2  jz      short loc_18000BC14
0x18000bbe4  cmp     edi, 1
0x18000bbe7  jnz     short loc_18000BC14
0x18000bbe9  mov     r9d, edi
0x18000bbec  lea     r8d, [rdi+7Fh]
0x18000bbf0  lea     rdx, aWdsserver; "WDSServer"
0x18000bbf7  lea     rcx, [rsp+48h+arg_0]
0x18000bbfc  call    cs:__imp_?Notify@CService@@QEAAKPEBGKW4WDS_SERVICE_WAIT_TYPE@@@Z; CService::Notify(ushort const *,ulong,WDS_SERVICE_WAIT_TYPE)
0x18000bc03  nop     dword ptr [rax+rax+00h]
0x18000bc08  xor     ebx, ebx
0x18000bc0a  cmp     eax, 426h
0x18000bc0f  cmovnz  ebx, eax
0x18000bc12  jmp     short loc_18000BBD1
0x18000bc14  mov     r9d, edi
0x18000bc17  lea     r8, aEncounteredAnI_0; "Encountered an invalid service notifica"...
0x18000bc1e  mov     edx, 80000h
0x18000bc23  lea     rcx, qword_18003B770
0x18000bc2a  mov     ebx, 80070057h
0x18000bc2f  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000bc36  nop     dword ptr [rax+rax+00h]
0x18000bc3b  mov     r9, rsi
0x18000bc3e  mov     [rsp+48h+var_28], ebx
0x18000bc42  lea     r8, aCwdstransportc_43; "<- CWdsTransportConfigurationManager::N"...
0x18000bc49  mov     edx, 10000h
0x18000bc4e  lea     rcx, qword_18003B770
0x18000bc55  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000bc5c  nop     dword ptr [rax+rax+00h]
0x18000bc61  lea     rcx, [rsp+48h+arg_0]
0x18000bc66  call    cs:__imp_??1CService@@QEAA@XZ; CService::~CService(void)
0x18000bc6d  nop     dword ptr [rax+rax+00h]
0x18000bc72  lea     rcx, [rsp+48h+var_18]
0x18000bc77  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000bc7c  mov     rsi, [rsp+48h+arg_10]
0x18000bc81  mov     eax, ebx
0x18000bc83  mov     rbx, [rsp+48h+arg_8]
0x18000bc88  add     rsp, 40h
0x18000bc8c  pop     rdi
0x18000bc8d  retn
```
