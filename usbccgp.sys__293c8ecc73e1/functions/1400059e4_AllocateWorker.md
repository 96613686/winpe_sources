# AllocateWorker

- ea: `0x1400059e4`
- end: `0x140005ba8`
- name: `AllocateWorker`
- size: `452`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x14000476c`
- `0x140004b08`
- `0x1400055c0`
- `0x140005fc4`
- `0x1400084c0`
- `0x140008980`
- `0x140013eb0`
- `0x1400145e0`
- `0x140014890`

## callees

- `0x140005854`
- `0x1400059e4`
- `0x1400088b4`
- `0x140008eac`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140005a83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005b33`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005a83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005b33`
- `ntoskrnl!IoFreeWorkItem` at `0x140005b42`
- `ntoskrnl!IoFreeWorkItem` at `0x140005b42`
- `ntoskrnl!IoQueueWorkItem` at `0x140005b88`
- `ntoskrnl!IoQueueWorkItem` at `0x140005b88`
- `ntoskrnl!ExAllocatePool2` at `0x140005a0e`
- `ntoskrnl!ExAllocatePool2` at `0x140005a0e`
- `ntoskrnl!IoAllocateWorkItem` at `0x140005a65`
- `ntoskrnl!IoAllocateWorkItem` at `0x140005a65`

## pseudocode

```c
__int64 __fastcall AllocateWorker(__int64 a1, void *a2, __int64 a3)
{
  _QWORD *Pool2; // rbx
  PIO_WORKITEM WorkItem; // rax
  struct _IO_WORKITEM *v9; // r15
  int v10; // esi
  unsigned __int16 v11; // r9

  Pool2 = (_QWORD *)ExAllocatePool2(64, 40, 1130525525);
  if ( Pool2 )
  {
    WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)(a1 + 32));
    v9 = WorkItem;
    if ( WorkItem )
    {
      Pool2[2] = a2;
      Pool2[3] = WorkItem;
      Pool2[4] = a3;
      Pool2[1] = a1;
      *(_DWORD *)Pool2 = 1802661719;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        WPP_RECORDER_SF_qq(
          *(_QWORD *)(a1 + 1368),
          5u,
          3u,
          0x38u,
          (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids,
          a2,
          a3);
      v10 = UsbcAcquireRemoveLock(a1, 1802661719, a2);
      if ( v10 >= 0 )
      {
        IoQueueWorkItem(v9, (PIO_WORKITEM_ROUTINE)UsbcWorkerFunction, CriticalWorkQueue, Pool2);
        return (unsigned int)v10;
      }
      ExFreePoolWithTag(Pool2, 0x43627355u);
      IoFreeWorkItem(v9);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v11 = 57;
        goto LABEL_14;
      }
    }
    else
    {
      v10 = -1073741670;
      ExFreePoolWithTag(Pool2, 0x43627355u);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v11 = 55;
LABEL_14:
        WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), 2u, 8u, v11, (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
      }
    }
    return (unsigned int)v10;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), 2u, 8u, 0x36u, (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
  return 3221225626LL;
}

