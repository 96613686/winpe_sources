# WIMCloseWIM

- ea: `0x18000f7c4`
- end: `0x18000fcca`
- name: `WIMCloseWIM`
- size: `1286`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000e230`

## callees

- `0x18000d9c4`
- `0x18000da6c`
- `0x18000daf0`
- `0x18000e3e0`
- `0x18000f278`
- `0x18000f7c4`
- `0x18000fcd0`
- `0x1800102ec`
- `0x180010360`
- `0x180011850`
- `0x180011880`
- `0x180011a38`
- `0x180011a84`
- `0x180011b50`
- `0x180011bb8`
- `0x180011df8`
- `0x18001219c`
- `0x180012208`
- `0x1800122cc`
- `0x180012304`
- `0x180012338`
- `0x180012368`
- `0x180012ccc`
- `0x1800130c0`
- `0x180016fdc`
- `0x180017344`
- `0x1800185f0`
- `0x18001eaac`
- `0x18001fb8c`
- `0x180021194`
- `0x180040e74`
- `0x180060e5a`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000faab`
- `KERNEL32!HeapFree` at `0x18000fafb`
- `KERNEL32!HeapFree` at `0x18000fbdd`
- `KERNEL32!HeapFree` at `0x18000fc15`
- `KERNEL32!HeapFree` at `0x18000fc45`
- `KERNEL32!HeapFree` at `0x18000fc90`
- `KERNEL32!HeapFree` at `0x18000faab`
- `KERNEL32!HeapFree` at `0x18000fafb`
- `KERNEL32!HeapFree` at `0x18000fbdd`
- `KERNEL32!HeapFree` at `0x18000fc15`
- `KERNEL32!HeapFree` at `0x18000fc45`
- `KERNEL32!HeapFree` at `0x18000fc90`
- `KERNEL32!GetLastError` at `0x18000f85e`
- `KERNEL32!GetLastError` at `0x18000f86c`
- `KERNEL32!GetLastError` at `0x18000f958`
- `KERNEL32!GetLastError` at `0x18000f989`
- `KERNEL32!GetLastError` at `0x18000fa0b`
- `KERNEL32!GetLastError` at `0x18000f85e`
- `KERNEL32!GetLastError` at `0x18000f86c`
- `KERNEL32!GetLastError` at `0x18000f958`
- `KERNEL32!GetLastError` at `0x18000f989`
- `KERNEL32!GetLastError` at `0x18000fa0b`
- `KERNEL32!SetLastError` at `0x18000f7fc`
- `KERNEL32!SetLastError` at `0x18000fca2`
- `KERNEL32!SetLastError` at `0x18000f7fc`
- `KERNEL32!SetLastError` at `0x18000fca2`
- `KERNEL32!GetProcessHeap` at `0x18000fa97`
- `KERNEL32!GetProcessHeap` at `0x18000fae7`
- `KERNEL32!GetProcessHeap` at `0x18000fbc9`
- `KERNEL32!GetProcessHeap` at `0x18000fc01`
- `KERNEL32!GetProcessHeap` at `0x18000fc31`
- `KERNEL32!GetProcessHeap` at `0x18000fc7c`
- `KERNEL32!GetProcessHeap` at `0x18000fa97`
- `KERNEL32!GetProcessHeap` at `0x18000fae7`
- `KERNEL32!GetProcessHeap` at `0x18000fbc9`
- `KERNEL32!GetProcessHeap` at `0x18000fc01`
- `KERNEL32!GetProcessHeap` at `0x18000fc31`
- `KERNEL32!GetProcessHeap` at `0x18000fc7c`
- `KERNEL32!FlushFileBuffers` at `0x18000f9fb`
- `KERNEL32!FlushFileBuffers` at `0x18000f9fb`

## string_xrefs

- `0x18000f9b1`: `Fail to read WIM header`
- `0x18000f980`: `Fail to update WIM header`

## pseudocode

