# WaitForLsa(void)

- ea: `0x14003ea80`
- end: `0x14003eb11`
- name: `?WaitForLsa@@YAJXZ`
- size: `145`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140095ed0`

## callees

- `0x14003ea80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14003eac3`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14003eac3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14003ea9a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14003ea9a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003eaf5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003eaf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003eaa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ead1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003eaa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ead1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003eafe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003eafe`

## pseudocode

```c
__int64 WaitForLsa(void)
{
  HANDLE EventW; // rdi
  signed int LastError; // eax
  unsigned int v2; // ebx

  EventW = CreateEventW(0, 1, 0, L"Global\\LSA_SUBSYSTEM_INITIALIZED");
  if ( EventW || GetLastError() != 183 || (EventW = OpenEventW(0x100000u, 0, L"Global\\LSA_SUBSYSTEM_INITIALIZED")) != 0 )
  {
    v2 = 0;
    if ( EventW )
    {
      WaitForSingleObject(EventW, 0xFFFFFFFF);
      CloseHandle(EventW);
    }
  }
  else
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v2;
}

```

## disassembly

```asm
0x14003ea80  mov     [rsp+arg_0], rbx
0x14003ea85  push    rdi
0x14003ea86  sub     rsp, 20h
0x14003ea8a  xor     r8d, r8d; bInitialState
0x14003ea8d  lea     r9, aGlobalLsaSubsy; "Global\\LSA_SUBSYSTEM_INITIALIZED"
0x14003ea94  xor     ecx, ecx; lpEventAttributes
0x14003ea96  lea     edx, [r8+1]; bManualReset
0x14003ea9a  call    cs:__imp_CreateEventW
0x14003eaa0  mov     rdi, rax
0x14003eaa3  test    rax, rax
0x14003eaa6  jnz     short loc_14003EAE8
0x14003eaa8  call    cs:__imp_GetLastError
0x14003eaae  cmp     eax, 0B7h
0x14003eab3  jnz     short loc_14003EAE8
0x14003eab5  lea     r8, aGlobalLsaSubsy; "Global\\LSA_SUBSYSTEM_INITIALIZED"
0x14003eabc  xor     edx, edx; bInheritHandle
0x14003eabe  mov     ecx, 100000h; dwDesiredAccess
0x14003eac3  call    cs:__imp_OpenEventW
0x14003eac9  mov     rdi, rax
0x14003eacc  test    rax, rax
0x14003eacf  jnz     short loc_14003EAE8
0x14003ead1  call    cs:__imp_GetLastError
0x14003ead7  mov     ebx, eax
0x14003ead9  test    eax, eax
0x14003eadb  jle     short loc_14003EB04
0x14003eadd  movzx   ebx, ax
0x14003eae0  or      ebx, 80070000h
0x14003eae6  jmp     short loc_14003EB04
0x14003eae8  xor     ebx, ebx
0x14003eaea  test    rdi, rdi
0x14003eaed  jz      short loc_14003EB04
0x14003eaef  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14003eaf2  mov     rcx, rdi; hHandle
0x14003eaf5  call    cs:__imp_WaitForSingleObject
0x14003eafb  mov     rcx, rdi; hObject
0x14003eafe  call    cs:__imp_CloseHandle
0x14003eb04  mov     eax, ebx
0x14003eb06  mov     rbx, [rsp+28h+arg_0]
0x14003eb0b  add     rsp, 20h
0x14003eb0f  pop     rdi
0x14003eb10  retn
```
