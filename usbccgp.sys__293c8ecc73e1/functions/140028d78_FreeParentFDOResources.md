# FreeParentFDOResources

- ea: `0x140028d78`
- end: `0x140028f73`
- name: `FreeParentFDOResources`
- size: `507`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140028cc0`
- `0x14002a2e0`

## callees

- `0x1400088b4`
- `0x14000d568`
- `0x14000e210`
- `0x140028d78`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140028dc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028e8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028eeb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028f3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028f4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028f62`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028dc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028e8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028eeb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028f3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028f4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028f62`
- `ntoskrnl!IoFreeIrp` at `0x140028e2a`
- `ntoskrnl!IoFreeIrp` at `0x140028e2a`
- `ntoskrnl!IoFreeWorkItem` at `0x140028f22`
- `ntoskrnl!IoFreeWorkItem` at `0x140028f22`
- `ntoskrnl!IoDeleteDevice` at `0x140028ebf`
- `ntoskrnl!IoDeleteDevice` at `0x140028ebf`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x140028e6b`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x140028e6b`

## pseudocode

```c
void __fastcall FreeParentFDOResources(__int64 a1, __int64 a2)
{
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  IRP *v8; // rcx
  void *v9; // rcx
  __int64 v10; // rdx
  void *v11; // rcx
  struct _IO_WORKITEM *v12; // rcx

  LOBYTE(a2) = 1;
  *(_DWORD *)(a1 + 12) = 8;
  FreeInterfaceList(a1, a2);
  v3 = *(void **)(a1 + 128);
  if ( v3 )
    ExFreePoolWithTag(v3, 0x43627355u);
  v4 = *(void **)(a1 + 48);
  *(_QWORD *)(a1 + 128) = 0;
  if ( v4 )
    ExFreePoolWithTag(v4, 0x43627355u);
  v5 = *(void **)(a1 + 1120);
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_BYTE *)(a1 + 64) = 0;
  if ( v5 )
    ExFreePoolWithTag(v5, 0x43627355u);
  v6 = *(void **)(a1 + 1128);
  *(_QWORD *)(a1 + 1120) = 0;
  if ( v6 )
    ExFreePoolWithTag(v6, 0x43627355u);
  v7 = *(void **)(a1 + 1136);
  *(_QWORD *)(a1 + 1128) = 0;
  if ( v7 )
    CleanFunctionList(v7);
  v8 = *(IRP **)(a1 + 656);
  *(_QWORD *)(a1 + 1136) = 0;
  if ( v8 )
    IoFreeIrp(v8);
  v9 = *(void **)(a1 + 1144);
  *(_QWORD *)(a1 + 656) = 0;
  if ( v9 )
    ExFreePoolWithTag(v9, 0x43627355u);
  v10 = *(_QWORD *)(a1 + 1368);
  *(_QWORD *)(a1 + 1144) = 0;
  if ( g_RecorderLog != v10 )
  {
    imp_WppRecorderLogDelete(WPP_GLOBAL_Control);
    *(_QWORD *)(a1 + 1368) = 0;
  }
  v11 = *(void **)(a1 + 1352);
  if ( v11 )
  {
    ExFreePoolWithTag(v11, 0x43627355u);
    *(_QWORD *)(a1 + 1352) = 0;
  }
  v12 = *(struct _IO_WORKITEM **)(a1 + 648);
  if ( v12 )
  {
    IoFreeWorkItem(v12);
    *(_QWORD *)(a1 + 648) = 0;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = 4;
    WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), v10, 2, 37, (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids);
  }
  IoDeleteDevice(*(PDEVICE_OBJECT *)(a1 + 32));
}

