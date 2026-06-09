# CVdsRawDiskLun::CleanDiskThread(void *)

- ea: `0x14000f600`
- end: `0x14000f91c`
- name: `?CleanDiskThread@CVdsRawDiskLun@@QEAAKPEAX@Z`
- size: `796`
- prototype: `__int64 __fastcall(CVdsRawDiskLun *this, CVdsAsyncObjectBase **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x14004d8f0`

## callees

- `0x14000d0f0`
- `0x14000f600`
- `0x14000f930`
- `0x14000f9b0`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f6a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f6a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f76a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f887`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f76a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f887`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x14000f75a`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x14000f7e9`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x14000f75a`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x14000f7e9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000f73d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000f818`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000f73d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000f818`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000f87d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000f87d`
- `vdsutil!OpenDevice` at `0x14000f658`
- `vdsutil!OpenDevice` at `0x14000f658`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x14000f8ca`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x14000f8ca`
- `vdsutil!?Signal@CVdsAsyncObjectBase@@QEAAXXZ` at `0x14000f8d4`
- `vdsutil!?Signal@CVdsAsyncObjectBase@@QEAAXXZ` at `0x14000f8d4`
- `vdsutil!VdsHeapAlloc` at `0x14000f6b7`
- `vdsutil!VdsHeapAlloc` at `0x14000f6b7`
- `vdsutil!VdsTraceEx` at `0x14000f673`
- `vdsutil!VdsTraceEx` at `0x14000f6f7`
- `vdsutil!VdsTraceEx` at `0x14000f78a`
- `vdsutil!VdsTraceEx` at `0x14000f89e`
- `vdsutil!VdsTraceEx` at `0x14000f673`
- `vdsutil!VdsTraceEx` at `0x14000f6f7`
- `vdsutil!VdsTraceEx` at `0x14000f78a`
- `vdsutil!VdsTraceEx` at `0x14000f89e`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000f640`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000f640`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000f8ef`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000f8ef`

## string_xrefs

- `0x14000f834`: `CRawDiskLun::CleanDiskThread, 5, error=%ld`
- `0x14000f632`: `CVdsRawDiskLun::CleanDiskThread()`
- `0x14000f892`: `CRawDiskLun::CleanDiskThread, 6, %ld`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsRawDiskLun::CleanDiskThread(CVdsRawDiskLun *this, CVdsAsyncObjectBase **a2)
{
  CVdsAsyncObjectBase **v2; // r15
  const void *v4; // rbx
  int v5; // eax
  __int64 LastError; // rdi
  DWORD v7; // r14d
  HANDLE ProcessHeap; // rax
  __int64 v9; // rax
  DWORD v10; // ecx
  unsigned int v11; // r13d
  unsigned int v12; // r15d
  BOOL v13; // eax
  LARGE_INTEGER v14; // rdi
  __int64 v15; // rax
  BOOL v16; // eax
  signed int v17; // ebx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-38h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-34h] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-30h] BYREF
  const void *v22; // [rsp+50h] [rbp-28h] BYREF
  _BYTE v23[32]; // [rsp+58h] [rbp-20h] BYREF

  v2 = a2;
  hFile = (HANDLE)-1LL;
  v4 = 0;
  v22 = 0;
  NumberOfBytesWritten = 0;
  BytesReturned = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v23, 0x5Eu, "CVdsRawDiskLun::CleanDiskThread()");
  v5 = OpenDevice(*((_QWORD *)this + 27), 3221225472LL, &hFile);
  LODWORD(LastError) = v5;
  if ( v5 )
  {
    VdsTraceEx(94, 0, "CRawDiskLun::Clean, 1, error=%ld", v5);
    if ( (int)LastError > 0 )
      LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_38;
  }
  v7 = 0x100000;
  while ( !v4 )
  {
    if ( v7 < 0x200 )
    {
      LODWORD(LastError) = -2147024882;
      VdsTraceEx(94, 0, "CRawDiskLun::Clean, 2, hr=%lX", -2147024882);
      goto LABEL_33;
    }
    ProcessHeap = GetProcessHeap();
    v9 = VdsHeapAlloc(ProcessHeap, 8, v7);
    CVdsHeapPtr<_MOUNTMGR_MOUNT_POINT>::operator=((__int64 *)&v22, v9);
    v4 = v22;
    v10 = v7 >> 1;
    if ( v22 )
      v10 = v7;
    v7 = v10;
  }
  v11 = 0x100000 / v7;
  v12 = 0x100000 / v7;
  v13 = 1;
  v14.QuadPart = 0;
  if ( 0x100000 / v7 )
  {
    while ( v13 )
    {
      v13 = WriteFile(hFile, v4, v7, &NumberOfBytesWritten, 0);
      if ( v13 )
      {
        v14.QuadPart += NumberOfBytesWritten;
        v13 = SetFilePointerEx(hFile, v14, 0, 0);
      }
      if ( !--v12 )
      {
        if ( v13 )
          goto LABEL_22;
        break;
      }
    }
    LastError = GetLastError();
    if ( v12 == v11 - 1 )
      VdsTraceEx(94, 0, "CRawDiskLun::Clean, 3, error=%ld", LastError);
    else
      VdsTraceEx(94, 0, "CRawDiskLun::Clean, 4, error=%ld", LastError);
    goto LABEL_19;
  }
