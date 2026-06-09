# NETWORK_MANAGER::WriteNetworkInformation(HKEY__ *,_DetectionData *)

- ea: `0x18005a030`
- end: `0x18005a1e8`
- name: `?WriteNetworkInformation@NETWORK_MANAGER@@AEAAKPEAUHKEY__@@PEAU_DetectionData@@@Z`
- size: `440`
- prototype: `unsigned int(NETWORK_MANAGER *__hidden this, HKEY, struct _DetectionData *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180059e3c`
- `0x18005a1f0`

## callees

- `0x18002acec`
- `0x180041eb0`
- `0x18005a030`
- `0x1800a1d10`
- `0x1800c2d50`
- `0x1800cf008`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a09f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a0d1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a103`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a15f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a09f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a0d1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a103`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005a15f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005a177`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005a177`

## pseudocode

```c
__int64 __fastcall NETWORK_MANAGER::WriteNetworkInformation(NETWORK_MANAGER *this, HKEY a2, const BYTE *a3)
{
  unsigned int v5; // ebx
  unsigned int v6; // eax
  BYTE *lpData; // [rsp+20h] [rbp-28h]
  int v9; // [rsp+30h] [rbp-18h] BYREF

  v9 = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_(1029, 48, WPP_927dd49ceab235c34f59e6ea3b7830f7_Traceguids);
  v5 = RegSetValueExW(a2, L"WpadDecisionReason", 0, 4u, a3 + 20, 4u);
  if ( !v5 )
  {
    v5 = RegSetValueExW(a2, L"WpadDecisionTime", 0, 3u, a3 + 24, 8u);
    if ( !v5 )
    {
      v5 = RegSetValueExW(a2, L"WpadDecision", 0, 4u, a3 + 16, 4u);
      if ( !v5 )
      {
        if ( *(_QWORD *)a3 )
        {
          v6 = WxStringCchLengthDWordW(*(_QWORD *)a3, 0x7FFFFFFF, &v9);
          v5 = WX_WIN32_FROM_HR(v6);
          if ( v5 )
            goto LABEL_15;
          v5 = RegSetValueExW(a2, L"WpadDetectedUrl", 0, 1u, *(const BYTE **)a3, 2 * v9 + 2);
          if ( v5 )
            goto LABEL_15;
        }
        else
        {
          RegDeleteValueW(a2, L"WpadDetectedUrl");
        }
        if ( *((_DWORD *)a3 + 2) )
          IncrementRegistryValue(a2, L"WpadDhcp");
        if ( *((_DWORD *)a3 + 3) )
          IncrementRegistryValue(a2, L"WpadDns");
      }
    }
  }
LABEL_15:
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 49, WPP_927dd49ceab235c34f59e6ea3b7830f7_Traceguids, v5, lpData);
  return v5;
}

```

## disassembly

