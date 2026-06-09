# VhdmpiMainProjectIoCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140041470`
- end: `0x14004155e`
- name: `?VhdmpiMainProjectIoCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `238`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140023560`
- `0x140026510`
- `0x140035e94`
- `0x140041470`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14004150f`
- `ntoskrnl!IoFreeIrp` at `0x14004150f`
- `ntoskrnl!IofCompleteRequest` at `0x140041541`
- `ntoskrnl!IofCompleteRequest` at `0x140041541`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041500`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041500`

## string_xrefs

- `0x1400414c2`: `VhdmpiMainProjectIoCompletion`
- `0x1400414b4`: `Block projection write completed with status: 0x%08x`

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
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2) )
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
0x140041470  push    rbx
0x140041472  push    rbp
0x140041473  push    rsi
0x140041474  push    rdi
0x140041475  push    r14
0x140041477  sub     rsp, 30h
0x14004147b  mov     eax, cs:dword_140087708
0x140041481  xor     ebp, ebp
0x140041483  mov     edi, [rdx+30h]
0x140041486  mov     rbx, r8
0x140041489  mov     rsi, rdx
0x14004148c  lea     r8d, [rbp+4]
0x140041490  cmp     eax, r8d
0x140041493  jbe     short loc_1400414CE
0x140041495  lea     edx, [rbp+2]
0x140041498  lea     rcx, dword_140087708
0x14004149f  call    _tlgKeywordOn
0x1400414a4  test    al, al
0x1400414a6  jz      short loc_1400414CE
0x1400414a8  mov     ecx, 0A67h
0x1400414ad  mov     dword ptr [rsp+58h+var_30], edi; char
0x1400414b1  mov     r9d, edx; int
0x1400414b4  lea     rax, aBlockProjectio_1; "Block projection write completed with s"...
0x1400414bb  mov     edx, ecx; int
0x1400414bd  mov     [rsp+58h+var_38], rax; char *
0x1400414c2  lea     rcx, aVhdmpimainproj; "VhdmpiMainProjectIoCompletion"
0x1400414c9  call    TraceEvents
0x1400414ce  test    edi, edi
0x1400414d0  js      short loc_1400414D5
0x1400414d2  mov     ebp, [rbx+5Ch]
0x1400414d5  mov     r14, [rsi+18h]
0x1400414d9  lea     rax, VhdmpiEmptyISOBackingStore
0x1400414e0  mov     rcx, [r14-8]
0x1400414e4  cmp     rcx, rax
0x1400414e7  jz      short loc_1400414F7
0x1400414e9  add     rcx, 48h ; 'H'
0x1400414ed  mov     edx, 1
0x1400414f2  call    VhdmpiFileWrapperUnpinFile
0x1400414f7  mov     edx, 70444856h; Tag
0x1400414fc  lea     rcx, [r14-8]; P
0x140041500  call    cs:__imp_ExFreePoolWithTag
0x140041507  nop     dword ptr [rax+rax+00h]
0x14004150c  mov     rcx, rsi; Irp
0x14004150f  call    cs:__imp_IoFreeIrp
0x140041516  nop     dword ptr [rax+rax+00h]
0x14004151b  mov     rax, [rbx+10h]
0x14004151f  xor     edx, edx; PriorityBoost
0x140041521  mov     ecx, ebp
0x140041523  mov     [rax+30h], edi
0x140041526  mov     rax, [rbx+10h]
0x14004152a  mov     [rax+38h], rcx
0x14004152e  mov     rax, [rbx+10h]
0x140041532  dec     byte ptr [rax+43h]
0x140041535  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x14004153d  mov     rcx, [rbx+10h]; Irp
0x140041541  call    cs:__imp_IofCompleteRequest
0x140041548  nop     dword ptr [rax+rax+00h]
0x14004154d  mov     eax, 0C0000016h
0x140041552  add     rsp, 30h
0x140041556  pop     r14
0x140041558  pop     rdi
0x140041559  pop     rsi
0x14004155a  pop     rbp
0x14004155b  pop     rbx
0x14004155c  retn
```
