# UnifiedStoreRundownProtection::RegisterForRundown(void *)

- ea: `0x180023b10`
- end: `0x180023c1c`
- name: `?RegisterForRundown@UnifiedStoreRundownProtection@@UEAAJPEAX@Z`
- size: `268`
- prototype: `__int64 __fastcall(PVOID pv, HANDLE hSourceHandle)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callees

- `0x1800068f0`
- `0x180023108`
- `0x180023b10`
- `0x18002993c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023bc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023bff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023bc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023bff`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180023b6f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180023b6f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180023b24`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180023b24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023b3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023b45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023b3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023b45`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180023b8a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180023b8a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180023bb6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180023bb6`

## string_xrefs

- `0x180023bdb`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\rpcservice.cpp`

## pseudocode

```c
__int64 __fastcall UnifiedStoreRundownProtection::RegisterForRundown(char *pv, HANDLE hSourceHandle)
{
  void **v4; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v6; // rax
  struct _TP_WAIT **v7; // rdi
  struct _TP_WAIT *ThreadpoolWait; // rbx
  signed int LastError; // eax
  unsigned int v11; // ebx
  __int64 v12; // r9
  signed int v13; // eax

  *((_DWORD *)pv + 50) = GetProcessId(hSourceHandle);
  v4 = tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),0>((void **)pv + 9);
  CurrentProcess = GetCurrentProcess();
  v6 = GetCurrentProcess();
  if ( DuplicateHandle(v6, hSourceHandle, CurrentProcess, v4, 0x101000u, 0, 0) )
  {
    v7 = (struct _TP_WAIT **)(pv + 64);
    ThreadpoolWait = CreateThreadpoolWait(UnifiedStoreRundownProtection::_TpCallback, pv, 0);
    if ( ThreadpoolWait == *((struct _TP_WAIT **)pv + 8) )
    {
      ThreadpoolWait = *v7;
    }
    else
    {
      tlx::auto_xxx<_TP_WAIT *,void (*)(_TP_WAIT *),&void CloseThreadpoolWait(_TP_WAIT *),0>::_Delete(pv + 64);
      *v7 = ThreadpoolWait;
    }
    if ( ThreadpoolWait )
    {
      SetThreadpoolWait(ThreadpoolWait, *((HANDLE *)pv + 9), 0);
      return 0;
    }
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    v12 = 560;
  }
  else
  {
    v13 = GetLastError();
    v11 = v13;
    if ( v13 > 0 )
      v11 = (unsigned __int16)v13 | 0x80070000;
    v12 = 554;
  }
  Log_UnistoreHREvent_0(
    v11,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\rpcservice.cpp",
    v12);
  return v11;
}

```

## disassembly

```asm
0x180023b10  push    rbx
0x180023b12  push    rbp
0x180023b13  push    rsi
0x180023b14  push    rdi
0x180023b15  push    r14
0x180023b17  sub     rsp, 40h
0x180023b1b  mov     rbp, rcx
0x180023b1e  mov     rsi, rdx
0x180023b21  mov     rcx, rdx; Process
0x180023b24  call    cs:__imp_GetProcessId
0x180023b2a  lea     rcx, [rbp+48h]
0x180023b2e  mov     [rbp+0C8h], eax
0x180023b34  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),0>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0> &)
0x180023b39  mov     rdi, rax
0x180023b3c  call    cs:__imp_GetCurrentProcess
0x180023b42  mov     rbx, rax
0x180023b45  call    cs:__imp_GetCurrentProcess
0x180023b4b  mov     [rsp+68h+dwOptions], 0; dwOptions
0x180023b53  mov     r9, rdi; lpTargetHandle
0x180023b56  mov     rcx, rax; hSourceProcessHandle
0x180023b59  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x180023b61  mov     r8, rbx; hTargetProcessHandle
0x180023b64  mov     [rsp+68h+dwDesiredAccess], 101000h; dwDesiredAccess
0x180023b6c  mov     rdx, rsi; hSourceHandle
0x180023b6f  call    cs:__imp_DuplicateHandle
0x180023b75  test    eax, eax
0x180023b77  jz      loc_180023BFF
0x180023b7d  xor     r8d, r8d; pcbe
0x180023b80  lea     rcx, ?_TpCallback@UnifiedStoreRundownProtection@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180023b87  mov     rdx, rbp; pv
0x180023b8a  call    cs:__imp_CreateThreadpoolWait
0x180023b90  lea     rdi, [rbp+40h]
0x180023b94  mov     rbx, rax
0x180023b97  cmp     rax, [rdi]
0x180023b9a  jz      short loc_180023BEF
0x180023b9c  mov     rcx, rdi
0x180023b9f  call    ?_Delete@?$auto_xxx@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?CloseThreadpoolWait@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<_TP_WAIT *,void (*)(_TP_WAIT *),&CloseThreadpoolWait(_TP_WAIT *),0>::_Delete(void)
0x180023ba4  mov     [rdi], rbx
0x180023ba7  test    rbx, rbx
0x180023baa  jz      short loc_180023BC9
0x180023bac  mov     rdx, [rbp+48h]; h
0x180023bb0  xor     r8d, r8d; pftTimeout
0x180023bb3  mov     rcx, rbx; pwa
0x180023bb6  call    cs:__imp_SetThreadpoolWait
0x180023bbc  xor     eax, eax
0x180023bbe  add     rsp, 40h
0x180023bc2  pop     r14
0x180023bc4  pop     rdi
0x180023bc5  pop     rsi
0x180023bc6  pop     rbp
0x180023bc7  pop     rbx
0x180023bc8  retn
0x180023bc9  call    cs:__imp_GetLastError
0x180023bcf  mov     ebx, eax
0x180023bd1  test    eax, eax
0x180023bd3  jg      short loc_180023BF4
0x180023bd5  mov     r9d, 230h
0x180023bdb  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180023be2  xor     edx, edx
0x180023be4  mov     ecx, ebx
0x180023be6  call    Log_UnistoreHREvent_0
0x180023beb  mov     eax, ebx
0x180023bed  jmp     short loc_180023BBE
0x180023bef  mov     rbx, [rdi]
0x180023bf2  jmp     short loc_180023BA7
0x180023bf4  movzx   ebx, ax
0x180023bf7  or      ebx, 80070000h
0x180023bfd  jmp     short loc_180023BD5
0x180023bff  call    cs:__imp_GetLastError
0x180023c05  mov     ebx, eax
0x180023c07  test    eax, eax
0x180023c09  jle     short loc_180023C14
0x180023c0b  movzx   ebx, ax
0x180023c0e  or      ebx, 80070000h
0x180023c14  mov     r9d, 22Ah
0x180023c1a  jmp     short loc_180023BDB
```
