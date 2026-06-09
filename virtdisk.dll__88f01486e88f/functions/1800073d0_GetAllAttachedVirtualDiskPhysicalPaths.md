# GetAllAttachedVirtualDiskPhysicalPaths

- ea: `0x1800073d0`
- end: `0x1800076c6`
- name: `GetAllAttachedVirtualDiskPhysicalPaths`
- size: `758`
- prototype: `DWORD __stdcall(PULONG PathsBufferSizeInBytes, PWSTR PathsBuffer)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180003d30`
- `0x180004110`
- `0x1800063a8`
- `0x180006fac`
- `0x1800073d0`
- `0x18000ba11`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007527`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007527`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000753c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000753c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000764c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000764c`
- `ntdll!RtlFreeHeap` at `0x1800075b6`
- `ntdll!RtlFreeHeap` at `0x180007630`
- `ntdll!RtlFreeHeap` at `0x18000766f`
- `ntdll!RtlFreeHeap` at `0x1800075b6`
- `ntdll!RtlFreeHeap` at `0x180007630`
- `ntdll!RtlFreeHeap` at `0x18000766f`
- `ntdll!RtlAllocateHeap` at `0x1800074db`
- `ntdll!RtlAllocateHeap` at `0x1800075d4`
- `ntdll!RtlAllocateHeap` at `0x1800074db`
- `ntdll!RtlAllocateHeap` at `0x1800075d4`

## pseudocode

```c
DWORD __stdcall GetAllAttachedVirtualDiskPhysicalPaths(PULONG PathsBufferSizeInBytes, PWSTR PathsBuffer)
{
  WCHAR *v2; // r12
  __int64 FileW; // r14
  DWORD LastError; // ebx
  unsigned int *Heap; // r15
  __int64 v8; // rdi
  DWORD VirtualDiskShimForFile; // eax
  DWORD v10; // eax
  LPCWSTR lpFileName; // [rsp+40h] [rbp-20h] BYREF
  int v13; // [rsp+48h] [rbp-18h] BYREF
  GUID v14; // [rsp+4Ch] [rbp-14h]
  int InBuffer; // [rsp+A0h] [rbp+40h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+B0h] [rbp+50h] BYREF
  HANDLE hObject; // [rsp+B8h] [rbp+58h] BYREF

  v2 = 0;
  InBuffer = 0;
  lpFileName = 0;
  NumberOfBytesTransferred = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_6afab5048b663292b11c40fad9d08467_Traceguids);
  }
  FileW = -1;
  hObject = (HANDLE)-1LL;
  if ( !PathsBufferSizeInBytes || !PathsBuffer && *PathsBufferSizeInBytes )
  {
    LastError = 87;
LABEL_7:
    *PathsBufferSizeInBytes = 10;
    goto LABEL_32;
  }
  if ( *PathsBufferSizeInBytes < 2 )
  {
    LastError = 122;
    goto LABEL_7;
  }
  v13 = 2;
  Heap = 0;
  v14 = VIRTUAL_STORAGE_TYPE_VENDOR_MICROSOFT;
  LODWORD(v8) = 10;
  VirtualDiskShimForFile = FindVirtualDiskShimForFile(0, 1, (void **)&lpFileName, (__int64)&v13, (__int64 *)&hObject);
  v2 = (WCHAR *)lpFileName;
  LastError = VirtualDiskShimForFile;
  FileW = (__int64)hObject;
  if ( VirtualDiskShimForFile )
  {
LABEL_30:
    *PathsBufferSizeInBytes = v8;
    if ( !Heap )
      goto LABEL_32;
    goto LABEL_31;
  }
  if ( hObject != (HANDLE)-1LL )
  {
    CloseHandle(hObject);
    FileW = -1;
  }
  Heap = (unsigned int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0xAu);
  if ( !Heap )
  {
LABEL_16:
    LastError = 14;
    *PathsBufferSizeInBytes = v8;
    goto LABEL_32;
  }
  InBuffer = 1;
  FileW = (__int64)CreateFileW(v2, 0x80000000, 7u, 0, 1u, 0x100000u, 0);
  if ( FileW != -1 )
  {
    while ( 1 )
    {
      v10 = IssueSynchronousDeviceIoControl(
              (HANDLE)FileW,
              0x2D19DCu,
              &InBuffer,
              4u,
              Heap,
              v8,
              &NumberOfBytesTransferred);
      LastError = v10;
      if ( !v10 && (unsigned int)v8 >= NumberOfBytesTransferred )
        break;
      if ( v10 != 234 )
        goto LABEL_30;
      v8 = Heap[1];
      if ( (unsigned int)v8 < 8 )
      {
        LastError = 13;
        goto LABEL_30;
      }
      if ( *PathsBufferSizeInBytes < (unsigned __int64)(v8 - 8) )
      {
        LastError = 122;
        goto LABEL_30;
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      Heap = (unsigned int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)v8);
      if ( !Heap )
        goto LABEL_16;
    }
    if ( PathsBuffer )
      memcpy_0(PathsBuffer, Heap + 2, (unsigned int)v8 - 8LL);
    goto LABEL_30;
  }
  LastError = GetLastError();
  *PathsBufferSizeInBytes = 10;
