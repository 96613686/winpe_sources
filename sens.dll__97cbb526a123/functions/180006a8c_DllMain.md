# DllMain

- ea: `0x180006a8c`
- end: `0x180006b42`
- name: `DllMain`
- size: `182`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800085f4`

## callees

- `0x180006a8c`
- `0x180006b48`
- `0x180006ba0`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180006ac8`
- `RPCRT4!RpcBindingFree` at `0x180006ac8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006ab4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006ab4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006b37`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006b37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ae1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ae1`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180006adb`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180006adb`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      ghSensHeap = GetProcessHeap();
      qword_180011768 = 0;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CtlGuid;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      WPP_MAIN_CB = 0;
      qword_180011770 = 1;
      WppInitUm();
      InitializeCriticalSection(&gSensapiLockP);
    }
  }
  else
  {
    if ( ghSensNotify )
    {
      RpcBindingFree(&ghSensNotify);
      ghSensNotify = 0;
    }
    DeleteCriticalSection(&gSensapiLockP);
    WppCleanupUm();
  }
  return 1;
}

```

## disassembly

```asm
0x180006a8c  sub     rsp, 28h
0x180006a90  test    edx, edx
0x180006a92  jz      short loc_180006AA3
0x180006a94  cmp     edx, 1
0x180006a97  jz      short loc_180006ADB
0x180006a99  mov     eax, 1
0x180006a9e  add     rsp, 28h
0x180006aa2  retn
0x180006aa3  cmp     cs:?ghSensNotify@@3PEAXEA, 0; void * ghSensNotify
0x180006aab  jnz     short loc_180006AC1
0x180006aad  lea     rcx, ?gSensapiLockP@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180006ab4  call    cs:__imp_DeleteCriticalSection
0x180006aba  call    WppCleanupUm
0x180006abf  jmp     short loc_180006A99
0x180006ac1  lea     rcx, ?ghSensNotify@@3PEAXEA; Binding
0x180006ac8  call    cs:__imp_RpcBindingFree
0x180006ace  mov     cs:?ghSensNotify@@3PEAXEA, 0; void * ghSensNotify
0x180006ad9  jmp     short loc_180006AAD
0x180006adb  call    cs:__imp_DisableThreadLibraryCalls
0x180006ae1  call    cs:__imp_GetProcessHeap
0x180006ae7  mov     cs:?ghSensHeap@@3PEAXEA, rax; void * ghSensHeap
0x180006aee  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x180006af5  mov     cs:qword_180011768, 0
0x180006b00  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180006b07  lea     rax, WPP_MAIN_CB
0x180006b0e  mov     cs:WPP_GLOBAL_Control, rax
0x180006b15  mov     cs:WPP_MAIN_CB, 0
0x180006b20  mov     cs:qword_180011770, 1
0x180006b2b  call    WppInitUm
0x180006b30  lea     rcx, ?gSensapiLockP@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180006b37  call    cs:__imp_InitializeCriticalSection
0x180006b3d  jmp     loc_180006A99
```
