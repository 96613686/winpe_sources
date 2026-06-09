# CLocalEventLogWriter::TrimLogFile(void)

- ea: `0x180168cbc`
- end: `0x180168f33`
- name: `?TrimLogFile@CLocalEventLogWriter@@AEAAXXZ`
- size: `631`
- prototype: `void __fastcall(CLocalEventLogWriter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180169128`

## callees

- `0x180168cbc`
- `0x180238984`
- `0x180239584`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180168d66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180168dd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180168e40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180168e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180168ed8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180168f0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180168d66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180168dd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180168e40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180168e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180168ed8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180168f0e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180168cf2`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180168cf2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180168d57`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180168dc7`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180168e33`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180168e7b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180168ecd`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180168f03`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180168d57`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180168dc7`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180168e33`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180168e7b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180168ecd`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180168f03`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180168ee6`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180168ee6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180168d86`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180168e64`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180168d86`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180168e64`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180168e02`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180168ea5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180168e02`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180168ea5`

## pseudocode

```c
void __fastcall CLocalEventLogWriter::TrimLogFile(HANDLE *this)
{
  DWORD v1; // ebp
  DWORD v3; // edi
  DWORD FileSize; // eax
  unsigned int v5; // esi
  _WORD *v6; // r15
  int v7; // ecx
  LONG v8; // r14d
  const struct std::nothrow_t *v9; // rdx
  unsigned int v10; // ebp
  unsigned int v11; // r14d
  LONG i; // r12d
  DWORD v13; // ebp
  HANDLE v14; // rcx

  v1 = 0;
  v3 = 0x100000;
  if ( *((_DWORD *)this + 6) )
  {
    FileSize = GetFileSize(this[1], 0);
    v5 = FileSize;
    if ( FileSize != -1 && FileSize > *((_DWORD *)this + 6) )
    {
      v6 = operator new[](0x100000u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v6 )
      {
        v7 = *((_DWORD *)this + 6) >> 1;
        v8 = v5 - v7 + 1;
        if ( (((_BYTE)v5 - (_BYTE)v7) & 1) == 0 )
          v8 = v5 - v7;
        if ( v8 + 0x100000 > v5 )
          v3 = v5 - v8;
        if ( (SetFilePointer(this[1], v8, 0, 0) != -1 || !GetLastError()) && ReadFile(this[1], v6, v3, 0, 0) )
        {
          if ( v3 )
          {
            do
            {
              if ( v6[(unsigned __int64)v1 >> 1] == 10 )
                break;
              v1 += 2;
            }
            while ( v1 < v3 );
          }
          v10 = v1 + 2 < v3 ? v1 + 2 : 0;
          if ( SetFilePointer(this[1], 2, 0, 0) != -1 || !GetLastError() )
          {
            if ( WriteFile(this[1], &v6[(unsigned __int64)v10 >> 1], v3 - v10, 0, 0) )
            {
              v11 = v3 + v8;
              for ( i = v3 - v10 + 2; ; i += v13 )
              {
                v14 = this[1];
                if ( v11 >= v5 )
                  break;
                v13 = v5 - v11;
                if ( v11 + v3 <= v5 )
                  v13 = v3;
                if ( SetFilePointer(v14, v11, 0, 0) == -1 && GetLastError()
                  || !ReadFile(this[1], v6, v13, 0, 0)
                  || SetFilePointer(this[1], i, 0, 0) == -1 && GetLastError()
                  || !WriteFile(this[1], v6, v13, 0, 0) )
                {
                  goto LABEL_32;
                }
                v11 += v13;
                v3 = v13;
              }
              if ( SetFilePointer(v14, i, 0, 0) != -1 || !GetLastError() )
                SetEndOfFile(this[1]);
            }
          }
        }
LABEL_32:
        operator delete(v6, v9);
        if ( SetFilePointer(this[1], 0, 0, 2u) == -1 )
          GetLastError();
      }
    }
  }
}

