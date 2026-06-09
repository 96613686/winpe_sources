# RmwiConsumeStateActive(_RMW_STORE *)

- ea: `0x140020b00`
- end: `0x140020c8c`
- name: `?RmwiConsumeStateActive@@YAEPEAU_RMW_STORE@@@Z`
- size: `396`
- prototype: `unsigned __int8 __fastcall(struct _RMW_STORE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400e8f24`

## callees

- `0x140020b00`
- `0x14002141c`
- `0x140023980`
- `0x140036284`
- `0x1400b98dc`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140020c52`
- `ntoskrnl!IofCompleteRequest` at `0x140020c52`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140020bd8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140020bd8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140020c36`
- `ntoskrnl!KeReleaseSpinLock` at `0x140020c36`

## pseudocode

```c
bool __fastcall RmwiConsumeStateActive(struct _RMW_STORE *a1)
{
  IRP *v2; // rsi
  __int64 v3; // rdi
  unsigned __int64 v4; // rcx
  unsigned int v5; // edx
  unsigned __int8 v6; // r8
  ULONG_PTR v7; // rax
  KIRQL v8; // dl
  bool v9; // bp
  __int64 *v10; // rdi
  _QWORD *v11; // r14
  _QWORD *v12; // rax
  _QWORD *v13; // rbx

  v2 = (IRP *)*((_QWORD *)a1 + 17);
  v3 = *((_QWORD *)a1 + 19);
  if ( *((int *)a1 + 119) >= 0 && v2->Tail.Overlay.CurrentStackLocation[-1].MajorFunction == 4 )
  {
    v4 = *(_QWORD *)(v3 + 56) + *(unsigned int *)(v3 + 64);
    if ( *((_QWORD *)a1 + 64) < v4 )
    {
      *((_QWORD *)a1 + 64) = v4;
      if ( (unsigned int)dword_1400876D0 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2) )
          TraceEvents(
            "RmwiConsumeStateActive",
            0x4FDu,
            v6,
            v5,
            "RmwiConsumeStateActive() RMW EndOfFileProxy = %llu",
            *((_QWORD *)a1 + 64));
      }
    }
    if ( *((_QWORD *)a1 + 14) > *((_QWORD *)a1 + 64) )
      RmwiTruncateBackingStoreFile(a1);
  }
  v2->IoStatus.Status = *((_DWORD *)a1 + 119);
  if ( *((int *)a1 + 119) < 0 )
    v7 = 0;
  else
    v7 = *(unsigned int *)(v3 + 64);
  v2->IoStatus.Information = v7;
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 1);
  v9 = *((_QWORD *)a1 + 4) != (_QWORD)a1 + 32;
  *((_DWORD *)a1 + 30) = v9;
  v10 = (__int64 *)*((_QWORD *)a1 + 6);
  if ( v10 == (__int64 *)((char *)a1 + 48) )
  {
    v10 = 0;
    v11 = 0;
  }
  else
  {
    v12 = (_QWORD *)*((_QWORD *)a1 + 3);
    v10[1] = (__int64)v12;
    *v12 = v10;
    v11 = (_QWORD *)*((_QWORD *)a1 + 7);
    *v11 = (char *)a1 + 16;
    *((_QWORD *)a1 + 3) = v11;
  }
  *((_QWORD *)a1 + 7) = (char *)a1 + 48;
  *((_QWORD *)a1 + 6) = (char *)a1 + 48;
  ++*((_DWORD *)a1 + 122);
  KeReleaseSpinLock((PKSPIN_LOCK)a1 + 1, v8);
  --v2->CurrentLocation;
  --v2->Tail.Overlay.CurrentStackLocation;
  IofCompleteRequest(v2, 0);
  if ( v10 )
  {
    do
    {
      v13 = v10;
      v10 = (__int64 *)*v10;
      RmwiCallDownLevelDriver((struct _VHD_IRP_CONTEXT_HEADER *)(v13 - 3), (struct _IRP *)*(v13 - 1));
    }
    while ( v13 != v11 );
  }
  return v9;
}

```

## disassembly

