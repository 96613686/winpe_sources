# WluiStartup

- ea: `0x140010b10`
- end: `0x140010c72`
- name: `WluiStartup`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14008be98`

## callees

- `0x14000d4e0`
- `0x140010144`
- `0x140010b10`
- `0x140012360`
- `0x140053720`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140010c4c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140010c4c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140010c30`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140010c30`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x140010be7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x140010be7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140010b79`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140010bc4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140010b79`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140010bc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010bd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010bf2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010bd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010bf2`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x140010c23`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x140010c23`

## pseudocode

```c
__int64 __fastcall WluiStartup(__int64 a1, void *a2, DWORD *a3)
{
  ULONG SessionId; // esi
  LSTATUS v6; // eax
  HKEY v7; // rcx
  LSTATUS v8; // ebx
  int v9; // eax
  unsigned int v10; // ebx
  HKEY phkResult; // [rsp+30h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-40h] BYREF
  WCHAR SubKey[8]; // [rsp+40h] [rbp-38h] BYREF

  *a3 = 0;
  phkResult = 0;
  hKey = 0;
  SessionId = NtCurrentPeb()->SessionId;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\SessionData",
         0,
         8u,
         &hKey);
  v7 = 0;
  v8 = v6;
  phkResult = 0;
  if ( !v6 )
  {
    v9 = StringCchPrintfW(SubKey, 8u, L"%d", SessionId);
    if ( v9 < 0 )
      v8 = (unsigned __int16)v9;
    else
      v8 = RegOpenKeyExW(hKey, SubKey, 0, 0x1000Bu, &phkResult);
    RegCloseKey(hKey);
    v7 = phkResult;
  }
  if ( v8 >= 0 )
  {
    RegDeleteTreeW(v7, 0);
    RegCloseKey(phkResult);
  }
  if ( a2 )
  {
    WluiiReleaseLessPrivilegedToken();
    DuplicateTokenEx(a2, 0xBu, 0, SecurityAnonymous, TokenPrimary, &phNewToken);
  }
  EnterCriticalSection(&stru_1400D2DD0);
  v10 = WluiiStartupImpl(1u, a2, a3);
  LeaveCriticalSection(&stru_1400D2DD0);
  return v10;
}

```

## disassembly

```asm
0x140010b10  mov     r11, rsp
0x140010b13  mov     [r11+8], rbx
0x140010b17  push    rsi
0x140010b18  push    rdi
0x140010b19  push    r14
0x140010b1b  sub     rsp, 60h
0x140010b1f  mov     rax, cs:__security_cookie
0x140010b26  xor     rax, rsp
0x140010b29  mov     [rsp+78h+var_28], rax
0x140010b2e  mov     dword ptr [r8], 0
0x140010b35  mov     r14, r8
0x140010b38  mov     qword ptr [r11-48h], 0
0x140010b40  mov     rdi, rdx
0x140010b43  mov     rax, gs:60h
0x140010b4c  lea     rdx, aSoftwareMicros_43; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140010b53  mov     r9d, 8; samDesired
0x140010b59  mov     qword ptr [r11-40h], 0
0x140010b61  xor     r8d, r8d; ulOptions
0x140010b64  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140010b6b  mov     esi, [rax+2C0h]
0x140010b71  lea     rax, [r11-40h]
0x140010b75  mov     [r11-58h], rax
0x140010b79  call    cs:__imp_RegOpenKeyExW
0x140010b7f  xor     ecx, ecx
0x140010b81  mov     ebx, eax
0x140010b83  mov     [rsp+78h+var_48], rcx
0x140010b88  test    eax, eax
0x140010b8a  jnz     short loc_140010BE1
0x140010b8c  mov     r9d, esi
0x140010b8f  lea     r8, aD; "%d"
0x140010b96  lea     edx, [rax+8]; unsigned __int64
0x140010b99  lea     rcx, [rsp+78h+SubKey]; unsigned __int16 *
0x140010b9e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140010ba3  test    eax, eax
0x140010ba5  js      short loc_140010BCE
0x140010ba7  mov     rcx, [rsp+78h+hKey]; hKey
0x140010bac  lea     rax, [rsp+78h+var_48]
0x140010bb1  mov     r9d, 1000Bh; samDesired
0x140010bb7  mov     [rsp+78h+phkResult], rax; phkResult
0x140010bbc  xor     r8d, r8d; ulOptions
0x140010bbf  lea     rdx, [rsp+78h+SubKey]; lpSubKey
0x140010bc4  call    cs:__imp_RegOpenKeyExW
0x140010bca  mov     ebx, eax
0x140010bcc  jmp     short loc_140010BD1
0x140010bce  movzx   ebx, ax
0x140010bd1  mov     rcx, [rsp+78h+hKey]; hKey
0x140010bd6  call    cs:__imp_RegCloseKey
0x140010bdc  mov     rcx, [rsp+78h+var_48]; hKey
0x140010be1  test    ebx, ebx
0x140010be3  js      short loc_140010BF8
0x140010be5  xor     edx, edx; lpSubKey
0x140010be7  call    cs:__imp_RegDeleteTreeW
0x140010bed  mov     rcx, [rsp+78h+var_48]; hKey
0x140010bf2  call    cs:__imp_RegCloseKey
0x140010bf8  mov     ebx, 1
0x140010bfd  test    rdi, rdi
0x140010c00  jz      short loc_140010C29
0x140010c02  call    WluiiReleaseLessPrivilegedToken
0x140010c07  lea     rax, phNewToken
0x140010c0e  xor     r9d, r9d; ImpersonationLevel
0x140010c11  mov     [rsp+78h+phNewToken], rax; phNewToken
0x140010c16  lea     edx, [rbx+0Ah]; dwDesiredAccess
0x140010c19  xor     r8d, r8d; lpTokenAttributes
0x140010c1c  mov     dword ptr [rsp+78h+phkResult], ebx; TokenType
0x140010c20  mov     rcx, rdi; hExistingToken
0x140010c23  call    cs:__imp_DuplicateTokenEx
0x140010c29  lea     rcx, stru_1400D2DD0; lpCriticalSection
0x140010c30  call    cs:__imp_EnterCriticalSection
0x140010c36  mov     r8, r14
0x140010c39  mov     rdx, rdi
0x140010c3c  mov     ecx, ebx
0x140010c3e  call    WluiiStartupImpl
0x140010c43  lea     rcx, stru_1400D2DD0; lpCriticalSection
0x140010c4a  mov     ebx, eax
0x140010c4c  call    cs:__imp_LeaveCriticalSection
0x140010c52  mov     eax, ebx
0x140010c54  mov     rcx, [rsp+78h+var_28]
0x140010c59  xor     rcx, rsp; StackCookie
0x140010c5c  call    __security_check_cookie
0x140010c61  mov     rbx, [rsp+78h+arg_0]
0x140010c69  add     rsp, 60h
0x140010c6d  pop     r14
0x140010c6f  pop     rdi
0x140010c70  pop     rsi
0x140010c71  retn
```
