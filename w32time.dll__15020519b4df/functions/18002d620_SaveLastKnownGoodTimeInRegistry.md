# SaveLastKnownGoodTimeInRegistry

- ea: `0x18002d620`
- end: `0x18002d7d5`
- name: `SaveLastKnownGoodTimeInRegistry`
- size: `437`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18001da40`
- `0x18002aa44`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x18002d620`
- `0x18003d270`
- `0x18003dd2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d73f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d73f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d7c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800677c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d7c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800677c5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d787`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d787`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002d6e4`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002d6e4`

## string_xrefs

- `0x18002d6dd`: `W32TimeConfig`
- `0x18002d6d6`: `System\CurrentControlSet\Services\W32Time\Config`
- `0x18002d708`: `System\CurrentControlSet\Services\W32Time\Config`
- `0x18002d75c`: `Failed to open config regkey. Error: 0x%x\n`

## pseudocode

```c
LSTATUS __fastcall SaveLastKnownGoodTimeInRegistry(BYTE *lpData)
{
  __int64 v2; // rax
  BOOL v3; // eax
  LSTATUS result; // eax
  unsigned int PersistedRegistryLocationW; // ebx
  unsigned int v6; // ebx
  unsigned int v7; // ebx
  HKEY hKey; // [rsp+30h] [rbp-238h] BYREF
  WCHAR SubKey; // [rsp+40h] [rbp-228h] BYREF
  _BYTE v10[526]; // [rsp+42h] [rbp-226h] BYREF

  hKey = 0;
  SubKey = 0;
  memset_0(v10, 0, 0x206u);
  v2 = HIDWORD(*(_QWORD *)lpData);
  if ( (unsigned int)v2 > 0x1D0CBED || ((_DWORD)v2 != 30460909 ? (v3 = 0) : (v3 = *(_DWORD *)lpData > 0x24C8000u), v3) )
  {
    PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                   L"W32TimeConfig",
                                   L"System\\CurrentControlSet\\Services\\W32Time\\Config",
                                   &SubKey,
                                   520,
                                   0);
    if ( PersistedRegistryLocationW )
    {
      result = FileLogAllowEntry(0);
      if ( (_BYTE)result )
        result = FileLogAdd(
                   L"Failed to get time regkey %s. Error: 0x%x\n",
                   L"System\\CurrentControlSet\\Services\\W32Time\\Config",
                   PersistedRegistryLocationW);
    }
    else
    {
      v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, &SubKey, 0, 3u, &hKey);
      if ( v6 )
      {
        result = FileLogAllowEntry(0);
        if ( (_BYTE)result )
          result = FileLogAdd(L"Failed to open config regkey. Error: 0x%x\n", v6);
      }
      else
      {
        result = RegSetValueExW(hKey, L"LastKnownGoodTime", 0, 0xBu, lpData, 8u);
        v7 = result;
        if ( result )
        {
          result = FileLogAllowEntry(1001);
          if ( (_BYTE)result )
            result = FileLogAdd(L"Failed to save LKG time. RetVal: 0x%x\n", v7);
        }
      }
    }
    if ( hKey )
      return RegCloseKey(hKey);
  }
  else
  {
    result = FileLogAllowEntry(0);
    if ( (_BYTE)result )
      return FileLogAdd(L"LKG Time value is too low.\n");
  }
  return result;
}

