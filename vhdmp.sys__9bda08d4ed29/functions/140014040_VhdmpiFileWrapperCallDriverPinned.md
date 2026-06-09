# VhdmpiFileWrapperCallDriverPinned

- ea: `0x140014040`
- end: `0x1400141d1`
- name: `VhdmpiFileWrapperCallDriverPinned`
- size: `401`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400c9d50`
- `0x1400e1f54`

## callees

- `0x140014040`
- `0x1400141e0`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14001416f`
- `ntoskrnl!IofCallDriver` at `0x14001416f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140014056`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140014056`
- `ntoskrnl!IofCompleteRequest` at `0x1400141b7`
- `ntoskrnl!IofCompleteRequest` at `0x1400141b7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001407d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001407d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001415d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014194`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001415d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014194`

## pseudocode

```c
NTSTATUS __fastcall VhdmpiFileWrapperCallDriverPinned(__int64 a1, struct _DEVICE_OBJECT *a2, IRP *a3)
{
  ULONG CurrentProcessorNumber; // eax
  USHORT v7; // bp
  __int64 v8; // rdi
  KIRQL v9; // al
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  union _IO_STACK_LOCATION::$3F40624FA6BA75D391A2F4D7FEA8ACCF *p_Parameters; // rdx
  struct _IO_STACK_LOCATION *v12; // rax
  char *v13; // r8
  char **v14; // rcx
  __int64 v15; // rdx
  PKSPIN_LOCK v16; // r8
  KIRQL v17; // r9

  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  v7 = CurrentProcessorNumber;
  v8 = 192LL * CurrentProcessorNumber;
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)((char *)VhdPerProcData + v8));
  if ( *(_DWORD *)(a1 + 672) )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)((char *)VhdPerProcData + v8), v9);
    --a3->CurrentLocation;
    --a3->Tail.Overlay.CurrentStackLocation;
    a3->IoStatus.Status = -1073741536;
    IofCompleteRequest(a3, 0);
    return 259;
  }
  else
  {
    --a3->CurrentLocation;
    CurrentStackLocation = a3->Tail.Overlay.CurrentStackLocation;
    a3->Tail.Overlay.CurrentStackLocation = CurrentStackLocation - 1;
    p_Parameters = &CurrentStackLocation[-1].Parameters;
    *(_OWORD *)&CurrentStackLocation[-2].MajorFunction = *(_OWORD *)&CurrentStackLocation[-1].MajorFunction;
    *(_OWORD *)&CurrentStackLocation[-2].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&CurrentStackLocation[-2].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota
                                                                               + 6);
    CurrentStackLocation[-2].FileObject = CurrentStackLocation[-1].FileObject;
    CurrentStackLocation[-2].Control = 0;
    v12 = a3->Tail.Overlay.CurrentStackLocation;
    v13 = (char *)VhdPerProcData + v8;
    v12[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)VhdmpiCompleteIrpForEnteredSafeFileReference;
    v12[-1].Context = &CurrentStackLocation[-1].Parameters;
    v12[-1].Control = -32;
    p_Parameters->Create.FileAttributes = v7;
    LODWORD(v12) = CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart;
    p_Parameters->CreatePipe.Parameters = (PNAMED_PIPE_CREATE_PARAMETERS)a1;
    p_Parameters->Read.ByteOffset.LowPart = ((unsigned int)v12
                                           ^ ((unsigned int)v12
                                            ^ (((_DWORD)CurrentStackLocation - 64 - (_DWORD)a3) << 16))
                                           & 0xFFFF0000)
                                          & 0x7FFFFFFF;
    v14 = (char **)*((_QWORD *)v13 + 2);
    if ( *v14 != v13 + 8 )
      __fastfail(3u);
    p_Parameters->WMI.ProviderId = (ULONG_PTR)(v13 + 8);
    p_Parameters->QueryDirectory.FileName = (PUNICODE_STRING)v14;
    *v14 = (char *)p_Parameters;
    *((_QWORD *)v13 + 2) = p_Parameters;
    VhdmpiCheckListEntryLinked((struct _LIST_ENTRY *)p_Parameters->Create.SecurityContext);
    VhdmpiCheckListEntryLinked(*(struct _LIST_ENTRY **)(v15 + 8));
    KeReleaseSpinLock(v16, v17);
    return IofCallDriver(a2, a3);
  }
}

```

## disassembly

