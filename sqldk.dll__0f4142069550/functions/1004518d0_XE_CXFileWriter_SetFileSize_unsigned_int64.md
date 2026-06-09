# XE_CXFileWriter::SetFileSize(unsigned __int64)

- ea: `0x1004518d0`
- end: `0x100451995`
- name: `?SetFileSize@XE_CXFileWriter@@AEAAH_K@Z`
- size: `197`
- prototype: `__int64 __fastcall(XE_CXFileWriter *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x100450160`
- `0x100451260`
- `0x100451560`

## callees

- `0x1004518d0`

## import_xrefs

- `KERNEL32!SetFileValidData` at `0x100451939`
- `KERNEL32!SetFileValidData` at `0x100451939`
- `KERNEL32!SetEndOfFile` at `0x100451927`
- `KERNEL32!SetEndOfFile` at `0x100451927`
- `KERNEL32!SetFilePointerEx` at `0x100451916`
- `KERNEL32!SetFilePointerEx` at `0x100451916`
- `KERNEL32!GetLastError` at `0x10045195b`
- `KERNEL32!GetLastError` at `0x10045195b`

## pseudocode

```c
__int64 __fastcall XE_CXFileWriter::SetFileSize(XE_CXFileWriter *this, __int64 a2)
{
  unsigned int v2; // ebp
  LONGLONG v4; // rbx
  __int64 v5; // rsi
  DWORD LastError; // eax

  v2 = 0;
  if ( a2 )
    v4 = *((unsigned int *)this + 4)
       * (((unsigned __int64)*((unsigned int *)this + 4) + a2 - 1)
        / *((unsigned int *)this + 4));
  else
    v4 = 0;
  if ( !SetFilePointerEx(*((HANDLE *)this + 73), (LARGE_INTEGER)v4, 0, 0)
    || (v2 = SetEndOfFile(*((HANDLE *)this + 73)), SetFileValidData(*((HANDLE *)this + 73), v4), !v2) )
  {
    v5 = **((_QWORD **)this + 105);
    LastError = GetLastError();
    (*(void (__fastcall **)(_QWORD, _QWORD, LONGLONG, _QWORD, char *))(v5 + 64))(
      *((_QWORD *)this + 105),
      LastError,
      v4,
      0,
      (char *)this + 32);
  }
  return v2;
}

```

## disassembly

```asm
0x1004518d0  mov     [rsp+arg_10], rbx
0x1004518d5  mov     [rsp+arg_18], rbp
0x1004518da  push    r14
0x1004518dc  sub     rsp, 30h
0x1004518e0  xor     ebp, ebp
0x1004518e2  mov     r14, rcx
0x1004518e5  test    rdx, rdx
0x1004518e8  jz      short loc_100451903
0x1004518ea  mov     r8d, [rcx+10h]
0x1004518ee  lea     rax, [rdx-1]
0x1004518f2  add     rax, r8
0x1004518f5  xor     edx, edx
0x1004518f7  div     r8
0x1004518fa  mov     rbx, rax
0x1004518fd  imul    rbx, r8
0x100451901  jmp     short loc_100451906
0x100451903  mov     rbx, rbp
0x100451906  mov     rcx, [rcx+248h]; hFile
0x10045190d  xor     r9d, r9d; dwMoveMethod
0x100451910  xor     r8d, r8d; lpNewFilePointer
0x100451913  mov     rdx, rbx; liDistanceToMove
0x100451916  call    cs:__imp_SetFilePointerEx
0x10045191c  test    eax, eax
0x10045191e  jz      short loc_100451943
0x100451920  mov     rcx, [r14+248h]; hFile
0x100451927  call    cs:__imp_SetEndOfFile
0x10045192d  mov     rcx, [r14+248h]; hFile
0x100451934  mov     rdx, rbx; ValidDataLength
0x100451937  mov     ebp, eax
0x100451939  call    cs:__imp_SetFileValidData
0x10045193f  test    ebp, ebp
0x100451941  jnz     short loc_100451982
0x100451943  mov     rax, [r14+348h]
0x10045194a  mov     [rsp+38h+arg_0], rsi
0x10045194f  mov     [rsp+38h+arg_8], rdi
0x100451954  lea     rdi, [r14+20h]
0x100451958  mov     rsi, [rax]
0x10045195b  call    cs:__imp_GetLastError
0x100451961  mov     rcx, [r14+348h]
0x100451968  xor     r9d, r9d
0x10045196b  mov     edx, eax
0x10045196d  mov     [rsp+38h+var_18], rdi
0x100451972  mov     r8, rbx
0x100451975  call    qword ptr [rsi+40h]
0x100451978  mov     rdi, [rsp+38h+arg_8]
0x10045197d  mov     rsi, [rsp+38h+arg_0]
0x100451982  mov     rbx, [rsp+38h+arg_10]
0x100451987  mov     eax, ebp
0x100451989  mov     rbp, [rsp+38h+arg_18]
0x10045198e  add     rsp, 30h
0x100451992  pop     r14
0x100451994  retn
```
