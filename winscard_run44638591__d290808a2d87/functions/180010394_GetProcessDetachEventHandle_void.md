# _GetProcessDetachEventHandle(void)

- ea: `0x180010394`
- end: `0x1800103f4`
- name: `?_GetProcessDetachEventHandle@@YAPEAXXZ`
- size: `96`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f270`

## callees

- `0x180010394`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800103bb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800103bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001039f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001039f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800103cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800103cf`

## pseudocode

```c
HANDLE _GetProcessDetachEventHandle(void)
{
  HANDLE result; // rax

  EnterCriticalSection(&g_ProcessDetachEventCreateCS);
  if ( !g_hProcessDetachEvent )
    g_hProcessDetachEvent = CreateEventW(0, 1, 0, 0);
  LeaveCriticalSection(&g_ProcessDetachEventCreateCS);
  result = g_hProcessDetachEvent;
  if ( g_hProcessDetachEvent )
  {
    _InterlockedIncrement(&g_lProcessDetachEventClients);
    return g_hProcessDetachEvent;
  }
  return result;
}

```

## disassembly

```asm
0x180010394  sub     rsp, 28h
0x180010398  lea     rcx, ?g_ProcessDetachEventCreateCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001039f  call    cs:__imp_EnterCriticalSection
0x1800103a5  cmp     cs:?g_hProcessDetachEvent@@3PEAXEA, 0; void * g_hProcessDetachEvent
0x1800103ad  jnz     short loc_1800103C8
0x1800103af  xor     r9d, r9d; lpName
0x1800103b2  xor     r8d, r8d; bInitialState
0x1800103b5  xor     ecx, ecx; lpEventAttributes
0x1800103b7  lea     edx, [r9+1]; bManualReset
0x1800103bb  call    cs:__imp_CreateEventW
0x1800103c1  mov     cs:?g_hProcessDetachEvent@@3PEAXEA, rax; void * g_hProcessDetachEvent
0x1800103c8  lea     rcx, ?g_ProcessDetachEventCreateCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800103cf  call    cs:__imp_LeaveCriticalSection
0x1800103d5  mov     rax, cs:?g_hProcessDetachEvent@@3PEAXEA; void * g_hProcessDetachEvent
0x1800103dc  test    rax, rax
0x1800103df  jz      short loc_1800103EF
0x1800103e1  lock inc cs:?g_lProcessDetachEventClients@@3JA; long g_lProcessDetachEventClients
0x1800103e8  mov     rax, cs:?g_hProcessDetachEvent@@3PEAXEA; void * g_hProcessDetachEvent
0x1800103ef  add     rsp, 28h
0x1800103f3  retn
```
