# TimerCompletion

- ea: `0x180001bc0`
- end: `0x180001e72`
- name: `TimerCompletion`
- size: `690`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f260`

## callees

- `0x180001bc0`
- `0x180001e80`
- `0x18001b010`

## import_xrefs

- `ntdll!NtCreateTimer` at `0x180001e14`
- `ntdll!NtCreateTimer` at `0x180001e14`
- `ntdll!NtSetEvent` at `0x180001db9`
- `ntdll!NtSetEvent` at `0x180001db9`
- `ntdll!NtSetTimer` at `0x180001d62`
- `ntdll!NtSetTimer` at `0x180001d62`
- `api-ms-win-mm-time-l1-1-0!timeEndPeriod` at `0x180001d7b`
- `api-ms-win-mm-time-l1-1-0!timeEndPeriod` at `0x180001daa`
- `api-ms-win-mm-time-l1-1-0!timeEndPeriod` at `0x180001d7b`
- `api-ms-win-mm-time-l1-1-0!timeEndPeriod` at `0x180001daa`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180001e55`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180001e55`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001bd3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001c85`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001bd3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001c85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001c5b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001c5b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001d99`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180001c44`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180001c44`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001c99`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001df4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001c99`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001df4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!PulseEvent` at `0x180001dd4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!PulseEvent` at `0x180001dd4`

## pseudocode

```c
void __fastcall TimerCompletion(unsigned int a1)
{
  __int64 v1; // rdi
  unsigned __int64 v2; // rbx
  int v3; // eax
  int v4; // eax
  __int64 v5; // r14
  void (__fastcall *v6)(__int64, _QWORD, __int64, _QWORD, _QWORD); // rbp
  __int64 v7; // rcx
  __int64 v8; // rax
  signed __int64 v9; // rdx
  _LARGE_INTEGER v10; // rax
  UINT v11; // ecx
  void *TimerHandle; // [rsp+78h] [rbp+10h] BYREF
  _LARGE_INTEGER DueTime; // [rsp+80h] [rbp+18h] BYREF

  v1 = a1;
  EnterCriticalSection(&TimerThreadCritSec);
  v2 = (unsigned __int64)(v1 & 0xF) << 6;
  if ( *(_DWORD *)((char *)&Events[3] + v2) == (_DWORD)v1 )
  {
    if ( *(_DWORD *)((char *)&Events[7] + v2) && *(__int64 *)((char *)&Events[6] + v2) - ReadInterruptTick() > 0 )
    {
      do
        Sleep(1u);
      while ( *(__int64 *)((char *)&Events[6] + v2) - ReadInterruptTick() > 0 );
    }
    v3 = *(_DWORD *)((_BYTE *)&Events[3] + v2 + 4) & 0xF0;
    if ( v3 )
    {
      if ( v3 == 16 )
      {
        SetEvent(*(HANDLE *)((char *)&Events[1] + v2));
      }
      else if ( v3 == 32 )
      {
        PulseEvent(*(HANDLE *)((char *)&Events[1] + v2));
      }
    }
    else
    {
      v4 = *(_DWORD *)((char *)&Events[3] + v2);
      dword_180026978 = 1;
      dword_180026974 = v4;
      ResetEvent(hHandle);
      v5 = *(__int64 *)((char *)&Events[2] + v2);
      v6 = *(void (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _QWORD))((char *)&Events[1] + v2);
      LeaveCriticalSection(&TimerThreadCritSec);
      if ( v6 )
        v6(v1, 0, v5, 0, 0);
      EnterCriticalSection(&TimerThreadCritSec);
      dword_180026978 = 0;
      SetEvent(hHandle);
    }
    if ( (_DWORD)v1 == *(_DWORD *)((char *)&Events[3] + v2) )
    {
      if ( (*(_DWORD *)((_BYTE *)&Events[3] + v2 + 4) & 1) == 0 )
      {
        v11 = *(_DWORD *)((char *)Events + v2 + 4);
        *(_DWORD *)((char *)&Events[3] + v2) = 0;
        timeEndPeriod(v11);
        NtSetEvent(Handle, 0);
        goto LABEL_17;
      }
      v7 = *(__int64 *)((char *)&Events[6] + v2);
      v8 = 10000LL * *(unsigned int *)((char *)Events + v2);
      DueTime.QuadPart = 0;
      *(__int64 *)((char *)&Events[6] + v2) = v8 + v7;
      if ( (*(_DWORD *)((_BYTE *)&Events[3] + v2 + 4) & 1) != 0 )
      {
        while ( MEMORY[0x7FFE000C] != MEMORY[0x7FFE0010] )
          ;
        v9 = (MEMORY[0x7FFE0008] | ((unsigned __int64)MEMORY[0x7FFE000C] << 32)) - *(__int64 *)((char *)&Events[6] + v2);
      }
      else
      {
        v9 = -10000LL * *(unsigned int *)((char *)Events + v2);
      }
      v10.QuadPart = 0;
      if ( v9 <= 0 )
        v10.QuadPart = v9;
      DueTime = v10;
      if ( !*(__int64 *)((char *)&Events[4] + v2) )
      {
        TimerHandle = 0;
        if ( NtCreateTimer(&TimerHandle, 0x1F0003u, 0, NotificationTimer) < 0 )
          goto LABEL_16;
        *(__int64 *)((char *)&Events[4] + v2) = (__int64)TimerHandle;
      }
      if ( NtSetTimer(
             *(HANDLE *)((char *)&Events[4] + v2),
             &DueTime,
             0,
             (PVOID)*(unsigned int *)((char *)&Events[3] + v2),
             0,
             0,
             0) < 0 )
      {
LABEL_16:
        *(_DWORD *)((char *)&Events[3] + v2) = 0;
        timeEndPeriod(*(_DWORD *)((char *)Events + v2 + 4));
      }
    }
  }
LABEL_17:
  LeaveCriticalSection(&TimerThreadCritSec);
}

```

