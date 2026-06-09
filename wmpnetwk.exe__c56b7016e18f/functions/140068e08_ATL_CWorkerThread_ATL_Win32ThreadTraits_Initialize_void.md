# ATL::CWorkerThread<ATL::Win32ThreadTraits>::Initialize(void)

- ea: `0x140068e08`
- end: `0x140068f67`
- name: `?Initialize@?$CWorkerThread@VWin32ThreadTraits@ATL@@@ATL@@QEAAJXZ`
- size: `351`
- prototype: `__int64 __fastcall(LPVOID lpParameter)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140068c18`

## callees

- `0x1400350c0`
- `0x14004bb5c`
- `0x140067fcc`
- `0x140068e08`
- `0x140069a84`
- `0x140069bf4`

## import_xrefs

- `KERNEL32!CreateThread` at `0x140068f2b`
- `KERNEL32!CreateThread` at `0x140068f2b`
- `KERNEL32!WaitForSingleObject` at `0x140068f44`
- `KERNEL32!WaitForSingleObject` at `0x140068f44`
- `KERNEL32!CreateEventW` at `0x140068e46`
- `KERNEL32!CreateEventW` at `0x140068e72`
- `KERNEL32!CreateEventW` at `0x140068ed7`
- `KERNEL32!CreateEventW` at `0x140068e46`
- `KERNEL32!CreateEventW` at `0x140068e72`
- `KERNEL32!CreateEventW` at `0x140068ed7`
- `KERNEL32!CloseHandle` at `0x140068eb8`
- `KERNEL32!CloseHandle` at `0x140068efc`
- `KERNEL32!CloseHandle` at `0x140068eb8`
- `KERNEL32!CloseHandle` at `0x140068efc`

## pseudocode

```c
__int64 __fastcall ATL::CWorkerThread<ATL::Win32ThreadTraits>::Initialize(char *lpParameter)
{
  __int64 result; // rax
  HANDLE EventW; // rax
  HANDLE v4; // rax
  void *v5; // rdi
  int Error; // edi
  int v7; // eax
  int v8; // esi
  HANDLE v9; // rax
  void *v10; // rsi
  HANDLE Thread; // rax

  if ( *((_QWORD *)lpParameter + 2) )
    return 2147549183LL;
  result = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(lpParameter + 56));
  if ( (int)result >= 0 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)lpParameter + 13) = EventW;
    if ( !EventW )
    {
      ATL::CComSafeDeleteCriticalSection::Term((ATL::CComSafeDeleteCriticalSection *)(lpParameter + 56));
      return ATL::AtlHresultFromLastError();
    }
    v4 = CreateEventW(0, 0, 0, 0);
    v5 = v4;
    if ( v4 )
    {
      v8 = ATL::CWorkerThread<ATL::Win32ThreadTraits>::AddHandle((__int64)lpParameter, (__int64)v4, 0);
      if ( v8 < 0 )
      {
        CloseHandle(v5);
        ATL::CWorkerThread<ATL::Win32ThreadTraits>::Shutdown(lpParameter);
        return (unsigned int)v8;
      }
      v9 = CreateEventW(0, 0, 0, 0);
      v10 = v9;
      if ( v9 )
      {
        Error = ATL::CWorkerThread<ATL::Win32ThreadTraits>::AddHandle((__int64)lpParameter, (__int64)v9, 0);
        if ( Error < 0 )
        {
          CloseHandle(v10);
          ATL::CWorkerThread<ATL::Win32ThreadTraits>::Shutdown(lpParameter);
          return (unsigned int)Error;
        }
        Thread = CreateThread(
                   0,
                   0,
                   (LPTHREAD_START_ROUTINE)ATL::CWorkerThread<ATL::Win32ThreadTraits>::_WorkerThreadProc,
                   lpParameter,
                   0,
                   (LPDWORD)lpParameter + 2);
        *(_QWORD *)lpParameter = Thread;
        if ( Thread )
        {
          if ( WaitForSingleObject(*((HANDLE *)lpParameter + 13), 0xFFFFFFFF) )
            return (unsigned int)ATL::AtlHresultFromLastError();
          return (unsigned int)Error;
        }
      }
    }
    Error = ATL::AtlHresultFromLastError();
    v7 = ATL::CWorkerThread<ATL::Win32ThreadTraits>::Shutdown(lpParameter);
    if ( v7 < 0 && Error >= 0 )
      return (unsigned int)v7;
    return (unsigned int)Error;
  }
  return result;
}

```

## disassembly

