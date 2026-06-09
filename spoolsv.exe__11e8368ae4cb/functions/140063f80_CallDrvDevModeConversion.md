# CallDrvDevModeConversion

- ea: `0x140063f80`
- end: `0x1400646a0`
- name: `CallDrvDevModeConversion`
- size: `1824`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, int *, unsigned int, int)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14006ba60`
- `0x14006be78`

## callees

- `0x140002b00`
- `0x1400041c0`
- `0x140007cc0`
- `0x14000a620`
- `0x14000f5f0`
- `0x140012920`
- `0x140013fe8`
- `0x1400140cc`
- `0x140017ae0`
- `0x1400182fc`
- `0x140018310`
- `0x140063f80`
- `0x140071a24`
- `0x140071aac`
- `0x140071b48`
- `0x140073328`
- `0x14007339c`
- `0x140073424`
- `0x140073538`
- `0x14007a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14006404d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14006404d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006411c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006415d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006436e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006454c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400645e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140064601`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006411c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006415d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006436e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006454c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400645e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140064601`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400640d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064163`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400641fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400643d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064491`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006461c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400640d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064163`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400641fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400643d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064491`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006461c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400642d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400642d7`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140064147`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140064612`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140064147`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140064612`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140064104`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140064104`

## string_xrefs

- `0x140064066`: `Cannot decorate printer name (%ws), decoration already in (%ws), %d`
- `0x14006450a`: `Retry using DocumentProperties completed with %d`
- `0x140064627`: `Thread recursion (4), %d`
- `0x14006464c`: `Config module %ws or a driver did not uninitialize COM properly on the current thread during devmode conversion.`
- `0x1400645b8`: `Devmode size (%d bytes) outside the valid limits (min: %d bytes)`

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
0x140063f80  mov     rax, rsp
0x140063f83  mov     [rax+20h], r9
0x140063f87  mov     [rax+18h], r8
0x140063f8b  mov     [rax+10h], rdx
0x140063f8f  mov     [rax+8], rcx
0x140063f93  push    rbx
0x140063f94  push    rsi
0x140063f95  push    rdi
0x140063f96  push    r12
0x140063f98  push    r13
0x140063f9a  push    r14
0x140063f9c  push    r15
0x140063f9e  sub     rsp, 0D0h
0x140063fa5  mov     r12, r9
0x140063fa8  mov     r14, rdx
0x140063fab  mov     rdi, rcx
0x140063fae  lea     rcx, [rax-88h]
0x140063fb5  call    SplInitializeWinSpoolDrv
0x140063fba  xorps   xmm0, xmm0
0x140063fbd  movdqu  [rsp+108h+var_A0], xmm0
0x140063fc3  lea     rcx, [rsp+108h+var_C0]
0x140063fc8  call    ??0?$TAutoPtrCOM@VSandboxManager@sandbox@@@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TAutoPtrCOM<sandbox::SandboxManager>::TAutoPtrCOM<sandbox::SandboxManager>(void)
0x140063fcd  mov     rcx, r14
0x140063fd0  mov     rax, cs:?g_pfnSplGetSandboxManagerByServerName@@3P6APEAXPEBG@ZEA; void * (*g_pfnSplGetSandboxManagerByServerName)(ushort const *)
0x140063fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140063fdc  mov     rbx, rax
0x140063fdf  mov     [rsp+108h+var_A8], rax
0x140063fe4  lea     rcx, [rsp+108h+var_C0]
0x140063fe9  call    ?Reset@?$TGenericSP@VPrinterPLM@@V?$TRefPtrCOM@VPrinterPLM@@@NCoreLibrary@@PEAV1@$0A@PEBV1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<PrinterPLM,NCoreLibrary::TRefPtrCOM<PrinterPLM>,PrinterPLM *,0,PrinterPLM const *>::Reset(void)
0x140063fee  mov     [rsp+108h+var_90], rbx
0x140063ff3  mov     [rsp+108h+var_C0], rbx
0x140063ff8  mov     r9, r14; unsigned __int16 *
0x140063ffb  mov     r8, rdi; unsigned __int16 *
0x140063ffe  mov     rdx, rbx; struct sandbox::SandboxManager *
0x140064001  lea     rcx, [rsp+108h+var_A0]; this
0x140064006  call    ?LoadConfigModule@DriverConfigModuleAdapter@sandbox@@QEAAKPEAVSandboxManager@2@PEBG11KK@Z; sandbox::DriverConfigModuleAdapter::LoadConfigModule(sandbox::SandboxManager *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x14006400b  mov     edi, eax
0x14006400d  mov     r8d, [rsp+108h+arg_28]
0x140064015  lea     rdx, aCalledForDevmo; "Called for devmode conversion mode 0x%0"...
0x14006401c  lea     rsi, aCalldrvdevmode; "CallDrvDevModeConversion"
0x140064023  mov     rcx, rsi; char *
0x140064026  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006402b  xor     ebx, ebx
0x14006402d  test    edi, edi
0x14006402f  jz      short loc_140064040
0x140064031  mov     r8d, edi
0x140064034  lea     rdx, aInvalidArgumen; "Invalid argument, %d"
0x14006403b  jmp     loc_140064175
0x140064040  lea     r15, gszDrvConvert; ",DrvConvert"
0x140064047  mov     rdx, r15; SubStr
0x14006404a  mov     rcx, r14; Str
0x14006404d  call    cs:__imp_wcsstr
0x140064053  test    rax, rax
0x140064056  jz      short loc_14006407F
0x140064058  mov     [rsp+108h+var_E8], 57h ; 'W'
0x140064060  mov     r9, r15
0x140064063  mov     r8, r14
0x140064066  lea     rdx, aCannotDecorate; "Cannot decorate printer name (%ws), dec"...
0x14006406d  mov     rcx, rsi; char *
0x140064070  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140064075  mov     edi, 57h ; 'W'
0x14006407a  jmp     loc_140064677
0x14006407f  test    r14, r14
0x140064082  jz      short loc_1400640C1
0x140064084  or      rax, 0FFFFFFFFFFFFFFFFh
0x140064088  inc     rax
0x14006408b  cmp     [r14+rax*2], bx
0x140064090  jnz     short loc_140064088
0x140064092  lea     edi, [rax+0Ch]
0x140064095  lea     ecx, [rdi+rdi]; dwBytes
0x140064098  call    DllAllocSplMem
0x14006409d  mov     r13, rax
0x1400640a0  mov     [rsp+108h+var_B0], rax
0x1400640a5  test    rax, rax
0x1400640a8  jz      short loc_1400640D1
0x1400640aa  mov     qword ptr [rsp+108h+var_E8], rbx
0x1400640af  mov     r9, r15
0x1400640b2  mov     r8, r14; unsigned int
0x1400640b5  mov     edx, edi; unsigned __int16 *
0x1400640b7  mov     rcx, rax; this
0x1400640ba  call    ?StrNCatBuff@NCoreLibrary@@YAJPEAGIZZ; NCoreLibrary::StrNCatBuff(ushort *,uint,...)
0x1400640bf  jmp     short loc_1400640D1
0x1400640c1  mov     rcx, r15; Src
0x1400640c4  call    AllocSplStr
0x1400640c9  mov     r13, rax
0x1400640cc  mov     [rsp+108h+var_B0], rax
0x1400640d1  test    r13, r13
0x1400640d4  jnz     short loc_1400640FE
0x1400640d6  call    cs:__imp_GetLastError
0x1400640dc  mov     ebx, eax
0x1400640de  mov     [rsp+108h+var_E8], eax
0x1400640e2  mov     r9, r15
0x1400640e5  mov     r8, r14
0x1400640e8  lea     rdx, aFailedDecorati; "Failed decorating printer name (%ws) wi"...
0x1400640ef  mov     rcx, rsi; char *
0x1400640f2  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400640f7  mov     edi, ebx
0x1400640f9  jmp     loc_140064677
0x1400640fe  mov     ecx, cs:?gdwTlsGetPrinterIndex@@3KA; dwTlsIndex
0x140064104  call    cs:__imp_TlsGetValue
0x14006410a  cmp     rax, 2
0x14006410e  jnz     short loc_14006413C
0x140064110  mov     r8, r13; lpMem
0x140064113  xor     edx, edx; dwFlags
0x140064115  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14006411c  call    cs:__imp_HeapFree
0x140064122  mov     r8d, 57h ; 'W'
0x140064128  lea     rdx, aPossibleInfini; "Possible infinite GetPrinter recursion "...
0x14006412f  mov     rcx, rsi; char *
0x140064132  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140064137  jmp     loc_140064075
0x14006413c  mov     edx, 2; lpTlsValue
0x140064141  mov     ecx, cs:?gdwTlsGetPrinterIndex@@3KA; dwTlsIndex
0x140064147  call    cs:__imp_TlsSetValue
0x14006414d  test    eax, eax
0x14006414f  jnz     short loc_140064182
0x140064151  mov     r8, r13; lpMem
0x140064154  xor     edx, edx; dwFlags
0x140064156  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14006415d  call    cs:__imp_HeapFree
0x140064163  call    cs:__imp_GetLastError
0x140064169  mov     edi, eax
0x14006416b  mov     r8d, eax
0x14006416e  lea     rdx, aPossibleInfini_0; "Possible infinite GetPrinter recursion "...
0x140064175  mov     rcx, rsi; char *
0x140064178  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006417d  jmp     loc_140064677
0x140064182  lea     rcx, [rsp+108h+var_C8]; this
0x140064187  call    ??0ComLeakCleaner@NCOMLibrary@@QEAA@XZ; NCOMLibrary::ComLeakCleaner::ComLeakCleaner(void)
0x14006418c  nop
0x14006418d  mov     r15, [rsp+108h+arg_20]
0x140064195  cmp     [rsp+108h+arg_30], ebx
0x14006419c  jz      short loc_14006420E
0x14006419e  mov     [r15], ebx
0x1400641a1  mov     [r12], rbx
0x1400641a5  mov     eax, [rsp+108h+arg_28]
0x1400641ac  mov     [rsp+108h+var_D8], eax; unsigned int
0x1400641b0  mov     [rsp+108h+var_E0], r15; int *
0x1400641b5  mov     [rsp+108h+var_E8], ebx; unsigned int
0x1400641b9  xor     r9d, r9d; struct _devicemodeW *
0x1400641bc  mov     r8, [rsp+108h+arg_10]; struct _devicemodeW *
0x1400641c4  mov     rdx, r13; unsigned __int16 *
0x1400641c7  lea     rcx, [rsp+108h+var_A0]; this
0x1400641cc  call    ?DrvConvertDevMode@DriverConfigModuleAdapter@sandbox@@QEAAKPEAGPEAU_devicemodeW@@1KPEAJK@Z; sandbox::DriverConfigModuleAdapter::DrvConvertDevMode(ushort *,_devicemodeW *,_devicemodeW *,ulong,long *,ulong)
0x1400641d1  mov     edi, eax
0x1400641d3  mov     [rsp+108h+var_C4], eax
0x1400641d7  test    eax, eax
0x1400641d9  jz      short loc_1400641EC
0x1400641db  cmp     eax, 7Ah ; 'z'
0x1400641de  jz      short loc_1400641EC
0x1400641e0  lea     rdx, aDrvconvertdevm_0; "DrvConvertDevMode(fMode: 0x%08X) failed"...
0x1400641e7  jmp     loc_1400642A4
0x1400641ec  mov     ecx, [r15]; dwBytes
0x1400641ef  call    DllAllocSplMem
0x1400641f4  mov     [r12], rax
0x1400641f8  test    rax, rax
0x1400641fb  jnz     short loc_14006420E
0x1400641fd  call    cs:__imp_GetLastError
0x140064203  mov     edi, eax
0x140064205  mov     [rsp+108h+var_C4], eax
0x140064209  jmp     loc_1400642B7
0x14006420e  mov     ecx, [r15]
0x140064211  test    r12, r12
0x140064214  jz      short loc_14006421C
0x140064216  mov     r9, [r12]
0x14006421a  jmp     short loc_14006421F
0x14006421c  mov     r9, rbx; struct _devicemodeW *
0x14006421f  mov     eax, [rsp+108h+arg_28]
0x140064226  mov     [rsp+108h+var_D8], eax; unsigned int
0x14006422a  mov     [rsp+108h+var_E0], r15; int *
0x14006422f  mov     [rsp+108h+var_E8], ecx; unsigned int
0x140064233  mov     r8, [rsp+108h+arg_10]; struct _devicemodeW *
0x14006423b  mov     rdx, r13; unsigned __int16 *
0x14006423e  lea     rcx, [rsp+108h+var_A0]; this
0x140064243  call    ?DrvConvertDevMode@DriverConfigModuleAdapter@sandbox@@QEAAKPEAGPEAU_devicemodeW@@1KPEAJK@Z; sandbox::DriverConfigModuleAdapter::DrvConvertDevMode(ushort *,_devicemodeW *,_devicemodeW *,ulong,long *,ulong)
0x140064248  mov     edi, eax
0x14006424a  mov     [rsp+108h+var_C4], eax
0x14006424e  test    eax, eax
0x140064250  jnz     short loc_1400641E0
0x140064252  mov     r9d, [r15]
0x140064255  mov     rcx, [r12]
0x140064259  mov     r8d, 8007000Dh
0x14006425f  mov     [rsp+108h+var_B8], r8d
0x140064264  test    rcx, rcx
0x140064267  jz      short loc_14006428B
0x140064269  cmp     r9, 4Ch ; 'L'
0x14006426d  jb      short loc_14006428B
0x14006426f  movzx   edx, word ptr [rcx+46h]
0x140064273  movzx   eax, word ptr [rcx+44h]
0x140064277  add     rdx, rax
0x14006427a  cmp     r9, rdx
0x14006427d  jb      short loc_14006428B
0x14006427f  call    ??$SplIsValidDevmodeNoSize@U_devicemodeW@@G@@YAJPEAU_devicemodeW@@@Z; SplIsValidDevmodeNoSize<_devicemodeW,ushort>(_devicemodeW *)
0x140064284  mov     r8d, eax
0x140064287  mov     [rsp+108h+var_B8], eax
0x14006428b  mov     ecx, r8d; this
0x14006428e  call    ?StatusFromHResult@NCoreLibrary@@YAKJ@Z; NCoreLibrary::StatusFromHResult(long)
0x140064293  mov     edi, eax
0x140064295  mov     [rsp+108h+var_C4], eax
0x140064299  test    eax, eax
0x14006429b  jz      short loc_1400642B7
0x14006429d  lea     rdx, aDrvconvertdevm; "DrvConvertDevMode(fMode: 0x%08X) return"...
0x1400642a4  mov     r9d, eax
0x1400642a7  mov     r8d, [rsp+108h+arg_28]
0x1400642af  mov     rcx, rsi; char *
0x1400642b2  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400642b7  jmp     short loc_14006430D
0x1400642b9  mov     edi, eax
0x1400642bb  mov     [rsp+108h+var_C4], eax
0x1400642bf  mov     r8d, eax
0x1400642c2  lea     rdx, aExceptionFromD; "Exception from driver, LE: %d"
0x1400642c9  lea     rcx, aCalldrvdevmode; "CallDrvDevModeConversion"
0x1400642d0  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400642d5  mov     ecx, edi; dwErrCode
0x1400642d7  call    cs:__imp_SetLastError
0x1400642dd  lea     rsi, aCalldrvdevmode; "CallDrvDevModeConversion"
0x1400642e4  xor     ebx, ebx
0x1400642e6  mov     r15, [rsp+108h+arg_20]
0x1400642ee  mov     r12, [rsp+108h+arg_18]
0x1400642f6  mov     r13, [rsp+108h+var_B0]
0x1400642fb  mov     rax, [rsp+108h+var_90]
0x140064300  mov     [rsp+108h+var_A8], rax
0x140064305  mov     r14, [rsp+108h+arg_8]
0x14006430d  test    edi, edi
0x14006430f  jz      loc_140064578
0x140064315  cmp     [rsp+108h+arg_28], 4
0x14006431d  jnz     loc_14006452C
0x140064323  lea     rdx, aRetryObtaining; "Retry obtaining the default devmode usi"...
0x14006432a  mov     rcx, rsi; char *
0x14006432d  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140064332  mov     [rsp+108h+arg_10], rbx
0x14006433a  mov     r8, r14; unsigned __int16 *
0x14006433d  mov     rdx, [rsp+108h+var_A8]; struct sandbox::SandboxManager *
0x140064342  lea     rcx, [rsp+108h+arg_10]; this
0x14006434a  call    ?Initialize@DocumentPropertiesAdapter@sandbox@@QEAAKPEAVSandboxManager@2@PEBG1K@Z; sandbox::DocumentPropertiesAdapter::Initialize(sandbox::SandboxManager *,ushort const *,ushort const *,ulong)
0x14006434f  mov     r14d, eax
0x140064352  cmp     [rsp+108h+arg_30], ebx
0x140064359  jz      short loc_140064378
0x14006435b  cmp     [r12], rbx
0x14006435f  jz      short loc_140064378
0x140064361  mov     r8, [r12]; lpMem
0x140064365  xor     edx, edx; dwFlags
0x140064367  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14006436e  call    cs:__imp_HeapFree
0x140064374  mov     [r12], rbx
0x140064378  mov     [r15], ebx
0x14006437b  mov     [rsp+108h+var_E8], ebx; unsigned int
0x14006437f  xor     r9d, r9d; struct _devicemodeW *
0x140064382  xor     r8d, r8d; unsigned int
0x140064385  lea     rcx, [rsp+108h+arg_10]; this
0x14006438d  call    ?DocumentPropertiesW@DocumentPropertiesAdapter@sandbox@@QEAAJPEAU_devicemodeW@@K0K@Z; sandbox::DocumentPropertiesAdapter::DocumentPropertiesW(_devicemodeW *,ulong,_devicemodeW *,ulong)
0x140064392  test    r14d, r14d
0x140064395  jnz     loc_140064507
0x14006439b  cmp     [rsp+108h+arg_30], ebx
0x1400643a2  jz      loc_140064433
0x1400643a8  mov     [rsp+108h+var_E8], ebx; unsigned int
0x1400643ac  xor     r9d, r9d; struct _devicemodeW *
0x1400643af  xor     r8d, r8d; unsigned int
0x1400643b2  lea     rcx, [rsp+108h+arg_10]; this
0x1400643ba  call    ?DocumentPropertiesW@DocumentPropertiesAdapter@sandbox@@QEAAJPEAU_devicemodeW@@K0K@Z; sandbox::DocumentPropertiesAdapter::DocumentPropertiesW(_devicemodeW *,ulong,_devicemodeW *,ulong)
0x1400643bf  mov     [r15], eax
0x1400643c2  test    eax, eax
0x1400643c4  jle     short loc_140064405
0x1400643c6  mov     ecx, eax; dwBytes
0x1400643c8  call    DllAllocSplMem
0x1400643cd  mov     [r12], rax
0x1400643d1  test    rax, rax
0x1400643d4  jnz     short loc_140064433
0x1400643d6  call    cs:__imp_GetLastError
0x1400643dc  mov     r14d, eax
0x1400643df  mov     r9d, eax
0x1400643e2  mov     r8d, [r15]
0x1400643e5  lea     rdx, aFailedToAlloca_5; "Failed to allocate %d bytes for devmode"...
0x1400643ec  mov     rcx, rsi; char *
0x1400643ef  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400643f4  test    r14d, r14d
0x1400643f7  jnz     loc_140064507
0x1400643fd  mov     r14d, 8
0x140064403  jmp     short loc_140064433
0x140064405  call    cs:__imp_GetLastError
0x14006440b  mov     r14d, eax
0x14006440e  mov     r9d, eax
0x140064411  mov     r8, [rsp+108h+arg_8]
0x140064419  lea     rdx, aDocumentproper_1; "DocumentProperties(%ws, 0) failed, LE: "...
0x140064420  mov     rcx, rsi; char *
0x140064423  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140064428  mov     eax, 8
0x14006442d  test    r14d, r14d
0x140064430  cmovz   edi, eax
0x140064433  test    r14d, r14d
0x140064436  jnz     loc_140064507
0x14006443c  cmp     [r15], ebx
0x14006443f  jle     short loc_140064447
0x140064441  cmp     [r12], rbx
0x140064445  jnz     short loc_140064468
0x140064447  mov     r14d, 57h ; 'W'
0x14006444d  mov     [rsp+108h+var_E8], r14d
0x140064452  mov     r9d, [r15]
0x140064455  mov     r8, [r12]
0x140064459  lea     rdx, aInvalidOutputD; "Invalid output devmode buffer argument("...
  ... truncated ...
```
