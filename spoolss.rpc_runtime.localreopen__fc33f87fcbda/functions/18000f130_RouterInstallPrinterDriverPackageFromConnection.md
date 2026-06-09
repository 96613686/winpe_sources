# RouterInstallPrinterDriverPackageFromConnection

- ea: `0x18000f130`
- end: `0x18000f183`
- name: `RouterInstallPrinterDriverPackageFromConnection`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000f130`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f159`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f159`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000f16c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000f16c`

## string_xrefs

- `0x18000f165`: `RouterInstallPrinterDriverPackageFromConnection`

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
0x18000f130  sub     rsp, 28h
0x18000f134  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000f13b  jnz     short loc_18000F154
0x18000f13d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000f144  mov     rax, [rax+648h]
0x18000f14b  add     rsp, 28h
0x18000f14f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000f154  mov     ecx, 32h ; '2'; dwErrCode
0x18000f159  call    cs:__imp_SetLastError
0x18000f160  nop     dword ptr [rax+rax+00h]
0x18000f165  lea     rcx, aRouterinstallp_2; "RouterInstallPrinterDriverPackageFromCo"...
0x18000f16c  call    cs:__imp_OutputDebugStringA
0x18000f173  nop     dword ptr [rax+rax+00h]
0x18000f178  mov     eax, 80070032h
0x18000f17d  add     rsp, 28h
0x18000f181  retn
```
