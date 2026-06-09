# DvcInfoGetMountMgrUniqueId

- ea: `0x1800a8fbc`
- end: `0x1800a9239`
- name: `DvcInfoGetMountMgrUniqueId`
- size: `637`
- prototype: `__int64 __fastcall(void *Src, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callers

- `0x18009b200`

## callees

- `0x180078746`
- `0x1800a8fbc`
- `0x1800b645a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9121`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a9220`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a9220`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a9002`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a9002`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a9156`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a91ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a9217`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a9156`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a91ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a9217`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a9069`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a90cf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a9069`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a90cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a905b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a90c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a9148`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a91de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a9209`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a905b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a90c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a9148`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a91de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a9209`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a9117`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a9117`

## string_xrefs

- `0x1800a8fe7`: `\\.\MountPointManager`

## pseudocode

```c
__int64 __fastcall DvcInfoGetMountMgrUniqueId(_WORD *Src, void *a2)
{
  HANDLE FileW; // rax
  __int64 v5; // r8
  void *v6; // r12
  DWORD LastError; // ebx
  int v8; // ebx
  DWORD v9; // r14d
  HANDLE ProcessHeap; // rcx
  _WORD *v11; // rax
  _WORD *v12; // rsi
  DWORD nOutBufferSize; // ebp
  HANDLE v14; // rcx
  DWORD *v15; // rax
  DWORD *lpOutBuffer; // rdi
  HANDLE v17; // rcx
  unsigned int v18; // ebx
  unsigned int i; // eax
  HANDLE v20; // rcx
  HANDLE v21; // rcx
  DWORD BytesReturned; // [rsp+A0h] [rbp+18h] BYREF

  BytesReturned = 0;
  FileW = CreateFileW(L"\\\\.\\MountPointManager", 0, 3u, 0, 4u, 0x80u, 0);
  v5 = -1;
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    return GetLastError();
  }
  else
  {
    do
      ++v5;
    while ( Src[v5] );
    v8 = 2 * v5;
    if ( (unsigned int)(2 * v5) <= 0xFFFF )
    {
      v9 = v8 + 24;
      if ( *(_QWORD *)&PfSvcGlobals )
        ProcessHeap = *(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL);
      else
        ProcessHeap = GetProcessHeap();
      v11 = HeapAlloc(ProcessHeap, 0, (unsigned int)(v8 + 24));
      v12 = v11;
      if ( v11 )
      {
        memset_0(v11, 0, (unsigned int)(v8 + 24));
        v12[10] = v8;
        *((_DWORD *)v12 + 4) = 24;
        memcpy_0(v12 + 12, Src, (unsigned __int16)v8);
        nOutBufferSize = 32;
        while ( 1 )
        {
          if ( *(_QWORD *)&PfSvcGlobals )
            v14 = *(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL);
          else
            v14 = GetProcessHeap();
          v15 = (DWORD *)HeapAlloc(v14, 0, nOutBufferSize);
          lpOutBuffer = v15;
          if ( !v15 )
          {
            LastError = 8;
            goto LABEL_32;
          }
          memset_0(v15, 0, nOutBufferSize);
          if ( DeviceIoControl(v6, 0x6D0008u, v12, v9, lpOutBuffer, nOutBufferSize, &BytesReturned, 0) )
            break;
          LastError = GetLastError();
          if ( LastError != 234 )
            goto LABEL_32;
          nOutBufferSize = *lpOutBuffer;
          if ( *(_QWORD *)&PfSvcGlobals )
            v17 = *(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL);
          else
            v17 = GetProcessHeap();
          HeapFree(v17, 0, lpOutBuffer);
        }
        if ( lpOutBuffer[1] )
        {
          v18 = *((unsigned __int16 *)lpOutBuffer + 10) >> 1;
          if ( 2 * v18 + 2 <= 0x200 )
          {
            memcpy_0(a2, (char *)lpOutBuffer + lpOutBuffer[4], 2LL * v18);
            for ( i = 0; i < v18; ++i )
            {
              if ( !*((_WORD *)a2 + i) )
                *((_WORD *)a2 + i) = 95;
            }
            *((_WORD *)a2 + v18) = 0;
            LastError = 0;
          }
          else
          {
            LastError = 122;
          }
        }
        else
        {
          LastError = 13;
        }
LABEL_32:
        if ( *(_QWORD *)&PfSvcGlobals )
          v20 = *(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL);
        else
          v20 = GetProcessHeap();
        HeapFree(v20, 0, v12);
        if ( lpOutBuffer )
        {
          if ( *(_QWORD *)&PfSvcGlobals )
            v21 = *(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL);
          else
            v21 = GetProcessHeap();
          HeapFree(v21, 0, lpOutBuffer);
        }
      }
      else
      {
        LastError = 8;
      }
    }
    else
    {
      LastError = 534;
    }
    CloseHandle(v6);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800a8fbc  mov     rax, rsp
0x1800a8fbf  mov     [rax+18h], r8d
0x1800a8fc3  push    rbx
0x1800a8fc4  push    rbp
0x1800a8fc5  push    rsi
0x1800a8fc6  push    rdi
0x1800a8fc7  push    r12
0x1800a8fc9  push    r13
0x1800a8fcb  push    r14
0x1800a8fcd  push    r15
0x1800a8fcf  sub     rsp, 48h
0x1800a8fd3  xor     r13d, r13d
0x1800a8fd6  mov     r15, rdx
0x1800a8fd9  mov     [rax-58h], r13
0x1800a8fdd  mov     rbp, rcx
0x1800a8fe0  mov     dword ptr [rax-60h], 80h
0x1800a8fe7  lea     rcx, FileName; "\\\\.\\MountPointManager"
0x1800a8fee  xor     r9d, r9d; lpSecurityAttributes
0x1800a8ff1  mov     [rax+18h], r13d
0x1800a8ff5  lea     r8d, [r13+3]; dwShareMode
0x1800a8ff9  mov     dword ptr [rax-68h], 4
0x1800a9000  xor     edx, edx; dwDesiredAccess
0x1800a9002  call    cs:__imp_CreateFileW
0x1800a9008  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800a900c  mov     r12, rax
0x1800a900f  cmp     rax, r8
0x1800a9012  jnz     short loc_1800A9021
0x1800a9014  call    cs:__imp_GetLastError
0x1800a901a  mov     ebx, eax
0x1800a901c  jmp     loc_1800A9226
0x1800a9021  inc     r8
0x1800a9024  cmp     [rbp+r8*2+0], r13w
0x1800a902a  jnz     short loc_1800A9021
0x1800a902c  lea     ebx, [r8+r8]
0x1800a9030  cmp     ebx, 0FFFFh
0x1800a9036  jbe     short loc_1800A9042
0x1800a9038  mov     ebx, 216h
0x1800a903d  jmp     loc_1800A921D
0x1800a9042  mov     rcx, cs:PfSvcGlobals
0x1800a9049  lea     r14d, [rbx+18h]
0x1800a904d  mov     edi, r14d
0x1800a9050  test    rcx, rcx
0x1800a9053  jz      short loc_1800A905B
0x1800a9055  mov     rcx, [rcx+58h]
0x1800a9059  jmp     short loc_1800A9064
0x1800a905b  call    cs:__imp_GetProcessHeap
0x1800a9061  mov     rcx, rax; hHeap
0x1800a9064  mov     r8, rdi; dwBytes
0x1800a9067  xor     edx, edx; dwFlags
0x1800a9069  call    cs:__imp_HeapAlloc
0x1800a906f  mov     rsi, rax
0x1800a9072  test    rax, rax
0x1800a9075  jnz     short loc_1800A907F
0x1800a9077  lea     ebx, [rax+8]
0x1800a907a  jmp     loc_1800A921D
0x1800a907f  mov     r8, rdi; Size
0x1800a9082  xor     edx, edx; Val
0x1800a9084  mov     rcx, rsi; void *
0x1800a9087  call    memset_0
0x1800a908c  movzx   r8d, bx; Size
0x1800a9090  lea     rcx, [rsi+18h]; void *
0x1800a9094  mov     rdx, rbp; Src
0x1800a9097  mov     [rsi+14h], r8w
0x1800a909c  mov     dword ptr [rsi+10h], 18h
0x1800a90a3  call    memcpy_0
0x1800a90a8  mov     ebp, 20h ; ' '
0x1800a90ad  mov     rcx, cs:PfSvcGlobals
0x1800a90b4  mov     ebx, ebp
0x1800a90b6  test    rcx, rcx
0x1800a90b9  jz      short loc_1800A90C1
0x1800a90bb  mov     rcx, [rcx+58h]
0x1800a90bf  jmp     short loc_1800A90CA
0x1800a90c1  call    cs:__imp_GetProcessHeap
0x1800a90c7  mov     rcx, rax; hHeap
0x1800a90ca  mov     r8, rbx; dwBytes
0x1800a90cd  xor     edx, edx; dwFlags
0x1800a90cf  call    cs:__imp_HeapAlloc
0x1800a90d5  mov     rdi, rax
0x1800a90d8  test    rax, rax
0x1800a90db  jz      loc_1800A91C7
0x1800a90e1  mov     r8, rbx; Size
0x1800a90e4  xor     edx, edx; Val
0x1800a90e6  mov     rcx, rax; void *
0x1800a90e9  call    memset_0
0x1800a90ee  mov     [rsp+88h+lpOverlapped], r13; lpOverlapped
0x1800a90f3  lea     rax, [rsp+88h+BytesReturned]
0x1800a90fb  mov     [rsp+88h+lpBytesReturned], rax; lpBytesReturned
0x1800a9100  mov     r9d, r14d; nInBufferSize
0x1800a9103  mov     [rsp+88h+nOutBufferSize], ebp; nOutBufferSize
0x1800a9107  mov     r8, rsi; lpInBuffer
0x1800a910a  mov     edx, 6D0008h; dwIoControlCode
0x1800a910f  mov     [rsp+88h+lpOutBuffer], rdi; lpOutBuffer
0x1800a9114  mov     rcx, r12; hDevice
0x1800a9117  call    cs:__imp_DeviceIoControl
0x1800a911d  test    eax, eax
0x1800a911f  jnz     short loc_1800A9161
0x1800a9121  call    cs:__imp_GetLastError
0x1800a9127  mov     ebx, eax
0x1800a9129  cmp     eax, 0EAh
0x1800a912e  jnz     loc_1800A91CC
0x1800a9134  mov     rcx, cs:PfSvcGlobals
0x1800a913b  mov     ebp, [rdi]
0x1800a913d  test    rcx, rcx
0x1800a9140  jz      short loc_1800A9148
0x1800a9142  mov     rcx, [rcx+58h]
0x1800a9146  jmp     short loc_1800A9151
0x1800a9148  call    cs:__imp_GetProcessHeap
0x1800a914e  mov     rcx, rax; hHeap
0x1800a9151  xor     edx, edx; dwFlags
0x1800a9153  mov     r8, rdi; lpMem
0x1800a9156  call    cs:__imp_HeapFree
0x1800a915c  jmp     loc_1800A90AD
0x1800a9161  cmp     dword ptr [rdi+4], 1
0x1800a9165  jnb     short loc_1800A916E
0x1800a9167  mov     ebx, 0Dh
0x1800a916c  jmp     short loc_1800A91CC
0x1800a916e  movzx   ebx, word ptr [rdi+14h]
0x1800a9172  shr     ebx, 1
0x1800a9174  lea     eax, ds:2[rbx*2]
0x1800a917b  cmp     eax, 200h
0x1800a9180  jbe     short loc_1800A9189
0x1800a9182  mov     ebx, 7Ah ; 'z'
0x1800a9187  jmp     short loc_1800A91CC
0x1800a9189  mov     edx, [rdi+10h]
0x1800a918c  mov     rcx, r15; void *
0x1800a918f  mov     r14d, ebx
0x1800a9192  add     rdx, rdi; Src
0x1800a9195  add     r14, r14
0x1800a9198  mov     r8, r14; Size
0x1800a919b  call    memcpy_0
0x1800a91a0  mov     eax, r13d
0x1800a91a3  test    ebx, ebx
0x1800a91a5  jz      short loc_1800A91BD
0x1800a91a7  mov     ecx, eax
0x1800a91a9  cmp     [r15+rcx*2], r13w
0x1800a91ae  jnz     short loc_1800A91B7
0x1800a91b0  mov     word ptr [r15+rcx*2], 5Fh ; '_'
0x1800a91b7  inc     eax
0x1800a91b9  cmp     eax, ebx
0x1800a91bb  jb      short loc_1800A91A7
0x1800a91bd  mov     [r14+r15], r13w
0x1800a91c2  mov     ebx, r13d
0x1800a91c5  jmp     short loc_1800A91CC
0x1800a91c7  mov     ebx, 8
0x1800a91cc  mov     rcx, cs:PfSvcGlobals
0x1800a91d3  test    rcx, rcx
0x1800a91d6  jz      short loc_1800A91DE
0x1800a91d8  mov     rcx, [rcx+58h]
0x1800a91dc  jmp     short loc_1800A91E7
0x1800a91de  call    cs:__imp_GetProcessHeap
0x1800a91e4  mov     rcx, rax; hHeap
0x1800a91e7  mov     r8, rsi; lpMem
0x1800a91ea  xor     edx, edx; dwFlags
0x1800a91ec  call    cs:__imp_HeapFree
0x1800a91f2  test    rdi, rdi
0x1800a91f5  jz      short loc_1800A921D
0x1800a91f7  mov     rcx, cs:PfSvcGlobals
0x1800a91fe  test    rcx, rcx
0x1800a9201  jz      short loc_1800A9209
0x1800a9203  mov     rcx, [rcx+58h]
0x1800a9207  jmp     short loc_1800A9212
0x1800a9209  call    cs:__imp_GetProcessHeap
0x1800a920f  mov     rcx, rax; hHeap
0x1800a9212  mov     r8, rdi; lpMem
0x1800a9215  xor     edx, edx; dwFlags
0x1800a9217  call    cs:__imp_HeapFree
0x1800a921d  mov     rcx, r12; hObject
0x1800a9220  call    cs:__imp_CloseHandle
0x1800a9226  mov     eax, ebx
0x1800a9228  add     rsp, 48h
0x1800a922c  pop     r15
0x1800a922e  pop     r14
0x1800a9230  pop     r13
0x1800a9232  pop     r12
0x1800a9234  pop     rdi
0x1800a9235  pop     rsi
0x1800a9236  pop     rbp
0x1800a9237  pop     rbx
0x1800a9238  retn
```
