# s_RunThread

- ea: `0x18007e6a0`
- end: `0x18007e82a`
- name: `s_RunThread`
- size: `394`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update`

## callees

- `0x18007e6a0`
- `0x18007e830`
- `0x18007e8e4`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e705`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e705`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18007e6d1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18007e6d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007e71c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007e729`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007e71c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007e729`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007e6ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007e6ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e7a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e7a0`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18007e754`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18007e754`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18007e6e5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18007e6e5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x18007e804`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x18007e804`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x18007e7fa`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x18007e7fa`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetMessageW` at `0x18007e7ec`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetMessageW` at `0x18007e7ec`
- `api-ms-win-shcore-thread-l1-1-0!SHSetThreadRef` at `0x18007e78d`
- `api-ms-win-shcore-thread-l1-1-0!SHSetThreadRef` at `0x18007e7ac`
- `api-ms-win-shcore-thread-l1-1-0!SHSetThreadRef` at `0x18007e78d`
- `api-ms-win-shcore-thread-l1-1-0!SHSetThreadRef` at `0x18007e7ac`

## pseudocode

```c
__int64 __fastcall s_RunThread(RTL_SRWLOCK *Parameter)
{
  bool v2; // si
  HWND *Ptr; // rcx
  DWORD WindowThreadProcessId; // ebx
  HANDLE CurrentProcess; // rax
  PVOID v6; // rdi
  void *v7; // rbx
  HANDLE v8; // rax
  int v10; // [rsp+48h] [rbp-1h] BYREF
  IUnknown *punk; // [rsp+50h] [rbp+7h] BYREF
  struct tagMSG Msg; // [rsp+58h] [rbp+Fh] BYREF
  HANDLE TargetHandle; // [rsp+B0h] [rbp+67h] BYREF

  if ( SLODWORD(Parameter[16].Ptr) >= 0 )
  {
    v2 = 0;
    AcquireSRWLockShared(Parameter + 13);
    Ptr = (HWND *)Parameter[14].Ptr;
    if ( Ptr )
    {
      WindowThreadProcessId = GetWindowThreadProcessId(*Ptr, 0);
      v2 = WindowThreadProcessId == GetCurrentThreadId();
    }
    ReleaseSRWLockShared(Parameter + 13);
    if ( v2 )
    {
      TargetHandle = 0;
      CurrentProcess = GetCurrentProcess();
      v6 = Parameter[15].Ptr;
      v7 = CurrentProcess;
      v8 = GetCurrentProcess();
      if ( DuplicateHandle(v8, v6, v7, &TargetHandle, 0, 0, 2u) )
      {
        v10 = 0;
        punk = 0;
        SHCreateDUIThreadRef(&v10, &punk);
        SHSetThreadRef(punk);
        CSettingsFlow::s_RunMessageLoop(TargetHandle);
        CloseHandle(TargetHandle);
        SHSetThreadRef(0);
        if ( punk )
        {
          ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
          punk = 0;
        }
        while ( v10 )
        {
          memset(&Msg, 0, sizeof(Msg));
          if ( GetMessageW(&Msg, 0, 0, 0) )
          {
            TranslateMessage(&Msg);
            DispatchMessageW(&Msg);
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18007e6a0  mov     [rsp-8+arg_8], rbx
0x18007e6a5  mov     [rsp-8+arg_10], rsi
0x18007e6aa  push    rbp
0x18007e6ab  push    rdi
0x18007e6ac  push    r14
0x18007e6ae  lea     rbp, [rsp-47h]
0x18007e6b3  sub     rsp, 90h
0x18007e6ba  cmp     dword ptr [rcx+80h], 0
0x18007e6c1  mov     rdi, rcx
0x18007e6c4  jl      loc_18007E810
0x18007e6ca  add     rcx, 68h ; 'h'; SRWLock
0x18007e6ce  xor     sil, sil
0x18007e6d1  call    cs:__imp_AcquireSRWLockShared
0x18007e6d7  mov     rcx, [rdi+70h]
0x18007e6db  test    rcx, rcx
0x18007e6de  jz      short loc_18007E701
0x18007e6e0  mov     rcx, [rcx]; hWnd
0x18007e6e3  xor     edx, edx; lpdwProcessId
0x18007e6e5  call    cs:__imp_GetWindowThreadProcessId
0x18007e6eb  mov     ebx, eax
0x18007e6ed  call    cs:__imp_GetCurrentThreadId
0x18007e6f3  movzx   esi, sil
0x18007e6f7  mov     ecx, 1
0x18007e6fc  cmp     ebx, eax
0x18007e6fe  cmovz   esi, ecx
0x18007e701  lea     rcx, [rdi+68h]; SRWLock
0x18007e705  call    cs:__imp_ReleaseSRWLockShared
0x18007e70b  test    sil, sil
0x18007e70e  jz      loc_18007E810
0x18007e714  mov     [rbp+57h+TargetHandle], 0
0x18007e71c  call    cs:__imp_GetCurrentProcess
0x18007e722  mov     rdi, [rdi+78h]
0x18007e726  mov     rbx, rax
0x18007e729  call    cs:__imp_GetCurrentProcess
0x18007e72f  mov     [rsp+0A0h+dwOptions], 2; dwOptions
0x18007e737  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x18007e73b  mov     rcx, rax; hSourceProcessHandle
0x18007e73e  mov     [rsp+0A0h+bInheritHandle], 0; bInheritHandle
0x18007e746  mov     r8, rbx; hTargetProcessHandle
0x18007e749  mov     [rsp+0A0h+dwDesiredAccess], 0; dwDesiredAccess
0x18007e751  mov     rdx, rdi; hSourceHandle
0x18007e754  call    cs:__imp_DuplicateHandle
0x18007e75a  test    eax, eax
0x18007e75c  jz      loc_18007E810
0x18007e762  lea     rbx, ??_7CThreadRefHost@@6B@; const CThreadRefHost::`vftable'
0x18007e769  mov     [rbp+57h+var_58], 0
0x18007e770  lea     rdx, [rbp+57h+punk]; struct IUnknown **
0x18007e774  mov     [rbp+57h+var_60], rbx
0x18007e778  lea     rcx, [rbp+57h+var_58]; int *
0x18007e77c  mov     [rbp+57h+punk], 0
0x18007e784  call    ?SHCreateDUIThreadRef@@YAJPEAJPEAPEAUIUnknown@@@Z; SHCreateDUIThreadRef(long *,IUnknown * *)
0x18007e789  mov     rcx, [rbp+57h+punk]; punk
0x18007e78d  call    cs:__imp_SHSetThreadRef
0x18007e793  mov     rcx, [rbp+57h+TargetHandle]; void *
0x18007e797  call    ?s_RunMessageLoop@CSettingsFlow@@CAJPEAX@Z; CSettingsFlow::s_RunMessageLoop(void *)
0x18007e79c  mov     rcx, [rbp+57h+TargetHandle]; hObject
0x18007e7a0  call    cs:__imp_CloseHandle
0x18007e7a6  xor     ecx, ecx; punk
0x18007e7a8  mov     [rbp+57h+var_60], rbx
0x18007e7ac  call    cs:__imp_SHSetThreadRef
0x18007e7b2  mov     rcx, [rbp+57h+punk]
0x18007e7b6  test    rcx, rcx
0x18007e7b9  jz      short loc_18007E80A
0x18007e7bb  mov     rax, [rcx]
0x18007e7be  mov     rax, [rax+10h]
0x18007e7c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e7c7  mov     [rbp+57h+punk], 0
0x18007e7cf  jmp     short loc_18007E80A
0x18007e7d1  xorps   xmm0, xmm0
0x18007e7d4  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18007e7d8  xor     r9d, r9d; wMsgFilterMax
0x18007e7db  xor     r8d, r8d; wMsgFilterMin
0x18007e7de  xor     edx, edx; hWnd
0x18007e7e0  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x18007e7e4  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x18007e7e8  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x18007e7ec  call    cs:__imp_GetMessageW
0x18007e7f2  test    eax, eax
0x18007e7f4  jz      short loc_18007E80A
0x18007e7f6  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18007e7fa  call    cs:__imp_TranslateMessage
0x18007e800  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18007e804  call    cs:__imp_DispatchMessageW
0x18007e80a  cmp     [rbp+57h+var_58], 0
0x18007e80e  jnz     short loc_18007E7D1
0x18007e810  lea     r11, [rsp+0A0h+var_10]
0x18007e818  xor     eax, eax
0x18007e81a  mov     rbx, [r11+28h]
0x18007e81e  mov     rsi, [r11+30h]
0x18007e822  mov     rsp, r11
0x18007e825  pop     r14
0x18007e827  pop     rdi
0x18007e828  pop     rbp
0x18007e829  retn
```
