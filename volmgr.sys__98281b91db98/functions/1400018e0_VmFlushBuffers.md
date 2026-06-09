# VmFlushBuffers

- ea: `0x1400018e0`
- end: `0x140001ad0`
- name: `VmFlushBuffers`
- size: `496`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400018e0`
- `0x140002910`
- `0x140005090`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400019cd`
- `ntoskrnl!IofCallDriver` at `0x1400019cd`
- `ntoskrnl!IofCompleteRequest` at `0x1400019ff`
- `ntoskrnl!IofCompleteRequest` at `0x140001a42`
- `ntoskrnl!IofCompleteRequest` at `0x1400019ff`
- `ntoskrnl!IofCompleteRequest` at `0x140001a42`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140001a25`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140001aba`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140001a25`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140001aba`

## pseudocode

```c
NTSTATUS __fastcall VmFlushBuffers(__int64 a1, IRP *a2)
{
  __int64 v2; // rbx
  NTSTATUS result; // eax
  int v5; // esi
  char v6; // cl
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v8; // rax
  char v9; // [rsp+20h] [rbp-18h]

  v2 = *(_QWORD *)(a1 + 64);
  if ( !*(_DWORD *)(v2 + 16) )
  {
    a2->IoStatus.Information = 0;
    a2->IoStatus.Status = -1073741808;
    IofCompleteRequest(a2, 0);
    return -1073741808;
  }
  if ( a2 )
    a2->IoStatus.Information = 0;
  result = VmpAcquireRundownShared((struct VM_VOLUME_EXTENSION *)v2, a2);
  v5 = result;
  if ( result != 259 )
  {
    if ( *(_BYTE *)(v2 + 426) )
    {
      if ( *(_QWORD *)(v2 + 432) )
        goto LABEL_7;
    }
    else if ( *(_QWORD *)(v2 + 344) )
    {
LABEL_7:
      v6 = 1;
LABEL_8:
      if ( *(_BYTE *)(v2 + 156) && v6 )
      {
        if ( *(_BYTE *)(v2 + 160) )
        {
          ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v2 + 112));
          v5 = -2147483632;
        }
        else if ( result >= 0 )
        {
          CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
          *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
          *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
          *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                                     + 6);
          CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
          CurrentStackLocation[-1].Control = 0;
          v8 = a2->Tail.Overlay.CurrentStackLocation;
          v8[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)VmpRefCountCompletionRoutine;
          v8[-1].Context = (PVOID)9;
          v8[-1].Control = -32;
          if ( !*(_BYTE *)(v2 + 426) )
            return IofCallDriver(*(PDEVICE_OBJECT *)(v2 + 368), a2);
          --a2->Tail.Overlay.CurrentStackLocation;
          --a2->CurrentLocation;
          v9 = 1;
          a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
          (*(void (__fastcall **)(_QWORD, IRP *, void (__fastcall *)(void *, int), IRP *, char))(*(_QWORD *)(*(_QWORD *)(v2 + 8) + 392LL)
                                                                                               + 216LL))(
            *(_QWORD *)(v2 + 432),
            a2,
            VmBroadcastIrpCompletionRoutine,
            a2,
            v9);
          return 259;
        }
      }
      else
      {
        ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v2 + 112));
        v5 = -1073741810;
      }
      a2->IoStatus.Information = 0;
      a2->IoStatus.Status = v5;
      IofCompleteRequest(a2, 0);
      return v5;
    }
    v6 = 0;
    goto LABEL_8;
  }
  return result;
}

```

## disassembly

