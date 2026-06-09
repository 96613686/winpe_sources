# GetCachedDefaultDevModeAndSize(void *,_devicemodeW * *,ulong *)

- ea: `0x14006bbc8`
- end: `0x14006be72`
- name: `?GetCachedDefaultDevModeAndSize@@YAHPEAXPEAPEAU_devicemodeW@@PEAK@Z`
- size: `682`
- prototype: `__int64 __fastcall(void *, struct _devicemodeW **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140005c30`

## callees

- `0x140002070`
- `0x140003c70`
- `0x1400041c0`
- `0x14000c0e0`
- `0x14000cd50`
- `0x140013fe8`
- `0x14006bbc8`
- `0x14006be78`
- `0x14006c004`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006bdcd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006bdcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006bc2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006bd14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006bd55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006bd87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006be23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006bc2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006bd14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006bd55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006bd87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006be23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006be52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006be52`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14006bc96`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14006bd0c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14006bd7f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14006bc96`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14006bd0c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14006bd7f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14006bca8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14006bde6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14006bdf6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14006bca8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14006bde6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14006bdf6`

## string_xrefs

- `0x14006bd1d`: ` RegQueryValueEx for gszDefaultDevMode completed with %u, LE: %d`
- `0x14006bd90`: `RegQueryValueEx to fetch DevMode status completed with %u, LE: %d`
- `0x14006bccd`: `GetCachedDefaultDevModeAndSize`
- `0x14006bce0`: `GetCachedDefaultDevModeAndSize`
- `0x14006bd27`: `GetCachedDefaultDevModeAndSize`
- `0x14006bd9a`: `GetCachedDefaultDevModeAndSize`
- `0x14006be07`: `GetCachedDefaultDevModeAndSize`
- `0x14006be36`: `GetCachedDefaultDevModeAndSize`
- `0x14006bcd9`: ` Query the registry for DevMode under HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wi NT\CurrentVersion\Print\Providers\Client Side Rendering Print Provider\<USER SID>\Printers\Connections\<printer name>\DefaultDevModes`
- `0x14006be00`: ` Could not find DevMode in the registry,Getting the Devmode from the printer driver`

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
0x14006bbc8  mov     [rsp-38h+arg_8], rbx
0x14006bbcd  push    rbp
0x14006bbce  push    rsi
0x14006bbcf  push    rdi
0x14006bbd0  push    r12
0x14006bbd2  push    r13
0x14006bbd4  push    r14
0x14006bbd6  push    r15
0x14006bbd8  mov     rbp, rsp
0x14006bbdb  sub     rsp, 50h
0x14006bbdf  xor     esi, esi
0x14006bbe1  mov     [rbp+Type], 3
0x14006bbe8  mov     [rbp+hKey], rsi
0x14006bbec  mov     r12, r8
0x14006bbef  mov     [rbp+cbData], esi
0x14006bbf2  mov     r14, rdx
0x14006bbf5  mov     r13, rcx
0x14006bbf8  test    rcx, rcx
0x14006bbfb  jz      loc_14006BE4D
0x14006bc01  test    rdx, rdx
0x14006bc04  jz      loc_14006BE4D
0x14006bc0a  test    r8, r8
0x14006bc0d  jz      loc_14006BE4D
0x14006bc13  lea     rcx, [rbp+var_18]; this
0x14006bc17  call    ??0Low2MediumIntegrity@NSecurityLibrary@@QEAA@XZ; NSecurityLibrary::Low2MediumIntegrity::Low2MediumIntegrity(void)
0x14006bc1c  mov     ecx, 2001Fh
0x14006bc21  call    SplGetClientUserHandle
0x14006bc26  mov     r15, rax
0x14006bc29  test    rax, rax
0x14006bc2c  jnz     short loc_14006BC3B
0x14006bc2e  call    cs:__imp_GetLastError
0x14006bc34  mov     ebx, eax
0x14006bc36  jmp     loc_14006BDFC
0x14006bc3b  mov     rdi, [r13+48h]
0x14006bc3f  test    rdi, rdi
0x14006bc42  jz      loc_14006BDEE
0x14006bc48  cmp     word ptr [rdi], 5Ch ; '\'
0x14006bc4c  jnz     loc_14006BDEE
0x14006bc52  cmp     word ptr [rdi+2], 5Ch ; '\'
0x14006bc57  jnz     loc_14006BDEE
0x14006bc5d  lea     r8, [rbp+hKey]; phkResult
0x14006bc61  mov     rdx, rdi; unsigned __int16 *
0x14006bc64  mov     rcx, r15; hKey
0x14006bc67  call    ?RegOpenConnectionKey@@YAKPEAUHKEY__@@PEAGPEAPEAU1@@Z; RegOpenConnectionKey(HKEY__ *,ushort *,HKEY__ * *)
0x14006bc6c  mov     ebx, eax
0x14006bc6e  test    eax, eax
0x14006bc70  jnz     loc_14006BDDD
0x14006bc76  mov     rcx, [rbp+hKey]; hKey
0x14006bc7a  lea     rax, [rbp+cbData]
0x14006bc7e  mov     [rsp+50h+lpcbData], rax; lpcbData
0x14006bc83  lea     r9, [rbp+Type]; lpType
0x14006bc87  xor     r8d, r8d; lpReserved
0x14006bc8a  mov     [rsp+50h+lpData], rsi; lpData
0x14006bc8f  lea     rdx, gszDefaultDevMode; "DefaultDevMode"
0x14006bc96  call    cs:__imp_RegQueryValueExW
0x14006bc9c  test    eax, eax
0x14006bc9e  jz      loc_14006BD3B
0x14006bca4  mov     rcx, [rbp+hKey]; hKey
0x14006bca8  call    cs:__imp_RegCloseKey
0x14006bcae  lea     rdx, [rbp+hKey]; phkResult
0x14006bcb2  mov     [rbp+hKey], rsi
0x14006bcb6  mov     rcx, rdi; unsigned __int16 *
0x14006bcb9  call    ?RegOpenCachedConnectionKey@@YAKPEAGPEAPEAUHKEY__@@@Z; RegOpenCachedConnectionKey(ushort *,HKEY__ * *)
0x14006bcbe  test    eax, eax
0x14006bcc0  jnz     loc_14006BDD8
0x14006bcc6  lea     rdx, aCouldNotFindDe; " Could not find DevMode under HKEY_CURR"...
0x14006bccd  lea     rcx, aGetcacheddefau; "GetCachedDefaultDevModeAndSize"
0x14006bcd4  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006bcd9  lea     rdx, aQueryTheRegist; " Query the registry for DevMode under H"...
0x14006bce0  lea     rcx, aGetcacheddefau; "GetCachedDefaultDevModeAndSize"
0x14006bce7  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006bcec  mov     rcx, [rbp+hKey]; hKey
0x14006bcf0  lea     rax, [rbp+cbData]
0x14006bcf4  mov     [rsp+50h+lpcbData], rax; lpcbData
0x14006bcf9  lea     r9, [rbp+Type]; lpType
0x14006bcfd  xor     r8d, r8d; lpReserved
0x14006bd00  mov     [rsp+50h+lpData], rsi; lpData
0x14006bd05  lea     rdx, gszDefaultDevMode; "DefaultDevMode"
0x14006bd0c  call    cs:__imp_RegQueryValueExW
0x14006bd12  mov     ebx, eax
0x14006bd14  call    cs:__imp_GetLastError
0x14006bd1a  mov     r8d, ebx
0x14006bd1d  lea     rdx, aRegqueryvaluee; " RegQueryValueEx for gszDefaultDevMode "...
0x14006bd24  mov     r9d, eax
0x14006bd27  lea     rcx, aGetcacheddefau; "GetCachedDefaultDevModeAndSize"
0x14006bd2e  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006bd33  test    ebx, ebx
0x14006bd35  jnz     loc_14006BDD8
0x14006bd3b  cmp     [rbp+Type], 3
0x14006bd3f  jnz     loc_14006BDD8
0x14006bd45  mov     ecx, [rbp+cbData]; dwBytes
0x14006bd48  call    DllAllocSplMem
0x14006bd4d  mov     [r14], rax
0x14006bd50  test    rax, rax
0x14006bd53  jnz     short loc_14006BD5F
0x14006bd55  call    cs:__imp_GetLastError
0x14006bd5b  mov     ebx, eax
0x14006bd5d  jmp     short loc_14006BDDD
0x14006bd5f  lea     rcx, [rbp+cbData]
0x14006bd63  xor     r8d, r8d; lpReserved
0x14006bd66  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x14006bd6b  lea     r9, [rbp+Type]; lpType
0x14006bd6f  mov     rcx, [rbp+hKey]; hKey
0x14006bd73  lea     rdx, gszDefaultDevMode; "DefaultDevMode"
0x14006bd7a  mov     [rsp+50h+lpData], rax; lpData
0x14006bd7f  call    cs:__imp_RegQueryValueExW
0x14006bd85  mov     ebx, eax
0x14006bd87  call    cs:__imp_GetLastError
0x14006bd8d  mov     r8d, ebx
0x14006bd90  lea     rdx, aRegqueryvaluee_0; "RegQueryValueEx to fetch DevMode status"...
0x14006bd97  mov     r9d, eax
0x14006bd9a  lea     rcx, aGetcacheddefau; "GetCachedDefaultDevModeAndSize"
0x14006bda1  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006bda6  mov     eax, [rbp+cbData]
0x14006bda9  add     eax, 3
0x14006bdac  and     eax, 0FFFFFFFCh
0x14006bdaf  mov     [r12], eax
0x14006bdb3  test    ebx, ebx
0x14006bdb5  jnz     short loc_14006BDBC
0x14006bdb7  lea     esi, [rbx+1]
0x14006bdba  jmp     short loc_14006BDDD
0x14006bdbc  mov     r8, [r14]; lpMem
0x14006bdbf  test    r8, r8
0x14006bdc2  jz      short loc_14006BDDD
0x14006bdc4  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14006bdcb  xor     edx, edx; dwFlags
0x14006bdcd  call    cs:__imp_HeapFree
0x14006bdd3  mov     [r14], rsi
0x14006bdd6  jmp     short loc_14006BDDD
0x14006bdd8  mov     ebx, 0Dh
0x14006bddd  mov     rcx, [rbp+hKey]; hKey
0x14006bde1  test    rcx, rcx
0x14006bde4  jz      short loc_14006BDF3
0x14006bde6  call    cs:__imp_RegCloseKey
0x14006bdec  jmp     short loc_14006BDF3
0x14006bdee  mov     ebx, 709h
0x14006bdf3  mov     rcx, r15; hKey
0x14006bdf6  call    cs:__imp_RegCloseKey
0x14006bdfc  test    ebx, ebx
0x14006bdfe  jz      short loc_14006BE42
0x14006be00  lea     rdx, aCouldNotFindDe_0; " Could not find DevMode in the registry"...
0x14006be07  lea     rcx, aGetcacheddefau; "GetCachedDefaultDevModeAndSize"
0x14006be0e  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006be13  mov     r8, r12; unsigned int *
0x14006be16  mov     rdx, r14; struct _devicemodeW **
0x14006be19  mov     rcx, r13; void *
0x14006be1c  call    ?GetDefaultDevModeAndSize@@YAHPEAXPEAPEAU_devicemodeW@@PEAK@Z; GetDefaultDevModeAndSize(void *,_devicemodeW * *,ulong *)
0x14006be21  mov     esi, eax
0x14006be23  call    cs:__imp_GetLastError
0x14006be29  mov     r8d, esi
0x14006be2c  lea     rdx, aGetdefaultdevm; " GetDefaultDevModeAndSize return %u, LE"...
0x14006be33  mov     r9d, eax
0x14006be36  lea     rcx, aGetcacheddefau; "GetCachedDefaultDevModeAndSize"
0x14006be3d  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006be42  lea     rcx, [rbp+var_18]; this
0x14006be46  call    ??1Low2MediumIntegrity@NSecurityLibrary@@QEAA@XZ; NSecurityLibrary::Low2MediumIntegrity::~Low2MediumIntegrity(void)
0x14006be4b  jmp     short loc_14006BE58
0x14006be4d  mov     ecx, 57h ; 'W'; dwErrCode
0x14006be52  call    cs:__imp_SetLastError
0x14006be58  mov     rbx, [rsp+50h+arg_8]
0x14006be60  mov     eax, esi
0x14006be62  add     rsp, 50h
0x14006be66  pop     r15
0x14006be68  pop     r14
0x14006be6a  pop     r13
0x14006be6c  pop     r12
0x14006be6e  pop     rdi
0x14006be6f  pop     rsi
0x14006be70  pop     rbp
0x14006be71  retn
```
