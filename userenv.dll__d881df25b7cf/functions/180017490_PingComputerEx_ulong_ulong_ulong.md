# PingComputerEx(ulong,ulong *,ulong *)

- ea: `0x180017490`
- end: `0x1800178fe`
- name: `?PingComputerEx@@YAKKPEAK0@Z`
- size: `1134`
- prototype: `unsigned int __fastcall(IPAddr DestinationAddress, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019ae0`

## callees

- `0x18000e640`
- `0x18000efe0`
- `0x180016d44`
- `0x180017490`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001766a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001766a`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18001767e`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18001767e`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18001764f`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18001764f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017567`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800175e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017567`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800175e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017531`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800175a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017531`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800175a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017580`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800175f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017580`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800175f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800178c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800178c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017625`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017625`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001769f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017819`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001769f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017819`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001770c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001770c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800178b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800178b2`
- `IPHLPAPI!IcmpCreateFile` at `0x180017724`
- `IPHLPAPI!IcmpCreateFile` at `0x180017724`
- `IPHLPAPI!IcmpCloseHandle` at `0x1800178a3`
- `IPHLPAPI!IcmpCloseHandle` at `0x1800178a3`
- `IPHLPAPI!GetBestInterface` at `0x1800176ce`
- `IPHLPAPI!GetBestInterface` at `0x1800176ce`
- `IPHLPAPI!IcmpSendEcho` at `0x180017782`
- `IPHLPAPI!IcmpSendEcho` at `0x180017807`
- `IPHLPAPI!IcmpSendEcho` at `0x180017782`
- `IPHLPAPI!IcmpSendEcho` at `0x180017807`
- `IPHLPAPI!GetIfEntry` at `0x1800176e3`
- `IPHLPAPI!GetIfEntry` at `0x1800176e3`

## string_xrefs

- `0x1800175c5`: `FastWanLink`

## pseudocode

```c
DWORD __fastcall PingComputerEx(IPAddr DestinationAddress, unsigned int *a2, unsigned int *a3)
{
  IPAddr v4; // r14d
  unsigned int v5; // r12d
  DWORD result; // eax
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
  if ( result )
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
0x180017490  mov     [rsp-8+arg_10], rbx
0x180017495  push    rbp
0x180017496  push    rsi
0x180017497  push    rdi
0x180017498  push    r12
0x18001749a  push    r13
0x18001749c  push    r14
0x18001749e  push    r15
0x1800174a0  lea     rbp, [rsp-2E0h]
0x1800174a8  sub     rsp, 3E0h
0x1800174af  mov     rax, cs:__security_cookie
0x1800174b6  xor     rax, rsp
0x1800174b9  mov     [rbp+310h+var_40], rax
0x1800174c0  mov     rbx, rdx
0x1800174c3  mov     [rsp+410h+var_3A8], rdx
0x1800174c8  mov     r14d, ecx
0x1800174cb  mov     [rsp+410h+DestinationAddress], ecx
0x1800174cf  xor     r12d, r12d
0x1800174d2  lea     rcx, [rsp+410h+pIfRow]; void *
0x1800174d7  xor     edx, edx; Val
0x1800174d9  mov     [rsp+410h+var_3C0], r12d
0x1800174de  mov     r8d, 35Ch; Size
0x1800174e4  call    memset_0
0x1800174e9  lea     rax, [rsp+410h+hKey]
0x1800174ee  mov     [rsp+410h+hKey], r12
0x1800174f3  mov     r15d, 20019h
0x1800174f9  mov     [rsp+410h+phkResult], rax; phkResult
0x1800174fe  mov     r13, 0FFFFFFFF80000002h
0x180017505  mov     [rsp+410h+var_3B0], r12
0x18001750a  mov     edi, 800h
0x18001750f  mov     dword ptr [rsp+410h+var_3C4], r12d
0x180017514  lea     esi, [r12+4]
0x180017519  mov     dword ptr [rsp+410h+Data], edi
0x18001751d  mov     r9d, r15d; samDesired
0x180017520  mov     [rsp+410h+cbData], esi
0x180017524  mov     rcx, r13; hKey
0x180017527  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001752e  xor     r8d, r8d; ulOptions
0x180017531  call    cs:__imp_RegOpenKeyExW
0x180017538  nop     dword ptr [rax+rax+00h]
0x18001753d  test    eax, eax
0x18001753f  jnz     short loc_18001758C
0x180017541  mov     rcx, [rsp+410h+hKey]; hKey
0x180017546  lea     rax, [rsp+410h+cbData]
0x18001754b  mov     [rsp+410h+lpcbData], rax; lpcbData
0x180017550  lea     rdx, ValueName; "PingBufferSize"
0x180017557  lea     rax, [rsp+410h+Data]
0x18001755c  xor     r9d, r9d; lpType
0x18001755f  xor     r8d, r8d; lpReserved
0x180017562  mov     [rsp+410h+phkResult], rax; lpData
0x180017567  call    cs:__imp_RegQueryValueExW
0x18001756e  nop     dword ptr [rax+rax+00h]
0x180017573  test    eax, eax
0x180017575  jz      short loc_18001757B
0x180017577  mov     dword ptr [rsp+410h+Data], edi
0x18001757b  mov     rcx, [rsp+410h+hKey]; hKey
0x180017580  call    cs:__imp_RegCloseKey
0x180017587  nop     dword ptr [rax+rax+00h]
0x18001758c  lea     rax, [rsp+410h+var_3B0]
0x180017591  mov     r9d, r15d; samDesired
0x180017594  xor     r8d, r8d; ulOptions
0x180017597  mov     [rsp+410h+phkResult], rax; phkResult
0x18001759c  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800175a3  mov     rcx, r13; hKey
0x1800175a6  call    cs:__imp_RegOpenKeyExW
0x1800175ad  nop     dword ptr [rax+rax+00h]
0x1800175b2  test    eax, eax
0x1800175b4  jnz     short loc_1800175FD
0x1800175b6  mov     rcx, [rsp+410h+var_3B0]; hKey
0x1800175bb  lea     rax, [rsp+410h+var_3C0]
0x1800175c0  mov     [rsp+410h+lpcbData], rax; lpcbData
0x1800175c5  lea     rdx, aFastwanlink; "FastWanLink"
0x1800175cc  lea     rax, [rsp+410h+var_3C4]
0x1800175d1  mov     [rsp+410h+var_3C0], esi
0x1800175d5  xor     r9d, r9d; lpType
0x1800175d8  mov     [rsp+410h+phkResult], rax; lpData
0x1800175dd  xor     r8d, r8d; lpReserved
0x1800175e0  call    cs:__imp_RegQueryValueExW
0x1800175e7  nop     dword ptr [rax+rax+00h]
0x1800175ec  mov     rcx, [rsp+410h+var_3B0]; hKey
0x1800175f1  call    cs:__imp_RegCloseKey
0x1800175f8  nop     dword ptr [rax+rax+00h]
0x1800175fd  mov     eax, dword ptr [rsp+410h+Data]
0x180017601  add     eax, 0FFFFFE0Ch
0x180017606  cmp     eax, 60Ch
0x18001760b  jbe     short loc_180017611
0x18001760d  mov     dword ptr [rsp+410h+Data], edi
0x180017611  call    ?InitializePingCritSec@@YAKXZ; InitializePingCritSec(void)
0x180017616  test    eax, eax
0x180017618  jnz     loc_1800178D3
0x18001761e  mov     rcx, cs:?g_PingCritSec@@3PEAU_RTL_CRITICAL_SECTION@@EA; lpCriticalSection
0x180017625  call    cs:__imp_EnterCriticalSection
0x18001762c  nop     dword ptr [rax+rax+00h]
0x180017631  cmp     cs:?g_lpTestData@@3PEAXEA, r12; void * g_lpTestData
0x180017638  jnz     short loc_1800176B2
0x18001763a  mov     rcx, cs:g_hDllInstance; hModule
0x180017641  lea     rdx, Type; "JPEG"
0x180017648  xor     r9d, r9d; wLanguage
0x18001764b  lea     r8d, [r9+1]; lpName
0x18001764f  call    cs:__imp_FindResourceExW
0x180017656  nop     dword ptr [rax+rax+00h]
0x18001765b  test    rax, rax
0x18001765e  jz      short loc_180017693
0x180017660  mov     rcx, cs:g_hDllInstance; hModule
0x180017667  mov     rdx, rax; hResInfo
0x18001766a  call    cs:__imp_LoadResource
0x180017671  nop     dword ptr [rax+rax+00h]
0x180017676  test    rax, rax
0x180017679  jz      short loc_180017693
0x18001767b  mov     rcx, rax; hResData
0x18001767e  call    cs:__imp_LockResource
0x180017685  nop     dword ptr [rax+rax+00h]
0x18001768a  mov     cs:?g_lpTestData@@3PEAXEA, rax; void * g_lpTestData
0x180017691  jmp     short loc_18001769A
0x180017693  mov     rax, cs:?g_lpTestData@@3PEAXEA; void * g_lpTestData
0x18001769a  test    rax, rax
0x18001769d  jnz     short loc_1800176B2
0x18001769f  call    cs:__imp_GetLastError
0x1800176a6  nop     dword ptr [rax+rax+00h]
0x1800176ab  mov     ebx, eax
0x1800176ad  jmp     loc_1800178BE
0x1800176b2  xor     edx, edx; Val
0x1800176b4  lea     rcx, [rsp+410h+pIfRow]; void *
0x1800176b9  mov     r8d, 35Ch; Size
0x1800176bf  call    memset_0
0x1800176c4  lea     rdx, [rbp+310h+pIfRow.dwIndex]; pdwBestIfIndex
0x1800176cb  mov     ecx, r14d; dwDestAddr
0x1800176ce  call    cs:__imp_GetBestInterface
0x1800176d5  nop     dword ptr [rax+rax+00h]
0x1800176da  test    eax, eax
0x1800176dc  jnz     short loc_1800176EF
0x1800176de  lea     rcx, [rsp+410h+pIfRow]; pIfRow
0x1800176e3  call    cs:__imp_GetIfEntry
0x1800176ea  nop     dword ptr [rax+rax+00h]
0x1800176ef  mov     eax, [rbp+310h+pIfRow.dwSpeed]
0x1800176f5  mov     ecx, 40h ; '@'; uFlags
0x1800176fa  shr     eax, 0Ah
0x1800176fd  mov     [rbx], eax
0x1800176ff  mov     ebx, dword ptr [rsp+410h+Data]
0x180017703  add     ebx, 30h ; '0'
0x180017706  mov     edx, ebx; uBytes
0x180017708  mov     [rsp+410h+var_3CC], ebx
0x18001770c  call    cs:__imp_LocalAlloc
0x180017713  nop     dword ptr [rax+rax+00h]
0x180017718  mov     rdi, rax
0x18001771b  test    rax, rax
0x18001771e  jz      loc_18001769F
0x180017724  call    cs:__imp_IcmpCreateFile
0x18001772b  nop     dword ptr [rax+rax+00h]
0x180017730  mov     rsi, rax
0x180017733  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180017737  jnz     short loc_18001774C
0x180017739  call    cs:__imp_GetLastError
0x180017740  nop     dword ptr [rax+rax+00h]
0x180017745  mov     ebx, eax
0x180017747  jmp     loc_1800178AF
0x18001774c  mov     r15d, r12d
0x18001774f  mov     r13d, r12d
0x180017752  cmp     r12d, 3
0x180017756  jnb     loc_18001786D
0x18001775c  mov     r8, cs:?g_lpTestData@@3PEAXEA; RequestData
0x180017763  xor     r9d, r9d; RequestSize
0x180017766  mov     [rsp+410h+Timeout], 1388h; Timeout
0x18001776e  mov     edx, r14d; DestinationAddress
0x180017771  mov     [rsp+410h+ReplySize], ebx; ReplySize
0x180017775  mov     rcx, rsi; IcmpHandle
0x180017778  mov     [rsp+410h+lpcbData], rdi; ReplyBuffer
0x18001777d  mov     [rsp+410h+phkResult], r9; RequestOptions
0x180017782  call    cs:__imp_IcmpSendEcho
0x180017789  nop     dword ptr [rax+rax+00h]
0x18001778e  xor     ecx, ecx
0x180017790  test    eax, eax
0x180017792  jnz     short loc_1800177B5
0x180017794  call    cs:__imp_GetLastError
0x18001779b  nop     dword ptr [rax+rax+00h]
0x1800177a0  cmp     eax, 2AFBh
0x1800177a5  jnz     loc_180017865
0x1800177ab  mov     ebx, 35h ; '5'
0x1800177b0  jmp     loc_1800178A0
0x1800177b5  cmp     [rdi+4], ecx
0x1800177b8  jz      short loc_1800177C3
0x1800177ba  cmp     dword ptr [rdi+4], 2AFBh
0x1800177c1  jmp     short loc_1800177A5
0x1800177c3  mov     r14d, [rdi+8]
0x1800177c7  mov     ebx, ecx
0x1800177c9  cmp     r14d, 0Ah
0x1800177cd  jnb     short loc_1800177D9
0x1800177cf  cmp     dword ptr [rsp+410h+var_3C4], ecx
0x1800177d3  jz      loc_1800178A0
0x1800177d9  mov     eax, [rsp+410h+var_3CC]
0x1800177dd  movzx   r9d, word ptr [rsp+410h+Data]; RequestSize
0x1800177e3  mov     r8, cs:?g_lpTestData@@3PEAXEA; RequestData
0x1800177ea  mov     edx, [rsp+410h+DestinationAddress]; DestinationAddress
0x1800177ee  mov     [rsp+410h+Timeout], 1388h; Timeout
0x1800177f6  mov     [rsp+410h+ReplySize], eax; ReplySize
0x1800177fa  mov     [rsp+410h+lpcbData], rdi; ReplyBuffer
0x1800177ff  mov     [rsp+410h+phkResult], rcx; RequestOptions
0x180017804  mov     rcx, rsi; IcmpHandle
0x180017807  call    cs:__imp_IcmpSendEcho
0x18001780e  nop     dword ptr [rax+rax+00h]
0x180017813  xor     ecx, ecx
0x180017815  test    eax, eax
0x180017817  jnz     short loc_180017832
0x180017819  call    cs:__imp_GetLastError
0x180017820  nop     dword ptr [rax+rax+00h]
0x180017825  cmp     eax, 2AFBh
0x18001782a  jz      loc_1800177AB
0x180017830  jmp     short loc_18001785C
0x180017832  cmp     [rdi+4], ecx
0x180017835  jz      short loc_180017840
0x180017837  cmp     dword ptr [rdi+4], 2AFBh
0x18001783e  jmp     short loc_18001782A
0x180017840  mov     eax, [rdi+8]
0x180017843  cmp     eax, 0Ah
0x180017846  jnb     short loc_18001784E
0x180017848  cmp     dword ptr [rsp+410h+var_3C4], ecx
0x18001784c  jz      short loc_1800178A0
0x18001784e  cmp     r14d, eax
0x180017851  jnb     short loc_18001785C
0x180017853  sub     eax, r14d
0x180017856  add     r15d, eax
0x180017859  inc     r13d
0x18001785c  mov     r14d, [rsp+410h+DestinationAddress]
0x180017861  mov     ebx, [rsp+410h+var_3CC]
0x180017865  inc     r12d
0x180017868  jmp     loc_180017752
0x18001786d  test    r15d, r15d
0x180017870  jz      short loc_18001789B
0x180017872  xor     edx, edx
0x180017874  mov     eax, r15d
0x180017877  div     r13d
0x18001787a  xor     edx, edx
0x18001787c  mov     ecx, eax
0x18001787e  imul    eax, dword ptr [rsp+410h+Data], 7D0h
0x180017886  div     ecx
0x180017888  mov     rcx, [rsp+410h+var_3A8]
0x18001788d  shr     eax, 7
0x180017890  and     eax, 3FFFFFh
0x180017895  xor     ebx, ebx
0x180017897  mov     [rcx], eax
0x180017899  jmp     short loc_1800178A0
0x18001789b  mov     ebx, 3Bh ; ';'
0x1800178a0  mov     rcx, rsi; IcmpHandle
0x1800178a3  call    cs:__imp_IcmpCloseHandle
0x1800178aa  nop     dword ptr [rax+rax+00h]
0x1800178af  mov     rcx, rdi; hMem
0x1800178b2  call    cs:__imp_LocalFree
0x1800178b9  nop     dword ptr [rax+rax+00h]
0x1800178be  mov     rcx, cs:?g_PingCritSec@@3PEAU_RTL_CRITICAL_SECTION@@EA; lpCriticalSection
0x1800178c5  call    cs:__imp_LeaveCriticalSection
0x1800178cc  nop     dword ptr [rax+rax+00h]
0x1800178d1  mov     eax, ebx
0x1800178d3  mov     rcx, [rbp+310h+var_40]
0x1800178da  xor     rcx, rsp; StackCookie
0x1800178dd  call    __security_check_cookie
0x1800178e2  mov     rbx, [rsp+410h+arg_10]
0x1800178ea  add     rsp, 3E0h
0x1800178f1  pop     r15
0x1800178f3  pop     r14
0x1800178f5  pop     r13
0x1800178f7  pop     r12
0x1800178f9  pop     rdi
0x1800178fa  pop     rsi
0x1800178fb  pop     rbp
0x1800178fc  retn
```
