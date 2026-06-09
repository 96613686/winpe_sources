# FilterOidRequestCompleteCommon

- ea: `0x14000aef0`
- end: `0x14000b552`
- name: `FilterOidRequestCompleteCommon`
- size: `1634`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400087b0`
- `0x14000ae50`

## callees

- `0x140007d58`
- `0x14000ada8`
- `0x14000aef0`
- `0x14000b558`
- `0x14000cd98`
- `0x14000d8ec`
- `0x14000d91c`
- `0x14000eed4`
- `0x14000f110`
- `0x14000f150`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x14000b345`
- `ntoskrnl!DbgPrint` at `0x14000b3a8`
- `ntoskrnl!DbgPrint` at `0x14000b345`
- `ntoskrnl!DbgPrint` at `0x14000b3a8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000af8e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000af8e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b03a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b03a`
- `NDIS!NdisFreeCloneOidRequest` at `0x14000b0c9`
- `NDIS!NdisFreeCloneOidRequest` at `0x14000b0c9`

## pseudocode

```c
void __fastcall FilterOidRequestCompleteCommon(__int64 a1, __int64 a2, unsigned int a3, char a4)
{
  _DWORD *v8; // rbp
  __int64 v9; // rbx
  KIRQL v10; // al
  __int64 v11; // r8
  KIRQL v12; // dl
  int v13; // ecx
  __int64 v14; // r8
  PDEVICE_OBJECT v15; // rcx
  PDEVICE_OBJECT *v16; // rdx
  __int64 v17; // rax
  bool v18; // zf
  int v19; // eax
  unsigned int v20; // [rsp+40h] [rbp-68h]
  int v21; // [rsp+48h] [rbp-60h] BYREF
  __int128 v22; // [rsp+4Ch] [rbp-5Ch]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 179, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  v20 = *(_DWORD *)(a2 + 32);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 180, *(unsigned int *)(a2 + 32), *(unsigned int *)(a2 + 32), a3);
  v8 = *(_DWORD **)(a2 + 216);
  if ( v8 )
  {
    v9 = *(_QWORD *)(a2 + 224);
    if ( !v9 )
      TraceAssert("pFilterMpCtx", "onecoreuap\\net\\vwifi\\filter\\filter.c", 2908);
    if ( *(_DWORD *)(a1 + 24) != 1801678668 )
    {
      DbgPrint("Trying to acquire uninited lock %p, %s, Line %d\n", (const void *)(a1 + 24), "FilterLock", 423);
      __debugbreak();
    }
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 28));
    v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 104));
    *(_BYTE *)(a1 + 32) = 1;
    *(_BYTE *)(a1 + 112) = v10;
    *(_QWORD *)(a1 + 72) = "FilterLock";
    *(_DWORD *)(a1 + 80) = 423;
    if ( v9 && *(_QWORD *)(v9 + 112) == a2
      || (TraceAssert(
            "pFilterMpCtx && pFilterMpCtx->PendingOidRequest == Request",
            "onecoreuap\\net\\vwifi\\filter\\filter.c",
            2912),
          *(_QWORD *)(v9 + 112) == a2) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 182, v11, v20, *(_DWORD *)(v9 + 104));
      if ( !a3 && *(_DWORD *)(a2 + 32) == 218170128 && *(_DWORD *)(v9 + 124) )
        TraceAssert("pFilterMpCtx->OutstandingSends == 0", "onecoreuap\\net\\vwifi\\filter\\filter.c", 2920);
      if ( !*(_BYTE *)(v9 + 2) )
        TraceAssert("pFilterMpCtx->fMpStarted", "onecoreuap\\net\\vwifi\\filter\\filter.c", 2926);
      *(_QWORD *)(v9 + 112) = 0;
    }
    else
    {
      v16 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 183, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_ssL(
            WPP_GLOBAL_Control->AttachedDevice,
            (_DWORD)v16,
            v11,
            (unsigned int)"FALSE",
            (__int64)"onecoreuap\\net\\vwifi\\filter\\filter.c",
            118);
      }
    }
    if ( *(_DWORD *)(a1 + 24) != 1801678668 )
    {
      DbgPrint("Trying to acquire uninited lock %p, %s, Line %d\n", (const void *)(a1 + 24), "FilterUnlock", 430);
      __debugbreak();
    }
    v12 = *(_BYTE *)(a1 + 112);
    *(_QWORD *)(a1 + 88) = "FilterUnlock";
    *(_DWORD *)(a1 + 96) = 430;
    *(_BYTE *)(a1 + 32) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 104), v12);
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 28));
    v13 = *(_DWORD *)(a2 + 4);
    v8[13] = *(_DWORD *)(a2 + 52);
    if ( v13 == 12 )
    {
      v8[16] = *(_DWORD *)(a2 + 64);
      v8[17] = *(_DWORD *)(a2 + 68);
      v8[15] = *(_DWORD *)(a2 + 60);
    }
    else
    {
      v8[14] = *(_DWORD *)(a2 + 56);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 248, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
    if ( *(_DWORD *)(a1 + 2692) == 9 && *(_DWORD *)(a2 + 32) == -50265846 )
    {
      v17 = *(_QWORD *)(a1 + 2704);
      if ( v17 )
      {
        v22 = 0;
        v21 = 1311360;
        v18 = (*(_BYTE *)(v17 + 8) & 1) == 0;
        v19 = _mm_cvtsi128_si32((__m128i)0LL);
        if ( !v18 )
          v19 = 1;
        LODWORD(v22) = v19;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 249, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
        if ( (unsigned int)filterDoInternalRequest(a1, 1, -50265847, (unsigned int)&v21, 20, 0) )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
LABEL_29:
            *(_QWORD *)(a2 + 216) = 0;
            NdisFreeCloneOidRequest(*(NDIS_HANDLE *)(a1 + 128), (PNDIS_OID_REQUEST)a2);
            if ( (*(_BYTE *)(v9 + 2)
               || (TraceAssert("pFilterMpCtx->fMpStarted", "onecoreuap\\net\\vwifi\\filter\\filter.c", 2970),
                   *(_BYTE *)(v9 + 2)))
              && a4 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
              {
                WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 184, v14, v20, *(_DWORD *)(v9 + 104));
              }
              (*(void (__fastcall **)(_QWORD, _DWORD *, _QWORD))(v9 + 80))(*(_QWORD *)(v9 + 56), v8, a3);
            }
            else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 185, v14, v20, *(_DWORD *)(v9 + 104));
            }
            _InterlockedDecrement((volatile signed __int32 *)(v9 + 132));
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 186, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
            }
            return;
          }
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 250, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
        }
      }
      else
      {
        TraceAssert("FALSE", "onecoreuap\\net\\vwifi\\filter\\filter.c", 4529);
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 251, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
    goto LABEL_29;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 181, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  filterInternalRequestComplete(v15, a2, a3);
}

```