LABEL_31:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
LABEL_32:
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( v2 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_6afab5048b663292b11c40fad9d08467_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800073d0  mov     [rsp-38h+arg_8], rbx
0x1800073d5  push    rbp
0x1800073d6  push    rsi
0x1800073d7  push    rdi
0x1800073d8  push    r12
0x1800073da  push    r13
0x1800073dc  push    r14
0x1800073de  push    r15
0x1800073e0  mov     rbp, rsp
0x1800073e3  sub     rsp, 60h
0x1800073e7  xor     r12d, r12d
0x1800073ea  mov     [rbp+InBuffer], 0
0x1800073f1  mov     [rbp+lpFileName], r12
0x1800073f5  mov     r13, rdx
0x1800073f8  mov     rsi, rcx
0x1800073fb  mov     [rbp+NumberOfBytesTransferred], 0
0x180007402  mov     rcx, cs:WPP_GLOBAL_Control
0x180007409  lea     r15, WPP_GLOBAL_Control
0x180007410  cmp     rcx, r15
0x180007413  jz      short loc_180007436
0x180007415  test    byte ptr [rcx+1Ch], 20h
0x180007419  jz      short loc_180007436
0x18000741b  cmp     byte ptr [rcx+19h], 4
0x18000741f  jb      short loc_180007436
0x180007421  mov     rcx, [rcx+10h]
0x180007425  lea     edx, [r12+10h]
0x18000742a  lea     r8, WPP_6afab5048b663292b11c40fad9d08467_Traceguids
0x180007431  call    WPP_SF_
0x180007436  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000743a  mov     [rbp+hObject], r14
0x18000743e  test    rsi, rsi
0x180007441  jnz     short loc_180007453
0x180007443  mov     ebx, 57h ; 'W'
0x180007448  mov     dword ptr [rsi], 0Ah
0x18000744e  jmp     loc_180007643
0x180007453  test    r13, r13
0x180007456  jnz     short loc_18000745D
0x180007458  cmp     [rsi], r12d
0x18000745b  jnz     short loc_180007443
0x18000745d  cmp     dword ptr [rsi], 2
0x180007460  jnb     short loc_180007469
0x180007462  mov     ebx, 7Ah ; 'z'
0x180007467  jmp     short loc_180007448
0x180007469  movups  xmm0, xmmword ptr cs:VIRTUAL_STORAGE_TYPE_VENDOR_MICROSOFT.Data1
0x180007470  lea     rax, [rbp+hObject]
0x180007474  mov     [rbp+var_18], 2
0x18000747b  xor     r15d, r15d
0x18000747e  mov     qword ptr [rsp+60h+dwCreationDisposition], rax; __int64
0x180007483  lea     r9, [rbp+var_18]
0x180007487  xor     ecx, ecx; Src
0x180007489  lea     r8, [rbp+lpFileName]
0x18000748d  movdqu  [rbp+var_14], xmm0
0x180007492  lea     edi, [r15+0Ah]
0x180007496  lea     edx, [rdi-9]
0x180007499  call    FindVirtualDiskShimForFile
0x18000749e  mov     r12, [rbp+lpFileName]
0x1800074a2  mov     ebx, eax
0x1800074a4  mov     r14, [rbp+hObject]
0x1800074a8  test    eax, eax
0x1800074aa  jnz     loc_180007617
0x1800074b0  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800074b4  jz      short loc_1800074C9
0x1800074b6  mov     rcx, r14; hObject
0x1800074b9  call    cs:__imp_CloseHandle
0x1800074c0  nop     dword ptr [rax+rax+00h]
0x1800074c5  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800074c9  mov     rcx, gs:60h
0x1800074d2  mov     r8, rdi; Size
0x1800074d5  xor     edx, edx; Flags
0x1800074d7  mov     rcx, [rcx+30h]; HeapHandle
0x1800074db  call    cs:__imp_RtlAllocateHeap
0x1800074e2  nop     dword ptr [rax+rax+00h]
0x1800074e7  mov     r15, rax
0x1800074ea  test    rax, rax
0x1800074ed  jnz     short loc_1800074FB
0x1800074ef  mov     ebx, 0Eh
0x1800074f4  mov     [rsi], edi
0x1800074f6  jmp     loc_18000763C
0x1800074fb  mov     eax, 1
0x180007500  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x180007509  mov     [rsp+60h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x180007511  xor     r9d, r9d; lpSecurityAttributes
0x180007514  mov     edx, 80000000h; dwDesiredAccess
0x180007519  mov     [rbp+InBuffer], eax
0x18000751c  mov     rcx, r12; lpFileName
0x18000751f  mov     [rsp+60h+dwCreationDisposition], eax; dwCreationDisposition
0x180007523  lea     r8d, [rax+6]; dwShareMode
0x180007527  call    cs:__imp_CreateFileW
0x18000752e  nop     dword ptr [rax+rax+00h]
0x180007533  mov     r14, rax
0x180007536  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000753a  jnz     short loc_180007551
0x18000753c  call    cs:__imp_GetLastError
0x180007543  nop     dword ptr [rax+rax+00h]
0x180007548  mov     ebx, eax
0x18000754a  mov     [rsi], edi
0x18000754c  jmp     loc_18000761E
0x180007551  lea     rax, [rbp+NumberOfBytesTransferred]
0x180007555  mov     r9d, 4; nInBufferSize
0x18000755b  mov     [rsp+60h+hTemplateFile], rax; lpNumberOfBytesTransferred
0x180007560  lea     r8, [rbp+InBuffer]; lpInBuffer
0x180007564  mov     [rsp+60h+dwFlagsAndAttributes], edi; DWORD
0x180007568  mov     edx, 2D19DCh; dwIoControlCode
0x18000756d  mov     rcx, r14; hFile
0x180007570  mov     qword ptr [rsp+60h+dwCreationDisposition], r15; LPVOID
0x180007575  call    IssueSynchronousDeviceIoControl
0x18000757a  mov     ebx, eax
0x18000757c  test    eax, eax
0x18000757e  jnz     short loc_180007585
0x180007580  cmp     edi, [rbp+NumberOfBytesTransferred]
0x180007583  jnb     short loc_1800075F1
0x180007585  cmp     eax, 0EAh
0x18000758a  jnz     loc_180007617
0x180007590  mov     edi, [r15+4]
0x180007594  cmp     edi, 8
0x180007597  jb      short loc_180007612
0x180007599  mov     eax, [rsi]
0x18000759b  lea     rcx, [rdi-8]
0x18000759f  cmp     rax, rcx
0x1800075a2  jb      short loc_18000760B
0x1800075a4  mov     rcx, gs:60h
0x1800075ad  mov     r8, r15; P
0x1800075b0  xor     edx, edx; Flags
0x1800075b2  mov     rcx, [rcx+30h]; HeapHandle
0x1800075b6  call    cs:__imp_RtlFreeHeap
0x1800075bd  nop     dword ptr [rax+rax+00h]
0x1800075c2  mov     rcx, gs:60h
0x1800075cb  mov     r8d, edi; Size
0x1800075ce  xor     edx, edx; Flags
0x1800075d0  mov     rcx, [rcx+30h]; HeapHandle
0x1800075d4  call    cs:__imp_RtlAllocateHeap
0x1800075db  nop     dword ptr [rax+rax+00h]
0x1800075e0  mov     r15, rax
0x1800075e3  test    rax, rax
0x1800075e6  jnz     loc_180007551
0x1800075ec  jmp     loc_1800074EF
0x1800075f1  test    r13, r13
0x1800075f4  jz      short loc_180007617
0x1800075f6  mov     r8d, edi
0x1800075f9  lea     rdx, [r15+8]; Src
0x1800075fd  sub     r8, 8; Size
0x180007601  mov     rcx, r13; void *
0x180007604  call    memcpy_0
0x180007609  jmp     short loc_180007617
0x18000760b  mov     ebx, 7Ah ; 'z'
0x180007610  jmp     short loc_180007617
0x180007612  mov     ebx, 0Dh
0x180007617  mov     [rsi], edi
0x180007619  test    r15, r15
0x18000761c  jz      short loc_18000763C
0x18000761e  mov     rcx, gs:60h
0x180007627  mov     r8, r15; P
0x18000762a  xor     edx, edx; Flags
0x18000762c  mov     rcx, [rcx+30h]; HeapHandle
0x180007630  call    cs:__imp_RtlFreeHeap
0x180007637  nop     dword ptr [rax+rax+00h]
0x18000763c  lea     r15, WPP_GLOBAL_Control
0x180007643  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180007647  jz      short loc_180007658
0x180007649  mov     rcx, r14; hObject
0x18000764c  call    cs:__imp_CloseHandle
0x180007653  nop     dword ptr [rax+rax+00h]
0x180007658  test    r12, r12
0x18000765b  jz      short loc_18000767B
0x18000765d  mov     rcx, gs:60h
0x180007666  mov     r8, r12; P
0x180007669  xor     edx, edx; Flags
0x18000766b  mov     rcx, [rcx+30h]; HeapHandle
0x18000766f  call    cs:__imp_RtlFreeHeap
0x180007676  nop     dword ptr [rax+rax+00h]
0x18000767b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007682  cmp     rcx, r15
0x180007685  jz      short loc_1800076AB
0x180007687  test    byte ptr [rcx+1Ch], 20h
0x18000768b  jz      short loc_1800076AB
0x18000768d  cmp     byte ptr [rcx+19h], 4
0x180007691  jb      short loc_1800076AB
0x180007693  mov     rcx, [rcx+10h]
0x180007697  lea     r8, WPP_6afab5048b663292b11c40fad9d08467_Traceguids
0x18000769e  mov     edx, 11h
0x1800076a3  mov     r9d, ebx
0x1800076a6  call    WPP_SF_d
0x1800076ab  mov     eax, ebx
0x1800076ad  mov     rbx, [rsp+60h+arg_8]
0x1800076b5  add     rsp, 60h
0x1800076b9  pop     r15
0x1800076bb  pop     r14
0x1800076bd  pop     r13
0x1800076bf  pop     r12
0x1800076c1  pop     rdi
0x1800076c2  pop     rsi
0x1800076c3  pop     rbp
0x1800076c4  retn
```
