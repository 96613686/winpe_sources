# _anonymous_namespace_::security_process_state::read_output

- ea: `0x180081660`
- end: `0x180081876`
- name: `_anonymous_namespace_::security_process_state::read_output`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800830e0`

## callees

- `0x180004510`
- `0x180005520`
- `0x18003af08`
- `0x1800511ac`
- `0x180081660`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800817b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800817b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081784`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800817bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800817ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800817d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081784`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800817bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800817ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800817d7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18008174b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180081795`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18008174b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180081795`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800817a4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800817a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800816e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800816e3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800816f3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800816f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800817e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081832`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800817e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081832`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180081769`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180081769`

## string_xrefs

- `0x180081844`: `read_output`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::security_process_state::read_output(
        __int64 a1,
        __int64 a2,
        DWORD a3,
        unsigned int a4)
{
  __int64 v4; // r15
  DWORD v7; // r12d
  LPVOID *v8; // r14
  HANDLE v9; // rbx
  void **v10; // rdi
  DWORD CurrentThreadId; // eax
  void *v12; // rdx
  struct _FILETIME *v13; // r8
  BOOL v14; // r12d
  DWORD LastError; // edi
  DWORD v16; // eax
  __int64 v18; // rdx
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-498h] BYREF
  __int64 v20; // [rsp+38h] [rbp-490h] BYREF
  HANDLE v21; // [rsp+40h] [rbp-488h]
  _BYTE pExceptionObject[1072]; // [rsp+50h] [rbp-478h] BYREF

  v4 = a4;
  v7 = 1024;
  if ( a3 )
    v7 = a3;
  if ( !*(_QWORD *)(a1 + 24) )
    goto LABEL_27;
  NumberOfBytesRead = 0;
  v8 = (LPVOID *)(a1 + 56);
  if ( (unsigned __int64)v7 > *(_QWORD *)(a1 + 64) - *(_QWORD *)(a1 + 56) )
    std::vector<unsigned char>::resize(a1 + 56);
  v9 = 0;
  v21 = 0;
  v10 = (void **)(a1 + 40);
  if ( !*(_QWORD *)(a1 + 32) || !*v10 && !(_DWORD)v4 )
    goto LABEL_17;
  CurrentThreadId = GetCurrentThreadId();
  v9 = OpenThread(0x100001u, 0, CurrentThreadId);
  v21 = v9;
  *(_QWORD *)(a1 + 48) = v9;
  v20 = 0;
  if ( (_DWORD)v4 )
    v20 = -10000000 * v4;
  v12 = *v10;
  if ( !*v10 )
  {
    if ( !v9 )
      goto LABEL_17;
    v12 = v9;
  }
  v13 = (struct _FILETIME *)&v20;
  if ( !(_DWORD)v4 )
    v13 = 0;
  SetThreadpoolWait(*(PTP_WAIT *)(a1 + 32), v12, v13);
LABEL_17:
  v14 = ReadFile(*(HANDLE *)(a1 + 24), *v8, v7, &NumberOfBytesRead, 0);
  if ( *(_QWORD *)(a1 + 32) && (*v10 || (_DWORD)v4) )
  {
    LastError = GetLastError();
    SetThreadpoolWait(*(PTP_WAIT *)(a1 + 32), 0, 0);
    WaitForThreadpoolWaitCallbacks(*(PTP_WAIT *)(a1 + 32), 1);
    *(_QWORD *)(a1 + 48) = 0;
    SetLastError(LastError);
  }
  if ( !v14 )
  {
    if ( GetLastError() != 109 && GetLastError() != 995 )
    {
      v16 = GetLastError();
      if ( v16 )
      {
        windiag::system_exception::system_exception(
          (windiag::system_exception *)pExceptionObject,
          v16,
          0,
          "[%s:%d] failed; ",
          "read_output",
          127);
        throw (windiag::system_exception *)pExceptionObject;
      }
    }
    if ( v9 )
      CloseHandle(v9);
LABEL_27:
    *(_BYTE *)(a2 + 16) = 0;
    return a2;
  }
  v18 = NumberOfBytesRead;
  *(_QWORD *)a2 = *v8;
  *(_QWORD *)(a2 + 8) = v18;
  *(_BYTE *)(a2 + 16) = 1;
  if ( v9 )
    CloseHandle(v9);
  return a2;
}

```

