# COSInstaller::~COSInstaller(void)

- ea: `0x1800272ac`
- end: `0x180027341`
- name: `??1COSInstaller@@EEAA@XZ`
- size: `149`
- prototype: `void __fastcall(COSInstaller *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180027270`

## callees

- `0x18001c230`
- `0x1800272ac`
- `0x18002d6ec`
- `0x1800335dc`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002732e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002732e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall COSInstaller::~COSInstaller(COSInstaller *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &COSInstaller::`vftable'{for `ISusUpdateDeploy'};
  *((_QWORD *)this + 1) = &COSInstaller::`vftable'{for `ISusUpdatePostRebootResult'};
  *((_QWORD *)this + 2) = &CUHHandlerDeployBase::`vftable'{for `ISusQueryDeploymentCustomReportingData'};
  *((_QWORD *)this + 3) = &CUHHandlerDeployBase::`vftable'{for `IUpdateDeploymentHandlerInfo'};
  OSDeploymentInformationFactory::ShutdownJITCOMServer((WCHAR *)&g_OSDeploymentInformationCFForDeployment);
  CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::~CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>((char *)this + 144);
  CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::~CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>((char *)this + 120);
  v2 = *((_QWORD *)this + 14);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 14) = 0;
  }
  *((_QWORD *)this + 8) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  CUHHandlerDeployBase::~CUHHandlerDeployBase(this);
}

```

## disassembly

```asm
0x1800272ac  push    rbx
0x1800272ae  sub     rsp, 20h
0x1800272b2  mov     rbx, rcx
0x1800272b5  lea     rax, ??_7COSInstaller@@6BISusUpdateDeploy@@@; const COSInstaller::`vftable'{for `ISusUpdateDeploy'}
0x1800272bc  mov     [rcx], rax
0x1800272bf  lea     rax, ??_7COSInstaller@@6BISusUpdatePostRebootResult@@@; const COSInstaller::`vftable'{for `ISusUpdatePostRebootResult'}
0x1800272c6  mov     [rcx+8], rax
0x1800272ca  lea     rax, ??_7CUHHandlerDeployBase@@6BISusQueryDeploymentCustomReportingData@@@; const CUHHandlerDeployBase::`vftable'{for `ISusQueryDeploymentCustomReportingData'}
0x1800272d1  mov     [rcx+10h], rax
0x1800272d5  lea     rax, ??_7CUHHandlerDeployBase@@6BIUpdateDeploymentHandlerInfo@@@; const CUHHandlerDeployBase::`vftable'{for `IUpdateDeploymentHandlerInfo'}
0x1800272dc  mov     [rcx+18h], rax
0x1800272e0  lea     rcx, ?g_OSDeploymentInformationCFForDeployment@@3VOSDeploymentInformationFactory@@A; this
0x1800272e7  call    ?ShutdownJITCOMServer@OSDeploymentInformationFactory@@QEAAXXZ; OSDeploymentInformationFactory::ShutdownJITCOMServer(void)
0x1800272ec  lea     rcx, [rbx+90h]
0x1800272f3  call    ??1?$CSusArrayList@UtagDSGlobalUpdateId@@V?$CSusArrayListItemOpNoop@UtagDSGlobalUpdateId@@@@@@UEAA@XZ; CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::~CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>(void)
0x1800272f8  lea     rcx, [rbx+78h]
0x1800272fc  call    ??1?$CSusArrayList@UtagDSGlobalUpdateId@@V?$CSusArrayListItemOpNoop@UtagDSGlobalUpdateId@@@@@@UEAA@XZ; CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::~CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>(void)
0x180027301  nop
0x180027302  mov     rcx, [rbx+70h]
0x180027306  test    rcx, rcx
0x180027309  jz      short loc_18002731F
0x18002730b  mov     rax, [rcx]
0x18002730e  mov     rax, [rax+10h]
0x180027312  call    _guard_dispatch_icall
0x180027317  mov     qword ptr [rbx+70h], 0
0x18002731f  lea     rax, ??_7CSusLock@@6B@; const CSusLock::`vftable'
0x180027326  mov     [rbx+40h], rax
0x18002732a  lea     rcx, [rbx+48h]; lpCriticalSection
0x18002732e  call    cs:__imp_DeleteCriticalSection
0x180027334  mov     rcx, rbx; this
0x180027337  add     rsp, 20h
0x18002733b  pop     rbx
0x18002733c  jmp     ??1CUHHandlerDeployBase@@UEAA@XZ; CUHHandlerDeployBase::~CUHHandlerDeployBase(void)
```
