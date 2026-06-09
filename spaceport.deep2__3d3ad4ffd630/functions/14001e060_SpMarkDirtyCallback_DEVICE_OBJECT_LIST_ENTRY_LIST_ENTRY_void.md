# SpMarkDirtyCallback(_DEVICE_OBJECT *,_LIST_ENTRY *,_LIST_ENTRY *,void *)

- ea: `0x14001e060`
- end: `0x14001e158`
- name: `?SpMarkDirtyCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_LIST_ENTRY@@1PEAX@Z`
- size: `248`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14001e060`
- `0x14001e160`
- `0x14002f610`
- `0x1400b7200`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001e0c3`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001e0ec`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001e0c3`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001e0ec`
- `ntoskrnl!IofCompleteRequest` at `0x14001e131`
- `ntoskrnl!IofCompleteRequest` at `0x14001e131`

## pseudocode

```c
__int64 __fastcall SpMarkDirtyCallback(
        struct _DEVICE_OBJECT *a1,
        struct _LIST_ENTRY *a2,
        struct _LIST_ENTRY *a3,
        void *a4)
{
  PEX_RUNDOWN_REF_CACHE_AWARE *v5; // rsi
  int v6; // edi
  PEX_RUNDOWN_REF_CACHE_AWARE *v7; // r14
  int v8; // eax
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *v10; // rcx

  v5 = (PEX_RUNDOWN_REF_CACHE_AWARE *)((char *)a1->DeviceExtension + 8);
  v6 = SP_DEVICE::AcquireRundownSharedNonQueued(v5);
  if ( v6 >= 0 )
  {
    while ( 1 )
    {
      v7 = v5 + 30;
      v6 = SIO_DRT::MarkDirty(*((SIO_DRT **)v5[403] + 46));
      if ( v6 != -1058602985 )
      {
LABEL_5:
        ExReleaseRundownProtectionCacheAware(*v7);
        goto LABEL_6;
      }
      v7 = v5 + 30;
      ExReleaseRundownProtectionCacheAware(v5[30]);
      v6 = SpDrtFull((struct SP_DEVICE *)v5);
      v8 = SP_DEVICE::AcquireRundownSharedNonQueued(v5);
      if ( v8 < 0 )
        break;
      if ( v6 < 0 )
        goto LABEL_5;
    }
    v6 = v8;
  }
LABEL_6:
  while ( 1 )
  {
    Flink = a2->Flink;
    if ( a2->Flink == a2 )
      break;
    if ( Flink->Blink != a2 || (v10 = Flink->Flink, Flink->Flink->Blink != Flink) )
      __fastfail(3u);
    a2->Flink = v10;
    v10->Blink = a2;
    LODWORD(Flink[-8].Blink) = v6;
    IofCompleteRequest((PIRP)&Flink[-11].Blink, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14001e060  mov     [rsp+arg_18], rbx
0x14001e065  push    rdi
0x14001e066  sub     rsp, 20h
0x14001e06a  mov     [rsp+28h+arg_8], rsi
0x14001e06f  mov     rbx, rdx
0x14001e072  mov     rsi, [rcx+40h]
0x14001e076  add     rsi, 8
0x14001e07a  mov     rcx, rsi; this
0x14001e07d  call    ?AcquireRundownSharedNonQueued@SP_DEVICE@@QEAAJXZ; SP_DEVICE::AcquireRundownSharedNonQueued(void)
0x14001e082  mov     edi, eax
0x14001e084  test    eax, eax
0x14001e086  js      short loc_14001E102
0x14001e088  mov     [rsp+28h+arg_0], rbp
0x14001e08d  mov     [rsp+28h+arg_10], r14
0x14001e092  mov     rcx, [rsi+0C98h]
0x14001e099  mov     rcx, [rcx+170h]; this
0x14001e0a0  call    ?MarkDirty@SIO_DRT@@QEAAJXZ; SIO_DRT::MarkDirty(void)
0x14001e0a5  lea     r14, [rsi+0F0h]
0x14001e0ac  mov     edi, eax
0x14001e0ae  test    eax, eax
0x14001e0b0  jns     short loc_14001E0E9
0x14001e0b2  cmp     eax, 0C0E70017h
0x14001e0b7  jnz     short loc_14001E0E9
0x14001e0b9  lea     r14, [rsi+0F0h]
0x14001e0c0  mov     rcx, [r14]; RunRefCacheAware
0x14001e0c3  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14001e0ca  nop     dword ptr [rax+rax+00h]
0x14001e0cf  mov     rcx, rsi; this
0x14001e0d2  call    ?SpDrtFull@@YAJPEAVSP_DEVICE@@@Z; SpDrtFull(SP_DEVICE *)
0x14001e0d7  mov     rcx, rsi; this
0x14001e0da  mov     edi, eax
0x14001e0dc  call    ?AcquireRundownSharedNonQueued@SP_DEVICE@@QEAAJXZ; SP_DEVICE::AcquireRundownSharedNonQueued(void)
0x14001e0e1  test    eax, eax
0x14001e0e3  js      short loc_14001E13F
0x14001e0e5  test    edi, edi
0x14001e0e7  jns     short loc_14001E092
0x14001e0e9  mov     rcx, [r14]; RunRefCacheAware
0x14001e0ec  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14001e0f3  nop     dword ptr [rax+rax+00h]
0x14001e0f8  mov     r14, [rsp+28h+arg_10]
0x14001e0fd  mov     rbp, [rsp+28h+arg_0]
0x14001e102  mov     rsi, [rsp+28h+arg_8]
0x14001e107  mov     rax, [rbx]
0x14001e10a  cmp     rax, rbx
0x14001e10d  jz      short loc_14001E14A
0x14001e10f  cmp     [rax+8], rbx
0x14001e113  jnz     short loc_14001E143
0x14001e115  mov     rcx, [rax]
0x14001e118  cmp     [rcx+8], rax
0x14001e11c  jnz     short loc_14001E143
0x14001e11e  mov     [rbx], rcx
0x14001e121  xor     edx, edx; PriorityBoost
0x14001e123  mov     [rcx+8], rbx
0x14001e127  lea     rcx, [rax-0A8h]; Irp
0x14001e12e  mov     [rcx+30h], edi
0x14001e131  call    cs:__imp_IofCompleteRequest
0x14001e138  nop     dword ptr [rax+rax+00h]
0x14001e13d  jmp     short loc_14001E107
0x14001e13f  mov     edi, eax
0x14001e141  jmp     short loc_14001E0F8
0x14001e143  mov     ecx, 3
0x14001e148  int     29h; Win8: RtlFailFast(ecx)
0x14001e14a  mov     rbx, [rsp+28h+arg_18]
0x14001e14f  xor     eax, eax
0x14001e151  add     rsp, 20h
0x14001e155  pop     rdi
0x14001e156  retn
```
