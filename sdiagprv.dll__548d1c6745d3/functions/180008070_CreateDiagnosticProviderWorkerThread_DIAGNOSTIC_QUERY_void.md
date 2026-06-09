# CreateDiagnosticProviderWorkerThread(_DIAGNOSTIC_QUERY *,void * *)

- ea: `0x180008070`
- end: `0x180008211`
- name: `?CreateDiagnosticProviderWorkerThread@@YAJPEAU_DIAGNOSTIC_QUERY@@PEAPEAX@Z`
- size: `417`
- prototype: `__int64 __fastcall(struct _DIAGNOSTIC_QUERY *lpParameter, char **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006fa0`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180008070`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000813a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000813a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008179`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800081e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800081e1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000812c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000812c`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000816e`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000816e`

## string_xrefs

- `0x1800080a4`: `CreateDiagnosticProviderWorkerThread`
- `0x1800080e9`: `CreateDiagnosticProviderWorkerThread`
- `0x1800081c4`: `CreateDiagnosticProviderWorkerThread`
- `0x1800081f2`: `CreateDiagnosticProviderWorkerThread`
- `0x1800080dc`: `DiagnosticProviderThreadHandle`

## pseudocode

```c
__int64 __fastcall CreateDiagnosticProviderWorkerThread(struct _DIAGNOSTIC_QUERY *lpParameter, char **a2)
{
  signed int v4; // ebx
  char *Thread; // rdi
  signed int LastError; // eax
  signed int v7; // eax
  __int64 v8; // r9

  if ( !lpParameter )
  {
    v4 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        0,
        (_DWORD)a2,
        (unsigned int)"CreateDiagnosticProviderWorkerThread",
        -2147024809,
        (__int64)"DiagnosticQuery");
    return (unsigned int)v4;
  }
  if ( !a2 )
  {
    Thread = 0;
    v4 = -2147024809;
LABEL_6:
    if ( !a2 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
        McTemplateU0sqs_EventWriteTransfer(
          (_DWORD)lpParameter,
          (_DWORD)a2,
          (unsigned int)"CreateDiagnosticProviderWorkerThread",
          -2147024809,
          (__int64)"DiagnosticProviderThreadHandle");
      goto LABEL_28;
    }
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
    {
LABEL_28:
      if ( (unsigned __int64)(Thread - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(Thread);
      return (unsigned int)v4;
    }
    v8 = 2147942487LL;
    goto LABEL_26;
  }
  v4 = 0;
  *a2 = (char *)-1LL;
  if ( *(_QWORD *)lpParameter )
  {
    Thread = (char *)CreateThread(0, 0, DiagnosticProviderWorkerThread, lpParameter, 4u, 0);
    if ( !Thread )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 < 0 )
        goto LABEL_20;
    }
    v4 = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)lpParameter + 8LL))(*(_QWORD *)lpParameter, Thread);
    if ( v4 < 0 )
      goto LABEL_20;
    if ( ResumeThread(Thread) == 1 )
      goto LABEL_19;
    v7 = GetLastError();
    v4 = v7;
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_19:
      *a2 = Thread;
    }
    else
    {
LABEL_20:
      if ( v4 == -2147024809 )
        goto LABEL_6;
    }
    if ( v4 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        goto LABEL_27;
      v8 = (unsigned int)v4;
LABEL_26:
      McTemplateU0sq_EventWriteTransfer(lpParameter, a2, "CreateDiagnosticProviderWorkerThread", v8);
LABEL_27:
      if ( v4 >= 0 )
        return (unsigned int)v4;
      goto LABEL_28;
    }
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(lpParameter, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CreateDiagnosticProviderWorkerThread");
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180008070  push    rbx
0x180008072  push    rsi
0x180008073  push    rdi
0x180008074  push    r14
0x180008076  sub     rsp, 38h
0x18000807a  mov     rsi, rdx
0x18000807d  mov     r14, rcx
0x180008080  test    rcx, rcx
0x180008083  jnz     short loc_1800080BA
0x180008085  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000808c  mov     ebx, 80070057h
0x180008091  jz      loc_180008205
0x180008097  lea     rax, aDiagnosticquer; "DiagnosticQuery"
0x18000809e  mov     r9d, 80070057h
0x1800080a4  lea     r8, aCreatediagnost; "CreateDiagnosticProviderWorkerThread"
0x1800080ab  mov     qword ptr [rsp+58h+dwCreationFlags], rax
0x1800080b0  call    McTemplateU0sqs_EventWriteTransfer
0x1800080b5  jmp     loc_180008205
0x1800080ba  test    rsi, rsi
0x1800080bd  jnz     short loc_1800080FF
0x1800080bf  xor     edi, edi
0x1800080c1  mov     ebx, 80070057h
0x1800080c6  test    rsi, rsi
0x1800080c9  jnz     loc_1800081B5
0x1800080cf  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800080d6  jz      loc_1800081D4
0x1800080dc  lea     rax, aDiagnosticprov_1; "DiagnosticProviderThreadHandle"
0x1800080e3  mov     r9d, 80070057h
0x1800080e9  lea     r8, aCreatediagnost; "CreateDiagnosticProviderWorkerThread"
0x1800080f0  mov     qword ptr [rsp+58h+dwCreationFlags], rax
0x1800080f5  call    McTemplateU0sqs_EventWriteTransfer
0x1800080fa  jmp     loc_1800081D4
0x1800080ff  xor     ebx, ebx
0x180008101  mov     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x180008108  cmp     [rcx], rbx
0x18000810b  jz      loc_1800081E9
0x180008111  mov     [rsp+58h+lpThreadId], rbx; lpThreadId
0x180008116  lea     r8, ?DiagnosticProviderWorkerThread@@YAKPEAX@Z; lpStartAddress
0x18000811d  mov     r9, r14; lpParameter
0x180008120  mov     [rsp+58h+dwCreationFlags], 4; dwCreationFlags
0x180008128  xor     edx, edx; dwStackSize
0x18000812a  xor     ecx, ecx; lpThreadAttributes
0x18000812c  call    cs:__imp_CreateThread
0x180008132  mov     rdi, rax
0x180008135  test    rax, rax
0x180008138  jnz     short loc_180008153
0x18000813a  call    cs:__imp_GetLastError
0x180008140  mov     ebx, eax
0x180008142  test    eax, eax
0x180008144  jle     short loc_18000814F
0x180008146  movzx   ebx, ax
0x180008149  or      ebx, 80070000h
0x18000814f  test    ebx, ebx
0x180008151  js      short loc_180008197
0x180008153  mov     rcx, [r14]
0x180008156  mov     rdx, rdi
0x180008159  mov     rax, [rcx]
0x18000815c  mov     rax, [rax+8]
0x180008160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008165  mov     ebx, eax
0x180008167  test    eax, eax
0x180008169  js      short loc_180008197
0x18000816b  mov     rcx, rdi; hThread
0x18000816e  call    cs:__imp_ResumeThread
0x180008174  cmp     eax, 1
0x180008177  jz      short loc_180008192
0x180008179  call    cs:__imp_GetLastError
0x18000817f  mov     ebx, eax
0x180008181  test    eax, eax
0x180008183  jle     short loc_18000818E
0x180008185  movzx   ebx, ax
0x180008188  or      ebx, 80070000h
0x18000818e  test    ebx, ebx
0x180008190  js      short loc_180008197
0x180008192  mov     [rsi], rdi
0x180008195  jmp     short loc_1800081A3
0x180008197  cmp     ebx, 80070057h
0x18000819d  jz      loc_1800080C6
0x1800081a3  test    ebx, ebx
0x1800081a5  jz      short loc_1800081E9
0x1800081a7  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800081ae  jz      short loc_1800081D0
0x1800081b0  mov     r9d, ebx
0x1800081b3  jmp     short loc_1800081C4
0x1800081b5  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800081bc  jz      short loc_1800081D4
0x1800081be  mov     r9d, 80070057h
0x1800081c4  lea     r8, aCreatediagnost; "CreateDiagnosticProviderWorkerThread"
0x1800081cb  call    McTemplateU0sq_EventWriteTransfer
0x1800081d0  test    ebx, ebx
0x1800081d2  jns     short loc_180008205
0x1800081d4  lea     rax, [rdi-1]
0x1800081d8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800081dc  ja      short loc_180008205
0x1800081de  mov     rcx, rdi; hObject
0x1800081e1  call    cs:__imp_CloseHandle
0x1800081e7  jmp     short loc_180008205
0x1800081e9  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x1800081f0  jz      short loc_180008205
0x1800081f2  lea     r8, aCreatediagnost; "CreateDiagnosticProviderWorkerThread"
0x1800081f9  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180008200  call    McTemplateU0s_EventWriteTransfer
0x180008205  mov     eax, ebx
0x180008207  add     rsp, 38h
0x18000820b  pop     r14
0x18000820d  pop     rdi
0x18000820e  pop     rsi
0x18000820f  pop     rbx
0x180008210  retn
```