## disassembly

```asm
0x180081660  push    rbx
0x180081662  push    rbp
0x180081663  push    rsi
0x180081664  push    rdi
0x180081665  push    r12
0x180081667  push    r14
0x180081669  push    r15
0x18008166b  sub     rsp, 490h
0x180081672  mov     rax, cs:__security_cookie
0x180081679  xor     rax, rsp
0x18008167c  mov     [rsp+4C8h+var_48], rax
0x180081684  mov     r15d, r9d
0x180081687  mov     rsi, rdx
0x18008168a  mov     rbp, rcx
0x18008168d  mov     r12d, 400h
0x180081693  test    r8d, r8d
0x180081696  cmovnz  r12d, r8d
0x18008169a  cmp     qword ptr [rcx+18h], 0
0x18008169f  jz      loc_1800817EF
0x1800816a5  mov     [rsp+4C8h+NumberOfBytesRead], 0
0x1800816ad  lea     r14, [rcx+38h]
0x1800816b1  mov     edx, r12d
0x1800816b4  mov     rax, [r14+8]
0x1800816b8  sub     rax, [r14]
0x1800816bb  cmp     rdx, rax
0x1800816be  jbe     short loc_1800816C8
0x1800816c0  mov     rcx, r14
0x1800816c3  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800816c8  xor     ebx, ebx
0x1800816ca  mov     [rsp+4C8h+var_488], rbx
0x1800816cf  lea     rdi, [rbp+28h]
0x1800816d3  cmp     [rbp+20h], rbx
0x1800816d7  jz      short loc_180081751
0x1800816d9  cmp     [rdi], rbx
0x1800816dc  jnz     short loc_1800816E3
0x1800816de  test    r15d, r15d
0x1800816e1  jz      short loc_180081751
0x1800816e3  call    cs:__imp_GetCurrentThreadId
0x1800816e9  mov     r8d, eax; dwThreadId
0x1800816ec  xor     edx, edx; bInheritHandle
0x1800816ee  mov     ecx, 100001h; dwDesiredAccess
0x1800816f3  call    cs:__imp_OpenThread
0x1800816f9  mov     rbx, rax
0x1800816fc  mov     [rsp+4C8h+var_488], rax
0x180081701  mov     [rbp+30h], rax
0x180081705  mov     [rsp+4C8h+var_490], 0
0x18008170e  test    r15d, r15d
0x180081711  jz      short loc_180081729
0x180081713  imul    rax, r15, 0FFFFFFFFFF676980h
0x18008171a  mov     rcx, rax
0x18008171d  shr     rcx, 20h
0x180081721  mov     dword ptr [rsp+4C8h+var_490+4], ecx
0x180081725  mov     dword ptr [rsp+4C8h+var_490], eax
0x180081729  mov     rdx, [rdi]
0x18008172c  test    rdx, rdx
0x18008172f  jnz     short loc_180081739
0x180081731  test    rbx, rbx
0x180081734  jz      short loc_180081751
0x180081736  mov     rdx, rbx; h
0x180081739  lea     r8, [rsp+4C8h+var_490]
0x18008173e  xor     eax, eax
0x180081740  test    r15d, r15d
0x180081743  cmovz   r8, rax; pftTimeout
0x180081747  mov     rcx, [rbp+20h]; pwa
0x18008174b  call    cs:__imp_SetThreadpoolWait
0x180081751  mov     [rsp+4C8h+lpOverlapped], 0; lpOverlapped
0x18008175a  lea     r9, [rsp+4C8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18008175f  mov     r8d, r12d; nNumberOfBytesToRead
0x180081762  mov     rdx, [r14]; lpBuffer
0x180081765  mov     rcx, [rbp+18h]; hFile
0x180081769  call    cs:__imp_ReadFile
0x18008176f  mov     r12d, eax
0x180081772  cmp     qword ptr [rbp+20h], 0
0x180081777  jz      short loc_1800817BA
0x180081779  cmp     qword ptr [rdi], 0
0x18008177d  jnz     short loc_180081784
0x18008177f  test    r15d, r15d
0x180081782  jz      short loc_1800817BA
0x180081784  call    cs:__imp_GetLastError
0x18008178a  mov     edi, eax
0x18008178c  xor     r8d, r8d; pftTimeout
0x18008178f  xor     edx, edx; h
0x180081791  mov     rcx, [rbp+20h]; pwa
0x180081795  call    cs:__imp_SetThreadpoolWait
0x18008179b  mov     edx, 1; fCancelPendingCallbacks
0x1800817a0  mov     rcx, [rbp+20h]; pwa
0x1800817a4  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800817aa  mov     qword ptr [rbp+30h], 0
0x1800817b2  mov     ecx, edi; dwErrCode
0x1800817b4  call    cs:__imp_SetLastError
0x1800817ba  test    r12d, r12d
0x1800817bd  jnz     short loc_180081818
0x1800817bf  call    cs:__imp_GetLastError
0x1800817c5  cmp     eax, 6Dh ; 'm'
0x1800817c8  jz      short loc_1800817E1
0x1800817ca  call    cs:__imp_GetLastError
0x1800817d0  cmp     eax, 3E3h
0x1800817d5  jz      short loc_1800817E1
0x1800817d7  call    cs:__imp_GetLastError
0x1800817dd  test    eax, eax
0x1800817df  jnz     short loc_18008183A
0x1800817e1  test    rbx, rbx
0x1800817e4  jz      short loc_1800817EF
0x1800817e6  mov     rcx, rbx; hObject
0x1800817e9  call    cs:__imp_CloseHandle
0x1800817ef  mov     byte ptr [rsi+10h], 0
0x1800817f3  mov     rax, rsi
0x1800817f6  mov     rcx, [rsp+4C8h+var_48]
0x1800817fe  xor     rcx, rsp; StackCookie
0x180081801  call    __security_check_cookie
0x180081806  add     rsp, 490h
0x18008180d  pop     r15
0x18008180f  pop     r14
0x180081811  pop     r12
0x180081813  pop     rdi
0x180081814  pop     rsi
0x180081815  pop     rbp
0x180081816  pop     rbx
0x180081817  retn
0x180081818  mov     edx, [rsp+4C8h+NumberOfBytesRead]
0x18008181c  mov     rcx, [r14]
0x18008181f  mov     [rsi], rcx
0x180081822  mov     [rsi+8], rdx
0x180081826  mov     byte ptr [rsi+10h], 1
0x18008182a  test    rbx, rbx
0x18008182d  jz      short loc_1800817F3
0x18008182f  mov     rcx, rbx; hObject
0x180081832  call    cs:__imp_CloseHandle
0x180081838  jmp     short loc_1800817F3
0x18008183a  mov     edx, eax; __int64
0x18008183c  mov     [rsp+4C8h+var_4A0], 7Fh
0x180081844  lea     rax, aReadOutput; "read_output"
0x18008184b  mov     [rsp+4C8h+lpOverlapped], rax
0x180081850  lea     r9, aSDFailed; "[%s:%d] failed; "
0x180081857  xor     r8d, r8d; void *
0x18008185a  lea     rcx, [rsp+4C8h+pExceptionObject]; this
0x18008185f  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x180081864  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18008186b  lea     rcx, [rsp+4C8h+pExceptionObject]; pExceptionObject
0x180081870  call    _CxxThrowException_0
```
