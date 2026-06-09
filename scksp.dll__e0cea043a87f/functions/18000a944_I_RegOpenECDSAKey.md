# I_RegOpenECDSAKey

- ea: `0x18000a944`
- end: `0x18000aa45`
- name: `I_RegOpenECDSAKey`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a848`

## callees

- `0x18000a944`
- `0x18000b0b0`
- `0x18000d9d0`
- `0x18002b140`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a9fe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a9fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa2d`

## pseudocode

```c
__int64 __fastcall I_RegOpenECDSAKey(HKEY *a1)
{
  wchar_t *v2; // rbx
  unsigned int v3; // edi
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  DWORD dwDisposition; // [rsp+68h] [rbp+10h] BYREF

  *a1 = 0;
  dwDisposition = 0;
  hKey = 0;
  v2 = (wchar_t *)MIDL_user_allocate(0xDAu);
  if ( v2 )
  {
    StringCbPrintfW(
      v2,
      0xDAu,
      L"%s%s\\%s",
      L"SYSTEM\\CurrentControlSet\\Control\\Cryptography\\Providers\\",
      L"Microsoft Smart Card Key Storage Provider",
      L"ECDSALogon");
    v3 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v2, 0, (LPWSTR)&Class, 0, 0x20007u, 0, &hKey, &dwDisposition);
    if ( !v3 )
    {
      *a1 = hKey;
      hKey = 0;
    }
    CspFreeH(v2);
  }
  else
  {
    v3 = 8;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x18000a944  mov     rax, rsp
0x18000a947  mov     [rax+18h], rbx
0x18000a94b  mov     [rax+20h], rsi
0x18000a94f  mov     [rax+10h], edx
0x18000a952  push    rdi
0x18000a953  sub     rsp, 50h
0x18000a957  mov     rsi, rcx
0x18000a95a  mov     qword ptr [rcx], 0
0x18000a961  mov     edi, 0DAh
0x18000a966  mov     dword ptr [rax+10h], 0
0x18000a96d  mov     ecx, edi; size
0x18000a96f  mov     qword ptr [rax+8], 0
0x18000a977  call    MIDL_user_allocate
0x18000a97c  mov     rbx, rax
0x18000a97f  test    rax, rax
0x18000a982  jnz     short loc_18000A98C
0x18000a984  lea     edi, [rax+8]
0x18000a987  jmp     loc_18000AA23
0x18000a98c  lea     rax, aEcdsalogon; "ECDSALogon"
0x18000a993  mov     rdx, rdi; cbDest
0x18000a996  mov     qword ptr [rsp+58h+samDesired], rax
0x18000a99b  lea     r9, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Cry"...
0x18000a9a2  lea     rax, aMicrosoftSmart; "Microsoft Smart Card Key Storage Provid"...
0x18000a9a9  mov     rcx, rbx; pszDest
0x18000a9ac  lea     r8, aSSS; "%s%s\\%s"
0x18000a9b3  mov     qword ptr [rsp+58h+dwOptions], rax
0x18000a9b8  call    StringCbPrintfW
0x18000a9bd  lea     rax, [rsp+58h+dwDisposition]
0x18000a9c2  xor     r8d, r8d; Reserved
0x18000a9c5  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18000a9ca  lea     r9, Class; lpClass
0x18000a9d1  lea     rax, [rsp+58h+hKey]
0x18000a9d6  mov     rdx, rbx; lpSubKey
0x18000a9d9  mov     [rsp+58h+phkResult], rax; phkResult
0x18000a9de  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a9e5  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000a9ee  mov     [rsp+58h+samDesired], 20007h; samDesired
0x18000a9f6  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000a9fe  call    cs:__imp_RegCreateKeyExW
0x18000aa04  mov     edi, eax
0x18000aa06  test    eax, eax
0x18000aa08  jnz     short loc_18000AA1B
0x18000aa0a  mov     rcx, [rsp+58h+hKey]
0x18000aa0f  mov     [rsi], rcx
0x18000aa12  mov     [rsp+58h+hKey], 0
0x18000aa1b  mov     rcx, rbx
0x18000aa1e  call    CspFreeH
0x18000aa23  mov     rcx, [rsp+58h+hKey]; hKey
0x18000aa28  test    rcx, rcx
0x18000aa2b  jz      short loc_18000AA33
0x18000aa2d  call    cs:__imp_RegCloseKey
0x18000aa33  mov     rbx, [rsp+58h+arg_10]
0x18000aa38  mov     eax, edi
0x18000aa3a  mov     rsi, [rsp+58h+arg_18]
0x18000aa3f  add     rsp, 50h
0x18000aa43  pop     rdi
0x18000aa44  retn
```
