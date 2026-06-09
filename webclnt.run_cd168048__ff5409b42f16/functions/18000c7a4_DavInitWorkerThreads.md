# DavInitWorkerThreads

- ea: `0x18000c7a4`
- end: `0x18000c9fd`
- name: `DavInitWorkerThreads`
- size: `601`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180025f10`

## callees

- `0x18000b7dc`
- `0x18000bc5c`
- `0x18000c7a4`
- `0x18000d748`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c8d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c97b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c8d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c97b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000c8cc`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000c8cc`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c96c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c96c`
- `KERNEL32!LocalFree` at `0x18000c91d`
- `KERNEL32!LocalFree` at `0x18000c91d`
- `KERNEL32!LocalAlloc` at `0x18000c7d6`
- `KERNEL32!LocalAlloc` at `0x18000c7d6`

## pseudocode

```c
__int64 __fastcall DavInitWorkerThreads(unsigned int a1, int a2)
{
  unsigned int v3; // eax
  _QWORD *v5; // rax
  char *v6; // r8
  DWORD LastError; // eax
  DWORD v8; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rsi
  char *v12; // rbx
  HANDLE Thread; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  DWORD v16; // eax
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-48h] BYREF

  DavOutstandingWorkerRequests = 0;
  v3 = 48 * a2 + 24;
  if ( v3 < 0x48 )
    return 534;
  v5 = LocalAlloc(0x40u, v3);
  DavThreadConstellation = v5;
  v6 = (char *)v5;
  if ( !v5 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_186e50dd2e3d3df6c9407dc12bb7d723_Traceguids, LastError);
    return v8;
  }
  *((_BYTE *)v5 + 16) = 0;
  *((_DWORD *)v5 + 3) = a1;
  *((_DWORD *)v5 + 2) = a2;
  *v5 = DavRedirDeviceHandle;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_186e50dd2e3d3df6c9407dc12bb7d723_Traceguids, v5);
    v6 = (char *)DavThreadConstellation;
    v10 = WPP_GLOBAL_Control;
  }
  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( !DavReflectorHandle )
  {
    v8 = 87;
LABEL_17:
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
    {
      WPP_SF_d(v10[2], 12, WPP_186e50dd2e3d3df6c9407dc12bb7d723_Traceguids, v8);
      v6 = (char *)DavThreadConstellation;
    }
    LocalFree(v6);
    DavThreadConstellation = 0;
    return v8;
  }
  v8 = 0;
  if ( *((_QWORD *)DavReflectorHandle + 1) != -1 )
  {
    if ( !DeviceIoControl(*((HANDLE *)DavReflectorHandle + 1), 0x140394u, 0, 0, 0, 0, 0, &Overlapped) )
      v8 = GetLastError();
    v10 = WPP_GLOBAL_Control;
    v6 = (char *)DavThreadConstellation;
  }
  if ( v8 )
    goto LABEL_17;
  v11 = 0;
  if ( a1 )
  {
    while ( 1 )
    {
      v12 = &v6[48 * v11];
      *((_QWORD *)v12 + 3) = v6;
      Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)DavWorkerThread, v12 + 24, 0, (LPDWORD)v12 + 10);
      *((_QWORD *)v12 + 4) = Thread;
      if ( Thread )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_DDq(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, (unsigned int)v11, *((_DWORD *)v12 + 10), Thread);
      }
      else
      {
        v16 = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_186e50dd2e3d3df6c9407dc12bb7d723_Traceguids, v16);
      }
      v11 = (unsigned int)(v11 + 1);
      if ( (unsigned int)v11 >= a1 )
        break;
      v6 = (char *)DavThreadConstellation;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000c7a4  push    rbx
0x18000c7a6  push    rbp
0x18000c7a7  push    rsi
0x18000c7a8  push    rdi
0x18000c7a9  push    r14
0x18000c7ab  sub     rsp, 60h
0x18000c7af  lea     eax, [rdx+rdx*2]
0x18000c7b2  mov     cs:DavOutstandingWorkerRequests, 0
0x18000c7bc  shl     eax, 4
0x18000c7bf  mov     ebx, edx
0x18000c7c1  add     eax, 18h
0x18000c7c4  mov     ebp, ecx
0x18000c7c6  cmp     eax, 48h ; 'H'
0x18000c7c9  jb      loc_18000C9ED
0x18000c7cf  mov     edx, eax; uBytes
0x18000c7d1  mov     ecx, 40h ; '@'; uFlags
0x18000c7d6  call    cs:__imp_LocalAlloc
0x18000c7dc  mov     cs:DavThreadConstellation, rax
0x18000c7e3  mov     r8, rax
0x18000c7e6  test    rax, rax
0x18000c7e9  jnz     short loc_18000C82B
0x18000c7eb  call    cs:__imp_GetLastError
0x18000c7f1  mov     ebx, eax
0x18000c7f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7fa  lea     rdi, WPP_GLOBAL_Control
0x18000c801  cmp     rcx, rdi
0x18000c804  jz      short loc_18000C824
0x18000c806  test    byte ptr [rcx+1Ch], 1
0x18000c80a  jz      short loc_18000C824
0x18000c80c  mov     rcx, [rcx+10h]
0x18000c810  lea     r8, WPP_186e50dd2e3d3df6c9407dc12bb7d723_Traceguids
0x18000c817  mov     edx, 0Ah
0x18000c81c  mov     r9d, eax
0x18000c81f  call    WPP_SF_d
0x18000c824  mov     eax, ebx
0x18000c826  jmp     loc_18000C9F2
0x18000c82b  mov     byte ptr [rax+10h], 0
0x18000c82f  mov     [rax+0Ch], ebp
0x18000c832  mov     [rax+8], ebx
0x18000c835  mov     rax, cs:DavRedirDeviceHandle
0x18000c83c  mov     [r8], rax
0x18000c83f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c846  lea     rdi, WPP_GLOBAL_Control
0x18000c84d  cmp     rcx, rdi
0x18000c850  jz      short loc_18000C87E
0x18000c852  test    byte ptr [rcx+1Ch], 2
0x18000c856  jz      short loc_18000C87E
0x18000c858  mov     rcx, [rcx+10h]
0x18000c85c  mov     r9, r8
0x18000c85f  lea     r8, WPP_186e50dd2e3d3df6c9407dc12bb7d723_Traceguids
0x18000c866  mov     edx, 0Bh
0x18000c86b  call    WPP_SF_q
0x18000c870  mov     r8, cs:DavThreadConstellation
0x18000c877  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c87e  mov     rax, cs:DavReflectorHandle
0x18000c885  xorps   xmm0, xmm0
0x18000c888  movups  xmmword ptr [rsp+88h+Overlapped.Internal], xmm0
0x18000c88d  movups  xmmword ptr [rsp+88h+Overlapped.10h], xmm0
0x18000c892  test    rax, rax
0x18000c895  jnz     short loc_18000C89C
0x18000c897  lea     ebx, [rax+57h]
0x18000c89a  jmp     short loc_18000C8F0
0x18000c89c  xor     ebx, ebx
0x18000c89e  cmp     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x18000c8a3  jz      short loc_18000C8EC
0x18000c8a5  lea     rcx, [rsp+88h+Overlapped]
0x18000c8aa  xor     r9d, r9d; nInBufferSize
0x18000c8ad  mov     [rsp+88h+lpOverlapped], rcx; lpOverlapped
0x18000c8b2  xor     r8d, r8d; lpInBuffer
0x18000c8b5  mov     rcx, [rax+8]; hDevice
0x18000c8b9  mov     edx, 140394h; dwIoControlCode
0x18000c8be  mov     [rsp+88h+lpBytesReturned], rbx; lpBytesReturned
0x18000c8c3  mov     [rsp+88h+nOutBufferSize], ebx; nOutBufferSize
0x18000c8c7  mov     [rsp+88h+lpOutBuffer], rbx; lpOutBuffer
0x18000c8cc  call    cs:__imp_DeviceIoControl
0x18000c8d2  test    eax, eax
0x18000c8d4  jnz     short loc_18000C8DE
0x18000c8d6  call    cs:__imp_GetLastError
0x18000c8dc  mov     ebx, eax
0x18000c8de  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c8e5  mov     r8, cs:DavThreadConstellation
0x18000c8ec  test    ebx, ebx
0x18000c8ee  jz      short loc_18000C933
0x18000c8f0  cmp     rcx, rdi
0x18000c8f3  jz      short loc_18000C91A
0x18000c8f5  test    byte ptr [rcx+1Ch], 1
0x18000c8f9  jz      short loc_18000C91A
0x18000c8fb  mov     rcx, [rcx+10h]
0x18000c8ff  lea     r8, WPP_186e50dd2e3d3df6c9407dc12bb7d723_Traceguids
0x18000c906  mov     edx, 0Ch
0x18000c90b  mov     r9d, ebx
0x18000c90e  call    WPP_SF_d
0x18000c913  mov     r8, cs:DavThreadConstellation
0x18000c91a  mov     rcx, r8; hMem
0x18000c91d  call    cs:__imp_LocalFree
0x18000c923  mov     cs:DavThreadConstellation, 0
0x18000c92e  jmp     loc_18000C824
0x18000c933  xor     esi, esi
0x18000c935  test    ebp, ebp
0x18000c937  jz      loc_18000C9E9
0x18000c93d  lea     rbx, [rsi+rsi*2]
0x18000c941  xor     edx, edx; dwStackSize
0x18000c943  shl     rbx, 4
0x18000c947  xor     ecx, ecx; lpThreadAttributes
0x18000c949  add     rbx, r8
0x18000c94c  mov     [rbx+18h], r8
0x18000c950  lea     r14, [rbx+28h]
0x18000c954  mov     qword ptr [rsp+88h+nOutBufferSize], r14; lpThreadId
0x18000c959  lea     r9, [rbx+18h]; lpParameter
0x18000c95d  lea     r8, DavWorkerThread; lpStartAddress
0x18000c964  mov     dword ptr [rsp+88h+lpOutBuffer], 0; dwCreationFlags
0x18000c96c  call    cs:__imp_CreateThread
0x18000c972  mov     [rbx+20h], rax
0x18000c976  test    rax, rax
0x18000c979  jnz     short loc_18000C9AD
0x18000c97b  call    cs:__imp_GetLastError
0x18000c981  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c988  cmp     rcx, rdi
0x18000c98b  jz      short loc_18000C9D7
0x18000c98d  test    byte ptr [rcx+1Ch], 1
0x18000c991  jz      short loc_18000C9D7
0x18000c993  mov     rcx, [rcx+10h]
0x18000c997  lea     r8, WPP_186e50dd2e3d3df6c9407dc12bb7d723_Traceguids
0x18000c99e  mov     edx, 0Dh
0x18000c9a3  mov     r9d, eax
0x18000c9a6  call    WPP_SF_d
0x18000c9ab  jmp     short loc_18000C9D7
0x18000c9ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9b4  cmp     rcx, rdi
0x18000c9b7  jz      short loc_18000C9D7
0x18000c9b9  test    byte ptr [rcx+1Ch], 2
0x18000c9bd  jz      short loc_18000C9D7
0x18000c9bf  mov     rcx, [rcx+10h]
0x18000c9c3  mov     r9d, esi
0x18000c9c6  mov     qword ptr [rsp+88h+nOutBufferSize], rax
0x18000c9cb  mov     eax, [r14]
0x18000c9ce  mov     dword ptr [rsp+88h+lpOutBuffer], eax
0x18000c9d2  call    WPP_SF_DDq
0x18000c9d7  inc     esi
0x18000c9d9  cmp     esi, ebp
0x18000c9db  jnb     short loc_18000C9E9
0x18000c9dd  mov     r8, cs:DavThreadConstellation
0x18000c9e4  jmp     loc_18000C93D
0x18000c9e9  xor     eax, eax
0x18000c9eb  jmp     short loc_18000C9F2
0x18000c9ed  mov     eax, 216h
0x18000c9f2  add     rsp, 60h
0x18000c9f6  pop     r14
0x18000c9f8  pop     rdi
0x18000c9f9  pop     rsi
0x18000c9fa  pop     rbp
0x18000c9fb  pop     rbx
0x18000c9fc  retn
```