LABEL_22:
  v15 = *((_QWORD *)this + 32) - *(_QWORD *)&GUID_DEVCLASS_SMRDISK.Data1;
  if ( !v15 )
    v15 = *((_QWORD *)this + 33) - *(_QWORD *)GUID_DEVCLASS_SMRDISK.Data4;
  if ( !v15 )
    goto LABEL_31;
  v16 = SetFilePointerEx(hFile, (LARGE_INTEGER)(*((_QWORD *)this + 20) - 0x100000LL), 0, 0);
  if ( !v16 )
    goto LABEL_29;
  v16 = 1;
  if ( !v11 )
  {
LABEL_31:
    LODWORD(LastError) = 0;
    goto LABEL_32;
  }
  do
  {
    if ( !v16 )
      break;
    v16 = WriteFile(hFile, v4, v7, &NumberOfBytesWritten, 0);
    --v11;
  }
  while ( v11 );
LABEL_29:
  if ( v16 )
    goto LABEL_31;
  LastError = GetLastError();
  VdsTraceEx(94, 0, "CRawDiskLun::CleanDiskThread, 5, error=%ld", LastError);
LABEL_19:
  if ( (int)LastError > 0 )
    LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
LABEL_32:
  v2 = a2;
LABEL_33:
  if ( !DeviceIoControl(hFile, 0x70140u, 0, 0, 0, 0, &BytesReturned, 0) )
  {
    v17 = GetLastError();
    VdsTraceEx(94, 0, "CRawDiskLun::CleanDiskThread, 6, %ld", v17);
    if ( !(_DWORD)LastError )
    {
      if ( v17 > 0 )
        LODWORD(LastError) = (unsigned __int16)v17 | 0x80070000;
      else
        LODWORD(LastError) = v17;
    }
  }
LABEL_38:
  CVdsAsyncObjectBase::SetCompletionStatus(v2[1], LastError, (((int)LastError >> 31) & 0xFFFFFF9C) + 100);
  CVdsAsyncObjectBase::Signal(v2[1]);
  (*(void (__fastcall **)(CVdsAsyncObjectBase *))(*(_QWORD *)v2[1] + 16LL))(v2[1]);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v23);
  CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&v22);
  CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(&hFile);
  return 0;
}

