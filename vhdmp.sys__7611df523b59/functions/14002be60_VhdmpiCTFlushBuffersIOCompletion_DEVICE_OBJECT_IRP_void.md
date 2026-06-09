# VhdmpiCTFlushBuffersIOCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x14002be60`
- end: `0x14002c037`
- name: `?VhdmpiCTFlushBuffersIOCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `471`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140014e5c`
- `0x140023560`
- `0x14002a390`
- `0x14002b91c`
- `0x14002bcbc`
- `0x14002bd20`
- `0x14002be60`
- `0x140033450`
- `0x140035e94`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14002bf6f`
- `ntoskrnl!IoFreeIrp` at `0x14002bf6f`
- `ntoskrnl!IoFreeMdl` at `0x14002bf58`
- `ntoskrnl!IoFreeMdl` at `0x14002bf58`
- `ntoskrnl!KeSetEvent` at `0x14002bfbd`
- `ntoskrnl!KeSetEvent` at `0x14002bfbd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002bfd3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002bfd3`

## string_xrefs

- `0x14002bee9`: `VhdmpiCTFlushBuffersIOCompletion failed for log file %S (VirtualDisk = %p) (BackingStore = %p): ERROR! IrpContext=0x%p  IrpStatus=0x%x`
- `0x14002bed3`: `VhdmpiCTFlushBuffersIOCompletion`

## pseudocode

```c
__int64 __fastcall VhdmpiCTFlushBuffersIOCompletion(struct _DEVICE_OBJECT *a1, struct _IRP *a2, void *a3)
{
  bool v3; // sf
  __int64 v4; // rsi
  __int64 v6; // r14
  int v8; // r8d
  __int64 v9; // r15
  int v10; // edx
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
    v9 = *(_QWORD *)(v4 + 72);
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
      TraceEvents(
        (int)"VhdmpiCTFlushBuffersIOCompletion",
        794,
        v8,
        v10,
        "VhdmpiCTFlushBuffersIOCompletion failed for log file %S (VirtualDisk = %p) (BackingStore = %p): ERROR! IrpContex"
        "t=0x%p  IrpStatus=0x%x",
        *(_QWORD *)(v4 + 32));
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
      VhdmpiCTLogFailChangeTracking(v9, Status, *(unsigned int *)(v9 + 2116));
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
0x14002be60  push    rbp
0x14002be62  push    rbx
0x14002be63  push    rsi
0x14002be64  push    rdi
0x14002be65  push    r14
0x14002be67  push    r15
0x14002be69  mov     rbp, rsp
0x14002be6c  sub     rsp, 68h
0x14002be70  cmp     dword ptr [rdx+30h], 0
0x14002be74  xorps   xmm0, xmm0
0x14002be77  mov     rsi, [r8+8]
0x14002be7b  mov     rdi, r8
0x14002be7e  mov     r14, [r8+18h]
0x14002be82  mov     rbx, rdx
0x14002be85  movups  xmmword ptr [rbp+var_18], xmm0
0x14002be89  jge     loc_14002BF3C
0x14002be8f  mov     eax, cs:dword_140087708
0x14002be95  mov     r8d, 2
0x14002be9b  mov     r15, [rsi+48h]
0x14002be9f  cmp     eax, r8d
0x14002bea2  jbe     short loc_14002BEFA
0x14002bea4  mov     edx, 1000h
0x14002bea9  lea     rcx, dword_140087708
0x14002beb0  call    _tlgKeywordOn
0x14002beb5  test    al, al
0x14002beb7  jz      short loc_14002BEFA
0x14002beb9  mov     eax, [rbx+30h]
0x14002bebc  mov     ecx, 31Ah
0x14002bec1  mov     [rsp+68h+var_20], eax
0x14002bec5  mov     r9d, edx; int
0x14002bec8  mov     rax, [rsi+20h]
0x14002becc  mov     edx, ecx; int
0x14002bece  mov     [rsp+68h+var_28], rdi
0x14002bed3  lea     rcx, aVhdmpictflushb_0; "VhdmpiCTFlushBuffersIOCompletion"
0x14002beda  mov     [rsp+68h+var_30], rsi
0x14002bedf  mov     [rsp+68h+var_38], r15
0x14002bee4  mov     qword ptr [rsp+68h+var_40], rax; char
0x14002bee9  lea     rax, aVhdmpictflushb; "VhdmpiCTFlushBuffersIOCompletion failed"...
0x14002bef0  mov     [rsp+68h+var_48], rax; char *
0x14002bef5  call    TraceEvents
0x14002befa  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 4
0x14002bf01  jz      short loc_14002BF1A
0x14002bf03  mov     eax, [rbx+30h]
0x14002bf06  lea     rdx, CTLogFlushBuffersFailed
0x14002bf0d  mov     r9, [rsi+20h]
0x14002bf11  mov     dword ptr [rsp+68h+var_48], eax
0x14002bf15  call    McTemplateK0zq_EtwWriteTransfer
0x14002bf1a  cmp     byte ptr [rsi+1150h], 0
0x14002bf21  mov     rcx, r15
0x14002bf24  mov     edx, [rbx+30h]
0x14002bf27  jz      short loc_14002BF30
0x14002bf29  call    VhdmpiAccumulateMirrorStatus
0x14002bf2e  jmp     short loc_14002BF3C
0x14002bf30  mov     r8d, [r15+844h]
0x14002bf37  call    VhdmpiCTLogFailChangeTracking
0x14002bf3c  mov     rcx, [rbx+8]; Mdl
0x14002bf40  test    rcx, rcx
0x14002bf43  jz      short loc_14002BF6C
0x14002bf45  mov     r8, [rdi+38h]; void *
0x14002bf49  test    r8, r8
0x14002bf4c  jz      short loc_14002BF58
0x14002bf4e  mov     edx, [rdi+30h]; unsigned int
0x14002bf51  call    ?VhdmpiCTDeleteMasterMDL@@YAXPEAU_MDL@@KPEAX@Z; VhdmpiCTDeleteMasterMDL(_MDL *,ulong,void *)
0x14002bf56  jmp     short loc_14002BF64
0x14002bf58  call    cs:__imp_IoFreeMdl
0x14002bf5f  nop     dword ptr [rax+rax+00h]
0x14002bf64  mov     qword ptr [rbx+8], 0
0x14002bf6c  mov     rcx, rbx; Irp
0x14002bf6f  call    cs:__imp_IoFreeIrp
0x14002bf76  nop     dword ptr [rax+rax+00h]
0x14002bf7b  lea     rax, [rbp+var_18]
0x14002bf7f  mov     [rbp+var_18+8], rax
0x14002bf83  lea     rax, [rbp+var_18]
0x14002bf87  mov     [rbp+var_18], rax
0x14002bf8b  mov     rax, [r14+8]
0x14002bf8f  cmp     [rax], r14
0x14002bf92  jnz     loc_14002C030
0x14002bf98  mov     [rbp+var_18+8], rax
0x14002bf9c  lea     rcx, [rbp+var_18]
0x14002bfa0  mov     [rbp+var_18], r14
0x14002bfa4  mov     [rax], rcx
0x14002bfa7  lea     rax, [rbp+var_18]
0x14002bfab  mov     [r14+8], rax
0x14002bfaf  mov     rcx, [rdi+28h]; Event
0x14002bfb3  test    rcx, rcx
0x14002bfb6  jz      short loc_14002BFC9
0x14002bfb8  xor     r8d, r8d; Wait
0x14002bfbb  xor     edx, edx; Increment
0x14002bfbd  call    cs:__imp_KeSetEvent
0x14002bfc4  nop     dword ptr [rax+rax+00h]
0x14002bfc9  lea     rcx, [rsi+1080h]; Lookaside
0x14002bfd0  mov     rdx, rdi; Entry
0x14002bfd3  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002bfda  nop     dword ptr [rax+rax+00h]
0x14002bfdf  mov     rbx, [rbp+var_18]
0x14002bfe3  lea     rax, [rbp+var_18]
0x14002bfe7  cmp     rbx, rax
0x14002bfea  jz      short loc_14002C01D
0x14002bfec  lea     rax, [rbp+var_18]
0x14002bff0  cmp     [rbx+8], rax
0x14002bff4  jnz     short loc_14002C030
0x14002bff6  mov     rax, [rbx]
0x14002bff9  cmp     [rax+8], rbx
0x14002bffd  jnz     short loc_14002C030
0x14002bfff  lea     rcx, [rbp+var_18]
0x14002c003  mov     [rbp+var_18], rax
0x14002c007  mov     [rax+8], rcx
0x14002c00b  mov     rcx, rbx; struct _CTLOG_BUFFER *
0x14002c00e  call    ?VhdmpiCTDetachBufferFromBackingStore@@YAXPEAU_CTLOG_BUFFER@@@Z; VhdmpiCTDetachBufferFromBackingStore(_CTLOG_BUFFER *)
0x14002c013  mov     rcx, rbx; struct _CTLOG_BUFFER *
0x14002c016  call    ?VhdmpiCTAddToAvailableBufferList@@YAXPEAU_CTLOG_BUFFER@@@Z; VhdmpiCTAddToAvailableBufferList(_CTLOG_BUFFER *)
0x14002c01b  jmp     short loc_14002BFDF
0x14002c01d  mov     eax, 0C0000016h
0x14002c022  add     rsp, 68h
0x14002c026  pop     r15
0x14002c028  pop     r14
0x14002c02a  pop     rdi
0x14002c02b  pop     rsi
0x14002c02c  pop     rbx
0x14002c02d  pop     rbp
0x14002c02e  retn
0x14002c030  mov     ecx, 3
0x14002c035  int     29h; Win8: RtlFailFast(ecx)
```
