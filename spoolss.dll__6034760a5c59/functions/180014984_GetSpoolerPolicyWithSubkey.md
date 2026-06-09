# GetSpoolerPolicyWithSubkey

- ea: `0x180014984`
- end: `0x180014a7b`
- name: `GetSpoolerPolicyWithSubkey`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180014928`

## callees

- `0x1800148a8`
- `0x1800148c0`
- `0x180014984`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014a2d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014a2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014a58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014a63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014a58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014a63`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014a00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014a00`

## pseudocode

```c
__int64 __fastcall GetSpoolerPolicyWithSubkey(HKEY a1, const WCHAR *a2, BYTE *a3, DWORD *a4, DWORD *a5)
{
  int v8; // ebx
  unsigned int v9; // eax
  int v10; // edx
  unsigned int v11; // eax
  int v12; // edx
  HKEY phkResult; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-30h] BYREF
  DWORD Type; // [rsp+70h] [rbp+8h] BYREF
  int v17; // [rsp+74h] [rbp+Ch]

  v17 = HIDWORD(a1);
  hKey = 0;
  phkResult = 0;
  Type = 0;
  if ( a2 && a3 && a4 )
  {
    v8 = OpenPrintPolicyKey(a1, &hKey);
    if ( v8 >= 0 )
    {
      v9 = RegOpenKeyExW(hKey, L"WPP", 0, 0x20019u, &phkResult);
      v8 = NCoreLibrary::HResultFromWin32((NCoreLibrary *)v9, v10);
      if ( v8 >= 0 )
      {
        v11 = RegQueryValueExW(phkResult, a2, 0, &Type, a3, a4);
        v8 = NCoreLibrary::HResultFromWin32((NCoreLibrary *)v11, v12);
        if ( v8 >= 0 && a5 )
          *a5 = Type;
        RegCloseKey(phkResult);
      }
      RegCloseKey(hKey);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180014984  mov     rax, rsp
0x180014987  mov     [rax+8], rcx
0x18001498b  push    rbx
0x18001498c  push    rbp
0x18001498d  push    rsi
0x18001498e  push    rdi
0x18001498f  sub     rsp, 48h
0x180014993  mov     qword ptr [rax-30h], 0
0x18001499b  mov     rdi, r9
0x18001499e  mov     qword ptr [rax-38h], 0
0x1800149a6  mov     rsi, r8
0x1800149a9  mov     dword ptr [rax+8], 0
0x1800149b0  mov     rbp, rdx
0x1800149b3  test    rdx, rdx
0x1800149b6  jz      loc_180014A6B
0x1800149bc  test    r8, r8
0x1800149bf  jz      loc_180014A6B
0x1800149c5  test    r9, r9
0x1800149c8  jz      loc_180014A6B
0x1800149ce  lea     rdx, [rax-30h]; HKEY *
0x1800149d2  call    ?OpenPrintPolicyKey@@YAJPEAUHKEY__@@PEAPEAU1@@Z; OpenPrintPolicyKey(HKEY__ *,HKEY__ * *)
0x1800149d7  mov     ebx, eax
0x1800149d9  test    eax, eax
0x1800149db  js      loc_180014A70
0x1800149e1  mov     rcx, [rsp+68h+hKey]; hKey
0x1800149e6  lea     rax, [rsp+68h+var_38]
0x1800149eb  mov     r9d, 20019h; samDesired
0x1800149f1  mov     [rsp+68h+phkResult], rax; phkResult
0x1800149f6  xor     r8d, r8d; ulOptions
0x1800149f9  lea     rdx, aWpp; "WPP"
0x180014a00  call    cs:__imp_RegOpenKeyExW
0x180014a06  mov     ecx, eax; this
0x180014a08  call    ?HResultFromWin32@NCoreLibrary@@YAJJ@Z; NCoreLibrary::HResultFromWin32(long)
0x180014a0d  mov     ebx, eax
0x180014a0f  test    eax, eax
0x180014a11  js      short loc_180014A5E
0x180014a13  mov     rcx, [rsp+68h+var_38]; hKey
0x180014a18  lea     r9, [rsp+68h+Type]; lpType
0x180014a1d  mov     [rsp+68h+lpcbData], rdi; lpcbData
0x180014a22  xor     r8d, r8d; lpReserved
0x180014a25  mov     rdx, rbp; lpValueName
0x180014a28  mov     [rsp+68h+phkResult], rsi; lpData
0x180014a2d  call    cs:__imp_RegQueryValueExW
0x180014a33  mov     ecx, eax; this
0x180014a35  call    ?HResultFromWin32@NCoreLibrary@@YAJJ@Z; NCoreLibrary::HResultFromWin32(long)
0x180014a3a  mov     ebx, eax
0x180014a3c  test    eax, eax
0x180014a3e  js      short loc_180014A53
0x180014a40  mov     rcx, [rsp+68h+arg_20]
0x180014a48  test    rcx, rcx
0x180014a4b  jz      short loc_180014A53
0x180014a4d  mov     eax, [rsp+68h+Type]
0x180014a51  mov     [rcx], eax
0x180014a53  mov     rcx, [rsp+68h+var_38]; hKey
0x180014a58  call    cs:__imp_RegCloseKey
0x180014a5e  mov     rcx, [rsp+68h+hKey]; hKey
0x180014a63  call    cs:__imp_RegCloseKey
0x180014a69  jmp     short loc_180014A70
0x180014a6b  mov     ebx, 80004003h
0x180014a70  mov     eax, ebx
0x180014a72  add     rsp, 48h
0x180014a76  pop     rdi
0x180014a77  pop     rsi
0x180014a78  pop     rbp
0x180014a79  pop     rbx
0x180014a7a  retn
```
