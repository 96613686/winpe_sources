# CWdsTransportConfigurationManager::get_WdsTransportServicesRunning(short,short *)

- ea: `0x18000c320`
- end: `0x18000c472`
- name: `?get_WdsTransportServicesRunning@CWdsTransportConfigurationManager@@UEAAJFPEAF@Z`
- size: `338`
- prototype: `__int64 __fastcall(CWdsTransportConfigurationManager *__hidden this, __int16, __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000c320`
- `0x18000c59c`

## import_xrefs

- `WdsCommonLib!??1CService@@QEAA@XZ` at `0x18000c44b`
- `WdsCommonLib!??1CService@@QEAA@XZ` at `0x18000c44b`
- `WdsCommonLib!?GetCurrentState@CService@@QEAAKPEBGPEAK@Z` at `0x18000c3e1`
- `WdsCommonLib!?GetCurrentState@CService@@QEAAKPEBGPEAK@Z` at `0x18000c3e1`
- `WdsCommonLib!??0CService@@QEAA@XZ` at `0x18000c34f`
- `WdsCommonLib!??0CService@@QEAA@XZ` at `0x18000c34f`
- `WdsCommonLib!?Initialize@CService@@QEAAKPEBG@Z` at `0x18000c39e`
- `WdsCommonLib!?Initialize@CService@@QEAAKPEBG@Z` at `0x18000c39e`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000c371`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000c43a`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000c371`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000c43a`

## string_xrefs

- `0x18000c35e`: `-> CWdsTransportConfigurationManager::get_WdsTransportServicesRunning(0x%p)`
- `0x18000c427`: `<- CWdsTransportConfigurationManager::get_WdsTransportServicesRunning(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportConfigurationManager::get_WdsTransportServicesRunning(
        CWdsTransportConfigurationManager *this,
        __int16 a2,
        __int16 *a3)
{
  unsigned int v6; // ebx
  __int64 CurrentState; // rdi
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  _BYTE v13[40]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v14; // [rsp+60h] [rbp+8h] BYREF
  char v15; // [rsp+70h] [rbp+18h] BYREF

  v6 = 0;
  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v13, (char *)this + 80);
  v14 = 0;
  CService::CService((CService *)&v15);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportConfigurationManager::get_WdsTransportServicesRunning(0x%p)",
    this);
  if ( !a3 )
  {
    v6 = -2147024809;
    goto LABEL_11;
  }
  if ( !a2 )
  {
LABEL_10:
    *a3 = -(*((_DWORD *)this + 32) != 0);
    goto LABEL_11;
  }
  CurrentState = CService::Initialize((CService *)&v15, *(const unsigned __int16 **)(*((_QWORD *)this + 8) + 112LL));
  if ( !(unsigned int)ElValidateWin32_3(CurrentState, v8, v9, 541) )
  {
    CurrentState = CService::GetCurrentState((CService *)&v15, L"WDSServer", &v14);
    if ( !(unsigned int)ElValidateWin32_3(CurrentState, v10, v11, 548) )
    {
      *((_DWORD *)this + 32) = v14 == 4;
      goto LABEL_10;
    }
  }
  if ( (int)CurrentState > 0 )
    v6 = (unsigned __int16)CurrentState | 0x80070000;
  else
    v6 = CurrentState;
LABEL_11:
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportConfigurationManager::get_WdsTransportServicesRunning(0x%p) =%x",
    this,
    v6);
  CService::~CService((CService *)&v15);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v13);
  return v6;
}

```

## disassembly

