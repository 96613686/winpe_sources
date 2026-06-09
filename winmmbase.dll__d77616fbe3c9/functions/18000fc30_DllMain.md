# DllMain

- ea: `0x18000fc30`
- end: `0x18000fd8c`
- name: `DllMain`
- size: `348`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x180010534`

## callees

- `0x18000ddc8`
- `0x18000e968`
- `0x18000e998`
- `0x18000ea20`
- `0x18000ef5c`
- `0x18000efb8`
- `0x18000f35c`
- `0x18000f578`
- `0x18000fc30`
- `0x18001752c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fcd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fcd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fcc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fcc9`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000fd66`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000fd66`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000fd22`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000fd22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fd46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fd46`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000fc49`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000fc49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fd09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fd09`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  PVOID *v5; // rcx
  DWORD CurrentThreadId; // ebx
  DWORD CurrentProcessId; // eax
  int v8; // edx
  struct _RTL_CRITICAL_SECTION **v9; // rcx

  ghInst = hinstDLL;
  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    qword_18002D298 = 1;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_AudioTrace;
    qword_18002D290 = 0;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WPP_MAIN_CB = 0;
    WppInitUm();
    McGenEventRegister_EventRegister();
    return DllProcessAttach(hinstDLL);
  }
  else
  {
    if ( !fdwReason )
    {
      v5 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        CurrentThreadId = GetCurrentThreadId();
        CurrentProcessId = GetCurrentProcessId();
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          &WPP_9cbfd48b59f836f28c728f41f2315d00_Traceguids,
          CurrentProcessId,
          CurrentThreadId);
      }
      AudioSrvBindingFree(v5, *(_QWORD *)&fdwReason, lpvReserved);
      if ( Drivers32Handle )
      {
        RegCloseKey(Drivers32Handle);
        Drivers32Handle = 0;
      }
      if ( hInstalledDriverList )
      {
        GlobalFree(hInstalledDriverList);
        hInstalledDriverList = 0;
        cInstalledDrivers = 0;
      }
      InvalidatePreferredDevices();
      v9 = (struct _RTL_CRITICAL_SECTION **)hEventApiInit;
      if ( hEventApiInit )
        CloseHandle(hEventApiInit);
      if ( gfValidCS )
        mmDeleteMultipleCriticalSections(v9, v8);
      if ( gTlsIndex != -1 )
      {
        TlsFree(gTlsIndex);
        gTlsIndex = -1;
      }
      McGenEventUnregister_EventUnregister();
      WppCleanupUm();
    }
    return 1;
  }
}

```

## disassembly

```asm
0x18000fc30  mov     [rsp+arg_0], rbx
0x18000fc35  push    rdi
0x18000fc36  sub     rsp, 30h
0x18000fc3a  mov     cs:ghInst, rcx
0x18000fc41  mov     rbx, rcx
0x18000fc44  cmp     edx, 1
0x18000fc47  jnz     short loc_18000FC9D
0x18000fc49  call    cs:__imp_DisableThreadLibraryCalls
0x18000fc4f  lea     rax, WPP_ThisDir_CTLGUID_AudioTrace
0x18000fc56  mov     cs:qword_18002D298, 1
0x18000fc61  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000fc68  xor     edi, edi
0x18000fc6a  lea     rax, WPP_MAIN_CB
0x18000fc71  mov     cs:qword_18002D290, rdi
0x18000fc78  mov     cs:WPP_GLOBAL_Control, rax
0x18000fc7f  mov     cs:WPP_MAIN_CB, rdi
0x18000fc86  call    WppInitUm
0x18000fc8b  call    McGenEventRegister_EventRegister
0x18000fc90  mov     rcx, rbx; HINSTANCE
0x18000fc93  call    ?DllProcessAttach@@YAHPEAUHINSTANCE__@@@Z; DllProcessAttach(HINSTANCE__ *)
0x18000fc98  jmp     loc_18000FD81
0x18000fc9d  xor     edi, edi
0x18000fc9f  test    edx, edx
0x18000fca1  jnz     loc_18000FD7C
0x18000fca7  mov     rax, cs:WPP_GLOBAL_Control
0x18000fcae  lea     rcx, WPP_GLOBAL_Control
0x18000fcb5  cmp     rax, rcx
0x18000fcb8  jz      short loc_18000FCF8
0x18000fcba  test    dword ptr [rax+1Ch], 400000h
0x18000fcc1  jz      short loc_18000FCF8
0x18000fcc3  cmp     byte ptr [rax+19h], 4
0x18000fcc7  jb      short loc_18000FCF8
0x18000fcc9  call    cs:__imp_GetCurrentThreadId
0x18000fccf  mov     ebx, eax
0x18000fcd1  call    cs:__imp_GetCurrentProcessId
0x18000fcd7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcde  lea     edx, [rdi+0Bh]
0x18000fce1  mov     r9d, eax
0x18000fce4  mov     [rsp+38h+var_18], ebx
0x18000fce8  lea     r8, WPP_9cbfd48b59f836f28c728f41f2315d00_Traceguids
0x18000fcef  mov     rcx, [rcx+10h]
0x18000fcf3  call    WPP_SF_DD
0x18000fcf8  call    AudioSrvBindingFree
0x18000fcfd  mov     rcx, cs:?Drivers32Handle@@3PEAUHKEY__@@EA; hKey
0x18000fd04  test    rcx, rcx
0x18000fd07  jz      short loc_18000FD16
0x18000fd09  call    cs:__imp_RegCloseKey
0x18000fd0f  mov     cs:?Drivers32Handle@@3PEAUHKEY__@@EA, rdi; HKEY__ * Drivers32Handle
0x18000fd16  mov     rcx, cs:hInstalledDriverList; hMem
0x18000fd1d  test    rcx, rcx
0x18000fd20  jz      short loc_18000FD35
0x18000fd22  call    cs:__imp_GlobalFree
0x18000fd28  mov     cs:hInstalledDriverList, rdi
0x18000fd2f  mov     cs:cInstalledDrivers, edi
0x18000fd35  call    InvalidatePreferredDevices
0x18000fd3a  mov     rcx, cs:hEventApiInit; hObject
0x18000fd41  test    rcx, rcx
0x18000fd44  jz      short loc_18000FD4C
0x18000fd46  call    cs:__imp_CloseHandle
0x18000fd4c  cmp     cs:?gfValidCS@@3HA, edi; int gfValidCS
0x18000fd52  jz      short loc_18000FD59
0x18000fd54  call    ?mmDeleteMultipleCriticalSections@@YAXPEAPEAU_RTL_CRITICAL_SECTION@@J@Z; mmDeleteMultipleCriticalSections(_RTL_CRITICAL_SECTION * *,long)
0x18000fd59  mov     ecx, cs:gTlsIndex; dwTlsIndex
0x18000fd5f  or      ebx, 0FFFFFFFFh
0x18000fd62  cmp     ecx, ebx
0x18000fd64  jz      short loc_18000FD72
0x18000fd66  call    cs:__imp_TlsFree
0x18000fd6c  mov     cs:gTlsIndex, ebx
0x18000fd72  call    McGenEventUnregister_EventUnregister
0x18000fd77  call    WppCleanupUm
0x18000fd7c  mov     eax, 1
0x18000fd81  mov     rbx, [rsp+38h+arg_0]
0x18000fd86  add     rsp, 30h
0x18000fd8a  pop     rdi
0x18000fd8b  retn
```
