# WIMCloseImage

- ea: `0x18000f278`
- end: `0x18000f7be`
- name: `WIMCloseImage`
- size: `1350`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e230`
- `0x18000f7c4`

## callees

- `0x18000ed20`
- `0x18000f124`
- `0x18000f278`
- `0x180016fdc`
- `0x1800193c0`
- `0x18001af78`
- `0x18001b298`
- `0x18001b570`
- `0x18001b870`
- `0x18001d6d0`
- `0x180060e5a`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000f384`
- `KERNEL32!HeapFree` at `0x18000f4cc`
- `KERNEL32!HeapFree` at `0x18000f503`
- `KERNEL32!HeapFree` at `0x18000f537`
- `KERNEL32!HeapFree` at `0x18000f574`
- `KERNEL32!HeapFree` at `0x18000f5b3`
- `KERNEL32!HeapFree` at `0x18000f5f0`
- `KERNEL32!HeapFree` at `0x18000f657`
- `KERNEL32!HeapFree` at `0x18000f68a`
- `KERNEL32!HeapFree` at `0x18000f6c2`
- `KERNEL32!HeapFree` at `0x18000f77e`
- `KERNEL32!HeapFree` at `0x18000f384`
- `KERNEL32!HeapFree` at `0x18000f4cc`
- `KERNEL32!HeapFree` at `0x18000f503`
- `KERNEL32!HeapFree` at `0x18000f537`
- `KERNEL32!HeapFree` at `0x18000f574`
- `KERNEL32!HeapFree` at `0x18000f5b3`
- `KERNEL32!HeapFree` at `0x18000f5f0`
- `KERNEL32!HeapFree` at `0x18000f657`
- `KERNEL32!HeapFree` at `0x18000f68a`
- `KERNEL32!HeapFree` at `0x18000f6c2`
- `KERNEL32!HeapFree` at `0x18000f77e`
- `KERNEL32!GetLastError` at `0x18000f2e5`
- `KERNEL32!GetLastError` at `0x18000f2e5`
- `KERNEL32!DeleteCriticalSection` at `0x18000f45d`
- `KERNEL32!DeleteCriticalSection` at `0x18000f470`
- `KERNEL32!DeleteCriticalSection` at `0x18000f483`
- `KERNEL32!DeleteCriticalSection` at `0x18000f4a0`
- `KERNEL32!DeleteCriticalSection` at `0x18000f45d`
- `KERNEL32!DeleteCriticalSection` at `0x18000f470`
- `KERNEL32!DeleteCriticalSection` at `0x18000f483`
- `KERNEL32!DeleteCriticalSection` at `0x18000f4a0`
- `KERNEL32!CloseHandle` at `0x18000f40c`
- `KERNEL32!CloseHandle` at `0x18000f420`
- `KERNEL32!CloseHandle` at `0x18000f435`
- `KERNEL32!CloseHandle` at `0x18000f44a`
- `KERNEL32!CloseHandle` at `0x18000f40c`
- `KERNEL32!CloseHandle` at `0x18000f420`
- `KERNEL32!CloseHandle` at `0x18000f435`
- `KERNEL32!CloseHandle` at `0x18000f44a`
- `KERNEL32!SetLastError` at `0x18000f2c9`
- `KERNEL32!SetLastError` at `0x18000f6dc`
- `KERNEL32!SetLastError` at `0x18000f790`
- `KERNEL32!SetLastError` at `0x18000f2c9`
- `KERNEL32!SetLastError` at `0x18000f6dc`
- `KERNEL32!SetLastError` at `0x18000f790`
- `KERNEL32!GetProcessHeap` at `0x18000f370`
- `KERNEL32!GetProcessHeap` at `0x18000f4b8`
- `KERNEL32!GetProcessHeap` at `0x18000f4ef`
- `KERNEL32!GetProcessHeap` at `0x18000f523`
- `KERNEL32!GetProcessHeap` at `0x18000f560`
- `KERNEL32!GetProcessHeap` at `0x18000f59f`
- `KERNEL32!GetProcessHeap` at `0x18000f5dc`
- `KERNEL32!GetProcessHeap` at `0x18000f643`
- `KERNEL32!GetProcessHeap` at `0x18000f676`
- `KERNEL32!GetProcessHeap` at `0x18000f6ae`
- `KERNEL32!GetProcessHeap` at `0x18000f76a`
- `KERNEL32!GetProcessHeap` at `0x18000f370`
- `KERNEL32!GetProcessHeap` at `0x18000f4b8`
- `KERNEL32!GetProcessHeap` at `0x18000f4ef`
- `KERNEL32!GetProcessHeap` at `0x18000f523`
- `KERNEL32!GetProcessHeap` at `0x18000f560`
- `KERNEL32!GetProcessHeap` at `0x18000f59f`
- `KERNEL32!GetProcessHeap` at `0x18000f5dc`
- `KERNEL32!GetProcessHeap` at `0x18000f643`
- `KERNEL32!GetProcessHeap` at `0x18000f676`
- `KERNEL32!GetProcessHeap` at `0x18000f6ae`
- `KERNEL32!GetProcessHeap` at `0x18000f76a`

