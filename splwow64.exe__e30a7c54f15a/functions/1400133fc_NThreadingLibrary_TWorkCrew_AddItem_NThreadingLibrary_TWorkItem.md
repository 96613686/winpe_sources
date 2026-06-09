# NThreadingLibrary::TWorkCrew::AddItem(NThreadingLibrary::TWorkItem *)

- ea: `0x1400133fc`
- end: `0x140013634`
- name: `?AddItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z`
- size: `568`
- prototype: `__int64 __fastcall(NThreadingLibrary::TWorkCrew *__hidden this, struct NThreadingLibrary::TWorkItem *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001140c`
- `0x140013de0`

## callees

- `0x1400133fc`
- `0x1400138cc`
- `0x1400139b0`
- `0x140016010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1400135fe`
- `ntdll!RtlNtStatusToDosError` at `0x1400135fe`
- `ntdll!TpSetWait` at `0x1400135af`
- `ntdll!TpSetWait` at `0x1400135af`
- `ntdll!TpSimpleTryPost` at `0x1400135f6`
- `ntdll!TpSimpleTryPost` at `0x1400135f6`
- `ntdll!TpPostWork` at `0x1400135e4`
- `ntdll!TpPostWork` at `0x1400135e4`
- `ntdll!TpAllocWait` at `0x140013594`
- `ntdll!TpAllocWait` at `0x140013594`
- `ntdll!TpAllocTimer` at `0x140013545`
- `ntdll!TpAllocTimer` at `0x140013545`
- `ntdll!TpSetTimer` at `0x140013564`
- `ntdll!TpSetTimer` at `0x140013564`
- `ntdll!TpAllocIoCompletion` at `0x140013505`
- `ntdll!TpAllocIoCompletion` at `0x140013505`
- `ntdll!TpStartAsyncIoOperation` at `0x140013514`
- `ntdll!TpStartAsyncIoOperation` at `0x140013514`
- `ntdll!TpAllocAlpcCompletion` at `0x1400134d1`
- `ntdll!TpAllocAlpcCompletion` at `0x1400134d1`
- `ntdll!TpAllocWork` at `0x1400135d1`
- `ntdll!TpAllocWork` at `0x1400135d1`

## pseudocode

