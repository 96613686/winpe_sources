# TmDeinit

- ea: `0x18007b638`
- end: `0x18007b715`
- name: `TmDeinit`
- size: `221`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18007a0d4`
- `0x18007a2e4`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18007b638`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b69a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b69a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x18007b68a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x18007b68a`

## pseudocode

```c
__int64 TmDeinit()
{
  DWORD v0; // ebx
  PVOID *v1; // rcx
  DWORD LastError; // eax

  v0 = 0;
  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids);
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( g_hTimerQueue )
  {
    if ( !DeleteTimerQueueEx(g_hTimerQueue, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      LastError = GetLastError();
      v0 = LastError;
      v1 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_10;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids, LastError);
    }
    v1 = (PVOID *)WPP_GLOBAL_Control;
LABEL_10:
    g_hTimerQueue = 0;
  }
  if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 1) != 0 )
    WPP_SF_d(v1[2], 15, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids, v0);
  return v0;
}

```

## disassembly

```asm
0x18007b638  mov     [rsp+arg_0], rbx
0x18007b63d  push    rdi
0x18007b63e  sub     rsp, 20h
0x18007b642  xor     ebx, ebx
0x18007b644  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b64b  lea     rdi, WPP_GLOBAL_Control
0x18007b652  cmp     rcx, rdi
0x18007b655  jz      short loc_18007B677
0x18007b657  test    byte ptr [rcx+1Ch], 1
0x18007b65b  jz      short loc_18007B677
0x18007b65d  mov     rcx, [rcx+10h]
0x18007b661  lea     edx, [rbx+0Dh]
0x18007b664  lea     r8, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids
0x18007b66b  call    WPP_SF_
0x18007b670  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b677  mov     rax, cs:g_hTimerQueue
0x18007b67e  test    rax, rax
0x18007b681  jz      short loc_18007B6E4
0x18007b683  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18007b687  mov     rcx, rax; TimerQueue
0x18007b68a  call    cs:__imp_DeleteTimerQueueEx
0x18007b691  nop     dword ptr [rax+rax+00h]
0x18007b696  test    eax, eax
0x18007b698  jnz     short loc_18007B6D2
0x18007b69a  call    cs:__imp_GetLastError
0x18007b6a1  nop     dword ptr [rax+rax+00h]
0x18007b6a6  mov     ebx, eax
0x18007b6a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b6af  cmp     rcx, rdi
0x18007b6b2  jz      short loc_18007B6D9
0x18007b6b4  test    byte ptr [rcx+1Ch], 2
0x18007b6b8  jz      short loc_18007B6D9
0x18007b6ba  mov     rcx, [rcx+10h]
0x18007b6be  lea     r8, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids
0x18007b6c5  mov     edx, 0Eh
0x18007b6ca  mov     r9d, eax
0x18007b6cd  call    WPP_SF_d
0x18007b6d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b6d9  mov     cs:g_hTimerQueue, 0
0x18007b6e4  cmp     rcx, rdi
0x18007b6e7  jz      short loc_18007B707
0x18007b6e9  test    byte ptr [rcx+1Ch], 1
0x18007b6ed  jz      short loc_18007B707
0x18007b6ef  mov     rcx, [rcx+10h]
0x18007b6f3  lea     r8, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids
0x18007b6fa  mov     edx, 0Fh
0x18007b6ff  mov     r9d, ebx
0x18007b702  call    WPP_SF_d
0x18007b707  mov     eax, ebx
0x18007b709  mov     rbx, [rsp+28h+arg_0]
0x18007b70e  add     rsp, 20h
0x18007b712  pop     rdi
0x18007b713  retn
```
