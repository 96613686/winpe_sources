# VmpPmWmiCounterLibContext(VM_ROOT_EXTENSION *,_IRP *)

- ea: `0x140012eac`
- end: `0x140012f11`
- name: `?VmpPmWmiCounterLibContext@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z`
- size: `101`
- prototype: `__int64 __fastcall(struct VM_ROOT_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002ea0`

## callees

- `0x1400029e0`
- `0x140002a30`
- `0x140012eac`

## pseudocode

```c
__int64 __fastcall VmpPmWmiCounterLibContext(struct VM_ROOT_EXTENSION *a1, struct _IRP *a2)
{
  struct _IRP *MasterIrp; // rax

  if ( a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.Options < 0x28 )
    return 3221225485LL;
  VmpAcquireAll(a1);
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  *((_OWORD *)a1 + 19) = *(_OWORD *)&MasterIrp->Type;
  *((_OWORD *)a1 + 20) = *(_OWORD *)&MasterIrp->Flags;
  *((_QWORD *)a1 + 42) = MasterIrp->ThreadListEntry.Flink;
  VmpReleaseAll(a1);
  return 0;
}

```

## disassembly

```asm
0x140012eac  mov     [rsp+arg_0], rbx
0x140012eb1  push    rdi
0x140012eb2  sub     rsp, 20h
0x140012eb6  mov     rax, [rdx+0B8h]
0x140012ebd  mov     rdi, rdx
0x140012ec0  mov     rbx, rcx
0x140012ec3  cmp     dword ptr [rax+10h], 28h ; '('
0x140012ec7  jnb     short loc_140012ED0
0x140012ec9  mov     eax, 0C000000Dh
0x140012ece  jmp     short loc_140012F05
0x140012ed0  call    ?VmpAcquireAll@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpAcquireAll(VM_ROOT_EXTENSION *)
0x140012ed5  mov     rax, [rdi+18h]
0x140012ed9  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x140012edc  movups  xmm0, xmmword ptr [rax]
0x140012edf  movups  xmmword ptr [rbx+130h], xmm0
0x140012ee6  movups  xmm1, xmmword ptr [rax+10h]
0x140012eea  movups  xmmword ptr [rbx+140h], xmm1
0x140012ef1  movsd   xmm0, qword ptr [rax+20h]
0x140012ef6  movsd   qword ptr [rbx+150h], xmm0
0x140012efe  call    ?VmpReleaseAll@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseAll(VM_ROOT_EXTENSION *)
0x140012f03  xor     eax, eax
0x140012f05  mov     rbx, [rsp+28h+arg_0]
0x140012f0a  add     rsp, 20h
0x140012f0e  pop     rdi
0x140012f0f  retn
```
