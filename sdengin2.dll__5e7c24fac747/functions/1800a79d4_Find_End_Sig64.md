# Find_End_Sig64

- ea: `0x1800a79d4`
- end: `0x1800a7cee`
- name: `Find_End_Sig64`
- size: `794`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800a9a0c`

## callees

- `0x1800a3608`
- `0x1800a7194`
- `0x1800a79d4`
- `0x1800a9458`
- `0x1800a94dc`
- `0x1800abd84`

## import_xrefs

- `KERNEL32!GlobalUnlock` at `0x1800a7bfe`
- `KERNEL32!GlobalUnlock` at `0x1800a7c8f`
- `KERNEL32!GlobalUnlock` at `0x1800a7cb1`
- `KERNEL32!GlobalUnlock` at `0x1800a7bfe`
- `KERNEL32!GlobalUnlock` at `0x1800a7c8f`
- `KERNEL32!GlobalUnlock` at `0x1800a7cb1`
- `KERNEL32!GlobalLock` at `0x1800a7b35`
- `KERNEL32!GlobalLock` at `0x1800a7b35`
- `KERNEL32!ReadFile` at `0x1800a7b62`
- `KERNEL32!ReadFile` at `0x1800a7c56`
- `KERNEL32!ReadFile` at `0x1800a7b62`
- `KERNEL32!ReadFile` at `0x1800a7c56`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800a79fa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800a79fa`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800a7b20`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800a7b20`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a7c07`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a7c98`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a7cba`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a7cdf`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a7c07`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a7c98`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a7cba`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a7cdf`

## pseudocode

```c
__int64 Find_End_Sig64()
{
  char *Value; // rax
  char *v1; // rdi
  unsigned int v2; // eax
  int v3; // eax
  __int64 v4; // r14
  int v5; // r15d
  __int64 v6; // rbx
  char v7; // r13
  int v8; // r12d
  char v9; // r15
  char v10; // al
  __int64 v11; // rdx
  __int64 v12; // rsi
  HGLOBAL v13; // rax
  void *v14; // rbx
  _BYTE *v15; // rax
  _BYTE *v16; // r14
  __int64 v17; // rcx
  __int64 v18; // rdx
  int v19; // r15d
  char v20; // r10
  __int64 v21; // r12
  char v22; // r9
  int i; // eax
  char v24; // r8
  __int64 v25; // rbx
  __int64 v26; // rcx
  DWORD NumberOfBytesRead; // [rsp+70h] [rbp+8h] BYREF
  int v29; // [rsp+78h] [rbp+10h]
  int v30; // [rsp+80h] [rbp+18h]

  NumberOfBytesRead = 0;
  Value = (char *)TlsGetValue(dwUnZIPTlsIndex);
  v1 = Value;
  if ( !Value )
    return -1;
  v2 = DriveFromPath(Value + 71270);
  v3 = IsMediaRemovable(v2);
  if ( !*((_DWORD *)v1 + 8) && !v3 )
  {
    v4 = 16;
    v5 = 3;
    v6 = *(_QWORD *)(v1 + 72190) - 16LL;
    while ( v6 >= 0 && v4 <= 102400 )
    {
      DZSetFilePointer(*((_QWORD *)v1 + 571), v6, 0);
      v29 = fget_byte();
      v7 = fget_byte();
      v30 = fget_byte();
      v8 = 18 - v5;
      v9 = v30;
      while ( v8 > 0 )
      {
        v10 = fget_byte();
        if ( (_BYTE)v29 == 80 && v7 == 75 && v9 == 6 && v10 == 7 )
          goto LABEL_39;
        LOBYTE(v29) = v7;
        --v8;
        v7 = v9;
        v9 = v10;
      }
      if ( v6 <= 0 )
        break;
      v6 = 0;
      v4 += 16;
      v5 = 0;
      if ( *(_QWORD *)(v1 + 72190) - v4 >= 0 )
        v6 = *(_QWORD *)(v1 + 72190) - v4;
    }
    return -1;
  }
  v11 = *(_QWORD *)(v1 + 72190);
  v12 = 102400;
  if ( v11 < 102400 )
    v12 = *(_QWORD *)(v1 + 72190);
  DZSetFilePointer(*((_QWORD *)v1 + 571), v11 - v12, 0);
  v13 = GlobalAlloc(2u, (int)v12);
  v14 = v13;
  if ( !v13 )
    return -4;
  v15 = GlobalLock(v13);
  v16 = v15;
  if ( !v15 )
  {
    GlobalFree(v14);
    return -4;
  }
  if ( !ReadFile(*((HANDLE *)v1 + 571), v15, v12, &NumberOfBytesRead, 0) || NumberOfBytesRead != (_DWORD)v12 )
  {
LABEL_45:
    GlobalUnlock(v14);
    GlobalFree(v14);
    return -1;
  }
  v17 = v12 - 16;
  v18 = 16;
  v19 = 3;
  while ( v17 >= 0 && v18 <= v12 )
  {
    v20 = v16[v17];
    v21 = v17 + 2;
    v22 = v16[v17 + 1];
    for ( i = 16 - v19; i > 0; --i )
    {
      v24 = v16[v21++];
      if ( v20 == 80 && v22 == 75 && v24 == 6 && v16[v21] == 7 )
      {
        GlobalUnlock(v14);
        GlobalFree(v14);
        v25 = v21 + *(_QWORD *)(v1 + 72190) - v12 + 1;
        if ( DZSetFilePointer(*((_QWORD *)v1 + 571), v25, 0) == v25 )
        {
LABEL_39:
          if ( ReadFile(*((HANDLE *)v1 + 571), v1 + 5460, 0x10u, &NumberOfBytesRead, 0) && NumberOfBytesRead == 16 )
          {
            v26 = *((_QWORD *)v1 + 683);
            *((_DWORD *)v1 + 1369) = *((_DWORD *)v1 + 1368);
            *((_DWORD *)v1 + 1370) = *((_DWORD *)v1 + 1365);
            return v26;
          }
        }
        return -1;
      }
      v20 = v22;
      v22 = v24;
    }
    if ( v17 <= 0 )
      goto LABEL_45;
    v17 = 0;
    v18 += 16;
    v19 = 0;
    if ( v12 - v18 >= 0 )
      v17 = v12 - v18;
  }
  GlobalUnlock(v14);
  GlobalFree(v14);
  return -(__int64)((unsigned int)IsCDPlacedFirst() != 0) - 2;
}

```

