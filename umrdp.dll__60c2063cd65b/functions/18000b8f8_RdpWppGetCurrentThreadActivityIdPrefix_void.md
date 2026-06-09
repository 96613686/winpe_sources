# RdpWppGetCurrentThreadActivityIdPrefix(void)

- ea: `0x18000b8f8`
- end: `0x18000b986`
- name: `?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ`
- size: `142`
- prototype: `unsigned int(void)`
- caller_count: `214`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002390`
- `0x180002a20`
- `0x180002b60`
- `0x180002eb4`
- `0x180003100`
- `0x1800032f0`
- `0x180003f20`
- `0x180004680`
- `0x180004b90`
- `0x180004e70`
- `0x180004f50`
- `0x18000539c`
- `0x180005520`
- `0x180005694`
- `0x180005c10`
- `0x1800069e0`
- `0x180006c70`
- `0x1800072f0`
- `0x180008380`
- `0x1800087d0`
- `0x180008ac0`
- `0x180009768`
- `0x180009ca8`
- `0x18000a5cc`
- `0x18000a920`
- `0x18000a99c`
- `0x18000abf0`
- `0x18000b030`
- `0x18000b480`
- `0x18000b600`
- `0x18000e504`
- `0x18000e5c0`
- `0x18000e8f0`
- `0x18000efdc`
- `0x18000f420`
- `0x18000f4d0`
- `0x18000f650`
- `0x180015094`
- `0x180015428`
- `0x180015cd8`
- `0x1800161e8`
- `0x18001a7ac`
- `0x18001a8f0`
- `0x18001bb30`
- `0x1800275f4`
- `0x180027720`
- `0x180027900`
- `0x180027a4c`
- `0x180027b10`
- `0x180027b90`

## callees

- `0x18000b8f8`
- `0x180047ef0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000b935`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000b935`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b94b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b94b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b96a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b96a`

## string_xrefs

- `0x18000b920`: `Advapi32.dll`

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
0x18000b8f8  sub     rsp, 48h
0x18000b8fc  mov     rax, cs:__security_cookie
0x18000b903  xor     rax, rsp
0x18000b906  mov     [rsp+48h+var_10], rax
0x18000b90b  xor     eax, eax
0x18000b90d  mov     [rsp+48h+phModule], 0
0x18000b916  lea     r8, [rsp+48h+phModule]; phModule
0x18000b91b  mov     [rsp+48h+var_1C], rax
0x18000b920  lea     rdx, ModuleName; "Advapi32.dll"
0x18000b927  mov     [rsp+48h+var_14], eax
0x18000b92b  xor     ecx, ecx; dwFlags
0x18000b92d  mov     [rsp+48h+var_20], 0F4E10000h
0x18000b935  call    cs:__imp_GetModuleHandleExA
0x18000b93b  test    eax, eax
0x18000b93d  jz      short loc_18000B970
0x18000b93f  mov     rcx, [rsp+48h+phModule]; hModule
0x18000b944  lea     rdx, ProcName; "EventActivityIdControl"
0x18000b94b  call    cs:__imp_GetProcAddress
0x18000b951  test    rax, rax
0x18000b954  jz      short loc_18000B965
0x18000b956  lea     rdx, [rsp+48h+var_20]
0x18000b95b  mov     ecx, 1
0x18000b960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b965  mov     rcx, [rsp+48h+phModule]; hLibModule
0x18000b96a  call    cs:__imp_FreeLibrary
0x18000b970  mov     eax, [rsp+48h+var_20]
0x18000b974  mov     rcx, [rsp+48h+var_10]
0x18000b979  xor     rcx, rsp; StackCookie
0x18000b97c  call    __security_check_cookie
0x18000b981  add     rsp, 48h
0x18000b985  retn
```
