# InitDwmInputProcessing

- ea: `0x14024a000`
- end: `0x14024a1b6`
- name: `InitDwmInputProcessing`
- size: `438`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14024a000`

## import_xrefs

- `win32kbase!?CreateSessionGlobal@CInputManager@@SAJXZ` at `0x14024a1a3`
- `win32kbase!?CreateSessionGlobal@CInputManager@@SAJXZ` at `0x14024a1a3`
- `win32kbase!CreateKernelSemaphore` at `0x14024a0f0`
- `win32kbase!CreateKernelSemaphore` at `0x14024a0f0`
- `win32kbase!hCreateKernelEvent` at `0x14024a01b`
- `win32kbase!hCreateKernelEvent` at `0x14024a041`
- `win32kbase!hCreateKernelEvent` at `0x14024a01b`
- `win32kbase!hCreateKernelEvent` at `0x14024a041`
- `win32kbase!CreateKernelEvent` at `0x14024a067`
- `win32kbase!CreateKernelEvent` at `0x14024a08d`
- `win32kbase!CreateKernelEvent` at `0x14024a0b3`
- `win32kbase!CreateKernelEvent` at `0x14024a067`
- `win32kbase!CreateKernelEvent` at `0x14024a08d`
- `win32kbase!CreateKernelEvent` at `0x14024a0b3`
- `WIN32K!W32GetUserSessionState` at `0x14024a02a`
- `WIN32K!W32GetUserSessionState` at `0x14024a050`
- `WIN32K!W32GetUserSessionState` at `0x14024a076`
- `WIN32K!W32GetUserSessionState` at `0x14024a09c`
- `WIN32K!W32GetUserSessionState` at `0x14024a0c2`
- `WIN32K!W32GetUserSessionState` at `0x14024a0d5`
- `WIN32K!W32GetUserSessionState` at `0x14024a0ff`
- `WIN32K!W32GetUserSessionState` at `0x14024a112`
- `WIN32K!W32GetUserSessionState` at `0x14024a13a`
- `WIN32K!W32GetUserSessionState` at `0x14024a14f`
- `WIN32K!W32GetUserSessionState` at `0x14024a164`
- `WIN32K!W32GetUserSessionState` at `0x14024a179`
- `WIN32K!W32GetUserSessionState` at `0x14024a18e`
- `WIN32K!W32GetUserSessionState` at `0x14024a02a`
- `WIN32K!W32GetUserSessionState` at `0x14024a050`
- `WIN32K!W32GetUserSessionState` at `0x14024a076`
- `WIN32K!W32GetUserSessionState` at `0x14024a09c`
- `WIN32K!W32GetUserSessionState` at `0x14024a0c2`
- `WIN32K!W32GetUserSessionState` at `0x14024a0d5`
- `WIN32K!W32GetUserSessionState` at `0x14024a0ff`
- `WIN32K!W32GetUserSessionState` at `0x14024a112`
- `WIN32K!W32GetUserSessionState` at `0x14024a13a`
- `WIN32K!W32GetUserSessionState` at `0x14024a14f`
- `WIN32K!W32GetUserSessionState` at `0x14024a164`
- `WIN32K!W32GetUserSessionState` at `0x14024a179`
- `WIN32K!W32GetUserSessionState` at `0x14024a18e`

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
0x14024a000  mov     [rsp+arg_0], rbx
0x14024a005  mov     [rsp+arg_8], rsi
0x14024a00a  push    rdi
0x14024a00b  sub     rsp, 20h
0x14024a00f  xor     edx, edx
0x14024a011  mov     edi, 0C0000017h
0x14024a016  lea     esi, [rdx+1]
0x14024a019  mov     ecx, esi
0x14024a01b  call    cs:__imp_hCreateKernelEvent
0x14024a022  nop     dword ptr [rax+rax+00h]
0x14024a027  mov     rbx, rax
0x14024a02a  call    cs:__imp_W32GetUserSessionState
0x14024a031  nop     dword ptr [rax+rax+00h]
0x14024a036  xor     edx, edx
0x14024a038  mov     ecx, esi
0x14024a03a  mov     [rax+4998h], rbx
0x14024a041  call    cs:__imp_hCreateKernelEvent
0x14024a048  nop     dword ptr [rax+rax+00h]
0x14024a04d  mov     rbx, rax
0x14024a050  call    cs:__imp_W32GetUserSessionState
0x14024a057  nop     dword ptr [rax+rax+00h]
0x14024a05c  xor     edx, edx
0x14024a05e  mov     ecx, esi
0x14024a060  mov     [rax+4970h], rbx
0x14024a067  call    cs:__imp_CreateKernelEvent
0x14024a06e  nop     dword ptr [rax+rax+00h]
0x14024a073  mov     rbx, rax
0x14024a076  call    cs:__imp_W32GetUserSessionState
0x14024a07d  nop     dword ptr [rax+rax+00h]
0x14024a082  xor     edx, edx
0x14024a084  mov     ecx, esi
0x14024a086  mov     [rax+4B80h], rbx
0x14024a08d  call    cs:__imp_CreateKernelEvent
0x14024a094  nop     dword ptr [rax+rax+00h]
0x14024a099  mov     rbx, rax
0x14024a09c  call    cs:__imp_W32GetUserSessionState
0x14024a0a3  nop     dword ptr [rax+rax+00h]
0x14024a0a8  xor     edx, edx
0x14024a0aa  mov     ecx, esi
0x14024a0ac  mov     [rax+49D8h], rbx
0x14024a0b3  call    cs:__imp_CreateKernelEvent
0x14024a0ba  nop     dword ptr [rax+rax+00h]
0x14024a0bf  mov     rbx, rax
0x14024a0c2  call    cs:__imp_W32GetUserSessionState
0x14024a0c9  nop     dword ptr [rax+rax+00h]
0x14024a0ce  mov     [rax+49B0h], rbx
0x14024a0d5  call    cs:__imp_W32GetUserSessionState
0x14024a0dc  nop     dword ptr [rax+rax+00h]
0x14024a0e1  xor     esi, esi
0x14024a0e3  mov     edx, 7FFFFFFFh
0x14024a0e8  xor     ecx, ecx
0x14024a0ea  mov     [rax+4B78h], esi
0x14024a0f0  call    cs:__imp_CreateKernelSemaphore
0x14024a0f7  nop     dword ptr [rax+rax+00h]
0x14024a0fc  mov     rbx, rax
0x14024a0ff  call    cs:__imp_W32GetUserSessionState
0x14024a106  nop     dword ptr [rax+rax+00h]
0x14024a10b  mov     [rax+4B70h], rbx
0x14024a112  call    cs:__imp_W32GetUserSessionState
0x14024a119  nop     dword ptr [rax+rax+00h]
0x14024a11e  cmp     [rax+4998h], rsi
0x14024a125  jnz     short loc_14024A13A
0x14024a127  mov     rbx, [rsp+28h+arg_0]
0x14024a12c  mov     eax, edi
0x14024a12e  mov     rsi, [rsp+28h+arg_8]
0x14024a133  add     rsp, 20h
0x14024a137  pop     rdi
0x14024a138  retn
0x14024a13a  call    cs:__imp_W32GetUserSessionState
0x14024a141  nop     dword ptr [rax+rax+00h]
0x14024a146  cmp     [rax+4970h], rsi
0x14024a14d  jz      short loc_14024A127
0x14024a14f  call    cs:__imp_W32GetUserSessionState
0x14024a156  nop     dword ptr [rax+rax+00h]
0x14024a15b  cmp     [rax+4B80h], rsi
0x14024a162  jz      short loc_14024A127
0x14024a164  call    cs:__imp_W32GetUserSessionState
0x14024a16b  nop     dword ptr [rax+rax+00h]
0x14024a170  cmp     [rax+49D8h], rsi
0x14024a177  jz      short loc_14024A127
0x14024a179  call    cs:__imp_W32GetUserSessionState
0x14024a180  nop     dword ptr [rax+rax+00h]
0x14024a185  cmp     [rax+49B0h], rsi
0x14024a18c  jz      short loc_14024A127
0x14024a18e  call    cs:__imp_W32GetUserSessionState
0x14024a195  nop     dword ptr [rax+rax+00h]
0x14024a19a  cmp     [rax+4B70h], rsi
0x14024a1a1  jz      short loc_14024A127
0x14024a1a3  call    cs:__imp_?CreateSessionGlobal@CInputManager@@SAJXZ; CInputManager::CreateSessionGlobal(void)
0x14024a1aa  nop     dword ptr [rax+rax+00h]
0x14024a1af  mov     edi, eax
0x14024a1b1  jmp     loc_14024A127
```
