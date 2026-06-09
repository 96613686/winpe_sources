# RmwiTriageIO(_VHD_IRP_CONTEXT_HEADER *)

- ea: `0x140025e74`
- end: `0x140026081`
- name: `?RmwiTriageIO@@YAJPEAU_VHD_IRP_CONTEXT_HEADER@@@Z`
- size: `525`
- prototype: `__int64 __fastcall(struct _VHD_IRP_CONTEXT_HEADER *)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140009a30`
- `0x140014c30`
- `0x140015540`
- `0x140017660`

## callees

- `0x14002141c`
- `0x140025e74`
- `0x140026088`
- `0x1400e8f24`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140025edd`
- `ntoskrnl!IofCompleteRequest` at `0x140025edd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025f55`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025ffc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025f55`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025ffc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025fd3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002604f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025fd3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002604f`

## pseudocode

```c
int __fastcall RmwiTriageIO(struct _VHD_IRP_CONTEXT_HEADER *a1)
{
  __int64 v1; // rax
  struct _IRP *v2; // rsi
  __int64 v4; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rax
  KSPIN_LOCK *v9; // r14
  struct _IO_STACK_LOCATION *v10; // rax
  char v11; // bp
  KIRQL v12; // r8
  unsigned __int64 v13; // rdx
  _QWORD *v14; // rcx
  __int64 v15; // rbx
  char *v16; // rax
  _QWORD *v17; // rdx
  char v19; // si
  KIRQL v20; // r8
  _QWORD *v21; // rdx
  __int64 v22; // [rsp+40h] [rbp+8h] BYREF

  v1 = *((_QWORD *)a1 + 1);
  v2 = (struct _IRP *)*((_QWORD *)a1 + 2);
  v22 = 0;
  v4 = *(_QWORD *)(v1 + 1480);
  CurrentStackLocation = v2->Tail.Overlay.CurrentStackLocation;
  *((_QWORD *)a1 + 7) = CurrentStackLocation[-1].Parameters.Read.ByteOffset.QuadPart;
  *((_DWORD *)a1 + 16) = CurrentStackLocation[-1].Parameters.Read.Length;
  if ( (int)VhdmpiGetVhdFileSize(*(_QWORD *)v4, &v22) < 0 )
  {
    --v2->CurrentLocation;
    --v2->Tail.Overlay.CurrentStackLocation;
    v2->IoStatus.Status = -1073741823;
    IofCompleteRequest(v2, 0);
    return 259;
  }
  v6 = *((_QWORD *)a1 + 7);
  v7 = *(unsigned int *)(v4 + 496) - 1LL;
  if ( (v7 & v6) != 0 || (v8 = *((unsigned int *)a1 + 16), (v8 & v7) != 0) || v6 + v8 > (v22 & (unsigned __int64)~v7) )
  {
    v19 = 0;
    v20 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 8));
    if ( !*(_DWORD *)(v4 + 120) )
    {
      v19 = 1;
      *(_DWORD *)(v4 + 120) = 1;
    }
    ++*(_DWORD *)(v4 + 484);
    v21 = *(_QWORD **)(v4 + 40);
    if ( *v21 == v4 + 32 )
    {
      *((_QWORD *)a1 + 3) = v4 + 32;
      *((_QWORD *)a1 + 4) = v21;
      *v21 = (char *)a1 + 24;
      *(_QWORD *)(v4 + 40) = (char *)a1 + 24;
      KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 8), v20);
      if ( v19 )
        RmwiConsumeNonAlignedQueue((struct _RMW_STORE *)v4);
      return 259;
    }
    goto LABEL_18;
  }
  *((_QWORD *)a1 + 5) = CurrentStackLocation[-1].CompletionRoutine;
  v9 = (KSPIN_LOCK *)(v4 + 8);
  *((_QWORD *)a1 + 6) = CurrentStackLocation[-1].Context;
  v10 = v2->Tail.Overlay.CurrentStackLocation;
  v10[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)RmwiCompletionAlignIo;
  v10[-1].Context = a1;
  v10[-1].Control = -32;
  v11 = 1;
  v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 8));
  ++*(_DWORD *)(v4 + 480);
  if ( *(int *)(v4 + 120) > 1 )
  {
    v13 = *((_QWORD *)a1 + 7);
    if ( v13 < *(_QWORD *)(v4 + 112) && v13 + *((unsigned int *)a1 + 16) > *(_QWORD *)(v4 + 104) )
    {
      v14 = *(_QWORD **)(v4 + 56);
      v15 = v4 + 48;
      if ( *v14 == v15 )
      {
        v16 = (char *)a1 + 24;
        *((_QWORD *)a1 + 3) = v15;
        *((_QWORD *)a1 + 4) = v14;
        *v14 = (char *)a1 + 24;
        goto LABEL_13;
      }
LABEL_18:
      __fastfail(3u);
    }
  }
  v17 = *(_QWORD **)(v4 + 24);
  v15 = v4 + 16;
  if ( *v17 != v15 )
    goto LABEL_18;
  v16 = (char *)a1 + 24;
  v11 = 0;
  *((_QWORD *)a1 + 3) = v15;
  *((_QWORD *)a1 + 4) = v17;
  *v17 = (char *)a1 + 24;
