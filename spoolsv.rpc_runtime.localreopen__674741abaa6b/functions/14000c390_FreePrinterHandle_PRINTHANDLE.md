# FreePrinterHandle(_PRINTHANDLE *)

- ea: `0x14000c390`
- end: `0x14000c505`
- name: `?FreePrinterHandle@@YAXPEAU_PRINTHANDLE@@@Z`
- size: `373`
- prototype: `void __fastcall(struct _PRINTHANDLE *)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x140004e08`
- `0x140005630`
- `0x14000d7e0`
- `0x1400103d0`
- `0x140012518`

## callees

- `0x14000c390`
- `0x14006d350`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000c3fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000c3fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000c3ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000c3ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c438`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c4f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c438`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c455`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c4f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c4aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c4aa`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000c4bb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000c4bb`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14000c4d7`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14000c4d7`

## pseudocode

```c
void __fastcall FreePrinterHandle(struct _PRINTHANDLE *a1)
{
  __int64 i; // rax
  struct _PRINTHANDLE *v3; // rax
  void *v4; // rcx
  const WCHAR *v5; // rcx
  void *v6; // r8
  _QWORD *v7; // rcx

  if ( a1 )
  {
    EnterCriticalSection(&RouterNotifySection);
    for ( i = *((_QWORD *)a1 + 4); i; i = *(_QWORD *)(i + 16) )
      *(_QWORD *)(i + 8) = 0;
    v3 = pPrintHandleReplyList;
    *((_DWORD *)a1 + 12) = 0;
    *((_DWORD *)a1 + 20) = 0;
    if ( v3 == a1 )
    {
      pPrintHandleReplyList = (struct _PRINTHANDLE *)*((_QWORD *)a1 + 5);
    }
    else
    {
      while ( v3 )
      {
        v7 = (_QWORD *)((char *)v3 + 40);
        v3 = (struct _PRINTHANDLE *)*((_QWORD *)v3 + 5);
        if ( v3 == a1 )
        {
          *v7 = *((_QWORD *)a1 + 5);
          break;
        }
      }
    }
    if ( *((_QWORD *)a1 + 3) )
      FreeChange((struct _CHANGE **)a1 + 3);
    LeaveCriticalSection(&RouterNotifySection);
    v4 = (void *)*((_QWORD *)a1 + 7);
    if ( v4 != (void *)-1LL )
      CloseHandle(v4);
    v5 = (const WCHAR *)*((_QWORD *)a1 + 8);
    if ( v5 )
    {
      if ( !DeleteFileW(v5) )
        MoveFileExW(*((LPCWSTR *)a1 + 8), 0, 4u);
      HeapFree(g_hSpoolssHeap, 0, *((LPVOID *)a1 + 8));
      *((_QWORD *)a1 + 8) = 0;
    }
    v6 = (void *)*((_QWORD *)a1 + 9);
    if ( v6 )
      HeapFree(g_hSpoolssHeap, 0, v6);
    HeapFree(g_hSpoolssHeap, 0, a1);
  }
}

