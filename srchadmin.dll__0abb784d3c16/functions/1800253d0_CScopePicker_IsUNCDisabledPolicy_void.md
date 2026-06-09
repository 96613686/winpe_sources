# CScopePicker::_IsUNCDisabledPolicy(void)

- ea: `0x1800253d0`
- end: `0x1800254d7`
- name: `?_IsUNCDisabledPolicy@CScopePicker@@AEAAHXZ`
- size: `263`
- prototype: `__int64 __fastcall(CScopePicker *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024de8`
- `0x180025b24`

## callees

- `0x1800253d0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025456`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800254c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025456`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800254c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025446`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800254b4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025446`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800254b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025412`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025480`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025412`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025480`

## pseudocode

```c
__int64 __fastcall CScopePicker::_IsUNCDisabledPolicy(CScopePicker *this)
{
  unsigned int v1; // ebx
  DWORD cbData; // [rsp+40h] [rbp+10h] BYREF
  int v4; // [rsp+44h] [rbp+14h]
  unsigned int Data; // [rsp+48h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+20h] BYREF

  v4 = HIDWORD(this);
  v1 = 0;
  Data = 0;
  hKey = 0;
  cbData = 0;
  if ( RegOpenKeyExW(HKEY_CURRENT_USER, L"SOFTWARE\\Policies\\Microsoft\\Windows\\Windows Search", 0, 0x20019u, &hKey) )
    goto LABEL_12;
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"HideUNCTab", 0, 0, (LPBYTE)&Data, &cbData) )
    v1 = Data;
  CloseHandle(hKey);
  if ( !v1 )
  {
LABEL_12:
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Policies\\Microsoft\\Windows\\Windows Search",
            0,
            0x20019u,
            &hKey) )
    {
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"HideUNCTab", 0, 0, (LPBYTE)&Data, &cbData) )
        v1 = Data;
      CloseHandle(hKey);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800253d0  mov     [rsp-8+arg_18], rbx
0x1800253d5  mov     qword ptr [rsp-8+cbData], rcx
0x1800253da  push    rbp
0x1800253db  mov     rbp, rsp
0x1800253de  sub     rsp, 30h
0x1800253e2  xor     ebx, ebx
0x1800253e4  mov     [rbp+Data], 0
0x1800253eb  lea     rax, [rbp+hKey]
0x1800253ef  mov     [rbp+hKey], rbx
0x1800253f3  mov     r9d, 20019h; samDesired
0x1800253f9  mov     [rbp+cbData], ebx
0x1800253fc  xor     r8d, r8d; ulOptions
0x1800253ff  mov     [rsp+30h+phkResult], rax; phkResult
0x180025404  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18002540b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180025412  call    cs:__imp_RegOpenKeyExW
0x180025418  test    eax, eax
0x18002541a  jnz     short loc_180025460
0x18002541c  mov     rcx, [rbp+hKey]; hKey
0x180025420  lea     rax, [rbp+cbData]
0x180025424  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180025429  lea     rdx, aHideunctab; "HideUNCTab"
0x180025430  lea     rax, [rbp+Data]
0x180025434  mov     [rbp+cbData], 4
0x18002543b  xor     r9d, r9d; lpType
0x18002543e  mov     [rsp+30h+phkResult], rax; lpData
0x180025443  xor     r8d, r8d; lpReserved
0x180025446  call    cs:__imp_RegQueryValueExW
0x18002544c  mov     rcx, [rbp+hKey]; hObject
0x180025450  test    eax, eax
0x180025452  cmovz   ebx, [rbp+Data]
0x180025456  call    cs:__imp_CloseHandle
0x18002545c  test    ebx, ebx
0x18002545e  jnz     short loc_1800254CA
0x180025460  lea     rax, [rbp+hKey]
0x180025464  mov     r9d, 20019h; samDesired
0x18002546a  xor     r8d, r8d; ulOptions
0x18002546d  mov     [rsp+30h+phkResult], rax; phkResult
0x180025472  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180025479  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025480  call    cs:__imp_RegOpenKeyExW
0x180025486  test    eax, eax
0x180025488  jnz     short loc_1800254CA
0x18002548a  mov     rcx, [rbp+hKey]; hKey
0x18002548e  lea     rax, [rbp+cbData]
0x180025492  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180025497  lea     rdx, aHideunctab; "HideUNCTab"
0x18002549e  lea     rax, [rbp+Data]
0x1800254a2  mov     [rbp+cbData], 4
0x1800254a9  xor     r9d, r9d; lpType
0x1800254ac  mov     [rsp+30h+phkResult], rax; lpData
0x1800254b1  xor     r8d, r8d; lpReserved
0x1800254b4  call    cs:__imp_RegQueryValueExW
0x1800254ba  mov     rcx, [rbp+hKey]; hObject
0x1800254be  test    eax, eax
0x1800254c0  cmovz   ebx, [rbp+Data]
0x1800254c4  call    cs:__imp_CloseHandle
0x1800254ca  mov     eax, ebx
0x1800254cc  mov     rbx, [rsp+30h+arg_18]
0x1800254d1  add     rsp, 30h
0x1800254d5  pop     rbp
0x1800254d6  retn
```
