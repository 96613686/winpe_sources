# DavTerminateWorkerThreads

- ea: `0x18000cc84`
- end: `0x18000ce06`
- name: `DavTerminateWorkerThreads`
- size: `386`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180025bf8`

## callees

- `0x18000b7dc`
- `0x18000cc84`
- `0x18000d7ac`

## import_xrefs

- `ntdll!NtClose` at `0x18000cdc8`
- `ntdll!NtClose` at `0x18000cdc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd06`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000ccfc`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000ccfc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000cdbf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000cdbf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000cd60`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000cd60`
- `KERNEL32!LocalFree` at `0x18000cde3`
- `KERNEL32!LocalFree` at `0x18000cde3`

## pseudocode

```c
__int64 __fastcall DavTerminateWorkerThreads(__int64 a1, __int64 a2, __int64 a3)
{
  _DWORD *v3; // rcx
  DWORD LastError; // ebx
  _QWORD *v5; // r10
  __int64 i; // rbx
  void *v7; // rdi
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-28h] BYREF

  v3 = DavThreadConstellation;
  if ( !DavThreadConstellation )
    goto LABEL_12;
  *((_BYTE *)DavThreadConstellation + 16) = 1;
  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( DavReflectorHandle )
  {
    LastError = 0;
    if ( *((_QWORD *)DavReflectorHandle + 1) != -1 )
    {
      if ( !DeviceIoControl(*((HANDLE *)DavReflectorHandle + 1), 0x140378u, 0, 0, 0, 0, 0, &Overlapped) )
        LastError = GetLastError();
      v3 = DavThreadConstellation;
    }
    if ( !LastError )
      goto LABEL_12;
  }
  else
  {
    LastError = 87;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_186e50dd2e3d3df6c9407dc12bb7d723_Traceguids, LastError);
    v3 = DavThreadConstellation;
LABEL_12:
    v5 = WPP_GLOBAL_Control;
  }
  if ( DavOutstandingWorkerRequests )
  {
    do
      Sleep(0xFAu);
    while ( DavOutstandingWorkerRequests );
    v3 = DavThreadConstellation;
    v5 = WPP_GLOBAL_Control;
  }
  if ( v3 )
  {
    for ( i = 0; (unsigned int)i < v3[2]; i = (unsigned int)(i + 1) )
    {
      v7 = *(void **)&v3[12 * i + 8];
      if ( v7 )
      {
        if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 2) != 0 )
          WPP_SF_Dq(v5[2], a2, a3, (unsigned int)v3[12 * i + 10], v7);
        WaitForSingleObject(v7, 0xFFFFFFFF);
        NtClose(v7);
        v3 = DavThreadConstellation;
        v5 = WPP_GLOBAL_Control;
      }
    }
    LocalFree(v3);
    DavThreadConstellation = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000cc84  mov     [rsp+arg_0], rbx
0x18000cc89  mov     [rsp+arg_8], rbp
0x18000cc8e  push    rdi
0x18000cc8f  sub     rsp, 60h
0x18000cc93  mov     rcx, cs:DavThreadConstellation
0x18000cc9a  lea     rbp, WPP_GLOBAL_Control
0x18000cca1  test    rcx, rcx
0x18000cca4  jz      loc_18000CD4B
0x18000ccaa  xorps   xmm0, xmm0
0x18000ccad  mov     byte ptr [rcx+10h], 1
0x18000ccb1  mov     rax, cs:DavReflectorHandle
0x18000ccb8  movups  xmmword ptr [rsp+68h+Overlapped.Internal], xmm0
0x18000ccbd  movups  xmmword ptr [rsp+68h+Overlapped.10h], xmm0
0x18000ccc2  test    rax, rax
0x18000ccc5  jnz     short loc_18000CCCC
0x18000ccc7  lea     ebx, [rax+57h]
0x18000ccca  jmp     short loc_18000CD19
0x18000cccc  xor     ebx, ebx
0x18000ccce  cmp     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x18000ccd3  jz      short loc_18000CD15
0x18000ccd5  lea     rcx, [rsp+68h+Overlapped]
0x18000ccda  xor     r9d, r9d; nInBufferSize
0x18000ccdd  mov     [rsp+68h+lpOverlapped], rcx; lpOverlapped
0x18000cce2  xor     r8d, r8d; lpInBuffer
0x18000cce5  mov     rcx, [rax+8]; hDevice
0x18000cce9  mov     edx, 140378h; dwIoControlCode
0x18000ccee  mov     [rsp+68h+lpBytesReturned], rbx; lpBytesReturned
0x18000ccf3  mov     [rsp+68h+nOutBufferSize], ebx; nOutBufferSize
0x18000ccf7  mov     [rsp+68h+lpOutBuffer], rbx; lpOutBuffer
0x18000ccfc  call    cs:__imp_DeviceIoControl
0x18000cd02  test    eax, eax
0x18000cd04  jnz     short loc_18000CD0E
0x18000cd06  call    cs:__imp_GetLastError
0x18000cd0c  mov     ebx, eax
0x18000cd0e  mov     rcx, cs:DavThreadConstellation
0x18000cd15  test    ebx, ebx
0x18000cd17  jz      short loc_18000CD4B
0x18000cd19  mov     r10, cs:WPP_GLOBAL_Control
0x18000cd20  cmp     r10, rbp
0x18000cd23  jz      short loc_18000CD52
0x18000cd25  test    byte ptr [r10+1Ch], 1
0x18000cd2a  jz      short loc_18000CD52
0x18000cd2c  mov     rcx, [r10+10h]
0x18000cd30  lea     r8, WPP_186e50dd2e3d3df6c9407dc12bb7d723_Traceguids
0x18000cd37  mov     edx, 0Fh
0x18000cd3c  mov     r9d, ebx
0x18000cd3f  call    WPP_SF_d
0x18000cd44  mov     rcx, cs:DavThreadConstellation
0x18000cd4b  mov     r10, cs:WPP_GLOBAL_Control
0x18000cd52  cmp     cs:DavOutstandingWorkerRequests, 0
0x18000cd59  jz      short loc_18000CD7D
0x18000cd5b  mov     ecx, 0FAh; dwMilliseconds
0x18000cd60  call    cs:__imp_Sleep
0x18000cd66  cmp     cs:DavOutstandingWorkerRequests, 0
0x18000cd6d  jnz     short loc_18000CD5B
0x18000cd6f  mov     rcx, cs:DavThreadConstellation
0x18000cd76  mov     r10, cs:WPP_GLOBAL_Control
0x18000cd7d  test    rcx, rcx
0x18000cd80  jz      short loc_18000CDF4
0x18000cd82  xor     ebx, ebx
0x18000cd84  cmp     [rcx+8], ebx
0x18000cd87  jbe     short loc_18000CDE3
0x18000cd89  lea     r9, [rbx+rbx*2]
0x18000cd8d  add     r9, r9
0x18000cd90  mov     rdi, [rcx+r9*8+20h]
0x18000cd95  test    rdi, rdi
0x18000cd98  jz      short loc_18000CDDC
0x18000cd9a  cmp     r10, rbp
0x18000cd9d  jz      short loc_18000CDB9
0x18000cd9f  test    byte ptr [r10+1Ch], 2
0x18000cda4  jz      short loc_18000CDB9
0x18000cda6  mov     r9d, [rcx+r9*8+28h]
0x18000cdab  mov     rcx, [r10+10h]
0x18000cdaf  mov     [rsp+68h+lpOutBuffer], rdi
0x18000cdb4  call    WPP_SF_Dq
0x18000cdb9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000cdbc  mov     rcx, rdi; hHandle
0x18000cdbf  call    cs:__imp_WaitForSingleObject
0x18000cdc5  mov     rcx, rdi; Handle
0x18000cdc8  call    cs:__imp_NtClose
0x18000cdce  mov     rcx, cs:DavThreadConstellation; hMem
0x18000cdd5  mov     r10, cs:WPP_GLOBAL_Control
0x18000cddc  inc     ebx
0x18000cdde  cmp     ebx, [rcx+8]
0x18000cde1  jb      short loc_18000CD89
0x18000cde3  call    cs:__imp_LocalFree
0x18000cde9  mov     cs:DavThreadConstellation, 0
0x18000cdf4  mov     rbx, [rsp+68h+arg_0]
0x18000cdf9  xor     eax, eax
0x18000cdfb  mov     rbp, [rsp+68h+arg_8]
0x18000ce00  add     rsp, 60h
0x18000ce04  pop     rdi
0x18000ce05  retn
```
