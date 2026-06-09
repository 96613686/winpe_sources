# InitDwmInputProcessing

- ea: `0x14024b3e0`
- end: `0x14024b596`
- name: `InitDwmInputProcessing`
- size: `438`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14024b3e0`

## import_xrefs

- `win32kbase!?CreateSessionGlobal@CInputManager@@SAJXZ` at `0x14024b583`
- `win32kbase!?CreateSessionGlobal@CInputManager@@SAJXZ` at `0x14024b583`
- `win32kbase!CreateKernelSemaphore` at `0x14024b4d0`
- `win32kbase!CreateKernelSemaphore` at `0x14024b4d0`
- `win32kbase!hCreateKernelEvent` at `0x14024b3fb`
- `win32kbase!hCreateKernelEvent` at `0x14024b421`
- `win32kbase!hCreateKernelEvent` at `0x14024b3fb`
- `win32kbase!hCreateKernelEvent` at `0x14024b421`
- `win32kbase!CreateKernelEvent` at `0x14024b447`
- `win32kbase!CreateKernelEvent` at `0x14024b46d`
- `win32kbase!CreateKernelEvent` at `0x14024b493`
- `win32kbase!CreateKernelEvent` at `0x14024b447`
- `win32kbase!CreateKernelEvent` at `0x14024b46d`
- `win32kbase!CreateKernelEvent` at `0x14024b493`
- `WIN32K!W32GetUserSessionState` at `0x14024b40a`
- `WIN32K!W32GetUserSessionState` at `0x14024b430`
- `WIN32K!W32GetUserSessionState` at `0x14024b456`
- `WIN32K!W32GetUserSessionState` at `0x14024b47c`
- `WIN32K!W32GetUserSessionState` at `0x14024b4a2`
- `WIN32K!W32GetUserSessionState` at `0x14024b4b5`
- `WIN32K!W32GetUserSessionState` at `0x14024b4df`
- `WIN32K!W32GetUserSessionState` at `0x14024b4f2`
- `WIN32K!W32GetUserSessionState` at `0x14024b51a`
- `WIN32K!W32GetUserSessionState` at `0x14024b52f`
- `WIN32K!W32GetUserSessionState` at `0x14024b544`
- `WIN32K!W32GetUserSessionState` at `0x14024b559`
- `WIN32K!W32GetUserSessionState` at `0x14024b56e`
- `WIN32K!W32GetUserSessionState` at `0x14024b40a`
- `WIN32K!W32GetUserSessionState` at `0x14024b430`
- `WIN32K!W32GetUserSessionState` at `0x14024b456`
- `WIN32K!W32GetUserSessionState` at `0x14024b47c`
- `WIN32K!W32GetUserSessionState` at `0x14024b4a2`
- `WIN32K!W32GetUserSessionState` at `0x14024b4b5`
- `WIN32K!W32GetUserSessionState` at `0x14024b4df`
- `WIN32K!W32GetUserSessionState` at `0x14024b4f2`
- `WIN32K!W32GetUserSessionState` at `0x14024b51a`
- `WIN32K!W32GetUserSessionState` at `0x14024b52f`
- `WIN32K!W32GetUserSessionState` at `0x14024b544`
- `WIN32K!W32GetUserSessionState` at `0x14024b559`
- `WIN32K!W32GetUserSessionState` at `0x14024b56e`

## pseudocode

```c
__int64 InitDwmInputProcessing()
{
  unsigned int v0; // edi
  __int64 KernelEvent; // rbx
  __int64 v2; // rcx
  __int64 v3; // rbx
  __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 KernelSemaphore; // rbx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx

  v0 = -1073741801;
  KernelEvent = hCreateKernelEvent(1);
  *(_QWORD *)(W32GetUserSessionState(v2) + 18840) = KernelEvent;
  v3 = hCreateKernelEvent(1);
  *(_QWORD *)(W32GetUserSessionState(v4) + 18800) = v3;
  v5 = CreateKernelEvent(1, 0);
  *(_QWORD *)(W32GetUserSessionState(v6) + 19328) = v5;
  v7 = CreateKernelEvent(1, 0);
  *(_QWORD *)(W32GetUserSessionState(v8) + 18904) = v7;
  v9 = CreateKernelEvent(1, 0);
  *(_QWORD *)(W32GetUserSessionState(v10) + 18864) = v9;
  *(_DWORD *)(W32GetUserSessionState(v11) + 19320) = 0;
  KernelSemaphore = CreateKernelSemaphore(0, 0x7FFFFFFF);
  *(_QWORD *)(W32GetUserSessionState(v13) + 19312) = KernelSemaphore;
  if ( *(_QWORD *)(W32GetUserSessionState(v14) + 18840)
    && *(_QWORD *)(W32GetUserSessionState(v15) + 18800)
    && *(_QWORD *)(W32GetUserSessionState(v17) + 19328)
    && *(_QWORD *)(W32GetUserSessionState(v18) + 18904)
    && *(_QWORD *)(W32GetUserSessionState(v19) + 18864)
    && *(_QWORD *)(W32GetUserSessionState(v20) + 19312) )
  {
    return (unsigned int)CInputManager::CreateSessionGlobal();
  }
  return v0;
}

