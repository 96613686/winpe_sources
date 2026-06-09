# CreateShellSessionKey(ulong,HKEY__ * *)

- ea: `0x18003ffe8`
- end: `0x1800400b4`
- name: `?CreateShellSessionKey@@YAJKPEAPEAUHKEY__@@@Z`
- size: `204`
- prototype: `LSTATUS __fastcall(__int64, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180029130`

## callees

- `0x1800228e8`
- `0x18002b1b0`
- `0x18003ffe8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180040022`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180040022`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180040015`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180040015`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180040089`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180040089`

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
0x18003ffe8  push    rbx
0x18003ffea  sub     rsp, 110h
0x18003fff1  mov     rax, cs:__security_cookie
0x18003fff8  xor     rax, rsp
0x18003fffb  mov     [rsp+118h+var_18], rax
0x180040003  mov     rbx, rdx
0x180040006  mov     qword ptr [rdx], 0
0x18004000d  mov     [rsp+118h+pSessionId], 0
0x180040015  call    cs:__imp_GetCurrentProcessId
0x18004001b  mov     ecx, eax; dwProcessId
0x18004001d  lea     rdx, [rsp+118h+pSessionId]; pSessionId
0x180040022  call    cs:__imp_ProcessIdToSessionId
0x180040028  mov     r9d, [rsp+118h+pSessionId]
0x18004002d  lea     r8, ?shellSessionKeyFormat@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180040034  mov     edx, 4Bh ; 'K'; unsigned __int64
0x180040039  lea     rcx, [rsp+118h+SubKey]; unsigned __int16 *
0x18004003e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180040043  test    eax, eax
0x180040045  js      short loc_18004009B
0x180040047  lea     rax, [rsp+118h+dwDisposition]
0x18004004c  mov     [rsp+118h+dwDisposition], 0
0x180040054  mov     [rsp+118h+lpdwDisposition], rax; lpdwDisposition
0x180040059  lea     rdx, [rsp+118h+SubKey]; lpSubKey
0x18004005e  mov     [rsp+118h+phkResult], rbx; phkResult
0x180040063  xor     r9d, r9d; lpClass
0x180040066  mov     [rsp+118h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18004006f  xor     r8d, r8d; Reserved
0x180040072  mov     [rsp+118h+samDesired], 4; samDesired
0x18004007a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180040081  mov     [rsp+118h+dwOptions], 1; dwOptions
0x180040089  call    cs:__imp_RegCreateKeyExW
0x18004008f  test    eax, eax
0x180040091  jle     short loc_18004009B
0x180040093  movzx   eax, ax
0x180040096  or      eax, 80070000h
0x18004009b  mov     rcx, [rsp+118h+var_18]
0x1800400a3  xor     rcx, rsp; StackCookie
0x1800400a6  call    __security_check_cookie
0x1800400ab  add     rsp, 110h
0x1800400b2  pop     rbx
0x1800400b3  retn
```
