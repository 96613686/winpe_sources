# SampRecordSystemSchemaVerisonInRegistry

- ea: `0x1800991b0`
- end: `0x18009939d`
- name: `SampRecordSystemSchemaVerisonInRegistry`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800975e0`

## callees

- `0x180027e24`
- `0x18002cd80`
- `0x1800955e0`
- `0x1800991b0`
- `0x1800bb764`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800992c6`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800992c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800991ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800991ff`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180099308`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180099308`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180099334`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180099334`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180099346`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180099346`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800991ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800991ed`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1800992a6`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1800992a6`

## string_xrefs

- `0x1800992e3`: `System\CurrentControlSet\Services\NTDS\Parameters`

## pseudocode

```c
__int64 SampRecordSystemSchemaVerisonInRegistry()
{
  unsigned int v0; // ebx
  DWORD LastError; // eax
  __int64 v2; // r8
  WCHAR *v3; // rax
  __int64 v4; // rdx
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR ReturnedString[32]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[264]; // [rsp+A0h] [rbp-60h] BYREF

  hKey = 0;
  *(_DWORD *)Data = 0;
  if ( !GetSystemDirectoryW(Buffer, 0x105u) )
  {
    v0 = 0;
    LastError = GetLastError();
    goto LABEL_12;
  }
  v2 = 261;
  v3 = Buffer;
  do
  {
    if ( !*v3 )
      break;
    ++v3;
    --v2;
  }
  while ( v2 );
  v0 = v2 == 0 ? 0xC000000D : 0;
  if ( v2 )
  {
    v4 = (261 - v2) & ((unsigned __int128)-(__int128)(unsigned __int64)v2 >> 64);
    v0 = RtlStringCopyWorkerW_0((unsigned int)&Buffer[v4], 261 - (int)v4, 0, (unsigned int)L"\\schema.ini", 2147483646);
    if ( (v0 & 0x80000000) == 0 )
    {
      GetPrivateProfileStringW(L"SCHEMA", L"objectVersion", L"NOT_FOUND", ReturnedString, 0x20u, Buffer);
      if ( !wcscmp_0(ReturnedString, L"NOT_FOUND")
        || (*(_DWORD *)Data = _o__wtoi(ReturnedString)) == 0
        || RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\NTDS\\Parameters",
             0,
             0,
             0,
             0x2000000u,
             0,
             &hKey,
             0) )
      {
LABEL_13:
        v0 = -1073741823;
        goto LABEL_14;
      }
      LastError = RegSetValueExW(hKey, L"System Schema Version", 0, 4u, Data, 4u);
LABEL_12:
      if ( !LastError )
        goto LABEL_14;
      goto LABEL_13;
    }
  }
LABEL_14:
  if ( RegCloseKey(hKey) )
    v0 = -1073741823;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 27, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids, v0, v0);
  return v0;
}

```

## disassembly

