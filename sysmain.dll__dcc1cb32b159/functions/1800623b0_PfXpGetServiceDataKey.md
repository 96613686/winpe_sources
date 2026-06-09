# PfXpGetServiceDataKey

- ea: `0x1800623b0`
- end: `0x1800624bf`
- name: `PfXpGetServiceDataKey`
- size: `271`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180062320`
- `0x18007a1c0`
- `0x180084ec4`

## callees

- `0x1800623b0`
- `0x1800b64c0`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x180062413`
- `ntdll!RtlGetPersistedStateLocation` at `0x180062413`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062492`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062492`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180062469`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180062469`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180062456`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180062456`

## string_xrefs

- `0x180062407`: `PrefetcherServiceDataKey`

## pseudocode

```c
__int64 __fastcall PfXpGetServiceDataKey(int a1, HKEY *a2)
{
  int PersistedStateLocation; // eax
  const WCHAR *v5; // rdx
  LSTATUS Key; // eax
  unsigned int v7; // ebx
  HKEY v8; // rcx
  HKEY hKey[2]; // [rsp+50h] [rbp-238h] BYREF
  _BYTE v11[528]; // [rsp+60h] [rbp-228h] BYREF

  hKey[0] = 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"PrefetcherServiceDataKey",
                             0,
                             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Prefetcher",
                             0,
                             v11,
                             520,
                             0);
  v5 = (const WCHAR *)v11;
  if ( PersistedStateLocation < 0 )
    v5 = L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Prefetcher";
  if ( a1 )
    Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0, 0, 0xF003Fu, 0, hKey, 0);
  else
    Key = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0xF003Fu, hKey);
  v7 = Key;
  if ( Key )
  {
    v8 = hKey[0];
  }
  else
  {
    v8 = 0;
    *a2 = hKey[0];
    v7 = 0;
    hKey[0] = 0;
  }
  if ( v8 )
    RegCloseKey(v8);
  return v7;
}

```

## disassembly

```asm
0x1800623b0  mov     [rsp+arg_0], rbx
0x1800623b5  mov     [rsp+arg_10], rsi
0x1800623ba  push    rdi
0x1800623bb  sub     rsp, 280h
0x1800623c2  mov     rax, cs:__security_cookie
0x1800623c9  xor     rax, rsp
0x1800623cc  mov     [rsp+288h+var_18], rax
0x1800623d4  mov     rdi, rdx
0x1800623d7  mov     [rsp+288h+lpSecurityAttributes], 0
0x1800623e0  mov     ebx, ecx
0x1800623e2  mov     [rsp+288h+samDesired], 208h
0x1800623ea  lea     rax, [rsp+288h+var_228]
0x1800623ef  mov     [rsp+288h+hKey], 0
0x1800623f8  lea     rsi, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800623ff  mov     qword ptr [rsp+288h+dwOptions], rax
0x180062404  mov     r8, rsi
0x180062407  lea     rcx, aPrefetcherserv; "PrefetcherServiceDataKey"
0x18006240e  xor     r9d, r9d
0x180062411  xor     edx, edx
0x180062413  call    cs:__imp_RtlGetPersistedStateLocation
0x180062419  lea     rdx, [rsp+288h+var_228]
0x18006241e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180062425  test    eax, eax
0x180062427  lea     rax, [rsp+288h+hKey]
0x18006242c  cmovs   rdx, rsi; lpSubKey
0x180062430  xor     r8d, r8d; ulOptions
0x180062433  test    ebx, ebx
0x180062435  jz      short loc_18006245E
0x180062437  mov     [rsp+288h+lpdwDisposition], r8; lpdwDisposition
0x18006243c  xor     r9d, r9d; lpClass
0x18006243f  mov     [rsp+288h+phkResult], rax; phkResult
0x180062444  mov     [rsp+288h+lpSecurityAttributes], r8; lpSecurityAttributes
0x180062449  mov     [rsp+288h+samDesired], 0F003Fh; samDesired
0x180062451  mov     [rsp+288h+dwOptions], r8d; dwOptions
0x180062456  call    cs:__imp_RegCreateKeyExW
0x18006245c  jmp     short loc_18006246F
0x18006245e  mov     r9d, 0F003Fh; samDesired
0x180062464  mov     qword ptr [rsp+288h+dwOptions], rax; phkResult
0x180062469  call    cs:__imp_RegOpenKeyExW
0x18006246f  mov     ebx, eax
0x180062471  test    eax, eax
0x180062473  jnz     short loc_180062488
0x180062475  mov     rax, [rsp+288h+hKey]
0x18006247a  xor     ecx, ecx
0x18006247c  mov     [rdi], rax
0x18006247f  xor     ebx, ebx
0x180062481  mov     [rsp+288h+hKey], rcx
0x180062486  jmp     short loc_18006248D
0x180062488  mov     rcx, [rsp+288h+hKey]; hKey
0x18006248d  test    rcx, rcx
0x180062490  jz      short loc_180062498
0x180062492  call    cs:__imp_RegCloseKey
0x180062498  mov     eax, ebx
0x18006249a  mov     rcx, [rsp+288h+var_18]
0x1800624a2  xor     rcx, rsp; StackCookie
0x1800624a5  call    __security_check_cookie
0x1800624aa  lea     r11, [rsp+288h+var_8]
0x1800624b2  mov     rbx, [r11+10h]
0x1800624b6  mov     rsi, [r11+20h]
0x1800624ba  mov     rsp, r11
0x1800624bd  pop     rdi
0x1800624be  retn
```
