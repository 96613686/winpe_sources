# CWwanRegistryListener::Deinitialize(void)

- ea: `0x18008ac40`
- end: `0x18008ad1b`
- name: `?Deinitialize@CWwanRegistryListener@@QEAAXXZ`
- size: `219`
- prototype: `void __fastcall(CWwanRegistryListener *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180065dfc`
- `0x18007aa2c`

## callees

- `0x180012300`
- `0x180014f1c`
- `0x18008ac40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008ac54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008ac54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008ac6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008ad0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008ac6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008ad0a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18008aca9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18008aca9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18008ac9f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18008ac9f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18008ac90`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18008ac90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008accd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008accd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008acbb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008acbb`

## string_xrefs

- `0x18008ac7b`: `CWwanRegistryListener::Deinitialize`
- `0x18008ace4`: `CWwanRegistryListener::Deinitialize`
- `0x18008acfb`: `CWwanRegistryListener::Deinitialize`

## pseudocode

```c
void __fastcall CWwanRegistryListener::Deinitialize(CWwanRegistryListener *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  HKEY v3; // rcx
  void *v4; // rcx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( *(_DWORD *)this )
  {
    *(_DWORD *)this = 0;
    LeaveCriticalSection(v1);
    WwanLog::Info("CWwanRegistryListener::Deinitialize", 0, L" de-initializing.");
    SetThreadpoolWait(*((PTP_WAIT *)this + 9), 0, 0);
    WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)this + 9), 1);
    CloseThreadpoolWait(*((PTP_WAIT *)this + 9));
    v3 = (HKEY)*((_QWORD *)this + 6);
    *((_QWORD *)this + 9) = 0;
    RegCloseKey(v3);
    v4 = (void *)*((_QWORD *)this + 8);
    *((_QWORD *)this + 6) = 0;
    CloseHandle(v4);
    *((_QWORD *)this + 8) = 0;
    WwanLog::Info("CWwanRegistryListener::Deinitialize", 0, L" Deinitialized CWwanMDMPolicy");
  }
  else
  {
    WwanLog::Error("CWwanRegistryListener::Deinitialize", 0, L"called while m_fInitialized is false ");
    LeaveCriticalSection(v1);
  }
}

```

## disassembly

```asm
0x18008ac40  mov     [rsp+arg_0], rbx
0x18008ac45  push    rdi
0x18008ac46  sub     rsp, 20h
0x18008ac4a  lea     rdi, [rcx+8]
0x18008ac4e  mov     rbx, rcx
0x18008ac51  mov     rcx, rdi; lpCriticalSection
0x18008ac54  call    cs:__imp_EnterCriticalSection
0x18008ac5a  cmp     dword ptr [rbx], 0
0x18008ac5d  jz      loc_18008ACF2
0x18008ac63  mov     rcx, rdi; lpCriticalSection
0x18008ac66  mov     dword ptr [rbx], 0
0x18008ac6c  call    cs:__imp_LeaveCriticalSection
0x18008ac72  lea     r8, aDeInitializing; " de-initializing."
0x18008ac79  xor     edx, edx; struct _GUID *
0x18008ac7b  lea     rcx, aCwwanregistryl_0; "CWwanRegistryListener::Deinitialize"
0x18008ac82  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18008ac87  mov     rcx, [rbx+48h]; pwa
0x18008ac8b  xor     r8d, r8d; pftTimeout
0x18008ac8e  xor     edx, edx; h
0x18008ac90  call    cs:__imp_SetThreadpoolWait
0x18008ac96  mov     rcx, [rbx+48h]; pwa
0x18008ac9a  mov     edx, 1; fCancelPendingCallbacks
0x18008ac9f  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18008aca5  mov     rcx, [rbx+48h]; pwa
0x18008aca9  call    cs:__imp_CloseThreadpoolWait
0x18008acaf  mov     rcx, [rbx+30h]; hKey
0x18008acb3  mov     qword ptr [rbx+48h], 0
0x18008acbb  call    cs:__imp_RegCloseKey
0x18008acc1  mov     rcx, [rbx+40h]; hObject
0x18008acc5  mov     qword ptr [rbx+30h], 0
0x18008accd  call    cs:__imp_CloseHandle
0x18008acd3  lea     r8, aDeinitializedC_0; " Deinitialized CWwanMDMPolicy"
0x18008acda  mov     qword ptr [rbx+40h], 0
0x18008ace2  xor     edx, edx; struct _GUID *
0x18008ace4  lea     rcx, aCwwanregistryl_0; "CWwanRegistryListener::Deinitialize"
0x18008aceb  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18008acf0  jmp     short loc_18008AD10
0x18008acf2  lea     r8, aCalledWhileMFi; "called while m_fInitialized is false "
0x18008acf9  xor     edx, edx; struct _GUID *
0x18008acfb  lea     rcx, aCwwanregistryl_0; "CWwanRegistryListener::Deinitialize"
0x18008ad02  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18008ad07  mov     rcx, rdi; lpCriticalSection
0x18008ad0a  call    cs:__imp_LeaveCriticalSection
0x18008ad10  mov     rbx, [rsp+28h+arg_0]
0x18008ad15  add     rsp, 20h
0x18008ad19  pop     rdi
0x18008ad1a  retn
```
