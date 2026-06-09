# WFDOOBDeInitializeGlobalState(void)

- ea: `0x18000a574`
- end: `0x18000a5e9`
- name: `?WFDOOBDeInitializeGlobalState@@YAXXZ`
- size: `117`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009944`

## callees

- `0x18000a574`
- `0x1800185f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a599`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a599`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a5ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a5ca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a5d7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a5d7`

## pseudocode

```c
void WFDOOBDeInitializeGlobalState(void)
{
  void **i; // rbx

  if ( dword_180084C50 )
  {
    EnterCriticalSection(&CriticalSection);
    for ( i = (void **)g_oobGlobalState; i != (void **)&g_oobGlobalState; i = (void **)*i )
      RemoveContextFromGlobalList((struct _WFD_OOB_SESSION_CONTEXT *)(i - 124));
    LeaveCriticalSection(&CriticalSection);
    DeleteCriticalSection(&CriticalSection);
    dword_180084C50 = 0;
  }
}

```

## disassembly

```asm
0x18000a574  mov     [rsp+arg_0], rbx
0x18000a579  push    rsi
0x18000a57a  sub     rsp, 20h
0x18000a57e  cmp     cs:dword_180084C50, 0
0x18000a585  jnz     short loc_18000A592
0x18000a587  mov     rbx, [rsp+28h+arg_0]
0x18000a58c  add     rsp, 20h
0x18000a590  pop     rsi
0x18000a591  retn
0x18000a592  lea     rcx, CriticalSection; lpCriticalSection
0x18000a599  call    cs:__imp_EnterCriticalSection
0x18000a59f  mov     rbx, cs:?g_oobGlobalState@@3U_WFD_OOB_GLOBAL_STATE@@A; _WFD_OOB_GLOBAL_STATE g_oobGlobalState
0x18000a5a6  lea     rsi, ?g_oobGlobalState@@3U_WFD_OOB_GLOBAL_STATE@@A; _WFD_OOB_GLOBAL_STATE g_oobGlobalState
0x18000a5ad  jmp     short loc_18000A5BE
0x18000a5af  lea     rcx, [rbx-3E0h]; struct _WFD_OOB_SESSION_CONTEXT *
0x18000a5b6  call    ?RemoveContextFromGlobalList@@YAKPEAU_WFD_OOB_SESSION_CONTEXT@@@Z; RemoveContextFromGlobalList(_WFD_OOB_SESSION_CONTEXT *)
0x18000a5bb  mov     rbx, [rbx]
0x18000a5be  cmp     rbx, rsi
0x18000a5c1  jnz     short loc_18000A5AF
0x18000a5c3  lea     rcx, CriticalSection; lpCriticalSection
0x18000a5ca  call    cs:__imp_LeaveCriticalSection
0x18000a5d0  lea     rcx, CriticalSection; lpCriticalSection
0x18000a5d7  call    cs:__imp_DeleteCriticalSection
0x18000a5dd  mov     cs:dword_180084C50, 0
0x18000a5e7  jmp     short loc_18000A587
```
