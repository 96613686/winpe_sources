# FExistsCLSID

- ea: `0x1800517a4`
- end: `0x18005187a`
- name: `FExistsCLSID`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180051a00`

## callees

- `0x1800517a4`
- `0x180051964`
- `0x180079490`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x1800517f6`
- `ADVAPI32!RegOpenKeyExA` at `0x180051827`
- `ADVAPI32!RegOpenKeyExA` at `0x1800517f6`
- `ADVAPI32!RegOpenKeyExA` at `0x180051827`
- `ADVAPI32!RegCloseKey` at `0x18005183c`
- `ADVAPI32!RegCloseKey` at `0x180051852`
- `ADVAPI32!RegCloseKey` at `0x18005183c`
- `ADVAPI32!RegCloseKey` at `0x180051852`

## string_xrefs

- `0x1800517e8`: `CLSID`

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
0x1800517a4  push    rbx
0x1800517a6  sub     rsp, 0C0h
0x1800517ad  mov     rax, cs:__security_cookie
0x1800517b4  xor     rax, rsp
0x1800517b7  mov     [rsp+0C8h+var_18], rax
0x1800517bf  xor     ebx, ebx
0x1800517c1  lea     rdx, [rsp+0C8h+SubKey]; char *
0x1800517c6  mov     [rsp+0C8h+hKey], rbx
0x1800517cb  mov     [rsp+0C8h+var_90], rbx
0x1800517d0  call    ?StringFromGuidA@@YAHAEBU_GUID@@PEADI@Z; StringFromGuidA(_GUID const &,char *,uint)
0x1800517d5  lea     rax, [rsp+0C8h+hKey]
0x1800517da  mov     r9d, 2000000h; samDesired
0x1800517e0  xor     r8d, r8d; ulOptions
0x1800517e3  mov     [rsp+0C8h+phkResult], rax; phkResult
0x1800517e8  lea     rdx, aClsid; "CLSID"
0x1800517ef  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800517f6  call    cs:__imp_RegOpenKeyExA
0x1800517fd  nop     dword ptr [rax+rax+00h]
0x180051802  test    eax, eax
0x180051804  jz      short loc_18005180A
0x180051806  xor     eax, eax
0x180051808  jmp     short loc_180051860
0x18005180a  mov     rcx, [rsp+0C8h+hKey]; hKey
0x18005180f  lea     rax, [rsp+0C8h+var_90]
0x180051814  mov     r9d, 2000000h; samDesired
0x18005181a  mov     [rsp+0C8h+phkResult], rax; phkResult
0x18005181f  xor     r8d, r8d; ulOptions
0x180051822  lea     rdx, [rsp+0C8h+SubKey]; lpSubKey
0x180051827  call    cs:__imp_RegOpenKeyExA
0x18005182e  nop     dword ptr [rax+rax+00h]
0x180051833  test    eax, eax
0x180051835  jnz     short loc_18005184D
0x180051837  mov     rcx, [rsp+0C8h+var_90]; hKey
0x18005183c  call    cs:__imp_RegCloseKey
0x180051843  nop     dword ptr [rax+rax+00h]
0x180051848  mov     ebx, 1
0x18005184d  mov     rcx, [rsp+0C8h+hKey]; hKey
0x180051852  call    cs:__imp_RegCloseKey
0x180051859  nop     dword ptr [rax+rax+00h]
0x18005185e  mov     eax, ebx
0x180051860  mov     rcx, [rsp+0C8h+var_18]
0x180051868  xor     rcx, rsp; StackCookie
0x18005186b  call    __security_check_cookie
0x180051870  add     rsp, 0C0h
0x180051877  pop     rbx
0x180051878  retn
```
