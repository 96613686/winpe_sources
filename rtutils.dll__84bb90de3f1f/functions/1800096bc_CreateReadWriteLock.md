# CreateReadWriteLock

- ea: `0x1800096bc`
- end: `0x18000970b`
- name: `CreateReadWriteLock`
- size: `79`
- prototype: `DWORD __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001510`
- `0x180003450`
- `0x180006e9c`

## callees

- `0x1800096bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800096ef`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800096ef`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800096cc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800096cc`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800096dd`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800096dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096fa`

## pseudocode

```c
DWORD __fastcall CreateReadWriteLock(LPCRITICAL_SECTION lpCriticalSection)
{
  HANDLE EventA; // rax

  LODWORD(lpCriticalSection[1].DebugInfo) = 0;
  InitializeCriticalSection(lpCriticalSection);
  EventA = CreateEventA(0, 0, 0, 0);
  *(_QWORD *)&lpCriticalSection[1].LockCount = EventA;
  if ( EventA )
    return 0;
  DeleteCriticalSection(lpCriticalSection);
  return GetLastError();
}

```

## disassembly

```asm
0x1800096bc  push    rbx
0x1800096be  sub     rsp, 20h
0x1800096c2  mov     rbx, rcx
0x1800096c5  mov     dword ptr [rcx+28h], 0
0x1800096cc  call    cs:__imp_InitializeCriticalSection
0x1800096d2  nop
0x1800096d3  xor     r9d, r9d; lpName
0x1800096d6  xor     r8d, r8d; bInitialState
0x1800096d9  xor     edx, edx; bManualReset
0x1800096db  xor     ecx, ecx; lpEventAttributes
0x1800096dd  call    cs:__imp_CreateEventA
0x1800096e3  mov     [rbx+30h], rax
0x1800096e7  test    rax, rax
0x1800096ea  jnz     short loc_180009701
0x1800096ec  mov     rcx, rbx; lpCriticalSection
0x1800096ef  call    cs:__imp_DeleteCriticalSection
0x1800096f5  add     rsp, 20h
0x1800096f9  pop     rbx
0x1800096fa  jmp     cs:__imp_GetLastError
0x180009701  xor     eax, eax
0x180009703  jmp     short $+2
0x180009705  add     rsp, 20h
0x180009709  pop     rbx
0x18000970a  retn
```
