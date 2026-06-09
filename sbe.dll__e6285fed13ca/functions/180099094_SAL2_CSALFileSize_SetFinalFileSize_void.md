# SAL2::CSALFileSize::SetFinalFileSize(void)

- ea: `0x180099094`
- end: `0x180099233`
- name: `?SetFinalFileSize@CSALFileSize@SAL2@@QEAAJXZ`
- size: `415`
- prototype: `__int64 __fastcall(SAL2::CSALFileSize *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180080f9c`
- `0x180098614`

## callees

- `0x1800627f0`
- `0x180099094`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180099218`
- `KERNEL32!LeaveCriticalSection` at `0x180099218`
- `KERNEL32!EnterCriticalSection` at `0x1800990b5`
- `KERNEL32!EnterCriticalSection` at `0x1800990b5`
- `KERNEL32!GetLastError` at `0x180099118`
- `KERNEL32!GetLastError` at `0x1800991b6`
- `KERNEL32!GetLastError` at `0x1800991eb`
- `KERNEL32!GetLastError` at `0x180099118`
- `KERNEL32!GetLastError` at `0x1800991b6`
- `KERNEL32!GetLastError` at `0x1800991eb`
- `KERNEL32!GetFileSizeEx` at `0x18009910e`
- `KERNEL32!GetFileSizeEx` at `0x18009910e`
- `KERNEL32!SetFilePointerEx` at `0x1800991ac`
- `KERNEL32!SetFilePointerEx` at `0x1800991ac`
- `KERNEL32!SetEndOfFile` at `0x1800991e1`
- `KERNEL32!SetEndOfFile` at `0x1800991e1`

## pseudocode

```c
__int64 __fastcall SAL2::CSALFileSize::SetFinalFileSize(SAL2::CSALFileSize *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  unsigned int v3; // ebx
  unsigned __int64 v4; // rbp
  __int64 v5; // rax
  void *v6; // rcx
  __int64 v7; // r14
  signed int v8; // eax
  struct CEhEventTracer *v9; // rcx
  unsigned int v10; // r8d
  unsigned int v11; // r9d
  unsigned __int64 v12; // rdx
  LARGE_INTEGER v13; // rcx
  signed int v14; // eax
  signed int LastError; // eax
  LARGE_INTEGER FileSize; // [rsp+40h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1872);
  v3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1872));
  if ( *((_BYTE *)this + 1916) && *((_QWORD *)this + 39) != -1 && *((_DWORD *)this + 76) )
  {
    v4 = *((unsigned int *)this + 80);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 36) + 64LL))(*((_QWORD *)this + 36));
    v6 = (void *)*((_QWORD *)this + 39);
    v7 = v5;
    FileSize.QuadPart = 0;
    if ( GetFileSizeEx(v6, &FileSize) )
    {
      v12 = (v7 + v4 - 1) % v4;
      v13.QuadPart = v7 + v4 - 1 - v12;
      if ( v13.QuadPart > (unsigned __int64)FileSize.QuadPart )
      {
        v3 = -2147467259;
        v9 = (SAL2::CSALFileSize *)((char *)this + 104);
        v11 = -2147467259;
        v10 = 344;
        goto LABEL_9;
      }
      if ( !v13.QuadPart )
      {
        v3 = -2147467259;
        v9 = (SAL2::CSALFileSize *)((char *)this + 104);
        v11 = -2147467259;
        v10 = 345;
        goto LABEL_9;
      }
      FileSize.QuadPart = v7 + v4 - 1 - v12;
      if ( SetFilePointerEx(*((HANDLE *)this + 39), FileSize, 0, 0) )
      {
        if ( SetEndOfFile(*((HANDLE *)this + 39)) )
        {
          *((_DWORD *)this + 76) = 0;
          goto LABEL_23;
        }
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        v9 = (SAL2::CSALFileSize *)((char *)this + 104);
        v10 = 353;
      }
      else
      {
        v14 = GetLastError();
        v3 = v14;
        if ( v14 > 0 )
          v3 = (unsigned __int16)v14 | 0x80070000;
        v9 = (SAL2::CSALFileSize *)((char *)this + 104);
        v10 = 352;
      }
    }
    else
    {
      v8 = GetLastError();
      v3 = v8;
      if ( v8 > 0 )
        v3 = (unsigned __int16)v8 | 0x80070000;
      v9 = (SAL2::CSALFileSize *)((char *)this + 64);
      v10 = 343;
    }
    v11 = v3;
LABEL_9:
    SBEBasicTracers::EtwTraceError(v9, "multimedia\\dshow\\filters\\sbe\\sal\\salfilesize.cpp", v10, v11);
  }
LABEL_23:
  LeaveCriticalSection(v1);
  return v3;
}