```

## disassembly

```asm
0x14000c390  test    rcx, rcx
0x14000c393  jnz     short loc_14000C397
0x14000c395  retn
0x14000c397  push    rbx
0x14000c398  sub     rsp, 20h
0x14000c39c  mov     rbx, rcx
0x14000c39f  mov     [rsp+28h+arg_0], rdi
0x14000c3a4  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000c3ab  call    cs:__imp_EnterCriticalSection
0x14000c3b2  nop     dword ptr [rax+rax+00h]
0x14000c3b7  mov     rax, [rbx+20h]
0x14000c3bb  xor     edi, edi
0x14000c3bd  test    rax, rax
0x14000c3c0  jnz     loc_14000C48E
0x14000c3c6  mov     rax, cs:?pPrintHandleReplyList@@3PEAU_PRINTHANDLE@@EA; _PRINTHANDLE * pPrintHandleReplyList
0x14000c3cd  mov     [rbx+30h], edi
0x14000c3d0  mov     [rbx+50h], edi
0x14000c3d3  cmp     rax, rbx
0x14000c3d6  jz      loc_14000C461
0x14000c3dc  test    rax, rax
0x14000c3df  jnz     loc_14000C471
0x14000c3e5  cmp     [rbx+18h], rdi
0x14000c3e9  lea     rcx, [rbx+18h]; struct _CHANGE **
0x14000c3ed  jnz     loc_14000C4A0
0x14000c3f3  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000c3fa  call    cs:__imp_LeaveCriticalSection
0x14000c401  nop     dword ptr [rax+rax+00h]
0x14000c406  mov     rcx, [rbx+38h]; hObject
0x14000c40a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000c40e  jnz     loc_14000C4AA
0x14000c414  mov     rcx, [rbx+40h]; lpFileName
0x14000c418  test    rcx, rcx
0x14000c41b  jnz     loc_14000C4BB
0x14000c421  mov     r8, [rbx+48h]; lpMem
0x14000c425  mov     rdi, [rsp+28h+arg_0]
0x14000c42a  test    r8, r8
0x14000c42d  jz      short loc_14000C444
0x14000c42f  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14000c436  xor     edx, edx; dwFlags
0x14000c438  call    cs:__imp_HeapFree
0x14000c43f  nop     dword ptr [rax+rax+00h]
0x14000c444  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; void * g_hSpoolssHeap
0x14000c44b  mov     r8, rbx
0x14000c44e  xor     edx, edx
0x14000c450  add     rsp, 20h
0x14000c454  pop     rbx
0x14000c455  jmp     cs:__imp_HeapFree
0x14000c461  mov     rax, [rbx+28h]
0x14000c465  mov     cs:?pPrintHandleReplyList@@3PEAU_PRINTHANDLE@@EA, rax; _PRINTHANDLE * pPrintHandleReplyList
0x14000c46c  jmp     loc_14000C3E5
0x14000c471  lea     rcx, [rax+28h]
0x14000c475  mov     rax, [rax+28h]
0x14000c479  cmp     rax, rbx
0x14000c47c  jnz     loc_14000C3DC
0x14000c482  mov     rax, [rbx+28h]
0x14000c486  mov     [rcx], rax
0x14000c489  jmp     loc_14000C3E5
0x14000c48e  mov     [rax+8], rdi
0x14000c492  mov     rax, [rax+10h]
0x14000c496  test    rax, rax
0x14000c499  jnz     short loc_14000C48E
0x14000c49b  jmp     loc_14000C3C6
0x14000c4a0  call    ?FreeChange@@YAHPEAPEAU_CHANGE@@@Z; FreeChange(_CHANGE * *)
0x14000c4a5  jmp     loc_14000C3F3
0x14000c4aa  call    cs:__imp_CloseHandle
0x14000c4b1  nop     dword ptr [rax+rax+00h]
0x14000c4b6  jmp     loc_14000C414
0x14000c4bb  call    cs:__imp_DeleteFileW
0x14000c4c2  nop     dword ptr [rax+rax+00h]
0x14000c4c7  test    eax, eax
0x14000c4c9  jnz     short loc_14000C4E3
0x14000c4cb  mov     rcx, [rbx+40h]; lpExistingFileName
0x14000c4cf  xor     edx, edx; lpNewFileName
0x14000c4d1  mov     r8d, 4; dwFlags
0x14000c4d7  call    cs:__imp_MoveFileExW
0x14000c4de  nop     dword ptr [rax+rax+00h]
0x14000c4e3  mov     r8, [rbx+40h]; lpMem
0x14000c4e7  xor     edx, edx; dwFlags
0x14000c4e9  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14000c4f0  call    cs:__imp_HeapFree
0x14000c4f7  nop     dword ptr [rax+rax+00h]
0x14000c4fc  mov     [rbx+40h], rdi
0x14000c500  jmp     loc_14000C421
```
