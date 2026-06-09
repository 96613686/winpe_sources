# BTNetworkConnectionThreadFunc

- ea: `0x18002fcc0`
- end: `0x18002ffcb`
- name: `BTNetworkConnectionThreadFunc`
- size: `779`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002590`
- `0x180003088`
- `0x18002fb08`
- `0x18002fcc0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002fdd3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002fdd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fd83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ffb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fd83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ffb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ff28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ff43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ff56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ff6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ff28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ff43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ff56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ff6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fefd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ff89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fefd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ff89`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002fda4`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002fda4`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18002fe5b`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18002feba`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18002fe5b`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18002feba`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002fdf5`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002fdf5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002fd75`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002fd75`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18002fdbe`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18002fdbe`

## pseudocode

```c
__int64 __fastcall BTNetworkConnectionThreadFunc(char *Parameter)
{
  DWORD LastError; // edi
  DWORD v3; // eax
  unsigned int v4; // r14d
  __int64 v5; // rdi
  char *i; // r12
  __int64 v7; // rsi
  __int64 j; // rdi
  __int64 v9; // rsi
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+44h] [rbp-BCh]
  unsigned int v17; // [rsp+48h] [rbp-B8h] BYREF
  char *v18; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE Handles[3]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE InBuffer[608]; // [rsp+70h] [rbp-90h] BYREF

  v16 = 0;
  BytesReturned = 0;
  *(_OWORD *)Handles = 0;
  memset_0(InBuffer, 0, 0x258u);
  if ( !Parameter )
  {
    LastError = 87;
    goto LABEL_29;
  }
  Handles[0] = *((HANDLE *)Parameter + 6);
  Handles[1] = *((HANDLE *)Parameter + 8);
  while ( 1 )
  {
    if ( DeviceIoControl(
           *((HANDLE *)Parameter + 2),
           0x12D818u,
           InBuffer,
           0x258u,
           0,
           BytesReturned,
           &BytesReturned,
           (LPOVERLAPPED)(Parameter + 24)) )
    {
      goto LABEL_11;
    }
    if ( GetLastError() != 997 )
      goto LABEL_41;
    v3 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    if ( v3 )
      break;
    if ( !GetOverlappedResult(*((HANDLE *)Parameter + 2), (LPOVERLAPPED)(Parameter + 24), &BytesReturned, 1) )
    {
LABEL_40:
      LastError = GetLastError();
      goto LABEL_29;
    }
LABEL_11:
    v17 = 0;
    v18 = 0;
    if ( !(unsigned int)BTGetAllConnections(&v17, &v18) )
    {
      v4 = v17;
      v5 = 0;
      for ( i = v18; (unsigned int)v5 < v4; v5 = (unsigned int)(v5 + 1) )
      {
        v7 = 0;
        if ( dword_180042180 )
        {
          while ( RtlCompareMemory(&i[8 * v5], (char *)hMem + 8 * v7, 6u) != 6 )
          {
            v7 = (unsigned int)(v7 + 1);
            if ( (unsigned int)v7 >= dword_180042180 )
              goto LABEL_16;
          }
        }
        else
        {
LABEL_16:
          (*(void (__fastcall **)(_QWORD, char *, __int64))Parameter)(*((_QWORD *)Parameter + 1), &i[8 * v5], 1);
        }
      }
      for ( j = 0; (unsigned int)j < dword_180042180; j = (unsigned int)(j + 1) )
      {
        v9 = 0;
        if ( v4 )
        {
          while ( RtlCompareMemory((char *)hMem + 8 * (unsigned int)j, &i[8 * v9], 6u) != 6 )
          {
            v9 = (unsigned int)(v9 + 1);
            if ( (unsigned int)v9 >= v4 )
              goto LABEL_22;
          }
        }
        else
        {
LABEL_22:
          (*(void (__fastcall **)(_QWORD, char *, _QWORD))Parameter)(
            *((_QWORD *)Parameter + 1),
            (char *)hMem + 8 * j,
            0);
        }
      }
      if ( hMem )
        LocalFree(hMem);
      hMem = i;
      dword_180042180 = v4;
    }
    if ( v16 )
    {
      LastError = 0;
      goto LABEL_29;
    }
  }
  if ( v3 == 1 )
  {
    if ( !CancelIoEx(*((HANDLE *)Parameter + 2), (LPOVERLAPPED)(Parameter + 24)) )
      goto LABEL_40;
    WaitForSingleObject(*((HANDLE *)Parameter + 6), 0xFFFFFFFF);
    v16 = 1;
    goto LABEL_11;
  }
LABEL_41:
  LastError = 1359;
LABEL_29:
  v10 = (void *)*((_QWORD *)Parameter + 8);
  if ( v10 )
  {
    CloseHandle(v10);
    *((_QWORD *)Parameter + 8) = 0;
  }
  v11 = (void *)*((_QWORD *)Parameter + 2);
  if ( v11 != (void *)-1LL )
  {
    CloseHandle(v11);
    *((_QWORD *)Parameter + 2) = -1;
  }
  v12 = (void *)*((_QWORD *)Parameter + 6);
  if ( v12 )
  {
    CloseHandle(v12);
    *((_QWORD *)Parameter + 6) = 0;
  }
  v13 = (void *)*((_QWORD *)Parameter + 7);
  if ( v13 )
  {
    CloseHandle(v13);
    *((_QWORD *)Parameter + 7) = 0;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Parameter + 18, 0xFFFFFFFF) == 1 )
    LocalFree(Parameter);
  return LastError;
}

```

