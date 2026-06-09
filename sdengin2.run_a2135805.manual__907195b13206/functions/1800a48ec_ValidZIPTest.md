# ValidZIPTest

- ea: `0x1800a48ec`
- end: `0x1800a4bd3`
- name: `ValidZIPTest`
- size: `743`
- prototype: `__int64 __fastcall(LPCSTR lpFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800a5c24`

## callees

- `0x1800a236c`
- `0x1800a2f88`
- `0x1800a48ec`
- `0x1800a84d0`
- `0x1800a8544`

## import_xrefs

- `KERNEL32!GlobalUnlock` at `0x1800a4b9b`
- `KERNEL32!GlobalUnlock` at `0x1800a4b9b`
- `KERNEL32!lstrcmpA` at `0x1800a492b`
- `KERNEL32!lstrcmpA` at `0x1800a492b`
- `KERNEL32!GlobalLock` at `0x1800a4a25`
- `KERNEL32!GlobalLock` at `0x1800a4a25`
- `KERNEL32!ReadFile` at `0x1800a4a53`
- `KERNEL32!ReadFile` at `0x1800a4a53`
- `KERNEL32!CloseHandle` at `0x1800a49b6`
- `KERNEL32!CloseHandle` at `0x1800a4b5a`
- `KERNEL32!CloseHandle` at `0x1800a49b6`
- `KERNEL32!CloseHandle` at `0x1800a4b5a`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800a4963`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800a4963`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800a4a0e`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800a4a0e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a4baf`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a4baf`

## pseudocode

```c
__int64 __fastcall ValidZIPTest(LPCSTR lpFileName, __int64 a2)
{
  int v4; // r13d
  HANDLE FileA; // rax
  void *v6; // r15
  __int64 v7; // rbp
  unsigned int v8; // esi
  _BYTE *v10; // r14
  __int64 v11; // rdi
  void *v12; // rdi
  unsigned int v13; // ebx
  DWORD v14; // r13d
  HGLOBAL v15; // rax
  void *v16; // rax
  __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rdx
  char v20; // r9
  __int64 v21; // rax
  char v22; // bp
  int v23; // r10d
  char v24; // r11
  unsigned int v25; // eax
  DWORD NumberOfBytesRead; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v29; // [rsp+A8h] [rbp+20h]

  NumberOfBytesRead = 0;
  if ( lpFileName
    && *lpFileName
    && lstrcmpA(lpFileName, "-")
    && (v4 = 3, FileA = CreateFileA(lpFileName, 0x80000000, 0, 0, 3u, 0x80u, 0), v6 = FileA, FileA != (HANDLE)-1LL) )
  {
    v7 = DZGetFileSize(FileA);
    if ( (!*(_DWORD *)(a2 + 624) || *(_DWORD *)(a2 + 628)) && v7 >= 0xFFFFFFFFLL )
    {
      v8 = 8;
LABEL_11:
      CloseHandle(v6);
      return v8;
    }
    if ( v7 < 22 )
    {
      v8 = 11;
      goto LABEL_11;
    }
    v10 = 0;
    v11 = 65579;
    if ( v7 < 65579 )
      v11 = v7;
    v29 = v11;
    if ( DZSetFilePointer(v6, v7 - v11, 0) == v7 - v11 )
    {
      v14 = v11;
      v15 = GlobalAlloc(2u, (unsigned int)v11);
      v12 = v15;
      if ( v15 && (v16 = GlobalLock(v15), (v10 = v16) != 0) )
      {
        if ( !ReadFile(v6, v16, v14, &NumberOfBytesRead, 0) || (v13 = 0, NumberOfBytesRead != v14) )
          v13 = 11;
      }
      else
      {
        v13 = 4;
      }
      v4 = 3;
    }
    else
    {
      v12 = 0;
      v13 = 11;
    }
    v17 = v29;
    v18 = 22;
    if ( v7 != 22 )
      v18 = 18;
    v19 = v29 - v18;
    LODWORD(v29) = 0;
    do
    {
      if ( v13 || v19 < 0 || v18 > v17 )
        break;
      v20 = v10[v19];
      v21 = v19 + 2;
      v22 = v10[v19 + 1];
      v23 = 18 - v4;
      do
      {
        v24 = v10[v21++];
        if ( v20 == 80 && v22 == 75 && v24 == 5 && v10[v21] == 6 )
        {
          if ( v10[v21 + 1] || v10[v21 + 2] )
          {
            v13 = 21;
          }
          else
          {
            v13 = 0;
            LODWORD(v29) = 1;
          }
        }
        --v23;
        v20 = v22;
        v22 = v24;
      }
      while ( v23 > 0 );
      if ( !(_DWORD)v29 && v19 <= 0 )
        v13 = 11;
      v18 += 18;
      v19 = 0;
      v4 = 0;
      if ( v17 - v18 >= 0 )
        v19 = v17 - v18;
    }
    while ( !(_DWORD)v29 );
    CloseHandle(v6);
    if ( v13 == 11 )
    {
      v25 = dzDriveFromPath(lpFileName);
      if ( (unsigned int)dzIsMediaRemovable(v25, a2) )
        v13 = 21;
    }
    if ( v10 )
      GlobalUnlock(v12);
    if ( v12 )
      GlobalFree(v12);
  }
  else
  {
    return 0;
  }
  return v13;
}

