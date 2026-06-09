# WaitForPendingDriverUpdates

- ea: `0x180013744`
- end: `0x180013a38`
- name: `WaitForPendingDriverUpdates`
- size: `756`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800126cc`

## callees

- `0x180012ffc`
- `0x180013744`
- `0x180018970`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180013828`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180013828`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180013978`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180013978`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800137dc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800137dc`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001399b`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001399b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001391b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800139f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013a07`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001391b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800139f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013a07`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001390a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001390a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800137cb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800137cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013887`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013887`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013a10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013a10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800139bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800139bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800139e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800139e9`

## string_xrefs

- `0x18001376d`: `Software\Microsoft\Windows\CurrentVersion\Device Installer`

## pseudocode

```c
__int64 __fastcall WaitForPendingDriverUpdates(void *a1)
{
  DWORD LastError; // r15d
  BOOL v3; // r12d
  int v4; // edi
  int v5; // r14d
  unsigned __int64 EventW; // rbx
  DWORD v7; // eax
  DWORD v8; // esi
  DWORD v9; // eax
  HKEY v10; // rcx
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  HKEY v14; // [rsp+50h] [rbp-39h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-31h] BYREF
  DWORD Type; // [rsp+5Ch] [rbp-2Dh] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-21h] BYREF
  HANDLE Handles[2]; // [rsp+70h] [rbp-19h] BYREF
  _QWORD v20[2]; // [rsp+80h] [rbp-9h] BYREF

  memset(v20, 0, 12);
  Type = 0;
  LastError = 0;
  *(_OWORD *)Handles = 0;
  cbData = 0;
  v3 = 0;
  hKey = 0;
  v14 = 0;
  *(_QWORD *)Data = 0;
  RegCreateKeyExW(
    HKEY_LOCAL_MACHINE,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Device Installer",
    0,
    0,
    0,
    2u,
    0,
    &hKey,
    0);
  v4 = 0;
  v5 = 0;
  EventW = (unsigned __int64)CreateEventW(0, 1, 0, 0);
  while ( 1 )
  {
    Handles[0] = a1;
    Handles[1] = (HANDLE)(EventW & -(__int64)v3);
    v7 = WaitForMultipleObjectsEx((Handles[1] != 0) + 1, Handles, 0, Handles[1] != 0 ? -1 : 1000, 0);
    v8 = v7;
    if ( !v7 )
      break;
    v9 = v7 - 1;
    if ( v9 )
    {
      if ( v9 != 257 )
      {
        LastError = GetLastError();
        break;
      }
      v4 = 1;
    }
    else if ( !v4 )
    {
      break;
    }
    if ( hKey )
    {
      v10 = v14;
      if ( !v14 )
      {
        RegOpenKeyExW(hKey, L"CurrentStatus", 0, 0x2000000u, &v14);
        goto LABEL_10;
      }
LABEL_13:
      if ( !v5 )
      {
        v20[0] = 2;
        LODWORD(v20[1]) = 0;
        PreshutdownProgressCallback(v20);
        v10 = v14;
        v5 = 1;
      }
      *(_QWORD *)Data = 0;
      cbData = 8;
      v11 = RegQueryValueExW(v10, L"Progress", 0, &Type, Data, &cbData);
      if ( v11 == 1018 )
      {
LABEL_16:
        RegCloseKey(v14);
        v14 = 0;
      }
      else if ( !v11 && Type == 11 && cbData == 8 )
      {
        LODWORD(v20[1]) = *(_DWORD *)Data;
        HIDWORD(v20[0]) = *(_DWORD *)&Data[4];
        LODWORD(v20[0]) = 2;
        PreshutdownProgressCallback(v20);
        v3 = 0;
        if ( EventW )
        {
          if ( ResetEvent((HANDLE)EventW) )
          {
            v12 = RegNotifyChangeKeyValue(v14, 0, 4u, (HANDLE)EventW, 1);
            if ( v12 == 1018 )
              goto LABEL_16;
            v3 = v12 == 0;
          }
        }
      }
    }
    else
    {
LABEL_10:
      v10 = v14;
      if ( v14 )
        goto LABEL_13;
      if ( !v5 )
      {
        *(_QWORD *)((char *)v20 + 4) = 0;
        LODWORD(v20[0]) = 1;
        PreshutdownProgressCallback(v20);
      }
    }
  }
  v20[0] = 0xFFFFFFFF00000003uLL;
  LODWORD(v20[1]) = -1;
  PreshutdownProgressCallback(v20);
  if ( EventW )
    CloseHandle((HANDLE)EventW);
  if ( v14 )
    RegCloseKey(v14);
  if ( hKey )
    RegCloseKey(hKey);
  SetLastError(LastError);
  return v8;
}

```