```

## disassembly

```asm
0x180099094  mov     [rsp+arg_8], rbx
0x180099099  mov     [rsp+arg_10], rbp
0x18009909e  push    rsi
0x18009909f  push    rdi
0x1800990a0  push    r14
0x1800990a2  sub     rsp, 20h
0x1800990a6  lea     rsi, [rcx+750h]
0x1800990ad  mov     rdi, rcx
0x1800990b0  mov     rcx, rsi; lpCriticalSection
0x1800990b3  xor     ebx, ebx
0x1800990b5  call    cs:__imp_EnterCriticalSection
0x1800990bb  cmp     [rdi+77Ch], bl
0x1800990c1  jz      loc_180099215
0x1800990c7  cmp     qword ptr [rdi+138h], 0FFFFFFFFFFFFFFFFh
0x1800990cf  jz      loc_180099215
0x1800990d5  cmp     [rdi+130h], ebx
0x1800990db  jz      loc_180099215
0x1800990e1  mov     rcx, [rdi+120h]
0x1800990e8  mov     ebp, [rdi+140h]
0x1800990ee  mov     rax, [rcx]
0x1800990f1  mov     rax, [rax+40h]
0x1800990f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800990fa  mov     rcx, [rdi+138h]; hFile
0x180099101  lea     rdx, [rsp+38h+FileSize]; lpFileSize
0x180099106  mov     r14, rax
0x180099109  mov     qword ptr [rsp+38h+FileSize], rbx
0x18009910e  call    cs:__imp_GetFileSizeEx
0x180099114  test    eax, eax
0x180099116  jnz     short loc_18009914B
0x180099118  call    cs:__imp_GetLastError
0x18009911e  mov     ebx, eax
0x180099120  test    eax, eax
0x180099122  jle     short loc_18009912D
0x180099124  movzx   ebx, ax
0x180099127  or      ebx, 80070000h
0x18009912d  lea     rcx, [rdi+40h]; struct CEhEventTracer *
0x180099131  mov     r8d, 157h; unsigned int
0x180099137  mov     r9d, ebx; unsigned int
0x18009913a  lea     rdx, aMultimediaDsho_30; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x180099141  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x180099146  jmp     loc_180099215
0x18009914b  xor     edx, edx
0x18009914d  lea     rcx, [rbp-1]
0x180099151  add     rcx, r14
0x180099154  mov     rax, rcx
0x180099157  div     rbp
0x18009915a  sub     rcx, rdx
0x18009915d  cmp     rcx, qword ptr [rsp+38h+FileSize]
0x180099162  jbe     short loc_18009917B
0x180099164  mov     ebx, 80004005h
0x180099169  lea     rcx, [rdi+68h]
0x18009916d  mov     r9d, 80004005h
0x180099173  mov     r8d, 158h
0x180099179  jmp     short loc_18009913A
0x18009917b  test    rcx, rcx
0x18009917e  jnz     short loc_180099197
0x180099180  mov     ebx, 80004005h
0x180099185  lea     rcx, [rdi+68h]
0x180099189  mov     r9d, 80004005h
0x18009918f  mov     r8d, 159h
0x180099195  jmp     short loc_18009913A
0x180099197  mov     qword ptr [rsp+38h+FileSize], rcx
0x18009919c  mov     rdx, rcx; liDistanceToMove
0x18009919f  mov     rcx, [rdi+138h]; hFile
0x1800991a6  xor     r9d, r9d; dwMoveMethod
0x1800991a9  xor     r8d, r8d; lpNewFilePointer
0x1800991ac  call    cs:__imp_SetFilePointerEx
0x1800991b2  test    eax, eax
0x1800991b4  jnz     short loc_1800991DA
0x1800991b6  call    cs:__imp_GetLastError
0x1800991bc  mov     ebx, eax
0x1800991be  test    eax, eax
0x1800991c0  jle     short loc_1800991CB
0x1800991c2  movzx   ebx, ax
0x1800991c5  or      ebx, 80070000h
0x1800991cb  lea     rcx, [rdi+68h]
0x1800991cf  mov     r8d, 160h
0x1800991d5  jmp     loc_180099137
0x1800991da  mov     rcx, [rdi+138h]; hFile
0x1800991e1  call    cs:__imp_SetEndOfFile
0x1800991e7  test    eax, eax
0x1800991e9  jnz     short loc_18009920F
0x1800991eb  call    cs:__imp_GetLastError
0x1800991f1  mov     ebx, eax
0x1800991f3  test    eax, eax
0x1800991f5  jle     short loc_180099200
0x1800991f7  movzx   ebx, ax
0x1800991fa  or      ebx, 80070000h
0x180099200  lea     rcx, [rdi+68h]
0x180099204  mov     r8d, 161h
0x18009920a  jmp     loc_180099137
0x18009920f  mov     [rdi+130h], ebx
0x180099215  mov     rcx, rsi; lpCriticalSection
0x180099218  call    cs:__imp_LeaveCriticalSection
0x18009921e  mov     rbp, [rsp+38h+arg_10]
0x180099223  mov     eax, ebx
0x180099225  mov     rbx, [rsp+38h+arg_8]
0x18009922a  add     rsp, 20h
0x18009922e  pop     r14
0x180099230  pop     rdi
0x180099231  pop     rsi
0x180099232  retn
```
