# RmwiConsumeStateActive(_RMW_STORE *)

- ea: `0x1400206e0`
- end: `0x14002086c`
- name: `?RmwiConsumeStateActive@@YAEPEAU_RMW_STORE@@@Z`
- size: `396`
- prototype: `bool __fastcall(struct _RMW_STORE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400e8f94`

## callees

- `0x1400206e0`
- `0x140020ffc`
- `0x140023560`
- `0x140035e94`
- `0x1400b98ec`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140020832`
- `ntoskrnl!IofCompleteRequest` at `0x140020832`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400207b8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400207b8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140020816`
- `ntoskrnl!KeReleaseSpinLock` at `0x140020816`

## pseudocode

```c
bool __fastcall RmwiConsumeStateActive(struct _RMW_STORE *a1)
{
  IRP *v2; // rsi
  __int64 v3; // rdi
  unsigned __int64 v4; // rcx
  int v5; // edx
  int v6; // r8d
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
      if ( (unsigned int)dword_140087708 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_140087708, 2) )
          TraceEvents(
            (int)"RmwiConsumeStateActive",
            1277,
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
0x1400206e0  push    rbx
0x1400206e2  push    rbp
0x1400206e3  push    rsi
0x1400206e4  push    rdi
0x1400206e5  push    r14
0x1400206e7  push    r15
0x1400206e9  sub     rsp, 38h
0x1400206ed  cmp     dword ptr [rcx+1DCh], 0
0x1400206f4  mov     rbx, rcx
0x1400206f7  mov     rsi, [rcx+88h]
0x1400206fe  mov     rdi, [rcx+98h]
0x140020705  jl      loc_140020797
0x14002070b  mov     rax, [rsi+0B8h]
0x140020712  cmp     byte ptr [rax-48h], 4
0x140020716  jnz     short loc_140020797
0x140020718  mov     ecx, [rdi+40h]
0x14002071b  add     rcx, [rdi+38h]
0x14002071f  cmp     [rbx+200h], rcx
0x140020726  jnb     short loc_140020782
0x140020728  mov     [rbx+200h], rcx
0x14002072f  mov     r8d, 5
0x140020735  mov     eax, cs:dword_140087708
0x14002073b  cmp     eax, r8d
0x14002073e  jbe     short loc_140020782
0x140020740  lea     edx, [r8-3]
0x140020744  lea     rcx, dword_140087708
0x14002074b  call    _tlgKeywordOn
0x140020750  test    al, al
0x140020752  jz      short loc_140020782
0x140020754  mov     rax, [rbx+200h]
0x14002075b  mov     ecx, 4FDh
0x140020760  mov     qword ptr [rsp+68h+var_40], rax; char
0x140020765  mov     r9d, edx; int
0x140020768  lea     rax, aRmwiconsumesta_0; "RmwiConsumeStateActive() RMW EndOfFileP"...
0x14002076f  mov     edx, ecx; int
0x140020771  lea     rcx, aRmwiconsumesta; "RmwiConsumeStateActive"
0x140020778  mov     [rsp+68h+var_48], rax; char *
0x14002077d  call    TraceEvents
0x140020782  mov     rax, [rbx+200h]
0x140020789  cmp     [rbx+70h], rax
0x14002078d  jbe     short loc_140020797
0x14002078f  mov     rcx, rbx; struct _RMW_STORE *
0x140020792  call    ?RmwiTruncateBackingStoreFile@@YAJPEAU_RMW_STORE@@@Z; RmwiTruncateBackingStoreFile(_RMW_STORE *)
0x140020797  mov     eax, [rbx+1DCh]
0x14002079d  mov     [rsi+30h], eax
0x1400207a0  cmp     dword ptr [rbx+1DCh], 0
0x1400207a7  jl      short loc_1400207AE
0x1400207a9  mov     eax, [rdi+40h]
0x1400207ac  jmp     short loc_1400207B0
0x1400207ae  xor     eax, eax
0x1400207b0  lea     rcx, [rbx+8]; SpinLock
0x1400207b4  mov     [rsi+38h], rax
0x1400207b8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400207bf  nop     dword ptr [rax+rax+00h]
0x1400207c4  lea     rcx, [rbx+20h]
0x1400207c8  mov     dl, al; NewIrql
0x1400207ca  cmp     [rcx], rcx
0x1400207cd  setnz   bpl
0x1400207d1  movzx   ecx, bpl
0x1400207d5  mov     [rbx+78h], ecx
0x1400207d8  lea     rcx, [rbx+30h]
0x1400207dc  mov     rdi, [rcx]
0x1400207df  cmp     rdi, rcx
0x1400207e2  jnz     short loc_1400207EB
0x1400207e4  xor     edi, edi
0x1400207e6  xor     r14d, r14d
0x1400207e9  jmp     short loc_140020805
0x1400207eb  mov     rax, [rbx+18h]
0x1400207ef  mov     [rdi+8], rax
0x1400207f3  mov     [rax], rdi
0x1400207f6  lea     rax, [rbx+10h]
0x1400207fa  mov     r14, [rbx+38h]
0x1400207fe  mov     [r14], rax
0x140020801  mov     [rbx+18h], r14
0x140020805  mov     [rcx+8], rcx
0x140020809  mov     [rcx], rcx
0x14002080c  lea     rcx, [rbx+8]; SpinLock
0x140020810  inc     dword ptr [rbx+1E8h]
0x140020816  call    cs:__imp_KeReleaseSpinLock
0x14002081d  nop     dword ptr [rax+rax+00h]
0x140020822  dec     byte ptr [rsi+43h]
0x140020825  xor     edx, edx; PriorityBoost
0x140020827  add     qword ptr [rsi+0B8h], 0FFFFFFFFFFFFFFB8h
0x14002082f  mov     rcx, rsi; Irp
0x140020832  call    cs:__imp_IofCompleteRequest
0x140020839  nop     dword ptr [rax+rax+00h]
0x14002083e  test    rdi, rdi
0x140020841  jz      short loc_14002085B
0x140020843  mov     rbx, rdi
0x140020846  mov     rdi, [rdi]
0x140020849  lea     rcx, [rbx-18h]; struct _VHD_IRP_CONTEXT_HEADER *
0x14002084d  mov     rdx, [rcx+10h]; struct _IRP *
0x140020851  call    ?RmwiCallDownLevelDriver@@YAJPEAU_VHD_IRP_CONTEXT_HEADER@@PEAU_IRP@@@Z; RmwiCallDownLevelDriver(_VHD_IRP_CONTEXT_HEADER *,_IRP *)
0x140020856  cmp     rbx, r14
0x140020859  jnz     short loc_140020843
0x14002085b  mov     al, bpl
0x14002085e  add     rsp, 38h
0x140020862  pop     r15
0x140020864  pop     r14
0x140020866  pop     rdi
0x140020867  pop     rsi
0x140020868  pop     rbp
0x140020869  pop     rbx
0x14002086a  retn
```