## pseudocode

```c
__int64 __fastcall WIMCloseImage(struct _RTL_CRITICAL_SECTION *a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  DWORD LastError; // ebp
  unsigned int v5; // eax
  HANDLE OwningThread; // rcx
  unsigned int v7; // r14d
  HANDLE LockSemaphore; // rcx
  struct _RTL_CRITICAL_SECTION *v9; // rax
  __int64 v10; // rcx
  void *v11; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE *p_LockSemaphore; // rdi
  void *SpinCount; // rcx
  HANDLE v15; // rcx
  void *v16; // rdi
  void *v17; // rcx
  HANDLE v18; // rcx
  struct _RTL_CRITICAL_SECTION *v19; // rcx
  void *v20; // rdi
  HANDLE v21; // rax
  HANDLE v22; // rdi
  HANDLE v23; // rax
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdi
  HANDLE v25; // rax
  int v26; // eax
  HANDLE v27; // rdi
  HANDLE v28; // rax
  int v29; // ecx
  HANDLE v30; // rdi
  HANDLE v31; // rax
  void *v32; // rdi
  HANDLE v33; // rax
  void *v34; // rcx
  PRTL_CRITICAL_SECTION_DEBUG v35; // rcx
  void *v36; // rcx
  HANDLE v37; // rdi
  HANDLE v38; // rax
  HANDLE v39; // rdi
  HANDLE v40; // rax
  void *v41; // rdi
  HANDLE v42; // rax
  void *v43; // rcx
  struct _RTL_CRITICAL_SECTION *v44; // rax
  int v45; // ecx
  _QWORD *p_DebugInfo; // rdx
  HANDLE v47; // rax

  v2 = 0;
  if ( a1 )
  {
    if ( LODWORD(a1->DebugInfo) == -17960958 )
    {
      v2 = *(struct _RTL_CRITICAL_SECTION **)&a1->LockCount;
    }
    else if ( LODWORD(a1->DebugInfo) == -17960959 )
    {
      v2 = a1;
    }
  }
  LastError = 0;
  if ( a1 )
  {
    if ( !(unsigned int)ProcessAddImagePathBeforeClose((_DWORD)a1) )
      LastError = GetLastError();
    v5 = WIMCommitImageChanges((_DWORD)a1);
    OwningThread = a1[5].OwningThread;
    v7 = v5;
    if ( OwningThread )
    {
      FreeWimHashTable(OwningThread, 0);
      a1[5].OwningThread = 0;
    }
    LockSemaphore = a1[5].LockSemaphore;
    if ( LockSemaphore )
    {
      FreeWimHashTable(LockSemaphore, 0);
      a1[5].LockSemaphore = 0;
    }
    if ( *(_QWORD *)&a1[5].LockCount )
    {
      v9 = a1;
      if ( a1[1].LockSemaphore )
        v9 = (struct _RTL_CRITICAL_SECTION *)a1[1].LockSemaphore;
      v10 = *(_QWORD *)&v9[5].LockCount;
      if ( v10 )
        FreeWimHashTable(v10, FreeRefIdNodeList);
    }
    if ( LODWORD(a1->DebugInfo) == -17960958 )
    {
      v11 = *(void **)&a1[8].LockCount;
      if ( v11 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v11);
      }
    }
    p_LockSemaphore = &a1[4].LockSemaphore;
    if ( a1 != (struct _RTL_CRITICAL_SECTION *)-184LL && *p_LockSemaphore )
    {
      FreeWimHashTable(*p_LockSemaphore, LZXFreeDecodeContext);
      *p_LockSemaphore = 0;
    }
    if ( a1[4].OwningThread )
    {
      FreeDirNode();
      a1[4].OwningThread = 0;
    }
    if ( !a1[1].LockSemaphore )
      FreeSecurityList(a1);
    if ( LODWORD(a1->DebugInfo) == -17960958 && a1[7].SpinCount )
    {
      SpinCount = 0;
      if ( LODWORD(a1->DebugInfo) == -17960958 )
        SpinCount = (void *)a1[7].SpinCount;
      ReleaseConfigFile(SpinCount);
    }
    v15 = a1[9].LockSemaphore;
    v16 = (void *)a1[9].SpinCount;
    if ( v15 )
      CloseHandle(v15);
    if ( v16 )
      CloseHandle(v16);
    v17 = *(void **)&a1[2].LockCount;
    if ( v17 )
      CloseHandle(v17);
    v18 = a1[2].OwningThread;
    if ( v18 )
      CloseHandle(v18);
    DeleteCriticalSection(a1 + 10);
    DeleteCriticalSection(a1 + 11);
    DeleteCriticalSection(a1 + 12);
    v19 = 0;
    if ( LODWORD(a1->DebugInfo) == -17960958 )
      v19 = a1 + 13;
    DeleteCriticalSection(v19);
    v20 = *(void **)&a1[6].LockCount;
    if ( v20 )
    {
      v21 = GetProcessHeap();
      if ( HeapFree(v21, 0, v20) )
        *(_QWORD *)&a1[6].LockCount = 0;
    }
    v22 = a1[6].OwningThread;
    if ( v22 )
    {
      v23 = GetProcessHeap();
      if ( HeapFree(v23, 0, v22) )
        a1[6].OwningThread = 0;
    }
    DebugInfo = a1[2].DebugInfo;
    if ( DebugInfo )
    {
      v25 = GetProcessHeap();
      HeapFree(v25, 0, DebugInfo);
    }
    v26 = (int)a1->DebugInfo;
    if ( LODWORD(a1->DebugInfo) == -17960958 )
    {
      v27 = a1[8].OwningThread;
      if ( v27 )
      {
        v28 = GetProcessHeap();
        HeapFree(v28, 0, v27);
        v26 = (int)a1->DebugInfo;
      }
    }
    v29 = v26;
    if ( v26 == -17960958 )
    {
      v30 = a1[8].LockSemaphore;
      if ( v30 )
      {
        v31 = GetProcessHeap();
        HeapFree(v31, 0, v30);
        v29 = (int)a1->DebugInfo;
      }
    }
    if ( v29 == -17960958 )
    {
      v32 = (void *)a1[8].SpinCount;
      if ( v32 )
      {
        v33 = GetProcessHeap();
        HeapFree(v33, 0, v32);
      }
    }
    v34 = (void *)a1[6].SpinCount;
    if ( v34 )
      FreeCompressionContext(v34);
    v35 = a1[7].DebugInfo;
    if ( v35 )
      FreeCompressionContext(v35);
    v36 = *(void **)&a1[7].LockCount;
    if ( v36 )
      FreeCompressionContext(v36);
    v37 = a1[7].OwningThread;
    if ( v37 )
    {
      ChunkWriterClose(a1[7].OwningThread);
      v38 = GetProcessHeap();
      HeapFree(v38, 0, v37);
      a1[7].OwningThread = 0;
    }
    v39 = a1[7].LockSemaphore;
    if ( v39 )
    {
      v40 = GetProcessHeap();
      HeapFree(v40, 0, v39);
      a1[7].LockSemaphore = 0;
    }
    if ( LODWORD(a1->DebugInfo) == -17960958 )
    {
      v41 = *(void **)&a1[4].LockCount;
      if ( v41 )
      {
        v42 = GetProcessHeap();
        HeapFree(v42, 0, v41);
        *(_QWORD *)&a1[4].LockCount = 0;
      }
    }
    else
    {
      SetLastError(6u);
    }
    v43 = 0;
    if ( LODWORD(a1->DebugInfo) == -17960958 )
      v43 = (void *)a1[5].SpinCount;
    FreeTempFileList(v43);
    v44 = 0;
    if ( v2 )
      v44 = (struct _RTL_CRITICAL_SECTION *)v2[14].OwningThread;
    if ( !a1[1].LockSemaphore && v44 )
    {
      if ( a1 == v44 )
      {
        if ( v2 )
          v2[14].OwningThread = v44[14].DebugInfo;
      }
      else
      {
        v45 = 1;
        do
        {
          if ( !v44 )
            break;
          p_DebugInfo = &v44[14].DebugInfo;
          v44 = (struct _RTL_CRITICAL_SECTION *)v44[14].DebugInfo;
          if ( v44 == a1 )
          {
            v44 = (struct _RTL_CRITICAL_SECTION *)v44[14].DebugInfo;
            v45 = 0;
            *p_DebugInfo = v44;
          }
        }
        while ( v45 );
      }
    }
    memset_0(a1, 0, 0x238u);
    v47 = GetProcessHeap();
    HeapFree(v47, 0, a1);
    if ( LastError )
      SetLastError(LastError);
    return v7;
  }
  else
  {
    SetLastError(6u);
    return 0;
  }
}

```

