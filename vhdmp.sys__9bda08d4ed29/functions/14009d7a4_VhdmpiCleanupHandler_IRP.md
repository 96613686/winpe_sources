# VhdmpiCleanupHandler(_IRP *)

- ea: `0x14009d7a4`
- end: `0x14009d99b`
- name: `?VhdmpiCleanupHandler@@YAJPEAU_IRP@@@Z`
- size: `503`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14001a410`

## callees

- `0x140015290`
- `0x14001bc1c`
- `0x14001c088`
- `0x14001fb48`
- `0x140023980`
- `0x140024400`
- `0x1400266a0`
- `0x140026dec`
- `0x140027608`
- `0x1400277d4`
- `0x140036284`
- `0x14009d7a4`
- `0x14009e984`
- `0x1400bc14c`
- `0x1400e6f08`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14009d864`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14009d864`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14009d8d1`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14009d8d1`
- `ntoskrnl!IofCompleteRequest` at `0x14009d981`
- `ntoskrnl!IofCompleteRequest` at `0x14009d981`

## pseudocode

```c
__int64 __fastcall VhdmpiCleanupHandler(PIRP Irp)
{
  __int64 HandleContextFromIrp; // rax
  __int64 v3; // rcx
  __int64 v4; // r8
  struct _EX_RUNDOWN_REF *v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rbp
  ULONG_PTR Count; // rcx
  __int64 v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // r8

  HandleContextFromIrp = VhdmpiGetHandleContextFromIrp(Irp);
  v5 = (struct _EX_RUNDOWN_REF *)HandleContextFromIrp;
  if ( HandleContextFromIrp )
  {
    v6 = *(_QWORD *)(HandleContextFromIrp + 56);
    if ( v6 )
      v7 = *(_QWORD *)(v6 + 2816);
    else
      v7 = 0;
    if ( (Microsoft_Windows_VHDMPEnableBits & 1) != 0 )
      McTemplateK0pp_EtwWriteTransfer(v3, VirtualDiskHandleCloseBegin, v4, v5[49].Count, v7);
    if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
      TraceEvents("VhdmpiCleanupHandler", 0xF43u, 5u, 0x10u, "VhdmpiCleanupHandler: enter... VirtualDisk %p", v5);
    VhdmpiDisableCachedRundowns(v5);
    VhdmpiCancelAllQueuedIoctlsOnHandle((char)v5);
    ExWaitForRundownProtectionRelease(v5 + 33);
    Count = v5[7].Count;
    if ( Count )
    {
      VhdmpiAcquirePassiveLock(Count + 184);
      v9 = v5[10].Count;
      if ( v9 && _InterlockedIncrement64((volatile signed __int64 *)(v9 + 72)) <= 1 )
        __fastfail(0xEu);
      VhdmpiReleasePassiveLock(v5[7].Count + 184);
      if ( v9 )
      {
        VhdmpiRemoveSurfaceOwnershipFromHandle((__int64)v5, v9);
        VhdmpiReleaseSurface(v9);
      }
    }
    KeFlushQueuedDpcs();
    if ( v5[7].Count )
      VhdmpiDetachHandleFromVirtualDisk((struct _VHD_HANDLE_CONTEXT *)v5);
    if ( v5[38].Count )
      VhdmpiReleaseVhdSetFileRef(v5);
    VhdmpiCleanupSecurityContext(&v5[2]);
    if ( (Microsoft_Windows_VHDMPEnableBits & 8) != 0 )
      McTemplateK0pp_EtwWriteTransfer(v10, VirtualDiskHandleClose, v11, v5[49].Count, v7);
  }
  else
  {
    VhdmpiDecrementDriverUserCount();
  }
  if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
    TraceEvents("VhdmpiCleanupHandler", 0xF8Du, 5u, 0x10u, "VhdmpiCleanupHandler: leaving... (0x%x)", 0);
  Irp->IoStatus.Status = 0;
  IofCompleteRequest(Irp, 0);
  return 0;
}

