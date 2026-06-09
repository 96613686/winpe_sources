# SIPObjectCAB_::ReserveSignedData(ulong)

- ea: `0x18003e548`
- end: `0x18003e754`
- name: `?ReserveSignedData@SIPObjectCAB_@@AEAAHK@Z`
- size: `524`
- prototype: `__int64 __fastcall(SIPObjectCAB_ *this, DWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180012510`

## callees

- `0x18003e548`
- `0x18003e75c`
- `0x18003e8a4`
- `0x18004de52`
- `0x18004de6a`

## import_xrefs

- `msvcrt!free` at `0x18003e604`
- `msvcrt!free` at `0x18003e715`
- `msvcrt!free` at `0x18003e725`
- `msvcrt!free` at `0x18003e74c`
- `msvcrt!free` at `0x18003e604`
- `msvcrt!free` at `0x18003e715`
- `msvcrt!free` at `0x18003e725`
- `msvcrt!free` at `0x18003e74c`
- `msvcrt!malloc` at `0x18003e5b0`
- `msvcrt!malloc` at `0x18003e656`
- `msvcrt!malloc` at `0x18003e5b0`
- `msvcrt!malloc` at `0x18003e656`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003e56f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003e56f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003e67f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003e67f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003e6fe`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003e6fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e730`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e730`

## pseudocode

```c
__int64 __fastcall SIPObjectCAB_::ReserveSignedData(SIPObjectCAB_ *this, DWORD a2)
{
  unsigned int v3; // ebp
  DWORD v4; // r14d
  int v5; // esi
  _WORD *v6; // rax
  _WORD *v7; // r15
  _DWORD *v8; // rdi
  _QWORD *v9; // r12
  const void *v10; // rdx
  void *v11; // rcx
  int v12; // ebp
  unsigned int v13; // r15d
  _DWORD *v14; // rax
  _DWORD *v15; // rax
  void *v16; // rcx
  DWORD NumberOfBytesRead; // [rsp+88h] [rbp+10h] BYREF

  NumberOfBytesRead = a2;
  if ( SetFilePointer(*((HANDLE *)this + 1), *((_DWORD *)this + 40), 0, 0) == -1 )
    return 0;
  v3 = *((unsigned __int16 *)this + 74);
  v4 = 0;
  *((_DWORD *)this + 42) = 0;
  v5 = (((_WORD)v3 + 23) & 0xFFFC) - *((unsigned __int16 *)this + 58);
  if ( !v5 )
    return 1;
  v6 = malloc((unsigned __int16)(v3 + 23) & 0xFFFC);
  v7 = v6;
  if ( v6 )
  {
    v8 = 0;
    memset_0(v6, 0, ((_WORD)v3 + 23) & 0xFFFC);
    v9 = (_QWORD *)((char *)this + 128);
    if ( (_WORD)v3 )
    {
      v10 = (const void *)(*v9 + 4LL);
      *v7 = v3;
      memcpy_0(v7 + 2, v10, v3);
    }
    v11 = (void *)*v9;
    v7[1] = 16;
    free(v11);
    *v9 = v7;
    *((_WORD *)this + 58) = (v3 + 23) & 0xFFFC;
    *((_WORD *)this + 75) = 16;
    if ( !*((_WORD *)this + 60) )
    {
      *((_WORD *)this + 55) |= 4u;
      v5 += 4;
      *((_WORD *)this + 60) = 4;
    }
    v12 = *((unsigned __int16 *)this + 53);
    if ( !(_WORD)v12 )
      goto LABEL_14;
    v13 = *((unsigned __int8 *)this + 118) + 8;
    NumberOfBytesRead = 0;
    v4 = v13 * v12;
    v14 = malloc(v13 * v12);
    v8 = v14;
    if ( v14 )
    {
      if ( ReadFile(*((HANDLE *)this + 1), v14, v4, &NumberOfBytesRead, 0) && NumberOfBytesRead == v4 )
      {
        v15 = v8;
        do
        {
          *v15 += v5;
          v15 = (_DWORD *)((char *)v15 + v13);
          LOWORD(v12) = v12 - 1;
        }
        while ( (_WORD)v12 );
LABEL_14:
        if ( !(unsigned int)SIPObjectCAB_::ShiftFileBytes(this, v5)
          || (*((_DWORD *)this + 40) += v5,
              *((_DWORD *)this + 22) += v5,
              *((_DWORD *)this + 24) += v5,
              !(unsigned int)SIPObjectCAB_::WriteHeader(this)) )
        {
LABEL_23:
          free(v8);
          return 0;
        }
        if ( v8 )
        {
          v16 = (void *)*((_QWORD *)this + 1);
          NumberOfBytesRead = 0;
          if ( WriteFile(v16, v8, v4, &NumberOfBytesRead, 0) && NumberOfBytesRead == v4 )
          {
            free(v8);
            return 1;
          }
          goto LABEL_23;
        }
        return 1;
      }
      free(v8);
      SetLastError(0xBu);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003e548  mov     [rsp+NumberOfBytesRead], edx
0x18003e54c  push    rbx
0x18003e54d  push    rbp
0x18003e54e  push    rsi
0x18003e54f  push    rdi
0x18003e550  push    r12
0x18003e552  push    r13
0x18003e554  push    r14
0x18003e556  push    r15
0x18003e558  sub     rsp, 38h
0x18003e55c  mov     edx, [rcx+0A0h]; lDistanceToMove
0x18003e562  mov     rbx, rcx
0x18003e565  mov     rcx, [rcx+8]; hFile
0x18003e569  xor     r9d, r9d; dwMoveMethod
0x18003e56c  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003e56f  call    cs:__imp_SetFilePointer
0x18003e575  cmp     eax, 0FFFFFFFFh
0x18003e578  jz      loc_18003E736
0x18003e57e  movzx   ebp, word ptr [rbx+94h]
0x18003e585  xor     r14d, r14d
0x18003e588  mov     ecx, 0FFFCh
0x18003e58d  mov     [rbx+0A8h], r14d
0x18003e594  lea     eax, [rbp+17h]
0x18003e597  and     ax, cx
0x18003e59a  movzx   r13d, ax
0x18003e59e  movzx   eax, word ptr [rbx+74h]
0x18003e5a2  mov     esi, r13d
0x18003e5a5  sub     esi, eax
0x18003e5a7  jz      loc_18003E71B
0x18003e5ad  mov     ecx, r13d; Size
0x18003e5b0  call    cs:__imp_malloc
0x18003e5b6  mov     r15, rax
0x18003e5b9  test    rax, rax
0x18003e5bc  jz      loc_18003E736
0x18003e5c2  mov     r8d, r13d; Size
0x18003e5c5  xor     edx, edx; Val
0x18003e5c7  mov     rcx, rax; void *
0x18003e5ca  mov     edi, r14d
0x18003e5cd  call    memset_0
0x18003e5d2  lea     r12, [rbx+80h]
0x18003e5d9  test    bp, bp
0x18003e5dc  jz      short loc_18003E5F6
0x18003e5de  mov     rdx, [r12]
0x18003e5e2  lea     rcx, [r15+4]; void *
0x18003e5e6  add     rdx, 4; Src
0x18003e5ea  mov     [r15], bp
0x18003e5ee  mov     r8d, ebp; Size
0x18003e5f1  call    memcpy_0
0x18003e5f6  mov     rcx, [r12]; Block
0x18003e5fa  mov     ebp, 10h
0x18003e5ff  mov     [r15+2], bp
0x18003e604  call    cs:__imp_free
0x18003e60a  mov     [r12], r15
0x18003e60e  xor     r12d, r12d
0x18003e611  mov     [rbx+74h], r13w
0x18003e616  mov     [rbx+96h], bp
0x18003e61d  cmp     [rbx+78h], r12w
0x18003e622  jnz     short loc_18003E631
0x18003e624  lea     eax, [rbp-0Ch]
0x18003e627  or      [rbx+6Eh], ax
0x18003e62b  add     esi, eax
0x18003e62d  mov     [rbx+78h], ax
0x18003e631  movzx   ebp, word ptr [rbx+6Ah]
0x18003e635  test    bp, bp
0x18003e638  jz      short loc_18003E6B0
0x18003e63a  movzx   r15d, byte ptr [rbx+76h]
0x18003e63f  mov     eax, ebp
0x18003e641  add     r15d, 8
0x18003e645  mov     [rsp+78h+NumberOfBytesRead], r12d
0x18003e64d  imul    eax, r15d
0x18003e651  mov     ecx, eax; Size
0x18003e653  mov     r14d, eax
0x18003e656  call    cs:__imp_malloc
0x18003e65c  mov     rdi, rax
0x18003e65f  test    rax, rax
0x18003e662  jz      loc_18003E736
0x18003e668  mov     rcx, [rbx+8]; hFile
0x18003e66c  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003e674  mov     r8d, r14d; nNumberOfBytesToRead
0x18003e677  mov     [rsp+78h+lpOverlapped], r12; lpOverlapped
0x18003e67c  mov     rdx, rax; lpBuffer
0x18003e67f  call    cs:__imp_ReadFile
0x18003e685  test    eax, eax
0x18003e687  jz      loc_18003E722
0x18003e68d  cmp     [rsp+78h+NumberOfBytesRead], r14d
0x18003e695  jnz     loc_18003E722
0x18003e69b  mov     rax, rdi
0x18003e69e  mov     ecx, r15d
0x18003e6a1  add     [rax], esi
0x18003e6a3  mov     edx, 0FFFFh
0x18003e6a8  add     rax, rcx
0x18003e6ab  add     bp, dx
0x18003e6ae  jnz     short loc_18003E6A1
0x18003e6b0  mov     edx, esi; int
0x18003e6b2  mov     rcx, rbx; this
0x18003e6b5  call    ?ShiftFileBytes@SIPObjectCAB_@@AEAAHJ@Z; SIPObjectCAB_::ShiftFileBytes(long)
0x18003e6ba  test    eax, eax
0x18003e6bc  jz      loc_18003E749
0x18003e6c2  add     [rbx+0A0h], esi
0x18003e6c8  mov     rcx, rbx; this
0x18003e6cb  add     [rbx+58h], esi
0x18003e6ce  add     [rbx+60h], esi
0x18003e6d1  call    ?WriteHeader@SIPObjectCAB_@@AEAAHXZ; SIPObjectCAB_::WriteHeader(void)
0x18003e6d6  test    eax, eax
0x18003e6d8  jz      short loc_18003E749
0x18003e6da  test    rdi, rdi
0x18003e6dd  jz      short loc_18003E71B
0x18003e6df  mov     rcx, [rbx+8]; hFile
0x18003e6e3  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesWritten
0x18003e6eb  mov     r8d, r14d; nNumberOfBytesToWrite
0x18003e6ee  mov     [rsp+78h+NumberOfBytesRead], r12d
0x18003e6f6  mov     rdx, rdi; lpBuffer
0x18003e6f9  mov     [rsp+78h+lpOverlapped], r12; lpOverlapped
0x18003e6fe  call    cs:__imp_WriteFile
0x18003e704  test    eax, eax
0x18003e706  jz      short loc_18003E749
0x18003e708  cmp     [rsp+78h+NumberOfBytesRead], r14d
0x18003e710  jnz     short loc_18003E749
0x18003e712  mov     rcx, rdi; Block
0x18003e715  call    cs:__imp_free
0x18003e71b  mov     eax, 1
0x18003e720  jmp     short loc_18003E738
0x18003e722  mov     rcx, rdi; Block
0x18003e725  call    cs:__imp_free
0x18003e72b  mov     ecx, 0Bh; dwErrCode
0x18003e730  call    cs:__imp_SetLastError
0x18003e736  xor     eax, eax
0x18003e738  add     rsp, 38h
0x18003e73c  pop     r15
0x18003e73e  pop     r14
0x18003e740  pop     r13
0x18003e742  pop     r12
0x18003e744  pop     rdi
0x18003e745  pop     rsi
0x18003e746  pop     rbp
0x18003e747  pop     rbx
0x18003e748  retn
0x18003e749  mov     rcx, rdi; Block
0x18003e74c  call    cs:__imp_free
0x18003e752  jmp     short loc_18003E736
```
