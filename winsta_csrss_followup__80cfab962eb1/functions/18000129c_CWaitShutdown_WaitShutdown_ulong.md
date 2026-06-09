# CWaitShutdown::WaitShutdown(ulong)

- ea: `0x18000129c`
- end: `0x180001398`
- name: `?WaitShutdown@CWaitShutdown@@QEAAJK@Z`
- size: `252`
- prototype: `__int64 __fastcall(PVOID Context, DWORD dwMilliseconds)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800011c0`

## callees

- `0x18000129c`
- `0x180005b40`
- `0x18000b8d4`
- `0x18000c180`
- `0x180013fcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800012e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800012e6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001380`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001380`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800012ce`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800012ce`

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
0x18000129c  mov     [rsp+arg_8], rbx
0x1800012a1  mov     [rsp+arg_10], rsi
0x1800012a6  push    rdi
0x1800012a7  sub     rsp, 20h
0x1800012ab  cmp     qword ptr [rcx+638h], 0
0x1800012b3  mov     esi, edx
0x1800012b5  mov     rdi, rcx
0x1800012b8  mov     [rsp+28h+arg_0], 0
0x1800012c0  jnz     short loc_18000131C
0x1800012c2  xor     r9d, r9d; lpName
0x1800012c5  xor     r8d, r8d; bInitialState
0x1800012c8  xor     ecx, ecx; lpEventAttributes
0x1800012ca  lea     edx, [r9+1]; bManualReset
0x1800012ce  call    cs:__imp_CreateEventW
0x1800012d5  nop     dword ptr [rax+rax+00h]
0x1800012da  mov     [rdi+638h], rax
0x1800012e1  test    rax, rax
0x1800012e4  jnz     short loc_18000131C
0x1800012e6  call    cs:__imp_GetLastError
0x1800012ed  nop     dword ptr [rax+rax+00h]
0x1800012f2  mov     ebx, eax
0x1800012f4  test    eax, eax
0x1800012f6  jle     short loc_180001301
0x1800012f8  movzx   ebx, ax
0x1800012fb  or      ebx, 80070000h
0x180001301  mov     rcx, rdi; this
0x180001304  call    ?StopWait@CWaitItem@@QEAAJXZ; CWaitItem::StopWait(void)
0x180001309  mov     rsi, [rsp+28h+arg_10]
0x18000130e  mov     eax, ebx
0x180001310  mov     rbx, [rsp+28h+arg_8]
0x180001315  add     rsp, 20h
0x180001319  pop     rdi
0x18000131a  retn
0x18000131c  mov     r8d, 90h; unsigned int
0x180001322  or      edx, 0FFFFFFFFh; int
0x180001325  mov     rcx, rdi; Context
0x180001328  call    ?StartWait@CWaitItem@@QEAAJJK@Z; CWaitItem::StartWait(long,ulong)
0x18000132d  mov     ebx, eax
0x18000132f  test    eax, eax
0x180001331  jns     short loc_180001350
0x180001333  lea     rdx, aStartwaitFaile; "StartWait failed: 0x%x in %s"
0x18000133a  mov     r8d, eax
0x18000133d  lea     r9, aCwaitshutdownW; "CWaitShutdown::WaitShutdown"
0x180001344  mov     ecx, 8; int
0x180001349  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000134e  jmp     short loc_180001301
0x180001350  lea     rdx, [rsp+28h+arg_0]; int *
0x180001355  mov     rcx, rdi; this
0x180001358  call    ?AreSessionsDrained@CWaitShutdown@@AEAAJPEAH@Z; CWaitShutdown::AreSessionsDrained(int *)
0x18000135d  mov     ebx, eax
0x18000135f  test    eax, eax
0x180001361  jns     short loc_18000136C
0x180001363  lea     rdx, aAresessionsdra; "AreSessionsDrained failed: 0x%x in %s"
0x18000136a  jmp     short loc_18000133A
0x18000136c  cmp     [rsp+28h+arg_0], 0
0x180001371  jz      short loc_180001377
0x180001373  xor     ebx, ebx
0x180001375  jmp     short loc_180001301
0x180001377  mov     rcx, [rdi+638h]; hHandle
0x18000137e  mov     edx, esi; dwMilliseconds
0x180001380  call    cs:__imp_WaitForSingleObject
0x180001387  nop     dword ptr [rax+rax+00h]
0x18000138c  mov     ebx, eax
0x18000138e  test    eax, eax
0x180001390  jnz     loc_1800012F6
0x180001396  jmp     short loc_180001373
```
