# SpSpaceFlush(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140010730`
- end: `0x1400108e7`
- name: `?SpSpaceFlush@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `439`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140034f5c`
- `0x140035738`

## callees

- `0x140010730`
- `0x1400108f0`
- `0x140010e10`
- `0x140011570`
- `0x140011970`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400108d1`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400108d1`
- `ntoskrnl!IofCompleteRequest` at `0x140010832`
- `ntoskrnl!IofCompleteRequest` at `0x140010832`

## pseudocode

```c
__int64 __fastcall SpSpaceFlush(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  PEX_RUNDOWN_REF_CACHE_AWARE *DeviceExtension; // rsi
  unsigned int v4; // edi
  __int64 v5; // r8
  __int64 v6; // r9
  struct _IO_STACK_LOCATION *v7; // rax
  struct _IO_STACK_LOCATION *v8; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v11; // rax
  struct _IO_STACK_LOCATION *v12; // rax

  DeviceExtension = (PEX_RUNDOWN_REF_CACHE_AWARE *)a1->DeviceExtension;
  a2->IoStatus.Information = 0;
  SpIoCountersInitialize(a2);
  v4 = SP_DEVICE::AcquireRundownShared((SP_DEVICE *)(DeviceExtension + 1), a2);
  if ( !v4 )
  {
    if ( DeviceExtension[18]
      || DeviceExtension[17]
      || *((_BYTE *)DeviceExtension + 3121)
      && (*(_DWORD *)(*((_QWORD *)DeviceExtension[404] + 47) + 248LL) == 1
       || *(_DWORD *)(*((_QWORD *)DeviceExtension[404] + 47) + 248LL) == 2
       || *(_DWORD *)(*((_QWORD *)DeviceExtension[404] + 47) + 248LL) == 4) )
    {
      CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
      *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
      *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                                 + 6);
      CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
      CurrentStackLocation[-1].Control = 0;
      v11 = a2->Tail.Overlay.CurrentStackLocation;
      v11[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpIoCompletionRoutine;
      v11[-1].Context = 0;
      v11[-1].Control = -32;
      v12 = --a2->Tail.Overlay.CurrentStackLocation;
      --a2->CurrentLocation;
      v12->Control |= 1u;
      SP_WORKITEM::Insert(DeviceExtension + 273, &a2->Tail.Overlay.ListEntry, 0, 0);
      ExReleaseRundownProtectionCacheAware(DeviceExtension[31]);
      return 259;
    }
    v7 = a2->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&v7[-1].MajorFunction = *(_OWORD *)&v7->MajorFunction;
    *(_OWORD *)&v7[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v7->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v7[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v7->Parameters.SetQuota + 6);
    v7[-1].FileObject = v7->FileObject;
    v7[-1].Control = 0;
    v8 = a2->Tail.Overlay.CurrentStackLocation;
    v8[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpIoCompletionRoutine;
    v8[-1].Context = (PVOID)2;
    v8[-1].Control = -32;
    --a2->CurrentLocation;
    --a2->Tail.Overlay.CurrentStackLocation;
    v4 = SP_DEVICE::Prepare(DeviceExtension + 1, a2, v5, v6);
  }
  if ( v4 != 259 )
  {
    a2->IoStatus.Status = v4;
    IofCompleteRequest(a2, 0);
  }
  return v4;
}

```

## disassembly

