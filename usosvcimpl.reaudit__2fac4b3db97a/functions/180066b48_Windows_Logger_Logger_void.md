# Windows::Logger::~Logger(void)

- ea: `0x180066b48`
- end: `0x180066bee`
- name: `??1Logger@Windows@@UEAA@XZ`
- size: `166`
- prototype: `void __fastcall(Windows::Logger *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18003224c`
- `0x1800374b4`
- `0x1800381c0`
- `0x180038630`

## callees

- `0x180011680`
- `0x180037a94`
- `0x180066b48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180066b9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180066b9f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180066bb1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180066bb1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180066b6b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180066b6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066bd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066bd8`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180066b89`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180066b89`

## pseudocode

```c
void __fastcall Windows::Logger::~Logger(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  TRACEHANDLE v3; // rcx
  PEVENT_TRACE_PROPERTIES *p_OwningThread; // rbx
  PEVENT_TRACE_PROPERTIES v5; // rcx

  v2 = this + 2;
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&Windows::Logger::`vftable';
  EnterCriticalSection(this + 2);
  v3 = *(_QWORD *)&this->LockCount;
  p_OwningThread = (PEVENT_TRACE_PROPERTIES *)&this->OwningThread;
  if ( v3 )
  {
    ControlTraceW(v3, 0, *p_OwningThread, 1u);
    *(_QWORD *)&this->LockCount = 0;
  }
  if ( v2 )
    LeaveCriticalSection(v2);
  std::wstring::~wstring(&this[3]);
  DeleteCriticalSection(v2);
  std::wstring::~wstring(&this[1].LockCount);
  std::vector<_GUID>::~vector<_GUID>(&this->LockSemaphore);
  v5 = *p_OwningThread;
  *p_OwningThread = 0;
  if ( v5 )
    LocalFree(v5);
}

```

## disassembly

```asm
0x180066b48  mov     [rsp+arg_8], rbx
0x180066b4d  mov     [rsp+arg_10], rsi
0x180066b52  push    rdi
0x180066b53  sub     rsp, 20h
0x180066b57  lea     rax, ??_7Logger@Windows@@6B@; const Windows::Logger::`vftable'
0x180066b5e  mov     rdi, rcx
0x180066b61  lea     rsi, [rcx+50h]
0x180066b65  mov     [rcx], rax
0x180066b68  mov     rcx, rsi; lpCriticalSection
0x180066b6b  call    cs:__imp_EnterCriticalSection
0x180066b71  mov     rcx, [rdi+8]; TraceHandle
0x180066b75  lea     rbx, [rdi+10h]
0x180066b79  test    rcx, rcx
0x180066b7c  jz      short loc_180066B97
0x180066b7e  mov     r8, [rbx]; Properties
0x180066b81  mov     r9d, 1; ControlCode
0x180066b87  xor     edx, edx; InstanceName
0x180066b89  call    cs:__imp_ControlTraceW
0x180066b8f  mov     qword ptr [rdi+8], 0
0x180066b97  test    rsi, rsi
0x180066b9a  jz      short loc_180066BA5
0x180066b9c  mov     rcx, rsi; lpCriticalSection
0x180066b9f  call    cs:__imp_LeaveCriticalSection
0x180066ba5  lea     rcx, [rdi+78h]; void *
0x180066ba9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180066bae  mov     rcx, rsi; lpCriticalSection
0x180066bb1  call    cs:__imp_DeleteCriticalSection
0x180066bb7  lea     rcx, [rdi+30h]; void *
0x180066bbb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180066bc0  lea     rcx, [rdi+18h]
0x180066bc4  call    ??1?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::~vector<_GUID>(void)
0x180066bc9  mov     rcx, [rbx]; hMem
0x180066bcc  mov     qword ptr [rbx], 0
0x180066bd3  test    rcx, rcx
0x180066bd6  jz      short loc_180066BDE
0x180066bd8  call    cs:__imp_LocalFree
0x180066bde  mov     rbx, [rsp+28h+arg_8]
0x180066be3  mov     rsi, [rsp+28h+arg_10]
0x180066be8  add     rsp, 20h
0x180066bec  pop     rdi
0x180066bed  retn
```
