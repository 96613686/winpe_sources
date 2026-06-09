# SpUpdateColumnCallback(_DEVICE_OBJECT *,_LIST_ENTRY *,_LIST_ENTRY *,void *)

- ea: `0x14003cae0`
- end: `0x14003cb49`
- name: `?SpUpdateColumnCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_LIST_ENTRY@@1PEAX@Z`
- size: `105`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x14003c778`
- `0x14003cae0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14003cb26`
- `ntoskrnl!IofCompleteRequest` at `0x14003cb26`

## pseudocode

```c
__int64 __fastcall SpUpdateColumnCallback(
        struct _DEVICE_OBJECT *a1,
        struct _LIST_ENTRY *a2,
        struct _LIST_ENTRY *a3,
        void *a4)
{
  NTSTATUS updated; // edi
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *v7; // rdx
  IRP *p_Blink; // rcx

  updated = SpUpdateColumn((struct SP_DEVICE *)((char *)a1->DeviceExtension + 8));
  while ( 1 )
  {
    Flink = a2->Flink;
    if ( a2->Flink == a2 )
      break;
    if ( Flink->Blink != a2 || (v7 = Flink->Flink, Flink->Flink->Blink != Flink) )
      __fastfail(3u);
    a2->Flink = v7;
    p_Blink = (IRP *)&Flink[-11].Blink;
    v7->Blink = a2;
    p_Blink->IoStatus.Status = updated;
    IofCompleteRequest(p_Blink, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14003cae0  mov     [rsp+arg_0], rbx
0x14003cae5  push    rdi
0x14003cae6  sub     rsp, 20h
0x14003caea  mov     rcx, [rcx+40h]
0x14003caee  mov     rbx, rdx
0x14003caf1  add     rcx, 8; this
0x14003caf5  call    ?SpUpdateColumn@@YAJPEAVSP_DEVICE@@@Z; SpUpdateColumn(SP_DEVICE *)
0x14003cafa  mov     edi, eax
0x14003cafc  mov     rcx, [rbx]
0x14003caff  cmp     rcx, rbx
0x14003cb02  jz      short loc_14003CB3B
0x14003cb04  cmp     [rcx+8], rbx
0x14003cb08  jnz     short loc_14003CB34
0x14003cb0a  mov     rdx, [rcx]
0x14003cb0d  cmp     [rdx+8], rcx
0x14003cb11  jnz     short loc_14003CB34
0x14003cb13  mov     [rbx], rdx
0x14003cb16  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x14003cb1d  mov     [rdx+8], rbx
0x14003cb21  xor     edx, edx; PriorityBoost
0x14003cb23  mov     [rcx+30h], edi
0x14003cb26  call    cs:__imp_IofCompleteRequest
0x14003cb2d  nop     dword ptr [rax+rax+00h]
0x14003cb32  jmp     short loc_14003CAFC
0x14003cb34  mov     ecx, 3
0x14003cb39  int     29h; Win8: RtlFailFast(ecx)
0x14003cb3b  mov     rbx, [rsp+28h+arg_0]
0x14003cb40  xor     eax, eax
0x14003cb42  add     rsp, 20h
0x14003cb46  pop     rdi
0x14003cb47  retn
```
