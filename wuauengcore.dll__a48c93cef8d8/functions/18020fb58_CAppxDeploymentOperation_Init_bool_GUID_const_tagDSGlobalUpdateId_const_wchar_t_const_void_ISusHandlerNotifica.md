# CAppxDeploymentOperation::Init(bool,_GUID const *,tagDSGlobalUpdateId const *,wchar_t const *,void *,ISusHandlerNotification *)

- ea: `0x18020fb58`
- end: `0x18020fd84`
- name: `?Init@CAppxDeploymentOperation@@AEAAJ_NPEBU_GUID@@PEBUtagDSGlobalUpdateId@@PEB_WPEAXPEAUISusHandlerNotification@@@Z`
- size: `556`
- prototype: `__int64 __fastcall(CAppxDeploymentOperation *__hidden this, bool, const struct _GUID *, const struct tagDSGlobalUpdateId *, const wchar_t *, HANDLE hSourceHandle, struct ISusHandlerNotification *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18020f7ac`

## callees

- `0x180110d24`
- `0x180113ae8`
- `0x18012b618`
- `0x18020fb58`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18020fce1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18020fcfa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18020fce1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18020fcfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020fd09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020fd22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020fd09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020fd22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18020fbd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18020fbe1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18020fbd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18020fbe1`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18020fc0e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18020fc0e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18020fd65`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18020fd65`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18020fc7f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18020fc7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAppxDeploymentOperation::Init(
        CAppxDeploymentOperation *this,
        char a2,
        const struct _GUID *a3,
        const struct tagDSGlobalUpdateId *a4,
        const wchar_t *a5,
        HANDLE hSourceHandle,
        struct ISusHandlerNotification *a7)
{
  _QWORD *v9; // rbx
  void *v10; // rcx
  int Instance; // ebx
  HANDLE CurrentProcess; // rbx
  HANDLE v13; // rax
  __int64 v14; // rcx
  HANDLE EventW; // rax
  HANDLE v17; // rax
  signed int LastError; // eax
  signed int v19; // ecx
  signed int v20; // eax

  if ( a4 )
  {
    *((_OWORD *)this + 11) = *(_OWORD *)a4;
    *((_DWORD *)this + 48) = *((_DWORD *)a4 + 4);
  }
  if ( a3 )
    *(struct _GUID *)((char *)this + 276) = *a3;
  v9 = (_QWORD *)((char *)this + 536);
  v10 = (void *)*((_QWORD *)this + 67);
  if ( v10 )
  {
    SusFree(v10);
    *v9 = 0;
  }
  Instance = DuplicateOptionalString<wchar_t const *,wchar_t *>(a5, v9);
  if ( Instance < 0 )
    goto LABEL_19;
  if ( hSourceHandle )
  {
    CurrentProcess = GetCurrentProcess();
    v13 = GetCurrentProcess();
    if ( !DuplicateHandle(v13, hSourceHandle, CurrentProcess, (LPHANDLE)this + 4, 0x100000u, 0, 0) )
      goto LABEL_23;
  }
  else
  {
    *((_QWORD *)this + 4) = 0;
  }
  if ( *((struct ISusHandlerNotification **)this + 21) != a7 )
  {
    if ( a7 )
      (*(void (__fastcall **)(struct ISusHandlerNotification *))(*(_QWORD *)a7 + 8LL))(a7);
    v14 = *((_QWORD *)this + 21);
    *((_QWORD *)this + 21) = a7;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  if ( !StringFromGUID2((const GUID *const)this + 11, (LPOLESTR)this + 98, 39) )
  {
    Instance = -2147024774;
LABEL_19:
    WUTrace("CAppxDeploymentOperation::Init", 284, 4096, 3, Instance, L"Method failed");
    return (unsigned int)Instance;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 5) = EventW;
  if ( EventW )
  {
    v17 = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 6) = v17;
    if ( v17 )
    {
      Instance = CoCreateInstance(
                   &CLSID_ContextSwitcher,
                   0,
                   1u,
                   &GUID_000001da_0000_0000_c000_000000000046,
                   (LPVOID *)this + 20);
      if ( Instance >= 0 )
      {
        *((_BYTE *)this + 560) = a2;
        *((_DWORD *)this + 5) = 1;
        return (unsigned int)Instance;
      }
      goto LABEL_19;
    }
  }
LABEL_23:
  LastError = GetLastError();
  v19 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v19 = LastError;
  if ( v19 >= 0 )
  {
    Instance = -2147467259;
  }
  else
  {
    v20 = GetLastError();
    Instance = (unsigned __int16)v20 | 0x80070000;
    if ( v20 <= 0 )
      Instance = v20;
  }
  if ( Instance < 0 )
    goto LABEL_19;
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18020fb58  mov     [rsp+arg_0], rbx
0x18020fb5d  mov     [rsp+arg_8], rsi
0x18020fb62  mov     [rsp+arg_10], rdi
0x18020fb67  push    r14
0x18020fb69  sub     rsp, 40h
0x18020fb6d  mov     r14b, dl
0x18020fb70  mov     rdi, rcx
0x18020fb73  test    r9, r9
0x18020fb76  jz      short loc_18020FB8D
0x18020fb78  movups  xmm0, xmmword ptr [r9]
0x18020fb7c  movups  xmmword ptr [rcx+0B0h], xmm0
0x18020fb83  mov     eax, [r9+10h]
0x18020fb87  mov     [rcx+0C0h], eax
0x18020fb8d  test    r8, r8
0x18020fb90  jz      short loc_18020FB9E
0x18020fb92  movups  xmm0, xmmword ptr [r8]
0x18020fb96  movdqu  xmmword ptr [rcx+114h], xmm0
0x18020fb9e  lea     rbx, [rcx+218h]
0x18020fba5  mov     rcx, [rbx]; lpMem
0x18020fba8  test    rcx, rcx
0x18020fbab  jz      short loc_18020FBB9
0x18020fbad  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18020fbb2  mov     qword ptr [rbx], 0
0x18020fbb9  mov     rdx, rbx
0x18020fbbc  mov     rcx, [rsp+48h+arg_20]
0x18020fbc1  call    ??$DuplicateOptionalString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x18020fbc6  mov     ebx, eax
0x18020fbc8  test    eax, eax
0x18020fbca  js      loc_18020FC8E
0x18020fbd0  cmp     [rsp+48h+hSourceHandle], 0
0x18020fbd6  jz      short loc_18020FC1D
0x18020fbd8  call    cs:__imp_GetCurrentProcess
0x18020fbde  mov     rbx, rax
0x18020fbe1  call    cs:__imp_GetCurrentProcess
0x18020fbe7  mov     [rsp+48h+dwOptions], 0; dwOptions
0x18020fbef  mov     [rsp+48h+bInheritHandle], 0; bInheritHandle
0x18020fbf7  mov     [rsp+48h+dwDesiredAccess], 100000h; dwDesiredAccess
0x18020fbff  lea     r9, [rdi+20h]; lpTargetHandle
0x18020fc03  mov     r8, rbx; hTargetProcessHandle
0x18020fc06  mov     rdx, [rsp+48h+hSourceHandle]; hSourceHandle
0x18020fc0b  mov     rcx, rax; hSourceProcessHandle
0x18020fc0e  call    cs:__imp_DuplicateHandle
0x18020fc14  test    eax, eax
0x18020fc16  jnz     short loc_18020FC25
0x18020fc18  jmp     loc_18020FD09
0x18020fc1d  mov     qword ptr [rdi+20h], 0
0x18020fc25  mov     rbx, [rsp+48h+arg_30]
0x18020fc2d  cmp     [rdi+0A8h], rbx
0x18020fc34  jz      short loc_18020FC6B
0x18020fc36  test    rbx, rbx
0x18020fc39  jz      short loc_18020FC4B
0x18020fc3b  mov     rax, [rbx]
0x18020fc3e  mov     rcx, rbx
0x18020fc41  mov     rax, [rax+8]
0x18020fc45  call    _guard_dispatch_icall
0x18020fc4a  nop
0x18020fc4b  mov     rcx, [rdi+0A8h]
0x18020fc52  mov     [rdi+0A8h], rbx
0x18020fc59  test    rcx, rcx
0x18020fc5c  jz      short loc_18020FC6B
0x18020fc5e  mov     rax, [rcx]
0x18020fc61  mov     rax, [rax+10h]
0x18020fc65  call    _guard_dispatch_icall
0x18020fc6a  nop
0x18020fc6b  lea     rdx, [rdi+0C4h]; lpsz
0x18020fc72  lea     rcx, [rdi+0B0h]; rguid
0x18020fc79  mov     r8d, 27h ; '''; cchMax
0x18020fc7f  call    cs:__imp_StringFromGUID2
0x18020fc85  test    eax, eax
0x18020fc87  jnz     short loc_18020FCD3
0x18020fc89  mov     ebx, 8007007Ah
0x18020fc8e  lea     rax, aMethodFailed; "Method failed"
0x18020fc95  mov     qword ptr [rsp+48h+bInheritHandle], rax
0x18020fc9a  mov     [rsp+48h+dwDesiredAccess], ebx
0x18020fc9e  mov     edx, 11Ch
0x18020fca3  mov     r9d, 3
0x18020fca9  mov     r8d, 1000h
0x18020fcaf  lea     rcx, aCappxdeploymen; "CAppxDeploymentOperation::Init"
0x18020fcb6  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18020fcbb  mov     eax, ebx
0x18020fcbd  mov     rbx, [rsp+48h+arg_0]
0x18020fcc2  mov     rsi, [rsp+48h+arg_8]
0x18020fcc7  mov     rdi, [rsp+48h+arg_10]
0x18020fccc  add     rsp, 40h
0x18020fcd0  pop     r14
0x18020fcd2  retn
0x18020fcd3  xor     r9d, r9d; lpName
0x18020fcd6  xor     r8d, r8d; bInitialState
0x18020fcd9  lea     esi, [r9+1]
0x18020fcdd  mov     edx, esi; bManualReset
0x18020fcdf  xor     ecx, ecx; lpEventAttributes
0x18020fce1  call    cs:__imp_CreateEventW
0x18020fce7  mov     [rdi+28h], rax
0x18020fceb  test    rax, rax
0x18020fcee  jz      short loc_18020FD09
0x18020fcf0  xor     r9d, r9d; lpName
0x18020fcf3  xor     r8d, r8d; bInitialState
0x18020fcf6  mov     edx, esi; bManualReset
0x18020fcf8  xor     ecx, ecx; lpEventAttributes
0x18020fcfa  call    cs:__imp_CreateEventW
0x18020fd00  mov     [rdi+30h], rax
0x18020fd04  test    rax, rax
0x18020fd07  jnz     short loc_18020FD46
0x18020fd09  call    cs:__imp_GetLastError
0x18020fd0f  mov     edi, 80070000h
0x18020fd14  movzx   ecx, ax
0x18020fd17  or      ecx, edi
0x18020fd19  test    eax, eax
0x18020fd1b  cmovle  ecx, eax
0x18020fd1e  test    ecx, ecx
0x18020fd20  jns     short loc_18020FD34
0x18020fd22  call    cs:__imp_GetLastError
0x18020fd28  movzx   ebx, ax
0x18020fd2b  or      ebx, edi
0x18020fd2d  test    eax, eax
0x18020fd2f  cmovle  ebx, eax
0x18020fd32  jmp     short loc_18020FD39
0x18020fd34  mov     ebx, 80004005h
0x18020fd39  test    ebx, ebx
0x18020fd3b  jns     loc_18020FCBB
0x18020fd41  jmp     loc_18020FC8E
0x18020fd46  lea     rax, [rdi+0A0h]
0x18020fd4d  mov     qword ptr [rsp+48h+dwDesiredAccess], rax; ppv
0x18020fd52  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x18020fd59  mov     r8d, esi; dwClsContext
0x18020fd5c  xor     edx, edx; pUnkOuter
0x18020fd5e  lea     rcx, CLSID_ContextSwitcher; rclsid
0x18020fd65  call    cs:__imp_CoCreateInstance
0x18020fd6b  mov     ebx, eax
0x18020fd6d  test    eax, eax
0x18020fd6f  js      loc_18020FC8E
0x18020fd75  mov     [rdi+230h], r14b
0x18020fd7c  mov     [rdi+14h], esi
0x18020fd7f  jmp     loc_18020FCBB
```
