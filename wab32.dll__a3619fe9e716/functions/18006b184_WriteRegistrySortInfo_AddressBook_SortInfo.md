# WriteRegistrySortInfo(AddressBook *,_SortInfo)

- ea: `0x18006b184`
- end: `0x18006b263`
- name: `?WriteRegistrySortInfo@@YAHPEAVAddressBook@@U_SortInfo@@@Z`
- size: `223`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180047e90`
- `0x18006a0d8`

## callees

- `0x18006b184`
- `0x180091ef0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18006b245`
- `ADVAPI32!RegCloseKey` at `0x18006b245`
- `ADVAPI32!RegCreateKeyExW` at `0x18006b1fa`
- `ADVAPI32!RegCreateKeyExW` at `0x18006b1fa`
- `ADVAPI32!RegSetValueExW` at `0x18006b22b`
- `ADVAPI32!RegSetValueExW` at `0x18006b22b`

## pseudocode

```c
__int64 __fastcall WriteRegistrySortInfo(__int64 a1, __int128 *a2)
{
  __int128 v2; // xmm0
  unsigned int v3; // ebx
  __int64 v4; // rcx
  DWORD dwDisposition; // [rsp+50h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-30h] BYREF
  BYTE Data[16]; // [rsp+60h] [rbp-28h] BYREF

  v2 = *a2;
  v3 = 0;
  hKey = 0;
  *(_OWORD *)Data = v2;
  if ( !a1 || (v4 = *(_QWORD *)(a1 + 1056)) == 0 )
    v4 = -2147483647;
  dwDisposition = 0;
  if ( !RegCreateKeyExW(
          (HKEY)v4,
          L"Software\\Microsoft\\WAB\\WAB Sort State",
          0,
          0,
          0,
          0xF003Fu,
          0,
          &hKey,
          &dwDisposition)
    && !RegSetValueExW(hKey, L"State", 0, 3u, Data, 0x10u) )
  {
    v3 = 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x18006b184  push    rbx
0x18006b186  sub     rsp, 80h
0x18006b18d  mov     rax, cs:__security_cookie
0x18006b194  xor     rax, rsp
0x18006b197  mov     [rsp+88h+var_18], rax
0x18006b19c  movups  xmm0, xmmword ptr [rdx]
0x18006b19f  xor     ebx, ebx
0x18006b1a1  mov     [rsp+88h+hKey], rbx
0x18006b1a6  movdqu  xmmword ptr [rsp+88h+Data], xmm0
0x18006b1ac  test    rcx, rcx
0x18006b1af  jz      short loc_18006B1BD
0x18006b1b1  mov     rcx, [rcx+420h]
0x18006b1b8  test    rcx, rcx
0x18006b1bb  jnz     short loc_18006B1C4
0x18006b1bd  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18006b1c4  lea     rax, [rsp+88h+dwDisposition]
0x18006b1c9  mov     [rsp+88h+dwDisposition], ebx
0x18006b1cd  mov     [rsp+88h+lpdwDisposition], rax; lpdwDisposition
0x18006b1d2  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\WAB\\WAB Sort Stat"...
0x18006b1d9  lea     rax, [rsp+88h+hKey]
0x18006b1de  xor     r9d, r9d; lpClass
0x18006b1e1  mov     [rsp+88h+phkResult], rax; phkResult
0x18006b1e6  xor     r8d, r8d; Reserved
0x18006b1e9  mov     [rsp+88h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18006b1ee  mov     [rsp+88h+samDesired], 0F003Fh; samDesired
0x18006b1f6  mov     [rsp+88h+dwOptions], ebx; dwOptions
0x18006b1fa  call    cs:__imp_RegCreateKeyExW
0x18006b200  test    eax, eax
0x18006b202  jnz     short loc_18006B23B
0x18006b204  mov     rcx, [rsp+88h+hKey]; hKey
0x18006b209  lea     rax, [rsp+88h+Data]
0x18006b20e  mov     [rsp+88h+samDesired], 10h; cbData
0x18006b216  lea     rdx, aState; "State"
0x18006b21d  mov     r9d, 3; dwType
0x18006b223  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x18006b228  xor     r8d, r8d; Reserved
0x18006b22b  call    cs:__imp_RegSetValueExW
0x18006b231  test    eax, eax
0x18006b233  mov     ecx, 1
0x18006b238  cmovz   ebx, ecx
0x18006b23b  mov     rcx, [rsp+88h+hKey]; hKey
0x18006b240  test    rcx, rcx
0x18006b243  jz      short loc_18006B24B
0x18006b245  call    cs:__imp_RegCloseKey
0x18006b24b  mov     eax, ebx
0x18006b24d  mov     rcx, [rsp+88h+var_18]
0x18006b252  xor     rcx, rsp; StackCookie
0x18006b255  call    __security_check_cookie
0x18006b25a  add     rsp, 80h
0x18006b261  pop     rbx
0x18006b262  retn
```
