# VhdmpiMainProjectIoCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140041860`
- end: `0x14004194e`
- name: `?VhdmpiMainProjectIoCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `238`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140023980`
- `0x140026930`
- `0x140036284`
- `0x140041860`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x1400418ff`
- `ntoskrnl!IoFreeIrp` at `0x1400418ff`
- `ntoskrnl!IofCompleteRequest` at `0x140041931`
- `ntoskrnl!IofCompleteRequest` at `0x140041931`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400418f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400418f0`

## string_xrefs

- `0x1400418b2`: `VhdmpiMainProjectIoCompletion`
- `0x1400418a4`: `Block projection write completed with status: 0x%08x`

## pseudocode

```c
__int64 __fastcall VhdmpiMainProjectIoCompletion(struct _DEVICE_OBJECT *a1, struct _IRP *a2, void *a3)
{
  unsigned int v3; // ebp
  NTSTATUS Status; // edi
  unsigned int v7; // edx
  unsigned __int8 v8; // r8
  struct _IRP *MasterIrp; // r14
  __int64 *v10; // rcx
  __int64 v11; // rax

  v3 = 0;
  Status = a2->IoStatus.Status;
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2) )
    TraceEvents(
      "VhdmpiMainProjectIoCompletion",
      0xA67u,
      v8,
      v7,
      "Block projection write completed with status: 0x%08x",
      Status);
  if ( Status >= 0 )
    v3 = *((_DWORD *)a3 + 23);
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  v10 = (__int64 *)*((_QWORD *)&MasterIrp[-1].Tail.CompletionKey + 10);
  if ( v10 != &VhdmpiEmptyISOBackingStore )
    VhdmpiFileWrapperUnpinFile(v10 + 9, 1);
  ExFreePoolWithTag(&MasterIrp[-1].Tail.CompletionKey + 10, 0x70444856u);
  IoFreeIrp(a2);
  *(_DWORD *)(*((_QWORD *)a3 + 2) + 48LL) = Status;
  *(_QWORD *)(*((_QWORD *)a3 + 2) + 56LL) = v3;
  v11 = *((_QWORD *)a3 + 2);
  --*(_BYTE *)(v11 + 67);
  *(_QWORD *)(v11 + 184) -= 72LL;
  IofCompleteRequest(*((PIRP *)a3 + 2), 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140041860  push    rbx
0x140041862  push    rbp
0x140041863  push    rsi
0x140041864  push    rdi
0x140041865  push    r14
0x140041867  sub     rsp, 30h
0x14004186b  mov     eax, cs:dword_1400876D0
0x140041871  xor     ebp, ebp
0x140041873  mov     edi, [rdx+30h]
0x140041876  mov     rbx, r8
0x140041879  mov     rsi, rdx
0x14004187c  lea     r8d, [rbp+4]
0x140041880  cmp     eax, r8d
0x140041883  jbe     short loc_1400418BE
0x140041885  lea     edx, [rbp+2]
0x140041888  lea     rcx, dword_1400876D0
0x14004188f  call    _tlgKeywordOn
0x140041894  test    al, al
0x140041896  jz      short loc_1400418BE
0x140041898  mov     ecx, 0A67h
0x14004189d  mov     dword ptr [rsp+58h+var_30], edi; char
0x1400418a1  mov     r9d, edx; int
0x1400418a4  lea     rax, aBlockProjectio_1; "Block projection write completed with s"...
0x1400418ab  mov     edx, ecx; int
0x1400418ad  mov     [rsp+58h+var_38], rax; char *
0x1400418b2  lea     rcx, aVhdmpimainproj; "VhdmpiMainProjectIoCompletion"
0x1400418b9  call    TraceEvents
0x1400418be  test    edi, edi
0x1400418c0  js      short loc_1400418C5
0x1400418c2  mov     ebp, [rbx+5Ch]
0x1400418c5  mov     r14, [rsi+18h]
0x1400418c9  lea     rax, VhdmpiEmptyISOBackingStore
0x1400418d0  mov     rcx, [r14-8]
0x1400418d4  cmp     rcx, rax
0x1400418d7  jz      short loc_1400418E7
0x1400418d9  add     rcx, 48h ; 'H'
0x1400418dd  mov     edx, 1
0x1400418e2  call    VhdmpiFileWrapperUnpinFile
0x1400418e7  mov     edx, 70444856h; Tag
0x1400418ec  lea     rcx, [r14-8]; P
0x1400418f0  call    cs:__imp_ExFreePoolWithTag
0x1400418f7  nop     dword ptr [rax+rax+00h]
0x1400418fc  mov     rcx, rsi; Irp
0x1400418ff  call    cs:__imp_IoFreeIrp
0x140041906  nop     dword ptr [rax+rax+00h]
0x14004190b  mov     rax, [rbx+10h]
0x14004190f  xor     edx, edx; PriorityBoost
0x140041911  mov     ecx, ebp
0x140041913  mov     [rax+30h], edi
0x140041916  mov     rax, [rbx+10h]
0x14004191a  mov     [rax+38h], rcx
0x14004191e  mov     rax, [rbx+10h]
0x140041922  dec     byte ptr [rax+43h]
0x140041925  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x14004192d  mov     rcx, [rbx+10h]; Irp
0x140041931  call    cs:__imp_IofCompleteRequest
0x140041938  nop     dword ptr [rax+rax+00h]
0x14004193d  mov     eax, 0C0000016h
0x140041942  add     rsp, 30h
0x140041946  pop     r14
0x140041948  pop     rdi
0x140041949  pop     rsi
0x14004194a  pop     rbp
0x14004194b  pop     rbx
0x14004194c  retn
```
