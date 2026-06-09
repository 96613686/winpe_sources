# GreUnlockVisRgnShared

- ea: `0x1400139c0`
- end: `0x140013c57`
- name: `GreUnlockVisRgnShared`
- size: `663`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400139c0`
- `0x140013ff0`
- `0x140028974`
- `0x140190650`

## import_xrefs

- `ntoskrnl!PsGetThreadWin32Thread` at `0x140013a14`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140013a7f`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140013aea`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140013a14`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140013a7f`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140013aea`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140013b4d`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140013b7c`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140013bab`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140013b4d`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140013b7c`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140013bab`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140013b3e`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140013b6d`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140013b9c`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140013b3e`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140013b6d`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140013b9c`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400139fd`
- `ntoskrnl!KeIsAttachedProcess` at `0x140013a68`
- `ntoskrnl!KeIsAttachedProcess` at `0x140013ad3`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400139fd`
- `ntoskrnl!KeIsAttachedProcess` at `0x140013a68`
- `ntoskrnl!KeIsAttachedProcess` at `0x140013ad3`
- `WIN32K!W32GetSessionState` at `0x1400139d2`
- `WIN32K!W32GetSessionState` at `0x1400139d2`

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
0x1400139c0  mov     [rsp+arg_8], rbx
0x1400139c5  mov     [rsp+arg_10], rbp
0x1400139ca  push    rsi
0x1400139cb  push    rdi
0x1400139cc  push    r14
0x1400139ce  sub     rsp, 30h
0x1400139d2  call    cs:__imp_W32GetSessionState
0x1400139d9  nop     dword ptr [rax+rax+00h]
0x1400139de  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x1400139e5  mov     r14, [rax+58h]
0x1400139e9  mov     rsi, [r14]
0x1400139ec  jnz     loc_140013BC4
0x1400139f2  mov     rbp, gs:188h
0x1400139fb  xor     edi, edi
0x1400139fd  call    cs:__imp_KeIsAttachedProcess
0x140013a04  nop     dword ptr [rax+rax+00h]
0x140013a09  test    al, al
0x140013a0b  jnz     loc_140013B37
0x140013a11  mov     rcx, rbp
0x140013a14  call    cs:__imp_PsGetThreadWin32Thread
0x140013a1b  nop     dword ptr [rax+rax+00h]
0x140013a20  test    rax, rax
0x140013a23  jz      short loc_140013A28
0x140013a25  mov     rdi, [rax]
0x140013a28  lea     rax, [rdi+8]
0x140013a2c  neg     rdi
0x140013a2f  sbb     rdx, rdx
0x140013a32  and     rdx, rax
0x140013a35  jz      short loc_140013A41
0x140013a37  add     byte ptr [rdx+0Bh], 0FFh
0x140013a3b  jnz     short loc_140013A41
0x140013a3d  and     qword ptr [rdx], 0FFFFFFFFFFFFFFF7h
0x140013a41  lea     rcx, [rsi+2D8h]; HSEMAPHORE
0x140013a48  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140013a4d  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x140013a54  mov     rsi, [r14]
0x140013a57  jnz     loc_140013BF5
0x140013a5d  mov     rbp, gs:188h
0x140013a66  xor     edi, edi
0x140013a68  call    cs:__imp_KeIsAttachedProcess
0x140013a6f  nop     dword ptr [rax+rax+00h]
0x140013a74  test    al, al
0x140013a76  jnz     loc_140013B66
0x140013a7c  mov     rcx, rbp
0x140013a7f  call    cs:__imp_PsGetThreadWin32Thread
0x140013a86  nop     dword ptr [rax+rax+00h]
0x140013a8b  test    rax, rax
0x140013a8e  jz      short loc_140013A93
0x140013a90  mov     rdi, [rax]
0x140013a93  lea     rax, [rdi+8]
0x140013a97  neg     rdi
0x140013a9a  sbb     rdx, rdx
0x140013a9d  and     rdx, rax
0x140013aa0  jz      short loc_140013AAC
0x140013aa2  add     byte ptr [rdx+0Ah], 0FFh
0x140013aa6  jnz     short loc_140013AAC
0x140013aa8  and     qword ptr [rdx], 0FFFFFFFFFFFFFFFBh
0x140013aac  lea     rcx, [rsi+478h]; HSEMAPHORE
0x140013ab3  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140013ab8  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x140013abf  mov     rsi, [r14]
0x140013ac2  jnz     loc_140013C26
0x140013ac8  mov     rbp, gs:188h
0x140013ad1  xor     edi, edi
0x140013ad3  call    cs:__imp_KeIsAttachedProcess
0x140013ada  nop     dword ptr [rax+rax+00h]
0x140013adf  test    al, al
0x140013ae1  jnz     loc_140013B95
0x140013ae7  mov     rcx, rbp
0x140013aea  call    cs:__imp_PsGetThreadWin32Thread
0x140013af1  nop     dword ptr [rax+rax+00h]
0x140013af6  test    rax, rax
0x140013af9  jz      short loc_140013AFE
0x140013afb  mov     rdi, [rax]
0x140013afe  lea     rax, [rdi+8]
0x140013b02  neg     rdi
0x140013b05  sbb     rdx, rdx
0x140013b08  and     rdx, rax
0x140013b0b  jz      short loc_140013B17
0x140013b0d  add     byte ptr [rdx+9], 0FFh
0x140013b11  jnz     short loc_140013B17
0x140013b13  and     qword ptr [rdx], 0FFFFFFFFFFFFFFFDh
0x140013b17  lea     rcx, [rsi+270h]; HSEMAPHORE
0x140013b1e  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140013b23  mov     rbx, [rsp+48h+arg_8]
0x140013b28  mov     rbp, [rsp+48h+arg_10]
0x140013b2d  add     rsp, 30h
0x140013b31  pop     r14
0x140013b33  pop     rdi
0x140013b34  pop     rsi
0x140013b35  retn
0x140013b37  call    W32GetCurrentWin32kSessionId
0x140013b3c  mov     ebx, eax
0x140013b3e  call    cs:__imp_PsGetCurrentThreadProcess
0x140013b45  nop     dword ptr [rax+rax+00h]
0x140013b4a  mov     rcx, rax
0x140013b4d  call    cs:__imp_PsGetProcessSessionIdEx
0x140013b54  nop     dword ptr [rax+rax+00h]
0x140013b59  cmp     ebx, eax
0x140013b5b  jz      loc_140013A11
0x140013b61  jmp     loc_140013A28
0x140013b66  call    W32GetCurrentWin32kSessionId
0x140013b6b  mov     ebx, eax
0x140013b6d  call    cs:__imp_PsGetCurrentThreadProcess
0x140013b74  nop     dword ptr [rax+rax+00h]
0x140013b79  mov     rcx, rax
0x140013b7c  call    cs:__imp_PsGetProcessSessionIdEx
0x140013b83  nop     dword ptr [rax+rax+00h]
0x140013b88  cmp     ebx, eax
0x140013b8a  jz      loc_140013A7C
0x140013b90  jmp     loc_140013A93
0x140013b95  call    W32GetCurrentWin32kSessionId
0x140013b9a  mov     ebx, eax
0x140013b9c  call    cs:__imp_PsGetCurrentThreadProcess
0x140013ba3  nop     dword ptr [rax+rax+00h]
0x140013ba8  mov     rcx, rax
0x140013bab  call    cs:__imp_PsGetProcessSessionIdEx
0x140013bb2  nop     dword ptr [rax+rax+00h]
0x140013bb7  cmp     ebx, eax
0x140013bb9  jz      loc_140013AE7
0x140013bbf  jmp     loc_140013AFE
0x140013bc4  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x140013bcb  jz      loc_1400139F2
0x140013bd1  lea     rax, aDcvisrgn; "DCVisRgn"
0x140013bd8  lea     r9, [rsi+2D8h]
0x140013bdf  mov     [rsp+48h+var_28], rax
0x140013be4  lea     rdx, LockRelease
0x140013beb  call    McTemplateK0pz_EtwWriteTransfer
0x140013bf0  jmp     loc_1400139F2
0x140013bf5  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x140013bfc  jz      loc_140013A5D
0x140013c02  lea     rax, aGrelock; "GreLock"
0x140013c09  lea     r9, [rsi+478h]
0x140013c10  mov     [rsp+48h+var_28], rax
0x140013c15  lea     rdx, LockRelease
0x140013c1c  call    McTemplateK0pz_EtwWriteTransfer
0x140013c21  jmp     loc_140013A5D
0x140013c26  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x140013c2d  jz      loc_140013AC8
0x140013c33  lea     rax, aDynamicmodecha; "DynamicModeChange"
0x140013c3a  lea     r9, [rsi+270h]
0x140013c41  mov     [rsp+48h+var_28], rax
0x140013c46  lea     rdx, LockRelease
0x140013c4d  call    McTemplateK0pz_EtwWriteTransfer
0x140013c52  jmp     loc_140013AC8
```
