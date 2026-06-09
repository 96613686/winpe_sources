# VhdmpiCTFlushBuffersIOCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x14002c380`
- end: `0x14002c557`
- name: `?VhdmpiCTFlushBuffersIOCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `471`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400152fc`
- `0x140023980`
- `0x14002a8b0`
- `0x14002be3c`
- `0x14002c1dc`
- `0x14002c240`
- `0x14002c380`
- `0x140033910`
- `0x140036284`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14002c48f`
- `ntoskrnl!IoFreeIrp` at `0x14002c48f`
- `ntoskrnl!IoFreeMdl` at `0x14002c478`
- `ntoskrnl!IoFreeMdl` at `0x14002c478`
- `ntoskrnl!KeSetEvent` at `0x14002c4dd`
- `ntoskrnl!KeSetEvent` at `0x14002c4dd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002c4f3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002c4f3`

## string_xrefs

- `0x14002c3f3`: `VhdmpiCTFlushBuffersIOCompletion`
- `0x14002c409`: `VhdmpiCTFlushBuffersIOCompletion failed for log file %S (VirtualDisk = %p) (BackingStore = %p): ERROR! IrpContext=0x%p  IrpStatus=0x%x`

## pseudocode

```c
__int64 __fastcall VhdmpiCTFlushBuffersIOCompletion(struct _DEVICE_OBJECT *a1, struct _IRP *a2, void *a3)
{
  bool v3; // sf
  __int64 v4; // rsi
  __int64 v6; // r14
  int v8; // r8d
  unsigned int *v9; // r15
  unsigned int v10; // edx
  __int64 Status; // rdx
  struct _MDL *MdlAddress; // rcx
  void *v13; // r8
  struct _CTLOG_BUFFER ***v14; // rax
  struct _KEVENT *v15; // rcx
  struct _CTLOG_BUFFER *v16; // rbx
  __int64 v17; // rax
  struct _CTLOG_BUFFER *v19[2]; // [rsp+50h] [rbp-18h] BYREF

  v3 = a2->IoStatus.Status < 0;
  v4 = *((_QWORD *)a3 + 1);
  v6 = *((_QWORD *)a3 + 3);
  *(_OWORD *)v19 = 0;
  if ( v3 )
  {
    v8 = 2;
    v9 = *(unsigned int **)(v4 + 72);
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4096) )
      TraceEvents(
        "VhdmpiCTFlushBuffersIOCompletion",
        0x31Au,
        v8,
        v10,
        "VhdmpiCTFlushBuffersIOCompletion failed for log file %S (VirtualDisk = %p) (BackingStore = %p): ERROR! IrpContex"
        "t=0x%p  IrpStatus=0x%x",
        *(const wchar_t **)(v4 + 32),
        v9,
        (const void *)v4,
        a3,
        a2->IoStatus.Status);
    if ( (Microsoft_Windows_VHDMPEnableBits & 4) != 0 )
      McTemplateK0zq_EtwWriteTransfer(
        (_DWORD)a1,
        (unsigned int)CTLogFlushBuffersFailed,
        v8,
        *(_QWORD *)(v4 + 32),
        a2->IoStatus.Status);
    Status = (unsigned int)a2->IoStatus.Status;
    if ( *(_BYTE *)(v4 + 4432) )
      VhdmpiAccumulateMirrorStatus(v9, Status);
    else
      VhdmpiCTLogFailChangeTracking(v9, Status, v9[529]);
  }
  MdlAddress = a2->MdlAddress;
  if ( MdlAddress )
  {
    v13 = (void *)*((_QWORD *)a3 + 7);
    if ( v13 )
      VhdmpiCTDeleteMasterMDL(MdlAddress, *((_DWORD *)a3 + 12), v13);
    else
      IoFreeMdl(MdlAddress);
    a2->MdlAddress = 0;
  }
  IoFreeIrp(a2);
  v19[1] = (struct _CTLOG_BUFFER *)v19;
  v19[0] = (struct _CTLOG_BUFFER *)v19;
  v14 = *(struct _CTLOG_BUFFER ****)(v6 + 8);
  if ( *v14 != (struct _CTLOG_BUFFER **)v6 )
