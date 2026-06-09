# PgmSendNextOData

- ea: `0x1400185a4`
- end: `0x140018afa`
- name: `PgmSendNextOData`
- size: `1366`
- prototype: `__int64 __fastcall(__int64, KIRQL *, _DWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001a334`

## callees

- `0x140005038`
- `0x140005068`
- `0x140016a74`
- `0x140017a30`
- `0x1400185a4`
- `0x14001aff4`
- `0x14001c0e8`
- `0x14001cca0`
- `0x14001cdf0`
- `0x14001d300`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400186e9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400186e9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140018833`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140018833`
- `ntoskrnl!KeStackAttachProcess` at `0x140018780`
- `ntoskrnl!KeStackAttachProcess` at `0x140018780`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400187d0`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400187d0`
- `ntoskrnl!PsGetCurrentProcess` at `0x140018763`
- `ntoskrnl!PsGetCurrentProcess` at `0x140018763`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018757`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400189de`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018757`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400189de`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400187e3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018aba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400187e3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018aba`

## pseudocode

```c
__int64 __fastcall PgmSendNextOData(__int64 a1, KIRQL *a2, _DWORD *a3)
{
  __int64 v3; // rdi
  char v4; // r14
  unsigned int v6; // ecx
  KIRQL *v7; // r13
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rbx
  __int64 v12; // rax
  _QWORD *v13; // rdx
  __int64 *v14; // rax
  int v15; // edx
  PVOID v16; // rax
  __int64 v17; // r15
  KIRQL v18; // dl
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  int v23; // r13d
  KIRQL v24; // al
  KIRQL *v25; // rcx
  int NextPacketOptionsAndData; // eax
  __int64 v27; // rax
  _QWORD *v28; // rcx
  __int64 *v29; // rcx
  __int64 v30; // rax
  __int16 v31; // ax
  unsigned int v32; // ebx
  KIRQL v33; // al
  _DWORD *v34; // rcx
  unsigned __int16 v35; // [rsp+50h] [rbp-98h] BYREF
  _DWORD *v36; // [rsp+58h] [rbp-90h] BYREF
  KIRQL *v37; // [rsp+60h] [rbp-88h]
  _DWORD *v38; // [rsp+68h] [rbp-80h]
  struct _KAPC_STATE ApcState; // [rsp+70h] [rbp-78h] BYREF

  v3 = *(_QWORD *)(a1 + 40);
  v4 = 0;
  *a3 = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  v35 = 0;
  v6 = *(unsigned __int8 *)(a1 + 160);
  v7 = a2;
  v36 = 0;
  v8 = *(_QWORD *)(a1 + 40);
  v38 = a3;
  v37 = a2;
  if ( *(_DWORD *)(v8 + 116) < v6 )
    return 0;
  v9 = v3 + 232;
  v10 = *(_QWORD *)(v3 + 232);
  if ( v10 == v3 + 232 )
  {
    v10 = *(_QWORD *)(v3 + 248);
    if ( v10 == v3 + 248 )
      return 3221225473LL;
    v12 = *(_QWORD *)v10;
    if ( *(_QWORD *)(*(_QWORD *)v10 + 8LL) != v10 )
      goto LABEL_51;
    v13 = *(_QWORD **)(v10 + 8);
    if ( *v13 != v10 )
      goto LABEL_51;
    *v13 = v12;
    *(_QWORD *)(v12 + 8) = v13;
    v14 = *(__int64 **)(v3 + 240);
    if ( *v14 != v9 )
      goto LABEL_51;
    *(_QWORD *)v10 = v9;
    *(_QWORD *)(v10 + 8) = v14;
    *v14 = v10;
    *(_QWORD *)(v3 + 240) = v10;
    *(_QWORD *)(v10 + 120) = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 128LL);
    v15 = *(_DWORD *)(*(_QWORD *)(a1 + 40) + 152LL);
    *(_DWORD *)(v10 + 88) = v15;
    *(_DWORD *)(v10 + 92) = *(_DWORD *)(*(_QWORD *)(a1 + 40) + 152LL);
    if ( *(_DWORD *)(v10 + 72) )
    {
      *(_DWORD *)(v10 + 96) = *(_DWORD *)(*(_QWORD *)(a1 + 40) + 168LL);
    }
    else
    {
      *(_DWORD *)(v10 + 96) = v15;
      *(_DWORD *)(*(_QWORD *)(a1 + 40) + 168LL) = v15;
    }
  }
  if ( *(_DWORD *)(v10 + 140) )
  {
    v35 = *(_WORD *)(v3 + 108);
    v16 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v3 + 448));
    v17 = (__int64)v16;
    if ( !v16 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids);
      return 3221225626LL;
    }
    memset(v16, 0, *(unsigned int *)(v3 + 108));
    v18 = *v7;
    v36 = (_DWORD *)(v17 + 32);
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 360), v18);
    if ( (PRKPROCESS)PsGetCurrentProcess(v20, v19, v21, v22) != PgmStaticConfig )
    {
      KeStackAttachProcess(PgmStaticConfig, &ApcState);
      v4 = 1;
    }
    v35 -= 32;
    v23 = PgmBuildParityPacket(a1, *(_QWORD *)(v3 + 272), *(unsigned __int8 **)(v3 + 424), (__int64)v36, &v35, 4u);
    if ( v4 )
      KeUnstackDetachProcess(&ApcState);
    v24 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 360));
    v25 = v37;
    *v37 = v24;
    if ( v23 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          61,
          WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids,
          (unsigned int)v23);
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v3 + 448), (PVOID)v17);
      return 0;
    }
    --*(_DWORD *)(v10 + 140);
    v7 = v25;
  }
  else
  {
    if ( !*(_DWORD *)(v10 + 128) )
    {
      *(_QWORD *)(v10 + 48) = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 296LL);
      if ( *(_BYTE *)(a1 + 161) )
        *(_DWORD *)(v3 + 156) = *(_DWORD *)(v3 + 152) - 1;
    }
    NextPacketOptionsAndData = GetNextPacketOptionsAndData(a1, v10, &v36, v7, (__int64)&v35);
    if ( NextPacketOptionsAndData < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          62,
          WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids,
          (unsigned int)NextPacketOptionsAndData);
      return 0;
    }
    ++*(_DWORD *)(v10 + 128);
    v17 = 0;
  }
  if ( *(_DWORD *)(v10 + 128) == *(_DWORD *)(v10 + 108) && !*(_DWORD *)(v10 + 140) && !*(_DWORD *)(v10 + 104) )
  {
    v27 = *(_QWORD *)v10;
    if ( *(_QWORD *)(*(_QWORD *)v10 + 8LL) == v10 )
    {
      v28 = *(_QWORD **)(v10 + 8);
      if ( *v28 == v10 )
      {
        *v28 = v27;
        *(_QWORD *)(v27 + 8) = v28;
        v29 = *(__int64 **)(v3 + 224);
        if ( *v29 == v3 + 216 )
        {
          *(_QWORD *)v10 = v3 + 216;
          *(_QWORD *)(v10 + 8) = v29;
          *v29 = v10;
          *(_QWORD *)(v3 + 224) = v10;
          --*(_DWORD *)(v3 + 144);
          if ( (*(_DWORD *)(v10 + 60) & 0x40) != 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids);
            }
            v30 = *(_QWORD *)(v3 + 376);
            *(_DWORD *)(v3 + 196) |= 0x40u;
            *(_QWORD *)(v3 + 368) = v30;
            *(_DWORD *)(a1 + 32) |= 4u;
          }
          goto LABEL_47;
        }
      }
    }
