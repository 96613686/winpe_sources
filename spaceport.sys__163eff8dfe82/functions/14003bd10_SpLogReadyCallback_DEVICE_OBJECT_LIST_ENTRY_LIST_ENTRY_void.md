# SpLogReadyCallback(_DEVICE_OBJECT *,_LIST_ENTRY *,_LIST_ENTRY *,void *)

- ea: `0x14003bd10`
- end: `0x14003be38`
- name: `?SpLogReadyCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_LIST_ENTRY@@1PEAX@Z`
- size: `296`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x14001e160`
- `0x140032354`
- `0x1400325fc`
- `0x14003bd10`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14003bd93`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14003bd93`
- `ntoskrnl!IofCompleteRequest` at `0x14003be09`
- `ntoskrnl!IofCompleteRequest` at `0x14003be09`
- `ntoskrnl!KeDelayExecutionThread` at `0x14003bdb8`
- `ntoskrnl!KeDelayExecutionThread` at `0x14003bdb8`

## pseudocode

```c
__int64 __fastcall SpLogReadyCallback(
        struct _DEVICE_OBJECT *a1,
        struct _LIST_ENTRY *a2,
        struct _LIST_ENTRY *a3,
        void *a4)
{
  char *DeviceExtension; // rdi
  int v5; // r14d
  int i; // r15d
  int v8; // ebp
  __int64 v9; // rcx
  int v10; // esi
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *v12; // rax
  IRP *p_Blink; // rcx
  union _LARGE_INTEGER Interval; // [rsp+50h] [rbp+8h] BYREF

  DeviceExtension = (char *)a1->DeviceExtension;
  v5 = 600000;
  Interval.QuadPart = -2000000;
  for ( i = 0; ; i = v10 )
  {
    v8 = SP_DEVICE::AcquireRundownSharedNonQueued((SP_DEVICE *)(DeviceExtension + 8));
    if ( v8 < 0 )
      break;
    v9 = *((_QWORD *)DeviceExtension + 404);
    v10 = *(_DWORD *)(*(_QWORD *)(v9 + 376) + 300LL);
    if ( !v10 )
    {
      SP_POOL::PauseTasks(*(SP_POOL **)(v9 + 1160));
      SP_POOL::ResumeTasks(*(SP_POOL **)(*((_QWORD *)DeviceExtension + 404) + 1160LL));
    }
    ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)DeviceExtension + 31));
    if ( !v10 )
      break;
    if ( v5 <= 0 )
    {
      v8 = -1073741661;
      break;
    }
    if ( v10 != i )
      v5 = 600000;
    KeDelayExecutionThread(0, 0, &Interval);
    v5 -= 200;
    if ( v10 == i )
      v10 = i;
  }
  while ( 1 )
  {
    Flink = a2->Flink;
    if ( a2->Flink == a2 )
      break;
    if ( Flink->Blink != a2 || (v12 = Flink->Flink, Flink->Flink->Blink != Flink) )
      __fastfail(3u);
    a2->Flink = v12;
    p_Blink = (IRP *)&Flink[-11].Blink;
    v12->Blink = a2;
    p_Blink->IoStatus.Status = v8;
    IofCompleteRequest(p_Blink, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14003bd10  mov     [rsp+arg_8], rbx
0x14003bd15  mov     [rsp+arg_10], rbp
0x14003bd1a  push    rsi
0x14003bd1b  push    rdi
0x14003bd1c  push    r12
0x14003bd1e  push    r14
0x14003bd20  push    r15
0x14003bd22  sub     rsp, 20h
0x14003bd26  mov     rdi, [rcx+40h]
0x14003bd2a  mov     r12d, 927C0h
0x14003bd30  mov     r14d, r12d
0x14003bd33  mov     qword ptr [rsp+48h+Interval], 0FFFFFFFFFFE17B80h
0x14003bd3c  mov     rbx, rdx
0x14003bd3f  xor     r15d, r15d
0x14003bd42  lea     rcx, [rdi+8]; this
0x14003bd46  call    ?AcquireRundownSharedNonQueued@SP_DEVICE@@QEAAJXZ; SP_DEVICE::AcquireRundownSharedNonQueued(void)
0x14003bd4b  mov     ebp, eax
0x14003bd4d  test    eax, eax
0x14003bd4f  js      loc_14003BDDF
0x14003bd55  mov     rcx, [rdi+0CA0h]
0x14003bd5c  mov     rdx, [rcx+178h]
0x14003bd63  mov     esi, [rdx+12Ch]
0x14003bd69  test    esi, esi
0x14003bd6b  jnz     short loc_14003BD8C
0x14003bd6d  mov     rcx, [rcx+488h]; this
0x14003bd74  call    ?PauseTasks@SP_POOL@@QEAAXXZ; SP_POOL::PauseTasks(void)
0x14003bd79  mov     rcx, [rdi+0CA0h]
0x14003bd80  mov     rcx, [rcx+488h]; this
0x14003bd87  call    ?ResumeTasks@SP_POOL@@QEAAXXZ; SP_POOL::ResumeTasks(void)
0x14003bd8c  mov     rcx, [rdi+0F8h]; RunRefCacheAware
0x14003bd93  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14003bd9a  nop     dword ptr [rax+rax+00h]
0x14003bd9f  test    esi, esi
0x14003bda1  jz      short loc_14003BDDF
0x14003bda3  test    r14d, r14d
0x14003bda6  jle     short loc_14003BDDA
0x14003bda8  cmp     esi, r15d
0x14003bdab  lea     r8, [rsp+48h+Interval]; Interval
0x14003bdb0  cmovnz  r14d, r12d
0x14003bdb4  xor     edx, edx; Alertable
0x14003bdb6  xor     ecx, ecx; WaitMode
0x14003bdb8  call    cs:__imp_KeDelayExecutionThread
0x14003bdbf  nop     dword ptr [rax+rax+00h]
0x14003bdc4  sub     r14d, 0C8h
0x14003bdcb  cmp     esi, r15d
0x14003bdce  cmovz   esi, r15d
0x14003bdd2  mov     r15d, esi
0x14003bdd5  jmp     loc_14003BD42
0x14003bdda  mov     ebp, 0C00000A3h
0x14003bddf  mov     rcx, [rbx]
0x14003bde2  cmp     rcx, rbx
0x14003bde5  jz      short loc_14003BE1E
0x14003bde7  cmp     [rcx+8], rbx
0x14003bdeb  jnz     short loc_14003BE17
0x14003bded  mov     rax, [rcx]
0x14003bdf0  cmp     [rax+8], rcx
0x14003bdf4  jnz     short loc_14003BE17
0x14003bdf6  mov     [rbx], rax
0x14003bdf9  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x14003be00  mov     [rax+8], rbx
0x14003be04  xor     edx, edx; PriorityBoost
0x14003be06  mov     [rcx+30h], ebp
0x14003be09  call    cs:__imp_IofCompleteRequest
0x14003be10  nop     dword ptr [rax+rax+00h]
0x14003be15  jmp     short loc_14003BDDF
0x14003be17  mov     ecx, 3
0x14003be1c  int     29h; Win8: RtlFailFast(ecx)
0x14003be1e  mov     rbx, [rsp+48h+arg_8]
0x14003be23  xor     eax, eax
0x14003be25  mov     rbp, [rsp+48h+arg_10]
0x14003be2a  add     rsp, 20h
0x14003be2e  pop     r15
0x14003be30  pop     r14
0x14003be32  pop     r12
0x14003be34  pop     rdi
0x14003be35  pop     rsi
0x14003be36  retn
```
