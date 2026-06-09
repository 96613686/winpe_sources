# Windows::Internal::Events::WatchdogEventCallMonitor::Initialize(void)

- ea: `0x180071f50`
- end: `0x180071ffb`
- name: `?Initialize@WatchdogEventCallMonitor@Events@Internal@Windows@@SAJXZ`
- size: `171`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180072004`

## callees

- `0x180071f50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180071f82`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180071f82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071f94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071f94`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180071fee`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180071fee`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180071fca`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180071fca`

## pseudocode

```c
signed int Windows::Internal::Events::WatchdogEventCallMonitor::Initialize(void)
{
  signed int result; // eax

  xmmword_1801485D0 = 0u;
  qword_1801485E8 = 0;
  hEvent = CreateEventExW(0, 0, 0, 0x110002u);
  if ( hEvent
    && (Windows::Internal::Events::WatchdogEventCallMonitor::s_State = CreateThread(
                                                                         0,
                                                                         0,
                                                                         Windows::Internal::Events::WatchdogEventCallMonitor::RunThread,
                                                                         0,
                                                                         4u,
                                                                         &ThreadId)) != 0 )
  {
    _InterlockedExchange(&dword_1801485F8, 1);
    ResumeThread(Windows::Internal::Events::WatchdogEventCallMonitor::s_State);
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180071f50  sub     rsp, 38h
0x180071f54  mov     r9d, 110002h; dwDesiredAccess
0x180071f5a  mov     qword ptr cs:xmmword_1801485D0+8, 0
0x180071f65  xor     r8d, r8d; dwFlags
0x180071f68  mov     qword ptr cs:xmmword_1801485D0, 0
0x180071f73  xor     edx, edx; lpName
0x180071f75  mov     cs:qword_1801485E8, 0
0x180071f80  xor     ecx, ecx; lpEventAttributes
0x180071f82  call    cs:__imp_CreateEventExW
0x180071f88  mov     cs:hEvent, rax
0x180071f8f  test    rax, rax
0x180071f92  jnz     short loc_180071FA8
0x180071f94  call    cs:__imp_GetLastError
0x180071f9a  test    eax, eax
0x180071f9c  jle     short loc_180071FF6
0x180071f9e  movzx   eax, ax
0x180071fa1  or      eax, 80070000h
0x180071fa6  jmp     short loc_180071FF6
0x180071fa8  lea     rax, ThreadId
0x180071faf  xor     r9d, r9d; lpParameter
0x180071fb2  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180071fb7  lea     r8, ?RunThread@WatchdogEventCallMonitor@Events@Internal@Windows@@SAKPEAX@Z; lpStartAddress
0x180071fbe  xor     edx, edx; dwStackSize
0x180071fc0  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180071fc8  xor     ecx, ecx; lpThreadAttributes
0x180071fca  call    cs:__imp_CreateThread
0x180071fd0  mov     cs:?s_State@WatchdogEventCallMonitor@Events@Internal@Windows@@1UProcessState@1234@A, rax; Windows::Internal::Events::WatchdogEventCallMonitor::ProcessState Windows::Internal::Events::WatchdogEventCallMonitor::s_State
0x180071fd7  test    rax, rax
0x180071fda  jz      short loc_180071F94
0x180071fdc  mov     eax, 1
0x180071fe1  xchg    eax, cs:dword_1801485F8
0x180071fe7  mov     rcx, cs:?s_State@WatchdogEventCallMonitor@Events@Internal@Windows@@1UProcessState@1234@A; hThread
0x180071fee  call    cs:__imp_ResumeThread
0x180071ff4  xor     eax, eax
0x180071ff6  add     rsp, 38h
0x180071ffa  retn
```
