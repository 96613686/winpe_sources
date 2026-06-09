# CNtService::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)

- ea: `0x18005b4b4`
- end: `0x18005b575`
- name: `?ReportStatusToSCMgr@CNtService@@IEAAHKKKK@Z`
- size: `193`
- prototype: `__int64 __fastcall(CNtService *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18003c5d0`
- `0x180042e20`
- `0x18005b580`

## callees

- `0x18005b4b4`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005b52c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005b52c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005b4e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005b4e5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18005b53b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18005b53b`

## string_xrefs

- `0x18005b551`: `Could not SetServiceStatus`

## pseudocode

```c
__int64 __fastcall CNtService::ReportStatusToSCMgr(CNtService *this, int a2, __int64 a3, int a4, unsigned int a5)
{
  int v8; // eax
  __int128 v9; // xmm1
  unsigned int v10; // edi
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  if ( a2 == 2 || a2 == 1 )
    v8 = 0;
  else
    v8 = *((_DWORD *)this + 6);
  *((_DWORD *)this + 12) = v8;
  *((_DWORD *)this + 16) = a5;
  *((_DWORD *)this + 11) = a2;
  *((_DWORD *)this + 13) = 0;
  *((_DWORD *)this + 15) = a4;
  v9 = *(_OWORD *)((char *)this + 52);
  *(_OWORD *)&ServiceStatus.dwServiceType = *(_OWORD *)((char *)this + 40);
  *(_OWORD *)&ServiceStatus.dwWin32ExitCode = v9;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v10 = SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 4), &ServiceStatus);
  if ( !v10 )
    (*(void (__fastcall **)(CNtService *, const wchar_t *))(*(_QWORD *)this + 56LL))(
      this,
      L"Could not SetServiceStatus");
  return v10;
}

```

## disassembly

```asm
0x18005b4b4  push    rbx
0x18005b4b6  push    rbp
0x18005b4b7  push    rsi
0x18005b4b8  push    rdi
0x18005b4b9  sub     rsp, 58h
0x18005b4bd  mov     rax, cs:__security_cookie
0x18005b4c4  xor     rax, rsp
0x18005b4c7  mov     [rsp+78h+var_38], rax
0x18005b4cc  xorps   xmm0, xmm0
0x18005b4cf  mov     rbx, rcx
0x18005b4d2  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x18005b4d7  add     rcx, 48h ; 'H'; lpCriticalSection
0x18005b4db  mov     ebp, r9d
0x18005b4de  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x18005b4e3  mov     edi, edx
0x18005b4e5  call    cs:__imp_EnterCriticalSection
0x18005b4eb  cmp     edi, 2
0x18005b4ee  jz      short loc_18005B4F5
0x18005b4f0  cmp     edi, 1
0x18005b4f3  jnz     short loc_18005B4F9
0x18005b4f5  xor     eax, eax
0x18005b4f7  jmp     short loc_18005B4FC
0x18005b4f9  mov     eax, [rbx+18h]
0x18005b4fc  mov     [rbx+30h], eax
0x18005b4ff  lea     rcx, [rbx+48h]; lpCriticalSection
0x18005b503  mov     eax, [rsp+78h+arg_20]
0x18005b50a  mov     [rbx+40h], eax
0x18005b50d  mov     [rbx+2Ch], edi
0x18005b510  mov     dword ptr [rbx+34h], 0
0x18005b517  mov     [rbx+3Ch], ebp
0x18005b51a  movups  xmm0, xmmword ptr [rbx+28h]
0x18005b51e  movups  xmm1, xmmword ptr [rbx+34h]
0x18005b522  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x18005b527  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm1
0x18005b52c  call    cs:__imp_LeaveCriticalSection
0x18005b532  mov     rcx, [rbx+20h]; hServiceStatus
0x18005b536  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18005b53b  call    cs:__imp_SetServiceStatus
0x18005b541  mov     edi, eax
0x18005b543  test    eax, eax
0x18005b545  jnz     short loc_18005B55D
0x18005b547  mov     rdx, [rbx]
0x18005b54a  mov     rcx, rbx
0x18005b54d  mov     rax, [rdx+38h]
0x18005b551  lea     rdx, aCouldNotSetser; "Could not SetServiceStatus"
0x18005b558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b55d  mov     eax, edi
0x18005b55f  mov     rcx, [rsp+78h+var_38]
0x18005b564  xor     rcx, rsp; StackCookie
0x18005b567  call    __security_check_cookie
0x18005b56c  add     rsp, 58h
0x18005b570  pop     rdi
0x18005b571  pop     rsi
0x18005b572  pop     rbp
0x18005b573  pop     rbx
0x18005b574  retn
```
