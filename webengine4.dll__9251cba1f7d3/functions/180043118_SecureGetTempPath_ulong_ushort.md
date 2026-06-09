# SecureGetTempPath(ulong,ushort *)

- ea: `0x180043118`
- end: `0x1800431e1`
- name: `?SecureGetTempPath@@YAKKPEAG@Z`
- size: `201`
- prototype: `unsigned int __fastcall(DWORD nBufferLength, LPWSTR lpBuffer)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800365bc`
- `0x180037c08`

## callees

- `0x180043118`
- `0x18004d030`
- `0x18006541c`
- `0x180065b60`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180043177`
- `KERNEL32!GetModuleHandleW` at `0x180043177`
- `KERNEL32!GetProcAddress` at `0x18004318c`
- `KERNEL32!GetProcAddress` at `0x18004318c`
- `KERNEL32!GetEnvironmentVariableW` at `0x180043150`
- `KERNEL32!GetEnvironmentVariableW` at `0x180043150`
- `KERNEL32!GetTempPathW` at `0x1800431c3`
- `KERNEL32!GetTempPathW` at `0x1800431c3`

## string_xrefs

- `0x180043170`: `kernel32.dll`
- `0x180043149`: `COMPlus_Disable_GetTempPath2`
- `0x180043182`: `GetTempPath2W`

## pseudocode

```c
DWORD __fastcall SecureGetTempPath(DWORD nBufferLength, LPWSTR lpBuffer)
{
  HMODULE ModuleHandleW; // rax
  WCHAR Buffer[8]; // [rsp+20h] [rbp-28h] BYREF

  if ( !g_fGetTempPathInitialized )
  {
    if ( GetEnvironmentVariableW(L"COMPlus_Disable_GetTempPath2", Buffer, 5u) != 4 || wcscmp_0(Buffer, L"true") )
    {
      ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
      if ( ModuleHandleW )
        g_pfnGetTempPath2 = (unsigned int (*)(unsigned int, unsigned __int16 *))GetProcAddress(
                                                                                  ModuleHandleW,
                                                                                  "GetTempPath2W");
    }
    g_fGetTempPathInitialized = 1;
  }
  if ( g_pfnGetTempPath2 )
    return ((__int64 (__fastcall *)(_QWORD, LPWSTR))g_pfnGetTempPath2)(nBufferLength, lpBuffer);
  else
    return GetTempPathW(nBufferLength, lpBuffer);
}

```

## disassembly

```asm
0x180043118  mov     [rsp+arg_10], rbx
0x18004311d  push    rdi
0x18004311e  sub     rsp, 40h
0x180043122  mov     rax, cs:__security_cookie
0x180043129  xor     rax, rsp
0x18004312c  mov     [rsp+48h+var_18], rax
0x180043131  mov     eax, cs:?g_fGetTempPathInitialized@@3HC; int volatile g_fGetTempPathInitialized
0x180043137  mov     rdi, rdx
0x18004313a  mov     ebx, ecx
0x18004313c  test    eax, eax
0x18004313e  jnz     short loc_1800431A3
0x180043140  lea     r8d, [rax+5]; nSize
0x180043144  lea     rdx, [rsp+48h+Buffer]; lpBuffer
0x180043149  lea     rcx, aComplusDisable; "COMPlus_Disable_GetTempPath2"
0x180043150  call    cs:__imp_GetEnvironmentVariableW
0x180043156  cmp     eax, 4
0x180043159  jnz     short loc_180043170
0x18004315b  lea     rdx, aTrue; "true"
0x180043162  lea     rcx, [rsp+48h+Buffer]; String1
0x180043167  call    wcscmp_0
0x18004316c  test    eax, eax
0x18004316e  jz      short loc_180043199
0x180043170  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180043177  call    cs:__imp_GetModuleHandleW
0x18004317d  test    rax, rax
0x180043180  jz      short loc_180043199
0x180043182  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x180043189  mov     rcx, rax; hModule
0x18004318c  call    cs:__imp_GetProcAddress
0x180043192  mov     cs:?g_pfnGetTempPath2@@3R6AKKPEAG@ZEA, rax; ulong (*g_pfnGetTempPath2)(ulong,ushort *)
0x180043199  mov     cs:?g_fGetTempPathInitialized@@3HC, 1; int volatile g_fGetTempPathInitialized
0x1800431a3  mov     rax, cs:?g_pfnGetTempPath2@@3R6AKKPEAG@ZEA; ulong (*g_pfnGetTempPath2)(ulong,ushort *)
0x1800431aa  mov     rdx, rdi; lpBuffer
0x1800431ad  mov     ecx, ebx; nBufferLength
0x1800431af  test    rax, rax
0x1800431b2  jz      short loc_1800431C3
0x1800431b4  mov     rax, cs:?g_pfnGetTempPath2@@3R6AKKPEAG@ZEA; ulong (*g_pfnGetTempPath2)(ulong,ushort *)
0x1800431bb  call    cs:__guard_dispatch_icall_fptr
0x1800431c1  jmp     short loc_1800431C9
0x1800431c3  call    cs:__imp_GetTempPathW
0x1800431c9  mov     rcx, [rsp+48h+var_18]
0x1800431ce  xor     rcx, rsp; StackCookie
0x1800431d1  call    __security_check_cookie
0x1800431d6  mov     rbx, [rsp+48h+arg_10]
0x1800431db  add     rsp, 40h
0x1800431df  pop     rdi
0x1800431e0  retn
```