LABEL_51:
    __fastfail(3u);
  }
LABEL_47:
  ++*(_DWORD *)(v10 + 136);
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 360), *v7);
  v36[5] = _byteswap_ulong(*(_DWORD *)(v3 + 164));
  *((_WORD *)v36 + 3) = 0;
  v31 = tcpxsum(0, v36, v35);
  *((_WORD *)v36 + 3) = ~v31;
  v32 = TdiSendDatagram(
          *(struct _FILE_OBJECT **)(*(_QWORD *)(v3 + 32) + 72LL),
          *(struct _DEVICE_OBJECT **)(*(_QWORD *)(v3 + 32) + 80LL),
          v36,
          v35,
          (void (__fastcall *)(__int64, __int64, __int64))&PgmSendODataCompletion,
          v10,
          v17,
          *(_DWORD *)(v3 + 40),
          *(_WORD *)(v3 + 48),
          v17 == 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_dddDd(
      WPP_GLOBAL_Control->AttachedDevice,
      *(unsigned int *)(v3 + 40),
      v35,
      *(unsigned int *)(v3 + 164),
      *(_DWORD *)(v3 + 156),
      v35,
      *(_DWORD *)(v3 + 40),
      *(unsigned __int16 *)(v3 + 48));
  v33 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 360));
  v34 = v38;
  *v7 = v33;
  ++*(_QWORD *)(*(_QWORD *)(a1 + 40) + 888LL);
  ++*(_QWORD *)(*(_QWORD *)(a1 + 40) + 840LL);
  *v34 = v35;
  return v32;
}

