# ShutdownMgr::Initialize(void)

- ea: `0x140006fcc`
- end: `0x14000703d`
- name: `?Initialize@ShutdownMgr@@SAJXZ`
- size: `113`
- prototype: `signed int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001968`

## callees

- `0x140006fcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007022`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006fed`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006fed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007007`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007007`

## pseudocode

```c
signed int ShutdownMgr::Initialize(void)
{
  char *v0; // rcx
  signed int result; // eax

  _InterlockedExchange((volatile __int32 *)&ShutdownMgr::s_sync, 1);
  _InterlockedExchange(&dword_1400159E4, 1);
  v0 = (char *)_InterlockedExchange64(&ShutdownMgr::s_hEvent, (__int64)CreateEventW(0, 1, 0, 0));
  if ( (unsigned __int64)(v0 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v0);
  if ( _InterlockedCompareExchange64(&ShutdownMgr::s_hEvent, -1, -1) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140006fcc  sub     rsp, 28h
0x140006fd0  mov     edx, 1; bManualReset
0x140006fd5  xor     r9d, r9d; lpName
0x140006fd8  mov     ecx, edx
0x140006fda  mov     eax, edx
0x140006fdc  xchg    eax, cs:?s_sync@ShutdownMgr@@0USync@1@A; ShutdownMgr::Sync ShutdownMgr::s_sync
0x140006fe2  xchg    ecx, cs:dword_1400159E4
0x140006fe8  xor     ecx, ecx; lpEventAttributes
0x140006fea  xor     r8d, r8d; bInitialState
0x140006fed  call    cs:__imp_CreateEventW
0x140006ff3  mov     rcx, rax
0x140006ff6  xchg    rcx, cs:?s_hEvent@ShutdownMgr@@0VInterlockedAutoHandle@@A; hObject
0x140006ffd  lea     rax, [rcx-1]
0x140007001  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140007005  ja      short loc_14000700D
0x140007007  call    cs:__imp_CloseHandle
0x14000700d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140007011  mov     rax, rcx
0x140007014  lock cmpxchg cs:?s_hEvent@ShutdownMgr@@0VInterlockedAutoHandle@@A, rcx; InterlockedAutoHandle ShutdownMgr::s_hEvent
0x14000701d  test    rax, rax
0x140007020  jnz     short loc_140007036
0x140007022  call    cs:__imp_GetLastError
0x140007028  test    eax, eax
0x14000702a  jle     short loc_140007038
0x14000702c  movzx   eax, ax
0x14000702f  or      eax, 80070000h
0x140007034  jmp     short loc_140007038
0x140007036  xor     eax, eax
0x140007038  add     rsp, 28h
0x14000703c  retn
```
