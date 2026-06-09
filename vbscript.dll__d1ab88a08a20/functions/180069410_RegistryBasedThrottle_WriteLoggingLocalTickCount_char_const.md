# RegistryBasedThrottle::WriteLoggingLocalTickCount(char const *)

- ea: `0x180069410`
- end: `0x180069526`
- name: `?WriteLoggingLocalTickCount@RegistryBasedThrottle@@QEAAJPEBD@Z`
- size: `278`
- prototype: `__int64 __fastcall(RegistryBasedThrottle *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180055fe4`

## callees

- `0x180043964`
- `0x180069410`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x180069433`
- `KERNEL32!GetTickCount64` at `0x180069433`
- `ADVAPI32!RegSetValueExA` at `0x1800694e0`
- `ADVAPI32!RegSetValueExA` at `0x1800694e0`
- `ADVAPI32!RegCreateKeyExA` at `0x1800694a9`
- `ADVAPI32!RegCreateKeyExA` at `0x1800694a9`
- `ADVAPI32!RegCloseKey` at `0x1800694fb`
- `ADVAPI32!RegCloseKey` at `0x18006950c`
- `ADVAPI32!RegCloseKey` at `0x1800694fb`
- `ADVAPI32!RegCloseKey` at `0x18006950c`
- `ADVAPI32!RegOpenCurrentUser` at `0x180069453`
- `ADVAPI32!RegOpenCurrentUser` at `0x180069453`

## pseudocode

```c
__int64 __fastcall RegistryBasedThrottle::WriteLoggingLocalTickCount(RegistryBasedThrottle *this, const char *a2)
{
  unsigned int v3; // ebx
  const CHAR *CurrentProcessTickCountRegistryKey; // rax
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp+18h] BYREF
  ULONGLONG Data; // [rsp+78h] [rbp+20h] BYREF

  phkResult = 0;
  hKey = 0;
  Data = GetTickCount64();
  v3 = -2147467259;
  if ( !RegOpenCurrentUser(0x20106u, &phkResult) )
  {
    CurrentProcessTickCountRegistryKey = RegistryBasedThrottle::GetCurrentProcessTickCountRegistryKey(this);
    if ( !RegCreateKeyExA(phkResult, CurrentProcessTickCountRegistryKey, 0, 0, 0, 0x2000000u, 0, &hKey, 0) )
    {
      v3 = RegSetValueExA(hKey, "VBScriptSetScriptStateStarted", 0, 0xBu, (const BYTE *)&Data, 8u) != 0 ? 0x80004005 : 0;
      RegCloseKey(hKey);
    }
    RegCloseKey(phkResult);
  }
  return v3;
}

```

## disassembly

```asm
0x180069410  mov     rax, rsp
0x180069413  mov     [rax+8], rbx
0x180069417  mov     [rax+10h], rdx
0x18006941b  push    rdi
0x18006941c  sub     rsp, 50h
0x180069420  mov     rdi, rcx
0x180069423  mov     qword ptr [rax+18h], 0
0x18006942b  mov     qword ptr [rax+10h], 0
0x180069433  call    cs:__imp_GetTickCount64
0x18006943a  nop     dword ptr [rax+rax+00h]
0x18006943f  lea     rdx, [rsp+58h+phkResult]; phkResult
0x180069444  mov     ecx, 20106h; samDesired
0x180069449  mov     [rsp+58h+Data], rax
0x18006944e  mov     ebx, 80004005h
0x180069453  call    cs:__imp_RegOpenCurrentUser
0x18006945a  nop     dword ptr [rax+rax+00h]
0x18006945f  test    eax, eax
0x180069461  jnz     loc_180069518
0x180069467  mov     rcx, rdi; this
0x18006946a  call    ?GetCurrentProcessTickCountRegistryKey@RegistryBasedThrottle@@AEAAPEADXZ; RegistryBasedThrottle::GetCurrentProcessTickCountRegistryKey(void)
0x18006946f  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180069478  lea     rcx, [rsp+58h+hKey]
0x18006947d  mov     [rsp+58h+var_20], rcx; phkResult
0x180069482  xor     r9d, r9d; lpClass
0x180069485  mov     rcx, [rsp+58h+phkResult]; hKey
0x18006948a  xor     r8d, r8d; Reserved
0x18006948d  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180069496  mov     rdx, rax; lpSubKey
0x180069499  mov     [rsp+58h+samDesired], 2000000h; samDesired
0x1800694a1  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800694a9  call    cs:__imp_RegCreateKeyExA
0x1800694b0  nop     dword ptr [rax+rax+00h]
0x1800694b5  test    eax, eax
0x1800694b7  jnz     short loc_180069507
0x1800694b9  mov     rcx, [rsp+58h+hKey]; hKey
0x1800694be  lea     rax, [rsp+58h+Data]
0x1800694c3  mov     [rsp+58h+samDesired], 8; cbData
0x1800694cb  lea     rdx, aVbscriptsetscr; "VBScriptSetScriptStateStarted"
0x1800694d2  mov     r9d, 0Bh; dwType
0x1800694d8  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800694dd  xor     r8d, r8d; Reserved
0x1800694e0  call    cs:__imp_RegSetValueExA
0x1800694e7  nop     dword ptr [rax+rax+00h]
0x1800694ec  xor     ecx, ecx
0x1800694ee  sub     ecx, eax
0x1800694f0  neg     ecx
0x1800694f2  mov     rcx, [rsp+58h+hKey]; hKey
0x1800694f7  sbb     eax, eax
0x1800694f9  and     ebx, eax
0x1800694fb  call    cs:__imp_RegCloseKey
0x180069502  nop     dword ptr [rax+rax+00h]
0x180069507  mov     rcx, [rsp+58h+phkResult]; hKey
0x18006950c  call    cs:__imp_RegCloseKey
0x180069513  nop     dword ptr [rax+rax+00h]
0x180069518  mov     eax, ebx
0x18006951a  mov     rbx, [rsp+58h+arg_0]
0x18006951f  add     rsp, 50h
0x180069523  pop     rdi
0x180069524  retn
```
