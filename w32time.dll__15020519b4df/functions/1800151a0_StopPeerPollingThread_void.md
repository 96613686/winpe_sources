# StopPeerPollingThread(void)

- ea: `0x1800151a0`
- end: `0x18001535e`
- name: `?StopPeerPollingThread@@YAJXZ`
- size: `446`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180015020`
- `0x180015620`
- `0x180029bbc`

## callees

- `0x1800151a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015290`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800152bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015290`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800152bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001525b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001525b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001529e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015300`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001532a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001529e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015300`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001532a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180015279`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180015279`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800151d3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180015201`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18001522e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800151d3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180015201`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18001522e`

## pseudocode

```c
__int64 StopPeerPollingThread(void)
{
  _NtpProvState *v0; // rbx
  int v1; // ebp
  void *v2; // rcx
  HANDLE *v3; // rdi
  HANDLE *v4; // rsi
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx
  signed int v7; // eax
  signed int v8; // edi
  signed int LastError; // eax
  bool v11; // sf
  signed int v12; // eax
  bool v13; // sf
  signed int v14; // eax
  bool v15; // sf

  v0 = g_pnpstate;
  v1 = 0;
  v2 = (void *)*((_QWORD *)g_pnpstate + 14);
  v3 = (HANDLE *)((char *)g_pnpstate + 120);
  v4 = (HANDLE *)((char *)g_pnpstate + 128);
  if ( v2 )
  {
    if ( !UnregisterWaitEx(v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      LastError = GetLastError();
      v11 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v11 = LastError < 0;
      }
      if ( v11 )
        v1 = LastError;
    }
    *((_QWORD *)v0 + 14) = 0;
    v0 = g_pnpstate;
  }
  if ( *v3 )
  {
    if ( !UnregisterWaitEx(*v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      v12 = GetLastError();
      v13 = v12 < 0;
      if ( v12 > 0 )
      {
        v12 = (unsigned __int16)v12 | 0x80070000;
        v13 = v12 < 0;
      }
      if ( v13 && v1 >= 0 )
        v1 = v12;
    }
    v0 = g_pnpstate;
    *v3 = 0;
  }
  if ( *v4 )
  {
    if ( !UnregisterWaitEx(*v4, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      v14 = GetLastError();
      v15 = v14 < 0;
      if ( v14 > 0 )
      {
        v14 = (unsigned __int16)v14 | 0x80070000;
        v15 = v14 < 0;
      }
      if ( v15 && v1 >= 0 )
        v1 = v14;
    }
    v0 = g_pnpstate;
    *v4 = 0;
  }
  v5 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)v0 + 17);
  if ( v5 )
  {
    EnterCriticalSection(v5);
    DebugInfo = v5[1].DebugInfo;
    if ( !DebugInfo )
    {
LABEL_14:
      LeaveCriticalSection(v5);
      return (unsigned int)v1;
    }
    if ( DeleteTimerQueueTimer(0, DebugInfo, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      v5[1].DebugInfo = 0;
      goto LABEL_14;
    }
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    LeaveCriticalSection(v5);
    if ( v8 < 0 && v1 >= 0 )
      return (unsigned int)v8;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800151a0  push    rbx
0x1800151a2  push    rbp
0x1800151a3  push    rsi
0x1800151a4  push    rdi
0x1800151a5  push    r14
0x1800151a7  sub     rsp, 20h
0x1800151ab  mov     rbx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800151b2  xor     r14d, r14d
0x1800151b5  mov     ebp, r14d
0x1800151b8  mov     rcx, [rbx+70h]; WaitHandle
0x1800151bc  lea     rdi, [rbx+78h]
0x1800151c0  lea     rsi, [rbx+80h]
0x1800151c7  test    rcx, rcx
0x1800151ca  jz      short loc_1800151F2
0x1800151cc  mov     rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800151d3  call    cs:__imp_UnregisterWaitEx
0x1800151da  nop     dword ptr [rax+rax+00h]
0x1800151df  test    eax, eax
0x1800151e1  jz      loc_1800152DE
0x1800151e7  mov     [rbx+70h], r14
0x1800151eb  mov     rbx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800151f2  mov     rcx, [rdi]; WaitHandle
0x1800151f5  test    rcx, rcx
0x1800151f8  jz      short loc_18001521F
0x1800151fa  mov     rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180015201  call    cs:__imp_UnregisterWaitEx
0x180015208  nop     dword ptr [rax+rax+00h]
0x18001520d  test    eax, eax
0x18001520f  jz      loc_180015300
0x180015215  mov     rbx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18001521c  mov     [rdi], r14
0x18001521f  mov     rcx, [rsi]; WaitHandle
0x180015222  test    rcx, rcx
0x180015225  jz      short loc_18001524C
0x180015227  mov     rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18001522e  call    cs:__imp_UnregisterWaitEx
0x180015235  nop     dword ptr [rax+rax+00h]
0x18001523a  test    eax, eax
0x18001523c  jz      loc_18001532A
0x180015242  mov     rbx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180015249  mov     [rsi], r14
0x18001524c  mov     rbx, [rbx+88h]
0x180015253  test    rbx, rbx
0x180015256  jz      short loc_1800152D0
0x180015258  mov     rcx, rbx; lpCriticalSection
0x18001525b  call    cs:__imp_EnterCriticalSection
0x180015262  nop     dword ptr [rax+rax+00h]
0x180015267  mov     rdx, [rbx+28h]; Timer
0x18001526b  test    rdx, rdx
0x18001526e  jz      short loc_18001528D
0x180015270  xor     ecx, ecx; TimerQueue
0x180015272  mov     r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180015279  call    cs:__imp_DeleteTimerQueueTimer
0x180015280  nop     dword ptr [rax+rax+00h]
0x180015285  test    eax, eax
0x180015287  jz      short loc_18001529E
0x180015289  mov     [rbx+28h], r14
0x18001528d  mov     rcx, rbx; lpCriticalSection
0x180015290  call    cs:__imp_LeaveCriticalSection
0x180015297  nop     dword ptr [rax+rax+00h]
0x18001529c  jmp     short loc_1800152D0
0x18001529e  call    cs:__imp_GetLastError
0x1800152a5  nop     dword ptr [rax+rax+00h]
0x1800152aa  mov     edi, eax
0x1800152ac  test    eax, eax
0x1800152ae  jle     short loc_1800152B9
0x1800152b0  movzx   edi, ax
0x1800152b3  or      edi, 80070000h
0x1800152b9  mov     rcx, rbx; lpCriticalSection
0x1800152bc  call    cs:__imp_LeaveCriticalSection
0x1800152c3  nop     dword ptr [rax+rax+00h]
0x1800152c8  test    edi, edi
0x1800152ca  js      loc_180015354
0x1800152d0  mov     eax, ebp
0x1800152d2  add     rsp, 20h
0x1800152d6  pop     r14
0x1800152d8  pop     rdi
0x1800152d9  pop     rsi
0x1800152da  pop     rbp
0x1800152db  pop     rbx
0x1800152dc  retn
0x1800152de  call    cs:__imp_GetLastError
0x1800152e5  nop     dword ptr [rax+rax+00h]
0x1800152ea  test    eax, eax
0x1800152ec  jle     short loc_1800152F8
0x1800152ee  movzx   eax, ax
0x1800152f1  or      eax, 80070000h
0x1800152f6  test    eax, eax
0x1800152f8  cmovs   ebp, eax
0x1800152fb  jmp     loc_1800151E7
0x180015300  call    cs:__imp_GetLastError
0x180015307  nop     dword ptr [rax+rax+00h]
0x18001530c  test    eax, eax
0x18001530e  jle     short loc_18001531A
0x180015310  movzx   eax, ax
0x180015313  or      eax, 80070000h
0x180015318  test    eax, eax
0x18001531a  jns     loc_180015215
0x180015320  test    ebp, ebp
0x180015322  cmovns  ebp, eax
0x180015325  jmp     loc_180015215
0x18001532a  call    cs:__imp_GetLastError
0x180015331  nop     dword ptr [rax+rax+00h]
0x180015336  test    eax, eax
0x180015338  jle     short loc_180015344
0x18001533a  movzx   eax, ax
0x18001533d  or      eax, 80070000h
0x180015342  test    eax, eax
0x180015344  jns     loc_180015242
0x18001534a  test    ebp, ebp
0x18001534c  cmovns  ebp, eax
0x18001534f  jmp     loc_180015242
0x180015354  test    ebp, ebp
0x180015356  cmovns  ebp, edi
0x180015359  jmp     loc_1800152D0
```
