# GetCachedDefaultDevModeAndSize(void *,_devicemodeW * *,ulong *)

- ea: `0x1400727d8`
- end: `0x140072ad4`
- name: `?GetCachedDefaultDevModeAndSize@@YAHPEAXPEAPEAU_devicemodeW@@PEAK@Z`
- size: `764`
- prototype: `__int64 __fastcall(void *, struct _devicemodeW **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400065e0`

## callees

- `0x140002c80`
- `0x140004790`
- `0x140004800`
- `0x14000cfe0`
- `0x14000deb0`
- `0x140015290`
- `0x1400727d8`
- `0x140072adc`
- `0x140072c7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140072a10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140072a10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007283e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007293c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140072983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400729c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140072a78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007283e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007293c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140072983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400729c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140072a78`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140072aad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140072aad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400728ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14007292e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400729b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400728ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14007292e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400729b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400728c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140072a2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140072a45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400728c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140072a2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140072a45`

## string_xrefs

- `0x1400728ef`: `GetCachedDefaultDevModeAndSize`
- `0x140072902`: `GetCachedDefaultDevModeAndSize`
- `0x140072955`: `GetCachedDefaultDevModeAndSize`
- `0x1400729dd`: `GetCachedDefaultDevModeAndSize`
- `0x140072a5c`: `GetCachedDefaultDevModeAndSize`
- `0x140072a91`: `GetCachedDefaultDevModeAndSize`
- `0x1400728fb`: ` Query the registry for DevMode under HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wi NT\CurrentVersion\Print\Providers\Client Side Rendering Print Provider\<USER SID>\Printers\Connections\<printer name>\DefaultDevModes`
- `0x140072a55`: ` Could not find DevMode in the registry,Getting the Devmode from the printer driver`
- `0x14007294b`: ` RegQueryValueEx for gszDefaultDevMode completed with %u, LE: %d`
- `0x1400729d3`: `RegQueryValueEx to fetch DevMode status completed with %u, LE: %d`

## pseudocode

```c
__int64 __fastcall GetCachedDefaultDevModeAndSize(void *a1, LPVOID *a2, unsigned int *a3)
{
  unsigned int DefaultDevModeAndSize; // esi
  HKEY ClientUserHandle; // rax
  HKEY v8; // r15
  unsigned int v9; // ebx
  unsigned __int16 *v10; // rdi
  unsigned int v11; // ebx
  DWORD v12; // eax
  struct _devicemodeW *lpData; // rax
  DWORD LastError; // eax
  DWORD v15; // eax
  HKEY hKey; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v18[24]; // [rsp+38h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+40h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+58h] BYREF

  DefaultDevModeAndSize = 0;
  Type = 3;
  hKey = 0;
  cbData = 0;
  if ( a1 && a2 && a3 )
  {
    NSecurityLibrary::Low2MediumIntegrity::Low2MediumIntegrity((NSecurityLibrary::Low2MediumIntegrity *)v18);
    ClientUserHandle = (HKEY)SplGetClientUserHandle(131103);
    v8 = ClientUserHandle;
    if ( ClientUserHandle )
    {
      v10 = (unsigned __int16 *)*((_QWORD *)a1 + 9);
      if ( v10 && *v10 == 92 && v10[1] == 92 )
      {
        v9 = RegOpenConnectionKey(ClientUserHandle, *((unsigned __int16 **)a1 + 9), &hKey);
        if ( !v9 )
        {
          if ( RegQueryValueExW(hKey, L"DefaultDevMode", 0, &Type, 0, &cbData)
            && ((RegCloseKey(hKey), hKey = 0, (unsigned int)RegOpenCachedConnectionKey(v10, &hKey))
             || (PrvSpoolssTelemetry::WriteDbgTraceInfo(
                   "GetCachedDefaultDevModeAndSize",
                   L" Could not find DevMode under HKEY_CURRENT_USER\\Printers\\Connections"),
                 PrvSpoolssTelemetry::WriteDbgTraceInfo(
                   "GetCachedDefaultDevModeAndSize",
                   L" Query the registry for DevMode under HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Wi NT\\CurrentVersion\\"
                    "Print\\Providers\\Client Side Rendering Print Provider\\<USER SID>\\Printers\\Connections\\<printer "
                    "name>\\DefaultDevModes"),
                 v11 = RegQueryValueExW(hKey, L"DefaultDevMode", 0, &Type, 0, &cbData),
                 v12 = GetLastError(),
                 PrvSpoolssTelemetry::WriteDbgTraceInfo(
                   "GetCachedDefaultDevModeAndSize",
                   L" RegQueryValueEx for gszDefaultDevMode completed with %u, LE: %d",
                   v11,
                   v12),
                 v11))
            || Type != 3 )
          {
            v9 = 13;
          }
          else
          {
            lpData = (struct _devicemodeW *)DllAllocSplMem(cbData);
            *a2 = lpData;
            if ( lpData )
            {
              v9 = RegQueryValueExW(hKey, L"DefaultDevMode", 0, &Type, (LPBYTE)lpData, &cbData);
              LastError = GetLastError();
              PrvSpoolssTelemetry::WriteDbgTraceInfo(
                "GetCachedDefaultDevModeAndSize",
                L"RegQueryValueEx to fetch DevMode status completed with %u, LE: %d",
                v9,
                LastError);
              *a3 = (cbData + 3) & 0xFFFFFFFC;
              if ( v9 )
              {
                if ( *a2 )
                {
                  HeapFree(g_hSpoolssHeap, 0, *a2);
                  *a2 = 0;
                }
              }
              else
              {
                DefaultDevModeAndSize = 1;
              }
            }
            else
            {
              v9 = GetLastError();
            }
          }
        }
        if ( hKey )
          RegCloseKey(hKey);
      }
      else
      {
        v9 = 1801;
      }
      RegCloseKey(v8);
    }
    else
    {
      v9 = GetLastError();
    }
    if ( v9 )
    {
      PrvSpoolssTelemetry::WriteDbgTraceInfo(
        "GetCachedDefaultDevModeAndSize",
        L" Could not find DevMode in the registry,Getting the Devmode from the printer driver");
      DefaultDevModeAndSize = GetDefaultDevModeAndSize(a1, (struct _devicemodeW **)a2, a3);
      v15 = GetLastError();
      PrvSpoolssTelemetry::WriteDbgTraceInfo(
        "GetCachedDefaultDevModeAndSize",
        L" GetDefaultDevModeAndSize return %u, LE: %d",
        DefaultDevModeAndSize,
        v15);
    }
    NSecurityLibrary::Low2MediumIntegrity::~Low2MediumIntegrity((NSecurityLibrary::Low2MediumIntegrity *)v18);
  }
  else
  {
    SetLastError(0x57u);
  }
  return DefaultDevModeAndSize;
}

