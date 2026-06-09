# CLuaSettingsChecktoid::GetStatusRegistryOnly(ushort const *)

- ea: `0x180003920`
- end: `0x180003a75`
- name: `?GetStatusRegistryOnly@CLuaSettingsChecktoid@@SAKPEBG@Z`
- size: `341`
- prototype: `_BOOL8 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002fc0`

## callees

- `0x180003920`
- `0x180003cd8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003962`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003962`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003a29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003a29`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800039be`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003a1a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800039be`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003a1a`

## pseudocode

```c
_BOOL8 __fastcall CLuaSettingsChecktoid::GetStatusRegistryOnly(LPCWSTR lpSubKey)
{
  BOOL v1; // ebx
  HKEY hKey; // [rsp+50h] [rbp-28h] BYREF
  DWORD Type; // [rsp+88h] [rbp+10h] BYREF
  int Data; // [rsp+90h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+20h] BYREF

  v1 = 0;
  hKey = 0;
  if ( !RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 1u, 0, &hKey, 0) )
  {
    Data = 0;
    cbData = 4;
    Type = 4;
    if ( !RegQueryValueExW(hKey, L"EnableLUA", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      v1 = Data == 0;
    Data = 0;
    cbData = 4;
    Type = 4;
    if ( !RegQueryValueExW(hKey, L"ConsentPromptBehaviorAdmin", 0, &Type, (LPBYTE)&Data, &cbData)
      && !Data
      && Type == 4
      && CLuaSettingsChecktoid::GetTokenType() == 1 )
    {
      v1 = 1;
    }
    RegCloseKey(hKey);
  }
  return v1;
}

```

## disassembly

```asm
0x180003920  push    rbx
0x180003922  push    rsi
0x180003923  push    rdi
0x180003924  sub     rsp, 60h
0x180003928  xor     edi, edi
0x18000392a  lea     rax, [rsp+78h+hKey]
0x18000392f  mov     [rsp+78h+lpdwDisposition], rdi; lpdwDisposition
0x180003934  mov     rdx, rcx; lpSubKey
0x180003937  mov     [rsp+78h+phkResult], rax; phkResult
0x18000393c  mov     esi, 1
0x180003941  mov     [rsp+78h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180003946  xor     r9d, r9d; lpClass
0x180003949  mov     [rsp+78h+samDesired], esi; samDesired
0x18000394d  xor     r8d, r8d; Reserved
0x180003950  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003957  mov     [rsp+78h+dwOptions], edi; dwOptions
0x18000395b  mov     ebx, edi
0x18000395d  mov     [rsp+78h+hKey], rdi
0x180003962  call    cs:__imp_RegCreateKeyExW
0x180003968  test    eax, eax
0x18000396a  jnz     loc_180003A2F
0x180003970  mov     rcx, [rsp+78h+hKey]; hKey
0x180003975  lea     rax, [rsp+78h+cbData]
0x18000397d  mov     qword ptr [rsp+78h+samDesired], rax; lpcbData
0x180003982  lea     r9, [rsp+78h+Type]; lpType
0x18000398a  lea     rax, [rsp+78h+Data]
0x180003992  mov     [rsp+78h+Data], edi
0x180003999  xor     r8d, r8d; lpReserved
0x18000399c  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x1800039a1  lea     rdx, aEnablelua; "EnableLUA"
0x1800039a8  mov     [rsp+78h+cbData], 4
0x1800039b3  mov     [rsp+78h+Type], 4
0x1800039be  call    cs:__imp_RegQueryValueExW
0x1800039c4  test    eax, eax
0x1800039c6  jz      loc_180003A58
0x1800039cc  mov     rcx, [rsp+78h+hKey]; hKey
0x1800039d1  lea     rax, [rsp+78h+cbData]
0x1800039d9  mov     qword ptr [rsp+78h+samDesired], rax; lpcbData
0x1800039de  lea     r9, [rsp+78h+Type]; lpType
0x1800039e6  lea     rax, [rsp+78h+Data]
0x1800039ee  mov     [rsp+78h+Data], edi
0x1800039f5  xor     r8d, r8d; lpReserved
0x1800039f8  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x1800039fd  lea     rdx, aConsentpromptb; "ConsentPromptBehaviorAdmin"
0x180003a04  mov     [rsp+78h+cbData], 4
0x180003a0f  mov     [rsp+78h+Type], 4
0x180003a1a  call    cs:__imp_RegQueryValueExW
0x180003a20  test    eax, eax
0x180003a22  jz      short loc_180003A39
0x180003a24  mov     rcx, [rsp+78h+hKey]; hKey
0x180003a29  call    cs:__imp_RegCloseKey
0x180003a2f  mov     eax, ebx
0x180003a31  add     rsp, 60h
0x180003a35  pop     rdi
0x180003a36  pop     rsi
0x180003a37  pop     rbx
0x180003a38  retn
0x180003a39  cmp     [rsp+78h+Data], edi
0x180003a40  jnz     short loc_180003A24
0x180003a42  cmp     [rsp+78h+Type], 4
0x180003a4a  jnz     short loc_180003A24
0x180003a4c  call    ?GetTokenType@CLuaSettingsChecktoid@@CAKXZ; CLuaSettingsChecktoid::GetTokenType(void)
0x180003a51  cmp     eax, esi
0x180003a53  cmovz   ebx, esi
0x180003a56  jmp     short loc_180003A24
0x180003a58  cmp     [rsp+78h+Type], 4
0x180003a60  jnz     loc_1800039CC
0x180003a66  cmp     [rsp+78h+Data], ebx
0x180003a6d  cmovz   ebx, esi
0x180003a70  jmp     loc_1800039CC
```
