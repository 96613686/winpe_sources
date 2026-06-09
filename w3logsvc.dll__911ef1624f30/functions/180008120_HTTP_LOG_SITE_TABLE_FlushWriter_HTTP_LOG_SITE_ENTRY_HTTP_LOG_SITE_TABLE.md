# HTTP_LOG_SITE_TABLE::FlushWriter(HTTP_LOG_SITE_ENTRY *,HTTP_LOG_SITE_TABLE *)

- ea: `0x180008120`
- end: `0x18000816c`
- name: `?FlushWriter@HTTP_LOG_SITE_TABLE@@CAJPEAVHTTP_LOG_SITE_ENTRY@@PEAV1@@Z`
- size: `76`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *, struct HTTP_LOG_SITE_TABLE *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004b28`
- `0x180008120`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008154`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008154`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008138`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008138`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_SITE_TABLE::FlushWriter(struct _RTL_CRITICAL_SECTION *a1, struct HTTP_LOG_SITE_TABLE *a2)
{
  unsigned int v3; // edi
  LOG_WRITER *DebugInfo; // rcx

  v3 = 0;
  EnterCriticalSection(a1 + 1);
  DebugInfo = (LOG_WRITER *)a1[2].DebugInfo;
  if ( DebugInfo )
    v3 = LOG_WRITER::Flush(DebugInfo, 0);
  LeaveCriticalSection(a1 + 1);
  return v3;
}

```

## disassembly

```asm
0x180008120  mov     [rsp+arg_0], rbx
0x180008125  mov     [rsp+arg_8], rsi
0x18000812a  push    rdi
0x18000812b  sub     rsp, 20h
0x18000812f  mov     rbx, rcx
0x180008132  xor     edi, edi
0x180008134  add     rcx, 28h ; '('; lpCriticalSection
0x180008138  call    cs:__imp_EnterCriticalSection
0x18000813e  mov     rcx, [rbx+50h]; this
0x180008142  test    rcx, rcx
0x180008145  jz      short loc_180008150
0x180008147  xor     edx, edx; int
0x180008149  call    ?Flush@LOG_WRITER@@AEAAJH@Z; LOG_WRITER::Flush(int)
0x18000814e  mov     edi, eax
0x180008150  lea     rcx, [rbx+28h]; lpCriticalSection
0x180008154  call    cs:__imp_LeaveCriticalSection
0x18000815a  mov     rbx, [rsp+28h+arg_0]
0x18000815f  mov     eax, edi
0x180008161  mov     rsi, [rsp+28h+arg_8]
0x180008166  add     rsp, 20h
0x18000816a  pop     rdi
0x18000816b  retn
```
