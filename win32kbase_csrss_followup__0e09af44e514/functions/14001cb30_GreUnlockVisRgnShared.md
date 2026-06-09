# GreUnlockVisRgnShared

- ea: `0x14001cb30`
- end: `0x14001cdc7`
- name: `GreUnlockVisRgnShared`
- size: `663`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14001cb30`
- `0x14001d160`
- `0x140031bf4`
- `0x140190760`

## import_xrefs

- `ntoskrnl!PsGetThreadWin32Thread` at `0x14001cb84`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14001cbef`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14001cc5a`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14001cb84`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14001cbef`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14001cc5a`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001ccbd`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001ccec`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001cd1b`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001ccbd`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001ccec`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001cd1b`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14001ccae`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14001ccdd`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14001cd0c`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14001ccae`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14001ccdd`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14001cd0c`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001cb6d`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001cbd8`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001cc43`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001cb6d`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001cbd8`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001cc43`
- `WIN32K!W32GetSessionState` at `0x14001cb42`
- `WIN32K!W32GetSessionState` at `0x14001cb42`

## pseudocode

```c
void __fastcall GreUnlockVisRgnShared(__int64 a1)
{
  int v1; // ecx
  int v2; // r8d
  __int64 *v3; // r14
  __int64 v4; // rsi
  struct _KTHREAD *CurrentThread; // rbp
  __int64 v6; // rdi
  __int64 *ThreadWin32Thread; // rax
  __int64 v8; // rax
  __int64 v9; // rdi
  bool v10; // zf
  int v11; // ecx
  int v12; // r8d
  __int64 v13; // rsi
  struct _KTHREAD *v14; // rbp
  __int64 v15; // rdi
  __int64 *v16; // rax
  __int64 v17; // rax
  __int64 v18; // rdi
  int v19; // ecx
  int v20; // r8d
  __int64 v21; // rsi
  struct _KTHREAD *v22; // rbp
  __int64 v23; // rdi
  __int64 *v24; // rax
  __int64 v25; // rax
  __int64 v26; // rdi
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  int v29; // ebx
  __int64 v30; // rax
  int v31; // ebx
  __int64 v32; // rax

  v3 = *(__int64 **)(W32GetSessionState(a1) + 88);
  v4 = *v3;
  if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
    McTemplateK0pz_EtwWriteTransfer(v1, (unsigned int)LockRelease, v2, v4 + 728, (__int64)L"DCVisRgn");
  CurrentThread = KeGetCurrentThread();
  v6 = 0;
  if ( !(unsigned __int8)KeIsAttachedProcess()
    || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(),
        CurrentThreadProcess = PsGetCurrentThreadProcess(),
        CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
  {
    ThreadWin32Thread = (__int64 *)PsGetThreadWin32Thread(CurrentThread);
    if ( ThreadWin32Thread )
      v6 = *ThreadWin32Thread;
  }
  v8 = v6 + 8;
  v9 = -v6;
  if ( (v8 & -(__int64)(v9 != 0)) != 0 )
  {
    v10 = (*(_BYTE *)((v8 & -(__int64)(v9 != 0)) + 0xB))-- == 1;
    if ( v10 )
      *(_QWORD *)(v8 & -(__int64)(v9 != 0)) &= ~8uLL;
  }
  GreReleaseSemaphoreSharedInternal((HSEMAPHORE)(v4 + 728));
  v13 = *v3;
  if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
    McTemplateK0pz_EtwWriteTransfer(v11, (unsigned int)LockRelease, v12, v13 + 1144, (__int64)L"GreLock");
  v14 = KeGetCurrentThread();
  v15 = 0;
  if ( !(unsigned __int8)KeIsAttachedProcess()
    || (v29 = W32GetCurrentWin32kSessionId(),
        v30 = PsGetCurrentThreadProcess(),
        v29 == (unsigned int)PsGetProcessSessionIdEx(v30)) )
  {
    v16 = (__int64 *)PsGetThreadWin32Thread(v14);
    if ( v16 )
      v15 = *v16;
  }
  v17 = v15 + 8;
  v18 = -v15;
  if ( (v17 & -(__int64)(v18 != 0)) != 0 )
  {
    v10 = (*(_BYTE *)((v17 & -(__int64)(v18 != 0)) + 0xA))-- == 1;
    if ( v10 )
      *(_QWORD *)(v17 & -(__int64)(v18 != 0)) &= ~4uLL;
  }
  GreReleaseSemaphoreSharedInternal((HSEMAPHORE)(v13 + 1144));
  v21 = *v3;
  if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
    McTemplateK0pz_EtwWriteTransfer(v19, (unsigned int)LockRelease, v20, v21 + 624, (__int64)L"DynamicModeChange");
  v22 = KeGetCurrentThread();
  v23 = 0;
  if ( !(unsigned __int8)KeIsAttachedProcess()
    || (v31 = W32GetCurrentWin32kSessionId(),
        v32 = PsGetCurrentThreadProcess(),
        v31 == (unsigned int)PsGetProcessSessionIdEx(v32)) )
  {
    v24 = (__int64 *)PsGetThreadWin32Thread(v22);
    if ( v24 )
      v23 = *v24;
  }
  v25 = v23 + 8;
  v26 = -v23;
  if ( (v25 & -(__int64)(v26 != 0)) != 0 )
  {
    v10 = (*(_BYTE *)((v25 & -(__int64)(v26 != 0)) + 9))-- == 1;
    if ( v10 )
      *(_QWORD *)(v25 & -(__int64)(v26 != 0)) &= ~2uLL;
  }
  GreReleaseSemaphoreSharedInternal((HSEMAPHORE)(v21 + 624));
}

```

