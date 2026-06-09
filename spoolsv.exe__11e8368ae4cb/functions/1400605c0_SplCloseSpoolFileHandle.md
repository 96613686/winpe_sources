# SplCloseSpoolFileHandle

- ea: `0x1400605c0`
- end: `0x140060690`
- name: `SplCloseSpoolFileHandle`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callers

- `0x140032660`

## callees

- `0x14000e590`
- `0x140014eb0`
- `0x1400605c0`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140060663`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140060663`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006067d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006067d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006060e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006060e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14006062f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14006062f`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140060643`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140060643`

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
0x1400605c0  mov     [rsp+arg_0], rbx
0x1400605c5  push    rdi
0x1400605c6  sub     rsp, 20h
0x1400605ca  mov     rbx, rcx
0x1400605cd  test    rcx, rcx
0x1400605d0  jz      loc_140060678
0x1400605d6  cmp     dword ptr [rcx], 6060h
0x1400605dc  jnz     loc_140060678
0x1400605e2  mov     rax, cs:?pLocalProvidor@@3PEAU_PROVIDOR@@EA; _PROVIDOR * pLocalProvidor
0x1400605e9  cmp     [rcx+8], rax
0x1400605ed  jnz     short loc_140060604
0x1400605ef  mov     rcx, [rcx+10h]
0x1400605f3  mov     rax, [rax+2B0h]
0x1400605fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400605ff  jmp     loc_140060685
0x140060604  mov     rcx, [rcx+38h]; hObject
0x140060608  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14006060c  jz      short loc_140060671
0x14006060e  call    cs:__imp_CloseHandle
0x140060614  cmp     qword ptr [rbx+40h], 0
0x140060619  mov     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x140060621  jz      short loc_140060671
0x140060623  call    RevertToPrinterSelf
0x140060628  mov     rcx, [rbx+40h]; lpFileName
0x14006062c  mov     rdi, rax
0x14006062f  call    cs:__imp_DeleteFileW
0x140060635  test    eax, eax
0x140060637  jnz     short loc_140060649
0x140060639  mov     rcx, [rbx+40h]; lpExistingFileName
0x14006063d  lea     r8d, [rax+4]; dwFlags
0x140060641  xor     edx, edx; lpNewFileName
0x140060643  call    cs:__imp_MoveFileExW
0x140060649  test    rdi, rdi
0x14006064c  jz      short loc_140060656
0x14006064e  mov     rcx, rdi; hToken
0x140060651  call    ImpersonatePrinterClient
0x140060656  mov     r8, [rbx+40h]; lpMem
0x14006065a  xor     edx, edx; dwFlags
0x14006065c  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140060663  call    cs:__imp_HeapFree
0x140060669  mov     qword ptr [rbx+40h], 0
0x140060671  mov     eax, 1
0x140060676  jmp     short loc_140060685
0x140060678  mov     ecx, 6; dwErrCode
0x14006067d  call    cs:__imp_SetLastError
0x140060683  xor     eax, eax
0x140060685  mov     rbx, [rsp+28h+arg_0]
0x14006068a  add     rsp, 20h
0x14006068e  pop     rdi
0x14006068f  retn
```