```asm
0x1800991b0  push    rbp
0x1800991b2  push    rbx
0x1800991b3  push    rsi
0x1800991b4  push    rdi
0x1800991b5  push    r14
0x1800991b7  lea     rbp, [rsp-1C0h]
0x1800991bf  sub     rsp, 2C0h
0x1800991c6  mov     rax, cs:__security_cookie
0x1800991cd  xor     rax, rsp
0x1800991d0  mov     [rbp+1E0h+var_30], rax
0x1800991d7  xor     esi, esi
0x1800991d9  lea     rcx, [rbp+1E0h+Buffer]; lpBuffer
0x1800991dd  mov     edi, 105h
0x1800991e2  mov     [rsp+2E0h+hKey], rsi
0x1800991e7  mov     edx, edi; uSize
0x1800991e9  mov     dword ptr [rsp+2E0h+Data], esi
0x1800991ed  call    cs:__imp_GetSystemDirectoryW
0x1800991f3  mov     r14d, 0C0000001h
0x1800991f9  test    eax, eax
0x1800991fb  jnz     short loc_18009920A
0x1800991fd  mov     ebx, esi
0x1800991ff  call    cs:__imp_GetLastError
0x180099205  jmp     loc_18009933A
0x18009920a  mov     r8, rdi
0x18009920d  lea     rax, [rbp+1E0h+Buffer]
0x180099211  cmp     [rax], si
0x180099214  jz      short loc_180099220
0x180099216  add     rax, 2
0x18009921a  sub     r8, 1
0x18009921e  jnz     short loc_180099211
0x180099220  mov     rax, r8
0x180099223  mov     rcx, rdi
0x180099226  neg     rax
0x180099229  mov     rax, r8
0x18009922c  sbb     ebx, ebx
0x18009922e  sub     rcx, r8
0x180099231  not     ebx
0x180099233  and     ebx, 0C000000Dh
0x180099239  neg     rax
0x18009923c  sbb     rdx, rdx
0x18009923f  and     rdx, rcx
0x180099242  test    r8, r8
0x180099245  jz      loc_180099341
0x18009924b  sub     rdi, rdx
0x18009924e  mov     qword ptr [rsp+2E0h+nSize], 7FFFFFFEh
0x180099257  lea     rcx, [rbp+1E0h+Buffer]
0x18009925b  xor     r8d, r8d
0x18009925e  lea     rcx, [rcx+rdx*2]
0x180099262  mov     rdx, rdi
0x180099265  lea     r9, aSchemaIni; "\\schema.ini"
0x18009926c  call    RtlStringCopyWorkerW_0
0x180099271  mov     ebx, eax
0x180099273  test    eax, eax
0x180099275  js      loc_180099341
0x18009927b  lea     rax, [rbp+1E0h+Buffer]
0x18009927f  mov     [rsp+2E0h+lpFileName], rax; lpFileName
0x180099284  lea     r9, [rsp+2E0h+ReturnedString]; lpReturnedString
0x180099289  lea     r8, aNotFound; "NOT_FOUND"
0x180099290  mov     [rsp+2E0h+nSize], 20h ; ' '; nSize
0x180099298  lea     rdx, aObjectversion; "objectVersion"
0x18009929f  lea     rcx, AppName; "SCHEMA"
0x1800992a6  call    cs:__imp_GetPrivateProfileStringW
0x1800992ac  lea     rdx, aNotFound; "NOT_FOUND"
0x1800992b3  lea     rcx, [rsp+2E0h+ReturnedString]; String1
0x1800992b8  call    wcscmp_0
0x1800992bd  test    eax, eax
0x1800992bf  jz      short loc_18009933E
0x1800992c1  lea     rcx, [rsp+2E0h+ReturnedString]
0x1800992c6  call    cs:__imp__o__wtoi
0x1800992cc  mov     dword ptr [rsp+2E0h+Data], eax
0x1800992d0  test    eax, eax
0x1800992d2  jz      short loc_18009933E
0x1800992d4  mov     [rsp+2E0h+lpdwDisposition], rsi; lpdwDisposition
0x1800992d9  lea     rax, [rsp+2E0h+hKey]
0x1800992de  mov     [rsp+2E0h+phkResult], rax; phkResult
0x1800992e3  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\NT"...
0x1800992ea  mov     [rsp+2E0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800992ef  xor     r9d, r9d; lpClass
0x1800992f2  mov     dword ptr [rsp+2E0h+lpFileName], 2000000h; samDesired
0x1800992fa  xor     r8d, r8d; Reserved
0x1800992fd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180099304  mov     [rsp+2E0h+nSize], esi; dwOptions
0x180099308  call    cs:__imp_RegCreateKeyExW
0x18009930e  test    eax, eax
0x180099310  jnz     short loc_18009933E
0x180099312  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180099317  lea     r9d, [rax+4]; dwType
0x18009931b  lea     rax, [rsp+2E0h+Data]
0x180099320  mov     dword ptr [rsp+2E0h+lpFileName], r9d; cbData
0x180099325  xor     r8d, r8d; Reserved
0x180099328  mov     qword ptr [rsp+2E0h+nSize], rax; lpData
0x18009932d  lea     rdx, aSystemSchemaVe; "System Schema Version"
0x180099334  call    cs:__imp_RegSetValueExW
0x18009933a  test    eax, eax
0x18009933c  jz      short loc_180099341
0x18009933e  mov     ebx, r14d
0x180099341  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180099346  call    cs:__imp_RegCloseKey
0x18009934c  test    eax, eax
0x18009934e  cmovnz  ebx, r14d
0x180099352  mov     rcx, cs:WPP_GLOBAL_Control
0x180099359  test    dword ptr [rcx+44h], 20000h
0x180099360  jz      short loc_18009937E
0x180099362  mov     rcx, [rcx+38h]
0x180099366  lea     r8, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids
0x18009936d  mov     edx, 1Bh
0x180099372  mov     [rsp+2E0h+nSize], ebx
0x180099376  mov     r9d, ebx
0x180099379  call    WPP_SF_Dd
0x18009937e  mov     eax, ebx
0x180099380  mov     rcx, [rbp+1E0h+var_30]
0x180099387  xor     rcx, rsp; StackCookie
0x18009938a  call    __security_check_cookie
0x18009938f  add     rsp, 2C0h
0x180099396  pop     r14
0x180099398  pop     rdi
0x180099399  pop     rsi
0x18009939a  pop     rbx
0x18009939b  pop     rbp
0x18009939c  retn
```
