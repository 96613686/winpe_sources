# FlReceiveNetBufferListChainCalloutRoutine

- ea: `0x1400ffc20`
- end: `0x1400fff38`
- name: `FlReceiveNetBufferListChainCalloutRoutine`
- size: `792`
- prototype: `EXPAND_STACK_CALLOUT`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1401aec20`

## callees

- `0x14003d510`
- `0x14003e22c`
- `0x14004a420`
- `0x14005caf0`
- `0x1400cc4b0`
- `0x1400ffc20`
- `0x1400fff40`
- `0x140100910`
- `0x140103de4`
- `0x140126cc4`
- `0x14014b9e4`
- `0x1401c0fd0`
- `0x1401c1200`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400ffd29`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401d4b23`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401d4c30`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400ffd29`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401d4b23`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401d4c30`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400ffc86`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401d4aeb`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400ffc86`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401d4aeb`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401d4b89`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401d4c82`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401d4c9d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401d4b89`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401d4c82`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401d4c9d`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401d4974`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401d49b5`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401d4b00`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401d4c16`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401d4974`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401d49b5`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401d4b00`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401d4c16`
- `NETIO!NetioUpdateNetBufferListContext` at `0x1401d4949`
- `NETIO!NetioUpdateNetBufferListContext` at `0x1401d4949`
- `NETIO!WfpNblInfoClearFlags` at `0x1401d495b`
- `NETIO!WfpNblInfoClearFlags` at `0x1401d495b`
- `NDIS!NdisGetDataBuffer` at `0x1401d49e4`
- `NDIS!NdisGetDataBuffer` at `0x1401d49e4`

## pseudocode

