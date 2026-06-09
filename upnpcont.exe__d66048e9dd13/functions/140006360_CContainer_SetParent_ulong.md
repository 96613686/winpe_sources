# CContainer::SetParent(ulong)

- ea: `0x140006360`
- end: `0x1400063f9`
- name: `?SetParent@CContainer@@UEAAJK@Z`
- size: `153`
- prototype: `__int64 __fastcall(CContainer *this, DWORD)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006360`
- `0x14000656c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400063dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400063dd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1400063b5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1400063b5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140006374`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140006374`

## pseudocode

```c
__int64 __fastcall CContainer::SetParent(CContainer *this, DWORD a2)
{
  HANDLE v2; // rax
  void *v3; // rbx
  unsigned int v4; // edi

  v2 = OpenProcess(0x100000u, 0, a2);
  v3 = v2;
  if ( !v2 )
    return (unsigned int)HrFromLastWin32Error();
  v4 = 0;
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&CContainer::s_hParentProc, (signed __int64)v2, 0) )
    goto LABEL_5;
  if ( !RegisterWaitForSingleObject(
          &CContainer::s_hProcessDiedWait,
          v2,
          (WAITORTIMERCALLBACK)CContainer::KillThread,
          0,
          0xFFFFFFFF,
          8u) )
  {
    v4 = -2147467259;
    CContainer::s_hProcessDiedWait = 0;
    CContainer::s_hParentProc = 0;
LABEL_5:
    CloseHandle(v3);
  }
  return v4;
}

```

## disassembly

```asm
0x140006360  mov     [rsp+arg_0], rbx
0x140006365  push    rdi
0x140006366  sub     rsp, 30h
0x14000636a  mov     r8d, edx; dwProcessId
0x14000636d  mov     ecx, 100000h; dwDesiredAccess
0x140006372  xor     edx, edx; bInheritHandle
0x140006374  call    cs:__imp_OpenProcess
0x14000637a  mov     rbx, rax
0x14000637d  test    rax, rax
0x140006380  jz      short loc_1400063E5
0x140006382  xor     edi, edi
0x140006384  xor     eax, eax
0x140006386  lock cmpxchg cs:?s_hParentProc@CContainer@@0PEAXEA, rbx; void * CContainer::s_hParentProc
0x14000638f  jnz     short loc_1400063DA
0x140006391  mov     [rsp+38h+dwFlags], 8; dwFlags
0x140006399  lea     r8, ?KillThread@CContainer@@CAXPEAXE@Z; Callback
0x1400063a0  xor     r9d, r9d; Context
0x1400063a3  mov     [rsp+38h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x1400063ab  mov     rdx, rbx; hObject
0x1400063ae  lea     rcx, ?s_hProcessDiedWait@CContainer@@0PEAXEA; phNewWaitObject
0x1400063b5  call    cs:__imp_RegisterWaitForSingleObject
0x1400063bb  test    eax, eax
0x1400063bd  jnz     short loc_1400063EC
0x1400063bf  mov     edi, 80004005h
0x1400063c4  mov     cs:?s_hProcessDiedWait@CContainer@@0PEAXEA, 0; void * CContainer::s_hProcessDiedWait
0x1400063cf  mov     cs:?s_hParentProc@CContainer@@0PEAXEA, 0; void * CContainer::s_hParentProc
0x1400063da  mov     rcx, rbx; hObject
0x1400063dd  call    cs:__imp_CloseHandle
0x1400063e3  jmp     short loc_1400063EC
0x1400063e5  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1400063ea  mov     edi, eax
0x1400063ec  mov     rbx, [rsp+38h+arg_0]
0x1400063f1  mov     eax, edi
0x1400063f3  add     rsp, 30h
0x1400063f7  pop     rdi
0x1400063f8  retn
```