```

## disassembly

```asm
0x1800a48ec  mov     rax, rsp
0x1800a48ef  mov     [rax+10h], rdx
0x1800a48f3  mov     [rax+8], rcx
0x1800a48f7  push    rbx
0x1800a48f8  push    rbp
0x1800a48f9  push    rsi
0x1800a48fa  push    rdi
0x1800a48fb  push    r12
0x1800a48fd  push    r13
0x1800a48ff  push    r14
0x1800a4901  push    r15
0x1800a4903  sub     rsp, 48h
0x1800a4907  xor     edi, edi
0x1800a4909  mov     rbx, rdx
0x1800a490c  mov     [rax+18h], edi
0x1800a490f  mov     r12, rcx
0x1800a4912  test    rcx, rcx
0x1800a4915  jz      loc_1800A4BBD
0x1800a491b  cmp     [rcx], dil
0x1800a491e  jz      loc_1800A4BBD
0x1800a4924  lea     rdx, asc_1800EE5BC; "-"
0x1800a492b  call    cs:__imp_lstrcmpA
0x1800a4932  nop     dword ptr [rax+rax+00h]
0x1800a4937  test    eax, eax
0x1800a4939  jz      loc_1800A4BBD
0x1800a493f  mov     [rsp+88h+hTemplateFile], rdi; hTemplateFile
0x1800a4944  lea     r13d, [rdi+3]
0x1800a4948  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800a4950  xor     r9d, r9d; lpSecurityAttributes
0x1800a4953  xor     r8d, r8d; dwShareMode
0x1800a4956  mov     [rsp+88h+dwCreationDisposition], r13d; dwCreationDisposition
0x1800a495b  mov     edx, 80000000h; dwDesiredAccess
0x1800a4960  mov     rcx, r12; lpFileName
0x1800a4963  call    cs:__imp_CreateFileA
0x1800a496a  nop     dword ptr [rax+rax+00h]
0x1800a496f  mov     r15, rax
0x1800a4972  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a4976  jz      loc_1800A4BBD
0x1800a497c  mov     rcx, rax
0x1800a497f  call    DZGetFileSize
0x1800a4984  mov     rbp, rax
0x1800a4987  cmp     [rbx+270h], edi
0x1800a498d  jz      short loc_1800A4997
0x1800a498f  cmp     [rbx+274h], edi
0x1800a4995  jz      short loc_1800A49A8
0x1800a4997  mov     eax, 0FFFFFFFFh
0x1800a499c  cmp     rbp, rax
0x1800a499f  jl      short loc_1800A49A8
0x1800a49a1  mov     esi, 8
0x1800a49a6  jmp     short loc_1800A49B3
0x1800a49a8  cmp     rbp, 16h
0x1800a49ac  jge     short loc_1800A49C9
0x1800a49ae  mov     esi, 0Bh
0x1800a49b3  mov     rcx, r15; hObject
0x1800a49b6  call    cs:__imp_CloseHandle
0x1800a49bd  nop     dword ptr [rax+rax+00h]
0x1800a49c2  mov     eax, esi
0x1800a49c4  jmp     loc_1800A4BC1
0x1800a49c9  mov     r14, rdi
0x1800a49cc  mov     rbx, rbp
0x1800a49cf  mov     edi, 1002Bh
0x1800a49d4  mov     rcx, r15
0x1800a49d7  cmp     rbp, rdi
0x1800a49da  cmovl   rdi, rbp
0x1800a49de  xor     r8d, r8d
0x1800a49e1  sub     rbx, rdi
0x1800a49e4  mov     [rsp+88h+arg_18], rdi
0x1800a49ec  mov     rdx, rbx
0x1800a49ef  call    DZSetFilePointer
0x1800a49f4  mov     esi, 0Bh
0x1800a49f9  cmp     rax, rbx
0x1800a49fc  jz      short loc_1800A4A04
0x1800a49fe  xor     edi, edi
0x1800a4a00  mov     ebx, esi
0x1800a4a02  jmp     short loc_1800A4A7E
0x1800a4a04  mov     edx, edi; dwBytes
0x1800a4a06  mov     ecx, 2; uFlags
0x1800a4a0b  mov     r13d, edi
0x1800a4a0e  call    cs:__imp_GlobalAlloc
0x1800a4a15  nop     dword ptr [rax+rax+00h]
0x1800a4a1a  mov     rdi, rax
0x1800a4a1d  test    rax, rax
0x1800a4a20  jz      short loc_1800A4A73
0x1800a4a22  mov     rcx, rax; hMem
0x1800a4a25  call    cs:__imp_GlobalLock
0x1800a4a2c  nop     dword ptr [rax+rax+00h]
0x1800a4a31  mov     r14, rax
0x1800a4a34  test    rax, rax
0x1800a4a37  jz      short loc_1800A4A73
0x1800a4a39  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800a4a41  mov     qword ptr [rsp+88h+dwCreationDisposition], 0; lpOverlapped
0x1800a4a4a  mov     r8d, r13d; nNumberOfBytesToRead
0x1800a4a4d  mov     rdx, rax; lpBuffer
0x1800a4a50  mov     rcx, r15; hFile
0x1800a4a53  call    cs:__imp_ReadFile
0x1800a4a5a  nop     dword ptr [rax+rax+00h]
0x1800a4a5f  test    eax, eax
0x1800a4a61  jz      short loc_1800A4A6F
0x1800a4a63  xor     ebx, ebx
0x1800a4a65  cmp     [rsp+88h+NumberOfBytesRead], r13d
0x1800a4a6d  jz      short loc_1800A4A78
0x1800a4a6f  mov     ebx, esi
0x1800a4a71  jmp     short loc_1800A4A78
0x1800a4a73  mov     ebx, 4
0x1800a4a78  mov     r13d, 3
0x1800a4a7e  mov     r8, [rsp+88h+arg_18]
0x1800a4a86  mov     ecx, 16h
0x1800a4a8b  cmp     rbp, rcx
0x1800a4a8e  mov     rdx, r8
0x1800a4a91  lea     r12d, [rcx-4]
0x1800a4a95  cmovnz  ecx, r12d
0x1800a4a99  sub     rdx, rcx
0x1800a4a9c  xor     r9d, r9d
0x1800a4a9f  mov     dword ptr [rsp+88h+arg_18], r9d
0x1800a4aa7  test    ebx, ebx
0x1800a4aa9  jnz     loc_1800A4B57
0x1800a4aaf  test    rdx, rdx
0x1800a4ab2  js      loc_1800A4B57
0x1800a4ab8  cmp     rcx, r8
0x1800a4abb  jg      loc_1800A4B57
0x1800a4ac1  mov     r9b, [r14+rdx]
0x1800a4ac5  lea     rax, [rdx+2]
0x1800a4ac9  mov     bpl, [r14+rdx+1]
0x1800a4ace  mov     r10d, r12d
0x1800a4ad1  sub     r10d, r13d
0x1800a4ad4  mov     r11b, [r14+rax]
0x1800a4ad8  inc     rax
0x1800a4adb  cmp     r9b, 50h ; 'P'
0x1800a4adf  jnz     short loc_1800A4B18
0x1800a4ae1  cmp     bpl, 4Bh ; 'K'
0x1800a4ae5  jnz     short loc_1800A4B18
0x1800a4ae7  cmp     r11b, 5
0x1800a4aeb  jnz     short loc_1800A4B18
0x1800a4aed  cmp     byte ptr [r14+rax], 6
0x1800a4af2  jnz     short loc_1800A4B18
0x1800a4af4  cmp     byte ptr [r14+rax+1], 0
0x1800a4afa  jnz     short loc_1800A4B13
0x1800a4afc  cmp     byte ptr [r14+rax+2], 0
0x1800a4b02  jnz     short loc_1800A4B13
0x1800a4b04  xor     ebx, ebx
0x1800a4b06  mov     dword ptr [rsp+88h+arg_18], 1
0x1800a4b11  jmp     short loc_1800A4B18
0x1800a4b13  mov     ebx, 15h
0x1800a4b18  dec     r10d
0x1800a4b1b  mov     r9b, bpl
0x1800a4b1e  mov     bpl, r11b
0x1800a4b21  test    r10d, r10d
0x1800a4b24  jg      short loc_1800A4AD4
0x1800a4b26  mov     r9d, dword ptr [rsp+88h+arg_18]
0x1800a4b2e  test    r9d, r9d
0x1800a4b31  jnz     short loc_1800A4B39
0x1800a4b33  test    rdx, rdx
0x1800a4b36  cmovle  ebx, esi
0x1800a4b39  add     rcx, r12
0x1800a4b3c  mov     edx, 0
0x1800a4b41  mov     rax, r8
0x1800a4b44  mov     r13d, edx
0x1800a4b47  sub     rax, rcx
0x1800a4b4a  cmovns  rdx, rax
0x1800a4b4e  test    r9d, r9d
0x1800a4b51  jz      loc_1800A4AA7
0x1800a4b57  mov     rcx, r15; hObject
0x1800a4b5a  call    cs:__imp_CloseHandle
0x1800a4b61  nop     dword ptr [rax+rax+00h]
0x1800a4b66  mov     r12, [rsp+88h+lpszStart]
0x1800a4b6e  cmp     ebx, esi
0x1800a4b70  jnz     short loc_1800A4B93
0x1800a4b72  mov     rcx, r12; lpszStart
0x1800a4b75  call    dzDriveFromPath
0x1800a4b7a  mov     rdx, [rsp+88h+arg_8]
0x1800a4b82  mov     ecx, eax
0x1800a4b84  call    dzIsMediaRemovable
0x1800a4b89  test    eax, eax
0x1800a4b8b  mov     eax, 15h
0x1800a4b90  cmovnz  ebx, eax
0x1800a4b93  test    r14, r14
0x1800a4b96  jz      short loc_1800A4BA7
0x1800a4b98  mov     rcx, rdi; hMem
0x1800a4b9b  call    cs:__imp_GlobalUnlock
0x1800a4ba2  nop     dword ptr [rax+rax+00h]
0x1800a4ba7  test    rdi, rdi
0x1800a4baa  jz      short loc_1800A4BBF
0x1800a4bac  mov     rcx, rdi; hMem
0x1800a4baf  call    cs:__imp_GlobalFree
0x1800a4bb6  nop     dword ptr [rax+rax+00h]
0x1800a4bbb  jmp     short loc_1800A4BBF
0x1800a4bbd  mov     ebx, edi
0x1800a4bbf  mov     eax, ebx
0x1800a4bc1  add     rsp, 48h
0x1800a4bc5  pop     r15
0x1800a4bc7  pop     r14
0x1800a4bc9  pop     r13
0x1800a4bcb  pop     r12
0x1800a4bcd  pop     rdi
0x1800a4bce  pop     rsi
0x1800a4bcf  pop     rbp
0x1800a4bd0  pop     rbx
0x1800a4bd1  retn
```
