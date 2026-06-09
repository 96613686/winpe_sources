# ParentResetOrCyclePort

- ea: `0x14000159c`
- end: `0x1400018a9`
- name: `ParentResetOrCyclePort`
- size: `781`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400018b0`

## callees

- `0x14000159c`
- `0x1400054a0`
- `0x1400088b4`
- `0x14000e128`
- `0x140029b30`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140001852`
- `ntoskrnl!IofCompleteRequest` at `0x140001852`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140001879`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140001879`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400015f0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001766`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400015f0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001766`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000168a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000180b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000168a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000180b`

## pseudocode

```c
__int64 __fastcall ParentResetOrCyclePort(__int64 a1, _QWORD *a2, int a3)
{
  __int64 v4; // rbx
  __int64 v7; // rbx
  KSPIN_LOCK *v8; // rcx
  __int64 v9; // r12
  KIRQL v10; // al
  bool v11; // zf
  int v12; // edx
  _QWORD *v13; // rcx
  unsigned int v14; // esi
  char v15; // r15
  __int64 v16; // rax
  __int64 v17; // rax
  unsigned int *v18; // rcx
  unsigned int v19; // edx
  __int64 v20; // rax
  unsigned int v21; // eax
  __int64 v22; // rdx
  KIRQL v23; // al
  KIRQL v24; // r8
  unsigned int *v25; // rcx
  unsigned int v26; // edx
  __int64 v27; // rax
  _QWORD *v28; // rax
  __int64 v29; // rcx
  _QWORD *v30; // rcx
  __int64 v31; // rbx
  __int64 v32; // rax
  IRP *v33; // rbx
  __int128 v35; // [rsp+30h] [rbp-10h] BYREF
  int v36; // [rsp+80h] [rbp+40h] BYREF
  KIRQL v37; // [rsp+90h] [rbp+50h]

  v36 = 0;
  v4 = 632;
  if ( a3 != 2228255 )
    v4 = 608;
  v7 = a1 + v4;
  v8 = (KSPIN_LOCK *)(a1 + 584);
  v9 = 624;
  if ( a3 != 2228255 )
    v9 = 604;
  v10 = KeAcquireSpinLockRaiseToDpc(v8);
  v11 = *(_BYTE *)(v9 + a1) == 0;
  LOBYTE(v12) = v10;
  v37 = v10;
  if ( v11 )
  {
    v14 = -1073741823;
    *(_BYTE *)(v9 + a1) = 1;
    v15 = 1;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), v12, 8, 57, (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids);
      LOBYTE(v12) = v37;
    }
    *(_BYTE *)(a2[23] + 3LL) |= 1u;
    v13 = *(_QWORD **)(v7 + 8);
    if ( *v13 != v7 )
