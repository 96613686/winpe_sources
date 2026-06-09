# mtx_do_lock

- ea: `0x180042e48`
- end: `0x180042ebe`
- name: `mtx_do_lock`
- size: `118`
- prototype: `__int64(void)`
- caller_count: `56`
- callee_count: `1`
- tags: ``

## callers

- `0x180011db0`
- `0x180014650`
- `0x180016f70`
- `0x180017760`
- `0x180017a70`
- `0x180017d74`
- `0x18001841c`
- `0x1800187f0`
- `0x18001c098`
- `0x18001d440`
- `0x18001d590`
- `0x18001d960`
- `0x18001dab0`
- `0x18001dc10`
- `0x18001dd60`
- `0x18001e6b0`
- `0x18001e8f0`
- `0x18001eb90`
- `0x18001ecf0`
- `0x18001ee50`
- `0x18001efb0`
- `0x180020250`
- `0x18002e27c`
- `0x180031edc`
- `0x180032028`
- `0x18003224c`
- `0x18003280c`
- `0x1800329a4`
- `0x180033d60`
- `0x180063968`
- `0x18006448c`
- `0x18006ea28`
- `0x18008a050`
- `0x18008a150`
- `0x18008a250`
- `0x180093410`
- `0x180093864`
- `0x180094210`
- `0x180097550`
- `0x18009873c`
- `0x18009abc0`
- `0x18009b210`
- `0x18009ce80`
- `0x1800b1a50`
- `0x1800b1e50`
- `0x1800b3550`
- `0x1800b4880`
- `0x1800b5170`
- `0x1800b5270`
- `0x1800ba8d0`

## callees

- `0x180042e48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180042e71`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180042e88`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180042e71`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180042e88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042e55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042e55`

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
0x180042e48  mov     [rsp+arg_0], rbx
0x180042e4d  push    rdi
0x180042e4e  sub     rsp, 20h
0x180042e52  mov     rbx, rcx
0x180042e55  call    cs:__imp_GetCurrentThreadId
0x180042e5b  mov     edx, [rbx]
0x180042e5d  mov     edi, eax
0x180042e5f  btr     edx, 8
0x180042e63  cmp     edx, 1
0x180042e66  jnz     short loc_180042E7F
0x180042e68  cmp     [rbx+48h], eax
0x180042e6b  jz      short loc_180042E7A
0x180042e6d  lea     rcx, [rbx+10h]; SRWLock
0x180042e71  call    cs:__imp_AcquireSRWLockExclusive
0x180042e77  mov     [rbx+48h], edi
0x180042e7a  inc     dword ptr [rbx+4Ch]
0x180042e7d  jmp     short loc_180042EB1
0x180042e7f  cmp     [rbx+48h], edi
0x180042e82  jz      short loc_180042E8E
0x180042e84  lea     rcx, [rbx+10h]; SRWLock
0x180042e88  call    cs:__imp_AcquireSRWLockExclusive
0x180042e8e  mov     ecx, [rbx+4Ch]
0x180042e91  lea     eax, [rcx+1]
0x180042e94  mov     [rbx+4Ch], eax
0x180042e97  cmp     eax, 1
0x180042e9a  jle     short loc_180042EAE
0x180042e9c  test    dword ptr [rbx], 100h
0x180042ea2  jnz     short loc_180042EB1
0x180042ea4  mov     [rbx+4Ch], ecx
0x180042ea7  mov     eax, 3
0x180042eac  jmp     short loc_180042EB3
0x180042eae  mov     [rbx+48h], edi
0x180042eb1  xor     eax, eax
0x180042eb3  mov     rbx, [rsp+28h+arg_0]
0x180042eb8  add     rsp, 20h
0x180042ebc  pop     rdi
0x180042ebd  retn
```
