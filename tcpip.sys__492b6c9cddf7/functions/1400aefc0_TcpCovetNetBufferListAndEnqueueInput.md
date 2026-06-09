# TcpCovetNetBufferListAndEnqueueInput

- ea: `0x1400aefc0`
- end: `0x1400af465`
- name: `TcpCovetNetBufferListAndEnqueueInput`
- size: `1189`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400ad488`

## callees

- `0x140053e04`
- `0x1400aefc0`
- `0x1400af4b0`
- `0x1400af9b8`
- `0x1400afa90`
- `0x1400afc10`
- `0x1401bf5c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400af338`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400af338`
- `NETIO!NetioDereferenceNetBufferList` at `0x1400af3ff`
- `NETIO!NetioDereferenceNetBufferList` at `0x1400af41a`
- `NETIO!NetioDereferenceNetBufferList` at `0x1400af3ff`
- `NETIO!NetioDereferenceNetBufferList` at `0x1400af41a`
- `NETIO!NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData` at `0x1400af05f`
- `NETIO!NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData` at `0x1400af05f`
- `NETIO!RtlCopyMdlToMdlIndirect` at `0x1400af111`
- `NETIO!RtlCopyMdlToMdlIndirect` at `0x1400af1b7`
- `NETIO!RtlCopyMdlToMdlIndirect` at `0x1400af111`
- `NETIO!RtlCopyMdlToMdlIndirect` at `0x1400af1b7`
- `NETIO!NetioAllocateAndReferenceNetBufferAndNetBufferList` at `0x1401c98f1`
- `NETIO!NetioAllocateAndReferenceNetBufferAndNetBufferList` at `0x1401c98f1`

## pseudocode

