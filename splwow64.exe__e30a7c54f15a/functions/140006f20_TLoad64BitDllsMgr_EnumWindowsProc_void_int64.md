# TLoad64BitDllsMgr::EnumWindowsProc(void *,__int64)

- ea: `0x140006f20`
- end: `0x140006f91`
- name: `?EnumWindowsProc@TLoad64BitDllsMgr@@KAHPEAX_J@Z`
- size: `113`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140006f20`
- `0x1400086e0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x140006f43`
- `KERNEL32!GetCurrentProcessId` at `0x140006f43`
- `USER32!EnumChildWindows` at `0x140006f79`
- `USER32!EnumChildWindows` at `0x140006f79`
- `USER32!GetWindowThreadProcessId` at `0x140006f3d`
- `USER32!GetWindowThreadProcessId` at `0x140006f3d`

## string_xrefs

- `0x140006f5c`: `TLoad64BitDllsMgr::EnumWindowsProc`

## pseudocode

```c
_BOOL8 __fastcall TLoad64BitDllsMgr::EnumWindowsProc(HWND a1, _BYTE *a2)
{
  DWORD dwProcessId; // [rsp+38h] [rbp+10h] BYREF

  dwProcessId = 0;
  GetWindowThreadProcessId(a1, &dwProcessId);
  if ( GetCurrentProcessId() == dwProcessId )
  {
    *a2 = 1;
    SplWow64Telemetry::WriteDbgTraceInfo(
      "TLoad64BitDllsMgr::EnumWindowsProc",
      L"Found window with HWND = %p belonging to splwow64 process.",
      a1);
    return 0;
  }
  else
  {
    EnumChildWindows(a1, (WNDENUMPROC)TLoad64BitDllsMgr::EnumChildProc, (LPARAM)a2);
    return *a2 == 0;
  }
}

```

## disassembly

```asm
0x140006f20  mov     [rsp+arg_0], rbx
0x140006f25  push    rdi
0x140006f26  sub     rsp, 20h
0x140006f2a  mov     rbx, rdx
0x140006f2d  mov     [rsp+28h+dwProcessId], 0
0x140006f35  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x140006f3a  mov     rdi, rcx
0x140006f3d  call    cs:__imp_GetWindowThreadProcessId
0x140006f43  call    cs:__imp_GetCurrentProcessId
0x140006f49  cmp     eax, [rsp+28h+dwProcessId]
0x140006f4d  jnz     short loc_140006F6C
0x140006f4f  mov     r8, rdi
0x140006f52  mov     byte ptr [rbx], 1
0x140006f55  lea     rdx, aFoundWindowWit; "Found window with HWND = %p belonging t"...
0x140006f5c  lea     rcx, aTload64bitdlls_8; "TLoad64BitDllsMgr::EnumWindowsProc"
0x140006f63  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140006f68  xor     eax, eax
0x140006f6a  jmp     short loc_140006F86
0x140006f6c  mov     r8, rbx; lParam
0x140006f6f  lea     rdx, ?EnumChildProc@TLoad64BitDllsMgr@@KAHPEAX_J@Z; lpEnumFunc
0x140006f76  mov     rcx, rdi; hWndParent
0x140006f79  call    cs:__imp_EnumChildWindows
0x140006f7f  xor     eax, eax
0x140006f81  cmp     [rbx], al
0x140006f83  setz    al
0x140006f86  mov     rbx, [rsp+28h+arg_0]
0x140006f8b  add     rsp, 20h
0x140006f8f  pop     rdi
0x140006f90  retn
```
