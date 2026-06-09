# UdfDismountVcb

- ea: `0x140018740`
- end: `0x140018b07`
- name: `UdfDismountVcb`
- size: `967`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140008594`
- `0x140049f80`

## callees

- `0x140008790`
- `0x140018740`
- `0x14002c008`
- `0x140052864`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400187af`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400189a2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400187af`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400189a2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001894b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140018aaa`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140018ae0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001894b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140018aaa`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140018ae0`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x1400189ca`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x1400189ca`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140018a4d`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140018a94`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140018aca`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140018a4d`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140018a94`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140018aca`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x140018967`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x140018967`

## pseudocode

```c
char __fastcall UdfDismountVcb(__int64 a1, __int64 a2, char a3)
{
  char v5; // di
  unsigned int v6; // esi
  unsigned int v7; // esi
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // rsi
  struct _KTHREAD *CurrentThread; // rax
  _DWORD *v22; // rcx
  char v23; // dl
  KIRQL Irql; // [rsp+70h] [rbp+18h] BYREF

  Irql = 0;
  v5 = 1;
  LOBYTE(v6) = 1;
  if ( a3 && (*(_DWORD *)(a2 + 2128) & 2) != 0 )
  {
    v7 = UdfFlushVolume(a1, a2, 0, 1, 1, 0);
    if ( *(_DWORD *)(a2 + 256) > *(_DWORD *)(a2 + 264) )
      return v5;
    v6 = v7 >> 31;
  }
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
  *(_QWORD *)(a2 + 1640) = KeGetCurrentThread();
  v8 = *(_QWORD *)(a2 + 288);
  *(_DWORD *)(a2 + 52) = 4;
  if ( v8 )
  {
    --*(_DWORD *)(v8 + 204);
    --*(_DWORD *)(*(_QWORD *)(a2 + 288) + 208LL);
  }
  v9 = *(_QWORD *)(a2 + 272);
  if ( v9 )
  {
    --*(_DWORD *)(v9 + 204);
    --*(_DWORD *)(*(_QWORD *)(a2 + 272) + 208LL);
  }
  v10 = *(_QWORD *)(a2 + 344);
  if ( v10 )
  {
    --*(_DWORD *)(v10 + 204);
    --*(_DWORD *)(*(_QWORD *)(a2 + 344) + 208LL);
  }
  v11 = *(_QWORD *)(a2 + 352);
  if ( v11 )
  {
    --*(_DWORD *)(v11 + 204);
    --*(_DWORD *)(*(_QWORD *)(a2 + 352) + 208LL);
  }
  v12 = *(_QWORD *)(a2 + 280);
  if ( v12 )
  {
    --*(_DWORD *)(v12 + 204);
    --*(_DWORD *)(*(_QWORD *)(a2 + 280) + 208LL);
  }
  v13 = *(_QWORD *)(a2 + 296);
  if ( v13 )
  {
    --*(_DWORD *)(v13 + 204);
    --*(_DWORD *)(*(_QWORD *)(a2 + 296) + 208LL);
  }
  v14 = *(_QWORD *)(a2 + 312);
  if ( v14 )
  {
    --*(_DWORD *)(v14 + 204);
    --*(_DWORD *)(*(_QWORD *)(a2 + 312) + 208LL);
  }
  v15 = *(_QWORD *)(a2 + 304);
  if ( v15 )
  {
    --*(_DWORD *)(v15 + 204);
    --*(_DWORD *)(*(_QWORD *)(a2 + 304) + 208LL);
  }
  v16 = *(_QWORD *)(a2 + 320);
  if ( v16 )
  {
    --*(_DWORD *)(v16 + 204);
    --*(_DWORD *)(*(_QWORD *)(a2 + 320) + 208LL);
  }
  v17 = *(_QWORD *)(a2 + 328);
  if ( v17 )
  {
    --*(_DWORD *)(v17 + 204);
    --*(_DWORD *)(*(_QWORD *)(a2 + 328) + 208LL);
  }
  v18 = *(_QWORD *)(a2 + 336);
  if ( v18 )
  {
    --*(_DWORD *)(v18 + 204);
    --*(_DWORD *)(*(_QWORD *)(a2 + 336) + 208LL);
  }
  *(_QWORD *)(a2 + 1640) = 0;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
  if ( (*(_DWORD *)(a2 + 48) & 0x2000000) != 0 )
  {
    IoUnregisterPlugPlayNotification(*(PVOID *)(a2 + 2528));
    *(_DWORD *)(a2 + 48) &= ~0x2000000u;
  }
  LOBYTE(v19) = 1;
  UdfFlushVolume(a1, a2, v19, 0, v6, 0);
  UdfFspClose(a2);
  v20 = *(_QWORD *)(a2 + 8);
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
  CurrentThread = KeGetCurrentThread();
  --*(_DWORD *)(a2 + 256);
  *(_QWORD *)(a2 + 1640) = CurrentThread;
  IoAcquireVpbSpinLock(&Irql);
  v22 = (_DWORD *)(v20 + 28);
  if ( *(_DWORD *)(a2 + 256) || (v23 = 1, *v22 != 1) )
    v23 = 0;
  if ( *(_QWORD *)(*(_QWORD *)(v20 + 16) + 56LL) == v20 )
  {
    if ( !v23 )
    {
      **(_WORD **)(a2 + 1848) = 10;
      *(_WORD *)(*(_QWORD *)(a2 + 1848) + 2LL) = 96;
      *(_QWORD *)(*(_QWORD *)(a2 + 1848) + 16LL) = *(_QWORD *)(v20 + 16);
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 1848) + 16LL) + 56LL) = *(_QWORD *)(a2 + 1848);
      *(_WORD *)(*(_QWORD *)(a2 + 1848) + 4LL) = *(_WORD *)(v20 + 4) & 8;
      IoReleaseVpbSpinLock(Irql);
      *(_QWORD *)(a2 + 1848) = 0;
LABEL_40:
      *(_QWORD *)(a2 + 1640) = 0;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
      return v5;
    }
    --*v22;
    *(_QWORD *)(v20 + 8) = 0;
    *(_WORD *)(*(_QWORD *)(a2 + 8) + 4LL) &= ~1u;
    *(_WORD *)(*(_QWORD *)(a2 + 8) + 4LL) &= 0xFFDDu;
    *(_QWORD *)(a2 + 8) = 0;
  }
  else
  {
    if ( !v23 )
    {
      IoReleaseVpbSpinLock(Irql);
      goto LABEL_40;
    }
    --*v22;
  }
  IoReleaseVpbSpinLock(Irql);
  *(_QWORD *)(a2 + 1640) = 0;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
  UdfDeleteVcb(a1, a2);
  return 0;
}

```

