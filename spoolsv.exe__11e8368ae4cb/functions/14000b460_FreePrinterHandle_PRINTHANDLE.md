# FreePrinterHandle(_PRINTHANDLE *)

- ea: `0x14000b460`
- end: `0x14000b59a`
- name: `?FreePrinterHandle@@YAXPEAU_PRINTHANDLE@@@Z`
- size: `314`
- prototype: `void __fastcall(struct _PRINTHANDLE *)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x140004708`
- `0x140004e90`
- `0x14000c510`
- `0x14000f120`
- `0x14001112c`

## callees

- `0x14000b460`
- `0x140066ca8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000b4bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000b4bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000b47a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000b47a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b4f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b58b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b4f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b50a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b58b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b557`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b557`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000b562`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000b562`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14000b578`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14000b578`

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
0x14000b460  test    rcx, rcx
0x14000b463  jnz     short loc_14000B466
0x14000b465  retn
0x14000b466  push    rbx
0x14000b467  sub     rsp, 20h
0x14000b46b  mov     rbx, rcx
0x14000b46e  mov     [rsp+28h+arg_0], rdi
0x14000b473  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000b47a  call    cs:__imp_EnterCriticalSection
0x14000b480  mov     rax, [rbx+20h]
0x14000b484  xor     edi, edi
0x14000b486  test    rax, rax
0x14000b489  jnz     loc_14000B53B
0x14000b48f  mov     rax, cs:?pPrintHandleReplyList@@3PEAU_PRINTHANDLE@@EA; _PRINTHANDLE * pPrintHandleReplyList
0x14000b496  mov     [rbx+30h], edi
0x14000b499  mov     [rbx+50h], edi
0x14000b49c  cmp     rax, rbx
0x14000b49f  jz      short loc_14000B511
0x14000b4a1  test    rax, rax
0x14000b4a4  jnz     short loc_14000B51E
0x14000b4a6  cmp     [rbx+18h], rdi
0x14000b4aa  lea     rcx, [rbx+18h]; struct _CHANGE **
0x14000b4ae  jnz     loc_14000B54D
0x14000b4b4  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000b4bb  call    cs:__imp_LeaveCriticalSection
0x14000b4c1  mov     rcx, [rbx+38h]; hObject
0x14000b4c5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000b4c9  jnz     loc_14000B557
0x14000b4cf  mov     rcx, [rbx+40h]; lpFileName
0x14000b4d3  test    rcx, rcx
0x14000b4d6  jnz     loc_14000B562
0x14000b4dc  mov     r8, [rbx+48h]; lpMem
0x14000b4e0  mov     rdi, [rsp+28h+arg_0]
0x14000b4e5  test    r8, r8
0x14000b4e8  jz      short loc_14000B4F9
0x14000b4ea  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14000b4f1  xor     edx, edx; dwFlags
0x14000b4f3  call    cs:__imp_HeapFree
0x14000b4f9  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; void * g_hSpoolssHeap
0x14000b500  mov     r8, rbx
0x14000b503  xor     edx, edx
0x14000b505  add     rsp, 20h
0x14000b509  pop     rbx
0x14000b50a  jmp     cs:__imp_HeapFree
0x14000b511  mov     rax, [rbx+28h]
0x14000b515  mov     cs:?pPrintHandleReplyList@@3PEAU_PRINTHANDLE@@EA, rax; _PRINTHANDLE * pPrintHandleReplyList
0x14000b51c  jmp     short loc_14000B4A6
0x14000b51e  lea     rcx, [rax+28h]
0x14000b522  mov     rax, [rax+28h]
0x14000b526  cmp     rax, rbx
0x14000b529  jnz     loc_14000B4A1
0x14000b52f  mov     rax, [rbx+28h]
0x14000b533  mov     [rcx], rax
0x14000b536  jmp     loc_14000B4A6
0x14000b53b  mov     [rax+8], rdi
0x14000b53f  mov     rax, [rax+10h]
0x14000b543  test    rax, rax
0x14000b546  jnz     short loc_14000B53B
0x14000b548  jmp     loc_14000B48F
0x14000b54d  call    ?FreeChange@@YAHPEAPEAU_CHANGE@@@Z; FreeChange(_CHANGE * *)
0x14000b552  jmp     loc_14000B4B4
0x14000b557  call    cs:__imp_CloseHandle
0x14000b55d  jmp     loc_14000B4CF
0x14000b562  call    cs:__imp_DeleteFileW
0x14000b568  test    eax, eax
0x14000b56a  jnz     short loc_14000B57E
0x14000b56c  mov     rcx, [rbx+40h]; lpExistingFileName
0x14000b570  xor     edx, edx; lpNewFileName
0x14000b572  mov     r8d, 4; dwFlags
0x14000b578  call    cs:__imp_MoveFileExW
0x14000b57e  mov     r8, [rbx+40h]; lpMem
0x14000b582  xor     edx, edx; dwFlags
0x14000b584  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14000b58b  call    cs:__imp_HeapFree
0x14000b591  mov     [rbx+40h], rdi
0x14000b595  jmp     loc_14000B4DC
```
