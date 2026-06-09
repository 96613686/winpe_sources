# SpUpdateColumnCallback(_DEVICE_OBJECT *,_LIST_ENTRY *,_LIST_ENTRY *,void *)

- ea: `0x14003ca20`
- end: `0x14003ca89`
- name: `?SpUpdateColumnCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_LIST_ENTRY@@1PEAX@Z`
- size: `105`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x14003c6b8`
- `0x14003ca20`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14003ca66`
- `ntoskrnl!IofCompleteRequest` at `0x14003ca66`

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
0x14003ca20  mov     [rsp+arg_0], rbx
0x14003ca25  push    rdi
0x14003ca26  sub     rsp, 20h
0x14003ca2a  mov     rcx, [rcx+40h]
0x14003ca2e  mov     rbx, rdx
0x14003ca31  add     rcx, 8; this
0x14003ca35  call    ?SpUpdateColumn@@YAJPEAVSP_DEVICE@@@Z; SpUpdateColumn(SP_DEVICE *)
0x14003ca3a  mov     edi, eax
0x14003ca3c  mov     rcx, [rbx]
0x14003ca3f  cmp     rcx, rbx
0x14003ca42  jz      short loc_14003CA7B
0x14003ca44  cmp     [rcx+8], rbx
0x14003ca48  jnz     short loc_14003CA74
0x14003ca4a  mov     rdx, [rcx]
0x14003ca4d  cmp     [rdx+8], rcx
0x14003ca51  jnz     short loc_14003CA74
0x14003ca53  mov     [rbx], rdx
0x14003ca56  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x14003ca5d  mov     [rdx+8], rbx
0x14003ca61  xor     edx, edx; PriorityBoost
0x14003ca63  mov     [rcx+30h], edi
0x14003ca66  call    cs:__imp_IofCompleteRequest
0x14003ca6d  nop     dword ptr [rax+rax+00h]
0x14003ca72  jmp     short loc_14003CA3C
0x14003ca74  mov     ecx, 3
0x14003ca79  int     29h; Win8: RtlFailFast(ecx)
0x14003ca7b  mov     rbx, [rsp+28h+arg_0]
0x14003ca80  xor     eax, eax
0x14003ca82  add     rsp, 20h
0x14003ca86  pop     rdi
0x14003ca87  retn
```
