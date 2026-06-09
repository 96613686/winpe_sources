# VmpQueryVetoQueryRemove(VM_ROOT_EXTENSION *,_IRP *)

- ea: `0x140013594`
- end: `0x14001366c`
- name: `?VmpQueryVetoQueryRemove@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z`
- size: `216`
- prototype: `__int64 __fastcall(struct VM_ROOT_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140002ea0`

## callees

- `0x140003170`
- `0x140003990`
- `0x140005090`
- `0x140013594`

## pseudocode

```c
__int64 __fastcall VmpQueryVetoQueryRemove(struct VM_ROOT_EXTENSION *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IRP *MasterIrp; // rsi
  __int64 v5; // rbp
  PMDL MdlAddress; // r15
  __int64 *i; // rbx
  char v9; // [rsp+68h] [rbp+10h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v9 = 0;
  if ( CurrentStackLocation->Parameters.Create.Options < 0x18 || !CurrentStackLocation->Parameters.Read.Length )
    return 3221225485LL;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  v5 = *(_QWORD *)&MasterIrp->Type;
  MdlAddress = MasterIrp->MdlAddress;
  LOBYTE(MasterIrp->Type) = 0;
  a2->IoStatus.Information = 1;
  VmpAcquireDevices(a1);
  for ( i = (__int64 *)*((_QWORD *)a1 + 26); i != (__int64 *)((char *)a1 + 208); i = (__int64 *)*i )
  {
    if ( *((_BYTE *)i + 394) )
    {
      if ( i[50]
        && *((_BYTE *)i + 124)
        && (*(unsigned __int8 (__fastcall **)(__int64, PMDL, char *))(*((_QWORD *)a1 + 49) + 200LL))(
             i[50],
             MdlAddress,
             &v9) )
      {
        LOBYTE(MasterIrp->Type) = v9 == 0;
        break;
      }
    }
    else if ( i[39] == v5 && *((_BYTE *)i + 124) )
    {
      break;
    }
  }
  VmpReleaseDevices((struct _KMUTANT *)a1);
  return 0;
}

```

## disassembly

```asm
0x140013594  push    rbx
0x140013596  push    rbp
0x140013597  push    rsi
0x140013598  push    rdi
0x140013599  push    r14
0x14001359b  push    r15
0x14001359d  sub     rsp, 28h
0x1400135a1  mov     rax, [rdx+0B8h]
0x1400135a8  mov     rdi, rcx
0x1400135ab  mov     [rsp+58h+arg_8], 0
0x1400135b0  cmp     dword ptr [rax+10h], 18h
0x1400135b4  jb      loc_140013659
0x1400135ba  cmp     dword ptr [rax+8], 1
0x1400135be  jb      loc_140013659
0x1400135c4  mov     rsi, [rdx+18h]
0x1400135c8  mov     rbp, [rsi]
0x1400135cb  mov     r15, [rsi+8]
0x1400135cf  mov     byte ptr [rsi], 0
0x1400135d2  mov     qword ptr [rdx+38h], 1
0x1400135da  call    ?VmpAcquireDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpAcquireDevices(VM_ROOT_EXTENSION *)
0x1400135df  lea     r14, [rdi+0D0h]
0x1400135e6  mov     rbx, [r14]
0x1400135e9  cmp     rbx, r14
0x1400135ec  jz      short loc_140013638
0x1400135ee  cmp     byte ptr [rbx+18Ah], 0
0x1400135f5  jz      short loc_140013644
0x1400135f7  cmp     qword ptr [rbx+190h], 0
0x1400135ff  jz      short loc_140013654
0x140013601  mov     al, [rbx+7Ch]
0x140013604  test    al, al
0x140013606  jz      short loc_140013654
0x140013608  mov     rax, [rdi+188h]
0x14001360f  lea     r8, [rsp+58h+arg_8]
0x140013614  mov     rcx, [rbx+190h]
0x14001361b  mov     rdx, r15
0x14001361e  mov     rax, [rax+0C8h]
0x140013625  call    _guard_dispatch_icall
0x14001362a  test    al, al
0x14001362c  jz      short loc_140013654
0x14001362e  cmp     [rsp+58h+arg_8], 0
0x140013633  setz    al
0x140013636  mov     [rsi], al
0x140013638  mov     rcx, rdi; struct VM_ROOT_EXTENSION *
0x14001363b  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x140013640  xor     eax, eax
0x140013642  jmp     short loc_14001365E
0x140013644  cmp     [rbx+138h], rbp
0x14001364b  jnz     short loc_140013654
0x14001364d  mov     al, [rbx+7Ch]
0x140013650  test    al, al
0x140013652  jnz     short loc_140013638
0x140013654  mov     rbx, [rbx]
0x140013657  jmp     short loc_1400135E9
0x140013659  mov     eax, 0C000000Dh
0x14001365e  add     rsp, 28h
0x140013662  pop     r15
0x140013664  pop     r14
0x140013666  pop     rdi
0x140013667  pop     rsi
0x140013668  pop     rbp
0x140013669  pop     rbx
0x14001366a  retn
```