```asm
0x140014040  push    rbx
0x140014042  push    rbp
0x140014043  push    rsi
0x140014044  push    rdi
0x140014045  push    r14
0x140014047  sub     rsp, 20h
0x14001404b  mov     rsi, rcx
0x14001404e  mov     rbx, r8
0x140014051  xor     ecx, ecx; ProcNumber
0x140014053  mov     r14, rdx
0x140014056  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14001405d  nop     dword ptr [rax+rax+00h]
0x140014062  mov     rcx, cs:VhdPerProcData
0x140014069  mov     ebp, eax
0x14001406b  lea     rdi, ds:0[rbp*2]
0x140014073  add     rdi, rbp
0x140014076  shl     rdi, 6
0x14001407a  add     rcx, rdi; SpinLock
0x14001407d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014084  nop     dword ptr [rax+rax+00h]
0x140014089  mov     r8d, [rsi+2A0h]
0x140014090  mov     r9b, al
0x140014093  test    r8d, r8d
0x140014096  jnz     loc_140014187
0x14001409c  dec     byte ptr [rbx+43h]
0x14001409f  mov     rcx, [rbx+0B8h]
0x1400140a6  lea     rax, [rcx-48h]
0x1400140aa  mov     [rbx+0B8h], rax
0x1400140b1  lea     rdx, [rcx-40h]
0x1400140b5  movups  xmm0, xmmword ptr [rax]
0x1400140b8  movups  xmmword ptr [rcx-90h], xmm0
0x1400140bf  movups  xmm1, xmmword ptr [rax+10h]
0x1400140c3  movups  xmmword ptr [rcx-80h], xmm1
0x1400140c7  movups  xmm0, xmmword ptr [rax+20h]
0x1400140cb  movups  xmmword ptr [rcx-70h], xmm0
0x1400140cf  movsd   xmm1, qword ptr [rax+30h]
0x1400140d4  movsd   qword ptr [rcx-60h], xmm1
0x1400140d9  mov     [rcx-8Dh], r8b
0x1400140e0  lea     rcx, ?VhdmpiCompleteIrpForEnteredSafeFileReference@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; VhdmpiCompleteIrpForEnteredSafeFileReference(_DEVICE_OBJECT *,_IRP *,void *)
0x1400140e7  mov     rax, [rbx+0B8h]
0x1400140ee  mov     r8, cs:VhdPerProcData
0x1400140f5  add     r8, rdi
0x1400140f8  mov     [rax-10h], rcx
0x1400140fc  mov     ecx, edx
0x1400140fe  sub     ecx, ebx
0x140014100  mov     [rax-8], rdx
0x140014104  mov     byte ptr [rax-45h], 0E0h
0x140014108  shl     ecx, 10h
0x14001410b  mov     [rdx+10h], bp
0x14001410f  mov     eax, [rdx+10h]
0x140014112  xor     ecx, eax
0x140014114  and     ecx, 0FFFF0000h
0x14001411a  mov     [rdx+18h], rsi
0x14001411e  xor     ecx, eax
0x140014120  lea     rax, [r8+8]
0x140014124  btr     ecx, 1Fh
0x140014128  mov     [rdx+10h], ecx
0x14001412b  mov     rcx, [rax+8]
0x14001412f  cmp     [rcx], rax
0x140014132  jnz     loc_1400141CA
0x140014138  mov     [rdx], rax
0x14001413b  mov     [rdx+8], rcx
0x14001413f  mov     [rcx], rdx
0x140014142  mov     [rax+8], rdx
0x140014146  mov     rcx, [rdx]; struct _LIST_ENTRY *
0x140014149  call    ?VhdmpiCheckListEntryLinked@@YAXPEAU_LIST_ENTRY@@@Z; VhdmpiCheckListEntryLinked(_LIST_ENTRY *)
0x14001414e  mov     rcx, [rdx+8]; struct _LIST_ENTRY *
0x140014152  call    ?VhdmpiCheckListEntryLinked@@YAXPEAU_LIST_ENTRY@@@Z; VhdmpiCheckListEntryLinked(_LIST_ENTRY *)
0x140014157  mov     rcx, r8; SpinLock
0x14001415a  mov     dl, r9b; NewIrql
0x14001415d  call    cs:__imp_KeReleaseSpinLock
0x140014164  nop     dword ptr [rax+rax+00h]
0x140014169  mov     rdx, rbx; Irp
0x14001416c  mov     rcx, r14; DeviceObject
0x14001416f  call    cs:__imp_IofCallDriver
0x140014176  nop     dword ptr [rax+rax+00h]
0x14001417b  add     rsp, 20h
0x14001417f  pop     r14
0x140014181  pop     rdi
0x140014182  pop     rsi
0x140014183  pop     rbp
0x140014184  pop     rbx
0x140014185  retn
0x140014187  mov     rcx, cs:VhdPerProcData
0x14001418e  mov     dl, r9b; NewIrql
0x140014191  add     rcx, rdi; SpinLock
0x140014194  call    cs:__imp_KeReleaseSpinLock
0x14001419b  nop     dword ptr [rax+rax+00h]
0x1400141a0  dec     byte ptr [rbx+43h]
0x1400141a3  xor     edx, edx; PriorityBoost
0x1400141a5  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x1400141ad  mov     rcx, rbx; Irp
0x1400141b0  mov     dword ptr [rbx+30h], 0C0000120h
0x1400141b7  call    cs:__imp_IofCompleteRequest
0x1400141be  nop     dword ptr [rax+rax+00h]
0x1400141c3  mov     eax, 103h
0x1400141c8  jmp     short loc_14001417B
0x1400141ca  mov     ecx, 3
0x1400141cf  int     29h; Win8: RtlFailFast(ecx)
```
