# GreUnlockVisRgnShared

- ea: `0x140034310`
- end: `0x1400345a7`
- name: `GreUnlockVisRgnShared`
- size: `663`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140031fa0`
- `0x140034310`
- `0x1400371c0`
- `0x140192b70`

## import_xrefs

- `ntoskrnl!PsGetThreadWin32Thread` at `0x140034364`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x1400343cf`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14003443a`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140034364`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x1400343cf`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14003443a`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14003449d`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400344cc`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400344fb`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14003449d`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400344cc`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400344fb`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14003448e`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x1400344bd`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x1400344ec`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14003448e`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x1400344bd`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x1400344ec`
- `ntoskrnl!KeIsAttachedProcess` at `0x14003434d`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400343b8`
- `ntoskrnl!KeIsAttachedProcess` at `0x140034423`
- `ntoskrnl!KeIsAttachedProcess` at `0x14003434d`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400343b8`
- `ntoskrnl!KeIsAttachedProcess` at `0x140034423`
- `WIN32K!W32GetSessionState` at `0x140034322`
- `WIN32K!W32GetSessionState` at `0x140034322`

## pseudocode

```c
void __fastcall GreUnlockVisRgnShared(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v2; // rcx
  int v3; // r8d
  __int64 *v4; // r14
  __int64 v5; // rsi
  struct _KTHREAD *CurrentThread; // rbp
  __int64 v7; // rdi
  __int64 *ThreadWin32Thread; // rax
  __int64 v9; // rax
  __int64 v10; // rdi
  bool v11; // zf
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // r8d
  __int64 v15; // rsi
  struct _KTHREAD *v16; // rbp
  __int64 v17; // rdi
  __int64 *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdi
  __int64 v21; // rdx
  __int64 v22; // rcx
  int v23; // r8d
  __int64 v24; // rsi
  struct _KTHREAD *v25; // rbp
  __int64 v26; // rdi
  __int64 *v27; // rax
  __int64 v28; // rax
  __int64 v29; // rdi
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  int v32; // ebx
  __int64 v33; // rax
  int v34; // ebx
  __int64 v35; // rax

  v4 = *(__int64 **)(W32GetSessionState(a1) + 88);
  v5 = *v4;
  if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
    McTemplateK0pz_EtwWriteTransfer(v2, (unsigned int)LockRelease, v3, v5 + 728, (__int64)L"DCVisRgn");
  CurrentThread = KeGetCurrentThread();
  v7 = 0;
  if ( !(unsigned __int8)KeIsAttachedProcess(v2, v1)
    || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(),
        CurrentThreadProcess = PsGetCurrentThreadProcess(),
        CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
  {
    ThreadWin32Thread = (__int64 *)PsGetThreadWin32Thread(CurrentThread);
    if ( ThreadWin32Thread )
      v7 = *ThreadWin32Thread;
  }
  v9 = v7 + 8;
  v10 = -v7;
  if ( (v9 & -(__int64)(v10 != 0)) != 0 )
  {
    v11 = (*(_BYTE *)((v9 & -(__int64)(v10 != 0)) + 0xB))-- == 1;
    if ( v11 )
      *(_QWORD *)(v9 & -(__int64)(v10 != 0)) &= ~8uLL;
  }
  GreReleaseSemaphoreSharedInternal((HSEMAPHORE)(v5 + 728));
  v15 = *v4;
  if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
    McTemplateK0pz_EtwWriteTransfer(v13, (unsigned int)LockRelease, v14, v15 + 1144, (__int64)L"GreLock");
  v16 = KeGetCurrentThread();
  v17 = 0;
  if ( !(unsigned __int8)KeIsAttachedProcess(v13, v12)
    || (v32 = W32GetCurrentWin32kSessionId(),
        v33 = PsGetCurrentThreadProcess(),
        v32 == (unsigned int)PsGetProcessSessionIdEx(v33)) )
  {
    v18 = (__int64 *)PsGetThreadWin32Thread(v16);
    if ( v18 )
      v17 = *v18;
  }
  v19 = v17 + 8;
  v20 = -v17;
  if ( (v19 & -(__int64)(v20 != 0)) != 0 )
  {
    v11 = (*(_BYTE *)((v19 & -(__int64)(v20 != 0)) + 0xA))-- == 1;
    if ( v11 )
      *(_QWORD *)(v19 & -(__int64)(v20 != 0)) &= ~4uLL;
  }
  GreReleaseSemaphoreSharedInternal((HSEMAPHORE)(v15 + 1144));
  v24 = *v4;
  if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
    McTemplateK0pz_EtwWriteTransfer(v22, (unsigned int)LockRelease, v23, v24 + 624, (__int64)L"DynamicModeChange");
  v25 = KeGetCurrentThread();
  v26 = 0;
  if ( !(unsigned __int8)KeIsAttachedProcess(v22, v21)
    || (v34 = W32GetCurrentWin32kSessionId(),
        v35 = PsGetCurrentThreadProcess(),
        v34 == (unsigned int)PsGetProcessSessionIdEx(v35)) )
  {
    v27 = (__int64 *)PsGetThreadWin32Thread(v25);
    if ( v27 )
      v26 = *v27;
  }
  v28 = v26 + 8;
  v29 = -v26;
  if ( (v28 & -(__int64)(v29 != 0)) != 0 )
  {
    v11 = (*(_BYTE *)((v28 & -(__int64)(v29 != 0)) + 9))-- == 1;
    if ( v11 )
      *(_QWORD *)(v28 & -(__int64)(v29 != 0)) &= ~2uLL;
  }
  GreReleaseSemaphoreSharedInternal((HSEMAPHORE)(v24 + 624));
}

```

