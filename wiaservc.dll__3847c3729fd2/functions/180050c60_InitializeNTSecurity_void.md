# InitializeNTSecurity(void)

- ea: `0x180050c60`
- end: `0x180050d0c`
- name: `?InitializeNTSecurity@@YAHXZ`
- size: `172`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800459d8`

## callees

- `0x18000c7c0`
- `0x18000da10`
- `0x18000dd00`
- `0x18004f008`
- `0x18005022c`
- `0x1800508a8`
- `0x18005096c`
- `0x180050c60`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180050cf1`
- `KERNEL32!GetLastError` at `0x180050cf1`
- `KERNEL32!CloseHandle` at `0x180050ca9`
- `KERNEL32!CloseHandle` at `0x180050ca9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180050c90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180050c90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180050caf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180050caf`

## string_xrefs

- `0x180050c69`: `InitializeNTSecurity`
- `0x180050c75`: `InitializeNTSecurity`

## pseudocode

```c
_BOOL8 InitializeNTSecurity(void)
{
  struct tagWiaTraceData_Type *v0; // rax
  char *v1; // rdx
  unsigned int v2; // r8d
  HANDLE CurrentProcess; // rax
  void *v4; // rbx
  HANDLE CurrentThread; // rax
  __int64 v6; // rdx
  void *v7; // r8
  void *v8; // r9
  BOOL v9; // ebx
  unsigned int v11; // [rsp+20h] [rbp-68h]
  _BYTE v12[88]; // [rsp+30h] [rbp-58h] BYREF

  v0 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("InitializeNTSecurity");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v12, v1, v2, "InitializeNTSecurity", v11, v0);
  CreateWellKnownSids();
  CurrentProcess = GetCurrentProcess();
  v4 = CurrentProcess;
  if ( CurrentProcess )
  {
    AdjustSecurityDescriptorForSync(CurrentProcess);
    CloseHandle(v4);
    CurrentThread = GetCurrentThread();
    AdjustSecurityDescriptorForSync(CurrentThread);
    LOBYTE(v6) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloScanner>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AppSiloScanner>::GetImpl'::`2'::impl,
      v6);
    v9 = CreateSecurityObject((struct ACE_DATA *)&qword_1800AE2B0, 8u, v7, v8) == 0;
    CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v12);
    return v9;
  }
  else
  {
    GetLastError();
    CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v12);
    return 0;
  }
}

```

## disassembly

```asm
0x180050c60  push    rbx
0x180050c62  sub     rsp, 80h
0x180050c69  lea     rcx, aInitializentse; "InitializeNTSecurity"
0x180050c70  call    WiaTrace_Trace
0x180050c75  lea     r9, aInitializentse; "InitializeNTSecurity"
0x180050c7c  mov     [rsp+88h+var_60], rax; void **
0x180050c81  lea     rcx, [rsp+88h+var_58]; this
0x180050c86  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180050c8b  call    ?CreateWellKnownSids@@YAKXZ; CreateWellKnownSids(void)
0x180050c90  call    cs:__imp_GetCurrentProcess
0x180050c96  mov     rbx, rax
0x180050c99  test    rax, rax
0x180050c9c  jz      short loc_180050CF1
0x180050c9e  mov     rcx, rax; Handle
0x180050ca1  call    ?AdjustSecurityDescriptorForSync@@YAHPEAX@Z; AdjustSecurityDescriptorForSync(void *)
0x180050ca6  mov     rcx, rbx; hObject
0x180050ca9  call    cs:__imp_CloseHandle
0x180050caf  call    cs:__imp_GetCurrentThread
0x180050cb5  mov     rcx, rax; Handle
0x180050cb8  call    ?AdjustSecurityDescriptorForSync@@YAHPEAX@Z; AdjustSecurityDescriptorForSync(void *)
0x180050cbd  mov     dl, 1
0x180050cbf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloScanner@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloScanner@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloScanner> `wil::Feature<__WilFeatureTraits_Feature_AppSiloScanner>::GetImpl(void)'::`2'::impl
0x180050cc6  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloScanner@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloScanner>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180050ccb  mov     edx, 8; unsigned int
0x180050cd0  lea     rcx, qword_1800AE2B0; struct ACE_DATA *
0x180050cd7  call    ?CreateSecurityObject@@YAKPEAUACE_DATA@@KPEAX1PEAU_GENERIC_MAPPING@@PEAPEAX@Z; CreateSecurityObject(ACE_DATA *,ulong,void *,void *,_GENERIC_MAPPING *,void * *)
0x180050cdc  xor     ebx, ebx
0x180050cde  lea     rcx, [rsp+88h+var_58]; this
0x180050ce3  test    eax, eax
0x180050ce5  setz    bl
0x180050ce8  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180050ced  mov     eax, ebx
0x180050cef  jmp     short loc_180050D03
0x180050cf1  call    cs:__imp_GetLastError
0x180050cf7  lea     rcx, [rsp+88h+var_58]; this
0x180050cfc  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180050d01  xor     eax, eax
0x180050d03  add     rsp, 80h
0x180050d0a  pop     rbx
0x180050d0b  retn
```
