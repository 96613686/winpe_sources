# MyUnregisterAppId(ushort const *)

- ea: `0x140003c44`
- end: `0x140003d72`
- name: `?MyUnregisterAppId@@YAJPEBG@Z`
- size: `302`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140005c80`

## callees

- `0x140001490`
- `0x140001e30`
- `0x140003c44`
- `0x140004258`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140003cee`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140003cee`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x140003d0e`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x140003d0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003ca6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003ca6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003d4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003d4a`

## pseudocode

```c
__int64 __fastcall MyUnregisterAppId(const unsigned __int16 *a1)
{
  HKEY v1; // rbx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v4[3]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Filename[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+260h] [rbp+160h] BYREF

  v4[1] = 0;
  v4[2] = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, L"AppID", 0, 0x20019u, &hKey) )
  {
    v1 = hKey;
    v4[0] = hKey;
    memset_0(Filename, 0, 0x20Au);
    hKey = (HKEY)qword_140008A50;
    if ( GetModuleFileNameW(hModule, Filename, 0x104u)
      && GetFullPathNameW(Filename, 0x104u, Buffer, (LPWSTR *)&hKey) - 1 <= 0x103 )
    {
      ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v4, (const unsigned __int16 *)hKey);
      ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v4, L"{4F0AC159-5804-4aa7-AE91-117D6E67BB9B}");
      v1 = (HKEY)v4[0];
    }
    if ( v1 )
      RegCloseKey(v1);
  }
  return 0;
}

```

## disassembly

```asm
0x140003c44  mov     [rsp-8+arg_0], rbx
0x140003c49  push    rbp
0x140003c4a  lea     rbp, [rsp-380h]
0x140003c52  sub     rsp, 480h
0x140003c59  mov     rax, cs:__security_cookie
0x140003c60  xor     rax, rsp
0x140003c63  mov     [rbp+380h+var_10], rax
0x140003c6a  lea     rax, [rsp+480h+hKey]
0x140003c6f  mov     [rsp+480h+var_440], 0
0x140003c78  mov     r9d, 20019h; samDesired
0x140003c7e  mov     [rsp+480h+phkResult], rax; phkResult
0x140003c83  xor     r8d, r8d; ulOptions
0x140003c86  mov     [rsp+480h+var_438], 0
0x140003c8f  lea     rdx, SubKey; "AppID"
0x140003c96  mov     [rsp+480h+hKey], 0
0x140003c9f  mov     rcx, 0FFFFFFFF80000000h; hKey
0x140003ca6  call    cs:__imp_RegOpenKeyExW
0x140003cac  test    eax, eax
0x140003cae  jnz     loc_140003D50
0x140003cb4  mov     rbx, [rsp+480h+hKey]
0x140003cb9  lea     rcx, [rsp+480h+Filename]; void *
0x140003cbe  xor     edx, edx; Val
0x140003cc0  mov     [rsp+480h+var_448], rbx
0x140003cc5  mov     r8d, 20Ah; Size
0x140003ccb  call    memset_0
0x140003cd0  mov     rcx, cs:hModule; hModule
0x140003cd7  lea     rax, qword_140008A50
0x140003cde  mov     r8d, 104h; nSize
0x140003ce4  mov     [rsp+480h+hKey], rax
0x140003ce9  lea     rdx, [rsp+480h+Filename]; lpFilename
0x140003cee  call    cs:__imp_GetModuleFileNameW
0x140003cf4  test    eax, eax
0x140003cf6  jz      short loc_140003D42
0x140003cf8  lea     r9, [rsp+480h+hKey]; lpFilePart
0x140003cfd  mov     edx, 104h; nBufferLength
0x140003d02  lea     r8, [rbp+380h+Buffer]; lpBuffer
0x140003d09  lea     rcx, [rsp+480h+Filename]; lpFileName
0x140003d0e  call    cs:__imp_GetFullPathNameW
0x140003d14  dec     eax
0x140003d16  cmp     eax, 103h
0x140003d1b  ja      short loc_140003D42
0x140003d1d  mov     rdx, [rsp+480h+hKey]; unsigned __int16 *
0x140003d22  lea     rcx, [rsp+480h+var_448]; this
0x140003d27  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x140003d2c  lea     rdx, Data; "{4F0AC159-5804-4aa7-AE91-117D6E67BB9B}"
0x140003d33  lea     rcx, [rsp+480h+var_448]; this
0x140003d38  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x140003d3d  mov     rbx, [rsp+480h+var_448]
0x140003d42  test    rbx, rbx
0x140003d45  jz      short loc_140003D50
0x140003d47  mov     rcx, rbx; hKey
0x140003d4a  call    cs:__imp_RegCloseKey
0x140003d50  xor     eax, eax
0x140003d52  mov     rcx, [rbp+380h+var_10]
0x140003d59  xor     rcx, rsp; StackCookie
0x140003d5c  call    __security_check_cookie
0x140003d61  mov     rbx, [rsp+480h+arg_0]
0x140003d69  add     rsp, 480h
0x140003d70  pop     rbp
0x140003d71  retn
```
