# PtPowerUpToD0Complete

- ea: `0x1400014f0`
- end: `0x1400015d4`
- name: `PtPowerUpToD0Complete`
- size: `228`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400014f0`
- `0x14000173c`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400015bb`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400015bb`
- `ntoskrnl!PoSetPowerState` at `0x14000157e`
- `ntoskrnl!PoSetPowerState` at `0x14000157e`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000159e`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000159e`

## pseudocode

```c
__int64 __fastcall PtPowerUpToD0Complete(__int64 a1, IRP *a2, int a3)
{
  __int64 v5; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  struct _DEVICE_OBJECT *v7; // rcx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      a3,
      47,
      (__int64)WPP_75fd79d40e58354b8c24f648881272a9_Traceguids);
  v5 = *(_QWORD *)(a1 + 64);
  if ( a2->IoStatus.Status >= 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_s(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        a3,
        48,
        (__int64)WPP_75fd79d40e58354b8c24f648881272a9_Traceguids);
    CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
    v7 = *(struct _DEVICE_OBJECT **)v5;
    *(_QWORD *)(v5 + 56) = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
    PoSetPowerState(v7, CurrentStackLocation->Parameters.Power.Type, CurrentStackLocation->Parameters.Power.State);
  }
  if ( a2->PendingReturned )
    a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  PoStartNextPowerIrp(a2);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v5 + 24), PtPower, 0x20u);
  return 0;
}

```

## disassembly

```asm
0x1400014f0  push    rbx
0x1400014f2  push    rbp
0x1400014f3  push    rdi
0x1400014f4  push    r14
0x1400014f6  sub     rsp, 38h
0x1400014fa  mov     rbx, rdx
0x1400014fd  mov     rdi, rcx
0x140001500  lea     rbp, WPP_RECORDER_INITIALIZED
0x140001507  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000150e  lea     r14, WPP_75fd79d40e58354b8c24f648881272a9_Traceguids
0x140001515  jz      short loc_140001532
0x140001517  mov     rcx, cs:WPP_GLOBAL_Control
0x14000151e  mov     r9d, 2Fh ; '/'
0x140001524  mov     [rsp+58h+var_38], r14
0x140001529  mov     rcx, [rcx+40h]
0x14000152d  call    WPP_RECORDER_SF_s
0x140001532  cmp     dword ptr [rbx+30h], 0
0x140001536  mov     rdi, [rdi+40h]
0x14000153a  jl      short loc_14000158A
0x14000153c  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140001543  jz      short loc_140001560
0x140001545  mov     rcx, cs:WPP_GLOBAL_Control
0x14000154c  mov     r9d, 30h ; '0'
0x140001552  mov     [rsp+58h+var_38], r14
0x140001557  mov     rcx, [rcx+40h]
0x14000155b  call    WPP_RECORDER_SF_s
0x140001560  mov     rdx, [rbx+0B8h]
0x140001567  mov     rcx, [rdi]; DeviceObject
0x14000156a  mov     eax, [rdx+18h]
0x14000156d  mov     [rdi+38h], eax
0x140001570  mov     dword ptr [rdi+3Ch], 0
0x140001577  mov     r8d, [rdx+18h]; State
0x14000157b  mov     edx, [rdx+10h]; Type
0x14000157e  call    cs:__imp_PoSetPowerState
0x140001585  nop     dword ptr [rax+rax+00h]
0x14000158a  cmp     byte ptr [rbx+41h], 0
0x14000158e  jz      short loc_14000159B
0x140001590  mov     rax, [rbx+0B8h]
0x140001597  or      byte ptr [rax+3], 1
0x14000159b  mov     rcx, rbx; Irp
0x14000159e  call    cs:__imp_PoStartNextPowerIrp
0x1400015a5  nop     dword ptr [rax+rax+00h]
0x1400015aa  lea     rcx, [rdi+18h]; RemoveLock
0x1400015ae  mov     r8d, 20h ; ' '; RemlockSize
0x1400015b4  lea     rdx, PtPower; Tag
0x1400015bb  call    cs:__imp_IoReleaseRemoveLockEx
0x1400015c2  nop     dword ptr [rax+rax+00h]
0x1400015c7  xor     eax, eax
0x1400015c9  add     rsp, 38h
0x1400015cd  pop     r14
0x1400015cf  pop     rdi
0x1400015d0  pop     rbp
0x1400015d1  pop     rbx
0x1400015d2  retn
```
