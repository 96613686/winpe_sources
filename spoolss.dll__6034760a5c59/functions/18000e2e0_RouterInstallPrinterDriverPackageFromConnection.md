# RouterInstallPrinterDriverPackageFromConnection

- ea: `0x18000e2e0`
- end: `0x18000e326`
- name: `RouterInstallPrinterDriverPackageFromConnection`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000e2e0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e309`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e309`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e316`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e316`

## string_xrefs

- `0x18000e30f`: `RouterInstallPrinterDriverPackageFromConnection`

## pseudocode

```c
__int64 RouterInstallPrinterDriverPackageFromConnection()
{
  if ( !g_bSandbox )
    return (*((__int64 (**)(void))g_pSpoolSvForwards + 201))();
  SetLastError(0x32u);
  OutputDebugStringA("RouterInstallPrinterDriverPackageFromConnection");
  return 2147942450LL;
}

```

## disassembly

```asm
0x18000e2e0  sub     rsp, 28h
0x18000e2e4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000e2eb  jnz     short loc_18000E304
0x18000e2ed  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000e2f4  mov     rax, [rax+648h]
0x18000e2fb  add     rsp, 28h
0x18000e2ff  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000e304  mov     ecx, 32h ; '2'; dwErrCode
0x18000e309  call    cs:__imp_SetLastError
0x18000e30f  lea     rcx, aRouterinstallp_2; "RouterInstallPrinterDriverPackageFromCo"...
0x18000e316  call    cs:__imp_OutputDebugStringA
0x18000e31c  mov     eax, 80070032h
0x18000e321  add     rsp, 28h
0x18000e325  retn
```
