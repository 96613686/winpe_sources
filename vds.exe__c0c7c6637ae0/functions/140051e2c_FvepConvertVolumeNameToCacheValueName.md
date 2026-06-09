# FvepConvertVolumeNameToCacheValueName

- ea: `0x140051e2c`
- end: `0x1400521c7`
- name: `FvepConvertVolumeNameToCacheValueName`
- size: `923`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1400524c8`
- `0x1400527c8`

## callees

- `0x14002e123`
- `0x14003ce10`
- `0x1400519c0`
- `0x140051e2c`
- `0x140052924`
- `0x140052a70`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140051ef7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140052036`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14005205c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400520ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14005214c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140052165`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140052183`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140051ef7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140052036`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14005205c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400520ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14005214c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140052165`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140052183`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140052044`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005215a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140052173`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140052191`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140052044`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005215a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140052173`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140052191`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140051f08`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14005206a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400520be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140051f08`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14005206a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400520be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051fa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140052003`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051fa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140052003`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140052133`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140052133`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140051f96`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140051f96`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140051ff5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140051ff5`

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
                  v5 = StringCopyWorkerW(v9, v12, v10, pszSrc, 0x7FFFFFFEu);
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
0x140051e2c  mov     [rsp-8+arg_10], rbx
0x140051e31  push    rbp
0x140051e32  push    rsi
0x140051e33  push    rdi
0x140051e34  push    r12
0x140051e36  push    r13
0x140051e38  push    r14
0x140051e3a  push    r15
0x140051e3c  lea     rbp, [rsp-80h]
0x140051e41  sub     rsp, 180h
0x140051e48  mov     rax, cs:__security_cookie
0x140051e4f  xor     rax, rsp
0x140051e52  mov     [rbp+0B0h+var_40], rax
0x140051e56  mov     rbx, rdx
0x140051e59  mov     [rsp+1B0h+var_158], rdx
0x140051e5e  mov     r15, rcx
0x140051e61  xor     edx, edx; Val
0x140051e63  lea     rcx, [rsp+1B0h+OutBuffer]; void *
0x140051e68  mov     r8d, 104h; Size
0x140051e6e  call    memset_0
0x140051e73  xor     r13d, r13d
0x140051e76  mov     [rsp+1B0h+BytesReturned], r13d
0x140051e7b  mov     [rsp+1B0h+pcchLength], r13
0x140051e80  mov     [rsp+1B0h+pullResult], r13
0x140051e85  test    r15, r15
0x140051e88  jnz     short loc_140051E94
0x140051e8a  mov     ebx, 80070057h
0x140051e8f  jmp     loc_14005219E
0x140051e94  test    rbx, rbx
0x140051e97  jnz     short loc_140051EA3
0x140051e99  mov     ebx, 80004003h
0x140051e9e  jmp     loc_14005219E
0x140051ea3  lea     r8, [rsp+1B0h+pcchLength]; pcchLength
0x140051ea8  mov     edx, 7FFFFFFFh; cchMax
0x140051ead  mov     rcx, r15; psz
0x140051eb0  call    StringCchLengthW
0x140051eb5  mov     ebx, eax
0x140051eb7  test    eax, eax
0x140051eb9  js      loc_14005219E
0x140051ebf  mov     r14, [rsp+1B0h+pcchLength]
0x140051ec4  lea     r8, [rsp+1B0h+pullResult]; pullResult
0x140051ec9  mov     rcx, r14; ullMultiplicand
0x140051ecc  mov     edx, 2; ullMultiplier
0x140051ed1  call    ULongLongMult
0x140051ed6  mov     ebx, eax
0x140051ed8  test    eax, eax
0x140051eda  js      loc_14005219E
0x140051ee0  mov     rax, [rsp+1B0h+pullResult]
0x140051ee5  lea     rdi, [rax+2]
0x140051ee9  cmp     rdi, rax
0x140051eec  jb      loc_140052199
0x140051ef2  mov     [rsp+1B0h+pullResult], rdi
0x140051ef7  call    cs:__imp_GetProcessHeap
0x140051efd  mov     r8, rdi; dwBytes
0x140051f00  mov     edx, 8; dwFlags
0x140051f05  mov     rcx, rax; hHeap
0x140051f08  call    cs:__imp_HeapAlloc
0x140051f0e  mov     r12, rax
0x140051f11  test    rax, rax
0x140051f14  jnz     short loc_140051F20
0x140051f16  mov     ebx, 8007000Eh
0x140051f1b  jmp     loc_14005219E
0x140051f20  shr     rdi, 1
0x140051f23  lea     rsi, [rsp+1B0h+OutBuffer]
0x140051f28  jz      loc_14005213B
0x140051f2e  cmp     rdi, 7FFFFFFFh
0x140051f35  jbe     short loc_140051F41
0x140051f37  mov     ebx, 80070057h
0x140051f3c  jmp     loc_140052145
0x140051f41  mov     r9, r15; pszSrc
0x140051f44  mov     [rsp+1B0h+cchToCopy], 7FFFFFFEh; cchToCopy
0x140051f4d  mov     rdx, rdi; cchDest
0x140051f50  mov     rcx, r12; pszDest
0x140051f53  call    StringCopyWorkerW
0x140051f58  mov     ebx, eax
0x140051f5a  test    eax, eax
0x140051f5c  js      loc_14005214C
0x140051f62  test    r14, r14
0x140051f65  jz      short loc_140051F78
0x140051f67  cmp     word ptr [r12+r14*2-2], 5Ch ; '\'
0x140051f6e  jnz     short loc_140051F78
0x140051f70  xor     eax, eax
0x140051f72  mov     [r12+r14*2-2], ax
0x140051f78  xor     r9d, r9d; lpSecurityAttributes
0x140051f7b  mov     [rsp+1B0h+hTemplateFile], r13; hTemplateFile
0x140051f80  mov     [rsp+1B0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x140051f85  xor     edx, edx; dwDesiredAccess
0x140051f87  mov     rcx, r12; lpFileName
0x140051f8a  mov     dword ptr [rsp+1B0h+cchToCopy], 3; dwCreationDisposition
0x140051f92  lea     r8d, [r9+7]; dwShareMode
0x140051f96  call    cs:__imp_CreateFileW
0x140051f9c  mov     [rsp+1B0h+pcchLength], rax
0x140051fa1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140051fa5  jnz     short loc_140051FC5
0x140051fa7  call    cs:__imp_GetLastError
0x140051fad  mov     ebx, eax
0x140051faf  test    eax, eax
0x140051fb1  jle     loc_14005214C
0x140051fb7  movzx   ebx, ax
0x140051fba  or      ebx, 80070000h
0x140051fc0  jmp     loc_14005214C
0x140051fc5  mov     edi, 104h
0x140051fca  mov     [rsp+1B0h+lpOverlapped], r13; lpOverlapped
0x140051fcf  lea     rcx, [rsp+1B0h+BytesReturned]
0x140051fd4  mov     [rsp+1B0h+hTemplateFile], rcx; lpBytesReturned
0x140051fd9  xor     r9d, r9d; nInBufferSize
0x140051fdc  mov     [rsp+1B0h+dwFlagsAndAttributes], edi; nOutBufferSize
0x140051fe0  mov     rcx, rax; hDevice
0x140051fe3  xor     r8d, r8d; lpInBuffer
0x140051fe6  mov     [rsp+1B0h+cchToCopy], rsi; lpOutBuffer
0x140051feb  mov     edx, 4D0000h; dwIoControlCode
0x140051ff0  mov     [rsp+1B0h+BytesReturned], r13d
0x140051ff5  call    cs:__imp_DeviceIoControl
0x140051ffb  test    eax, eax
0x140051ffd  jnz     loc_140052083
0x140052003  call    cs:__imp_GetLastError
0x140052009  mov     ebx, eax
0x14005200b  test    eax, eax
0x14005200d  jle     short loc_140052018
0x14005200f  movzx   ebx, ax
0x140052012  or      ebx, 80070000h
0x140052018  cmp     ebx, 8007007Ah
0x14005201e  jz      short loc_14005202C
0x140052020  cmp     ebx, 800700EAh
0x140052026  jnz     loc_14005212E
0x14005202c  lea     rax, [rsp+1B0h+OutBuffer]
0x140052031  cmp     rsi, rax
0x140052034  jz      short loc_14005204C
0x140052036  call    cs:__imp_GetProcessHeap
0x14005203c  mov     r8, rsi; lpMem
0x14005203f  xor     edx, edx; dwFlags
0x140052041  mov     rcx, rax; hHeap
0x140052044  call    cs:__imp_HeapFree
0x14005204a  xor     esi, esi
0x14005204c  lea     eax, [rdi+104h]
0x140052052  cmp     eax, edi
0x140052054  jb      loc_140052129
0x14005205a  mov     edi, eax
0x14005205c  call    cs:__imp_GetProcessHeap
0x140052062  mov     r8d, edi; dwBytes
0x140052065  xor     edx, edx; dwFlags
0x140052067  mov     rcx, rax; hHeap
0x14005206a  call    cs:__imp_HeapAlloc
0x140052070  mov     rsi, rax
0x140052073  test    rax, rax
0x140052076  mov     rax, [rsp+1B0h+pcchLength]
0x14005207b  jnz     loc_140051FCA
0x140052081  jmp     short loc_1400520CC
0x140052083  movzx   ecx, word ptr [rsi]; ullMultiplicand
0x140052086  lea     r8, [rsp+1B0h+pullResult]; pullResult
0x14005208b  mov     edx, 4; ullMultiplier
0x140052090  call    ULongLongMult
0x140052095  mov     ebx, eax
0x140052097  test    eax, eax
0x140052099  js      loc_14005212E
0x14005209f  mov     rax, [rsp+1B0h+pullResult]
0x1400520a4  lea     r15, [rax+2]
0x1400520a8  cmp     r15, rax
0x1400520ab  jb      short loc_140052129
0x1400520ad  call    cs:__imp_GetProcessHeap
0x1400520b3  mov     r8, r15; dwBytes
0x1400520b6  mov     edx, 8; dwFlags
0x1400520bb  mov     rcx, rax; hHeap
0x1400520be  call    cs:__imp_HeapAlloc
0x1400520c4  mov     r13, rax
0x1400520c7  test    rax, rax
0x1400520ca  jnz     short loc_1400520D3
0x1400520cc  mov     ebx, 8007000Eh
0x1400520d1  jmp     short loc_14005212E
0x1400520d3  xor     edi, edi
0x1400520d5  xor     r14d, r14d
0x1400520d8  xor     ebx, ebx
0x1400520da  movzx   eax, word ptr [rsi]
0x1400520dd  cmp     rdi, rax
0x1400520e0  jnb     short loc_14005211C
0x1400520e2  mov     rax, r15
0x1400520e5  shr     rax, 1
0x1400520e8  cmp     r14, rax
0x1400520eb  jnb     short loc_14005211C
0x1400520ed  movzx   r9d, byte ptr [rsi+rdi+2]
0x1400520f3  lea     rax, [r14+r14]
0x1400520f7  mov     rdx, r15
0x1400520fa  lea     rcx, [rax+r13]; pszDest
0x1400520fe  sub     rdx, rax; cbDest
0x140052101  lea     r8, a02x; "%02X"
0x140052108  call    StringCbPrintfW
0x14005210d  mov     ebx, eax
0x14005210f  test    eax, eax
0x140052111  js      short loc_14005212E
0x140052113  inc     rdi
0x140052116  add     r14, 2
0x14005211a  jmp     short loc_1400520DA
0x14005211c  mov     rax, [rsp+1B0h+var_158]
0x140052121  mov     [rax], r13
0x140052124  xor     r13d, r13d
0x140052127  jmp     short loc_14005212E
0x140052129  mov     ebx, 80070216h
0x14005212e  mov     rcx, [rsp+1B0h+pcchLength]; hObject
0x140052133  call    cs:__imp_CloseHandle
0x140052139  jmp     short loc_14005214C
0x14005213b  mov     ebx, 80070057h
0x140052140  test    rdi, rdi
0x140052143  jz      short loc_14005214C
0x140052145  xor     eax, eax
0x140052147  mov     [r12], ax
0x14005214c  call    cs:__imp_GetProcessHeap
0x140052152  mov     r8, r12; lpMem
0x140052155  xor     edx, edx; dwFlags
0x140052157  mov     rcx, rax; hHeap
0x14005215a  call    cs:__imp_HeapFree
0x140052160  test    r13, r13
0x140052163  jz      short loc_140052179
0x140052165  call    cs:__imp_GetProcessHeap
0x14005216b  mov     r8, r13; lpMem
0x14005216e  xor     edx, edx; dwFlags
0x140052170  mov     rcx, rax; hHeap
0x140052173  call    cs:__imp_HeapFree
0x140052179  lea     rax, [rsp+1B0h+OutBuffer]
0x14005217e  cmp     rsi, rax
0x140052181  jz      short loc_14005219E
0x140052183  call    cs:__imp_GetProcessHeap
0x140052189  mov     r8, rsi; lpMem
0x14005218c  xor     edx, edx; dwFlags
0x14005218e  mov     rcx, rax; hHeap
0x140052191  call    cs:__imp_HeapFree
0x140052197  jmp     short loc_14005219E
0x140052199  mov     ebx, 80070216h
0x14005219e  mov     eax, ebx
0x1400521a0  mov     rcx, [rbp+0B0h+var_40]
0x1400521a4  xor     rcx, rsp; StackCookie
0x1400521a7  call    __security_check_cookie
0x1400521ac  mov     rbx, [rsp+1B0h+arg_10]
0x1400521b4  add     rsp, 180h
0x1400521bb  pop     r15
0x1400521bd  pop     r14
0x1400521bf  pop     r13
0x1400521c1  pop     r12
0x1400521c3  pop     rdi
0x1400521c4  pop     rsi
0x1400521c5  pop     rbp
0x1400521c6  retn
```
