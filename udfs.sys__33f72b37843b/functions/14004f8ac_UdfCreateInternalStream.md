# UdfCreateInternalStream

- ea: `0x14004f8ac`
- end: `0x14004fc68`
- name: `UdfCreateInternalStream`
- size: `956`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140014cb8`
- `0x14003d334`
- `0x140041110`
- `0x140041900`
- `0x14004d700`
- `0x14004e020`

## callees

- `0x140009014`
- `0x14000c490`
- `0x140011b54`
- `0x14004f8ac`
- `0x140056938`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004f9a1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004faa2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004fbc3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005a695`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004f9a1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004faa2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004fbc3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005a695`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004f9ef`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004fb5e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004fc57`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005a737`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004f9ef`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004fb5e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004fc57`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005a737`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004f8fb`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004f8fb`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004f957`
- `ntoskrnl!ExReleaseFastMutex` at `0x14005a77a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004f957`
- `ntoskrnl!ExReleaseFastMutex` at `0x14005a77a`
- `ntoskrnl!ObfDereferenceObject` at `0x14005a656`
- `ntoskrnl!ObfDereferenceObject` at `0x14005a656`
- `ntoskrnl!IoCreateStreamFileObjectLite` at `0x14004fa41`
- `ntoskrnl!IoCreateStreamFileObjectLite` at `0x14004fa41`
- `ntoskrnl!CcInitializeCacheMap` at `0x14004fb91`
- `ntoskrnl!CcInitializeCacheMap` at `0x14004fb91`

## pseudocode

```c
void __fastcall UdfCreateInternalStream(__int64 a1, __int64 a2, struct _CC_FILE_SIZES *a3, UNICODE_STRING *a4)
{
  struct _KTHREAD *CurrentThread; // rbx
  LARGE_INTEGER ValidDataLength; // rcx
  LARGE_INTEGER v10; // rax
  __int64 v11; // rax
  LARGE_INTEGER v12; // rax
  PFILE_OBJECT StreamFileObjectLite; // rax
  PFILE_OBJECT v14; // r14
  PVOID FsContext2; // rbx

  CurrentThread = KeGetCurrentThread();
  ValidDataLength = a3[5].ValidDataLength;
  if ( CurrentThread != *(struct _KTHREAD **)(ValidDataLength.QuadPart + 64) )
  {
    ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(ValidDataLength.QuadPart + 80) + 216LL));
    *(_QWORD *)(a3[5].ValidDataLength.QuadPart + 64) = CurrentThread;
  }
  ++*(_DWORD *)(a3[5].ValidDataLength.QuadPart + 72);
  if ( a3[21].AllocationSize.QuadPart )
  {
    --*(_DWORD *)(a3[5].ValidDataLength.QuadPart + 72);
    v10 = a3[5].ValidDataLength;
    if ( *(_DWORD *)(v10.QuadPart + 72) )
      return;
    *(_QWORD *)(v10.QuadPart + 64) = 0;
    goto LABEL_6;
  }
  if ( (a3[8].ValidDataLength.HighPart & 0x8000000) != 0 )
  {
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
    *(_QWORD *)(a2 + 1640) = KeGetCurrentThread();
    ++*(_DWORD *)(*(_QWORD *)(a2 + 320) + 204LL);
    v11 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 320) + 136LL) + 8LL);
    ++*(_DWORD *)(v11 + 256);
    *(_QWORD *)(a2 + 1640) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
    a3[21].AllocationSize.QuadPart = *(_QWORD *)(*(_QWORD *)(a2 + 320) + 504LL);
  }
  else
  {
    StreamFileObjectLite = IoCreateStreamFileObjectLite(0, *(PDEVICE_OBJECT *)(*(_QWORD *)(a2 + 8) + 16LL));
    v14 = StreamFileObjectLite;
    if ( !StreamFileObjectLite )
      UdfRaiseStatusEx(a1, 3221225626LL, 0);
    *(_WORD *)&StreamFileObjectLite->ReadAccess = 1;
    StreamFileObjectLite->DeleteAccess = 0;
    StreamFileObjectLite->SectionObjectPointer = (PSECTION_OBJECT_POINTERS)(a3[17].ValidDataLength.QuadPart + 8);
    UdfSetFileObject(a1, (_DWORD)StreamFileObjectLite, 1, (_DWORD)a3, 0);
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
    *(_QWORD *)(a2 + 1640) = KeGetCurrentThread();
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 2) != 0 )
    {
      WPP_SF_qdddd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
        10,
        WPP_caac521dd36031f4ea1a4be88351727a_Traceguids,
        a3,
        *(_DWORD *)(a2 + 256),
        *(_DWORD *)(a2 + 260),
        a3[8].FileSize.HighPart,
        a3[8].ValidDataLength.LowPart);
    }
    a3[8].FileSize.HighPart += 2;
    a3[8].ValidDataLength.LowPart = a3[8].ValidDataLength.LowPart;
    *(_DWORD *)(*(_QWORD *)(a3[5].ValidDataLength.QuadPart + 8) + 256LL) += 2;
    *(_DWORD *)(*(_QWORD *)(a3[5].ValidDataLength.QuadPart + 8) + 260LL) = *(_DWORD *)(*(_QWORD *)(a3[5].ValidDataLength.QuadPart
                                                                                                 + 8)
                                                                                     + 260LL);
    *(_QWORD *)(a2 + 1640) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
    FsContext2 = v14->FsContext2;
    v14->FsContext2 = 0;
    CcInitializeCacheMap(v14, a3 + 1, 1u, &Callbacks, a3);
    v14->FsContext2 = FsContext2;
    if ( a4 )
      v14->FileName = *a4;
    a3[21].AllocationSize.QuadPart = (LONGLONG)v14;
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
    *(_QWORD *)(a2 + 1640) = KeGetCurrentThread();
    --a3[8].FileSize.HighPart;
    --*(_DWORD *)(*(_QWORD *)(a3[5].ValidDataLength.QuadPart + 8) + 256LL);
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 2) != 0 )
    {
      WPP_SF_DDDD(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
        11,
        WPP_caac521dd36031f4ea1a4be88351727a_Traceguids,
        *(unsigned int *)(a2 + 256),
        *(_DWORD *)(a2 + 260),
        a3[8].FileSize.HighPart,
        a3[8].ValidDataLength.LowPart);
    }
    *(_QWORD *)(a2 + 1640) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
  }
  --*(_DWORD *)(a3[5].ValidDataLength.QuadPart + 72);
  v12 = a3[5].ValidDataLength;
  if ( !*(_DWORD *)(v12.QuadPart + 72) )
  {
    *(_QWORD *)(v12.QuadPart + 64) = 0;
LABEL_6:
    ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a3[5].ValidDataLength.QuadPart + 80) + 216LL));
  }
}

```

