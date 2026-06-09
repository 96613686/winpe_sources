# PfsIdleTaskMgrRegisterInternal

- ea: `0x180064c68`
- end: `0x180064e55`
- name: `PfsIdleTaskMgrRegisterInternal`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180064c38`

## callees

- `0x180059164`
- `0x180059264`
- `0x180064c68`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180064d48`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180064db6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180064d48`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180064db6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180064d57`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180064e02`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180064d57`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180064e02`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180064cc7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180064cea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180064cc7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180064cea`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180064df9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180064df9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064cd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064cf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064cd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064cf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064d03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064d11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064d03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064d11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064d27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064e38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064d27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064e38`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064ca0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064d6e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064ca0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064d6e`

## pseudocode

```c
__int64 __fastcall PfsIdleTaskMgrRegisterInternal(_QWORD *a1, HANDLE **a2, _QWORD *a3, _QWORD *a4)
{
  _QWORD *v5; // rbx
  HANDLE *v7; // rsi
  DWORD LastError; // ebx
  void *v9; // rdi
  HANDLE EventW; // r12
  HANDLE v11; // rax
  void *v12; // r14
  _OWORD *v13; // rax
  _QWORD *v14; // rcx

  v5 = a3;
  v7 = (HANDLE *)HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, 0x20u);
  if ( !v7 )
    return 8;
  v9 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  if ( EventW )
  {
    v11 = CreateEventW(0, 1, 0, 0);
    v12 = v11;
    if ( !v11 )
    {
      LastError = GetLastError();
      goto LABEL_7;
    }
    v7[2] = 0;
    v7[3] = 0;
    *v7 = EventW;
    v7[1] = v11;
    RtlAcquireSRWLockExclusive(a1 + 3);
    if ( (_QWORD *)*a1 == a1 )
    {
      RtlReleaseSRWLockExclusive(a1 + 3);
      v13 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, 0x20u);
      v9 = v13;
      if ( !v13 )
      {
        LastError = 8;
        goto LABEL_7;
      }
      *v13 = 0;
      *((_QWORD *)v13 + 2) = 0;
      *((_QWORD *)v13 + 3) = a1;
      LastError = PfsWorkerStart(v13, PfsIdleTaskMgrWorker, v13, 0);
      if ( LastError )
      {
LABEL_7:
        CloseHandle(EventW);
        if ( v12 )
          CloseHandle(v12);
        goto LABEL_9;
      }
      RtlAcquireSRWLockExclusive(a1 + 3);
      v5 = a3;
      if ( !a1[2] )
      {
        a1[2] = v9;
        v9 = 0;
      }
    }
    v14 = (_QWORD *)a1[1];
    if ( (_QWORD *)*v14 != a1 )
      __fastfail(3u);
    v7[2] = a1;
    v7[3] = v14;
    *v14 = v7 + 2;
    a1[1] = v7 + 2;
    if ( (a1[4] & 1) != 0 )
      SetEvent(*v7);
    RtlReleaseSRWLockExclusive(a1 + 3);
    *a2 = v7;
    *v5 = EventW;
    LastError = 0;
    *a4 = v12;
    goto LABEL_21;
  }
  LastError = GetLastError();
LABEL_9:
  HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v7);
LABEL_21:
  if ( v9 )
  {
    PfsWorkerStop(v9, 0);
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v9);
  }
  return LastError;
}

```

## disassembly