```

## disassembly

```asm
0x14024b3e0  mov     [rsp+arg_0], rbx
0x14024b3e5  mov     [rsp+arg_8], rsi
0x14024b3ea  push    rdi
0x14024b3eb  sub     rsp, 20h
0x14024b3ef  xor     edx, edx
0x14024b3f1  mov     edi, 0C0000017h
0x14024b3f6  lea     esi, [rdx+1]
0x14024b3f9  mov     ecx, esi
0x14024b3fb  call    cs:__imp_hCreateKernelEvent
0x14024b402  nop     dword ptr [rax+rax+00h]
0x14024b407  mov     rbx, rax
0x14024b40a  call    cs:__imp_W32GetUserSessionState
0x14024b411  nop     dword ptr [rax+rax+00h]
0x14024b416  xor     edx, edx
0x14024b418  mov     ecx, esi
0x14024b41a  mov     [rax+4998h], rbx
0x14024b421  call    cs:__imp_hCreateKernelEvent
0x14024b428  nop     dword ptr [rax+rax+00h]
0x14024b42d  mov     rbx, rax
0x14024b430  call    cs:__imp_W32GetUserSessionState
0x14024b437  nop     dword ptr [rax+rax+00h]
0x14024b43c  xor     edx, edx
0x14024b43e  mov     ecx, esi
0x14024b440  mov     [rax+4970h], rbx
0x14024b447  call    cs:__imp_CreateKernelEvent
0x14024b44e  nop     dword ptr [rax+rax+00h]
0x14024b453  mov     rbx, rax
0x14024b456  call    cs:__imp_W32GetUserSessionState
0x14024b45d  nop     dword ptr [rax+rax+00h]
0x14024b462  xor     edx, edx
0x14024b464  mov     ecx, esi
0x14024b466  mov     [rax+4B80h], rbx
0x14024b46d  call    cs:__imp_CreateKernelEvent
0x14024b474  nop     dword ptr [rax+rax+00h]
0x14024b479  mov     rbx, rax
0x14024b47c  call    cs:__imp_W32GetUserSessionState
0x14024b483  nop     dword ptr [rax+rax+00h]
0x14024b488  xor     edx, edx
0x14024b48a  mov     ecx, esi
0x14024b48c  mov     [rax+49D8h], rbx
0x14024b493  call    cs:__imp_CreateKernelEvent
0x14024b49a  nop     dword ptr [rax+rax+00h]
0x14024b49f  mov     rbx, rax
0x14024b4a2  call    cs:__imp_W32GetUserSessionState
0x14024b4a9  nop     dword ptr [rax+rax+00h]
0x14024b4ae  mov     [rax+49B0h], rbx
0x14024b4b5  call    cs:__imp_W32GetUserSessionState
0x14024b4bc  nop     dword ptr [rax+rax+00h]
0x14024b4c1  xor     esi, esi
0x14024b4c3  mov     edx, 7FFFFFFFh
0x14024b4c8  xor     ecx, ecx
0x14024b4ca  mov     [rax+4B78h], esi
0x14024b4d0  call    cs:__imp_CreateKernelSemaphore
0x14024b4d7  nop     dword ptr [rax+rax+00h]
0x14024b4dc  mov     rbx, rax
0x14024b4df  call    cs:__imp_W32GetUserSessionState
0x14024b4e6  nop     dword ptr [rax+rax+00h]
0x14024b4eb  mov     [rax+4B70h], rbx
0x14024b4f2  call    cs:__imp_W32GetUserSessionState
0x14024b4f9  nop     dword ptr [rax+rax+00h]
0x14024b4fe  cmp     [rax+4998h], rsi
0x14024b505  jnz     short loc_14024B51A
0x14024b507  mov     rbx, [rsp+28h+arg_0]
0x14024b50c  mov     eax, edi
0x14024b50e  mov     rsi, [rsp+28h+arg_8]
0x14024b513  add     rsp, 20h
0x14024b517  pop     rdi
0x14024b518  retn
0x14024b51a  call    cs:__imp_W32GetUserSessionState
0x14024b521  nop     dword ptr [rax+rax+00h]
0x14024b526  cmp     [rax+4970h], rsi
0x14024b52d  jz      short loc_14024B507
0x14024b52f  call    cs:__imp_W32GetUserSessionState
0x14024b536  nop     dword ptr [rax+rax+00h]
0x14024b53b  cmp     [rax+4B80h], rsi
0x14024b542  jz      short loc_14024B507
0x14024b544  call    cs:__imp_W32GetUserSessionState
0x14024b54b  nop     dword ptr [rax+rax+00h]
0x14024b550  cmp     [rax+49D8h], rsi
0x14024b557  jz      short loc_14024B507
0x14024b559  call    cs:__imp_W32GetUserSessionState
0x14024b560  nop     dword ptr [rax+rax+00h]
0x14024b565  cmp     [rax+49B0h], rsi
0x14024b56c  jz      short loc_14024B507
0x14024b56e  call    cs:__imp_W32GetUserSessionState
0x14024b575  nop     dword ptr [rax+rax+00h]
0x14024b57a  cmp     [rax+4B70h], rsi
0x14024b581  jz      short loc_14024B507
0x14024b583  call    cs:__imp_?CreateSessionGlobal@CInputManager@@SAJXZ; CInputManager::CreateSessionGlobal(void)
0x14024b58a  nop     dword ptr [rax+rax+00h]
0x14024b58f  mov     edi, eax
0x14024b591  jmp     loc_14024B507
```
