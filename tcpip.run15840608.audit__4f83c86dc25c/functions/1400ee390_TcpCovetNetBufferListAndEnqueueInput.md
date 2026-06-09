# TcpCovetNetBufferListAndEnqueueInput

- ea: `0x1400ee390`
- end: `0x1400ee89e`
- name: `TcpCovetNetBufferListAndEnqueueInput`
- size: `1294`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400a2d20`

## callees

- `0x14000e120`
- `0x1400148e0`
- `0x140014974`
- `0x1400ee390`
- `0x1400ee8a4`
- `0x1400ee940`
- `0x1400eeac0`
- `0x1401c1200`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400ee71d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400ee71d`
- `NETIO!NetioDereferenceNetBufferList` at `0x1400ee825`
- `NETIO!NetioDereferenceNetBufferList` at `0x1400ee840`
- `NETIO!NetioDereferenceNetBufferList` at `0x1400ee825`
- `NETIO!NetioDereferenceNetBufferList` at `0x1400ee840`
- `NETIO!NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData` at `0x1400ee432`
- `NETIO!NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData` at `0x1400ee432`
- `NETIO!RtlCopyMdlToMdlIndirect` at `0x1400ee4e4`
- `NETIO!RtlCopyMdlToMdlIndirect` at `0x1400ee59b`
- `NETIO!RtlCopyMdlToMdlIndirect` at `0x1400ee4e4`
- `NETIO!RtlCopyMdlToMdlIndirect` at `0x1400ee59b`
- `NETIO!NetioAllocateAndReferenceNetBufferAndNetBufferList` at `0x1401d30c9`
- `NETIO!NetioAllocateAndReferenceNetBufferAndNetBufferList` at `0x1401d30c9`

## pseudocode

