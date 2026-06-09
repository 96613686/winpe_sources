# CRPCTimeout::CRPCTimeout(ulong)

- ea: `0x180080f78`
- end: `0x180080ff3`
- name: `??0CRPCTimeout@@QEAA@K@Z`
- size: `123`
- prototype: `CRPCTimeout *__fastcall(CRPCTimeout *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180084f70`

## callees

- `0x180080f78`
- `0x180082dd4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180080f85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180080f85`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180080fdf`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180080fdf`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180080faa`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180080faa`

## pseudocode

```c
CRPCTimeout *__fastcall CRPCTimeout::CRPCTimeout(CRPCTimeout *this)
{
  DWORD CurrentThreadId; // eax
  HRESULT v3; // eax

  CurrentThreadId = GetCurrentThreadId();
  *((_BYTE *)this + 4) = 0;
  *(_DWORD *)this = CurrentThreadId;
  *((_DWORD *)this + 2) = -2147467259;
  *((_QWORD *)this + 2) = 0;
  CBaseRPCTimeout::Disarm(this);
  v3 = CoEnableCallCancellation(0);
  *((_DWORD *)this + 2) = v3;
  if ( v3 >= 0 )
    CreateTimerQueueTimer((PHANDLE)this + 2, 0, CBaseRPCTimeout::s_Callback, this, 0xBB8u, 0x3E8u, 0);
  return this;
}

```

## disassembly

```asm
0x180080f78  mov     [rsp+arg_0], rbx
0x180080f7d  push    rdi
0x180080f7e  sub     rsp, 40h
0x180080f82  mov     rbx, rcx
0x180080f85  call    cs:__imp_GetCurrentThreadId
0x180080f8b  mov     rcx, rbx; this
0x180080f8e  mov     byte ptr [rbx+4], 0
0x180080f92  mov     [rbx], eax
0x180080f94  mov     dword ptr [rbx+8], 80004005h
0x180080f9b  mov     qword ptr [rbx+10h], 0
0x180080fa3  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x180080fa8  xor     ecx, ecx; pReserved
0x180080faa  call    cs:__imp_CoEnableCallCancellation
0x180080fb0  mov     [rbx+8], eax
0x180080fb3  test    eax, eax
0x180080fb5  js      short loc_180080FE5
0x180080fb7  mov     [rsp+48h+Flags], 0; Flags
0x180080fbf  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x180080fc6  mov     [rsp+48h+Period], 3E8h; Period
0x180080fce  lea     rcx, [rbx+10h]; phNewTimer
0x180080fd2  mov     r9, rbx; Parameter
0x180080fd5  mov     [rsp+48h+DueTime], 0BB8h; DueTime
0x180080fdd  xor     edx, edx; TimerQueue
0x180080fdf  call    cs:__imp_CreateTimerQueueTimer
0x180080fe5  mov     rax, rbx
0x180080fe8  mov     rbx, [rsp+48h+arg_0]
0x180080fed  add     rsp, 40h
0x180080ff1  pop     rdi
0x180080ff2  retn
```
