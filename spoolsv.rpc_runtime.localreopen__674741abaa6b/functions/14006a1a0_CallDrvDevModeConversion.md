# CallDrvDevModeConversion

- ea: `0x14006a1a0`
- end: `0x14006a931`
- name: `CallDrvDevModeConversion`
- size: `1937`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, int *, unsigned int, int)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140072664`
- `0x140072adc`

## callees

- `0x140002f40`
- `0x140004790`
- `0x1400088b0`
- `0x14000b4b0`
- `0x140010300`
- `0x140013b50`
- `0x140015290`
- `0x140015378`
- `0x140018f84`
- `0x140019838`
- `0x14001984c`
- `0x14006a1a0`
- `0x1400789f4`
- `0x140078a80`
- `0x140078b30`
- `0x14007a404`
- `0x14007a480`
- `0x14007a50c`
- `0x14007a624`
- `0x140081010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14006a26d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14006a26d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006a34e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006a39b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006a5c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006a7ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006a860`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006a87f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006a34e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006a39b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006a5c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006a7ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006a860`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006a87f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006a2fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006a3a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006a447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006a632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006a667`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006a6f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006a8a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006a2fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006a3a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006a447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006a632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006a667`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006a6f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006a8a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006a527`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006a527`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14006a37f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14006a896`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14006a37f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14006a896`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14006a330`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14006a330`

## string_xrefs

- `0x14006a28c`: `Cannot decorate printer name (%ws), decoration already in (%ws), %d`
- `0x14006a778`: `Retry using DocumentProperties completed with %d`
- `0x14006a8dc`: `Config module %ws or a driver did not uninitialize COM properly on the current thread during devmode conversion.`
- `0x14006a830`: `Devmode size (%d bytes) outside the valid limits (min: %d bytes)`
- `0x14006a8b7`: `Thread recursion (4), %d`

## pseudocode

