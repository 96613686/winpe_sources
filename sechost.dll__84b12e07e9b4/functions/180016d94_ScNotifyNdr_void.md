# ScNotifyNdr(void)

- ea: `0x180016d94`
- end: `0x180016e00`
- name: `?ScNotifyNdr@@YAKXZ`
- size: `108`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180016c40`
- `0x180016cf0`

## callees

- `0x180016d94`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016dd1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016dd1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180016db1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180016db1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016df2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016df2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016dbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016dbb`

## string_xrefs

- `0x180016da8`: `rpcrt4.dll`

## pseudocode

```c
__int64 ScNotifyNdr(void)
{
  DWORD LastError; // eax
  DWORD v1; // ebx
  FARPROC ProcAddress; // rax
  HMODULE phModule; // [rsp+30h] [rbp+8h] BYREF

  phModule = 0;
  if ( GetModuleHandleExW(0, L"rpcrt4.dll", &phModule) )
  {
    v1 = 0;
    ProcAddress = GetProcAddress(phModule, "I_RpcSNCHOption");
    if ( !ProcAddress )
      goto LABEL_6;
    LastError = ((__int64 (__fastcall *)(__int64, _QWORD))ProcAddress)(2, 0);
  }
  else
  {
    LastError = GetLastError();
  }
  v1 = LastError;
LABEL_6:
  if ( phModule )
    FreeLibrary(phModule);
  return v1;
}

```

## disassembly

```asm
0x180016d94  push    rbx
0x180016d96  sub     rsp, 20h
0x180016d9a  lea     r8, [rsp+28h+phModule]; phModule
0x180016d9f  mov     [rsp+28h+phModule], 0
0x180016da8  lea     rdx, ModuleName; "rpcrt4.dll"
0x180016daf  xor     ecx, ecx; dwFlags
0x180016db1  call    cs:__imp_GetModuleHandleExW
0x180016db7  test    eax, eax
0x180016db9  jnz     short loc_180016DC3
0x180016dbb  call    cs:__imp_GetLastError
0x180016dc1  jmp     short loc_180016DE6
0x180016dc3  mov     rcx, [rsp+28h+phModule]; hModule
0x180016dc8  lea     rdx, aIRpcsnchoption; "I_RpcSNCHOption"
0x180016dcf  xor     ebx, ebx
0x180016dd1  call    cs:__imp_GetProcAddress
0x180016dd7  test    rax, rax
0x180016dda  jz      short loc_180016DE8
0x180016ddc  xor     edx, edx
0x180016dde  lea     ecx, [rbx+2]
0x180016de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016de6  mov     ebx, eax
0x180016de8  mov     rcx, [rsp+28h+phModule]; hLibModule
0x180016ded  test    rcx, rcx
0x180016df0  jz      short loc_180016DF8
0x180016df2  call    cs:__imp_FreeLibrary
0x180016df8  mov     eax, ebx
0x180016dfa  add     rsp, 20h
0x180016dfe  pop     rbx
0x180016dff  retn
```