## disassembly

```asm
0x14000aef0  push    rbx
0x14000aef2  push    rbp
0x14000aef3  push    rdi
0x14000aef4  push    r12
0x14000aef6  push    r14
0x14000aef8  push    r15
0x14000aefa  sub     rsp, 78h
0x14000aefe  mov     rax, cs:__security_cookie
0x14000af05  xor     rax, rsp
0x14000af08  mov     [rsp+0A8h+var_48], rax
0x14000af0d  movzx   r12d, r9b
0x14000af11  mov     r15d, r8d
0x14000af14  mov     rdi, rdx
0x14000af17  mov     r14, rcx
0x14000af1a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000af21  lea     rbx, WPP_GLOBAL_Control
0x14000af28  cmp     rcx, rbx
0x14000af2b  jnz     loc_14000B18A
0x14000af31  mov     r8d, [rdi+20h]
0x14000af35  mov     [rsp+0A8h+var_68], r8d
0x14000af3a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000af41  cmp     rcx, rbx
0x14000af44  jnz     loc_14000B164
0x14000af4a  mov     rbp, [rdi+0D8h]
0x14000af51  test    rbp, rbp
0x14000af54  jz      loc_14000B1D7
0x14000af5a  mov     rbx, [rdi+0E0h]
0x14000af61  mov     [rsp+0A8h+arg_18], rsi
0x14000af69  mov     [rsp+0A8h+var_38], r13
0x14000af6e  test    rbx, rbx
0x14000af71  jz      loc_14000B30F
0x14000af77  cmp     dword ptr [r14+18h], 6B636F4Ch
0x14000af7f  jnz     loc_14000B32D
0x14000af85  lock inc dword ptr [r14+1Ch]
0x14000af8a  lea     rcx, [r14+68h]; SpinLock
0x14000af8e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000af95  nop     dword ptr [rax+rax+00h]
0x14000af9a  mov     byte ptr [r14+20h], 1
0x14000af9f  mov     [r14+70h], al
0x14000afa3  lea     rax, aFilterlock; "FilterLock"
0x14000afaa  mov     [r14+48h], rax
0x14000afae  mov     dword ptr [r14+50h], 1A7h
0x14000afb6  test    rbx, rbx
0x14000afb9  jz      loc_14000B211
0x14000afbf  cmp     [rbx+70h], rdi
0x14000afc3  jnz     loc_14000B211
0x14000afc9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000afd0  lea     rdx, WPP_GLOBAL_Control
0x14000afd7  cmp     rcx, rdx
0x14000afda  jz      short loc_14000AFE7
0x14000afdc  mov     eax, [rcx+2Ch]
0x14000afdf  test    al, 4
0x14000afe1  jnz     loc_14000B357
0x14000afe7  test    r15d, r15d
0x14000afea  jnz     short loc_14000AFF9
0x14000afec  cmp     dword ptr [rdi+20h], 0D010310h
0x14000aff3  jz      loc_14000B1AF
0x14000aff9  cmp     byte ptr [rbx+2], 0
0x14000affd  jz      loc_14000B376
0x14000b003  mov     qword ptr [rbx+70h], 0
0x14000b00b  cmp     dword ptr [r14+18h], 6B636F4Ch
0x14000b013  lea     rax, aFilterunlock; "FilterUnlock"
0x14000b01a  jnz     loc_14000B394
0x14000b020  movzx   edx, byte ptr [r14+70h]; NewIrql
0x14000b025  lea     rcx, [r14+68h]; SpinLock
0x14000b029  mov     [r14+58h], rax
0x14000b02d  mov     dword ptr [r14+60h], 1AEh
0x14000b035  mov     byte ptr [r14+20h], 0
0x14000b03a  call    cs:__imp_KeReleaseSpinLock
0x14000b041  nop     dword ptr [rax+rax+00h]
0x14000b046  lock dec dword ptr [r14+1Ch]
0x14000b04b  mov     ecx, [rdi+4]
0x14000b04e  mov     eax, [rdi+34h]
0x14000b051  mov     [rbp+34h], eax
0x14000b054  cmp     ecx, 0Ch
0x14000b057  jnz     loc_14000B159
0x14000b05d  mov     eax, [rdi+40h]
0x14000b060  mov     [rbp+40h], eax
0x14000b063  mov     eax, [rdi+44h]
0x14000b066  mov     [rbp+44h], eax
0x14000b069  mov     eax, [rdi+3Ch]
0x14000b06c  mov     [rbp+3Ch], eax
0x14000b06f  xor     esi, esi
0x14000b071  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b078  lea     r13, WPP_GLOBAL_Control
0x14000b07f  cmp     rcx, r13
0x14000b082  jz      short loc_14000B08F
0x14000b084  mov     eax, [rcx+2Ch]
0x14000b087  test    al, 20h
0x14000b089  jnz     loc_14000B3C1
0x14000b08f  cmp     dword ptr [r14+0A84h], 9
0x14000b097  jz      loc_14000B3DB
0x14000b09d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b0a4  cmp     rcx, r13
0x14000b0a7  jz      short loc_14000B0B4
0x14000b0a9  mov     eax, [rcx+2Ch]
0x14000b0ac  test    al, 20h
0x14000b0ae  jnz     loc_14000B4ED
0x14000b0b4  mov     qword ptr [rdi+0D8h], 0
0x14000b0bf  mov     rdx, rdi; Request
0x14000b0c2  mov     rcx, [r14+80h]; SourceHandle
0x14000b0c9  call    cs:__imp_NdisFreeCloneOidRequest
0x14000b0d0  nop     dword ptr [rax+rax+00h]
0x14000b0d5  cmp     byte ptr [rbx+2], 0
0x14000b0d9  mov     rsi, [rsp+0A8h+arg_18]
0x14000b0e1  jz      loc_14000B2B2
0x14000b0e7  test    r12b, r12b
0x14000b0ea  jz      loc_14000B2D5
0x14000b0f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b0f7  cmp     rcx, r13
0x14000b0fa  jz      short loc_14000B107
0x14000b0fc  mov     eax, [rcx+2Ch]
0x14000b0ff  test    al, 4
0x14000b101  jnz     loc_14000B516
0x14000b107  mov     rax, [rbx+50h]
0x14000b10b  mov     r8d, r15d
0x14000b10e  mov     rcx, [rbx+38h]
0x14000b112  mov     rdx, rbp
0x14000b115  call    _guard_dispatch_icall
0x14000b11a  lock dec dword ptr [rbx+84h]
0x14000b121  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b128  cmp     rcx, r13
0x14000b12b  mov     r13, [rsp+0A8h+var_38]
0x14000b130  jz      short loc_14000B13D
0x14000b132  mov     eax, [rcx+2Ch]
0x14000b135  test    al, 20h
0x14000b137  jnz     loc_14000B535
0x14000b13d  mov     rcx, [rsp+0A8h+var_48]
0x14000b142  xor     rcx, rsp; StackCookie
0x14000b145  call    __security_check_cookie
0x14000b14a  add     rsp, 78h
0x14000b14e  pop     r15
0x14000b150  pop     r14
0x14000b152  pop     r12
0x14000b154  pop     rdi
0x14000b155  pop     rbp
0x14000b156  pop     rbx
0x14000b157  retn
0x14000b159  mov     eax, [rdi+38h]
0x14000b15c  mov     [rbp+38h], eax
0x14000b15f  jmp     loc_14000B06F
0x14000b164  mov     eax, [rcx+2Ch]
0x14000b167  test    al, 4
0x14000b169  jz      loc_14000AF4A
0x14000b16f  mov     rcx, [rcx+18h]
0x14000b173  mov     edx, 0B4h
0x14000b178  mov     r9d, r8d
0x14000b17b  mov     dword ptr [rsp+0A8h+var_88], r15d
0x14000b180  call    WPP_SF_Dd
0x14000b185  jmp     loc_14000AF4A
0x14000b18a  mov     eax, [rcx+2Ch]
0x14000b18d  test    al, 20h
0x14000b18f  jz      loc_14000AF31
0x14000b195  mov     rcx, [rcx+18h]
0x14000b199  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000b1a0  mov     edx, 0B3h
0x14000b1a5  call    WPP_SF_
0x14000b1aa  jmp     loc_14000AF31
0x14000b1af  cmp     dword ptr [rbx+7Ch], 0
0x14000b1b3  jz      loc_14000AFF9
0x14000b1b9  mov     r8d, 0B68h
0x14000b1bf  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000b1c6  lea     rcx, aPfiltermpctxOu; "pFilterMpCtx->OutstandingSends == 0"
0x14000b1cd  call    TraceAssert
0x14000b1d2  jmp     loc_14000AFF9
0x14000b1d7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b1de  cmp     rcx, rbx
0x14000b1e1  jnz     short loc_14000B1F3
0x14000b1e3  mov     r8d, r15d
0x14000b1e6  mov     rdx, rdi
0x14000b1e9  call    filterInternalRequestComplete
0x14000b1ee  jmp     loc_14000B13D
0x14000b1f3  mov     eax, [rcx+2Ch]
0x14000b1f6  test    al, 4
0x14000b1f8  jz      short loc_14000B1E3
0x14000b1fa  mov     rcx, [rcx+18h]
0x14000b1fe  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000b205  mov     edx, 0B5h
0x14000b20a  call    WPP_SF_
0x14000b20f  jmp     short loc_14000B1E3
0x14000b211  mov     r8d, 0B60h
0x14000b217  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000b21e  lea     rcx, aPfiltermpctxPf; "pFilterMpCtx && pFilterMpCtx->PendingOi"...
0x14000b225  call    TraceAssert
0x14000b22a  cmp     [rbx+70h], rdi
0x14000b22e  jz      loc_14000AFC9
0x14000b234  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b23b  lea     rdx, WPP_GLOBAL_Control
0x14000b242  cmp     rcx, rdx
0x14000b245  jz      loc_14000B00B
0x14000b24b  mov     eax, [rcx+2Ch]
0x14000b24e  test    al, 4
0x14000b250  jz      short loc_14000B267
0x14000b252  mov     rcx, [rcx+18h]
0x14000b256  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000b25d  mov     edx, 0B7h
0x14000b262  call    WPP_SF_
0x14000b267  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b26e  lea     rax, WPP_GLOBAL_Control
0x14000b275  cmp     rcx, rax
0x14000b278  jz      loc_14000B00B
0x14000b27e  mov     eax, [rcx+2Ch]
0x14000b281  test    al, 2
0x14000b283  jz      loc_14000B00B
0x14000b289  mov     rcx, [rcx+18h]
0x14000b28d  lea     rax, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000b294  mov     [rsp+0A8h+var_80], 0B76h
0x14000b29c  lea     r9, aFalse; "FALSE"
0x14000b2a3  mov     [rsp+0A8h+var_88], rax
0x14000b2a8  call    WPP_SF_ssL
0x14000b2ad  jmp     loc_14000B00B
0x14000b2b2  mov     r8d, 0B9Ah
0x14000b2b8  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000b2bf  lea     rcx, aPfiltermpctxFm_0; "pFilterMpCtx->fMpStarted"
0x14000b2c6  call    TraceAssert
0x14000b2cb  cmp     byte ptr [rbx+2], 0
0x14000b2cf  jnz     loc_14000B0E7
0x14000b2d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b2dc  cmp     rcx, r13
0x14000b2df  jz      loc_14000B11A
0x14000b2e5  mov     eax, [rcx+2Ch]
0x14000b2e8  test    al, 4
0x14000b2ea  jz      loc_14000B11A
0x14000b2f0  mov     eax, [rbx+68h]
0x14000b2f3  mov     edx, 0B9h
0x14000b2f8  mov     r9d, [rsp+0A8h+var_68]
0x14000b2fd  mov     rcx, [rcx+18h]
0x14000b301  mov     dword ptr [rsp+0A8h+var_88], eax
0x14000b305  call    WPP_SF_Dd
0x14000b30a  jmp     loc_14000B11A
0x14000b30f  mov     r8d, 0B5Ch
0x14000b315  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000b31c  lea     rcx, aPfiltermpctx; "pFilterMpCtx"
0x14000b323  call    TraceAssert
0x14000b328  jmp     loc_14000AF77
0x14000b32d  mov     r9d, 1A7h
0x14000b333  lea     r8, aFilterlock; "FilterLock"
0x14000b33a  lea     rdx, [r14+18h]
0x14000b33e  lea     rcx, Format; "Trying to acquire uninited lock %p, %s,"...
0x14000b345  call    cs:__imp_DbgPrint
0x14000b34c  nop     dword ptr [rax+rax+00h]
0x14000b351  int     3; Trap to Debugger
0x14000b352  jmp     loc_14000AF85
0x14000b357  mov     eax, [rbx+68h]
0x14000b35a  mov     edx, 0B6h
0x14000b35f  mov     r9d, [rsp+0A8h+var_68]
0x14000b364  mov     rcx, [rcx+18h]
0x14000b368  mov     dword ptr [rsp+0A8h+var_88], eax
0x14000b36c  call    WPP_SF_Dd
0x14000b371  jmp     loc_14000AFE7
0x14000b376  mov     r8d, 0B6Eh
0x14000b37c  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000b383  lea     rcx, aPfiltermpctxFm_0; "pFilterMpCtx->fMpStarted"
0x14000b38a  call    TraceAssert
0x14000b38f  jmp     loc_14000B003
0x14000b394  mov     r9d, 1AEh
0x14000b39a  lea     rdx, [r14+18h]
0x14000b39e  mov     r8, rax
0x14000b3a1  lea     rcx, Format; "Trying to acquire uninited lock %p, %s,"...
0x14000b3a8  call    cs:__imp_DbgPrint
0x14000b3af  nop     dword ptr [rax+rax+00h]
0x14000b3b4  int     3; Trap to Debugger
0x14000b3b5  lea     rax, aFilterunlock; "FilterUnlock"
0x14000b3bc  jmp     loc_14000B020
0x14000b3c1  mov     rcx, [rcx+18h]
0x14000b3c5  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000b3cc  mov     edx, 0F8h
0x14000b3d1  call    WPP_SF_
0x14000b3d6  jmp     loc_14000B08F
0x14000b3db  cmp     dword ptr [rdi+20h], 0FD01010Ah
0x14000b3e2  jnz     loc_14000B09D
0x14000b3e8  mov     rax, [r14+0A90h]
0x14000b3ef  test    rax, rax
0x14000b3f2  jz      loc_14000B4CF
0x14000b3f8  mov     r13, [rdi+0E0h]
0x14000b3ff  xorps   xmm0, xmm0
0x14000b402  movdqu  [rsp+0A8h+var_5C], xmm0
0x14000b408  mov     [rsp+0A8h+var_60], 140280h
0x14000b410  mov     ecx, 1
0x14000b415  test    byte ptr [rax+8], 1
0x14000b419  movd    eax, xmm0
0x14000b41d  mov     [rsp+0A8h+var_64], esi
0x14000b421  cmovnz  eax, ecx
0x14000b424  mov     dword ptr [rsp+0A8h+var_5C], eax
0x14000b428  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b42f  lea     rax, WPP_GLOBAL_Control
0x14000b436  cmp     rcx, rax
0x14000b439  jz      short loc_14000B45B
0x14000b43b  mov     eax, [rcx+2Ch]
0x14000b43e  test    al, 4
0x14000b440  jz      short loc_14000B45B
0x14000b442  mov     r9d, [r13+68h]
0x14000b446  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000b44d  mov     rcx, [rcx+18h]
0x14000b451  mov     edx, 0F9h
0x14000b456  call    WPP_SF_d
0x14000b45b  lea     rax, [rsp+0A8h+var_64]
0x14000b460  mov     edx, 1
0x14000b465  mov     [rsp+0A8h+var_70], rax
0x14000b46a  lea     r9, [rsp+0A8h+var_60]
  ... truncated ...
```