```

## disassembly

```asm
0x18002d620  mov     [rsp+arg_8], rbx
0x18002d625  push    rdi
0x18002d626  sub     rsp, 260h
0x18002d62d  mov     rax, cs:__security_cookie
0x18002d634  xor     rax, rsp
0x18002d637  mov     [rsp+268h+var_18], rax
0x18002d63f  mov     rdi, rcx
0x18002d642  mov     [rsp+268h+hKey], 0
0x18002d64b  xor     eax, eax
0x18002d64d  mov     [rsp+268h+SubKey], ax
0x18002d652  xor     edx, edx; Val
0x18002d654  mov     r8d, 206h; Size
0x18002d65a  lea     rcx, [rsp+268h+var_226]; void *
0x18002d65f  call    memset_0
0x18002d664  mov     rax, [rdi]
0x18002d667  shr     rax, 20h
0x18002d66b  mov     ecx, 1D0CBEDh
0x18002d670  cmp     eax, ecx
0x18002d672  ja      short loc_18002D6C2
0x18002d674  jnz     short loc_18002D683
0x18002d676  xor     eax, eax
0x18002d678  cmp     dword ptr [rdi], 24C8000h
0x18002d67e  setnbe  al
0x18002d681  jmp     short loc_18002D685
0x18002d683  xor     eax, eax
0x18002d685  test    eax, eax
0x18002d687  jnz     short loc_18002D6C2
0x18002d689  xor     ecx, ecx
0x18002d68b  call    FileLogAllowEntry
0x18002d690  test    al, al
0x18002d692  jz      short loc_18002D6A0
0x18002d694  lea     rcx, aLkgTimeValueIs; "LKG Time value is too low.\n"
0x18002d69b  call    FileLogAdd
0x18002d6a0  mov     rcx, [rsp+268h+var_18]
0x18002d6a8  xor     rcx, rsp; StackCookie
0x18002d6ab  call    __security_check_cookie
0x18002d6b0  mov     rbx, [rsp+268h+arg_8]
0x18002d6b8  add     rsp, 260h
0x18002d6bf  pop     rdi
0x18002d6c0  retn
0x18002d6c2  mov     [rsp+268h+phkResult], 0
0x18002d6cb  mov     r9d, 208h
0x18002d6d1  lea     r8, [rsp+268h+SubKey]
0x18002d6d6  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x18002d6dd  lea     rcx, aW32timeconfig; "W32TimeConfig"
0x18002d6e4  call    cs:__imp_GetPersistedRegistryLocationW
0x18002d6eb  nop     dword ptr [rax+rax+00h]
0x18002d6f0  mov     ebx, eax
0x18002d6f2  test    eax, eax
0x18002d6f4  jz      short loc_18002D720
0x18002d6f6  xor     ecx, ecx
0x18002d6f8  call    FileLogAllowEntry
0x18002d6fd  test    al, al
0x18002d6ff  jz      loc_18002D7B6
0x18002d705  mov     r8d, ebx
0x18002d708  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x18002d70f  lea     rcx, aFailedToGetTim; "Failed to get time regkey %s. Error: 0x"...
0x18002d716  call    FileLogAdd
0x18002d71b  jmp     loc_18002D7B6
0x18002d720  lea     rax, [rsp+268h+hKey]
0x18002d725  mov     [rsp+268h+phkResult], rax; phkResult
0x18002d72a  mov     r9d, 3; samDesired
0x18002d730  xor     r8d, r8d; ulOptions
0x18002d733  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x18002d738  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d73f  call    cs:__imp_RegOpenKeyExW
0x18002d746  nop     dword ptr [rax+rax+00h]
0x18002d74b  mov     ebx, eax
0x18002d74d  test    eax, eax
0x18002d74f  jz      short loc_18002D765
0x18002d751  xor     ecx, ecx
0x18002d753  call    FileLogAllowEntry
0x18002d758  test    al, al
0x18002d75a  jz      short loc_18002D7B6
0x18002d75c  lea     rcx, aFailedToOpenCo; "Failed to open config regkey. Error: 0x"...
0x18002d763  jmp     short loc_18002D7AE
0x18002d765  mov     [rsp+268h+cbData], 8; cbData
0x18002d76d  mov     [rsp+268h+phkResult], rdi; lpData
0x18002d772  mov     r9d, 0Bh; dwType
0x18002d778  xor     r8d, r8d; Reserved
0x18002d77b  lea     rdx, aLastknowngoodt; "LastKnownGoodTime"
0x18002d782  mov     rcx, [rsp+268h+hKey]; hKey
0x18002d787  call    cs:__imp_RegSetValueExW
0x18002d78e  nop     dword ptr [rax+rax+00h]
0x18002d793  mov     ebx, eax
0x18002d795  test    eax, eax
0x18002d797  jz      short loc_18002D7B6
0x18002d799  mov     ecx, 3E9h
0x18002d79e  call    FileLogAllowEntry
0x18002d7a3  test    al, al
0x18002d7a5  jz      short loc_18002D7B6
0x18002d7a7  lea     rcx, aFailedToSaveLk; "Failed to save LKG time. RetVal: 0x%x\n"
0x18002d7ae  mov     edx, ebx
0x18002d7b0  call    FileLogAdd
0x18002d7b5  nop
0x18002d7b6  mov     rcx, [rsp+268h+hKey]; hKey
0x18002d7bb  test    rcx, rcx
0x18002d7be  jz      loc_18002D6A0
0x18002d7c4  call    cs:__imp_RegCloseKey
0x18002d7cb  nop     dword ptr [rax+rax+00h]
0x18002d7d0  jmp     loc_18002D6A0
0x1800677b3  push    rbp
0x1800677b5  sub     rsp, 30h
0x1800677b9  mov     rbp, rdx
0x1800677bc  mov     rcx, [rbp+30h]; hKey
0x1800677c0  test    rcx, rcx
0x1800677c3  jz      short loc_1800677D2
0x1800677c5  call    cs:__imp_RegCloseKey
0x1800677cc  nop     dword ptr [rax+rax+00h]
0x1800677d1  nop
0x1800677d2  add     rsp, 30h
0x1800677d6  pop     rbp
0x1800677d7  retn
```