```asm
0x140010730  mov     [rsp+arg_0], rbx
0x140010735  mov     [rsp+arg_8], rsi
0x14001073a  push    rdi
0x14001073b  sub     rsp, 20h
0x14001073f  mov     rsi, [rcx+40h]
0x140010743  mov     rbx, rdx
0x140010746  mov     rcx, rdx; struct _IRP *
0x140010749  mov     qword ptr [rdx+38h], 0
0x140010751  call    ?SpIoCountersInitialize@@YAXPEAU_IRP@@@Z; SpIoCountersInitialize(_IRP *)
0x140010756  mov     rdx, rbx; struct _IRP *
0x140010759  lea     rcx, [rsi+8]; this
0x14001075d  call    ?AcquireRundownShared@SP_DEVICE@@QEAAJPEAU_IRP@@@Z; SP_DEVICE::AcquireRundownShared(_IRP *)
0x140010762  mov     edi, eax
0x140010764  test    eax, eax
0x140010766  jnz     loc_140010822
0x14001076c  cmp     qword ptr [rsi+90h], 0
0x140010774  jnz     loc_140010851
0x14001077a  cmp     qword ptr [rsi+88h], 0
0x140010782  jnz     loc_140010851
0x140010788  cmp     [rsi+0C31h], al
0x14001078e  jz      short loc_1400107BF
0x140010790  mov     rax, [rsi+0CA0h]
0x140010797  mov     rcx, [rax+178h]
0x14001079e  mov     edx, [rcx+0F8h]
0x1400107a4  sub     edx, 1
0x1400107a7  jz      loc_140010851
0x1400107ad  sub     edx, 1
0x1400107b0  jz      loc_140010851
0x1400107b6  cmp     edx, 2
0x1400107b9  jz      loc_140010851
0x1400107bf  mov     rax, [rbx+0B8h]
0x1400107c6  lea     rcx, ?SpIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SpIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x1400107cd  mov     rdx, rbx
0x1400107d0  movups  xmm0, xmmword ptr [rax]
0x1400107d3  movups  xmmword ptr [rax-48h], xmm0
0x1400107d7  movups  xmm1, xmmword ptr [rax+10h]
0x1400107db  movups  xmmword ptr [rax-38h], xmm1
0x1400107df  movups  xmm0, xmmword ptr [rax+20h]
0x1400107e3  movups  xmmword ptr [rax-28h], xmm0
0x1400107e7  movsd   xmm1, qword ptr [rax+30h]
0x1400107ec  movsd   qword ptr [rax-18h], xmm1
0x1400107f1  mov     byte ptr [rax-45h], 0
0x1400107f5  mov     rax, [rbx+0B8h]
0x1400107fc  mov     [rax-10h], rcx
0x140010800  lea     rcx, [rsi+8]
0x140010804  mov     qword ptr [rax-8], 2
0x14001080c  mov     byte ptr [rax-45h], 0E0h
0x140010810  dec     byte ptr [rbx+43h]
0x140010813  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x14001081b  call    ?Prepare@SP_DEVICE@@QEAAJPEAU_IRP@@W4_SC_OPERATION@@@Z; SP_DEVICE::Prepare(_IRP *,_SC_OPERATION)
0x140010820  mov     edi, eax
0x140010822  cmp     edi, 103h
0x140010828  jz      short loc_14001083E
0x14001082a  xor     edx, edx; PriorityBoost
0x14001082c  mov     [rbx+30h], edi
0x14001082f  mov     rcx, rbx; Irp
0x140010832  call    cs:__imp_IofCompleteRequest
0x140010839  nop     dword ptr [rax+rax+00h]
0x14001083e  mov     eax, edi
0x140010840  mov     rbx, [rsp+28h+arg_0]
0x140010845  mov     rsi, [rsp+28h+arg_8]
0x14001084a  add     rsp, 20h
0x14001084e  pop     rdi
0x14001084f  retn
0x140010851  mov     rax, [rbx+0B8h]
0x140010858  lea     rcx, ?SpIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SpIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x14001085f  lea     rdx, [rbx+0A8h]; struct _LIST_ENTRY *
0x140010866  xor     r9d, r9d; unsigned __int8
0x140010869  xor     r8d, r8d; unsigned int
0x14001086c  movups  xmm0, xmmword ptr [rax]
0x14001086f  movups  xmmword ptr [rax-48h], xmm0
0x140010873  movups  xmm1, xmmword ptr [rax+10h]
0x140010877  movups  xmmword ptr [rax-38h], xmm1
0x14001087b  movups  xmm0, xmmword ptr [rax+20h]
0x14001087f  movups  xmmword ptr [rax-28h], xmm0
0x140010883  movsd   xmm1, qword ptr [rax+30h]
0x140010888  movsd   qword ptr [rax-18h], xmm1
0x14001088d  mov     byte ptr [rax-45h], 0
0x140010891  mov     rax, [rbx+0B8h]
0x140010898  mov     [rax-10h], rcx
0x14001089c  lea     rcx, [rsi+888h]; Context
0x1400108a3  mov     qword ptr [rax-8], 0
0x1400108ab  mov     byte ptr [rax-45h], 0E0h
0x1400108af  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x1400108b7  mov     rax, [rbx+0B8h]
0x1400108be  dec     byte ptr [rbx+43h]
0x1400108c1  or      byte ptr [rax+3], 1
0x1400108c5  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x1400108ca  mov     rcx, [rsi+0F8h]; RunRefCacheAware
0x1400108d1  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400108d8  nop     dword ptr [rax+rax+00h]
0x1400108dd  mov     eax, 103h
0x1400108e2  jmp     loc_140010840
```
