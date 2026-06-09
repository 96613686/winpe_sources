# SplCloseSpoolFileHandle

- ea: `0x1400664b0`
- end: `0x14006659f`
- name: `SplCloseSpoolFileHandle`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callers

- `0x140034fb0`

## callees

- `0x14000f600`
- `0x1400161d0`
- `0x1400664b0`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140066565`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140066565`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140066585`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140066585`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400664fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400664fe`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140066525`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140066525`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14006653f`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14006653f`

## pseudocode

```c
__int64 __fastcall SplCloseSpoolFileHandle(__int64 a1)
{
  void *v3; // rcx
  bool v4; // zf
  HANDLE v5; // rdi

  if ( a1 && *(_DWORD *)a1 == 24672 )
  {
    if ( *(struct _PROVIDOR **)(a1 + 8) == pLocalProvidor )
    {
      return (*((__int64 (__fastcall **)(_QWORD))pLocalProvidor + 86))(*(_QWORD *)(a1 + 16));
    }
    else
    {
      v3 = *(void **)(a1 + 56);
      if ( v3 != (void *)-1LL )
      {
        CloseHandle(v3);
        v4 = *(_QWORD *)(a1 + 64) == 0;
        *(_QWORD *)(a1 + 56) = -1;
        if ( !v4 )
        {
          v5 = RevertToPrinterSelf();
          if ( !DeleteFileW(*(LPCWSTR *)(a1 + 64)) )
            MoveFileExW(*(LPCWSTR *)(a1 + 64), 0, 4u);
          if ( v5 )
            ImpersonatePrinterClient(v5);
          HeapFree(g_hSpoolssHeap, 0, *(LPVOID *)(a1 + 64));
          *(_QWORD *)(a1 + 64) = 0;
        }
      }
      return 1;
    }
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
0x1400664b0  mov     [rsp+arg_0], rbx
0x1400664b5  push    rdi
0x1400664b6  sub     rsp, 20h
0x1400664ba  mov     rbx, rcx
0x1400664bd  test    rcx, rcx
0x1400664c0  jz      loc_140066580
0x1400664c6  cmp     dword ptr [rcx], 6060h
0x1400664cc  jnz     loc_140066580
0x1400664d2  mov     rax, cs:?pLocalProvidor@@3PEAU_PROVIDOR@@EA; _PROVIDOR * pLocalProvidor
0x1400664d9  cmp     [rcx+8], rax
0x1400664dd  jnz     short loc_1400664F4
0x1400664df  mov     rcx, [rcx+10h]
0x1400664e3  mov     rax, [rax+2B0h]
0x1400664ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400664ef  jmp     loc_140066593
0x1400664f4  mov     rcx, [rcx+38h]; hObject
0x1400664f8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400664fc  jz      short loc_140066579
0x1400664fe  call    cs:__imp_CloseHandle
0x140066505  nop     dword ptr [rax+rax+00h]
0x14006650a  cmp     qword ptr [rbx+40h], 0
0x14006650f  mov     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x140066517  jz      short loc_140066579
0x140066519  call    RevertToPrinterSelf
0x14006651e  mov     rcx, [rbx+40h]; lpFileName
0x140066522  mov     rdi, rax
0x140066525  call    cs:__imp_DeleteFileW
0x14006652c  nop     dword ptr [rax+rax+00h]
0x140066531  test    eax, eax
0x140066533  jnz     short loc_14006654B
0x140066535  mov     rcx, [rbx+40h]; lpExistingFileName
0x140066539  lea     r8d, [rax+4]; dwFlags
0x14006653d  xor     edx, edx; lpNewFileName
0x14006653f  call    cs:__imp_MoveFileExW
0x140066546  nop     dword ptr [rax+rax+00h]
0x14006654b  test    rdi, rdi
0x14006654e  jz      short loc_140066558
0x140066550  mov     rcx, rdi; hToken
0x140066553  call    ImpersonatePrinterClient
0x140066558  mov     r8, [rbx+40h]; lpMem
0x14006655c  xor     edx, edx; dwFlags
0x14006655e  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140066565  call    cs:__imp_HeapFree
0x14006656c  nop     dword ptr [rax+rax+00h]
0x140066571  mov     qword ptr [rbx+40h], 0
0x140066579  mov     eax, 1
0x14006657e  jmp     short loc_140066593
0x140066580  mov     ecx, 6; dwErrCode
0x140066585  call    cs:__imp_SetLastError
0x14006658c  nop     dword ptr [rax+rax+00h]
0x140066591  xor     eax, eax
0x140066593  mov     rbx, [rsp+28h+arg_0]
0x140066598  add     rsp, 20h
0x14006659c  pop     rdi
0x14006659d  retn
```
