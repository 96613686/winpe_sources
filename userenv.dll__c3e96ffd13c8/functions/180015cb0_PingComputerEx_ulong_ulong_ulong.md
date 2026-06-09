# PingComputerEx(ulong,ulong *,ulong *)

- ea: `0x180015cb0`
- end: `0x18001608b`
- name: `?PingComputerEx@@YAKKPEAK0@Z`
- size: `987`
- prototype: `__int64 __fastcall(IPAddr DestinationAddress, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800181b0`

## callees

- `0x18000d9b0`
- `0x18000e330`
- `0x180015618`
- `0x180015cb0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180015e5a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180015e5a`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180015e68`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180015e68`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180015e45`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180015e45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015d81`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015de8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015d81`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015de8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015d51`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015db4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015d51`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015db4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015d94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015df3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015d94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015df3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016059`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016059`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015e21`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015e21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015efb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015fc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015efb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015fc3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015ede`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015ede`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001604c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001604c`
- `IPHLPAPI!IcmpCreateFile` at `0x180015eec`
- `IPHLPAPI!IcmpCreateFile` at `0x180015eec`
- `IPHLPAPI!IcmpCloseHandle` at `0x180016043`
- `IPHLPAPI!IcmpCloseHandle` at `0x180016043`
- `IPHLPAPI!GetBestInterface` at `0x180015eac`
- `IPHLPAPI!GetBestInterface` at `0x180015eac`
- `IPHLPAPI!IcmpSendEcho` at `0x180015f3e`
- `IPHLPAPI!IcmpSendEcho` at `0x180015fb7`
- `IPHLPAPI!IcmpSendEcho` at `0x180015f3e`
- `IPHLPAPI!IcmpSendEcho` at `0x180015fb7`
- `IPHLPAPI!GetIfEntry` at `0x180015ebb`
- `IPHLPAPI!GetIfEntry` at `0x180015ebb`

## string_xrefs

- `0x180015dcd`: `FastWanLink`

## pseudocode

```c
__int64 __fastcall PingComputerEx(IPAddr DestinationAddress, unsigned int *a2, unsigned int *a3)
{
  IPAddr v4; // r14d
  unsigned int v5; // r12d
  __int64 result; // rax
  HRSRC Resource; // rax
  HGLOBAL v8; // rax
  void *v9; // rax
  DWORD LastError; // ebx
  int ReplySize; // ebx
  _DWORD *v12; // rdi
  HANDLE File; // rsi
  unsigned int v14; // r15d
  unsigned int v15; // r13d
  bool v16; // zf
  unsigned int v17; // r14d
  bool v18; // zf
  unsigned int v19; // eax
  BYTE Data[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v21; // [rsp+44h] [rbp-BCh]
  IPAddr DestinationAddressa; // [rsp+48h] [rbp-B8h]
  BYTE v23[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD lpcbData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE cbData[12]; // [rsp+54h] [rbp-ACh] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int *v27; // [rsp+68h] [rbp-98h]
  _MIB_IFROW pIfRow; // [rsp+70h] [rbp-90h] BYREF

  v27 = a2;
  v4 = DestinationAddress;
  DestinationAddressa = DestinationAddress;
  v5 = 0;
  lpcbData = 0;
  memset_0(&pIfRow, 0, sizeof(pIfRow));
  *(_DWORD *)&cbData[8] = 0;
  phkResult = 0;
  *(_DWORD *)v23 = 0;
  *(_DWORD *)Data = 2048;
  *(_QWORD *)cbData = 4;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
          0,
          0x20019u,
          (PHKEY)&cbData[4]) )
  {
    if ( RegQueryValueExW(*(HKEY *)&cbData[4], L"PingBufferSize", 0, 0, Data, (LPDWORD)cbData) )
      *(_DWORD *)Data = 2048;
    RegCloseKey(*(HKEY *)&cbData[4]);
  }
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
          0,
          0x20019u,
          &phkResult) )
  {
    lpcbData = 4;
    RegQueryValueExW(phkResult, L"FastWanLink", 0, 0, v23, &lpcbData);
    RegCloseKey(phkResult);
  }
  if ( (unsigned int)(*(_DWORD *)Data - 500) > 0x60C )
    *(_DWORD *)Data = 2048;
  result = InitializePingCritSec();
  if ( (_DWORD)result )
    return result;
  EnterCriticalSection(g_PingCritSec);
  if ( !g_lpTestData )
  {
    Resource = FindResourceExW(g_hDllInstance, L"JPEG", (LPCWSTR)1, 0);
    if ( Resource && (v8 = LoadResource(g_hDllInstance, Resource)) != 0 )
    {
      v9 = LockResource(v8);
      g_lpTestData = v9;
    }
    else
    {
      v9 = g_lpTestData;
    }
    if ( !v9 )
      goto LABEL_16;
  }
  memset_0(&pIfRow, 0, sizeof(pIfRow));
  if ( !GetBestInterface(v4, &pIfRow.dwIndex) )
    GetIfEntry(&pIfRow);
  *a2 = pIfRow.dwSpeed >> 10;
  ReplySize = *(_DWORD *)Data + 48;
  v21 = *(_DWORD *)Data + 48;
  v12 = LocalAlloc(0x40u, (unsigned int)(*(_DWORD *)Data + 48));
  if ( !v12 )
  {
LABEL_16:
    LastError = GetLastError();
    goto LABEL_49;
  }
  File = IcmpCreateFile();
  if ( File == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    goto LABEL_48;
  }
  v14 = 0;
  v15 = 0;
  while ( v5 < 3 )
  {
    if ( IcmpSendEcho(File, v4, g_lpTestData, 0, 0, v12, ReplySize, 0x1388u) )
    {
      if ( !v12[1] )
      {
        v17 = v12[2];
        LastError = 0;
        if ( v17 < 0xA && !*(_DWORD *)v23 )
          goto LABEL_47;
        if ( IcmpSendEcho(File, DestinationAddressa, g_lpTestData, *(WORD *)Data, 0, v12, v21, 0x1388u) )
        {
          if ( v12[1] )
          {
            v18 = v12[1] == 11003;
            goto LABEL_34;
          }
          v19 = v12[2];
          if ( v19 < 0xA && !*(_DWORD *)v23 )
            goto LABEL_47;
          if ( v17 < v19 )
          {
            v14 += v19 - v17;
            ++v15;
          }
        }
        else
        {
          v18 = GetLastError() == 11003;
LABEL_34:
          if ( v18 )
          {
LABEL_27:
            LastError = 53;
            goto LABEL_47;
          }
        }
        v4 = DestinationAddressa;
        ReplySize = v21;
        goto LABEL_43;
      }
      v16 = v12[1] == 11003;
    }
    else
    {
      v16 = GetLastError() == 11003;
    }
    if ( v16 )
      goto LABEL_27;
LABEL_43:
    ++v5;
  }
  if ( v14 )
  {
    LastError = 0;
    *v27 = ((2000 * *(_DWORD *)Data / (v14 / v15)) >> 7) & 0x3FFFFF;
  }
  else
  {
    LastError = 59;
  }