```c
__int64 __fastcall TcpCovetNetBufferListAndEnqueueInput(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        unsigned int a5)
{
  __int64 (__fastcall **v6)(_QWORD, _QWORD); // r8
  unsigned int v8; // r14d
  bool v9; // zf
  int v10; // esi
  __int64 v12; // r15
  __int64 v13; // r15
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rdi
  __int64 v17; // rax
  __int64 v18; // rdi
  __int64 v19; // rdx
  unsigned int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rdi
  __int64 v23; // r8
  int v24; // edx
  unsigned int v25; // eax
  __int64 v26; // r8
  __int64 v28; // r15
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rcx
  unsigned int v32; // eax
  __int64 *v33; // rsi
  int v34; // edi
  __int64 v35; // rcx
  __int64 *v36; // r13
  char *v37; // rsi
  char *v38; // rax
  __int64 v39; // rcx
  __int64 v40; // r9
  __int64 v41; // rax
  __int64 v42; // rdx
  __int64 v43; // rax
  __int64 v44; // rax
  int v45; // [rsp+28h] [rbp-58h]
  unsigned int v46; // [rsp+40h] [rbp-40h]
  __int64 v47; // [rsp+48h] [rbp-38h] BYREF
  __int64 v48; // [rsp+50h] [rbp-30h] BYREF
  __int64 v49; // [rsp+58h] [rbp-28h] BYREF
  __int64 v50; // [rsp+60h] [rbp-20h] BYREF
  __int64 v51; // [rsp+68h] [rbp-18h] BYREF
  __int64 v52; // [rsp+70h] [rbp-10h]
  __int64 v53; // [rsp+78h] [rbp-8h]
  unsigned int v54; // [rsp+D0h] [rbp+50h] BYREF
  int v55; // [rsp+D8h] [rbp+58h] BYREF

  v6 = *(__int64 (__fastcall ***)(_QWORD, _QWORD))&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
  v47 = 0;
  v8 = 4032;
  v50 = 0;
  v54 = 0;
  if ( *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels )
    v8 = 4096;
  v55 = 0;
  v9 = (*(_DWORD *)(a3 + 136) & 0x10000000) == 0;
  v10 = a2;
  v48 = 0;
  *a4 = 0;
  if ( !v9 )
  {
    *(_QWORD *)a3 = 0;
    TcpEnqueueTcbInput(a1, a2, a3, a3, 1);
    *a4 = *(unsigned int *)(*(_QWORD *)(a3 + 8) + 24LL);
    return 0;
  }
  v12 = *(_QWORD *)(a2 + 64);
  if ( v12 )
  {
    v28 = *(_QWORD *)(v12 + 16);
    if ( v28 )
    {
      if ( *(__int64 (__fastcall **)(PNET_BUFFER_LIST))(v28 + 80) == TcpDelayedDeliveryCompletionRoutine )
      {
        v29 = *(_QWORD *)(v28 + 8);
        v53 = v29;
        if ( *(_DWORD *)(v29 + 40) < 0x20000u )
        {
          v30 = *(_QWORD *)(v28 + 112);
          v47 = v30;
          if ( v29 )
          {
            v31 = *(_QWORD *)(a3 + 8);
            v46 = 0;
            v23 = *(unsigned int *)(v31 + 24);
            v50 = *(_QWORD *)(v31 + 8);
            v55 = *(_DWORD *)(v31 + 16);
            v32 = *(_DWORD *)(v30 + 40);
            v51 = v23;
            if ( v32 >= v8 )
              goto LABEL_45;
            v54 = v32;
            *(_DWORD *)(v30 + 40) = v8;
            v46 = v32;
            if ( !v54 )
              goto LABEL_45;
            v33 = 0;
            v22 = 0;
            if ( v23 + (unsigned __int64)v54 > v8 )
            {
              if ( v54 )
              {
                v34 = v54 + v23 - v8;
                goto LABEL_37;
              }
LABEL_45:
              v34 = v23;
LABEL_37:
              v35 = *(_QWORD *)(a1 + 848);
              v36 = &v49;
              v52 = v35;
              v49 = 0;
              while ( 1 )
              {
                if ( *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels )
                {
                  v43 = (**(__int64 (__fastcall ***)(__int64, __int64))&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels)(
                          4096,
                          v35);
                  *v36 = v43;
                  v33 = (__int64 *)v43;
                  if ( !v43 )
                  {
                    v39 = v49;
                    if ( !v49 )
                      goto LABEL_47;
                    goto LABEL_57;
                  }
                  v34 -= 4096;
                }
                else
                {
                  v37 = (char *)TcpDelayedDeliveryMdlPool + 128 * (unsigned __int64)(a5 + 1);
                  if ( !v37[176] )
                    PplpLazyInitializeLookasideList(TcpDelayedDeliveryMdlPool, v37 + 64);
                  v38 = (char *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v37 + 64));
                  if ( !v38 )
                  {
                    v39 = v49;
                    if ( !v49 )
                      goto LABEL_47;
LABEL_57:
                    TcpDestroyMdlChain(v39, a5);
                    goto LABEL_47;
                  }
                  v33 = (__int64 *)(v38 - 64);
                  v34 -= 4032;
                  *v36 = (__int64)(v38 - 64);
                }
                if ( v34 <= 0 )
                  break;
                v35 = v52;
                v36 = v33;
              }
              v22 = v49;
              if ( v49 )
              {
                v23 = v51;
                *(_QWORD *)v47 = v49;
                if ( !v54 )
                  v47 = v22;
                goto LABEL_19;
              }
LABEL_47:
              if ( v54 )
                *(_DWORD *)(v47 + 40) = v54;
              return 3221225495LL;
            }
LABEL_19:
            RtlCopyMdlToMdlIndirect(&v50, &v55, &v47, &v54, v23, 0, &v48);
            v24 = v51;
            if ( v48 == v51 )
            {
              if ( v33 )
                *(_QWORD *)(v28 + 112) = v33;
              v25 = v54;
              if ( !v54 )
                v25 = v8;
              *(_DWORD *)(*(_QWORD *)(v28 + 112) + 40LL) = v25;
              *(_DWORD *)(v53 + 24) += v24;
              if ( *(int *)(a3 + 136) < 0 )
                *(_DWORD *)(v28 + 136) |= 0x80000000;
              goto LABEL_26;
            }
            if ( v33 )
            {
              if ( v46 )
                *(_DWORD *)(*(_QWORD *)(v28 + 112) + 40LL) = v46;
              TcpDestroyMdlChain(v22, a5);
              **(_QWORD **)(v28 + 112) = 0;
            }
            else
            {
              *(_DWORD *)(*(_QWORD *)(v28 + 112) + 40LL) = v46;
            }
            return 3221225473LL;
          }
        }
      }
    }
  }
  if ( v6 )
  {
    v44 = (*v6)(v8, *(_QWORD *)(a1 + 848));
    v53 = v44;
    if ( !v44 )
      return 3221225495LL;
    v13 = NetioAllocateAndReferenceNetBufferAndNetBufferList(TcpDelayedDeliveryCompletionRoutine, 0, v44, 0, v8, 1);
    if ( !v13 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 8LL))(v53);
      return 3221225495LL;
    }
  }
  else
  {
    v45 = 0;
    v13 = NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData(TcpDelayedDeliveryNblPool, v8, 0);
    if ( !v13 )
      return 3221225495LL;
  }
  if ( *(int *)(a3 + 136) < 0 )
    *(_DWORD *)(v13 + 136) |= 0x80000000;
  *(_DWORD *)(v13 + 136) |= 0x10000000u;
  v14 = *(_QWORD *)(a3 + 8);
  v15 = *(unsigned int *)(v14 + 24);
  v50 = *(_QWORD *)(v14 + 8);
  v55 = *(_DWORD *)(v14 + 16);
  v16 = *(_QWORD *)(v13 + 8);
  v53 = v15;
  v47 = *(_QWORD *)(v16 + 32);
  if ( (unsigned int)v15 > v8 )
  {
    v40 = *(_QWORD *)(a1 + 848);
    v51 = 0;
    v41 = TcpBuildMdlChain((unsigned int)v15 - v8, &v51, a5, v40);
    *(_QWORD *)v47 = v41;
    if ( v41 )
    {
      v17 = v51;
      LODWORD(v15) = v53;
      goto LABEL_11;
    }
    LOBYTE(v42) = 1;
    NetioDereferenceNetBufferList(v13, v42);
    return 3221225495LL;
  }
  v17 = *(_QWORD *)(v16 + 8);
LABEL_11:
  *(_QWORD *)(v13 + 112) = v17;
  *(_QWORD *)(v16 + 80) = 0;
  *(_DWORD *)(v16 + 40) = 0;
  v54 = 0;
  *(_DWORD *)(v16 + 24) = v15;
  *(_DWORD *)(v16 + 16) = 0;
  v18 = (unsigned int)v15;
  LOBYTE(v45) = 0;
  RtlCopyMdlToMdlIndirect(&v50, &v55, &v47, &v54, (unsigned int)v15, v45, &v48);
  if ( v48 == v18 )
  {
    v20 = v54;
    v21 = *(_QWORD *)(v13 + 112);
    if ( !v54 )
      v20 = v8;
    *(_DWORD *)(v21 + 40) = v20;
    TcpEnqueueTcbInput(v21, v10, v13, v13, 1);
LABEL_26:
    v26 = a5;
    *(_QWORD *)a3 = 0;
    TcpNetBufferListChainDelay(a3, a3, v26);
    *a4 = v48;
    return 0;
  }
  LOBYTE(v19) = 1;
  NetioDereferenceNetBufferList(v13, v19);
  return 3221225473LL;
}

```

