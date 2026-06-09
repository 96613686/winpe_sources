# CreateShellSessionKey(ulong,HKEY__ * *)

- ea: `0x180426c84`
- end: `0x180426d50`
- name: `?CreateShellSessionKey@@YAJKPEAPEAUHKEY__@@@Z`
- size: `204`
- prototype: `int(unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180429d48`

## callees

- `0x1800469e8`
- `0x18015cb00`
- `0x180426c84`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180426cb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180426cb1`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180426cbe`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180426cbe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180426d25`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180426d25`

## pseudocode

```c
LSTATUS __fastcall CreateShellSessionKey(__int64 a1, HKEY *a2)
{
  DWORD CurrentProcessId; // eax
  LSTATUS result; // eax
  DWORD pSessionId; // [rsp+50h] [rbp-C8h] BYREF
  DWORD dwDisposition[3]; // [rsp+54h] [rbp-C4h] BYREF
  WCHAR SubKey[80]; // [rsp+60h] [rbp-B8h] BYREF

  *a2 = 0;
  pSessionId = 0;
  CurrentProcessId = GetCurrentProcessId();
  ProcessIdToSessionId(CurrentProcessId, &pSessionId);
  result = StringCchPrintfW(
             SubKey,
             0x4Bu,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\SessionInfo\\%d",
             pSessionId);
  if ( result >= 0 )
  {
    dwDisposition[0] = 0;
    result = RegCreateKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0, 1u, 4u, 0, a2, dwDisposition);
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180426c84  push    rbx
0x180426c86  sub     rsp, 110h
0x180426c8d  mov     rax, cs:__security_cookie
0x180426c94  xor     rax, rsp
0x180426c97  mov     [rsp+118h+var_18], rax
0x180426c9f  mov     rbx, rdx
0x180426ca2  mov     qword ptr [rdx], 0
0x180426ca9  mov     [rsp+118h+pSessionId], 0
0x180426cb1  call    cs:__imp_GetCurrentProcessId
0x180426cb7  mov     ecx, eax; dwProcessId
0x180426cb9  lea     rdx, [rsp+118h+pSessionId]; pSessionId
0x180426cbe  call    cs:__imp_ProcessIdToSessionId
0x180426cc4  mov     r9d, [rsp+118h+pSessionId]
0x180426cc9  lea     r8, ?shellSessionKeyFormat@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180426cd0  mov     edx, 4Bh ; 'K'; unsigned __int64
0x180426cd5  lea     rcx, [rsp+118h+SubKey]; wchar_t *
0x180426cda  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180426cdf  test    eax, eax
0x180426ce1  js      short loc_180426D37
0x180426ce3  lea     rax, [rsp+118h+dwDisposition]
0x180426ce8  mov     [rsp+118h+dwDisposition], 0
0x180426cf0  mov     [rsp+118h+lpdwDisposition], rax; lpdwDisposition
0x180426cf5  lea     rdx, [rsp+118h+SubKey]; lpSubKey
0x180426cfa  mov     [rsp+118h+phkResult], rbx; phkResult
0x180426cff  xor     r9d, r9d; lpClass
0x180426d02  mov     [rsp+118h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180426d0b  xor     r8d, r8d; Reserved
0x180426d0e  mov     [rsp+118h+samDesired], 4; samDesired
0x180426d16  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180426d1d  mov     [rsp+118h+dwOptions], 1; dwOptions
0x180426d25  call    cs:__imp_RegCreateKeyExW
0x180426d2b  test    eax, eax
0x180426d2d  jle     short loc_180426D37
0x180426d2f  movzx   eax, ax
0x180426d32  or      eax, 80070000h
0x180426d37  mov     rcx, [rsp+118h+var_18]
0x180426d3f  xor     rcx, rsp; StackCookie
0x180426d42  call    __security_check_cookie
0x180426d47  add     rsp, 110h
0x180426d4e  pop     rbx
0x180426d4f  retn
```
