# WdipDMConnect

- ea: `0x180002890`
- end: `0x180002b90`
- name: `WdipDMConnect`
- size: `768`
- prototype: `__int64 __fastcall(_OWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001980`
- `0x180003420`

## callees

- `0x180002890`
- `0x180002ba0`
- `0x18000f1c2`
- `0x18000f1f0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180002b1d`
- `ntdll!RtlNtStatusToDosError` at `0x180002b1d`
- `ntdll!RtlInitUnicodeString` at `0x1800029eb`
- `ntdll!RtlInitUnicodeString` at `0x1800029eb`
- `ntdll!NtAlpcConnectPort` at `0x180002b0c`
- `ntdll!NtAlpcConnectPort` at `0x180002b0c`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x180002a13`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x180002a13`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000291e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000291e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000297e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000297e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800029c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800029c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002a4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002b5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002a4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002b5a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002a60`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002a60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002b68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002b68`

## string_xrefs

- `0x180002b4e`: `clientcore\base\diagnosis\pdi\wdi\framework\library\communicationcli.cpp`
- `0x1800029b2`: `clientcore\base\diagnosis\pdi\wdi\framework\common\utils.cpp`
- `0x1800028c4`: `System\CurrentControlSet\Control\WDI\Config`

## pseudocode

```c
__int64 __fastcall WdipDMConnect(_OWORD *a1)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  int v4; // r8d
  LSTATUS v5; // eax
  _OWORD *v6; // rdi
  signed int v7; // eax
  int v8; // r8d
  HANDLE ProcessHeap; // rax
  _OWORD *v10; // rax
  int v11; // eax
  NTSTATUS v12; // eax
  bool v13; // sf
  HANDLE v14; // rax
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  __int64 v19; // [rsp+70h] [rbp-90h] BYREF
  __int64 v20; // [rsp+78h] [rbp-88h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  __int128 v22; // [rsp+90h] [rbp-70h] BYREF
  __int128 v23; // [rsp+A0h] [rbp-60h]
  __int128 v24; // [rsp+B0h] [rbp-50h]
  __int128 v25; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v26; // [rsp+D0h] [rbp-30h]
  __int128 v27; // [rsp+E0h] [rbp-20h]
  __int128 v28; // [rsp+F0h] [rbp-10h]
  __int64 v29; // [rsp+100h] [rbp+0h]
  WCHAR Data[128]; // [rsp+110h] [rbp+10h] BYREF

  cbData = 256;
  v29 = 0;
  v20 = 0;
  v19 = 0;
  hKey = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  DestinationString = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\WDI\\Config", 0, 0x20019u, &hKey);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 < 0 )
  {
    v4 = 718;
LABEL_11:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\utils.cpp",
      (int)L"WdipGetServerPortName",
      v4,
      (int)L"Error = %d",
      v3);
    goto LABEL_12;
  }
  if ( !hKey )
  {
    v3 = -2147467259;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\utils.cpp",
      (int)L"WdipGetServerPortName",
      720,
      (int)L"Error = %d",
      5);
    goto LABEL_12;
  }
  v5 = RegQueryValueExW(hKey, L"ServerName", 0, 0, (LPBYTE)Data, &cbData);
  v3 = v5;
  if ( v5 > 0 )
    v3 = (unsigned __int16)v5 | 0x80070000;
  if ( v3 < 0 )
  {
    v4 = 730;
    goto LABEL_11;
  }
LABEL_12:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v3 < 0 )
  {
    v6 = 0;
    LOBYTE(v7) = v3;
    v8 = 94;
LABEL_30:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\communicationcli.cpp",
      (int)L"WdipDMConnect",
      v8,
      (int)L"Error = %d",
      v7);
    goto LABEL_31;
  }
  RtlInitUnicodeString(&DestinationString, Data);
  LODWORD(v22) = 48;
  v24 = 0;
  *((_QWORD *)&v22 + 1) = 0;
  DWORD2(v23) = 0;
  *(_QWORD *)&v23 = 0;
  LODWORD(v25) = 393216;
  v26 = (unsigned __int64)AlpcMaxAllowedMessageLength();
  *((_QWORD *)&v25 + 1) = 0x100000001LL;
  v27 = 0u;
  v28 = 0u;
  DWORD1(v25) = 12;
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 8u, 0xF8u);
  v6 = v10;
  if ( !v10 )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\communicationcli.cpp",
      (int)L"WdipDMConnect",
      106,
      (int)L"Error = %d",
      14);
    goto LABEL_31;
  }
  memset_0(v10, 0, 0xF8u);
  v19 = 248;
  if ( a1 )
  {
    if ( v6 != (_OWORD *)-80LL )
      v6[5] = *a1;
    v11 = 6;
  }
  else
  {
    v11 = 7;
  }
  *((_DWORD *)v6 + 11) = v11;
  lpcbData = (LPDWORD)g_pLocalServSid;
  *((_DWORD *)v6 + 6) = 0;
  *(_QWORD *)v6 = 16253136;
  *((_QWORD *)v6 + 1) = 0;
  *((_QWORD *)v6 + 2) = 0;
  v12 = NtAlpcConnectPort(&v20, &DestinationString, &v22, &v25, 0x20000, lpcbData, v6, &v19, 0, 0, 0);
  if ( v12 < 0 )
  {
    v7 = RtlNtStatusToDosError(v12);
    v13 = v7 < 0;
    if ( v7 <= 0 )
      goto LABEL_28;
    v7 = (unsigned __int16)v7 | 0x80070000;
  }
  else
  {
    v7 = 0;
  }
  v13 = v7 < 0;
LABEL_28:
  if ( v13 )
  {
    v8 = 151;
    goto LABEL_30;
  }
LABEL_31:
  v14 = GetProcessHeap();
  HeapFree(v14, 0, v6);
  return v20;
}

```

