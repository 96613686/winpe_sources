# OsEventsSystemRestored

- ea: `0x1800c2a28`
- end: `0x1800c2c11`
- name: `OsEventsSystemRestored`
- size: `489`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180093d78`

## callees

- `0x180006770`
- `0x180017b98`
- `0x18009aee0`
- `0x18009bb88`
- `0x1800c2a28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800c2bd6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800c2bd6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800c2bc8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800c2bc8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c2b62`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c2b91`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c2b62`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c2b91`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c2bc0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c2bc0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c2b2b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c2b2b`

## pseudocode

```c
bool OsEventsSystemRestored()
{
  bool v0; // bl
  HKEY *phkResult; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t ValueName[16]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[64]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE v8[128]; // [rsp+E0h] [rbp-20h] BYREF
  BYTE Data[128]; // [rsp+160h] [rbp+60h] BYREF

  wcscpy(SubKey, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\SystemResore");
  wcscpy(ValueName, L"LaststoreId");
  memset_0(v8, 0, sizeof(v8));
  memset_0(Data, 0, sizeof(Data));
  v0 = 0;
  Type = 0;
  cbData = 0;
  if ( !qword_180111DC8 )
    return 0;
  hKey = 0;
  phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, phkResult) )
  {
    cbData = 128;
    RegQueryValueExW(qword_180111DC8, ValueName, 0, 0, Data, &cbData);
    cbData = 128;
    if ( RegQueryValueExW(hKey, ValueName, 0, &Type, v8, &cbData) )
    {
      RegDeleteValueW(qword_180111DC8, ValueName);
    }
    else
    {
      cbData = 128;
      RegSetValueExW(qword_180111DC8, ValueName, 0, Type, v8, 0x80u);
    }
    v0 = (unsigned int)_o__wcsicmp(v8, Data) != 0;
  }
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  return v0;
}

