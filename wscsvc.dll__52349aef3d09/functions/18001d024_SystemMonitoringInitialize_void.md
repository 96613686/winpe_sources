# SystemMonitoringInitialize(void)

- ea: `0x18001d024`
- end: `0x18001d1b6`
- name: `?SystemMonitoringInitialize@@YAJXZ`
- size: `402`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d2f0`

## callees

- `0x180008e48`
- `0x18001d024`
- `0x18003e6e8`
- `0x18003e7e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d044`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d05d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d05d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d0f2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d0f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d12e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d12e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d121`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d121`

## string_xrefs

- `0x18001d0b1`: `SOFTWARE\Microsoft\Security Center`

## pseudocode

```c
__int64 SystemMonitoringInitialize(void)
{
  unsigned int v0; // ebx
  signed int LastError; // eax
  LSTATUS v2; // eax
  int v3; // r8d
  int v4; // r9d
  LSTATUS v5; // edi
  int v6; // edx
  int v7; // r8d
  int v8; // r9d
  int Data; // [rsp+70h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  v0 = 0;
  g_hEventSessionLogonEvent = CreateEventW(0, 0, 0, 0);
  if ( !g_hEventSessionLogonEvent )
  {
    LastError = GetLastError();
    v0 = LastError > 0 ? (unsigned __int16)LastError | 0x80070000 : LastError;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_c81c3ae13a39328400a46a9fe4e4d5f2_Traceguids,
        (unsigned int)LastError);
    }
  }
  Data = 0;
  hKey = 0;
  v2 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Security Center", 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v3, v4, (__int64)L"SOFTWARE\\Microsoft\\Security Center", v2);
    }
  }
  else
  {
    v5 = RegSetValueExW(hKey, L"cval", 0, 4u, (const BYTE *)&Data, 4u);
    RegCloseKey(hKey);
    hKey = 0;
    if ( v5
      && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qSSdd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        v7,
        v8,
        (__int64)L"SOFTWARE\\Microsoft\\Security Center",
        (__int64)L"cval",
        Data,
        v5);
    }
  }
  return v0;
}

```

## disassembly

```asm
0x18001d024  mov     [rsp+arg_10], rbx
0x18001d029  mov     [rsp+arg_18], rdi
0x18001d02e  push    r12
0x18001d030  push    r14
0x18001d032  push    r15
0x18001d034  sub     rsp, 50h
0x18001d038  xor     r9d, r9d; lpName
0x18001d03b  xor     r8d, r8d; bInitialState
0x18001d03e  xor     edx, edx; bManualReset
0x18001d040  xor     ecx, ecx; lpEventAttributes
0x18001d042  xor     ebx, ebx
0x18001d044  call    cs:__imp_CreateEventW
0x18001d04a  mov     cs:?g_hEventSessionLogonEvent@@3PEAXEA, rax; void * g_hEventSessionLogonEvent
0x18001d051  lea     r14, WPP_GLOBAL_Control
0x18001d058  test    rax, rax
0x18001d05b  jnz     short loc_18001D09E
0x18001d05d  call    cs:__imp_GetLastError
0x18001d063  test    eax, eax
0x18001d065  jg      short loc_18001D06B
0x18001d067  mov     ebx, eax
0x18001d069  jmp     short loc_18001D074
0x18001d06b  movzx   ebx, ax
0x18001d06e  or      ebx, 80070000h
0x18001d074  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d07b  cmp     rcx, r14
0x18001d07e  jz      short loc_18001D09E
0x18001d080  test    byte ptr [rcx+1Ch], 1
0x18001d084  jz      short loc_18001D09E
0x18001d086  mov     rcx, [rcx+10h]
0x18001d08a  lea     r8, WPP_c81c3ae13a39328400a46a9fe4e4d5f2_Traceguids
0x18001d091  mov     edx, 0Ah
0x18001d096  mov     r9d, eax
0x18001d099  call    WPP_SF_d
0x18001d09e  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x18001d0a7  lea     rax, [rsp+68h+hKey]
0x18001d0ac  mov     [rsp+68h+phkResult], rax; phkResult
0x18001d0b1  lea     r15, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Security Center"
0x18001d0b8  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001d0c1  xor     r9d, r9d; lpClass
0x18001d0c4  mov     [rsp+68h+samDesired], 20006h; samDesired
0x18001d0cc  xor     r8d, r8d; Reserved
0x18001d0cf  mov     rdx, r15; lpSubKey
0x18001d0d2  mov     [rsp+68h+dwOptions], 0; dwOptions
0x18001d0da  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d0e1  mov     [rsp+68h+Data], 0
0x18001d0e9  mov     [rsp+68h+hKey], 0
0x18001d0f2  call    cs:__imp_RegCreateKeyExW
0x18001d0f8  test    eax, eax
0x18001d0fa  jnz     short loc_18001D174
0x18001d0fc  mov     rcx, [rsp+68h+hKey]; hKey
0x18001d101  lea     r9d, [rax+4]; dwType
0x18001d105  lea     rax, [rsp+68h+Data]
0x18001d10a  mov     [rsp+68h+samDesired], r9d; cbData
0x18001d10f  lea     r12, aCval; "cval"
0x18001d116  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18001d11b  mov     rdx, r12; lpValueName
0x18001d11e  xor     r8d, r8d; Reserved
0x18001d121  call    cs:__imp_RegSetValueExW
0x18001d127  mov     rcx, [rsp+68h+hKey]; hKey
0x18001d12c  mov     edi, eax
0x18001d12e  call    cs:__imp_RegCloseKey
0x18001d134  mov     [rsp+68h+hKey], 0
0x18001d13d  test    edi, edi
0x18001d13f  jz      short loc_18001D19D
0x18001d141  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d148  cmp     rcx, r14
0x18001d14b  jz      short loc_18001D19D
0x18001d14d  test    byte ptr [rcx+1Ch], 1
0x18001d151  jz      short loc_18001D19D
0x18001d153  mov     eax, [rsp+68h+Data]
0x18001d157  mov     rcx, [rcx+10h]
0x18001d15b  mov     dword ptr [rsp+68h+phkResult], edi
0x18001d15f  mov     dword ptr [rsp+68h+lpSecurityAttributes], eax
0x18001d163  mov     qword ptr [rsp+68h+samDesired], r12
0x18001d168  mov     qword ptr [rsp+68h+dwOptions], r15
0x18001d16d  call    WPP_SF_qSSdd
0x18001d172  jmp     short loc_18001D19D
0x18001d174  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d17b  cmp     rcx, r14
0x18001d17e  jz      short loc_18001D19D
0x18001d180  test    byte ptr [rcx+1Ch], 1
0x18001d184  jz      short loc_18001D19D
0x18001d186  mov     rcx, [rcx+10h]
0x18001d18a  mov     edx, 18h
0x18001d18f  mov     [rsp+68h+samDesired], eax
0x18001d193  mov     qword ptr [rsp+68h+dwOptions], r15
0x18001d198  call    WPP_SF_qSd
0x18001d19d  lea     r11, [rsp+68h+var_18]
0x18001d1a2  mov     eax, ebx
0x18001d1a4  mov     rbx, [r11+30h]
0x18001d1a8  mov     rdi, [r11+38h]
0x18001d1ac  mov     rsp, r11
0x18001d1af  pop     r15
0x18001d1b1  pop     r14
0x18001d1b3  pop     r12
0x18001d1b5  retn
```
