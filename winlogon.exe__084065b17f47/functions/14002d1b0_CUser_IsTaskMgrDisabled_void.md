# CUser::IsTaskMgrDisabled(void)

- ea: `0x14002d1b0`
- end: `0x14002d31b`
- name: `?IsTaskMgrDisabled@CUser@@QEAAHXZ`
- size: `363`
- prototype: `__int64 __fastcall(CUser *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14006cb70`
- `0x140080254`

## callees

- `0x14002d1b0`
- `0x14002d410`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002d1fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002d26c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002d1fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002d26c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002d232`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002d2a1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002d232`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002d2a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002d23c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002d2ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002d23c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002d2ab`

## string_xrefs

- `0x14002d22b`: `DisableTaskMgr`
- `0x14002d29a`: `DisableTaskMgr`
- `0x14002d2be`: `DisableTaskMgr`
- `0x14002d2e6`: `DisableTaskMgr`

## pseudocode

```c
_BOOL8 __fastcall CUser::IsTaskMgrDisabled(CUser *this)
{
  HKEY hKey[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int Data; // [rsp+58h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  DWORD Type; // [rsp+68h] [rbp+28h] BYREF

  hKey[0] = 0;
  Type = 0;
  cbData = 0;
  Data = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
          0,
          0x20019u,
          hKey) )
  {
    cbData = 4;
    RegQueryValueExW(hKey[0], L"DisableTaskMgr", 0, &Type, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey[0]);
  }
  if ( Data )
    return 1;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
          0,
          0x20019u,
          hKey) )
  {
    cbData = 4;
    RegQueryValueExW(hKey[0], L"DisableTaskMgr", 0, &Type, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey[0]);
  }
  if ( Data )
    return 1;
  CUser::RegQueryDWORD(this, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", L"DisableTaskMgr", 0, &Data);
  if ( Data )
    return 1;
  CUser::RegQueryDWORD(
    this,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
    L"DisableTaskMgr",
    0,
    &Data);
  return Data != 0;
}

```

## disassembly

```asm
0x14002d1b0  mov     [rsp-8+arg_0], rbx
0x14002d1b5  push    rbp
0x14002d1b6  mov     rbp, rsp
0x14002d1b9  sub     rsp, 40h
0x14002d1bd  mov     rbx, rcx
0x14002d1c0  mov     [rbp+hKey], 0
0x14002d1c8  lea     rax, [rbp+hKey]
0x14002d1cc  mov     [rbp+Type], 0
0x14002d1d3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002d1da  mov     [rsp+40h+phkResult], rax; phkResult
0x14002d1df  mov     r9d, 20019h; samDesired
0x14002d1e5  mov     [rbp+cbData], 0
0x14002d1ec  xor     r8d, r8d; ulOptions
0x14002d1ef  mov     [rbp+Data], 0
0x14002d1f6  lea     rdx, aSoftwareMicros_48; "Software\\Microsoft\\Windows NT\\Curren"...
0x14002d1fd  call    cs:__imp_RegOpenKeyExW
0x14002d203  test    eax, eax
0x14002d205  jnz     short loc_14002D242
0x14002d207  mov     rcx, [rbp+hKey]; hKey
0x14002d20b  lea     rax, [rbp+cbData]
0x14002d20f  mov     [rsp+40h+lpcbData], rax; lpcbData
0x14002d214  lea     r9, [rbp+Type]; lpType
0x14002d218  lea     rax, [rbp+Data]
0x14002d21c  mov     [rbp+cbData], 4
0x14002d223  xor     r8d, r8d; lpReserved
0x14002d226  mov     [rsp+40h+phkResult], rax; lpData
0x14002d22b  lea     rdx, aDisabletaskmgr; "DisableTaskMgr"
0x14002d232  call    cs:__imp_RegQueryValueExW
0x14002d238  mov     rcx, [rbp+hKey]; hKey
0x14002d23c  call    cs:__imp_RegCloseKey
0x14002d242  cmp     [rbp+Data], 0
0x14002d246  jnz     loc_14002D30B
0x14002d24c  lea     rax, [rbp+hKey]
0x14002d250  mov     r9d, 20019h; samDesired
0x14002d256  xor     r8d, r8d; ulOptions
0x14002d259  mov     [rsp+40h+phkResult], rax; phkResult
0x14002d25e  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14002d265  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002d26c  call    cs:__imp_RegOpenKeyExW
0x14002d272  test    eax, eax
0x14002d274  jnz     short loc_14002D2B1
0x14002d276  mov     rcx, [rbp+hKey]; hKey
0x14002d27a  lea     rax, [rbp+cbData]
0x14002d27e  mov     [rsp+40h+lpcbData], rax; lpcbData
0x14002d283  lea     r9, [rbp+Type]; lpType
0x14002d287  lea     rax, [rbp+Data]
0x14002d28b  mov     [rbp+cbData], 4
0x14002d292  xor     r8d, r8d; lpReserved
0x14002d295  mov     [rsp+40h+phkResult], rax; lpData
0x14002d29a  lea     rdx, aDisabletaskmgr; "DisableTaskMgr"
0x14002d2a1  call    cs:__imp_RegQueryValueExW
0x14002d2a7  mov     rcx, [rbp+hKey]; hKey
0x14002d2ab  call    cs:__imp_RegCloseKey
0x14002d2b1  cmp     [rbp+Data], 0
0x14002d2b5  jnz     short loc_14002D30B
0x14002d2b7  lea     rax, [rbp+Data]
0x14002d2bb  xor     r9d, r9d; unsigned int
0x14002d2be  lea     r8, aDisabletaskmgr; "DisableTaskMgr"
0x14002d2c5  mov     [rsp+40h+phkResult], rax; unsigned int *
0x14002d2ca  lea     rdx, aSoftwareMicros_48; "Software\\Microsoft\\Windows NT\\Curren"...
0x14002d2d1  mov     rcx, rbx; this
0x14002d2d4  call    ?RegQueryDWORD@CUser@@QEAAKPEBG0KPEAK@Z; CUser::RegQueryDWORD(ushort const *,ushort const *,ulong,ulong *)
0x14002d2d9  cmp     [rbp+Data], 0
0x14002d2dd  jnz     short loc_14002D30B
0x14002d2df  lea     rax, [rbp+Data]
0x14002d2e3  xor     r9d, r9d; unsigned int
0x14002d2e6  lea     r8, aDisabletaskmgr; "DisableTaskMgr"
0x14002d2ed  mov     [rsp+40h+phkResult], rax; unsigned int *
0x14002d2f2  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14002d2f9  mov     rcx, rbx; this
0x14002d2fc  call    ?RegQueryDWORD@CUser@@QEAAKPEBG0KPEAK@Z; CUser::RegQueryDWORD(ushort const *,ushort const *,ulong,ulong *)
0x14002d301  cmp     [rbp+Data], 0
0x14002d305  jnz     short loc_14002D30B
0x14002d307  xor     eax, eax
0x14002d309  jmp     short loc_14002D310
0x14002d30b  mov     eax, 1
0x14002d310  mov     rbx, [rsp+40h+arg_0]
0x14002d315  add     rsp, 40h
0x14002d319  pop     rbp
0x14002d31a  retn
```