## disassembly

```asm
0x180013744  push    rbp
0x180013746  push    rbx
0x180013747  push    rsi
0x180013748  push    rdi
0x180013749  push    r12
0x18001374b  push    r13
0x18001374d  push    r14
0x18001374f  push    r15
0x180013751  lea     rbp, [rsp-1Fh]
0x180013756  sub     rsp, 0A8h
0x18001375d  mov     rax, cs:__security_cookie
0x180013764  xor     rax, rsp
0x180013767  mov     [rbp+57h+var_50], rax
0x18001376b  xor     esi, esi
0x18001376d  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180013774  xor     eax, eax
0x180013776  mov     [rsp+0E0h+lpdwDisposition], rsi; lpdwDisposition
0x18001377b  mov     [rbp+57h+var_60], rax
0x18001377f  mov     r13, rcx
0x180013782  mov     [rbp+57h+var_58], eax
0x180013785  xorps   xmm0, xmm0
0x180013788  lea     rax, [rbp+57h+hKey]
0x18001378c  mov     [rbp+57h+Type], esi
0x18001378f  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180013794  xor     r9d, r9d; lpClass
0x180013797  mov     [rsp+0E0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18001379c  xor     r8d, r8d; Reserved
0x18001379f  mov     [rsp+0E0h+samDesired], 2; samDesired
0x1800137a7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800137ae  mov     [rsp+0E0h+dwOptions], esi; dwOptions
0x1800137b2  mov     r15d, esi
0x1800137b5  movups  xmmword ptr [rbp+57h+Handles], xmm0
0x1800137b9  mov     [rbp+57h+cbData], esi
0x1800137bc  mov     r12d, esi
0x1800137bf  mov     [rbp+57h+hKey], rsi
0x1800137c3  mov     [rbp+57h+var_90], rsi
0x1800137c7  mov     qword ptr [rbp+57h+Data], rsi
0x1800137cb  call    cs:__imp_RegCreateKeyExW
0x1800137d1  xor     r9d, r9d; lpName
0x1800137d4  lea     edx, [rsi+1]; bManualReset
0x1800137d7  xor     r8d, r8d; bInitialState
0x1800137da  xor     ecx, ecx; lpEventAttributes
0x1800137dc  call    cs:__imp_CreateEventW
0x1800137e2  mov     edi, esi
0x1800137e4  mov     r14d, esi
0x1800137e7  mov     rbx, rax
0x1800137ea  mov     eax, r12d
0x1800137ed  mov     [rbp+57h+Handles], r13
0x1800137f1  neg     eax
0x1800137f3  mov     [rsp+0E0h+dwOptions], esi; bAlertable
0x1800137f7  lea     rdx, [rbp+57h+Handles]; lpHandles
0x1800137fb  sbb     rcx, rcx
0x1800137fe  and     rcx, rbx
0x180013801  mov     rax, rcx
0x180013804  mov     [rbp+57h+Handles+8], rcx
0x180013808  neg     rax
0x18001380b  sbb     r9d, r9d
0x18001380e  and     r9d, 0FFFFFC17h
0x180013815  add     r9d, 3E8h; dwMilliseconds
0x18001381c  neg     rcx
0x18001381f  sbb     ecx, ecx
0x180013821  xor     r8d, r8d; bWaitAll
0x180013824  neg     ecx
0x180013826  inc     ecx; nCount
0x180013828  call    cs:__imp_WaitForMultipleObjectsEx
0x18001382e  mov     esi, eax
0x180013830  test    eax, eax
0x180013832  jz      loc_1800139C6
0x180013838  sub     eax, 1
0x18001383b  jz      short loc_18001384F
0x18001383d  cmp     eax, 101h
0x180013842  jnz     loc_1800139BD
0x180013848  mov     edi, 1
0x18001384d  jmp     short loc_180013857
0x18001384f  test    edi, edi
0x180013851  jz      loc_1800139C6
0x180013857  mov     rax, [rbp+57h+hKey]
0x18001385b  xor     esi, esi
0x18001385d  test    rax, rax
0x180013860  jz      short loc_18001388D
0x180013862  mov     rcx, [rbp+57h+var_90]
0x180013866  test    rcx, rcx
0x180013869  jnz     short loc_1800138BA
0x18001386b  lea     rcx, [rbp+57h+var_90]
0x18001386f  mov     r9d, 2000000h; samDesired
0x180013875  mov     qword ptr [rsp+0E0h+dwOptions], rcx; phkResult
0x18001387a  lea     rdx, aCurrentstatus; "CurrentStatus"
0x180013881  mov     rcx, rax; hKey
0x180013884  xor     r8d, r8d; ulOptions
0x180013887  call    cs:__imp_RegOpenKeyExW
0x18001388d  mov     rcx, [rbp+57h+var_90]
0x180013891  test    rcx, rcx
0x180013894  jnz     short loc_1800138BA
0x180013896  test    r14d, r14d
0x180013899  jnz     loc_1800137EA
0x18001389f  xor     edx, edx
0x1800138a1  mov     [rbp+57h+var_60+4], rsi
0x1800138a5  lea     rcx, [rbp+57h+var_60]
0x1800138a9  mov     dword ptr [rbp+57h+var_60], 1
0x1800138b0  call    PreshutdownProgressCallback
0x1800138b5  jmp     loc_1800137EA
0x1800138ba  test    r14d, r14d
0x1800138bd  jnz     short loc_1800138DF
0x1800138bf  xor     edx, edx
0x1800138c1  mov     [rbp+57h+var_60], 2
0x1800138c9  lea     rcx, [rbp+57h+var_60]
0x1800138cd  mov     [rbp+57h+var_58], esi
0x1800138d0  call    PreshutdownProgressCallback
0x1800138d5  mov     rcx, [rbp+57h+var_90]; hKey
0x1800138d9  mov     r14d, 1
0x1800138df  lea     rax, [rbp+57h+cbData]
0x1800138e3  mov     qword ptr [rbp+57h+Data], rsi
0x1800138e7  mov     qword ptr [rsp+0E0h+samDesired], rax; lpcbData
0x1800138ec  lea     r9, [rbp+57h+Type]; lpType
0x1800138f0  lea     rax, [rbp+57h+Data]
0x1800138f4  mov     [rbp+57h+cbData], 8
0x1800138fb  xor     r8d, r8d; lpReserved
0x1800138fe  mov     qword ptr [rsp+0E0h+dwOptions], rax; lpData
0x180013903  lea     rdx, aProgress; "Progress"
0x18001390a  call    cs:__imp_RegQueryValueExW
0x180013910  cmp     eax, 3FAh
0x180013915  jnz     short loc_18001392A
0x180013917  mov     rcx, [rbp+57h+var_90]; hKey
0x18001391b  call    cs:__imp_RegCloseKey
0x180013921  mov     [rbp+57h+var_90], rsi
0x180013925  jmp     loc_1800137EA
0x18001392a  test    eax, eax
0x18001392c  jnz     loc_1800137EA
0x180013932  cmp     [rbp+57h+Type], 0Bh
0x180013936  jnz     loc_1800137EA
0x18001393c  cmp     [rbp+57h+cbData], 8
0x180013940  jnz     loc_1800137EA
0x180013946  mov     rcx, qword ptr [rbp+57h+Data]
0x18001394a  xor     edx, edx
0x18001394c  mov     rax, rcx
0x18001394f  mov     [rbp+57h+var_58], ecx
0x180013952  shr     rax, 20h
0x180013956  lea     rcx, [rbp+57h+var_60]
0x18001395a  mov     dword ptr [rbp+57h+var_60+4], eax
0x18001395d  mov     dword ptr [rbp+57h+var_60], 2
0x180013964  call    PreshutdownProgressCallback
0x180013969  mov     r12d, esi
0x18001396c  test    rbx, rbx
0x18001396f  jz      loc_1800137EA
0x180013975  mov     rcx, rbx; hEvent
0x180013978  call    cs:__imp_ResetEvent
0x18001397e  test    eax, eax
0x180013980  jz      loc_1800137EA
0x180013986  mov     rcx, [rbp+57h+var_90]; hKey
0x18001398a  xor     edx, edx; bWatchSubtree
0x18001398c  mov     r9, rbx; hEvent
0x18001398f  mov     [rsp+0E0h+dwOptions], 1; fAsynchronous
0x180013997  lea     r8d, [rdx+4]; dwNotifyFilter
0x18001399b  call    cs:__imp_RegNotifyChangeKeyValue
0x1800139a1  cmp     eax, 3FAh
0x1800139a6  jz      loc_180013917
0x1800139ac  test    eax, eax
0x1800139ae  jnz     loc_1800137EA
0x1800139b4  lea     r12d, [rax+1]
0x1800139b8  jmp     loc_1800137EA
0x1800139bd  call    cs:__imp_GetLastError
0x1800139c3  mov     r15d, eax
0x1800139c6  or      eax, 0FFFFFFFFh
0x1800139c9  mov     dword ptr [rbp+57h+var_60], 3
0x1800139d0  xor     edx, edx
0x1800139d2  mov     dword ptr [rbp+57h+var_60+4], eax
0x1800139d5  lea     rcx, [rbp+57h+var_60]
0x1800139d9  mov     [rbp+57h+var_58], eax
0x1800139dc  call    PreshutdownProgressCallback
0x1800139e1  test    rbx, rbx
0x1800139e4  jz      short loc_1800139EF
0x1800139e6  mov     rcx, rbx; hObject
0x1800139e9  call    cs:__imp_CloseHandle
0x1800139ef  mov     rcx, [rbp+57h+var_90]; hKey
0x1800139f3  test    rcx, rcx
0x1800139f6  jz      short loc_1800139FE
0x1800139f8  call    cs:__imp_RegCloseKey
0x1800139fe  mov     rcx, [rbp+57h+hKey]; hKey
0x180013a02  test    rcx, rcx
0x180013a05  jz      short loc_180013A0D
0x180013a07  call    cs:__imp_RegCloseKey
0x180013a0d  mov     ecx, r15d; dwErrCode
0x180013a10  call    cs:__imp_SetLastError
0x180013a16  mov     eax, esi
0x180013a18  mov     rcx, [rbp+57h+var_50]
0x180013a1c  xor     rcx, rsp; StackCookie
0x180013a1f  call    __security_check_cookie
0x180013a24  add     rsp, 0A8h
0x180013a2b  pop     r15
0x180013a2d  pop     r14
0x180013a2f  pop     r13
0x180013a31  pop     r12
0x180013a33  pop     rdi
0x180013a34  pop     rsi
0x180013a35  pop     rbx
0x180013a36  pop     rbp
0x180013a37  retn
```
