# SplDriverUnloadComplete

- ea: `0x18000f6d0`
- end: `0x18000f71c`
- name: `SplDriverUnloadComplete`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000f6d0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f6f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f6f9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000f710`

## string_xrefs

- `0x18000f705`: `SplDriverUnloadComplete`

## pseudocode

```c
void SplDriverUnloadComplete()
{
  if ( g_bSandbox )
  {
    SetLastError(0x32u);
    OutputDebugStringA("SplDriverUnloadComplete");
  }
  else
  {
    (*((void (**)(void))g_pSpoolSvForwards + 135))();
  }
}

```

## disassembly

```asm
0x18000f6d0  sub     rsp, 28h
0x18000f6d4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000f6db  jnz     short loc_18000F6F4
0x18000f6dd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000f6e4  mov     rax, [rax+438h]
0x18000f6eb  add     rsp, 28h
0x18000f6ef  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6f4  mov     ecx, 32h ; '2'; dwErrCode
0x18000f6f9  call    cs:__imp_SetLastError
0x18000f700  nop     dword ptr [rax+rax+00h]
0x18000f705  lea     rcx, aSpldriverunloa_0; "SplDriverUnloadComplete"
0x18000f70c  add     rsp, 28h
0x18000f710  jmp     cs:__imp_OutputDebugStringA
```