```asm
0x1400018e0  mov     [rsp+arg_8], rbx
0x1400018e5  mov     [rsp+arg_10], rbp
0x1400018ea  push    rdi
0x1400018eb  sub     rsp, 30h
0x1400018ef  mov     rbx, [rcx+40h]
0x1400018f3  xor     ebp, ebp
0x1400018f5  mov     rdi, rdx
0x1400018f8  cmp     [rbx+10h], ebp
0x1400018fb  jz      loc_1400019EF
0x140001901  mov     [rsp+38h+arg_0], rsi
0x140001906  test    rdx, rdx
0x140001909  jz      short loc_14000190F
0x14000190b  mov     [rdx+38h], rbp
0x14000190f  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x140001912  call    ?VmpAcquireRundownShared@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z; VmpAcquireRundownShared(VM_VOLUME_EXTENSION *,_IRP *)
0x140001917  mov     esi, eax
0x140001919  cmp     eax, 103h
0x14000191e  jz      loc_1400019D9
0x140001924  cmp     [rbx+1AAh], bpl
0x14000192b  jnz     loc_140001A52
0x140001931  cmp     [rbx+158h], rbp
0x140001938  jz      loc_140001A5F
0x14000193e  mov     cl, 1
0x140001940  movzx   eax, byte ptr [rbx+9Ch]
0x140001947  test    al, al
0x140001949  jz      loc_140001A21
0x14000194f  test    cl, cl
0x140001951  jz      loc_140001A21
0x140001957  cmp     [rbx+0A0h], bpl
0x14000195e  jnz     loc_140001AB6
0x140001964  test    esi, esi
0x140001966  js      loc_140001A36
0x14000196c  mov     rax, [rdi+0B8h]
0x140001973  lea     rcx, VmpRefCountCompletionRoutine
0x14000197a  movups  xmm0, xmmword ptr [rax]
0x14000197d  movups  xmmword ptr [rax-48h], xmm0
0x140001981  movups  xmm1, xmmword ptr [rax+10h]
0x140001985  movups  xmmword ptr [rax-38h], xmm1
0x140001989  movups  xmm0, xmmword ptr [rax+20h]
0x14000198d  movups  xmmword ptr [rax-28h], xmm0
0x140001991  movsd   xmm1, qword ptr [rax+30h]
0x140001996  movsd   qword ptr [rax-18h], xmm1
0x14000199b  mov     [rax-45h], bpl
0x14000199f  mov     rax, [rdi+0B8h]
0x1400019a6  mov     [rax-10h], rcx
0x1400019aa  mov     qword ptr [rax-8], 9
0x1400019b2  mov     byte ptr [rax-45h], 0E0h
0x1400019b6  cmp     [rbx+1AAh], bpl
0x1400019bd  jnz     loc_140001A66
0x1400019c3  mov     rcx, [rbx+170h]; DeviceObject
0x1400019ca  mov     rdx, rdi; Irp
0x1400019cd  call    cs:__imp_IofCallDriver
0x1400019d4  nop     dword ptr [rax+rax+00h]
0x1400019d9  mov     rsi, [rsp+38h+arg_0]
0x1400019de  mov     rbx, [rsp+38h+arg_8]
0x1400019e3  mov     rbp, [rsp+38h+arg_10]
0x1400019e8  add     rsp, 30h
0x1400019ec  pop     rdi
0x1400019ed  retn
0x1400019ef  mov     [rdx+38h], rbp
0x1400019f3  mov     rcx, rdi; Irp
0x1400019f6  mov     dword ptr [rdx+30h], 0C0000010h
0x1400019fd  xor     edx, edx; PriorityBoost
0x1400019ff  call    cs:__imp_IofCompleteRequest
0x140001a06  nop     dword ptr [rax+rax+00h]
0x140001a0b  mov     rbx, [rsp+38h+arg_8]
0x140001a10  mov     eax, 0C0000010h
0x140001a15  mov     rbp, [rsp+38h+arg_10]
0x140001a1a  add     rsp, 30h
0x140001a1e  pop     rdi
0x140001a1f  retn
0x140001a21  mov     rcx, [rbx+70h]; RunRefCacheAware
0x140001a25  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140001a2c  nop     dword ptr [rax+rax+00h]
0x140001a31  mov     esi, 0C000000Eh
0x140001a36  xor     edx, edx; PriorityBoost
0x140001a38  mov     [rdi+38h], rbp
0x140001a3c  mov     rcx, rdi; Irp
0x140001a3f  mov     [rdi+30h], esi
0x140001a42  call    cs:__imp_IofCompleteRequest
0x140001a49  nop     dword ptr [rax+rax+00h]
0x140001a4e  mov     eax, esi
0x140001a50  jmp     short loc_1400019D9
0x140001a52  cmp     [rbx+1B0h], rbp
0x140001a59  jnz     loc_14000193E
0x140001a5f  xor     cl, cl
0x140001a61  jmp     loc_140001940
0x140001a66  add     qword ptr [rdi+0B8h], 0FFFFFFFFFFFFFFB8h
0x140001a6e  lea     r8, ?VmBroadcastIrpCompletionRoutine@@YAXPEAXJ@Z; VmBroadcastIrpCompletionRoutine(void *,long)
0x140001a75  dec     byte ptr [rdi+43h]
0x140001a78  mov     r9, rdi
0x140001a7b  mov     rcx, [rdi+0B8h]
0x140001a82  mov     [rsp+38h+var_18], 1
0x140001a87  or      byte ptr [rcx+3], 1
0x140001a8b  mov     rcx, [rbx+8]
0x140001a8f  mov     rdx, [rcx+188h]
0x140001a96  mov     rcx, [rbx+1B0h]
0x140001a9d  mov     rax, [rdx+0D8h]
0x140001aa4  mov     rdx, rdi
0x140001aa7  call    _guard_dispatch_icall
0x140001aac  mov     eax, 103h
0x140001ab1  jmp     loc_1400019D9
0x140001ab6  mov     rcx, [rbx+70h]; RunRefCacheAware
0x140001aba  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140001ac1  nop     dword ptr [rax+rax+00h]
0x140001ac6  mov     esi, 80000010h
0x140001acb  jmp     loc_140001A36
```
