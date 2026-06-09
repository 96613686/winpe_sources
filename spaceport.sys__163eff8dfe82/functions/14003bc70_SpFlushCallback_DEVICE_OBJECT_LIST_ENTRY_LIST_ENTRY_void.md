# SpFlushCallback(_DEVICE_OBJECT *,_LIST_ENTRY *,_LIST_ENTRY *,void *)

- ea: `0x14003bc70`
- end: `0x14003bd07`
- name: `?SpFlushCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_LIST_ENTRY@@1PEAX@Z`
- size: `151`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14001e160`
- `0x14002b7a4`
- `0x14003bc70`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14003bca9`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14003bca9`
- `ntoskrnl!IofCompleteRequest` at `0x14003bcdf`
- `ntoskrnl!IofCompleteRequest` at `0x14003bcdf`

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
0x14003bc70  mov     [rsp+arg_0], rbx
0x14003bc75  mov     [rsp+arg_8], rsi
0x14003bc7a  push    rdi
0x14003bc7b  sub     rsp, 20h
0x14003bc7f  mov     rsi, [rcx+40h]
0x14003bc83  mov     rbx, rdx
0x14003bc86  lea     rcx, [rsi+8]; this
0x14003bc8a  call    ?AcquireRundownSharedNonQueued@SP_DEVICE@@QEAAJXZ; SP_DEVICE::AcquireRundownSharedNonQueued(void)
0x14003bc8f  mov     edi, eax
0x14003bc91  test    eax, eax
0x14003bc93  js      short loc_14003BCB5
0x14003bc95  xor     edx, edx; unsigned __int8
0x14003bc97  lea     rcx, [rsi+8]; this
0x14003bc9b  call    ?FlushMetadata@SP_DEVICE@@QEAAJE@Z; SP_DEVICE::FlushMetadata(uchar)
0x14003bca0  mov     rcx, [rsi+0F8h]; RunRefCacheAware
0x14003bca7  mov     edi, eax
0x14003bca9  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14003bcb0  nop     dword ptr [rax+rax+00h]
0x14003bcb5  mov     rcx, [rbx]
0x14003bcb8  cmp     rcx, rbx
0x14003bcbb  jz      short loc_14003BCF4
0x14003bcbd  cmp     [rcx+8], rbx
0x14003bcc1  jnz     short loc_14003BCED
0x14003bcc3  mov     rax, [rcx]
0x14003bcc6  cmp     [rax+8], rcx
0x14003bcca  jnz     short loc_14003BCED
0x14003bccc  mov     [rbx], rax
0x14003bccf  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x14003bcd6  mov     [rax+8], rbx
0x14003bcda  xor     edx, edx; PriorityBoost
0x14003bcdc  mov     [rcx+30h], edi
0x14003bcdf  call    cs:__imp_IofCompleteRequest
0x14003bce6  nop     dword ptr [rax+rax+00h]
0x14003bceb  jmp     short loc_14003BCB5
0x14003bced  mov     ecx, 3
0x14003bcf2  int     29h; Win8: RtlFailFast(ecx)
0x14003bcf4  mov     rbx, [rsp+28h+arg_0]
0x14003bcf9  mov     eax, edi
0x14003bcfb  mov     rsi, [rsp+28h+arg_8]
0x14003bd00  add     rsp, 20h
0x14003bd04  pop     rdi
0x14003bd05  retn
```