LABEL_34:
      __fastfail(3u);
    v14 = 259;
    a2[21] = v7;
    v15 = 0;
    a2[22] = v13;
    *v13 = a2 + 21;
    *(_QWORD *)(v7 + 8) = a2 + 21;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 584), v12);
  if ( v15 )
  {
    v16 = a2[23];
    v35 = 0;
    *(_OWORD *)(v16 - 72) = *(_OWORD *)v16;
    *(_OWORD *)(v16 - 56) = *(_OWORD *)(v16 + 16);
    *(_OWORD *)(v16 - 40) = *(_OWORD *)(v16 + 32);
    *(_QWORD *)(v16 - 24) = *(_QWORD *)(v16 + 48);
    *(_BYTE *)(v16 - 69) = 0;
    if ( *(_BYTE *)(a1 + 1376) == 1 )
    {
      if ( a3 == 2228231 )
      {
        v17 = a2[23];
        *(_DWORD *)(v17 - 48) = 2232243;
        *(_QWORD *)(v17 - 64) = &v36;
      }
      v18 = *(unsigned int **)(a1 + 128);
      if ( *v18 )
      {
        v19 = 0;
        do
        {
          v20 = v19++;
          *(_BYTE *)(*(_QWORD *)(*(_QWORD *)&v18[2 * v20 + 2] + 64LL) + 413LL) = 1;
          v18 = *(unsigned int **)(a1 + 128);
        }
        while ( v19 < *v18 );
      }
    }
    v21 = CallNextDriverSync(a1, a2);
    LOBYTE(v22) = *(_BYTE *)(a1 + 1362);
    v14 = v21;
    NotifyPdosOfSurprisePowerOn(a1, v22);
    *((_QWORD *)&v35 + 1) = &v35;
    *(_QWORD *)&v35 = &v35;
    v23 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 584));
    *(_BYTE *)(v9 + a1) = 0;
    v24 = v23;
    if ( *(_BYTE *)(a1 + 1376) == 1 )
    {
      v25 = *(unsigned int **)(a1 + 128);
      if ( *v25 )
      {
        v26 = 0;
        do
        {
          v27 = *(_QWORD *)(*(_QWORD *)&v25[2 * v26 + 2] + 64LL);
          if ( *(_BYTE *)(v27 + 414) == 1 )
            *(_WORD *)(v27 + 413) = 0;
          v25 = *(unsigned int **)(a1 + 128);
          ++v26;
        }
        while ( v26 < *v25 );
      }
    }
    while ( 1 )
    {
      v28 = *(_QWORD **)v7;
      if ( *(_QWORD *)v7 == v7 )
        break;
      if ( v28[1] != v7 )
        goto LABEL_34;
      v29 = *v28;
      if ( *(_QWORD **)(*v28 + 8LL) != v28 )
        goto LABEL_34;
      *(_QWORD *)v7 = v29;
      *(_QWORD *)(v29 + 8) = v7;
      v30 = (_QWORD *)*((_QWORD *)&v35 + 1);
      if ( **((__int128 ***)&v35 + 1) != &v35 )
        goto LABEL_34;
      v28[1] = *((_QWORD *)&v35 + 1);
      *v28 = &v35;
      *v30 = v28;
      *((_QWORD *)&v35 + 1) = v28;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 584), v24);
    while ( 1 )
    {
      v31 = v35;
      if ( (__int128 *)v35 == &v35 )
        break;
      if ( *(__int128 **)(v35 + 8) != &v35 )
        goto LABEL_34;
      v32 = *(_QWORD *)v35;
      if ( *(_QWORD *)(*(_QWORD *)v35 + 8LL) != (_QWORD)v35 )
        goto LABEL_34;
      *(_QWORD *)&v35 = *(_QWORD *)v35;
      *(_QWORD *)(v32 + 8) = &v35;
      v33 = (IRP *)(v31 - 168);
      v33->IoStatus.Status = v14;
      IofCompleteRequest(v33, 0);
      UsbcReleaseRemoveLock(a1, v33);
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 200), v33, 0x20u);
    }
  }
  return v14;
}

