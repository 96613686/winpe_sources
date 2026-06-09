# SpoolerFindFirstPrinterChangeNotification

- ea: `0x1800035a0`
- end: `0x180003622`
- name: `SpoolerFindFirstPrinterChangeNotification`
- size: `130`
- prototype: `BOOL __stdcall(HANDLE hPrinter, DWORD fdwFilterFlags, DWORD fdwOptions, PVOID pPrinterNotifyOptions, PVOID pvReserved, PVOID pNotificationConfig, PHANDLE phNotify, PHANDLE phEvent)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800035a0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003607`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003607`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003614`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003614`

## pseudocode

```c
BOOL __stdcall SpoolerFindFirstPrinterChangeNotification(
        HANDLE hPrinter,
        DWORD fdwFilterFlags,
        DWORD fdwOptions,
        PVOID pPrinterNotifyOptions,
        PVOID pvReserved,
        PVOID pNotificationConfig,
        PHANDLE phNotify,
        PHANDLE phEvent)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(HANDLE, _QWORD, DWORD, PVOID, PVOID, PVOID, PHANDLE, PHANDLE))g_pSpoolSvForwards
            + 77))(
             hPrinter,
             fdwFilterFlags,
             fdwOptions,
             pPrinterNotifyOptions,
             pvReserved,
             pNotificationConfig,
             phNotify,
             phEvent);
  SetLastError(0x32u);
  OutputDebugStringA("SpoolerFindFirstPrinterChangeNotification");
  return 0;
}

```

## disassembly

```asm
0x1800035a0  push    rbx
0x1800035a2  sub     rsp, 50h
0x1800035a6  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x1800035ad  mov     r11, r9
0x1800035b0  mov     ebx, edx
0x1800035b2  jnz     short loc_180003602
0x1800035b4  mov     rdx, [rsp+58h+pvReserved]
0x1800035bc  mov     r10, [rsp+58h+phEvent]
0x1800035c4  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x1800035cb  mov     r9, [rsp+58h+pNotificationConfig]
0x1800035d3  mov     [rsp+58h+var_20], r10
0x1800035d8  mov     r10, [rsp+58h+phNotify]
0x1800035e0  mov     rax, [rax+268h]
0x1800035e7  mov     [rsp+58h+var_28], r10
0x1800035ec  mov     [rsp+58h+var_30], r9
0x1800035f1  mov     r9, r11
0x1800035f4  mov     [rsp+58h+var_38], rdx
0x1800035f9  mov     edx, ebx
0x1800035fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003600  jmp     short loc_18000361C
0x180003602  mov     ecx, 32h ; '2'; dwErrCode
0x180003607  call    cs:__imp_SetLastError
0x18000360d  lea     rcx, aSpoolerfindfir_0; "SpoolerFindFirstPrinterChangeNotificati"...
0x180003614  call    cs:__imp_OutputDebugStringA
0x18000361a  xor     eax, eax
0x18000361c  add     rsp, 50h
0x180003620  pop     rbx
0x180003621  retn
```
