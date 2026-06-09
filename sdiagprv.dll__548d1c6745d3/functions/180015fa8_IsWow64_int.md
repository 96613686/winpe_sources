# IsWow64(int *)

- ea: `0x180015fa8`
- end: `0x1800161e2`
- name: `?IsWow64@@YAJPEAH@Z`
- size: `570`
- prototype: `__int64 __fastcall(int *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015ae8`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x1800034e4`
- `0x18000edd4`
- `0x180015fa8`
- `0x1800180be`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016103`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016103`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016135`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016135`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016034`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016034`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016076`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016076`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016021`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016068`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016021`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800160af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016116`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016143`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016170`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800160af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016116`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016143`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016170`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016158`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016158`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800160a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800160a5`

## string_xrefs

- `0x1800160e4`: `\kernel32.dll`

## pseudocode

```c
__int64 __fastcall IsWow64(int *a1, __int64 a2)
{
  WCHAR *v2; // rdi
  signed int v4; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *v6; // rax
  __int64 *v7; // rdx
  HANDLE v8; // rax
  UINT SystemDirectoryW; // eax
  signed int LastError; // eax
  HMODULE ModuleHandleW; // rbp
  signed int v13; // eax
  FARPROC ProcAddress; // rbp
  signed int v15; // eax
  HANDLE CurrentProcess; // rax
  signed int v17; // eax
  SIZE_T dwBytes; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  dwBytes = 0;
  if ( !a1 )
  {
    v4 = -2147024809;
    goto LABEL_3;
  }
  *a1 = 0;
  v4 = ULongLongMult(0x104u, 2u, &dwBytes);
  if ( v4 >= 0 )
  {
    ProcessHeap = GetProcessHeap();
    v6 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, dwBytes);
    v2 = v6;
    if ( !v6 )
    {
      v4 = -2147024882;
LABEL_8:
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        goto LABEL_11;
      v7 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
      goto LABEL_10;
    }
    memset_0(v6, 0, dwBytes);
    SystemDirectoryW = GetSystemDirectoryW(v2, 0x104u);
    if ( !SystemDirectoryW )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_17;
    }
    if ( SystemDirectoryW >= 0x104 )
    {
      v4 = -2147024774;
      goto LABEL_37;
    }
    v4 = StringCchCatW(v2, 0x104u, L"\\kernel32.dll");
    if ( v4 >= 0 )
    {
      ModuleHandleW = GetModuleHandleW(v2);
      if ( ModuleHandleW )
        goto LABEL_26;
      v13 = GetLastError();
      v4 = v13;
      if ( v13 > 0 )
        v4 = (unsigned __int16)v13 | 0x80070000;
      if ( v4 >= 0 )
      {
LABEL_26:
        ProcAddress = GetProcAddress(ModuleHandleW, "IsWow64Process");
        if ( ProcAddress )
          goto LABEL_30;
        v15 = GetLastError();
        v4 = v15;
        if ( v15 > 0 )
          v4 = (unsigned __int16)v15 | 0x80070000;
        if ( v4 >= 0 )
        {
LABEL_30:
          CurrentProcess = GetCurrentProcess();
          if ( ((unsigned int (__fastcall *)(HANDLE, int *))ProcAddress)(CurrentProcess, a1) )
          {
            v4 = 0;
            if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
              goto LABEL_11;
            v7 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_10:
            McTemplateU0s_EventWriteTransfer(a1, v7, "IsWow64");
            goto LABEL_11;
          }
          v17 = GetLastError();
          v4 = v17;
          if ( v17 > 0 )
            v4 = (unsigned __int16)v17 | 0x80070000;
LABEL_17:
          if ( v4 >= 0 )
          {
            v4 = -2147467259;
            goto LABEL_37;
          }
        }
      }
    }
  }
  if ( v4 == -2147024882 )
    goto LABEL_8;
  if ( v4 == -2147024809 )
  {
LABEL_3:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer((_DWORD)a1, a2, (unsigned int)"IsWow64", -2147024809, (__int64)"IsWow64Proc");
    goto LABEL_11;
  }
