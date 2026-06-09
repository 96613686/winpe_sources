# GetTempFileHandle

- ea: `0x180019090`
- end: `0x180019181`
- name: `GetTempFileHandle`
- size: `241`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180013490`
- `0x180013690`
- `0x180013878`
- `0x18001d7c8`
- `0x180024050`

## callees

- `0x180018e94`
- `0x180019090`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180019146`
- `KERNEL32!HeapFree` at `0x180019146`
- `KERNEL32!CreateFileW` at `0x180019113`
- `KERNEL32!CreateFileW` at `0x180019113`
- `KERNEL32!SetLastError` at `0x18001915c`
- `KERNEL32!SetLastError` at `0x18001915c`
- `KERNEL32!GetProcessHeap` at `0x180019132`
- `KERNEL32!GetProcessHeap` at `0x180019132`

## pseudocode

```c
__int64 __fastcall GetTempFileHandle(int *a1, int a2, WCHAR **a3)
{
  __int64 FileW; // rsi
  int v4; // eax
  const WCHAR *TempFile; // rax
  WCHAR *v8; // rdi
  HANDLE ProcessHeap; // rax

  FileW = -1;
  v4 = -1;
  if ( a1 )
    v4 = *a1;
  if ( a3 )
    *a3 = 0;
  if ( a1 && (unsigned int)(v4 + 17960959) <= 1 )
  {
    TempFile = (const WCHAR *)GetTempFile((__int64)a1);
    v8 = (WCHAR *)TempFile;
    if ( TempFile )
    {
      FileW = (__int64)CreateFileW(TempFile, 0xC0000000, 7u, 0, 2u, a2 != 0 ? 201326848 : 134217984, 0);
      if ( FileW == -1 || !a3 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v8);
      }
      else
      {
        *a3 = v8;
      }
    }
    return FileW;
  }
  else
  {
    SetLastError(6u);
    return -1;
  }
}

```

## disassembly

```asm
0x180019090  mov     [rsp+arg_0], rbx
0x180019095  mov     [rsp+arg_8], rbp
0x18001909a  mov     [rsp+arg_10], rsi
0x18001909f  push    rdi
0x1800190a0  sub     rsp, 40h
0x1800190a4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800190a8  or      eax, 0FFFFFFFFh
0x1800190ab  mov     rbx, r8
0x1800190ae  mov     ebp, edx
0x1800190b0  test    rcx, rcx
0x1800190b3  jz      short loc_1800190B7
0x1800190b5  mov     eax, [rcx]
0x1800190b7  test    rbx, rbx
0x1800190ba  jz      short loc_1800190C0
0x1800190bc  and     qword ptr [r8], 0
0x1800190c0  test    rcx, rcx
0x1800190c3  jz      loc_180019157
0x1800190c9  add     eax, 1120FFFh
0x1800190ce  cmp     eax, 1
0x1800190d1  ja      loc_180019157
0x1800190d7  call    GetTempFile
0x1800190dc  mov     rdi, rax
0x1800190df  test    rax, rax
0x1800190e2  jz      short loc_180019152
0x1800190e4  neg     ebp
0x1800190e6  mov     edx, 0C0000000h; dwDesiredAccess
0x1800190eb  mov     rcx, rdi; lpFileName
0x1800190ee  sbb     eax, eax
0x1800190f0  and     [rsp+48h+var_18], 0
0x1800190f6  xor     r9d, r9d; lpSecurityAttributes
0x1800190f9  and     eax, 4000000h
0x1800190fe  add     eax, 8000100h
0x180019103  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180019107  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x18001910f  lea     r8d, [r9+7]; dwShareMode
0x180019113  call    cs:__imp_CreateFileW
0x18001911a  nop     dword ptr [rax+rax+00h]
0x18001911f  mov     rsi, rax
0x180019122  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180019126  jz      short loc_180019132
0x180019128  test    rbx, rbx
0x18001912b  jz      short loc_180019132
0x18001912d  mov     [rbx], rdi
0x180019130  jmp     short loc_180019152
0x180019132  call    cs:__imp_GetProcessHeap
0x180019139  nop     dword ptr [rax+rax+00h]
0x18001913e  mov     r8, rdi; lpMem
0x180019141  xor     edx, edx; dwFlags
0x180019143  mov     rcx, rax; hHeap
0x180019146  call    cs:__imp_HeapFree
0x18001914d  nop     dword ptr [rax+rax+00h]
0x180019152  mov     rax, rsi
0x180019155  jmp     short loc_18001916C
0x180019157  mov     ecx, 6; dwErrCode
0x18001915c  call    cs:__imp_SetLastError
0x180019163  nop     dword ptr [rax+rax+00h]
0x180019168  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001916c  mov     rbx, [rsp+48h+arg_0]
0x180019171  mov     rbp, [rsp+48h+arg_8]
0x180019176  mov     rsi, [rsp+48h+arg_10]
0x18001917b  add     rsp, 40h
0x18001917f  pop     rdi
0x180019180  retn
```
