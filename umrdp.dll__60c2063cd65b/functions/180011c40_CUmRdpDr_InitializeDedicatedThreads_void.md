# CUmRdpDr::InitializeDedicatedThreads(void)

- ea: `0x180011c40`
- end: `0x180011e5a`
- name: `?InitializeDedicatedThreads@CUmRdpDr@@AEAAHXZ`
- size: `538`
- prototype: `__int64 __fastcall(CUmRdpDr *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011850`

## callees

- `0x180011c40`
- `0x18001327c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011db1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011dee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011db1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011dee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011e2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011e2f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011e22`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011e22`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011e10`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011e10`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011cc8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011ce8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011d49`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011d69`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011cc8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011ce8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011d49`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011d69`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180011cac`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180011d31`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180011cac`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180011d31`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180011d9f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180011ddc`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180011d9f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180011ddc`

## pseudocode

```c
__int64 __fastcall CUmRdpDr::InitializeDedicatedThreads(CUmRdpDr *this)
{
  _QWORD *v1; // rsi
  _QWORD *v3; // r14
  unsigned int v4; // edi
  HANDLE EventW; // rax
  HANDLE v6; // rax
  HANDLE v7; // rax
  HANDLE v8; // rax
  HANDLE v9; // rax
  HANDLE v10; // rax
  void *v11; // rcx
  DWORD ThreadId; // [rsp+60h] [rbp+8h] BYREF

  v1 = (_QWORD *)((char *)this + 2200);
  ThreadId = 0;
  if ( !*((_QWORD *)this + 276) )
  {
    v3 = (_QWORD *)((char *)this + 2296);
    if ( !*((_QWORD *)this + 288) )
    {
      *v1 = this;
      *((_QWORD *)this + 280) = (char *)this + 2232;
      *((_QWORD *)this + 279) = (char *)this + 2232;
      *((_QWORD *)this + 276) = 0;
      *((_DWORD *)this + 572) = 0;
      if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 2248), 0x400u) )
      {
        v4 = 1;
        EventW = CreateEventW(0, 1, 0, 0);
        *((_QWORD *)this + 277) = EventW;
        if ( EventW )
        {
          v6 = CreateEventW(0, 0, 0, 0);
          *((_QWORD *)this + 278) = v6;
          if ( v6 )
          {
            *v3 = this;
            *((_QWORD *)this + 292) = v3 + 4;
            *((_QWORD *)this + 291) = v3 + 4;
            *((_QWORD *)this + 288) = 0;
            *((_DWORD *)this + 596) = 0;
            if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v3 + 6), 0x400u) )
            {
              v7 = CreateEventW(0, 1, 0, 0);
              *((_QWORD *)this + 289) = v7;
              if ( v7 )
              {
                v8 = CreateEventW(0, 0, 0, 0);
                *((_QWORD *)this + 290) = v8;
                if ( v8 )
                {
                  v9 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)DedicatedPrinterAnnounceThread, v1, 0, &ThreadId);
                  *((_QWORD *)this + 276) = v9;
                  if ( v9 )
                  {
                    v10 = CreateThread(0, 0, DedicatedPortAnnounceThread, v3, 0, &ThreadId);
                    *((_QWORD *)this + 288) = v10;
                    if ( v10 )
                      return v4;
                    GetLastError();
                    if ( *((_QWORD *)this + 276) )
                    {
                      v11 = (void *)*((_QWORD *)this + 277);
                      *((_DWORD *)this + 572) = 1;
                      if ( v11 )
                        SetEvent(v11);
                      WaitForSingleObject(*((HANDLE *)this + 276), 0x1388u);
                      CloseHandle(*((HANDLE *)this + 276));
                      *((_QWORD *)this + 276) = 0;
                    }
                  }
                  else
                  {
                    GetLastError();
                  }
                }
              }
            }
          }
        }
      }
      v4 = 0;
      CUmRdpDr::ShutdownDedicatedThreads(this);
      return v4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180011c40  push    rbx
