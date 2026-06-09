# joyConfigChanged

- ea: `0x18000e680`
- end: `0x18000e6cc`
- name: `joyConfigChanged`
- size: `76`
- prototype: `MMRESULT __stdcall(DWORD dwFlags)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000e658`
- `0x18000e680`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e696`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e696`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e6a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e6a8`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x18000e6bf`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x18000e6bf`

## pseudocode

```c
MMRESULT __stdcall joyConfigChanged(DWORD dwFlags)
{
  if ( dwFlags )
    return 165;
  EnterCriticalSection(&joyCritSec);
  joyCloseAll();
  LeaveCriticalSection(&joyCritSec);
  PostMessageW(HWND_BROADCAST, Msg, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x18000e680  sub     rsp, 28h
0x18000e684  test    ecx, ecx
0x18000e686  jz      short loc_18000E68F
0x18000e688  mov     eax, 0A5h
0x18000e68d  jmp     short loc_18000E6C7
0x18000e68f  lea     rcx, joyCritSec; lpCriticalSection
0x18000e696  call    cs:__imp_EnterCriticalSection
0x18000e69c  call    joyCloseAll
0x18000e6a1  lea     rcx, joyCritSec; lpCriticalSection
0x18000e6a8  call    cs:__imp_LeaveCriticalSection
0x18000e6ae  mov     edx, cs:Msg; Msg
0x18000e6b4  xor     r9d, r9d; lParam
0x18000e6b7  xor     r8d, r8d; wParam
0x18000e6ba  mov     ecx, 0FFFFh; hWnd
0x18000e6bf  call    cs:__imp_PostMessageW
0x18000e6c5  xor     eax, eax
0x18000e6c7  add     rsp, 28h
0x18000e6cb  retn
```
