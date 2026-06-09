# WorkThreadManager::CThread::AdjustThreadPriority(Windows::Internal::TaskOptions)

- ea: `0x1800377e0`
- end: `0x1800378ce`
- name: `?AdjustThreadPriority@CThread@WorkThreadManager@@QEAA@W4TaskOptions@Internal@Windows@@@Z`
- size: `238`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180019840`
- `0x180019918`

## callees

- `0x1800377e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180037879`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180037879`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003785d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003786e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003785d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003786e`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180037866`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180037866`

## pseudocode

```c
__int64 __fastcall WorkThreadManager::CThread::AdjustThreadPriority(__int64 a1, __int64 a2, __int16 a3)
{
  int v3; // r8d
  int v5; // ebx
  HANDLE CurrentThread; // rax
  int ThreadPriority; // edi
  HANDLE v8; // rax
  __int64 result; // rax

  v3 = a3 & 0xF000;
  switch ( v3 )
  {
    case 24576:
      v5 = 1;
      break;
    case 28672:
      v5 = 2;
      break;
    case 20480:
      v5 = 0;
      break;
    case 4096:
      v5 = 0x10000;
      ThreadPriority = 0x20000;
      goto LABEL_11;
    case 8192:
      v5 = -15;
      break;
    case 12288:
      v5 = -2;
      break;
    case 16384:
      v5 = -1;
      break;
    default:
      v5 = 15;
      if ( v3 != 0x8000 )
        v5 = 0;
      break;
  }
  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
LABEL_11:
  v8 = GetCurrentThread();
  *(_DWORD *)a2 = SetThreadPriority(v8, v5);
  result = a2;
  *(_DWORD *)(a2 + 4) = ThreadPriority;
  *(_BYTE *)(a2 + 8) = 1;
  return result;
}

```

## disassembly

```asm
0x1800377e0  mov     [rsp+arg_0], rbx
0x1800377e5  mov     [rsp+arg_8], rsi
0x1800377ea  push    rdi
0x1800377eb  sub     rsp, 20h
0x1800377ef  and     r8d, 0F000h
0x1800377f6  mov     rsi, rdx
0x1800377f9  cmp     r8d, 6000h
0x180037800  jz      loc_18003789B
0x180037806  cmp     r8d, 7000h
0x18003780d  jz      loc_1800378A2
0x180037813  cmp     r8d, 5000h
0x18003781a  jz      loc_1800378A9
0x180037820  cmp     r8d, 1000h
0x180037827  jz      loc_1800378AF
0x18003782d  cmp     r8d, 2000h
0x180037834  jz      loc_1800378C7
0x18003783a  cmp     r8d, 3000h
0x180037841  jz      short loc_1800378C0
0x180037843  cmp     r8d, 4000h
0x18003784a  jz      short loc_1800378BB
0x18003784c  xor     eax, eax
0x18003784e  mov     ebx, 0Fh
0x180037853  cmp     r8d, 8000h
0x18003785a  cmovnz  ebx, eax
0x18003785d  call    cs:__imp_GetCurrentThread
0x180037863  mov     rcx, rax; hThread
0x180037866  call    cs:__imp_GetThreadPriority
0x18003786c  mov     edi, eax
0x18003786e  call    cs:__imp_GetCurrentThread
0x180037874  mov     rcx, rax; hThread
0x180037877  mov     edx, ebx; nPriority
0x180037879  call    cs:__imp_SetThreadPriority
0x18003787f  mov     rbx, [rsp+28h+arg_0]
0x180037884  mov     [rsi], eax
0x180037886  mov     rax, rsi
0x180037889  mov     [rsi+4], edi
0x18003788c  mov     byte ptr [rsi+8], 1
0x180037890  mov     rsi, [rsp+28h+arg_8]
0x180037895  add     rsp, 20h
0x180037899  pop     rdi
0x18003789a  retn
0x18003789b  mov     ebx, 1
0x1800378a0  jmp     short loc_18003785D
0x1800378a2  mov     ebx, 2
0x1800378a7  jmp     short loc_18003785D
0x1800378a9  xor     eax, eax
0x1800378ab  mov     ebx, eax
0x1800378ad  jmp     short loc_18003785D
0x1800378af  mov     ebx, 10000h
0x1800378b4  mov     edi, 20000h
0x1800378b9  jmp     short loc_18003786E
0x1800378bb  or      ebx, 0FFFFFFFFh
0x1800378be  jmp     short loc_18003785D
0x1800378c0  mov     ebx, 0FFFFFFFEh
0x1800378c5  jmp     short loc_18003785D
0x1800378c7  mov     ebx, 0FFFFFFF1h
0x1800378cc  jmp     short loc_18003785D
```
