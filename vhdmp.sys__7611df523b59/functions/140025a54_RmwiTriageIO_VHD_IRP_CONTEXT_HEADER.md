# RmwiTriageIO(_VHD_IRP_CONTEXT_HEADER *)

- ea: `0x140025a54`
- end: `0x140025c61`
- name: `?RmwiTriageIO@@YAJPEAU_VHD_IRP_CONTEXT_HEADER@@@Z`
- size: `525`
- prototype: `int __fastcall(struct _VHD_IRP_CONTEXT_HEADER *)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140009a30`
- `0x140014790`
- `0x1400150a0`
- `0x1400171c0`

## callees

- `0x140020ffc`
- `0x140025a54`
- `0x140025c68`
- `0x1400e8f94`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140025abd`
- `ntoskrnl!IofCompleteRequest` at `0x140025abd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025b35`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025bdc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025b35`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025bdc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025bb3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025c2f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025bb3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025c2f`

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
0x140025a54  mov     r11, rsp
0x140025a57  mov     [r11+10h], rbx
0x140025a5b  mov     [r11+18h], rbp
0x140025a5f  push    rsi
0x140025a60  push    rdi
0x140025a61  push    r14
0x140025a63  sub     rsp, 20h
0x140025a67  mov     rax, [rcx+8]
0x140025a6b  lea     rdx, [r11+8]
0x140025a6f  mov     rsi, [rcx+10h]
0x140025a73  mov     rdi, rcx
0x140025a76  mov     qword ptr [r11+8], 0
0x140025a7e  mov     rbx, [rax+5C8h]
0x140025a85  mov     rbp, [rsi+0B8h]
0x140025a8c  mov     rax, [rbp-30h]
0x140025a90  mov     [rcx+38h], rax
0x140025a94  mov     eax, [rbp-40h]
0x140025a97  mov     [rcx+40h], eax
0x140025a9a  mov     rcx, [rbx]
0x140025a9d  call    VhdmpiGetVhdFileSize
0x140025aa2  test    eax, eax
0x140025aa4  jns     short loc_140025ACE
0x140025aa6  dec     byte ptr [rsi+43h]
0x140025aa9  xor     edx, edx; PriorityBoost
0x140025aab  add     qword ptr [rsi+0B8h], 0FFFFFFFFFFFFFFB8h
0x140025ab3  mov     rcx, rsi; Irp
0x140025ab6  mov     dword ptr [rsi+30h], 0C0000001h
0x140025abd  call    cs:__imp_IofCompleteRequest
0x140025ac4  nop     dword ptr [rax+rax+00h]
0x140025ac9  jmp     loc_140025C48
0x140025ace  mov     ecx, [rbx+1F0h]
0x140025ad4  mov     rdx, [rdi+38h]
0x140025ad8  dec     rcx
0x140025adb  test    rdx, rcx
0x140025ade  jnz     loc_140025BD5
0x140025ae4  mov     eax, [rdi+40h]
0x140025ae7  test    rcx, rax
0x140025aea  jnz     loc_140025BD5
0x140025af0  not     rcx
0x140025af3  add     rax, rdx
0x140025af6  and     rcx, [rsp+38h+arg_0]
0x140025afb  cmp     rax, rcx
0x140025afe  ja      loc_140025BD5
0x140025b04  mov     rax, [rbp-10h]
0x140025b08  lea     rcx, ?RmwiCompletionAlignIo@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; RmwiCompletionAlignIo(_DEVICE_OBJECT *,_IRP *,void *)
0x140025b0f  mov     [rdi+28h], rax
0x140025b13  lea     r14, [rbx+8]
0x140025b17  mov     rax, [rbp-8]
0x140025b1b  mov     [rdi+30h], rax
0x140025b1f  mov     rax, [rsi+0B8h]
0x140025b26  mov     [rax-10h], rcx
0x140025b2a  mov     rcx, r14; SpinLock
0x140025b2d  mov     [rax-8], rdi
0x140025b31  mov     byte ptr [rax-45h], 0E0h
0x140025b35  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140025b3c  nop     dword ptr [rax+rax+00h]
0x140025b41  mov     ebp, 1
0x140025b46  mov     r8b, al
0x140025b49  add     [rbx+1E0h], ebp
0x140025b4f  cmp     [rbx+78h], ebp
0x140025b52  jle     short loc_140025B8B
0x140025b54  mov     rdx, [rdi+38h]
0x140025b58  cmp     rdx, [rbx+70h]
0x140025b5c  jnb     short loc_140025B8B
0x140025b5e  mov     ecx, [rdi+40h]
0x140025b61  add     rcx, rdx
0x140025b64  cmp     rcx, [rbx+68h]
0x140025b68  jbe     short loc_140025B8B
0x140025b6a  mov     rcx, [rbx+38h]
0x140025b6e  add     rbx, 30h ; '0'
0x140025b72  cmp     [rcx], rbx
0x140025b75  jnz     loc_140025C0F
0x140025b7b  lea     rax, [rdi+18h]
0x140025b7f  mov     [rax], rbx
0x140025b82  mov     [rax+8], rcx
0x140025b86  mov     [rcx], rax
0x140025b89  jmp     short loc_140025BA9
0x140025b8b  mov     rdx, [rbx+18h]
0x140025b8f  add     rbx, 10h
0x140025b93  cmp     [rdx], rbx
0x140025b96  jnz     short loc_140025C0F
0x140025b98  lea     rax, [rdi+18h]
0x140025b9c  xor     bpl, bpl
0x140025b9f  mov     [rax], rbx
0x140025ba2  mov     [rax+8], rdx
0x140025ba6  mov     [rdx], rax
0x140025ba9  mov     dl, r8b; NewIrql
0x140025bac  mov     [rbx+8], rax
0x140025bb0  mov     rcx, r14; SpinLock
0x140025bb3  call    cs:__imp_KeReleaseSpinLock
0x140025bba  nop     dword ptr [rax+rax+00h]
0x140025bbf  test    bpl, bpl
0x140025bc2  jnz     loc_140025C48
0x140025bc8  mov     rdx, rsi; struct _IRP *
0x140025bcb  mov     rcx, rdi; struct _VHD_IRP_CONTEXT_HEADER *
0x140025bce  call    ?RmwiCallDownLevelDriver@@YAJPEAU_VHD_IRP_CONTEXT_HEADER@@PEAU_IRP@@@Z; RmwiCallDownLevelDriver(_VHD_IRP_CONTEXT_HEADER *,_IRP *)
0x140025bd3  jmp     short loc_140025C4D
0x140025bd5  lea     rcx, [rbx+8]; SpinLock
0x140025bd9  xor     sil, sil
0x140025bdc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140025be3  nop     dword ptr [rax+rax+00h]
0x140025be8  cmp     dword ptr [rbx+78h], 0
0x140025bec  mov     ebp, 1
0x140025bf1  mov     r8b, al
0x140025bf4  jnz     short loc_140025BFC
0x140025bf6  mov     sil, bpl
0x140025bf9  mov     [rbx+78h], ebp
0x140025bfc  add     [rbx+1E4h], ebp
0x140025c02  lea     rcx, [rbx+20h]
0x140025c06  mov     rdx, [rcx+8]
0x140025c0a  cmp     [rdx], rcx
0x140025c0d  jz      short loc_140025C16
0x140025c0f  mov     ecx, 3
0x140025c14  int     29h; Win8: RtlFailFast(ecx)
0x140025c16  lea     rax, [rdi+18h]
0x140025c1a  mov     [rax], rcx
0x140025c1d  mov     [rax+8], rdx
0x140025c21  mov     [rdx], rax
0x140025c24  mov     dl, r8b; NewIrql
0x140025c27  mov     [rcx+8], rax
0x140025c2b  lea     rcx, [rbx+8]; SpinLock
0x140025c2f  call    cs:__imp_KeReleaseSpinLock
0x140025c36  nop     dword ptr [rax+rax+00h]
0x140025c3b  test    sil, sil
0x140025c3e  jz      short loc_140025C48
0x140025c40  mov     rcx, rbx; struct _RMW_STORE *
0x140025c43  call    ?RmwiConsumeNonAlignedQueue@@YAXPEAU_RMW_STORE@@@Z; RmwiConsumeNonAlignedQueue(_RMW_STORE *)
0x140025c48  mov     eax, 103h
0x140025c4d  mov     rbx, [rsp+38h+arg_8]
0x140025c52  mov     rbp, [rsp+38h+arg_10]
0x140025c57  add     rsp, 20h
0x140025c5b  pop     r14
0x140025c5d  pop     rdi
0x140025c5e  pop     rsi
0x140025c5f  retn
```
