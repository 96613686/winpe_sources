# _dynamic_initializer_for____g_traceInfo__

- ea: `0x180001010`
- end: `0x18000105f`
- name: `_dynamic_initializer_for____g_traceInfo__`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001010`
- `0x18000eed4`
- `0x18000f2b8`
- `0x18002e934`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x180001027`
- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x180001027`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001014`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001014`

## pseudocode

```c
int dynamic_initializer_for____g_traceInfo__()
{
  const WCHAR *v0; // rcx
  __Trace *v1; // rcx

  dword_180068B88 = GetTickCount();
  hObject = CreateMutexA(0, 0, 0);
  if ( hObject )
  {
    __Trace::ReadLogDirectory(v0);
    __Trace::ReReadRegistry(v1);
  }
  else
  {
    CStaticCritSec::anyFailed_ = 1;
  }
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for____g_traceInfo__);
}

```

## disassembly

```asm
0x180001010  sub     rsp, 28h
0x180001014  call    cs:__imp_GetTickCount
0x18000101a  xor     r8d, r8d; lpName
0x18000101d  xor     edx, edx; bInitialOwner
0x18000101f  xor     ecx, ecx; lpMutexAttributes
0x180001021  mov     cs:dword_180068B88, eax
0x180001027  call    cs:__imp_CreateMutexA
0x18000102d  mov     cs:hObject, rax
0x180001034  test    rax, rax
0x180001037  jnz     short loc_180001045
0x180001039  mov     cs:?anyFailed_@CStaticCritSec@@0HA, 1; int CStaticCritSec::anyFailed_
0x180001043  jmp     short loc_18000104F
0x180001045  call    ?ReadLogDirectory@__Trace@@AEAAXXZ; __Trace::ReadLogDirectory(void)
0x18000104a  call    ?ReReadRegistry@__Trace@@AEAAXXZ; __Trace::ReReadRegistry(void)
0x18000104f  lea     rcx, _dynamic_atexit_destructor_for____g_traceInfo__
0x180001056  add     rsp, 28h
0x18000105a  jmp     atexit
```