```c
void __fastcall FlReceiveNetBufferListChainCalloutRoutine(_QWORD *Parameter)
{
  _DWORD *v1; // rbx
  __int64 v2; // r14
  ULONG v3; // r15d
  __int64 v4; // rdi
  int v5; // r13d
  int v6; // edx
  KIRQL CurrentIrql; // si
  char v8; // r12
  int v9; // eax
  __int64 v10; // rcx
  ULONG v11; // eax
  ULONG v12; // r15d
  ULONG v13; // r14d
  int v14; // r8d
  _QWORD *v15; // rax
  __int64 v16; // rcx
  void (__fastcall *v17)(__int64, _QWORD *); // rax
  __int64 v18; // rcx
  _QWORD *i; // rbx
  __int64 v20; // rcx
  void (__fastcall *v21)(__int64, _QWORD *); // rax
  __int64 v22; // rcx
  _QWORD *v23; // rbx
  __int64 v24; // rdx
  __int64 v25; // r14
  _QWORD *v26; // rbx
  int v27; // esi
  __int64 v28; // rdx
  _QWORD *v29; // r15
  _BYTE *DataBuffer; // rax
  __int64 *v31; // rax
  char v32; // cl
  __int64 **v33; // rax
  __int64 v34; // rbx
  __int64 v35; // rdx
  int v36; // r8d
  int v37; // r9d
  __int64 v38; // rbx
  __int64 v39; // rdx
  int v40; // r8d
  int v41; // r9d
  unsigned __int16 v42; // [rsp+40h] [rbp-C0h]
  _QWORD *v43; // [rsp+48h] [rbp-B8h] BYREF
  ULONG Count; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v45; // [rsp+58h] [rbp-A8h]
  _QWORD *v46; // [rsp+60h] [rbp-A0h] BYREF
  ULONG v47; // [rsp+68h] [rbp-98h]
  _QWORD *v48; // [rsp+70h] [rbp-90h] BYREF
  _DWORD *v49; // [rsp+78h] [rbp-88h]
  __int64 v50; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v51; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v52; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v53; // [rsp+98h] [rbp-68h] BYREF
  __int64 v54; // [rsp+A0h] [rbp-60h] BYREF
  char Storage[96]; // [rsp+B0h] [rbp-50h] BYREF

  v1 = (_DWORD *)Parameter[3];
  v2 = Parameter[5];
  v3 = *((_DWORD *)Parameter + 5);
  v4 = *Parameter;
  v5 = *((_DWORD *)Parameter + 8);
  v48 = (_QWORD *)Parameter[1];
  v43 = 0;
  v46 = 0;
  Count = 0;
  v54 = 0;
  v49 = v1;
  v45 = v2;
  v47 = v3;
  CurrentIrql = KeGetCurrentIrql();
  v8 = CurrentIrql >= 2u;
  v42 = *(_WORD *)(*(_QWORD *)(v4 + 32) + 92LL);
  if ( (BYTE1(WPP_MAIN_CB.Dpc.DeferredContext) & 0x20) != 0 )
  {
    for ( i = v48; i; i = (_QWORD *)*i )
      NetioEtwTraceNblOobInfo(i, 1);
    v1 = v49;
  }
  if ( (v5 & 2) != 0 )
    goto LABEL_18;
  v9 = *(_DWORD *)(v4 + 312);
  if ( v9 )
  {
    if ( v9 != 9 )
      goto LABEL_18;
  }
  if ( !*(_DWORD *)(v4 + 944) )
  {
    v10 = *(_QWORD *)(*(_QWORD *)(v4 + 288) + 256LL);
    if ( v10 )
    {
      if ( !*(_BYTE *)(v10 + 24) )
        goto LABEL_18;
    }
  }
  LOBYTE(v6) = CurrentIrql >= 2u;
  v11 = FlpValidateNetBufferListChain(v4, v6, 0, (unsigned int)&v43, (__int64)&v48);
  v12 = v3 - v11;
  v13 = v11;
  v47 = v12;
  if ( !v11 )
  {
LABEL_17:
    v2 = v45;
LABEL_18:
    if ( v47 )
      FlpReceiveNonPreValidatedNetBufferListChain(v4, v48, v2, v49, v5);
    return;
  }
  if ( ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v4 + 72), v11) )
  {
    *v1 += v13;
    if ( !Fl6tTeredoShuntReadWrite || *(_DWORD *)(v4 + 312) )
    {
      v15 = v43;
    }
    else
    {
      v26 = v43;
      v27 = 0;
      v51 = &v50;
      v50 = 0;
      v53 = (__int64 *)&v52;
      v52 = 0;
      if ( v43 )
      {
        do
        {
          v29 = v26;
          DataBuffer = NdisGetDataBuffer((PNET_BUFFER)v26[1], 0x52u, Storage, 2u, 0);
          if ( DataBuffer
            && DataBuffer[14] == 69
            && DataBuffer[23] == 17
            && *((_WORD *)DataBuffer + 18) == 0xD80D
            && (DataBuffer[42] & 0xF0) == 0x60
            && (unsigned __int8)(DataBuffer[48] - 58) > 1u )
          {
            v31 = v51;
            v32 = 1;
            ++v27;
          }
          else
          {
            v31 = v53;
            v32 = 0;
          }
          *v31 = (__int64)v26;
          v33 = &v53;
          if ( v32 )
            v33 = &v51;
          *v33 = v26;
          v26 = (_QWORD *)*v26;
          *v29 = 0;
        }
        while ( v26 );
        if ( v27 )
        {
          if ( FlTeredoInterface )
          {
            _InterlockedIncrement((volatile signed __int32 *)(FlTeredoInterface + 48));
            v34 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, int, int))(*(_QWORD *)(FlTeredoInterface + 32)
                                                                                         + 432LL))(
                    v4,
                    FlTeredoInterface,
                    v50,
                    0,
                    v27,
                    v5);
            FlpDereferenceInterface(FlTeredoInterface);
            *v53 = v34;
          }
          else
          {
            FlpLogPacketDiscardWithType(0, v50, 1, v27, 8, 0, MEMORY[0xCC], -536854519);
            LOBYTE(v35) = KeGetCurrentIrql() >= 2u;
            NetioDereferenceNetBufferListChain(v50, v35);
          }
        }
      }
      v15 = v52;
      v43 = v52;
    }
    if ( v15 )
    {
      if ( *(_DWORD *)(v4 + 944) )
      {
        do
        {
          LOBYTE(v14) = v8;
          FlpSplitNetBufferListChainByIsolationId(
            v4,
            (unsigned int)&v43,
            v14,
            (unsigned int)&v46,
            (__int64)&Count,
            (__int64)&v54);
          v38 = v54;
          if ( v54 )
          {
            v20 = *(_QWORD *)(v54 + 256);
            if ( v20
              && !*(_BYTE *)(v20 + 24)
              && ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v20 + 16), 1u) )
            {
              v41 = 2048;
              if ( v42 != 2 )
                LOWORD(v41) = -31011;
              FlpFlsInterceptReceivePackets(v38, (_DWORD)v46, v40, v41, 1, v8, v5);
              ExReleaseRundownProtectionCacheAwareEx(
                *(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v38 + 256) + 16LL),
                1u);
            }
            else
            {
              FlpUpdateFastPathCounters(v42, Count);
              v21 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 32) + 216LL)
                                                                         + 8LL)
                                                             + 72LL);
              v22 = *(_QWORD *)(v38 + 144);
              if ( v21 == IpFlcReceivePreValidatedPackets )
                IpFlcReceivePreValidatedPackets(v22, v46);
              else
                v21(v22, v46);
            }
            ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v38 + 56), Count);
          }
          else
          {
            FlpLogPacketDiscardWithType(
              *(_QWORD *)(v4 + 288),
              (_DWORD)v46,
              1,
              Count,
              14,
              *(_DWORD *)(v4 + 944),
              *(_DWORD *)(*(_QWORD *)(v4 + 288) + 204LL),
              -536854526);
            LOBYTE(v39) = v8;
            NetioDereferenceNetBufferListChain(v46, v39);
          }
        }
        while ( v43 );
      }
      else
      {
        v16 = *(_QWORD *)(*(_QWORD *)(v4 + 288) + 256LL);
        if ( v16
          && !*(_BYTE *)(v16 + 24)
          && ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v16 + 16), 1u) )
        {
          v37 = 2048;
          if ( v42 != 2 )
            LOWORD(v37) = -31011;
          FlpFlsInterceptReceivePackets(*(_QWORD *)(v4 + 288), (_DWORD)v43, v36, v37, 1, v8, v5);
          ExReleaseRundownProtectionCacheAwareEx(
            *(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(*(_QWORD *)(v4 + 288) + 256LL) + 16LL),
            1u);
        }
        else
        {
          FlpUpdateFastPathCounters(v42, v13);
          v17 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 32) + 216LL) + 8LL)
                                                         + 72LL);
          v18 = *(_QWORD *)(v4 + 304);
          if ( v17 == IpFlcReceivePreValidatedPackets )
            IpFlcReceivePreValidatedPackets(v18, v43);
          else
            v17(v18, v43);
        }
      }
    }
    goto LABEL_17;
  }
  v23 = v43;
  FlpLogPacketDiscardWithType(
    *(_QWORD *)(v4 + 288),
    (_DWORD)v43,
    1,
    v13,
    8,
    0,
    *(_DWORD *)(*(_QWORD *)(v4 + 288) + 204LL),
    -536854526);
  v25 = v45;
  while ( v23 )
  {
    if ( v25 )
      NetioUpdateNetBufferListContext(v23, FlpCompleteNdisNetBufferListChain, v4);
    WfpNblInfoClearFlags(v23, 1);
    v23 = (_QWORD *)*v23;
  }
  LOBYTE(v24) = CurrentIrql >= 2u;
  NetioDereferenceNetBufferListChain(v43, v24);
  if ( v48 )
  {
    if ( v25 )
    {
      FlpNdisReturnNetBufferListsWrapper(v4, v48, CurrentIrql >= 2u, v12);
    }
    else
    {
      LOBYTE(v28) = CurrentIrql >= 2u;
      NetioDereferenceNetBufferListChain(v48, v28);
    }
  }
}

```

