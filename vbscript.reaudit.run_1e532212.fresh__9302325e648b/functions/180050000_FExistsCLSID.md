# FExistsCLSID

- ea: `0x180050000`
- end: `0x1800500bd`
- name: `FExistsCLSID`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180050244`

## callees

- `0x180050000`
- `0x1800501ac`
- `0x1800767a0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x180050052`
- `ADVAPI32!RegOpenKeyExA` at `0x18005007d`
- `ADVAPI32!RegOpenKeyExA` at `0x180050052`
- `ADVAPI32!RegOpenKeyExA` at `0x18005007d`
- `ADVAPI32!RegCloseKey` at `0x18005008c`
- `ADVAPI32!RegCloseKey` at `0x18005009c`
- `ADVAPI32!RegCloseKey` at `0x18005008c`
- `ADVAPI32!RegCloseKey` at `0x18005009c`

## string_xrefs

- `0x180050044`: `CLSID`

## pseudocode

```c
__int64 __fastcall FExistsCLSID(const struct _GUID *a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // ebx
  HKEY hKey; // [rsp+30h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-90h] BYREF
  CHAR SubKey[112]; // [rsp+40h] [rbp-88h] BYREF

  v3 = 0;
  hKey = 0;
  phkResult = 0;
  StringFromGuidA(a1, SubKey, a3);
  if ( RegOpenKeyExA(HKEY_CLASSES_ROOT, "CLSID", 0, 0x2000000u, &hKey) )
    return 0;
  if ( !RegOpenKeyExA(hKey, SubKey, 0, 0x2000000u, &phkResult) )
  {
    RegCloseKey(phkResult);
    v3 = 1;
  }
  RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x180050000  push    rbx
0x180050002  sub     rsp, 0C0h
0x180050009  mov     rax, cs:__security_cookie
0x180050010  xor     rax, rsp
0x180050013  mov     [rsp+0C8h+var_18], rax
0x18005001b  xor     ebx, ebx
0x18005001d  lea     rdx, [rsp+0C8h+SubKey]; char *
0x180050022  mov     [rsp+0C8h+hKey], rbx
0x180050027  mov     [rsp+0C8h+var_90], rbx
0x18005002c  call    ?StringFromGuidA@@YAHAEBU_GUID@@PEADI@Z; StringFromGuidA(_GUID const &,char *,uint)
0x180050031  lea     rax, [rsp+0C8h+hKey]
0x180050036  mov     r9d, 2000000h; samDesired
0x18005003c  xor     r8d, r8d; ulOptions
0x18005003f  mov     [rsp+0C8h+phkResult], rax; phkResult
0x180050044  lea     rdx, aClsid; "CLSID"
0x18005004b  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180050052  call    cs:__imp_RegOpenKeyExA
0x180050058  test    eax, eax
0x18005005a  jz      short loc_180050060
0x18005005c  xor     eax, eax
0x18005005e  jmp     short loc_1800500A4
0x180050060  mov     rcx, [rsp+0C8h+hKey]; hKey
0x180050065  lea     rax, [rsp+0C8h+var_90]
0x18005006a  mov     r9d, 2000000h; samDesired
0x180050070  mov     [rsp+0C8h+phkResult], rax; phkResult
0x180050075  xor     r8d, r8d; ulOptions
0x180050078  lea     rdx, [rsp+0C8h+SubKey]; lpSubKey
0x18005007d  call    cs:__imp_RegOpenKeyExA
0x180050083  test    eax, eax
0x180050085  jnz     short loc_180050097
0x180050087  mov     rcx, [rsp+0C8h+var_90]; hKey
0x18005008c  call    cs:__imp_RegCloseKey
0x180050092  mov     ebx, 1
0x180050097  mov     rcx, [rsp+0C8h+hKey]; hKey
0x18005009c  call    cs:__imp_RegCloseKey
0x1800500a2  mov     eax, ebx
0x1800500a4  mov     rcx, [rsp+0C8h+var_18]
0x1800500ac  xor     rcx, rsp; StackCookie
0x1800500af  call    __security_check_cookie
0x1800500b4  add     rsp, 0C0h
0x1800500bb  pop     rbx
0x1800500bc  retn
```
