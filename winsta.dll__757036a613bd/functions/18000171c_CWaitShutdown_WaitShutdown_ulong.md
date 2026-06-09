# CWaitShutdown::WaitShutdown(ulong)

- ea: `0x18000171c`
- end: `0x180001805`
- name: `?WaitShutdown@CWaitShutdown@@QEAAJK@Z`
- size: `233`
- prototype: `__int64 __fastcall(PVOID Context, DWORD dwMilliseconds)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180001640`

## callees

- `0x18000171c`
- `0x180001b68`
- `0x1800023a0`
- `0x180007890`
- `0x180013088`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001760`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800017f3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800017f3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000174e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000174e`

## pseudocode

```c
__int64 __fastcall CWaitShutdown::WaitShutdown(PVOID Context, DWORD dwMilliseconds)
{
  bool v2; // zf
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v7; // ebx
  bool v8; // cc
  int started; // eax
  int v11; // eax
  int v12; // [rsp+30h] [rbp+8h] BYREF

  v2 = *((_QWORD *)Context + 199) == 0;
  v12 = 0;
  if ( !v2 || (EventW = CreateEventW(0, 1, 0, 0), (*((_QWORD *)Context + 199) = EventW) != 0) )
  {
    started = CWaitItem::StartWait(Context, -1, 0x90u);
    v7 = started;
    if ( started < 0 )
    {
      _DbgPrintMessage(8, "StartWait failed: 0x%x in %s", (unsigned int)started, "CWaitShutdown::WaitShutdown");
      goto LABEL_6;
    }
    v11 = CWaitShutdown::AreSessionsDrained((CWaitShutdown *)Context, &v12);
    v7 = v11;
    if ( v11 < 0 )
    {
      _DbgPrintMessage(8, "AreSessionsDrained failed: 0x%x in %s", (unsigned int)v11, "CWaitShutdown::WaitShutdown");
      goto LABEL_6;
    }
    if ( v12
      || (LastError = WaitForSingleObject(*((HANDLE *)Context + 199), dwMilliseconds),
          v7 = LastError,
          v8 = LastError <= 0,
          !LastError) )
    {
      v7 = 0;
      goto LABEL_6;
    }
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    v8 = LastError <= 0;
  }
  if ( !v8 )
    v7 = (unsigned __int16)LastError | 0x80070000;
LABEL_6:
  CWaitItem::StopWait((CWaitItem *)Context);
  return v7;
}

```

## disassembly

```asm
0x18000171c  mov     [rsp+arg_8], rbx
0x180001721  mov     [rsp+arg_10], rsi
0x180001726  push    rdi
0x180001727  sub     rsp, 20h
0x18000172b  cmp     qword ptr [rcx+638h], 0
0x180001733  mov     esi, edx
0x180001735  mov     rdi, rcx
0x180001738  mov     [rsp+28h+arg_0], 0
0x180001740  jnz     short loc_18000178F
0x180001742  xor     r9d, r9d; lpName
0x180001745  xor     r8d, r8d; bInitialState
0x180001748  xor     ecx, ecx; lpEventAttributes
0x18000174a  lea     edx, [r9+1]; bManualReset
0x18000174e  call    cs:__imp_CreateEventW
0x180001754  mov     [rdi+638h], rax
0x18000175b  test    rax, rax
0x18000175e  jnz     short loc_18000178F
0x180001760  call    cs:__imp_GetLastError
0x180001766  mov     ebx, eax
0x180001768  test    eax, eax
0x18000176a  jle     short loc_180001775
0x18000176c  movzx   ebx, ax
0x18000176f  or      ebx, 80070000h
0x180001775  mov     rcx, rdi; this
0x180001778  call    ?StopWait@CWaitItem@@QEAAJXZ; CWaitItem::StopWait(void)
0x18000177d  mov     rsi, [rsp+28h+arg_10]
0x180001782  mov     eax, ebx
0x180001784  mov     rbx, [rsp+28h+arg_8]
0x180001789  add     rsp, 20h
0x18000178d  pop     rdi
0x18000178e  retn
0x18000178f  mov     r8d, 90h; unsigned int
0x180001795  or      edx, 0FFFFFFFFh; int
0x180001798  mov     rcx, rdi; Context
0x18000179b  call    ?StartWait@CWaitItem@@QEAAJJK@Z; CWaitItem::StartWait(long,ulong)
0x1800017a0  mov     ebx, eax
0x1800017a2  test    eax, eax
0x1800017a4  jns     short loc_1800017C3
0x1800017a6  lea     rdx, aStartwaitFaile; "StartWait failed: 0x%x in %s"
0x1800017ad  mov     r8d, eax
0x1800017b0  lea     r9, aCwaitshutdownW; "CWaitShutdown::WaitShutdown"
0x1800017b7  mov     ecx, 8; int
0x1800017bc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800017c1  jmp     short loc_180001775
0x1800017c3  lea     rdx, [rsp+28h+arg_0]; int *
0x1800017c8  mov     rcx, rdi; this
0x1800017cb  call    ?AreSessionsDrained@CWaitShutdown@@AEAAJPEAH@Z; CWaitShutdown::AreSessionsDrained(int *)
0x1800017d0  mov     ebx, eax
0x1800017d2  test    eax, eax
0x1800017d4  jns     short loc_1800017DF
0x1800017d6  lea     rdx, aAresessionsdra; "AreSessionsDrained failed: 0x%x in %s"
0x1800017dd  jmp     short loc_1800017AD
0x1800017df  cmp     [rsp+28h+arg_0], 0
0x1800017e4  jz      short loc_1800017EA
0x1800017e6  xor     ebx, ebx
0x1800017e8  jmp     short loc_180001775
0x1800017ea  mov     rcx, [rdi+638h]; hHandle
0x1800017f1  mov     edx, esi; dwMilliseconds
0x1800017f3  call    cs:__imp_WaitForSingleObject
0x1800017f9  mov     ebx, eax
0x1800017fb  test    eax, eax
0x1800017fd  jnz     loc_18000176A
0x180001803  jmp     short loc_1800017E6
```
