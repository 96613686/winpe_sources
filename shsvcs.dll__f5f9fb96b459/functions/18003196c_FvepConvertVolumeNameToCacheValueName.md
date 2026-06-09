# FvepConvertVolumeNameToCacheValueName

- ea: `0x18003196c`
- end: `0x180031d07`
- name: `FvepConvertVolumeNameToCacheValueName`
- size: `923`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, wchar_t **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180032008`
- `0x180032308`

## callees

- `0x180018328`
- `0x18003196c`
- `0x180032464`
- `0x1800325b0`
- `0x180032608`
- `0x180032c6a`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031a37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031b76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031b9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031bed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031c8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031ca5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031cc3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031a37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031b76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031b9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031bed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031c8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031ca5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031cc3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031b84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031c9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031cb3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031cd1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031b84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031c9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031cb3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031cd1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031a48`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031baa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031bfe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031a48`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031baa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031bfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ae7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ae7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031c73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031c73`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180031b35`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180031b35`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031ad6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031ad6`

## pseudocode

```c
__int64 __fastcall FvepConvertVolumeNameToCacheValueName(STRSAFE_PCNZWCH pszSrc, wchar_t **a2)
{
  wchar_t *v4; // r13
  int v5; // ebx
  size_t v6; // r14
  SIZE_T v7; // rdi
  HANDLE ProcessHeap; // rax
  wchar_t *v9; // rax
  size_t *v10; // r8
  WCHAR *v11; // r12
  size_t v12; // rdi
  unsigned __int16 *v13; // rsi
  void *FileW; // rax
  signed int LastError; // eax
  DWORD v16; // edi
  signed int v17; // eax
  HANDLE v18; // rax
  HANDLE v19; // rax
  SIZE_T v20; // r15
  HANDLE v21; // rax
  unsigned __int64 v22; // rdi
  SIZE_T v23; // r14
  HANDLE v24; // rax
  HANDLE v25; // rax
  HANDLE v26; // rax
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  ULONGLONG pullResult; // [rsp+48h] [rbp-B8h] BYREF
  size_t pcchLength; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t **v31; // [rsp+58h] [rbp-A8h]
  _BYTE OutBuffer[272]; // [rsp+60h] [rbp-A0h] BYREF

  v31 = a2;
  memset_0(OutBuffer, 0, 0x104u);
  v4 = 0;
  BytesReturned = 0;
  pcchLength = 0;
  pullResult = 0;
  if ( pszSrc )
  {
    if ( a2 )
    {
      v5 = StringCchLengthW(pszSrc, 0x7FFFFFFFu, &pcchLength);
      if ( v5 >= 0 )
      {
        v6 = pcchLength;
        v5 = ULongLongMult(pcchLength, 2u, &pullResult);
        if ( v5 >= 0 )
        {
          v7 = pullResult + 2;
          if ( pullResult + 2 < pullResult )
          {
            return (unsigned int)-2147024362;
          }
          else
          {
            pullResult += 2LL;
            ProcessHeap = GetProcessHeap();
            v9 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, v7);
            v11 = v9;
            if ( v9 )
            {
              v12 = v7 >> 1;
              v13 = (unsigned __int16 *)OutBuffer;
              if ( v12 )
              {
                if ( v12 <= 0x7FFFFFFF )
                {
                  v5 = StringCopyWorkerW_0(v9, v12, v10, pszSrc, 0x7FFFFFFEu);
                  if ( v5 >= 0 )
                  {
                    if ( v6 && v11[v6 - 1] == 92 )
                      v11[v6 - 1] = 0;
                    FileW = CreateFileW(v11, 0, 7u, 0, 3u, 0, 0);
                    pcchLength = (size_t)FileW;
                    if ( FileW == (void *)-1LL )
                    {
                      LastError = GetLastError();
                      v5 = LastError;
                      if ( LastError > 0 )
                        v5 = (unsigned __int16)LastError | 0x80070000;
                    }
                    else
                    {
                      v16 = 260;
                      while ( 1 )
                      {
                        BytesReturned = 0;
                        if ( DeviceIoControl(FileW, 0x4D0000u, 0, 0, v13, v16, &BytesReturned, 0) )
                          break;
                        v17 = GetLastError();
                        v5 = v17;
                        if ( v17 > 0 )
                          v5 = (unsigned __int16)v17 | 0x80070000;
                        if ( v5 != -2147024774 && v5 != -2147024662 )
                          goto LABEL_42;
                        if ( v13 != (unsigned __int16 *)OutBuffer )
                        {
                          v18 = GetProcessHeap();
                          HeapFree(v18, 0, v13);
                          v13 = 0;
                        }
                        if ( v16 + 260 < v16 )
                          goto LABEL_41;
                        v16 += 260;
                        v19 = GetProcessHeap();
                        v13 = (unsigned __int16 *)HeapAlloc(v19, 0, v16);
                        FileW = (void *)pcchLength;
                        if ( !v13 )
                          goto LABEL_34;
                      }
                      v5 = ULongLongMult(*v13, 4u, &pullResult);
                      if ( v5 < 0 )
                        goto LABEL_42;
                      v20 = pullResult + 2;
                      if ( pullResult + 2 < pullResult )
                      {
LABEL_41:
                        v5 = -2147024362;
                        goto LABEL_42;
                      }
                      v21 = GetProcessHeap();
                      v4 = (wchar_t *)HeapAlloc(v21, 8u, v20);
                      if ( !v4 )
                      {
LABEL_34:
                        v5 = -2147024882;
                        goto LABEL_42;
                      }
                      v22 = 0;
                      v23 = 0;
                      v5 = 0;
                      while ( v22 < *v13 && v23 < v20 >> 1 )
                      {
                        v5 = StringCbPrintfW(&v4[v23], v20 - 2 * v23, L"%02X", *((unsigned __int8 *)v13 + v22 + 2));
                        if ( v5 < 0 )
                          goto LABEL_42;
                        ++v22;
                        v23 += 2LL;
                      }
                      *v31 = v4;
                      v4 = 0;
LABEL_42:
                      CloseHandle((HANDLE)pcchLength);
                    }
                  }
                }
                else
                {
                  v5 = -2147024809;
                  *v9 = 0;
                }
              }
              else
              {
                v5 = -2147024809;
              }
              v24 = GetProcessHeap();
              HeapFree(v24, 0, v11);
              if ( v4 )
              {
                v25 = GetProcessHeap();
                HeapFree(v25, 0, v4);
              }
              if ( v13 != (unsigned __int16 *)OutBuffer )
              {
                v26 = GetProcessHeap();
                HeapFree(v26, 0, v13);
              }
            }
            else
            {
              return (unsigned int)-2147024882;
            }
          }
        }
      }
    }
    else
    {
      return (unsigned int)-2147467261;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003196c  mov     [rsp-8+arg_10], rbx
0x180031971  push    rbp
0x180031972  push    rsi
0x180031973  push    rdi
0x180031974  push    r12
0x180031976  push    r13
0x180031978  push    r14
0x18003197a  push    r15
0x18003197c  lea     rbp, [rsp-80h]
0x180031981  sub     rsp, 180h
0x180031988  mov     rax, cs:__security_cookie
0x18003198f  xor     rax, rsp
0x180031992  mov     [rbp+0B0h+var_40], rax
0x180031996  mov     rbx, rdx
0x180031999  mov     [rsp+1B0h+var_158], rdx
0x18003199e  mov     r15, rcx
0x1800319a1  xor     edx, edx; Val
0x1800319a3  lea     rcx, [rsp+1B0h+OutBuffer]; void *
0x1800319a8  mov     r8d, 104h; Size
0x1800319ae  call    memset_0
0x1800319b3  xor     r13d, r13d
0x1800319b6  mov     [rsp+1B0h+BytesReturned], r13d
0x1800319bb  mov     [rsp+1B0h+pcchLength], r13
0x1800319c0  mov     [rsp+1B0h+pullResult], r13
0x1800319c5  test    r15, r15
0x1800319c8  jnz     short loc_1800319D4
0x1800319ca  mov     ebx, 80070057h
0x1800319cf  jmp     loc_180031CDE
0x1800319d4  test    rbx, rbx
0x1800319d7  jnz     short loc_1800319E3
0x1800319d9  mov     ebx, 80004003h
0x1800319de  jmp     loc_180031CDE
0x1800319e3  lea     r8, [rsp+1B0h+pcchLength]; pcchLength
0x1800319e8  mov     edx, 7FFFFFFFh; cchMax
0x1800319ed  mov     rcx, r15; psz
0x1800319f0  call    StringCchLengthW
0x1800319f5  mov     ebx, eax
0x1800319f7  test    eax, eax
0x1800319f9  js      loc_180031CDE
0x1800319ff  mov     r14, [rsp+1B0h+pcchLength]
0x180031a04  lea     r8, [rsp+1B0h+pullResult]; pullResult
0x180031a09  mov     rcx, r14; ullMultiplicand
0x180031a0c  mov     edx, 2; ullMultiplier
0x180031a11  call    ULongLongMult
0x180031a16  mov     ebx, eax
0x180031a18  test    eax, eax
0x180031a1a  js      loc_180031CDE
0x180031a20  mov     rax, [rsp+1B0h+pullResult]
0x180031a25  lea     rdi, [rax+2]
0x180031a29  cmp     rdi, rax
0x180031a2c  jb      loc_180031CD9
0x180031a32  mov     [rsp+1B0h+pullResult], rdi
0x180031a37  call    cs:__imp_GetProcessHeap
0x180031a3d  mov     r8, rdi; dwBytes
0x180031a40  mov     edx, 8; dwFlags
0x180031a45  mov     rcx, rax; hHeap
0x180031a48  call    cs:__imp_HeapAlloc
0x180031a4e  mov     r12, rax
0x180031a51  test    rax, rax
0x180031a54  jnz     short loc_180031A60
0x180031a56  mov     ebx, 8007000Eh
0x180031a5b  jmp     loc_180031CDE
0x180031a60  shr     rdi, 1
0x180031a63  lea     rsi, [rsp+1B0h+OutBuffer]
0x180031a68  jz      loc_180031C7B
0x180031a6e  cmp     rdi, 7FFFFFFFh
0x180031a75  jbe     short loc_180031A81
0x180031a77  mov     ebx, 80070057h
0x180031a7c  jmp     loc_180031C85
0x180031a81  mov     r9, r15; pszSrc
0x180031a84  mov     [rsp+1B0h+cchToCopy], 7FFFFFFEh; cchToCopy
0x180031a8d  mov     rdx, rdi; cchDest
0x180031a90  mov     rcx, r12; pszDest
0x180031a93  call    StringCopyWorkerW_0
0x180031a98  mov     ebx, eax
0x180031a9a  test    eax, eax
0x180031a9c  js      loc_180031C8C
0x180031aa2  test    r14, r14
0x180031aa5  jz      short loc_180031AB8
0x180031aa7  cmp     word ptr [r12+r14*2-2], 5Ch ; '\'
0x180031aae  jnz     short loc_180031AB8
0x180031ab0  xor     eax, eax
0x180031ab2  mov     [r12+r14*2-2], ax
0x180031ab8  xor     r9d, r9d; lpSecurityAttributes
0x180031abb  mov     [rsp+1B0h+hTemplateFile], r13; hTemplateFile
0x180031ac0  mov     [rsp+1B0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180031ac5  xor     edx, edx; dwDesiredAccess
0x180031ac7  mov     rcx, r12; lpFileName
0x180031aca  mov     dword ptr [rsp+1B0h+cchToCopy], 3; dwCreationDisposition
0x180031ad2  lea     r8d, [r9+7]; dwShareMode
0x180031ad6  call    cs:__imp_CreateFileW
0x180031adc  mov     [rsp+1B0h+pcchLength], rax
0x180031ae1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180031ae5  jnz     short loc_180031B05
0x180031ae7  call    cs:__imp_GetLastError
0x180031aed  mov     ebx, eax
0x180031aef  test    eax, eax
0x180031af1  jle     loc_180031C8C
0x180031af7  movzx   ebx, ax
0x180031afa  or      ebx, 80070000h
0x180031b00  jmp     loc_180031C8C
0x180031b05  mov     edi, 104h
0x180031b0a  mov     [rsp+1B0h+lpOverlapped], r13; lpOverlapped
0x180031b0f  lea     rcx, [rsp+1B0h+BytesReturned]
0x180031b14  mov     [rsp+1B0h+hTemplateFile], rcx; lpBytesReturned
0x180031b19  xor     r9d, r9d; nInBufferSize
0x180031b1c  mov     [rsp+1B0h+dwFlagsAndAttributes], edi; nOutBufferSize
0x180031b20  mov     rcx, rax; hDevice
0x180031b23  xor     r8d, r8d; lpInBuffer
0x180031b26  mov     [rsp+1B0h+cchToCopy], rsi; lpOutBuffer
0x180031b2b  mov     edx, 4D0000h; dwIoControlCode
0x180031b30  mov     [rsp+1B0h+BytesReturned], r13d
0x180031b35  call    cs:__imp_DeviceIoControl
0x180031b3b  test    eax, eax
0x180031b3d  jnz     loc_180031BC3
0x180031b43  call    cs:__imp_GetLastError
0x180031b49  mov     ebx, eax
0x180031b4b  test    eax, eax
0x180031b4d  jle     short loc_180031B58
0x180031b4f  movzx   ebx, ax
0x180031b52  or      ebx, 80070000h
0x180031b58  cmp     ebx, 8007007Ah
0x180031b5e  jz      short loc_180031B6C
0x180031b60  cmp     ebx, 800700EAh
0x180031b66  jnz     loc_180031C6E
0x180031b6c  lea     rax, [rsp+1B0h+OutBuffer]
0x180031b71  cmp     rsi, rax
0x180031b74  jz      short loc_180031B8C
0x180031b76  call    cs:__imp_GetProcessHeap
0x180031b7c  mov     r8, rsi; lpMem
0x180031b7f  xor     edx, edx; dwFlags
0x180031b81  mov     rcx, rax; hHeap
0x180031b84  call    cs:__imp_HeapFree
0x180031b8a  xor     esi, esi
0x180031b8c  lea     eax, [rdi+104h]
0x180031b92  cmp     eax, edi
0x180031b94  jb      loc_180031C69
0x180031b9a  mov     edi, eax
0x180031b9c  call    cs:__imp_GetProcessHeap
0x180031ba2  mov     r8d, edi; dwBytes
0x180031ba5  xor     edx, edx; dwFlags
0x180031ba7  mov     rcx, rax; hHeap
0x180031baa  call    cs:__imp_HeapAlloc
0x180031bb0  mov     rsi, rax
0x180031bb3  test    rax, rax
0x180031bb6  mov     rax, [rsp+1B0h+pcchLength]
0x180031bbb  jnz     loc_180031B0A
0x180031bc1  jmp     short loc_180031C0C
0x180031bc3  movzx   ecx, word ptr [rsi]; ullMultiplicand
0x180031bc6  lea     r8, [rsp+1B0h+pullResult]; pullResult
0x180031bcb  mov     edx, 4; ullMultiplier
0x180031bd0  call    ULongLongMult
0x180031bd5  mov     ebx, eax
0x180031bd7  test    eax, eax
0x180031bd9  js      loc_180031C6E
0x180031bdf  mov     rax, [rsp+1B0h+pullResult]
0x180031be4  lea     r15, [rax+2]
0x180031be8  cmp     r15, rax
0x180031beb  jb      short loc_180031C69
0x180031bed  call    cs:__imp_GetProcessHeap
0x180031bf3  mov     r8, r15; dwBytes
0x180031bf6  mov     edx, 8; dwFlags
0x180031bfb  mov     rcx, rax; hHeap
0x180031bfe  call    cs:__imp_HeapAlloc
0x180031c04  mov     r13, rax
0x180031c07  test    rax, rax
0x180031c0a  jnz     short loc_180031C13
0x180031c0c  mov     ebx, 8007000Eh
0x180031c11  jmp     short loc_180031C6E
0x180031c13  xor     edi, edi
0x180031c15  xor     r14d, r14d
0x180031c18  xor     ebx, ebx
0x180031c1a  movzx   eax, word ptr [rsi]
0x180031c1d  cmp     rdi, rax
0x180031c20  jnb     short loc_180031C5C
0x180031c22  mov     rax, r15
0x180031c25  shr     rax, 1
0x180031c28  cmp     r14, rax
0x180031c2b  jnb     short loc_180031C5C
0x180031c2d  movzx   r9d, byte ptr [rsi+rdi+2]
0x180031c33  lea     rax, [r14+r14]
0x180031c37  mov     rdx, r15
0x180031c3a  lea     rcx, [rax+r13]; pszDest
0x180031c3e  sub     rdx, rax; cbDest
0x180031c41  lea     r8, a02x; "%02X"
0x180031c48  call    StringCbPrintfW
0x180031c4d  mov     ebx, eax
0x180031c4f  test    eax, eax
0x180031c51  js      short loc_180031C6E
0x180031c53  inc     rdi
0x180031c56  add     r14, 2
0x180031c5a  jmp     short loc_180031C1A
0x180031c5c  mov     rax, [rsp+1B0h+var_158]
0x180031c61  mov     [rax], r13
0x180031c64  xor     r13d, r13d
0x180031c67  jmp     short loc_180031C6E
0x180031c69  mov     ebx, 80070216h
0x180031c6e  mov     rcx, [rsp+1B0h+pcchLength]; hObject
0x180031c73  call    cs:__imp_CloseHandle
0x180031c79  jmp     short loc_180031C8C
0x180031c7b  mov     ebx, 80070057h
0x180031c80  test    rdi, rdi
0x180031c83  jz      short loc_180031C8C
0x180031c85  xor     eax, eax
0x180031c87  mov     [r12], ax
0x180031c8c  call    cs:__imp_GetProcessHeap
0x180031c92  mov     r8, r12; lpMem
0x180031c95  xor     edx, edx; dwFlags
0x180031c97  mov     rcx, rax; hHeap
0x180031c9a  call    cs:__imp_HeapFree
0x180031ca0  test    r13, r13
0x180031ca3  jz      short loc_180031CB9
0x180031ca5  call    cs:__imp_GetProcessHeap
0x180031cab  mov     r8, r13; lpMem
0x180031cae  xor     edx, edx; dwFlags
0x180031cb0  mov     rcx, rax; hHeap
0x180031cb3  call    cs:__imp_HeapFree
0x180031cb9  lea     rax, [rsp+1B0h+OutBuffer]
0x180031cbe  cmp     rsi, rax
0x180031cc1  jz      short loc_180031CDE
0x180031cc3  call    cs:__imp_GetProcessHeap
0x180031cc9  mov     r8, rsi; lpMem
0x180031ccc  xor     edx, edx; dwFlags
0x180031cce  mov     rcx, rax; hHeap
0x180031cd1  call    cs:__imp_HeapFree
0x180031cd7  jmp     short loc_180031CDE
0x180031cd9  mov     ebx, 80070216h
0x180031cde  mov     eax, ebx
0x180031ce0  mov     rcx, [rbp+0B0h+var_40]
0x180031ce4  xor     rcx, rsp; StackCookie
0x180031ce7  call    __security_check_cookie
0x180031cec  mov     rbx, [rsp+1B0h+arg_10]
0x180031cf4  add     rsp, 180h
0x180031cfb  pop     r15
0x180031cfd  pop     r14
0x180031cff  pop     r13
0x180031d01  pop     r12
0x180031d03  pop     rdi
0x180031d04  pop     rsi
0x180031d05  pop     rbp
0x180031d06  retn
```