```

## disassembly

```asm
0x1800c2a28  mov     [rsp-8+arg_0], rbx
0x1800c2a2d  mov     [rsp-8+arg_8], rdi
0x1800c2a32  push    rbp
0x1800c2a33  lea     rbp, [rsp-0F0h]
0x1800c2a3b  sub     rsp, 1F0h
0x1800c2a42  mov     rax, cs:__security_cookie
0x1800c2a49  xor     rax, rsp
0x1800c2a4c  mov     [rbp+0F0h+var_10], rax
0x1800c2a53  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800c2a5a  lea     rcx, [rbp+0F0h+var_110]; void *
0x1800c2a5e  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_4+10h; "\\Microsoft\\Windows NT\\CurrentVersion"...
0x1800c2a65  mov     edi, 80h
0x1800c2a6a  movaps  xmmword ptr [rsp+1F0h+SubKey], xmm0
0x1800c2a6f  mov     r8d, edi; Size
0x1800c2a72  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_4+20h; "ft\\Windows NT\\CurrentVersion\\SystemR"...
0x1800c2a79  xor     edx, edx; Val
0x1800c2a7b  movaps  [rsp+1F0h+var_180], xmm1
0x1800c2a80  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_4+30h; "ws NT\\CurrentVersion\\SystemRestore"
0x1800c2a87  movaps  [rbp+0F0h+var_170], xmm0
0x1800c2a8b  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_4+40h; "rrentVersion\\SystemRestore"
0x1800c2a92  movaps  [rbp+0F0h+var_160], xmm1
0x1800c2a96  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_4+50h; "sion\\SystemRestore"
0x1800c2a9d  movaps  [rbp+0F0h+var_150], xmm0
0x1800c2aa1  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_4+60h; "temRestore"
0x1800c2aa8  movaps  [rbp+0F0h+var_140], xmm1
0x1800c2aac  movsd   xmm1, qword ptr cs:aSoftwareMicros_4+6Eh; "ore"
0x1800c2ab4  movaps  [rbp+0F0h+var_130], xmm0
0x1800c2ab8  movups  xmm0, xmmword ptr cs:aLastrestoreid; "LastRestoreId"
0x1800c2abf  movsd   qword ptr [rbp+0F0h+var_130+0Eh], xmm1
0x1800c2ac4  movups  xmm1, xmmword ptr cs:aLastrestoreid+0Ch; "storeId"
0x1800c2acb  movups  xmmword ptr [rsp+1F0h+ValueName], xmm0
0x1800c2ad0  movups  xmmword ptr [rsp+1F0h+ValueName+0Ch], xmm1
0x1800c2ad5  call    memset_0
0x1800c2ada  mov     r8d, edi; Size
0x1800c2add  lea     rcx, [rbp+0F0h+Data]; void *
0x1800c2ae1  xor     edx, edx; Val
0x1800c2ae3  call    memset_0
0x1800c2ae8  xor     ebx, ebx
0x1800c2aea  cmp     cs:qword_180111DC8, rbx
0x1800c2af1  mov     [rsp+1F0h+Type], ebx
0x1800c2af5  mov     [rsp+1F0h+cbData], ebx
0x1800c2af9  jnz     short loc_1800C2B02
0x1800c2afb  xor     al, al
0x1800c2afd  jmp     loc_1800C2BED
0x1800c2b02  lea     rcx, [rsp+1F0h+hKey]
0x1800c2b07  mov     [rsp+1F0h+hKey], rbx
0x1800c2b0c  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800c2b11  mov     r9d, 20019h; samDesired
0x1800c2b17  mov     [rsp+1F0h+phkResult], rax; phkResult
0x1800c2b1c  xor     r8d, r8d; ulOptions
0x1800c2b1f  lea     rdx, [rsp+1F0h+SubKey]; lpSubKey
0x1800c2b24  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c2b2b  call    cs:__imp_RegOpenKeyExW
0x1800c2b31  test    eax, eax
0x1800c2b33  jnz     loc_1800C2BE1
0x1800c2b39  mov     rcx, cs:qword_180111DC8; hKey
0x1800c2b40  lea     rax, [rsp+1F0h+cbData]
0x1800c2b45  mov     [rsp+1F0h+lpcbData], rax; lpcbData
0x1800c2b4a  lea     rdx, [rsp+1F0h+ValueName]; lpValueName
0x1800c2b4f  lea     rax, [rbp+0F0h+Data]
0x1800c2b53  mov     [rsp+1F0h+cbData], edi
0x1800c2b57  xor     r9d, r9d; lpType
0x1800c2b5a  mov     [rsp+1F0h+phkResult], rax; lpData
0x1800c2b5f  xor     r8d, r8d; lpReserved
0x1800c2b62  call    cs:__imp_RegQueryValueExW
0x1800c2b68  mov     rcx, [rsp+1F0h+hKey]; hKey
0x1800c2b6d  lea     rax, [rsp+1F0h+cbData]
0x1800c2b72  mov     [rsp+1F0h+lpcbData], rax; lpcbData
0x1800c2b77  lea     r9, [rsp+1F0h+Type]; lpType
0x1800c2b7c  lea     rax, [rbp+0F0h+var_110]
0x1800c2b80  mov     [rsp+1F0h+cbData], edi
0x1800c2b84  xor     r8d, r8d; lpReserved
0x1800c2b87  mov     [rsp+1F0h+phkResult], rax; lpData
0x1800c2b8c  lea     rdx, [rsp+1F0h+ValueName]; lpValueName
0x1800c2b91  call    cs:__imp_RegQueryValueExW
0x1800c2b97  mov     rcx, cs:qword_180111DC8; hKey
0x1800c2b9e  lea     rdx, [rsp+1F0h+ValueName]; lpValueName
0x1800c2ba3  test    eax, eax
0x1800c2ba5  jnz     short loc_1800C2BC8
0x1800c2ba7  mov     r9d, [rsp+1F0h+Type]; dwType
0x1800c2bac  lea     rax, [rbp+0F0h+var_110]
0x1800c2bb0  mov     dword ptr [rsp+1F0h+lpcbData], edi; cbData
0x1800c2bb4  xor     r8d, r8d; Reserved
0x1800c2bb7  mov     [rsp+1F0h+phkResult], rax; lpData
0x1800c2bbc  mov     [rsp+1F0h+cbData], edi
0x1800c2bc0  call    cs:__imp_RegSetValueExW
0x1800c2bc6  jmp     short loc_1800C2BCE
0x1800c2bc8  call    cs:__imp_RegDeleteValueW
0x1800c2bce  lea     rdx, [rbp+0F0h+Data]
0x1800c2bd2  lea     rcx, [rbp+0F0h+var_110]
0x1800c2bd6  call    cs:__imp__o__wcsicmp
0x1800c2bdc  test    eax, eax
0x1800c2bde  setnz   bl
0x1800c2be1  lea     rcx, [rsp+1F0h+hKey]
0x1800c2be6  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800c2beb  mov     al, bl
0x1800c2bed  mov     rcx, [rbp+0F0h+var_10]
0x1800c2bf4  xor     rcx, rsp; StackCookie
0x1800c2bf7  call    __security_check_cookie
0x1800c2bfc  lea     r11, [rsp+1F0h+var_s0]
0x1800c2c04  mov     rbx, [r11+10h]
0x1800c2c08  mov     rdi, [r11+18h]
0x1800c2c0c  mov     rsp, r11
0x1800c2c0f  pop     rbp
0x1800c2c10  retn
```