```asm
0x140020b00  push    rbx
0x140020b02  push    rbp
0x140020b03  push    rsi
0x140020b04  push    rdi
0x140020b05  push    r14
0x140020b07  push    r15
0x140020b09  sub     rsp, 38h
0x140020b0d  cmp     dword ptr [rcx+1DCh], 0
0x140020b14  mov     rbx, rcx
0x140020b17  mov     rsi, [rcx+88h]
0x140020b1e  mov     rdi, [rcx+98h]
0x140020b25  jl      loc_140020BB7
0x140020b2b  mov     rax, [rsi+0B8h]
0x140020b32  cmp     byte ptr [rax-48h], 4
0x140020b36  jnz     short loc_140020BB7
0x140020b38  mov     ecx, [rdi+40h]
0x140020b3b  add     rcx, [rdi+38h]
0x140020b3f  cmp     [rbx+200h], rcx
0x140020b46  jnb     short loc_140020BA2
0x140020b48  mov     [rbx+200h], rcx
0x140020b4f  mov     r8d, 5
0x140020b55  mov     eax, cs:dword_1400876D0
0x140020b5b  cmp     eax, r8d
0x140020b5e  jbe     short loc_140020BA2
0x140020b60  lea     edx, [r8-3]
0x140020b64  lea     rcx, dword_1400876D0
0x140020b6b  call    _tlgKeywordOn
0x140020b70  test    al, al
0x140020b72  jz      short loc_140020BA2
0x140020b74  mov     rax, [rbx+200h]
0x140020b7b  mov     ecx, 4FDh
0x140020b80  mov     qword ptr [rsp+68h+var_40], rax; char
0x140020b85  mov     r9d, edx; int
0x140020b88  lea     rax, aRmwiconsumesta_0; "RmwiConsumeStateActive() RMW EndOfFileP"...
0x140020b8f  mov     edx, ecx; int
0x140020b91  lea     rcx, aRmwiconsumesta; "RmwiConsumeStateActive"
0x140020b98  mov     [rsp+68h+var_48], rax; char *
0x140020b9d  call    TraceEvents
0x140020ba2  mov     rax, [rbx+200h]
0x140020ba9  cmp     [rbx+70h], rax
0x140020bad  jbe     short loc_140020BB7
0x140020baf  mov     rcx, rbx; struct _RMW_STORE *
0x140020bb2  call    ?RmwiTruncateBackingStoreFile@@YAJPEAU_RMW_STORE@@@Z; RmwiTruncateBackingStoreFile(_RMW_STORE *)
0x140020bb7  mov     eax, [rbx+1DCh]
0x140020bbd  mov     [rsi+30h], eax
0x140020bc0  cmp     dword ptr [rbx+1DCh], 0
0x140020bc7  jl      short loc_140020BCE
0x140020bc9  mov     eax, [rdi+40h]
0x140020bcc  jmp     short loc_140020BD0
0x140020bce  xor     eax, eax
0x140020bd0  lea     rcx, [rbx+8]; SpinLock
0x140020bd4  mov     [rsi+38h], rax
0x140020bd8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140020bdf  nop     dword ptr [rax+rax+00h]
0x140020be4  lea     rcx, [rbx+20h]
0x140020be8  mov     dl, al; NewIrql
0x140020bea  cmp     [rcx], rcx
0x140020bed  setnz   bpl
0x140020bf1  movzx   ecx, bpl
0x140020bf5  mov     [rbx+78h], ecx
0x140020bf8  lea     rcx, [rbx+30h]
0x140020bfc  mov     rdi, [rcx]
0x140020bff  cmp     rdi, rcx
0x140020c02  jnz     short loc_140020C0B
0x140020c04  xor     edi, edi
0x140020c06  xor     r14d, r14d
0x140020c09  jmp     short loc_140020C25
0x140020c0b  mov     rax, [rbx+18h]
0x140020c0f  mov     [rdi+8], rax
0x140020c13  mov     [rax], rdi
0x140020c16  lea     rax, [rbx+10h]
0x140020c1a  mov     r14, [rbx+38h]
0x140020c1e  mov     [r14], rax
0x140020c21  mov     [rbx+18h], r14
0x140020c25  mov     [rcx+8], rcx
0x140020c29  mov     [rcx], rcx
0x140020c2c  lea     rcx, [rbx+8]; SpinLock
0x140020c30  inc     dword ptr [rbx+1E8h]
0x140020c36  call    cs:__imp_KeReleaseSpinLock
0x140020c3d  nop     dword ptr [rax+rax+00h]
0x140020c42  dec     byte ptr [rsi+43h]
0x140020c45  xor     edx, edx; PriorityBoost
0x140020c47  add     qword ptr [rsi+0B8h], 0FFFFFFFFFFFFFFB8h
0x140020c4f  mov     rcx, rsi; Irp
0x140020c52  call    cs:__imp_IofCompleteRequest
0x140020c59  nop     dword ptr [rax+rax+00h]
0x140020c5e  test    rdi, rdi
0x140020c61  jz      short loc_140020C7B
0x140020c63  mov     rbx, rdi
0x140020c66  mov     rdi, [rdi]
0x140020c69  lea     rcx, [rbx-18h]; struct _VHD_IRP_CONTEXT_HEADER *
0x140020c6d  mov     rdx, [rcx+10h]; struct _IRP *
0x140020c71  call    ?RmwiCallDownLevelDriver@@YAJPEAU_VHD_IRP_CONTEXT_HEADER@@PEAU_IRP@@@Z; RmwiCallDownLevelDriver(_VHD_IRP_CONTEXT_HEADER *,_IRP *)
0x140020c76  cmp     rbx, r14
0x140020c79  jnz     short loc_140020C63
0x140020c7b  mov     al, bpl
0x140020c7e  add     rsp, 38h
0x140020c82  pop     r15
0x140020c84  pop     r14
0x140020c86  pop     rdi
0x140020c87  pop     rsi
0x140020c88  pop     rbp
0x140020c89  pop     rbx
0x140020c8a  retn
```