```

## disassembly

```asm
0x140028d78  mov     [rsp+arg_0], rbx
0x140028d7d  mov     [rsp+arg_8], rsi
0x140028d82  push    rdi
0x140028d83  sub     rsp, 30h
0x140028d87  mov     dl, 1
0x140028d89  mov     dword ptr [rcx+0Ch], 8
0x140028d90  mov     rbx, rcx
0x140028d93  call    FreeInterfaceList
0x140028d98  mov     rcx, [rbx+80h]; P
0x140028d9f  xor     edi, edi
0x140028da1  mov     esi, 43627355h
0x140028da6  test    rcx, rcx
0x140028da9  jnz     loc_140028EE9
0x140028daf  mov     rcx, [rbx+30h]; P
0x140028db3  mov     [rbx+80h], rdi
0x140028dba  test    rcx, rcx
0x140028dbd  jz      short loc_140028DCD
0x140028dbf  mov     edx, esi; Tag
0x140028dc1  call    cs:__imp_ExFreePoolWithTag
0x140028dc8  nop     dword ptr [rax+rax+00h]
0x140028dcd  mov     rcx, [rbx+460h]; P
0x140028dd4  mov     [rbx+30h], rdi
0x140028dd8  mov     [rbx+38h], rdi
0x140028ddc  mov     [rbx+40h], dil
0x140028de0  test    rcx, rcx
0x140028de3  jnz     loc_140028F3A
0x140028de9  mov     rcx, [rbx+468h]; P
0x140028df0  mov     [rbx+460h], rdi
0x140028df7  test    rcx, rcx
0x140028dfa  jnz     loc_140028F4D
0x140028e00  mov     rcx, [rbx+470h]; P
0x140028e07  mov     [rbx+468h], rdi
0x140028e0e  test    rcx, rcx
0x140028e11  jnz     loc_140028EDC
0x140028e17  mov     rcx, [rbx+290h]; Irp
0x140028e1e  mov     [rbx+470h], rdi
0x140028e25  test    rcx, rcx
0x140028e28  jz      short loc_140028E36
0x140028e2a  call    cs:__imp_IoFreeIrp
0x140028e31  nop     dword ptr [rax+rax+00h]
0x140028e36  mov     rcx, [rbx+478h]; P
0x140028e3d  mov     [rbx+290h], rdi
0x140028e44  test    rcx, rcx
0x140028e47  jnz     loc_140028F60
0x140028e4d  mov     rdx, [rbx+558h]
0x140028e54  mov     [rbx+478h], rdi
0x140028e5b  cmp     cs:g_RecorderLog, rdx
0x140028e62  jz      short loc_140028E7E
0x140028e64  mov     rcx, cs:WPP_GLOBAL_Control
0x140028e6b  call    cs:__imp_imp_WppRecorderLogDelete
0x140028e72  nop     dword ptr [rax+rax+00h]
0x140028e77  mov     [rbx+558h], rdi
0x140028e7e  mov     rcx, [rbx+548h]; P
0x140028e85  test    rcx, rcx
0x140028e88  jz      short loc_140028E9F
0x140028e8a  mov     edx, esi; Tag
0x140028e8c  call    cs:__imp_ExFreePoolWithTag
0x140028e93  nop     dword ptr [rax+rax+00h]
0x140028e98  mov     [rbx+548h], rdi
0x140028e9f  mov     rcx, [rbx+288h]; IoWorkItem
0x140028ea6  test    rcx, rcx
0x140028ea9  jnz     short loc_140028F22
0x140028eab  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140028eb2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140028eb9  jnz     short loc_140028EFC
0x140028ebb  mov     rcx, [rbx+20h]; DeviceObject
0x140028ebf  call    cs:__imp_IoDeleteDevice
0x140028ec6  nop     dword ptr [rax+rax+00h]
0x140028ecb  mov     rbx, [rsp+38h+arg_0]
0x140028ed0  mov     rsi, [rsp+38h+arg_8]
0x140028ed5  add     rsp, 30h
0x140028ed9  pop     rdi
0x140028eda  retn
0x140028edc  mov     edx, [rbx+74h]
0x140028edf  call    CleanFunctionList
0x140028ee4  jmp     loc_140028E17
0x140028ee9  mov     edx, esi; Tag
0x140028eeb  call    cs:__imp_ExFreePoolWithTag
0x140028ef2  nop     dword ptr [rax+rax+00h]
0x140028ef7  jmp     loc_140028DAF
0x140028efc  mov     rcx, [rbx+558h]
0x140028f03  lea     rax, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x140028f0a  mov     r9d, 25h ; '%'
0x140028f10  mov     [rsp+38h+var_18], rax
0x140028f15  mov     dl, 4
0x140028f17  lea     r8d, [r9-23h]
0x140028f1b  call    WPP_RECORDER_SF_
0x140028f20  jmp     short loc_140028EBB
0x140028f22  call    cs:__imp_IoFreeWorkItem
0x140028f29  nop     dword ptr [rax+rax+00h]
0x140028f2e  mov     [rbx+288h], rdi
0x140028f35  jmp     loc_140028EAB
0x140028f3a  mov     edx, esi; Tag
0x140028f3c  call    cs:__imp_ExFreePoolWithTag
0x140028f43  nop     dword ptr [rax+rax+00h]
0x140028f48  jmp     loc_140028DE9
0x140028f4d  mov     edx, esi; Tag
0x140028f4f  call    cs:__imp_ExFreePoolWithTag
0x140028f56  nop     dword ptr [rax+rax+00h]
0x140028f5b  jmp     loc_140028E00
0x140028f60  mov     edx, esi; Tag
0x140028f62  call    cs:__imp_ExFreePoolWithTag
0x140028f69  nop     dword ptr [rax+rax+00h]
0x140028f6e  jmp     loc_140028E4D
```