## disassembly

```asm
0x14004f8ac  mov     rax, rsp
0x14004f8af  mov     [rax+8], rbx
0x14004f8b3  mov     [rax+20h], rsi
0x14004f8b7  mov     [rax+18h], r8
0x14004f8bb  mov     [rax+10h], rdx
0x14004f8bf  push    rdi
0x14004f8c0  push    r12
0x14004f8c2  push    r13
0x14004f8c4  push    r14
0x14004f8c6  push    r15
0x14004f8c8  sub     rsp, 50h
0x14004f8cc  mov     r13, r9
0x14004f8cf  mov     rdi, r8
0x14004f8d2  mov     rsi, rdx
0x14004f8d5  mov     r12, rcx
0x14004f8d8  mov     rbx, gs:188h
0x14004f8e1  mov     rcx, [r8+88h]
0x14004f8e8  mov     r15d, 0D8h
0x14004f8ee  cmp     rbx, [rcx+40h]
0x14004f8f2  jz      short loc_14004F912
0x14004f8f4  mov     rcx, [rcx+50h]
0x14004f8f8  add     rcx, r15; FastMutex
0x14004f8fb  call    cs:__imp_ExAcquireFastMutex
0x14004f902  nop     dword ptr [rax+rax+00h]
0x14004f907  mov     rax, [rdi+88h]
0x14004f90e  mov     [rax+40h], rbx
0x14004f912  mov     rax, [rdi+88h]
0x14004f919  inc     dword ptr [rax+48h]
0x14004f91c  xor     ebx, ebx
0x14004f91e  cmp     [rdi+1F8h], rbx
0x14004f925  jz      short loc_14004F97E
0x14004f927  mov     rax, [rdi+88h]
0x14004f92e  or      ebx, 0FFFFFFFFh
0x14004f931  add     [rax+48h], ebx
0x14004f934  mov     rax, [rdi+88h]
0x14004f93b  cmp     dword ptr [rax+48h], 0
0x14004f93f  jnz     short loc_14004F963
0x14004f941  mov     qword ptr [rax+40h], 0
0x14004f949  mov     rax, [rdi+88h]
0x14004f950  mov     rcx, [rax+50h]
0x14004f954  add     rcx, r15; FastMutex
0x14004f957  call    cs:__imp_ExReleaseFastMutex
0x14004f95e  nop     dword ptr [rax+rax+00h]
0x14004f963  lea     r11, [rsp+78h+var_28]
0x14004f968  mov     rbx, [r11+30h]
0x14004f96c  mov     rsi, [r11+48h]
0x14004f970  mov     rsp, r11
0x14004f973  pop     r15
0x14004f975  pop     r14
0x14004f977  pop     r13
0x14004f979  pop     r12
0x14004f97b  pop     rdi
0x14004f97c  retn
0x14004f97e  mov     [rsp+78h+var_30], rbx
0x14004f983  mov     [rsp+78h+var_38], bl
0x14004f987  test    dword ptr [rdi+0D4h], 8000000h
0x14004f991  jz      loc_14004FA37
0x14004f997  lea     rbx, [rsi+630h]
0x14004f99e  mov     rcx, rbx; FastMutex
0x14004f9a1  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14004f9a8  nop     dword ptr [rax+rax+00h]
0x14004f9ad  mov     rax, gs:188h
0x14004f9b6  mov     [rsi+668h], rax
0x14004f9bd  mov     rax, [rsi+140h]
0x14004f9c4  inc     dword ptr [rax+0CCh]
0x14004f9ca  mov     rax, [rsi+140h]
0x14004f9d1  mov     rdx, [rax+88h]
0x14004f9d8  mov     rax, [rdx+8]
0x14004f9dc  inc     dword ptr [rax+100h]
0x14004f9e2  xor     r14d, r14d
0x14004f9e5  mov     [rsi+668h], r14
0x14004f9ec  mov     rcx, rbx; FastMutex
0x14004f9ef  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14004f9f6  nop     dword ptr [rax+rax+00h]
0x14004f9fb  mov     rax, [rsi+140h]
0x14004fa02  mov     rcx, [rax+1F8h]
0x14004fa09  mov     [rdi+1F8h], rcx
0x14004fa10  or      ebx, 0FFFFFFFFh
0x14004fa13  mov     rax, [rdi+88h]
0x14004fa1a  add     [rax+48h], ebx
0x14004fa1d  mov     rax, [rdi+88h]
0x14004fa24  cmp     [rax+48h], r14d
0x14004fa28  jnz     loc_14004F963
0x14004fa2e  mov     [rax+40h], r14
0x14004fa32  jmp     loc_14004F949
0x14004fa37  mov     rdx, [rsi+8]
0x14004fa3b  mov     rdx, [rdx+10h]; DeviceObject
0x14004fa3f  xor     ecx, ecx; FileObject
0x14004fa41  call    cs:__imp_IoCreateStreamFileObjectLite
0x14004fa48  nop     dword ptr [rax+rax+00h]
0x14004fa4d  mov     r14, rax
0x14004fa50  mov     [rsp+78h+var_30], rax
0x14004fa55  mov     rcx, r12
0x14004fa58  test    rax, rax
0x14004fa5b  jnz     short loc_14004FA6A
0x14004fa5d  xor     r8d, r8d
0x14004fa60  mov     edx, 0C000009Ah
0x14004fa65  call    UdfRaiseStatusEx
0x14004fa6a  mov     word ptr [rax+4Ah], 1
0x14004fa70  mov     [rax+4Ch], bl
0x14004fa73  mov     rax, [rdi+1A8h]
0x14004fa7a  add     rax, 8
0x14004fa7e  mov     [r14+28h], rax
0x14004fa82  mov     [rsp+78h+LazyWriteContext], rbx
0x14004fa87  mov     r9, rdi
0x14004fa8a  mov     r8d, 1
0x14004fa90  mov     rdx, r14
0x14004fa93  call    UdfSetFileObject
0x14004fa98  lea     r12, [rsi+630h]
0x14004fa9f  mov     rcx, r12; FastMutex
0x14004faa2  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14004faa9  nop     dword ptr [rax+rax+00h]
0x14004faae  mov     rax, gs:188h
0x14004fab7  mov     [rsi+668h], rax
0x14004fabe  lea     rax, WPP_GLOBAL_Control
0x14004fac5  mov     rcx, cs:WPP_GLOBAL_Control
0x14004facc  cmp     rcx, rax
0x14004facf  jz      short loc_14004FB18
0x14004fad1  mov     eax, [rcx+2Ch]
0x14004fad4  test    al, 2
0x14004fad6  jz      short loc_14004FB18
0x14004fad8  mov     edx, 0Ah
0x14004fadd  mov     eax, [rdi+0D0h]
0x14004fae3  mov     [rsp+78h+var_40], eax
0x14004fae7  mov     eax, [rdi+0CCh]
0x14004faed  mov     [rsp+78h+var_48], eax
0x14004faf1  mov     eax, [rsi+104h]
0x14004faf7  mov     [rsp+78h+var_50], eax
0x14004fafb  mov     eax, [rsi+100h]
0x14004fb01  mov     dword ptr [rsp+78h+LazyWriteContext], eax
0x14004fb05  mov     r9, rdi
0x14004fb08  lea     r8, WPP_caac521dd36031f4ea1a4be88351727a_Traceguids
0x14004fb0f  mov     rcx, [rcx+18h]
0x14004fb13  call    WPP_SF_qdddd
0x14004fb18  add     dword ptr [rdi+0CCh], 2
0x14004fb1f  mov     eax, [rdi+0D0h]
0x14004fb25  mov     [rdi+0D0h], eax
0x14004fb2b  mov     rax, [rdi+88h]
0x14004fb32  mov     rcx, [rax+8]
0x14004fb36  add     dword ptr [rcx+100h], 2
0x14004fb3d  mov     rax, [rdi+88h]
0x14004fb44  mov     rcx, [rax+8]
0x14004fb48  mov     eax, [rcx+104h]
0x14004fb4e  mov     [rcx+104h], eax
0x14004fb54  mov     [rsi+668h], rbx
0x14004fb5b  mov     rcx, r12; FastMutex
0x14004fb5e  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14004fb65  nop     dword ptr [rax+rax+00h]
0x14004fb6a  mov     [rsp+78h+var_38], 1
0x14004fb6f  mov     rbx, [r14+20h]
0x14004fb73  mov     qword ptr [r14+20h], 0
0x14004fb7b  lea     rdx, [rdi+18h]; FileSizes
0x14004fb7f  mov     [rsp+78h+LazyWriteContext], rdi; LazyWriteContext
0x14004fb84  lea     r9, Callbacks; Callbacks
0x14004fb8b  mov     r8b, 1; PinAccess
0x14004fb8e  mov     rcx, r14; FileObject
0x14004fb91  call    cs:__imp_CcInitializeCacheMap
0x14004fb98  nop     dword ptr [rax+rax+00h]
0x14004fb9d  mov     [r14+20h], rbx
0x14004fba1  test    r13, r13
0x14004fba4  jz      short loc_14004FBB1
0x14004fba6  movaps  xmm0, xmmword ptr [r13+0]
0x14004fbab  movdqu  xmmword ptr [r14+58h], xmm0
0x14004fbb1  mov     [rdi+1F8h], r14
0x14004fbb8  xor     r14d, r14d
0x14004fbbb  mov     [rsp+78h+var_30], r14
0x14004fbc0  mov     rcx, r12; FastMutex
0x14004fbc3  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14004fbca  nop     dword ptr [rax+rax+00h]
0x14004fbcf  mov     rax, gs:188h
0x14004fbd8  mov     [rsi+668h], rax
0x14004fbdf  or      ebx, 0FFFFFFFFh
0x14004fbe2  add     [rdi+0CCh], ebx
0x14004fbe8  mov     rax, [rdi+88h]
0x14004fbef  mov     rcx, [rax+8]
0x14004fbf3  add     [rcx+100h], ebx
0x14004fbf9  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fc00  lea     rax, WPP_GLOBAL_Control
0x14004fc07  cmp     rcx, rax
0x14004fc0a  jz      short loc_14004FC4D
0x14004fc0c  mov     eax, [rcx+2Ch]
0x14004fc0f  test    al, 2
0x14004fc11  jz      short loc_14004FC4D
0x14004fc13  mov     edx, 0Bh
0x14004fc18  mov     eax, [rdi+0D0h]
0x14004fc1e  mov     [rsp+78h+var_48], eax
0x14004fc22  mov     eax, [rdi+0CCh]
0x14004fc28  mov     [rsp+78h+var_50], eax
0x14004fc2c  mov     eax, [rsi+104h]
0x14004fc32  mov     dword ptr [rsp+78h+LazyWriteContext], eax
0x14004fc36  mov     r9d, [rsi+100h]
0x14004fc3d  lea     r8, WPP_caac521dd36031f4ea1a4be88351727a_Traceguids
0x14004fc44  mov     rcx, [rcx+18h]
0x14004fc48  call    WPP_SF_DDDD
0x14004fc4d  mov     [rsi+668h], r14
0x14004fc54  mov     rcx, r12; FastMutex
0x14004fc57  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14004fc5e  nop     dword ptr [rax+rax+00h]
0x14004fc63  jmp     loc_14004FA13
0x14005a642  push    rbx
0x14005a644  push    rbp
0x14005a645  push    rdi
0x14005a646  sub     rsp, 40h
0x14005a64a  mov     rbp, rdx
0x14005a64d  mov     rcx, [rbp+48h]; Object
0x14005a651  test    rcx, rcx
0x14005a654  jz      short loc_14005A676
0x14005a656  call    cs:__imp_ObfDereferenceObject
0x14005a65d  nop     dword ptr [rax+rax+00h]
0x14005a662  mov     rbx, [rbp+90h]
0x14005a669  mov     qword ptr [rbx+1F8h], 0
0x14005a674  jmp     short loc_14005A67D
0x14005a676  mov     rbx, [rbp+90h]
0x14005a67d  cmp     byte ptr [rbp+40h], 0
0x14005a681  jz      loc_14005A744
0x14005a687  mov     rdi, [rbp+88h]
0x14005a68e  lea     rcx, [rdi+630h]; FastMutex
0x14005a695  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14005a69c  nop     dword ptr [rax+rax+00h]
0x14005a6a1  mov     rax, gs:188h
0x14005a6aa  mov     [rdi+668h], rax
0x14005a6b1  dec     dword ptr [rbx+0CCh]
0x14005a6b7  mov     rax, [rbx+88h]
0x14005a6be  mov     rcx, [rax+8]
0x14005a6c2  mov     edx, [rcx+100h]
0x14005a6c8  dec     edx
0x14005a6ca  mov     [rcx+100h], edx
0x14005a6d0  lea     rax, WPP_GLOBAL_Control
0x14005a6d7  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a6de  cmp     rcx, rax
0x14005a6e1  jz      short loc_14005A725
0x14005a6e3  mov     eax, [rcx+2Ch]
0x14005a6e6  test    al, 2
0x14005a6e8  jz      short loc_14005A725
0x14005a6ea  mov     edx, 0Bh
0x14005a6ef  mov     eax, [rbx+0D0h]
0x14005a6f5  mov     dword ptr [rsp+58h+var_28], eax
0x14005a6f9  mov     eax, [rbx+0CCh]
0x14005a6ff  mov     dword ptr [rsp+58h+var_30], eax
0x14005a703  mov     eax, [rdi+104h]
0x14005a709  mov     dword ptr [rsp+58h+var_38], eax
0x14005a70d  mov     r9d, [rdi+100h]
0x14005a714  lea     r8, WPP_caac521dd36031f4ea1a4be88351727a_Traceguids
0x14005a71b  mov     rcx, [rcx+18h]
0x14005a71f  call    WPP_SF_DDDD
0x14005a724  nop
0x14005a725  mov     qword ptr [rdi+668h], 0
0x14005a730  lea     rcx, [rdi+630h]; FastMutex
0x14005a737  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14005a73e  nop     dword ptr [rax+rax+00h]
0x14005a743  nop
0x14005a744  mov     rax, [rbx+88h]
0x14005a74b  mov     ecx, [rax+48h]
0x14005a74e  dec     ecx
0x14005a750  mov     [rax+48h], ecx
0x14005a753  mov     rax, [rbx+88h]
0x14005a75a  cmp     dword ptr [rax+48h], 0
0x14005a75e  jnz     short loc_14005A787
0x14005a760  mov     qword ptr [rax+40h], 0
0x14005a768  mov     rax, [rbx+88h]
0x14005a76f  mov     rcx, [rax+50h]
0x14005a773  add     rcx, 0D8h; FastMutex
0x14005a77a  call    cs:__imp_ExReleaseFastMutex
0x14005a781  nop     dword ptr [rax+rax+00h]
0x14005a786  nop
0x14005a787  add     rsp, 40h
0x14005a78b  pop     rdi
0x14005a78c  pop     rbp
0x14005a78d  pop     rbx
0x14005a78e  retn
```
