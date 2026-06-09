# Proximity::LoadProximityLibrary(void)

- ea: `0x18002a824`
- end: `0x18002a93f`
- name: `?LoadProximityLibrary@Proximity@@YAPEAUHINSTANCE__@@XZ`
- size: `283`
- prototype: `HINSTANCE __fastcall(Proximity *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002a7b0`

## callees

- `0x18001afa8`
- `0x18002a824`
- `0x180032c6a`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002a8fd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002a8fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a8c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a8c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a910`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a910`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a874`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a874`

## string_xrefs

- `0x18002a862`: `Software\Microsoft\Windows\CurrentVersion\Proximity\Plugin`
- `0x18002a8b9`: `ProximityServiceLibrary`

## pseudocode

```c
HINSTANCE __fastcall Proximity::LoadProximityLibrary(Proximity *this)
{
  HMODULE Library; // rbx
  unsigned __int64 v2; // rcx
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[2]; // [rsp+40h] [rbp-C0h] BYREF

  hKey = 0;
  Library = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Proximity\\Plugin",
          0,
          1u,
          &hKey) )
  {
    memset_0(Data, 0, 0x208u);
    Type = 0;
    cbData = 520;
    if ( !RegQueryValueExW(hKey, L"ProximityServiceLibrary", 0, &Type, Data, &cbData) && Type == 1 )
    {
      v2 = (cbData & 0xFFFFFFFE) - 2LL;
      if ( v2 >= 0x208 )
        _report_rangecheckfailure();
      *(_WORD *)&Data[v2] = 0;
      Library = LoadLibraryExW((LPCWSTR)Data, 0, 0);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return Library;
}

```

## disassembly

```asm
0x18002a824  mov     [rsp-8+arg_0], rbx
0x18002a829  push    rbp
0x18002a82a  lea     rbp, [rsp-160h]
0x18002a832  sub     rsp, 260h
0x18002a839  mov     rax, cs:__security_cookie
0x18002a840  xor     rax, rsp
0x18002a843  mov     [rbp+160h+var_10], rax
0x18002a84a  lea     rax, [rsp+260h+hKey]
0x18002a84f  mov     [rsp+260h+hKey], 0
0x18002a858  xor     ebx, ebx
0x18002a85a  mov     [rsp+260h+phkResult], rax; phkResult
0x18002a85f  xor     r8d, r8d; ulOptions
0x18002a862  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002a869  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a870  lea     r9d, [rbx+1]; samDesired
0x18002a874  call    cs:__imp_RegOpenKeyExW
0x18002a87a  test    eax, eax
0x18002a87c  jnz     loc_18002A906
0x18002a882  xor     edx, edx; Val
0x18002a884  lea     rcx, [rsp+260h+Data]; void *
0x18002a889  mov     r8d, 208h; Size
0x18002a88f  call    memset_0
0x18002a894  mov     rcx, [rsp+260h+hKey]; hKey
0x18002a899  lea     rax, [rsp+260h+cbData]
0x18002a89e  mov     [rsp+260h+lpcbData], rax; lpcbData
0x18002a8a3  lea     r9, [rsp+260h+Type]; lpType
0x18002a8a8  lea     rax, [rsp+260h+Data]
0x18002a8ad  mov     [rsp+260h+Type], ebx
0x18002a8b1  xor     r8d, r8d; lpReserved
0x18002a8b4  mov     [rsp+260h+phkResult], rax; lpData
0x18002a8b9  lea     rdx, ValueName; "ProximityServiceLibrary"
0x18002a8c0  mov     [rsp+260h+cbData], 208h
0x18002a8c8  call    cs:__imp_RegQueryValueExW
0x18002a8ce  test    eax, eax
0x18002a8d0  jnz     short loc_18002A906
0x18002a8d2  cmp     [rsp+260h+Type], 1
0x18002a8d7  jnz     short loc_18002A906
0x18002a8d9  mov     ecx, [rsp+260h+cbData]
0x18002a8dd  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18002a8e1  add     rcx, 0FFFFFFFFFFFFFFFEh
0x18002a8e5  cmp     rcx, 208h
0x18002a8ec  jnb     short loc_18002A939
0x18002a8ee  mov     word ptr [rsp+rcx+260h+Data], ax
0x18002a8f3  xor     r8d, r8d; dwFlags
0x18002a8f6  lea     rcx, [rsp+260h+Data]; lpLibFileName
0x18002a8fb  xor     edx, edx; hFile
0x18002a8fd  call    cs:__imp_LoadLibraryExW
0x18002a903  mov     rbx, rax
0x18002a906  mov     rcx, [rsp+260h+hKey]; hKey
0x18002a90b  test    rcx, rcx
0x18002a90e  jz      short loc_18002A916
0x18002a910  call    cs:__imp_RegCloseKey
0x18002a916  mov     rax, rbx
0x18002a919  mov     rcx, [rbp+160h+var_10]
0x18002a920  xor     rcx, rsp; StackCookie
0x18002a923  call    __security_check_cookie
0x18002a928  mov     rbx, [rsp+260h+arg_0]
0x18002a930  add     rsp, 260h
0x18002a937  pop     rbp
0x18002a938  retn
0x18002a939  call    __report_rangecheckfailure
```
