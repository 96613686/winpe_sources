# RdpWppGetCurrentThreadActivityIdPrefix(void)

- ea: `0x18002ee14`
- end: `0x18002eea2`
- name: `?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ`
- size: `142`
- prototype: `unsigned int(void)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000eadc`
- `0x18000ece8`
- `0x18000eee4`
- `0x18002eea8`
- `0x18002f140`

## callees

- `0x18002ee14`
- `0x18002fe40`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ee67`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ee67`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18002ee51`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18002ee51`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002ee86`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002ee86`

## string_xrefs

- `0x18002ee3c`: `Advapi32.dll`

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
0x18002ee14  sub     rsp, 48h
0x18002ee18  mov     rax, cs:__security_cookie
0x18002ee1f  xor     rax, rsp
0x18002ee22  mov     [rsp+48h+var_10], rax
0x18002ee27  xor     eax, eax
0x18002ee29  mov     [rsp+48h+phModule], 0
0x18002ee32  lea     r8, [rsp+48h+phModule]; phModule
0x18002ee37  mov     [rsp+48h+var_1C], rax
0x18002ee3c  lea     rdx, aAdvapi32Dll; "Advapi32.dll"
0x18002ee43  mov     [rsp+48h+var_14], eax
0x18002ee47  xor     ecx, ecx; dwFlags
0x18002ee49  mov     [rsp+48h+var_20], 0F4E10000h
0x18002ee51  call    cs:__imp_GetModuleHandleExA
0x18002ee57  test    eax, eax
0x18002ee59  jz      short loc_18002EE8C
0x18002ee5b  mov     rcx, [rsp+48h+phModule]; hModule
0x18002ee60  lea     rdx, aEventactivityi; "EventActivityIdControl"
0x18002ee67  call    cs:__imp_GetProcAddress
0x18002ee6d  test    rax, rax
0x18002ee70  jz      short loc_18002EE81
0x18002ee72  lea     rdx, [rsp+48h+var_20]
0x18002ee77  mov     ecx, 1
0x18002ee7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee81  mov     rcx, [rsp+48h+phModule]; hLibModule
0x18002ee86  call    cs:__imp_FreeLibrary
0x18002ee8c  mov     eax, [rsp+48h+var_20]
0x18002ee90  mov     rcx, [rsp+48h+var_10]
0x18002ee95  xor     rcx, rsp; StackCookie
0x18002ee98  call    __security_check_cookie
0x18002ee9d  add     rsp, 48h
0x18002eea1  retn
```
