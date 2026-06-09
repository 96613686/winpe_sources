# SpFlushCallback(_DEVICE_OBJECT *,_LIST_ENTRY *,_LIST_ENTRY *,void *)

- ea: `0x14003bbb0`
- end: `0x14003bc47`
- name: `?SpFlushCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_LIST_ENTRY@@1PEAX@Z`
- size: `151`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14001e160`
- `0x14002b7a4`
- `0x14003bbb0`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14003bbe9`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14003bbe9`
- `ntoskrnl!IofCompleteRequest` at `0x14003bc1f`
- `ntoskrnl!IofCompleteRequest` at `0x14003bc1f`

## pseudocode

```c
__int64 __fastcall SpFlushCallback(struct _DEVICE_OBJECT *a1, struct _LIST_ENTRY *a2, struct _LIST_ENTRY *a3, void *a4)
{
  PEX_RUNDOWN_REF_CACHE_AWARE *DeviceExtension; // rsi
  int v6; // edi
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *v8; // rax
  IRP *p_Blink; // rcx

  DeviceExtension = (PEX_RUNDOWN_REF_CACHE_AWARE *)a1->DeviceExtension;
  v6 = SP_DEVICE::AcquireRundownSharedNonQueued(DeviceExtension + 1);
  if ( v6 >= 0 )
  {
    v6 = SP_DEVICE::FlushMetadata((SP_DEVICE *)(DeviceExtension + 1), 0);
    ExReleaseRundownProtectionCacheAware(DeviceExtension[31]);
  }
  while ( 1 )
  {
    Flink = a2->Flink;
    if ( a2->Flink == a2 )
      break;
    if ( Flink->Blink != a2 || (v8 = Flink->Flink, Flink->Flink->Blink != Flink) )
      __fastfail(3u);
    a2->Flink = v8;
    p_Blink = (IRP *)&Flink[-11].Blink;
    v8->Blink = a2;
    p_Blink->IoStatus.Status = v6;
    IofCompleteRequest(p_Blink, 0);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14003bbb0  mov     [rsp+arg_0], rbx
0x14003bbb5  mov     [rsp+arg_8], rsi
0x14003bbba  push    rdi
0x14003bbbb  sub     rsp, 20h
0x14003bbbf  mov     rsi, [rcx+40h]
0x14003bbc3  mov     rbx, rdx
0x14003bbc6  lea     rcx, [rsi+8]; this
0x14003bbca  call    ?AcquireRundownSharedNonQueued@SP_DEVICE@@QEAAJXZ; SP_DEVICE::AcquireRundownSharedNonQueued(void)
0x14003bbcf  mov     edi, eax
0x14003bbd1  test    eax, eax
0x14003bbd3  js      short loc_14003BBF5
0x14003bbd5  xor     edx, edx; unsigned __int8
0x14003bbd7  lea     rcx, [rsi+8]; this
0x14003bbdb  call    ?FlushMetadata@SP_DEVICE@@QEAAJE@Z; SP_DEVICE::FlushMetadata(uchar)
0x14003bbe0  mov     rcx, [rsi+0F8h]; RunRefCacheAware
0x14003bbe7  mov     edi, eax
0x14003bbe9  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14003bbf0  nop     dword ptr [rax+rax+00h]
0x14003bbf5  mov     rcx, [rbx]
0x14003bbf8  cmp     rcx, rbx
0x14003bbfb  jz      short loc_14003BC34
0x14003bbfd  cmp     [rcx+8], rbx
0x14003bc01  jnz     short loc_14003BC2D
0x14003bc03  mov     rax, [rcx]
0x14003bc06  cmp     [rax+8], rcx
0x14003bc0a  jnz     short loc_14003BC2D
0x14003bc0c  mov     [rbx], rax
0x14003bc0f  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x14003bc16  mov     [rax+8], rbx
0x14003bc1a  xor     edx, edx; PriorityBoost
0x14003bc1c  mov     [rcx+30h], edi
0x14003bc1f  call    cs:__imp_IofCompleteRequest
0x14003bc26  nop     dword ptr [rax+rax+00h]
0x14003bc2b  jmp     short loc_14003BBF5
0x14003bc2d  mov     ecx, 3
0x14003bc32  int     29h; Win8: RtlFailFast(ecx)
0x14003bc34  mov     rbx, [rsp+28h+arg_0]
0x14003bc39  mov     eax, edi
0x14003bc3b  mov     rsi, [rsp+28h+arg_8]
0x14003bc40  add     rsp, 20h
0x14003bc44  pop     rdi
0x14003bc45  retn
```
