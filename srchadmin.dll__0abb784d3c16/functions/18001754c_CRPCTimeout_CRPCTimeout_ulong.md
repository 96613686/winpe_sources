# CRPCTimeout::CRPCTimeout(ulong)

- ea: `0x18001754c`
- end: `0x1800175c7`
- name: `??0CRPCTimeout@@QEAA@K@Z`
- size: `123`
- prototype: `CRPCTimeout *__fastcall(CRPCTimeout *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018730`

## callees

- `0x18001754c`
- `0x180017650`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017559`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017559`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18001757e`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18001757e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800175b3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800175b3`

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
    CreateTimerQueueTimer((PHANDLE)this + 2, 0, CBaseRPCTimeout::s_Callback, this, 0x2710u, 0x3E8u, 0);
  return this;
}

```

## disassembly

```asm
0x18001754c  mov     [rsp+arg_0], rbx
0x180017551  push    rdi
0x180017552  sub     rsp, 40h
0x180017556  mov     rbx, rcx
0x180017559  call    cs:__imp_GetCurrentThreadId
0x18001755f  mov     rcx, rbx; this
0x180017562  mov     byte ptr [rbx+4], 0
0x180017566  mov     [rbx], eax
0x180017568  mov     dword ptr [rbx+8], 80004005h
0x18001756f  mov     qword ptr [rbx+10h], 0
0x180017577  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x18001757c  xor     ecx, ecx; pReserved
0x18001757e  call    cs:__imp_CoEnableCallCancellation
0x180017584  mov     [rbx+8], eax
0x180017587  test    eax, eax
0x180017589  js      short loc_1800175B9
0x18001758b  mov     [rsp+48h+Flags], 0; Flags
0x180017593  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x18001759a  mov     [rsp+48h+Period], 3E8h; Period
0x1800175a2  lea     rcx, [rbx+10h]; phNewTimer
0x1800175a6  mov     r9, rbx; Parameter
0x1800175a9  mov     [rsp+48h+DueTime], 2710h; DueTime
0x1800175b1  xor     edx, edx; TimerQueue
0x1800175b3  call    cs:__imp_CreateTimerQueueTimer
0x1800175b9  mov     rax, rbx
0x1800175bc  mov     rbx, [rsp+48h+arg_0]
0x1800175c1  add     rsp, 40h
0x1800175c5  pop     rdi
0x1800175c6  retn
```
