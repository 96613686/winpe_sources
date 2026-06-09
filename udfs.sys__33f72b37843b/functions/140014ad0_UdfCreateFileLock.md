# UdfCreateFileLock

- ea: `0x140014ad0`
- end: `0x140014bff`
- name: `UdfCreateFileLock`
- size: `303`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140036c38`
- `0x140057c30`

## callees

- `0x140014ad0`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x140014bde`
- `ntoskrnl!ExRaiseStatus` at `0x140014bde`
- `ntoskrnl!ExAcquireFastMutex` at `0x140014b09`
- `ntoskrnl!ExAcquireFastMutex` at `0x140014b09`
- `ntoskrnl!ExReleaseFastMutex` at `0x140014b6a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140014bbf`
- `ntoskrnl!ExReleaseFastMutex` at `0x140014b6a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140014bbf`
- `ntoskrnl!FsRtlAllocateFileLock` at `0x140014b7c`
- `ntoskrnl!FsRtlAllocateFileLock` at `0x140014b7c`

## pseudocode

```c
char __fastcall UdfCreateFileLock(__int64 a1, __int64 a2, char a3)
{
  struct _KTHREAD *CurrentThread; // rdi
  __int64 v5; // rcx
  char v8; // di
  __int64 v9; // rax
  PFILE_LOCK FileLock; // rax
  __int64 v11; // rcx
  PFILE_LOCK v12; // rsi
  __int64 v13; // rax

  CurrentThread = KeGetCurrentThread();
  v5 = *(_QWORD *)(a2 + 136);
  if ( CurrentThread != *(struct _KTHREAD **)(v5 + 64) )
  {
    ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v5 + 80) + 216LL));
    *(_QWORD *)(*(_QWORD *)(a2 + 136) + 64LL) = CurrentThread;
  }
  v8 = 1;
  ++*(_DWORD *)(*(_QWORD *)(a2 + 136) + 72LL);
  if ( *(_QWORD *)(a2 + 504) )
  {
    --*(_DWORD *)(*(_QWORD *)(a2 + 136) + 72LL);
    v9 = *(_QWORD *)(a2 + 136);
    if ( !*(_DWORD *)(v9 + 72) )
    {
      *(_QWORD *)(v9 + 64) = 0;
      ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(a2 + 136) + 80LL) + 216LL));
    }
  }
  else
  {
    FileLock = FsRtlAllocateFileLock(0, 0);
    v11 = *(_QWORD *)(a2 + 136);
    v12 = FileLock;
    *(_QWORD *)(a2 + 504) = FileLock;
    --*(_DWORD *)(v11 + 72);
    v13 = *(_QWORD *)(a2 + 136);
    if ( !*(_DWORD *)(v13 + 72) )
    {
      *(_QWORD *)(v13 + 64) = 0;
      ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(a2 + 136) + 80LL) + 216LL));
    }
    if ( !v12 )
    {
      if ( a3 )
      {
        *(_DWORD *)(a1 + 24) = -1073741670;
        ExRaiseStatus(-1073741670);
      }
      return 0;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x140014ad0  push    rbx
0x140014ad2  push    rbp
0x140014ad3  push    rsi
0x140014ad4  push    rdi
0x140014ad5  push    r12
0x140014ad7  push    r14
0x140014ad9  sub     rsp, 28h
0x140014add  mov     rdi, gs:188h
0x140014ae6  mov     r14, rcx
0x140014ae9  mov     rcx, [rdx+88h]
0x140014af0  mov     bpl, r8b
0x140014af3  mov     rbx, rdx
0x140014af6  mov     r12d, 0D8h
0x140014afc  cmp     rdi, [rcx+40h]
0x140014b00  jz      short loc_140014B20
0x140014b02  mov     rcx, [rcx+50h]
0x140014b06  add     rcx, r12; FastMutex
0x140014b09  call    cs:__imp_ExAcquireFastMutex
0x140014b10  nop     dword ptr [rax+rax+00h]
0x140014b15  mov     rax, [rbx+88h]
0x140014b1c  mov     [rax+40h], rdi
0x140014b20  mov     rax, [rbx+88h]
0x140014b27  mov     edi, 1
0x140014b2c  add     [rax+48h], edi
0x140014b2f  cmp     qword ptr [rbx+1F8h], 0
0x140014b37  jz      short loc_140014B78
0x140014b39  mov     rcx, [rbx+88h]
0x140014b40  dec     dword ptr [rcx+48h]
0x140014b43  mov     rax, [rbx+88h]
0x140014b4a  cmp     dword ptr [rax+48h], 0
0x140014b4e  jnz     loc_140014BEE
0x140014b54  mov     qword ptr [rax+40h], 0
0x140014b5c  mov     rcx, [rbx+88h]
0x140014b63  mov     rcx, [rcx+50h]
0x140014b67  add     rcx, r12; FastMutex
0x140014b6a  call    cs:__imp_ExReleaseFastMutex
0x140014b71  nop     dword ptr [rax+rax+00h]
0x140014b76  jmp     short loc_140014BEE
0x140014b78  xor     edx, edx; UnlockRoutine
0x140014b7a  xor     ecx, ecx; CompleteLockIrpRoutine
0x140014b7c  call    cs:__imp_FsRtlAllocateFileLock
0x140014b83  nop     dword ptr [rax+rax+00h]
0x140014b88  mov     rcx, [rbx+88h]
0x140014b8f  mov     rsi, rax
0x140014b92  mov     [rbx+1F8h], rax
0x140014b99  dec     dword ptr [rcx+48h]
0x140014b9c  mov     rax, [rbx+88h]
0x140014ba3  cmp     dword ptr [rax+48h], 0
0x140014ba7  jnz     short loc_140014BCB
0x140014ba9  mov     qword ptr [rax+40h], 0
0x140014bb1  mov     rcx, [rbx+88h]
0x140014bb8  mov     rcx, [rcx+50h]
0x140014bbc  add     rcx, r12; FastMutex
0x140014bbf  call    cs:__imp_ExReleaseFastMutex
0x140014bc6  nop     dword ptr [rax+rax+00h]
0x140014bcb  test    rsi, rsi
0x140014bce  jnz     short loc_140014BEE
0x140014bd0  test    bpl, bpl
0x140014bd3  jz      short loc_140014BEB
0x140014bd5  mov     ecx, 0C000009Ah; Status
0x140014bda  mov     [r14+18h], ecx
0x140014bde  call    cs:__imp_ExRaiseStatus
0x140014beb  xor     dil, dil
0x140014bee  mov     al, dil
0x140014bf1  add     rsp, 28h
0x140014bf5  pop     r14
0x140014bf7  pop     r12
0x140014bf9  pop     rdi
0x140014bfa  pop     rsi
0x140014bfb  pop     rbp
0x140014bfc  pop     rbx
0x140014bfd  retn
```
