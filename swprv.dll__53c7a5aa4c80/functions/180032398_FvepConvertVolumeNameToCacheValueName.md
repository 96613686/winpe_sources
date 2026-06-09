# FvepConvertVolumeNameToCacheValueName

- ea: `0x180032398`
- end: `0x180032733`
- name: `FvepConvertVolumeNameToCacheValueName`
- size: `923`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180032a34`
- `0x180032d34`

## callees

- `0x180001580`
- `0x18000212c`
- `0x180007650`
- `0x180031f18`
- `0x180032398`
- `0x180032e90`
- `0x180032fb0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003269f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003269f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032513`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003256f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032513`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003256f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180032502`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180032502`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180032561`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180032561`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032463`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800325a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800325c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032619`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800326b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800326d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800326ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032463`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800325a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800325c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032619`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800326b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800326d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800326ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800325b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800326c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800326df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800326fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800325b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800326c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800326df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800326fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032474`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800325d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003262a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032474`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800325d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003262a`

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
0x180032398  mov     [rsp-8+arg_10], rbx
0x18003239d  push    rbp
0x18003239e  push    rsi
0x18003239f  push    rdi
0x1800323a0  push    r12
0x1800323a2  push    r13
0x1800323a4  push    r14
0x1800323a6  push    r15
0x1800323a8  lea     rbp, [rsp-80h]
0x1800323ad  sub     rsp, 180h
0x1800323b4  mov     rax, cs:__security_cookie
0x1800323bb  xor     rax, rsp
0x1800323be  mov     [rbp+0B0h+var_40], rax
0x1800323c2  mov     rbx, rdx
0x1800323c5  mov     [rsp+1B0h+var_158], rdx
0x1800323ca  mov     r15, rcx
0x1800323cd  xor     edx, edx; Val
0x1800323cf  lea     rcx, [rsp+1B0h+OutBuffer]; void *
0x1800323d4  mov     r8d, 104h; Size
0x1800323da  call    memset_0
0x1800323df  xor     r13d, r13d
0x1800323e2  mov     [rsp+1B0h+BytesReturned], r13d
0x1800323e7  mov     [rsp+1B0h+pcchLength], r13
0x1800323ec  mov     [rsp+1B0h+pullResult], r13
0x1800323f1  test    r15, r15
0x1800323f4  jnz     short loc_180032400
0x1800323f6  mov     ebx, 80070057h
0x1800323fb  jmp     loc_18003270A
0x180032400  test    rbx, rbx
0x180032403  jnz     short loc_18003240F
0x180032405  mov     ebx, 80004003h
0x18003240a  jmp     loc_18003270A
0x18003240f  lea     r8, [rsp+1B0h+pcchLength]; pcchLength
0x180032414  mov     edx, 7FFFFFFFh; cchMax
0x180032419  mov     rcx, r15; psz
0x18003241c  call    StringCchLengthW
0x180032421  mov     ebx, eax
0x180032423  test    eax, eax
0x180032425  js      loc_18003270A
0x18003242b  mov     r14, [rsp+1B0h+pcchLength]
0x180032430  lea     r8, [rsp+1B0h+pullResult]; pullResult
0x180032435  mov     rcx, r14; ullMultiplicand
0x180032438  mov     edx, 2; ullMultiplier
0x18003243d  call    ULongLongMult
0x180032442  mov     ebx, eax
0x180032444  test    eax, eax
0x180032446  js      loc_18003270A
0x18003244c  mov     rax, [rsp+1B0h+pullResult]
0x180032451  lea     rdi, [rax+2]
0x180032455  cmp     rdi, rax
0x180032458  jb      loc_180032705
0x18003245e  mov     [rsp+1B0h+pullResult], rdi
0x180032463  call    cs:__imp_GetProcessHeap
0x180032469  mov     r8, rdi; dwBytes
0x18003246c  mov     edx, 8; dwFlags
0x180032471  mov     rcx, rax; hHeap
0x180032474  call    cs:__imp_HeapAlloc
0x18003247a  mov     r12, rax
0x18003247d  test    rax, rax
0x180032480  jnz     short loc_18003248C
0x180032482  mov     ebx, 8007000Eh
0x180032487  jmp     loc_18003270A
0x18003248c  shr     rdi, 1
0x18003248f  lea     rsi, [rsp+1B0h+OutBuffer]
0x180032494  jz      loc_1800326A7
0x18003249a  cmp     rdi, 7FFFFFFFh
0x1800324a1  jbe     short loc_1800324AD
0x1800324a3  mov     ebx, 80070057h
0x1800324a8  jmp     loc_1800326B1
0x1800324ad  mov     r9, r15; pszSrc
0x1800324b0  mov     [rsp+1B0h+cchToCopy], 7FFFFFFEh; cchToCopy
0x1800324b9  mov     rdx, rdi; cchDest
0x1800324bc  mov     rcx, r12; pszDest
0x1800324bf  call    StringCopyWorkerW
0x1800324c4  mov     ebx, eax
0x1800324c6  test    eax, eax
0x1800324c8  js      loc_1800326B8
0x1800324ce  test    r14, r14
0x1800324d1  jz      short loc_1800324E4
0x1800324d3  cmp     word ptr [r12+r14*2-2], 5Ch ; '\'
0x1800324da  jnz     short loc_1800324E4
0x1800324dc  xor     eax, eax
0x1800324de  mov     [r12+r14*2-2], ax
0x1800324e4  xor     r9d, r9d; lpSecurityAttributes
0x1800324e7  mov     [rsp+1B0h+hTemplateFile], r13; hTemplateFile
0x1800324ec  mov     [rsp+1B0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x1800324f1  xor     edx, edx; dwDesiredAccess
0x1800324f3  mov     rcx, r12; lpFileName
0x1800324f6  mov     dword ptr [rsp+1B0h+cchToCopy], 3; dwCreationDisposition
0x1800324fe  lea     r8d, [r9+7]; dwShareMode
0x180032502  call    cs:__imp_CreateFileW
0x180032508  mov     [rsp+1B0h+pcchLength], rax
0x18003250d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180032511  jnz     short loc_180032531
0x180032513  call    cs:__imp_GetLastError
0x180032519  mov     ebx, eax
0x18003251b  test    eax, eax
0x18003251d  jle     loc_1800326B8
0x180032523  movzx   ebx, ax
0x180032526  or      ebx, 80070000h
0x18003252c  jmp     loc_1800326B8
0x180032531  mov     edi, 104h
0x180032536  mov     [rsp+1B0h+lpOverlapped], r13; lpOverlapped
0x18003253b  lea     rcx, [rsp+1B0h+BytesReturned]
0x180032540  mov     [rsp+1B0h+hTemplateFile], rcx; lpBytesReturned
0x180032545  xor     r9d, r9d; nInBufferSize
0x180032548  mov     [rsp+1B0h+dwFlagsAndAttributes], edi; nOutBufferSize
0x18003254c  mov     rcx, rax; hDevice
0x18003254f  xor     r8d, r8d; lpInBuffer
0x180032552  mov     [rsp+1B0h+cchToCopy], rsi; lpOutBuffer
0x180032557  mov     edx, 4D0000h; dwIoControlCode
0x18003255c  mov     [rsp+1B0h+BytesReturned], r13d
0x180032561  call    cs:__imp_DeviceIoControl
0x180032567  test    eax, eax
0x180032569  jnz     loc_1800325EF
0x18003256f  call    cs:__imp_GetLastError
0x180032575  mov     ebx, eax
0x180032577  test    eax, eax
0x180032579  jle     short loc_180032584
0x18003257b  movzx   ebx, ax
0x18003257e  or      ebx, 80070000h
0x180032584  cmp     ebx, 8007007Ah
0x18003258a  jz      short loc_180032598
0x18003258c  cmp     ebx, 800700EAh
0x180032592  jnz     loc_18003269A
0x180032598  lea     rax, [rsp+1B0h+OutBuffer]
0x18003259d  cmp     rsi, rax
0x1800325a0  jz      short loc_1800325B8
0x1800325a2  call    cs:__imp_GetProcessHeap
0x1800325a8  mov     r8, rsi; lpMem
0x1800325ab  xor     edx, edx; dwFlags
0x1800325ad  mov     rcx, rax; hHeap
0x1800325b0  call    cs:__imp_HeapFree
0x1800325b6  xor     esi, esi
0x1800325b8  lea     eax, [rdi+104h]
0x1800325be  cmp     eax, edi
0x1800325c0  jb      loc_180032695
0x1800325c6  mov     edi, eax
0x1800325c8  call    cs:__imp_GetProcessHeap
0x1800325ce  mov     r8d, edi; dwBytes
0x1800325d1  xor     edx, edx; dwFlags
0x1800325d3  mov     rcx, rax; hHeap
0x1800325d6  call    cs:__imp_HeapAlloc
0x1800325dc  mov     rsi, rax
0x1800325df  test    rax, rax
0x1800325e2  mov     rax, [rsp+1B0h+pcchLength]
0x1800325e7  jnz     loc_180032536
0x1800325ed  jmp     short loc_180032638
0x1800325ef  movzx   ecx, word ptr [rsi]; ullMultiplicand
0x1800325f2  lea     r8, [rsp+1B0h+pullResult]; pullResult
0x1800325f7  mov     edx, 4; ullMultiplier
0x1800325fc  call    ULongLongMult
0x180032601  mov     ebx, eax
0x180032603  test    eax, eax
0x180032605  js      loc_18003269A
0x18003260b  mov     rax, [rsp+1B0h+pullResult]
0x180032610  lea     r15, [rax+2]
0x180032614  cmp     r15, rax
0x180032617  jb      short loc_180032695
0x180032619  call    cs:__imp_GetProcessHeap
0x18003261f  mov     r8, r15; dwBytes
0x180032622  mov     edx, 8; dwFlags
0x180032627  mov     rcx, rax; hHeap
0x18003262a  call    cs:__imp_HeapAlloc
0x180032630  mov     r13, rax
0x180032633  test    rax, rax
0x180032636  jnz     short loc_18003263F
0x180032638  mov     ebx, 8007000Eh
0x18003263d  jmp     short loc_18003269A
0x18003263f  xor     edi, edi
0x180032641  xor     r14d, r14d
0x180032644  xor     ebx, ebx
0x180032646  movzx   eax, word ptr [rsi]
0x180032649  cmp     rdi, rax
0x18003264c  jnb     short loc_180032688
0x18003264e  mov     rax, r15
0x180032651  shr     rax, 1
0x180032654  cmp     r14, rax
0x180032657  jnb     short loc_180032688
0x180032659  movzx   r9d, byte ptr [rsi+rdi+2]
0x18003265f  lea     rax, [r14+r14]
0x180032663  mov     rdx, r15
0x180032666  lea     rcx, [rax+r13]; pszDest
0x18003266a  sub     rdx, rax; cbDest
0x18003266d  lea     r8, a02x; "%02X"
0x180032674  call    StringCbPrintfW
0x180032679  mov     ebx, eax
0x18003267b  test    eax, eax
0x18003267d  js      short loc_18003269A
0x18003267f  inc     rdi
0x180032682  add     r14, 2
0x180032686  jmp     short loc_180032646
0x180032688  mov     rax, [rsp+1B0h+var_158]
0x18003268d  mov     [rax], r13
0x180032690  xor     r13d, r13d
0x180032693  jmp     short loc_18003269A
0x180032695  mov     ebx, 80070216h
0x18003269a  mov     rcx, [rsp+1B0h+pcchLength]; hObject
0x18003269f  call    cs:__imp_CloseHandle
0x1800326a5  jmp     short loc_1800326B8
0x1800326a7  mov     ebx, 80070057h
0x1800326ac  test    rdi, rdi
0x1800326af  jz      short loc_1800326B8
0x1800326b1  xor     eax, eax
0x1800326b3  mov     [r12], ax
0x1800326b8  call    cs:__imp_GetProcessHeap
0x1800326be  mov     r8, r12; lpMem
0x1800326c1  xor     edx, edx; dwFlags
0x1800326c3  mov     rcx, rax; hHeap
0x1800326c6  call    cs:__imp_HeapFree
0x1800326cc  test    r13, r13
0x1800326cf  jz      short loc_1800326E5
0x1800326d1  call    cs:__imp_GetProcessHeap
0x1800326d7  mov     r8, r13; lpMem
0x1800326da  xor     edx, edx; dwFlags
0x1800326dc  mov     rcx, rax; hHeap
0x1800326df  call    cs:__imp_HeapFree
0x1800326e5  lea     rax, [rsp+1B0h+OutBuffer]
0x1800326ea  cmp     rsi, rax
0x1800326ed  jz      short loc_18003270A
0x1800326ef  call    cs:__imp_GetProcessHeap
0x1800326f5  mov     r8, rsi; lpMem
0x1800326f8  xor     edx, edx; dwFlags
0x1800326fa  mov     rcx, rax; hHeap
0x1800326fd  call    cs:__imp_HeapFree
0x180032703  jmp     short loc_18003270A
0x180032705  mov     ebx, 80070216h
0x18003270a  mov     eax, ebx
0x18003270c  mov     rcx, [rbp+0B0h+var_40]
0x180032710  xor     rcx, rsp; StackCookie
0x180032713  call    __security_check_cookie
0x180032718  mov     rbx, [rsp+1B0h+arg_10]
0x180032720  add     rsp, 180h
0x180032727  pop     r15
0x180032729  pop     r14
0x18003272b  pop     r13
0x18003272d  pop     r12
0x18003272f  pop     rdi
0x180032730  pop     rsi
0x180032731  pop     rbp
0x180032732  retn
```
