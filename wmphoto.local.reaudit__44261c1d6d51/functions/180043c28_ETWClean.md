# ETWClean

- ea: `0x180043c28`
- end: `0x180043c89`
- name: `ETWClean`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002f510`

## callees

- `0x180043c28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043c64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043c64`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043c40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043c40`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180043c7d`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180043c55`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180043c55`

## pseudocode

```c
void ETWClean()
{
  _QWORD *v0; // rdi
  struct _RTL_CRITICAL_SECTION *v1; // rbx

  v0 = g_petwPro;
  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)g_petwPro + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_petwPro + 16));
  if ( !*(_DWORD *)v0 )
    EventUnregister(v0[1]);
  LeaveCriticalSection(v1);
  DeleteCriticalSection(v1);
}

```

## disassembly

```asm
0x180043c28  mov     [rsp+arg_0], rbx
0x180043c2d  push    rdi
0x180043c2e  sub     rsp, 20h
0x180043c32  mov     rdi, cs:g_petwPro
0x180043c39  lea     rbx, [rdi+10h]
0x180043c3d  mov     rcx, rbx; lpCriticalSection
0x180043c40  call    cs:__imp_EnterCriticalSection
0x180043c47  nop     dword ptr [rax+rax+00h]
0x180043c4c  cmp     dword ptr [rdi], 0
0x180043c4f  jnz     short loc_180043C61
0x180043c51  mov     rcx, [rdi+8]; RegHandle
0x180043c55  call    cs:__imp_EventUnregister
0x180043c5c  nop     dword ptr [rax+rax+00h]
0x180043c61  mov     rcx, rbx; lpCriticalSection
0x180043c64  call    cs:__imp_LeaveCriticalSection
0x180043c6b  nop     dword ptr [rax+rax+00h]
0x180043c70  mov     rcx, rbx
0x180043c73  mov     rbx, [rsp+28h+arg_0]
0x180043c78  add     rsp, 20h
0x180043c7c  pop     rdi
0x180043c7d  jmp     cs:__imp_DeleteCriticalSection
```
