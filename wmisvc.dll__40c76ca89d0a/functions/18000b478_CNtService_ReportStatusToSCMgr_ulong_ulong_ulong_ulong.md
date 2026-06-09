# CNtService::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)

- ea: `0x18000b478`
- end: `0x18000b4ec`
- name: `?ReportStatusToSCMgr@CNtService@@IEAAKKKKK@Z`
- size: `116`
- prototype: `__int64 __fastcall(CNtService *this, int, __int64, int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180006ed0`

## callees

- `0x18000b478`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b4c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b4c1`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000b4b7`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000b4b7`

## string_xrefs

- `0x18000b4ca`: `Could not SetServiceStatus`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CNtService::ReportStatusToSCMgr(CNtService *this, int a2, __int64 a3, int a4, unsigned int a5)
{
  DWORD LastError; // edi
  int v7; // eax

  LastError = 0;
  if ( a2 == 2 || a2 == 1 )
    v7 = 0;
  else
    v7 = *((_DWORD *)this + 6) | 5;
  *((_DWORD *)this + 9) = v7;
  *((_DWORD *)this + 8) = a2;
  *((_DWORD *)this + 13) = a5;
  *((_DWORD *)this + 10) = 0;
  *((_DWORD *)this + 12) = a4;
  if ( !SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 7), (LPSERVICE_STATUS)this + 1) )
  {
    LastError = GetLastError();
    (*(void (__fastcall **)(CNtService *, const wchar_t *))(*(_QWORD *)this + 56LL))(
      this,
      L"Could not SetServiceStatus");
  }
  return LastError;
}

```

## disassembly

```asm
0x18000b478  mov     [rsp+arg_0], rbx
0x18000b47d  push    rdi
0x18000b47e  sub     rsp, 20h
0x18000b482  xor     edi, edi
0x18000b484  mov     rbx, rcx
0x18000b487  cmp     edx, 2
0x18000b48a  jz      short loc_18000B491
0x18000b48c  cmp     edx, 1
0x18000b48f  jnz     short loc_18000B495
0x18000b491  xor     eax, eax
0x18000b493  jmp     short loc_18000B49B
0x18000b495  mov     eax, [rcx+18h]
0x18000b498  or      eax, 5
0x18000b49b  mov     [rcx+24h], eax
0x18000b49e  mov     eax, [rsp+28h+arg_20]
0x18000b4a2  mov     [rcx+20h], edx
0x18000b4a5  lea     rdx, [rcx+1Ch]; lpServiceStatus
0x18000b4a9  mov     [rcx+34h], eax
0x18000b4ac  mov     [rcx+28h], edi
0x18000b4af  mov     [rcx+30h], r9d
0x18000b4b3  mov     rcx, [rcx+38h]; hServiceStatus
0x18000b4b7  call    cs:__imp_SetServiceStatus
0x18000b4bd  test    eax, eax
0x18000b4bf  jnz     short loc_18000B4DF
0x18000b4c1  call    cs:__imp_GetLastError
0x18000b4c7  mov     rcx, [rbx]
0x18000b4ca  lea     rdx, aCouldNotSetser; "Could not SetServiceStatus"
0x18000b4d1  mov     edi, eax
0x18000b4d3  mov     rax, [rcx+38h]
0x18000b4d7  mov     rcx, rbx
0x18000b4da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4df  mov     rbx, [rsp+28h+arg_0]
0x18000b4e4  mov     eax, edi
0x18000b4e6  add     rsp, 20h
0x18000b4ea  pop     rdi
0x18000b4eb  retn
```