```

## disassembly

```asm
0x1400727d8  mov     [rsp-38h+arg_8], rbx
0x1400727dd  push    rbp
0x1400727de  push    rsi
0x1400727df  push    rdi
0x1400727e0  push    r12
0x1400727e2  push    r13
0x1400727e4  push    r14
0x1400727e6  push    r15
0x1400727e8  mov     rbp, rsp
0x1400727eb  sub     rsp, 50h
0x1400727ef  xor     esi, esi
0x1400727f1  mov     [rbp+Type], 3
0x1400727f8  mov     [rbp+hKey], rsi
0x1400727fc  mov     r12, r8
0x1400727ff  mov     [rbp+cbData], esi
0x140072802  mov     r14, rdx
0x140072805  mov     r13, rcx
0x140072808  test    rcx, rcx
0x14007280b  jz      loc_140072AA8
0x140072811  test    rdx, rdx
0x140072814  jz      loc_140072AA8
0x14007281a  test    r8, r8
0x14007281d  jz      loc_140072AA8
0x140072823  lea     rcx, [rbp+var_18]; this
0x140072827  call    ??0Low2MediumIntegrity@NSecurityLibrary@@QEAA@XZ; NSecurityLibrary::Low2MediumIntegrity::Low2MediumIntegrity(void)
0x14007282c  mov     ecx, 2001Fh
0x140072831  call    SplGetClientUserHandle
0x140072836  mov     r15, rax
0x140072839  test    rax, rax
0x14007283c  jnz     short loc_140072851
0x14007283e  call    cs:__imp_GetLastError
0x140072845  nop     dword ptr [rax+rax+00h]
0x14007284a  mov     ebx, eax
0x14007284c  jmp     loc_140072A51
0x140072851  mov     rdi, [r13+48h]
0x140072855  test    rdi, rdi
0x140072858  jz      loc_140072A3D
0x14007285e  cmp     word ptr [rdi], 5Ch ; '\'
0x140072862  jnz     loc_140072A3D
0x140072868  cmp     word ptr [rdi+2], 5Ch ; '\'
0x14007286d  jnz     loc_140072A3D
0x140072873  lea     r8, [rbp+hKey]; phkResult
0x140072877  mov     rdx, rdi; unsigned __int16 *
0x14007287a  mov     rcx, r15; hKey
0x14007287d  call    ?RegOpenConnectionKey@@YAKPEAUHKEY__@@PEAGPEAPEAU1@@Z; RegOpenConnectionKey(HKEY__ *,ushort *,HKEY__ * *)
0x140072882  mov     ebx, eax
0x140072884  test    eax, eax
0x140072886  jnz     loc_140072A26
0x14007288c  mov     rcx, [rbp+hKey]; hKey
0x140072890  lea     rax, [rbp+cbData]
0x140072894  mov     [rsp+50h+lpcbData], rax; lpcbData
0x140072899  lea     r9, [rbp+Type]; lpType
0x14007289d  xor     r8d, r8d; lpReserved
0x1400728a0  mov     [rsp+50h+lpData], rsi; lpData
0x1400728a5  lea     rdx, gszDefaultDevMode; "DefaultDevMode"
0x1400728ac  call    cs:__imp_RegQueryValueExW
0x1400728b3  nop     dword ptr [rax+rax+00h]
0x1400728b8  test    eax, eax
0x1400728ba  jz      loc_140072969
0x1400728c0  mov     rcx, [rbp+hKey]; hKey
0x1400728c4  call    cs:__imp_RegCloseKey
0x1400728cb  nop     dword ptr [rax+rax+00h]
0x1400728d0  lea     rdx, [rbp+hKey]; phkResult
0x1400728d4  mov     [rbp+hKey], rsi
0x1400728d8  mov     rcx, rdi; unsigned __int16 *
0x1400728db  call    ?RegOpenCachedConnectionKey@@YAKPEAGPEAPEAUHKEY__@@@Z; RegOpenCachedConnectionKey(ushort *,HKEY__ * *)
0x1400728e0  test    eax, eax
0x1400728e2  jnz     loc_140072A21
0x1400728e8  lea     rdx, aCouldNotFindDe; " Could not find DevMode under HKEY_CURR"...
0x1400728ef  lea     rcx, aGetcacheddefau; "GetCachedDefaultDevModeAndSize"
0x1400728f6  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400728fb  lea     rdx, aQueryTheRegist; " Query the registry for DevMode under H"...
0x140072902  lea     rcx, aGetcacheddefau; "GetCachedDefaultDevModeAndSize"
0x140072909  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14007290e  mov     rcx, [rbp+hKey]; hKey
0x140072912  lea     rax, [rbp+cbData]
0x140072916  mov     [rsp+50h+lpcbData], rax; lpcbData
0x14007291b  lea     r9, [rbp+Type]; lpType
0x14007291f  xor     r8d, r8d; lpReserved
0x140072922  mov     [rsp+50h+lpData], rsi; lpData
0x140072927  lea     rdx, gszDefaultDevMode; "DefaultDevMode"
0x14007292e  call    cs:__imp_RegQueryValueExW
0x140072935  nop     dword ptr [rax+rax+00h]
0x14007293a  mov     ebx, eax
0x14007293c  call    cs:__imp_GetLastError
0x140072943  nop     dword ptr [rax+rax+00h]
0x140072948  mov     r8d, ebx
0x14007294b  lea     rdx, aRegqueryvaluee; " RegQueryValueEx for gszDefaultDevMode "...
0x140072952  mov     r9d, eax
0x140072955  lea     rcx, aGetcacheddefau; "GetCachedDefaultDevModeAndSize"
0x14007295c  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140072961  test    ebx, ebx
0x140072963  jnz     loc_140072A21
0x140072969  cmp     [rbp+Type], 3
0x14007296d  jnz     loc_140072A21
0x140072973  mov     ecx, [rbp+cbData]; dwBytes
0x140072976  call    DllAllocSplMem
0x14007297b  mov     [r14], rax
0x14007297e  test    rax, rax
0x140072981  jnz     short loc_140072996
0x140072983  call    cs:__imp_GetLastError
0x14007298a  nop     dword ptr [rax+rax+00h]
0x14007298f  mov     ebx, eax
0x140072991  jmp     loc_140072A26
0x140072996  lea     rcx, [rbp+cbData]
0x14007299a  xor     r8d, r8d; lpReserved
0x14007299d  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x1400729a2  lea     r9, [rbp+Type]; lpType
0x1400729a6  mov     rcx, [rbp+hKey]; hKey
0x1400729aa  lea     rdx, gszDefaultDevMode; "DefaultDevMode"
0x1400729b1  mov     [rsp+50h+lpData], rax; lpData
0x1400729b6  call    cs:__imp_RegQueryValueExW
0x1400729bd  nop     dword ptr [rax+rax+00h]
0x1400729c2  mov     ebx, eax
0x1400729c4  call    cs:__imp_GetLastError
0x1400729cb  nop     dword ptr [rax+rax+00h]
0x1400729d0  mov     r8d, ebx
0x1400729d3  lea     rdx, aRegqueryvaluee_0; "RegQueryValueEx to fetch DevMode status"...
0x1400729da  mov     r9d, eax
0x1400729dd  lea     rcx, aGetcacheddefau; "GetCachedDefaultDevModeAndSize"
0x1400729e4  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400729e9  mov     eax, [rbp+cbData]
0x1400729ec  add     eax, 3
0x1400729ef  and     eax, 0FFFFFFFCh
0x1400729f2  mov     [r12], eax
0x1400729f6  test    ebx, ebx
0x1400729f8  jnz     short loc_1400729FF
0x1400729fa  lea     esi, [rbx+1]
0x1400729fd  jmp     short loc_140072A26
0x1400729ff  mov     r8, [r14]; lpMem
0x140072a02  test    r8, r8
0x140072a05  jz      short loc_140072A26
0x140072a07  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140072a0e  xor     edx, edx; dwFlags
0x140072a10  call    cs:__imp_HeapFree
0x140072a17  nop     dword ptr [rax+rax+00h]
0x140072a1c  mov     [r14], rsi
0x140072a1f  jmp     short loc_140072A26
0x140072a21  mov     ebx, 0Dh
0x140072a26  mov     rcx, [rbp+hKey]; hKey
0x140072a2a  test    rcx, rcx
0x140072a2d  jz      short loc_140072A42
0x140072a2f  call    cs:__imp_RegCloseKey
0x140072a36  nop     dword ptr [rax+rax+00h]
0x140072a3b  jmp     short loc_140072A42
0x140072a3d  mov     ebx, 709h
0x140072a42  mov     rcx, r15; hKey
0x140072a45  call    cs:__imp_RegCloseKey
0x140072a4c  nop     dword ptr [rax+rax+00h]
0x140072a51  test    ebx, ebx
0x140072a53  jz      short loc_140072A9D
0x140072a55  lea     rdx, aCouldNotFindDe_0; " Could not find DevMode in the registry"...
0x140072a5c  lea     rcx, aGetcacheddefau; "GetCachedDefaultDevModeAndSize"
0x140072a63  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140072a68  mov     r8, r12; unsigned int *
0x140072a6b  mov     rdx, r14; struct _devicemodeW **
0x140072a6e  mov     rcx, r13; void *
0x140072a71  call    ?GetDefaultDevModeAndSize@@YAHPEAXPEAPEAU_devicemodeW@@PEAK@Z; GetDefaultDevModeAndSize(void *,_devicemodeW * *,ulong *)
0x140072a76  mov     esi, eax
0x140072a78  call    cs:__imp_GetLastError
0x140072a7f  nop     dword ptr [rax+rax+00h]
0x140072a84  mov     r8d, esi
0x140072a87  lea     rdx, aGetdefaultdevm; " GetDefaultDevModeAndSize return %u, LE"...
0x140072a8e  mov     r9d, eax
0x140072a91  lea     rcx, aGetcacheddefau; "GetCachedDefaultDevModeAndSize"
0x140072a98  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140072a9d  lea     rcx, [rbp+var_18]; this
0x140072aa1  call    ??1Low2MediumIntegrity@NSecurityLibrary@@QEAA@XZ; NSecurityLibrary::Low2MediumIntegrity::~Low2MediumIntegrity(void)
0x140072aa6  jmp     short loc_140072AB9
0x140072aa8  mov     ecx, 57h ; 'W'; dwErrCode
0x140072aad  call    cs:__imp_SetLastError
0x140072ab4  nop     dword ptr [rax+rax+00h]
0x140072ab9  mov     rbx, [rsp+50h+arg_8]
0x140072ac1  mov     eax, esi
0x140072ac3  add     rsp, 50h
0x140072ac7  pop     r15
0x140072ac9  pop     r14
0x140072acb  pop     r13
0x140072acd  pop     r12
0x140072acf  pop     rdi
0x140072ad0  pop     rsi
0x140072ad1  pop     rbp
0x140072ad2  retn
```
