# CNtService::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)

- ea: `0x18005e0a8`
- end: `0x18005e17c`
- name: `?ReportStatusToSCMgr@CNtService@@IEAAHKKKK@Z`
- size: `212`
- prototype: `__int64 __fastcall(CNtService *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18003e250`
- `0x180044fc0`
- `0x18005e190`

## callees

- `0x18005e0a8`
- `0x180082a40`
- `0x180088010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e126`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e126`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e0d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e0d9`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18005e13b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18005e13b`

## string_xrefs

- `0x18005e157`: `Could not SetServiceStatus`

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
0x18005e0a8  push    rbx
0x18005e0aa  push    rbp
0x18005e0ab  push    rsi
0x18005e0ac  push    rdi
0x18005e0ad  sub     rsp, 58h
0x18005e0b1  mov     rax, cs:__security_cookie
0x18005e0b8  xor     rax, rsp
0x18005e0bb  mov     [rsp+78h+var_38], rax
0x18005e0c0  xorps   xmm0, xmm0
0x18005e0c3  mov     rbx, rcx
0x18005e0c6  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x18005e0cb  add     rcx, 48h ; 'H'; lpCriticalSection
0x18005e0cf  mov     ebp, r9d
0x18005e0d2  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x18005e0d7  mov     edi, edx
0x18005e0d9  call    cs:__imp_EnterCriticalSection
0x18005e0e0  nop     dword ptr [rax+rax+00h]
0x18005e0e5  cmp     edi, 2
0x18005e0e8  jz      short loc_18005E0EF
0x18005e0ea  cmp     edi, 1
0x18005e0ed  jnz     short loc_18005E0F3
0x18005e0ef  xor     eax, eax
0x18005e0f1  jmp     short loc_18005E0F6
0x18005e0f3  mov     eax, [rbx+18h]
0x18005e0f6  mov     [rbx+30h], eax
0x18005e0f9  lea     rcx, [rbx+48h]; lpCriticalSection
0x18005e0fd  mov     eax, [rsp+78h+arg_20]
0x18005e104  mov     [rbx+40h], eax
0x18005e107  mov     [rbx+2Ch], edi
0x18005e10a  mov     dword ptr [rbx+34h], 0
0x18005e111  mov     [rbx+3Ch], ebp
0x18005e114  movups  xmm0, xmmword ptr [rbx+28h]
0x18005e118  movups  xmm1, xmmword ptr [rbx+34h]
0x18005e11c  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x18005e121  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm1
0x18005e126  call    cs:__imp_LeaveCriticalSection
0x18005e12d  nop     dword ptr [rax+rax+00h]
0x18005e132  mov     rcx, [rbx+20h]; hServiceStatus
0x18005e136  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18005e13b  call    cs:__imp_SetServiceStatus
0x18005e142  nop     dword ptr [rax+rax+00h]
0x18005e147  mov     edi, eax
0x18005e149  test    eax, eax
0x18005e14b  jnz     short loc_18005E163
0x18005e14d  mov     rdx, [rbx]
0x18005e150  mov     rcx, rbx
0x18005e153  mov     rax, [rdx+38h]
0x18005e157  lea     rdx, aCouldNotSetser; "Could not SetServiceStatus"
0x18005e15e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e163  mov     eax, edi
0x18005e165  mov     rcx, [rsp+78h+var_38]
0x18005e16a  xor     rcx, rsp; StackCookie
0x18005e16d  call    __security_check_cookie
0x18005e172  add     rsp, 58h
0x18005e176  pop     rdi
0x18005e177  pop     rsi
0x18005e178  pop     rbp
0x18005e179  pop     rbx
0x18005e17a  retn
```