```c
__int64 __fastcall CallDrvDevModeConversion(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        struct _devicemodeW *a3,
        LPVOID *a4,
        int *a5,
        unsigned int a6,
        int a7)
{
  const unsigned __int16 *v8; // r14
  struct sandbox::SandboxManager *v9; // rbx
  const unsigned __int16 *v10; // rdi
  __int64 v11; // rax
  unsigned int v12; // edi
  NCoreLibrary *v13; // rax
  NCoreLibrary *v14; // r13
  DWORD LastError; // ebx
  unsigned int *v16; // r15
  unsigned int v17; // eax
  __int64 v18; // rax
  struct _devicemodeW *v19; // r9
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // r9
  unsigned __int16 *v22; // rcx
  unsigned int IsValidDevmodeNo; // r8d
  unsigned int v24; // eax
  const unsigned __int16 *v25; // r9
  struct _devicemodeW *v26; // rdx
  struct _devicemodeW *v27; // rdx
  int v28; // eax
  __int64 v29; // rax
  unsigned __int64 v30; // rdx
  unsigned __int16 *v31; // rcx
  unsigned __int64 v32; // r8
  unsigned int v33; // eax
  unsigned int v34; // r14d
  const unsigned __int16 *v36; // [rsp+20h] [rbp-E8h]
  unsigned int v37[2]; // [rsp+20h] [rbp-E8h]
  unsigned int v38; // [rsp+20h] [rbp-E8h]
  unsigned int v39[2]; // [rsp+20h] [rbp-E8h]
  unsigned int v40; // [rsp+28h] [rbp-E0h]
  unsigned int v41; // [rsp+30h] [rbp-D8h]
  _BYTE v42[4]; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v43; // [rsp+44h] [rbp-C4h]
  struct sandbox::SandboxManager *v44; // [rsp+48h] [rbp-C0h] BYREF
  int v45; // [rsp+50h] [rbp-B8h]
  NCoreLibrary *v46; // [rsp+58h] [rbp-B0h]
  struct sandbox::SandboxManager *v47; // [rsp+60h] [rbp-A8h]
  __int128 v48; // [rsp+68h] [rbp-A0h] BYREF
  struct sandbox::SandboxManager *v49; // [rsp+78h] [rbp-90h]
  __int64 v50; // [rsp+80h] [rbp-88h] BYREF
  struct _devicemodeW *v53; // [rsp+120h] [rbp+18h] BYREF
  LPVOID *v54; // [rsp+128h] [rbp+20h]

  v54 = a4;
  v53 = a3;
  v8 = a2;
  v10 = a1;
  SplInitializeWinSpoolDrv(&v50);
  v48 = 0;
  NCoreLibrary::TAutoPtrCOM<sandbox::SandboxManager>::TAutoPtrCOM<sandbox::SandboxManager>(&v44);
  v9 = (struct sandbox::SandboxManager *)((__int64 (__fastcall *)(const unsigned __int16 *))g_pfnSplGetSandboxManagerByServerName)(v8);
  v47 = v9;
  NCoreLibrary::TGenericSP<PrinterPLM,NCoreLibrary::TRefPtrCOM<PrinterPLM>,PrinterPLM *,0,PrinterPLM const *>::Reset(&v44);
  v49 = v9;
  v44 = v9;
  LODWORD(v10) = sandbox::DriverConfigModuleAdapter::LoadConfigModule(
                   (sandbox::DriverConfigModuleAdapter *)&v48,
                   v9,
                   v10,
                   v8,
                   v36,
                   v40,
                   v41);
  PrvSpoolssTelemetry::WriteDbgTraceInfo(
    "CallDrvDevModeConversion",
    L"Called for devmode conversion mode 0x%08X...",
    a6);
  if ( (_DWORD)v10 )
  {
    PrvSpoolssTelemetry::WriteDbgTraceError("CallDrvDevModeConversion", L"Invalid argument, %d", (unsigned int)v10);
    goto LABEL_87;
  }
  if ( wcsstr(v8, L",DrvConvert") )
  {
    v37[0] = 87;
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "CallDrvDevModeConversion",
      L"Cannot decorate printer name (%ws), decoration already in (%ws), %d",
      v8,
      L",DrvConvert",
      *(_QWORD *)v37);
LABEL_5:
    LODWORD(v10) = 87;
    goto LABEL_87;
  }
  if ( v8 )
  {
    v11 = -1;
    do
      ++v11;
    while ( v8[v11] );
    v12 = v11 + 12;
    v13 = (NCoreLibrary *)DllAllocSplMem((unsigned int)(2 * (v11 + 12)));
    v14 = v13;
    v46 = v13;
    if ( v13 )
      NCoreLibrary::StrNCatBuff(v13, (unsigned __int16 *)v12, (unsigned int)v8, L",DrvConvert", 0);
  }
  else
  {
    v14 = (NCoreLibrary *)AllocSplStr((void *)L",DrvConvert");
    v46 = v14;
  }
  if ( !v14 )
  {
    LastError = GetLastError();
    v37[0] = LastError;
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "CallDrvDevModeConversion",
      L"Failed decorating printer name (%ws) with %ws, %d",
      v8,
      L",DrvConvert",
      *(_QWORD *)v37);
    LODWORD(v10) = LastError;
    goto LABEL_87;
  }
  if ( TlsGetValue(gdwTlsGetPrinterIndex) == (LPVOID)2 )
  {
    HeapFree(g_hSpoolssHeap, 0, v14);
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "CallDrvDevModeConversion",
      L"Possible infinite GetPrinter recursion (1), %d",
      87);
    goto LABEL_5;
  }
  if ( !TlsSetValue(gdwTlsGetPrinterIndex, (LPVOID)2) )
  {
    HeapFree(g_hSpoolssHeap, 0, v14);
    v10 = (const unsigned __int16 *)GetLastError();
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "CallDrvDevModeConversion",
      L"Possible infinite GetPrinter recursion (2), %d",
      v10);
    goto LABEL_87;
  }
  NCOMLibrary::ComLeakCleaner::ComLeakCleaner((NCOMLibrary::ComLeakCleaner *)v42);
  v16 = (unsigned int *)a5;
  if ( !a7 )
    goto LABEL_25;
  *a5 = 0;
  *a4 = 0;
  v17 = sandbox::DriverConfigModuleAdapter::DrvConvertDevMode(
          (sandbox::DriverConfigModuleAdapter *)&v48,
          (unsigned __int16 *)v14,
          v53,
          0,
          0,
          (int *)v16,
          a6);
  LODWORD(v10) = v17;
  v43 = v17;
  if ( v17 && v17 != 122 )
  {
LABEL_22:
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "CallDrvDevModeConversion",
      L"DrvConvertDevMode(fMode: 0x%08X) failed, LE: %d",
      a6,
      v17);
    goto LABEL_35;
  }
  v18 = DllAllocSplMem(*v16);
  *a4 = (LPVOID)v18;
  if ( v18 )
  {
LABEL_25:
    if ( a4 )
      v19 = (struct _devicemodeW *)*a4;
    else
      v19 = 0;
    v17 = sandbox::DriverConfigModuleAdapter::DrvConvertDevMode(
            (sandbox::DriverConfigModuleAdapter *)&v48,
            (unsigned __int16 *)v14,
            v53,
            v19,
            *v16,
            (int *)v16,
            a6);
    LODWORD(v10) = v17;
    v43 = v17;
    if ( v17 )
      goto LABEL_22;
    v21 = *v16;
    v22 = (unsigned __int16 *)*a4;
    IsValidDevmodeNo = -2147024883;
    v45 = -2147024883;
    if ( v22 )
    {
      if ( v21 >= 0x4C )
      {
        v20 = v22[34] + (unsigned __int64)v22[35];
        if ( v21 >= v20 )
        {
          IsValidDevmodeNo = SplIsValidDevmodeNoSize<_devicemodeW,unsigned short>(v22, v20, 2147942413LL);
          v45 = IsValidDevmodeNo;
        }
      }
    }
    v24 = NCoreLibrary::StatusFromHResult((NCoreLibrary *)IsValidDevmodeNo, v20);
    LODWORD(v10) = v24;
    v43 = v24;
    if ( v24 )
      PrvSpoolssTelemetry::WriteDbgTraceError(
        "CallDrvDevModeConversion",
        L"DrvConvertDevMode(fMode: 0x%08X) returned an invalid devmode, LE: %d",
        a6,
        v24);
  }
  else
  {
    LODWORD(v10) = GetLastError();
    v43 = (unsigned int)v10;
  }
LABEL_35:
  if ( !(_DWORD)v10 )
    goto LABEL_74;
  if ( a6 != 4 )
    goto LABEL_66;
  PrvSpoolssTelemetry::WriteDbgTraceInfo(
    "CallDrvDevModeConversion",
    L"Retry obtaining the default devmode using DocumentProperties...");
  v53 = 0;
  LODWORD(v8) = sandbox::DocumentPropertiesAdapter::Initialize(
                  (sandbox::DocumentPropertiesAdapter *)&v53,
                  v47,
                  v8,
                  v25,
                  v38);
  if ( a7 && *a4 )
  {
    HeapFree(g_hSpoolssHeap, 0, *a4);
    *a4 = 0;
  }
  *v16 = 0;
  sandbox::DocumentPropertiesAdapter::DocumentPropertiesW((sandbox::DocumentPropertiesAdapter *)&v53, v26, 0, 0, 0);
  if ( !(_DWORD)v8 )
  {
    if ( !a7 )
      goto LABEL_48;
    v28 = sandbox::DocumentPropertiesAdapter::DocumentPropertiesW(
            (sandbox::DocumentPropertiesAdapter *)&v53,
            v27,
            0,
            0,
            0);
    *v16 = v28;
    if ( v28 <= 0 )
    {
      v8 = (const unsigned __int16 *)GetLastError();
      PrvSpoolssTelemetry::WriteDbgTraceError(
        "CallDrvDevModeConversion",
        L"DocumentProperties(%ws, 0) failed, LE: %d",
        a2,
        v8);
      if ( !(_DWORD)v8 )
        LODWORD(v10) = 8;
      goto LABEL_48;
    }
    v29 = DllAllocSplMem((unsigned int)v28);
    *a4 = (LPVOID)v29;
    if ( v29 )
    {
LABEL_48:
      if ( !(_DWORD)v8 )
      {
        if ( (int)*v16 <= 0 || !*a4 )
        {
          LODWORD(v8) = 87;
          v39[0] = 87;
          PrvSpoolssTelemetry::WriteDbgTraceError(
            "CallDrvDevModeConversion",
            L"Invalid output devmode buffer argument(s) (%p, %d bytes), LE: %d",
            *a4,
            *v16,
            *(_QWORD *)v39);
        }
        if ( !(_DWORD)v8 )
        {
          if ( (int)sandbox::DocumentPropertiesAdapter::DocumentPropertiesW(
                      (sandbox::DocumentPropertiesAdapter *)&v53,
                      v27,
                      2u,
                      (struct _devicemodeW *)*a4,
                      *v16) < 0 )
          {
            v8 = (const unsigned __int16 *)GetLastError();
            PrvSpoolssTelemetry::WriteDbgTraceError(
              "CallDrvDevModeConversion",
              L"DocumentProperties(%ws, DM_OUT_BUFFER) failed, LE: %d",
              a2,
              v8);
          }
          if ( !(_DWORD)v8 )
          {
            v31 = (unsigned __int16 *)*a4;
            if ( *a4 && (v32 = *v16, v32 >= 0x4C) && (v30 = v31[34] + (unsigned __int64)v31[35], v32 >= v30) )
              v33 = SplIsValidDevmodeNoSize<_devicemodeW,unsigned short>(v31, v30, v32);
            else
              v33 = -2147024883;
            LODWORD(v8) = NCoreLibrary::StatusFromHResult((NCoreLibrary *)v33, v30);
            if ( (_DWORD)v8 )
              PrvSpoolssTelemetry::WriteDbgTraceError(
                "CallDrvDevModeConversion",
                L"DocumentProperties(DM_OUT_BUFFER) returned an invalid devmode, LE: %d",
                (unsigned int)v10);
          }
        }
      }
      goto LABEL_63;
    }
    v8 = (const unsigned __int16 *)GetLastError();
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "CallDrvDevModeConversion",
      L"Failed to allocate %d bytes for devmode, LE: %d",
      *v16,
      v8);
    if ( !(_DWORD)v8 )
    {
      LODWORD(v8) = 8;
      goto LABEL_48;
    }
  }
LABEL_63:
  PrvSpoolssTelemetry::WriteDbgTraceInfo(
    "CallDrvDevModeConversion",
    L"Retry using DocumentProperties completed with %d",
    (unsigned int)v8);
  if ( !(_DWORD)v8 )
    LODWORD(v10) = 0;
  sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter((sandbox::DriverConfigModuleAdapter *)&v53);
LABEL_66:
  if ( !(_DWORD)v10 )
  {
LABEL_74:
    v34 = *((unsigned __int16 *)*a4 + 34) + *((unsigned __int16 *)*a4 + 35);
    if ( *v16 == v34 )
    {
      v34 = *v16;
    }
    else
    {
      PrvSpoolssTelemetry::WriteDbgTraceError(
        "CallDrvDevModeConversion",
        L"Driver reports out devmode size is %d bytes instead of required %d bytes, adjusted",
        *v16,
        v34);
      *v16 = v34;
    }
    if ( v34 < 0x48 )
    {
      PrvSpoolssTelemetry::WriteDbgTraceError(
        "CallDrvDevModeConversion",
        L"Devmode size (%d bytes) outside the valid limits (min: %d bytes)",
        v34);
      LODWORD(v10) = 87;
      if ( a7 && *a4 )
      {
        HeapFree(g_hSpoolssHeap, 0, *a4);
        *a4 = 0;
      }
      *v16 = 0;
    }
    goto LABEL_82;
  }
  if ( a7 && *a4 )
  {
    HeapFree(g_hSpoolssHeap, 0, *a4);
    *a4 = 0;
  }
  *v16 = 0;
  if ( (_DWORD)v10 != 122 )
    PrvSpoolssTelemetry::WriteDbgTraceError("CallDrvDevModeConversion", L"Failing with %d", (unsigned int)v10);
LABEL_82:
  HeapFree(g_hSpoolssHeap, 0, v14);
  if ( !TlsSetValue(gdwTlsGetPrinterIndex, (LPVOID)1) )
  {
    v10 = (const unsigned __int16 *)GetLastError();
    PrvSpoolssTelemetry::WriteDbgTraceError("CallDrvDevModeConversion", L"Thread recursion (4), %d", v10);
  }
  if ( (unsigned int)NCOMLibrary::ComLeakCleaner::Cleanup((NCOMLibrary::ComLeakCleaner *)v42) )
    PrvSpoolssTelemetry::WriteDbgTraceInfo(
      "CallDrvDevModeConversion",
      L"Config module %ws or a driver did not uninitialize COM properly on the current thread during devmode conversion.",
      a1);
  PrvSpoolssTelemetry::WriteDbgTraceInfo("CallDrvDevModeConversion", L"Returning %d", (unsigned int)v10);
  NCOMLibrary::ComLeakCleaner::Cleanup((NCOMLibrary::ComLeakCleaner *)v42);
LABEL_87:
  NCoreLibrary::TAutoPtrCOM<sandbox::SandboxManager>::~TAutoPtrCOM<sandbox::SandboxManager>(&v44);
  sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter((sandbox::DriverConfigModuleAdapter *)&v48);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14006a1a0  mov     rax, rsp
0x14006a1a3  mov     [rax+20h], r9
0x14006a1a7  mov     [rax+18h], r8
0x14006a1ab  mov     [rax+10h], rdx
0x14006a1af  mov     [rax+8], rcx
0x14006a1b3  push    rbx
0x14006a1b4  push    rsi
0x14006a1b5  push    rdi
0x14006a1b6  push    r12
0x14006a1b8  push    r13
0x14006a1ba  push    r14
0x14006a1bc  push    r15
0x14006a1be  sub     rsp, 0D0h
0x14006a1c5  mov     r12, r9
0x14006a1c8  mov     r14, rdx
0x14006a1cb  mov     rdi, rcx
0x14006a1ce  lea     rcx, [rax-88h]
0x14006a1d5  call    SplInitializeWinSpoolDrv
0x14006a1da  xorps   xmm0, xmm0
0x14006a1dd  movdqu  [rsp+108h+var_A0], xmm0
0x14006a1e3  lea     rcx, [rsp+108h+var_C0]
0x14006a1e8  call    ??0?$TAutoPtrCOM@VSandboxManager@sandbox@@@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TAutoPtrCOM<sandbox::SandboxManager>::TAutoPtrCOM<sandbox::SandboxManager>(void)
0x14006a1ed  mov     rcx, r14
0x14006a1f0  mov     rax, cs:?g_pfnSplGetSandboxManagerByServerName@@3P6APEAXPEBG@ZEA; void * (*g_pfnSplGetSandboxManagerByServerName)(ushort const *)
0x14006a1f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a1fc  mov     rbx, rax
0x14006a1ff  mov     [rsp+108h+var_A8], rax
0x14006a204  lea     rcx, [rsp+108h+var_C0]
0x14006a209  call    ?Reset@?$TGenericSP@VPrinterPLM@@V?$TRefPtrCOM@VPrinterPLM@@@NCoreLibrary@@PEAV1@$0A@PEBV1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<PrinterPLM,NCoreLibrary::TRefPtrCOM<PrinterPLM>,PrinterPLM *,0,PrinterPLM const *>::Reset(void)
0x14006a20e  mov     [rsp+108h+var_90], rbx
0x14006a213  mov     [rsp+108h+var_C0], rbx
0x14006a218  mov     r9, r14; unsigned __int16 *
0x14006a21b  mov     r8, rdi; unsigned __int16 *
0x14006a21e  mov     rdx, rbx; struct sandbox::SandboxManager *
0x14006a221  lea     rcx, [rsp+108h+var_A0]; this
0x14006a226  call    ?LoadConfigModule@DriverConfigModuleAdapter@sandbox@@QEAAKPEAVSandboxManager@2@PEBG11KK@Z; sandbox::DriverConfigModuleAdapter::LoadConfigModule(sandbox::SandboxManager *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x14006a22b  mov     edi, eax
0x14006a22d  mov     r8d, [rsp+108h+arg_28]
0x14006a235  lea     rdx, aCalledForDevmo; "Called for devmode conversion mode 0x%0"...
0x14006a23c  lea     rsi, aCalldrvdevmode; "CallDrvDevModeConversion"
0x14006a243  mov     rcx, rsi; char *
0x14006a246  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006a24b  xor     ebx, ebx
0x14006a24d  test    edi, edi
0x14006a24f  jz      short loc_14006A260
0x14006a251  mov     r8d, edi
0x14006a254  lea     rdx, aInvalidArgumen; "Invalid argument, %d"
0x14006a25b  jmp     loc_14006A3BF
0x14006a260  lea     r15, gszDrvConvert; ",DrvConvert"
0x14006a267  mov     rdx, r15; SubStr
0x14006a26a  mov     rcx, r14; Str
0x14006a26d  call    cs:__imp_wcsstr
0x14006a274  nop     dword ptr [rax+rax+00h]
0x14006a279  test    rax, rax
0x14006a27c  jz      short loc_14006A2A5
0x14006a27e  mov     [rsp+108h+var_E8], 57h ; 'W'
0x14006a286  mov     r9, r15
0x14006a289  mov     r8, r14
0x14006a28c  lea     rdx, aCannotDecorate; "Cannot decorate printer name (%ws), dec"...
0x14006a293  mov     rcx, rsi; char *
0x14006a296  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006a29b  mov     edi, 57h ; 'W'
0x14006a2a0  jmp     loc_14006A907
0x14006a2a5  test    r14, r14
0x14006a2a8  jz      short loc_14006A2E7
0x14006a2aa  or      rax, 0FFFFFFFFFFFFFFFFh
0x14006a2ae  inc     rax
0x14006a2b1  cmp     [r14+rax*2], bx
0x14006a2b6  jnz     short loc_14006A2AE
0x14006a2b8  lea     edi, [rax+0Ch]
0x14006a2bb  lea     ecx, [rdi+rdi]; dwBytes
0x14006a2be  call    DllAllocSplMem
0x14006a2c3  mov     r13, rax
0x14006a2c6  mov     [rsp+108h+var_B0], rax
0x14006a2cb  test    rax, rax
0x14006a2ce  jz      short loc_14006A2F7
0x14006a2d0  mov     qword ptr [rsp+108h+var_E8], rbx
0x14006a2d5  mov     r9, r15
0x14006a2d8  mov     r8, r14; unsigned int
0x14006a2db  mov     edx, edi; unsigned __int16 *
0x14006a2dd  mov     rcx, rax; this
0x14006a2e0  call    ?StrNCatBuff@NCoreLibrary@@YAJPEAGIZZ; NCoreLibrary::StrNCatBuff(ushort *,uint,...)
0x14006a2e5  jmp     short loc_14006A2F7
0x14006a2e7  mov     rcx, r15; Src
0x14006a2ea  call    AllocSplStr
0x14006a2ef  mov     r13, rax
0x14006a2f2  mov     [rsp+108h+var_B0], rax
0x14006a2f7  test    r13, r13
0x14006a2fa  jnz     short loc_14006A32A
0x14006a2fc  call    cs:__imp_GetLastError
0x14006a303  nop     dword ptr [rax+rax+00h]
0x14006a308  mov     ebx, eax
0x14006a30a  mov     [rsp+108h+var_E8], eax
0x14006a30e  mov     r9, r15
0x14006a311  mov     r8, r14
0x14006a314  lea     rdx, aFailedDecorati; "Failed decorating printer name (%ws) wi"...
0x14006a31b  mov     rcx, rsi; char *
0x14006a31e  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006a323  mov     edi, ebx
0x14006a325  jmp     loc_14006A907
0x14006a32a  mov     ecx, cs:?gdwTlsGetPrinterIndex@@3KA; dwTlsIndex
0x14006a330  call    cs:__imp_TlsGetValue
0x14006a337  nop     dword ptr [rax+rax+00h]
0x14006a33c  cmp     rax, 2
0x14006a340  jnz     short loc_14006A374
0x14006a342  mov     r8, r13; lpMem
0x14006a345  xor     edx, edx; dwFlags
0x14006a347  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14006a34e  call    cs:__imp_HeapFree
0x14006a355  nop     dword ptr [rax+rax+00h]
0x14006a35a  mov     r8d, 57h ; 'W'
0x14006a360  lea     rdx, aPossibleInfini; "Possible infinite GetPrinter recursion "...
0x14006a367  mov     rcx, rsi; char *
0x14006a36a  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006a36f  jmp     loc_14006A29B
0x14006a374  mov     edx, 2; lpTlsValue
0x14006a379  mov     ecx, cs:?gdwTlsGetPrinterIndex@@3KA; dwTlsIndex
0x14006a37f  call    cs:__imp_TlsSetValue
0x14006a386  nop     dword ptr [rax+rax+00h]
0x14006a38b  test    eax, eax
0x14006a38d  jnz     short loc_14006A3CC
0x14006a38f  mov     r8, r13; lpMem
0x14006a392  xor     edx, edx; dwFlags
0x14006a394  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14006a39b  call    cs:__imp_HeapFree
0x14006a3a2  nop     dword ptr [rax+rax+00h]
0x14006a3a7  call    cs:__imp_GetLastError
0x14006a3ae  nop     dword ptr [rax+rax+00h]
0x14006a3b3  mov     edi, eax
0x14006a3b5  mov     r8d, eax
0x14006a3b8  lea     rdx, aPossibleInfini_0; "Possible infinite GetPrinter recursion "...
0x14006a3bf  mov     rcx, rsi; char *
0x14006a3c2  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006a3c7  jmp     loc_14006A907
0x14006a3cc  lea     rcx, [rsp+108h+var_C8]; this
0x14006a3d1  call    ??0ComLeakCleaner@NCOMLibrary@@QEAA@XZ; NCOMLibrary::ComLeakCleaner::ComLeakCleaner(void)
0x14006a3d6  nop
0x14006a3d7  mov     r15, [rsp+108h+arg_20]
0x14006a3df  cmp     [rsp+108h+arg_30], ebx
0x14006a3e6  jz      short loc_14006A45E
0x14006a3e8  mov     [r15], ebx
0x14006a3eb  mov     [r12], rbx
0x14006a3ef  mov     eax, [rsp+108h+arg_28]
0x14006a3f6  mov     [rsp+108h+var_D8], eax; unsigned int
0x14006a3fa  mov     [rsp+108h+var_E0], r15; int *
0x14006a3ff  mov     [rsp+108h+var_E8], ebx; unsigned int
0x14006a403  xor     r9d, r9d; struct _devicemodeW *
0x14006a406  mov     r8, [rsp+108h+arg_10]; struct _devicemodeW *
0x14006a40e  mov     rdx, r13; unsigned __int16 *
0x14006a411  lea     rcx, [rsp+108h+var_A0]; this
0x14006a416  call    ?DrvConvertDevMode@DriverConfigModuleAdapter@sandbox@@QEAAKPEAGPEAU_devicemodeW@@1KPEAJK@Z; sandbox::DriverConfigModuleAdapter::DrvConvertDevMode(ushort *,_devicemodeW *,_devicemodeW *,ulong,long *,ulong)
0x14006a41b  mov     edi, eax
0x14006a41d  mov     [rsp+108h+var_C4], eax
0x14006a421  test    eax, eax
0x14006a423  jz      short loc_14006A436
0x14006a425  cmp     eax, 7Ah ; 'z'
0x14006a428  jz      short loc_14006A436
0x14006a42a  lea     rdx, aDrvconvertdevm_0; "DrvConvertDevMode(fMode: 0x%08X) failed"...
0x14006a431  jmp     loc_14006A4F4
0x14006a436  mov     ecx, [r15]; dwBytes
0x14006a439  call    DllAllocSplMem
0x14006a43e  mov     [r12], rax
0x14006a442  test    rax, rax
0x14006a445  jnz     short loc_14006A45E
0x14006a447  call    cs:__imp_GetLastError
0x14006a44e  nop     dword ptr [rax+rax+00h]
0x14006a453  mov     edi, eax
0x14006a455  mov     [rsp+108h+var_C4], eax
0x14006a459  jmp     loc_14006A507
0x14006a45e  mov     ecx, [r15]
0x14006a461  test    r12, r12
0x14006a464  jz      short loc_14006A46C
0x14006a466  mov     r9, [r12]
0x14006a46a  jmp     short loc_14006A46F
0x14006a46c  mov     r9, rbx; struct _devicemodeW *
0x14006a46f  mov     eax, [rsp+108h+arg_28]
0x14006a476  mov     [rsp+108h+var_D8], eax; unsigned int
0x14006a47a  mov     [rsp+108h+var_E0], r15; int *
0x14006a47f  mov     [rsp+108h+var_E8], ecx; unsigned int
0x14006a483  mov     r8, [rsp+108h+arg_10]; struct _devicemodeW *
0x14006a48b  mov     rdx, r13; unsigned __int16 *
0x14006a48e  lea     rcx, [rsp+108h+var_A0]; this
0x14006a493  call    ?DrvConvertDevMode@DriverConfigModuleAdapter@sandbox@@QEAAKPEAGPEAU_devicemodeW@@1KPEAJK@Z; sandbox::DriverConfigModuleAdapter::DrvConvertDevMode(ushort *,_devicemodeW *,_devicemodeW *,ulong,long *,ulong)
0x14006a498  mov     edi, eax
0x14006a49a  mov     [rsp+108h+var_C4], eax
0x14006a49e  test    eax, eax
0x14006a4a0  jnz     short loc_14006A42A
0x14006a4a2  mov     r9d, [r15]
0x14006a4a5  mov     rcx, [r12]
0x14006a4a9  mov     r8d, 8007000Dh
0x14006a4af  mov     [rsp+108h+var_B8], r8d
0x14006a4b4  test    rcx, rcx
0x14006a4b7  jz      short loc_14006A4DB
0x14006a4b9  cmp     r9, 4Ch ; 'L'
0x14006a4bd  jb      short loc_14006A4DB
0x14006a4bf  movzx   edx, word ptr [rcx+46h]
0x14006a4c3  movzx   eax, word ptr [rcx+44h]
0x14006a4c7  add     rdx, rax
0x14006a4ca  cmp     r9, rdx
0x14006a4cd  jb      short loc_14006A4DB
0x14006a4cf  call    ??$SplIsValidDevmodeNoSize@U_devicemodeW@@G@@YAJPEAU_devicemodeW@@@Z; SplIsValidDevmodeNoSize<_devicemodeW,ushort>(_devicemodeW *)
0x14006a4d4  mov     r8d, eax
0x14006a4d7  mov     [rsp+108h+var_B8], eax
0x14006a4db  mov     ecx, r8d; this
0x14006a4de  call    ?StatusFromHResult@NCoreLibrary@@YAKJ@Z; NCoreLibrary::StatusFromHResult(long)
0x14006a4e3  mov     edi, eax
0x14006a4e5  mov     [rsp+108h+var_C4], eax
0x14006a4e9  test    eax, eax
0x14006a4eb  jz      short loc_14006A507
0x14006a4ed  lea     rdx, aDrvconvertdevm; "DrvConvertDevMode(fMode: 0x%08X) return"...
0x14006a4f4  mov     r9d, eax
0x14006a4f7  mov     r8d, [rsp+108h+arg_28]
0x14006a4ff  mov     rcx, rsi; char *
0x14006a502  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006a507  jmp     short loc_14006A563
0x14006a509  mov     edi, eax
0x14006a50b  mov     [rsp+108h+var_C4], eax
0x14006a50f  mov     r8d, eax
0x14006a512  lea     rdx, aExceptionFromD; "Exception from driver, LE: %d"
0x14006a519  lea     rcx, aCalldrvdevmode; "CallDrvDevModeConversion"
0x14006a520  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006a525  mov     ecx, edi; dwErrCode
0x14006a527  call    cs:__imp_SetLastError
0x14006a52e  nop     dword ptr [rax+rax+00h]
0x14006a533  lea     rsi, aCalldrvdevmode; "CallDrvDevModeConversion"
0x14006a53a  xor     ebx, ebx
0x14006a53c  mov     r15, [rsp+108h+arg_20]
0x14006a544  mov     r12, [rsp+108h+arg_18]
0x14006a54c  mov     r13, [rsp+108h+var_B0]
0x14006a551  mov     rax, [rsp+108h+var_90]
0x14006a556  mov     [rsp+108h+var_A8], rax
0x14006a55b  mov     r14, [rsp+108h+arg_8]
0x14006a563  test    edi, edi
0x14006a565  jz      loc_14006A7F0
0x14006a56b  cmp     [rsp+108h+arg_28], 4
0x14006a573  jnz     loc_14006A79A
0x14006a579  lea     rdx, aRetryObtaining; "Retry obtaining the default devmode usi"...
0x14006a580  mov     rcx, rsi; char *
0x14006a583  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006a588  mov     [rsp+108h+arg_10], rbx
0x14006a590  mov     r8, r14; unsigned __int16 *
0x14006a593  mov     rdx, [rsp+108h+var_A8]; struct sandbox::SandboxManager *
0x14006a598  lea     rcx, [rsp+108h+arg_10]; this
0x14006a5a0  call    ?Initialize@DocumentPropertiesAdapter@sandbox@@QEAAKPEAVSandboxManager@2@PEBG1K@Z; sandbox::DocumentPropertiesAdapter::Initialize(sandbox::SandboxManager *,ushort const *,ushort const *,ulong)
0x14006a5a5  mov     r14d, eax
0x14006a5a8  cmp     [rsp+108h+arg_30], ebx
0x14006a5af  jz      short loc_14006A5D4
0x14006a5b1  cmp     [r12], rbx
0x14006a5b5  jz      short loc_14006A5D4
0x14006a5b7  mov     r8, [r12]; lpMem
0x14006a5bb  xor     edx, edx; dwFlags
0x14006a5bd  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14006a5c4  call    cs:__imp_HeapFree
0x14006a5cb  nop     dword ptr [rax+rax+00h]
0x14006a5d0  mov     [r12], rbx
0x14006a5d4  mov     [r15], ebx
0x14006a5d7  mov     [rsp+108h+var_E8], ebx; unsigned int
0x14006a5db  xor     r9d, r9d; struct _devicemodeW *
0x14006a5de  xor     r8d, r8d; unsigned int
0x14006a5e1  lea     rcx, [rsp+108h+arg_10]; this
0x14006a5e9  call    ?DocumentPropertiesW@DocumentPropertiesAdapter@sandbox@@QEAAJPEAU_devicemodeW@@K0K@Z; sandbox::DocumentPropertiesAdapter::DocumentPropertiesW(_devicemodeW *,ulong,_devicemodeW *,ulong)
0x14006a5ee  test    r14d, r14d
0x14006a5f1  jnz     loc_14006A775
0x14006a5f7  cmp     [rsp+108h+arg_30], ebx
0x14006a5fe  jz      loc_14006A69B
0x14006a604  mov     [rsp+108h+var_E8], ebx; unsigned int
0x14006a608  xor     r9d, r9d; struct _devicemodeW *
0x14006a60b  xor     r8d, r8d; unsigned int
0x14006a60e  lea     rcx, [rsp+108h+arg_10]; this
0x14006a616  call    ?DocumentPropertiesW@DocumentPropertiesAdapter@sandbox@@QEAAJPEAU_devicemodeW@@K0K@Z; sandbox::DocumentPropertiesAdapter::DocumentPropertiesW(_devicemodeW *,ulong,_devicemodeW *,ulong)
0x14006a61b  mov     [r15], eax
0x14006a61e  test    eax, eax
0x14006a620  jle     short loc_14006A667
0x14006a622  mov     ecx, eax; dwBytes
0x14006a624  call    DllAllocSplMem
0x14006a629  mov     [r12], rax
0x14006a62d  test    rax, rax
0x14006a630  jnz     short loc_14006A69B
0x14006a632  call    cs:__imp_GetLastError
0x14006a639  nop     dword ptr [rax+rax+00h]
0x14006a63e  mov     r14d, eax
0x14006a641  mov     r9d, eax
0x14006a644  mov     r8d, [r15]
0x14006a647  lea     rdx, aFailedToAlloca_5; "Failed to allocate %d bytes for devmode"...
0x14006a64e  mov     rcx, rsi; char *
0x14006a651  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006a656  test    r14d, r14d
0x14006a659  jnz     loc_14006A775
0x14006a65f  mov     r14d, 8
0x14006a665  jmp     short loc_14006A69B
0x14006a667  call    cs:__imp_GetLastError
0x14006a66e  nop     dword ptr [rax+rax+00h]
0x14006a673  mov     r14d, eax
0x14006a676  mov     r9d, eax
0x14006a679  mov     r8, [rsp+108h+arg_8]
0x14006a681  lea     rdx, aDocumentproper_1; "DocumentProperties(%ws, 0) failed, LE: "...
0x14006a688  mov     rcx, rsi; char *
0x14006a68b  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006a690  mov     eax, 8
0x14006a695  test    r14d, r14d
  ... truncated ...
```
