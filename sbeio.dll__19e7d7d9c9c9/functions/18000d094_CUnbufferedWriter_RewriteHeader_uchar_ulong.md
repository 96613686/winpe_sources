# CUnbufferedWriter::RewriteHeader(uchar *,ulong)

- ea: `0x18000d094`
- end: `0x18000d138`
- name: `?RewriteHeader@CUnbufferedWriter@@QEAAJPEAEK@Z`
- size: `164`
- prototype: `int(CUnbufferedWriter *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180009630`

## callees

- `0x18000d094`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d116`
- `KERNEL32!GetLastError` at `0x18000d116`
- `KERNEL32!SetFilePointer` at `0x18000d0e1`
- `KERNEL32!SetFilePointer` at `0x18000d0e1`
- `KERNEL32!WriteFile` at `0x18000d104`
- `KERNEL32!WriteFile` at `0x18000d104`

## pseudocode

```c
int __fastcall CUnbufferedWriter::RewriteHeader(CUnbufferedWriter *this, unsigned __int8 *a2, DWORD a3)
{
  bool v3; // zf
  int result; // eax
  void *v8; // rcx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF
  LONG DistanceToMoveHigh; // [rsp+58h] [rbp+20h] BYREF

  v3 = *((_DWORD *)this + 16) == 0;
  NumberOfBytesWritten = 0;
  DistanceToMoveHigh = 0;
  if ( v3 )
    return -2147418113;
  v8 = (void *)*((_QWORD *)this + 3);
  if ( v8 == (void *)-1LL )
  {
    result = *((_DWORD *)this + 13);
    goto LABEL_9;
  }
  if ( SetFilePointer(v8, 0, &DistanceToMoveHigh, 0) == -1
    || !WriteFile(*((HANDLE *)this + 3), a2, a3, &NumberOfBytesWritten, 0)
    || (result = 0, a3 != NumberOfBytesWritten) )
  {
    result = GetLastError();
LABEL_9:
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18000d094  mov     rax, rsp
0x18000d097  mov     [rax+10h], rbx
0x18000d09b  mov     [rax+18h], rsi
0x18000d09f  push    rdi
0x18000d0a0  sub     rsp, 30h
0x18000d0a4  cmp     dword ptr [rcx+40h], 0
0x18000d0a8  mov     edi, r8d
0x18000d0ab  mov     rsi, rdx
0x18000d0ae  mov     dword ptr [rax+8], 0
0x18000d0b5  mov     rbx, rcx
0x18000d0b8  mov     dword ptr [rax+20h], 0
0x18000d0bf  jnz     short loc_18000D0C8
0x18000d0c1  mov     eax, 8000FFFFh
0x18000d0c6  jmp     short loc_18000D128
0x18000d0c8  mov     rcx, [rcx+18h]; hFile
0x18000d0cc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000d0d0  jnz     short loc_18000D0D7
0x18000d0d2  mov     eax, [rbx+34h]
0x18000d0d5  jmp     short loc_18000D11C
0x18000d0d7  xor     r9d, r9d; dwMoveMethod
0x18000d0da  lea     r8, [rsp+38h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x18000d0df  xor     edx, edx; lDistanceToMove
0x18000d0e1  call    cs:__imp_SetFilePointer
0x18000d0e7  cmp     eax, 0FFFFFFFFh
0x18000d0ea  jz      short loc_18000D116
0x18000d0ec  mov     rcx, [rbx+18h]; hFile
0x18000d0f0  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000d0f5  mov     r8d, edi; nNumberOfBytesToWrite
0x18000d0f8  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18000d101  mov     rdx, rsi; lpBuffer
0x18000d104  call    cs:__imp_WriteFile
0x18000d10a  test    eax, eax
0x18000d10c  jz      short loc_18000D116
0x18000d10e  xor     eax, eax
0x18000d110  cmp     edi, [rsp+38h+NumberOfBytesWritten]
0x18000d114  jz      short loc_18000D128
0x18000d116  call    cs:__imp_GetLastError
0x18000d11c  test    eax, eax
0x18000d11e  jle     short loc_18000D128
0x18000d120  movzx   eax, ax
0x18000d123  or      eax, 80070000h
0x18000d128  mov     rbx, [rsp+38h+arg_8]
0x18000d12d  mov     rsi, [rsp+38h+arg_10]
0x18000d132  add     rsp, 30h
0x18000d136  pop     rdi
0x18000d137  retn
```
