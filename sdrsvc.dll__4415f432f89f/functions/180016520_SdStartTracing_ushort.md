# SdStartTracing(ushort * *)

- ea: `0x180016520`
- end: `0x180016986`
- name: `?SdStartTracing@@YAJPEAPEAG@Z`
- size: `1126`
- prototype: `__int64 __fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000efb0`

## callees

- `0x18001586c`
- `0x180015974`
- `0x1800160c8`
- `0x180016324`
- `0x180016520`
- `0x18001e67c`
- `0x18001ffb4`
- `0x180020488`
- `0x180020618`
- `0x18002097c`
- `0x180020a54`
- `0x1800212e4`
- `0x1800215d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800165e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016958`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800165e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016958`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016610`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016610`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016941`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016941`

## pseudocode

```c
__int64 __fastcall SdStartTracing(LPVOID *a1)
{
  unsigned int v2; // edi
  __int16 v3; // ax
  int SDTracingDirectory; // ebx
  __int16 v5; // ax
  LSTATUS v6; // eax
  const unsigned __int16 *v7; // rcx
  const unsigned __int16 *v8; // r9
  const unsigned __int16 *v9; // rcx
  unsigned int v10; // r8d
  GUID ProviderId; // [rsp+60h] [rbp-59h] BYREF
  int v13; // [rsp+70h] [rbp-49h] BYREF
  __int16 v14; // [rsp+74h] [rbp-45h]
  __int16 v15; // [rsp+76h] [rbp-43h]
  unsigned __int16 *v16; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v17; // [rsp+B0h] [rbp-9h]
  int v18; // [rsp+B8h] [rbp-1h] BYREF
  __int16 v19; // [rsp+BCh] [rbp+3h]
  __int16 v20; // [rsp+BEh] [rbp+5h]
  unsigned int v21; // [rsp+120h] [rbp+67h] BYREF
  TRACEHANDLE TraceHandle; // [rsp+128h] [rbp+6Fh] BYREF
  HKEY hKey; // [rsp+130h] [rbp+77h] BYREF
  LPVOID pv; // [rsp+138h] [rbp+7Fh] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v13, "SdStartTracing", 312, 1);
  v17 = 0;
  v16 = (unsigned __int16 *)qword_180028260;
  v2 = 503316717;
  TraceHandle = -1;
  v3 = 321;
  hKey = 0;
  v21 = 503316717;
  pv = 0;
  if ( !a1 )
  {
    SDTracingDirectory = -2147024809;
    v13 = -2147024809;
    goto LABEL_35;
  }
  *a1 = 0;
  v13 = 0;
  v14 = 321;
  SDTracingDirectory = SxCheckWBDiagSession();
  v13 = SDTracingDirectory;
  v3 = 326;
  if ( SDTracingDirectory < 0 )
    goto LABEL_35;
  v14 = 326;
  if ( SDTracingDirectory == 1 )
  {
    v5 = 329;
LABEL_5:
    v13 = SDTracingDirectory;
    v14 = v5;
    goto LABEL_36;
  }
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup",
         0,
         0x20019u,
         &hKey);
  SDTracingDirectory = v6;
  if ( v6 > 0 )
    SDTracingDirectory = (unsigned __int16)v6 | 0x80070000;
  v13 = SDTracingDirectory;
  v3 = 332;
  if ( SDTracingDirectory < 0 )
    goto LABEL_35;
  v14 = 332;
  if ( !(unsigned int)SxRegReadDWORD(hKey, L"WindowsBackupTracingFlags", &v21, 0) )
  {
    v2 = v21;
    if ( !v21 )
    {
      SDTracingDirectory = 0;
      v5 = 344;
      goto LABEL_5;
    }
  }
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v18, "SdStopTracing", 258, 1);
  v18 = SxStopTracing(v7);
  if ( v18 >= 0 )
    v19 = 260;
  else
    v20 = 260;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v18);
  SDTracingDirectory = GetSDTracingDirectory((struct CBsString *)&v16);
  v13 = SDTracingDirectory;
  v3 = 354;
  if ( SDTracingDirectory < 0 )
    goto LABEL_35;
  v14 = 354;
  SDTracingDirectory = EnsureTracingDirectory((const WCHAR **)&v16);
  v13 = SDTracingDirectory;
  v3 = 356;
  if ( SDTracingDirectory < 0 )
    goto LABEL_35;
  v14 = 356;
  if ( !(_DWORD)v17 )
  {
    SDTracingDirectory = -2147020579;
    v13 = -2147020579;
LABEL_22:
    v3 = 358;
    goto LABEL_35;
  }
  v13 = CBsString::_CombinePathImpl((CBsString *)&v16, L"WindowsBackup", 0, v8);
  SDTracingDirectory = v13;
  if ( v13 < 0 )
    goto LABEL_22;
  v14 = 358;
  SDTracingDirectory = SxStartTracing(v9, v16, v10, &TraceHandle, (unsigned __int16 **)&pv);
  v13 = SDTracingDirectory;
  v3 = 364;
  if ( SDTracingDirectory >= 0 )
  {
    v14 = 364;
    ProviderId = c_guidEngineTracingControlGuid;
    SDTracingDirectory = SxEnableTraceDefault(TraceHandle, &ProviderId, v2);
    v13 = SDTracingDirectory;
    v3 = 366;
    if ( SDTracingDirectory >= 0 )
    {
      v14 = 366;
      ProviderId = c_guidGuiTracingControlGuid;
      SDTracingDirectory = SxEnableTraceDefault(TraceHandle, &ProviderId, v2);
      v13 = SDTracingDirectory;
      v3 = 367;
      if ( SDTracingDirectory >= 0 )
      {
        v14 = 367;
        ProviderId = c_guidServiceTracingControlGuid;
        SDTracingDirectory = SxEnableTraceDefault(TraceHandle, &ProviderId, v2);
        v13 = SDTracingDirectory;
        v3 = 368;
        if ( SDTracingDirectory >= 0 )
        {
          v14 = 368;
          ProviderId = c_guidShellExtTracingControlGuid;
          SDTracingDirectory = SxEnableTraceDefault(TraceHandle, &ProviderId, v2);
          v13 = SDTracingDirectory;
          v3 = 369;
          if ( SDTracingDirectory >= 0 )
          {
            v14 = 369;
            ProviderId = c_guidSppTracingControlGuid;
            SDTracingDirectory = SxEnableTraceDefault(TraceHandle, &ProviderId, v2);
            v13 = SDTracingDirectory;
            v3 = 370;
            if ( SDTracingDirectory >= 0 )
            {
              v14 = 370;
              ProviderId = c_guidAsrTracingControlGuid;
              SDTracingDirectory = SxEnableTraceCustom(TraceHandle, &ProviderId, 0xFFu, 0xFFu);
              v13 = SDTracingDirectory;
              v3 = 375;
              if ( SDTracingDirectory >= 0 )
              {
                v14 = 375;
                ProviderId = c_guidUdfdTracingControlGuid;
                SDTracingDirectory = SxEnableTraceCustom(TraceHandle, &ProviderId, 0xFFu, 0xFFu);
                v13 = SDTracingDirectory;
                v3 = 380;
                if ( SDTracingDirectory >= 0 )
                {
                  v14 = 380;
                  ProviderId = c_guidUdfsTracingControlGuid;
                  SDTracingDirectory = SxEnableTraceCustom(TraceHandle, &ProviderId, 0xFFu, 0xFFu);
                  v13 = SDTracingDirectory;
                  v3 = 389;
                  if ( SDTracingDirectory >= 0 )
                  {
                    v14 = 389;
                    ProviderId = c_guidBlbEngineTracingControlGuid;
                    SDTracingDirectory = SxEnableTraceCustom(TraceHandle, &ProviderId, 0x20000065u, 4u);
                    v13 = SDTracingDirectory;
                    v3 = 398;
                    if ( SDTracingDirectory >= 0 )
                    {
                      v14 = 398;
                      *a1 = pv;
                      pv = 0;
                      goto LABEL_36;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_35:
  v15 = v3;
LABEL_36:
  if ( pv )
  {
    CoTaskMemFree(pv);
    SDTracingDirectory = v13;
  }
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CBsString::_Release((LPVOID *)&v16);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v13);
  return (unsigned int)SDTracingDirectory;
}

```

## disassembly

```asm
0x180016520  push    rbp
0x180016522  push    rbx
0x180016523  push    rsi
0x180016524  push    rdi
0x180016525  lea     rbp, [rsp-3Fh]
0x18001652a  sub     rsp, 0F8h
0x180016531  mov     rsi, rcx
0x180016534  lea     rdx, aSdstarttracing; "SdStartTracing"
0x18001653b  lea     rcx, [rbp+57h+var_A0]; this
0x18001653f  mov     r9d, 1; unsigned __int16
0x180016545  mov     r8d, 138h; unsigned __int16
0x18001654b  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180016550  mov     [rbp+57h+var_60], 0
0x180016558  lea     rax, qword_180028260
0x18001655f  mov     [rbp+57h+var_68], rax
0x180016563  mov     edi, 1E0000EDh
0x180016568  mov     [rbp+57h+TraceHandle], 0FFFFFFFFFFFFFFFFh
0x180016570  mov     eax, 141h
0x180016575  mov     [rbp+57h+hKey], 0
0x18001657d  mov     [rbp+57h+arg_0], edi
0x180016580  mov     [rbp+57h+pv], 0
0x180016588  test    rsi, rsi
0x18001658b  jz      loc_18001692C
0x180016591  mov     qword ptr [rsi], 0
0x180016598  mov     [rbp+57h+var_A0], 0
0x18001659f  mov     [rbp+57h+var_9C], ax
0x1800165a3  call    ?SxCheckWBDiagSession@@YAJXZ; SxCheckWBDiagSession(void)
0x1800165a8  mov     ebx, eax
0x1800165aa  mov     [rbp+57h+var_A0], eax
0x1800165ad  test    eax, eax
0x1800165af  mov     eax, 146h
0x1800165b4  js      loc_180016934
0x1800165ba  mov     [rbp+57h+var_9C], ax
0x1800165be  cmp     ebx, 1
0x1800165c1  jnz     short loc_1800165D4
0x1800165c3  mov     eax, 149h
0x1800165c8  mov     [rbp+57h+var_A0], ebx
0x1800165cb  mov     [rbp+57h+var_9C], ax
0x1800165cf  jmp     loc_180016938
0x1800165d4  mov     rcx, [rbp+57h+hKey]; hKey
0x1800165d8  lea     rax, [rcx-1]
0x1800165dc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800165e0  ja      short loc_1800165F0
0x1800165e2  call    cs:__imp_RegCloseKey
0x1800165e8  mov     [rbp+57h+hKey], 0
0x1800165f0  lea     rax, [rbp+57h+hKey]
0x1800165f4  mov     r9d, 20019h; samDesired
0x1800165fa  xor     r8d, r8d; ulOptions
0x1800165fd  mov     [rsp+110h+phkResult], rax; unsigned __int16 *
0x180016602  lea     rdx, c_wszSafedocsUser_Key; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180016609  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016610  call    cs:__imp_RegOpenKeyExW
0x180016616  mov     ebx, eax
0x180016618  test    eax, eax
0x18001661a  jle     short loc_180016625
0x18001661c  movzx   ebx, ax
0x18001661f  or      ebx, 80070000h
0x180016625  mov     [rbp+57h+var_A0], ebx
0x180016628  mov     eax, 14Ch
0x18001662d  test    ebx, ebx
0x18001662f  js      loc_180016934
0x180016635  mov     rcx, [rbp+57h+hKey]; hKey
0x180016639  lea     r8, [rbp+57h+arg_0]; unsigned int *
0x18001663d  xor     r9d, r9d; int
0x180016640  mov     [rbp+57h+var_9C], ax
0x180016644  lea     rdx, c_wszSafedocsTracingFlags; "WindowsBackupTracingFlags"
0x18001664b  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x180016650  test    eax, eax
0x180016652  jnz     short loc_180016667
0x180016654  mov     edi, [rbp+57h+arg_0]
0x180016657  test    edi, edi
0x180016659  jnz     short loc_180016667
0x18001665b  xor     ebx, ebx
0x18001665d  mov     eax, 158h
0x180016662  jmp     loc_1800165C8
0x180016667  mov     r9d, 1; unsigned __int16
0x18001666d  lea     rdx, aSdstoptracing; "SdStopTracing"
0x180016674  mov     r8d, 102h; unsigned __int16
0x18001667a  lea     rcx, [rbp+57h+var_58]; this
0x18001667e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180016683  call    ?SxStopTracing@@YAJPEBG@Z; SxStopTracing(ushort const *)
0x180016688  mov     [rbp+57h+var_58], eax
0x18001668b  test    eax, eax
0x18001668d  mov     eax, 104h
0x180016692  jns     short loc_18001669A
0x180016694  mov     [rbp+57h+var_52], ax
0x180016698  jmp     short loc_18001669E
0x18001669a  mov     [rbp+57h+var_54], ax
0x18001669e  lea     rcx, [rbp+57h+var_58]; this
0x1800166a2  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800166a7  lea     rcx, [rbp+57h+var_68]; this
0x1800166ab  call    ?GetSDTracingDirectory@@YAJPEAVCBsString@@@Z; GetSDTracingDirectory(CBsString *)
0x1800166b0  mov     ebx, eax
0x1800166b2  mov     [rbp+57h+var_A0], eax
0x1800166b5  test    eax, eax
0x1800166b7  mov     eax, 162h
0x1800166bc  js      loc_180016934
0x1800166c2  lea     rcx, [rbp+57h+var_68]; struct CBsString *
0x1800166c6  mov     [rbp+57h+var_9C], ax
0x1800166ca  call    ?EnsureTracingDirectory@@YAJPEAVCBsString@@@Z; EnsureTracingDirectory(CBsString *)
0x1800166cf  mov     ebx, eax
0x1800166d1  mov     [rbp+57h+var_A0], eax
0x1800166d4  test    eax, eax
0x1800166d6  mov     eax, 164h
0x1800166db  js      loc_180016934
0x1800166e1  cmp     dword ptr [rbp+57h+var_60], 0
0x1800166e5  mov     [rbp+57h+var_9C], ax
0x1800166e9  jnz     short loc_1800166F5
0x1800166eb  mov     ebx, 800710DDh
0x1800166f0  mov     [rbp+57h+var_A0], ebx
0x1800166f3  jmp     short loc_180016711
0x1800166f5  xor     r8d, r8d; unsigned __int16 *
0x1800166f8  lea     rdx, aWindowsbackup_0; "WindowsBackup"
0x1800166ff  lea     rcx, [rbp+57h+var_68]; this
0x180016703  call    ?_CombinePathImpl@CBsString@@AEAAJPEBG000000000@Z; CBsString::_CombinePathImpl(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180016708  mov     [rbp+57h+var_A0], eax
0x18001670b  mov     ebx, eax
0x18001670d  test    eax, eax
0x18001670f  jns     short loc_18001671B
0x180016711  mov     eax, 166h
0x180016716  jmp     loc_180016934
0x18001671b  mov     rdx, [rbp+57h+var_68]; unsigned __int16 *
0x18001671f  lea     r9, [rbp+57h+TraceHandle]; unsigned __int64 *
0x180016723  mov     eax, 166h
0x180016728  mov     [rbp+57h+var_9C], ax
0x18001672c  lea     rax, [rbp+57h+pv]
0x180016730  mov     [rsp+110h+phkResult], rax; unsigned __int16 **
0x180016735  call    ?SxStartTracing@@YAJPEBG0KPEA_KPEAPEAG@Z; SxStartTracing(ushort const *,ushort const *,ulong,unsigned __int64 *,ushort * *)
0x18001673a  mov     ebx, eax
0x18001673c  mov     [rbp+57h+var_A0], eax
0x18001673f  test    eax, eax
0x180016741  mov     eax, 16Ch
0x180016746  js      loc_180016934
0x18001674c  movups  xmm0, xmmword ptr cs:?c_guidEngineTracingControlGuid@@3U_GUID@@B.Data1; _GUID const c_guidEngineTracingControlGuid ...
0x180016753  mov     rcx, [rbp+57h+TraceHandle]; TraceHandle
0x180016757  lea     rdx, [rbp+57h+ProviderId]; struct _GUID
0x18001675b  mov     r8d, edi; unsigned int
0x18001675e  mov     [rbp+57h+var_9C], ax
0x180016762  movdqu  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x180016767  call    ?SxEnableTraceDefault@@YAJ_KU_GUID@@K@Z; SxEnableTraceDefault(unsigned __int64,_GUID,ulong)
0x18001676c  mov     ebx, eax
0x18001676e  mov     [rbp+57h+var_A0], eax
0x180016771  test    eax, eax
0x180016773  mov     eax, 16Eh
0x180016778  js      loc_180016934
0x18001677e  movups  xmm0, xmmword ptr cs:?c_guidGuiTracingControlGuid@@3U_GUID@@B.Data1; _GUID const c_guidGuiTracingControlGuid ...
0x180016785  mov     rcx, [rbp+57h+TraceHandle]; TraceHandle
0x180016789  lea     rdx, [rbp+57h+ProviderId]; struct _GUID
0x18001678d  mov     r8d, edi; unsigned int
0x180016790  mov     [rbp+57h+var_9C], ax
0x180016794  movdqu  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x180016799  call    ?SxEnableTraceDefault@@YAJ_KU_GUID@@K@Z; SxEnableTraceDefault(unsigned __int64,_GUID,ulong)
0x18001679e  mov     ebx, eax
0x1800167a0  mov     [rbp+57h+var_A0], eax
0x1800167a3  test    eax, eax
0x1800167a5  mov     eax, 16Fh
0x1800167aa  js      loc_180016934
0x1800167b0  movups  xmm0, xmmword ptr cs:?c_guidServiceTracingControlGuid@@3U_GUID@@B.Data1; _GUID const c_guidServiceTracingControlGuid ...
0x1800167b7  mov     rcx, [rbp+57h+TraceHandle]; TraceHandle
0x1800167bb  lea     rdx, [rbp+57h+ProviderId]; struct _GUID
0x1800167bf  mov     r8d, edi; unsigned int
0x1800167c2  mov     [rbp+57h+var_9C], ax
0x1800167c6  movdqu  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x1800167cb  call    ?SxEnableTraceDefault@@YAJ_KU_GUID@@K@Z; SxEnableTraceDefault(unsigned __int64,_GUID,ulong)
0x1800167d0  mov     ebx, eax
0x1800167d2  mov     [rbp+57h+var_A0], eax
0x1800167d5  test    eax, eax
0x1800167d7  mov     eax, 170h
0x1800167dc  js      loc_180016934
0x1800167e2  movups  xmm0, xmmword ptr cs:?c_guidShellExtTracingControlGuid@@3U_GUID@@B.Data1; _GUID const c_guidShellExtTracingControlGuid ...
0x1800167e9  mov     rcx, [rbp+57h+TraceHandle]; TraceHandle
0x1800167ed  lea     rdx, [rbp+57h+ProviderId]; struct _GUID
0x1800167f1  mov     r8d, edi; unsigned int
0x1800167f4  mov     [rbp+57h+var_9C], ax
0x1800167f8  movdqu  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x1800167fd  call    ?SxEnableTraceDefault@@YAJ_KU_GUID@@K@Z; SxEnableTraceDefault(unsigned __int64,_GUID,ulong)
0x180016802  mov     ebx, eax
0x180016804  mov     [rbp+57h+var_A0], eax
0x180016807  test    eax, eax
0x180016809  mov     eax, 171h
0x18001680e  js      loc_180016934
0x180016814  movups  xmm0, xmmword ptr cs:?c_guidSppTracingControlGuid@@3U_GUID@@B.Data1; _GUID const c_guidSppTracingControlGuid ...
0x18001681b  mov     rcx, [rbp+57h+TraceHandle]; TraceHandle
0x18001681f  lea     rdx, [rbp+57h+ProviderId]; struct _GUID
0x180016823  mov     r8d, edi; unsigned int
0x180016826  mov     [rbp+57h+var_9C], ax
0x18001682a  movdqu  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x18001682f  call    ?SxEnableTraceDefault@@YAJ_KU_GUID@@K@Z; SxEnableTraceDefault(unsigned __int64,_GUID,ulong)
0x180016834  mov     ebx, eax
0x180016836  mov     [rbp+57h+var_A0], eax
0x180016839  test    eax, eax
0x18001683b  mov     eax, 172h
0x180016840  js      loc_180016934
0x180016846  movups  xmm0, xmmword ptr cs:?c_guidAsrTracingControlGuid@@3U_GUID@@B.Data1; _GUID const c_guidAsrTracingControlGuid ...
0x18001684d  mov     rcx, [rbp+57h+TraceHandle]; TraceHandle
0x180016851  lea     edi, [rax-73h]
0x180016854  mov     r9d, edi; unsigned int
0x180016857  mov     [rbp+57h+var_9C], ax
0x18001685b  mov     r8d, edi; MatchAnyKeyword
0x18001685e  lea     rdx, [rbp+57h+ProviderId]; ProviderId
0x180016862  movdqu  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x180016867  call    ?SxEnableTraceCustom@@YAJ_KU_GUID@@KK@Z; SxEnableTraceCustom(unsigned __int64,_GUID,ulong,ulong)
0x18001686c  mov     ebx, eax
0x18001686e  mov     [rbp+57h+var_A0], eax
0x180016871  test    eax, eax
0x180016873  lea     eax, [rdi+78h]
0x180016876  js      loc_180016934
0x18001687c  movups  xmm0, xmmword ptr cs:?c_guidUdfdTracingControlGuid@@3U_GUID@@B.Data1; _GUID const c_guidUdfdTracingControlGuid ...
0x180016883  mov     rcx, [rbp+57h+TraceHandle]; TraceHandle
0x180016887  lea     rdx, [rbp+57h+ProviderId]; ProviderId
0x18001688b  mov     r9d, edi; unsigned int
0x18001688e  mov     [rbp+57h+var_9C], ax
0x180016892  mov     r8d, edi; MatchAnyKeyword
0x180016895  movdqu  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x18001689a  call    ?SxEnableTraceCustom@@YAJ_KU_GUID@@KK@Z; SxEnableTraceCustom(unsigned __int64,_GUID,ulong,ulong)
0x18001689f  mov     ebx, eax
0x1800168a1  mov     [rbp+57h+var_A0], eax
0x1800168a4  test    eax, eax
0x1800168a6  lea     eax, [rdi+7Dh]
0x1800168a9  js      loc_180016934
0x1800168af  movups  xmm0, xmmword ptr cs:?c_guidUdfsTracingControlGuid@@3U_GUID@@B.Data1; _GUID const c_guidUdfsTracingControlGuid ...
0x1800168b6  mov     rcx, [rbp+57h+TraceHandle]; TraceHandle
0x1800168ba  lea     rdx, [rbp+57h+ProviderId]; ProviderId
0x1800168be  mov     r9d, edi; unsigned int
0x1800168c1  mov     [rbp+57h+var_9C], ax
0x1800168c5  mov     r8d, edi; MatchAnyKeyword
0x1800168c8  movdqu  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x1800168cd  call    ?SxEnableTraceCustom@@YAJ_KU_GUID@@KK@Z; SxEnableTraceCustom(unsigned __int64,_GUID,ulong,ulong)
0x1800168d2  mov     ebx, eax
0x1800168d4  mov     [rbp+57h+var_A0], eax
0x1800168d7  test    eax, eax
0x1800168d9  mov     eax, 185h
0x1800168de  js      short loc_180016934
0x1800168e0  movups  xmm0, xmmword ptr cs:?c_guidBlbEngineTracingControlGuid@@3U_GUID@@B.Data1; _GUID const c_guidBlbEngineTracingControlGuid ...
0x1800168e7  mov     rcx, [rbp+57h+TraceHandle]; TraceHandle
0x1800168eb  lea     rdx, [rbp+57h+ProviderId]; ProviderId
0x1800168ef  mov     r9d, 4; unsigned int
0x1800168f5  mov     [rbp+57h+var_9C], ax
0x1800168f9  mov     r8d, 20000065h; MatchAnyKeyword
0x1800168ff  movdqu  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x180016904  call    ?SxEnableTraceCustom@@YAJ_KU_GUID@@KK@Z; SxEnableTraceCustom(unsigned __int64,_GUID,ulong,ulong)
0x180016909  mov     ebx, eax
0x18001690b  mov     [rbp+57h+var_A0], eax
0x18001690e  test    eax, eax
0x180016910  mov     eax, 18Eh
0x180016915  js      short loc_180016934
0x180016917  mov     [rbp+57h+var_9C], ax
0x18001691b  mov     rax, [rbp+57h+pv]
0x18001691f  mov     [rsi], rax
0x180016922  mov     [rbp+57h+pv], 0
0x18001692a  jmp     short loc_180016938
0x18001692c  mov     ebx, 80070057h
0x180016931  mov     [rbp+57h+var_A0], ebx
0x180016934  mov     [rbp+57h+var_9A], ax
0x180016938  mov     rcx, [rbp+57h+pv]; pv
0x18001693c  test    rcx, rcx
0x18001693f  jz      short loc_18001694A
0x180016941  call    cs:__imp_CoTaskMemFree
0x180016947  mov     ebx, [rbp+57h+var_A0]
0x18001694a  mov     rcx, [rbp+57h+hKey]; hKey
0x18001694e  lea     rdx, [rcx-1]
0x180016952  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180016956  ja      short loc_180016966
0x180016958  call    cs:__imp_RegCloseKey
0x18001695e  mov     [rbp+57h+hKey], 0
0x180016966  lea     rcx, [rbp+57h+var_68]; this
0x18001696a  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001696f  lea     rcx, [rbp+57h+var_A0]; this
0x180016973  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180016978  mov     eax, ebx
0x18001697a  add     rsp, 0F8h
0x180016981  pop     rdi
0x180016982  pop     rsi
0x180016983  pop     rbx
0x180016984  pop     rbp
0x180016985  retn
```
