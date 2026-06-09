# VmpOffline(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x140012710`
- end: `0x1400127e9`
- name: `?VmpOffline@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `217`
- prototype: `int(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001ae0`

## callees

- `0x140003c50`
- `0x140005090`
- `0x140012710`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400127b6`
- `ntoskrnl!KeReleaseMutex` at `0x1400127b6`
- `ntoskrnl!IofCompleteRequest` at `0x1400127d1`
- `ntoskrnl!IofCompleteRequest` at `0x1400127d1`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012775`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012775`

## pseudocode

```c
__int64 __fastcall VmpOffline(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  NTSTATUS v2; // edi

  v2 = 0;
  if ( !*((_BYTE *)a1 + 160) )
  {
    if ( (*(_DWORD *)(*(_QWORD *)a1 + 48LL) & 0x600100) != 0 || *((_DWORD *)a1 + 37) )
    {
      v2 = -1073741808;
    }
    else
    {
      v2 = VmpZeroRefCallback(a1, VmpChangeOfflineCallback, (void *)1);
      if ( v2 >= 0 )
      {
        KeWaitForSingleObject((char *)a1 + 56, Executive, 0, 0, 0);
        if ( *((_BYTE *)a1 + 426) && *((_QWORD *)a1 + 54) )
          (*(void (**)(void))(*((_QWORD *)VmRootExtension + 49) + 224LL))();
        KeReleaseMutex((PRKMUTEX)a1 + 1, 0);
      }
    }
  }
  a2->IoStatus.Status = v2;
  IofCompleteRequest(a2, 0);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140012710  push    rbx
0x140012712  push    rbp
0x140012713  push    rsi
0x140012714  push    rdi
0x140012715  sub     rsp, 38h
0x140012719  xor     edi, edi
0x14001271b  mov     rsi, rdx
0x14001271e  mov     rbx, rcx
0x140012721  cmp     [rcx+0A0h], dil
0x140012728  jnz     loc_1400127C9
0x14001272e  mov     rax, [rcx]
0x140012731  mov     r8d, [rax+30h]
0x140012735  test    r8d, 600100h
0x14001273c  jnz     loc_1400127C4
0x140012742  cmp     [rcx+94h], edi
0x140012748  jnz     short loc_1400127C4
0x14001274a  lea     r8d, [rdi+1]; void *
0x14001274e  lea     rdx, ?VmpChangeOfflineCallback@@YAJPEAVVM_VOLUME_EXTENSION@@PEAX@Z; int (*)(struct VM_VOLUME_EXTENSION *, void *)
0x140012755  call    ?VmpZeroRefCallback@@YAJPEAVVM_VOLUME_EXTENSION@@P6AJ0PEAX@Z1@Z; VmpZeroRefCallback(VM_VOLUME_EXTENSION *,long (*)(VM_VOLUME_EXTENSION *,void *),void *)
0x14001275a  mov     edi, eax
0x14001275c  test    eax, eax
0x14001275e  js      short loc_1400127C9
0x140012760  xor     r9d, r9d; Alertable
0x140012763  mov     [rsp+58h+Timeout], 0; Timeout
0x14001276c  xor     r8d, r8d; WaitMode
0x14001276f  lea     rcx, [rbx+38h]; Object
0x140012773  xor     edx, edx; WaitReason
0x140012775  call    cs:__imp_KeWaitForSingleObject
0x14001277c  nop     dword ptr [rax+rax+00h]
0x140012781  cmp     byte ptr [rbx+1AAh], 0
0x140012788  jz      short loc_1400127B0
0x14001278a  mov     rcx, [rbx+1B0h]
0x140012791  test    rcx, rcx
0x140012794  jz      short loc_1400127B0
0x140012796  mov     rax, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x14001279d  mov     rdx, [rax+188h]
0x1400127a4  mov     rax, [rdx+0E0h]
0x1400127ab  call    _guard_dispatch_icall
0x1400127b0  xor     edx, edx; Wait
0x1400127b2  lea     rcx, [rbx+38h]; Mutex
0x1400127b6  call    cs:__imp_KeReleaseMutex
0x1400127bd  nop     dword ptr [rax+rax+00h]
0x1400127c2  jmp     short loc_1400127C9
0x1400127c4  mov     edi, 0C0000010h
0x1400127c9  xor     edx, edx; PriorityBoost
0x1400127cb  mov     [rsi+30h], edi
0x1400127ce  mov     rcx, rsi; Irp
0x1400127d1  call    cs:__imp_IofCompleteRequest
0x1400127d8  nop     dword ptr [rax+rax+00h]
0x1400127dd  mov     eax, edi
0x1400127df  add     rsp, 38h
0x1400127e3  pop     rdi
0x1400127e4  pop     rsi
0x1400127e5  pop     rbp
0x1400127e6  pop     rbx
0x1400127e7  retn
```
