# FlowEndpointBase::DoesWindowBelongToCallingProcess(HWND__ *)

- ea: `0x140055274`
- end: `0x140055353`
- name: `?DoesWindowBelongToCallingProcess@FlowEndpointBase@@IEAA_NPEAUHWND__@@@Z`
- size: `223`
- prototype: `bool(FlowEndpointBase *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1400588a0`

## callees

- `0x140052fbc`
- `0x140054bac`
- `0x140055274`
- `0x140067010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400552aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400552aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005531d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005531d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x1400552de`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x1400552de`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14005529c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14005529c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x14005530a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x14005530a`

## string_xrefs

- `0x140055295`: `user32.dll`

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
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v13);
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
0x140055274  mov     [rsp+arg_0], rbx
0x140055279  mov     [rsp+arg_8], rsi
0x14005527e  push    rdi
0x14005527f  sub     rsp, 20h
0x140055283  mov     rsi, rdx
0x140055286  mov     rdi, rcx
0x140055289  mov     rax, cs:?pfnGetSendMessageThread@?1??DoesWindowBelongToCallingProcess@FlowEndpointBase@@IEAA_NPEAUHWND__@@@Z@4P6APEAXKH@ZEA; void * (*`FlowEndpointBase::DoesWindowBelongToCallingProcess(HWND__ *)'::`2'::pfnGetSendMessageThread)(ulong,int)
0x140055290  test    rax, rax
0x140055293  jnz     short loc_1400552C0
0x140055295  lea     rcx, aUser32Dll_0; "user32.dll"
0x14005529c  call    cs:__imp_LoadLibraryW
0x1400552a2  mov     edx, 0AFFh; lpProcName
0x1400552a7  mov     rcx, rax; hModule
0x1400552aa  call    cs:__imp_GetProcAddress
0x1400552b0  mov     cs:?pfnGetSendMessageThread@?1??DoesWindowBelongToCallingProcess@FlowEndpointBase@@IEAA_NPEAUHWND__@@@Z@4P6APEAXKH@ZEA, rax; void * (*`FlowEndpointBase::DoesWindowBelongToCallingProcess(HWND__ *)'::`2'::pfnGetSendMessageThread)(ulong,int)
0x1400552b7  test    rax, rax
0x1400552ba  jz      loc_140055343
0x1400552c0  xor     edx, edx
0x1400552c2  mov     ecx, 800h
0x1400552c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400552cc  mov     [rsp+28h+arg_18], rax
0x1400552d1  lea     rcx, [rax-1]
0x1400552d5  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1400552d9  ja      short loc_14005531D
0x1400552db  mov     rcx, rax; Thread
0x1400552de  call    cs:__imp_GetProcessIdOfThread
0x1400552e4  mov     ebx, eax
0x1400552e6  cmp     rsi, [rdi+28h]
0x1400552ea  jnz     short loc_1400552FA
0x1400552ec  cmp     dword ptr [rdi+30h], 0
0x1400552f0  jz      short loc_1400552FA
0x1400552f2  cmp     eax, [rdi+30h]
0x1400552f5  setz    bl
0x1400552f8  jmp     short loc_140055337
0x1400552fa  mov     [rsp+28h+dwProcessId], 0
0x140055302  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x140055307  mov     rcx, rsi; hWnd
0x14005530a  call    cs:__imp_GetWindowThreadProcessId
0x140055310  test    eax, eax
0x140055312  jz      short loc_140055335
0x140055314  cmp     ebx, [rsp+28h+dwProcessId]
0x140055318  setz    bl
0x14005531b  jmp     short loc_140055337
0x14005531d  call    cs:__imp_GetLastError
0x140055323  cmp     eax, 5
0x140055326  jnz     short loc_140055335
0x140055328  call    ?AreRunningLowIl@FlowEndpointBase@@IEAA_NXZ; FlowEndpointBase::AreRunningLowIl(void)
0x14005532d  test    al, al
0x14005532f  jz      short loc_140055335
0x140055331  mov     bl, 1
0x140055333  jmp     short loc_140055337
0x140055335  xor     bl, bl
0x140055337  lea     rcx, [rsp+28h+arg_18]
0x14005533c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140055341  mov     al, bl
0x140055343  mov     rbx, [rsp+28h+arg_0]
0x140055348  mov     rsi, [rsp+28h+arg_8]
0x14005534d  add     rsp, 20h
0x140055351  pop     rdi
0x140055352  retn
```
