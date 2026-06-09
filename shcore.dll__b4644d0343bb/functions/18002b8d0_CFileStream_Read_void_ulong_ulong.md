# CFileStream::Read(void *,ulong,ulong *)

- ea: `0x18002b8d0`
- end: `0x18002bae7`
- name: `?Read@CFileStream@@UEAAJPEAXKPEAK@Z`
- size: `535`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002b8d0`

## callees

- `0x18001aad4`
- `0x18001abfc`
- `0x18002b8d0`
- `0x18009341c`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002ba0b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002ba5d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002ba0b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002ba5d`

## pseudocode

```c
__int64 __fastcall CFileStream::Read(CFileStream *this, char *a2, unsigned int a3, unsigned int *a4)
{
  CFileStream *v4; // rbx
  __int64 v6; // rcx
  __int64 *v9; // rcx
  __int64 v10; // rax
  __int64 result; // rax
  int Error; // r12d
  bool v13; // zf
  HANDLE v14; // rbp
  unsigned int v15; // esi
  __int64 v16; // rdx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // eax
  __int64 v20; // r15
  unsigned int v21; // r15d
  DWORD v22; // eax
  HANDLE hFile[6]; // [rsp+38h] [rbp-30h] BYREF
  DWORD NumberOfBytesRead; // [rsp+70h] [rbp+8h] BYREF

  while ( 1 )
  {
    v4 = this;
    v6 = *((_QWORD *)this + 532);
    if ( !v6 || (*((_DWORD *)v4 + 13) & 0x10000) == 0 )
      break;
    this = (CFileStream *)(v6 + 16);
  }
  v9 = (__int64 *)*((_QWORD *)v4 + 527);
  if ( !v9 )
    return 2147942406LL;
  v10 = *v9;
  hFile[0] = 0;
  result = (*(__int64 (__fastcall **)(__int64 *, HANDLE *))(v10 + 24))(v9, hFile);
  Error = result;
  if ( (int)result >= 0 )
  {
    v13 = *((_BYTE *)v4 + 56) == 1;
    v14 = hFile[0];
    v15 = a3;
    NumberOfBytesRead = 0;
    if ( v13 && (Error = CFileStream::_NonTransactedCommit((char *)v4 - 16, 0), Error < 0) )
    {
      if ( !a4 )
        goto LABEL_13;
    }
    else
    {
      *((_BYTE *)v4 + 56) = 0;
      while ( a3 )
      {
        v16 = *((unsigned int *)v4 + 15);
        v17 = *((_DWORD *)v4 + 16);
        if ( (unsigned int)v16 < v17 )
        {
          v18 = v17 - v16;
          v19 = a3;
          if ( v18 <= a3 )
            v19 = v18;
          v20 = v19;
          memcpy_0(a2, (char *)v4 + v16 + 68, v19);
          *((_DWORD *)v4 + 15) += v20;
          a3 -= v20;
          if ( !a3 )
            break;
          a2 += v20;
        }
        if ( a3 > 0x1000 )
        {
          v21 = a3 & 0xFFFFF000;
          if ( !ReadFile(v14, a2, a3 & 0xFFFFF000, &NumberOfBytesRead, 0) )
            goto LABEL_29;
          a3 -= NumberOfBytesRead;
          if ( v21 != NumberOfBytesRead || !a3 )
            break;
          a2 += NumberOfBytesRead;
        }
        if ( (unsigned int)(*((_DWORD *)v4 + 16) - 1) <= 0xFFE )
          break;
        if ( !ReadFile(v14, (char *)v4 + 68, 0x1000u, &NumberOfBytesRead, 0) )
        {
LABEL_29:
          Error = ResultFromLastError();
          break;
        }
        v22 = NumberOfBytesRead;
        if ( !NumberOfBytesRead )
          break;
        *((_DWORD *)v4 + 15) = 0;
        *((_DWORD *)v4 + 16) = v22;
      }
      if ( !a4 )
        goto LABEL_13;
    }
    *a4 = v15 - a3;
LABEL_13:
    if ( a3 )
      Error = 1;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 527) + 32LL))(*((_QWORD *)v4 + 527));
    return (unsigned int)Error;
  }
  return result;
}

```

## disassembly