```

## disassembly

```asm
0x1400059e4  push    rbx
0x1400059e6  push    rbp
0x1400059e7  push    rsi
0x1400059e8  push    rdi
0x1400059e9  push    r12
0x1400059eb  push    r13
0x1400059ed  push    r14
0x1400059ef  push    r15
0x1400059f1  sub     rsp, 48h
0x1400059f5  mov     rsi, rdx
0x1400059f8  mov     r12, r8
0x1400059fb  mov     edx, 28h ; '('
0x140005a00  mov     rbp, rcx
0x140005a03  mov     edi, 43627355h
0x140005a08  mov     r8d, edi
0x140005a0b  lea     ecx, [rdx+18h]
0x140005a0e  call    cs:__imp_ExAllocatePool2
0x140005a15  nop     dword ptr [rax+rax+00h]
0x140005a1a  xor     r13d, r13d
0x140005a1d  mov     rbx, rax
0x140005a20  test    rax, rax
0x140005a23  jnz     short loc_140005A61
0x140005a25  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140005a2c  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140005a33  jz      short loc_140005A57
0x140005a35  mov     rcx, [rbp+558h]
0x140005a3c  lea     r14, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x140005a43  lea     r9d, [rax+36h]
0x140005a47  mov     [rsp+88h+var_68], r14
0x140005a4c  lea     r8d, [rax+8]
0x140005a50  mov     dl, 2
0x140005a52  call    WPP_RECORDER_SF_
0x140005a57  mov     eax, 0C000009Ah
0x140005a5c  jmp     loc_140005B96
0x140005a61  mov     rcx, [rbp+20h]; DeviceObject
0x140005a65  call    cs:__imp_IoAllocateWorkItem
0x140005a6c  nop     dword ptr [rax+rax+00h]
0x140005a71  mov     r15, rax
0x140005a74  test    rax, rax
0x140005a77  jnz     short loc_140005AB3
0x140005a79  mov     edx, edi; Tag
0x140005a7b  mov     rcx, rbx; P
0x140005a7e  mov     esi, 0C000009Ah
0x140005a83  call    cs:__imp_ExFreePoolWithTag
0x140005a8a  nop     dword ptr [rax+rax+00h]
0x140005a8f  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140005a96  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140005a9d  jz      loc_140005B94
0x140005aa3  lea     r9d, [r15+37h]
0x140005aa7  lea     r14, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x140005aae  jmp     loc_140005B5D
0x140005ab3  mov     [rbx+10h], rsi
0x140005ab7  mov     [rbx+18h], r15
0x140005abb  mov     [rbx+20h], r12
0x140005abf  mov     [rbx+8], rbp
0x140005ac3  mov     dword ptr [rbx], 6B726F57h
0x140005ac9  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140005ad0  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140005ad7  lea     r14, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x140005ade  jz      short loc_140005B15
0x140005ae0  mov     rax, cs:WPP_GLOBAL_Control
0x140005ae7  cmp     [rax+48h], r13w
0x140005aec  jz      short loc_140005B15
0x140005aee  mov     rcx, [rbp+558h]
0x140005af5  mov     r9d, 38h ; '8'
0x140005afb  mov     [rsp+88h+var_58], r12
0x140005b00  mov     dl, 5
0x140005b02  mov     [rsp+88h+var_60], rsi
0x140005b07  mov     [rsp+88h+var_68], r14
0x140005b0c  lea     r8d, [r9-35h]
0x140005b10  call    WPP_RECORDER_SF_qq
0x140005b15  mov     r8, rsi
0x140005b18  mov     edx, 6B726F57h
0x140005b1d  mov     rcx, rbp
0x140005b20  call    UsbcAcquireRemoveLock
0x140005b25  mov     esi, eax
0x140005b27  test    eax, eax
0x140005b29  jns     short loc_140005B78
0x140005b2b  mov     edx, 43627355h; Tag
0x140005b30  mov     rcx, rbx; P
0x140005b33  call    cs:__imp_ExFreePoolWithTag
0x140005b3a  nop     dword ptr [rax+rax+00h]
0x140005b3f  mov     rcx, r15; IoWorkItem
0x140005b42  call    cs:__imp_IoFreeWorkItem
0x140005b49  nop     dword ptr [rax+rax+00h]
0x140005b4e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140005b55  jz      short loc_140005B94
0x140005b57  mov     r9d, 39h ; '9'
0x140005b5d  mov     rcx, [rbp+558h]
0x140005b64  mov     r8d, 8
0x140005b6a  mov     dl, 2
0x140005b6c  mov     [rsp+88h+var_68], r14
0x140005b71  call    WPP_RECORDER_SF_
0x140005b76  jmp     short loc_140005B94
0x140005b78  mov     r9, rbx; Context
0x140005b7b  lea     rdx, UsbcWorkerFunction; WorkerRoutine
0x140005b82  xor     r8d, r8d; QueueType
0x140005b85  mov     rcx, r15; IoWorkItem
0x140005b88  call    cs:__imp_IoQueueWorkItem
0x140005b8f  nop     dword ptr [rax+rax+00h]
0x140005b94  mov     eax, esi
0x140005b96  add     rsp, 48h
0x140005b9a  pop     r15
0x140005b9c  pop     r14
0x140005b9e  pop     r13
0x140005ba0  pop     r12
0x140005ba2  pop     rdi
0x140005ba3  pop     rsi
0x140005ba4  pop     rbp
0x140005ba5  pop     rbx
0x140005ba6  retn
```
