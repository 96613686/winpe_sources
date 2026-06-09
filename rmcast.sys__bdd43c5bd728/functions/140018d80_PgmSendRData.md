# PgmSendRData

- ea: `0x140018d80`
- end: `0x1400192bb`
- name: `PgmSendRData`
- size: `1339`
- prototype: `__int64 __fastcall(__int64, __int64, KIRQL *, _DWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001a334`

## callees

- `0x140005038`
- `0x140005068`
- `0x140008364`
- `0x140008400`
- `0x140008998`
- `0x14000907c`
- `0x140017a30`
- `0x140018d80`
- `0x14001af84`
- `0x14001c0e8`
- `0x14001cca0`
- `0x14001cdf0`
- `0x14001d000`
- `0x14001d300`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140018dde`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140018dde`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400190cd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400190cd`
- `ntoskrnl!KeStackAttachProcess` at `0x140018f6d`
- `ntoskrnl!KeStackAttachProcess` at `0x140018f6d`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001909d`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001919a`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001909d`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001919a`
- `ntoskrnl!PsGetCurrentProcess` at `0x140018f50`
- `ntoskrnl!PsGetCurrentProcess` at `0x140018f50`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018f44`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018f44`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400190b0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001925e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400190b0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001925e`

## pseudocode

```c
__int64 __fastcall PgmSendRData(__int64 a1, __int64 a2, KIRQL *a3, _DWORD *a4)
{
  __int64 v4; // rdi
  PVOID v7; // r15
  unsigned int v9; // eax
  unsigned __int16 v10; // r14
  unsigned int v11; // r12d
  __int16 v12; // ax
  int v13; // esi
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rcx
  KIRQL *v16; // rdx
  int v17; // esi
  unsigned __int16 v18; // ax
  unsigned __int16 *v19; // rsi
  unsigned __int16 v20; // r8
  unsigned __int16 *v21; // rdx
  int v22; // ecx
  int v23; // esi
  KIRQL v24; // al
  unsigned int v25; // ebx
  __int64 v26; // r8
  KIRQL v27; // al
  unsigned __int8 v28; // [rsp+50h] [rbp-98h] BYREF
  char v29; // [rsp+51h] [rbp-97h]
  unsigned __int16 v30; // [rsp+54h] [rbp-94h] BYREF
  unsigned int v31; // [rsp+58h] [rbp-90h]
  unsigned __int16 *v32; // [rsp+60h] [rbp-88h]
  KIRQL *v33; // [rsp+68h] [rbp-80h]
  _DWORD *v34; // [rsp+70h] [rbp-78h]
  struct _KAPC_STATE ApcState; // [rsp+78h] [rbp-70h] BYREF

  v4 = *(_QWORD *)(a1 + 40);
  ApcState.ApcListHead[0] = 0;
  v34 = a4;
  v33 = a3;
  v28 = 0;
  *a4 = 0;
  memset(&ApcState.ApcListHead[1], 0, 32);
  v7 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v4 + 448));
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids);
    return 3221225626LL;
  }
  v9 = *(_DWORD *)(a2 + 16);
  v10 = *(_WORD *)(v4 + 112) + 68;
  v11 = 1;
  v30 = v10;
  v31 = v9;
  if ( *(_BYTE *)(a1 + 161) )
  {
    v12 = *(_WORD *)(a2 + 58);
    if ( v12 )
    {
      v13 = 2;
      *(_WORD *)(a2 + 58) = v12 - 1;
    }
    else
    {
      v13 = 1;
      if ( (unsigned __int8)GetNextNakIndex(a2, &v28) )
        v31 += v28;
    }
    v28 = AnyMoreNaks(a2);
    if ( !v28 )
    {
      *(_QWORD *)(a2 + 40) = *(_QWORD *)(a2 + 32) + *(_QWORD *)(v4 + 296);
      --*(_DWORD *)(v4 + 148);
      if ( !*(_QWORD *)(a2 + 32) )
        RemoveEntry(*(_QWORD *)(v4 + 264), a2);
    }
  }
  else
  {
    *(_BYTE *)(a2 + 64) = 0;
    *(_QWORD *)(a2 + 40) = *(_QWORD *)(a2 + 32) + *(_QWORD *)(v4 + 296);
    --*(_DWORD *)(v4 + 148);
    v28 = 0;
    if ( !*(_QWORD *)(a2 + 32) )
      RemoveEntry(*(_QWORD *)(v4 + 264), a2);
    v13 = 1;
  }
  v14 = *(_QWORD *)(v4 + 88);
  v15 = *(_QWORD *)(v4 + 136) + *(_DWORD *)(v4 + 108) * (v31 - *(_DWORD *)(v4 + 160)) - v14;
  if ( *(_QWORD *)(v4 + 136) + (unsigned __int64)(*(_DWORD *)(v4 + 108) * (v31 - *(_DWORD *)(v4 + 160))) < v14 )
    v15 = *(_QWORD *)(v4 + 136) + *(_DWORD *)(v4 + 108) * (v31 - *(_DWORD *)(v4 + 160));
  v16 = v33;
  v32 = (unsigned __int16 *)(v15 + *(_QWORD *)(v4 + 80));
  ++*(_WORD *)(a2 + 56);
  ++*(_DWORD *)(a1 + 20);
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 360), *v16);
  if ( (PRKPROCESS)PsGetCurrentProcess() == PgmStaticConfig )
  {
    v29 = 0;
  }
  else
  {
    KeStackAttachProcess(PgmStaticConfig, &ApcState);
    v29 = 1;
  }
  v17 = v13 - 1;
  if ( !v17 )
    goto LABEL_52;
  if ( v17 != 1 )
    goto LABEL_53;
  LOBYTE(v18) = *(_BYTE *)(a2 + 97);
  v19 = v32;
  if ( !(_BYTE)v18 )
  {
    *(_DWORD *)(a2 + 100) = 0;
    v20 = 0;
    *(_BYTE *)(a2 + 97) = 0;
    v21 = v19;
    LOBYTE(v18) = *(_BYTE *)(a1 + 160);
    if ( !(_BYTE)v18 )
      goto LABEL_32;
    do
    {
      *(_QWORD *)(a2 + 8LL * v20 + 104) = (char *)v21 + v21[1] + 56;
      v22 = *(_DWORD *)(a2 + 100) | *((_DWORD *)v21 + 1) & 0x861;
      *(_DWORD *)(a2 + 100) = v22;
      if ( _bittest((const signed __int32 *)v21 + 1, 0xBu) )
        *(_BYTE *)(a2 + 97) = *((_BYTE *)v21 + 29);
      ++v20;
      v21 = (unsigned __int16 *)((char *)v21 + *(unsigned int *)(v4 + 108));
      v18 = *(unsigned __int8 *)(a1 + 160);
    }
    while ( v20 < v18 );
    if ( (v22 & 0x800) != 0 )
      LOBYTE(v18) = *(_BYTE *)(a2 + 97);
    else
LABEL_32:
      *(_BYTE *)(a2 + 97) = v18;
  }
  if ( (_BYTE)v18 == 1 )
  {
    if ( v28 )
    {
      v11 = *(unsigned __int16 *)(a2 + 58) + 1;
      *(_WORD *)(a2 + 58) = 0;
      while ( (unsigned __int8)GetNextNakIndex(a2, &v28) )
        ++v11;
      *(_QWORD *)(a2 + 40) = *(_QWORD *)(a2 + 32) + *(_QWORD *)(v4 + 296);
      --*(_DWORD *)(v4 + 148);
      if ( !*(_QWORD *)(a2 + 32) )
        RemoveEntry(*(_QWORD *)(v4 + 264), a2);
    }
LABEL_52:
    v10 = *v32;
    memmove(v7, v32 + 16, *v32);
    goto LABEL_53;
  }
  memset(v7, 0, v10);
  v23 = PgmBuildParityPacket(a1, (_DWORD)v19, (int)a2 + 96, (_DWORD)v7, (__int64)&v30, 5);
  if ( v23 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        41,
        WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids,
        (unsigned int)v23);
    if ( v29 )
      KeUnstackDetachProcess(&ApcState);
    v24 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 360));
    *v33 = v24;
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v4 + 448), v7);
    if ( v28 || *(_QWORD *)(a2 + 32) )
    {
      --*(_WORD *)(a2 + 56);
      ++*(_WORD *)(a2 + 58);
      ++*(_DWORD *)(v4 + 148);
    }
    else
    {
      DestroyEntry(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 264LL), a2);
    }
    return (unsigned int)v23;
  }
  v10 = v30;
LABEL_53:
  if ( v29 )
    KeUnstackDetachProcess(&ApcState);
  *((_DWORD *)v7 + 5) = _byteswap_ulong(*(_DWORD *)(v4 + 164));
  *((_WORD *)v7 + 3) = 0;
  *((_BYTE *)v7 + 4) = 5;
  *((_WORD *)v7 + 3) = ~(unsigned __int16)tcpxsum(0, v7, v10);
  v25 = TdiSendDatagram(
          *(struct _FILE_OBJECT **)(*(_QWORD *)(v4 + 32) + 96LL),
          *(struct _DEVICE_OBJECT **)(*(_QWORD *)(v4 + 32) + 104LL),
          v7,
          v10,
          (void (__fastcall *)(__int64, __int64, __int64))&PgmSendRDataCompletion,
          a2,
          (__int64)v7,
          *(_DWORD *)(v4 + 40),
          *(_WORD *)(v4 + 48),
          0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_ddDd(
      WPP_GLOBAL_Control->AttachedDevice,
      *(unsigned int *)(v4 + 40),
      v26,
      v31,
      v10,
      *(_DWORD *)(v4 + 40),
      *(unsigned __int16 *)(v4 + 48));
  v27 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 360));
  *v33 = v27;
  *(_QWORD *)(v4 + 872) -= v11;
  ++*(_QWORD *)(v4 + 896);
  ++*(_QWORD *)(v4 + 848);
  *v34 = v10;
  return v25;
}

```