LABEL_47:
  IcmpCloseHandle(File);
LABEL_48:
  LocalFree(v12);
LABEL_49:
  LeaveCriticalSection(g_PingCritSec);
  return LastError;
}

```

## disassembly

```asm
0x180015cb0  mov     [rsp-8+arg_10], rbx
0x180015cb5  push    rbp
0x180015cb6  push    rsi
0x180015cb7  push    rdi
0x180015cb8  push    r12
0x180015cba  push    r13
0x180015cbc  push    r14
0x180015cbe  push    r15
0x180015cc0  lea     rbp, [rsp-2E0h]
0x180015cc8  sub     rsp, 3E0h
0x180015ccf  mov     rax, cs:__security_cookie
0x180015cd6  xor     rax, rsp
0x180015cd9  mov     [rbp+310h+var_40], rax
0x180015ce0  mov     rbx, rdx
0x180015ce3  mov     [rsp+410h+var_3A8], rdx
0x180015ce8  mov     r14d, ecx
0x180015ceb  mov     [rsp+410h+DestinationAddress], ecx
0x180015cef  xor     r12d, r12d
0x180015cf2  lea     rcx, [rsp+410h+pIfRow]; void *
0x180015cf7  xor     edx, edx; Val
0x180015cf9  mov     [rsp+410h+var_3C0], r12d
0x180015cfe  mov     r8d, 35Ch; Size
0x180015d04  call    memset_0
0x180015d09  lea     rax, [rsp+410h+hKey]
0x180015d0e  mov     [rsp+410h+hKey], r12
0x180015d13  mov     r15d, 20019h
0x180015d19  mov     [rsp+410h+phkResult], rax; phkResult
0x180015d1e  mov     r13, 0FFFFFFFF80000002h
0x180015d25  mov     [rsp+410h+var_3B0], r12
0x180015d2a  mov     edi, 800h
0x180015d2f  mov     dword ptr [rsp+410h+var_3C4], r12d
0x180015d34  lea     esi, [r12+4]
0x180015d39  mov     dword ptr [rsp+410h+Data], edi
0x180015d3d  mov     r9d, r15d; samDesired
0x180015d40  mov     [rsp+410h+cbData], esi
0x180015d44  mov     rcx, r13; hKey
0x180015d47  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x180015d4e  xor     r8d, r8d; ulOptions
0x180015d51  call    cs:__imp_RegOpenKeyExW
0x180015d57  test    eax, eax
0x180015d59  jnz     short loc_180015D9A
0x180015d5b  mov     rcx, [rsp+410h+hKey]; hKey
0x180015d60  lea     rax, [rsp+410h+cbData]
0x180015d65  mov     [rsp+410h+lpcbData], rax; lpcbData
0x180015d6a  lea     rdx, ValueName; "PingBufferSize"
0x180015d71  lea     rax, [rsp+410h+Data]
0x180015d76  xor     r9d, r9d; lpType
0x180015d79  xor     r8d, r8d; lpReserved
0x180015d7c  mov     [rsp+410h+phkResult], rax; lpData
0x180015d81  call    cs:__imp_RegQueryValueExW
0x180015d87  test    eax, eax
0x180015d89  jz      short loc_180015D8F
0x180015d8b  mov     dword ptr [rsp+410h+Data], edi
0x180015d8f  mov     rcx, [rsp+410h+hKey]; hKey
0x180015d94  call    cs:__imp_RegCloseKey
0x180015d9a  lea     rax, [rsp+410h+var_3B0]
0x180015d9f  mov     r9d, r15d; samDesired
0x180015da2  xor     r8d, r8d; ulOptions
0x180015da5  mov     [rsp+410h+phkResult], rax; phkResult
0x180015daa  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x180015db1  mov     rcx, r13; hKey
0x180015db4  call    cs:__imp_RegOpenKeyExW
0x180015dba  test    eax, eax
0x180015dbc  jnz     short loc_180015DF9
0x180015dbe  mov     rcx, [rsp+410h+var_3B0]; hKey
0x180015dc3  lea     rax, [rsp+410h+var_3C0]
0x180015dc8  mov     [rsp+410h+lpcbData], rax; lpcbData
0x180015dcd  lea     rdx, aFastwanlink; "FastWanLink"
0x180015dd4  lea     rax, [rsp+410h+var_3C4]
0x180015dd9  mov     [rsp+410h+var_3C0], esi
0x180015ddd  xor     r9d, r9d; lpType
0x180015de0  mov     [rsp+410h+phkResult], rax; lpData
0x180015de5  xor     r8d, r8d; lpReserved
0x180015de8  call    cs:__imp_RegQueryValueExW
0x180015dee  mov     rcx, [rsp+410h+var_3B0]; hKey
0x180015df3  call    cs:__imp_RegCloseKey
0x180015df9  mov     eax, dword ptr [rsp+410h+Data]
0x180015dfd  add     eax, 0FFFFFE0Ch
0x180015e02  cmp     eax, 60Ch
0x180015e07  jbe     short loc_180015E0D
0x180015e09  mov     dword ptr [rsp+410h+Data], edi
0x180015e0d  call    ?InitializePingCritSec@@YAKXZ; InitializePingCritSec(void)
0x180015e12  test    eax, eax
0x180015e14  jnz     loc_180016061
0x180015e1a  mov     rcx, cs:?g_PingCritSec@@3PEAU_RTL_CRITICAL_SECTION@@EA; lpCriticalSection
0x180015e21  call    cs:__imp_EnterCriticalSection
0x180015e27  cmp     cs:?g_lpTestData@@3PEAXEA, r12; void * g_lpTestData
0x180015e2e  jnz     short loc_180015E90
0x180015e30  mov     rcx, cs:g_hDllInstance; hModule
0x180015e37  lea     rdx, Type; "JPEG"
0x180015e3e  xor     r9d, r9d; wLanguage
0x180015e41  lea     r8d, [r9+1]; lpName
0x180015e45  call    cs:__imp_FindResourceExW
0x180015e4b  test    rax, rax
0x180015e4e  jz      short loc_180015E77
0x180015e50  mov     rcx, cs:g_hDllInstance; hModule
0x180015e57  mov     rdx, rax; hResInfo
0x180015e5a  call    cs:__imp_LoadResource
0x180015e60  test    rax, rax
0x180015e63  jz      short loc_180015E77
0x180015e65  mov     rcx, rax; hResData
0x180015e68  call    cs:__imp_LockResource
0x180015e6e  mov     cs:?g_lpTestData@@3PEAXEA, rax; void * g_lpTestData
0x180015e75  jmp     short loc_180015E7E
0x180015e77  mov     rax, cs:?g_lpTestData@@3PEAXEA; void * g_lpTestData
0x180015e7e  test    rax, rax
0x180015e81  jnz     short loc_180015E90
0x180015e83  call    cs:__imp_GetLastError
0x180015e89  mov     ebx, eax
0x180015e8b  jmp     loc_180016052
0x180015e90  xor     edx, edx; Val
0x180015e92  lea     rcx, [rsp+410h+pIfRow]; void *
0x180015e97  mov     r8d, 35Ch; Size
0x180015e9d  call    memset_0
0x180015ea2  lea     rdx, [rbp+310h+pIfRow.dwIndex]; pdwBestIfIndex
0x180015ea9  mov     ecx, r14d; dwDestAddr
0x180015eac  call    cs:__imp_GetBestInterface
0x180015eb2  test    eax, eax
0x180015eb4  jnz     short loc_180015EC1
0x180015eb6  lea     rcx, [rsp+410h+pIfRow]; pIfRow
0x180015ebb  call    cs:__imp_GetIfEntry
0x180015ec1  mov     eax, [rbp+310h+pIfRow.dwSpeed]
0x180015ec7  mov     ecx, 40h ; '@'; uFlags
0x180015ecc  shr     eax, 0Ah
0x180015ecf  mov     [rbx], eax
0x180015ed1  mov     ebx, dword ptr [rsp+410h+Data]
0x180015ed5  add     ebx, 30h ; '0'
0x180015ed8  mov     edx, ebx; uBytes
0x180015eda  mov     [rsp+410h+var_3CC], ebx
0x180015ede  call    cs:__imp_LocalAlloc
0x180015ee4  mov     rdi, rax
0x180015ee7  test    rax, rax
0x180015eea  jz      short loc_180015E83
0x180015eec  call    cs:__imp_IcmpCreateFile
0x180015ef2  mov     rsi, rax
0x180015ef5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015ef9  jnz     short loc_180015F08
0x180015efb  call    cs:__imp_GetLastError
0x180015f01  mov     ebx, eax
0x180015f03  jmp     loc_180016049
0x180015f08  mov     r15d, r12d
0x180015f0b  mov     r13d, r12d
0x180015f0e  cmp     r12d, 3
0x180015f12  jnb     loc_18001600D
0x180015f18  mov     r8, cs:?g_lpTestData@@3PEAXEA; RequestData
0x180015f1f  xor     r9d, r9d; RequestSize
0x180015f22  mov     [rsp+410h+Timeout], 1388h; Timeout
0x180015f2a  mov     edx, r14d; DestinationAddress
0x180015f2d  mov     [rsp+410h+ReplySize], ebx; ReplySize
0x180015f31  mov     rcx, rsi; IcmpHandle
0x180015f34  mov     [rsp+410h+lpcbData], rdi; ReplyBuffer
0x180015f39  mov     [rsp+410h+phkResult], r9; RequestOptions
0x180015f3e  call    cs:__imp_IcmpSendEcho
0x180015f44  xor     ecx, ecx
0x180015f46  test    eax, eax
0x180015f48  jnz     short loc_180015F65
0x180015f4a  call    cs:__imp_GetLastError
0x180015f50  cmp     eax, 2AFBh
0x180015f55  jnz     loc_180016005
0x180015f5b  mov     ebx, 35h ; '5'
0x180015f60  jmp     loc_180016040
0x180015f65  cmp     [rdi+4], ecx
0x180015f68  jz      short loc_180015F73
0x180015f6a  cmp     dword ptr [rdi+4], 2AFBh
0x180015f71  jmp     short loc_180015F55
0x180015f73  mov     r14d, [rdi+8]
0x180015f77  mov     ebx, ecx
0x180015f79  cmp     r14d, 0Ah
0x180015f7d  jnb     short loc_180015F89
0x180015f7f  cmp     dword ptr [rsp+410h+var_3C4], ecx
0x180015f83  jz      loc_180016040
0x180015f89  mov     eax, [rsp+410h+var_3CC]
0x180015f8d  movzx   r9d, word ptr [rsp+410h+Data]; RequestSize
0x180015f93  mov     r8, cs:?g_lpTestData@@3PEAXEA; RequestData
0x180015f9a  mov     edx, [rsp+410h+DestinationAddress]; DestinationAddress
0x180015f9e  mov     [rsp+410h+Timeout], 1388h; Timeout
0x180015fa6  mov     [rsp+410h+ReplySize], eax; ReplySize
0x180015faa  mov     [rsp+410h+lpcbData], rdi; ReplyBuffer
0x180015faf  mov     [rsp+410h+phkResult], rcx; RequestOptions
0x180015fb4  mov     rcx, rsi; IcmpHandle
0x180015fb7  call    cs:__imp_IcmpSendEcho
0x180015fbd  xor     ecx, ecx
0x180015fbf  test    eax, eax
0x180015fc1  jnz     short loc_180015FD2
0x180015fc3  call    cs:__imp_GetLastError
0x180015fc9  cmp     eax, 2AFBh
0x180015fce  jz      short loc_180015F5B
0x180015fd0  jmp     short loc_180015FFC
0x180015fd2  cmp     [rdi+4], ecx
0x180015fd5  jz      short loc_180015FE0
0x180015fd7  cmp     dword ptr [rdi+4], 2AFBh
0x180015fde  jmp     short loc_180015FCE
0x180015fe0  mov     eax, [rdi+8]
0x180015fe3  cmp     eax, 0Ah
0x180015fe6  jnb     short loc_180015FEE
0x180015fe8  cmp     dword ptr [rsp+410h+var_3C4], ecx
0x180015fec  jz      short loc_180016040
0x180015fee  cmp     r14d, eax
0x180015ff1  jnb     short loc_180015FFC
0x180015ff3  sub     eax, r14d
0x180015ff6  add     r15d, eax
0x180015ff9  inc     r13d
0x180015ffc  mov     r14d, [rsp+410h+DestinationAddress]
0x180016001  mov     ebx, [rsp+410h+var_3CC]
0x180016005  inc     r12d
0x180016008  jmp     loc_180015F0E
0x18001600d  test    r15d, r15d
0x180016010  jz      short loc_18001603B
0x180016012  xor     edx, edx
0x180016014  mov     eax, r15d
0x180016017  div     r13d
0x18001601a  xor     edx, edx
0x18001601c  mov     ecx, eax
0x18001601e  imul    eax, dword ptr [rsp+410h+Data], 7D0h
0x180016026  div     ecx
0x180016028  mov     rcx, [rsp+410h+var_3A8]
0x18001602d  shr     eax, 7
0x180016030  and     eax, 3FFFFFh
0x180016035  xor     ebx, ebx
0x180016037  mov     [rcx], eax
0x180016039  jmp     short loc_180016040
0x18001603b  mov     ebx, 3Bh ; ';'
0x180016040  mov     rcx, rsi; IcmpHandle
0x180016043  call    cs:__imp_IcmpCloseHandle
0x180016049  mov     rcx, rdi; hMem
0x18001604c  call    cs:__imp_LocalFree
0x180016052  mov     rcx, cs:?g_PingCritSec@@3PEAU_RTL_CRITICAL_SECTION@@EA; lpCriticalSection
0x180016059  call    cs:__imp_LeaveCriticalSection
0x18001605f  mov     eax, ebx
0x180016061  mov     rcx, [rbp+310h+var_40]
0x180016068  xor     rcx, rsp; StackCookie
0x18001606b  call    __security_check_cookie
0x180016070  mov     rbx, [rsp+410h+arg_10]
0x180016078  add     rsp, 3E0h
0x18001607f  pop     r15
0x180016081  pop     r14
0x180016083  pop     r13
0x180016085  pop     r12
0x180016087  pop     rdi
0x180016088  pop     rsi
0x180016089  pop     rbp
0x18001608a  retn
```
