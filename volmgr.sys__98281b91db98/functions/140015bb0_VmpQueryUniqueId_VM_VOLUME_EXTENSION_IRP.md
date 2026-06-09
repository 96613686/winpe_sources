# VmpQueryUniqueId(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x140015bb0`
- end: `0x140015c22`
- name: `?VmpQueryUniqueId@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001ae0`

## callees

- `0x140015bb0`
- `0x140015c30`

## pseudocode

```c
__int64 __fastcall VmpQueryUniqueId(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  ULONG Length; // eax
  struct _IRP *MasterIrp; // rdi
  __int64 result; // rax

  Length = a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length;
  if ( Length < 4 )
  {
    a2->IoStatus.Information = 0;
    return 3221225485LL;
  }
  else
  {
    MasterIrp = a2->AssociatedIrp.MasterIrp;
    MasterIrp->Type = Length - 2;
    result = VmpQueryUniqueIdInternal(a1, (unsigned __int16 *)MasterIrp, (unsigned __int8 *)&MasterIrp->Size);
    if ( (int)result >= 0 )
      a2->IoStatus.Information = (unsigned __int16)MasterIrp->Type + 2LL;
    else
      a2->IoStatus.Information = 2;
  }
  return result;
}

```

## disassembly

```asm
0x140015bb0  push    rbx
0x140015bb2  sub     rsp, 20h
0x140015bb6  mov     rax, [rdx+0B8h]
0x140015bbd  mov     rbx, rdx
0x140015bc0  mov     eax, [rax+8]
0x140015bc3  cmp     eax, 4
0x140015bc6  jb      short loc_140015C13
0x140015bc8  sub     ax, 2
0x140015bcc  mov     [rsp+28h+arg_0], rdi
0x140015bd1  mov     rdi, [rdx+18h]
0x140015bd5  mov     rdx, rdi; unsigned __int16 *
0x140015bd8  lea     r8, [rdi+2]; unsigned __int8 *
0x140015bdc  mov     [rdi], ax
0x140015bdf  call    ?VmpQueryUniqueIdInternal@@YAJPEAVVM_VOLUME_EXTENSION@@PEAGPEAE@Z; VmpQueryUniqueIdInternal(VM_VOLUME_EXTENSION *,ushort *,uchar *)
0x140015be4  test    eax, eax
0x140015be6  jns     short loc_140015BFC
0x140015be8  mov     rdi, [rsp+28h+arg_0]
0x140015bed  mov     qword ptr [rbx+38h], 2
0x140015bf5  add     rsp, 20h
0x140015bf9  pop     rbx
0x140015bfa  retn
0x140015bfc  movzx   ecx, word ptr [rdi]
0x140015bff  mov     rdi, [rsp+28h+arg_0]
0x140015c04  add     rcx, 2
0x140015c08  mov     [rbx+38h], rcx
0x140015c0c  add     rsp, 20h
0x140015c10  pop     rbx
0x140015c11  retn
0x140015c13  mov     qword ptr [rdx+38h], 0
0x140015c1b  mov     eax, 0C000000Dh
0x140015c20  jmp     short loc_140015BF5
```
