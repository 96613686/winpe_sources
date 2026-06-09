# IsProxyCall

- ea: `0x180007520`
- end: `0x18000758e`
- name: `IsProxyCall`
- size: `110`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800071cc`
- `0x18000afb0`
- `0x18000b9c8`
- `0x18000ebd0`

## callees

- `0x180007520`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000753b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000753b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000755b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000755b`

## pseudocode

```c
_BOOL8 __fastcall IsProxyCall(__int64 a1)
{
  int v2; // edi

  AcquireSRWLockShared((PSRWLOCK)SstpSvcGlobals + 96);
  v2 = *((_DWORD *)SstpSvcGlobals + 194);
  ReleaseSRWLockShared((PSRWLOCK)SstpSvcGlobals + 96);
  return (v2 & 1) != 0 && a1 && *(_QWORD *)(a1 + 624) != 0;
}

```

## disassembly

```asm
0x180007520  mov     [rsp+arg_0], rbx
0x180007525  push    rdi
0x180007526  sub     rsp, 20h
0x18000752a  mov     rbx, rcx
0x18000752d  mov     rcx, cs:SstpSvcGlobals
0x180007534  add     rcx, 300h; SRWLock
0x18000753b  call    cs:__imp_AcquireSRWLockShared
0x180007542  nop     dword ptr [rax+rax+00h]
0x180007547  mov     rcx, cs:SstpSvcGlobals
0x18000754e  mov     edi, [rcx+308h]
0x180007554  add     rcx, 300h; SRWLock
0x18000755b  call    cs:__imp_ReleaseSRWLockShared
0x180007562  nop     dword ptr [rax+rax+00h]
0x180007567  bt      edi, 0
0x18000756b  jb      short loc_18000757B
0x18000756d  xor     eax, eax
0x18000756f  mov     rbx, [rsp+28h+arg_0]
0x180007574  add     rsp, 20h
0x180007578  pop     rdi
0x180007579  retn
0x18000757b  test    rbx, rbx
0x18000757e  jz      short loc_18000756D
0x180007580  xor     eax, eax
0x180007582  cmp     [rbx+270h], rax
0x180007589  setnz   al
0x18000758c  jmp     short loc_18000756F
```
