# fcopy

- ea: `0x1800a8ae0`
- end: `0x1800a8c37`
- name: `fcopy`
- size: `343`
- prototype: `__int64 __fastcall(HANDLE hFile, HANDLE)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800a0b44`
- `0x1800a72b0`
- `0x1800a9708`

## callees

- `0x18009f590`
- `0x1800a8ae0`

## import_xrefs

- `msvcrt!free` at `0x1800a8bd7`
- `msvcrt!free` at `0x1800a8bed`
- `msvcrt!free` at `0x1800a8c03`
- `msvcrt!free` at `0x1800a8c16`
- `msvcrt!free` at `0x1800a8bd7`
- `msvcrt!free` at `0x1800a8bed`
- `msvcrt!free` at `0x1800a8c03`
- `msvcrt!free` at `0x1800a8c16`
- `msvcrt!malloc` at `0x1800a8b14`
- `msvcrt!malloc` at `0x1800a8b14`
- `KERNEL32!ReadFile` at `0x1800a8b6b`
- `KERNEL32!ReadFile` at `0x1800a8b6b`
- `KERNEL32!WriteFile` at `0x1800a8b9d`
- `KERNEL32!WriteFile` at `0x1800a8b9d`

## pseudocode

```c
__int64 __fastcall fcopy(HANDLE hFile, HANDLE a2, __int64 a3, __int64 a4)
{
  void *v8; // rbx
  __int64 i; // rdi
  DWORD v11; // r8d
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-48h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+34h] [rbp-44h] BYREF

  NumberOfBytesRead = 0;
  NumberOfBytesWritten = 0;
  v8 = malloc(0x2000u);
  if ( !v8 )
    return 4;
  for ( i = 0; ; i += NumberOfBytesWritten )
  {
    if ( a3 == -1 )
      goto LABEL_8;
    if ( i >= a3 )
      goto LABEL_17;
    if ( a3 - i >= 0x2000 )
LABEL_8:
      v11 = 0x2000;
    else
      v11 = a3 - i;
    if ( !ReadFile(hFile, v8, v11, &NumberOfBytesRead, 0) )
      break;
    if ( !NumberOfBytesRead )
    {
LABEL_17:
      free(v8);
      return 0;
    }
    if ( !WriteFile(a2, v8, NumberOfBytesRead, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != NumberOfBytesRead )
    {
      free(v8);
      return 10;
    }
    CheckForAbort(a4);
    if ( *(_DWORD *)(a4 + 208) )
    {
      free(v8);
      return 9;
    }
  }
  free(v8);
  return 11;
}

```

## disassembly

```asm
0x1800a8ae0  push    rbx
0x1800a8ae2  push    rbp
0x1800a8ae3  push    rsi
0x1800a8ae4  push    rdi
0x1800a8ae5  push    r13
0x1800a8ae7  push    r14
0x1800a8ae9  push    r15
0x1800a8aeb  sub     rsp, 40h
0x1800a8aef  mov     r15, rcx
0x1800a8af2  mov     [rsp+78h+NumberOfBytesRead], 0
0x1800a8afa  mov     r13d, 2000h
0x1800a8b00  mov     [rsp+78h+NumberOfBytesWritten], 0
0x1800a8b08  mov     ecx, r13d; Size
0x1800a8b0b  mov     rbp, r9
0x1800a8b0e  mov     rsi, r8
0x1800a8b11  mov     r14, rdx
0x1800a8b14  call    cs:__imp_malloc
0x1800a8b1b  nop     dword ptr [rax+rax+00h]
0x1800a8b20  mov     rbx, rax
0x1800a8b23  test    rax, rax
0x1800a8b26  jnz     short loc_1800A8B30
0x1800a8b28  lea     eax, [rbx+4]
0x1800a8b2b  jmp     loc_1800A8C27
0x1800a8b30  xor     edi, edi
0x1800a8b32  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800a8b36  jz      short loc_1800A8B54
0x1800a8b38  cmp     rdi, rsi
0x1800a8b3b  jge     loc_1800A8C00
0x1800a8b41  mov     rax, rsi
0x1800a8b44  sub     rax, rdi
0x1800a8b47  cmp     rax, r13
0x1800a8b4a  jge     short loc_1800A8B54
0x1800a8b4c  mov     r8d, esi
0x1800a8b4f  sub     r8d, edi
0x1800a8b52  jmp     short loc_1800A8B57
0x1800a8b54  mov     r8d, r13d; nNumberOfBytesToRead
0x1800a8b57  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800a8b5c  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x1800a8b65  mov     rdx, rbx; lpBuffer
0x1800a8b68  mov     rcx, r15; hFile
0x1800a8b6b  call    cs:__imp_ReadFile
0x1800a8b72  nop     dword ptr [rax+rax+00h]
0x1800a8b77  test    eax, eax
0x1800a8b79  jz      loc_1800A8C13
0x1800a8b7f  mov     r8d, [rsp+78h+NumberOfBytesRead]; nNumberOfBytesToWrite
0x1800a8b84  test    r8d, r8d
0x1800a8b87  jz      short loc_1800A8C00
0x1800a8b89  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800a8b8e  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x1800a8b97  mov     rdx, rbx; lpBuffer
0x1800a8b9a  mov     rcx, r14; hFile
0x1800a8b9d  call    cs:__imp_WriteFile
0x1800a8ba4  nop     dword ptr [rax+rax+00h]
0x1800a8ba9  test    eax, eax
0x1800a8bab  jz      short loc_1800A8BEA
0x1800a8bad  mov     eax, [rsp+78h+NumberOfBytesRead]
0x1800a8bb1  cmp     [rsp+78h+NumberOfBytesWritten], eax
0x1800a8bb5  jnz     short loc_1800A8BEA
0x1800a8bb7  mov     rcx, rbp
0x1800a8bba  call    CheckForAbort
0x1800a8bbf  cmp     dword ptr [rbp+0D0h], 0
0x1800a8bc6  jnz     short loc_1800A8BD4
0x1800a8bc8  mov     eax, [rsp+78h+NumberOfBytesWritten]
0x1800a8bcc  add     rdi, rax
0x1800a8bcf  jmp     loc_1800A8B32
0x1800a8bd4  mov     rcx, rbx; Block
0x1800a8bd7  call    cs:__imp_free
0x1800a8bde  nop     dword ptr [rax+rax+00h]
0x1800a8be3  mov     eax, 9
0x1800a8be8  jmp     short loc_1800A8C27
0x1800a8bea  mov     rcx, rbx; Block
0x1800a8bed  call    cs:__imp_free
0x1800a8bf4  nop     dword ptr [rax+rax+00h]
0x1800a8bf9  mov     eax, 0Ah
0x1800a8bfe  jmp     short loc_1800A8C27
0x1800a8c00  mov     rcx, rbx; Block
0x1800a8c03  call    cs:__imp_free
0x1800a8c0a  nop     dword ptr [rax+rax+00h]
0x1800a8c0f  xor     eax, eax
0x1800a8c11  jmp     short loc_1800A8C27
0x1800a8c13  mov     rcx, rbx; Block
0x1800a8c16  call    cs:__imp_free
0x1800a8c1d  nop     dword ptr [rax+rax+00h]
0x1800a8c22  mov     eax, 0Bh
0x1800a8c27  add     rsp, 40h
0x1800a8c2b  pop     r15
0x1800a8c2d  pop     r14
0x1800a8c2f  pop     r13
0x1800a8c31  pop     rdi
0x1800a8c32  pop     rsi
0x1800a8c33  pop     rbp
0x1800a8c34  pop     rbx
0x1800a8c35  retn
```
