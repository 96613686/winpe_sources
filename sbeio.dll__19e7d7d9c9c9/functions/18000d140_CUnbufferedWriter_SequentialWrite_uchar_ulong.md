# CUnbufferedWriter::SequentialWrite(uchar *,ulong)

- ea: `0x18000d140`
- end: `0x18000d201`
- name: `?SequentialWrite@CUnbufferedWriter@@QEAAJPEAEK@Z`
- size: `193`
- prototype: `__int64 __fastcall(CUnbufferedWriter *__hidden this, unsigned __int8 *Src, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000c1b0`

## callees

- `0x18000cc7c`
- `0x18000cfa8`
- `0x18000d140`
- `0x18000d208`
- `0x18002a070`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x18000d16c`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000d16c`
- `KERNEL32!ReleaseMutex` at `0x18000d1ea`
- `KERNEL32!ReleaseMutex` at `0x18000d1ea`

## pseudocode

```c
__int64 __fastcall CUnbufferedWriter::SequentialWrite(HANDLE *this, unsigned __int8 *Src, unsigned int a3)
{
  signed int v6; // ebx
  struct CAsyncOperation *CurrentOperation; // rsi
  int v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // r15d
  unsigned int v11; // edx
  void *v12; // rcx

  v6 = 0;
  CUnbufferedWriter::ProcessCompletions((CUnbufferedWriter *)this, 0);
  WaitForSingleObjectEx(this[9], 0xFFFFFFFF, 1);
  while ( 1 )
  {
    CurrentOperation = CUnbufferedWriter::FindCurrentOperation((CUnbufferedWriter *)this);
    if ( !CurrentOperation )
    {
      v6 = -2147418113;
      goto LABEL_14;
    }
    v8 = *((_DWORD *)this + 13);
    if ( v8 )
      break;
    v9 = *((unsigned int *)CurrentOperation + 10);
    v10 = a3;
    v11 = *((_DWORD *)this + 10) - v9;
    v12 = (void *)(*((_QWORD *)CurrentOperation + 4) + v9);
    if ( a3 > v11 )
      v10 = v11;
    memcpy_0(v12, Src, v10);
    *((_DWORD *)CurrentOperation + 10) += v10;
    if ( *((_DWORD *)CurrentOperation + 10) == *((_DWORD *)this + 10) )
    {
      v6 = CUnbufferedWriter::SubmitWriteOperation((CUnbufferedWriter *)this);
      if ( v6 < 0 )
        goto LABEL_14;
    }
    a3 -= v10;
    if ( !a3 )
      goto LABEL_14;
    Src += v10;
  }
  if ( v8 > 0 )
    v6 = (unsigned __int16)v8 | 0x80070000;
  else
    v6 = *((_DWORD *)this + 13);
LABEL_14:
  ReleaseMutex(this[9]);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000d140  push    rbx
0x18000d142  push    rbp
0x18000d143  push    rsi
0x18000d144  push    rdi
0x18000d145  push    r12
0x18000d147  push    r14
0x18000d149  push    r15
0x18000d14b  sub     rsp, 20h
0x18000d14f  mov     r14, rdx
0x18000d152  mov     ebp, r8d
0x18000d155  xor     edx, edx; unsigned int
0x18000d157  mov     rdi, rcx
0x18000d15a  xor     ebx, ebx
0x18000d15c  call    ?ProcessCompletions@CUnbufferedWriter@@QEAAXK@Z; CUnbufferedWriter::ProcessCompletions(ulong)
0x18000d161  mov     rcx, [rdi+48h]; hHandle
0x18000d165  lea     r8d, [rbx+1]; bAlertable
0x18000d169  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000d16c  call    cs:__imp_WaitForSingleObjectEx
0x18000d172  mov     rcx, rdi; this
0x18000d175  call    ?FindCurrentOperation@CUnbufferedWriter@@AEAAPEAUCAsyncOperation@@XZ; CUnbufferedWriter::FindCurrentOperation(void)
0x18000d17a  mov     rsi, rax
0x18000d17d  test    rax, rax
0x18000d180  jz      short loc_18000D1E1
0x18000d182  mov     eax, [rdi+34h]
0x18000d185  test    eax, eax
0x18000d187  jnz     short loc_18000D1D0
0x18000d189  mov     ecx, [rsi+28h]
0x18000d18c  mov     r15d, ebp
0x18000d18f  mov     edx, [rdi+28h]
0x18000d192  sub     edx, ecx
0x18000d194  add     rcx, [rsi+20h]; void *
0x18000d198  cmp     ebp, edx
0x18000d19a  cmova   r15d, edx
0x18000d19e  mov     rdx, r14; Src
0x18000d1a1  mov     r8d, r15d; Size
0x18000d1a4  mov     r12d, r15d
0x18000d1a7  call    memcpy_0
0x18000d1ac  add     [rsi+28h], r15d
0x18000d1b0  mov     eax, [rsi+28h]
0x18000d1b3  cmp     eax, [rdi+28h]
0x18000d1b6  jnz     short loc_18000D1C6
0x18000d1b8  mov     rcx, rdi; this
0x18000d1bb  call    ?SubmitWriteOperation@CUnbufferedWriter@@AEAAJXZ; CUnbufferedWriter::SubmitWriteOperation(void)
0x18000d1c0  mov     ebx, eax
0x18000d1c2  test    eax, eax
0x18000d1c4  js      short loc_18000D1E6
0x18000d1c6  sub     ebp, r15d
0x18000d1c9  jz      short loc_18000D1E6
0x18000d1cb  add     r14, r12
0x18000d1ce  jmp     short loc_18000D172
0x18000d1d0  jg      short loc_18000D1D6
0x18000d1d2  mov     ebx, eax
0x18000d1d4  jmp     short loc_18000D1E6
0x18000d1d6  movzx   ebx, ax
0x18000d1d9  or      ebx, 80070000h
0x18000d1df  jmp     short loc_18000D1E6
0x18000d1e1  mov     ebx, 8000FFFFh
0x18000d1e6  mov     rcx, [rdi+48h]; hMutex
0x18000d1ea  call    cs:__imp_ReleaseMutex
0x18000d1f0  mov     eax, ebx
0x18000d1f2  add     rsp, 20h
0x18000d1f6  pop     r15
0x18000d1f8  pop     r14
0x18000d1fa  pop     r12
0x18000d1fc  pop     rdi
0x18000d1fd  pop     rsi
0x18000d1fe  pop     rbp
0x18000d1ff  pop     rbx
0x18000d200  retn
```
