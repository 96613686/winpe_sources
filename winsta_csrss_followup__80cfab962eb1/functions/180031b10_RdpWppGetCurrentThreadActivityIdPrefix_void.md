# RdpWppGetCurrentThreadActivityIdPrefix(void)

- ea: `0x180031b10`
- end: `0x180031bb1`
- name: `?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ`
- size: `161`
- prototype: `unsigned int(void)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000f578`
- `0x18000f7a0`
- `0x18000f9c4`
- `0x180031bb8`
- `0x180031e70`

## callees

- `0x180031b10`
- `0x180032c20`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031b69`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031b69`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180031b4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180031b4d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180031b8e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180031b8e`

## string_xrefs

- `0x180031b38`: `Advapi32.dll`

## pseudocode

```c
__int64 RdpWppGetCurrentThreadActivityIdPrefix(void)
{
  FARPROC ProcAddress; // rax
  HMODULE phModule; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v3; // [rsp+28h] [rbp-20h] BYREF
  __int64 v4; // [rsp+2Ch] [rbp-1Ch]
  int v5; // [rsp+34h] [rbp-14h]

  phModule = 0;
  v4 = 0;
  v5 = 0;
  v3 = -186580992;
  if ( GetModuleHandleExA(0, "Advapi32.dll", &phModule) )
  {
    ProcAddress = GetProcAddress(phModule, "EventActivityIdControl");
    if ( ProcAddress )
      ((void (__fastcall *)(__int64, unsigned int *))ProcAddress)(1, &v3);
    FreeLibrary(phModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180031b10  sub     rsp, 48h
0x180031b14  mov     rax, cs:__security_cookie
0x180031b1b  xor     rax, rsp
0x180031b1e  mov     [rsp+48h+var_10], rax
0x180031b23  xor     eax, eax
0x180031b25  mov     [rsp+48h+phModule], 0
0x180031b2e  lea     r8, [rsp+48h+phModule]; phModule
0x180031b33  mov     [rsp+48h+var_1C], rax
0x180031b38  lea     rdx, aAdvapi32Dll; "Advapi32.dll"
0x180031b3f  mov     [rsp+48h+var_14], eax
0x180031b43  xor     ecx, ecx; dwFlags
0x180031b45  mov     [rsp+48h+var_20], 0F4E10000h
0x180031b4d  call    cs:__imp_GetModuleHandleExA
0x180031b54  nop     dword ptr [rax+rax+00h]
0x180031b59  test    eax, eax
0x180031b5b  jz      short loc_180031B9A
0x180031b5d  mov     rcx, [rsp+48h+phModule]; hModule
0x180031b62  lea     rdx, aEventactivityi; "EventActivityIdControl"
0x180031b69  call    cs:__imp_GetProcAddress
0x180031b70  nop     dword ptr [rax+rax+00h]
0x180031b75  test    rax, rax
0x180031b78  jz      short loc_180031B89
0x180031b7a  lea     rdx, [rsp+48h+var_20]
0x180031b7f  mov     ecx, 1
0x180031b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b89  mov     rcx, [rsp+48h+phModule]; hLibModule
0x180031b8e  call    cs:__imp_FreeLibrary
0x180031b95  nop     dword ptr [rax+rax+00h]
0x180031b9a  mov     eax, [rsp+48h+var_20]
0x180031b9e  mov     rcx, [rsp+48h+var_10]
0x180031ba3  xor     rcx, rsp; StackCookie
0x180031ba6  call    __security_check_cookie
0x180031bab  add     rsp, 48h
0x180031baf  retn
```
