# ComTaskHost::StartTaskThread(void *)

- ea: `0x140004940`
- end: `0x140004a1f`
- name: `?StartTaskThread@ComTaskHost@@CAKPEAX@Z`
- size: `223`
- prototype: `__int64 __fastcall(ComTaskHost *Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x140004940`
- `0x140004a30`
- `0x140009be0`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400049d3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400049d3`

## pseudocode

```c
__int64 __fastcall ComTaskHost::StartTaskThread(ComTaskHost *Parameter)
{
  unsigned int started; // edi
  __int32 v4; // [rsp+40h] [rbp+8h] BYREF

  v4 = 0;
  _InterlockedExchange(&v4, 0);
  _InterlockedIncrement((volatile signed __int32 *)&ShutdownMgr::s_sync);
  _InterlockedExchange(&v4, _InterlockedCompareExchange(&dword_1400159E4, 0, 0) != 0);
  if ( _InterlockedCompareExchange(&v4, 0, 0) )
  {
    started = ComTaskHost::StartTaskWorker(Parameter);
  }
  else
  {
    started = -2147024255;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids,
        Parameter,
        -2147024255);
  }
  (*(void (__fastcall **)(ComTaskHost *))(*(_QWORD *)Parameter + 16LL))(Parameter);
  _InterlockedExchange(&v4, 0);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&ShutdownMgr::s_sync, 0xFFFFFFFF) == 1 )
    SetEvent((HANDLE)_InterlockedCompareExchange64(&ShutdownMgr::s_hEvent, -1, -1));
  return started;
}

```

## disassembly

```asm
0x140004940  mov     [rsp+arg_10], rbx
0x140004945  push    rdi
0x140004946  sub     rsp, 30h
0x14000494a  mov     rbx, rcx
0x14000494d  mov     [rsp+38h+arg_0], 0
0x140004955  xor     eax, eax
0x140004957  xchg    eax, [rsp+38h+arg_0]
0x14000495b  lock inc cs:?s_sync@ShutdownMgr@@0USync@1@A; ShutdownMgr::Sync ShutdownMgr::s_sync
0x140004962  xor     ecx, ecx
0x140004964  xor     eax, eax
0x140004966  lock cmpxchg cs:dword_1400159E4, ecx
0x14000496e  setnz   cl
0x140004971  xchg    ecx, [rsp+38h+arg_0]
0x140004975  xor     ecx, ecx
0x140004977  xor     eax, eax
0x140004979  lock cmpxchg [rsp+38h+arg_0], ecx
0x14000497f  jz      short loc_1400049DB
0x140004981  mov     rcx, rbx; this
0x140004984  call    ?StartTaskWorker@ComTaskHost@@AEAAJXZ; ComTaskHost::StartTaskWorker(void)
0x140004989  mov     edi, eax
0x14000498b  mov     rax, [rbx]
0x14000498e  mov     rcx, rbx
0x140004991  mov     rax, [rax+10h]
0x140004995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000499a  nop
0x14000499b  xor     eax, eax
0x14000499d  xchg    eax, [rsp+38h+arg_0]
0x1400049a1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400049a8  mov     eax, ecx
0x1400049aa  lock xadd cs:?s_sync@ShutdownMgr@@0USync@1@A, eax; ShutdownMgr::Sync ShutdownMgr::s_sync
0x1400049b2  cmp     eax, 1
0x1400049b5  jz      short loc_1400049C4
0x1400049b7  mov     eax, edi
0x1400049b9  mov     rbx, [rsp+38h+arg_10]
0x1400049be  add     rsp, 30h
0x1400049c2  pop     rdi
0x1400049c3  retn
0x1400049c4  mov     rax, rcx
0x1400049c7  lock cmpxchg cs:?s_hEvent@ShutdownMgr@@0VInterlockedAutoHandle@@A, rcx; InterlockedAutoHandle ShutdownMgr::s_hEvent
0x1400049d0  mov     rcx, rax; hEvent
0x1400049d3  call    cs:__imp_SetEvent
0x1400049d9  jmp     short loc_1400049B7
0x1400049db  mov     edi, 80070281h
0x1400049e0  lea     rax, WPP_GLOBAL_Control
0x1400049e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400049ee  cmp     rcx, rax
0x1400049f1  jz      short loc_14000498B
0x1400049f3  test    byte ptr [rcx+1Ch], 1
0x1400049f7  jz      short loc_14000498B
0x1400049f9  mov     edx, 0Dh
0x1400049fe  mov     [rsp+38h+var_18], 80070281h
0x140004a06  mov     r9, rbx
0x140004a09  lea     r8, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids
0x140004a10  mov     rcx, [rcx+10h]
0x140004a14  call    WPP_SF_qD
0x140004a19  jmp     loc_14000498B
```
