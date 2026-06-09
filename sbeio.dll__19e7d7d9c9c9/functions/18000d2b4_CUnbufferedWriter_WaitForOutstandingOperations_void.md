# CUnbufferedWriter::WaitForOutstandingOperations(void)

- ea: `0x18000d2b4`
- end: `0x18000d33d`
- name: `?WaitForOutstandingOperations@CUnbufferedWriter@@QEAAJXZ`
- size: `137`
- prototype: `__int64 __fastcall(CUnbufferedWriter *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008aa0`
- `0x18000c914`
- `0x18000cb10`

## callees

- `0x18000cfa8`
- `0x18000d2b4`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x18000d2d6`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000d2d6`
- `KERNEL32!ReleaseMutex` at `0x18000d2fd`
- `KERNEL32!ReleaseMutex` at `0x18000d314`
- `KERNEL32!ReleaseMutex` at `0x18000d2fd`
- `KERNEL32!ReleaseMutex` at `0x18000d314`

## pseudocode

```c
__int64 __fastcall CUnbufferedWriter::WaitForOutstandingOperations(HANDLE *this)
{
  unsigned int v2; // ebx
  __int64 i; // rdx
  int v4; // eax

  v2 = 0;
LABEL_2:
  if ( this[10] )
  {
    WaitForSingleObjectEx(this[9], 0xFFFFFFFF, 1);
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 11); i = (unsigned int)(i + 1) )
    {
      if ( *((_DWORD *)this[10] + 12 * i + 11) == 2 )
      {
        ReleaseMutex(this[9]);
        CUnbufferedWriter::ProcessCompletions((CUnbufferedWriter *)this, -1);
        goto LABEL_2;
      }
    }
    ReleaseMutex(this[9]);
  }
  v4 = *((_DWORD *)this + 13);
  if ( v4 )
  {
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
    else
      return *((unsigned int *)this + 13);
  }
  return v2;
}

```

## disassembly

```asm
0x18000d2b4  mov     [rsp+arg_0], rbx
0x18000d2b9  push    rdi
0x18000d2ba  sub     rsp, 20h
0x18000d2be  mov     rdi, rcx
0x18000d2c1  xor     ebx, ebx
0x18000d2c3  cmp     [rdi+50h], rbx
0x18000d2c7  jz      short loc_18000D31A
0x18000d2c9  mov     rcx, [rdi+48h]; hHandle
0x18000d2cd  mov     r8d, 1; bAlertable
0x18000d2d3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000d2d6  call    cs:__imp_WaitForSingleObjectEx
0x18000d2dc  xor     edx, edx
0x18000d2de  cmp     edx, [rdi+2Ch]
0x18000d2e1  jnb     short loc_18000D310
0x18000d2e3  mov     rax, [rdi+50h]
0x18000d2e7  lea     rcx, [rdx+rdx*2]
0x18000d2eb  add     rcx, rcx
0x18000d2ee  cmp     dword ptr [rax+rcx*8+2Ch], 2
0x18000d2f3  jz      short loc_18000D2F9
0x18000d2f5  inc     edx
0x18000d2f7  jmp     short loc_18000D2DE
0x18000d2f9  mov     rcx, [rdi+48h]; hMutex
0x18000d2fd  call    cs:__imp_ReleaseMutex
0x18000d303  or      edx, 0FFFFFFFFh; unsigned int
0x18000d306  mov     rcx, rdi; this
0x18000d309  call    ?ProcessCompletions@CUnbufferedWriter@@QEAAXK@Z; CUnbufferedWriter::ProcessCompletions(ulong)
0x18000d30e  jmp     short loc_18000D2C3
0x18000d310  mov     rcx, [rdi+48h]; hMutex
0x18000d314  call    cs:__imp_ReleaseMutex
0x18000d31a  mov     eax, [rdi+34h]
0x18000d31d  test    eax, eax
0x18000d31f  jz      short loc_18000D330
0x18000d321  jg      short loc_18000D327
0x18000d323  mov     ebx, eax
0x18000d325  jmp     short loc_18000D330
0x18000d327  movzx   ebx, ax
0x18000d32a  or      ebx, 80070000h
0x18000d330  mov     eax, ebx
0x18000d332  mov     rbx, [rsp+28h+arg_0]
0x18000d337  add     rsp, 20h
0x18000d33b  pop     rdi
0x18000d33c  retn
```