0x180011c42  push    rsi
0x180011c43  push    rdi
0x180011c44  push    r14
0x180011c46  sub     rsp, 38h
0x180011c4a  lea     rsi, [rcx+898h]
0x180011c51  mov     [rsp+58h+ThreadId], 0
0x180011c59  cmp     qword ptr [rsi+8], 0
0x180011c5e  mov     rbx, rcx
0x180011c61  jnz     loc_180011E4E
0x180011c67  lea     r14, [rcx+8F8h]
0x180011c6e  cmp     qword ptr [r14+8], 0
0x180011c73  jnz     loc_180011E4E
0x180011c79  lea     rax, [rsi+20h]
0x180011c7d  mov     [rsi], rcx
0x180011c80  mov     [rcx+8C0h], rax
0x180011c87  mov     edx, 400h; dwSpinCount
0x180011c8c  mov     [rcx+8B8h], rax
0x180011c93  mov     qword ptr [rcx+8A0h], 0
0x180011c9e  mov     dword ptr [rcx+8F0h], 0
0x180011ca8  lea     rcx, [rsi+30h]; lpCriticalSection
0x180011cac  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180011cb2  test    eax, eax
0x180011cb4  jz      loc_180011E40
0x180011cba  xor     r9d, r9d; lpName
0x180011cbd  xor     r8d, r8d; bInitialState
0x180011cc0  xor     ecx, ecx; lpEventAttributes
0x180011cc2  lea     edi, [r9+1]
0x180011cc6  mov     edx, edi; bManualReset
0x180011cc8  call    cs:__imp_CreateEventW
0x180011cce  mov     [rbx+8A8h], rax
0x180011cd5  test    rax, rax
0x180011cd8  jz      loc_180011E40
0x180011cde  xor     r9d, r9d; lpName
0x180011ce1  xor     r8d, r8d; bInitialState
0x180011ce4  xor     edx, edx; bManualReset
0x180011ce6  xor     ecx, ecx; lpEventAttributes
0x180011ce8  call    cs:__imp_CreateEventW
0x180011cee  mov     [rbx+8B0h], rax
0x180011cf5  test    rax, rax
0x180011cf8  jz      loc_180011E40
0x180011cfe  lea     rax, [r14+20h]
0x180011d02  mov     [r14], rbx
0x180011d05  lea     rcx, [r14+30h]; lpCriticalSection
0x180011d09  mov     [rbx+920h], rax
0x180011d10  mov     edx, 400h; dwSpinCount
0x180011d15  mov     [rbx+918h], rax
0x180011d1c  mov     qword ptr [rbx+900h], 0
0x180011d27  mov     dword ptr [rbx+950h], 0
0x180011d31  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180011d37  test    eax, eax
0x180011d39  jz      loc_180011E40
0x180011d3f  xor     r9d, r9d; lpName
0x180011d42  xor     r8d, r8d; bInitialState
0x180011d45  mov     edx, edi; bManualReset
0x180011d47  xor     ecx, ecx; lpEventAttributes
0x180011d49  call    cs:__imp_CreateEventW
0x180011d4f  mov     [rbx+908h], rax
0x180011d56  test    rax, rax
0x180011d59  jz      loc_180011E40
0x180011d5f  xor     r9d, r9d; lpName
0x180011d62  xor     r8d, r8d; bInitialState
0x180011d65  xor     edx, edx; bManualReset
0x180011d67  xor     ecx, ecx; lpEventAttributes
0x180011d69  call    cs:__imp_CreateEventW
0x180011d6f  mov     [rbx+910h], rax
0x180011d76  test    rax, rax
0x180011d79  jz      loc_180011E40
0x180011d7f  lea     rax, [rsp+58h+ThreadId]
0x180011d84  mov     r9, rsi; lpParameter
0x180011d87  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x180011d8c  lea     r8, DedicatedPrinterAnnounceThread; lpStartAddress
0x180011d93  xor     edx, edx; dwStackSize
0x180011d95  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x180011d9d  xor     ecx, ecx; lpThreadAttributes
0x180011d9f  call    cs:__imp_CreateThread
0x180011da5  mov     [rbx+8A0h], rax
0x180011dac  test    rax, rax
0x180011daf  jnz     short loc_180011DBC
0x180011db1  call    cs:__imp_GetLastError
0x180011db7  jmp     loc_180011E40
0x180011dbc  lea     rax, [rsp+58h+ThreadId]
0x180011dc1  mov     r9, r14; lpParameter
0x180011dc4  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x180011dc9  lea     r8, DedicatedPortAnnounceThread; lpStartAddress
0x180011dd0  xor     edx, edx; dwStackSize
0x180011dd2  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x180011dda  xor     ecx, ecx; lpThreadAttributes
0x180011ddc  call    cs:__imp_CreateThread
0x180011de2  mov     [rbx+900h], rax
0x180011de9  test    rax, rax
0x180011dec  jnz     short loc_180011E4A
0x180011dee  call    cs:__imp_GetLastError
0x180011df4  cmp     qword ptr [rbx+8A0h], 0
0x180011dfc  jz      short loc_180011E40
0x180011dfe  mov     rcx, [rbx+8A8h]; hEvent
0x180011e05  mov     [rbx+8F0h], edi
0x180011e0b  test    rcx, rcx
0x180011e0e  jz      short loc_180011E16
0x180011e10  call    cs:__imp_SetEvent
0x180011e16  mov     rcx, [rbx+8A0h]; hHandle
0x180011e1d  mov     edx, 1388h; dwMilliseconds
0x180011e22  call    cs:__imp_WaitForSingleObject
0x180011e28  mov     rcx, [rbx+8A0h]; hObject
0x180011e2f  call    cs:__imp_CloseHandle
0x180011e35  mov     qword ptr [rbx+8A0h], 0
0x180011e40  xor     edi, edi
0x180011e42  mov     rcx, rbx; this
0x180011e45  call    ?ShutdownDedicatedThreads@CUmRdpDr@@AEAAXXZ; CUmRdpDr::ShutdownDedicatedThreads(void)
0x180011e4a  mov     eax, edi
0x180011e4c  jmp     short loc_180011E50
0x180011e4e  xor     eax, eax
0x180011e50  add     rsp, 38h
0x180011e54  pop     r14
0x180011e56  pop     rdi
0x180011e57  pop     rsi
0x180011e58  pop     rbx
0x180011e59  retn
```
