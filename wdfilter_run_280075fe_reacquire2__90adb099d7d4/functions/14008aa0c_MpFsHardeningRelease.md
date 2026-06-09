# MpFsHardeningRelease

- ea: `0x14008aa0c`
- end: `0x14008aaac`
- name: `MpFsHardeningRelease`
- size: `160`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14007bef0`
- `0x14008f314`

## callees

- `0x140073f28`
- `0x14008aa0c`

## import_xrefs

- `ntoskrnl!ExDeleteLookasideListEx` at `0x14008aa60`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14008aa60`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008aa8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008aa8f`
- `FLTMGR!FltReleasePushLock` at `0x14008aa40`
- `FLTMGR!FltReleasePushLock` at `0x14008aa40`
- `FLTMGR!FltDeletePushLock` at `0x14008aa77`
- `FLTMGR!FltDeletePushLock` at `0x14008aa77`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x14008aa24`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x14008aa24`

## pseudocode

```c
void MpFsHardeningRelease()
{
  if ( MpFsHardeningData )
  {
    FltAcquirePushLockExclusive((PULONG_PTR)MpFsHardeningData + 3);
    FsHardeningItemListClearUnsafe();
    FltReleasePushLock((PULONG_PTR)MpFsHardeningData + 3);
    if ( *((_DWORD *)MpFsHardeningData + 32) )
      ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)((char *)MpFsHardeningData + 32));
    FltDeletePushLock((PULONG_PTR)MpFsHardeningData + 3);
    ExFreePoolWithTag(MpFsHardeningData, 0x6468504Du);
    MpFsHardeningData = 0;
  }
}

```

## disassembly

```asm
0x14008aa0c  sub     rsp, 28h
0x14008aa10  mov     rcx, cs:MpFsHardeningData
0x14008aa17  test    rcx, rcx
0x14008aa1a  jz      loc_14008AAA6
0x14008aa20  add     rcx, 18h; PushLock
0x14008aa24  call    cs:__imp_FltAcquirePushLockExclusive
0x14008aa2b  nop     dword ptr [rax+rax+00h]
0x14008aa30  call    FsHardeningItemListClearUnsafe
0x14008aa35  mov     rcx, cs:MpFsHardeningData
0x14008aa3c  add     rcx, 18h; PushLock
0x14008aa40  call    cs:__imp_FltReleasePushLock
0x14008aa47  nop     dword ptr [rax+rax+00h]
0x14008aa4c  mov     rcx, cs:MpFsHardeningData
0x14008aa53  cmp     dword ptr [rcx+80h], 0
0x14008aa5a  jz      short loc_14008AA6C
0x14008aa5c  add     rcx, 20h ; ' '; Lookaside
0x14008aa60  call    cs:__imp_ExDeleteLookasideListEx
0x14008aa67  nop     dword ptr [rax+rax+00h]
0x14008aa6c  mov     rcx, cs:MpFsHardeningData
0x14008aa73  add     rcx, 18h; PushLock
0x14008aa77  call    cs:__imp_FltDeletePushLock
0x14008aa7e  nop     dword ptr [rax+rax+00h]
0x14008aa83  mov     rcx, cs:MpFsHardeningData; P
0x14008aa8a  mov     edx, 6468504Dh; Tag
0x14008aa8f  call    cs:__imp_ExFreePoolWithTag
0x14008aa96  nop     dword ptr [rax+rax+00h]
0x14008aa9b  mov     cs:MpFsHardeningData, 0
0x14008aaa6  add     rsp, 28h
0x14008aaaa  retn
```