## disassembly

```asm
0x1400aefc0  mov     [rsp-38h+arg_0], rbx
0x1400aefc5  push    rbp
0x1400aefc6  push    rsi
0x1400aefc7  push    rdi
0x1400aefc8  push    r12
0x1400aefca  push    r13
0x1400aefcc  push    r14
0x1400aefce  push    r15
0x1400aefd0  mov     rbp, rsp
0x1400aefd3  sub     rsp, 80h
0x1400aefda  xor     r10d, r10d
0x1400aefdd  mov     rbx, r8
0x1400aefe0  mov     r8, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400aefe7  mov     r12, r9
0x1400aefea  test    r8, r8
0x1400aefed  mov     [rbp+var_38], r10
0x1400aeff1  mov     r14d, 0FC0h
0x1400aeff7  mov     [rbp+var_20], r10
0x1400aeffb  mov     r9d, 1000h
0x1400af001  mov     [rbp+arg_10], r10d
0x1400af005  cmovnz  r14d, r9d
0x1400af009  mov     [rbp+arg_18], r10d
0x1400af00d  test    dword ptr [rbx+88h], 10000000h
0x1400af017  mov     rsi, rdx
0x1400af01a  mov     r13, rcx
0x1400af01d  mov     [rbp+var_30], r10
0x1400af021  mov     [r12], r10
0x1400af025  jnz     loc_1400AF14F
0x1400af02b  mov     r15, [rdx+40h]
0x1400af02f  test    r15, r15
0x1400af032  jnz     loc_1400AF241
0x1400af038  lea     rdi, TcpDelayedDeliveryCompletionRoutine
0x1400af03f  test    r8, r8
0x1400af042  jnz     loc_1401C98BD
0x1400af048  mov     rcx, cs:TcpDelayedDeliveryNblPool
0x1400af04f  xor     r9d, r9d
0x1400af052  mov     [rsp+80h+var_58], r10
0x1400af057  mov     edx, r14d
0x1400af05a  mov     [rsp+80h+var_60], rdi
0x1400af05f  call    cs:__imp_NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData
0x1400af066  nop     dword ptr [rax+rax+00h]
0x1400af06b  mov     r15, rax
0x1400af06e  test    rax, rax
0x1400af071  jz      loc_1400AF391
0x1400af077  cmp     dword ptr [rbx+88h], 0
0x1400af07e  jge     short loc_1400AF08B
0x1400af080  or      dword ptr [r15+88h], 80000000h
0x1400af08b  or      dword ptr [r15+88h], 10000000h
0x1400af096  mov     rcx, [rbx+8]
0x1400af09a  mov     rax, [rcx+8]
0x1400af09e  mov     edx, [rcx+18h]
0x1400af0a1  mov     [rbp+var_20], rax
0x1400af0a5  mov     eax, [rcx+10h]
0x1400af0a8  mov     [rbp+arg_18], eax
0x1400af0ab  mov     rdi, [r15+8]
0x1400af0af  mov     [rbp+var_8], rdx
0x1400af0b3  mov     rax, [rdi+20h]
0x1400af0b7  mov     [rbp+var_38], rax
0x1400af0bb  cmp     edx, r14d
0x1400af0be  ja      loc_1400AF39B
0x1400af0c4  mov     rax, [rdi+8]
0x1400af0c8  mov     [r15+70h], rax
0x1400af0cc  lea     r9, [rbp+arg_10]
0x1400af0d0  mov     qword ptr [rdi+50h], 0
0x1400af0d8  lea     rax, [rbp+var_30]
0x1400af0dc  mov     dword ptr [rdi+28h], 0
0x1400af0e3  lea     r8, [rbp+var_38]
0x1400af0e7  mov     [rbp+arg_10], 0
0x1400af0ee  lea     rcx, [rbp+var_20]
0x1400af0f2  mov     [rdi+18h], edx
0x1400af0f5  mov     [rsp+80h+var_50], rax
0x1400af0fa  mov     dword ptr [rdi+10h], 0
0x1400af101  mov     edi, edx
0x1400af103  lea     rdx, [rbp+arg_18]
0x1400af107  mov     byte ptr [rsp+80h+var_58], 0
0x1400af10c  mov     [rsp+80h+var_60], rdi
0x1400af111  call    cs:__imp_RtlCopyMdlToMdlIndirect
0x1400af118  nop     dword ptr [rax+rax+00h]
0x1400af11d  cmp     [rbp+var_30], rdi
0x1400af121  jnz     loc_1400AF3FA
0x1400af127  mov     eax, [rbp+arg_10]
0x1400af12a  mov     r9, r15
0x1400af12d  mov     rcx, [r15+70h]
0x1400af131  test    eax, eax
0x1400af133  mov     r8, r15
0x1400af136  mov     byte ptr [rsp+80h+var_60], 1
0x1400af13b  cmovz   eax, r14d
0x1400af13f  mov     rdx, rsi
0x1400af142  mov     [rcx+28h], eax
0x1400af145  call    TcpEnqueueTcbInput
0x1400af14a  jmp     loc_1400AF205
0x1400af14f  mov     r9, rbx
0x1400af152  mov     [rbx], r10
0x1400af155  mov     r8, rbx
0x1400af158  mov     byte ptr [rsp+80h+var_60], 1
0x1400af15d  call    TcpEnqueueTcbInput
0x1400af162  mov     rax, [rbx+8]
0x1400af166  mov     ecx, [rax+18h]
0x1400af169  mov     [r12], rcx
0x1400af16d  jmp     loc_1400AF223
0x1400af172  mov     rdi, [rbp+var_28]
0x1400af176  test    rdi, rdi
0x1400af179  jz      loc_1400AF383
0x1400af17f  mov     rax, [rbp+var_38]
0x1400af183  mov     r8, [rbp+var_18]
0x1400af187  mov     [rax], rdi
0x1400af18a  cmp     [rbp+arg_10], 0
0x1400af18e  jnz     short loc_1400AF194
0x1400af190  mov     [rbp+var_38], rdi
0x1400af194  lea     rax, [rbp+var_30]
0x1400af198  mov     [rsp+80h+var_50], rax
0x1400af19d  lea     r9, [rbp+arg_10]
0x1400af1a1  mov     byte ptr [rsp+80h+var_58], 0
0x1400af1a6  lea     rdx, [rbp+arg_18]
0x1400af1aa  mov     [rsp+80h+var_60], r8
0x1400af1af  lea     rcx, [rbp+var_20]
0x1400af1b3  lea     r8, [rbp+var_38]
0x1400af1b7  call    cs:__imp_RtlCopyMdlToMdlIndirect
0x1400af1be  nop     dword ptr [rax+rax+00h]
0x1400af1c3  mov     rdx, [rbp+var_18]
0x1400af1c7  cmp     [rbp+var_30], rdx
0x1400af1cb  jnz     loc_1400AF445
0x1400af1d1  test    rsi, rsi
0x1400af1d4  jz      short loc_1400AF1DA
0x1400af1d6  mov     [r15+70h], rsi
0x1400af1da  mov     eax, [rbp+arg_10]
0x1400af1dd  test    eax, eax
0x1400af1df  mov     rcx, [r15+70h]
0x1400af1e3  cmovz   eax, r14d
0x1400af1e7  mov     [rcx+28h], eax
0x1400af1ea  mov     rax, [rbp+var_8]
0x1400af1ee  add     [rax+18h], edx
0x1400af1f1  cmp     dword ptr [rbx+88h], 0
0x1400af1f8  jge     short loc_1400AF205
0x1400af1fa  or      dword ptr [r15+88h], 80000000h
0x1400af205  mov     r8d, [rbp+arg_20]
0x1400af209  mov     rdx, rbx
0x1400af20c  mov     rcx, rbx
0x1400af20f  mov     qword ptr [rbx], 0
0x1400af216  call    TcpNetBufferListChainDelay
0x1400af21b  mov     rax, [rbp+var_30]
0x1400af21f  mov     [r12], rax
0x1400af223  xor     eax, eax
0x1400af225  mov     rbx, [rsp+80h+arg_0]
0x1400af22d  add     rsp, 80h
0x1400af234  pop     r15
0x1400af236  pop     r14
0x1400af238  pop     r13
0x1400af23a  pop     r12
0x1400af23c  pop     rdi
0x1400af23d  pop     rsi
0x1400af23e  pop     rbp
0x1400af23f  retn
0x1400af241  mov     r15, [r15+10h]
0x1400af245  test    r15, r15
0x1400af248  jz      loc_1400AF038
0x1400af24e  lea     rdi, TcpDelayedDeliveryCompletionRoutine
0x1400af255  cmp     [r15+50h], rdi
0x1400af259  jnz     loc_1400AF03F
0x1400af25f  mov     rax, [r15+8]
0x1400af263  mov     [rbp+var_8], rax
0x1400af267  cmp     dword ptr [rax+28h], 20000h
0x1400af26e  jnb     loc_1400AF03F
0x1400af274  mov     rdx, [r15+70h]
0x1400af278  mov     [rbp+var_38], rdx
0x1400af27c  test    rax, rax
0x1400af27f  jz      loc_1400AF03F
0x1400af285  mov     rcx, [rbx+8]
0x1400af289  mov     [rbp+var_40], r10d
0x1400af28d  mov     rax, [rcx+8]
0x1400af291  mov     r8d, [rcx+18h]
0x1400af295  mov     [rbp+var_20], rax
0x1400af299  mov     eax, [rcx+10h]
0x1400af29c  mov     [rbp+arg_18], eax
0x1400af29f  mov     eax, [rdx+28h]
0x1400af2a2  mov     [rbp+var_18], r8
0x1400af2a6  cmp     eax, r14d
0x1400af2a9  jnb     loc_1400AF36E
0x1400af2af  mov     [rbp+arg_10], eax
0x1400af2b2  mov     [rdx+28h], r14d
0x1400af2b6  mov     edx, [rbp+arg_10]
0x1400af2b9  mov     [rbp+var_40], eax
0x1400af2bc  test    edx, edx
0x1400af2be  jz      loc_1400AF36E
0x1400af2c4  lea     rcx, [r8+rdx]
0x1400af2c8  mov     eax, r14d
0x1400af2cb  mov     rsi, r10
0x1400af2ce  mov     rdi, r10
0x1400af2d1  cmp     rcx, rax
0x1400af2d4  jbe     loc_1400AF194
0x1400af2da  test    edx, edx
0x1400af2dc  jz      loc_1400AF36E
0x1400af2e2  mov     edi, r8d
0x1400af2e5  sub     edi, r14d
0x1400af2e8  add     edi, edx
0x1400af2ea  mov     rcx, [r13+350h]
0x1400af2f1  lea     r13, [rbp+var_28]
0x1400af2f5  mov     [rbp+var_10], rcx
0x1400af2f9  mov     [rbp+var_28], r10
0x1400af2fd  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400af304  test    rax, rax
0x1400af307  jnz     loc_1400AF3D5
0x1400af30d  mov     esi, [rbp+arg_20]
0x1400af310  mov     rcx, cs:TcpDelayedDeliveryMdlPool
0x1400af317  inc     esi
0x1400af319  shl     rsi, 7
0x1400af31d  add     rsi, rcx
0x1400af320  movzx   eax, byte ptr [rsi+0B0h]
0x1400af327  test    al, al
0x1400af329  jnz     short loc_1400AF334
0x1400af32b  lea     rdx, [rsi+40h]
0x1400af32f  call    PplpLazyInitializeLookasideList
0x1400af334  lea     rcx, [rsi+40h]; Lookaside
0x1400af338  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400af33f  nop     dword ptr [rax+rax+00h]
0x1400af344  test    rax, rax
0x1400af347  jz      short loc_1400AF376
0x1400af349  lea     rsi, [rax-40h]
0x1400af34d  sub     edi, 0FC0h
0x1400af353  mov     [r13+0], rsi
0x1400af357  test    edi, edi
0x1400af359  jle     loc_1400AF172
0x1400af35f  mov     rcx, [rbp+var_10]
0x1400af363  mov     r13, rsi
0x1400af366  mov     r9d, 1000h
0x1400af36c  jmp     short loc_1400AF2FD
0x1400af36e  mov     edi, r8d
0x1400af371  jmp     loc_1400AF2EA
0x1400af376  mov     rcx, [rbp+var_28]
0x1400af37a  test    rcx, rcx
0x1400af37d  jnz     loc_1400AF438
0x1400af383  mov     ecx, [rbp+arg_10]
0x1400af386  test    ecx, ecx
0x1400af388  jz      short loc_1400AF391
0x1400af38a  mov     rax, [rbp+var_38]
0x1400af38e  mov     [rax+28h], ecx
0x1400af391  mov     eax, 0C0000017h
0x1400af396  jmp     loc_1400AF225
0x1400af39b  mov     r9, [r13+350h]
0x1400af3a2  mov     ecx, edx
0x1400af3a4  mov     r8d, [rbp+arg_20]
0x1400af3a8  lea     rdx, [rbp+var_18]
0x1400af3ac  sub     ecx, r14d
0x1400af3af  mov     [rbp+var_18], 0
0x1400af3b7  call    TcpBuildMdlChain
0x1400af3bc  mov     rcx, [rbp+var_38]
0x1400af3c0  mov     [rcx], rax
0x1400af3c3  test    rax, rax
0x1400af3c6  jz      short loc_1400AF415
0x1400af3c8  mov     rax, [rbp+var_18]
0x1400af3cc  mov     rdx, [rbp+var_8]
0x1400af3d0  jmp     loc_1400AF0C8
0x1400af3d5  mov     rax, [rax]
0x1400af3d8  mov     rdx, rcx
0x1400af3db  mov     ecx, r9d
0x1400af3de  call    _guard_dispatch_icall
0x1400af3e3  mov     [r13+0], rax
0x1400af3e7  mov     rsi, rax
0x1400af3ea  test    rax, rax
0x1400af3ed  jz      short loc_1400AF42B
0x1400af3ef  sub     edi, 1000h
0x1400af3f5  jmp     loc_1400AF357
0x1400af3fa  mov     dl, 1
0x1400af3fc  mov     rcx, r15
0x1400af3ff  call    cs:__imp_NetioDereferenceNetBufferList
0x1400af406  nop     dword ptr [rax+rax+00h]
0x1400af40b  mov     eax, 0C0000001h
0x1400af410  jmp     loc_1400AF225
0x1400af415  mov     dl, 1
0x1400af417  mov     rcx, r15
0x1400af41a  call    cs:__imp_NetioDereferenceNetBufferList
0x1400af421  nop     dword ptr [rax+rax+00h]
0x1400af426  jmp     loc_1400AF391
0x1400af42b  mov     rcx, [rbp+var_28]
0x1400af42f  test    rcx, rcx
0x1400af432  jz      loc_1400AF383
0x1400af438  mov     edx, [rbp+arg_20]
0x1400af43b  call    TcpDestroyMdlChain
0x1400af440  jmp     loc_1400AF383
0x1400af445  mov     ecx, [rbp+var_40]
0x1400af448  test    rsi, rsi
0x1400af44b  jz      loc_1401C98AC
0x1400af451  test    ecx, ecx
0x1400af453  jz      loc_1401C9894
0x1400af459  mov     rax, [r15+70h]
0x1400af45d  mov     [rax+28h], ecx
0x1400af460  jmp     loc_1401C9894
0x1401c9894  mov     edx, [rbp+arg_20]
0x1401c9897  mov     rcx, rdi
0x1401c989a  call    TcpDestroyMdlChain
0x1401c989f  mov     rax, [r15+70h]
0x1401c98a3  mov     qword ptr [rax], 0
0x1401c98aa  jmp     short loc_1401C98B3
0x1401c98ac  mov     rax, [r15+70h]
0x1401c98b0  mov     [rax+28h], ecx
0x1401c98b3  mov     eax, 0C0000001h
0x1401c98b8  jmp     loc_1400AF225
0x1401c98bd  mov     rdx, [rcx+350h]
0x1401c98c4  mov     ecx, r14d
0x1401c98c7  mov     rax, [r8]
  ... truncated ...
```
