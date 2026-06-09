# _dynamic_initializer_for__CWerCplSupportService::ms_instance__

- ea: `0x180001480`
- end: `0x1800014d1`
- name: `_dynamic_initializer_for__CWerCplSupportService::ms_instance__`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001c1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180001490`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180001490`

## pseudocode

```c
int dynamic_initializer_for__CWerCplSupportService::ms_instance__()
{
  InitializeCriticalSectionEx(&CWerCplSupportService::ms_instance, 0, 0);
  dword_18001C9B8 = 1;
  xmmword_18001C9C0 = 0;
  xmmword_18001C9D0 = 0;
  qword_18001C9E0 = 0;
  return atexit(dynamic_atexit_destructor_for__CWerCplSupportService::ms_instance__);
}

```

## disassembly

```asm
0x180001480  sub     rsp, 28h
0x180001484  xor     r8d, r8d; Flags
0x180001487  lea     rcx, ?ms_instance@CWerCplSupportService@@0V1@A; lpCriticalSection
0x18000148e  xor     edx, edx; dwSpinCount
0x180001490  call    cs:__imp_InitializeCriticalSectionEx
0x180001496  xorps   xmm0, xmm0
0x180001499  mov     cs:dword_18001C9B8, 1
0x1800014a3  xorps   xmm1, xmm1
0x1800014a6  movdqa  cs:xmmword_18001C9C0, xmm0
0x1800014ae  lea     rcx, _dynamic_atexit_destructor_for__CWerCplSupportService__ms_instance__
0x1800014b5  movdqa  cs:xmmword_18001C9D0, xmm1
0x1800014bd  mov     cs:qword_18001C9E0, 0
0x1800014c8  add     rsp, 28h
0x1800014cc  jmp     atexit
```
