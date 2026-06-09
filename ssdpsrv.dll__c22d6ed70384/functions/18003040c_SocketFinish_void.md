# SocketFinish(void)

- ea: `0x18003040c`
- end: `0x180030498`
- name: `?SocketFinish@@YAXXZ`
- size: `140`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18002d870`

## callees

- `0x18003040c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030452`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030452`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030474`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030474`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030436`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030436`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030485`
- `WS2_32!__imp_WSACleanup` at `0x180030420`
- `WS2_32!__imp_WSACleanup` at `0x180030420`

## pseudocode

```c
void SocketFinish(void)
{
  if ( _InterlockedDecrement(&dword_180042630) < 0 )
  {
    _InterlockedIncrement(&dword_180042630);
  }
  else
  {
    WSACleanup();
    if ( dword_18004262C )
    {
      EnterCriticalSection(&s_csPipValid);
      dword_18004262C = 0;
      if ( qword_180042638 )
      {
        free(qword_180042638);
        qword_180042638 = 0;
      }
      dword_180042640 = 0;
      LeaveCriticalSection(&s_csPipValid);
      DeleteCriticalSection(&s_csPipValid);
    }
  }
}

```

## disassembly

```asm
0x18003040c  sub     rsp, 28h
0x180030410  or      eax, 0FFFFFFFFh
0x180030413  lock xadd cs:dword_180042630, eax
0x18003041b  cmp     eax, 1
0x18003041e  js      short loc_18003048C
0x180030420  call    cs:__imp_WSACleanup
0x180030426  cmp     cs:dword_18004262C, 0
0x18003042d  jz      short loc_180030493
0x18003042f  lea     rcx, ?s_csPipValid@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180030436  call    cs:__imp_EnterCriticalSection
0x18003043c  mov     rcx, cs:qword_180042638; Block
0x180030443  mov     cs:dword_18004262C, 0
0x18003044d  test    rcx, rcx
0x180030450  jz      short loc_180030463
0x180030452  call    cs:__imp_free
0x180030458  mov     cs:qword_180042638, 0
0x180030463  lea     rcx, ?s_csPipValid@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003046a  mov     cs:dword_180042640, 0
0x180030474  call    cs:__imp_LeaveCriticalSection
0x18003047a  lea     rcx, ?s_csPipValid@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION s_csPipValid
0x180030481  add     rsp, 28h
0x180030485  jmp     cs:__imp_DeleteCriticalSection
0x18003048c  lock inc cs:dword_180042630
0x180030493  add     rsp, 28h
0x180030497  retn
```
