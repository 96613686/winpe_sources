# CWdsTransportConfigurationManager::EnableWdsTransportServices(void)

- ea: `0x18000b740`
- end: `0x18000b851`
- name: `?EnableWdsTransportServices@CWdsTransportConfigurationManager@@UEAAJXZ`
- size: `273`
- prototype: `__int64 __fastcall(CWdsTransportConfigurationManager *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000b740`
- `0x18000c59c`

## import_xrefs

- `WdsCommonLib!??1CService@@QEAA@XZ` at `0x18000b828`
- `WdsCommonLib!??1CService@@QEAA@XZ` at `0x18000b828`
- `WdsCommonLib!??0CService@@QEAA@XZ` at `0x18000b767`
- `WdsCommonLib!??0CService@@QEAA@XZ` at `0x18000b767`
- `WdsCommonLib!?Initialize@CService@@QEAAKPEBG@Z` at `0x18000b7a2`
- `WdsCommonLib!?Initialize@CService@@QEAAKPEBG@Z` at `0x18000b7a2`
- `WdsCommonLib!?Enable@CService@@QEAAKPEBG@Z` at `0x18000b7cd`
- `WdsCommonLib!?Enable@CService@@QEAAKPEBG@Z` at `0x18000b7cd`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000b789`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000b817`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000b789`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000b817`

## string_xrefs

- `0x18000b776`: `-> CWdsTransportConfigurationManager::EnableWdsTransportServices(0x%p)`
- `0x18000b804`: `<- CWdsTransportConfigurationManager::EnableWdsTransportServices(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportConfigurationManager::EnableWdsTransportServices(
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
    L"-> CWdsTransportConfigurationManager::EnableWdsTransportServices(0x%p)",
    this);
  v3 = CService::Initialize((CService *)&v11, *(const unsigned __int16 **)(*((_QWORD *)this + 8) + 112LL));
  if ( (unsigned int)ElValidateWin32_3(v3, v4, v5, 601)
    || (v3 = CService::Enable((CService *)&v11, L"WDSServer"), (unsigned int)ElValidateWin32_3(v3, v6, v7, 607)) )
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
    L"<- CWdsTransportConfigurationManager::EnableWdsTransportServices(0x%p) =%x",
    this,
    v9);
  CService::~CService((CService *)&v11);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v10);
  return v2;
}

```

## disassembly

```asm
0x18000b740  mov     [rsp+arg_8], rbx
0x18000b745  mov     [rsp+arg_10], rsi
0x18000b74a  push    rdi
0x18000b74b  sub     rsp, 40h
0x18000b74f  mov     rsi, rcx
0x18000b752  lea     rdx, [rcx+50h]
0x18000b756  lea     rcx, [rsp+48h+var_18]
0x18000b75b  xor     ebx, ebx
0x18000b75d  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000b762  lea     rcx, [rsp+48h+arg_0]
0x18000b767  call    cs:__imp_??0CService@@QEAA@XZ; CService::CService(void)
0x18000b76e  nop     dword ptr [rax+rax+00h]
0x18000b773  mov     r9, rsi
0x18000b776  lea     r8, aCwdstransportc_31; "-> CWdsTransportConfigurationManager::E"...
0x18000b77d  mov     edx, 10000h
0x18000b782  lea     rcx, qword_18003B770
0x18000b789  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000b790  nop     dword ptr [rax+rax+00h]
0x18000b795  mov     rdx, [rsi+40h]
0x18000b799  lea     rcx, [rsp+48h+arg_0]
0x18000b79e  mov     rdx, [rdx+70h]
0x18000b7a2  call    cs:__imp_?Initialize@CService@@QEAAKPEBG@Z; CService::Initialize(ushort const *)
0x18000b7a9  nop     dword ptr [rax+rax+00h]
0x18000b7ae  mov     ecx, eax
0x18000b7b0  mov     r9d, 259h
0x18000b7b6  mov     edi, eax
0x18000b7b8  call    ElValidateWin32_3
0x18000b7bd  test    eax, eax
0x18000b7bf  jnz     short loc_18000B7EC
0x18000b7c1  lea     rdx, aWdsserver; "WDSServer"
0x18000b7c8  lea     rcx, [rsp+48h+arg_0]
0x18000b7cd  call    cs:__imp_?Enable@CService@@QEAAKPEBG@Z; CService::Enable(ushort const *)
0x18000b7d4  nop     dword ptr [rax+rax+00h]
0x18000b7d9  mov     ecx, eax
0x18000b7db  mov     r9d, 25Fh
0x18000b7e1  mov     edi, eax
0x18000b7e3  call    ElValidateWin32_3
0x18000b7e8  test    eax, eax
0x18000b7ea  jz      short loc_18000B7FD
0x18000b7ec  test    edi, edi
0x18000b7ee  jg      short loc_18000B7F4
0x18000b7f0  mov     ebx, edi
0x18000b7f2  jmp     short loc_18000B7FD
0x18000b7f4  movzx   ebx, di
0x18000b7f7  or      ebx, 80070000h
0x18000b7fd  mov     r9, rsi
0x18000b800  mov     [rsp+48h+var_28], ebx
0x18000b804  lea     r8, aCwdstransportc_3; "<- CWdsTransportConfigurationManager::E"...
0x18000b80b  mov     edx, 10000h
0x18000b810  lea     rcx, qword_18003B770
0x18000b817  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000b81e  nop     dword ptr [rax+rax+00h]
0x18000b823  lea     rcx, [rsp+48h+arg_0]
0x18000b828  call    cs:__imp_??1CService@@QEAA@XZ; CService::~CService(void)
0x18000b82f  nop     dword ptr [rax+rax+00h]
0x18000b834  lea     rcx, [rsp+48h+var_18]
0x18000b839  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000b83e  mov     rsi, [rsp+48h+arg_10]
0x18000b843  mov     eax, ebx
0x18000b845  mov     rbx, [rsp+48h+arg_8]
0x18000b84a  add     rsp, 40h
0x18000b84e  pop     rdi
0x18000b84f  retn
```
