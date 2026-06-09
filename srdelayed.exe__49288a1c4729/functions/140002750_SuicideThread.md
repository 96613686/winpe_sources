# SuicideThread

- ea: `0x140002750`
- end: `0x1400027ee`
- name: `SuicideThread`
- size: `158`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140002750`

## import_xrefs

- `ntdll!RtlExitUserProcess` at `0x1400027d1`
- `ntdll!RtlExitUserProcess` at `0x1400027d1`
- `ntdll!NtWaitForMultipleObjects` at `0x1400027a7`
- `ntdll!NtWaitForMultipleObjects` at `0x1400027a7`

## pseudocode

```c
__int64 SuicideThread()
{
  union _LARGE_INTEGER *Time; // rbx
  NTSTATUS v1; // eax
  HANDLE Object[3]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v4; // [rsp+58h] [rbp+10h] BYREF

  Object[0] = g_hExitEvent;
  Object[1] = g_hProgressEvent;
  v4 = 0;
  if ( g_fDebug )
  {
    Time = 0;
  }
  else
  {
    v4 = -600000000;
    Time = (union _LARGE_INTEGER *)&v4;
  }
  do
  {
    v1 = NtWaitForMultipleObjects(2u, Object, WaitAny, 0, Time);
    if ( !v1 )
    {
      g_ThreadStatus = 0;
      return (unsigned int)g_ThreadStatus;
    }
  }
  while ( v1 == 1 );
  if ( v1 == 258 )
  {
    RtlExitUserProcess(258);
    __debugbreak();
  }
  if ( v1 < 0 )
    g_ThreadStatus = v1;
  return (unsigned int)g_ThreadStatus;
}

```

## disassembly

```asm
0x140002750  push    rbx
0x140002752  sub     rsp, 40h
0x140002756  cmp     cs:g_fDebug, 0
0x14000275d  mov     rax, cs:g_hExitEvent
0x140002764  mov     [rsp+48h+Object], rax
0x140002769  mov     rax, cs:g_hProgressEvent
0x140002770  mov     [rsp+48h+var_10], rax
0x140002775  mov     [rsp+48h+arg_8], 0
0x14000277e  jz      short loc_140002784
0x140002780  xor     ebx, ebx
0x140002782  jmp     short loc_140002792
0x140002784  mov     [rsp+48h+arg_8], 0FFFFFFFFDC3CBA00h
0x14000278d  lea     rbx, [rsp+48h+arg_8]
0x140002792  xor     r9d, r9d; Alertable
0x140002795  mov     [rsp+48h+Time], rbx; Time
0x14000279a  lea     rdx, [rsp+48h+Object]; Object
0x14000279f  lea     r8d, [r9+1]; WaitType
0x1400027a3  lea     ecx, [r9+2]; Count
0x1400027a7  call    cs:__imp_NtWaitForMultipleObjects
0x1400027ad  mov     edx, eax
0x1400027af  test    eax, eax
0x1400027b1  jz      short loc_1400027D8
0x1400027b3  sub     edx, 1
0x1400027b6  jz      short loc_140002792
0x1400027b8  cmp     edx, 101h
0x1400027be  jz      short loc_1400027CC
0x1400027c0  test    eax, eax
0x1400027c2  jns     short loc_1400027E2
0x1400027c4  mov     cs:g_ThreadStatus, eax
0x1400027ca  jmp     short loc_1400027E2
0x1400027cc  mov     ecx, 102h
0x1400027d1  call    cs:__imp_RtlExitUserProcess
0x1400027d7  int     3; Trap to Debugger
0x1400027d8  mov     cs:g_ThreadStatus, 0
0x1400027e2  mov     eax, cs:g_ThreadStatus
0x1400027e8  add     rsp, 40h
0x1400027ec  pop     rbx
0x1400027ed  retn
```
