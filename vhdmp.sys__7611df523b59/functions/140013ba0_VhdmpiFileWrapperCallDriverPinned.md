# VhdmpiFileWrapperCallDriverPinned

- ea: `0x140013ba0`
- end: `0x140013d31`
- name: `VhdmpiFileWrapperCallDriverPinned`
- size: `401`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400c9d60`
- `0x1400e1fc4`

## callees

- `0x140013ba0`
- `0x140013d40`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140013ccf`
- `ntoskrnl!IofCallDriver` at `0x140013ccf`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140013bb6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140013bb6`
- `ntoskrnl!IofCompleteRequest` at `0x140013d17`
- `ntoskrnl!IofCompleteRequest` at `0x140013d17`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013bdd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013bdd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013cbd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013cf4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013cbd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013cf4`

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
0x140013ba0  push    rbx
0x140013ba2  push    rbp
0x140013ba3  push    rsi
0x140013ba4  push    rdi
0x140013ba5  push    r14
0x140013ba7  sub     rsp, 20h
0x140013bab  mov     rsi, rcx
0x140013bae  mov     rbx, r8
0x140013bb1  xor     ecx, ecx; ProcNumber
0x140013bb3  mov     r14, rdx
0x140013bb6  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140013bbd  nop     dword ptr [rax+rax+00h]
0x140013bc2  mov     rcx, cs:VhdPerProcData
0x140013bc9  mov     ebp, eax
0x140013bcb  lea     rdi, ds:0[rbp*2]
0x140013bd3  add     rdi, rbp
0x140013bd6  shl     rdi, 6
0x140013bda  add     rcx, rdi; SpinLock
0x140013bdd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013be4  nop     dword ptr [rax+rax+00h]
0x140013be9  mov     r8d, [rsi+2A0h]
0x140013bf0  mov     r9b, al
0x140013bf3  test    r8d, r8d
0x140013bf6  jnz     loc_140013CE7
0x140013bfc  dec     byte ptr [rbx+43h]
0x140013bff  mov     rcx, [rbx+0B8h]
0x140013c06  lea     rax, [rcx-48h]
0x140013c0a  mov     [rbx+0B8h], rax
0x140013c11  lea     rdx, [rcx-40h]
0x140013c15  movups  xmm0, xmmword ptr [rax]
0x140013c18  movups  xmmword ptr [rcx-90h], xmm0
0x140013c1f  movups  xmm1, xmmword ptr [rax+10h]
0x140013c23  movups  xmmword ptr [rcx-80h], xmm1
0x140013c27  movups  xmm0, xmmword ptr [rax+20h]
0x140013c2b  movups  xmmword ptr [rcx-70h], xmm0
0x140013c2f  movsd   xmm1, qword ptr [rax+30h]
0x140013c34  movsd   qword ptr [rcx-60h], xmm1
0x140013c39  mov     [rcx-8Dh], r8b
0x140013c40  lea     rcx, ?VhdmpiCompleteIrpForEnteredSafeFileReference@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; VhdmpiCompleteIrpForEnteredSafeFileReference(_DEVICE_OBJECT *,_IRP *,void *)
0x140013c47  mov     rax, [rbx+0B8h]
0x140013c4e  mov     r8, cs:VhdPerProcData
0x140013c55  add     r8, rdi
0x140013c58  mov     [rax-10h], rcx
0x140013c5c  mov     ecx, edx
0x140013c5e  sub     ecx, ebx
0x140013c60  mov     [rax-8], rdx
0x140013c64  mov     byte ptr [rax-45h], 0E0h
0x140013c68  shl     ecx, 10h
0x140013c6b  mov     [rdx+10h], bp
0x140013c6f  mov     eax, [rdx+10h]
0x140013c72  xor     ecx, eax
0x140013c74  and     ecx, 0FFFF0000h
0x140013c7a  mov     [rdx+18h], rsi
0x140013c7e  xor     ecx, eax
0x140013c80  lea     rax, [r8+8]
0x140013c84  btr     ecx, 1Fh
0x140013c88  mov     [rdx+10h], ecx
0x140013c8b  mov     rcx, [rax+8]
0x140013c8f  cmp     [rcx], rax
0x140013c92  jnz     loc_140013D2A
0x140013c98  mov     [rdx], rax
0x140013c9b  mov     [rdx+8], rcx
0x140013c9f  mov     [rcx], rdx
0x140013ca2  mov     [rax+8], rdx
0x140013ca6  mov     rcx, [rdx]; struct _LIST_ENTRY *
0x140013ca9  call    ?VhdmpiCheckListEntryLinked@@YAXPEAU_LIST_ENTRY@@@Z; VhdmpiCheckListEntryLinked(_LIST_ENTRY *)
0x140013cae  mov     rcx, [rdx+8]; struct _LIST_ENTRY *
0x140013cb2  call    ?VhdmpiCheckListEntryLinked@@YAXPEAU_LIST_ENTRY@@@Z; VhdmpiCheckListEntryLinked(_LIST_ENTRY *)
0x140013cb7  mov     rcx, r8; SpinLock
0x140013cba  mov     dl, r9b; NewIrql
0x140013cbd  call    cs:__imp_KeReleaseSpinLock
0x140013cc4  nop     dword ptr [rax+rax+00h]
0x140013cc9  mov     rdx, rbx; Irp
0x140013ccc  mov     rcx, r14; DeviceObject
0x140013ccf  call    cs:__imp_IofCallDriver
0x140013cd6  nop     dword ptr [rax+rax+00h]
0x140013cdb  add     rsp, 20h
0x140013cdf  pop     r14
0x140013ce1  pop     rdi
0x140013ce2  pop     rsi
0x140013ce3  pop     rbp
0x140013ce4  pop     rbx
0x140013ce5  retn
0x140013ce7  mov     rcx, cs:VhdPerProcData
0x140013cee  mov     dl, r9b; NewIrql
0x140013cf1  add     rcx, rdi; SpinLock
0x140013cf4  call    cs:__imp_KeReleaseSpinLock
0x140013cfb  nop     dword ptr [rax+rax+00h]
0x140013d00  dec     byte ptr [rbx+43h]
0x140013d03  xor     edx, edx; PriorityBoost
0x140013d05  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x140013d0d  mov     rcx, rbx; Irp
0x140013d10  mov     dword ptr [rbx+30h], 0C0000120h
0x140013d17  call    cs:__imp_IofCompleteRequest
0x140013d1e  nop     dword ptr [rax+rax+00h]
0x140013d23  mov     eax, 103h
0x140013d28  jmp     short loc_140013CDB
0x140013d2a  mov     ecx, 3
0x140013d2f  int     29h; Win8: RtlFailFast(ecx)
```
