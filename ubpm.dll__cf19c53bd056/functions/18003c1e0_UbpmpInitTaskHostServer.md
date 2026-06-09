# UbpmpInitTaskHostServer

- ea: `0x18003c1e0`
- end: `0x18003c2f8`
- name: `UbpmpInitTaskHostServer`
- size: `280`
- prototype: `PVOID()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18002a7f0`

## callees

- `0x18001ea6c`
- `0x180032e38`
- `0x18003c1e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c2c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c2c6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003c254`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003c254`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c226`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c226`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c26b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c26b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003c29b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003c29b`

## string_xrefs

- `0x18003c248`: `TaskhostTimeout`

## pseudocode

```c
PVOID UbpmpInitTaskHostServer()
{
  PVOID result; // rax
  DWORD LastError; // eax
  int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD Type; // [rsp+48h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 4;
  Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control", 0, 0x20019u, &hKey) )
  {
    if ( !RegQueryValueExW(hKey, L"TaskhostTimeout", 0, &Type, (LPBYTE)&Data, &cbData) && Type != 4 )
      Data = 0;
    RegCloseKey(hKey);
  }
  if ( Data )
  {
    g_dwTaskhostResponseTimeoutMsec = Data & 0x7FFFFFFF;
    g_fBreakOnTaskhostTimeout = Data < 0;
  }
  g_hLowPowerEpochExited = CreateEventW(0, 0, 1, 0);
  if ( g_hLowPowerEpochExited )
    return (PVOID)UbpmpSetInitialHostServerJobObjectRequests();
  result = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LastError = GetLastError();
    return (PVOID)WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    211,
                    WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                    LastError);
  }
  return result;
}

```

## disassembly

```asm
0x18003c1e0  push    rbp
0x18003c1e2  mov     rbp, rsp
0x18003c1e5  sub     rsp, 30h
0x18003c1e9  lea     rax, [rbp+hKey]
0x18003c1ed  mov     [rbp+hKey], 0
0x18003c1f5  mov     r9d, 20019h; samDesired
0x18003c1fb  mov     [rsp+30h+phkResult], rax; phkResult
0x18003c200  xor     r8d, r8d; ulOptions
0x18003c203  mov     [rbp+Type], 0
0x18003c20a  lea     rdx, SubKey; "System\\CurrentControlSet\\Control"
0x18003c211  mov     [rbp+cbData], 4
0x18003c218  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003c21f  mov     [rbp+Data], 0
0x18003c226  call    cs:__imp_RegOpenKeyExW
0x18003c22c  test    eax, eax
0x18003c22e  jnz     short loc_18003C271
0x18003c230  mov     rcx, [rbp+hKey]; hKey
0x18003c234  lea     rax, [rbp+cbData]
0x18003c238  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18003c23d  lea     r9, [rbp+Type]; lpType
0x18003c241  lea     rax, [rbp+Data]
0x18003c245  xor     r8d, r8d; lpReserved
0x18003c248  lea     rdx, aTaskhosttimeou; "TaskhostTimeout"
0x18003c24f  mov     [rsp+30h+phkResult], rax; lpData
0x18003c254  call    cs:__imp_RegQueryValueExW
0x18003c25a  test    eax, eax
0x18003c25c  jnz     short loc_18003C267
0x18003c25e  cmp     [rbp+Type], 4
0x18003c262  jz      short loc_18003C267
0x18003c264  mov     [rbp+Data], eax
0x18003c267  mov     rcx, [rbp+hKey]; hKey
0x18003c26b  call    cs:__imp_RegCloseKey
0x18003c271  mov     ecx, [rbp+Data]
0x18003c274  test    ecx, ecx
0x18003c276  jz      short loc_18003C290
0x18003c278  mov     eax, ecx
0x18003c27a  shr     ecx, 1Fh
0x18003c27d  btr     eax, 1Fh
0x18003c281  and     cl, 1
0x18003c284  mov     cs:?g_dwTaskhostResponseTimeoutMsec@@3KA, eax; ulong g_dwTaskhostResponseTimeoutMsec
0x18003c28a  mov     cs:?g_fBreakOnTaskhostTimeout@@3EA, cl; uchar g_fBreakOnTaskhostTimeout
0x18003c290  xor     r9d, r9d; lpName
0x18003c293  xor     edx, edx; bManualReset
0x18003c295  xor     ecx, ecx; lpEventAttributes
0x18003c297  lea     r8d, [r9+1]; bInitialState
0x18003c29b  call    cs:__imp_CreateEventW
0x18003c2a1  mov     cs:?g_hLowPowerEpochExited@@3PEAXEA, rax; void * g_hLowPowerEpochExited
0x18003c2a8  test    rax, rax
0x18003c2ab  jnz     short loc_18003C2ED
0x18003c2ad  mov     rax, cs:WPP_GLOBAL_Control
0x18003c2b4  lea     rcx, WPP_GLOBAL_Control
0x18003c2bb  cmp     rax, rcx
0x18003c2be  jz      short loc_18003C2F2
0x18003c2c0  test    byte ptr [rax+1Ch], 1
0x18003c2c4  jz      short loc_18003C2F2
0x18003c2c6  call    cs:__imp_GetLastError
0x18003c2cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c2d3  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18003c2da  mov     edx, 0D3h
0x18003c2df  mov     r9d, eax
0x18003c2e2  mov     rcx, [rcx+10h]
0x18003c2e6  call    WPP_SF_d
0x18003c2eb  jmp     short loc_18003C2F2
0x18003c2ed  call    UbpmpSetInitialHostServerJobObjectRequests
0x18003c2f2  add     rsp, 30h
0x18003c2f6  pop     rbp
0x18003c2f7  retn
```