## disassembly

```asm
0x1800a79d4  mov     [rsp+arg_18], rbx
0x1800a79d9  mov     [rsp+NumberOfBytesRead], ecx
0x1800a79dd  push    rbp
0x1800a79de  push    rsi
0x1800a79df  push    rdi
0x1800a79e0  push    r12
0x1800a79e2  push    r13
0x1800a79e4  push    r14
0x1800a79e6  push    r15
0x1800a79e8  sub     rsp, 30h
0x1800a79ec  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x1800a79f2  mov     [rsp+68h+NumberOfBytesRead], 0
0x1800a79fa  call    cs:__imp_TlsGetValue
0x1800a7a00  mov     rdi, rax
0x1800a7a03  test    rax, rax
0x1800a7a06  jz      loc_1800A7CC0
0x1800a7a0c  lea     rcx, [rax+11666h]; Str1
0x1800a7a13  call    DriveFromPath
0x1800a7a18  mov     ecx, eax
0x1800a7a1a  call    IsMediaRemovable
0x1800a7a1f  cmp     dword ptr [rdi+20h], 0
0x1800a7a23  jnz     loc_1800A7AF3
0x1800a7a29  test    eax, eax
0x1800a7a2b  jnz     loc_1800A7AF3
0x1800a7a31  mov     rbx, [rdi+119FEh]
0x1800a7a38  lea     ebp, [rax+10h]
0x1800a7a3b  mov     r14d, ebp
0x1800a7a3e  lea     r15d, [rax+3]
0x1800a7a42  sub     rbx, rbp
0x1800a7a45  mov     esi, 19000h
0x1800a7a4a  test    rbx, rbx
0x1800a7a4d  js      loc_1800A7CC0
0x1800a7a53  cmp     r14, rsi
0x1800a7a56  jg      loc_1800A7CC0
0x1800a7a5c  mov     rcx, [rdi+11D8h]
0x1800a7a63  xor     r8d, r8d
0x1800a7a66  mov     rdx, rbx
0x1800a7a69  call    DZSetFilePointer
0x1800a7a6e  call    fget_byte
0x1800a7a73  mov     [rsp+68h+arg_8], eax
0x1800a7a77  call    fget_byte
0x1800a7a7c  mov     r13d, eax
0x1800a7a7f  call    fget_byte
0x1800a7a84  mov     r12d, 12h
0x1800a7a8a  mov     [rsp+68h+arg_10], eax
0x1800a7a91  sub     r12d, r15d
0x1800a7a94  mov     r15d, eax
0x1800a7a97  test    r12d, r12d
0x1800a7a9a  jle     short loc_1800A7ACC
0x1800a7a9c  call    fget_byte
0x1800a7aa1  cmp     byte ptr [rsp+68h+arg_8], 50h ; 'P'
0x1800a7aa6  jnz     short loc_1800A7ABC
0x1800a7aa8  cmp     r13b, 4Bh ; 'K'
0x1800a7aac  jnz     short loc_1800A7ABC
0x1800a7aae  cmp     r15b, 6
0x1800a7ab2  jnz     short loc_1800A7ABC
0x1800a7ab4  cmp     al, 7
0x1800a7ab6  jz      loc_1800A7C34
0x1800a7abc  mov     byte ptr [rsp+68h+arg_8], r13b
0x1800a7ac1  dec     r12d
0x1800a7ac4  mov     r13b, r15b
0x1800a7ac7  mov     r15b, al
0x1800a7aca  jmp     short loc_1800A7A97
0x1800a7acc  test    rbx, rbx
0x1800a7acf  jle     loc_1800A7CC0
0x1800a7ad5  mov     rax, [rdi+119FEh]
0x1800a7adc  mov     ebx, 0
0x1800a7ae1  add     r14, rbp
0x1800a7ae4  mov     r15d, ebx
0x1800a7ae7  sub     rax, r14
0x1800a7aea  cmovns  rbx, rax
0x1800a7aee  jmp     loc_1800A7A4A
0x1800a7af3  mov     rdx, [rdi+119FEh]
0x1800a7afa  mov     esi, 19000h
0x1800a7aff  mov     rcx, [rdi+11D8h]
0x1800a7b06  cmp     rdx, rsi
0x1800a7b09  cmovl   rsi, rdx
0x1800a7b0d  xor     r8d, r8d
0x1800a7b10  sub     rdx, rsi
0x1800a7b13  call    DZSetFilePointer
0x1800a7b18  movsxd  rdx, esi; dwBytes
0x1800a7b1b  mov     ecx, 2; uFlags
0x1800a7b20  call    cs:__imp_GlobalAlloc
0x1800a7b26  mov     rbx, rax
0x1800a7b29  test    rax, rax
0x1800a7b2c  jz      loc_1800A7CE5
0x1800a7b32  mov     rcx, rax; hMem
0x1800a7b35  call    cs:__imp_GlobalLock
0x1800a7b3b  mov     r14, rax
0x1800a7b3e  test    rax, rax
0x1800a7b41  jz      loc_1800A7CDC
0x1800a7b47  mov     rcx, [rdi+11D8h]; hFile
0x1800a7b4e  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800a7b53  mov     r8d, esi; nNumberOfBytesToRead
0x1800a7b56  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x1800a7b5f  mov     rdx, rax; lpBuffer
0x1800a7b62  call    cs:__imp_ReadFile
0x1800a7b68  test    eax, eax
0x1800a7b6a  jz      loc_1800A7CAE
0x1800a7b70  cmp     [rsp+68h+NumberOfBytesRead], esi
0x1800a7b74  jnz     loc_1800A7CAE
0x1800a7b7a  mov     ebp, 10h
0x1800a7b7f  lea     rcx, [rsi-10h]
0x1800a7b83  mov     edx, ebp
0x1800a7b85  lea     r15d, [rbp-0Dh]
0x1800a7b89  test    rcx, rcx
0x1800a7b8c  js      loc_1800A7C8C
0x1800a7b92  cmp     rdx, rsi
0x1800a7b95  jg      loc_1800A7C8C
0x1800a7b9b  mov     r10b, [r14+rcx]
0x1800a7b9f  lea     r12, [rcx+2]
0x1800a7ba3  mov     r9b, [r14+rcx+1]
0x1800a7ba8  mov     eax, ebp
0x1800a7baa  sub     eax, r15d
0x1800a7bad  test    eax, eax
0x1800a7baf  jle     short loc_1800A7BDB
0x1800a7bb1  mov     r8b, [r14+r12]
0x1800a7bb5  inc     r12
0x1800a7bb8  cmp     r10b, 50h ; 'P'
0x1800a7bbc  jnz     short loc_1800A7BD1
0x1800a7bbe  cmp     r9b, 4Bh ; 'K'
0x1800a7bc2  jnz     short loc_1800A7BD1
0x1800a7bc4  cmp     r8b, 6
0x1800a7bc8  jnz     short loc_1800A7BD1
0x1800a7bca  cmp     byte ptr [r14+r12], 7
0x1800a7bcf  jz      short loc_1800A7BFB
0x1800a7bd1  mov     r10b, r9b
0x1800a7bd4  dec     eax
0x1800a7bd6  mov     r9b, r8b
0x1800a7bd9  jmp     short loc_1800A7BAD
0x1800a7bdb  test    rcx, rcx
0x1800a7bde  jle     loc_1800A7CAE
0x1800a7be4  mov     ecx, 0
0x1800a7be9  add     rdx, rbp
0x1800a7bec  mov     rax, rsi
0x1800a7bef  mov     r15d, ecx
0x1800a7bf2  sub     rax, rdx
0x1800a7bf5  cmovns  rcx, rax
0x1800a7bf9  jmp     short loc_1800A7B89
0x1800a7bfb  mov     rcx, rbx; hMem
0x1800a7bfe  call    cs:__imp_GlobalUnlock
0x1800a7c04  mov     rcx, rbx; hMem
0x1800a7c07  call    cs:__imp_GlobalFree
0x1800a7c0d  mov     rbx, [rdi+119FEh]
0x1800a7c14  xor     r8d, r8d
0x1800a7c17  mov     rcx, [rdi+11D8h]
0x1800a7c1e  sub     rbx, rsi
0x1800a7c21  inc     rbx
0x1800a7c24  add     rbx, r12
0x1800a7c27  mov     rdx, rbx
0x1800a7c2a  call    DZSetFilePointer
0x1800a7c2f  cmp     rax, rbx
0x1800a7c32  jnz     short loc_1800A7C83
0x1800a7c34  mov     rcx, [rdi+11D8h]; hFile
0x1800a7c3b  lea     rbx, [rdi+1554h]
0x1800a7c42  mov     rdx, rbx; lpBuffer
0x1800a7c45  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x1800a7c4e  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800a7c53  mov     r8d, ebp; nNumberOfBytesToRead
0x1800a7c56  call    cs:__imp_ReadFile
0x1800a7c5c  test    eax, eax
0x1800a7c5e  jz      short loc_1800A7C83
0x1800a7c60  cmp     [rsp+68h+NumberOfBytesRead], ebp
0x1800a7c64  jnz     short loc_1800A7C83
0x1800a7c66  mov     eax, [rdi+1560h]
0x1800a7c6c  mov     rcx, [rdi+1558h]
0x1800a7c73  mov     [rdi+1564h], eax
0x1800a7c79  mov     eax, [rbx]
0x1800a7c7b  mov     [rdi+1568h], eax
0x1800a7c81  jmp     short loc_1800A7C87
0x1800a7c83  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800a7c87  mov     rax, rcx
0x1800a7c8a  jmp     short loc_1800A7CC4
0x1800a7c8c  mov     rcx, rbx; hMem
0x1800a7c8f  call    cs:__imp_GlobalUnlock
0x1800a7c95  mov     rcx, rbx; hMem
0x1800a7c98  call    cs:__imp_GlobalFree
0x1800a7c9e  call    IsCDPlacedFirst
0x1800a7ca3  neg     eax
0x1800a7ca5  sbb     rax, rax
0x1800a7ca8  add     rax, 0FFFFFFFFFFFFFFFEh
0x1800a7cac  jmp     short loc_1800A7CC4
0x1800a7cae  mov     rcx, rbx; hMem
0x1800a7cb1  call    cs:__imp_GlobalUnlock
0x1800a7cb7  mov     rcx, rbx; hMem
0x1800a7cba  call    cs:__imp_GlobalFree
0x1800a7cc0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a7cc4  mov     rbx, [rsp+68h+arg_18]
0x1800a7ccc  add     rsp, 30h
0x1800a7cd0  pop     r15
0x1800a7cd2  pop     r14
0x1800a7cd4  pop     r13
0x1800a7cd6  pop     r12
0x1800a7cd8  pop     rdi
0x1800a7cd9  pop     rsi
0x1800a7cda  pop     rbp
0x1800a7cdb  retn
0x1800a7cdc  mov     rcx, rbx; hMem
0x1800a7cdf  call    cs:__imp_GlobalFree
0x1800a7ce5  mov     rax, 0FFFFFFFFFFFFFFFCh
0x1800a7cec  jmp     short loc_1800A7CC4
```