```asm
0x18000c320  mov     [rsp+arg_8], rbx
0x18000c325  push    rsi
0x18000c326  push    rdi
0x18000c327  push    r14
0x18000c329  sub     rsp, 40h
0x18000c32d  movzx   edi, dx
0x18000c330  mov     rsi, rcx
0x18000c333  lea     rdx, [rcx+50h]
0x18000c337  mov     r14, r8
0x18000c33a  lea     rcx, [rsp+58h+var_28]
0x18000c33f  xor     ebx, ebx
0x18000c341  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000c346  lea     rcx, [rsp+58h+arg_10]
0x18000c34b  mov     [rsp+58h+arg_0], ebx
0x18000c34f  call    cs:__imp_??0CService@@QEAA@XZ; CService::CService(void)
0x18000c356  nop     dword ptr [rax+rax+00h]
0x18000c35b  mov     r9, rsi
0x18000c35e  lea     r8, aCwdstransportc_45; "-> CWdsTransportConfigurationManager::g"...
0x18000c365  mov     edx, 10000h
0x18000c36a  lea     rcx, qword_18003B770
0x18000c371  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000c378  nop     dword ptr [rax+rax+00h]
0x18000c37d  test    r14, r14
0x18000c380  jnz     short loc_18000C38C
0x18000c382  mov     ebx, 80070057h
0x18000c387  jmp     loc_18000C420
0x18000c38c  test    di, di
0x18000c38f  jz      short loc_18000C410
0x18000c391  mov     rdx, [rsi+40h]
0x18000c395  lea     rcx, [rsp+58h+arg_10]
0x18000c39a  mov     rdx, [rdx+70h]
0x18000c39e  call    cs:__imp_?Initialize@CService@@QEAAKPEBG@Z; CService::Initialize(ushort const *)
0x18000c3a5  nop     dword ptr [rax+rax+00h]
0x18000c3aa  mov     ecx, eax
0x18000c3ac  mov     r9d, 21Dh
0x18000c3b2  mov     edi, eax
0x18000c3b4  call    ElValidateWin32_3
0x18000c3b9  test    eax, eax
0x18000c3bb  jz      short loc_18000C3D0
0x18000c3bd  test    edi, edi
0x18000c3bf  jg      short loc_18000C3C5
0x18000c3c1  mov     ebx, edi
0x18000c3c3  jmp     short loc_18000C420
0x18000c3c5  movzx   ebx, di
0x18000c3c8  or      ebx, 80070000h
0x18000c3ce  jmp     short loc_18000C420
0x18000c3d0  lea     r8, [rsp+58h+arg_0]
0x18000c3d5  lea     rdx, aWdsserver; "WDSServer"
0x18000c3dc  lea     rcx, [rsp+58h+arg_10]
0x18000c3e1  call    cs:__imp_?GetCurrentState@CService@@QEAAKPEBGPEAK@Z; CService::GetCurrentState(ushort const *,ulong *)
0x18000c3e8  nop     dword ptr [rax+rax+00h]
0x18000c3ed  mov     ecx, eax
0x18000c3ef  mov     r9d, 224h
0x18000c3f5  mov     edi, eax
0x18000c3f7  call    ElValidateWin32_3
0x18000c3fc  test    eax, eax
0x18000c3fe  jnz     short loc_18000C3BD
0x18000c400  cmp     [rsp+58h+arg_0], 4
0x18000c405  mov     eax, ebx
0x18000c407  setz    al
0x18000c40a  mov     [rsi+80h], eax
0x18000c410  mov     eax, [rsi+80h]
0x18000c416  neg     eax
0x18000c418  sbb     r8w, r8w
0x18000c41c  mov     [r14], r8w
0x18000c420  mov     r9, rsi
0x18000c423  mov     [rsp+58h+var_38], ebx
0x18000c427  lea     r8, aCwdstransportc_15; "<- CWdsTransportConfigurationManager::g"...
0x18000c42e  mov     edx, 10000h
0x18000c433  lea     rcx, qword_18003B770
0x18000c43a  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000c441  nop     dword ptr [rax+rax+00h]
0x18000c446  lea     rcx, [rsp+58h+arg_10]
0x18000c44b  call    cs:__imp_??1CService@@QEAA@XZ; CService::~CService(void)
0x18000c452  nop     dword ptr [rax+rax+00h]
0x18000c457  lea     rcx, [rsp+58h+var_28]
0x18000c45c  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000c461  mov     eax, ebx
0x18000c463  mov     rbx, [rsp+58h+arg_8]
0x18000c468  add     rsp, 40h
0x18000c46c  pop     r14
0x18000c46e  pop     rdi
0x18000c46f  pop     rsi
0x18000c470  retn
```