```asm
0x18002b8d0  push    rbx
0x18002b8d2  push    rdi
0x18002b8d3  push    r13
0x18002b8d5  push    r14
0x18002b8d7  push    r15
0x18002b8d9  sub     rsp, 40h
0x18002b8dd  mov     rbx, rcx
0x18002b8e0  mov     r14, r9
0x18002b8e3  mov     rcx, [rcx+10A0h]
0x18002b8ea  mov     edi, r8d
0x18002b8ed  mov     r13, rdx
0x18002b8f0  test    rcx, rcx
0x18002b8f3  jnz     loc_18002BA8A
0x18002b8f9  mov     rcx, [rbx+1078h]
0x18002b900  test    rcx, rcx
0x18002b903  jz      loc_18002BADD
0x18002b909  mov     rax, [rcx]
0x18002b90c  lea     rdx, [rsp+68h+hFile]
0x18002b911  mov     [rsp+68h+arg_18], r12
0x18002b919  mov     [rsp+68h+hFile], 0
0x18002b922  mov     rax, [rax+18h]
0x18002b926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b92b  mov     r12d, eax
0x18002b92e  test    eax, eax
0x18002b930  js      loc_18002B9CA
0x18002b936  cmp     byte ptr [rbx+38h], 1
0x18002b93a  mov     [rsp+68h+arg_8], rbp
0x18002b93f  mov     rbp, [rsp+68h+hFile]
0x18002b944  mov     [rsp+68h+arg_10], rsi
0x18002b94c  mov     esi, edi
0x18002b94e  mov     [rsp+68h+NumberOfBytesRead], 0
0x18002b956  jz      loc_18002BAB9
0x18002b95c  mov     byte ptr [rbx+38h], 0
0x18002b960  test    edi, edi
0x18002b962  jz      short loc_18002B995
0x18002b964  mov     edx, [rbx+3Ch]
0x18002b967  mov     ecx, [rbx+40h]
0x18002b96a  cmp     edx, ecx
0x18002b96c  jnb     short loc_18002B9E2
0x18002b96e  sub     ecx, edx
0x18002b970  mov     eax, edi
0x18002b972  cmp     ecx, edi
0x18002b974  cmovbe  eax, ecx
0x18002b977  add     rdx, 44h ; 'D'
0x18002b97b  add     rdx, rbx; Src
0x18002b97e  mov     r8d, eax; Size
0x18002b981  mov     rcx, r13; void *
0x18002b984  mov     r15d, eax
0x18002b987  call    memcpy_0
0x18002b98c  add     [rbx+3Ch], r15d
0x18002b990  sub     edi, r15d
0x18002b993  jnz     short loc_18002B9DF
0x18002b995  test    r14, r14
0x18002b998  jz      short loc_18002B99F
0x18002b99a  sub     esi, edi
0x18002b99c  mov     [r14], esi
0x18002b99f  mov     rsi, [rsp+68h+arg_10]
0x18002b9a7  mov     rbp, [rsp+68h+arg_8]
0x18002b9ac  test    edi, edi
0x18002b9ae  jnz     loc_18002BA7F
0x18002b9b4  mov     rcx, [rbx+1078h]
0x18002b9bb  mov     rax, [rcx]
0x18002b9be  mov     rax, [rax+20h]
0x18002b9c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9c7  mov     eax, r12d
0x18002b9ca  mov     r12, [rsp+68h+arg_18]
0x18002b9d2  add     rsp, 40h
0x18002b9d6  pop     r15
0x18002b9d8  pop     r14
0x18002b9da  pop     r13
0x18002b9dc  pop     rdi
0x18002b9dd  pop     rbx
0x18002b9de  retn
0x18002b9df  add     r13, r15
0x18002b9e2  cmp     edi, 1000h
0x18002b9e8  jbe     short loc_18002BA33
0x18002b9ea  mov     r15d, edi
0x18002b9ed  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x18002b9f6  and     r15d, 0FFFFF000h
0x18002b9fd  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002ba02  mov     r8d, r15d; nNumberOfBytesToRead
0x18002ba05  mov     rdx, r13; lpBuffer
0x18002ba08  mov     rcx, rbp; hFile
0x18002ba0b  call    cs:__imp_ReadFile
0x18002ba11  test    eax, eax
0x18002ba13  jz      loc_18002BAAC
0x18002ba19  mov     eax, [rsp+68h+NumberOfBytesRead]
0x18002ba1d  sub     edi, eax
0x18002ba1f  cmp     r15d, eax
0x18002ba22  jnz     loc_18002B995
0x18002ba28  test    edi, edi
0x18002ba2a  jz      loc_18002B995
0x18002ba30  add     r13, rax
0x18002ba33  mov     eax, [rbx+40h]
0x18002ba36  dec     eax
0x18002ba38  cmp     eax, 0FFEh
0x18002ba3d  jbe     loc_18002B995
0x18002ba43  xor     r15d, r15d
0x18002ba46  lea     rdx, [rbx+44h]; lpBuffer
0x18002ba4a  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002ba4f  mov     [rsp+68h+lpOverlapped], r15; lpOverlapped
0x18002ba54  mov     r8d, 1000h; nNumberOfBytesToRead
0x18002ba5a  mov     rcx, rbp; hFile
0x18002ba5d  call    cs:__imp_ReadFile
0x18002ba63  test    eax, eax
0x18002ba65  jz      short loc_18002BAAC
0x18002ba67  mov     eax, [rsp+68h+NumberOfBytesRead]
0x18002ba6b  test    eax, eax
0x18002ba6d  jz      loc_18002B995
0x18002ba73  mov     [rbx+3Ch], r15d
0x18002ba77  mov     [rbx+40h], eax
0x18002ba7a  jmp     loc_18002B960
0x18002ba7f  mov     r12d, 1
0x18002ba85  jmp     loc_18002B9B4
0x18002ba8a  test    dword ptr [rbx+34h], 10000h
0x18002ba91  jz      loc_18002B8F9
0x18002ba97  add     rcx, 10h; this
0x18002ba9b  add     rsp, 40h
0x18002ba9f  pop     r15
0x18002baa1  pop     r14
0x18002baa3  pop     r13
0x18002baa5  pop     rdi
0x18002baa6  pop     rbx
0x18002baa7  jmp     ?Read@CFileStream@@UEAAJPEAXKPEAK@Z; CFileStream::Read(void *,ulong,ulong *)
0x18002baac  call    ResultFromLastError
0x18002bab1  mov     r12d, eax
0x18002bab4  jmp     loc_18002B995
0x18002bab9  xor     edx, edx
0x18002babb  lea     rcx, [rbx-10h]
0x18002babf  call    ?_NonTransactedCommit@CFileStream@@AEAAJW4COMMIT_TYPE@1@@Z; CFileStream::_NonTransactedCommit(CFileStream::COMMIT_TYPE)
0x18002bac4  mov     r12d, eax
0x18002bac7  test    eax, eax
0x18002bac9  jns     loc_18002B95C
0x18002bacf  test    r14, r14
0x18002bad2  jz      loc_18002B99F
0x18002bad8  jmp     loc_18002B99A
0x18002badd  mov     eax, 80070006h
0x18002bae2  jmp     loc_18002B9D2
```
