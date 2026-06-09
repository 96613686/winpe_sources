# mmTaskCreate

- ea: `0x18001d190`
- end: `0x18001d294`
- name: `mmTaskCreate`
- size: `260`
- prototype: `UINT __stdcall(LPTASKCALLBACK lpfn, HANDLE *lph, DWORD_PTR dwInst)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x1800174ec`
- `0x18001d190`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001d213`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001d213`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d280`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d280`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d1b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d1b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d229`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d277`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d229`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d277`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001d1db`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001d1db`

## pseudocode

```c
UINT __stdcall mmTaskCreate(LPTASKCALLBACK lpfn, HANDLE *lph, DWORD_PTR dwInst)
{
  HANDLE *v6; // rax
  HANDLE *v7; // rbx
  HANDLE EventA; // rax
  HANDLE v9; // rsi
  HANDLE v10; // rax
  DWORD ThreadId; // [rsp+78h] [rbp+20h] BYREF

  ThreadId = 0;
  v6 = (HANDLE *)LocalAlloc(0x40u, 0x18u);
  v7 = v6;
  if ( !v6 )
    return 2;
  v6[1] = (HANDLE)dwInst;
  v6[2] = lpfn;
  if ( lph )
  {
    EventA = CreateEventA(0, 0, 0, 0);
    *v7 = EventA;
    if ( !EventA )
    {
LABEL_14:
      LocalFree(v7);
      return 2;
    }
  }
  v9 = *v7;
  v10 = CreateThread(0, 0x200u, mmStartTask, v7, 0, &ThreadId);
  if ( !v10 )
  {
    if ( lph )
      CloseHandle(*v7);
    goto LABEL_14;
  }
  if ( lph )
    *lph = v9;
  CloseHandle(v10);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_6bd16d013d8c3f57013cff63c39441ae_Traceguids, ThreadId);
  }
  return 0;
}

```

## disassembly

```asm
0x18001d190  push    rbx
0x18001d192  push    rbp
0x18001d193  push    rsi
0x18001d194  push    rdi
0x18001d195  sub     rsp, 38h
0x18001d199  mov     rdi, rdx
0x18001d19c  mov     [rsp+58h+ThreadId], 0
0x18001d1a4  mov     edx, 18h; uBytes
0x18001d1a9  mov     rbp, rcx
0x18001d1ac  mov     rsi, r8
0x18001d1af  lea     ecx, [rdx+28h]; uFlags
0x18001d1b2  call    cs:__imp_LocalAlloc
0x18001d1b8  mov     rbx, rax
0x18001d1bb  test    rax, rax
0x18001d1be  jz      loc_18001D286
0x18001d1c4  mov     [rax+8], rsi
0x18001d1c8  mov     [rax+10h], rbp
0x18001d1cc  test    rdi, rdi
0x18001d1cf  jz      short loc_18001D1ED
0x18001d1d1  xor     r9d, r9d; lpName
0x18001d1d4  xor     r8d, r8d; bInitialState
0x18001d1d7  xor     edx, edx; bManualReset
0x18001d1d9  xor     ecx, ecx; lpEventAttributes
0x18001d1db  call    cs:__imp_CreateEventA
0x18001d1e1  mov     [rbx], rax
0x18001d1e4  test    rax, rax
0x18001d1e7  jz      loc_18001D27D
0x18001d1ed  mov     rsi, [rbx]
0x18001d1f0  lea     rax, [rsp+58h+ThreadId]
0x18001d1f5  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x18001d1fa  lea     r8, ?mmStartTask@@YAKPEAX@Z; lpStartAddress
0x18001d201  mov     r9, rbx; lpParameter
0x18001d204  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18001d20c  mov     edx, 200h; dwStackSize
0x18001d211  xor     ecx, ecx; lpThreadAttributes
0x18001d213  call    cs:__imp_CreateThread
0x18001d219  test    rax, rax
0x18001d21c  jz      short loc_18001D26F
0x18001d21e  test    rdi, rdi
0x18001d221  jz      short loc_18001D226
0x18001d223  mov     [rdi], rsi
0x18001d226  mov     rcx, rax; hObject
0x18001d229  call    cs:__imp_CloseHandle
0x18001d22f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d236  lea     rax, WPP_GLOBAL_Control
0x18001d23d  cmp     rcx, rax
0x18001d240  jz      short loc_18001D26B
0x18001d242  test    dword ptr [rcx+1Ch], 400000h
0x18001d249  jz      short loc_18001D26B
0x18001d24b  cmp     byte ptr [rcx+19h], 2
0x18001d24f  jb      short loc_18001D26B
0x18001d251  mov     r9d, [rsp+58h+ThreadId]
0x18001d256  lea     r8, WPP_6bd16d013d8c3f57013cff63c39441ae_Traceguids
0x18001d25d  mov     rcx, [rcx+10h]
0x18001d261  mov     edx, 0Ch
0x18001d266  call    WPP_SF_D
0x18001d26b  xor     eax, eax
0x18001d26d  jmp     short loc_18001D28B
0x18001d26f  test    rdi, rdi
0x18001d272  jz      short loc_18001D27D
0x18001d274  mov     rcx, [rbx]; hObject
0x18001d277  call    cs:__imp_CloseHandle
0x18001d27d  mov     rcx, rbx; hMem
0x18001d280  call    cs:__imp_LocalFree
0x18001d286  mov     eax, 2
0x18001d28b  add     rsp, 38h
0x18001d28f  pop     rdi
0x18001d290  pop     rsi
0x18001d291  pop     rbp
0x18001d292  pop     rbx
0x18001d293  retn
```