## disassembly

```asm
0x14001cb30  mov     [rsp+arg_8], rbx
0x14001cb35  mov     [rsp+arg_10], rbp
0x14001cb3a  push    rsi
0x14001cb3b  push    rdi
0x14001cb3c  push    r14
0x14001cb3e  sub     rsp, 30h
0x14001cb42  call    cs:__imp_W32GetSessionState
0x14001cb49  nop     dword ptr [rax+rax+00h]
0x14001cb4e  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x14001cb55  mov     r14, [rax+58h]
0x14001cb59  mov     rsi, [r14]
0x14001cb5c  jnz     loc_14001CD34
0x14001cb62  mov     rbp, gs:188h
0x14001cb6b  xor     edi, edi
0x14001cb6d  call    cs:__imp_KeIsAttachedProcess
0x14001cb74  nop     dword ptr [rax+rax+00h]
0x14001cb79  test    al, al
0x14001cb7b  jnz     loc_14001CCA7
0x14001cb81  mov     rcx, rbp
0x14001cb84  call    cs:__imp_PsGetThreadWin32Thread
0x14001cb8b  nop     dword ptr [rax+rax+00h]
0x14001cb90  test    rax, rax
0x14001cb93  jz      short loc_14001CB98
0x14001cb95  mov     rdi, [rax]
0x14001cb98  lea     rax, [rdi+8]
0x14001cb9c  neg     rdi
0x14001cb9f  sbb     rdx, rdx
0x14001cba2  and     rdx, rax
0x14001cba5  jz      short loc_14001CBB1
0x14001cba7  add     byte ptr [rdx+0Bh], 0FFh
0x14001cbab  jnz     short loc_14001CBB1
0x14001cbad  and     qword ptr [rdx], 0FFFFFFFFFFFFFFF7h
0x14001cbb1  lea     rcx, [rsi+2D8h]; HSEMAPHORE
0x14001cbb8  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x14001cbbd  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x14001cbc4  mov     rsi, [r14]
0x14001cbc7  jnz     loc_14001CD65
0x14001cbcd  mov     rbp, gs:188h
0x14001cbd6  xor     edi, edi
0x14001cbd8  call    cs:__imp_KeIsAttachedProcess
0x14001cbdf  nop     dword ptr [rax+rax+00h]
0x14001cbe4  test    al, al
0x14001cbe6  jnz     loc_14001CCD6
0x14001cbec  mov     rcx, rbp
0x14001cbef  call    cs:__imp_PsGetThreadWin32Thread
0x14001cbf6  nop     dword ptr [rax+rax+00h]
0x14001cbfb  test    rax, rax
0x14001cbfe  jz      short loc_14001CC03
0x14001cc00  mov     rdi, [rax]
0x14001cc03  lea     rax, [rdi+8]
0x14001cc07  neg     rdi
0x14001cc0a  sbb     rdx, rdx
0x14001cc0d  and     rdx, rax
0x14001cc10  jz      short loc_14001CC1C
0x14001cc12  add     byte ptr [rdx+0Ah], 0FFh
0x14001cc16  jnz     short loc_14001CC1C
0x14001cc18  and     qword ptr [rdx], 0FFFFFFFFFFFFFFFBh
0x14001cc1c  lea     rcx, [rsi+478h]; HSEMAPHORE
0x14001cc23  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x14001cc28  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x14001cc2f  mov     rsi, [r14]
0x14001cc32  jnz     loc_14001CD96
0x14001cc38  mov     rbp, gs:188h
0x14001cc41  xor     edi, edi
0x14001cc43  call    cs:__imp_KeIsAttachedProcess
0x14001cc4a  nop     dword ptr [rax+rax+00h]
0x14001cc4f  test    al, al
0x14001cc51  jnz     loc_14001CD05
0x14001cc57  mov     rcx, rbp
0x14001cc5a  call    cs:__imp_PsGetThreadWin32Thread
0x14001cc61  nop     dword ptr [rax+rax+00h]
0x14001cc66  test    rax, rax
0x14001cc69  jz      short loc_14001CC6E
0x14001cc6b  mov     rdi, [rax]
0x14001cc6e  lea     rax, [rdi+8]
0x14001cc72  neg     rdi
0x14001cc75  sbb     rdx, rdx
0x14001cc78  and     rdx, rax
0x14001cc7b  jz      short loc_14001CC87
0x14001cc7d  add     byte ptr [rdx+9], 0FFh
0x14001cc81  jnz     short loc_14001CC87
0x14001cc83  and     qword ptr [rdx], 0FFFFFFFFFFFFFFFDh
0x14001cc87  lea     rcx, [rsi+270h]; HSEMAPHORE
0x14001cc8e  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x14001cc93  mov     rbx, [rsp+48h+arg_8]
0x14001cc98  mov     rbp, [rsp+48h+arg_10]
0x14001cc9d  add     rsp, 30h
0x14001cca1  pop     r14
0x14001cca3  pop     rdi
0x14001cca4  pop     rsi
0x14001cca5  retn
0x14001cca7  call    W32GetCurrentWin32kSessionId
0x14001ccac  mov     ebx, eax
0x14001ccae  call    cs:__imp_PsGetCurrentThreadProcess
0x14001ccb5  nop     dword ptr [rax+rax+00h]
0x14001ccba  mov     rcx, rax
0x14001ccbd  call    cs:__imp_PsGetProcessSessionIdEx
0x14001ccc4  nop     dword ptr [rax+rax+00h]
0x14001ccc9  cmp     ebx, eax
0x14001cccb  jz      loc_14001CB81
0x14001ccd1  jmp     loc_14001CB98
0x14001ccd6  call    W32GetCurrentWin32kSessionId
0x14001ccdb  mov     ebx, eax
0x14001ccdd  call    cs:__imp_PsGetCurrentThreadProcess
0x14001cce4  nop     dword ptr [rax+rax+00h]
0x14001cce9  mov     rcx, rax
0x14001ccec  call    cs:__imp_PsGetProcessSessionIdEx
0x14001ccf3  nop     dword ptr [rax+rax+00h]
0x14001ccf8  cmp     ebx, eax
0x14001ccfa  jz      loc_14001CBEC
0x14001cd00  jmp     loc_14001CC03
0x14001cd05  call    W32GetCurrentWin32kSessionId
0x14001cd0a  mov     ebx, eax
0x14001cd0c  call    cs:__imp_PsGetCurrentThreadProcess
0x14001cd13  nop     dword ptr [rax+rax+00h]
0x14001cd18  mov     rcx, rax
0x14001cd1b  call    cs:__imp_PsGetProcessSessionIdEx
0x14001cd22  nop     dword ptr [rax+rax+00h]
0x14001cd27  cmp     ebx, eax
0x14001cd29  jz      loc_14001CC57
0x14001cd2f  jmp     loc_14001CC6E
0x14001cd34  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x14001cd3b  jz      loc_14001CB62
0x14001cd41  lea     rax, aDcvisrgn; "DCVisRgn"
0x14001cd48  lea     r9, [rsi+2D8h]
0x14001cd4f  mov     [rsp+48h+var_28], rax
0x14001cd54  lea     rdx, LockRelease
0x14001cd5b  call    McTemplateK0pz_EtwWriteTransfer
0x14001cd60  jmp     loc_14001CB62
0x14001cd65  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x14001cd6c  jz      loc_14001CBCD
0x14001cd72  lea     rax, aGrelock; "GreLock"
0x14001cd79  lea     r9, [rsi+478h]
0x14001cd80  mov     [rsp+48h+var_28], rax
0x14001cd85  lea     rdx, LockRelease
0x14001cd8c  call    McTemplateK0pz_EtwWriteTransfer
0x14001cd91  jmp     loc_14001CBCD
0x14001cd96  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x14001cd9d  jz      loc_14001CC38
0x14001cda3  lea     rax, aDynamicmodecha; "DynamicModeChange"
0x14001cdaa  lea     r9, [rsi+270h]
0x14001cdb1  mov     [rsp+48h+var_28], rax
0x14001cdb6  lea     rdx, LockRelease
0x14001cdbd  call    McTemplateK0pz_EtwWriteTransfer
0x14001cdc2  jmp     loc_14001CC38
```