```asm
0x18005a030  mov     [rsp+arg_0], rbx
0x18005a035  mov     [rsp+arg_18], rsi
0x18005a03a  push    rdi
0x18005a03b  sub     rsp, 40h
0x18005a03f  mov     rax, cs:__security_cookie
0x18005a046  xor     rax, rsp
0x18005a049  mov     [rsp+48h+var_10], rax
0x18005a04e  mov     rdi, r8
0x18005a051  mov     [rsp+48h+var_18], 0
0x18005a059  mov     rsi, rdx
0x18005a05c  test    byte ptr cs:xmmword_180107A60, 20h
0x18005a063  jz      short loc_18005A07B
0x18005a065  mov     edx, 30h ; '0'
0x18005a06a  lea     r8, WPP_927dd49ceab235c34f59e6ea3b7830f7_Traceguids
0x18005a071  mov     ecx, 405h
0x18005a076  call    WPP_SF_
0x18005a07b  lea     rax, [rdi+14h]
0x18005a07f  mov     [rsp+48h+cbData], 4; cbData
0x18005a087  mov     r9d, 4; dwType
0x18005a08d  mov     [rsp+48h+lpData], rax; lpData
0x18005a092  xor     r8d, r8d; Reserved
0x18005a095  lea     rdx, aWpaddecisionre; "WpadDecisionReason"
0x18005a09c  mov     rcx, rsi; hKey
0x18005a09f  call    cs:__imp_RegSetValueExW
0x18005a0a5  mov     ebx, eax
0x18005a0a7  test    eax, eax
0x18005a0a9  jnz     loc_18005A1A7
0x18005a0af  lea     rax, [rdi+18h]
0x18005a0b3  mov     [rsp+48h+cbData], 8; cbData
0x18005a0bb  lea     r9d, [rbx+3]; dwType
0x18005a0bf  mov     [rsp+48h+lpData], rax; lpData
0x18005a0c4  xor     r8d, r8d; Reserved
0x18005a0c7  lea     rdx, aWpaddecisionti; "WpadDecisionTime"
0x18005a0ce  mov     rcx, rsi; hKey
0x18005a0d1  call    cs:__imp_RegSetValueExW
0x18005a0d7  mov     ebx, eax
0x18005a0d9  test    eax, eax
0x18005a0db  jnz     loc_18005A1A7
0x18005a0e1  lea     rax, [rdi+10h]
0x18005a0e5  mov     [rsp+48h+cbData], 4; cbData
0x18005a0ed  lea     r9d, [rbx+4]; dwType
0x18005a0f1  mov     [rsp+48h+lpData], rax; lpData
0x18005a0f6  xor     r8d, r8d; Reserved
0x18005a0f9  lea     rdx, aWpaddecision; "WpadDecision"
0x18005a100  mov     rcx, rsi; hKey
0x18005a103  call    cs:__imp_RegSetValueExW
0x18005a109  mov     ebx, eax
0x18005a10b  test    eax, eax
0x18005a10d  jnz     loc_18005A1A7
0x18005a113  mov     rcx, [rdi]
0x18005a116  test    rcx, rcx
0x18005a119  jz      short loc_18005A16D
0x18005a11b  lea     r8, [rsp+48h+var_18]
0x18005a120  mov     edx, 7FFFFFFFh
0x18005a125  call    WxStringCchLengthDWordW
0x18005a12a  mov     ecx, eax
0x18005a12c  call    WX_WIN32_FROM_HR
0x18005a131  mov     ebx, eax
0x18005a133  test    eax, eax
0x18005a135  jnz     short loc_18005A1A7
0x18005a137  mov     eax, [rsp+48h+var_18]
0x18005a13b  lea     r9d, [rbx+1]; dwType
0x18005a13f  xor     r8d, r8d; Reserved
0x18005a142  lea     rdx, aWpaddetectedur; "WpadDetectedUrl"
0x18005a149  mov     rcx, rsi; hKey
0x18005a14c  lea     eax, ds:2[rax*2]
0x18005a153  mov     [rsp+48h+cbData], eax; cbData
0x18005a157  mov     rax, [rdi]
0x18005a15a  mov     [rsp+48h+lpData], rax; lpData
0x18005a15f  call    cs:__imp_RegSetValueExW
0x18005a165  mov     ebx, eax
0x18005a167  test    eax, eax
0x18005a169  jz      short loc_18005A17D
0x18005a16b  jmp     short loc_18005A1A7
0x18005a16d  lea     rdx, aWpaddetectedur; "WpadDetectedUrl"
0x18005a174  mov     rcx, rsi; hKey
0x18005a177  call    cs:__imp_RegDeleteValueW
0x18005a17d  cmp     dword ptr [rdi+8], 0
0x18005a181  jz      short loc_18005A192
0x18005a183  lea     rdx, aWpaddhcp; "WpadDhcp"
0x18005a18a  mov     rcx, rsi; hKey
0x18005a18d  call    ?IncrementRegistryValue@@YAKPEAUHKEY__@@PEBG@Z; IncrementRegistryValue(HKEY__ *,ushort const *)
0x18005a192  cmp     dword ptr [rdi+0Ch], 0
0x18005a196  jz      short loc_18005A1A7
0x18005a198  lea     rdx, aWpaddns; "WpadDns"
0x18005a19f  mov     rcx, rsi; hKey
0x18005a1a2  call    ?IncrementRegistryValue@@YAKPEAUHKEY__@@PEBG@Z; IncrementRegistryValue(HKEY__ *,ushort const *)
0x18005a1a7  test    byte ptr cs:xmmword_180107A60, 20h
0x18005a1ae  jz      short loc_18005A1C9
0x18005a1b0  mov     edx, 31h ; '1'
0x18005a1b5  lea     r8, WPP_927dd49ceab235c34f59e6ea3b7830f7_Traceguids
0x18005a1bc  mov     ecx, 405h
0x18005a1c1  mov     r9d, ebx
0x18005a1c4  call    WPP_SF_d
0x18005a1c9  mov     eax, ebx
0x18005a1cb  mov     rcx, [rsp+48h+var_10]
0x18005a1d0  xor     rcx, rsp; StackCookie
0x18005a1d3  call    __security_check_cookie
0x18005a1d8  mov     rbx, [rsp+48h+arg_0]
0x18005a1dd  mov     rsi, [rsp+48h+arg_18]
0x18005a1e2  add     rsp, 40h
0x18005a1e6  pop     rdi
0x18005a1e7  retn
```
