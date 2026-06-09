# fcopy

- ea: `0x18001b4ac`
- end: `0x18001b5fa`
- name: `fcopy`
- size: `334`
- prototype: `__int64 __fastcall(HANDLE hFile, HANDLE, __int64, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001a6cc`
- `0x18001b658`
- `0x1800269f0`

## callees

- `0x18001b4ac`
- `0x18001b600`
- `0x180036f50`
- `0x18003791c`
- `0x180037928`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001b54f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001b54f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001b51f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001b51f`

## pseudocode

```c
__int64 __fastcall fcopy(HANDLE hFile, HANDLE a2, __int64 a3, __int64 a4)
{
  void *v8; // rbx
  __int64 i; // rdi
  DWORD v10; // r8d
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-48h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+34h] [rbp-44h] BYREF

  NumberOfBytesRead = 0;
  NumberOfBytesWritten = 0;
  v8 = o_malloc_0(0x2000u);
  if ( !v8 )
    return 4;
  for ( i = 0; ; i += NumberOfBytesWritten )
  {
    if ( a3 == -1 )
      goto LABEL_4;
    if ( i >= a3 )
      goto LABEL_16;
    if ( a3 - i >= 0x2000 )
LABEL_4:
      v10 = 0x2000;
    else
      v10 = a3 - i;
    if ( !ReadFile(hFile, v8, v10, &NumberOfBytesRead, 0) )
    {
      free(v8);
      return 11;
    }
    if ( !NumberOfBytesRead )
    {
LABEL_16:
      free(v8);
      return 0;
    }
    if ( !WriteFile(a2, v8, NumberOfBytesRead, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != NumberOfBytesRead )
      break;
    CheckForAbort(a4);
    if ( *(_DWORD *)(a4 + 200) )
    {
      free(v8);
      return 9;
    }
  }
  free(v8);
  return 10;
}

```

## disassembly

```asm
0x18001b4ac  push    rbx
0x18001b4ae  push    rbp
0x18001b4af  push    rsi
0x18001b4b0  push    rdi
0x18001b4b1  push    r13
0x18001b4b3  push    r14
0x18001b4b5  push    r15
0x18001b4b7  sub     rsp, 40h
0x18001b4bb  mov     rax, cs:__security_cookie
0x18001b4c2  xor     rax, rsp
0x18001b4c5  mov     [rsp+78h+var_40], rax
0x18001b4ca  mov     r14, rcx
0x18001b4cd  mov     [rsp+78h+NumberOfBytesRead], 0
0x18001b4d5  mov     r13d, 2000h
0x18001b4db  mov     [rsp+78h+NumberOfBytesWritten], 0
0x18001b4e3  mov     ecx, r13d; Size
0x18001b4e6  mov     rbp, r9
0x18001b4e9  mov     rsi, r8
0x18001b4ec  mov     r15, rdx
0x18001b4ef  call    _o_malloc_0
0x18001b4f4  mov     rbx, rax
0x18001b4f7  test    rax, rax
0x18001b4fa  jz      loc_18001B5F3
0x18001b500  xor     edi, edi
0x18001b502  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001b506  jnz     short loc_18001B581
0x18001b508  mov     r8d, r13d; nNumberOfBytesToRead
0x18001b50b  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001b510  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18001b519  mov     rdx, rbx; lpBuffer
0x18001b51c  mov     rcx, r14; hFile
0x18001b51f  call    cs:__imp_ReadFile
0x18001b525  test    eax, eax
0x18001b527  jz      loc_18001B5C9
0x18001b52d  mov     r8d, [rsp+78h+NumberOfBytesRead]; nNumberOfBytesToWrite
0x18001b532  test    r8d, r8d
0x18001b535  jz      loc_18001B5D8
0x18001b53b  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001b540  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18001b549  mov     rdx, rbx; lpBuffer
0x18001b54c  mov     rcx, r15; hFile
0x18001b54f  call    cs:__imp_WriteFile
0x18001b555  test    eax, eax
0x18001b557  jz      loc_18001B5E4
0x18001b55d  mov     eax, [rsp+78h+NumberOfBytesRead]
0x18001b561  cmp     [rsp+78h+NumberOfBytesWritten], eax
0x18001b565  jnz     short loc_18001B5E4
0x18001b567  mov     rcx, rbp
0x18001b56a  call    CheckForAbort
0x18001b56f  cmp     dword ptr [rbp+0C8h], 0
0x18001b576  jnz     short loc_18001B5A0
0x18001b578  mov     eax, [rsp+78h+NumberOfBytesWritten]
0x18001b57c  add     rdi, rax
0x18001b57f  jmp     short loc_18001B502
0x18001b581  cmp     rdi, rsi
0x18001b584  jge     short loc_18001B5D8
0x18001b586  mov     rax, rsi
0x18001b589  sub     rax, rdi
0x18001b58c  cmp     rax, r13
0x18001b58f  jge     loc_18001B508
0x18001b595  mov     r8d, esi
0x18001b598  sub     r8d, edi
0x18001b59b  jmp     loc_18001B50B
0x18001b5a0  mov     rcx, rbx; Block
0x18001b5a3  call    free
0x18001b5a8  mov     eax, 9
0x18001b5ad  mov     rcx, [rsp+78h+var_40]
0x18001b5b2  xor     rcx, rsp; StackCookie
0x18001b5b5  call    __security_check_cookie
0x18001b5ba  add     rsp, 40h
0x18001b5be  pop     r15
0x18001b5c0  pop     r14
0x18001b5c2  pop     r13
0x18001b5c4  pop     rdi
0x18001b5c5  pop     rsi
0x18001b5c6  pop     rbp
0x18001b5c7  pop     rbx
0x18001b5c8  retn
0x18001b5c9  mov     rcx, rbx; Block
0x18001b5cc  call    free
0x18001b5d1  mov     eax, 0Bh
0x18001b5d6  jmp     short loc_18001B5AD
0x18001b5d8  mov     rcx, rbx; Block
0x18001b5db  call    free
0x18001b5e0  xor     eax, eax
0x18001b5e2  jmp     short loc_18001B5AD
0x18001b5e4  mov     rcx, rbx; Block
0x18001b5e7  call    free
0x18001b5ec  mov     eax, 0Ah
0x18001b5f1  jmp     short loc_18001B5AD
0x18001b5f3  mov     eax, 4
0x18001b5f8  jmp     short loc_18001B5AD
```