```

## disassembly

```asm
0x14000159c  mov     [rsp-38h+arg_8], rbx
0x1400015a1  push    rbp
0x1400015a2  push    rsi
0x1400015a3  push    rdi
0x1400015a4  push    r12
0x1400015a6  push    r13
0x1400015a8  push    r14
0x1400015aa  push    r15
0x1400015ac  mov     rbp, rsp
0x1400015af  sub     rsp, 40h
0x1400015b3  mov     rdi, rcx
0x1400015b6  mov     [rbp+arg_0], 0
0x1400015bd  mov     ecx, 22001Fh
0x1400015c2  mov     ebx, 278h
0x1400015c7  cmp     r8d, ecx
0x1400015ca  mov     r13d, r8d
0x1400015cd  mov     r14, rdx
0x1400015d0  lea     eax, [rbx-18h]
0x1400015d3  cmovnz  ebx, eax
0x1400015d6  mov     eax, 25Ch
0x1400015db  add     rbx, rdi
0x1400015de  cmp     r8d, ecx
0x1400015e1  lea     rcx, [rdi+248h]; SpinLock
0x1400015e8  lea     r12d, [rax+14h]
0x1400015ec  cmovnz  r12d, eax
0x1400015f0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400015f7  nop     dword ptr [rax+rax+00h]
0x1400015fc  cmp     byte ptr [r12+rdi], 0
0x140001601  mov     dl, al; NewIrql
0x140001603  mov     [rbp+arg_10], al
0x140001606  jz      short loc_140001676
0x140001608  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000160f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140001616  jz      short loc_14000163F
0x140001618  mov     rcx, [rdi+558h]
0x14000161f  lea     rax, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x140001626  mov     r9d, 39h ; '9'
0x14000162c  mov     [rsp+40h+var_20], rax
0x140001631  mov     dl, 2
0x140001633  lea     r8d, [r9-31h]
0x140001637  call    WPP_RECORDER_SF_
0x14000163c  mov     dl, [rbp+arg_10]
0x14000163f  mov     rax, [r14+0B8h]
0x140001646  or      byte ptr [rax+3], 1
0x14000164a  mov     rcx, [rbx+8]
0x14000164e  cmp     [rcx], rbx
0x140001651  jnz     loc_140001887
0x140001657  lea     rax, [r14+0A8h]
0x14000165e  mov     esi, 103h
0x140001663  mov     [rax], rbx
0x140001666  xor     r15b, r15b
0x140001669  mov     [rax+8], rcx
0x14000166d  mov     [rcx], rax
0x140001670  mov     [rbx+8], rax
0x140001674  jmp     short loc_140001683
0x140001676  mov     esi, 0C0000001h
0x14000167b  mov     byte ptr [r12+rdi], 1
0x140001680  mov     r15b, 1
0x140001683  lea     rcx, [rdi+248h]; SpinLock
0x14000168a  call    cs:__imp_KeReleaseSpinLock
0x140001691  nop     dword ptr [rax+rax+00h]
0x140001696  test    r15b, r15b
0x140001699  jz      loc_14000188E
0x14000169f  mov     rax, [r14+0B8h]
0x1400016a6  xorps   xmm0, xmm0
0x1400016a9  movups  [rbp+var_10], xmm0
0x1400016ad  xor     r15d, r15d
0x1400016b0  mov     r8b, 1
0x1400016b3  movups  xmm0, xmmword ptr [rax]
0x1400016b6  movups  xmmword ptr [rax-48h], xmm0
0x1400016ba  movups  xmm1, xmmword ptr [rax+10h]
0x1400016be  movups  xmmword ptr [rax-38h], xmm1
0x1400016c2  movups  xmm0, xmmword ptr [rax+20h]
0x1400016c6  movups  xmmword ptr [rax-28h], xmm0
0x1400016ca  movsd   xmm1, qword ptr [rax+30h]
0x1400016cf  movsd   qword ptr [rax-18h], xmm1
0x1400016d4  mov     [rax-45h], r15b
0x1400016d8  cmp     [rdi+560h], r8b
0x1400016df  jnz     short loc_140001731
0x1400016e1  cmp     r13d, 220007h
0x1400016e8  jnz     short loc_140001700
0x1400016ea  mov     rax, [r14+0B8h]
0x1400016f1  lea     rcx, [rbp+arg_0]
0x1400016f5  mov     dword ptr [rax-30h], 220FB3h
0x1400016fc  mov     [rax-40h], rcx
0x140001700  mov     rcx, [rdi+80h]
0x140001707  cmp     [rcx], r15d
0x14000170a  jbe     short loc_14000172E
0x14000170c  mov     edx, r15d
0x14000170f  mov     eax, edx
0x140001711  inc     edx
0x140001713  mov     rcx, [rcx+rax*8+8]
0x140001718  mov     rax, [rcx+40h]
0x14000171c  mov     [rax+19Dh], r8b
0x140001723  mov     rcx, [rdi+80h]
0x14000172a  cmp     edx, [rcx]
0x14000172c  jb      short loc_14000170F
0x14000172e  mov     r8b, r15b
0x140001731  mov     rdx, r14
0x140001734  mov     rcx, rdi
0x140001737  call    CallNextDriverSync
0x14000173c  mov     dl, [rdi+552h]
0x140001742  mov     rcx, rdi
0x140001745  mov     esi, eax
0x140001747  call    NotifyPdosOfSurprisePowerOn
0x14000174c  lea     rax, [rbp+var_10]
0x140001750  mov     qword ptr [rbp+var_10+8], rax
0x140001754  lea     r14, [rdi+248h]
0x14000175b  lea     rax, [rbp+var_10]
0x14000175f  mov     rcx, r14; SpinLock
0x140001762  mov     qword ptr [rbp+var_10], rax
0x140001766  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000176d  nop     dword ptr [rax+rax+00h]
0x140001772  mov     [r12+rdi], r15b
0x140001776  mov     r8b, al
0x140001779  cmp     byte ptr [rdi+560h], 1
0x140001780  jnz     short loc_1400017BA
0x140001782  mov     rcx, [rdi+80h]
0x140001789  cmp     [rcx], r15d
0x14000178c  jbe     short loc_1400017BA
0x14000178e  mov     edx, r15d
0x140001791  mov     eax, edx
0x140001793  mov     rcx, [rcx+rax*8+8]
0x140001798  mov     rax, [rcx+40h]
0x14000179c  cmp     byte ptr [rax+19Eh], 1
0x1400017a3  jnz     short loc_1400017AD
0x1400017a5  mov     [rax+19Dh], r15w
0x1400017ad  mov     rcx, [rdi+80h]
0x1400017b4  inc     edx
0x1400017b6  cmp     edx, [rcx]
0x1400017b8  jb      short loc_140001791
0x1400017ba  mov     rax, [rbx]
0x1400017bd  cmp     rax, rbx
0x1400017c0  jz      short loc_140001805
0x1400017c2  cmp     [rax+8], rbx
0x1400017c6  jnz     loc_140001887
0x1400017cc  mov     rcx, [rax]
0x1400017cf  cmp     [rcx+8], rax
0x1400017d3  jnz     loc_140001887
0x1400017d9  mov     [rbx], rcx
0x1400017dc  lea     rdx, [rbp+var_10]
0x1400017e0  mov     [rcx+8], rbx
0x1400017e4  mov     rcx, qword ptr [rbp+var_10+8]
0x1400017e8  cmp     [rcx], rdx
0x1400017eb  jnz     loc_140001887
0x1400017f1  mov     [rax+8], rcx
0x1400017f5  lea     rdx, [rbp+var_10]
0x1400017f9  mov     [rax], rdx
0x1400017fc  mov     [rcx], rax
0x1400017ff  mov     qword ptr [rbp+var_10+8], rax
0x140001803  jmp     short loc_1400017BA
0x140001805  mov     dl, r8b; NewIrql
0x140001808  mov     rcx, r14; SpinLock
0x14000180b  call    cs:__imp_KeReleaseSpinLock
0x140001812  nop     dword ptr [rax+rax+00h]
0x140001817  mov     rbx, qword ptr [rbp+var_10]
0x14000181b  lea     rax, [rbp+var_10]
0x14000181f  cmp     rbx, rax
0x140001822  jz      short loc_14000188E
0x140001824  lea     rax, [rbp+var_10]
0x140001828  cmp     [rbx+8], rax
0x14000182c  jnz     short loc_140001887
0x14000182e  mov     rax, [rbx]
0x140001831  cmp     [rax+8], rbx
0x140001835  jnz     short loc_140001887
0x140001837  mov     qword ptr [rbp+var_10], rax
0x14000183b  lea     rcx, [rbp+var_10]
0x14000183f  mov     [rax+8], rcx
0x140001843  add     rbx, 0FFFFFFFFFFFFFF58h
0x14000184a  xor     edx, edx; PriorityBoost
0x14000184c  mov     rcx, rbx; Irp
0x14000184f  mov     [rbx+30h], esi
0x140001852  call    cs:__imp_IofCompleteRequest
0x140001859  nop     dword ptr [rax+rax+00h]
0x14000185e  mov     rdx, rbx
0x140001861  mov     rcx, rdi
0x140001864  call    UsbcReleaseRemoveLock
0x140001869  lea     rcx, [rdi+0C8h]; RemoveLock
0x140001870  mov     r8d, 20h ; ' '; RemlockSize
0x140001876  mov     rdx, rbx; Tag
0x140001879  call    cs:__imp_IoReleaseRemoveLockEx
0x140001880  nop     dword ptr [rax+rax+00h]
0x140001885  jmp     short loc_140001817
0x140001887  mov     ecx, 3
0x14000188c  int     29h; Win8: RtlFailFast(ecx)
0x14000188e  mov     rbx, [rsp+40h+arg_8]
0x140001896  mov     eax, esi
0x140001898  add     rsp, 40h
0x14000189c  pop     r15
0x14000189e  pop     r14
0x1400018a0  pop     r13
0x1400018a2  pop     r12
0x1400018a4  pop     rdi
0x1400018a5  pop     rsi
0x1400018a6  pop     rbp
0x1400018a7  retn
```
