# mtx_do_lock

- ea: `0x14001a620`
- end: `0x14001a6a9`
- name: `mtx_do_lock`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001a5d8`

## callees

- `0x14001a620`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001a64f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001a66c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001a64f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001a66c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001a62d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001a62d`

## pseudocode

```c
__int64 __fastcall mtx_do_lock(__int64 a1)
{
  DWORD CurrentThreadId; // eax
  DWORD v3; // edi
  int v4; // ecx

  CurrentThreadId = GetCurrentThreadId();
  v3 = CurrentThreadId;
  if ( (*(_DWORD *)a1 & 0xFFFFFEFF) == 1 )
  {
    if ( *(_DWORD *)(a1 + 72) != CurrentThreadId )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 16));
      *(_DWORD *)(a1 + 72) = v3;
    }
    ++*(_DWORD *)(a1 + 76);
  }
  else
  {
    if ( *(_DWORD *)(a1 + 72) != CurrentThreadId )
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 16));
    v4 = *(_DWORD *)(a1 + 76);
    *(_DWORD *)(a1 + 76) = v4 + 1;
    if ( v4 + 1 <= 1 )
    {
      *(_DWORD *)(a1 + 72) = v3;
    }
    else if ( (*(_DWORD *)a1 & 0x100) == 0 )
    {
      *(_DWORD *)(a1 + 76) = v4;
      return 3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14001a620  mov     [rsp+arg_0], rbx
0x14001a625  push    rdi
0x14001a626  sub     rsp, 20h
0x14001a62a  mov     rbx, rcx
0x14001a62d  call    cs:__imp_GetCurrentThreadId
0x14001a634  nop     dword ptr [rax+rax+00h]
0x14001a639  mov     edx, [rbx]
0x14001a63b  mov     edi, eax
0x14001a63d  btr     edx, 8
0x14001a641  cmp     edx, 1
0x14001a644  jnz     short loc_14001A663
0x14001a646  cmp     [rbx+48h], eax
0x14001a649  jz      short loc_14001A65E
0x14001a64b  lea     rcx, [rbx+10h]; SRWLock
0x14001a64f  call    cs:__imp_AcquireSRWLockExclusive
0x14001a656  nop     dword ptr [rax+rax+00h]
0x14001a65b  mov     [rbx+48h], edi
0x14001a65e  inc     dword ptr [rbx+4Ch]
0x14001a661  jmp     short loc_14001A69B
0x14001a663  cmp     [rbx+48h], edi
0x14001a666  jz      short loc_14001A678
0x14001a668  lea     rcx, [rbx+10h]; SRWLock
0x14001a66c  call    cs:__imp_AcquireSRWLockExclusive
0x14001a673  nop     dword ptr [rax+rax+00h]
0x14001a678  mov     ecx, [rbx+4Ch]
0x14001a67b  lea     eax, [rcx+1]
0x14001a67e  mov     [rbx+4Ch], eax
0x14001a681  cmp     eax, 1
0x14001a684  jle     short loc_14001A698
0x14001a686  test    dword ptr [rbx], 100h
0x14001a68c  jnz     short loc_14001A69B
0x14001a68e  mov     [rbx+4Ch], ecx
0x14001a691  mov     eax, 3
0x14001a696  jmp     short loc_14001A69D
0x14001a698  mov     [rbx+48h], edi
0x14001a69b  xor     eax, eax
0x14001a69d  mov     rbx, [rsp+28h+arg_0]
0x14001a6a2  add     rsp, 20h
0x14001a6a6  pop     rdi
0x14001a6a7  retn
```