```

## disassembly

```asm
0x14000f600  mov     [rsp-40h+arg_8], rdx
0x14000f605  push    rbp
0x14000f606  push    rbx
0x14000f607  push    rsi
0x14000f608  push    rdi
0x14000f609  push    r12
0x14000f60b  push    r13
0x14000f60d  push    r14
0x14000f60f  push    r15
0x14000f611  mov     rbp, rsp
0x14000f614  sub     rsp, 78h
0x14000f618  mov     r15, rdx
0x14000f61b  mov     r12, rcx
0x14000f61e  mov     [rbp+hFile], 0FFFFFFFFFFFFFFFFh
0x14000f626  xor     ebx, ebx
0x14000f628  mov     [rbp+var_28], rbx
0x14000f62c  mov     [rbp+NumberOfBytesWritten], ebx
0x14000f62f  mov     [rbp+BytesReturned], ebx
0x14000f632  lea     r8, aCvdsrawdisklun_41; "CVdsRawDiskLun::CleanDiskThread()"
0x14000f639  lea     edx, [rbx+5Eh]
0x14000f63c  lea     rcx, [rbp+var_20]
0x14000f640  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000f646  nop
0x14000f647  lea     r8, [rbp+hFile]
0x14000f64b  mov     edx, 0C0000000h
0x14000f650  mov     rcx, [r12+0D8h]
0x14000f658  call    cs:__imp_OpenDevice
0x14000f65e  mov     edi, eax
0x14000f660  test    eax, eax
0x14000f662  jz      short loc_14000F68F
0x14000f664  mov     r9d, eax
0x14000f667  lea     r8, aCrawdisklunCle_2; "CRawDiskLun::Clean, 1, error=%ld"
0x14000f66e  xor     edx, edx
0x14000f670  lea     ecx, [rbx+5Eh]
0x14000f673  call    cs:__imp_VdsTraceEx
0x14000f679  test    edi, edi
0x14000f67b  jle     loc_14000F8B5
0x14000f681  movzx   edi, di
0x14000f684  or      edi, 80070000h
0x14000f68a  jmp     loc_14000F8B5
0x14000f68f  mov     r14d, 100000h
0x14000f695  mov     esi, 80070000h
0x14000f69a  test    rbx, rbx
0x14000f69d  jnz     short loc_14000F702
0x14000f69f  cmp     r14d, 200h
0x14000f6a6  jb      short loc_14000F6E3
0x14000f6a8  call    cs:__imp_GetProcessHeap
0x14000f6ae  mov     rcx, rax
0x14000f6b1  mov     r8d, r14d
0x14000f6b4  lea     edx, [rbx+8]
0x14000f6b7  call    cs:__imp_VdsHeapAlloc
0x14000f6bd  mov     rdx, rax
0x14000f6c0  lea     rcx, [rbp+var_28]
0x14000f6c4  call    ??4?$CVdsHeapPtr@U_MOUNTMGR_MOUNT_POINT@@@@QEAAPEAU_MOUNTMGR_MOUNT_POINT@@PEAU1@@Z; CVdsHeapPtr<_MOUNTMGR_MOUNT_POINT>::operator=(_MOUNTMGR_MOUNT_POINT *)
0x14000f6c9  mov     rbx, [rbp+var_28]
0x14000f6cd  test    rbx, rbx
0x14000f6d0  setz    al
0x14000f6d3  mov     ecx, r14d
0x14000f6d6  shr     ecx, 1
0x14000f6d8  test    al, al
0x14000f6da  cmovz   ecx, r14d
0x14000f6de  mov     r14d, ecx
0x14000f6e1  jmp     short loc_14000F695
0x14000f6e3  mov     edi, 8007000Eh
0x14000f6e8  mov     r9d, edi
0x14000f6eb  lea     r8, aCrawdisklunCle; "CRawDiskLun::Clean, 2, hr=%lX"
0x14000f6f2  xor     edx, edx
0x14000f6f4  lea     ecx, [rdx+5Eh]
0x14000f6f7  call    cs:__imp_VdsTraceEx
0x14000f6fd  jmp     loc_14000F84B
0x14000f702  xor     edx, edx
0x14000f704  mov     eax, 100000h
0x14000f709  div     r14d
0x14000f70c  mov     r13d, eax
0x14000f70f  mov     r15d, eax
0x14000f712  mov     eax, 1
0x14000f717  xor     edi, edi
0x14000f719  test    r15d, r15d
0x14000f71c  jz      loc_14000F7AB
0x14000f722  test    eax, eax
0x14000f724  jz      short loc_14000F76A
0x14000f726  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x14000f72f  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14000f733  mov     r8d, r14d; nNumberOfBytesToWrite
0x14000f736  mov     rdx, rbx; lpBuffer
0x14000f739  mov     rcx, [rbp+hFile]; hFile
0x14000f73d  call    cs:__imp_WriteFile
0x14000f743  test    eax, eax
0x14000f745  jz      short loc_14000F760
0x14000f747  mov     eax, [rbp+NumberOfBytesWritten]
0x14000f74a  add     rdi, rax
0x14000f74d  xor     r9d, r9d; dwMoveMethod
0x14000f750  xor     r8d, r8d; lpNewFilePointer
0x14000f753  mov     rdx, rdi; liDistanceToMove
0x14000f756  mov     rcx, [rbp+hFile]; hFile
0x14000f75a  call    cs:__imp_SetFilePointerEx
0x14000f760  add     r15d, 0FFFFFFFFh
0x14000f764  jnz     short loc_14000F722
0x14000f766  test    eax, eax
0x14000f768  jnz     short loc_14000F7AB
0x14000f76a  call    cs:__imp_GetLastError
0x14000f770  mov     edi, eax
0x14000f772  lea     eax, [r13-1]
0x14000f776  mov     r9d, edi
0x14000f779  xor     edx, edx
0x14000f77b  lea     ecx, [rdx+5Eh]
0x14000f77e  cmp     r15d, eax
0x14000f781  jnz     short loc_14000F7A2
0x14000f783  lea     r8, aCrawdisklunCle_3; "CRawDiskLun::Clean, 3, error=%ld"
0x14000f78a  call    cs:__imp_VdsTraceEx
0x14000f790  test    edi, edi
0x14000f792  jle     loc_14000F847
0x14000f798  movzx   edi, di
0x14000f79b  or      edi, esi
0x14000f79d  jmp     loc_14000F847
0x14000f7a2  lea     r8, aCrawdisklunCle_1; "CRawDiskLun::Clean, 4, error=%ld"
0x14000f7a9  jmp     short loc_14000F78A
0x14000f7ab  mov     rax, [r12+100h]
0x14000f7b3  sub     rax, qword ptr cs:GUID_DEVCLASS_SMRDISK.Data1
0x14000f7ba  jnz     short loc_14000F7CB
0x14000f7bc  mov     rax, [r12+108h]
0x14000f7c4  sub     rax, qword ptr cs:GUID_DEVCLASS_SMRDISK.Data4
0x14000f7cb  test    rax, rax
0x14000f7ce  jz      short loc_14000F845
0x14000f7d0  mov     rdx, [r12+0A0h]
0x14000f7d8  sub     rdx, 100000h; liDistanceToMove
0x14000f7df  xor     r9d, r9d; dwMoveMethod
0x14000f7e2  xor     r8d, r8d; lpNewFilePointer
0x14000f7e5  mov     rcx, [rbp+hFile]; hFile
0x14000f7e9  call    cs:__imp_SetFilePointerEx
0x14000f7ef  test    eax, eax
0x14000f7f1  jz      short loc_14000F824
0x14000f7f3  mov     eax, 1
0x14000f7f8  test    r13d, r13d
0x14000f7fb  jz      short loc_14000F845
0x14000f7fd  test    eax, eax
0x14000f7ff  jz      short loc_14000F824
0x14000f801  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x14000f80a  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14000f80e  mov     r8d, r14d; nNumberOfBytesToWrite
0x14000f811  mov     rdx, rbx; lpBuffer
0x14000f814  mov     rcx, [rbp+hFile]; hFile
0x14000f818  call    cs:__imp_WriteFile
0x14000f81e  add     r13d, 0FFFFFFFFh
0x14000f822  jnz     short loc_14000F7FD
0x14000f824  cmp     eax, 1
0x14000f827  jz      short loc_14000F845
0x14000f829  call    cs:__imp_GetLastError
0x14000f82f  mov     edi, eax
0x14000f831  mov     r9d, eax
0x14000f834  lea     r8, aCrawdisklunCle_5; "CRawDiskLun::CleanDiskThread, 5, error="...
0x14000f83b  xor     edx, edx
0x14000f83d  lea     ecx, [rdx+5Eh]
0x14000f840  jmp     loc_14000F78A
0x14000f845  xor     edi, edi
0x14000f847  mov     r15, [rbp+arg_8]
0x14000f84b  mov     [rsp+78h+var_40], 0; lpOverlapped
0x14000f854  lea     rax, [rbp+BytesReturned]
0x14000f858  mov     [rsp+78h+lpBytesReturned], rax; lpBytesReturned
0x14000f85d  mov     [rsp+78h+nOutBufferSize], 0; nOutBufferSize
0x14000f865  mov     [rsp+78h+lpOverlapped], 0; lpOutBuffer
0x14000f86e  xor     r9d, r9d; nInBufferSize
0x14000f871  xor     r8d, r8d; lpInBuffer
0x14000f874  mov     edx, 70140h; dwIoControlCode
0x14000f879  mov     rcx, [rbp+hFile]; hDevice
0x14000f87d  call    cs:__imp_DeviceIoControl
0x14000f883  test    eax, eax
0x14000f885  jnz     short loc_14000F8B5
0x14000f887  call    cs:__imp_GetLastError
0x14000f88d  mov     ebx, eax
0x14000f88f  mov     r9d, eax
0x14000f892  lea     r8, aCrawdisklunCle_0; "CRawDiskLun::CleanDiskThread, 6, %ld"
0x14000f899  xor     edx, edx
0x14000f89b  lea     ecx, [rdx+5Eh]
0x14000f89e  call    cs:__imp_VdsTraceEx
0x14000f8a4  test    edi, edi
0x14000f8a6  jnz     short loc_14000F8B5
0x14000f8a8  test    ebx, ebx
0x14000f8aa  jg      short loc_14000F8B0
0x14000f8ac  mov     edi, ebx
0x14000f8ae  jmp     short loc_14000F8B5
0x14000f8b0  movzx   edi, bx
0x14000f8b3  or      edi, esi
0x14000f8b5  mov     r8d, edi
0x14000f8b8  sar     r8d, 1Fh
0x14000f8bc  and     r8d, 0FFFFFF9Ch
0x14000f8c0  add     r8d, 64h ; 'd'
0x14000f8c4  mov     edx, edi
0x14000f8c6  mov     rcx, [r15+8]
0x14000f8ca  call    cs:__imp_?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z; CVdsAsyncObjectBase::SetCompletionStatus(long,ulong)
0x14000f8d0  mov     rcx, [r15+8]
0x14000f8d4  call    cs:__imp_?Signal@CVdsAsyncObjectBase@@QEAAXXZ; CVdsAsyncObjectBase::Signal(void)
0x14000f8da  mov     rcx, [r15+8]
0x14000f8de  mov     rax, [rcx]
0x14000f8e1  mov     rax, [rax+10h]
0x14000f8e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f8ea  nop
0x14000f8eb  lea     rcx, [rbp+var_20]
0x14000f8ef  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000f8f5  nop
0x14000f8f6  lea     rcx, [rbp+var_28]
0x14000f8fa  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x14000f8ff  nop
0x14000f900  lea     rcx, [rbp+hFile]
0x14000f904  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x14000f909  xor     eax, eax
0x14000f90b  add     rsp, 78h
0x14000f90f  pop     r15
0x14000f911  pop     r14
0x14000f913  pop     r13
0x14000f915  pop     r12
0x14000f917  pop     rdi
0x14000f918  pop     rsi
0x14000f919  pop     rbx
0x14000f91a  pop     rbp
0x14000f91b  retn
```
