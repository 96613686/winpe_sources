# CUnbufferedWriter::ProcessCompletions(ulong)

- ea: `0x18000cfa8`
- end: `0x18000d08b`
- name: `?ProcessCompletions@CUnbufferedWriter@@QEAAXK@Z`
- size: `227`
- prototype: `void __fastcall(CUnbufferedWriter *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000cc7c`
- `0x18000d140`
- `0x18000d2b4`

## callees

- `0x18000cfa8`
- `0x18002b010`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x18000d012`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000d012`
- `KERNEL32!GetLastError` at `0x18000cff8`
- `KERNEL32!GetLastError` at `0x18000cff8`
- `KERNEL32!ReleaseMutex` at `0x18000d052`
- `KERNEL32!ReleaseMutex` at `0x18000d052`

## pseudocode

```c
void __fastcall CUnbufferedWriter::ProcessCompletions(CUnbufferedWriter *this, int a2)
{
  unsigned int (__fastcall *i)(_QWORD, int *, __int64 *, __int64 *, int); // rax
  DWORD LastError; // edi
  __int64 v6; // rsi
  __int64 j; // r8
  __int64 v8; // rdx
  int v9; // [rsp+50h] [rbp+8h] BYREF
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF
  __int64 v11; // [rsp+68h] [rbp+20h] BYREF

  for ( i = *(unsigned int (__fastcall **)(_QWORD, int *, __int64 *, __int64 *, int))this;
        ;
        i = *(unsigned int (__fastcall **)(_QWORD, int *, __int64 *, __int64 *, int))this )
  {
    v10 = 0;
    v11 = 0;
    v9 = 0;
    if ( !i || !*((_DWORD *)this + 12) )
      break;
    LastError = 0;
    if ( !i(*((_QWORD *)this + 4), &v9, &v11, &v10, a2) )
    {
      if ( !v10 )
        return;
      LastError = GetLastError();
    }
    v6 = v10;
    WaitForSingleObjectEx(*((HANDLE *)this + 9), 0xFFFFFFFF, 1);
    for ( j = 0; (unsigned int)j < *((_DWORD *)this + 11); j = (unsigned int)(j + 1) )
    {
      v8 = *((_QWORD *)this + 10) + 48 * j;
      if ( v8 == v6 )
      {
        if ( v8 )
        {
          if ( LastError )
            *((_DWORD *)this + 13) = LastError;
          *(_QWORD *)(v8 + 40) = 0;
          --*((_DWORD *)this + 12);
        }
        break;
      }
    }
    ReleaseMutex(*((HANDLE *)this + 9));
  }
}

```

## disassembly

```asm
0x18000cfa8  mov     [rsp+arg_8], rbx
0x18000cfad  push    rbp
0x18000cfae  push    rsi
0x18000cfaf  push    rdi
0x18000cfb0  sub     rsp, 30h
0x18000cfb4  mov     rax, [rcx]
0x18000cfb7  mov     ebp, edx
0x18000cfb9  mov     rbx, rcx
0x18000cfbc  jmp     loc_18000D05B
0x18000cfc1  cmp     dword ptr [rbx+30h], 0
0x18000cfc5  jbe     loc_18000D07E
0x18000cfcb  mov     rcx, [rbx+20h]
0x18000cfcf  lea     r9, [rsp+48h+arg_10]
0x18000cfd4  lea     r8, [rsp+48h+arg_18]
0x18000cfd9  mov     [rsp+48h+var_28], ebp
0x18000cfdd  lea     rdx, [rsp+48h+arg_0]
0x18000cfe2  xor     edi, edi
0x18000cfe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfe9  test    eax, eax
0x18000cfeb  jnz     short loc_18000D000
0x18000cfed  cmp     [rsp+48h+arg_10], rdi
0x18000cff2  jz      loc_18000D07E
0x18000cff8  call    cs:__imp_GetLastError
0x18000cffe  mov     edi, eax
0x18000d000  mov     rcx, [rbx+48h]; hHandle
0x18000d004  mov     r8d, 1; bAlertable
0x18000d00a  mov     rsi, [rsp+48h+arg_10]
0x18000d00f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000d012  call    cs:__imp_WaitForSingleObjectEx
0x18000d018  xor     r8d, r8d
0x18000d01b  cmp     r8d, [rbx+2Ch]
0x18000d01f  jnb     short loc_18000D04E
0x18000d021  lea     rdx, [r8+r8*2]
0x18000d025  shl     rdx, 4
0x18000d029  add     rdx, [rbx+50h]
0x18000d02d  cmp     rdx, rsi
0x18000d030  jz      short loc_18000D037
0x18000d032  inc     r8d
0x18000d035  jmp     short loc_18000D01B
0x18000d037  test    rdx, rdx
0x18000d03a  jz      short loc_18000D04E
0x18000d03c  test    edi, edi
0x18000d03e  jz      short loc_18000D043
0x18000d040  mov     [rbx+34h], edi
0x18000d043  mov     qword ptr [rdx+28h], 0
0x18000d04b  dec     dword ptr [rbx+30h]
0x18000d04e  mov     rcx, [rbx+48h]; hMutex
0x18000d052  call    cs:__imp_ReleaseMutex
0x18000d058  mov     rax, [rbx]
0x18000d05b  mov     [rsp+48h+arg_10], 0
0x18000d064  mov     [rsp+48h+arg_18], 0
0x18000d06d  mov     [rsp+48h+arg_0], 0
0x18000d075  test    rax, rax
0x18000d078  jnz     loc_18000CFC1
0x18000d07e  mov     rbx, [rsp+48h+arg_8]
0x18000d083  add     rsp, 30h
0x18000d087  pop     rdi
0x18000d088  pop     rsi
0x18000d089  pop     rbp
0x18000d08a  retn
```