LABEL_37:
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    McTemplateU0sq_EventWriteTransfer(a1, a2, "IsWow64", (unsigned int)v4);
LABEL_11:
  if ( v2 )
  {
    v8 = GetProcessHeap();
    HeapFree(v8, 0, v2);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015fa8  mov     [rsp+arg_8], rbx
0x180015fad  mov     [rsp+arg_10], rbp
0x180015fb2  push    rsi
0x180015fb3  push    rdi
0x180015fb4  push    r14
0x180015fb6  sub     rsp, 30h
0x180015fba  xor     edi, edi
0x180015fbc  mov     [rsp+48h+dwBytes], 0
0x180015fc5  mov     r14, rcx
0x180015fc8  test    rcx, rcx
0x180015fcb  jnz     short loc_180015FFF
0x180015fcd  mov     ebx, 80070057h
0x180015fd2  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180015fd9  jz      loc_180016063
0x180015fdf  lea     rax, aIswow64proc; "IsWow64Proc"
0x180015fe6  mov     r9d, 80070057h
0x180015fec  lea     r8, aIswow64; "IsWow64"
0x180015ff3  mov     [rsp+48h+var_28], rax
0x180015ff8  call    McTemplateU0sqs_EventWriteTransfer
0x180015ffd  jmp     short loc_180016063
0x180015fff  mov     [rcx], edi
0x180016001  lea     r8, [rsp+48h+dwBytes]; unsigned __int64 *
0x180016006  mov     esi, 104h
0x18001600b  mov     edx, 2; unsigned __int64
0x180016010  mov     ecx, esi; unsigned __int64
0x180016012  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180016017  mov     ebx, eax
0x180016019  test    eax, eax
0x18001601b  js      loc_1800161A5
0x180016021  call    cs:__imp_GetProcessHeap
0x180016027  mov     r8, [rsp+48h+dwBytes]; dwBytes
0x18001602c  mov     edx, 8; dwFlags
0x180016031  mov     rcx, rax; hHeap
0x180016034  call    cs:__imp_HeapAlloc
0x18001603a  mov     rdi, rax
0x18001603d  test    rax, rax
0x180016040  jnz     short loc_180016091
0x180016042  mov     ebx, 8007000Eh
0x180016047  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18001604e  jz      short loc_180016063
0x180016050  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180016057  lea     r8, aIswow64; "IsWow64"
0x18001605e  call    McTemplateU0s_EventWriteTransfer
0x180016063  test    rdi, rdi
0x180016066  jz      short loc_18001607C
0x180016068  call    cs:__imp_GetProcessHeap
0x18001606e  mov     r8, rdi; lpMem
0x180016071  xor     edx, edx; dwFlags
0x180016073  mov     rcx, rax; hHeap
0x180016076  call    cs:__imp_HeapFree
0x18001607c  mov     rbp, [rsp+48h+arg_10]
0x180016081  mov     eax, ebx
0x180016083  mov     rbx, [rsp+48h+arg_8]
0x180016088  add     rsp, 30h
0x18001608c  pop     r14
0x18001608e  pop     rdi
0x18001608f  pop     rsi
0x180016090  retn
0x180016091  mov     r8, [rsp+48h+dwBytes]; Size
0x180016096  xor     edx, edx; Val
0x180016098  mov     rcx, rdi; void *
0x18001609b  call    memset_0
0x1800160a0  mov     edx, esi; uSize
0x1800160a2  mov     rcx, rdi; lpBuffer
0x1800160a5  call    cs:__imp_GetSystemDirectoryW
0x1800160ab  test    eax, eax
0x1800160ad  jnz     short loc_1800160D6
0x1800160af  call    cs:__imp_GetLastError
0x1800160b5  mov     ebx, eax
0x1800160b7  test    eax, eax
0x1800160b9  jle     short loc_1800160C4
0x1800160bb  movzx   ebx, ax
0x1800160be  or      ebx, 80070000h
0x1800160c4  test    ebx, ebx
0x1800160c6  js      loc_1800161A5
0x1800160cc  mov     ebx, 80004005h
0x1800160d1  jmp     loc_1800161C1
0x1800160d6  cmp     eax, esi
0x1800160d8  jb      short loc_1800160E4
0x1800160da  mov     ebx, 8007007Ah
0x1800160df  jmp     loc_1800161C1
0x1800160e4  lea     r8, aKernel32Dll; "\\kernel32.dll"
0x1800160eb  mov     rdx, rsi; unsigned __int64
0x1800160ee  mov     rcx, rdi; unsigned __int16 *
0x1800160f1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800160f6  mov     ebx, eax
0x1800160f8  test    eax, eax
0x1800160fa  js      loc_1800161A5
0x180016100  mov     rcx, rdi; lpModuleName
0x180016103  call    cs:__imp_GetModuleHandleW
0x180016109  mov     rbp, rax
0x18001610c  mov     esi, 80070000h
0x180016111  test    rax, rax
0x180016114  jnz     short loc_18001612B
0x180016116  call    cs:__imp_GetLastError
0x18001611c  mov     ebx, eax
0x18001611e  test    eax, eax
0x180016120  jle     short loc_180016127
0x180016122  movzx   ebx, ax
0x180016125  or      ebx, esi
0x180016127  test    ebx, ebx
0x180016129  js      short loc_1800161A5
0x18001612b  lea     rdx, ProcName; "IsWow64Process"
0x180016132  mov     rcx, rbp; hModule
0x180016135  call    cs:__imp_GetProcAddress
0x18001613b  mov     rbp, rax
0x18001613e  test    rax, rax
0x180016141  jnz     short loc_180016158
0x180016143  call    cs:__imp_GetLastError
0x180016149  mov     ebx, eax
0x18001614b  test    eax, eax
0x18001614d  jle     short loc_180016154
0x18001614f  movzx   ebx, ax
0x180016152  or      ebx, esi
0x180016154  test    ebx, ebx
0x180016156  js      short loc_1800161A5
0x180016158  call    cs:__imp_GetCurrentProcess
0x18001615e  mov     rcx, rax
0x180016161  mov     rdx, r14
0x180016164  mov     rax, rbp
0x180016167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001616c  test    eax, eax
0x18001616e  jnz     short loc_18001618A
0x180016170  call    cs:__imp_GetLastError
0x180016176  mov     ebx, eax
0x180016178  test    eax, eax
0x18001617a  jle     loc_1800160C4
0x180016180  movzx   ebx, ax
0x180016183  or      ebx, esi
0x180016185  jmp     loc_1800160C4
0x18001618a  xor     ebx, ebx
0x18001618c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180016193  jz      loc_180016063
0x180016199  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x1800161a0  jmp     loc_180016057
0x1800161a5  cmp     ebx, 8007000Eh
0x1800161ab  jz      loc_180016047
0x1800161b1  cmp     ebx, 80070057h
0x1800161b7  jz      loc_180015FD2
0x1800161bd  test    ebx, ebx
0x1800161bf  jz      short loc_18001618C
0x1800161c1  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800161c8  jz      loc_180016063
0x1800161ce  mov     r9d, ebx
0x1800161d1  lea     r8, aIswow64; "IsWow64"
0x1800161d8  call    McTemplateU0sq_EventWriteTransfer
0x1800161dd  jmp     loc_180016063
```
