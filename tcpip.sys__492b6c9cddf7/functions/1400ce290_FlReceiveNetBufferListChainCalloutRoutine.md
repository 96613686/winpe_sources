# FlReceiveNetBufferListChainCalloutRoutine

- ea: `0x1400ce290`
- end: `0x1400ce5a8`
- name: `FlReceiveNetBufferListChainCalloutRoutine`
- size: `792`
- prototype: `EXPAND_STACK_CALLOUT`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1401acf20`

## callees

- `0x140090f50`
- `0x1400946f8`
- `0x1400c28c0`
- `0x1400c54b0`
- `0x1400ce290`
- `0x1400ce5b0`
- `0x1400cef80`
- `0x1400cefc0`
- `0x1400cfb14`
- `0x14011fcfc`
- `0x140149764`
- `0x1401bf390`
- `0x1401bf5c0`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400ce399`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cc3f1`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cc4fe`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400ce399`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cc3f1`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cc4fe`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc457`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc550`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc56b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc457`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc550`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc56b`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400ce2f6`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401cc3b9`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400ce2f6`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401cc3b9`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc242`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc283`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc3ce`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc4e4`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc242`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc283`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc3ce`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc4e4`
- `NETIO!NetioUpdateNetBufferListContext` at `0x1401cc217`
- `NETIO!NetioUpdateNetBufferListContext` at `0x1401cc217`
- `NETIO!WfpNblInfoClearFlags` at `0x1401cc229`
- `NETIO!WfpNblInfoClearFlags` at `0x1401cc229`
- `NDIS!NdisGetDataBuffer` at `0x1401cc2b2`
- `NDIS!NdisGetDataBuffer` at `0x1401cc2b2`

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
  void (__fastcall *v21)(__int64, __int64); // rax
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
  __int64 v46; // [rsp+60h] [rbp-A0h] BYREF
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
  if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 9) & 0x20) != 0 )
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
              FlpFlsInterceptReceivePackets(v38, v46, v40, v41, 1, v8, v5);
              ExReleaseRundownProtectionCacheAwareEx(
                *(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v38 + 256) + 16LL),
                1u);
            }
            else
            {
              FlpUpdateFastPathCounters(v42, Count);
              v21 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 32) + 216LL) + 8LL)
                                                            + 72LL);
              v22 = *(_QWORD *)(v38 + 144);
              if ( (char *)v21 == (char *)IpFlcReceivePreValidatedPackets )
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
              v46,
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
          if ( (char *)v17 == (char *)IpFlcReceivePreValidatedPackets )
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
0x1400ce290  push    rbp
0x1400ce292  push    rbx
0x1400ce293  push    rsi
0x1400ce294  push    rdi
0x1400ce295  push    r12
0x1400ce297  push    r13
0x1400ce299  push    r14
0x1400ce29b  push    r15
0x1400ce29d  lea     rbp, [rsp-28h]
0x1400ce2a2  sub     rsp, 128h
0x1400ce2a9  mov     rax, cs:__security_cookie
0x1400ce2b0  xor     rax, rsp
0x1400ce2b3  mov     [rbp+60h+var_50], rax
0x1400ce2b7  mov     rax, [rcx+8]
0x1400ce2bb  mov     rbx, [rcx+18h]
0x1400ce2bf  mov     r14, [rcx+28h]
0x1400ce2c3  mov     r15d, [rcx+14h]
0x1400ce2c7  mov     rdi, [rcx]
0x1400ce2ca  mov     r13d, [rcx+20h]
0x1400ce2ce  mov     [rsp+160h+var_F0], rax
0x1400ce2d3  xor     eax, eax
0x1400ce2d5  mov     [rsp+160h+var_118], rax
0x1400ce2da  mov     [rsp+160h+var_100], rax
0x1400ce2df  mov     [rsp+160h+Count], eax
0x1400ce2e3  mov     [rbp+60h+var_C0], rax
0x1400ce2e7  mov     [rsp+160h+var_E8], rbx
0x1400ce2ec  mov     [rsp+160h+var_108], r14
0x1400ce2f1  mov     [rsp+160h+var_F8], r15d
0x1400ce2f6  call    cs:__imp_KeGetCurrentIrql
0x1400ce2fd  nop     dword ptr [rax+rax+00h]
0x1400ce302  mov     rcx, [rdi+20h]
0x1400ce306  cmp     al, 2
0x1400ce308  mov     sil, al
0x1400ce30b  setnb   r12b
0x1400ce30f  test    byte ptr cs:WPP_MAIN_CB+149h, 20h
0x1400ce316  movzx   eax, word ptr [rcx+5Ch]
0x1400ce31a  mov     [rsp+160h+var_120], ax
0x1400ce31f  jnz     loc_1400CE47F
0x1400ce325  test    r13b, 2
0x1400ce329  jnz     loc_1400CE434
0x1400ce32f  mov     eax, [rdi+138h]
0x1400ce335  test    eax, eax
0x1400ce337  jnz     loc_1400CE4FD
0x1400ce33d  cmp     dword ptr [rdi+3B0h], 0
0x1400ce344  jnz     short loc_1400CE363
0x1400ce346  mov     rax, [rdi+120h]
0x1400ce34d  mov     rcx, [rax+100h]
0x1400ce354  test    rcx, rcx
0x1400ce357  jz      short loc_1400CE363
0x1400ce359  cmp     byte ptr [rcx+18h], 0
0x1400ce35d  jz      loc_1400CE434
0x1400ce363  lea     rax, [rsp+160h+var_F0]
0x1400ce368  xor     r8d, r8d
0x1400ce36b  lea     r9, [rsp+160h+var_118]
0x1400ce370  mov     qword ptr [rsp+160h+AlignOffset], rax
0x1400ce375  mov     dl, r12b
0x1400ce378  mov     rcx, rdi
0x1400ce37b  call    FlpValidateNetBufferListChain
0x1400ce380  sub     r15d, eax
0x1400ce383  mov     r14d, eax
0x1400ce386  mov     [rsp+160h+var_F8], r15d
0x1400ce38b  test    eax, eax
0x1400ce38d  jz      loc_1400CE42F
0x1400ce393  mov     rcx, [rdi+48h]; RunRefCacheAware
0x1400ce397  mov     edx, eax; Count
0x1400ce399  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1400ce3a0  nop     dword ptr [rax+rax+00h]
0x1400ce3a5  test    al, al
0x1400ce3a7  jz      loc_1400CE50B
0x1400ce3ad  add     [rbx], r14d
0x1400ce3b0  cmp     cs:Fl6tTeredoShuntReadWrite, 0
0x1400ce3b7  jnz     loc_1400CE557
0x1400ce3bd  mov     rax, [rsp+160h+var_118]
0x1400ce3c2  test    rax, rax
0x1400ce3c5  jz      short loc_1400CE42F
0x1400ce3c7  cmp     dword ptr [rdi+3B0h], 0
0x1400ce3ce  jnz     loc_1400CE591
0x1400ce3d4  mov     rax, [rdi+120h]
0x1400ce3db  mov     rcx, [rax+100h]
0x1400ce3e2  test    rcx, rcx
0x1400ce3e5  jz      short loc_1400CE3F2
0x1400ce3e7  mov     al, [rcx+18h]
0x1400ce3ea  test    al, al
0x1400ce3ec  jz      loc_1401CC3E8
0x1400ce3f2  movzx   ecx, [rsp+160h+var_120]
0x1400ce3f7  mov     edx, r14d
0x1400ce3fa  call    FlpUpdateFastPathCounters
0x1400ce3ff  mov     r9, [rdi+20h]
0x1400ce403  lea     r14, IpFlcReceivePreValidatedPackets
0x1400ce40a  mov     rdx, [rsp+160h+var_118]
0x1400ce40f  mov     rax, [r9+0D8h]
0x1400ce416  mov     rcx, [rax+8]
0x1400ce41a  mov     rax, [rcx+48h]
0x1400ce41e  mov     rcx, [rdi+130h]
0x1400ce425  cmp     rax, r14
0x1400ce428  jnz     short loc_1400CE478
0x1400ce42a  call    IpFlcReceivePreValidatedPackets
0x1400ce42f  mov     r14, [rsp+160h+var_108]
0x1400ce434  cmp     [rsp+160h+var_F8], 0
0x1400ce439  ja      short loc_1400CE45C
0x1400ce43b  mov     rcx, [rbp+60h+var_50]
0x1400ce43f  xor     rcx, rsp; StackCookie
0x1400ce442  call    __security_check_cookie
0x1400ce447  add     rsp, 128h
0x1400ce44e  pop     r15
0x1400ce450  pop     r14
0x1400ce452  pop     r13
0x1400ce454  pop     r12
0x1400ce456  pop     rdi
0x1400ce457  pop     rsi
0x1400ce458  pop     rbx
0x1400ce459  pop     rbp
0x1400ce45a  retn
0x1400ce45c  mov     r9, [rsp+160h+var_E8]
0x1400ce461  mov     r8, r14
0x1400ce464  mov     rdx, [rsp+160h+var_F0]
0x1400ce469  mov     rcx, rdi
0x1400ce46c  mov     [rsp+160h+AlignOffset], r13d
0x1400ce471  call    FlpReceiveNonPreValidatedNetBufferListChain
0x1400ce476  jmp     short loc_1400CE43B
0x1400ce478  call    _guard_dispatch_icall
0x1400ce47d  jmp     short loc_1400CE42F
0x1400ce47f  mov     rbx, [rsp+160h+var_F0]
0x1400ce484  test    rbx, rbx
0x1400ce487  jz      short loc_1400CE49B
0x1400ce489  mov     edx, 1
0x1400ce48e  mov     rcx, rbx
0x1400ce491  call    NetioEtwTraceNblOobInfo
0x1400ce496  mov     rbx, [rbx]
0x1400ce499  jmp     short loc_1400CE484
0x1400ce49b  mov     rbx, [rsp+160h+var_E8]
0x1400ce4a0  jmp     loc_1400CE325
0x1400ce4a5  mov     rcx, [rbx+100h]
0x1400ce4ac  test    rcx, rcx
0x1400ce4af  jz      short loc_1400CE4BC
0x1400ce4b1  mov     al, [rcx+18h]
0x1400ce4b4  test    al, al
0x1400ce4b6  jz      loc_1401CC4F5
0x1400ce4bc  mov     edx, [rsp+160h+Count]
0x1400ce4c0  movzx   ecx, [rsp+160h+var_120]
0x1400ce4c5  call    FlpUpdateFastPathCounters
0x1400ce4ca  mov     r9, [rdi+20h]
0x1400ce4ce  mov     rdx, [rsp+160h+var_100]
0x1400ce4d3  mov     rax, [r9+0D8h]
0x1400ce4da  mov     rcx, [rax+8]
0x1400ce4de  mov     rax, [rcx+48h]
0x1400ce4e2  mov     rcx, [rbx+90h]
0x1400ce4e9  cmp     rax, r14
0x1400ce4ec  jnz     loc_1401CC55E
0x1400ce4f2  call    IpFlcReceivePreValidatedPackets
0x1400ce4f7  nop
0x1400ce4f8  jmp     loc_1401CC563
0x1400ce4fd  cmp     eax, 9
0x1400ce500  jnz     loc_1400CE434
0x1400ce506  jmp     loc_1400CE33D
0x1400ce50b  mov     rcx, [rdi+120h]
0x1400ce512  mov     r13d, 1
0x1400ce518  mov     rbx, [rsp+160h+var_118]
0x1400ce51d  mov     r9d, r14d
0x1400ce520  mov     [rsp+160h+var_128], 0E0004002h
0x1400ce528  mov     r8d, r13d
0x1400ce52b  mov     rdx, rbx
0x1400ce52e  mov     eax, [rcx+0CCh]
0x1400ce534  mov     [rsp+160h+var_130], eax
0x1400ce538  mov     dword ptr [rsp+160h+var_138], 0
0x1400ce540  mov     [rsp+160h+AlignOffset], 8
0x1400ce548  call    FlpLogPacketDiscardWithType
0x1400ce54d  mov     r14, [rsp+160h+var_108]
0x1400ce552  jmp     loc_1401CC200
0x1400ce557  cmp     dword ptr [rdi+138h], 0
0x1400ce55e  jnz     loc_1400CE3BD
0x1400ce564  mov     rbx, [rsp+160h+var_118]
0x1400ce569  lea     rax, [rbp+60h+var_E0]
0x1400ce56d  xor     esi, esi
0x1400ce56f  mov     [rbp+60h+var_D8], rax
0x1400ce573  mov     [rbp+60h+var_E0], rsi
0x1400ce577  lea     rax, [rbp+60h+var_D0]
0x1400ce57b  mov     [rbp+60h+var_C8], rax
0x1400ce57f  mov     [rbp+60h+var_D0], rsi
0x1400ce583  test    rbx, rbx
0x1400ce586  jnz     loc_1401CC295
0x1400ce58c  jmp     loc_1401CC3DA
0x1400ce591  mov     esi, 800h
0x1400ce596  lea     r14, IpFlcReceivePreValidatedPackets
0x1400ce59d  mov     r15d, 86DDh
0x1400ce5a3  jmp     loc_1401CC469
0x1401cc200  test    rbx, rbx
0x1401cc203  jz      short loc_1401CC23A
0x1401cc205  test    r14, r14
0x1401cc208  jz      short loc_1401CC223
0x1401cc20a  mov     r8, rdi
0x1401cc20d  lea     rdx, FlpCompleteNdisNetBufferListChain
0x1401cc214  mov     rcx, rbx
0x1401cc217  call    cs:__imp_NetioUpdateNetBufferListContext
0x1401cc21e  nop     dword ptr [rax+rax+00h]
0x1401cc223  mov     rdx, r13
0x1401cc226  mov     rcx, rbx
0x1401cc229  call    cs:__imp_WfpNblInfoClearFlags
0x1401cc230  nop     dword ptr [rax+rax+00h]
0x1401cc235  mov     rbx, [rbx]
0x1401cc238  jmp     short loc_1401CC200
0x1401cc23a  mov     rcx, [rsp+160h+var_118]
0x1401cc23f  mov     dl, r12b
0x1401cc242  call    cs:__imp_NetioDereferenceNetBufferListChain
0x1401cc249  nop     dword ptr [rax+rax+00h]
0x1401cc24e  mov     rcx, [rsp+160h+var_F0]
0x1401cc253  test    rcx, rcx
0x1401cc256  jz      loc_1400CE43B
0x1401cc25c  test    r14, r14
0x1401cc25f  jz      short loc_1401CC280
0x1401cc261  xor     r8d, r8d
0x1401cc264  mov     rdx, rcx
0x1401cc267  cmp     sil, 2
0x1401cc26b  mov     r9d, r15d
0x1401cc26e  mov     rcx, rdi
0x1401cc271  setnb   r8b
0x1401cc275  call    FlpNdisReturnNetBufferListsWrapper
0x1401cc27a  nop
0x1401cc27b  jmp     loc_1400CE43B
0x1401cc280  mov     dl, r12b
0x1401cc283  call    cs:__imp_NetioDereferenceNetBufferListChain
0x1401cc28a  nop     dword ptr [rax+rax+00h]
0x1401cc28f  nop
0x1401cc290  jmp     loc_1400CE43B
0x1401cc295  mov     rcx, [rbx+8]; NetBuffer
0x1401cc299  lea     r8, [rbp+60h+Storage]; Storage
0x1401cc29d  mov     r9d, 2; AlignMultiple
0x1401cc2a3  mov     [rsp+160h+AlignOffset], 0; AlignOffset
0x1401cc2ab  mov     r15, rbx
0x1401cc2ae  lea     edx, [r9+50h]; BytesNeeded
0x1401cc2b2  call    cs:__imp_NdisGetDataBuffer
0x1401cc2b9  nop     dword ptr [rax+rax+00h]
0x1401cc2be  test    rax, rax
0x1401cc2c1  jz      short loc_1401CC2FB
0x1401cc2c3  cmp     byte ptr [rax+0Eh], 45h ; 'E'
0x1401cc2c7  jnz     short loc_1401CC2FB
0x1401cc2c9  cmp     byte ptr [rax+17h], 11h
0x1401cc2cd  jnz     short loc_1401CC2FB
0x1401cc2cf  mov     ecx, 0D80Dh
0x1401cc2d4  cmp     [rax+24h], cx
0x1401cc2d8  jnz     short loc_1401CC2FB
0x1401cc2da  mov     ecx, [rax+2Ah]
0x1401cc2dd  and     ecx, 0F0h
0x1401cc2e3  cmp     cl, 60h ; '`'
0x1401cc2e6  jnz     short loc_1401CC2FB
0x1401cc2e8  mov     al, [rax+30h]
0x1401cc2eb  sub     al, 3Ah ; ':'
0x1401cc2ed  cmp     al, 1
0x1401cc2ef  jbe     short loc_1401CC2FB
0x1401cc2f1  mov     rax, [rbp+60h+var_D8]
0x1401cc2f5  mov     cl, 1
0x1401cc2f7  inc     esi
0x1401cc2f9  jmp     short loc_1401CC301
0x1401cc2fb  mov     rax, [rbp+60h+var_C8]
0x1401cc2ff  xor     cl, cl
0x1401cc301  mov     [rax], rbx
0x1401cc304  lea     rdx, [rbp+60h+var_D8]
0x1401cc308  test    cl, cl
0x1401cc30a  lea     rax, [rbp+60h+var_C8]
0x1401cc30e  cmovnz  rax, rdx
0x1401cc312  mov     [rax], rbx
0x1401cc315  mov     rbx, [rbx]
0x1401cc318  mov     qword ptr [r15], 0
0x1401cc31f  test    rbx, rbx
0x1401cc322  jnz     loc_1401CC295
0x1401cc328  test    esi, esi
0x1401cc32a  jz      loc_1401CC3DA
0x1401cc330  mov     rax, cs:FlTeredoInterface
0x1401cc337  test    rax, rax
0x1401cc33a  jz      short loc_1401CC382
0x1401cc33c  lock inc dword ptr [rax+30h]
0x1401cc340  mov     rdx, cs:FlTeredoInterface
0x1401cc347  xor     r9d, r9d
0x1401cc34a  mov     r8, [rbp+60h+var_E0]
0x1401cc34e  mov     rcx, rdi
0x1401cc351  mov     dword ptr [rsp+160h+var_138], r13d
0x1401cc356  mov     [rsp+160h+AlignOffset], esi
0x1401cc35a  mov     rax, [rdx+20h]
0x1401cc35e  mov     rax, [rax+1B0h]
0x1401cc365  call    _guard_dispatch_icall
0x1401cc36a  mov     rcx, cs:FlTeredoInterface
0x1401cc371  mov     rbx, rax
0x1401cc374  call    FlpDereferenceInterface
0x1401cc379  mov     rcx, [rbp+60h+var_C8]
0x1401cc37d  mov     [rcx], rbx
0x1401cc380  jmp     short loc_1401CC3DA
0x1401cc382  mov     eax, ds:0CCh
0x1401cc389  mov     r9d, esi
0x1401cc38c  mov     rdx, [rbp+60h+var_E0]
0x1401cc390  mov     r8d, 1
0x1401cc396  mov     [rsp+160h+var_128], 0E0004009h
0x1401cc39e  xor     ecx, ecx
0x1401cc3a0  mov     [rsp+160h+var_130], eax
0x1401cc3a4  mov     dword ptr [rsp+160h+var_138], 0
0x1401cc3ac  mov     [rsp+160h+AlignOffset], 8
0x1401cc3b4  call    FlpLogPacketDiscardWithType
0x1401cc3b9  call    cs:__imp_KeGetCurrentIrql
0x1401cc3c0  nop     dword ptr [rax+rax+00h]
0x1401cc3c5  mov     rcx, [rbp+60h+var_E0]
0x1401cc3c9  cmp     al, 2
  ... truncated ...
```
