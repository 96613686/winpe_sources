# CPVRAsyncWriter::SetPVRFileLength_(unsigned __int64)

- ea: `0x18007b8b0`
- end: `0x18007b925`
- name: `?SetPVRFileLength_@CPVRAsyncWriter@@IEAAK_K@Z`
- size: `117`
- prototype: `unsigned int __fastcall(CPVRAsyncWriter *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18007935c`
- `0x18007a424`

## callees

- `0x18007b8b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007b8ee`
- `KERNEL32!GetLastError` at `0x18007b907`
- `KERNEL32!GetLastError` at `0x18007b8ee`
- `KERNEL32!GetLastError` at `0x18007b907`
- `KERNEL32!SetFilePointerEx` at `0x18007b8e0`
- `KERNEL32!SetFilePointerEx` at `0x18007b8e0`
- `KERNEL32!SetEndOfFile` at `0x18007b8fd`
- `KERNEL32!SetEndOfFile` at `0x18007b8fd`

## pseudocode

```c
__int64 __fastcall CPVRAsyncWriter::SetPVRFileLength_(LARGE_INTEGER *this, LARGE_INTEGER a2)
{
  void *QuadPart; // rbp
  DWORD LastError; // ebx

  QuadPart = (void *)this[3].QuadPart;
  if ( SetFilePointerEx(QuadPart, a2, 0, 0) )
  {
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
      return LastError;
  }
  if ( SetEndOfFile(QuadPart) || (LastError = GetLastError()) == 0 )
    this[16] = a2;
  return LastError;
}

```

## disassembly

```asm
0x18007b8b0  push    rbx
0x18007b8b2  push    rbp
0x18007b8b3  push    rsi
0x18007b8b4  push    rdi
0x18007b8b5  sub     rsp, 28h
0x18007b8b9  mov     rbp, [rcx+18h]
0x18007b8bd  mov     rax, rdx
0x18007b8c0  mov     rdi, rdx
0x18007b8c3  shr     rax, 20h
0x18007b8c7  mov     dword ptr [rsp+48h+liDistanceToMove+4], eax
0x18007b8cb  mov     rsi, rcx
0x18007b8ce  mov     dword ptr [rsp+48h+liDistanceToMove], edi
0x18007b8d2  xor     r9d, r9d; dwMoveMethod
0x18007b8d5  mov     rdx, qword ptr [rsp+48h+liDistanceToMove]; liDistanceToMove
0x18007b8da  xor     r8d, r8d; lpNewFilePointer
0x18007b8dd  mov     rcx, rbp; hFile
0x18007b8e0  call    cs:__imp_SetFilePointerEx
0x18007b8e6  test    eax, eax
0x18007b8e8  jz      short loc_18007B8EE
0x18007b8ea  xor     ebx, ebx
0x18007b8ec  jmp     short loc_18007B8FA
0x18007b8ee  call    cs:__imp_GetLastError
0x18007b8f4  mov     ebx, eax
0x18007b8f6  test    eax, eax
0x18007b8f8  jnz     short loc_18007B91A
0x18007b8fa  mov     rcx, rbp; hFile
0x18007b8fd  call    cs:__imp_SetEndOfFile
0x18007b903  test    eax, eax
0x18007b905  jnz     short loc_18007B913
0x18007b907  call    cs:__imp_GetLastError
0x18007b90d  mov     ebx, eax
0x18007b90f  test    eax, eax
0x18007b911  jnz     short loc_18007B91A
0x18007b913  mov     [rsi+80h], rdi
0x18007b91a  mov     eax, ebx
0x18007b91c  add     rsp, 28h
0x18007b920  pop     rdi
0x18007b921  pop     rsi
0x18007b922  pop     rbp
0x18007b923  pop     rbx
0x18007b924  retn
```
