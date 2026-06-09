# DirectLaunch::DirectLaunchManager::WriteHandlerToRegistry(wil::write_lock_required,wil::basic_zstring_view<ushort>,std::optional<uint>)

- ea: `0x180042e88`
- end: `0x180042f3f`
- name: `?WriteHandlerToRegistry@DirectLaunchManager@DirectLaunch@@AEAAXUwrite_lock_required@wil@@V?$basic_zstring_view@G@4@V?$optional@I@std@@@Z`
- size: `183`
- prototype: `unsigned int __fastcall(__int64, __int64, LPCWSTR *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180042004`
- `0x1800424f4`

## callees

- `0x18002b1b0`
- `0x18003a1e4`
- `0x1800402e8`
- `0x180042e88`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180042f03`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180042f03`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180042ed9`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180042ed9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned int __fastcall DirectLaunch::DirectLaunchManager::WriteHandlerToRegistry(
        __int64 a1,
        __int64 a2,
        LPCWSTR *a3,
        __int64 a4)
{
  int v4; // ebx
  HKEY v6; // rax
  const WCHAR *v7; // r8
  unsigned int result; // eax
  unsigned int lpData; // [rsp+20h] [rbp-28h]
  unsigned int lpDataa; // [rsp+20h] [rbp-28h]
  int Data; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  char v13; // [rsp+6Ch] [rbp+24h]

  v13 = BYTE4(a4);
  v4 = a4;
  v6 = (HKEY)DirectLaunch::DirectLaunchManager::EnsureHandlerMapKey();
  if ( v13 )
  {
    v7 = *a3;
    Data = v4;
    result = RegSetKeyValueW(v6, 0, v7, 4u, &Data, 4u);
    if ( result )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x253,
        (unsigned int)"onecoreuap\\shell\\SrcPkg\\DirectLaunch\\inc\\DirectLaunchManager.h",
        (const char *)result,
        lpDataa);
  }
  else
  {
    result = RegDeleteValueW(v6, *a3);
    if ( result )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x257,
        (unsigned int)"onecoreuap\\shell\\SrcPkg\\DirectLaunch\\inc\\DirectLaunchManager.h",
        (const char *)result,
        lpData);
  }
  return result;
}

```

## disassembly

```asm
0x180042e88  mov     [rsp+arg_8], rbx
0x180042e8d  mov     [rsp+arg_18], r9
0x180042e92  push    rdi
0x180042e93  sub     rsp, 40h
0x180042e97  mov     rax, cs:__security_cookie
0x180042e9e  xor     rax, rsp
0x180042ea1  mov     [rsp+48h+var_10], rax
0x180042ea6  mov     rbx, r9
0x180042ea9  mov     rdi, r8
0x180042eac  call    ?EnsureHandlerMapKey@DirectLaunchManager@DirectLaunch@@AEAAPEAUHKEY__@@Uwrite_lock_required@wil@@@Z; DirectLaunch::DirectLaunchManager::EnsureHandlerMapKey(wil::write_lock_required)
0x180042eb1  cmp     byte ptr [rsp+48h+arg_18+4], 0
0x180042eb6  jz      short loc_180042EFD
0x180042eb8  mov     r8, [rdi]; lpValueName
0x180042ebb  lea     rcx, [rsp+48h+Data]
0x180042ec0  mov     r9d, 4; dwType
0x180042ec6  mov     [rsp+48h+Data], ebx
0x180042eca  mov     [rsp+48h+cbData], r9d; cbData
0x180042ecf  xor     edx, edx; lpSubKey
0x180042ed1  mov     [rsp+48h+lpData], rcx; unsigned int
0x180042ed6  mov     rcx, rax; hKey
0x180042ed9  call    cs:__imp_RegSetKeyValueW
0x180042edf  test    eax, eax
0x180042ee1  jz      short loc_180042F27
0x180042ee3  mov     rcx, [rsp+48h]; this
0x180042ee8  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\SrcPkg\\DirectLaunch"...
0x180042eef  mov     r9d, eax; char *
0x180042ef2  mov     edx, 253h; void *
0x180042ef7  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180042efd  mov     rdx, [rdi]; lpValueName
0x180042f00  mov     rcx, rax; hKey
0x180042f03  call    cs:__imp_RegDeleteValueW
0x180042f09  test    eax, eax
0x180042f0b  jz      short loc_180042F27
0x180042f0d  mov     rcx, [rsp+48h]; this
0x180042f12  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\SrcPkg\\DirectLaunch"...
0x180042f19  mov     r9d, eax; char *
0x180042f1c  mov     edx, 257h; void *
0x180042f21  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180042f27  mov     rcx, [rsp+48h+var_10]
0x180042f2c  xor     rcx, rsp; StackCookie
0x180042f2f  call    __security_check_cookie
0x180042f34  mov     rbx, [rsp+48h+arg_8]
0x180042f39  add     rsp, 40h
0x180042f3d  pop     rdi
0x180042f3e  retn
```