```

## disassembly

```asm
0x1400185a4  mov     r11, rsp
0x1400185a7  push    rbx
0x1400185a8  push    rsi
0x1400185a9  push    rdi
0x1400185aa  push    r12
0x1400185ac  push    r13
0x1400185ae  push    r14
0x1400185b0  push    r15
0x1400185b2  sub     rsp, 0B0h
0x1400185b9  mov     rax, cs:__security_cookie
0x1400185c0  xor     rax, rsp
0x1400185c3  mov     [rsp+0E8h+var_48], rax
0x1400185cb  mov     rdi, [rcx+28h]
0x1400185cf  xor     r14d, r14d
0x1400185d2  mov     [r8], r14d
0x1400185d5  xorps   xmm0, xmm0
0x1400185d8  movups  xmmword ptr [rsp+0E8h+ApcState.ApcListHead.Flink], xmm0
0x1400185dd  mov     rsi, rcx
0x1400185e0  mov     [rsp+0E8h+var_98], r14w
0x1400185e6  movzx   ecx, byte ptr [rcx+0A0h]
0x1400185ed  mov     r13, rdx
0x1400185f0  movups  xmmword ptr [r11-68h], xmm0
0x1400185f5  mov     [rsp+0E8h+var_90], r14
0x1400185fa  mov     rax, [rsi+28h]
0x1400185fe  movups  xmmword ptr [r11-58h], xmm0
0x140018603  mov     [rsp+0E8h+var_80], r8
0x140018608  mov     [rsp+0E8h+var_88], rdx
0x14001860d  cmp     [rax+74h], ecx
0x140018610  jb      loc_14001883F
0x140018616  lea     rcx, [rdi+0E8h]
0x14001861d  mov     rbx, [rcx]
0x140018620  cmp     rbx, rcx
0x140018623  jnz     loc_1400186C9
0x140018629  lea     rax, [rdi+0F8h]
0x140018630  mov     rbx, [rax]
0x140018633  cmp     rbx, rax
0x140018636  jnz     short loc_140018642
0x140018638  mov     eax, 0C0000001h
0x14001863d  jmp     loc_140018841
0x140018642  mov     rax, [rbx]
0x140018645  cmp     [rax+8], rbx
0x140018649  jnz     loc_140018AF3
0x14001864f  mov     rdx, [rbx+8]
0x140018653  cmp     [rdx], rbx
0x140018656  jnz     loc_140018AF3
0x14001865c  mov     [rdx], rax
0x14001865f  mov     [rax+8], rdx
0x140018663  mov     rax, [rcx+8]
0x140018667  cmp     [rax], rcx
0x14001866a  jnz     loc_140018AF3
0x140018670  mov     [rbx], rcx
0x140018673  mov     [rbx+8], rax
0x140018677  mov     [rax], rbx
0x14001867a  mov     [rcx+8], rbx
0x14001867e  mov     rax, [rsi+28h]
0x140018682  mov     rcx, [rax+80h]
0x140018689  mov     [rbx+78h], rcx
0x14001868d  mov     rax, [rsi+28h]
0x140018691  mov     edx, [rax+98h]
0x140018697  mov     [rbx+58h], edx
0x14001869a  mov     rax, [rsi+28h]
0x14001869e  mov     ecx, [rax+98h]
0x1400186a4  mov     [rbx+5Ch], ecx
0x1400186a7  cmp     [rbx+48h], r14d
0x1400186ab  jz      short loc_1400186BC
0x1400186ad  mov     rax, [rsi+28h]
0x1400186b1  mov     ecx, [rax+0A8h]
0x1400186b7  mov     [rbx+60h], ecx
0x1400186ba  jmp     short loc_1400186C9
0x1400186bc  mov     [rbx+60h], edx
0x1400186bf  mov     rax, [rsi+28h]
0x1400186c3  mov     [rax+0A8h], edx
0x1400186c9  cmp     [rbx+8Ch], r14d
0x1400186d0  jz      loc_140018873
0x1400186d6  movzx   eax, word ptr [rdi+6Ch]
0x1400186da  lea     r12, [rdi+1C0h]
0x1400186e1  mov     rcx, r12; Lookaside
0x1400186e4  mov     [rsp+0E8h+var_98], ax
0x1400186e9  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400186f0  nop     dword ptr [rax+rax+00h]
0x1400186f5  mov     r15, rax
0x1400186f8  test    rax, rax
0x1400186fb  jnz     short loc_140018735
0x1400186fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140018704  lea     r14, WPP_GLOBAL_Control
0x14001870b  cmp     rcx, r14
0x14001870e  jz      short loc_14001872B
0x140018710  mov     eax, [rcx+2Ch]
0x140018713  test    al, 2
0x140018715  jz      short loc_14001872B
0x140018717  mov     rcx, [rcx+18h]
0x14001871b  lea     edx, [r15+3Ch]
0x14001871f  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x140018726  call    WPP_SF_
0x14001872b  mov     eax, 0C000009Ah
0x140018730  jmp     loc_140018841
0x140018735  mov     r8d, [rdi+6Ch]; Size
0x140018739  xor     edx, edx; Val
0x14001873b  mov     rcx, r15; void *
0x14001873e  call    memset
0x140018743  mov     dl, [r13+0]; NewIrql
0x140018747  lea     rax, [r15+20h]
0x14001874b  lea     rcx, [rsi+168h]; SpinLock
0x140018752  mov     [rsp+0E8h+var_90], rax
0x140018757  call    cs:__imp_KeReleaseSpinLock
0x14001875e  nop     dword ptr [rax+rax+00h]
0x140018763  call    cs:__imp_PsGetCurrentProcess
0x14001876a  nop     dword ptr [rax+rax+00h]
0x14001876f  mov     rcx, cs:PgmStaticConfig; PROCESS
0x140018776  cmp     rax, rcx
0x140018779  jz      short loc_14001878F
0x14001877b  lea     rdx, [rsp+0E8h+ApcState]; ApcState
0x140018780  call    cs:__imp_KeStackAttachProcess
0x140018787  nop     dword ptr [rax+rax+00h]
0x14001878c  mov     r14b, 1
0x14001878f  mov     r9, [rsp+0E8h+var_90]
0x140018794  mov     eax, 0FFE0h
0x140018799  add     [rsp+0E8h+var_98], ax
0x14001879e  mov     rcx, rsi
0x1400187a1  mov     r8, [rdi+1A8h]
0x1400187a8  lea     rax, [rsp+0E8h+var_98]
0x1400187ad  mov     rdx, [rdi+110h]
0x1400187b4  mov     byte ptr [rsp+0E8h+var_C0], 4
0x1400187b9  mov     [rsp+0E8h+var_C8], rax
0x1400187be  call    PgmBuildParityPacket
0x1400187c3  mov     r13d, eax
0x1400187c6  test    r14b, r14b
0x1400187c9  jz      short loc_1400187DC
0x1400187cb  lea     rcx, [rsp+0E8h+ApcState]; ApcState
0x1400187d0  call    cs:__imp_KeUnstackDetachProcess
0x1400187d7  nop     dword ptr [rax+rax+00h]
0x1400187dc  lea     rcx, [rsi+168h]; SpinLock
0x1400187e3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400187ea  nop     dword ptr [rax+rax+00h]
0x1400187ef  mov     rcx, [rsp+0E8h+var_88]
0x1400187f4  mov     [rcx], al
0x1400187f6  test    r13d, r13d
0x1400187f9  jns     short loc_140018865
0x1400187fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140018802  lea     r14, WPP_GLOBAL_Control
0x140018809  cmp     rcx, r14
0x14001880c  jz      short loc_14001882D
0x14001880e  mov     eax, [rcx+2Ch]
0x140018811  test    al, 2
0x140018813  jz      short loc_14001882D
0x140018815  mov     rcx, [rcx+18h]
0x140018819  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x140018820  mov     edx, 3Dh ; '='
0x140018825  mov     r9d, r13d
0x140018828  call    WPP_SF_d
0x14001882d  mov     rdx, r15; Entry
0x140018830  mov     rcx, r12; Lookaside
0x140018833  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001883a  nop     dword ptr [rax+rax+00h]
0x14001883f  xor     eax, eax
0x140018841  mov     rcx, [rsp+0E8h+var_48]
0x140018849  xor     rcx, rsp; StackCookie
0x14001884c  call    __security_check_cookie
0x140018851  add     rsp, 0B0h
0x140018858  pop     r15
0x14001885a  pop     r14
0x14001885c  pop     r13
0x14001885e  pop     r12
0x140018860  pop     rdi
0x140018861  pop     rsi
0x140018862  pop     rbx
0x140018863  retn
0x140018865  dec     dword ptr [rbx+8Ch]
0x14001886b  mov     r13, rcx
0x14001886e  jmp     loc_14001890C
0x140018873  cmp     [rbx+80h], r14d
0x14001887a  jnz     short loc_1400188A2
0x14001887c  mov     rax, [rsi+28h]
0x140018880  mov     rcx, [rax+128h]
0x140018887  mov     [rbx+30h], rcx
0x14001888b  cmp     [rsi+0A1h], r14b
0x140018892  jz      short loc_1400188A2
0x140018894  mov     eax, [rdi+98h]
0x14001889a  dec     eax
0x14001889c  mov     [rdi+9Ch], eax
0x1400188a2  lea     rax, [rsp+0E8h+var_98]
0x1400188a7  mov     r9, r13
0x1400188aa  lea     r8, [rsp+0E8h+var_90]
0x1400188af  mov     [rsp+0E8h+var_C8], rax
0x1400188b4  mov     rdx, rbx
0x1400188b7  mov     rcx, rsi
0x1400188ba  call    GetNextPacketOptionsAndData
0x1400188bf  test    eax, eax
0x1400188c1  jns     short loc_140018903
0x1400188c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400188ca  lea     r14, WPP_GLOBAL_Control
0x1400188d1  cmp     rcx, r14
0x1400188d4  jz      loc_14001883F
0x1400188da  mov     edx, [rcx+2Ch]
0x1400188dd  test    dl, 2
0x1400188e0  jz      loc_14001883F
0x1400188e6  mov     rcx, [rcx+18h]
0x1400188ea  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x1400188f1  mov     edx, 3Eh ; '>'
0x1400188f6  mov     r9d, eax
0x1400188f9  call    WPP_SF_d
0x1400188fe  jmp     loc_14001883F
0x140018903  inc     dword ptr [rbx+80h]
0x140018909  mov     r15, r14
0x14001890c  mov     eax, [rbx+6Ch]
0x14001890f  lea     r14, WPP_GLOBAL_Control
0x140018916  cmp     [rbx+80h], eax
0x14001891c  jnz     loc_1400189CA
0x140018922  cmp     dword ptr [rbx+8Ch], 0
0x140018929  jnz     loc_1400189CA
0x14001892f  cmp     dword ptr [rbx+68h], 0
0x140018933  jnz     loc_1400189CA
0x140018939  mov     rax, [rbx]
0x14001893c  cmp     [rax+8], rbx
0x140018940  jnz     loc_140018AF3
0x140018946  mov     rcx, [rbx+8]
0x14001894a  cmp     [rcx], rbx
0x14001894d  jnz     loc_140018AF3
0x140018953  mov     [rcx], rax
0x140018956  mov     [rax+8], rcx
0x14001895a  lea     rax, [rdi+0D8h]
0x140018961  mov     rcx, [rax+8]
0x140018965  cmp     [rcx], rax
0x140018968  jnz     loc_140018AF3
0x14001896e  mov     [rbx], rax
0x140018971  mov     [rbx+8], rcx
0x140018975  mov     [rcx], rbx
0x140018978  mov     [rax+8], rbx
0x14001897c  dec     dword ptr [rdi+90h]
0x140018982  mov     eax, [rbx+3Ch]
0x140018985  test    al, 40h
0x140018987  jz      short loc_1400189CA
0x140018989  mov     rcx, cs:WPP_GLOBAL_Control
0x140018990  cmp     rcx, r14
0x140018993  jz      short loc_1400189B1
0x140018995  mov     eax, [rcx+2Ch]
0x140018998  test    al, 20h
0x14001899a  jz      short loc_1400189B1
0x14001899c  mov     rcx, [rcx+18h]
0x1400189a0  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x1400189a7  mov     edx, 3Fh ; '?'
0x1400189ac  call    WPP_SF_
0x1400189b1  mov     rax, [rdi+178h]
0x1400189b8  or      dword ptr [rdi+0C4h], 40h
0x1400189bf  mov     [rdi+170h], rax
0x1400189c6  or      dword ptr [rsi+20h], 4
0x1400189ca  inc     dword ptr [rbx+88h]
0x1400189d0  lea     r12, [rsi+168h]
0x1400189d7  mov     dl, [r13+0]; NewIrql
0x1400189db  mov     rcx, r12; SpinLock
0x1400189de  call    cs:__imp_KeReleaseSpinLock
0x1400189e5  nop     dword ptr [rax+rax+00h]
0x1400189ea  mov     rax, [rsp+0E8h+var_90]
0x1400189ef  mov     ecx, [rdi+0A4h]
0x1400189f5  bswap   ecx
0x1400189f7  mov     [rax+14h], ecx
0x1400189fa  xor     ecx, ecx
0x1400189fc  mov     rax, [rsp+0E8h+var_90]
0x140018a01  mov     [rax+6], cx
0x140018a05  movzx   r8d, [rsp+0E8h+var_98]
0x140018a0b  mov     rdx, [rsp+0E8h+var_90]
0x140018a10  call    tcpxsum
0x140018a15  mov     rcx, [rsp+0E8h+var_90]
0x140018a1a  not     ax
0x140018a1d  test    r15, r15
0x140018a20  mov     [rcx+6], ax
0x140018a24  setz    al
0x140018a27  mov     rcx, [rdi+20h]
0x140018a2b  movzx   r9d, [rsp+0E8h+var_98]
0x140018a31  mov     r8, [rsp+0E8h+var_90]
0x140018a36  mov     [rsp+0E8h+var_A0], al
0x140018a3a  movzx   eax, word ptr [rdi+30h]
0x140018a3e  mov     rdx, [rcx+50h]
0x140018a42  mov     rcx, [rcx+48h]
0x140018a46  mov     [rsp+0E8h+var_A8], ax
0x140018a4b  mov     eax, [rdi+28h]
0x140018a4e  mov     [rsp+0E8h+var_B0], eax
0x140018a52  lea     rax, PgmSendODataCompletion
0x140018a59  mov     [rsp+0E8h+var_B8], r15
0x140018a5e  mov     [rsp+0E8h+var_C0], rbx
0x140018a63  mov     [rsp+0E8h+var_C8], rax
0x140018a68  call    TdiSendDatagram
0x140018a6d  mov     ebx, eax
0x140018a6f  mov     rcx, cs:WPP_GLOBAL_Control
0x140018a76  cmp     rcx, r14
0x140018a79  jz      short loc_140018AB7
0x140018a7b  mov     edx, [rcx+2Ch]
0x140018a7e  test    dl, 10h
0x140018a81  jz      short loc_140018AB7
0x140018a83  movzx   edx, word ptr [rdi+30h]
0x140018a87  movzx   r8d, [rsp+0E8h+var_98]
0x140018a8d  mov     eax, [rdi+9Ch]
0x140018a93  mov     r9d, [rdi+0A4h]
0x140018a9a  mov     rcx, [rcx+18h]
0x140018a9e  mov     [rsp+0E8h+var_B0], edx
0x140018aa2  mov     edx, [rdi+28h]
0x140018aa5  mov     dword ptr [rsp+0E8h+var_B8], edx
0x140018aa9  mov     dword ptr [rsp+0E8h+var_C0], r8d
0x140018aae  mov     dword ptr [rsp+0E8h+var_C8], eax
0x140018ab2  call    WPP_SF_dddDd
  ... truncated ...
```
