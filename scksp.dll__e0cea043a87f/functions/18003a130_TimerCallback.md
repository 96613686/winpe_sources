# TimerCallback

- ea: `0x18003a130`
- end: `0x18003a155`
- name: `TimerCallback`
- size: `37`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18003a130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18003a13c`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18003a13c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003a14a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003a14a`

## pseudocode

```c
void __fastcall TimerCallback(PTP_CALLBACK_INSTANCE Instance, const WCHAR *Context, PTP_TIMER Timer)
{
  HANDLE v3; // rax

  v3 = OpenEventW(2u, 0, Context);
  if ( v3 )
    SetEvent(v3);
}

```

## disassembly

```asm
0x18003a130  sub     rsp, 28h
0x18003a134  mov     r8, rdx; lpName
0x18003a137  xor     edx, edx; bInheritHandle
0x18003a139  lea     ecx, [rdx+2]; dwDesiredAccess
0x18003a13c  call    cs:__imp_OpenEventW
0x18003a142  test    rax, rax
0x18003a145  jz      short loc_18003A150
0x18003a147  mov     rcx, rax; hEvent
0x18003a14a  call    cs:__imp_SetEvent
0x18003a150  add     rsp, 28h
0x18003a154  retn
```
