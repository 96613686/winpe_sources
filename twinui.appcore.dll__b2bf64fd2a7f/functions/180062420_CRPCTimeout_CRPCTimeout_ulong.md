# CRPCTimeout::CRPCTimeout(ulong)

- ea: `0x180062420`
- end: `0x1800624a2`
- name: `??0CRPCTimeout@@QEAA@K@Z`
- size: `130`
- prototype: `CRPCTimeout *__fastcall(CRPCTimeout *__hidden this, DWORD DueTime)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800143f4`
- `0x18002aba0`
- `0x180063800`
- `0x18006fbbc`

## callees

- `0x180062420`
- `0x180062c48`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006242f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006242f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18006248f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18006248f`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18006245e`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18006245e`

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
0x180062420  push    rbx
0x180062422  push    rsi
0x180062423  push    rdi
0x180062424  push    r14
0x180062426  sub     rsp, 48h
0x18006242a  mov     ebx, edx
0x18006242c  mov     rdi, rcx
0x18006242f  call    cs:__imp_GetCurrentThreadId
0x180062435  mov     rcx, rdi; this
0x180062438  mov     byte ptr [rdi+4], 0
0x18006243c  mov     [rdi], eax
0x18006243e  mov     dword ptr [rdi+8], 80004005h
0x180062445  mov     qword ptr [rdi+10h], 0
0x18006244d  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x180062452  test    ebx, ebx
0x180062454  mov     esi, 1388h
0x180062459  cmovnz  esi, ebx
0x18006245c  xor     ecx, ecx; pReserved
0x18006245e  call    cs:__imp_CoEnableCallCancellation
0x180062464  mov     [rdi+8], eax
0x180062467  test    eax, eax
0x180062469  js      short loc_180062495
0x18006246b  mov     [rsp+68h+Flags], 0; Flags
0x180062473  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x18006247a  mov     [rsp+68h+Period], 3E8h; Period
0x180062482  lea     rcx, [rdi+10h]; phNewTimer
0x180062486  mov     r9, rdi; Parameter
0x180062489  mov     [rsp+68h+DueTime], esi; DueTime
0x18006248d  xor     edx, edx; TimerQueue
0x18006248f  call    cs:__imp_CreateTimerQueueTimer
0x180062495  mov     rax, rdi
0x180062498  add     rsp, 48h
0x18006249c  pop     r14
0x18006249e  pop     rdi
0x18006249f  pop     rsi
0x1800624a0  pop     rbx
0x1800624a1  retn
```
