# UdfNotifyChangeDirectory

- ea: `0x14002e198`
- end: `0x14002e277`
- name: `UdfNotifyChangeDirectory`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14003f440`

## callees

- `0x1400030e0`
- `0x14002e198`
- `0x1400444c4`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14002e254`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b1bc`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002e254`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b1bc`
- `ntoskrnl!FsRtlNotifyFullChangeDirectory` at `0x14002e23c`
- `ntoskrnl!FsRtlNotifyFullChangeDirectory` at `0x14002e23c`

## pseudocode

```c
__int64 __fastcall UdfNotifyChangeDirectory(__int64 a1, IRP *a2, __int64 a3, _DWORD *a4)
{
  __int64 v9; // r8

  if ( (a4[1] & 3) != 0 )
    return 3221225485LL;
  *(_DWORD *)(a1 + 28) |= 4u;
  UdfAcquireResource(a1, *(_QWORD *)(a1 + 16) + 1480LL, 0, 1);
  UdfVerifyVcb(a1, *(_QWORD *)(a1 + 16), v9);
  FsRtlNotifyFullChangeDirectory(
    *(PNOTIFY_SYNC *)(*(_QWORD *)(a1 + 16) + 1712LL),
    (PLIST_ENTRY)(*(_QWORD *)(a1 + 16) + 1720LL),
    a4,
    (PSTRING)(*(_QWORD *)(a3 + 48) + 88LL),
    *(_BYTE *)(a3 + 2) & 1,
    0,
    *(_DWORD *)(a3 + 16),
    a2,
    0,
    0);
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a1 + 16) + 1480LL));
  UdfCompleteRequest((void *)a1, 0, 0);
  return 259;
}

```

## disassembly

```asm
0x14002e198  mov     [rsp+arg_0], rcx
0x14002e19d  push    rbx
0x14002e19e  push    rsi
0x14002e19f  push    rdi
0x14002e1a0  push    r14
0x14002e1a2  sub     rsp, 58h
0x14002e1a6  mov     rdi, r9
0x14002e1a9  mov     rsi, r8
0x14002e1ac  mov     r14, rdx
0x14002e1af  mov     rbx, rcx
0x14002e1b2  mov     eax, [r9+4]
0x14002e1b6  test    al, 3
0x14002e1b8  jz      short loc_14002E1CA
0x14002e1ba  mov     eax, 0C000000Dh
0x14002e1bf  add     rsp, 58h
0x14002e1c3  pop     r14
0x14002e1c5  pop     rdi
0x14002e1c6  pop     rsi
0x14002e1c7  pop     rbx
0x14002e1c8  retn
0x14002e1ca  or      dword ptr [rcx+1Ch], 4
0x14002e1ce  mov     rdx, [rcx+10h]
0x14002e1d2  add     rdx, 5C8h
0x14002e1d9  mov     r9d, 1
0x14002e1df  xor     r8d, r8d
0x14002e1e2  call    UdfAcquireResource
0x14002e1e7  nop
0x14002e1e8  mov     rdx, [rbx+10h]
0x14002e1ec  mov     rcx, rbx
0x14002e1ef  call    UdfVerifyVcb
0x14002e1f4  mov     rcx, [rbx+10h]
0x14002e1f8  mov     r8b, [rsi+2]
0x14002e1fc  and     r8b, 1
0x14002e200  mov     r9, [rsi+30h]
0x14002e204  add     r9, 58h ; 'X'; FullDirectoryName
0x14002e208  lea     rdx, [rcx+6B8h]; NotifyList
0x14002e20f  xor     r10d, r10d
0x14002e212  mov     [rsp+78h+SubjectContext], r10; SubjectContext
0x14002e217  mov     [rsp+78h+TraverseCallback], r10; TraverseCallback
0x14002e21c  mov     [rsp+78h+NotifyIrp], r14; NotifyIrp
0x14002e221  mov     eax, [rsi+10h]
0x14002e224  mov     [rsp+78h+CompletionFilter], eax; CompletionFilter
0x14002e228  mov     [rsp+78h+IgnoreBuffer], r10b; IgnoreBuffer
0x14002e22d  mov     [rsp+78h+WatchTree], r8b; WatchTree
0x14002e232  mov     r8, rdi; FsContext
0x14002e235  mov     rcx, [rcx+6B0h]; NotifySync
0x14002e23c  call    cs:__imp_FsRtlNotifyFullChangeDirectory
0x14002e243  nop     dword ptr [rax+rax+00h]
0x14002e248  nop
0x14002e249  mov     rcx, [rbx+10h]
0x14002e24d  add     rcx, 5C8h; Resource
0x14002e254  call    cs:__imp_ExReleaseResourceLite
0x14002e25b  nop     dword ptr [rax+rax+00h]
0x14002e260  xor     r8d, r8d
0x14002e263  xor     edx, edx
0x14002e265  mov     rcx, rbx
0x14002e268  call    UdfCompleteRequest
0x14002e26d  mov     eax, 103h
0x14002e272  jmp     loc_14002E1BF
0x14005b1a1  push    rbp
0x14005b1a3  sub     rsp, 50h
0x14005b1a7  mov     rbp, rdx
0x14005b1aa  mov     rax, [rbp+80h]
0x14005b1b1  mov     rcx, [rax+10h]
0x14005b1b5  add     rcx, 5C8h; Resource
0x14005b1bc  call    cs:__imp_ExReleaseResourceLite
0x14005b1c3  nop     dword ptr [rax+rax+00h]
0x14005b1c8  nop
0x14005b1c9  add     rsp, 50h
0x14005b1cd  pop     rbp
0x14005b1ce  retn
```
