# CWerCplSupportService::StaticHandler(ulong,ulong,void *,void *)

- ea: `0x180007b00`
- end: `0x180007b81`
- name: `?StaticHandler@CWerCplSupportService@@CAKKKPEAX0@Z`
- size: `129`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180007b00`
- `0x180007c9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007b19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007b40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007b19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007b40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007b60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007b69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007b60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007b69`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007b4a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007b4a`

## pseudocode

```c
__int64 __fastcall CWerCplSupportService::StaticHandler(
        DWORD dwControl,
        DWORD dwEventType,
        LPVOID lpEventData,
        LPVOID lpContext)
{
  unsigned int v6; // esi
  DWORD v7; // edi

  v6 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)lpContext);
  v7 = dwControl - 1;
  if ( v7 )
  {
    if ( v7 == 3 )
      CWerCplSupportService::_SetServiceStatus((CWerCplSupportService *)lpContext, *((_DWORD *)lpContext + 10));
    else
      v6 = 120;
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)lpContext);
    SetEvent(*((HANDLE *)lpContext + 7));
    CWerCplSupportService::_SetServiceStatus((CWerCplSupportService *)lpContext, 3u);
    LeaveCriticalSection((LPCRITICAL_SECTION)lpContext);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)lpContext);
  return v6;
}

```

## disassembly

```asm
0x180007b00  mov     [rsp+arg_0], rbx
0x180007b05  mov     [rsp+arg_8], rsi
0x180007b0a  push    rdi
0x180007b0b  sub     rsp, 20h
0x180007b0f  mov     edi, ecx
0x180007b11  mov     rbx, r9
0x180007b14  mov     rcx, r9; lpCriticalSection
0x180007b17  xor     esi, esi
0x180007b19  call    cs:__imp_EnterCriticalSection
0x180007b1f  sub     edi, 1
0x180007b22  jz      short loc_180007B3D
0x180007b24  cmp     edi, 3
0x180007b27  jz      short loc_180007B30
0x180007b29  mov     esi, 78h ; 'x'
0x180007b2e  jmp     short loc_180007B66
0x180007b30  mov     edx, [rbx+28h]; unsigned int
0x180007b33  mov     rcx, rbx; this
0x180007b36  call    ?_SetServiceStatus@CWerCplSupportService@@AEAAXKK@Z; CWerCplSupportService::_SetServiceStatus(ulong,ulong)
0x180007b3b  jmp     short loc_180007B66
0x180007b3d  mov     rcx, rbx; lpCriticalSection
0x180007b40  call    cs:__imp_EnterCriticalSection
0x180007b46  mov     rcx, [rbx+38h]; hEvent
0x180007b4a  call    cs:__imp_SetEvent
0x180007b50  mov     edx, 3; unsigned int
0x180007b55  mov     rcx, rbx; this
0x180007b58  call    ?_SetServiceStatus@CWerCplSupportService@@AEAAXKK@Z; CWerCplSupportService::_SetServiceStatus(ulong,ulong)
0x180007b5d  mov     rcx, rbx; lpCriticalSection
0x180007b60  call    cs:__imp_LeaveCriticalSection
0x180007b66  mov     rcx, rbx; lpCriticalSection
0x180007b69  call    cs:__imp_LeaveCriticalSection
0x180007b6f  mov     rbx, [rsp+28h+arg_0]
0x180007b74  mov     eax, esi
0x180007b76  mov     rsi, [rsp+28h+arg_8]
0x180007b7b  add     rsp, 20h
0x180007b7f  pop     rdi
0x180007b80  retn
```