```c
__int64 __fastcall TcpCovetNetBufferListAndEnqueueInput(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        unsigned int a5)
{
  struct _LIST_ENTRY *Blink; // rdx
  unsigned int v7; // r14d
  bool v8; // zf
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
  __int64 v22; // rax
  __int64 v23; // rdi
  __int64 v24; // r9
  int v25; // edx
  unsigned int v26; // eax
  __int64 v27; // r8
  __int64 v29; // r15
  __int64 v30; // rax
  __int64 v31; // r8
  __int64 v32; // rcx
  unsigned int v33; // eax
  __int64 *v34; // rsi
  int v35; // edi
  __int64 v36; // rcx
  __int64 *v37; // r13
  char *v38; // rsi
  char *v39; // rax
  _QWORD *v40; // rcx
  _QWORD *i; // rdi
  _QWORD *v42; // rax
  __int64 v43; // rcx
  __int64 v44; // r9
  __int64 v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rax
  __int64 v48; // rax
  int v49; // [rsp+28h] [rbp-58h]
  unsigned int v50; // [rsp+40h] [rbp-40h]
  __int64 v51; // [rsp+48h] [rbp-38h] BYREF
  __int64 v52; // [rsp+50h] [rbp-30h] BYREF
  __int64 v53; // [rsp+58h] [rbp-28h] BYREF
  __int64 v54; // [rsp+60h] [rbp-20h] BYREF
  __int64 v55; // [rsp+68h] [rbp-18h] BYREF
  __int64 v56; // [rsp+70h] [rbp-10h]
  __int64 v57; // [rsp+78h] [rbp-8h]
  unsigned int v58; // [rsp+D0h] [rbp+50h] BYREF
  int v59; // [rsp+D8h] [rbp+58h] BYREF

  Blink = WPP_MAIN_CB.Queue.ListEntry.Blink;
  v7 = 4032;
  v51 = 0;
  v54 = 0;
  if ( WPP_MAIN_CB.Queue.ListEntry.Blink )
    v7 = 4096;
  v58 = 0;
  v8 = (*(_DWORD *)(a3 + 136) & 0x10000000) == 0;
  v59 = 0;
  v52 = 0;
  *a4 = 0;
  if ( !v8 )
  {
    *(_QWORD *)a3 = 0;
    v22 = *(_QWORD *)(a2 + 64);
    if ( v22 )
    {
      if ( *(_QWORD *)(v22 + 8) )
      {
        **(_QWORD **)(v22 + 16) = a3;
LABEL_18:
        *(_QWORD *)(*(_QWORD *)(a2 + 64) + 16LL) = a3;
LABEL_19:
        *a4 = *(unsigned int *)(*(_QWORD *)(a3 + 8) + 24LL);
        return 0;
      }
    }
    else
    {
      v40 = *(_QWORD **)(a2 + 40);
      for ( i = (_QWORD *)(a2 + 40); v40; v40 = (_QWORD *)*v40 )
        i = v40;
      v42 = (_QWORD *)PplAllocateFromLookasideList(TcpInputPool);
      *i = v42;
      if ( !v42 )
        goto LABEL_19;
      *(_QWORD *)(a2 + 64) = v42;
      *v42 = 0;
      v22 = *(_QWORD *)(a2 + 64);
    }
    *(_QWORD *)(v22 + 8) = a3;
    goto LABEL_18;
  }
  v12 = *(_QWORD *)(a2 + 64);
  if ( v12 )
  {
    v29 = *(_QWORD *)(v12 + 16);
    if ( v29 )
    {
      if ( *(__int64 (__fastcall **)(PNET_BUFFER_LIST))(v29 + 80) == TcpDelayedDeliveryCompletionRoutine )
      {
        v30 = *(_QWORD *)(v29 + 8);
        v57 = v30;
        if ( *(_DWORD *)(v30 + 40) < 0x20000u )
        {
          v31 = *(_QWORD *)(v29 + 112);
          v51 = v31;
          if ( v30 )
          {
            v32 = *(_QWORD *)(a3 + 8);
            v50 = 0;
            v24 = *(unsigned int *)(v32 + 24);
            v54 = *(_QWORD *)(v32 + 8);
            v59 = *(_DWORD *)(v32 + 16);
            v33 = *(_DWORD *)(v31 + 40);
            v55 = v24;
            if ( v33 >= v7 )
              goto LABEL_49;
            v58 = v33;
            *(_DWORD *)(v31 + 40) = v7;
            v50 = v33;
            if ( !v58 )
              goto LABEL_49;
            v34 = 0;
            v23 = 0;
            if ( v24 + (unsigned __int64)v58 > v7 )
            {
              if ( v58 )
              {
                v35 = v58 + v24 - v7;
                goto LABEL_41;
              }
LABEL_49:
              v35 = v24;
LABEL_41:
              v36 = *(_QWORD *)(a1 + 848);
              v37 = &v53;
              v56 = v36;
              v53 = 0;
              while ( 1 )
              {
                if ( WPP_MAIN_CB.Queue.ListEntry.Blink )
                {
                  v47 = ((__int64 (__fastcall *)(__int64, __int64))WPP_MAIN_CB.Queue.ListEntry.Blink->Flink)(4096, v36);
                  *v37 = v47;
                  v34 = (__int64 *)v47;
                  if ( !v47 )
                  {
                    v43 = v53;
                    if ( !v53 )
                      goto LABEL_55;
                    goto LABEL_65;
                  }
                  v35 -= 4096;
                }
                else
                {
                  v38 = (char *)TcpDelayedDeliveryMdlPool + 128 * (unsigned __int64)(a5 + 1);
                  if ( !v38[176] )
                    PplpLazyInitializeLookasideList(TcpDelayedDeliveryMdlPool, v38 + 64);
                  v39 = (char *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v38 + 64));
                  if ( !v39 )
                  {
                    v43 = v53;
                    if ( !v53 )
                      goto LABEL_55;
LABEL_65:
                    TcpDestroyMdlChain(v43, a5);
                    goto LABEL_55;
                  }
                  v34 = (__int64 *)(v39 - 64);
                  v35 -= 4032;
                  *v37 = (__int64)(v39 - 64);
                }
                if ( v35 <= 0 )
                  break;
                v36 = v56;
                v37 = v34;
              }
              v23 = v53;
              if ( v53 )
              {
                v24 = v55;
                *(_QWORD *)v51 = v53;
                if ( !v58 )
                  v51 = v23;
                goto LABEL_23;
              }
LABEL_55:
              if ( v58 )
                *(_DWORD *)(v51 + 40) = v58;
              return 3221225495LL;
            }
LABEL_23:
            RtlCopyMdlToMdlIndirect(&v54, &v59, &v51, &v58, v24, 0, &v52);
            v25 = v55;
            if ( v52 == v55 )
            {
              if ( v34 )
                *(_QWORD *)(v29 + 112) = v34;
              v26 = v58;
              if ( !v58 )
                v26 = v7;
              *(_DWORD *)(*(_QWORD *)(v29 + 112) + 40LL) = v26;
              *(_DWORD *)(v57 + 24) += v25;
              if ( *(int *)(a3 + 136) < 0 )
                *(_DWORD *)(v29 + 136) |= 0x80000000;
              goto LABEL_30;
            }
            if ( v34 )
            {
              if ( v50 )
                *(_DWORD *)(*(_QWORD *)(v29 + 112) + 40LL) = v50;
              TcpDestroyMdlChain(v23, a5);
              **(_QWORD **)(v29 + 112) = 0;
            }
            else
            {
              *(_DWORD *)(*(_QWORD *)(v29 + 112) + 40LL) = v50;
            }
            return 3221225473LL;
          }
        }
      }
    }
  }
  if ( Blink )
  {
    v48 = ((__int64 (__fastcall *)(_QWORD, _QWORD))Blink->Flink)(v7, *(_QWORD *)(a1 + 848));
    v57 = v48;
    if ( !v48 )
      return 3221225495LL;
    v13 = NetioAllocateAndReferenceNetBufferAndNetBufferList(TcpDelayedDeliveryCompletionRoutine, 0, v48, 0, v7, 1);
    if ( !v13 )
    {
      ((void (__fastcall *)(__int64))WPP_MAIN_CB.Queue.ListEntry.Blink->Blink)(v57);
      return 3221225495LL;
    }
  }
  else
  {
    v49 = 0;
    v13 = NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData(TcpDelayedDeliveryNblPool, v7, 0);
    if ( !v13 )
      return 3221225495LL;
  }
  if ( *(int *)(a3 + 136) < 0 )
    *(_DWORD *)(v13 + 136) |= 0x80000000;
  *(_DWORD *)(v13 + 136) |= 0x10000000u;
  v14 = *(_QWORD *)(a3 + 8);
  v15 = *(unsigned int *)(v14 + 24);
  v54 = *(_QWORD *)(v14 + 8);
  v59 = *(_DWORD *)(v14 + 16);
  v16 = *(_QWORD *)(v13 + 8);
  v57 = v15;
  v51 = *(_QWORD *)(v16 + 32);
  if ( (unsigned int)v15 > v7 )
  {
    v44 = *(_QWORD *)(a1 + 848);
    v55 = 0;
    v45 = TcpBuildMdlChain((unsigned int)v15 - v7, &v55, a5, v44);
    *(_QWORD *)v51 = v45;
    if ( v45 )
    {
      v17 = v55;
      LODWORD(v15) = v57;
      goto LABEL_11;
    }
    LOBYTE(v46) = 1;
    NetioDereferenceNetBufferList(v13, v46);
    return 3221225495LL;
  }
  v17 = *(_QWORD *)(v16 + 8);
LABEL_11:
  *(_QWORD *)(v13 + 112) = v17;
  *(_QWORD *)(v16 + 80) = 0;
  *(_DWORD *)(v16 + 40) = 0;
  v58 = 0;
  *(_DWORD *)(v16 + 24) = v15;
  *(_DWORD *)(v16 + 16) = 0;
  v18 = (unsigned int)v15;
  LOBYTE(v49) = 0;
  RtlCopyMdlToMdlIndirect(&v54, &v59, &v51, &v58, (unsigned int)v15, v49, &v52);
  if ( v52 == v18 )
  {
    v20 = v58;
    v21 = *(_QWORD *)(v13 + 112);
    if ( !v58 )
      v20 = v7;
    *(_DWORD *)(v21 + 40) = v20;
    TcpEnqueueTcbInput(v21, a2, v13, v13);
LABEL_30:
    v27 = a5;
    *(_QWORD *)a3 = 0;
    TcpNetBufferListChainDelay(a3, a3, v27);
    *a4 = v52;
    return 0;
  }
  LOBYTE(v19) = 1;
  NetioDereferenceNetBufferList(v13, v19);
  return 3221225473LL;
}

```