## disassembly

```asm
0x140018740  mov     r11, rsp
0x140018743  mov     [r11+8], rbx
0x140018747  mov     [r11+10h], rbp
0x14001874b  push    rsi
0x14001874c  push    rdi
0x14001874d  push    r12
0x14001874f  push    r14
0x140018751  push    r15
0x140018753  sub     rsp, 30h
0x140018757  xor     r15d, r15d
0x14001875a  mov     rbx, rdx
0x14001875d  mov     [r11+18h], r15b
0x140018761  mov     r14, rcx
0x140018764  lea     edi, [r15+1]
0x140018768  mov     sil, dil
0x14001876b  test    r8b, r8b
0x14001876e  jz      short loc_1400187A5
0x140018770  mov     eax, [rdx+850h]
0x140018776  test    al, 2
0x140018778  jz      short loc_1400187A5
0x14001877a  mov     [r11-30h], r15b
0x14001877e  mov     r9b, dil
0x140018781  xor     r8d, r8d
0x140018784  mov     [rsp+58h+var_38], dil; char
0x140018789  call    UdfFlushVolume
0x14001878e  mov     ecx, [rbx+108h]
0x140018794  mov     esi, eax
0x140018796  cmp     [rbx+100h], ecx
0x14001879c  ja      loc_140018AEC
0x1400187a2  shr     esi, 1Fh
0x1400187a5  lea     rbp, [rbx+630h]
0x1400187ac  mov     rcx, rbp; FastMutex
0x1400187af  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400187b6  nop     dword ptr [rax+rax+00h]
0x1400187bb  mov     rax, gs:188h
0x1400187c4  or      r12d, 0FFFFFFFFh
0x1400187c8  mov     [rbx+668h], rax
0x1400187cf  mov     rax, [rbx+120h]
0x1400187d6  mov     dword ptr [rbx+34h], 4
0x1400187dd  test    rax, rax
0x1400187e0  jz      short loc_1400187F7
0x1400187e2  add     [rax+0CCh], r12d
0x1400187e9  mov     rax, [rbx+120h]
0x1400187f0  add     [rax+0D0h], r12d
0x1400187f7  mov     rax, [rbx+110h]
0x1400187fe  test    rax, rax
0x140018801  jz      short loc_140018818
0x140018803  add     [rax+0CCh], r12d
0x14001880a  mov     rax, [rbx+110h]
0x140018811  add     [rax+0D0h], r12d
0x140018818  mov     rax, [rbx+158h]
0x14001881f  test    rax, rax
0x140018822  jz      short loc_140018839
0x140018824  add     [rax+0CCh], r12d
0x14001882b  mov     rax, [rbx+158h]
0x140018832  add     [rax+0D0h], r12d
0x140018839  mov     rax, [rbx+160h]
0x140018840  test    rax, rax
0x140018843  jz      short loc_14001885A
0x140018845  add     [rax+0CCh], r12d
0x14001884c  mov     rax, [rbx+160h]
0x140018853  add     [rax+0D0h], r12d
0x14001885a  mov     rax, [rbx+118h]
0x140018861  test    rax, rax
0x140018864  jz      short loc_14001887B
0x140018866  add     [rax+0CCh], r12d
0x14001886d  mov     rax, [rbx+118h]
0x140018874  add     [rax+0D0h], r12d
0x14001887b  mov     rax, [rbx+128h]
0x140018882  test    rax, rax
0x140018885  jz      short loc_14001889C
0x140018887  add     [rax+0CCh], r12d
0x14001888e  mov     rax, [rbx+128h]
0x140018895  add     [rax+0D0h], r12d
0x14001889c  mov     rax, [rbx+138h]
0x1400188a3  test    rax, rax
0x1400188a6  jz      short loc_1400188BD
0x1400188a8  add     [rax+0CCh], r12d
0x1400188af  mov     rax, [rbx+138h]
0x1400188b6  add     [rax+0D0h], r12d
0x1400188bd  mov     rax, [rbx+130h]
0x1400188c4  test    rax, rax
0x1400188c7  jz      short loc_1400188DE
0x1400188c9  add     [rax+0CCh], r12d
0x1400188d0  mov     rax, [rbx+130h]
0x1400188d7  add     [rax+0D0h], r12d
0x1400188de  mov     rax, [rbx+140h]
0x1400188e5  test    rax, rax
0x1400188e8  jz      short loc_1400188FF
0x1400188ea  add     [rax+0CCh], r12d
0x1400188f1  mov     rax, [rbx+140h]
0x1400188f8  add     [rax+0D0h], r12d
0x1400188ff  mov     rax, [rbx+148h]
0x140018906  test    rax, rax
0x140018909  jz      short loc_140018920
0x14001890b  add     [rax+0CCh], r12d
0x140018912  mov     rax, [rbx+148h]
0x140018919  add     [rax+0D0h], r12d
0x140018920  mov     rax, [rbx+150h]
0x140018927  test    rax, rax
0x14001892a  jz      short loc_140018941
0x14001892c  add     [rax+0CCh], r12d
0x140018933  mov     rax, [rbx+150h]
0x14001893a  add     [rax+0D0h], r12d
0x140018941  mov     rcx, rbp; FastMutex
0x140018944  mov     [rbx+668h], r15
0x14001894b  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140018952  nop     dword ptr [rax+rax+00h]
0x140018957  test    dword ptr [rbx+30h], 2000000h
0x14001895e  jz      short loc_140018978
0x140018960  mov     rcx, [rbx+9E0h]; NotificationEntry
0x140018967  call    cs:__imp_IoUnregisterPlugPlayNotification
0x14001896e  nop     dword ptr [rax+rax+00h]
0x140018973  btr     dword ptr [rbx+30h], 19h
0x140018978  mov     [rsp+58h+var_30], r15b; char
0x14001897d  xor     r9d, r9d
0x140018980  mov     r8b, dil
0x140018983  mov     [rsp+58h+var_38], sil; char
0x140018988  mov     rdx, rbx
0x14001898b  mov     rcx, r14; int
0x14001898e  call    UdfFlushVolume
0x140018993  mov     rcx, rbx
0x140018996  call    UdfFspClose
0x14001899b  mov     rsi, [rbx+8]
0x14001899f  mov     rcx, rbp; FastMutex
0x1400189a2  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400189a9  nop     dword ptr [rax+rax+00h]
0x1400189ae  mov     rax, gs:188h
0x1400189b7  lea     rcx, [rsp+58h+Irql]; Irql
0x1400189bc  add     [rbx+100h], r12d
0x1400189c3  mov     [rbx+668h], rax
0x1400189ca  call    cs:__imp_IoAcquireVpbSpinLock
0x1400189d1  nop     dword ptr [rax+rax+00h]
0x1400189d6  lea     rcx, [rsi+1Ch]
0x1400189da  cmp     [rbx+100h], r15d
0x1400189e1  jnz     short loc_1400189EA
0x1400189e3  mov     dl, dil
0x1400189e6  cmp     [rcx], edi
0x1400189e8  jz      short loc_1400189ED
0x1400189ea  mov     dl, r15b
0x1400189ed  mov     rax, [rsi+10h]
0x1400189f1  cmp     [rax+38h], rsi
0x1400189f5  jnz     loc_140018A89
0x1400189fb  test    dl, dl
0x1400189fd  jnz     short loc_140018A62
0x1400189ff  mov     rax, [rbx+738h]
0x140018a06  mov     word ptr [rax], 0Ah
0x140018a0b  mov     rax, [rbx+738h]
0x140018a12  mov     word ptr [rax+2], 60h ; '`'
0x140018a18  mov     rdx, [rbx+738h]
0x140018a1f  mov     rax, [rsi+10h]
0x140018a23  mov     [rdx+10h], rax
0x140018a27  mov     rdx, [rbx+738h]
0x140018a2e  mov     rax, [rdx+10h]
0x140018a32  mov     [rax+38h], rdx
0x140018a36  movzx   edx, word ptr [rsi+4]
0x140018a3a  mov     rax, [rbx+738h]
0x140018a41  and     dx, 8
0x140018a45  mov     [rax+4], dx
0x140018a49  mov     cl, [rsp+58h+Irql]; Irql
0x140018a4d  call    cs:__imp_IoReleaseVpbSpinLock
0x140018a54  nop     dword ptr [rax+rax+00h]
0x140018a59  mov     [rbx+738h], r15
0x140018a60  jmp     short loc_140018AD6
0x140018a62  add     [rcx], r12d
0x140018a65  mov     ecx, 0FFFEh
0x140018a6a  mov     [rsi+8], r15
0x140018a6e  mov     rax, [rbx+8]
0x140018a72  and     [rax+4], cx
0x140018a76  mov     ecx, 0FFDDh
0x140018a7b  mov     rax, [rbx+8]
0x140018a7f  and     [rax+4], cx
0x140018a83  mov     [rbx+8], r15
0x140018a87  jmp     short loc_140018A90
0x140018a89  test    dl, dl
0x140018a8b  jz      short loc_140018AC6
0x140018a8d  add     [rcx], r12d
0x140018a90  mov     cl, [rsp+58h+Irql]; Irql
0x140018a94  call    cs:__imp_IoReleaseVpbSpinLock
0x140018a9b  nop     dword ptr [rax+rax+00h]
0x140018aa0  mov     rcx, rbp; FastMutex
0x140018aa3  mov     [rbx+668h], r15
0x140018aaa  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140018ab1  nop     dword ptr [rax+rax+00h]
0x140018ab6  mov     rdx, rbx
0x140018ab9  mov     rcx, r14
0x140018abc  call    UdfDeleteVcb
0x140018ac1  mov     dil, r15b
0x140018ac4  jmp     short loc_140018AEC
0x140018ac6  mov     cl, [rsp+58h+Irql]; Irql
0x140018aca  call    cs:__imp_IoReleaseVpbSpinLock
0x140018ad1  nop     dword ptr [rax+rax+00h]
0x140018ad6  mov     rcx, rbp; FastMutex
0x140018ad9  mov     [rbx+668h], r15
0x140018ae0  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140018ae7  nop     dword ptr [rax+rax+00h]
0x140018aec  mov     rbx, [rsp+58h+arg_0]
0x140018af1  mov     al, dil
0x140018af4  mov     rbp, [rsp+58h+arg_8]
0x140018af9  add     rsp, 30h
0x140018afd  pop     r15
0x140018aff  pop     r14
0x140018b01  pop     r12
0x140018b03  pop     rdi
0x140018b04  pop     rsi
0x140018b05  retn
```