## disassembly

```asm
0x140034310  mov     [rsp+arg_8], rbx
0x140034315  mov     [rsp+arg_10], rbp
0x14003431a  push    rsi
0x14003431b  push    rdi
0x14003431c  push    r14
0x14003431e  sub     rsp, 30h
0x140034322  call    cs:__imp_W32GetSessionState
0x140034329  nop     dword ptr [rax+rax+00h]
0x14003432e  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x140034335  mov     r14, [rax+58h]
0x140034339  mov     rsi, [r14]
0x14003433c  jnz     loc_140034514
0x140034342  mov     rbp, gs:188h
0x14003434b  xor     edi, edi
0x14003434d  call    cs:__imp_KeIsAttachedProcess
0x140034354  nop     dword ptr [rax+rax+00h]
0x140034359  test    al, al
0x14003435b  jnz     loc_140034487
0x140034361  mov     rcx, rbp
0x140034364  call    cs:__imp_PsGetThreadWin32Thread
0x14003436b  nop     dword ptr [rax+rax+00h]
0x140034370  test    rax, rax
0x140034373  jz      short loc_140034378
0x140034375  mov     rdi, [rax]
0x140034378  lea     rax, [rdi+8]
0x14003437c  neg     rdi
0x14003437f  sbb     rdx, rdx
0x140034382  and     rdx, rax
0x140034385  jz      short loc_140034391
0x140034387  add     byte ptr [rdx+0Bh], 0FFh
0x14003438b  jnz     short loc_140034391
0x14003438d  and     qword ptr [rdx], 0FFFFFFFFFFFFFFF7h
0x140034391  lea     rcx, [rsi+2D8h]; HSEMAPHORE
0x140034398  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x14003439d  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x1400343a4  mov     rsi, [r14]
0x1400343a7  jnz     loc_140034545
0x1400343ad  mov     rbp, gs:188h
0x1400343b6  xor     edi, edi
0x1400343b8  call    cs:__imp_KeIsAttachedProcess
0x1400343bf  nop     dword ptr [rax+rax+00h]
0x1400343c4  test    al, al
0x1400343c6  jnz     loc_1400344B6
0x1400343cc  mov     rcx, rbp
0x1400343cf  call    cs:__imp_PsGetThreadWin32Thread
0x1400343d6  nop     dword ptr [rax+rax+00h]
0x1400343db  test    rax, rax
0x1400343de  jz      short loc_1400343E3
0x1400343e0  mov     rdi, [rax]
0x1400343e3  lea     rax, [rdi+8]
0x1400343e7  neg     rdi
0x1400343ea  sbb     rdx, rdx
0x1400343ed  and     rdx, rax
0x1400343f0  jz      short loc_1400343FC
0x1400343f2  add     byte ptr [rdx+0Ah], 0FFh
0x1400343f6  jnz     short loc_1400343FC
0x1400343f8  and     qword ptr [rdx], 0FFFFFFFFFFFFFFFBh
0x1400343fc  lea     rcx, [rsi+478h]; HSEMAPHORE
0x140034403  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140034408  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x14003440f  mov     rsi, [r14]
0x140034412  jnz     loc_140034576
0x140034418  mov     rbp, gs:188h
0x140034421  xor     edi, edi
0x140034423  call    cs:__imp_KeIsAttachedProcess
0x14003442a  nop     dword ptr [rax+rax+00h]
0x14003442f  test    al, al
0x140034431  jnz     loc_1400344E5
0x140034437  mov     rcx, rbp
0x14003443a  call    cs:__imp_PsGetThreadWin32Thread
0x140034441  nop     dword ptr [rax+rax+00h]
0x140034446  test    rax, rax
0x140034449  jz      short loc_14003444E
0x14003444b  mov     rdi, [rax]
0x14003444e  lea     rax, [rdi+8]
0x140034452  neg     rdi
0x140034455  sbb     rdx, rdx
0x140034458  and     rdx, rax
0x14003445b  jz      short loc_140034467
0x14003445d  add     byte ptr [rdx+9], 0FFh
0x140034461  jnz     short loc_140034467
0x140034463  and     qword ptr [rdx], 0FFFFFFFFFFFFFFFDh
0x140034467  lea     rcx, [rsi+270h]; HSEMAPHORE
0x14003446e  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140034473  mov     rbx, [rsp+48h+arg_8]
0x140034478  mov     rbp, [rsp+48h+arg_10]
0x14003447d  add     rsp, 30h
0x140034481  pop     r14
0x140034483  pop     rdi
0x140034484  pop     rsi
0x140034485  retn
0x140034487  call    W32GetCurrentWin32kSessionId
0x14003448c  mov     ebx, eax
0x14003448e  call    cs:__imp_PsGetCurrentThreadProcess
0x140034495  nop     dword ptr [rax+rax+00h]
0x14003449a  mov     rcx, rax
0x14003449d  call    cs:__imp_PsGetProcessSessionIdEx
0x1400344a4  nop     dword ptr [rax+rax+00h]
0x1400344a9  cmp     ebx, eax
0x1400344ab  jz      loc_140034361
0x1400344b1  jmp     loc_140034378
0x1400344b6  call    W32GetCurrentWin32kSessionId
0x1400344bb  mov     ebx, eax
0x1400344bd  call    cs:__imp_PsGetCurrentThreadProcess
0x1400344c4  nop     dword ptr [rax+rax+00h]
0x1400344c9  mov     rcx, rax
0x1400344cc  call    cs:__imp_PsGetProcessSessionIdEx
0x1400344d3  nop     dword ptr [rax+rax+00h]
0x1400344d8  cmp     ebx, eax
0x1400344da  jz      loc_1400343CC
0x1400344e0  jmp     loc_1400343E3
0x1400344e5  call    W32GetCurrentWin32kSessionId
0x1400344ea  mov     ebx, eax
0x1400344ec  call    cs:__imp_PsGetCurrentThreadProcess
0x1400344f3  nop     dword ptr [rax+rax+00h]
0x1400344f8  mov     rcx, rax
0x1400344fb  call    cs:__imp_PsGetProcessSessionIdEx
0x140034502  nop     dword ptr [rax+rax+00h]
0x140034507  cmp     ebx, eax
0x140034509  jz      loc_140034437
0x14003450f  jmp     loc_14003444E
0x140034514  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x14003451b  jz      loc_140034342
0x140034521  lea     rax, aDcvisrgn; "DCVisRgn"
0x140034528  lea     r9, [rsi+2D8h]
0x14003452f  mov     [rsp+48h+var_28], rax
0x140034534  lea     rdx, LockRelease
0x14003453b  call    McTemplateK0pz_EtwWriteTransfer
0x140034540  jmp     loc_140034342
0x140034545  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x14003454c  jz      loc_1400343AD
0x140034552  lea     rax, aGrelock; "GreLock"
0x140034559  lea     r9, [rsi+478h]
0x140034560  mov     [rsp+48h+var_28], rax
0x140034565  lea     rdx, LockRelease
0x14003456c  call    McTemplateK0pz_EtwWriteTransfer
0x140034571  jmp     loc_1400343AD
0x140034576  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x14003457d  jz      loc_140034418
0x140034583  lea     rax, aDynamicmodecha; "DynamicModeChange"
0x14003458a  lea     r9, [rsi+270h]
0x140034591  mov     [rsp+48h+var_28], rax
0x140034596  lea     rdx, LockRelease
0x14003459d  call    McTemplateK0pz_EtwWriteTransfer
0x1400345a2  jmp     loc_140034418
```