## disassembly

```asm
0x18000f278  mov     rax, rsp
0x18000f27b  mov     [rax+8], rbx
0x18000f27f  mov     [rax+10h], rbp
0x18000f283  mov     [rax+18h], rsi
0x18000f287  mov     [rax+20h], rdi
0x18000f28b  push    r12
0x18000f28d  push    r14
0x18000f28f  push    r15
0x18000f291  sub     rsp, 20h
0x18000f295  xor     r15d, r15d
0x18000f298  mov     rbx, rcx
0x18000f29b  mov     esi, r15d
0x18000f29e  mov     r12d, 0FEEDF002h
0x18000f2a4  test    rcx, rcx
0x18000f2a7  jz      short loc_18000F2BE
0x18000f2a9  cmp     [rcx], r12d
0x18000f2ac  jnz     short loc_18000F2B4
0x18000f2ae  mov     rsi, [rcx+8]
0x18000f2b2  jmp     short loc_18000F2BE
0x18000f2b4  cmp     dword ptr [rcx], 0FEEDF001h
0x18000f2ba  cmovz   rsi, rbx
0x18000f2be  mov     ebp, r15d
0x18000f2c1  test    rbx, rbx
0x18000f2c4  jnz     short loc_18000F2DC
0x18000f2c6  lea     ecx, [rbx+6]; dwErrCode
0x18000f2c9  call    cs:__imp_SetLastError
0x18000f2d0  nop     dword ptr [rax+rax+00h]
0x18000f2d5  xor     eax, eax
0x18000f2d7  jmp     loc_18000F79F
0x18000f2dc  call    ProcessAddImagePathBeforeClose
0x18000f2e1  test    eax, eax
0x18000f2e3  jnz     short loc_18000F2F3
0x18000f2e5  call    cs:__imp_GetLastError
0x18000f2ec  nop     dword ptr [rax+rax+00h]
0x18000f2f1  mov     ebp, eax
0x18000f2f3  mov     rcx, rbx
0x18000f2f6  call    WIMCommitImageChanges
0x18000f2fb  mov     rcx, [rbx+0D8h]
0x18000f302  mov     r14d, eax
0x18000f305  test    rcx, rcx
0x18000f308  jz      short loc_18000F318
0x18000f30a  xor     edx, edx
0x18000f30c  call    FreeWimHashTable
0x18000f311  mov     [rbx+0D8h], r15
0x18000f318  mov     rcx, [rbx+0E0h]
0x18000f31f  test    rcx, rcx
0x18000f322  jz      short loc_18000F332
0x18000f324  xor     edx, edx
0x18000f326  call    FreeWimHashTable
0x18000f32b  mov     [rbx+0E0h], r15
0x18000f332  cmp     [rbx+0D0h], r15
0x18000f339  jz      short loc_18000F35F
0x18000f33b  cmp     [rbx+40h], r15
0x18000f33f  mov     rax, rbx
0x18000f342  cmovnz  rax, [rbx+40h]
0x18000f347  mov     rcx, [rax+0D0h]
0x18000f34e  test    rcx, rcx
0x18000f351  jz      short loc_18000F35F
0x18000f353  lea     rdx, FreeRefIdNodeList
0x18000f35a  call    FreeWimHashTable
0x18000f35f  cmp     [rbx], r12d
0x18000f362  jnz     short loc_18000F390
0x18000f364  mov     rdi, [rbx+148h]
0x18000f36b  test    rdi, rdi
0x18000f36e  jz      short loc_18000F390
0x18000f370  call    cs:__imp_GetProcessHeap
0x18000f377  nop     dword ptr [rax+rax+00h]
0x18000f37c  mov     r8, rdi; lpMem
0x18000f37f  xor     edx, edx; dwFlags
0x18000f381  mov     rcx, rax; hHeap
0x18000f384  call    cs:__imp_HeapFree
0x18000f38b  nop     dword ptr [rax+rax+00h]
0x18000f390  lea     rdi, [rbx+0B8h]
0x18000f397  test    rdi, rdi
0x18000f39a  jz      short loc_18000F3B3
0x18000f39c  mov     rcx, [rdi]
0x18000f39f  test    rcx, rcx
0x18000f3a2  jz      short loc_18000F3B3
0x18000f3a4  lea     rdx, LZXFreeDecodeContext
0x18000f3ab  call    FreeWimHashTable
0x18000f3b0  mov     [rdi], r15
0x18000f3b3  mov     rcx, [rbx+0B0h]
0x18000f3ba  test    rcx, rcx
0x18000f3bd  jz      short loc_18000F3CB
0x18000f3bf  call    FreeDirNode
0x18000f3c4  mov     [rbx+0B0h], r15
0x18000f3cb  cmp     [rbx+40h], r15
0x18000f3cf  jnz     short loc_18000F3D9
0x18000f3d1  mov     rcx, rbx
0x18000f3d4  call    FreeSecurityList
0x18000f3d9  cmp     [rbx], r12d
0x18000f3dc  jnz     short loc_18000F3F9
0x18000f3de  mov     rax, [rbx+138h]
0x18000f3e5  test    rax, rax
0x18000f3e8  jz      short loc_18000F3F9
0x18000f3ea  cmp     [rbx], r12d
0x18000f3ed  mov     rcx, r15
0x18000f3f0  cmovz   rcx, rax; lpMem
0x18000f3f4  call    ReleaseConfigFile
0x18000f3f9  mov     rcx, [rbx+180h]; hObject
0x18000f400  mov     rdi, [rbx+188h]
0x18000f407  test    rcx, rcx
0x18000f40a  jz      short loc_18000F418
0x18000f40c  call    cs:__imp_CloseHandle
0x18000f413  nop     dword ptr [rax+rax+00h]
0x18000f418  test    rdi, rdi
0x18000f41b  jz      short loc_18000F42C
0x18000f41d  mov     rcx, rdi; hObject
0x18000f420  call    cs:__imp_CloseHandle
0x18000f427  nop     dword ptr [rax+rax+00h]
0x18000f42c  mov     rcx, [rbx+58h]; hObject
0x18000f430  test    rcx, rcx
0x18000f433  jz      short loc_18000F441
0x18000f435  call    cs:__imp_CloseHandle
0x18000f43c  nop     dword ptr [rax+rax+00h]
0x18000f441  mov     rcx, [rbx+60h]; hObject
0x18000f445  test    rcx, rcx
0x18000f448  jz      short loc_18000F456
0x18000f44a  call    cs:__imp_CloseHandle
0x18000f451  nop     dword ptr [rax+rax+00h]
0x18000f456  lea     rcx, [rbx+190h]; lpCriticalSection
0x18000f45d  call    cs:__imp_DeleteCriticalSection
0x18000f464  nop     dword ptr [rax+rax+00h]
0x18000f469  lea     rcx, [rbx+1B8h]; lpCriticalSection
0x18000f470  call    cs:__imp_DeleteCriticalSection
0x18000f477  nop     dword ptr [rax+rax+00h]
0x18000f47c  lea     rcx, [rbx+1E0h]; lpCriticalSection
0x18000f483  call    cs:__imp_DeleteCriticalSection
0x18000f48a  nop     dword ptr [rax+rax+00h]
0x18000f48f  cmp     [rbx], r12d
0x18000f492  lea     rax, [rbx+208h]
0x18000f499  mov     rcx, r15
0x18000f49c  cmovz   rcx, rax; lpCriticalSection
0x18000f4a0  call    cs:__imp_DeleteCriticalSection
0x18000f4a7  nop     dword ptr [rax+rax+00h]
0x18000f4ac  mov     rdi, [rbx+0F8h]
0x18000f4b3  test    rdi, rdi
0x18000f4b6  jz      short loc_18000F4E3
0x18000f4b8  call    cs:__imp_GetProcessHeap
0x18000f4bf  nop     dword ptr [rax+rax+00h]
0x18000f4c4  mov     r8, rdi; lpMem
0x18000f4c7  xor     edx, edx; dwFlags
0x18000f4c9  mov     rcx, rax; hHeap
0x18000f4cc  call    cs:__imp_HeapFree
0x18000f4d3  nop     dword ptr [rax+rax+00h]
0x18000f4d8  test    eax, eax
0x18000f4da  jz      short loc_18000F4E3
0x18000f4dc  mov     [rbx+0F8h], r15
0x18000f4e3  mov     rdi, [rbx+100h]
0x18000f4ea  test    rdi, rdi
0x18000f4ed  jz      short loc_18000F51A
0x18000f4ef  call    cs:__imp_GetProcessHeap
0x18000f4f6  nop     dword ptr [rax+rax+00h]
0x18000f4fb  mov     r8, rdi; lpMem
0x18000f4fe  xor     edx, edx; dwFlags
0x18000f500  mov     rcx, rax; hHeap
0x18000f503  call    cs:__imp_HeapFree
0x18000f50a  nop     dword ptr [rax+rax+00h]
0x18000f50f  test    eax, eax
0x18000f511  jz      short loc_18000F51A
0x18000f513  mov     [rbx+100h], r15
0x18000f51a  mov     rdi, [rbx+50h]
0x18000f51e  test    rdi, rdi
0x18000f521  jz      short loc_18000F543
0x18000f523  call    cs:__imp_GetProcessHeap
0x18000f52a  nop     dword ptr [rax+rax+00h]
0x18000f52f  mov     r8, rdi; lpMem
0x18000f532  xor     edx, edx; dwFlags
0x18000f534  mov     rcx, rax; hHeap
0x18000f537  call    cs:__imp_HeapFree
0x18000f53e  nop     dword ptr [rax+rax+00h]
0x18000f543  mov     eax, [rbx]
0x18000f545  cmp     eax, r12d
0x18000f548  jnz     short loc_18000F582
0x18000f54a  mov     rdi, [rbx+150h]
0x18000f551  test    rdi, rdi
0x18000f554  jz      short loc_18000F582
0x18000f556  cmp     eax, r12d
0x18000f559  jnz     short loc_18000F582
0x18000f55b  test    rdi, rdi
0x18000f55e  jz      short loc_18000F582
0x18000f560  call    cs:__imp_GetProcessHeap
0x18000f567  nop     dword ptr [rax+rax+00h]
0x18000f56c  mov     r8, rdi; lpMem
0x18000f56f  xor     edx, edx; dwFlags
0x18000f571  mov     rcx, rax; hHeap
0x18000f574  call    cs:__imp_HeapFree
0x18000f57b  nop     dword ptr [rax+rax+00h]
0x18000f580  mov     eax, [rbx]
0x18000f582  mov     ecx, eax
0x18000f584  cmp     eax, r12d
0x18000f587  jnz     short loc_18000F5C1
0x18000f589  mov     rdi, [rbx+158h]
0x18000f590  test    rdi, rdi
0x18000f593  jz      short loc_18000F5C1
0x18000f595  cmp     eax, r12d
0x18000f598  jnz     short loc_18000F5C1
0x18000f59a  test    rdi, rdi
0x18000f59d  jz      short loc_18000F5C1
0x18000f59f  call    cs:__imp_GetProcessHeap
0x18000f5a6  nop     dword ptr [rax+rax+00h]
0x18000f5ab  mov     r8, rdi; lpMem
0x18000f5ae  xor     edx, edx; dwFlags
0x18000f5b0  mov     rcx, rax; hHeap
0x18000f5b3  call    cs:__imp_HeapFree
0x18000f5ba  nop     dword ptr [rax+rax+00h]
0x18000f5bf  mov     ecx, [rbx]
0x18000f5c1  cmp     ecx, r12d
0x18000f5c4  jnz     short loc_18000F5FC
0x18000f5c6  mov     rdi, [rbx+160h]
0x18000f5cd  test    rdi, rdi
0x18000f5d0  jz      short loc_18000F5FC
0x18000f5d2  cmp     ecx, r12d
0x18000f5d5  jnz     short loc_18000F5FC
0x18000f5d7  test    rdi, rdi
0x18000f5da  jz      short loc_18000F5FC
0x18000f5dc  call    cs:__imp_GetProcessHeap
0x18000f5e3  nop     dword ptr [rax+rax+00h]
0x18000f5e8  mov     r8, rdi; lpMem
0x18000f5eb  xor     edx, edx; dwFlags
0x18000f5ed  mov     rcx, rax; hHeap
0x18000f5f0  call    cs:__imp_HeapFree
0x18000f5f7  nop     dword ptr [rax+rax+00h]
0x18000f5fc  mov     rcx, [rbx+110h]; lpMem
0x18000f603  test    rcx, rcx
0x18000f606  jz      short loc_18000F60D
0x18000f608  call    FreeCompressionContext
0x18000f60d  mov     rcx, [rbx+118h]; lpMem
0x18000f614  test    rcx, rcx
0x18000f617  jz      short loc_18000F61E
0x18000f619  call    FreeCompressionContext
0x18000f61e  mov     rcx, [rbx+120h]; lpMem
0x18000f625  test    rcx, rcx
0x18000f628  jz      short loc_18000F62F
0x18000f62a  call    FreeCompressionContext
0x18000f62f  mov     rdi, [rbx+128h]
0x18000f636  test    rdi, rdi
0x18000f639  jz      short loc_18000F66A
0x18000f63b  mov     rcx, rdi
0x18000f63e  call    ChunkWriterClose
0x18000f643  call    cs:__imp_GetProcessHeap
0x18000f64a  nop     dword ptr [rax+rax+00h]
0x18000f64f  mov     r8, rdi; lpMem
0x18000f652  xor     edx, edx; dwFlags
0x18000f654  mov     rcx, rax; hHeap
0x18000f657  call    cs:__imp_HeapFree
0x18000f65e  nop     dword ptr [rax+rax+00h]
0x18000f663  mov     [rbx+128h], r15
0x18000f66a  mov     rdi, [rbx+130h]
0x18000f671  test    rdi, rdi
0x18000f674  jz      short loc_18000F69D
0x18000f676  call    cs:__imp_GetProcessHeap
0x18000f67d  nop     dword ptr [rax+rax+00h]
0x18000f682  mov     r8, rdi; lpMem
0x18000f685  xor     edx, edx; dwFlags
0x18000f687  mov     rcx, rax; hHeap
0x18000f68a  call    cs:__imp_HeapFree
0x18000f691  nop     dword ptr [rax+rax+00h]
0x18000f696  mov     [rbx+130h], r15
0x18000f69d  cmp     [rbx], r12d
0x18000f6a0  jnz     short loc_18000F6D7
0x18000f6a2  mov     rdi, [rbx+0A8h]
0x18000f6a9  test    rdi, rdi
0x18000f6ac  jz      short loc_18000F6E8
0x18000f6ae  call    cs:__imp_GetProcessHeap
0x18000f6b5  nop     dword ptr [rax+rax+00h]
0x18000f6ba  mov     r8, rdi; lpMem
0x18000f6bd  xor     edx, edx; dwFlags
0x18000f6bf  mov     rcx, rax; hHeap
0x18000f6c2  call    cs:__imp_HeapFree
0x18000f6c9  nop     dword ptr [rax+rax+00h]
0x18000f6ce  mov     [rbx+0A8h], r15
0x18000f6d5  jmp     short loc_18000F6E8
0x18000f6d7  mov     ecx, 6; dwErrCode
0x18000f6dc  call    cs:__imp_SetLastError
0x18000f6e3  nop     dword ptr [rax+rax+00h]
0x18000f6e8  mov     rcx, r15
0x18000f6eb  cmp     [rbx], r12d
0x18000f6ee  jnz     short loc_18000F6F7
0x18000f6f0  mov     rcx, [rbx+0E8h]; lpMem
0x18000f6f7  call    FreeTempFileList
0x18000f6fc  mov     rax, r15
0x18000f6ff  test    rsi, rsi
0x18000f702  jz      short loc_18000F70B
0x18000f704  mov     rax, [rsi+240h]
0x18000f70b  cmp     [rbx+40h], r15
0x18000f70f  jnz     short loc_18000F75A
0x18000f711  test    rax, rax
0x18000f714  jz      short loc_18000F75A
0x18000f716  cmp     rbx, rax
0x18000f719  jnz     short loc_18000F730
0x18000f71b  test    rsi, rsi
0x18000f71e  jz      short loc_18000F75A
0x18000f720  mov     rax, [rax+230h]
0x18000f727  mov     [rsi+240h], rax
0x18000f72e  jmp     short loc_18000F75A
0x18000f730  mov     ecx, 1
0x18000f735  test    rax, rax
0x18000f738  jz      short loc_18000F75A
0x18000f73a  lea     rdx, [rax+230h]
  ... truncated ...
```