## disassembly

```asm
0x140018d80  mov     r11, rsp
0x140018d83  push    rbx
0x140018d84  push    rsi
0x140018d85  push    rdi
0x140018d86  push    r12
0x140018d88  push    r13
0x140018d8a  push    r14
0x140018d8c  push    r15
0x140018d8e  sub     rsp, 0B0h
0x140018d95  mov     rax, cs:__security_cookie
0x140018d9c  xor     rax, rsp
0x140018d9f  mov     [rsp+0E8h+var_40], rax
0x140018da7  mov     rdi, [rcx+28h]
0x140018dab  xorps   xmm0, xmm0
0x140018dae  movups  xmmword ptr [rsp+0E8h+ApcState.ApcListHead.Flink], xmm0
0x140018db3  mov     r13, rcx
0x140018db6  mov     [rsp+0E8h+var_78], r9
0x140018dbb  xor     esi, esi
0x140018dbd  mov     [rsp+0E8h+var_80], r8
0x140018dc2  lea     rcx, [rdi+1C0h]; Lookaside
0x140018dc9  mov     [rsp+0E8h+var_98], sil
0x140018dce  mov     rbx, rdx
0x140018dd1  mov     [r9], esi
0x140018dd4  movups  xmmword ptr [r11-60h], xmm0
0x140018dd9  movups  xmmword ptr [r11-50h], xmm0
0x140018dde  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140018de5  nop     dword ptr [rax+rax+00h]
0x140018dea  mov     r15, rax
0x140018ded  test    rax, rax
0x140018df0  jnz     short loc_140018E29
0x140018df2  mov     rcx, cs:WPP_GLOBAL_Control
0x140018df9  lea     rax, WPP_GLOBAL_Control
0x140018e00  cmp     rcx, rax
0x140018e03  jz      short loc_140018E1F
0x140018e05  mov     eax, [rcx+2Ch]
0x140018e08  test    al, 2
0x140018e0a  jz      short loc_140018E1F
0x140018e0c  mov     rcx, [rcx+18h]
0x140018e10  lea     edx, [rsi+28h]
0x140018e13  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x140018e1a  call    WPP_SF_
0x140018e1f  mov     eax, 0C000009Ah
0x140018e24  jmp     loc_140019297
0x140018e29  movzx   r14d, word ptr [rdi+70h]
0x140018e2e  mov     ecx, 1
0x140018e33  mov     eax, [rbx+10h]
0x140018e36  add     r14w, 44h ; 'D'
0x140018e3b  mov     r12d, ecx
0x140018e3e  mov     [rsp+0E8h+var_94], r14w
0x140018e44  mov     [rsp+0E8h+var_90], eax
0x140018e48  cmp     [r13+0A1h], sil
0x140018e4f  jz      short loc_140018EBF
0x140018e51  movzx   eax, word ptr [rbx+3Ah]
0x140018e55  test    ax, ax
0x140018e58  jz      short loc_140018E66
0x140018e5a  sub     ax, cx
0x140018e5d  lea     esi, [rcx+1]
0x140018e60  mov     [rbx+3Ah], ax
0x140018e64  jmp     short loc_140018E82
0x140018e66  mov     esi, ecx
0x140018e68  lea     rdx, [rsp+0E8h+var_98]
0x140018e6d  mov     rcx, rbx
0x140018e70  call    GetNextNakIndex
0x140018e75  test    al, al
0x140018e77  jz      short loc_140018E82
0x140018e79  movzx   eax, [rsp+0E8h+var_98]
0x140018e7e  add     [rsp+0E8h+var_90], eax
0x140018e82  mov     rcx, rbx
0x140018e85  call    AnyMoreNaks
0x140018e8a  mov     [rsp+0E8h+var_98], al
0x140018e8e  test    al, al
0x140018e90  jnz     short loc_140018EF9
0x140018e92  mov     rcx, [rdi+128h]
0x140018e99  add     rcx, [rbx+20h]
0x140018e9d  mov     [rbx+28h], rcx
0x140018ea1  dec     dword ptr [rdi+94h]
0x140018ea7  cmp     qword ptr [rbx+20h], 0
0x140018eac  jnz     short loc_140018EF9
0x140018eae  mov     rcx, [rdi+108h]
0x140018eb5  mov     rdx, rbx
0x140018eb8  call    RemoveEntry
0x140018ebd  jmp     short loc_140018EF9
0x140018ebf  mov     [rbx+40h], sil
0x140018ec3  mov     rax, [rdi+128h]
0x140018eca  add     rax, [rbx+20h]
0x140018ece  mov     [rbx+28h], rax
0x140018ed2  dec     dword ptr [rdi+94h]
0x140018ed8  mov     [rsp+0E8h+var_98], sil
0x140018edd  cmp     [rbx+20h], rsi
0x140018ee1  jnz     short loc_140018EF7
0x140018ee3  mov     rcx, [rdi+108h]
0x140018eea  mov     rdx, rbx
0x140018eed  call    RemoveEntry
0x140018ef2  mov     esi, r12d
0x140018ef5  jmp     short loc_140018EF9
0x140018ef7  mov     esi, ecx
0x140018ef9  mov     rax, [rdi+58h]
0x140018efd  mov     edx, [rsp+0E8h+var_90]
0x140018f01  sub     edx, [rdi+0A0h]
0x140018f07  imul    edx, [rdi+6Ch]
0x140018f0b  add     rdx, [rdi+88h]
0x140018f12  mov     rcx, rdx
0x140018f15  sub     rcx, rax
0x140018f18  cmp     rdx, rax
0x140018f1b  mov     rax, [rdi+50h]
0x140018f1f  cmovb   rcx, rdx
0x140018f23  mov     rdx, [rsp+0E8h+var_80]
0x140018f28  add     rax, rcx
0x140018f2b  lea     rcx, [r13+168h]; SpinLock
0x140018f32  mov     [rsp+0E8h+var_88], rax
0x140018f37  mov     rax, r12
0x140018f3a  add     [rbx+38h], ax
0x140018f3e  add     [r13+14h], eax
0x140018f42  mov     dl, [rdx]; NewIrql
0x140018f44  call    cs:__imp_KeReleaseSpinLock
0x140018f4b  nop     dword ptr [rax+rax+00h]
0x140018f50  call    cs:__imp_PsGetCurrentProcess
0x140018f57  nop     dword ptr [rax+rax+00h]
0x140018f5c  mov     rcx, cs:PgmStaticConfig; PROCESS
0x140018f63  cmp     rax, rcx
0x140018f66  jz      short loc_140018F83
0x140018f68  lea     rdx, [rsp+0E8h+ApcState]; ApcState
0x140018f6d  call    cs:__imp_KeStackAttachProcess
0x140018f74  nop     dword ptr [rax+rax+00h]
0x140018f79  mov     r9, r12
0x140018f7c  mov     [rsp+0E8h+var_97], r9b
0x140018f81  jmp     short loc_140018F8B
0x140018f83  mov     [rsp+0E8h+var_97], 0
0x140018f88  mov     r9, r12
0x140018f8b  sub     esi, r12d
0x140018f8e  jz      loc_140019176
0x140018f94  cmp     esi, r12d
0x140018f97  jnz     loc_14001918E
0x140018f9d  mov     al, [rbx+61h]
0x140018fa0  mov     rsi, [rsp+0E8h+var_88]
0x140018fa5  test    al, al
0x140018fa7  jnz     short loc_14001901A
0x140018fa9  mov     dword ptr [rbx+64h], 0
0x140018fb0  xor     r8d, r8d
0x140018fb3  mov     [rbx+61h], al
0x140018fb6  mov     rdx, rsi
0x140018fb9  mov     al, [r13+0A0h]
0x140018fc0  test    al, al
0x140018fc2  jz      short loc_140019017
0x140018fc4  movzx   ecx, word ptr [rdx+2]
0x140018fc8  add     rcx, 38h ; '8'
0x140018fcc  movzx   eax, r8w
0x140018fd0  add     rcx, rdx
0x140018fd3  mov     [rbx+rax*8+68h], rcx
0x140018fd8  mov     ecx, [rdx+4]
0x140018fdb  and     ecx, 861h
0x140018fe1  or      ecx, [rbx+64h]
0x140018fe4  mov     [rbx+64h], ecx
0x140018fe7  bt      dword ptr [rdx+4], 0Bh
0x140018fec  jnb     short loc_140018FF4
0x140018fee  mov     al, [rdx+1Dh]
0x140018ff1  mov     [rbx+61h], al
0x140018ff4  mov     eax, [rdi+6Ch]
0x140018ff7  add     r8w, r9w
0x140018ffb  add     rdx, rax
0x140018ffe  movzx   eax, byte ptr [r13+0A0h]
0x140019006  cmp     r8w, ax
0x14001900a  jb      short loc_140018FC4
0x14001900c  bt      ecx, 0Bh
0x140019010  jnb     short loc_140019017
0x140019012  mov     al, [rbx+61h]
0x140019015  jmp     short loc_14001901A
0x140019017  mov     [rbx+61h], al
0x14001901a  cmp     al, r9b
0x14001901d  jz      loc_140019120
0x140019023  movzx   r8d, r14w; Size
0x140019027  xor     edx, edx; Val
0x140019029  mov     rcx, r15; void *
0x14001902c  call    memset
0x140019031  lea     rax, [rsp+0E8h+var_94]
0x140019036  mov     byte ptr [rsp+0E8h+var_C0], 5
0x14001903b  lea     r8, [rbx+60h]
0x14001903f  mov     [rsp+0E8h+var_C8], rax
0x140019044  mov     r9, r15
0x140019047  mov     rdx, rsi
0x14001904a  mov     rcx, r13
0x14001904d  call    PgmBuildParityPacket
0x140019052  xor     r14d, r14d
0x140019055  mov     esi, eax
0x140019057  test    eax, eax
0x140019059  jns     loc_140019118
0x14001905f  mov     rcx, cs:WPP_GLOBAL_Control
0x140019066  lea     rax, WPP_GLOBAL_Control
0x14001906d  cmp     rcx, rax
0x140019070  jz      short loc_140019091
0x140019072  mov     edx, [rcx+2Ch]
0x140019075  test    dl, 2
0x140019078  jz      short loc_140019091
0x14001907a  mov     rcx, [rcx+18h]
0x14001907e  lea     edx, [r14+29h]
0x140019082  mov     r9d, esi
0x140019085  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x14001908c  call    WPP_SF_d
0x140019091  cmp     [rsp+0E8h+var_97], r14b
0x140019096  jz      short loc_1400190A9
0x140019098  lea     rcx, [rsp+0E8h+ApcState]; ApcState
0x14001909d  call    cs:__imp_KeUnstackDetachProcess
0x1400190a4  nop     dword ptr [rax+rax+00h]
0x1400190a9  lea     rcx, [r13+168h]; SpinLock
0x1400190b0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400190b7  nop     dword ptr [rax+rax+00h]
0x1400190bc  mov     rcx, [rsp+0E8h+var_80]
0x1400190c1  mov     rdx, r15; Entry
0x1400190c4  mov     [rcx], al
0x1400190c6  lea     rcx, [rdi+1C0h]; Lookaside
0x1400190cd  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400190d4  nop     dword ptr [rax+rax+00h]
0x1400190d9  cmp     [rsp+0E8h+var_98], r14b
0x1400190de  jnz     short loc_1400190FB
0x1400190e0  cmp     [rbx+20h], r14
0x1400190e4  jnz     short loc_1400190FB
0x1400190e6  mov     rcx, [r13+28h]
0x1400190ea  mov     rdx, rbx
0x1400190ed  mov     rcx, [rcx+108h]
0x1400190f4  call    DestroyEntry
0x1400190f9  jmp     short loc_140019111
0x1400190fb  mov     eax, 0FFFFh
0x140019100  add     [rbx+38h], ax
0x140019104  mov     rax, r12
0x140019107  add     [rbx+3Ah], ax
0x14001910b  add     [rdi+94h], eax
0x140019111  mov     eax, esi
0x140019113  jmp     loc_140019297
0x140019118  movzx   r14d, [rsp+0E8h+var_94]
0x14001911e  jmp     short loc_14001918E
0x140019120  cmp     [rsp+0E8h+var_98], 0
0x140019125  jz      short loc_140019176
0x140019127  movzx   r12d, word ptr [rbx+3Ah]
0x14001912c  add     r12d, r9d
0x14001912f  xor     eax, eax
0x140019131  mov     [rbx+3Ah], ax
0x140019135  jmp     short loc_14001913A
0x140019137  inc     r12d
0x14001913a  lea     rdx, [rsp+0E8h+var_98]
0x14001913f  mov     rcx, rbx
0x140019142  call    GetNextNakIndex
0x140019147  test    al, al
0x140019149  jnz     short loc_140019137
0x14001914b  mov     rax, [rdi+128h]
0x140019152  add     rax, [rbx+20h]
0x140019156  mov     [rbx+28h], rax
0x14001915a  dec     dword ptr [rdi+94h]
0x140019160  cmp     qword ptr [rbx+20h], 0
0x140019165  jnz     short loc_140019176
0x140019167  mov     rcx, [rdi+108h]
0x14001916e  mov     rdx, rbx
0x140019171  call    RemoveEntry
0x140019176  mov     rax, [rsp+0E8h+var_88]
0x14001917b  mov     rcx, r15; void *
0x14001917e  movzx   r14d, word ptr [rax]
0x140019182  lea     rdx, [rax+20h]; Src
0x140019186  mov     r8d, r14d; Size
0x140019189  call    memmove
0x14001918e  cmp     [rsp+0E8h+var_97], 0
0x140019193  jz      short loc_1400191A6
0x140019195  lea     rcx, [rsp+0E8h+ApcState]; ApcState
0x14001919a  call    cs:__imp_KeUnstackDetachProcess
0x1400191a1  nop     dword ptr [rax+rax+00h]
0x1400191a6  mov     eax, [rdi+0A4h]
0x1400191ac  mov     rdx, r15
0x1400191af  bswap   eax
0x1400191b1  mov     [r15+14h], eax
0x1400191b5  xor     ecx, ecx
0x1400191b7  xor     eax, eax
0x1400191b9  movzx   esi, r14w
0x1400191bd  mov     r8d, esi
0x1400191c0  mov     [r15+6], ax
0x1400191c5  mov     byte ptr [r15+4], 5
0x1400191ca  call    tcpxsum
0x1400191cf  not     ax
0x1400191d2  mov     [rsp+0E8h+var_A0], 0
0x1400191d7  mov     [r15+6], ax
0x1400191dc  mov     r9d, esi
0x1400191df  movzx   eax, word ptr [rdi+30h]
0x1400191e3  mov     r8, r15
0x1400191e6  mov     rcx, [rdi+20h]
0x1400191ea  mov     [rsp+0E8h+var_A8], ax
0x1400191ef  mov     eax, [rdi+28h]
0x1400191f2  mov     [rsp+0E8h+var_B0], eax
0x1400191f6  lea     rax, PgmSendRDataCompletion
0x1400191fd  mov     rdx, [rcx+68h]
0x140019201  mov     rcx, [rcx+60h]
0x140019205  mov     [rsp+0E8h+var_B8], r15
0x14001920a  mov     [rsp+0E8h+var_C0], rbx
0x14001920f  mov     [rsp+0E8h+var_C8], rax
0x140019214  call    TdiSendDatagram
0x140019219  mov     ebx, eax
0x14001921b  mov     rcx, cs:WPP_GLOBAL_Control
0x140019222  lea     rax, WPP_GLOBAL_Control
0x140019229  cmp     rcx, rax
0x14001922c  jz      short loc_140019257
0x14001922e  mov     edx, [rcx+2Ch]
0x140019231  test    dl, 10h
0x140019234  jz      short loc_140019257
0x140019236  movzx   edx, word ptr [rdi+30h]
  ... truncated ...
```
