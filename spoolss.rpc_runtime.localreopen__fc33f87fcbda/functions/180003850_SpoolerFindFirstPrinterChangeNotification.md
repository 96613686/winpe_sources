# SpoolerFindFirstPrinterChangeNotification

- ea: `0x180003850`
- end: `0x1800038df`
- name: `SpoolerFindFirstPrinterChangeNotification`
- size: `143`
- prototype: `BOOL __stdcall(HANDLE hPrinter, DWORD fdwFilterFlags, DWORD fdwOptions, PVOID pPrinterNotifyOptions, PVOID pvReserved, PVOID pNotificationConfig, PHANDLE phNotify, PHANDLE phEvent)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180003850`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800038b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800038b7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800038ca`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800038ca`

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
0x180003850  push    rbx
0x180003852  sub     rsp, 50h
0x180003856  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000385d  mov     r11, r9
0x180003860  mov     ebx, edx
0x180003862  jnz     short loc_1800038B2
0x180003864  mov     rdx, [rsp+58h+pvReserved]
0x18000386c  mov     r10, [rsp+58h+phEvent]
0x180003874  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000387b  mov     r9, [rsp+58h+pNotificationConfig]
0x180003883  mov     [rsp+58h+var_20], r10
0x180003888  mov     r10, [rsp+58h+phNotify]
0x180003890  mov     rax, [rax+268h]
0x180003897  mov     [rsp+58h+var_28], r10
0x18000389c  mov     [rsp+58h+var_30], r9
0x1800038a1  mov     r9, r11
0x1800038a4  mov     [rsp+58h+var_38], rdx
0x1800038a9  mov     edx, ebx
0x1800038ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038b0  jmp     short loc_1800038D8
0x1800038b2  mov     ecx, 32h ; '2'; dwErrCode
0x1800038b7  call    cs:__imp_SetLastError
0x1800038be  nop     dword ptr [rax+rax+00h]
0x1800038c3  lea     rcx, aSpoolerfindfir_0; "SpoolerFindFirstPrinterChangeNotificati"...
0x1800038ca  call    cs:__imp_OutputDebugStringA
0x1800038d1  nop     dword ptr [rax+rax+00h]
0x1800038d6  xor     eax, eax
0x1800038d8  add     rsp, 50h
0x1800038dc  pop     rbx
0x1800038dd  retn
```