LABEL_13:
  *(_QWORD *)(v15 + 8) = v16;
  KeReleaseSpinLock(v9, v12);
  if ( !v11 )
    return RmwiCallDownLevelDriver(a1, v2);
  return 259;
}

```

## disassembly

```asm
0x140025e74  mov     r11, rsp
0x140025e77  mov     [r11+10h], rbx
0x140025e7b  mov     [r11+18h], rbp
0x140025e7f  push    rsi
0x140025e80  push    rdi
0x140025e81  push    r14
0x140025e83  sub     rsp, 20h
0x140025e87  mov     rax, [rcx+8]
0x140025e8b  lea     rdx, [r11+8]
0x140025e8f  mov     rsi, [rcx+10h]
0x140025e93  mov     rdi, rcx
0x140025e96  mov     qword ptr [r11+8], 0
0x140025e9e  mov     rbx, [rax+5C8h]
0x140025ea5  mov     rbp, [rsi+0B8h]
0x140025eac  mov     rax, [rbp-30h]
0x140025eb0  mov     [rcx+38h], rax
0x140025eb4  mov     eax, [rbp-40h]
0x140025eb7  mov     [rcx+40h], eax
0x140025eba  mov     rcx, [rbx]
0x140025ebd  call    VhdmpiGetVhdFileSize
0x140025ec2  test    eax, eax
0x140025ec4  jns     short loc_140025EEE
0x140025ec6  dec     byte ptr [rsi+43h]
0x140025ec9  xor     edx, edx; PriorityBoost
0x140025ecb  add     qword ptr [rsi+0B8h], 0FFFFFFFFFFFFFFB8h
0x140025ed3  mov     rcx, rsi; Irp
0x140025ed6  mov     dword ptr [rsi+30h], 0C0000001h
0x140025edd  call    cs:__imp_IofCompleteRequest
0x140025ee4  nop     dword ptr [rax+rax+00h]
0x140025ee9  jmp     loc_140026068
0x140025eee  mov     ecx, [rbx+1F0h]
0x140025ef4  mov     rdx, [rdi+38h]
0x140025ef8  dec     rcx
0x140025efb  test    rdx, rcx
0x140025efe  jnz     loc_140025FF5
0x140025f04  mov     eax, [rdi+40h]
0x140025f07  test    rcx, rax
0x140025f0a  jnz     loc_140025FF5
0x140025f10  not     rcx
0x140025f13  add     rax, rdx
0x140025f16  and     rcx, [rsp+38h+arg_0]
0x140025f1b  cmp     rax, rcx
0x140025f1e  ja      loc_140025FF5
0x140025f24  mov     rax, [rbp-10h]
0x140025f28  lea     rcx, ?RmwiCompletionAlignIo@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; RmwiCompletionAlignIo(_DEVICE_OBJECT *,_IRP *,void *)
0x140025f2f  mov     [rdi+28h], rax
0x140025f33  lea     r14, [rbx+8]
0x140025f37  mov     rax, [rbp-8]
0x140025f3b  mov     [rdi+30h], rax
0x140025f3f  mov     rax, [rsi+0B8h]
0x140025f46  mov     [rax-10h], rcx
0x140025f4a  mov     rcx, r14; SpinLock
0x140025f4d  mov     [rax-8], rdi
0x140025f51  mov     byte ptr [rax-45h], 0E0h
0x140025f55  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140025f5c  nop     dword ptr [rax+rax+00h]
0x140025f61  mov     ebp, 1
0x140025f66  mov     r8b, al
0x140025f69  add     [rbx+1E0h], ebp
0x140025f6f  cmp     [rbx+78h], ebp
0x140025f72  jle     short loc_140025FAB
0x140025f74  mov     rdx, [rdi+38h]
0x140025f78  cmp     rdx, [rbx+70h]
0x140025f7c  jnb     short loc_140025FAB
0x140025f7e  mov     ecx, [rdi+40h]
0x140025f81  add     rcx, rdx
0x140025f84  cmp     rcx, [rbx+68h]
0x140025f88  jbe     short loc_140025FAB
0x140025f8a  mov     rcx, [rbx+38h]
0x140025f8e  add     rbx, 30h ; '0'
0x140025f92  cmp     [rcx], rbx
0x140025f95  jnz     loc_14002602F
0x140025f9b  lea     rax, [rdi+18h]
0x140025f9f  mov     [rax], rbx
0x140025fa2  mov     [rax+8], rcx
0x140025fa6  mov     [rcx], rax
0x140025fa9  jmp     short loc_140025FC9
0x140025fab  mov     rdx, [rbx+18h]
0x140025faf  add     rbx, 10h
0x140025fb3  cmp     [rdx], rbx
0x140025fb6  jnz     short loc_14002602F
0x140025fb8  lea     rax, [rdi+18h]
0x140025fbc  xor     bpl, bpl
0x140025fbf  mov     [rax], rbx
0x140025fc2  mov     [rax+8], rdx
0x140025fc6  mov     [rdx], rax
0x140025fc9  mov     dl, r8b; NewIrql
0x140025fcc  mov     [rbx+8], rax
0x140025fd0  mov     rcx, r14; SpinLock
0x140025fd3  call    cs:__imp_KeReleaseSpinLock
0x140025fda  nop     dword ptr [rax+rax+00h]
0x140025fdf  test    bpl, bpl
0x140025fe2  jnz     loc_140026068
0x140025fe8  mov     rdx, rsi; struct _IRP *
0x140025feb  mov     rcx, rdi; struct _VHD_IRP_CONTEXT_HEADER *
0x140025fee  call    ?RmwiCallDownLevelDriver@@YAJPEAU_VHD_IRP_CONTEXT_HEADER@@PEAU_IRP@@@Z; RmwiCallDownLevelDriver(_VHD_IRP_CONTEXT_HEADER *,_IRP *)
0x140025ff3  jmp     short loc_14002606D
0x140025ff5  lea     rcx, [rbx+8]; SpinLock
0x140025ff9  xor     sil, sil
0x140025ffc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140026003  nop     dword ptr [rax+rax+00h]
0x140026008  cmp     dword ptr [rbx+78h], 0
0x14002600c  mov     ebp, 1
0x140026011  mov     r8b, al
0x140026014  jnz     short loc_14002601C
0x140026016  mov     sil, bpl
0x140026019  mov     [rbx+78h], ebp
0x14002601c  add     [rbx+1E4h], ebp
0x140026022  lea     rcx, [rbx+20h]
0x140026026  mov     rdx, [rcx+8]
0x14002602a  cmp     [rdx], rcx
0x14002602d  jz      short loc_140026036
0x14002602f  mov     ecx, 3
0x140026034  int     29h; Win8: RtlFailFast(ecx)
0x140026036  lea     rax, [rdi+18h]
0x14002603a  mov     [rax], rcx
0x14002603d  mov     [rax+8], rdx
0x140026041  mov     [rdx], rax
0x140026044  mov     dl, r8b; NewIrql
0x140026047  mov     [rcx+8], rax
0x14002604b  lea     rcx, [rbx+8]; SpinLock
0x14002604f  call    cs:__imp_KeReleaseSpinLock
0x140026056  nop     dword ptr [rax+rax+00h]
0x14002605b  test    sil, sil
0x14002605e  jz      short loc_140026068
0x140026060  mov     rcx, rbx; struct _RMW_STORE *
0x140026063  call    ?RmwiConsumeNonAlignedQueue@@YAXPEAU_RMW_STORE@@@Z; RmwiConsumeNonAlignedQueue(_RMW_STORE *)
0x140026068  mov     eax, 103h
0x14002606d  mov     rbx, [rsp+38h+arg_8]
0x140026072  mov     rbp, [rsp+38h+arg_10]
0x140026077  add     rsp, 20h
0x14002607b  pop     r14
0x14002607d  pop     rdi
0x14002607e  pop     rsi
0x14002607f  retn
```