LABEL_24:
    __fastfail(3u);
  v19[1] = *(struct _CTLOG_BUFFER **)(v6 + 8);
  v19[0] = (struct _CTLOG_BUFFER *)v6;
  *v14 = v19;
  *(_QWORD *)(v6 + 8) = v19;
  v15 = (struct _KEVENT *)*((_QWORD *)a3 + 5);
  if ( v15 )
    KeSetEvent(v15, 0, 0);
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v4 + 4224), a3);
  while ( 1 )
  {
    v16 = v19[0];
    if ( (struct _CTLOG_BUFFER **)v19[0] == v19 )
      return 3221225494LL;
    if ( *((struct _CTLOG_BUFFER ***)v19[0] + 1) != v19 )
      goto LABEL_24;
    v17 = *(_QWORD *)v19[0];
    if ( *(struct _CTLOG_BUFFER **)(*(_QWORD *)v19[0] + 8LL) != v19[0] )
      goto LABEL_24;
    v19[0] = *(struct _CTLOG_BUFFER **)v19[0];
    *(_QWORD *)(v17 + 8) = v19;
    VhdmpiCTDetachBufferFromBackingStore(v16);
    VhdmpiCTAddToAvailableBufferList(v16);
  }
}

```

## disassembly

```asm
0x14002c380  push    rbp
0x14002c382  push    rbx
0x14002c383  push    rsi
0x14002c384  push    rdi
0x14002c385  push    r14
0x14002c387  push    r15
0x14002c389  mov     rbp, rsp
0x14002c38c  sub     rsp, 68h
0x14002c390  cmp     dword ptr [rdx+30h], 0
0x14002c394  xorps   xmm0, xmm0
0x14002c397  mov     rsi, [r8+8]
0x14002c39b  mov     rdi, r8
0x14002c39e  mov     r14, [r8+18h]
0x14002c3a2  mov     rbx, rdx
0x14002c3a5  movups  xmmword ptr [rbp+var_18], xmm0
0x14002c3a9  jge     loc_14002C45C
0x14002c3af  mov     eax, cs:dword_1400876D0
0x14002c3b5  mov     r8d, 2
0x14002c3bb  mov     r15, [rsi+48h]
0x14002c3bf  cmp     eax, r8d
0x14002c3c2  jbe     short loc_14002C41A
0x14002c3c4  mov     edx, 1000h
0x14002c3c9  lea     rcx, dword_1400876D0
0x14002c3d0  call    _tlgKeywordOn
0x14002c3d5  test    al, al
0x14002c3d7  jz      short loc_14002C41A
0x14002c3d9  mov     eax, [rbx+30h]
0x14002c3dc  mov     ecx, 31Ah
0x14002c3e1  mov     [rsp+68h+var_20], eax
0x14002c3e5  mov     r9d, edx; int
0x14002c3e8  mov     rax, [rsi+20h]
0x14002c3ec  mov     edx, ecx; int
0x14002c3ee  mov     [rsp+68h+var_28], rdi
0x14002c3f3  lea     rcx, aVhdmpictflushb_0; "VhdmpiCTFlushBuffersIOCompletion"
0x14002c3fa  mov     [rsp+68h+var_30], rsi
0x14002c3ff  mov     [rsp+68h+var_38], r15
0x14002c404  mov     qword ptr [rsp+68h+var_40], rax; char
0x14002c409  lea     rax, aVhdmpictflushb; "VhdmpiCTFlushBuffersIOCompletion failed"...
0x14002c410  mov     [rsp+68h+var_48], rax; char *
0x14002c415  call    TraceEvents
0x14002c41a  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 4
0x14002c421  jz      short loc_14002C43A
0x14002c423  mov     eax, [rbx+30h]
0x14002c426  lea     rdx, CTLogFlushBuffersFailed
0x14002c42d  mov     r9, [rsi+20h]
0x14002c431  mov     dword ptr [rsp+68h+var_48], eax
0x14002c435  call    McTemplateK0zq_EtwWriteTransfer
0x14002c43a  cmp     byte ptr [rsi+1150h], 0
0x14002c441  mov     rcx, r15
0x14002c444  mov     edx, [rbx+30h]
0x14002c447  jz      short loc_14002C450
0x14002c449  call    VhdmpiAccumulateMirrorStatus
0x14002c44e  jmp     short loc_14002C45C
0x14002c450  mov     r8d, [r15+844h]
0x14002c457  call    VhdmpiCTLogFailChangeTracking
0x14002c45c  mov     rcx, [rbx+8]; Mdl
0x14002c460  test    rcx, rcx
0x14002c463  jz      short loc_14002C48C
0x14002c465  mov     r8, [rdi+38h]; void *
0x14002c469  test    r8, r8
0x14002c46c  jz      short loc_14002C478
0x14002c46e  mov     edx, [rdi+30h]; unsigned int
0x14002c471  call    ?VhdmpiCTDeleteMasterMDL@@YAXPEAU_MDL@@KPEAX@Z; VhdmpiCTDeleteMasterMDL(_MDL *,ulong,void *)
0x14002c476  jmp     short loc_14002C484
0x14002c478  call    cs:__imp_IoFreeMdl
0x14002c47f  nop     dword ptr [rax+rax+00h]
0x14002c484  mov     qword ptr [rbx+8], 0
0x14002c48c  mov     rcx, rbx; Irp
0x14002c48f  call    cs:__imp_IoFreeIrp
0x14002c496  nop     dword ptr [rax+rax+00h]
0x14002c49b  lea     rax, [rbp+var_18]
0x14002c49f  mov     [rbp+var_18+8], rax
0x14002c4a3  lea     rax, [rbp+var_18]
0x14002c4a7  mov     [rbp+var_18], rax
0x14002c4ab  mov     rax, [r14+8]
0x14002c4af  cmp     [rax], r14
0x14002c4b2  jnz     loc_14002C550
0x14002c4b8  mov     [rbp+var_18+8], rax
0x14002c4bc  lea     rcx, [rbp+var_18]
0x14002c4c0  mov     [rbp+var_18], r14
0x14002c4c4  mov     [rax], rcx
0x14002c4c7  lea     rax, [rbp+var_18]
0x14002c4cb  mov     [r14+8], rax
0x14002c4cf  mov     rcx, [rdi+28h]; Event
0x14002c4d3  test    rcx, rcx
0x14002c4d6  jz      short loc_14002C4E9
0x14002c4d8  xor     r8d, r8d; Wait
0x14002c4db  xor     edx, edx; Increment
0x14002c4dd  call    cs:__imp_KeSetEvent
0x14002c4e4  nop     dword ptr [rax+rax+00h]
0x14002c4e9  lea     rcx, [rsi+1080h]; Lookaside
0x14002c4f0  mov     rdx, rdi; Entry
0x14002c4f3  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002c4fa  nop     dword ptr [rax+rax+00h]
0x14002c4ff  mov     rbx, [rbp+var_18]
0x14002c503  lea     rax, [rbp+var_18]
0x14002c507  cmp     rbx, rax
0x14002c50a  jz      short loc_14002C53D
0x14002c50c  lea     rax, [rbp+var_18]
0x14002c510  cmp     [rbx+8], rax
0x14002c514  jnz     short loc_14002C550
0x14002c516  mov     rax, [rbx]
0x14002c519  cmp     [rax+8], rbx
0x14002c51d  jnz     short loc_14002C550
0x14002c51f  lea     rcx, [rbp+var_18]
0x14002c523  mov     [rbp+var_18], rax
0x14002c527  mov     [rax+8], rcx
0x14002c52b  mov     rcx, rbx; struct _CTLOG_BUFFER *
0x14002c52e  call    ?VhdmpiCTDetachBufferFromBackingStore@@YAXPEAU_CTLOG_BUFFER@@@Z; VhdmpiCTDetachBufferFromBackingStore(_CTLOG_BUFFER *)
0x14002c533  mov     rcx, rbx; struct _CTLOG_BUFFER *
0x14002c536  call    ?VhdmpiCTAddToAvailableBufferList@@YAXPEAU_CTLOG_BUFFER@@@Z; VhdmpiCTAddToAvailableBufferList(_CTLOG_BUFFER *)
0x14002c53b  jmp     short loc_14002C4FF
0x14002c53d  mov     eax, 0C0000016h
0x14002c542  add     rsp, 68h
0x14002c546  pop     r15
0x14002c548  pop     r14
0x14002c54a  pop     rdi
0x14002c54b  pop     rsi
0x14002c54c  pop     rbx
0x14002c54d  pop     rbp
0x14002c54e  retn
0x14002c550  mov     ecx, 3
0x14002c555  int     29h; Win8: RtlFailFast(ecx)
```
