# ScWaitForEvent(ushort const *)

- ea: `0x14007c868`
- end: `0x14007c918`
- name: `?ScWaitForEvent@@YAXPEBG@Z`
- size: `176`
- prototype: `void __fastcall(LPCWSTR lpName)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140035120`
- `0x14007c920`

## callees

- `0x140003e54`
- `0x14007c868`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14007c8a6`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14007c8a6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14007c8fe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14007c8fe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14007c881`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14007c881`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007c88f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007c8cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007c88f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007c8cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007c907`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007c907`

## pseudocode

```c
void __fastcall ScWaitForEvent(LPCWSTR lpName)
{
  HANDLE EventW; // rbx
  char LastError; // al

  EventW = CreateEventW(0, 1, 0, lpName);
  if ( EventW || GetLastError() == 183 && (EventW = OpenEventW(0x100000u, 0, lpName)) != 0 )
  {
    WaitForSingleObject(EventW, 0xFFFFFFFF);
    CloseHandle(EventW);
  }
  else if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
         && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_Sd(
      WPP_GLOBAL_Control->StubInfo,
      38,
      (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
      (_DWORD)lpName,
      LastError);
  }
}

```

## disassembly

```asm
0x14007c868  mov     [rsp+arg_0], rbx
0x14007c86d  push    rdi
0x14007c86e  sub     rsp, 30h
0x14007c872  xor     r8d, r8d; bInitialState
0x14007c875  mov     rdi, rcx
0x14007c878  mov     r9, rcx; lpName
0x14007c87b  xor     ecx, ecx; lpEventAttributes
0x14007c87d  lea     edx, [r8+1]; bManualReset
0x14007c881  call    cs:__imp_CreateEventW
0x14007c887  mov     rbx, rax
0x14007c88a  test    rax, rax
0x14007c88d  jnz     short loc_14007C8F8
0x14007c88f  call    cs:__imp_GetLastError
0x14007c895  cmp     eax, 0B7h
0x14007c89a  jnz     short loc_14007C8B4
0x14007c89c  mov     r8, rdi; lpName
0x14007c89f  xor     edx, edx; bInheritHandle
0x14007c8a1  mov     ecx, 100000h; dwDesiredAccess
0x14007c8a6  call    cs:__imp_OpenEventW
0x14007c8ac  mov     rbx, rax
0x14007c8af  test    rax, rax
0x14007c8b2  jnz     short loc_14007C8F8
0x14007c8b4  mov     rax, cs:WPP_GLOBAL_Control
0x14007c8bb  lea     rcx, WPP_GLOBAL_Control
0x14007c8c2  cmp     rax, rcx
0x14007c8c5  jz      short loc_14007C90D
0x14007c8c7  test    byte ptr [rax+1Ch], 1
0x14007c8cb  jz      short loc_14007C90D
0x14007c8cd  call    cs:__imp_GetLastError
0x14007c8d3  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c8da  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14007c8e1  mov     edx, 26h ; '&'
0x14007c8e6  mov     [rsp+38h+var_18], eax
0x14007c8ea  mov     r9, rdi
0x14007c8ed  mov     rcx, [rcx+10h]
0x14007c8f1  call    WPP_SF_Sd
0x14007c8f6  jmp     short loc_14007C90D
0x14007c8f8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14007c8fb  mov     rcx, rbx; hHandle
0x14007c8fe  call    cs:__imp_WaitForSingleObject
0x14007c904  mov     rcx, rbx; hObject
0x14007c907  call    cs:__imp_CloseHandle
0x14007c90d  mov     rbx, [rsp+38h+arg_0]
0x14007c912  add     rsp, 30h
0x14007c916  pop     rdi
0x14007c917  retn
```
