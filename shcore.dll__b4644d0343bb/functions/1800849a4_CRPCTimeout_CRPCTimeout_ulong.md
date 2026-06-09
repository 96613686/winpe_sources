# CRPCTimeout::CRPCTimeout(ulong)

- ea: `0x1800849a4`
- end: `0x180084a26`
- name: `??0CRPCTimeout@@QEAA@K@Z`
- size: `130`
- prototype: `CRPCTimeout *__fastcall(CRPCTimeout *__hidden this, DWORD DueTime)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180084b88`
- `0x180091f00`

## callees

- `0x1800849a4`
- `0x1800857b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800849b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800849b3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180084a13`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180084a13`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x1800849e2`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x1800849e2`

## pseudocode

```c
CRPCTimeout *__fastcall CRPCTimeout::CRPCTimeout(CRPCTimeout *this, DWORD DueTime)
{
  DWORD CurrentThreadId; // eax
  DWORD v5; // esi
  HRESULT v6; // eax

  CurrentThreadId = GetCurrentThreadId();
  *((_BYTE *)this + 4) = 0;
  *(_DWORD *)this = CurrentThreadId;
  *((_DWORD *)this + 2) = -2147467259;
  *((_QWORD *)this + 2) = 0;
  CBaseRPCTimeout::Disarm(this);
  v5 = 5000;
  if ( DueTime )
    v5 = DueTime;
  v6 = CoEnableCallCancellation(0);
  *((_DWORD *)this + 2) = v6;
  if ( v6 >= 0 )
    CreateTimerQueueTimer((PHANDLE)this + 2, 0, CBaseRPCTimeout::s_Callback, this, v5, 0x3E8u, 0);
  return this;
}

```

## disassembly

```asm
0x1800849a4  push    rbx
0x1800849a6  push    rsi
0x1800849a7  push    rdi
0x1800849a8  push    r14
0x1800849aa  sub     rsp, 48h
0x1800849ae  mov     ebx, edx
0x1800849b0  mov     rdi, rcx
0x1800849b3  call    cs:__imp_GetCurrentThreadId
0x1800849b9  mov     rcx, rdi; this
0x1800849bc  mov     byte ptr [rdi+4], 0
0x1800849c0  mov     [rdi], eax
0x1800849c2  mov     dword ptr [rdi+8], 80004005h
0x1800849c9  mov     qword ptr [rdi+10h], 0
0x1800849d1  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x1800849d6  test    ebx, ebx
0x1800849d8  mov     esi, 1388h
0x1800849dd  cmovnz  esi, ebx
0x1800849e0  xor     ecx, ecx; pReserved
0x1800849e2  call    cs:__imp_CoEnableCallCancellation
0x1800849e8  mov     [rdi+8], eax
0x1800849eb  test    eax, eax
0x1800849ed  js      short loc_180084A19
0x1800849ef  mov     [rsp+68h+Flags], 0; Flags
0x1800849f7  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x1800849fe  mov     [rsp+68h+Period], 3E8h; Period
0x180084a06  lea     rcx, [rdi+10h]; phNewTimer
0x180084a0a  mov     r9, rdi; Parameter
0x180084a0d  mov     [rsp+68h+DueTime], esi; DueTime
0x180084a11  xor     edx, edx; TimerQueue
0x180084a13  call    cs:__imp_CreateTimerQueueTimer
0x180084a19  mov     rax, rdi
0x180084a1c  add     rsp, 48h
0x180084a20  pop     r14
0x180084a22  pop     rdi
0x180084a23  pop     rsi
0x180084a24  pop     rbx
0x180084a25  retn
```
