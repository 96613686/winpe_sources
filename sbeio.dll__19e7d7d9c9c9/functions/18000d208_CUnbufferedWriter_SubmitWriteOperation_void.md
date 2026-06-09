# CUnbufferedWriter::SubmitWriteOperation(void)

- ea: `0x18000d208`
- end: `0x18000d2ae`
- name: `?SubmitWriteOperation@CUnbufferedWriter@@AEAAJXZ`
- size: `166`
- prototype: `__int64 __fastcall(CUnbufferedWriter *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000d140`

## callees

- `0x18000d208`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d275`
- `KERNEL32!GetLastError` at `0x18000d275`
- `KERNEL32!WriteFile` at `0x18000d26b`
- `KERNEL32!WriteFile` at `0x18000d26b`

## pseudocode

```c
__int64 __fastcall CUnbufferedWriter::SubmitWriteOperation(CUnbufferedWriter *this)
{
  __int64 i; // rcx
  __int64 lpOverlapped; // rdx
  __int64 v4; // rax
  signed int LastError; // eax
  unsigned int v6; // ecx

  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= *((_DWORD *)this + 11) )
      return (unsigned int)-2147418113;
    lpOverlapped = *((_QWORD *)this + 10) + 48 * i;
    if ( *(_DWORD *)(lpOverlapped + 44) == 1 )
      break;
  }
  if ( !lpOverlapped )
    return (unsigned int)-2147418113;
  *(_DWORD *)(lpOverlapped + 16) = *((_DWORD *)this + 14);
  v4 = *((_QWORD *)this + 7);
  *(_QWORD *)(lpOverlapped + 24) = 0;
  *(_DWORD *)(lpOverlapped + 44) = 2;
  *(_DWORD *)(lpOverlapped + 20) = HIDWORD(v4);
  if ( WriteFile(
         *((HANDLE *)this + 3),
         *(LPCVOID *)(lpOverlapped + 32),
         *((_DWORD *)this + 10),
         0,
         (LPOVERLAPPED)lpOverlapped)
    || (LastError = GetLastError(), v6 = LastError, LastError == 997) )
  {
    v6 = 0;
    *((_QWORD *)this + 7) += *((unsigned int *)this + 10);
    ++*((_DWORD *)this + 12);
  }
  else if ( LastError > 0 )
  {
    return (unsigned __int16)LastError | 0x80070000;
  }
  return v6;
}

```

## disassembly

```asm
0x18000d208  push    rbx
0x18000d20a  sub     rsp, 30h
0x18000d20e  mov     rbx, rcx
0x18000d211  xor     ecx, ecx
0x18000d213  cmp     ecx, [rbx+2Ch]
0x18000d216  jnb     loc_18000D2A1
0x18000d21c  lea     rdx, [rcx+rcx*2]
0x18000d220  shl     rdx, 4
0x18000d224  add     rdx, [rbx+50h]
0x18000d228  cmp     dword ptr [rdx+2Ch], 1
0x18000d22c  jz      short loc_18000D232
0x18000d22e  inc     ecx
0x18000d230  jmp     short loc_18000D213
0x18000d232  test    rdx, rdx
0x18000d235  jz      short loc_18000D2A1
0x18000d237  mov     eax, [rbx+38h]
0x18000d23a  xor     r9d, r9d; lpNumberOfBytesWritten
0x18000d23d  mov     [rdx+10h], eax
0x18000d240  mov     rax, [rbx+38h]
0x18000d244  mov     qword ptr [rdx+18h], 0
0x18000d24c  mov     dword ptr [rdx+2Ch], 2
0x18000d253  shr     rax, 20h
0x18000d257  mov     [rdx+14h], eax
0x18000d25a  mov     r8d, [rbx+28h]; nNumberOfBytesToWrite
0x18000d25e  mov     rcx, [rbx+18h]; hFile
0x18000d262  mov     [rsp+38h+lpOverlapped], rdx; lpOverlapped
0x18000d267  mov     rdx, [rdx+20h]; lpBuffer
0x18000d26b  call    cs:__imp_WriteFile
0x18000d271  test    eax, eax
0x18000d273  jnz     short loc_18000D293
0x18000d275  call    cs:__imp_GetLastError
0x18000d27b  mov     ecx, eax
0x18000d27d  cmp     eax, 3E5h
0x18000d282  jz      short loc_18000D293
0x18000d284  test    eax, eax
0x18000d286  jle     short loc_18000D2A6
0x18000d288  movzx   ecx, ax
0x18000d28b  or      ecx, 80070000h
0x18000d291  jmp     short loc_18000D2A6
0x18000d293  mov     eax, [rbx+28h]
0x18000d296  xor     ecx, ecx
0x18000d298  add     [rbx+38h], rax
0x18000d29c  inc     dword ptr [rbx+30h]
0x18000d29f  jmp     short loc_18000D2A6
0x18000d2a1  mov     ecx, 8000FFFFh
0x18000d2a6  mov     eax, ecx
0x18000d2a8  add     rsp, 30h
0x18000d2ac  pop     rbx
0x18000d2ad  retn
```
