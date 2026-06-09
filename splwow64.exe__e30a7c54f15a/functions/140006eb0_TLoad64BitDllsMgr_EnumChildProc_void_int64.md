# TLoad64BitDllsMgr::EnumChildProc(void *,__int64)

- ea: `0x140006eb0`
- end: `0x140006f0c`
- name: `?EnumChildProc@TLoad64BitDllsMgr@@KAHPEAX_J@Z`
- size: `92`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140006eb0`
- `0x1400086e0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x140006ed3`
- `KERNEL32!GetCurrentProcessId` at `0x140006ed3`
- `USER32!GetWindowThreadProcessId` at `0x140006ecd`
- `USER32!GetWindowThreadProcessId` at `0x140006ecd`

## string_xrefs

- `0x140006eec`: `TLoad64BitDllsMgr::EnumChildProc`

## pseudocode

```c
__int64 __fastcall TLoad64BitDllsMgr::EnumChildProc(HWND a1, _BYTE *a2)
{
  DWORD dwProcessId; // [rsp+40h] [rbp+18h] BYREF

  dwProcessId = 0;
  GetWindowThreadProcessId(a1, &dwProcessId);
  if ( GetCurrentProcessId() != dwProcessId )
    return 1;
  *a2 = 1;
  SplWow64Telemetry::WriteDbgTraceInfo(
    "TLoad64BitDllsMgr::EnumChildProc",
    L"Found child window with HWND = %p belonging to splwow64 process.",
    a1);
  return 0;
}

```

## disassembly

```asm
0x140006eb0  mov     [rsp+arg_0], rbx
0x140006eb5  push    rdi
0x140006eb6  sub     rsp, 20h
0x140006eba  mov     rdi, rdx
0x140006ebd  mov     [rsp+28h+dwProcessId], 0
0x140006ec5  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x140006eca  mov     rbx, rcx
0x140006ecd  call    cs:__imp_GetWindowThreadProcessId
0x140006ed3  call    cs:__imp_GetCurrentProcessId
0x140006ed9  cmp     eax, [rsp+28h+dwProcessId]
0x140006edd  jnz     short loc_140006EFC
0x140006edf  mov     r8, rbx
0x140006ee2  mov     byte ptr [rdi], 1
0x140006ee5  lea     rdx, aFoundChildWind; "Found child window with HWND = %p belon"...
0x140006eec  lea     rcx, aTload64bitdlls_1; "TLoad64BitDllsMgr::EnumChildProc"
0x140006ef3  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140006ef8  xor     eax, eax
0x140006efa  jmp     short loc_140006F01
0x140006efc  mov     eax, 1
0x140006f01  mov     rbx, [rsp+28h+arg_0]
0x140006f06  add     rsp, 20h
0x140006f0a  pop     rdi
0x140006f0b  retn
```