## disassembly

```asm
0x1400ffc20  push    rbp
0x1400ffc22  push    rbx
0x1400ffc23  push    rsi
0x1400ffc24  push    rdi
0x1400ffc25  push    r12
0x1400ffc27  push    r13
0x1400ffc29  push    r14
0x1400ffc2b  push    r15
0x1400ffc2d  lea     rbp, [rsp-28h]
0x1400ffc32  sub     rsp, 128h
0x1400ffc39  mov     rax, cs:__security_cookie
0x1400ffc40  xor     rax, rsp
0x1400ffc43  mov     [rbp+60h+var_50], rax
0x1400ffc47  mov     rax, [rcx+8]
0x1400ffc4b  mov     rbx, [rcx+18h]
0x1400ffc4f  mov     r14, [rcx+28h]
0x1400ffc53  mov     r15d, [rcx+14h]
0x1400ffc57  mov     rdi, [rcx]
0x1400ffc5a  mov     r13d, [rcx+20h]
0x1400ffc5e  mov     [rsp+160h+var_F0], rax
0x1400ffc63  xor     eax, eax
0x1400ffc65  mov     [rsp+160h+var_118], rax
0x1400ffc6a  mov     [rsp+160h+var_100], rax
0x1400ffc6f  mov     [rsp+160h+Count], eax
0x1400ffc73  mov     [rbp+60h+var_C0], rax
0x1400ffc77  mov     [rsp+160h+var_E8], rbx
0x1400ffc7c  mov     [rsp+160h+var_108], r14
0x1400ffc81  mov     [rsp+160h+var_F8], r15d
0x1400ffc86  call    cs:__imp_KeGetCurrentIrql
0x1400ffc8d  nop     dword ptr [rax+rax+00h]
0x1400ffc92  mov     rcx, [rdi+20h]
0x1400ffc96  cmp     al, 2
0x1400ffc98  mov     sil, al
0x1400ffc9b  setnb   r12b
0x1400ffc9f  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext+1, 20h
0x1400ffca6  movzx   eax, word ptr [rcx+5Ch]
0x1400ffcaa  mov     [rsp+160h+var_120], ax
0x1400ffcaf  jnz     loc_1400FFE0F
0x1400ffcb5  test    r13b, 2
0x1400ffcb9  jnz     loc_1400FFDC4
0x1400ffcbf  mov     eax, [rdi+138h]
0x1400ffcc5  test    eax, eax
0x1400ffcc7  jnz     loc_1400FFE8D
0x1400ffccd  cmp     dword ptr [rdi+3B0h], 0
0x1400ffcd4  jnz     short loc_1400FFCF3
0x1400ffcd6  mov     rax, [rdi+120h]
0x1400ffcdd  mov     rcx, [rax+100h]
0x1400ffce4  test    rcx, rcx
0x1400ffce7  jz      short loc_1400FFCF3
0x1400ffce9  cmp     byte ptr [rcx+18h], 0
0x1400ffced  jz      loc_1400FFDC4
0x1400ffcf3  lea     rax, [rsp+160h+var_F0]
0x1400ffcf8  xor     r8d, r8d
0x1400ffcfb  lea     r9, [rsp+160h+var_118]
0x1400ffd00  mov     qword ptr [rsp+160h+AlignOffset], rax
0x1400ffd05  mov     dl, r12b
0x1400ffd08  mov     rcx, rdi
0x1400ffd0b  call    FlpValidateNetBufferListChain
0x1400ffd10  sub     r15d, eax
0x1400ffd13  mov     r14d, eax
0x1400ffd16  mov     [rsp+160h+var_F8], r15d
0x1400ffd1b  test    eax, eax
0x1400ffd1d  jz      loc_1400FFDBF
0x1400ffd23  mov     rcx, [rdi+48h]; RunRefCacheAware
0x1400ffd27  mov     edx, eax; Count
0x1400ffd29  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1400ffd30  nop     dword ptr [rax+rax+00h]
0x1400ffd35  test    al, al
0x1400ffd37  jz      loc_1400FFE9B
0x1400ffd3d  add     [rbx], r14d
0x1400ffd40  cmp     cs:Fl6tTeredoShuntReadWrite, 0
0x1400ffd47  jnz     loc_1400FFEE7
0x1400ffd4d  mov     rax, [rsp+160h+var_118]
0x1400ffd52  test    rax, rax
0x1400ffd55  jz      short loc_1400FFDBF
0x1400ffd57  cmp     dword ptr [rdi+3B0h], 0
0x1400ffd5e  jnz     loc_1400FFF21
0x1400ffd64  mov     rax, [rdi+120h]
0x1400ffd6b  mov     rcx, [rax+100h]
0x1400ffd72  test    rcx, rcx
0x1400ffd75  jz      short loc_1400FFD82
0x1400ffd77  mov     al, [rcx+18h]
0x1400ffd7a  test    al, al
0x1400ffd7c  jz      loc_1401D4B1A
0x1400ffd82  movzx   ecx, [rsp+160h+var_120]
0x1400ffd87  mov     edx, r14d
0x1400ffd8a  call    FlpUpdateFastPathCounters
0x1400ffd8f  mov     r9, [rdi+20h]
0x1400ffd93  lea     r14, IpFlcReceivePreValidatedPackets
0x1400ffd9a  mov     rdx, [rsp+160h+var_118]
0x1400ffd9f  mov     rax, [r9+0D8h]
0x1400ffda6  mov     rcx, [rax+8]
0x1400ffdaa  mov     rax, [rcx+48h]
0x1400ffdae  mov     rcx, [rdi+130h]
0x1400ffdb5  cmp     rax, r14
0x1400ffdb8  jnz     short loc_1400FFE08
0x1400ffdba  call    IpFlcReceivePreValidatedPackets
0x1400ffdbf  mov     r14, [rsp+160h+var_108]
0x1400ffdc4  cmp     [rsp+160h+var_F8], 0
0x1400ffdc9  ja      short loc_1400FFDEC
0x1400ffdcb  mov     rcx, [rbp+60h+var_50]
0x1400ffdcf  xor     rcx, rsp; StackCookie
0x1400ffdd2  call    __security_check_cookie
0x1400ffdd7  add     rsp, 128h
0x1400ffdde  pop     r15
0x1400ffde0  pop     r14
0x1400ffde2  pop     r13
0x1400ffde4  pop     r12
0x1400ffde6  pop     rdi
0x1400ffde7  pop     rsi
0x1400ffde8  pop     rbx
0x1400ffde9  pop     rbp
0x1400ffdea  retn
0x1400ffdec  mov     r9, [rsp+160h+var_E8]
0x1400ffdf1  mov     r8, r14
0x1400ffdf4  mov     rdx, [rsp+160h+var_F0]
0x1400ffdf9  mov     rcx, rdi
0x1400ffdfc  mov     [rsp+160h+AlignOffset], r13d
0x1400ffe01  call    FlpReceiveNonPreValidatedNetBufferListChain
0x1400ffe06  jmp     short loc_1400FFDCB
0x1400ffe08  call    _guard_dispatch_icall
0x1400ffe0d  jmp     short loc_1400FFDBF
0x1400ffe0f  mov     rbx, [rsp+160h+var_F0]
0x1400ffe14  test    rbx, rbx
0x1400ffe17  jz      short loc_1400FFE2B
0x1400ffe19  mov     edx, 1
0x1400ffe1e  mov     rcx, rbx
0x1400ffe21  call    NetioEtwTraceNblOobInfo
0x1400ffe26  mov     rbx, [rbx]
0x1400ffe29  jmp     short loc_1400FFE14
0x1400ffe2b  mov     rbx, [rsp+160h+var_E8]
0x1400ffe30  jmp     loc_1400FFCB5
0x1400ffe35  mov     rcx, [rbx+100h]
0x1400ffe3c  test    rcx, rcx
0x1400ffe3f  jz      short loc_1400FFE4C
0x1400ffe41  mov     al, [rcx+18h]
0x1400ffe44  test    al, al
0x1400ffe46  jz      loc_1401D4C27
0x1400ffe4c  mov     edx, [rsp+160h+Count]
0x1400ffe50  movzx   ecx, [rsp+160h+var_120]
0x1400ffe55  call    FlpUpdateFastPathCounters
0x1400ffe5a  mov     r9, [rdi+20h]
0x1400ffe5e  mov     rdx, [rsp+160h+var_100]
0x1400ffe63  mov     rax, [r9+0D8h]
0x1400ffe6a  mov     rcx, [rax+8]
0x1400ffe6e  mov     rax, [rcx+48h]
0x1400ffe72  mov     rcx, [rbx+90h]
0x1400ffe79  cmp     rax, r14
0x1400ffe7c  jnz     loc_1401D4C90
0x1400ffe82  call    IpFlcReceivePreValidatedPackets
0x1400ffe87  nop
0x1400ffe88  jmp     loc_1401D4C95
0x1400ffe8d  cmp     eax, 9
0x1400ffe90  jnz     loc_1400FFDC4
0x1400ffe96  jmp     loc_1400FFCCD
0x1400ffe9b  mov     rcx, [rdi+120h]
0x1400ffea2  mov     r13d, 1
0x1400ffea8  mov     rbx, [rsp+160h+var_118]
0x1400ffead  mov     r9d, r14d
0x1400ffeb0  mov     [rsp+160h+var_128], 0E0004002h
0x1400ffeb8  mov     r8d, r13d
0x1400ffebb  mov     rdx, rbx
0x1400ffebe  mov     eax, [rcx+0CCh]
0x1400ffec4  mov     [rsp+160h+var_130], eax
0x1400ffec8  mov     dword ptr [rsp+160h+var_138], 0
0x1400ffed0  mov     [rsp+160h+AlignOffset], 8
0x1400ffed8  call    FlpLogPacketDiscardWithType
0x1400ffedd  mov     r14, [rsp+160h+var_108]
0x1400ffee2  jmp     loc_1401D4932
0x1400ffee7  cmp     dword ptr [rdi+138h], 0
0x1400ffeee  jnz     loc_1400FFD4D
0x1400ffef4  mov     rbx, [rsp+160h+var_118]
0x1400ffef9  lea     rax, [rbp+60h+var_E0]
0x1400ffefd  xor     esi, esi
0x1400ffeff  mov     [rbp+60h+var_D8], rax
0x1400fff03  mov     [rbp+60h+var_E0], rsi
0x1400fff07  lea     rax, [rbp+60h+var_D0]
0x1400fff0b  mov     [rbp+60h+var_C8], rax
0x1400fff0f  mov     [rbp+60h+var_D0], rsi
0x1400fff13  test    rbx, rbx
0x1400fff16  jnz     loc_1401D49C7
0x1400fff1c  jmp     loc_1401D4B0C
0x1400fff21  mov     esi, 800h
0x1400fff26  lea     r14, IpFlcReceivePreValidatedPackets
0x1400fff2d  mov     r15d, 86DDh
0x1400fff33  jmp     loc_1401D4B9B
0x1401d4932  test    rbx, rbx
0x1401d4935  jz      short loc_1401D496C
0x1401d4937  test    r14, r14
0x1401d493a  jz      short loc_1401D4955
0x1401d493c  mov     r8, rdi
0x1401d493f  lea     rdx, FlpCompleteNdisNetBufferListChain
0x1401d4946  mov     rcx, rbx
0x1401d4949  call    cs:__imp_NetioUpdateNetBufferListContext
0x1401d4950  nop     dword ptr [rax+rax+00h]
0x1401d4955  mov     rdx, r13
0x1401d4958  mov     rcx, rbx
0x1401d495b  call    cs:__imp_WfpNblInfoClearFlags
0x1401d4962  nop     dword ptr [rax+rax+00h]
0x1401d4967  mov     rbx, [rbx]
0x1401d496a  jmp     short loc_1401D4932
0x1401d496c  mov     rcx, [rsp+160h+var_118]
0x1401d4971  mov     dl, r12b
0x1401d4974  call    cs:__imp_NetioDereferenceNetBufferListChain
0x1401d497b  nop     dword ptr [rax+rax+00h]
0x1401d4980  mov     rcx, [rsp+160h+var_F0]
0x1401d4985  test    rcx, rcx
0x1401d4988  jz      loc_1400FFDCB
0x1401d498e  test    r14, r14
0x1401d4991  jz      short loc_1401D49B2
0x1401d4993  xor     r8d, r8d
0x1401d4996  mov     rdx, rcx
0x1401d4999  cmp     sil, 2
0x1401d499d  mov     r9d, r15d
0x1401d49a0  mov     rcx, rdi
0x1401d49a3  setnb   r8b
0x1401d49a7  call    FlpNdisReturnNetBufferListsWrapper
0x1401d49ac  nop
0x1401d49ad  jmp     loc_1400FFDCB
0x1401d49b2  mov     dl, r12b
0x1401d49b5  call    cs:__imp_NetioDereferenceNetBufferListChain
0x1401d49bc  nop     dword ptr [rax+rax+00h]
0x1401d49c1  nop
0x1401d49c2  jmp     loc_1400FFDCB
0x1401d49c7  mov     rcx, [rbx+8]; NetBuffer
0x1401d49cb  lea     r8, [rbp+60h+Storage]; Storage
0x1401d49cf  mov     r9d, 2; AlignMultiple
0x1401d49d5  mov     [rsp+160h+AlignOffset], 0; AlignOffset
0x1401d49dd  mov     r15, rbx
0x1401d49e0  lea     edx, [r9+50h]; BytesNeeded
0x1401d49e4  call    cs:__imp_NdisGetDataBuffer
0x1401d49eb  nop     dword ptr [rax+rax+00h]
0x1401d49f0  test    rax, rax
0x1401d49f3  jz      short loc_1401D4A2D
0x1401d49f5  cmp     byte ptr [rax+0Eh], 45h ; 'E'
0x1401d49f9  jnz     short loc_1401D4A2D
0x1401d49fb  cmp     byte ptr [rax+17h], 11h
0x1401d49ff  jnz     short loc_1401D4A2D
0x1401d4a01  mov     ecx, 0D80Dh
0x1401d4a06  cmp     [rax+24h], cx
0x1401d4a0a  jnz     short loc_1401D4A2D
0x1401d4a0c  mov     ecx, [rax+2Ah]
0x1401d4a0f  and     ecx, 0F0h
0x1401d4a15  cmp     cl, 60h ; '`'
0x1401d4a18  jnz     short loc_1401D4A2D
0x1401d4a1a  mov     al, [rax+30h]
0x1401d4a1d  sub     al, 3Ah ; ':'
0x1401d4a1f  cmp     al, 1
0x1401d4a21  jbe     short loc_1401D4A2D
0x1401d4a23  mov     rax, [rbp+60h+var_D8]
0x1401d4a27  mov     cl, 1
0x1401d4a29  inc     esi
0x1401d4a2b  jmp     short loc_1401D4A33
0x1401d4a2d  mov     rax, [rbp+60h+var_C8]
0x1401d4a31  xor     cl, cl
0x1401d4a33  mov     [rax], rbx
0x1401d4a36  lea     rdx, [rbp+60h+var_D8]
0x1401d4a3a  test    cl, cl
0x1401d4a3c  lea     rax, [rbp+60h+var_C8]
0x1401d4a40  cmovnz  rax, rdx
0x1401d4a44  mov     [rax], rbx
0x1401d4a47  mov     rbx, [rbx]
0x1401d4a4a  mov     qword ptr [r15], 0
0x1401d4a51  test    rbx, rbx
0x1401d4a54  jnz     loc_1401D49C7
0x1401d4a5a  test    esi, esi
0x1401d4a5c  jz      loc_1401D4B0C
0x1401d4a62  mov     rax, cs:FlTeredoInterface
0x1401d4a69  test    rax, rax
0x1401d4a6c  jz      short loc_1401D4AB4
0x1401d4a6e  lock inc dword ptr [rax+30h]
0x1401d4a72  mov     rdx, cs:FlTeredoInterface
0x1401d4a79  xor     r9d, r9d
0x1401d4a7c  mov     r8, [rbp+60h+var_E0]
0x1401d4a80  mov     rcx, rdi
0x1401d4a83  mov     dword ptr [rsp+160h+var_138], r13d
0x1401d4a88  mov     [rsp+160h+AlignOffset], esi
0x1401d4a8c  mov     rax, [rdx+20h]
0x1401d4a90  mov     rax, [rax+1B0h]
0x1401d4a97  call    _guard_dispatch_icall
0x1401d4a9c  mov     rcx, cs:FlTeredoInterface
0x1401d4aa3  mov     rbx, rax
0x1401d4aa6  call    FlpDereferenceInterface
0x1401d4aab  mov     rcx, [rbp+60h+var_C8]
0x1401d4aaf  mov     [rcx], rbx
0x1401d4ab2  jmp     short loc_1401D4B0C
0x1401d4ab4  mov     eax, ds:0CCh
0x1401d4abb  mov     r9d, esi
0x1401d4abe  mov     rdx, [rbp+60h+var_E0]
0x1401d4ac2  mov     r8d, 1
0x1401d4ac8  mov     [rsp+160h+var_128], 0E0004009h
0x1401d4ad0  xor     ecx, ecx
0x1401d4ad2  mov     [rsp+160h+var_130], eax
0x1401d4ad6  mov     dword ptr [rsp+160h+var_138], 0
0x1401d4ade  mov     [rsp+160h+AlignOffset], 8
0x1401d4ae6  call    FlpLogPacketDiscardWithType
0x1401d4aeb  call    cs:__imp_KeGetCurrentIrql
0x1401d4af2  nop     dword ptr [rax+rax+00h]
0x1401d4af7  mov     rcx, [rbp+60h+var_E0]
0x1401d4afb  cmp     al, 2
  ... truncated ...
```
