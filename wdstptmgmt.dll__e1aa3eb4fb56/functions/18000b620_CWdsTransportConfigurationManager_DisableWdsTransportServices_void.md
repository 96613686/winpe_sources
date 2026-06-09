# CWdsTransportConfigurationManager::DisableWdsTransportServices(void)

- ea: `0x18000b620`
- end: `0x18000b731`
- name: `?DisableWdsTransportServices@CWdsTransportConfigurationManager@@UEAAJXZ`
- size: `273`
- prototype: `__int64 __fastcall(CWdsTransportConfigurationManager *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000b620`
- `0x18000c59c`

## import_xrefs

- `WdsCommonLib!??1CService@@QEAA@XZ` at `0x18000b708`
- `WdsCommonLib!??1CService@@QEAA@XZ` at `0x18000b708`
- `WdsCommonLib!?Disable@CService@@QEAAKPEBG@Z` at `0x18000b6ad`
- `WdsCommonLib!?Disable@CService@@QEAAKPEBG@Z` at `0x18000b6ad`
- `WdsCommonLib!??0CService@@QEAA@XZ` at `0x18000b647`
- `WdsCommonLib!??0CService@@QEAA@XZ` at `0x18000b647`
- `WdsCommonLib!?Initialize@CService@@QEAAKPEBG@Z` at `0x18000b682`
- `WdsCommonLib!?Initialize@CService@@QEAAKPEBG@Z` at `0x18000b682`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000b669`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000b6f7`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000b669`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000b6f7`

## string_xrefs

- `0x18000b656`: `-> CWdsTransportConfigurationManager::DisableWdsTransportServices(0x%p)`
- `0x18000b6e4`: `<- CWdsTransportConfigurationManager::DisableWdsTransportServices(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportConfigurationManager::DisableWdsTransportServices(
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
    L"-> CWdsTransportConfigurationManager::DisableWdsTransportServices(0x%p)",
    this);
  v3 = CService::Initialize((CService *)&v11, *(const unsigned __int16 **)(*((_QWORD *)this + 8) + 112LL));
  if ( (unsigned int)ElValidateWin32_3(v3, v4, v5, 649)
    || (v3 = CService::Disable((CService *)&v11, L"WDSServer"), (unsigned int)ElValidateWin32_3(v3, v6, v7, 655)) )
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
    L"<- CWdsTransportConfigurationManager::DisableWdsTransportServices(0x%p) =%x",
    this,
    v9);
  CService::~CService((CService *)&v11);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v10);
  return v2;
}

```

## disassembly

```asm
0x18000b620  mov     [rsp+arg_8], rbx
0x18000b625  mov     [rsp+arg_10], rsi
0x18000b62a  push    rdi
0x18000b62b  sub     rsp, 40h
0x18000b62f  mov     rsi, rcx
0x18000b632  lea     rdx, [rcx+50h]
0x18000b636  lea     rcx, [rsp+48h+var_18]
0x18000b63b  xor     ebx, ebx
0x18000b63d  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000b642  lea     rcx, [rsp+48h+arg_0]
0x18000b647  call    cs:__imp_??0CService@@QEAA@XZ; CService::CService(void)
0x18000b64e  nop     dword ptr [rax+rax+00h]
0x18000b653  mov     r9, rsi
0x18000b656  lea     r8, aCwdstransportc_36; "-> CWdsTransportConfigurationManager::D"...
0x18000b65d  mov     edx, 10000h
0x18000b662  lea     rcx, qword_18003B770
0x18000b669  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000b670  nop     dword ptr [rax+rax+00h]
0x18000b675  mov     rdx, [rsi+40h]
0x18000b679  lea     rcx, [rsp+48h+arg_0]
0x18000b67e  mov     rdx, [rdx+70h]
0x18000b682  call    cs:__imp_?Initialize@CService@@QEAAKPEBG@Z; CService::Initialize(ushort const *)
0x18000b689  nop     dword ptr [rax+rax+00h]
0x18000b68e  mov     ecx, eax
0x18000b690  mov     r9d, 289h
0x18000b696  mov     edi, eax
0x18000b698  call    ElValidateWin32_3
0x18000b69d  test    eax, eax
0x18000b69f  jnz     short loc_18000B6CC
0x18000b6a1  lea     rdx, aWdsserver; "WDSServer"
0x18000b6a8  lea     rcx, [rsp+48h+arg_0]
0x18000b6ad  call    cs:__imp_?Disable@CService@@QEAAKPEBG@Z; CService::Disable(ushort const *)
0x18000b6b4  nop     dword ptr [rax+rax+00h]
0x18000b6b9  mov     ecx, eax
0x18000b6bb  mov     r9d, 28Fh
0x18000b6c1  mov     edi, eax
0x18000b6c3  call    ElValidateWin32_3
0x18000b6c8  test    eax, eax
0x18000b6ca  jz      short loc_18000B6DD
0x18000b6cc  test    edi, edi
0x18000b6ce  jg      short loc_18000B6D4
0x18000b6d0  mov     ebx, edi
0x18000b6d2  jmp     short loc_18000B6DD
0x18000b6d4  movzx   ebx, di
0x18000b6d7  or      ebx, 80070000h
0x18000b6dd  mov     r9, rsi
0x18000b6e0  mov     [rsp+48h+var_28], ebx
0x18000b6e4  lea     r8, aCwdstransportc_13; "<- CWdsTransportConfigurationManager::D"...
0x18000b6eb  mov     edx, 10000h
0x18000b6f0  lea     rcx, qword_18003B770
0x18000b6f7  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000b6fe  nop     dword ptr [rax+rax+00h]
0x18000b703  lea     rcx, [rsp+48h+arg_0]
0x18000b708  call    cs:__imp_??1CService@@QEAA@XZ; CService::~CService(void)
0x18000b70f  nop     dword ptr [rax+rax+00h]
0x18000b714  lea     rcx, [rsp+48h+var_18]
0x18000b719  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000b71e  mov     rsi, [rsp+48h+arg_10]
0x18000b723  mov     eax, ebx
0x18000b725  mov     rbx, [rsp+48h+arg_8]
0x18000b72a  add     rsp, 40h
0x18000b72e  pop     rdi
0x18000b72f  retn
```
