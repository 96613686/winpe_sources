# FlowEndpointBase::DoesWindowBelongToCallingProcess(HWND__ *)

- ea: `0x180426e20`
- end: `0x180426eff`
- name: `?DoesWindowBelongToCallingProcess@FlowEndpointBase@@IEAA_NPEAUHWND__@@@Z`
- size: `223`
- prototype: `bool(FlowEndpointBase *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18042b328`

## callees

- `0x1800a14f8`
- `0x180425e7c`
- `0x180426e20`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180426e56`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180426e56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180426ec9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180426ec9`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x180426e8a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x180426e8a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180426e48`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180426e48`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180426eb6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180426eb6`

## string_xrefs

- `0x180426e41`: `user32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall FlowEndpointBase::DoesWindowBelongToCallingProcess(FlowEndpointBase *this, HWND a2)
{
  FARPROC ProcAddress; // rax
  HMODULE LibraryW; // rax
  char *v6; // rax
  DWORD ProcessIdOfThread; // eax
  DWORD v8; // ebx
  bool v9; // bl
  FlowEndpointBase *v10; // rcx
  DWORD dwProcessId; // [rsp+40h] [rbp+18h] BYREF
  char *v13; // [rsp+48h] [rbp+20h] BYREF

  ProcAddress = (FARPROC)`FlowEndpointBase::DoesWindowBelongToCallingProcess'::`2'::pfnGetSendMessageThread;
  if ( `FlowEndpointBase::DoesWindowBelongToCallingProcess'::`2'::pfnGetSendMessageThread
    || (LibraryW = LoadLibraryW(L"user32.dll"),
        ProcAddress = GetProcAddress(LibraryW, (LPCSTR)0xAFF),
        (`FlowEndpointBase::DoesWindowBelongToCallingProcess'::`2'::pfnGetSendMessageThread = (__int64)ProcAddress) != 0) )
  {
    v6 = (char *)((__int64 (__fastcall *)(__int64, _QWORD))ProcAddress)(2048, 0);
    v13 = v6;
    if ( (unsigned __int64)(v6 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      if ( GetLastError() == 5 && FlowEndpointBase::AreRunningLowIl(v10) )
      {
        v9 = 1;
        goto LABEL_13;
      }
    }
    else
    {
      ProcessIdOfThread = GetProcessIdOfThread(v6);
      v8 = ProcessIdOfThread;
      if ( a2 == *((HWND *)this + 5) && *((_DWORD *)this + 12) )
      {
        v9 = ProcessIdOfThread == *((_DWORD *)this + 12);
LABEL_13:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v13);
        LOBYTE(ProcAddress) = v9;
        return (char)ProcAddress;
      }
      dwProcessId = 0;
      if ( GetWindowThreadProcessId(a2, &dwProcessId) )
      {
        v9 = v8 == dwProcessId;
        goto LABEL_13;
      }
    }
    v9 = 0;
    goto LABEL_13;
  }
  return (char)ProcAddress;
}

```

## disassembly

```asm
0x180426e20  mov     [rsp+arg_0], rbx
0x180426e25  mov     [rsp+arg_8], rsi
0x180426e2a  push    rdi
0x180426e2b  sub     rsp, 20h
0x180426e2f  mov     rsi, rdx
0x180426e32  mov     rdi, rcx
0x180426e35  mov     rax, cs:?pfnGetSendMessageThread@?1??DoesWindowBelongToCallingProcess@FlowEndpointBase@@IEAA_NPEAUHWND__@@@Z@4P6APEAXKH@ZEA; void * (*`FlowEndpointBase::DoesWindowBelongToCallingProcess(HWND__ *)'::`2'::pfnGetSendMessageThread)(ulong,int)
0x180426e3c  test    rax, rax
0x180426e3f  jnz     short loc_180426E6C
0x180426e41  lea     rcx, aUser32Dll; "user32.dll"
0x180426e48  call    cs:__imp_LoadLibraryW
0x180426e4e  mov     edx, 0AFFh; lpProcName
0x180426e53  mov     rcx, rax; hModule
0x180426e56  call    cs:__imp_GetProcAddress
0x180426e5c  mov     cs:?pfnGetSendMessageThread@?1??DoesWindowBelongToCallingProcess@FlowEndpointBase@@IEAA_NPEAUHWND__@@@Z@4P6APEAXKH@ZEA, rax; void * (*`FlowEndpointBase::DoesWindowBelongToCallingProcess(HWND__ *)'::`2'::pfnGetSendMessageThread)(ulong,int)
0x180426e63  test    rax, rax
0x180426e66  jz      loc_180426EEF
0x180426e6c  xor     edx, edx
0x180426e6e  mov     ecx, 800h
0x180426e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180426e78  mov     [rsp+28h+arg_18], rax
0x180426e7d  lea     rcx, [rax-1]
0x180426e81  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180426e85  ja      short loc_180426EC9
0x180426e87  mov     rcx, rax; Thread
0x180426e8a  call    cs:__imp_GetProcessIdOfThread
0x180426e90  mov     ebx, eax
0x180426e92  cmp     rsi, [rdi+28h]
0x180426e96  jnz     short loc_180426EA6
0x180426e98  cmp     dword ptr [rdi+30h], 0
0x180426e9c  jz      short loc_180426EA6
0x180426e9e  cmp     eax, [rdi+30h]
0x180426ea1  setz    bl
0x180426ea4  jmp     short loc_180426EE3
0x180426ea6  mov     [rsp+28h+dwProcessId], 0
0x180426eae  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x180426eb3  mov     rcx, rsi; hWnd
0x180426eb6  call    cs:__imp_GetWindowThreadProcessId
0x180426ebc  test    eax, eax
0x180426ebe  jz      short loc_180426EE1
0x180426ec0  cmp     ebx, [rsp+28h+dwProcessId]
0x180426ec4  setz    bl
0x180426ec7  jmp     short loc_180426EE3
0x180426ec9  call    cs:__imp_GetLastError
0x180426ecf  cmp     eax, 5
0x180426ed2  jnz     short loc_180426EE1
0x180426ed4  call    ?AreRunningLowIl@FlowEndpointBase@@IEAA_NXZ; FlowEndpointBase::AreRunningLowIl(void)
0x180426ed9  test    al, al
0x180426edb  jz      short loc_180426EE1
0x180426edd  mov     bl, 1
0x180426edf  jmp     short loc_180426EE3
0x180426ee1  xor     bl, bl
0x180426ee3  lea     rcx, [rsp+28h+arg_18]
0x180426ee8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180426eed  mov     al, bl
0x180426eef  mov     rbx, [rsp+28h+arg_0]
0x180426ef4  mov     rsi, [rsp+28h+arg_8]
0x180426ef9  add     rsp, 20h
0x180426efd  pop     rdi
0x180426efe  retn
```