## disassembly

```asm
0x1400ee390  mov     [rsp-38h+arg_0], rbx
0x1400ee395  push    rbp
0x1400ee396  push    rsi
0x1400ee397  push    rdi
0x1400ee398  push    r12
0x1400ee39a  push    r13
0x1400ee39c  push    r14
0x1400ee39e  push    r15
0x1400ee3a0  mov     rbp, rsp
0x1400ee3a3  sub     rsp, 80h
0x1400ee3aa  xor     r10d, r10d
0x1400ee3ad  mov     rsi, rdx
0x1400ee3b0  mov     rdx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400ee3b7  mov     r14d, 0FC0h
0x1400ee3bd  test    rdx, rdx
0x1400ee3c0  mov     [rbp+var_38], r10
0x1400ee3c4  mov     r11d, 1000h
0x1400ee3ca  mov     [rbp+var_20], r10
0x1400ee3ce  cmovnz  r14d, r11d
0x1400ee3d2  mov     [rbp+arg_10], r10d
0x1400ee3d6  test    dword ptr [r8+88h], 10000000h
0x1400ee3e1  mov     r12, r9
0x1400ee3e4  mov     rbx, r8
0x1400ee3e7  mov     [rbp+arg_18], r10d
0x1400ee3eb  mov     r13, rcx
0x1400ee3ee  mov     [rbp+var_30], r10
0x1400ee3f2  mov     [r9], r10
0x1400ee3f5  jnz     loc_1400EE51D
0x1400ee3fb  mov     r15, [rsi+40h]
0x1400ee3ff  test    r15, r15
0x1400ee402  jnz     loc_1400EE625
0x1400ee408  lea     rdi, TcpDelayedDeliveryCompletionRoutine
0x1400ee40f  test    rdx, rdx
0x1400ee412  jnz     loc_1401D3095
0x1400ee418  mov     rcx, cs:TcpDelayedDeliveryNblPool
0x1400ee41f  xor     r9d, r9d
0x1400ee422  mov     [rsp+80h+var_58], r10
0x1400ee427  xor     r8d, r8d
0x1400ee42a  mov     edx, r14d
0x1400ee42d  mov     [rsp+80h+var_60], rdi
0x1400ee432  call    cs:__imp_NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData
0x1400ee439  nop     dword ptr [rax+rax+00h]
0x1400ee43e  mov     r15, rax
0x1400ee441  test    rax, rax
0x1400ee444  jz      loc_1400EE7B7
0x1400ee44a  cmp     dword ptr [rbx+88h], 0
0x1400ee451  jge     short loc_1400EE45E
0x1400ee453  or      dword ptr [r15+88h], 80000000h
0x1400ee45e  or      dword ptr [r15+88h], 10000000h
0x1400ee469  mov     rcx, [rbx+8]
0x1400ee46d  mov     rax, [rcx+8]
0x1400ee471  mov     edx, [rcx+18h]
0x1400ee474  mov     [rbp+var_20], rax
0x1400ee478  mov     eax, [rcx+10h]
0x1400ee47b  mov     [rbp+arg_18], eax
0x1400ee47e  mov     rdi, [r15+8]
0x1400ee482  mov     [rbp+var_8], rdx
0x1400ee486  mov     rax, [rdi+20h]
0x1400ee48a  mov     [rbp+var_38], rax
0x1400ee48e  cmp     edx, r14d
0x1400ee491  ja      loc_1400EE7C1
0x1400ee497  mov     rax, [rdi+8]
0x1400ee49b  mov     [r15+70h], rax
0x1400ee49f  lea     r9, [rbp+arg_10]
0x1400ee4a3  mov     qword ptr [rdi+50h], 0
0x1400ee4ab  lea     rax, [rbp+var_30]
0x1400ee4af  mov     dword ptr [rdi+28h], 0
0x1400ee4b6  lea     r8, [rbp+var_38]
0x1400ee4ba  mov     [rbp+arg_10], 0
0x1400ee4c1  lea     rcx, [rbp+var_20]
0x1400ee4c5  mov     [rdi+18h], edx
0x1400ee4c8  mov     [rsp+80h+var_50], rax
0x1400ee4cd  mov     dword ptr [rdi+10h], 0
0x1400ee4d4  mov     edi, edx
0x1400ee4d6  lea     rdx, [rbp+arg_18]
0x1400ee4da  mov     byte ptr [rsp+80h+var_58], 0
0x1400ee4df  mov     [rsp+80h+var_60], rdi
0x1400ee4e4  call    cs:__imp_RtlCopyMdlToMdlIndirect
0x1400ee4eb  nop     dword ptr [rax+rax+00h]
0x1400ee4f0  cmp     [rbp+var_30], rdi
0x1400ee4f4  jnz     loc_1400EE820
0x1400ee4fa  mov     eax, [rbp+arg_10]
0x1400ee4fd  mov     r9, r15
0x1400ee500  mov     rcx, [r15+70h]
0x1400ee504  test    eax, eax
0x1400ee506  mov     r8, r15
0x1400ee509  mov     rdx, rsi
0x1400ee50c  cmovz   eax, r14d
0x1400ee510  mov     [rcx+28h], eax
0x1400ee513  call    TcpEnqueueTcbInput
0x1400ee518  jmp     loc_1400EE5E9
0x1400ee51d  mov     [r8], r10
0x1400ee520  mov     rax, [rsi+40h]
0x1400ee524  test    rax, rax
0x1400ee527  jz      loc_1400EE75B
0x1400ee52d  cmp     [rax+8], r10
0x1400ee531  jz      loc_1400EE793
0x1400ee537  mov     rax, [rax+10h]
0x1400ee53b  mov     [rax], rbx
0x1400ee53e  mov     rax, [rsi+40h]
0x1400ee542  mov     [rax+10h], rbx
0x1400ee546  mov     rax, [rbx+8]
0x1400ee54a  mov     ecx, [rax+18h]
0x1400ee54d  mov     [r12], rcx
0x1400ee551  jmp     loc_1400EE607
0x1400ee556  mov     rdi, [rbp+var_28]
0x1400ee55a  test    rdi, rdi
0x1400ee55d  jz      loc_1400EE7A9
0x1400ee563  mov     rax, [rbp+var_38]
0x1400ee567  mov     r9, [rbp+var_18]
0x1400ee56b  mov     [rax], rdi
0x1400ee56e  cmp     [rbp+arg_10], 0
0x1400ee572  jnz     short loc_1400EE578
0x1400ee574  mov     [rbp+var_38], rdi
0x1400ee578  lea     rax, [rbp+var_30]
0x1400ee57c  mov     [rsp+80h+var_50], rax
0x1400ee581  lea     r8, [rbp+var_38]
0x1400ee585  mov     byte ptr [rsp+80h+var_58], 0
0x1400ee58a  lea     rdx, [rbp+arg_18]
0x1400ee58e  mov     [rsp+80h+var_60], r9
0x1400ee593  lea     rcx, [rbp+var_20]
0x1400ee597  lea     r9, [rbp+arg_10]
0x1400ee59b  call    cs:__imp_RtlCopyMdlToMdlIndirect
0x1400ee5a2  nop     dword ptr [rax+rax+00h]
0x1400ee5a7  mov     rdx, [rbp+var_18]
0x1400ee5ab  cmp     [rbp+var_30], rdx
0x1400ee5af  jnz     loc_1400EE86B
0x1400ee5b5  test    rsi, rsi
0x1400ee5b8  jz      short loc_1400EE5BE
0x1400ee5ba  mov     [r15+70h], rsi
0x1400ee5be  mov     eax, [rbp+arg_10]
0x1400ee5c1  test    eax, eax
0x1400ee5c3  mov     rcx, [r15+70h]
0x1400ee5c7  cmovz   eax, r14d
0x1400ee5cb  mov     [rcx+28h], eax
0x1400ee5ce  mov     rax, [rbp+var_8]
0x1400ee5d2  add     [rax+18h], edx
0x1400ee5d5  cmp     dword ptr [rbx+88h], 0
0x1400ee5dc  jge     short loc_1400EE5E9
0x1400ee5de  or      dword ptr [r15+88h], 80000000h
0x1400ee5e9  mov     r8d, [rbp+arg_20]
0x1400ee5ed  mov     rdx, rbx
0x1400ee5f0  mov     rcx, rbx
0x1400ee5f3  mov     qword ptr [rbx], 0
0x1400ee5fa  call    TcpNetBufferListChainDelay
0x1400ee5ff  mov     rax, [rbp+var_30]
0x1400ee603  mov     [r12], rax
0x1400ee607  xor     eax, eax
0x1400ee609  mov     rbx, [rsp+80h+arg_0]
0x1400ee611  add     rsp, 80h
0x1400ee618  pop     r15
0x1400ee61a  pop     r14
0x1400ee61c  pop     r13
0x1400ee61e  pop     r12
0x1400ee620  pop     rdi
0x1400ee621  pop     rsi
0x1400ee622  pop     rbp
0x1400ee623  retn
0x1400ee625  mov     r15, [r15+10h]
0x1400ee629  test    r15, r15
0x1400ee62c  jz      loc_1400EE408
0x1400ee632  lea     rdi, TcpDelayedDeliveryCompletionRoutine
0x1400ee639  cmp     [r15+50h], rdi
0x1400ee63d  jnz     loc_1400EE40F
0x1400ee643  mov     rax, [r15+8]
0x1400ee647  mov     [rbp+var_8], rax
0x1400ee64b  cmp     dword ptr [rax+28h], 20000h
0x1400ee652  jnb     loc_1400EE40F
0x1400ee658  mov     r8, [r15+70h]
0x1400ee65c  mov     [rbp+var_38], r8
0x1400ee660  test    rax, rax
0x1400ee663  jz      loc_1400EE40F
0x1400ee669  mov     rcx, [rbx+8]
0x1400ee66d  mov     [rbp+var_40], r10d
0x1400ee671  mov     rax, [rcx+8]
0x1400ee675  mov     r9d, [rcx+18h]
0x1400ee679  mov     [rbp+var_20], rax
0x1400ee67d  mov     eax, [rcx+10h]
0x1400ee680  mov     [rbp+arg_18], eax
0x1400ee683  mov     eax, [r8+28h]
0x1400ee687  mov     [rbp+var_18], r9
0x1400ee68b  cmp     eax, r14d
0x1400ee68e  jnb     loc_1400EE753
0x1400ee694  mov     [rbp+arg_10], eax
0x1400ee697  mov     [r8+28h], r14d
0x1400ee69b  mov     edx, [rbp+arg_10]
0x1400ee69e  mov     [rbp+var_40], eax
0x1400ee6a1  test    edx, edx
0x1400ee6a3  jz      loc_1400EE753
0x1400ee6a9  lea     rcx, [r9+rdx]
0x1400ee6ad  mov     eax, r14d
0x1400ee6b0  mov     rsi, r10
0x1400ee6b3  mov     rdi, r10
0x1400ee6b6  cmp     rcx, rax
0x1400ee6b9  jbe     loc_1400EE578
0x1400ee6bf  test    edx, edx
0x1400ee6c1  jz      loc_1400EE753
0x1400ee6c7  mov     edi, r9d
0x1400ee6ca  sub     edi, r14d
0x1400ee6cd  add     edi, edx
0x1400ee6cf  mov     rcx, [r13+350h]
0x1400ee6d6  lea     r13, [rbp+var_28]
0x1400ee6da  mov     [rbp+var_10], rcx
0x1400ee6de  mov     [rbp+var_28], r10
0x1400ee6e2  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400ee6e9  test    rax, rax
0x1400ee6ec  jnz     loc_1400EE7FB
0x1400ee6f2  mov     esi, [rbp+arg_20]
0x1400ee6f5  mov     rcx, cs:TcpDelayedDeliveryMdlPool
0x1400ee6fc  inc     esi
0x1400ee6fe  shl     rsi, 7
0x1400ee702  add     rsi, rcx
0x1400ee705  movzx   eax, byte ptr [rsi+0B0h]
0x1400ee70c  test    al, al
0x1400ee70e  jnz     short loc_1400EE719
0x1400ee710  lea     rdx, [rsi+40h]
0x1400ee714  call    PplpLazyInitializeLookasideList
0x1400ee719  lea     rcx, [rsi+40h]; Lookaside
0x1400ee71d  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400ee724  nop     dword ptr [rax+rax+00h]
0x1400ee729  test    rax, rax
0x1400ee72c  jz      short loc_1400EE79C
0x1400ee72e  lea     rsi, [rax-40h]
0x1400ee732  sub     edi, 0FC0h
0x1400ee738  mov     [r13+0], rsi
0x1400ee73c  test    edi, edi
0x1400ee73e  jle     loc_1400EE556
0x1400ee744  mov     rcx, [rbp+var_10]
0x1400ee748  mov     r13, rsi
0x1400ee74b  mov     r11d, 1000h
0x1400ee751  jmp     short loc_1400EE6E2
0x1400ee753  mov     edi, r9d
0x1400ee756  jmp     loc_1400EE6CF
0x1400ee75b  mov     rcx, [rsi+28h]
0x1400ee75f  lea     rdi, [rsi+28h]
0x1400ee763  test    rcx, rcx
0x1400ee766  jnz     loc_1400EE88B
0x1400ee76c  mov     rcx, cs:TcpInputPool
0x1400ee773  call    PplAllocateFromLookasideList
0x1400ee778  mov     [rdi], rax
0x1400ee77b  test    rax, rax
0x1400ee77e  jz      loc_1400EE546
0x1400ee784  mov     [rsi+40h], rax
0x1400ee788  mov     qword ptr [rax], 0
0x1400ee78f  mov     rax, [rsi+40h]
0x1400ee793  mov     [rax+8], rbx
0x1400ee797  jmp     loc_1400EE53E
0x1400ee79c  mov     rcx, [rbp+var_28]
0x1400ee7a0  test    rcx, rcx
0x1400ee7a3  jnz     loc_1400EE85E
0x1400ee7a9  mov     ecx, [rbp+arg_10]
0x1400ee7ac  test    ecx, ecx
0x1400ee7ae  jz      short loc_1400EE7B7
0x1400ee7b0  mov     rax, [rbp+var_38]
0x1400ee7b4  mov     [rax+28h], ecx
0x1400ee7b7  mov     eax, 0C0000017h
0x1400ee7bc  jmp     loc_1400EE609
0x1400ee7c1  mov     r9, [r13+350h]
0x1400ee7c8  mov     ecx, edx
0x1400ee7ca  mov     r8d, [rbp+arg_20]
0x1400ee7ce  lea     rdx, [rbp+var_18]
0x1400ee7d2  sub     ecx, r14d
0x1400ee7d5  mov     [rbp+var_18], 0
0x1400ee7dd  call    TcpBuildMdlChain
0x1400ee7e2  mov     rcx, [rbp+var_38]
0x1400ee7e6  mov     [rcx], rax
0x1400ee7e9  test    rax, rax
0x1400ee7ec  jz      short loc_1400EE83B
0x1400ee7ee  mov     rax, [rbp+var_18]
0x1400ee7f2  mov     rdx, [rbp+var_8]
0x1400ee7f6  jmp     loc_1400EE49B
0x1400ee7fb  mov     rax, [rax]
0x1400ee7fe  mov     rdx, rcx
0x1400ee801  mov     ecx, r11d
0x1400ee804  call    _guard_dispatch_icall
0x1400ee809  mov     [r13+0], rax
0x1400ee80d  mov     rsi, rax
0x1400ee810  test    rax, rax
0x1400ee813  jz      short loc_1400EE851
0x1400ee815  sub     edi, 1000h
0x1400ee81b  jmp     loc_1400EE73C
0x1400ee820  mov     dl, 1
0x1400ee822  mov     rcx, r15
0x1400ee825  call    cs:__imp_NetioDereferenceNetBufferList
0x1400ee82c  nop     dword ptr [rax+rax+00h]
0x1400ee831  mov     eax, 0C0000001h
0x1400ee836  jmp     loc_1400EE609
0x1400ee83b  mov     dl, 1
0x1400ee83d  mov     rcx, r15
0x1400ee840  call    cs:__imp_NetioDereferenceNetBufferList
0x1400ee847  nop     dword ptr [rax+rax+00h]
0x1400ee84c  jmp     loc_1400EE7B7
0x1400ee851  mov     rcx, [rbp+var_28]
0x1400ee855  test    rcx, rcx
0x1400ee858  jz      loc_1400EE7A9
0x1400ee85e  mov     edx, [rbp+arg_20]
0x1400ee861  call    TcpDestroyMdlChain
0x1400ee866  jmp     loc_1400EE7A9
0x1400ee86b  mov     ecx, [rbp+var_40]
0x1400ee86e  test    rsi, rsi
  ... truncated ...
```
