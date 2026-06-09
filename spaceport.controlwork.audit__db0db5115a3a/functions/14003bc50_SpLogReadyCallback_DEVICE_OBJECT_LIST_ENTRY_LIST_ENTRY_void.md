# SpLogReadyCallback(_DEVICE_OBJECT *,_LIST_ENTRY *,_LIST_ENTRY *,void *)

- ea: `0x14003bc50`
- end: `0x14003bd78`
- name: `?SpLogReadyCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_LIST_ENTRY@@1PEAX@Z`
- size: `296`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x14001e160`
- `0x1400322e4`
- `0x14003258c`
- `0x14003bc50`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14003bcd3`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14003bcd3`
- `ntoskrnl!IofCompleteRequest` at `0x14003bd49`
- `ntoskrnl!IofCompleteRequest` at `0x14003bd49`
- `ntoskrnl!KeDelayExecutionThread` at `0x14003bcf8`
- `ntoskrnl!KeDelayExecutionThread` at `0x14003bcf8`

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
0x14003bc50  mov     [rsp+arg_8], rbx
0x14003bc55  mov     [rsp+arg_10], rbp
0x14003bc5a  push    rsi
0x14003bc5b  push    rdi
0x14003bc5c  push    r12
0x14003bc5e  push    r14
0x14003bc60  push    r15
0x14003bc62  sub     rsp, 20h
0x14003bc66  mov     rdi, [rcx+40h]
0x14003bc6a  mov     r12d, 927C0h
0x14003bc70  mov     r14d, r12d
0x14003bc73  mov     qword ptr [rsp+48h+Interval], 0FFFFFFFFFFE17B80h
0x14003bc7c  mov     rbx, rdx
0x14003bc7f  xor     r15d, r15d
0x14003bc82  lea     rcx, [rdi+8]; this
0x14003bc86  call    ?AcquireRundownSharedNonQueued@SP_DEVICE@@QEAAJXZ; SP_DEVICE::AcquireRundownSharedNonQueued(void)
0x14003bc8b  mov     ebp, eax
0x14003bc8d  test    eax, eax
0x14003bc8f  js      loc_14003BD1F
0x14003bc95  mov     rcx, [rdi+0CA0h]
0x14003bc9c  mov     rdx, [rcx+178h]
0x14003bca3  mov     esi, [rdx+12Ch]
0x14003bca9  test    esi, esi
0x14003bcab  jnz     short loc_14003BCCC
0x14003bcad  mov     rcx, [rcx+488h]; this
0x14003bcb4  call    ?PauseTasks@SP_POOL@@QEAAXXZ; SP_POOL::PauseTasks(void)
0x14003bcb9  mov     rcx, [rdi+0CA0h]
0x14003bcc0  mov     rcx, [rcx+488h]; this
0x14003bcc7  call    ?ResumeTasks@SP_POOL@@QEAAXXZ; SP_POOL::ResumeTasks(void)
0x14003bccc  mov     rcx, [rdi+0F8h]; RunRefCacheAware
0x14003bcd3  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14003bcda  nop     dword ptr [rax+rax+00h]
0x14003bcdf  test    esi, esi
0x14003bce1  jz      short loc_14003BD1F
0x14003bce3  test    r14d, r14d
0x14003bce6  jle     short loc_14003BD1A
0x14003bce8  cmp     esi, r15d
0x14003bceb  lea     r8, [rsp+48h+Interval]; Interval
0x14003bcf0  cmovnz  r14d, r12d
0x14003bcf4  xor     edx, edx; Alertable
0x14003bcf6  xor     ecx, ecx; WaitMode
0x14003bcf8  call    cs:__imp_KeDelayExecutionThread
0x14003bcff  nop     dword ptr [rax+rax+00h]
0x14003bd04  sub     r14d, 0C8h
0x14003bd0b  cmp     esi, r15d
0x14003bd0e  cmovz   esi, r15d
0x14003bd12  mov     r15d, esi
0x14003bd15  jmp     loc_14003BC82
0x14003bd1a  mov     ebp, 0C00000A3h
0x14003bd1f  mov     rcx, [rbx]
0x14003bd22  cmp     rcx, rbx
0x14003bd25  jz      short loc_14003BD5E
0x14003bd27  cmp     [rcx+8], rbx
0x14003bd2b  jnz     short loc_14003BD57
0x14003bd2d  mov     rax, [rcx]
0x14003bd30  cmp     [rax+8], rcx
0x14003bd34  jnz     short loc_14003BD57
0x14003bd36  mov     [rbx], rax
0x14003bd39  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x14003bd40  mov     [rax+8], rbx
0x14003bd44  xor     edx, edx; PriorityBoost
0x14003bd46  mov     [rcx+30h], ebp
0x14003bd49  call    cs:__imp_IofCompleteRequest
0x14003bd50  nop     dword ptr [rax+rax+00h]
0x14003bd55  jmp     short loc_14003BD1F
0x14003bd57  mov     ecx, 3
0x14003bd5c  int     29h; Win8: RtlFailFast(ecx)
0x14003bd5e  mov     rbx, [rsp+48h+arg_8]
0x14003bd63  xor     eax, eax
0x14003bd65  mov     rbp, [rsp+48h+arg_10]
0x14003bd6a  add     rsp, 20h
0x14003bd6e  pop     r15
0x14003bd70  pop     r14
0x14003bd72  pop     r12
0x14003bd74  pop     rdi
0x14003bd75  pop     rsi
0x14003bd76  retn
```
