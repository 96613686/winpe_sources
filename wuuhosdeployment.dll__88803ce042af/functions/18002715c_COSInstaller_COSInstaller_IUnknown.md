# COSInstaller::COSInstaller(IUnknown *)

- ea: `0x18002715c`
- end: `0x18002725f`
- name: `??0COSInstaller@@AEAA@PEAUIUnknown@@@Z`
- size: `259`
- prototype: `COSInstaller *__fastcall(COSInstaller *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180016c30`

## callees

- `0x18000956c`
- `0x18001c06c`
- `0x18002715c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800271c4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800271c4`

## string_xrefs

- `0x180027232`: `Failed to Setup JIT COM Server for OSInstaller`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
COSInstaller *__fastcall COSInstaller::COSInstaller(COSInstaller *this, struct IUnknown *a2)
{
  *((_DWORD *)this + 12) = 0;
  *((_DWORD *)this + 9) = 7;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 8) = 1;
  *(_QWORD *)this = &COSInstaller::`vftable'{for `ISusUpdateDeploy'};
  *((_QWORD *)this + 1) = &COSInstaller::`vftable'{for `ISusUpdatePostRebootResult'};
  *((_QWORD *)this + 2) = &CUHHandlerDeployBase::`vftable'{for `ISusQueryDeploymentCustomReportingData'};
  *((_QWORD *)this + 3) = &CUHHandlerDeployBase::`vftable'{for `IUpdateDeploymentHandlerInfo'};
  *((_BYTE *)this + 56) = 0;
  *((_QWORD *)this + 8) = &CSusLock::`vftable';
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = &CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::`vftable';
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = &CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::`vftable';
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_DWORD *)this + 42) = 2;
  *((_BYTE *)this + 172) = 0;
  if ( (int)OSDeploymentInformationFactory::StartJITCOMServer((OSDeploymentInformationFactory *)&g_OSDeploymentInformationCFForDeployment) < 0 )
    WUTrace(0, 0, 4096, 2);
  return this;
}

```

## disassembly

```asm
0x18002715c  mov     [rsp+arg_0], rcx
0x180027161  push    rbx
0x180027162  sub     rsp, 30h
0x180027166  mov     rbx, rcx
0x180027169  mov     dword ptr [rcx+30h], 0
0x180027170  mov     dword ptr [rcx+24h], 7
0x180027177  mov     qword ptr [rcx+28h], 0
0x18002717f  mov     dword ptr [rcx+20h], 1
0x180027186  lea     rax, ??_7COSInstaller@@6BISusUpdateDeploy@@@; const COSInstaller::`vftable'{for `ISusUpdateDeploy'}
0x18002718d  mov     [rcx], rax
0x180027190  lea     rax, ??_7COSInstaller@@6BISusUpdatePostRebootResult@@@; const COSInstaller::`vftable'{for `ISusUpdatePostRebootResult'}
0x180027197  mov     [rcx+8], rax
0x18002719b  lea     rax, ??_7CUHHandlerDeployBase@@6BISusQueryDeploymentCustomReportingData@@@; const CUHHandlerDeployBase::`vftable'{for `ISusQueryDeploymentCustomReportingData'}
0x1800271a2  mov     [rcx+10h], rax
0x1800271a6  lea     rax, ??_7CUHHandlerDeployBase@@6BIUpdateDeploymentHandlerInfo@@@; const CUHHandlerDeployBase::`vftable'{for `IUpdateDeploymentHandlerInfo'}
0x1800271ad  mov     [rcx+18h], rax
0x1800271b1  mov     byte ptr [rcx+38h], 0
0x1800271b5  lea     rax, ??_7CSusLock@@6B@; const CSusLock::`vftable'
0x1800271bc  mov     [rcx+40h], rax
0x1800271c0  add     rcx, 48h ; 'H'; lpCriticalSection
0x1800271c4  call    cs:__imp_InitializeCriticalSection
0x1800271ca  nop
0x1800271cb  mov     qword ptr [rbx+70h], 0
0x1800271d3  lea     rax, ??_7?$CSusArrayList@UtagDSGlobalUpdateId@@V?$CSusArrayListItemOpNoop@UtagDSGlobalUpdateId@@@@@@6B@; const CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::`vftable'
0x1800271da  mov     [rbx+78h], rax
0x1800271de  mov     qword ptr [rbx+80h], 0
0x1800271e9  mov     qword ptr [rbx+88h], 0
0x1800271f4  mov     [rbx+90h], rax
0x1800271fb  mov     qword ptr [rbx+98h], 0
0x180027206  mov     qword ptr [rbx+0A0h], 0
0x180027211  mov     dword ptr [rbx+0A8h], 2
0x18002721b  mov     byte ptr [rbx+0ACh], 0
0x180027222  lea     rcx, ?g_OSDeploymentInformationCFForDeployment@@3VOSDeploymentInformationFactory@@A; this
0x180027229  call    ?StartJITCOMServer@OSDeploymentInformationFactory@@QEAAJXZ; OSDeploymentInformationFactory::StartJITCOMServer(void)
0x18002722e  test    eax, eax
0x180027230  jns     short loc_180027256
0x180027232  lea     rcx, aFailedToSetupJ; "Failed to Setup JIT COM Server for OSIn"...
0x180027239  mov     [rsp+38h+var_10], rcx
0x18002723e  mov     [rsp+38h+var_18], eax
0x180027242  xor     edx, edx
0x180027244  xor     ecx, ecx
0x180027246  lea     r9d, [rdx+2]
0x18002724a  mov     r8d, 1000h
0x180027250  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180027255  nop
0x180027256  mov     rax, rbx
0x180027259  add     rsp, 30h
0x18002725d  pop     rbx
0x18002725e  retn
```
