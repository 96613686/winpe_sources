# UdfCommonLockControl

- ea: `0x140036c38`
- end: `0x140036e3d`
- name: `UdfCommonLockControl`
- size: `517`
- prototype: `__int64 __fastcall(PVOID Context, PIRP Irp)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400077f0`
- `0x1400094c0`

## callees

- `0x1400030e0`
- `0x140014ad0`
- `0x140036c38`
- `0x140045f10`
- `0x14004ce50`
- `0x140054460`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140036e1c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005bfec`
- `ntoskrnl!ExReleaseResourceLite` at `0x140036e1c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005bfec`
- `ntoskrnl!ExAcquireFastMutex` at `0x140036d72`
- `ntoskrnl!ExAcquireFastMutex` at `0x140036d72`
- `ntoskrnl!ExReleaseFastMutex` at `0x140036e00`
- `ntoskrnl!ExReleaseFastMutex` at `0x140036e00`
- `ntoskrnl!FsRtlCheckOplock` at `0x140036cfb`
- `ntoskrnl!FsRtlCheckOplock` at `0x140036cfb`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140036da0`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140036da0`
- `ntoskrnl!FsRtlProcessFileLock` at `0x140036d3e`
- `ntoskrnl!FsRtlProcessFileLock` at `0x140036d3e`

## pseudocode

```c
__int64 __fastcall UdfCommonLockControl(PVOID Context, PIRP Irp)
{
  __int64 v5; // rbx
  char v6; // si
  __int64 v7; // r8
  unsigned int v8; // r15d
  struct _KTHREAD *CurrentThread; // r14
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // [rsp+78h] [rbp+10h] BYREF
  __int64 v14; // [rsp+80h] [rbp+18h] BYREF

  v13 = 0;
  v14 = 0;
  if ( (unsigned int)UdfDecodeFileObject(Irp->Tail.Overlay.CurrentStackLocation->FileObject, &v13, &v14) == 4 )
  {
    v5 = v13;
    v6 = 1;
    UdfAcquireResource(Context, *(_QWORD *)(*(_QWORD *)(v13 + 136) + 80LL) + 8LL, 0, 1);
    UdfVerifyScbOperation(Context, v5, v14);
    v8 = FsRtlCheckOplock((POPLOCK)(v5 + 88), Irp, Context, UdfOplockComplete, UdfPrePostIrp);
    if ( v8 )
    {
      Context = 0;
    }
    else
    {
      if ( !*(_QWORD *)(v5 + 504) )
      {
        LOBYTE(v7) = 1;
        UdfCreateFileLock(Context, v5, v7);
      }
      v8 = FsRtlProcessFileLock(*(PFILE_LOCK *)(v5 + 504), Irp, 0);
      CurrentThread = KeGetCurrentThread();
      v10 = *(_QWORD *)(v5 + 136);
      if ( CurrentThread != *(struct _KTHREAD **)(v10 + 64) )
      {
        ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v10 + 80) + 216LL));
        *(_QWORD *)(*(_QWORD *)(v5 + 136) + 64LL) = CurrentThread;
      }
      ++*(_DWORD *)(*(_QWORD *)(v5 + 136) + 72LL);
      if ( *(_DWORD *)(v5 + 216) || !FsRtlOplockIsFastIoPossible((POPLOCK)(v5 + 88)) )
      {
        v6 = 0;
      }
      else
      {
        v11 = *(_QWORD *)(v5 + 504);
        if ( v11 && *(_BYTE *)(v11 + 16) )
          v6 = 2;
      }
      *(_BYTE *)(v5 + 5) = v6;
      --*(_DWORD *)(*(_QWORD *)(v5 + 136) + 72LL);
      v12 = *(_QWORD *)(v5 + 136);
      if ( !*(_DWORD *)(v12 + 72) )
      {
        *(_QWORD *)(v12 + 64) = 0;
        ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(v5 + 136) + 80LL) + 216LL));
      }
    }
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v5 + 136) + 80LL) + 8LL));
    UdfCompleteRequest(Context, 0, v8);
    return v8;
  }
  else
  {
    UdfCompleteRequest(Context, Irp, -1073741811);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x140036c38  mov     rax, rsp
0x140036c3b  mov     [rax+8], rbx
0x140036c3f  push    rsi
0x140036c40  push    rdi
0x140036c41  push    r12
0x140036c43  push    r14
0x140036c45  push    r15
0x140036c47  sub     rsp, 40h
0x140036c4b  mov     r14, rdx
0x140036c4e  mov     rdi, rcx
0x140036c51  mov     qword ptr [rax+10h], 0
0x140036c59  mov     qword ptr [rax+18h], 0
0x140036c61  mov     rcx, [rdx+0B8h]
0x140036c68  lea     r8, [rax+18h]
0x140036c6c  lea     rdx, [rax+10h]
0x140036c70  mov     rcx, [rcx+30h]
0x140036c74  call    UdfDecodeFileObject
0x140036c79  mov     rcx, rdi
0x140036c7c  cmp     eax, 4
0x140036c7f  jz      short loc_140036CA6
0x140036c81  mov     ebx, 0C000000Dh
0x140036c86  mov     r8d, ebx
0x140036c89  mov     rdx, r14
0x140036c8c  call    UdfCompleteRequest
0x140036c91  mov     eax, ebx
0x140036c93  mov     rbx, [rsp+68h+arg_0]
0x140036c98  add     rsp, 40h
0x140036c9c  pop     r15
0x140036c9e  pop     r14
0x140036ca0  pop     r12
0x140036ca2  pop     rdi
0x140036ca3  pop     rsi
0x140036ca4  retn
0x140036ca6  mov     rbx, [rsp+68h+arg_8]
0x140036cab  mov     rax, [rbx+88h]
0x140036cb2  mov     rdx, [rax+50h]
0x140036cb6  add     rdx, 8
0x140036cba  mov     esi, 1
0x140036cbf  mov     r9d, esi
0x140036cc2  xor     r8d, r8d
0x140036cc5  call    UdfAcquireResource
0x140036cca  nop
0x140036ccb  mov     r8, [rsp+68h+arg_10]
0x140036cd3  mov     rdx, rbx
0x140036cd6  mov     rcx, rdi
0x140036cd9  call    UdfVerifyScbOperation
0x140036cde  lea     rax, UdfPrePostIrp
0x140036ce5  mov     [rsp+68h+PostIrpRoutine], rax; PostIrpRoutine
0x140036cea  lea     r9, UdfOplockComplete; CompletionRoutine
0x140036cf1  mov     r8, rdi; Context
0x140036cf4  mov     rdx, r14; Irp
0x140036cf7  lea     rcx, [rbx+58h]; Oplock
0x140036cfb  call    cs:__imp_FsRtlCheckOplock
0x140036d02  nop     dword ptr [rax+rax+00h]
0x140036d07  mov     r15d, eax
0x140036d0a  mov     [rsp+68h+var_38], eax
0x140036d0e  test    eax, eax
0x140036d10  jz      short loc_140036D19
0x140036d12  xor     edi, edi
0x140036d14  jmp     loc_140036E0D
0x140036d19  cmp     qword ptr [rbx+1F8h], 0
0x140036d21  jnz     short loc_140036D31
0x140036d23  mov     r8b, sil
0x140036d26  mov     rdx, rbx
0x140036d29  mov     rcx, rdi
0x140036d2c  call    UdfCreateFileLock
0x140036d31  xor     r8d, r8d; Context
0x140036d34  mov     rdx, r14; Irp
0x140036d37  mov     rcx, [rbx+1F8h]; FileLock
0x140036d3e  call    cs:__imp_FsRtlProcessFileLock
0x140036d45  nop     dword ptr [rax+rax+00h]
0x140036d4a  mov     r15d, eax
0x140036d4d  mov     [rsp+68h+var_38], eax
0x140036d51  mov     r14, gs:188h
0x140036d5a  mov     rcx, [rbx+88h]
0x140036d61  cmp     r14, [rcx+40h]
0x140036d65  jz      short loc_140036D89
0x140036d67  mov     rcx, [rcx+50h]
0x140036d6b  add     rcx, 0D8h; FastMutex
0x140036d72  call    cs:__imp_ExAcquireFastMutex
0x140036d79  nop     dword ptr [rax+rax+00h]
0x140036d7e  mov     rax, [rbx+88h]
0x140036d85  mov     [rax+40h], r14
0x140036d89  mov     rax, [rbx+88h]
0x140036d90  add     [rax+48h], esi
0x140036d93  cmp     dword ptr [rbx+0D8h], 0
0x140036d9a  jnz     short loc_140036DC9
0x140036d9c  lea     rcx, [rbx+58h]; Oplock
0x140036da0  call    cs:__imp_FsRtlOplockIsFastIoPossible
0x140036da7  nop     dword ptr [rax+rax+00h]
0x140036dac  test    al, al
0x140036dae  jz      short loc_140036DC9
0x140036db0  mov     rax, [rbx+1F8h]
0x140036db7  test    rax, rax
0x140036dba  jz      short loc_140036DCB
0x140036dbc  cmp     byte ptr [rax+10h], 0
0x140036dc0  jz      short loc_140036DCB
0x140036dc2  mov     esi, 2
0x140036dc7  jmp     short loc_140036DCB
0x140036dc9  xor     esi, esi
0x140036dcb  mov     [rbx+5], sil
0x140036dcf  mov     rax, [rbx+88h]
0x140036dd6  dec     dword ptr [rax+48h]
0x140036dd9  mov     rax, [rbx+88h]
0x140036de0  cmp     dword ptr [rax+48h], 0
0x140036de4  jnz     short loc_140036E0D
0x140036de6  mov     qword ptr [rax+40h], 0
0x140036dee  mov     rax, [rbx+88h]
0x140036df5  mov     rcx, [rax+50h]
0x140036df9  add     rcx, 0D8h; FastMutex
0x140036e00  call    cs:__imp_ExReleaseFastMutex
0x140036e07  nop     dword ptr [rax+rax+00h]
0x140036e0c  nop
0x140036e0d  mov     rax, [rbx+88h]
0x140036e14  mov     rcx, [rax+50h]
0x140036e18  add     rcx, 8; Resource
0x140036e1c  call    cs:__imp_ExReleaseResourceLite
0x140036e23  nop     dword ptr [rax+rax+00h]
0x140036e28  mov     r8d, r15d
0x140036e2b  xor     edx, edx
0x140036e2d  mov     rcx, rdi
0x140036e30  call    UdfCompleteRequest
0x140036e35  mov     eax, r15d
0x140036e38  jmp     loc_140036C93
0x14005bfd0  push    rbp
0x14005bfd2  sub     rsp, 30h
0x14005bfd6  mov     rbp, rdx
0x14005bfd9  mov     rax, [rbp+78h]
0x14005bfdd  mov     rcx, [rax+88h]
0x14005bfe4  mov     rcx, [rcx+50h]
0x14005bfe8  add     rcx, 8; Resource
0x14005bfec  call    cs:__imp_ExReleaseResourceLite
0x14005bff3  nop     dword ptr [rax+rax+00h]
0x14005bff8  nop
0x14005bff9  add     rsp, 30h
0x14005bffd  pop     rbp
0x14005bffe  retn
```
