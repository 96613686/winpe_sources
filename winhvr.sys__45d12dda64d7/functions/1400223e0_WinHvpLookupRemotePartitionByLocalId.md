# WinHvpLookupRemotePartitionByLocalId

- ea: `0x1400223e0`
- end: `0x14002247d`
- name: `WinHvpLookupRemotePartitionByLocalId`
- size: `157`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1400218a0`
- `0x140021c40`
- `0x140021d00`
- `0x140021de0`
- `0x140021ec0`
- `0x140021f80`
- `0x1400220e0`

## callees

- `0x1400223e0`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14002245a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002245a`
- `ntoskrnl!ExAcquireFastMutex` at `0x140022404`
- `ntoskrnl!ExAcquireFastMutex` at `0x140022404`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14002243e`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14002243e`

## pseudocode

```c
__int64 __fastcall WinHvpLookupRemotePartitionByLocalId(__int64 a1, ULONG_PTR *a2, struct _EX_RUNDOWN_REF **a3)
{
  char v4; // bl
  struct _EX_RUNDOWN_REF *i; // rdi

  *a2 = 0;
  v4 = 0;
  ExAcquireFastMutex(&WinHvpRemoteIdMapLock);
  for ( i = (struct _EX_RUNDOWN_REF *)WinHvpRemoteIdMap;
        i != (struct _EX_RUNDOWN_REF *)&WinHvpRemoteIdMap;
        i = (struct _EX_RUNDOWN_REF *)i->Count )
  {
    if ( i[2].Count == a1 )
    {
      *a2 = i[3].Count;
      if ( a3 )
      {
        if ( !ExAcquireRundownProtection(i + 14) )
          break;
        *a3 = i;
      }
      v4 = 1;
      break;
    }
  }
  ExReleaseFastMutex(&WinHvpRemoteIdMapLock);
  return v4 == 0 ? 0xC035000D : 0;
}

```

## disassembly

```asm
0x1400223e0  push    rbx
0x1400223e2  push    rbp
0x1400223e3  push    rsi
0x1400223e4  push    rdi
0x1400223e5  push    r14
0x1400223e7  sub     rsp, 20h
0x1400223eb  mov     rbp, rcx
0x1400223ee  mov     qword ptr [rdx], 0
0x1400223f5  lea     rcx, WinHvpRemoteIdMapLock; FastMutex
0x1400223fc  xor     bl, bl
0x1400223fe  mov     rsi, r8
0x140022401  mov     r14, rdx
0x140022404  call    cs:__imp_ExAcquireFastMutex
0x14002240b  nop     dword ptr [rax+rax+00h]
0x140022410  mov     rdi, cs:WinHvpRemoteIdMap
0x140022417  lea     rax, WinHvpRemoteIdMap
0x14002241e  cmp     rdi, rax
0x140022421  jz      short loc_140022453
0x140022423  cmp     [rdi+10h], rbp
0x140022427  jz      short loc_14002242E
0x140022429  mov     rdi, [rdi]
0x14002242c  jmp     short loc_140022417
0x14002242e  mov     rax, [rdi+18h]
0x140022432  mov     [r14], rax
0x140022435  test    rsi, rsi
0x140022438  jz      short loc_140022451
0x14002243a  lea     rcx, [rdi+70h]; RunRef
0x14002243e  call    cs:__imp_ExAcquireRundownProtection
0x140022445  nop     dword ptr [rax+rax+00h]
0x14002244a  test    al, al
0x14002244c  jz      short loc_140022453
0x14002244e  mov     [rsi], rdi
0x140022451  mov     bl, 1
0x140022453  lea     rcx, WinHvpRemoteIdMapLock; FastMutex
0x14002245a  call    cs:__imp_ExReleaseFastMutex
0x140022461  nop     dword ptr [rax+rax+00h]
0x140022466  neg     bl
0x140022468  sbb     eax, eax
0x14002246a  not     eax
0x14002246c  and     eax, 0C035000Dh
0x140022471  add     rsp, 20h
0x140022475  pop     r14
0x140022477  pop     rdi
0x140022478  pop     rsi
0x140022479  pop     rbp
0x14002247a  pop     rbx
0x14002247b  retn
```
