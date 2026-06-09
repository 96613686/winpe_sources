# SpReadPipeMsg(void *,_OVERLAPPED *,ulong *,SPIPCMSG * *,ulong *)

- ea: `0x1800ec564`
- end: `0x1800ec748`
- name: `?SpReadPipeMsg@@YAJPEAXPEAU_OVERLAPPED@@PEAKPEAPEAUSPIPCMSG@@2@Z`
- size: `484`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, LPOVERLAPPED lpOverlapped@<rdx>, unsigned int *@<r8>, struct SPIPCMSG **@<r9>, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800eafcc`
- `0x1800ec3bc`

## callees

- `0x1800ec1cc`
- `0x1800ec264`
- `0x1800ec564`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ec6a8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ec6a8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800ec68e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800ec68e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ec72e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ec72e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800ec664`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800ec6d9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800ec664`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800ec6d9`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800ec613`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800ec613`

## pseudocode

```c
__int64 __fastcall SpReadPipeMsg(
        HANDLE hFile,
        LPOVERLAPPED lpOverlapped,
        unsigned int *a3,
        struct SPIPCMSG **a4,
        unsigned int *a5)
{
  unsigned int *v9; // rsi
  unsigned int v10; // ecx
  struct SPIPCMSG *v11; // rdx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  BOOL OverlappedResult; // eax
  unsigned int v16; // ebx
  unsigned __int64 v17; // r8
  LPVOID v18; // rdx
  BOOL v19; // eax
  int v20; // [rsp+30h] [rbp-18h] BYREF
  struct SPIPCMSG *v21; // [rsp+38h] [rbp-10h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+80h] [rbp+38h] BYREF

  if ( hFile )
  {
    if ( lpOverlapped )
    {
      if ( a3 )
      {
        if ( a4 )
        {
          v9 = a5;
          if ( a5 )
          {
            v10 = *a3;
            if ( *a3 && (!*a4 || v10 > 3) )
              return 2147942487LL;
            v11 = *a4;
            if ( *a4 )
            {
              if ( *a5 < 0x14 || v11 > (struct SPIPCMSG *)((char *)v11 + *a5) )
                return 2147942487LL;
            }
            NumberOfBytesTransferred = 0;
            if ( v10 )
            {
              v13 = v10 - 1;
              if ( !v13 )
              {
LABEL_17:
                OverlappedResult = GetOverlappedResult(hFile, lpOverlapped, &NumberOfBytesTransferred, 0);
LABEL_18:
                v16 = SpProcessReadResult(
                        OverlappedResult,
                        NumberOfBytesTransferred,
                        (_DWORD)a3,
                        (_DWORD)a4,
                        (__int64)v9);
                goto LABEL_29;
              }
              v14 = v13 - 1;
              if ( v14 )
              {
                if ( v14 != 1 )
                {
LABEL_30:
                  if ( *a3 == 4 )
                  {
                    *a3 = 0;
                    v16 = 0;
LABEL_33:
                    SetEvent(lpOverlapped->hEvent);
                    return v16;
                  }
                  v16 = 1;
                  if ( (*a3 & 0xFFFFFFFD) == 0 )
                    goto LABEL_33;
                  return v16;
                }
                goto LABEL_17;
              }
              v17 = (unsigned int)(*((_DWORD *)v11 + 1) - 20 + *(_DWORD *)v11);
              if ( v17 + 20 > v17 && v17 + 20 <= *a5 )
              {
                OverlappedResult = ReadFile(hFile, (char *)v11 + 20, v17, &NumberOfBytesTransferred, lpOverlapped);
                goto LABEL_18;
              }
              v16 = -2147024809;
            }
            else
            {
              v20 = *a5;
              v21 = v11;
              if ( !v11 )
              {
                v20 = 20;
                v21 = (struct SPIPCMSG *)malloc(0x14u);
                v11 = v21;
                if ( !v21 )
                {
                  v16 = -2147024882;
                  goto LABEL_26;
                }
              }
              SpInitIpcMsg(v11);
              v19 = ReadFile(hFile, v18, 0x14u, &NumberOfBytesTransferred, lpOverlapped);
              v16 = SpProcessReadResult(v19, NumberOfBytesTransferred, (_DWORD)a3, (unsigned int)&v21, (__int64)&v20);
              *a4 = v21;
              *v9 = v20;
            }
LABEL_29:
            if ( (v16 & 0x80000000) == 0 )
              goto LABEL_30;
LABEL_26:
            free(*a4);
            *a4 = 0;
            *v9 = 0;
            return v16;
          }
        }
      }
    }
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x1800ec564  push    rbp
0x1800ec566  push    rbx
0x1800ec567  push    rsi
0x1800ec568  push    rdi
0x1800ec569  push    r14
0x1800ec56b  push    r15
0x1800ec56d  mov     rbp, rsp
0x1800ec570  sub     rsp, 48h
0x1800ec574  mov     rdi, r9
0x1800ec577  mov     r14, r8
0x1800ec57a  mov     r15, rdx
0x1800ec57d  mov     rbx, rcx
0x1800ec580  test    rcx, rcx
0x1800ec583  jz      loc_1800EC736
0x1800ec589  test    rdx, rdx
0x1800ec58c  jz      loc_1800EC736
0x1800ec592  test    r8, r8
0x1800ec595  jz      loc_1800EC736
0x1800ec59b  test    r9, r9
0x1800ec59e  jz      loc_1800EC736
0x1800ec5a4  mov     rsi, [rbp+arg_20]
0x1800ec5a8  test    rsi, rsi
0x1800ec5ab  jz      loc_1800EC736
0x1800ec5b1  mov     ecx, [r8]
0x1800ec5b4  test    ecx, ecx
0x1800ec5b6  jz      short loc_1800EC5C3
0x1800ec5b8  cmp     qword ptr [r9], 0
0x1800ec5bc  jz      short loc_1800EC5DA
0x1800ec5be  cmp     ecx, 3
0x1800ec5c1  ja      short loc_1800EC5DA
0x1800ec5c3  mov     rdx, [r9]
0x1800ec5c6  test    rdx, rdx
0x1800ec5c9  jz      short loc_1800EC5E4
0x1800ec5cb  cmp     dword ptr [rsi], 14h
0x1800ec5ce  jb      short loc_1800EC5DA
0x1800ec5d0  mov     eax, [rsi]
0x1800ec5d2  add     rax, rdx
0x1800ec5d5  cmp     rdx, rax
0x1800ec5d8  jbe     short loc_1800EC5E4
0x1800ec5da  mov     eax, 80070057h
0x1800ec5df  jmp     loc_1800EC73B
0x1800ec5e4  mov     [rbp+NumberOfBytesTransferred], 0
0x1800ec5eb  test    ecx, ecx
0x1800ec5ed  jz      loc_1800EC676
0x1800ec5f3  sub     ecx, 1
0x1800ec5f6  jz      short loc_1800EC606
0x1800ec5f8  sub     ecx, 1
0x1800ec5fb  jz      short loc_1800EC635
0x1800ec5fd  cmp     ecx, 1
0x1800ec600  jnz     loc_1800EC70B
0x1800ec606  xor     r9d, r9d; bWait
0x1800ec609  lea     r8, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1800ec60d  mov     rdx, r15; lpOverlapped
0x1800ec610  mov     rcx, rbx; hFile
0x1800ec613  call    cs:__imp_GetOverlappedResult
0x1800ec619  mov     edx, [rbp+NumberOfBytesTransferred]
0x1800ec61c  mov     r9, rdi
0x1800ec61f  mov     r8, r14
0x1800ec622  mov     [rsp+48h+lpOverlapped], rsi
0x1800ec627  mov     ecx, eax
0x1800ec629  call    SpProcessReadResult
0x1800ec62e  mov     ebx, eax
0x1800ec630  jmp     loc_1800EC707
0x1800ec635  mov     ecx, [rdx+4]
0x1800ec638  mov     r8d, [rdx]
0x1800ec63b  add     ecx, 0FFFFFFECh
0x1800ec63e  add     r8d, ecx; nNumberOfBytesToRead
0x1800ec641  mov     eax, r8d
0x1800ec644  lea     rcx, [r8+14h]
0x1800ec648  cmp     rcx, rax
0x1800ec64b  jbe     short loc_1800EC66C
0x1800ec64d  mov     eax, [rsi]
0x1800ec64f  cmp     rcx, rax
0x1800ec652  ja      short loc_1800EC66C
0x1800ec654  add     rdx, 14h; lpBuffer
0x1800ec658  mov     [rsp+48h+lpOverlapped], r15; lpOverlapped
0x1800ec65d  lea     r9, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesRead
0x1800ec661  mov     rcx, rbx; hFile
0x1800ec664  call    cs:__imp_ReadFile
0x1800ec66a  jmp     short loc_1800EC619
0x1800ec66c  mov     ebx, 80070057h
0x1800ec671  jmp     loc_1800EC707
0x1800ec676  mov     eax, [rsi]
0x1800ec678  mov     [rbp+var_18], eax
0x1800ec67b  mov     [rbp+var_10], rdx
0x1800ec67f  test    rdx, rdx
0x1800ec682  jnz     short loc_1800EC6BF
0x1800ec684  lea     ecx, [rdx+14h]; Size
0x1800ec687  mov     [rbp+var_18], 14h
0x1800ec68e  call    cs:__imp_malloc
0x1800ec694  mov     [rbp+var_10], rax
0x1800ec698  mov     rdx, rax
0x1800ec69b  test    rax, rax
0x1800ec69e  jnz     short loc_1800EC6BF
0x1800ec6a0  mov     ebx, 8007000Eh
0x1800ec6a5  mov     rcx, [rdi]; Block
0x1800ec6a8  call    cs:__imp_free
0x1800ec6ae  mov     qword ptr [rdi], 0
0x1800ec6b5  mov     dword ptr [rsi], 0
0x1800ec6bb  mov     eax, ebx
0x1800ec6bd  jmp     short loc_1800EC73B
0x1800ec6bf  mov     rcx, rdx; struct SPIPCMSG *
0x1800ec6c2  call    ?SpInitIpcMsg@@YAXPEAUSPIPCMSG@@@Z; SpInitIpcMsg(SPIPCMSG *)
0x1800ec6c7  lea     r9, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesRead
0x1800ec6cb  mov     [rsp+48h+lpOverlapped], r15; lpOverlapped
0x1800ec6d0  mov     r8d, 14h; nNumberOfBytesToRead
0x1800ec6d6  mov     rcx, rbx; hFile
0x1800ec6d9  call    cs:__imp_ReadFile
0x1800ec6df  mov     edx, [rbp+NumberOfBytesTransferred]
0x1800ec6e2  lea     rcx, [rbp+var_18]
0x1800ec6e6  mov     [rsp+48h+lpOverlapped], rcx
0x1800ec6eb  lea     r9, [rbp+var_10]
0x1800ec6ef  mov     ecx, eax
0x1800ec6f1  mov     r8, r14
0x1800ec6f4  call    SpProcessReadResult
0x1800ec6f9  mov     ebx, eax
0x1800ec6fb  mov     rax, [rbp+var_10]
0x1800ec6ff  mov     [rdi], rax
0x1800ec702  mov     eax, [rbp+var_18]
0x1800ec705  mov     [rsi], eax
0x1800ec707  test    ebx, ebx
0x1800ec709  js      short loc_1800EC6A5
0x1800ec70b  cmp     dword ptr [r14], 4
0x1800ec70f  jnz     short loc_1800EC71C
0x1800ec711  mov     dword ptr [r14], 0
0x1800ec718  xor     ebx, ebx
0x1800ec71a  jmp     short loc_1800EC72A
0x1800ec71c  test    dword ptr [r14], 0FFFFFFFDh
0x1800ec723  mov     ebx, 1
0x1800ec728  jnz     short loc_1800EC6BB
0x1800ec72a  mov     rcx, [r15+18h]; hEvent
0x1800ec72e  call    cs:__imp_SetEvent
0x1800ec734  jmp     short loc_1800EC6BB
0x1800ec736  mov     eax, 80004003h
0x1800ec73b  add     rsp, 48h
0x1800ec73f  pop     r15
0x1800ec741  pop     r14
0x1800ec743  pop     rdi
0x1800ec744  pop     rsi
0x1800ec745  pop     rbx
0x1800ec746  pop     rbp
0x1800ec747  retn
```