```c
__int64 __fastcall WIMCloseWIM(__int64 a1)
{
  unsigned int v1; // r14d
  DWORD v3; // esi
  int v4; // ebx
  DWORD v5; // ecx
  char HandleFlags; // al
  char *ImageHandle; // rax
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  DWORD LastError; // eax
  __int64 WimHeader; // rax
  char v12; // r12
  __int64 WimLastEOF; // rax
  void *WimFileHandle; // rax
  LARGE_INTEGER v15; // rdx
  __int64 v16; // r8
  DWORD v17; // r9d
  void *v18; // rax
  __int64 v19; // rax
  int v20; // r8d
  int WimPath; // eax
  NTSTATUS Status; // edx
  int v23; // eax
  NTSTATUS v24; // edx
  void *v25; // rax
  int v26; // eax
  NTSTATUS v27; // edx
  void *v28; // rax
  __int64 v29; // rax
  _QWORD *v30; // rbp
  void *v31; // rbx
  HANDLE ProcessHeap; // rax
  void *WimIntegrityInfo; // rbx
  HANDLE v34; // rax
  __int64 v35; // rdx
  const WCHAR *v36; // rax
  int v37; // eax
  void *v38; // rbx
  HANDLE v39; // rax
  void *v40; // rbx
  HANDLE v41; // rax
  void *WimTempPath; // rbx
  HANDLE v43; // rax
  HANDLE v44; // rax
  __int64 v45; // [rsp+70h] [rbp+8h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp+10h] BYREF

  lpMem = 0;
  v1 = 1;
  v3 = 0;
  v4 = WIMGetImageCount();
  if ( !a1 )
  {
    v5 = 6;
LABEL_3:
    SetLastError(v5);
    return 0;
  }
  if ( *(_QWORD *)(a1 + 576) )
  {
    v5 = 32;
    goto LABEL_3;
  }
  HandleFlags = GetHandleFlags(a1);
  if ( (HandleFlags & 0x11) == 0 && (HandleFlags & 0xE) != 0 && v4 )
  {
    ImageHandle = CreateImageHandle(a1, 0);
    v9 = (struct _RTL_CRITICAL_SECTION *)ImageHandle;
    if ( ImageHandle )
    {
      SetHandleFlag(ImageHandle, 1);
      v1 = WIMCloseImage(v9);
      if ( v1 )
      {
LABEL_14:
        WimHeader = GetWimHeader(a1);
        SetWriteOffset(a1, *(_QWORD *)(WimHeader + 64));
        goto LABEL_15;
      }
      LastError = GetLastError();
    }
    else
    {
      LastError = GetLastError();
      v1 = 0;
    }
    v3 = LastError;
    if ( !LastError )
      goto LABEL_14;
  }
LABEL_15:
  v12 = GetHandleFlags(a1);
  if ( (v12 & 0x10) != 0 )
  {
    WimLastEOF = GetWimLastEOF(a1);
    SetWriteOffset(a1, WimLastEOF);
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))GetWriteOffset)(a1, 0, (LARGE_INTEGER)g_liZero.QuadPart);
    WimFileHandle = (void *)GetWimFileHandle(a1);
    WIMSetFilePointerEx(WimFileHandle, v15, v16, v17);
    v18 = (void *)GetWimFileHandle(a1);
    WIMSetEndOfFile(v18);
    if ( (v12 & 8) != 0 )
    {
      if ( (unsigned int)ReadWimHeader(a1, 0) && (*(_BYTE *)(GetWimHeader(a1) + 16) & 0x40) != 0 )
      {
        GetWimHeader(a1);
        v19 = GetWimHeader(a1);
        *(_DWORD *)(v19 + 16) = v20;
        if ( (unsigned int)UpdateWimHeader(a1, 0) )
        {
          ResetHandleFlag(a1, 8);
        }
        else
        {
          v3 = GetLastError();
          WimPath = GetWimPath(a1);
          WIMLogMsg(1, 0, WimPath, (int)L"Fail to update WIM header", Status, (__int64)L"WIMCloseWIM", 2764);
        }
      }
      else
      {
        v3 = GetLastError();
        v23 = GetWimPath(a1);
        WIMLogMsg(1, 0, v23, (int)L"Fail to read WIM header", v24, (__int64)L"WIMCloseWIM", 2772);
      }
    }
  }
  FreeWimRefExt(a1);
  FreeWimReferenceList(a1);
  if ( (*(_DWORD *)(a1 + 428) & 0x40000000) != 0 )
  {
    v25 = (void *)GetWimFileHandle(a1);
    if ( !FlushFileBuffers(v25) )
    {
      GetLastError();
      v26 = GetWimPath(a1);
      WIMLogMsg(1, 0, v26, (int)L"Fail to flush file buffers", v27, (__int64)L"WIMCloseWIM", 2791);
    }
  }
  v28 = (void *)GetWimFileHandle(a1);
  WIMFileCloseHandle(v28);
  if ( *(_DWORD *)a1 == -17960959 )
  {
    v29 = a1;
    goto LABEL_30;
  }
  if ( *(_DWORD *)a1 == -17960958 )
  {
    v29 = *(_QWORD *)(a1 + 8);
LABEL_30:
    if ( v29 )
      *(_QWORD *)(v29 + 8) = -1;
  }
  v30 = *(_QWORD **)(a1 + 496);
  while ( v30 )
  {
    v31 = v30;
    v30 = (_QWORD *)v30[1];
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v31);
  }
  FreeWimHashTable(*(_QWORD *)(a1 + 464), 0);
  if ( GetWimIntegrityInfo(a1) )
  {
    WimIntegrityInfo = (void *)GetWimIntegrityInfo(a1);
    if ( WimIntegrityInfo )
    {
      v34 = GetProcessHeap();
      HeapFree(v34, 0, WimIntegrityInfo);
    }
  }
  ResNodeFree(*(LPVOID *)(a1 + 16));
  ResNodeFree(*(LPVOID *)(a1 + 32));
  if ( (v12 & 0x10) != 0 )
  {
    if ( GetWimLastEOF(a1) )
    {
      if ( (v12 & 2) != 0 )
      {
        v1 = 0;
        v3 = 1392;
        v37 = GetWimPath(a1);
        WIMLogMsg(1, 0, v37, (int)L"The existing WIM file became corrupted", -2147023504, (__int64)L"WIMCloseWIM", 2838);
      }
    }
    else
    {
      v36 = (const WCHAR *)GetWimPath(a1);
      WimDeleteFile(v36);
    }
  }
  if ( *(_DWORD *)a1 == -17960959 && *(_QWORD *)(a1 + 512) )
  {
    v45 = 0;
    WimGetMessageStruct(a1, v35, &v45);
    WimFreeMessageStruct(a1, v45);
  }
  v38 = *(void **)(a1 + 480);
  if ( v38 )
  {
    UnattendCtxCleanup(*(_QWORD *)(a1 + 480));
    v39 = GetProcessHeap();
    HeapFree(v39, 0, v38);
  }
  *(_QWORD *)(a1 + 480) = 0;
  v40 = (void *)GetWimPath(a1);
  if ( v40 )
  {
    v41 = GetProcessHeap();
    HeapFree(v41, 0, v40);
  }
  WimTempPath = (void *)GetWimTempPath(a1);
  if ( WimTempPath )
  {
    v43 = GetProcessHeap();
    HeapFree(v43, 0, WimTempPath);
  }
  if ( (int)GetChunkReader(a1, &lpMem) >= 0 )
    ChunkReaderClose(lpMem);
  memset_0((void *)a1, 0, 0x258u);
  v44 = GetProcessHeap();
  HeapFree(v44, 0, (LPVOID)a1);
  if ( v3 )
    SetLastError(v3);
  return v1;
}

```

