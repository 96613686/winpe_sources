# LaunchUmfdHostWithVirtualAccountAsync(void)

- ea: `0x140095e2c`
- end: `0x140095ec7`
- name: `?LaunchUmfdHostWithVirtualAccountAsync@@YA_NXZ`
- size: `155`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400957a4`

## callees

- `0x14004dba8`
- `0x140095e2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140095e52`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140095e52`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140095e93`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140095e93`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140095e7f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140095e7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140095e9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140095eaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140095e9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140095eaa`

## pseudocode

```c
char LaunchUmfdHostWithVirtualAccountAsync(void)
{
  char v0; // di
  HANDLE EventW; // rax
  void *v2; // rbx
  HANDLE Thread; // rsi

  if ( !OneTimeInitialize() )
    return 0;
  v0 = 1;
  EventW = CreateEventW(0, 1, 0, 0);
  v2 = EventW;
  if ( !EventW )
    return 0;
  Thread = CreateThread(0, 0, LaunchUmfdHostWithVirtualAccountThreadProc, EventW, 0, 0);
  if ( Thread )
  {
    WaitForSingleObject(v2, 0xFFFFFFFF);
    CloseHandle(Thread);
  }
  else
  {
    v0 = 0;
  }
  CloseHandle(v2);
  return v0;
}

```

## disassembly

```asm
0x140095e2c  mov     [rsp+arg_0], rbx
0x140095e31  mov     [rsp+arg_8], rsi
0x140095e36  push    rdi
0x140095e37  sub     rsp, 30h
0x140095e3b  call    ?OneTimeInitialize@@YA_NXZ; OneTimeInitialize(void)
0x140095e40  test    al, al
0x140095e42  jz      short loc_140095EB5
0x140095e44  xor     r9d, r9d; lpName
0x140095e47  xor     r8d, r8d; bInitialState
0x140095e4a  xor     ecx, ecx; lpEventAttributes
0x140095e4c  lea     edi, [r9+1]
0x140095e50  mov     edx, edi; bManualReset
0x140095e52  call    cs:__imp_CreateEventW
0x140095e58  mov     rbx, rax
0x140095e5b  test    rax, rax
0x140095e5e  jz      short loc_140095EB5
0x140095e60  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x140095e69  lea     r8, ?LaunchUmfdHostWithVirtualAccountThreadProc@@YAKPEAX@Z; lpStartAddress
0x140095e70  mov     r9, rax; lpParameter
0x140095e73  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x140095e7b  xor     edx, edx; dwStackSize
0x140095e7d  xor     ecx, ecx; lpThreadAttributes
0x140095e7f  call    cs:__imp_CreateThread
0x140095e85  mov     rsi, rax
0x140095e88  test    rax, rax
0x140095e8b  jz      short loc_140095EA4
0x140095e8d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140095e90  mov     rcx, rbx; hHandle
0x140095e93  call    cs:__imp_WaitForSingleObject
0x140095e99  mov     rcx, rsi; hObject
0x140095e9c  call    cs:__imp_CloseHandle
0x140095ea2  jmp     short loc_140095EA7
0x140095ea4  xor     dil, dil
0x140095ea7  mov     rcx, rbx; hObject
0x140095eaa  call    cs:__imp_CloseHandle
0x140095eb0  mov     al, dil
0x140095eb3  jmp     short loc_140095EB7
0x140095eb5  xor     al, al
0x140095eb7  mov     rbx, [rsp+38h+arg_0]
0x140095ebc  mov     rsi, [rsp+38h+arg_8]
0x140095ec1  add     rsp, 30h
0x140095ec5  pop     rdi
0x140095ec6  retn
```