## disassembly

```asm
0x180001bc0  push    rbx
0x180001bc2  push    rsi
0x180001bc3  push    rdi
0x180001bc4  push    r15
0x180001bc6  sub     rsp, 48h
0x180001bca  mov     edi, ecx
0x180001bcc  lea     rcx, TimerThreadCritSec; lpCriticalSection
0x180001bd3  call    cs:__imp_EnterCriticalSection
0x180001bd9  mov     ebx, edi
0x180001bdb  lea     r15, Events
0x180001be2  and     ebx, 0Fh
0x180001be5  shl     rbx, 6
0x180001be9  mov     eax, [rbx+r15+18h]
0x180001bee  cmp     eax, edi
0x180001bf0  jnz     loc_180001D89
0x180001bf6  mov     eax, [rbx+r15+38h]
0x180001bfb  mov     [rsp+68h+arg_18], r12
0x180001c03  test    eax, eax
0x180001c05  jnz     loc_180001E31
0x180001c0b  mov     eax, [rbx+r15+1Ch]
0x180001c10  xor     r12d, r12d
0x180001c13  and     eax, 0F0h
0x180001c18  jnz     loc_180001DC1
0x180001c1e  mov     eax, [rbx+r15+18h]
0x180001c23  mov     rcx, cs:hHandle; hEvent
0x180001c2a  mov     [rsp+68h+arg_0], rbp
0x180001c2f  mov     [rsp+68h+var_28], r14
0x180001c34  mov     cs:dword_180026978, 1
0x180001c3e  mov     cs:dword_180026974, eax
0x180001c44  call    cs:__imp_ResetEvent
0x180001c4a  mov     r14, [rbx+r15+10h]
0x180001c4f  lea     rcx, TimerThreadCritSec; lpCriticalSection
0x180001c56  mov     rbp, [rbx+r15+8]
0x180001c5b  call    cs:__imp_LeaveCriticalSection
0x180001c61  test    rbp, rbp
0x180001c64  jz      short loc_180001C7E
0x180001c66  xor     r9d, r9d
0x180001c69  mov     qword ptr [rsp+68h+WakeTimer], r12
0x180001c6e  mov     r8, r14
0x180001c71  xor     edx, edx
0x180001c73  mov     rcx, rdi
0x180001c76  mov     rax, rbp
0x180001c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c7e  lea     rcx, TimerThreadCritSec; lpCriticalSection
0x180001c85  call    cs:__imp_EnterCriticalSection
0x180001c8b  mov     rcx, cs:hHandle; hEvent
0x180001c92  mov     cs:dword_180026978, r12d
0x180001c99  call    cs:__imp_SetEvent
0x180001c9f  mov     r14, [rsp+68h+var_28]
0x180001ca4  mov     rbp, [rsp+68h+arg_0]
0x180001ca9  mov     eax, [rbx+r15+18h]
0x180001cae  cmp     edi, eax
0x180001cb0  jnz     loc_180001D81
0x180001cb6  mov     eax, [rbx+r15+1Ch]
0x180001cbb  test    al, 1
0x180001cbd  jz      loc_180001DA0
0x180001cc3  mov     eax, [rbx+r15]
0x180001cc7  mov     rcx, [rbx+r15+30h]
0x180001ccc  imul    rax, 2710h
0x180001cd3  mov     qword ptr [rsp+68h+DueTime], r12
0x180001cdb  add     rcx, rax
0x180001cde  mov     [rbx+r15+30h], rcx
0x180001ce3  mov     eax, [rbx+r15+1Ch]
0x180001ce8  test    al, 1
0x180001cea  jz      loc_180001DDF
0x180001cf0  mov     ecx, ds:7FFE000Ch
0x180001cf7  mov     r8d, ds:7FFE0008h
0x180001cff  mov     eax, ds:7FFE0010h
0x180001d06  cmp     ecx, eax
0x180001d08  jnz     short loc_180001CF0
0x180001d0a  mov     eax, r8d
0x180001d0d  mov     edx, ecx
0x180001d0f  shl     rdx, 20h
0x180001d13  or      rdx, rax
0x180001d16  mov     rax, [rbx+r15+30h]
0x180001d1b  sub     rdx, rax
0x180001d1e  test    rdx, rdx
0x180001d21  mov     rax, r12
0x180001d24  cmovle  rax, rdx
0x180001d28  mov     qword ptr [rsp+68h+DueTime], rax
0x180001d30  mov     rax, [rbx+r15+20h]
0x180001d35  test    rax, rax
0x180001d38  jz      loc_180001DFF
0x180001d3e  mov     r9d, [rbx+r15+18h]; TimerContext
0x180001d43  lea     rdx, [rsp+68h+DueTime]; DueTime
0x180001d4b  mov     rcx, [rbx+r15+20h]; TimerHandle
0x180001d50  xor     r8d, r8d; TimerApcRoutine
0x180001d53  mov     [rsp+68h+PreviousState], r12; PreviousState
0x180001d58  mov     [rsp+68h+Period], r12d; Period
0x180001d5d  mov     [rsp+68h+WakeTimer], r12b; WakeTimer
0x180001d62  call    cs:__imp_NtSetTimer
0x180001d68  test    eax, eax
0x180001d6a  jns     short loc_180001D81
0x180001d6c  mov     eax, [rbx+r15+4]
0x180001d71  mov     [rbx+r15+18h], r12d
0x180001d76  mov     ecx, [rbx+r15+4]; uPeriod
0x180001d7b  call    cs:__imp_timeEndPeriod
0x180001d81  mov     r12, [rsp+68h+arg_18]
0x180001d89  lea     rcx, TimerThreadCritSec
0x180001d90  add     rsp, 48h
0x180001d94  pop     r15
0x180001d96  pop     rdi
0x180001d97  pop     rsi
0x180001d98  pop     rbx
0x180001d99  jmp     cs:__imp_LeaveCriticalSection
0x180001da0  mov     ecx, [rbx+r15+4]; uPeriod
0x180001da5  mov     [rbx+r15+18h], r12d
0x180001daa  call    cs:__imp_timeEndPeriod
0x180001db0  mov     rcx, cs:Handle; EventHandle
0x180001db7  xor     edx, edx; PreviousState
0x180001db9  call    cs:__imp_NtSetEvent
0x180001dbf  jmp     short loc_180001D81
0x180001dc1  cmp     eax, 10h
0x180001dc4  jz      short loc_180001DEF
0x180001dc6  cmp     eax, 20h ; ' '
0x180001dc9  jnz     loc_180001CA9
0x180001dcf  mov     rcx, [rbx+r15+8]; hEvent
0x180001dd4  call    cs:__imp_PulseEvent
0x180001dda  jmp     loc_180001CA9
0x180001ddf  mov     eax, [rbx+r15]
0x180001de3  imul    rdx, rax, 0FFFFFFFFFFFFD8F0h
0x180001dea  jmp     loc_180001D1E
0x180001def  mov     rcx, [rbx+r15+8]; hEvent
0x180001df4  call    cs:__imp_SetEvent
0x180001dfa  jmp     loc_180001CA9
0x180001dff  xor     r9d, r9d; TimerType
0x180001e02  mov     [rsp+68h+TimerHandle], r12
0x180001e07  xor     r8d, r8d; ObjectAttributes
0x180001e0a  lea     rcx, [rsp+68h+TimerHandle]; TimerHandle
0x180001e0f  mov     edx, 1F0003h; DesiredAccess
0x180001e14  call    cs:__imp_NtCreateTimer
0x180001e1a  test    eax, eax
0x180001e1c  js      loc_180001D6C
0x180001e22  mov     rax, [rsp+68h+TimerHandle]
0x180001e27  mov     [rbx+r15+20h], rax
0x180001e2c  jmp     loc_180001D3E
0x180001e31  call    ReadInterruptTick
0x180001e36  mov     rcx, [rbx+r15+30h]
0x180001e3b  sub     rcx, rax
0x180001e3e  test    rcx, rcx
0x180001e41  jle     loc_180001C0B
0x180001e47  nop     word ptr [rax+rax+00000000h]
0x180001e50  mov     ecx, 1; dwMilliseconds
0x180001e55  call    cs:__imp_Sleep
0x180001e5b  call    ReadInterruptTick
0x180001e60  mov     rcx, [rbx+r15+30h]
0x180001e65  sub     rcx, rax
0x180001e68  test    rcx, rcx
0x180001e6b  jg      short loc_180001E50
0x180001e6d  jmp     loc_180001C0B
```