## disassembly

```asm
0x18000f7c4  mov     [rsp+arg_10], rbx
0x18000f7c9  mov     [rsp+arg_18], rbp
0x18000f7ce  push    rsi
0x18000f7cf  push    rdi
0x18000f7d0  push    r12
0x18000f7d2  push    r14
0x18000f7d4  push    r15
0x18000f7d6  sub     rsp, 40h
0x18000f7da  and     [rsp+68h+lpMem], 0
0x18000f7e0  mov     ebp, 1
0x18000f7e5  mov     r14d, ebp
0x18000f7e8  mov     rdi, rcx
0x18000f7eb  xor     esi, esi
0x18000f7ed  call    WIMGetImageCount
0x18000f7f2  mov     ebx, eax
0x18000f7f4  test    rdi, rdi
0x18000f7f7  jnz     short loc_18000F80F
0x18000f7f9  lea     ecx, [rbp+5]; dwErrCode
0x18000f7fc  call    cs:__imp_SetLastError
0x18000f803  nop     dword ptr [rax+rax+00h]
0x18000f808  xor     eax, eax
0x18000f80a  jmp     loc_18000FCB1
0x18000f80f  cmp     [rdi+240h], rsi
0x18000f816  jz      short loc_18000F81F
0x18000f818  mov     ecx, 20h ; ' '
0x18000f81d  jmp     short loc_18000F7FC
0x18000f81f  mov     rcx, rdi
0x18000f822  call    GetHandleFlags
0x18000f827  test    al, 11h
0x18000f829  jnz     short loc_18000F895
0x18000f82b  test    al, 0Eh
0x18000f82d  jz      short loc_18000F895
0x18000f82f  test    ebx, ebx
0x18000f831  jz      short loc_18000F895
0x18000f833  xor     edx, edx
0x18000f835  mov     rcx, rdi
0x18000f838  call    CreateImageHandle
0x18000f83d  mov     rbx, rax
0x18000f840  test    rax, rax
0x18000f843  jz      short loc_18000F86C
0x18000f845  mov     edx, ebp
0x18000f847  mov     rcx, rax
0x18000f84a  call    SetHandleFlag
0x18000f84f  mov     rcx, rbx; void *
0x18000f852  call    WIMCloseImage
0x18000f857  mov     r14d, eax
0x18000f85a  test    eax, eax
0x18000f85c  jnz     short loc_18000F881
0x18000f85e  call    cs:__imp_GetLastError
0x18000f865  nop     dword ptr [rax+rax+00h]
0x18000f86a  jmp     short loc_18000F87B
0x18000f86c  call    cs:__imp_GetLastError
0x18000f873  nop     dword ptr [rax+rax+00h]
0x18000f878  xor     r14d, r14d
0x18000f87b  mov     esi, eax
0x18000f87d  test    eax, eax
0x18000f87f  jnz     short loc_18000F895
0x18000f881  mov     rcx, rdi
0x18000f884  call    GetWimHeader
0x18000f889  mov     rcx, rdi
0x18000f88c  mov     rdx, [rax+40h]
0x18000f890  call    SetWriteOffset
0x18000f895  mov     rcx, rdi
0x18000f898  call    GetHandleFlags
0x18000f89d  mov     r15d, eax
0x18000f8a0  mov     r12d, eax
0x18000f8a3  mov     ebx, 80070000h
0x18000f8a8  and     r15d, 10h
0x18000f8ac  jz      loc_18000F9D4
0x18000f8b2  mov     rcx, rdi
0x18000f8b5  call    GetWimLastEOF
0x18000f8ba  mov     rdx, rax
0x18000f8bd  mov     rcx, rdi
0x18000f8c0  call    SetWriteOffset
0x18000f8c5  mov     r8, qword ptr cs:g_liZero
0x18000f8cc  mov     rcx, rdi
0x18000f8cf  xor     edx, edx
0x18000f8d1  call    GetWriteOffset
0x18000f8d6  mov     rcx, rdi
0x18000f8d9  mov     rdx, rax
0x18000f8dc  call    GetWimFileHandle
0x18000f8e1  mov     rcx, rax; hFile
0x18000f8e4  call    WIMSetFilePointerEx
0x18000f8e9  mov     rcx, rdi
0x18000f8ec  call    GetWimFileHandle
0x18000f8f1  mov     rcx, rax; hFile
0x18000f8f4  call    WIMSetEndOfFile
0x18000f8f9  test    r12b, 8
0x18000f8fd  jz      loc_18000F9D4
0x18000f903  xor     edx, edx
0x18000f905  mov     rcx, rdi
0x18000f908  call    ReadWimHeader
0x18000f90d  test    eax, eax
0x18000f90f  jz      short loc_18000F989
0x18000f911  mov     rcx, rdi
0x18000f914  call    GetWimHeader
0x18000f919  test    byte ptr [rax+10h], 40h
0x18000f91d  jz      short loc_18000F989
0x18000f91f  mov     rcx, rdi
0x18000f922  call    GetWimHeader
0x18000f927  mov     rcx, rdi
0x18000f92a  mov     r8d, [rax+10h]
0x18000f92e  and     r8d, 0FFFFFFBFh
0x18000f932  call    GetWimHeader
0x18000f937  xor     edx, edx
0x18000f939  mov     rcx, rdi
0x18000f93c  mov     [rax+10h], r8d
0x18000f940  call    UpdateWimHeader
0x18000f945  test    eax, eax
0x18000f947  jz      short loc_18000F958
0x18000f949  mov     edx, 8
0x18000f94e  mov     rcx, rdi
0x18000f951  call    ResetHandleFlag
0x18000f956  jmp     short loc_18000F9D4
0x18000f958  call    cs:__imp_GetLastError
0x18000f95f  nop     dword ptr [rax+rax+00h]
0x18000f964  movzx   edx, ax
0x18000f967  mov     rcx, rdi
0x18000f96a  or      edx, ebx
0x18000f96c  mov     esi, eax
0x18000f96e  test    eax, eax
0x18000f970  cmovle  edx, eax
0x18000f973  call    GetWimPath
0x18000f978  mov     [rsp+68h+var_38], 0ACCh
0x18000f980  lea     r9, aFailToUpdateWi; "Fail to update WIM header"
0x18000f987  jmp     short loc_18000F9B8
0x18000f989  call    cs:__imp_GetLastError
0x18000f990  nop     dword ptr [rax+rax+00h]
0x18000f995  movzx   edx, ax
0x18000f998  mov     rcx, rdi
0x18000f99b  or      edx, ebx
0x18000f99d  mov     esi, eax
0x18000f99f  test    eax, eax
0x18000f9a1  cmovle  edx, eax
0x18000f9a4  call    GetWimPath
0x18000f9a9  mov     [rsp+68h+var_38], 0AD4h; int
0x18000f9b1  lea     r9, aFailToReadWimH; "Fail to read WIM header"
0x18000f9b8  mov     r8, rax; int
0x18000f9bb  mov     ecx, ebp; int
0x18000f9bd  lea     rax, aWimclosewim; "WIMCloseWIM"
0x18000f9c4  mov     [rsp+68h+var_40], rax; __int64
0x18000f9c9  mov     [rsp+68h+Status], edx; Status
0x18000f9cd  xor     edx, edx; int
0x18000f9cf  call    _WIMLogMsg
0x18000f9d4  mov     rcx, rdi
0x18000f9d7  call    FreeWimRefExt
0x18000f9dc  mov     rcx, rdi
0x18000f9df  call    FreeWimReferenceList
0x18000f9e4  test    dword ptr [rdi+1ACh], 40000000h
0x18000f9ee  jz      short loc_18000FA54
0x18000f9f0  mov     rcx, rdi
0x18000f9f3  call    GetWimFileHandle
0x18000f9f8  mov     rcx, rax; hFile
0x18000f9fb  call    cs:__imp_FlushFileBuffers
0x18000fa02  nop     dword ptr [rax+rax+00h]
0x18000fa07  test    eax, eax
0x18000fa09  jnz     short loc_18000FA54
0x18000fa0b  call    cs:__imp_GetLastError
0x18000fa12  nop     dword ptr [rax+rax+00h]
0x18000fa17  movzx   edx, ax
0x18000fa1a  mov     rcx, rdi
0x18000fa1d  or      edx, ebx
0x18000fa1f  test    eax, eax
0x18000fa21  cmovle  edx, eax
0x18000fa24  call    GetWimPath
0x18000fa29  mov     r8, rax; int
0x18000fa2c  mov     [rsp+68h+var_38], 0AE7h; int
0x18000fa34  lea     rax, aWimclosewim; "WIMCloseWIM"
0x18000fa3b  mov     ecx, ebp; int
0x18000fa3d  mov     [rsp+68h+var_40], rax; __int64
0x18000fa42  lea     r9, aFailToFlushFil; "Fail to flush file buffers"
0x18000fa49  mov     [rsp+68h+Status], edx; Status
0x18000fa4d  xor     edx, edx; int
0x18000fa4f  call    _WIMLogMsg
0x18000fa54  mov     rcx, rdi
0x18000fa57  call    GetWimFileHandle
0x18000fa5c  mov     rcx, rax; hObject
0x18000fa5f  call    WIMFileCloseHandle
0x18000fa64  cmp     dword ptr [rdi], 0FEEDF001h
0x18000fa6a  jnz     short loc_18000FA71
0x18000fa6c  mov     rax, rdi
0x18000fa6f  jmp     short loc_18000FA7D
0x18000fa71  cmp     dword ptr [rdi], 0FEEDF002h
0x18000fa77  jnz     short loc_18000FA87
0x18000fa79  mov     rax, [rdi+8]
0x18000fa7d  test    rax, rax
0x18000fa80  jz      short loc_18000FA87
0x18000fa82  or      qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x18000fa87  mov     rbp, [rdi+1F0h]
0x18000fa8e  jmp     short loc_18000FAB7
0x18000fa90  mov     rbx, rbp
0x18000fa93  mov     rbp, [rbp+8]
0x18000fa97  call    cs:__imp_GetProcessHeap
0x18000fa9e  nop     dword ptr [rax+rax+00h]
0x18000faa3  mov     r8, rbx; lpMem
0x18000faa6  xor     edx, edx; dwFlags
0x18000faa8  mov     rcx, rax; hHeap
0x18000faab  call    cs:__imp_HeapFree
0x18000fab2  nop     dword ptr [rax+rax+00h]
0x18000fab7  test    rbp, rbp
0x18000faba  jnz     short loc_18000FA90
0x18000fabc  mov     rcx, [rdi+1D0h]
0x18000fac3  xor     edx, edx
0x18000fac5  call    FreeWimHashTable
0x18000faca  mov     rcx, rdi
0x18000facd  call    GetWimIntegrityInfo
0x18000fad2  test    rax, rax
0x18000fad5  jz      short loc_18000FB07
0x18000fad7  mov     rcx, rdi
0x18000fada  call    GetWimIntegrityInfo
0x18000fadf  mov     rbx, rax
0x18000fae2  test    rax, rax
0x18000fae5  jz      short loc_18000FB07
0x18000fae7  call    cs:__imp_GetProcessHeap
0x18000faee  nop     dword ptr [rax+rax+00h]
0x18000faf3  mov     r8, rbx; lpMem
0x18000faf6  xor     edx, edx; dwFlags
0x18000faf8  mov     rcx, rax; hHeap
0x18000fafb  call    cs:__imp_HeapFree
0x18000fb02  nop     dword ptr [rax+rax+00h]
0x18000fb07  mov     rcx, [rdi+10h]; lpMem
0x18000fb0b  call    _ResNodeFree
0x18000fb10  mov     rcx, [rdi+20h]; lpMem
0x18000fb14  call    _ResNodeFree
0x18000fb19  test    r15d, r15d
0x18000fb1c  jz      short loc_18000FB83
0x18000fb1e  mov     rcx, rdi
0x18000fb21  call    GetWimLastEOF
0x18000fb26  test    rax, rax
0x18000fb29  jnz     short loc_18000FB3D
0x18000fb2b  mov     rcx, rdi
0x18000fb2e  call    GetWimPath
0x18000fb33  mov     rcx, rax; lpFileName
0x18000fb36  call    WimDeleteFile
0x18000fb3b  jmp     short loc_18000FB83
0x18000fb3d  test    r12b, 2
0x18000fb41  jz      short loc_18000FB83
0x18000fb43  mov     rcx, rdi
0x18000fb46  xor     r14d, r14d
0x18000fb49  mov     esi, 570h
0x18000fb4e  call    GetWimPath
0x18000fb53  xor     edx, edx; int
0x18000fb55  mov     [rsp+68h+var_38], 0B16h; int
0x18000fb5d  mov     r8, rax; int
0x18000fb60  lea     r9, aTheExistingWim; "The existing WIM file became corrupted"
0x18000fb67  lea     rax, aWimclosewim; "WIMCloseWIM"
0x18000fb6e  mov     [rsp+68h+var_40], rax; __int64
0x18000fb73  lea     ecx, [rdx+1]; int
0x18000fb76  mov     [rsp+68h+Status], 80070570h; Status
0x18000fb7e  call    _WIMLogMsg
0x18000fb83  cmp     dword ptr [rdi], 0FEEDF001h
0x18000fb89  jnz     short loc_18000FBB5
0x18000fb8b  cmp     qword ptr [rdi+200h], 0
0x18000fb93  jz      short loc_18000FBB5
0x18000fb95  and     [rsp+68h+arg_0], 0
0x18000fb9b  lea     r8, [rsp+68h+arg_0]
0x18000fba0  mov     rcx, rdi
0x18000fba3  call    WimGetMessageStruct
0x18000fba8  mov     rdx, [rsp+68h+arg_0]
0x18000fbad  mov     rcx, rdi
0x18000fbb0  call    WimFreeMessageStruct
0x18000fbb5  mov     rbx, [rdi+1E0h]
0x18000fbbc  test    rbx, rbx
0x18000fbbf  jz      short loc_18000FBE9
0x18000fbc1  mov     rcx, rbx
0x18000fbc4  call    UnattendCtxCleanup
0x18000fbc9  call    cs:__imp_GetProcessHeap
0x18000fbd0  nop     dword ptr [rax+rax+00h]
0x18000fbd5  mov     r8, rbx; lpMem
0x18000fbd8  xor     edx, edx; dwFlags
0x18000fbda  mov     rcx, rax; hHeap
0x18000fbdd  call    cs:__imp_HeapFree
0x18000fbe4  nop     dword ptr [rax+rax+00h]
0x18000fbe9  and     qword ptr [rdi+1E0h], 0
0x18000fbf1  mov     rcx, rdi
0x18000fbf4  call    GetWimPath
0x18000fbf9  mov     rbx, rax
0x18000fbfc  test    rax, rax
0x18000fbff  jz      short loc_18000FC21
0x18000fc01  call    cs:__imp_GetProcessHeap
0x18000fc08  nop     dword ptr [rax+rax+00h]
0x18000fc0d  mov     r8, rbx; lpMem
0x18000fc10  xor     edx, edx; dwFlags
0x18000fc12  mov     rcx, rax; hHeap
0x18000fc15  call    cs:__imp_HeapFree
0x18000fc1c  nop     dword ptr [rax+rax+00h]
0x18000fc21  mov     rcx, rdi
0x18000fc24  call    GetWimTempPath
0x18000fc29  mov     rbx, rax
0x18000fc2c  test    rax, rax
0x18000fc2f  jz      short loc_18000FC51
0x18000fc31  call    cs:__imp_GetProcessHeap
0x18000fc38  nop     dword ptr [rax+rax+00h]
0x18000fc3d  mov     r8, rbx; lpMem
0x18000fc40  xor     edx, edx; dwFlags
0x18000fc42  mov     rcx, rax; hHeap
0x18000fc45  call    cs:__imp_HeapFree
0x18000fc4c  nop     dword ptr [rax+rax+00h]
0x18000fc51  lea     rdx, [rsp+68h+lpMem]
0x18000fc56  mov     rcx, rdi
  ... truncated ...
```
