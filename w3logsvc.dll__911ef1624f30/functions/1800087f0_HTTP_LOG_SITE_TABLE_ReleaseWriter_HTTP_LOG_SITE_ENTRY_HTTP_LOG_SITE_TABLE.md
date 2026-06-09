# HTTP_LOG_SITE_TABLE::ReleaseWriter(HTTP_LOG_SITE_ENTRY *,HTTP_LOG_SITE_TABLE *)

- ea: `0x1800087f0`
- end: `0x18000884f`
- name: `?ReleaseWriter@HTTP_LOG_SITE_TABLE@@CAJPEAVHTTP_LOG_SITE_ENTRY@@PEAV1@@Z`
- size: `95`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *, struct HTTP_LOG_SITE_TABLE *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800087f0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000883c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000883c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008801`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008801`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_SITE_TABLE::ReleaseWriter(struct _RTL_CRITICAL_SECTION *a1, struct HTTP_LOG_SITE_TABLE *a2)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  EnterCriticalSection(a1 + 1);
  DebugInfo = a1[2].DebugInfo;
  if ( DebugInfo )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)&DebugInfo[14], 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(PRTL_CRITICAL_SECTION_DEBUG, __int64))&DebugInfo->Type)(DebugInfo, 1);
    a1[2].DebugInfo = 0;
  }
  LeaveCriticalSection(a1 + 1);
  return 0;
}

```

## disassembly

```asm
0x1800087f0  mov     [rsp+arg_8], rbx
0x1800087f5  push    rdi
0x1800087f6  sub     rsp, 20h
0x1800087fa  mov     rbx, rcx
0x1800087fd  add     rcx, 28h ; '('; lpCriticalSection
0x180008801  call    cs:__imp_EnterCriticalSection
0x180008807  mov     rcx, [rbx+50h]
0x18000880b  test    rcx, rcx
0x18000880e  jz      short loc_180008838
0x180008810  or      eax, 0FFFFFFFFh
0x180008813  lock xadd [rcx+2A0h], eax
0x18000881b  cmp     eax, 1
0x18000881e  jnz     short loc_180008830
0x180008820  mov     rax, [rcx]
0x180008823  mov     edx, 1
0x180008828  mov     rax, [rax]
0x18000882b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008830  mov     qword ptr [rbx+50h], 0
0x180008838  lea     rcx, [rbx+28h]; lpCriticalSection
0x18000883c  call    cs:__imp_LeaveCriticalSection
0x180008842  mov     rbx, [rsp+28h+arg_8]
0x180008847  xor     eax, eax
0x180008849  add     rsp, 20h
0x18000884d  pop     rdi
0x18000884e  retn
```
