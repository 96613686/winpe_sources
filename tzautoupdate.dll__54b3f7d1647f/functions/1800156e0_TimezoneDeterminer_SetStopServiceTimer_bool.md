# TimezoneDeterminer::SetStopServiceTimer(bool)

- ea: `0x1800156e0`
- end: `0x180015743`
- name: `?SetStopServiceTimer@TimezoneDeterminer@@QEAAX_N@Z`
- size: `99`
- prototype: `void __fastcall(TimezoneDeterminer *this, unsigned __int8)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18001307c`
- `0x180014ec0`

## callees

- `0x1800156e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800156f4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015738`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015738`

## pseudocode

```c
void __fastcall TimezoneDeterminer::SetStopServiceTimer(TimezoneDeterminer *this, unsigned __int8 a2)
{
  void *v3; // rcx
  __int64 v4; // rax
  DWORD v5; // r9d
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  v3 = (void *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    SetEvent(v3);
  }
  else
  {
    v4 = 4 * (unsigned int)a2 + 1;
    v5 = v4 * *((_DWORD *)this + 8);
    pftDueTime = (struct _FILETIME)(-10000 * v4 * *((unsigned int *)this + 8));
    SetThreadpoolTimer(*((PTP_TIMER *)this + 5), &pftDueTime, 0, v5);
  }
}

```

## disassembly

```asm
0x1800156e0  sub     rsp, 28h
0x1800156e4  mov     r10, rcx
0x1800156e7  mov     rcx, [rcx+30h]
0x1800156eb  test    rcx, rcx
0x1800156ee  jz      short loc_1800156FB
0x1800156f0  add     rsp, 28h
0x1800156f4  jmp     cs:__imp_SetEvent
0x1800156fb  mov     r9d, [r10+20h]
0x1800156ff  xor     r8d, r8d; msPeriod
0x180015702  movzx   eax, dl
0x180015705  mov     ecx, r9d
0x180015708  lea     edx, ds:1[rax*4]
0x18001570f  mov     eax, edx
0x180015711  imul    rcx, rax
0x180015715  imul    r9d, edx; msWindowLength
0x180015719  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18001571e  imul    rax, rcx, 0FFFFFFFFFFFFD8F0h
0x180015725  mov     rcx, rax
0x180015728  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x18001572c  shr     rcx, 20h
0x180015730  mov     [rsp+28h+pftDueTime.dwHighDateTime], ecx
0x180015734  mov     rcx, [r10+28h]; pti
0x180015738  call    cs:__imp_SetThreadpoolTimer
0x18001573e  add     rsp, 28h
0x180015742  retn
```