## disassembly

```asm
0x18002fcc0  push    rbp
0x18002fcc2  push    rbx
0x18002fcc3  push    rsi
0x18002fcc4  push    rdi
0x18002fcc5  push    r12
0x18002fcc7  push    r13
0x18002fcc9  push    r14
0x18002fccb  push    r15
0x18002fccd  lea     rbp, [rsp-1E8h]
0x18002fcd5  sub     rsp, 2E8h
0x18002fcdc  mov     rax, cs:__security_cookie
0x18002fce3  xor     rax, rsp
0x18002fce6  mov     [rbp+220h+var_50], rax
0x18002fced  mov     rbx, rcx
0x18002fcf0  mov     [rsp+320h+var_2DC], 0
0x18002fcf8  xorps   xmm0, xmm0
0x18002fcfb  mov     [rsp+320h+BytesReturned], 0
0x18002fd03  lea     rcx, [rsp+320h+InBuffer]; void *
0x18002fd08  xor     edx, edx; Val
0x18002fd0a  mov     r8d, 258h; Size
0x18002fd10  movups  xmmword ptr [rsp+320h+Handles], xmm0
0x18002fd15  call    memset_0
0x18002fd1a  test    rbx, rbx
0x18002fd1d  jnz     short loc_18002FD27
0x18002fd1f  lea     edi, [rbx+57h]
0x18002fd22  jmp     loc_18002FF1F
0x18002fd27  mov     rax, [rbx+30h]
0x18002fd2b  lea     r13, [rbx+18h]
0x18002fd2f  mov     [rsp+320h+Handles], rax
0x18002fd34  mov     rax, [rbx+40h]
0x18002fd38  mov     [rsp+320h+Handles+8], rax
0x18002fd3d  mov     eax, [rsp+320h+var_2DC]
0x18002fd41  mov     rcx, [rbx+10h]; hDevice
0x18002fd45  lea     rax, [rsp+320h+BytesReturned]
0x18002fd4a  mov     [rsp+320h+lpOverlapped], r13; lpOverlapped
0x18002fd4f  lea     r8, [rsp+320h+InBuffer]; lpInBuffer
0x18002fd54  mov     [rsp+320h+lpBytesReturned], rax; lpBytesReturned
0x18002fd59  mov     r9d, 258h; nInBufferSize
0x18002fd5f  mov     eax, [rsp+320h+BytesReturned]
0x18002fd63  mov     edx, 12D818h; dwIoControlCode
0x18002fd68  mov     [rsp+320h+nOutBufferSize], eax; nOutBufferSize
0x18002fd6c  mov     [rsp+320h+lpOutBuffer], 0; lpOutBuffer
0x18002fd75  call    cs:__imp_DeviceIoControl
0x18002fd7b  test    eax, eax
0x18002fd7d  jnz     loc_18002FE03
0x18002fd83  call    cs:__imp_GetLastError
0x18002fd89  cmp     eax, 3E5h
0x18002fd8e  jnz     loc_18002FFC1
0x18002fd94  xor     r8d, r8d; bWaitAll
0x18002fd97  lea     rdx, [rsp+320h+Handles]; lpHandles
0x18002fd9c  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18002fda0  lea     ecx, [r8+2]; nCount
0x18002fda4  call    cs:__imp_WaitForMultipleObjects
0x18002fdaa  test    eax, eax
0x18002fdac  jz      short loc_18002FDE3
0x18002fdae  cmp     eax, 1
0x18002fdb1  jnz     loc_18002FFC1
0x18002fdb7  mov     rcx, [rbx+10h]; hFile
0x18002fdbb  mov     rdx, r13; lpOverlapped
0x18002fdbe  call    cs:__imp_CancelIoEx
0x18002fdc4  test    eax, eax
0x18002fdc6  jz      loc_18002FFB4
0x18002fdcc  mov     rcx, [rbx+30h]; hHandle
0x18002fdd0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002fdd3  call    cs:__imp_WaitForSingleObject
0x18002fdd9  mov     [rsp+320h+var_2DC], 1
0x18002fde1  jmp     short loc_18002FE03
0x18002fde3  mov     rcx, [rbx+10h]; hFile
0x18002fde7  lea     r8, [rsp+320h+BytesReturned]; lpNumberOfBytesTransferred
0x18002fdec  mov     r9d, 1; bWait
0x18002fdf2  mov     rdx, r13; lpOverlapped
0x18002fdf5  call    cs:__imp_GetOverlappedResult
0x18002fdfb  test    eax, eax
0x18002fdfd  jz      loc_18002FFB4
0x18002fe03  lea     rdx, [rsp+320h+var_2D0]
0x18002fe08  mov     [rsp+320h+var_2D8], 0
0x18002fe10  lea     rcx, [rsp+320h+var_2D8]
0x18002fe15  mov     [rsp+320h+var_2D0], 0
0x18002fe1e  call    BTGetAllConnections
0x18002fe23  test    eax, eax
0x18002fe25  jnz     loc_18002FF11
0x18002fe2b  mov     r14d, [rsp+320h+var_2D8]
0x18002fe30  xor     edi, edi
0x18002fe32  mov     r12, [rsp+320h+var_2D0]
0x18002fe37  test    r14d, r14d
0x18002fe3a  jz      short loc_18002FE8E
0x18002fe3c  xor     esi, esi
0x18002fe3e  cmp     cs:dword_180042180, esi
0x18002fe44  jbe     short loc_18002FE71
0x18002fe46  mov     rax, cs:hMem
0x18002fe4d  lea     rcx, [r12+rdi*8]; Source1
0x18002fe51  mov     r8d, 6; Length
0x18002fe57  lea     rdx, [rax+rsi*8]; Source2
0x18002fe5b  call    cs:__imp_RtlCompareMemory
0x18002fe61  cmp     rax, 6
0x18002fe65  jz      short loc_18002FE87
0x18002fe67  inc     esi
0x18002fe69  cmp     esi, cs:dword_180042180
0x18002fe6f  jb      short loc_18002FE46
0x18002fe71  mov     rcx, [rbx+8]
0x18002fe75  lea     rdx, [r12+rdi*8]
0x18002fe79  mov     rax, [rbx]
0x18002fe7c  mov     r8d, 1
0x18002fe82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe87  inc     edi
0x18002fe89  cmp     edi, r14d
0x18002fe8c  jb      short loc_18002FE3C
0x18002fe8e  xor     edi, edi
0x18002fe90  cmp     cs:dword_180042180, edi
0x18002fe96  jbe     short loc_18002FEF1
0x18002fe98  xor     esi, esi
0x18002fe9a  test    r14d, r14d
0x18002fe9d  jz      short loc_18002FECD
0x18002fe9f  mov     r15d, edi
0x18002fea2  shl     r15, 3
0x18002fea6  mov     rcx, cs:hMem
0x18002fead  lea     rdx, [r12+rsi*8]; Source2
0x18002feb1  add     rcx, r15; Source1
0x18002feb4  mov     r8d, 6; Length
0x18002feba  call    cs:__imp_RtlCompareMemory
0x18002fec0  cmp     rax, 6
0x18002fec4  jz      short loc_18002FEE7
0x18002fec6  inc     esi
0x18002fec8  cmp     esi, r14d
0x18002fecb  jb      short loc_18002FEA6
0x18002fecd  mov     rax, cs:hMem
0x18002fed4  xor     r8d, r8d
0x18002fed7  mov     rcx, [rbx+8]
0x18002fedb  lea     rdx, [rax+rdi*8]
0x18002fedf  mov     rax, [rbx]
0x18002fee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fee7  inc     edi
0x18002fee9  cmp     edi, cs:dword_180042180
0x18002feef  jb      short loc_18002FE98
0x18002fef1  mov     rcx, cs:hMem; hMem
0x18002fef8  test    rcx, rcx
0x18002fefb  jz      short loc_18002FF03
0x18002fefd  call    cs:__imp_LocalFree
0x18002ff03  mov     cs:hMem, r12
0x18002ff0a  mov     cs:dword_180042180, r14d
0x18002ff11  mov     eax, [rsp+320h+var_2DC]
0x18002ff15  test    eax, eax
0x18002ff17  jz      loc_18002FD41
0x18002ff1d  xor     edi, edi
0x18002ff1f  mov     rcx, [rbx+40h]; hObject
0x18002ff23  test    rcx, rcx
0x18002ff26  jz      short loc_18002FF36
0x18002ff28  call    cs:__imp_CloseHandle
0x18002ff2e  mov     qword ptr [rbx+40h], 0
0x18002ff36  mov     rcx, [rbx+10h]; hObject
0x18002ff3a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002ff3e  cmp     rcx, rsi
0x18002ff41  jz      short loc_18002FF4D
0x18002ff43  call    cs:__imp_CloseHandle
0x18002ff49  mov     [rbx+10h], rsi
0x18002ff4d  mov     rcx, [rbx+30h]; hObject
0x18002ff51  test    rcx, rcx
0x18002ff54  jz      short loc_18002FF64
0x18002ff56  call    cs:__imp_CloseHandle
0x18002ff5c  mov     qword ptr [rbx+30h], 0
0x18002ff64  mov     rcx, [rbx+38h]; hObject
0x18002ff68  test    rcx, rcx
0x18002ff6b  jz      short loc_18002FF7B
0x18002ff6d  call    cs:__imp_CloseHandle
0x18002ff73  mov     qword ptr [rbx+38h], 0
0x18002ff7b  mov     eax, esi
0x18002ff7d  lock xadd [rbx+48h], eax
0x18002ff82  add     eax, esi
0x18002ff84  jnz     short loc_18002FF8F
0x18002ff86  mov     rcx, rbx; hMem
0x18002ff89  call    cs:__imp_LocalFree
0x18002ff8f  mov     eax, edi
0x18002ff91  mov     rcx, [rbp+220h+var_50]
0x18002ff98  xor     rcx, rsp; StackCookie
0x18002ff9b  call    __security_check_cookie
0x18002ffa0  add     rsp, 2E8h
0x18002ffa7  pop     r15
0x18002ffa9  pop     r14
0x18002ffab  pop     r13
0x18002ffad  pop     r12
0x18002ffaf  pop     rdi
0x18002ffb0  pop     rsi
0x18002ffb1  pop     rbx
0x18002ffb2  pop     rbp
0x18002ffb3  retn
0x18002ffb4  call    cs:__imp_GetLastError
0x18002ffba  mov     edi, eax
0x18002ffbc  jmp     loc_18002FF1F
0x18002ffc1  mov     edi, 54Fh
0x18002ffc6  jmp     loc_18002FF1F
```