```asm
0x140068e08  mov     [rsp+arg_0], rbx
0x140068e0d  mov     [rsp+arg_8], rsi
0x140068e12  push    rdi
0x140068e13  sub     rsp, 30h
0x140068e17  cmp     qword ptr [rcx+10h], 0
0x140068e1c  mov     rbx, rcx
0x140068e1f  jz      short loc_140068E2B
0x140068e21  mov     eax, 8000FFFFh
0x140068e26  jmp     loc_140068F57
0x140068e2b  add     rcx, 38h ; '8'; this
0x140068e2f  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x140068e34  test    eax, eax
0x140068e36  js      loc_140068F57
0x140068e3c  xor     r9d, r9d; lpName
0x140068e3f  xor     r8d, r8d; bInitialState
0x140068e42  xor     edx, edx; bManualReset
0x140068e44  xor     ecx, ecx; lpEventAttributes
0x140068e46  call    cs:__imp_CreateEventW
0x140068e4c  mov     [rbx+68h], rax
0x140068e50  test    rax, rax
0x140068e53  jnz     short loc_140068E68
0x140068e55  lea     rcx, [rbx+38h]; this
0x140068e59  call    ?Term@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Term(void)
0x140068e5e  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140068e63  jmp     loc_140068F57
0x140068e68  xor     r9d, r9d; lpName
0x140068e6b  xor     r8d, r8d; bInitialState
0x140068e6e  xor     edx, edx; bManualReset
0x140068e70  xor     ecx, ecx; lpEventAttributes
0x140068e72  call    cs:__imp_CreateEventW
0x140068e78  mov     rdi, rax
0x140068e7b  test    rax, rax
0x140068e7e  jnz     short loc_140068EA1
0x140068e80  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140068e85  mov     rcx, rbx
0x140068e88  mov     edi, eax
0x140068e8a  call    ?Shutdown@?$CWorkerThread@VWin32ThreadTraits@ATL@@@ATL@@QEAAJK@Z; ATL::CWorkerThread<ATL::Win32ThreadTraits>::Shutdown(ulong)
0x140068e8f  test    eax, eax
0x140068e91  jns     loc_140068F55
0x140068e97  test    edi, edi
0x140068e99  cmovns  edi, eax
0x140068e9c  jmp     loc_140068F55
0x140068ea1  xor     r8d, r8d
0x140068ea4  mov     rdx, rdi
0x140068ea7  mov     rcx, rbx
0x140068eaa  call    ?AddHandle@?$CWorkerThread@VWin32ThreadTraits@ATL@@@ATL@@QEAAJPEAXPEAUIWorkerThreadClient@2@_K@Z; ATL::CWorkerThread<ATL::Win32ThreadTraits>::AddHandle(void *,ATL::IWorkerThreadClient *,unsigned __int64)
0x140068eaf  mov     esi, eax
0x140068eb1  test    eax, eax
0x140068eb3  jns     short loc_140068ECD
0x140068eb5  mov     rcx, rdi; hObject
0x140068eb8  call    cs:__imp_CloseHandle
0x140068ebe  mov     rcx, rbx
0x140068ec1  call    ?Shutdown@?$CWorkerThread@VWin32ThreadTraits@ATL@@@ATL@@QEAAJK@Z; ATL::CWorkerThread<ATL::Win32ThreadTraits>::Shutdown(ulong)
0x140068ec6  mov     eax, esi
0x140068ec8  jmp     loc_140068F57
0x140068ecd  xor     r9d, r9d; lpName
0x140068ed0  xor     r8d, r8d; bInitialState
0x140068ed3  xor     edx, edx; bManualReset
0x140068ed5  xor     ecx, ecx; lpEventAttributes
0x140068ed7  call    cs:__imp_CreateEventW
0x140068edd  mov     rsi, rax
0x140068ee0  test    rax, rax
0x140068ee3  jz      short loc_140068E80
0x140068ee5  xor     r8d, r8d
0x140068ee8  mov     rdx, rax
0x140068eeb  mov     rcx, rbx
0x140068eee  call    ?AddHandle@?$CWorkerThread@VWin32ThreadTraits@ATL@@@ATL@@QEAAJPEAXPEAUIWorkerThreadClient@2@_K@Z; ATL::CWorkerThread<ATL::Win32ThreadTraits>::AddHandle(void *,ATL::IWorkerThreadClient *,unsigned __int64)
0x140068ef3  mov     edi, eax
0x140068ef5  test    eax, eax
0x140068ef7  jns     short loc_140068F0C
0x140068ef9  mov     rcx, rsi; hObject
0x140068efc  call    cs:__imp_CloseHandle
0x140068f02  mov     rcx, rbx
0x140068f05  call    ?Shutdown@?$CWorkerThread@VWin32ThreadTraits@ATL@@@ATL@@QEAAJK@Z; ATL::CWorkerThread<ATL::Win32ThreadTraits>::Shutdown(ulong)
0x140068f0a  jmp     short loc_140068F55
0x140068f0c  lea     rax, [rbx+8]
0x140068f10  mov     r9, rbx; lpParameter
0x140068f13  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x140068f18  lea     r8, ?_WorkerThreadProc@?$CWorkerThread@VWin32ThreadTraits@ATL@@@ATL@@KAKPEAV12@@Z; lpStartAddress
0x140068f1f  xor     edx, edx; dwStackSize
0x140068f21  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x140068f29  xor     ecx, ecx; lpThreadAttributes
0x140068f2b  call    cs:__imp_CreateThread
0x140068f31  mov     [rbx], rax
0x140068f34  test    rax, rax
0x140068f37  jz      loc_140068E80
0x140068f3d  mov     rcx, [rbx+68h]; hHandle
0x140068f41  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140068f44  call    cs:__imp_WaitForSingleObject
0x140068f4a  test    eax, eax
0x140068f4c  jz      short loc_140068F55
0x140068f4e  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140068f53  mov     edi, eax
0x140068f55  mov     eax, edi
0x140068f57  mov     rbx, [rsp+38h+arg_0]
0x140068f5c  mov     rsi, [rsp+38h+arg_8]
0x140068f61  add     rsp, 30h
0x140068f65  pop     rdi
0x140068f66  retn
```
