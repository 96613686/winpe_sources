# CRegistryEventRequest::ForceDeactivate(void)

- ea: `0x180014000`
- end: `0x180014096`
- name: `?ForceDeactivate@CRegistryEventRequest@@QEAAJXZ`
- size: `150`
- prototype: `__int64 __fastcall(CRegistryEventRequest *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008370`

## callees

- `0x1800082d0`
- `0x18000a2e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014051`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014051`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014088`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014088`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014069`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014069`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180014039`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180014039`
- `wbemcomn!?Empty@CFlexArray@@QEAAXXZ` at `0x180014028`
- `wbemcomn!?Empty@CFlexArray@@QEAAXXZ` at `0x180014028`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRegistryEventRequest::ForceDeactivate(CRegistryEventRequest *this)
{
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp+8h] BYREF

  CInCritSec::CInCritSec((CInCritSec *)&lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)((char *)this + 184));
  _InterlockedExchange((volatile __int32 *)this + 41, -1);
  CFlexArray::Empty((CRegistryEventRequest *)((char *)this + 32));
  UnregisterWaitEx(*((HANDLE *)this + 22), (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  *((_QWORD *)this + 22) = 0;
  RegCloseKey(*((HKEY *)this + 18));
  *((_QWORD *)this + 18) = 0;
  CloseHandle(*((HANDLE *)this + 19));
  *((_QWORD *)this + 19) = 0;
  CRegistryEventRequest::Release(this);
  LeaveCriticalSection(lpCriticalSection);
  return 0;
}

```

## disassembly

```asm
0x180014000  push    rbx
0x180014002  sub     rsp, 20h
0x180014006  mov     rbx, rcx
0x180014009  lea     rdx, [rcx+0B8h]; struct _RTL_CRITICAL_SECTION *
0x180014010  lea     rcx, [rsp+28h+lpCriticalSection]; this
0x180014015  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18001401a  nop
0x18001401b  or      eax, 0FFFFFFFFh
0x18001401e  xchg    eax, [rbx+0A4h]
0x180014024  lea     rcx, [rbx+20h]
0x180014028  call    cs:__imp_?Empty@CFlexArray@@QEAAXXZ; CFlexArray::Empty(void)
0x18001402e  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180014032  mov     rcx, [rbx+0B0h]; WaitHandle
0x180014039  call    cs:__imp_UnregisterWaitEx
0x18001403f  mov     qword ptr [rbx+0B0h], 0
0x18001404a  mov     rcx, [rbx+90h]; hKey
0x180014051  call    cs:__imp_RegCloseKey
0x180014057  mov     qword ptr [rbx+90h], 0
0x180014062  mov     rcx, [rbx+98h]; hObject
0x180014069  call    cs:__imp_CloseHandle
0x18001406f  mov     qword ptr [rbx+98h], 0
0x18001407a  mov     rcx, rbx; this
0x18001407d  call    ?Release@CRegistryEventRequest@@QEAAJXZ; CRegistryEventRequest::Release(void)
0x180014082  nop
0x180014083  mov     rcx, [rsp+28h+lpCriticalSection]; lpCriticalSection
0x180014088  call    cs:__imp_LeaveCriticalSection
0x18001408e  xor     eax, eax
0x180014090  add     rsp, 20h
0x180014094  pop     rbx
0x180014095  retn
```
