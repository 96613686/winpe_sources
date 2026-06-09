# SqospQueueDeviceTimer

- ea: `0x140004550`
- end: `0x1400045a9`
- name: `SqospQueueDeviceTimer`
- size: `89`
- prototype: `__int64 __fastcall(PFLT_CONTEXT Context)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x1400011c0`
- `0x140002300`
- `0x1400066e0`
- `0x140007238`

## callees

- `0x140004550`

## import_xrefs

- `ntoskrnl!KeSetTimer` at `0x140004596`
- `ntoskrnl!KeSetTimer` at `0x140004596`
- `FLTMGR!FltReferenceContext` at `0x140004575`
- `FLTMGR!FltReferenceContext` at `0x140004575`

## pseudocode

```c
char __fastcall SqospQueueDeviceTimer(char *Context)
{
  signed __int32 v1; // eax

  v1 = *((_DWORD *)Context + 73);
  if ( !v1 )
  {
    v1 = _InterlockedCompareExchange((volatile signed __int32 *)Context + 73, 1, 0);
    if ( !v1 )
    {
      FltReferenceContext(Context);
      LOBYTE(v1) = KeSetTimer((PKTIMER)(Context + 296), (LARGE_INTEGER)-100000LL, (PKDPC)(Context + 360));
    }
  }
  return v1;
}

```

## disassembly

```asm
0x140004550  push    rbx
0x140004552  sub     rsp, 20h
0x140004556  mov     eax, [rcx+124h]
0x14000455c  mov     rbx, rcx
0x14000455f  test    eax, eax
0x140004561  jnz     short loc_1400045A2
0x140004563  mov     ecx, 1
0x140004568  lock cmpxchg [rbx+124h], ecx
0x140004570  jnz     short loc_1400045A2
0x140004572  mov     rcx, rbx; Context
0x140004575  call    cs:__imp_FltReferenceContext
0x14000457c  nop     dword ptr [rax+rax+00h]
0x140004581  lea     r8, [rbx+168h]; Dpc
0x140004588  mov     rdx, 0FFFFFFFFFFFE7960h; DueTime
0x14000458f  lea     rcx, [rbx+128h]; Timer
0x140004596  call    cs:__imp_KeSetTimer
0x14000459d  nop     dword ptr [rax+rax+00h]
0x1400045a2  add     rsp, 20h
0x1400045a6  pop     rbx
0x1400045a7  retn
```