## disassembly

```asm
0x180002890  push    rbp
0x180002892  push    rbx
0x180002893  push    rsi
0x180002894  push    rdi
0x180002895  push    r14
0x180002897  lea     rbp, [rsp-120h]
0x18000289f  sub     rsp, 220h
0x1800028a6  mov     rax, cs:__security_cookie
0x1800028ad  xor     rax, rsp
0x1800028b0  mov     [rbp+140h+var_30], rax
0x1800028b7  xorps   xmm0, xmm0
0x1800028ba  mov     [rsp+240h+cbData], 100h
0x1800028c2  xor     eax, eax
0x1800028c4  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\WDI"...
0x1800028cb  xor     r14d, r14d
0x1800028ce  mov     [rbp+140h+var_140], rax
0x1800028d2  lea     rax, [rsp+240h+hKey]
0x1800028d7  mov     [rsp+240h+var_1C8], r14
0x1800028dc  mov     rsi, rcx
0x1800028df  mov     [rsp+240h+phkResult], rax; phkResult
0x1800028e4  mov     r9d, 20019h; samDesired
0x1800028ea  mov     [rsp+240h+var_1D0], r14
0x1800028ef  xor     r8d, r8d; ulOptions
0x1800028f2  mov     [rsp+240h+hKey], r14
0x1800028f7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800028fe  movups  [rbp+140h+var_180], xmm0
0x180002902  movups  [rbp+140h+var_170], xmm0
0x180002906  movups  [rbp+140h+var_160], xmm0
0x18000290a  movups  [rbp+140h+var_150], xmm0
0x18000290e  movups  [rbp+140h+var_1B0], xmm0
0x180002912  movups  [rbp+140h+var_1A0], xmm0
0x180002916  movups  [rbp+140h+var_190], xmm0
0x18000291a  movups  xmmword ptr [rbp+140h+DestinationString.Length], xmm0
0x18000291e  call    cs:__imp_RegOpenKeyExW
0x180002924  mov     ebx, eax
0x180002926  test    eax, eax
0x180002928  jle     short loc_180002933
0x18000292a  movzx   ebx, ax
0x18000292d  or      ebx, 80070000h
0x180002933  test    ebx, ebx
0x180002935  jns     short loc_18000293F
0x180002937  mov     r8d, 2CEh
0x18000293d  jmp     short loc_18000299D
0x18000293f  mov     rcx, [rsp+240h+hKey]; hKey
0x180002944  test    rcx, rcx
0x180002947  jnz     short loc_18000295E
0x180002949  mov     ebx, 80004005h
0x18000294e  mov     dword ptr [rsp+240h+phkResult], 4005h
0x180002956  mov     r8d, 2D0h
0x18000295c  jmp     short loc_1800029A4
0x18000295e  lea     rax, [rsp+240h+cbData]
0x180002963  xor     r9d, r9d; lpType
0x180002966  mov     [rsp+240h+lpcbData], rax; lpcbData
0x18000296b  lea     rdx, aServername; "ServerName"
0x180002972  lea     rax, [rbp+140h+Data]
0x180002976  xor     r8d, r8d; lpReserved
0x180002979  mov     [rsp+240h+phkResult], rax; lpData
0x18000297e  call    cs:__imp_RegQueryValueExW
0x180002984  mov     ebx, eax
0x180002986  test    eax, eax
0x180002988  jle     short loc_180002993
0x18000298a  movzx   ebx, ax
0x18000298d  or      ebx, 80070000h
0x180002993  test    ebx, ebx
0x180002995  jns     short loc_1800029BE
0x180002997  mov     r8d, 2DAh; int
0x18000299d  movzx   eax, bx
0x1800029a0  mov     dword ptr [rsp+240h+phkResult], eax; Args
0x1800029a4  lea     r9, aErrorD_0; "Error = %d"
0x1800029ab  lea     rdx, aWdipgetserverp; "WdipGetServerPortName"
0x1800029b2  lea     rcx, aClientcoreBase_0; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800029b9  call    WdipTraceError
0x1800029be  mov     rcx, [rsp+240h+hKey]; hKey
0x1800029c3  test    rcx, rcx
0x1800029c6  jz      short loc_1800029CE
0x1800029c8  call    cs:__imp_RegCloseKey
0x1800029ce  test    ebx, ebx
0x1800029d0  jns     short loc_1800029E3
0x1800029d2  mov     rdi, r14
0x1800029d5  movzx   eax, bx
0x1800029d8  mov     r8d, 5Eh ; '^'
0x1800029de  jmp     loc_180002B3C
0x1800029e3  lea     rdx, [rbp+140h+Data]; SourceString
0x1800029e7  lea     rcx, [rbp+140h+DestinationString]; DestinationString
0x1800029eb  call    cs:__imp_RtlInitUnicodeString
0x1800029f1  xorps   xmm0, xmm0
0x1800029f4  mov     dword ptr [rbp+140h+var_1B0], 30h ; '0'
0x1800029fb  movdqu  [rbp+140h+var_190], xmm0
0x180002a00  mov     qword ptr [rbp+140h+var_1B0+8], r14
0x180002a04  mov     dword ptr [rbp+140h+var_1A0+8], r14d
0x180002a08  mov     qword ptr [rbp+140h+var_1A0], r14
0x180002a0c  mov     dword ptr [rbp+140h+var_180], 60000h
0x180002a13  call    cs:__imp_AlpcMaxAllowedMessageLength
0x180002a19  mov     qword ptr [rbp+140h+var_170], rax
0x180002a1d  xor     eax, eax
0x180002a1f  mov     qword ptr [rbp+140h+var_180+4], rax
0x180002a23  mov     qword ptr [rbp+140h+var_180+8], 1
0x180002a2b  mov     byte ptr [rbp+140h+var_180+0Ch], 1
0x180002a2f  mov     qword ptr [rbp+140h+var_160], r14
0x180002a33  mov     qword ptr [rbp+140h+var_160+8], r14
0x180002a37  mov     qword ptr [rbp+140h+var_150+8], r14
0x180002a3b  mov     qword ptr [rbp+140h+var_150], r14
0x180002a3f  mov     qword ptr [rbp+140h+var_170+8], r14
0x180002a43  mov     dword ptr [rbp+140h+var_180+4], 0Ch
0x180002a4a  call    cs:__imp_GetProcessHeap
0x180002a50  mov     ebx, 0F8h
0x180002a55  mov     edx, 8; dwFlags
0x180002a5a  mov     rcx, rax; hHeap
0x180002a5d  mov     r8d, ebx; dwBytes
0x180002a60  call    cs:__imp_HeapAlloc
0x180002a66  mov     rdi, rax
0x180002a69  test    rax, rax
0x180002a6c  jnz     short loc_180002A81
0x180002a6e  mov     dword ptr [rsp+240h+phkResult], 0Eh
0x180002a76  mov     r8d, 6Ah ; 'j'
0x180002a7c  jmp     loc_180002B40
0x180002a81  mov     r8, rbx; Size
0x180002a84  xor     edx, edx; Val
0x180002a86  mov     rcx, rdi; void *
0x180002a89  call    memset_0
0x180002a8e  mov     [rsp+240h+var_1D0], rbx
0x180002a93  test    rsi, rsi
0x180002a96  jz      short loc_180002AAE
0x180002a98  lea     rax, [rdi+50h]
0x180002a9c  test    rax, rax
0x180002a9f  jz      short loc_180002AA7
0x180002aa1  movups  xmm0, xmmword ptr [rsi]
0x180002aa4  movups  xmmword ptr [rax], xmm0
0x180002aa7  mov     eax, 6
0x180002aac  jmp     short loc_180002AB3
0x180002aae  mov     eax, 7
0x180002ab3  mov     [rdi+2Ch], eax
0x180002ab6  lea     r9, [rbp+140h+var_180]
0x180002aba  mov     [rsp+240h+var_1F0], r14
0x180002abf  lea     rax, [rsp+240h+var_1D0]
0x180002ac4  mov     [rsp+240h+var_1F8], r14
0x180002ac9  lea     r8, [rbp+140h+var_1B0]
0x180002acd  mov     [rsp+240h+var_200], r14
0x180002ad2  lea     rdx, [rbp+140h+DestinationString]
0x180002ad6  mov     [rsp+240h+var_208], rax
0x180002adb  lea     rcx, [rsp+240h+var_1C8]
0x180002ae0  mov     rax, cs:g_pLocalServSid
0x180002ae7  mov     [rsp+240h+var_210], rdi
0x180002aec  mov     [rsp+240h+lpcbData], rax
0x180002af1  mov     dword ptr [rsp+240h+phkResult], 20000h
0x180002af9  mov     [rdi+18h], r14d
0x180002afd  mov     qword ptr [rdi], 0F800D0h
0x180002b04  mov     [rdi+8], r14
0x180002b08  mov     [rdi+10h], r14
0x180002b0c  call    cs:__imp_NtAlpcConnectPort
0x180002b12  test    eax, eax
0x180002b14  js      short loc_180002B1B
0x180002b16  mov     eax, r14d
0x180002b19  jmp     short loc_180002B2F
0x180002b1b  mov     ecx, eax; Status
0x180002b1d  call    cs:__imp_RtlNtStatusToDosError
0x180002b23  test    eax, eax
0x180002b25  jle     short loc_180002B31
0x180002b27  movzx   eax, ax
0x180002b2a  or      eax, 80070000h
0x180002b2f  test    eax, eax
0x180002b31  jns     short loc_180002B5A
0x180002b33  movzx   eax, ax
0x180002b36  mov     r8d, 97h; int
0x180002b3c  mov     dword ptr [rsp+240h+phkResult], eax; Args
0x180002b40  lea     r9, aErrorD_0; "Error = %d"
0x180002b47  lea     rdx, aWdipdmconnect; "WdipDMConnect"
0x180002b4e  lea     rcx, aClientcoreBase; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180002b55  call    WdipTraceError
0x180002b5a  call    cs:__imp_GetProcessHeap
0x180002b60  mov     r8, rdi; lpMem
0x180002b63  xor     edx, edx; dwFlags
0x180002b65  mov     rcx, rax; hHeap
0x180002b68  call    cs:__imp_HeapFree
0x180002b6e  mov     rax, [rsp+240h+var_1C8]
0x180002b73  mov     rcx, [rbp+140h+var_30]
0x180002b7a  xor     rcx, rsp; StackCookie
0x180002b7d  call    __security_check_cookie
0x180002b82  add     rsp, 220h
0x180002b89  pop     r14
0x180002b8b  pop     rdi
0x180002b8c  pop     rsi
0x180002b8d  pop     rbx
0x180002b8e  pop     rbp
0x180002b8f  retn
```
