# WldpSetWindowsLockdownRestriction(WLDP_WINDOWS_LOCKDOWN_RESTRICTION)

- ea: `0x180028140`
- end: `0x180028266`
- name: `?WldpSetWindowsLockdownRestriction@@YAJW4WLDP_WINDOWS_LOCKDOWN_RESTRICTION@@@Z`
- size: `294`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180028140`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028206`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028206`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028244`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028244`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028237`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028237`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800281b5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800281b5`

## pseudocode

```c
__int64 __fastcall WldpSetWindowsLockdownRestriction(int a1)
{
  LSTATUS v2; // ebx
  enum WLDP_WINDOWS_LOCKDOWN_RESTRICTION Data; // [rsp+60h] [rbp+8h] BYREF
  int pvData; // [rsp+68h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+70h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  Data = a1;
  pvData = 0;
  hKey = 0;
  if ( a1 >= 3 )
    return 2147942487LL;
  if ( a1 == 2 )
    return 2147942405LL;
  pcbData = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Control\\CI\\Policy",
          L"LockDownRestriction",
          0x18u,
          0,
          &pvData,
          &pcbData)
    && pvData == 2 )
  {
    return 2147942405LL;
  }
  v2 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\CI\\Policy", 0, 0, 0, 2u, 0, &hKey, 0);
  if ( !v2 )
  {
    v2 = RegSetValueExW(hKey, L"LockDownRestriction", 0, 4u, (const BYTE *)&Data, 4u);
    RegCloseKey(hKey);
  }
  if ( v2 > 0 )
    return (unsigned __int16)v2 | 0x80070000;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180028140  mov     [rsp+Data], ecx
0x180028144  push    rbx
0x180028145  sub     rsp, 50h
0x180028149  mov     [rsp+58h+arg_8], 0
0x180028151  mov     [rsp+58h+hKey], 0
0x18002815a  cmp     ecx, 3
0x18002815d  jl      short loc_180028169
0x18002815f  mov     eax, 80070057h
0x180028164  jmp     loc_180028260
0x180028169  cmp     ecx, 2
0x18002816c  jz      loc_18002825B
0x180028172  lea     rax, [rsp+58h+arg_10]
0x180028177  mov     [rsp+58h+arg_10], 4
0x18002817f  mov     [rsp+58h+pcbData], rax; pcbData
0x180028184  lea     r8, aLockdownrestri; "LockDownRestriction"
0x18002818b  lea     rax, [rsp+58h+arg_8]
0x180028190  mov     rbx, 0FFFFFFFF80000002h
0x180028197  mov     [rsp+58h+pvData], rax; pvData
0x18002819c  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\CI"...
0x1800281a3  mov     r9d, 18h; dwFlags
0x1800281a9  mov     [rsp+58h+pdwType], 0; pdwType
0x1800281b2  mov     rcx, rbx; hkey
0x1800281b5  call    cs:__imp_RegGetValueW
0x1800281bb  test    eax, eax
0x1800281bd  jnz     short loc_1800281CA
0x1800281bf  cmp     [rsp+58h+arg_8], 2
0x1800281c4  jz      loc_18002825B
0x1800281ca  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800281d3  lea     rax, [rsp+58h+hKey]
0x1800281d8  mov     [rsp+58h+phkResult], rax; phkResult
0x1800281dd  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\CI"...
0x1800281e4  mov     [rsp+58h+pcbData], 0; lpSecurityAttributes
0x1800281ed  xor     r9d, r9d; lpClass
0x1800281f0  mov     dword ptr [rsp+58h+pvData], 2; samDesired
0x1800281f8  xor     r8d, r8d; Reserved
0x1800281fb  mov     rcx, rbx; hKey
0x1800281fe  mov     dword ptr [rsp+58h+pdwType], 0; dwOptions
0x180028206  call    cs:__imp_RegCreateKeyExW
0x18002820c  mov     ebx, eax
0x18002820e  test    eax, eax
0x180028210  jnz     short loc_18002824A
0x180028212  mov     rcx, [rsp+58h+hKey]; hKey
0x180028217  lea     rax, [rsp+58h+Data]
0x18002821c  mov     dword ptr [rsp+58h+pvData], 4; cbData
0x180028224  lea     r9d, [rbx+4]; dwType
0x180028228  xor     r8d, r8d; Reserved
0x18002822b  mov     [rsp+58h+pdwType], rax; lpData
0x180028230  lea     rdx, aLockdownrestri; "LockDownRestriction"
0x180028237  call    cs:__imp_RegSetValueExW
0x18002823d  mov     rcx, [rsp+58h+hKey]; hKey
0x180028242  mov     ebx, eax
0x180028244  call    cs:__imp_RegCloseKey
0x18002824a  test    ebx, ebx
0x18002824c  jle     short loc_180028257
0x18002824e  movzx   ebx, bx
0x180028251  or      ebx, 80070000h
0x180028257  mov     eax, ebx
0x180028259  jmp     short loc_180028260
0x18002825b  mov     eax, 80070005h
0x180028260  add     rsp, 50h
0x180028264  pop     rbx
0x180028265  retn
```
