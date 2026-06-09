# CRPCTimeout::CRPCTimeout(ulong)

- ea: `0x180028358`
- end: `0x1800283e9`
- name: `??0CRPCTimeout@@QEAA@K@Z`
- size: `145`
- prototype: `CRPCTimeout *__fastcall(CRPCTimeout *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011c10`

## callees

- `0x180028358`
- `0x1800283f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028370`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028370`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800283d0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800283d0`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18002839f`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18002839f`

## pseudocode

```c
CRPCTimeout *__fastcall CRPCTimeout::CRPCTimeout(CRPCTimeout *this)
{
  DWORD DueTime; // edi
  DWORD CurrentThreadId; // eax
  HRESULT v4; // eax

  DueTime = dwMilliseconds;
  CurrentThreadId = GetCurrentThreadId();
  *((_BYTE *)this + 4) = 0;
  *(_DWORD *)this = CurrentThreadId;
  *((_DWORD *)this + 2) = -2147467259;
  *((_QWORD *)this + 2) = 0;
  CBaseRPCTimeout::Disarm(this);
  if ( !DueTime )
    DueTime = 5000;
  v4 = CoEnableCallCancellation(0);
  *((_DWORD *)this + 2) = v4;
  if ( v4 >= 0 )
    CreateTimerQueueTimer((PHANDLE)this + 2, 0, CBaseRPCTimeout::s_Callback, this, DueTime, 0x3E8u, 0);
  return this;
}

```

## disassembly

```asm
0x180028358  mov     [rsp+arg_0], rbx
0x18002835d  mov     [rsp+arg_8], rsi
0x180028362  push    rdi
0x180028363  sub     rsp, 40h
0x180028367  mov     edi, cs:dwMilliseconds
0x18002836d  mov     rbx, rcx
0x180028370  call    cs:__imp_GetCurrentThreadId
0x180028376  mov     rcx, rbx; this
0x180028379  mov     byte ptr [rbx+4], 0
0x18002837d  mov     [rbx], eax
0x18002837f  mov     dword ptr [rbx+8], 80004005h
0x180028386  mov     qword ptr [rbx+10h], 0
0x18002838e  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x180028393  mov     eax, 1388h
0x180028398  test    edi, edi
0x18002839a  cmovz   edi, eax
0x18002839d  xor     ecx, ecx; pReserved
0x18002839f  call    cs:__imp_CoEnableCallCancellation
0x1800283a5  mov     [rbx+8], eax
0x1800283a8  test    eax, eax
0x1800283aa  js      short loc_1800283D6
0x1800283ac  mov     [rsp+48h+Flags], 0; Flags
0x1800283b4  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x1800283bb  mov     [rsp+48h+Period], 3E8h; Period
0x1800283c3  lea     rcx, [rbx+10h]; phNewTimer
0x1800283c7  mov     r9, rbx; Parameter
0x1800283ca  mov     [rsp+48h+DueTime], edi; DueTime
0x1800283ce  xor     edx, edx; TimerQueue
0x1800283d0  call    cs:__imp_CreateTimerQueueTimer
0x1800283d6  mov     rsi, [rsp+48h+arg_8]
0x1800283db  mov     rax, rbx
0x1800283de  mov     rbx, [rsp+48h+arg_0]
0x1800283e3  add     rsp, 40h
0x1800283e7  pop     rdi
0x1800283e8  retn
```
