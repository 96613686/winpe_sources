# VmpQueryFailoverSet(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x140013138`
- end: `0x1400131b3`
- name: `?VmpQueryFailoverSet@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `123`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001ae0`

## callees

- `0x140005090`
- `0x140013138`

## pseudocode

```c
__int64 __fastcall VmpQueryFailoverSet(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  __int64 v3; // rcx
  __int64 result; // rax
  struct _IRP *MasterIrp; // rcx

  if ( *((_BYTE *)a1 + 426) )
  {
    v3 = *((_QWORD *)a1 + 54);
    if ( v3 )
      return (*(__int64 (__fastcall **)(__int64, struct _IRP *))(*(_QWORD *)(*((_QWORD *)a1 + 1) + 392LL) + 104LL))(
               v3,
               a2);
    return 3221225486LL;
  }
  if ( !*((_QWORD *)a1 + 43) )
    return 3221225486LL;
  if ( a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length < 8 )
    return 3221225485LL;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  *(_DWORD *)&MasterIrp->Type = 1;
  *(_DWORD *)(&MasterIrp->Size + 1) = *((_DWORD *)a1 + 96);
  result = 0;
  a2->IoStatus.Information = 8;
  return result;
}

```

## disassembly

```asm
0x140013138  sub     rsp, 28h
0x14001313c  cmp     byte ptr [rcx+1AAh], 0
0x140013143  mov     r8, rcx
0x140013146  jz      short loc_14001316A
0x140013148  mov     rcx, [rcx+1B0h]
0x14001314f  test    rcx, rcx
0x140013152  jz      short loc_140013174
0x140013154  mov     rax, [r8+8]
0x140013158  mov     r8, [rax+188h]
0x14001315f  mov     rax, [r8+68h]
0x140013163  call    _guard_dispatch_icall
0x140013168  jmp     short loc_1400131AD
0x14001316a  cmp     qword ptr [rcx+158h], 0
0x140013172  jnz     short loc_14001317B
0x140013174  mov     eax, 0C000000Eh
0x140013179  jmp     short loc_1400131AD
0x14001317b  mov     rax, [rdx+0B8h]
0x140013182  cmp     dword ptr [rax+8], 8
0x140013186  jnb     short loc_14001318F
0x140013188  mov     eax, 0C000000Dh
0x14001318d  jmp     short loc_1400131AD
0x14001318f  mov     rcx, [rdx+18h]
0x140013193  mov     dword ptr [rcx], 1
0x140013199  mov     eax, [r8+180h]
0x1400131a0  mov     [rcx+4], eax
0x1400131a3  xor     eax, eax
0x1400131a5  mov     qword ptr [rdx+38h], 8
0x1400131ad  add     rsp, 28h
0x1400131b1  retn
```