```

## disassembly

```asm
0x180168cbc  mov     rax, rsp
0x180168cbf  mov     [rax+8], rbx
0x180168cc3  mov     [rax+10h], rbp
0x180168cc7  mov     [rax+18h], rsi
0x180168ccb  mov     [rax+20h], rdi
0x180168ccf  push    r12
0x180168cd1  push    r14
0x180168cd3  push    r15
0x180168cd5  sub     rsp, 30h
0x180168cd9  xor     ebp, ebp
0x180168cdb  mov     rbx, rcx
0x180168cde  mov     edi, 100000h
0x180168ce3  cmp     [rcx+18h], ebp
0x180168ce6  jz      loc_180168F14
0x180168cec  mov     rcx, [rcx+8]; hFile
0x180168cf0  xor     edx, edx; lpFileSizeHigh
0x180168cf2  call    cs:__imp_GetFileSize
0x180168cf8  mov     esi, eax
0x180168cfa  cmp     eax, 0FFFFFFFFh
0x180168cfd  jz      loc_180168F14
0x180168d03  cmp     eax, [rbx+18h]
0x180168d06  jbe     loc_180168F14
0x180168d0c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180168d13  mov     ecx, edi; unsigned __int64
0x180168d15  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180168d1a  mov     r15, rax
0x180168d1d  test    rax, rax
0x180168d20  jz      loc_180168F14
0x180168d26  mov     ecx, [rbx+18h]
0x180168d29  mov     edx, esi
0x180168d2b  shr     ecx, 1
0x180168d2d  sub     edx, ecx
0x180168d2f  test    dl, 1
0x180168d32  lea     r14d, [rdx+1]
0x180168d36  cmovz   r14d, edx
0x180168d3a  lea     eax, [r14+100000h]
0x180168d41  cmp     eax, esi
0x180168d43  jbe     short loc_180168D4A
0x180168d45  mov     edi, esi
0x180168d47  sub     edi, r14d
0x180168d4a  mov     rcx, [rbx+8]; hFile
0x180168d4e  xor     r9d, r9d; dwMoveMethod
0x180168d51  xor     r8d, r8d; lpDistanceToMoveHigh
0x180168d54  mov     edx, r14d; lDistanceToMove
0x180168d57  call    cs:__imp_SetFilePointer
0x180168d5d  or      r12d, 0FFFFFFFFh
0x180168d61  cmp     eax, r12d
0x180168d64  jnz     short loc_180168D74
0x180168d66  call    cs:__imp_GetLastError
0x180168d6c  test    eax, eax
0x180168d6e  jnz     loc_180168EEC
0x180168d74  mov     rcx, [rbx+8]; hFile
0x180168d78  xor     r9d, r9d; lpNumberOfBytesRead
0x180168d7b  mov     r8d, edi; nNumberOfBytesToRead
0x180168d7e  mov     [rsp+48h+lpOverlapped], rbp; lpOverlapped
0x180168d83  mov     rdx, r15; lpBuffer
0x180168d86  call    cs:__imp_ReadFile
0x180168d8c  test    eax, eax
0x180168d8e  jz      loc_180168EEC
0x180168d94  test    edi, edi
0x180168d96  jz      short loc_180168DB0
0x180168d98  mov     eax, ebp
0x180168d9a  mov     ecx, 0Ah
0x180168d9f  shr     rax, 1
0x180168da2  cmp     cx, [r15+rax*2]
0x180168da7  jz      short loc_180168DB0
0x180168da9  add     ebp, 2
0x180168dac  cmp     ebp, edi
0x180168dae  jb      short loc_180168D98
0x180168db0  mov     rcx, [rbx+8]; hFile
0x180168db4  lea     eax, [rbp+2]
0x180168db7  cmp     eax, edi
0x180168db9  sbb     ebp, ebp
0x180168dbb  xor     r9d, r9d; dwMoveMethod
0x180168dbe  xor     r8d, r8d; lpDistanceToMoveHigh
0x180168dc1  and     ebp, eax
0x180168dc3  lea     edx, [r9+2]; lDistanceToMove
0x180168dc7  call    cs:__imp_SetFilePointer
0x180168dcd  cmp     eax, r12d
0x180168dd0  jnz     short loc_180168DE0
0x180168dd2  call    cs:__imp_GetLastError
0x180168dd8  test    eax, eax
0x180168dda  jnz     loc_180168EEC
0x180168de0  mov     rcx, [rbx+8]; hFile
0x180168de4  mov     r12d, edi
0x180168de7  mov     eax, ebp
0x180168de9  sub     r12d, ebp
0x180168dec  shr     rax, 1
0x180168def  xor     r9d, r9d; lpNumberOfBytesWritten
0x180168df2  mov     r8d, r12d; nNumberOfBytesToWrite
0x180168df5  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x180168dfe  lea     rdx, [r15+rax*2]; lpBuffer
0x180168e02  call    cs:__imp_WriteFile
0x180168e08  test    eax, eax
0x180168e0a  jz      loc_180168EEC
0x180168e10  add     r14d, edi
0x180168e13  add     r12d, 2
0x180168e17  jmp     loc_180168EB7
0x180168e1c  lea     eax, [r14+rdi]
0x180168e20  mov     ebp, esi
0x180168e22  sub     ebp, r14d
0x180168e25  mov     edx, r14d; lDistanceToMove
0x180168e28  cmp     eax, esi
0x180168e2a  cmovbe  ebp, edi
0x180168e2d  xor     r9d, r9d; dwMoveMethod
0x180168e30  xor     r8d, r8d; lpDistanceToMoveHigh
0x180168e33  call    cs:__imp_SetFilePointer
0x180168e39  or      edi, 0FFFFFFFFh
0x180168e3c  cmp     eax, edi
0x180168e3e  jnz     short loc_180168E4E
0x180168e40  call    cs:__imp_GetLastError
0x180168e46  test    eax, eax
0x180168e48  jnz     loc_180168EEC
0x180168e4e  mov     rcx, [rbx+8]; hFile
0x180168e52  xor     r9d, r9d; lpNumberOfBytesRead
0x180168e55  mov     r8d, ebp; nNumberOfBytesToRead
0x180168e58  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x180168e61  mov     rdx, r15; lpBuffer
0x180168e64  call    cs:__imp_ReadFile
0x180168e6a  test    eax, eax
0x180168e6c  jz      short loc_180168EEC
0x180168e6e  mov     rcx, [rbx+8]; hFile
0x180168e72  xor     r9d, r9d; dwMoveMethod
0x180168e75  xor     r8d, r8d; lpDistanceToMoveHigh
0x180168e78  mov     edx, r12d; lDistanceToMove
0x180168e7b  call    cs:__imp_SetFilePointer
0x180168e81  cmp     eax, edi
0x180168e83  jnz     short loc_180168E8F
0x180168e85  call    cs:__imp_GetLastError
0x180168e8b  test    eax, eax
0x180168e8d  jnz     short loc_180168EEC
0x180168e8f  mov     rcx, [rbx+8]; hFile
0x180168e93  xor     r9d, r9d; lpNumberOfBytesWritten
0x180168e96  mov     r8d, ebp; nNumberOfBytesToWrite
0x180168e99  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x180168ea2  mov     rdx, r15; lpBuffer
0x180168ea5  call    cs:__imp_WriteFile
0x180168eab  test    eax, eax
0x180168ead  jz      short loc_180168EEC
0x180168eaf  add     r14d, ebp
0x180168eb2  mov     edi, ebp
0x180168eb4  add     r12d, ebp
0x180168eb7  mov     rcx, [rbx+8]; hFile
0x180168ebb  cmp     r14d, esi
0x180168ebe  jb      loc_180168E1C
0x180168ec4  xor     r9d, r9d; dwMoveMethod
0x180168ec7  xor     r8d, r8d; lpDistanceToMoveHigh
0x180168eca  mov     edx, r12d; lDistanceToMove
0x180168ecd  call    cs:__imp_SetFilePointer
0x180168ed3  cmp     eax, 0FFFFFFFFh
0x180168ed6  jnz     short loc_180168EE2
0x180168ed8  call    cs:__imp_GetLastError
0x180168ede  test    eax, eax
0x180168ee0  jnz     short loc_180168EEC
0x180168ee2  mov     rcx, [rbx+8]; hFile
0x180168ee6  call    cs:__imp_SetEndOfFile
0x180168eec  mov     rcx, r15; void *
0x180168eef  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180168ef4  mov     rcx, [rbx+8]; hFile
0x180168ef8  mov     r9d, 2; dwMoveMethod
0x180168efe  xor     r8d, r8d; lpDistanceToMoveHigh
0x180168f01  xor     edx, edx; lDistanceToMove
0x180168f03  call    cs:__imp_SetFilePointer
0x180168f09  cmp     eax, 0FFFFFFFFh
0x180168f0c  jnz     short loc_180168F14
0x180168f0e  call    cs:__imp_GetLastError
0x180168f14  mov     rbx, [rsp+48h+arg_0]
0x180168f19  mov     rbp, [rsp+48h+arg_8]
0x180168f1e  mov     rsi, [rsp+48h+arg_10]
0x180168f23  mov     rdi, [rsp+48h+arg_18]
0x180168f28  add     rsp, 30h
0x180168f2c  pop     r15
0x180168f2e  pop     r14
0x180168f30  pop     r12
0x180168f32  retn
```
