# SvcResetPhoneInternal(void *,_BF_SCENARIO,_BF_OPTION,ulong,ulong)

- ea: `0x18003a624`
- end: `0x18003a77c`
- name: `?SvcResetPhoneInternal@@YAJPEAXW4_BF_SCENARIO@@W4_BF_OPTION@@KK@Z`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003a790`

## callees

- `0x18003a624`
- `0x18003c758`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a6ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a6ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003a6b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003a6b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a70f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a728`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a70f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a728`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003a6e0`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003a6e0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003a757`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003a757`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003a6a4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003a6a4`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18003a67f`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18003a67f`

## pseudocode

```c
__int64 __fastcall SvcResetPhoneInternal(void *a1, __int64 a2, unsigned int a3, unsigned int a4, unsigned int a5)
{
  DWORD v5; // ebp
  unsigned __int64 v7; // rsi
  HANDLE v9; // rdi
  signed int v10; // ebx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int Pid; // [rsp+70h] [rbp+18h] BYREF

  Pid = a3;
  v5 = a5;
  v7 = a4;
  if ( a4 && a5 > 0x1D4C0 )
    return 2147942487LL;
  v9 = 0;
  v10 = BfSetScenario(1);
  if ( v10 < 0 )
    goto LABEL_13;
  Pid = 0;
  if ( I_RpcBindingInqLocalClientPID(a1, &Pid) )
  {
    v10 = -2147467259;
LABEL_13:
    if ( TargetHandle )
    {
      CloseHandle(TargetHandle);
      TargetHandle = 0;
    }
    if ( v9 )
      CloseHandle(v9);
    BfSetScenario(0);
    dword_1800C08F8 = 0;
    return (unsigned int)v10;
  }
  if ( (_DWORD)v7 )
  {
    v9 = OpenProcess(0xFFFFFu, 0, Pid);
    if ( !v9
      || (CurrentProcess = GetCurrentProcess(), !DuplicateHandle(
                                                   v9,
                                                   (HANDLE)v7,
                                                   CurrentProcess,
                                                   &TargetHandle,
                                                   0,
                                                   0,
                                                   2u)) )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      if ( v10 >= 0 )
        return (unsigned int)v10;
      goto LABEL_13;
    }
  }
  else
  {
    TargetHandle = 0;
  }
  v10 = 0;
  dwMilliseconds = v5;
  SubmitThreadpoolWork(qword_1800C08F0);
  dword_1800C08F8 = 1;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003a624  mov     [rsp+arg_0], rbx
0x18003a629  mov     [rsp+arg_8], rbp
0x18003a62e  mov     [rsp+Pid], r8d
0x18003a633  push    rsi
0x18003a634  push    rdi
0x18003a635  push    r14
0x18003a637  sub     rsp, 40h
0x18003a63b  mov     ebp, [rsp+58h+arg_20]
0x18003a642  mov     r14, rcx
0x18003a645  mov     esi, r9d
0x18003a648  test    r9d, r9d
0x18003a64b  jz      short loc_18003A65F
0x18003a64d  cmp     ebp, 1D4C0h
0x18003a653  jbe     short loc_18003A65F
0x18003a655  mov     eax, 80070057h
0x18003a65a  jmp     loc_18003A769
0x18003a65f  xor     edi, edi
0x18003a661  lea     ecx, [rdi+1]
0x18003a664  call    BfSetScenario
0x18003a669  mov     ebx, eax
0x18003a66b  test    eax, eax
0x18003a66d  js      loc_18003A703
0x18003a673  lea     rdx, [rsp+58h+Pid]; Pid
0x18003a678  mov     [rsp+58h+Pid], edi
0x18003a67c  mov     rcx, r14; Binding
0x18003a67f  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18003a685  test    eax, eax
0x18003a687  jz      short loc_18003A690
0x18003a689  mov     ebx, 80004005h
0x18003a68e  jmp     short loc_18003A703
0x18003a690  test    esi, esi
0x18003a692  jz      loc_18003A741
0x18003a698  mov     r8d, [rsp+58h+Pid]; dwProcessId
0x18003a69d  xor     edx, edx; bInheritHandle
0x18003a69f  mov     ecx, 0FFFFFh; dwDesiredAccess
0x18003a6a4  call    cs:__imp_OpenProcess
0x18003a6aa  mov     rdi, rax
0x18003a6ad  test    rax, rax
0x18003a6b0  jz      short loc_18003A6EA
0x18003a6b2  call    cs:__imp_GetCurrentProcess
0x18003a6b8  mov     [rsp+58h+dwOptions], 2; dwOptions
0x18003a6c0  lea     r9, TargetHandle; lpTargetHandle
0x18003a6c7  mov     r8, rax; hTargetProcessHandle
0x18003a6ca  mov     [rsp+58h+bInheritHandle], 0; bInheritHandle
0x18003a6d2  mov     rdx, rsi; hSourceHandle
0x18003a6d5  mov     [rsp+58h+dwDesiredAccess], 0; dwDesiredAccess
0x18003a6dd  mov     rcx, rdi; hSourceProcessHandle
0x18003a6e0  call    cs:__imp_DuplicateHandle
0x18003a6e6  test    eax, eax
0x18003a6e8  jnz     short loc_18003A748
0x18003a6ea  call    cs:__imp_GetLastError
0x18003a6f0  mov     ebx, eax
0x18003a6f2  test    eax, eax
0x18003a6f4  jle     short loc_18003A6FF
0x18003a6f6  movzx   ebx, ax
0x18003a6f9  or      ebx, 80070000h
0x18003a6ff  test    ebx, ebx
0x18003a701  jns     short loc_18003A767
0x18003a703  mov     rcx, cs:TargetHandle; hObject
0x18003a70a  test    rcx, rcx
0x18003a70d  jz      short loc_18003A720
0x18003a70f  call    cs:__imp_CloseHandle
0x18003a715  mov     cs:TargetHandle, 0
0x18003a720  test    rdi, rdi
0x18003a723  jz      short loc_18003A72E
0x18003a725  mov     rcx, rdi; hObject
0x18003a728  call    cs:__imp_CloseHandle
0x18003a72e  xor     ecx, ecx
0x18003a730  call    BfSetScenario
0x18003a735  mov     cs:dword_1800C08F8, 0
0x18003a73f  jmp     short loc_18003A767
0x18003a741  mov     cs:TargetHandle, rdi
0x18003a748  mov     rcx, cs:qword_1800C08F0; pwk
0x18003a74f  xor     ebx, ebx
0x18003a751  mov     cs:dwMilliseconds, ebp
0x18003a757  call    cs:__imp_SubmitThreadpoolWork
0x18003a75d  mov     cs:dword_1800C08F8, 1
0x18003a767  mov     eax, ebx
0x18003a769  mov     rbx, [rsp+58h+arg_0]
0x18003a76e  mov     rbp, [rsp+58h+arg_8]
0x18003a773  add     rsp, 40h
0x18003a777  pop     r14
0x18003a779  pop     rdi
0x18003a77a  pop     rsi
0x18003a77b  retn
```