```

## disassembly

```asm
0x14009d7a4  push    rbx
0x14009d7a6  push    rbp
0x14009d7a7  push    rsi
0x14009d7a8  push    rdi
0x14009d7a9  push    r13
0x14009d7ab  sub     rsp, 30h
0x14009d7af  mov     rsi, rcx
0x14009d7b2  call    VhdmpiGetHandleContextFromIrp
0x14009d7b7  mov     rbx, rax
0x14009d7ba  mov     r13d, 10h
0x14009d7c0  test    rax, rax
0x14009d7c3  jnz     short loc_14009D7CF
0x14009d7c5  call    VhdmpiDecrementDriverUserCount
0x14009d7ca  jmp     loc_14009D928
0x14009d7cf  mov     rax, [rax+38h]
0x14009d7d3  test    rax, rax
0x14009d7d6  jz      short loc_14009D7E1
0x14009d7d8  mov     rbp, [rax+0B00h]
0x14009d7df  jmp     short loc_14009D7E3
0x14009d7e1  xor     ebp, ebp
0x14009d7e3  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 1
0x14009d7ea  jz      short loc_14009D804
0x14009d7ec  mov     r9, [rbx+188h]
0x14009d7f3  lea     rdx, VirtualDiskHandleCloseBegin
0x14009d7fa  mov     [rsp+58h+var_38], rbp
0x14009d7ff  call    McTemplateK0pp_EtwWriteTransfer
0x14009d804  mov     eax, cs:dword_1400876D0
0x14009d80a  cmp     eax, 5
0x14009d80d  jbe     short loc_14009D84D
0x14009d80f  mov     rdx, r13
0x14009d812  lea     rcx, dword_1400876D0
0x14009d819  call    _tlgKeywordOn
0x14009d81e  test    al, al
0x14009d820  jz      short loc_14009D84D
0x14009d822  lea     rax, aVhdmpicleanuph_1; "VhdmpiCleanupHandler: enter... VirtualD"...
0x14009d829  mov     qword ptr [rsp+58h+var_30], rbx; char
0x14009d82e  mov     edx, 0F43h; int
0x14009d833  mov     [rsp+58h+var_38], rax; char *
0x14009d838  mov     r9d, r13d; int
0x14009d83b  lea     rcx, aVhdmpicleanuph; "VhdmpiCleanupHandler"
0x14009d842  mov     r8d, 5; int
0x14009d848  call    TraceEvents
0x14009d84d  mov     rcx, rbx
0x14009d850  call    VhdmpiDisableCachedRundowns
0x14009d855  mov     rcx, rbx; char
0x14009d858  call    VhdmpiCancelAllQueuedIoctlsOnHandle
0x14009d85d  lea     rcx, [rbx+108h]; RunRef
0x14009d864  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14009d86b  nop     dword ptr [rax+rax+00h]
0x14009d870  mov     rcx, [rbx+38h]
0x14009d874  test    rcx, rcx
0x14009d877  jz      short loc_14009D8D1
0x14009d879  add     rcx, 0B8h
0x14009d880  call    VhdmpiAcquirePassiveLock
0x14009d885  mov     rdi, [rbx+50h]
0x14009d889  test    rdi, rdi
0x14009d88c  jz      short loc_14009D8A9
0x14009d88e  mov     eax, 1
0x14009d893  lock xadd [rdi+48h], rax
0x14009d899  inc     rax
0x14009d89c  cmp     rax, 1
0x14009d8a0  jg      short loc_14009D8A9
0x14009d8a2  mov     ecx, 0Eh
0x14009d8a7  int     29h; Win8: RtlFailFast(ecx)
0x14009d8a9  mov     rcx, [rbx+38h]
0x14009d8ad  add     rcx, 0B8h
0x14009d8b4  call    VhdmpiReleasePassiveLock
0x14009d8b9  test    rdi, rdi
0x14009d8bc  jz      short loc_14009D8D1
0x14009d8be  mov     rdx, rdi
0x14009d8c1  mov     rcx, rbx
0x14009d8c4  call    VhdmpiRemoveSurfaceOwnershipFromHandle
0x14009d8c9  mov     rcx, rdi
0x14009d8cc  call    VhdmpiReleaseSurface
0x14009d8d1  call    cs:__imp_KeFlushQueuedDpcs
0x14009d8d8  nop     dword ptr [rax+rax+00h]
0x14009d8dd  cmp     qword ptr [rbx+38h], 0
0x14009d8e2  jz      short loc_14009D8EC
0x14009d8e4  mov     rcx, rbx; struct _VHD_HANDLE_CONTEXT *
0x14009d8e7  call    VhdmpiDetachHandleFromVirtualDisk
0x14009d8ec  cmp     qword ptr [rbx+130h], 0
0x14009d8f4  jz      short loc_14009D8FE
0x14009d8f6  mov     rcx, rbx
0x14009d8f9  call    VhdmpiReleaseVhdSetFileRef
0x14009d8fe  lea     rcx, [rbx+10h]
0x14009d902  call    VhdmpiCleanupSecurityContext
0x14009d907  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 8
0x14009d90e  jz      short loc_14009D928
0x14009d910  mov     r9, [rbx+188h]
0x14009d917  lea     rdx, VirtualDiskHandleClose
0x14009d91e  mov     [rsp+58h+var_38], rbp
0x14009d923  call    McTemplateK0pp_EtwWriteTransfer
0x14009d928  mov     eax, cs:dword_1400876D0
0x14009d92e  cmp     eax, 5
0x14009d931  jbe     short loc_14009D975
0x14009d933  mov     rdx, r13
0x14009d936  lea     rcx, dword_1400876D0
0x14009d93d  call    _tlgKeywordOn
0x14009d942  test    al, al
0x14009d944  jz      short loc_14009D975
0x14009d946  lea     rax, aVhdmpicleanuph_0; "VhdmpiCleanupHandler: leaving... (0x%x)"
0x14009d94d  mov     qword ptr [rsp+58h+var_30], 0; char
0x14009d956  mov     edx, 0F8Dh; int
0x14009d95b  mov     [rsp+58h+var_38], rax; char *
0x14009d960  mov     r9d, r13d; int
0x14009d963  lea     rcx, aVhdmpicleanuph; "VhdmpiCleanupHandler"
0x14009d96a  mov     r8d, 5; int
0x14009d970  call    TraceEvents
0x14009d975  xor     edx, edx; PriorityBoost
0x14009d977  mov     dword ptr [rsi+30h], 0
0x14009d97e  mov     rcx, rsi; Irp
0x14009d981  call    cs:__imp_IofCompleteRequest
0x14009d988  nop     dword ptr [rax+rax+00h]
0x14009d98d  xor     eax, eax
0x14009d98f  add     rsp, 30h
0x14009d993  pop     r13
0x14009d995  pop     rdi
0x14009d996  pop     rsi
0x14009d997  pop     rbp
0x14009d998  pop     rbx
0x14009d999  retn
```