```asm
0x180064c68  mov     [rsp+arg_0], rbx
0x180064c6d  mov     [rsp+arg_10], r8
0x180064c72  mov     [rsp+arg_8], rdx
0x180064c77  push    rbp
0x180064c78  push    rsi
0x180064c79  push    rdi
0x180064c7a  push    r12
0x180064c7c  push    r13
0x180064c7e  push    r14
0x180064c80  push    r15
0x180064c82  sub     rsp, 20h
0x180064c86  mov     rbp, rcx
0x180064c89  xor     edx, edx; dwFlags
0x180064c8b  mov     rcx, cs:PfSvcGlobals
0x180064c92  mov     rbx, r8
0x180064c95  mov     r13, r9
0x180064c98  lea     r8d, [rdx+20h]; dwBytes
0x180064c9c  mov     rcx, [rcx+58h]; hHeap
0x180064ca0  call    cs:__imp_HeapAlloc
0x180064ca6  mov     rsi, rax
0x180064ca9  test    rax, rax
0x180064cac  jnz     short loc_180064CB6
0x180064cae  lea     ebx, [rax+8]
0x180064cb1  jmp     loc_180064E3E
0x180064cb6  xor     edi, edi
0x180064cb8  xor     r9d, r9d; lpName
0x180064cbb  xor     r8d, r8d; bInitialState
0x180064cbe  xor     ecx, ecx; lpEventAttributes
0x180064cc0  lea     r14d, [rdi+1]
0x180064cc4  mov     edx, r14d; bManualReset
0x180064cc7  call    cs:__imp_CreateEventW
0x180064ccd  mov     r12, rax
0x180064cd0  test    rax, rax
0x180064cd3  jnz     short loc_180064CDF
0x180064cd5  call    cs:__imp_GetLastError
0x180064cdb  mov     ebx, eax
0x180064cdd  jmp     short loc_180064D17
0x180064cdf  xor     r9d, r9d; lpName
0x180064ce2  xor     r8d, r8d; bInitialState
0x180064ce5  mov     edx, r14d; bManualReset
0x180064ce8  xor     ecx, ecx; lpEventAttributes
0x180064cea  call    cs:__imp_CreateEventW
0x180064cf0  mov     r14, rax
0x180064cf3  test    rax, rax
0x180064cf6  jnz     short loc_180064D32
0x180064cf8  call    cs:__imp_GetLastError
0x180064cfe  mov     ebx, eax
0x180064d00  mov     rcx, r12; hObject
0x180064d03  call    cs:__imp_CloseHandle
0x180064d09  test    r14, r14
0x180064d0c  jz      short loc_180064D17
0x180064d0e  mov     rcx, r14; hObject
0x180064d11  call    cs:__imp_CloseHandle
0x180064d17  mov     rcx, cs:PfSvcGlobals
0x180064d1e  mov     r8, rsi; lpMem
0x180064d21  xor     edx, edx; dwFlags
0x180064d23  mov     rcx, [rcx+58h]; hHeap
0x180064d27  call    cs:__imp_HeapFree
0x180064d2d  jmp     loc_180064E19
0x180064d32  mov     [rsi+10h], rdi
0x180064d36  lea     r15, [rbp+18h]
0x180064d3a  mov     [rsi+18h], rdi
0x180064d3e  mov     rcx, r15
0x180064d41  mov     [rsi], r12
0x180064d44  mov     [rsi+8], r14
0x180064d48  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180064d4e  cmp     [rbp+0], rbp
0x180064d52  jnz     short loc_180064DCE
0x180064d54  mov     rcx, r15
0x180064d57  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180064d5d  mov     rcx, cs:PfSvcGlobals
0x180064d64  xor     edx, edx; dwFlags
0x180064d66  mov     rcx, [rcx+58h]; hHeap
0x180064d6a  lea     r8d, [rdx+20h]; dwBytes
0x180064d6e  call    cs:__imp_HeapAlloc
0x180064d74  mov     rdi, rax
0x180064d77  test    rax, rax
0x180064d7a  jnz     short loc_180064D84
0x180064d7c  lea     ebx, [rax+8]
0x180064d7f  jmp     loc_180064D00
0x180064d84  xorps   xmm0, xmm0
0x180064d87  lea     rdx, PfsIdleTaskMgrWorker
0x180064d8e  movups  xmmword ptr [rdi], xmm0
0x180064d91  xor     eax, eax
0x180064d93  xor     r9d, r9d
0x180064d96  mov     [rdi+10h], rax
0x180064d9a  mov     r8, rdi
0x180064d9d  mov     rcx, rdi
0x180064da0  mov     [rdi+18h], rbp
0x180064da4  call    PfsWorkerStart
0x180064da9  mov     ebx, eax
0x180064dab  test    eax, eax
0x180064dad  jnz     loc_180064D00
0x180064db3  mov     rcx, r15
0x180064db6  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180064dbc  cmp     qword ptr [rbp+10h], 0
0x180064dc1  mov     rbx, [rsp+58h+arg_10]
0x180064dc6  jnz     short loc_180064DCE
0x180064dc8  mov     [rbp+10h], rdi
0x180064dcc  xor     edi, edi
0x180064dce  mov     rcx, [rbp+8]
0x180064dd2  cmp     [rcx], rbp
0x180064dd5  jz      short loc_180064DDE
0x180064dd7  mov     ecx, 3
0x180064ddc  int     29h; Win8: RtlFailFast(ecx)
0x180064dde  lea     rax, [rsi+10h]
0x180064de2  mov     [rax], rbp
0x180064de5  mov     [rax+8], rcx
0x180064de9  mov     [rcx], rax
0x180064dec  mov     [rbp+8], rax
0x180064df0  test    byte ptr [rbp+20h], 1
0x180064df4  jz      short loc_180064DFF
0x180064df6  mov     rcx, [rsi]; hEvent
0x180064df9  call    cs:__imp_SetEvent
0x180064dff  mov     rcx, r15
0x180064e02  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180064e08  mov     rax, [rsp+58h+arg_8]
0x180064e0d  mov     [rax], rsi
0x180064e10  mov     [rbx], r12
0x180064e13  xor     ebx, ebx
0x180064e15  mov     [r13+0], r14
0x180064e19  test    rdi, rdi
0x180064e1c  jz      short loc_180064E3E
0x180064e1e  xor     edx, edx
0x180064e20  mov     rcx, rdi
0x180064e23  call    PfsWorkerStop
0x180064e28  mov     rcx, cs:PfSvcGlobals
0x180064e2f  mov     r8, rdi; lpMem
0x180064e32  xor     edx, edx; dwFlags
0x180064e34  mov     rcx, [rcx+58h]; hHeap
0x180064e38  call    cs:__imp_HeapFree
0x180064e3e  mov     eax, ebx
0x180064e40  mov     rbx, [rsp+58h+arg_0]
0x180064e45  add     rsp, 20h
0x180064e49  pop     r15
0x180064e4b  pop     r14
0x180064e4d  pop     r13
0x180064e4f  pop     r12
0x180064e51  pop     rdi
0x180064e52  pop     rsi
0x180064e53  pop     rbp
0x180064e54  retn
```
