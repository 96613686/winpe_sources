# RdpWppGetCurrentThreadActivityIdPrefix(void)

- ea: `0x180003970`
- end: `0x1800039fe`
- name: `?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ`
- size: `142`
- prototype: `unsigned int(void)`
- caller_count: `29`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002e64`
- `0x180003178`
- `0x180003a04`
- `0x180003ef8`
- `0x180004cd0`
- `0x180005060`
- `0x180005260`
- `0x180005a30`
- `0x180006d80`
- `0x180006f60`
- `0x180007180`
- `0x180007430`
- `0x180007820`
- `0x180007de0`
- `0x180008690`
- `0x180008810`
- `0x180008990`
- `0x180008bc0`
- `0x180008ea0`
- `0x180009170`
- `0x180009380`
- `0x1800095c8`
- `0x1800097e0`
- `0x180009960`
- `0x180009bc0`
- `0x180009d6c`
- `0x18000a090`
- `0x18000a250`
- `0x18000a8ac`

## callees

- `0x180003970`
- `0x18000aea0`
- `0x18000c010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800039e2`
- `KERNEL32!FreeLibrary` at `0x1800039e2`
- `KERNEL32!GetProcAddress` at `0x1800039c3`
- `KERNEL32!GetProcAddress` at `0x1800039c3`
- `KERNEL32!GetModuleHandleExA` at `0x1800039ad`
- `KERNEL32!GetModuleHandleExA` at `0x1800039ad`

## string_xrefs

- `0x180003998`: `Advapi32.dll`

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
0x180003970  sub     rsp, 48h
0x180003974  mov     rax, cs:__security_cookie
0x18000397b  xor     rax, rsp
0x18000397e  mov     [rsp+48h+var_10], rax
0x180003983  xor     eax, eax
0x180003985  mov     [rsp+48h+phModule], 0
0x18000398e  lea     r8, [rsp+48h+phModule]; phModule
0x180003993  mov     [rsp+48h+var_1C], rax
0x180003998  lea     rdx, ModuleName; "Advapi32.dll"
0x18000399f  mov     [rsp+48h+var_14], eax
0x1800039a3  xor     ecx, ecx; dwFlags
0x1800039a5  mov     [rsp+48h+var_20], 0F4E10000h
0x1800039ad  call    cs:__imp_GetModuleHandleExA
0x1800039b3  test    eax, eax
0x1800039b5  jz      short loc_1800039E8
0x1800039b7  mov     rcx, [rsp+48h+phModule]; hModule
0x1800039bc  lea     rdx, ProcName; "EventActivityIdControl"
0x1800039c3  call    cs:__imp_GetProcAddress
0x1800039c9  test    rax, rax
0x1800039cc  jz      short loc_1800039DD
0x1800039ce  lea     rdx, [rsp+48h+var_20]
0x1800039d3  mov     ecx, 1
0x1800039d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039dd  mov     rcx, [rsp+48h+phModule]; hLibModule
0x1800039e2  call    cs:__imp_FreeLibrary
0x1800039e8  mov     eax, [rsp+48h+var_20]
0x1800039ec  mov     rcx, [rsp+48h+var_10]
0x1800039f1  xor     rcx, rsp; StackCookie
0x1800039f4  call    __security_check_cookie
0x1800039f9  add     rsp, 48h
0x1800039fd  retn
```
