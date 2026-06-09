# VmpQueryVolumeNumber(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x140013674`
- end: `0x1400136af`
- name: `?VmpQueryVolumeNumber@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `59`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140001ae0`

## callees

- `0x140013674`

## pseudocode

```c
__int64 __fastcall VmpQueryVolumeNumber(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  __int64 result; // rax
  struct _IRP *MasterIrp; // rcx

  if ( a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length < 0x14 )
    return 3221225485LL;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  *(_DWORD *)&MasterIrp->Type = *((_DWORD *)a1 + 41);
  result = 0;
  *(_OWORD *)(&MasterIrp->Size + 1) = *(_OWORD *)L"VOLMGR  ";
  a2->IoStatus.Information = 20;
  return result;
}

```

## disassembly

```asm
0x140013674  mov     rax, [rdx+0B8h]
0x14001367b  mov     r8, rcx
0x14001367e  cmp     dword ptr [rax+8], 14h
0x140013682  jnb     short loc_14001368B
0x140013684  mov     eax, 0C000000Dh
0x140013689  retn
0x14001368b  mov     eax, [r8+0A4h]
0x140013692  mov     rcx, [rdx+18h]
0x140013696  mov     [rcx], eax
0x140013698  xor     eax, eax
0x14001369a  movups  xmm0, xmmword ptr cs:aVolmgr; "VOLMGR  "
0x1400136a1  movdqu  xmmword ptr [rcx+4], xmm0
0x1400136a6  mov     qword ptr [rdx+38h], 14h
0x1400136ae  retn
```
