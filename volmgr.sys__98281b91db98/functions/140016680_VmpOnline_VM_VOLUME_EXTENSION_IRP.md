# VmpOnline(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x140016680`
- end: `0x140016752`
- name: `?VmpOnline@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `210`
- prototype: `int(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001ae0`

## callees

- `0x140003c50`
- `0x140016680`

## import_xrefs

- `ntoskrnl!IoForwardIrpSynchronously` at `0x140016708`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140016708`
- `ntoskrnl!KeReleaseMutex` at `0x14001671a`
- `ntoskrnl!KeReleaseMutex` at `0x14001671a`
- `ntoskrnl!IofCompleteRequest` at `0x140016733`
- `ntoskrnl!IofCompleteRequest` at `0x140016733`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400166e4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400166e4`

## pseudocode

```c
__int64 __fastcall VmpOnline(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  NTSTATUS v2; // ebx
  struct _DEVICE_OBJECT *v5; // rcx

  v2 = 0;
  if ( *((_BYTE *)a1 + 160) )
  {
    if ( _bittest64((const signed __int64 *)a1 + 39, 0x3Bu) )
    {
      v2 = -1073741808;
    }
    else
    {
      v2 = VmpZeroRefCallback(a1, VmpChangeOfflineCallback, 0);
      if ( v2 >= 0 )
      {
        KeWaitForSingleObject((char *)a1 + 56, Executive, 0, 0, 0);
        if ( !*((_BYTE *)a1 + 426) )
        {
          v5 = (struct _DEVICE_OBJECT *)*((_QWORD *)a1 + 43);
          if ( v5 )
            IoForwardIrpSynchronously(v5, a2);
        }
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
0x140016680  mov     [rsp+arg_8], rbx
0x140016685  mov     [rsp+arg_10], rsi
0x14001668a  push    rdi
0x14001668b  sub     rsp, 30h
0x14001668f  xor     ebx, ebx
0x140016691  mov     rdi, rdx
0x140016694  mov     rsi, rcx
0x140016697  cmp     [rcx+0A0h], bl
0x14001669d  jz      loc_14001672B
0x1400166a3  bt      qword ptr [rcx+138h], 3Bh ; ';'
0x1400166ac  jnb     short loc_1400166B5
0x1400166ae  mov     ebx, 0C0000010h
0x1400166b3  jmp     short loc_14001672B
0x1400166b5  xor     r8d, r8d; void *
0x1400166b8  lea     rdx, ?VmpChangeOfflineCallback@@YAJPEAVVM_VOLUME_EXTENSION@@PEAX@Z; int (*)(struct VM_VOLUME_EXTENSION *, void *)
0x1400166bf  call    ?VmpZeroRefCallback@@YAJPEAVVM_VOLUME_EXTENSION@@P6AJ0PEAX@Z1@Z; VmpZeroRefCallback(VM_VOLUME_EXTENSION *,long (*)(VM_VOLUME_EXTENSION *,void *),void *)
0x1400166c4  mov     ebx, eax
0x1400166c6  test    eax, eax
0x1400166c8  js      short loc_14001672B
0x1400166ca  xor     r9d, r9d; Alertable
0x1400166cd  mov     [rsp+38h+arg_0], rbp
0x1400166d2  xor     r8d, r8d; WaitMode
0x1400166d5  mov     [rsp+38h+Timeout], 0; Timeout
0x1400166de  xor     edx, edx; WaitReason
0x1400166e0  lea     rcx, [rsi+38h]; Object
0x1400166e4  call    cs:__imp_KeWaitForSingleObject
0x1400166eb  nop     dword ptr [rax+rax+00h]
0x1400166f0  cmp     byte ptr [rsi+1AAh], 0
0x1400166f7  jnz     short loc_140016714
0x1400166f9  mov     rcx, [rsi+158h]; DeviceObject
0x140016700  test    rcx, rcx
0x140016703  jz      short loc_140016714
0x140016705  mov     rdx, rdi; Irp
0x140016708  call    cs:__imp_IoForwardIrpSynchronously
0x14001670f  nop     dword ptr [rax+rax+00h]
0x140016714  xor     edx, edx; Wait
0x140016716  lea     rcx, [rsi+38h]; Mutex
0x14001671a  call    cs:__imp_KeReleaseMutex
0x140016721  nop     dword ptr [rax+rax+00h]
0x140016726  mov     rbp, [rsp+38h+arg_0]
0x14001672b  xor     edx, edx; PriorityBoost
0x14001672d  mov     [rdi+30h], ebx
0x140016730  mov     rcx, rdi; Irp
0x140016733  call    cs:__imp_IofCompleteRequest
0x14001673a  nop     dword ptr [rax+rax+00h]
0x14001673f  mov     rsi, [rsp+38h+arg_10]
0x140016744  mov     eax, ebx
0x140016746  mov     rbx, [rsp+38h+arg_8]
0x14001674b  add     rsp, 30h
0x14001674f  pop     rdi
0x140016750  retn
```
