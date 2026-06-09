# FvepConvertVolumeNameToCacheValueName

- ea: `0x180042fc8`
- end: `0x1800433de`
- name: `FvepConvertVolumeNameToCacheValueName`
- size: `1046`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800436e0`
- `0x1800439e0`

## callees

- `0x180035ae0`
- `0x180042fc8`
- `0x18007ec9a`
- `0x18007ed40`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180043179`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180043179`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800430a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043221`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004324b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800432c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043365`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043380`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004339e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800430a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043221`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004324b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800432c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043365`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043380`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004339e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800430b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180043259`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800432d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800430b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180043259`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800432d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004322f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043375`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004338e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800433ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004322f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043375`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004338e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800433ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004318a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800431ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004318a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800431ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043351`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043351`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800431db`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180043294`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800431db`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180043294`

## pseudocode

```c
__int64 __fastcall FvepConvertVolumeNameToCacheValueName(WCHAR *a1, wchar_t **a2)
{
  DWORD v4; // r13d
  wchar_t *v5; // r12
  signed int v6; // ebx
  WCHAR *v7; // rax
  __int64 v8; // rdx
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rax
  SIZE_T v11; // rdi
  HANDLE ProcessHeap; // rax
  _WORD *v13; // rax
  const WCHAR *v14; // r10
  unsigned __int64 v15; // rdi
  _WORD *v16; // r14
  __int64 v17; // rax
  WCHAR *v18; // rdx
  WCHAR *v19; // rcx
  unsigned __int64 v20; // r15
  HANDLE FileW; // rax
  signed int LastError; // eax
  HANDLE v23; // rdi
  signed int v24; // eax
  HANDLE v25; // rax
  HANDLE v26; // rax
  unsigned __int64 v27; // rax
  SIZE_T v28; // rdi
  HANDLE v29; // rax
  SIZE_T v30; // rsi
  HANDLE v31; // rax
  HANDLE v32; // rax
  HANDLE v33; // rax
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hDevice; // [rsp+48h] [rbp-B8h]
  LPVOID lpMem; // [rsp+50h] [rbp-B0h]
  wchar_t **v38; // [rsp+58h] [rbp-A8h]
  _BYTE OutBuffer[272]; // [rsp+70h] [rbp-90h] BYREF

  v38 = a2;
  v4 = 260;
  memset_0(OutBuffer, 0, 0x104u);
  v5 = 0;
  BytesReturned = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      v7 = a1;
      v8 = 0x7FFFFFFF;
      do
      {
        if ( !*v7 )
          break;
        ++v7;
        --v8;
      }
      while ( v8 );
      v6 = -2147024809;
      v9 = (0x7FFFFFFF - v8) & -(__int64)(v8 != 0);
      if ( v8 )
      {
        lpMem = 0;
        v10 = 2 * v9;
        if ( is_mul_ok(v9, 2u) && (v11 = v10 + 2, v10 + 2 >= v10) )
        {
          ProcessHeap = GetProcessHeap();
          v13 = HeapAlloc(ProcessHeap, 8u, v11);
          lpMem = v13;
          v14 = v13;
          if ( v13 )
          {
            v15 = v11 >> 1;
            v16 = OutBuffer;
            if ( v15 )
            {
              if ( v15 <= 0x7FFFFFFF )
              {
                v17 = 2147483646;
                v18 = (WCHAR *)v14;
                do
                {
                  if ( !v17 )
                    break;
                  if ( !*a1 )
                    break;
                  *v18++ = *a1++;
                  --v17;
                  --v15;
                }
                while ( v15 );
                v19 = v18 - 1;
                v20 = 0;
                v6 = v15 == 0 ? 0x8007007A : 0;
                if ( v15 )
                  v19 = v18;
                *v19 = 0;
                if ( v15 )
                {
                  if ( v9 && v14[v9 - 1] == 92 )
                    v14[v9 - 1] = 0;
                  FileW = CreateFileW(v14, 0, 7u, 0, 3u, 0, 0);
                  hDevice = FileW;
                  if ( FileW == (HANDLE)-1LL )
                  {
                    LastError = GetLastError();
                    v6 = LastError;
                    if ( LastError > 0 )
                      v6 = (unsigned __int16)LastError | 0x80070000;
                  }
                  else
                  {
                    BytesReturned = 0;
                    if ( DeviceIoControl(FileW, 0x4D0000u, 0, 0, OutBuffer, 0x104u, &BytesReturned, 0) )
                    {
LABEL_41:
                      v27 = 4LL * (unsigned __int16)*v16;
                      if ( is_mul_ok((unsigned __int16)*v16, 4u) && (v28 = v27 + 2, v27 + 2 >= v27) )
                      {
                        v29 = GetProcessHeap();
                        v5 = (wchar_t *)HeapAlloc(v29, 8u, v28);
                        if ( v5 )
                        {
                          v30 = 0;
                          v6 = 0;
                          if ( *v16 )
                          {
                            do
                            {
                              if ( v30 >= v28 >> 1 )
                                break;
                              v6 = StringCbPrintfW(
                                     &v5[v30],
                                     v28 - 2 * v30,
                                     L"%02X",
                                     *((unsigned __int8 *)v16 + v20 + 2));
                              if ( v6 < 0 )
                                goto LABEL_51;
                              ++v20;
                              v30 += 2LL;
                            }
                            while ( v20 < (unsigned __int16)*v16 );
                          }
                          *v38 = v5;
                          v5 = 0;
                        }
                        else
                        {
LABEL_49:
                          v6 = -2147024882;
                        }
                      }
                      else
                      {
LABEL_50:
                        v6 = -2147024362;
                      }
                    }
                    else
                    {
                      v23 = hDevice;
                      while ( 1 )
                      {
                        v24 = GetLastError();
                        v6 = v24;
                        if ( v24 > 0 )
                          v6 = (unsigned __int16)v24 | 0x80070000;
                        if ( v6 != -2147024774 && v6 != -2147024662 )
                          break;
                        if ( v16 != (_WORD *)OutBuffer )
                        {
                          v25 = GetProcessHeap();
                          HeapFree(v25, 0, v16);
                          v16 = 0;
                        }
                        if ( v4 + 260 < v4 )
                          goto LABEL_50;
                        v4 += 260;
                        v26 = GetProcessHeap();
                        v16 = HeapAlloc(v26, 0, v4);
                        if ( !v16 )
                          goto LABEL_49;
                        BytesReturned = 0;
                        if ( DeviceIoControl(v23, 0x4D0000u, 0, 0, v16, v4, &BytesReturned, 0) )
                          goto LABEL_41;
                      }
                    }
LABEL_51:
                    CloseHandle(hDevice);
                  }
                }
              }
              else
              {
                *v13 = 0;
              }
            }
            v31 = GetProcessHeap();
            HeapFree(v31, 0, lpMem);
            if ( v5 )
            {
              v32 = GetProcessHeap();
              HeapFree(v32, 0, v5);
            }
            if ( v16 != (_WORD *)OutBuffer )
            {
              v33 = GetProcessHeap();
              HeapFree(v33, 0, v16);
            }
          }
          else
          {
            return (unsigned int)-2147024882;
          }
        }
        else
        {
          return (unsigned int)-2147024362;
        }
      }
      else
      {
        return (unsigned int)-2147024809;
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
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180042fc8  push    rbp
0x180042fca  push    rbx
0x180042fcb  push    rsi
0x180042fcc  push    rdi
0x180042fcd  push    r12
0x180042fcf  push    r13
0x180042fd1  push    r14
0x180042fd3  push    r15
0x180042fd5  lea     rbp, [rsp-98h]
0x180042fdd  sub     rsp, 198h
0x180042fe4  mov     rax, cs:__security_cookie
0x180042feb  xor     rax, rsp
0x180042fee  mov     [rbp+0D0h+var_50], rax
0x180042ff5  mov     rbx, rdx
0x180042ff8  mov     [rsp+1D0h+var_178], rdx
0x180042ffd  mov     r15, rcx
0x180043000  mov     r13d, 104h
0x180043006  mov     r8d, r13d; Size
0x180043009  lea     rcx, [rsp+1D0h+OutBuffer]; void *
0x18004300e  xor     edx, edx; Val
0x180043010  call    memset_0
0x180043015  xor     r12d, r12d
0x180043018  mov     [rsp+1D0h+BytesReturned], r12d
0x18004301d  test    r15, r15
0x180043020  jnz     short loc_18004302C
0x180043022  mov     ebx, 80070057h
0x180043027  jmp     loc_1800433B9
0x18004302c  test    rbx, rbx
0x18004302f  jnz     short loc_18004303B
0x180043031  mov     ebx, 80004003h
0x180043036  jmp     loc_1800433B9
0x18004303b  mov     ecx, 7FFFFFFFh
0x180043040  mov     rax, r15
0x180043043  mov     edx, ecx
0x180043045  cmp     [rax], r12w
0x180043049  jz      short loc_180043055
0x18004304b  add     rax, 2
0x18004304f  sub     rdx, 1
0x180043053  jnz     short loc_180043045
0x180043055  mov     rax, rdx
0x180043058  mov     ebx, 80070057h
0x18004305d  neg     rax
0x180043060  mov     rax, rdx
0x180043063  sbb     r8d, r8d
0x180043066  sub     rcx, rdx
0x180043069  not     r8d
0x18004306c  and     r8d, ebx
0x18004306f  neg     rax
0x180043072  sbb     rsi, rsi
0x180043075  and     rsi, rcx
0x180043078  test    rdx, rdx
0x18004307b  jnz     short loc_180043085
0x18004307d  mov     ebx, r8d
0x180043080  jmp     loc_1800433B9
0x180043085  mov     eax, 2
0x18004308a  mov     [rsp+1D0h+lpMem], r12
0x18004308f  mul     rsi
0x180043092  test    rdx, rdx
0x180043095  jnz     loc_1800433B4
0x18004309b  lea     rdi, [rax+2]
0x18004309f  cmp     rdi, rax
0x1800430a2  jb      loc_1800433B4
0x1800430a8  call    cs:__imp_GetProcessHeap
0x1800430ae  mov     r8, rdi; dwBytes
0x1800430b1  mov     edx, 8; dwFlags
0x1800430b6  mov     rcx, rax; hHeap
0x1800430b9  call    cs:__imp_HeapAlloc
0x1800430bf  mov     [rsp+1D0h+lpMem], rax
0x1800430c4  mov     r10, rax
0x1800430c7  test    rax, rax
0x1800430ca  jnz     short loc_1800430D6
0x1800430cc  mov     ebx, 8007000Eh
0x1800430d1  jmp     loc_1800433B9
0x1800430d6  shr     rdi, 1
0x1800430d9  lea     r14, [rsp+1D0h+OutBuffer]
0x1800430de  jz      loc_180043359
0x1800430e4  cmp     rdi, 7FFFFFFFh
0x1800430eb  jbe     short loc_1800430F5
0x1800430ed  xor     r15d, r15d
0x1800430f0  jmp     loc_180043361
0x1800430f5  mov     eax, 7FFFFFFEh
0x1800430fa  mov     rdx, r10
0x1800430fd  test    rax, rax
0x180043100  jz      short loc_18004311F
0x180043102  movzx   ecx, word ptr [r15]
0x180043106  test    cx, cx
0x180043109  jz      short loc_18004311F
0x18004310b  mov     [rdx], cx
0x18004310e  add     r15, 2
0x180043112  add     rdx, 2
0x180043116  dec     rax
0x180043119  sub     rdi, 1
0x18004311d  jnz     short loc_1800430FD
0x18004311f  mov     rax, rdi
0x180043122  lea     rcx, [rdx-2]
0x180043126  neg     rax
0x180043129  sbb     ebx, ebx
0x18004312b  xor     r15d, r15d
0x18004312e  not     ebx
0x180043130  and     ebx, 8007007Ah
0x180043136  test    rdi, rdi
0x180043139  cmovnz  rcx, rdx
0x18004313d  mov     [rcx], r15w
0x180043141  jz      loc_180043365
0x180043147  test    rsi, rsi
0x18004314a  jz      short loc_18004315B
0x18004314c  cmp     word ptr [r10+rsi*2-2], 5Ch ; '\'
0x180043153  jnz     short loc_18004315B
0x180043155  mov     [r10+rsi*2-2], r15w
0x18004315b  xor     r9d, r9d; lpSecurityAttributes
0x18004315e  mov     [rsp+1D0h+hTemplateFile], r15; hTemplateFile
0x180043163  mov     [rsp+1D0h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x180043168  xor     edx, edx; dwDesiredAccess
0x18004316a  mov     rcx, r10; lpFileName
0x18004316d  mov     [rsp+1D0h+dwCreationDisposition], 3; dwCreationDisposition
0x180043175  lea     r8d, [r9+7]; dwShareMode
0x180043179  call    cs:__imp_CreateFileW
0x18004317f  mov     [rsp+1D0h+hDevice], rax
0x180043184  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180043188  jnz     short loc_1800431A8
0x18004318a  call    cs:__imp_GetLastError
0x180043190  mov     ebx, eax
0x180043192  test    eax, eax
0x180043194  jle     loc_180043365
0x18004319a  movzx   ebx, ax
0x18004319d  or      ebx, 80070000h
0x1800431a3  jmp     loc_180043365
0x1800431a8  mov     [rsp+1D0h+lpOverlapped], r15; lpOverlapped
0x1800431ad  lea     rcx, [rsp+1D0h+BytesReturned]
0x1800431b2  mov     [rsp+1D0h+hTemplateFile], rcx; lpBytesReturned
0x1800431b7  mov     esi, 4D0000h
0x1800431bc  lea     rcx, [rsp+1D0h+OutBuffer]
0x1800431c1  mov     [rsp+1D0h+dwFlagsAndAttributes], r13d; nOutBufferSize
0x1800431c6  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rcx; lpOutBuffer
0x1800431cb  xor     r9d, r9d; nInBufferSize
0x1800431ce  mov     rcx, rax; hDevice
0x1800431d1  mov     [rsp+1D0h+BytesReturned], r15d
0x1800431d6  xor     r8d, r8d; lpInBuffer
0x1800431d9  mov     edx, esi; dwIoControlCode
0x1800431db  call    cs:__imp_DeviceIoControl
0x1800431e1  test    eax, eax
0x1800431e3  jnz     loc_1800432A2
0x1800431e9  mov     rdi, [rsp+1D0h+hDevice]
0x1800431ee  call    cs:__imp_GetLastError
0x1800431f4  mov     ebx, eax
0x1800431f6  test    eax, eax
0x1800431f8  jle     short loc_180043203
0x1800431fa  movzx   ebx, ax
0x1800431fd  or      ebx, 80070000h
0x180043203  cmp     ebx, 8007007Ah
0x180043209  jz      short loc_180043217
0x18004320b  cmp     ebx, 800700EAh
0x180043211  jnz     loc_18004334C
0x180043217  lea     rax, [rsp+1D0h+OutBuffer]
0x18004321c  cmp     r14, rax
0x18004321f  jz      short loc_180043238
0x180043221  call    cs:__imp_GetProcessHeap
0x180043227  mov     r8, r14; lpMem
0x18004322a  xor     edx, edx; dwFlags
0x18004322c  mov     rcx, rax; hHeap
0x18004322f  call    cs:__imp_HeapFree
0x180043235  mov     r14, r15
0x180043238  lea     eax, [r13+104h]
0x18004323f  cmp     eax, r13d
0x180043242  jb      loc_180043347
0x180043248  mov     r13d, eax
0x18004324b  call    cs:__imp_GetProcessHeap
0x180043251  mov     r8d, r13d; dwBytes
0x180043254  xor     edx, edx; dwFlags
0x180043256  mov     rcx, rax; hHeap
0x180043259  call    cs:__imp_HeapAlloc
0x18004325f  mov     r14, rax
0x180043262  test    rax, rax
0x180043265  jz      loc_180043340
0x18004326b  mov     [rsp+1D0h+lpOverlapped], r15; lpOverlapped
0x180043270  lea     rax, [rsp+1D0h+BytesReturned]
0x180043275  mov     [rsp+1D0h+hTemplateFile], rax; lpBytesReturned
0x18004327a  xor     r9d, r9d; nInBufferSize
0x18004327d  mov     [rsp+1D0h+dwFlagsAndAttributes], r13d; nOutBufferSize
0x180043282  xor     r8d, r8d; lpInBuffer
0x180043285  mov     edx, esi; dwIoControlCode
0x180043287  mov     qword ptr [rsp+1D0h+dwCreationDisposition], r14; lpOutBuffer
0x18004328c  mov     rcx, rdi; hDevice
0x18004328f  mov     [rsp+1D0h+BytesReturned], r15d
0x180043294  call    cs:__imp_DeviceIoControl
0x18004329a  test    eax, eax
0x18004329c  jz      loc_1800431EE
0x1800432a2  movzx   ecx, word ptr [r14]
0x1800432a6  mov     eax, 4
0x1800432ab  mul     rcx
0x1800432ae  test    rdx, rdx
0x1800432b1  jnz     loc_180043347
0x1800432b7  lea     rdi, [rax+2]
0x1800432bb  cmp     rdi, rax
0x1800432be  jb      loc_180043347
0x1800432c4  call    cs:__imp_GetProcessHeap
0x1800432ca  mov     r8, rdi; dwBytes
0x1800432cd  mov     edx, 8; dwFlags
0x1800432d2  mov     rcx, rax; hHeap
0x1800432d5  call    cs:__imp_HeapAlloc
0x1800432db  mov     r12, rax
0x1800432de  test    rax, rax
0x1800432e1  jz      short loc_180043340
0x1800432e3  xor     eax, eax
0x1800432e5  mov     esi, eax
0x1800432e7  mov     ebx, eax
0x1800432e9  cmp     ax, [r14]
0x1800432ed  jnb     short loc_180043330
0x1800432ef  mov     r13, rdi
0x1800432f2  shr     r13, 1
0x1800432f5  cmp     rsi, r13
0x1800432f8  jnb     short loc_180043330
0x1800432fa  movzx   r9d, byte ptr [r14+r15+2]
0x180043300  lea     rax, [rsi+rsi]
0x180043304  mov     rdx, rdi
0x180043307  lea     rcx, [rax+r12]; pszDest
0x18004330b  sub     rdx, rax; cbDest
0x18004330e  lea     r8, a02x; "%02X"
0x180043315  call    StringCbPrintfW
0x18004331a  mov     ebx, eax
0x18004331c  test    eax, eax
0x18004331e  js      short loc_18004334C
0x180043320  movzx   ecx, word ptr [r14]
0x180043324  inc     r15
0x180043327  add     rsi, 2
0x18004332b  cmp     r15, rcx
0x18004332e  jb      short loc_1800432F5
0x180043330  mov     rax, [rsp+1D0h+var_178]
0x180043335  xor     r15d, r15d
0x180043338  mov     [rax], r12
0x18004333b  mov     r12d, r15d
0x18004333e  jmp     short loc_18004334C
0x180043340  mov     ebx, 8007000Eh
0x180043345  jmp     short loc_18004334C
0x180043347  mov     ebx, 80070216h
0x18004334c  mov     rcx, [rsp+1D0h+hDevice]; hObject
0x180043351  call    cs:__imp_CloseHandle
0x180043357  jmp     short loc_180043365
0x180043359  xor     r15d, r15d
0x18004335c  test    rdi, rdi
0x18004335f  jz      short loc_180043365
0x180043361  mov     [rax], r15w
0x180043365  call    cs:__imp_GetProcessHeap
0x18004336b  mov     r8, [rsp+1D0h+lpMem]; lpMem
0x180043370  xor     edx, edx; dwFlags
0x180043372  mov     rcx, rax; hHeap
0x180043375  call    cs:__imp_HeapFree
0x18004337b  test    r12, r12
0x18004337e  jz      short loc_180043394
0x180043380  call    cs:__imp_GetProcessHeap
0x180043386  mov     r8, r12; lpMem
0x180043389  xor     edx, edx; dwFlags
0x18004338b  mov     rcx, rax; hHeap
0x18004338e  call    cs:__imp_HeapFree
0x180043394  lea     rax, [rsp+1D0h+OutBuffer]
0x180043399  cmp     r14, rax
0x18004339c  jz      short loc_1800433B9
0x18004339e  call    cs:__imp_GetProcessHeap
0x1800433a4  mov     r8, r14; lpMem
0x1800433a7  xor     edx, edx; dwFlags
0x1800433a9  mov     rcx, rax; hHeap
0x1800433ac  call    cs:__imp_HeapFree
0x1800433b2  jmp     short loc_1800433B9
0x1800433b4  mov     ebx, 80070216h
0x1800433b9  mov     eax, ebx
0x1800433bb  mov     rcx, [rbp+0D0h+var_50]
0x1800433c2  xor     rcx, rsp; StackCookie
0x1800433c5  call    __security_check_cookie
0x1800433ca  add     rsp, 198h
0x1800433d1  pop     r15
0x1800433d3  pop     r14
0x1800433d5  pop     r13
0x1800433d7  pop     r12
0x1800433d9  pop     rdi
0x1800433da  pop     rsi
0x1800433db  pop     rbx
0x1800433dc  pop     rbp
0x1800433dd  retn
```