```c
__int64 __fastcall NThreadingLibrary::TWorkCrew::AddItem(
        NThreadingLibrary::TWorkCrew *this,
        struct NThreadingLibrary::TWorkItem *a2)
{
  __int64 v4; // rdx
  signed int inserted; // ebx
  __int64 v6; // r8
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rdx
  int v15; // esi
  NTSTATUS v16; // ecx
  signed int v17; // eax

  if ( !a2
    || (*(int (__fastcall **)(struct NThreadingLibrary::TWorkItem *))(*(_QWORD *)a2 + 16LL))(a2) < 0
    || *((_DWORD *)a2 + 16) != 1953063799 )
  {
    return (unsigned int)-2147024809;
  }
  inserted = NThreadingLibrary::TWorkCrew::InsertWorkItem(this, a2);
  if ( inserted < 0 )
    return (unsigned int)inserted;
  v6 = *((_QWORD *)a2 + 3);
  if ( v6 )
    *(_QWORD *)(v6 + 8) = *((_QWORD *)this + 28);
  else
    v6 = *((_QWORD *)this + 3);
  v7 = *((_DWORD *)a2 + 22);
  if ( !v7 )
  {
    v13 = TpSimpleTryPost(NThreadingLibrary::TWorkCrew::tpSimpleCallback, a2, v6);
    goto LABEL_36;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    if ( *((_QWORD *)a2 + 12)
      || (v13 = TpAllocWork((char *)a2 + 96, NThreadingLibrary::TWorkCrew::tpWorkCallback, a2, v6), v13 >= 0) )
    {
      inserted = 0;
      _InterlockedIncrement((volatile signed __int32 *)a2 + 26);
      TpPostWork(*((_QWORD *)a2 + 12), v4, v6);
      goto LABEL_39;
    }
    goto LABEL_36;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    if ( *((_QWORD *)a2 + 13) )
    {
      if ( *((_QWORD *)a2 + 12)
        || (v13 = TpAllocWait((char *)a2 + 96, NThreadingLibrary::TWorkCrew::tpWaitCallback, a2, v6), v13 >= 0) )
      {
        inserted = 0;
        TpSetWait(*((_QWORD *)a2 + 12), *(_QWORD *)(*((_QWORD *)a2 + 13) + 16LL), *((_QWORD *)a2 + 15));
        goto LABEL_39;
      }
      goto LABEL_36;
    }
    goto LABEL_16;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    if ( *((_QWORD *)a2 + 12)
      || (v13 = TpAllocTimer((char *)a2 + 96, NThreadingLibrary::TWorkCrew::tpTimerCallback, a2, v6), v13 >= 0) )
    {
      inserted = 0;
      TpSetTimer(*((_QWORD *)a2 + 12), (char *)a2 + 104, *((unsigned int *)a2 + 28), *((unsigned int *)a2 + 29));
      goto LABEL_39;
    }
    goto LABEL_36;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    v14 = *((_QWORD *)a2 + 13);
    if ( v14 )
    {
      if ( !*((_QWORD *)a2 + 12) )
      {
        v15 = TpAllocIoCompletion(
                (char *)a2 + 96,
                *(_QWORD *)(v14 + 16),
                NThreadingLibrary::TWorkCrew::tpIOCallback,
                a2,
                v6);
        if ( v15 >= 0 )
          TpStartAsyncIoOperation(*((_QWORD *)a2 + 12));
        v16 = v15;
        goto LABEL_37;
      }
LABEL_24:
      inserted = 458802;
      goto LABEL_39;
    }
LABEL_16:
    inserted = -2147024809;
    goto LABEL_39;
  }
  if ( v11 != 1 )
  {
    inserted = -2147024809;
LABEL_40:
    NThreadingLibrary::TWorkCrew::MoveWorkItemToCancelQueue(this, a2);
    return (unsigned int)inserted;
  }
  v12 = *((_QWORD *)a2 + 13);
  if ( !v12 )
    goto LABEL_16;
  if ( *((_QWORD *)a2 + 12) )
    goto LABEL_24;
  v13 = TpAllocAlpcCompletion(
          (char *)a2 + 96,
          *(_QWORD *)(v12 + 16),
          NThreadingLibrary::TWorkCrew::tpIOCallback,
          a2,
          v6);
LABEL_36:
  v16 = v13;
LABEL_37:
  v17 = RtlNtStatusToDosError(v16);
  inserted = v17;
  if ( v17 > 0 )
    inserted = (unsigned __int16)v17 | 0x80070000;
LABEL_39:
  if ( inserted < 0 )
    goto LABEL_40;
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1400133fc  push    rbx
0x1400133fe  push    rbp
0x1400133ff  push    rsi
0x140013400  push    rdi
0x140013401  sub     rsp, 38h
0x140013405  mov     rdi, rdx
0x140013408  mov     rbp, rcx
0x14001340b  test    rdx, rdx
0x14001340e  jz      loc_140013624
0x140013414  mov     rax, [rdx]
0x140013417  mov     rcx, rdx
0x14001341a  mov     rax, [rax+10h]
0x14001341e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013423  test    eax, eax
0x140013425  js      loc_140013624
0x14001342b  cmp     dword ptr [rdi+40h], 74696377h
0x140013432  jnz     loc_140013624
0x140013438  mov     rdx, rdi; struct NThreadingLibrary::TWorkItem *
0x14001343b  mov     rcx, rbp; this
0x14001343e  call    ?InsertWorkItem@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::InsertWorkItem(NThreadingLibrary::TWorkItem *)
0x140013443  mov     ebx, eax
0x140013445  test    eax, eax
0x140013447  js      loc_140013629
0x14001344d  mov     r8, [rdi+18h]
0x140013451  test    r8, r8
0x140013454  jz      short loc_140013463
0x140013456  mov     rax, [rbp+0E0h]
0x14001345d  mov     [r8+8], rax
0x140013461  jmp     short loc_140013467
0x140013463  mov     r8, [rbp+18h]
0x140013467  mov     ecx, [rdi+58h]
0x14001346a  test    ecx, ecx
0x14001346c  jz      loc_1400135EC
0x140013472  sub     ecx, 1
0x140013475  jz      loc_1400135B7
0x14001347b  sub     ecx, 1
0x14001347e  jz      loc_14001356F
0x140013484  sub     ecx, 1
0x140013487  jz      loc_14001352B
0x14001348d  sub     ecx, 1
0x140013490  jz      short loc_1400134DC
0x140013492  cmp     ecx, 1
0x140013495  jz      short loc_1400134A1
0x140013497  mov     ebx, 80070057h
0x14001349c  jmp     loc_140013617
0x1400134a1  mov     rdx, [rdi+68h]
0x1400134a5  test    rdx, rdx
0x1400134a8  jnz     short loc_1400134B4
0x1400134aa  mov     ebx, 80070057h
0x1400134af  jmp     loc_140013613
0x1400134b4  lea     rcx, [rdi+60h]
0x1400134b8  cmp     qword ptr [rcx], 0
0x1400134bc  jnz     short loc_140013521
0x1400134be  mov     rdx, [rdx+10h]
0x1400134c2  mov     r9, rdi
0x1400134c5  mov     [rsp+58h+var_38], r8
0x1400134ca  lea     r8, ?tpIOCallback@TWorkCrew@NThreadingLibrary@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1PEAU_IO_STATUS_BLOCK@@PEAU_TP_IO@@@Z; NThreadingLibrary::TWorkCrew::tpIOCallback(_TP_CALLBACK_INSTANCE *,void *,void *,_IO_STATUS_BLOCK *,_TP_IO *)
0x1400134d1  call    cs:__imp_TpAllocAlpcCompletion
0x1400134d7  jmp     loc_1400135FC
0x1400134dc  mov     rdx, [rdi+68h]
0x1400134e0  test    rdx, rdx
0x1400134e3  jz      short loc_1400134AA
0x1400134e5  lea     rbx, [rdi+60h]
0x1400134e9  cmp     qword ptr [rbx], 0
0x1400134ed  jnz     short loc_140013521
0x1400134ef  mov     rdx, [rdx+10h]
0x1400134f3  mov     r9, rdi
0x1400134f6  mov     [rsp+58h+var_38], r8
0x1400134fb  mov     rcx, rbx
0x1400134fe  lea     r8, ?tpIOCallback@TWorkCrew@NThreadingLibrary@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1PEAU_IO_STATUS_BLOCK@@PEAU_TP_IO@@@Z; NThreadingLibrary::TWorkCrew::tpIOCallback(_TP_CALLBACK_INSTANCE *,void *,void *,_IO_STATUS_BLOCK *,_TP_IO *)
0x140013505  call    cs:__imp_TpAllocIoCompletion
0x14001350b  mov     esi, eax
0x14001350d  test    eax, eax
0x14001350f  js      short loc_14001351A
0x140013511  mov     rcx, [rbx]
0x140013514  call    cs:__imp_TpStartAsyncIoOperation
0x14001351a  mov     ecx, esi
0x14001351c  jmp     loc_1400135FE
0x140013521  mov     ebx, 70032h
0x140013526  jmp     loc_140013613
0x14001352b  lea     rsi, [rdi+60h]
0x14001352f  cmp     qword ptr [rsi], 0
0x140013533  jnz     short loc_140013553
0x140013535  mov     r9, r8
0x140013538  lea     rdx, ?tpTimerCallback@TWorkCrew@NThreadingLibrary@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; NThreadingLibrary::TWorkCrew::tpTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)
0x14001353f  mov     r8, rdi
0x140013542  mov     rcx, rsi
0x140013545  call    cs:__imp_TpAllocTimer
0x14001354b  test    eax, eax
0x14001354d  js      loc_1400135FC
0x140013553  mov     r9d, [rdi+74h]
0x140013557  lea     rdx, [rdi+68h]
0x14001355b  mov     r8d, [rdi+70h]
0x14001355f  xor     ebx, ebx
0x140013561  mov     rcx, [rsi]
0x140013564  call    cs:__imp_TpSetTimer
0x14001356a  jmp     loc_140013613
0x14001356f  cmp     qword ptr [rdi+68h], 0
0x140013574  jz      loc_1400134AA
0x14001357a  lea     rsi, [rdi+60h]
0x14001357e  cmp     qword ptr [rsi], 0
0x140013582  jnz     short loc_14001359E
0x140013584  mov     r9, r8
0x140013587  lea     rdx, ?tpWaitCallback@TWorkCrew@NThreadingLibrary@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; NThreadingLibrary::TWorkCrew::tpWaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)
0x14001358e  mov     r8, rdi
0x140013591  mov     rcx, rsi
0x140013594  call    cs:__imp_TpAllocWait
0x14001359a  test    eax, eax
0x14001359c  js      short loc_1400135FC
0x14001359e  mov     rdx, [rdi+68h]
0x1400135a2  xor     ebx, ebx
0x1400135a4  mov     r8, [rdi+78h]
0x1400135a8  mov     rcx, [rsi]
0x1400135ab  mov     rdx, [rdx+10h]
0x1400135af  call    cs:__imp_TpSetWait
0x1400135b5  jmp     short loc_140013613
0x1400135b7  lea     rsi, [rdi+60h]
0x1400135bb  cmp     qword ptr [rsi], 0
0x1400135bf  jnz     short loc_1400135DB
0x1400135c1  mov     r9, r8
0x1400135c4  lea     rdx, ?tpWorkCallback@TWorkCrew@NThreadingLibrary@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; NThreadingLibrary::TWorkCrew::tpWorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)
0x1400135cb  mov     r8, rdi
0x1400135ce  mov     rcx, rsi
0x1400135d1  call    cs:__imp_TpAllocWork
0x1400135d7  test    eax, eax
0x1400135d9  js      short loc_1400135FC
0x1400135db  xor     ebx, ebx
0x1400135dd  lock inc dword ptr [rdi+68h]
0x1400135e1  mov     rcx, [rsi]
0x1400135e4  call    cs:__imp_TpPostWork
0x1400135ea  jmp     short loc_140013613
0x1400135ec  mov     rdx, rdi
0x1400135ef  lea     rcx, ?tpSimpleCallback@TWorkCrew@NThreadingLibrary@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; NThreadingLibrary::TWorkCrew::tpSimpleCallback(_TP_CALLBACK_INSTANCE *,void *)
0x1400135f6  call    cs:__imp_TpSimpleTryPost
0x1400135fc  mov     ecx, eax; Status
0x1400135fe  call    cs:__imp_RtlNtStatusToDosError
0x140013604  mov     ebx, eax
0x140013606  test    eax, eax
0x140013608  jle     short loc_140013613
0x14001360a  movzx   ebx, ax
0x14001360d  or      ebx, 80070000h
0x140013613  test    ebx, ebx
0x140013615  jns     short loc_140013629
0x140013617  mov     rdx, rdi; struct NThreadingLibrary::TWorkItem *
0x14001361a  mov     rcx, rbp; this
0x14001361d  call    ?MoveWorkItemToCancelQueue@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::MoveWorkItemToCancelQueue(NThreadingLibrary::TWorkItem *)
0x140013622  jmp     short loc_140013629
0x140013624  mov     ebx, 80070057h
0x140013629  mov     eax, ebx
0x14001362b  add     rsp, 38h
0x14001362f  pop     rdi
0x140013630  pop     rsi
0x140013631  pop     rbp
0x140013632  pop     rbx
0x140013633  retn
```
