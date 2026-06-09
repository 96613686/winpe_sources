# TcpCovetNetBufferListAndEnqueueInput

- ea: `0x1400aebe0`
- end: `0x1400af085`
- name: `TcpCovetNetBufferListAndEnqueueInput`
- size: `1189`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400ad0a8`

## callees

- `0x1400540a4`
- `0x1400aebe0`
- `0x1400af0d0`
- `0x1400af5d8`
- `0x1400af6b0`
- `0x1400af830`
- `0x1401bf700`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400aef58`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400aef58`
- `NETIO!NetioDereferenceNetBufferList` at `0x1400af01f`
- `NETIO!NetioDereferenceNetBufferList` at `0x1400af03a`
- `NETIO!NetioDereferenceNetBufferList` at `0x1400af01f`
- `NETIO!NetioDereferenceNetBufferList` at `0x1400af03a`
- `NETIO!NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData` at `0x1400aec7f`
- `NETIO!NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData` at `0x1400aec7f`
- `NETIO!RtlCopyMdlToMdlIndirect` at `0x1400aed31`
- `NETIO!RtlCopyMdlToMdlIndirect` at `0x1400aedd7`
- `NETIO!RtlCopyMdlToMdlIndirect` at `0x1400aed31`
- `NETIO!RtlCopyMdlToMdlIndirect` at `0x1400aedd7`
- `NETIO!NetioAllocateAndReferenceNetBufferAndNetBufferList` at `0x1401c9a15`
- `NETIO!NetioAllocateAndReferenceNetBufferAndNetBufferList` at `0x1401c9a15`

## pseudocode

```c
__int64 __fastcall TcpCovetNetBufferListAndEnqueueInput(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        unsigned int a5)
{
  PDRIVER_CONTROL DeviceRoutine; // r8
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

  DeviceRoutine = WPP_MAIN_CB.Queue.Wcb.DeviceRoutine;
  v47 = 0;
  v8 = 4032;
  v50 = 0;
  v54 = 0;
  if ( WPP_MAIN_CB.Queue.Wcb.DeviceRoutine )
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
                if ( WPP_MAIN_CB.Queue.Wcb.DeviceRoutine )
                {
                  v43 = (*(__int64 (__fastcall **)(__int64, __int64))WPP_MAIN_CB.Queue.Wcb.DeviceRoutine)(4096, v35);
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
  if ( DeviceRoutine )
  {
    v44 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))DeviceRoutine)(v8, *(_QWORD *)(a1 + 848));
    v53 = v44;
    if ( !v44 )
      return 3221225495LL;
    v13 = NetioAllocateAndReferenceNetBufferAndNetBufferList(TcpDelayedDeliveryCompletionRoutine, 0, v44, 0, v8, 1);
    if ( !v13 )
    {
      (*((void (__fastcall **)(__int64))WPP_MAIN_CB.Queue.Wcb.DeviceRoutine + 1))(v53);
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
0x1400aebe0  mov     [rsp-38h+arg_0], rbx
0x1400aebe5  push    rbp
0x1400aebe6  push    rsi
0x1400aebe7  push    rdi
0x1400aebe8  push    r12
0x1400aebea  push    r13
0x1400aebec  push    r14
0x1400aebee  push    r15
0x1400aebf0  mov     rbp, rsp
0x1400aebf3  sub     rsp, 80h
0x1400aebfa  xor     r10d, r10d
0x1400aebfd  mov     rbx, r8
0x1400aec00  mov     r8, qword ptr cs:WPP_MAIN_CB.Queue+18h
0x1400aec07  mov     r12, r9
0x1400aec0a  test    r8, r8
0x1400aec0d  mov     [rbp+var_38], r10
0x1400aec11  mov     r14d, 0FC0h
0x1400aec17  mov     [rbp+var_20], r10
0x1400aec1b  mov     r9d, 1000h
0x1400aec21  mov     [rbp+arg_10], r10d
0x1400aec25  cmovnz  r14d, r9d
0x1400aec29  mov     [rbp+arg_18], r10d
0x1400aec2d  test    dword ptr [rbx+88h], 10000000h
0x1400aec37  mov     rsi, rdx
0x1400aec3a  mov     r13, rcx
0x1400aec3d  mov     [rbp+var_30], r10
0x1400aec41  mov     [r12], r10
0x1400aec45  jnz     loc_1400AED6F
0x1400aec4b  mov     r15, [rdx+40h]
0x1400aec4f  test    r15, r15
0x1400aec52  jnz     loc_1400AEE61
0x1400aec58  lea     rdi, TcpDelayedDeliveryCompletionRoutine
0x1400aec5f  test    r8, r8
0x1400aec62  jnz     loc_1401C99E1
0x1400aec68  mov     rcx, cs:TcpDelayedDeliveryNblPool
0x1400aec6f  xor     r9d, r9d
0x1400aec72  mov     [rsp+80h+var_58], r10
0x1400aec77  mov     edx, r14d
0x1400aec7a  mov     [rsp+80h+var_60], rdi
0x1400aec7f  call    cs:__imp_NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData
0x1400aec86  nop     dword ptr [rax+rax+00h]
0x1400aec8b  mov     r15, rax
0x1400aec8e  test    rax, rax
0x1400aec91  jz      loc_1400AEFB1
0x1400aec97  cmp     dword ptr [rbx+88h], 0
0x1400aec9e  jge     short loc_1400AECAB
0x1400aeca0  or      dword ptr [r15+88h], 80000000h
0x1400aecab  or      dword ptr [r15+88h], 10000000h
0x1400aecb6  mov     rcx, [rbx+8]
0x1400aecba  mov     rax, [rcx+8]
0x1400aecbe  mov     edx, [rcx+18h]
0x1400aecc1  mov     [rbp+var_20], rax
0x1400aecc5  mov     eax, [rcx+10h]
0x1400aecc8  mov     [rbp+arg_18], eax
0x1400aeccb  mov     rdi, [r15+8]
0x1400aeccf  mov     [rbp+var_8], rdx
0x1400aecd3  mov     rax, [rdi+20h]
0x1400aecd7  mov     [rbp+var_38], rax
0x1400aecdb  cmp     edx, r14d
0x1400aecde  ja      loc_1400AEFBB
0x1400aece4  mov     rax, [rdi+8]
0x1400aece8  mov     [r15+70h], rax
0x1400aecec  lea     r9, [rbp+arg_10]
0x1400aecf0  mov     qword ptr [rdi+50h], 0
0x1400aecf8  lea     rax, [rbp+var_30]
0x1400aecfc  mov     dword ptr [rdi+28h], 0
0x1400aed03  lea     r8, [rbp+var_38]
0x1400aed07  mov     [rbp+arg_10], 0
0x1400aed0e  lea     rcx, [rbp+var_20]
0x1400aed12  mov     [rdi+18h], edx
0x1400aed15  mov     [rsp+80h+var_50], rax
0x1400aed1a  mov     dword ptr [rdi+10h], 0
0x1400aed21  mov     edi, edx
0x1400aed23  lea     rdx, [rbp+arg_18]
0x1400aed27  mov     byte ptr [rsp+80h+var_58], 0
0x1400aed2c  mov     [rsp+80h+var_60], rdi
0x1400aed31  call    cs:__imp_RtlCopyMdlToMdlIndirect
0x1400aed38  nop     dword ptr [rax+rax+00h]
0x1400aed3d  cmp     [rbp+var_30], rdi
0x1400aed41  jnz     loc_1400AF01A
0x1400aed47  mov     eax, [rbp+arg_10]
0x1400aed4a  mov     r9, r15
0x1400aed4d  mov     rcx, [r15+70h]
0x1400aed51  test    eax, eax
0x1400aed53  mov     r8, r15
0x1400aed56  mov     byte ptr [rsp+80h+var_60], 1
0x1400aed5b  cmovz   eax, r14d
0x1400aed5f  mov     rdx, rsi
0x1400aed62  mov     [rcx+28h], eax
0x1400aed65  call    TcpEnqueueTcbInput
0x1400aed6a  jmp     loc_1400AEE25
0x1400aed6f  mov     r9, rbx
0x1400aed72  mov     [rbx], r10
0x1400aed75  mov     r8, rbx
0x1400aed78  mov     byte ptr [rsp+80h+var_60], 1
0x1400aed7d  call    TcpEnqueueTcbInput
0x1400aed82  mov     rax, [rbx+8]
0x1400aed86  mov     ecx, [rax+18h]
0x1400aed89  mov     [r12], rcx
0x1400aed8d  jmp     loc_1400AEE43
0x1400aed92  mov     rdi, [rbp+var_28]
0x1400aed96  test    rdi, rdi
0x1400aed99  jz      loc_1400AEFA3
0x1400aed9f  mov     rax, [rbp+var_38]
0x1400aeda3  mov     r8, [rbp+var_18]
0x1400aeda7  mov     [rax], rdi
0x1400aedaa  cmp     [rbp+arg_10], 0
0x1400aedae  jnz     short loc_1400AEDB4
0x1400aedb0  mov     [rbp+var_38], rdi
0x1400aedb4  lea     rax, [rbp+var_30]
0x1400aedb8  mov     [rsp+80h+var_50], rax
0x1400aedbd  lea     r9, [rbp+arg_10]
0x1400aedc1  mov     byte ptr [rsp+80h+var_58], 0
0x1400aedc6  lea     rdx, [rbp+arg_18]
0x1400aedca  mov     [rsp+80h+var_60], r8
0x1400aedcf  lea     rcx, [rbp+var_20]
0x1400aedd3  lea     r8, [rbp+var_38]
0x1400aedd7  call    cs:__imp_RtlCopyMdlToMdlIndirect
0x1400aedde  nop     dword ptr [rax+rax+00h]
0x1400aede3  mov     rdx, [rbp+var_18]
0x1400aede7  cmp     [rbp+var_30], rdx
0x1400aedeb  jnz     loc_1400AF065
0x1400aedf1  test    rsi, rsi
0x1400aedf4  jz      short loc_1400AEDFA
0x1400aedf6  mov     [r15+70h], rsi
0x1400aedfa  mov     eax, [rbp+arg_10]
0x1400aedfd  test    eax, eax
0x1400aedff  mov     rcx, [r15+70h]
0x1400aee03  cmovz   eax, r14d
0x1400aee07  mov     [rcx+28h], eax
0x1400aee0a  mov     rax, [rbp+var_8]
0x1400aee0e  add     [rax+18h], edx
0x1400aee11  cmp     dword ptr [rbx+88h], 0
0x1400aee18  jge     short loc_1400AEE25
0x1400aee1a  or      dword ptr [r15+88h], 80000000h
0x1400aee25  mov     r8d, [rbp+arg_20]
0x1400aee29  mov     rdx, rbx
0x1400aee2c  mov     rcx, rbx
0x1400aee2f  mov     qword ptr [rbx], 0
0x1400aee36  call    TcpNetBufferListChainDelay
0x1400aee3b  mov     rax, [rbp+var_30]
0x1400aee3f  mov     [r12], rax
0x1400aee43  xor     eax, eax
0x1400aee45  mov     rbx, [rsp+80h+arg_0]
0x1400aee4d  add     rsp, 80h
0x1400aee54  pop     r15
0x1400aee56  pop     r14
0x1400aee58  pop     r13
0x1400aee5a  pop     r12
0x1400aee5c  pop     rdi
0x1400aee5d  pop     rsi
0x1400aee5e  pop     rbp
0x1400aee5f  retn
0x1400aee61  mov     r15, [r15+10h]
0x1400aee65  test    r15, r15
0x1400aee68  jz      loc_1400AEC58
0x1400aee6e  lea     rdi, TcpDelayedDeliveryCompletionRoutine
0x1400aee75  cmp     [r15+50h], rdi
0x1400aee79  jnz     loc_1400AEC5F
0x1400aee7f  mov     rax, [r15+8]
0x1400aee83  mov     [rbp+var_8], rax
0x1400aee87  cmp     dword ptr [rax+28h], 20000h
0x1400aee8e  jnb     loc_1400AEC5F
0x1400aee94  mov     rdx, [r15+70h]
0x1400aee98  mov     [rbp+var_38], rdx
0x1400aee9c  test    rax, rax
0x1400aee9f  jz      loc_1400AEC5F
0x1400aeea5  mov     rcx, [rbx+8]
0x1400aeea9  mov     [rbp+var_40], r10d
0x1400aeead  mov     rax, [rcx+8]
0x1400aeeb1  mov     r8d, [rcx+18h]
0x1400aeeb5  mov     [rbp+var_20], rax
0x1400aeeb9  mov     eax, [rcx+10h]
0x1400aeebc  mov     [rbp+arg_18], eax
0x1400aeebf  mov     eax, [rdx+28h]
0x1400aeec2  mov     [rbp+var_18], r8
0x1400aeec6  cmp     eax, r14d
0x1400aeec9  jnb     loc_1400AEF8E
0x1400aeecf  mov     [rbp+arg_10], eax
0x1400aeed2  mov     [rdx+28h], r14d
0x1400aeed6  mov     edx, [rbp+arg_10]
0x1400aeed9  mov     [rbp+var_40], eax
0x1400aeedc  test    edx, edx
0x1400aeede  jz      loc_1400AEF8E
0x1400aeee4  lea     rcx, [r8+rdx]
0x1400aeee8  mov     eax, r14d
0x1400aeeeb  mov     rsi, r10
0x1400aeeee  mov     rdi, r10
0x1400aeef1  cmp     rcx, rax
0x1400aeef4  jbe     loc_1400AEDB4
0x1400aeefa  test    edx, edx
0x1400aeefc  jz      loc_1400AEF8E
0x1400aef02  mov     edi, r8d
0x1400aef05  sub     edi, r14d
0x1400aef08  add     edi, edx
0x1400aef0a  mov     rcx, [r13+350h]
0x1400aef11  lea     r13, [rbp+var_28]
0x1400aef15  mov     [rbp+var_10], rcx
0x1400aef19  mov     [rbp+var_28], r10
0x1400aef1d  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+18h
0x1400aef24  test    rax, rax
0x1400aef27  jnz     loc_1400AEFF5
0x1400aef2d  mov     esi, [rbp+arg_20]
0x1400aef30  mov     rcx, cs:TcpDelayedDeliveryMdlPool
0x1400aef37  inc     esi
0x1400aef39  shl     rsi, 7
0x1400aef3d  add     rsi, rcx
0x1400aef40  movzx   eax, byte ptr [rsi+0B0h]
0x1400aef47  test    al, al
0x1400aef49  jnz     short loc_1400AEF54
0x1400aef4b  lea     rdx, [rsi+40h]
0x1400aef4f  call    PplpLazyInitializeLookasideList
0x1400aef54  lea     rcx, [rsi+40h]; Lookaside
0x1400aef58  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400aef5f  nop     dword ptr [rax+rax+00h]
0x1400aef64  test    rax, rax
0x1400aef67  jz      short loc_1400AEF96
0x1400aef69  lea     rsi, [rax-40h]
0x1400aef6d  sub     edi, 0FC0h
0x1400aef73  mov     [r13+0], rsi
0x1400aef77  test    edi, edi
0x1400aef79  jle     loc_1400AED92
0x1400aef7f  mov     rcx, [rbp+var_10]
0x1400aef83  mov     r13, rsi
0x1400aef86  mov     r9d, 1000h
0x1400aef8c  jmp     short loc_1400AEF1D
0x1400aef8e  mov     edi, r8d
0x1400aef91  jmp     loc_1400AEF0A
0x1400aef96  mov     rcx, [rbp+var_28]
0x1400aef9a  test    rcx, rcx
0x1400aef9d  jnz     loc_1400AF058
0x1400aefa3  mov     ecx, [rbp+arg_10]
0x1400aefa6  test    ecx, ecx
0x1400aefa8  jz      short loc_1400AEFB1
0x1400aefaa  mov     rax, [rbp+var_38]
0x1400aefae  mov     [rax+28h], ecx
0x1400aefb1  mov     eax, 0C0000017h
0x1400aefb6  jmp     loc_1400AEE45
0x1400aefbb  mov     r9, [r13+350h]
0x1400aefc2  mov     ecx, edx
0x1400aefc4  mov     r8d, [rbp+arg_20]
0x1400aefc8  lea     rdx, [rbp+var_18]
0x1400aefcc  sub     ecx, r14d
0x1400aefcf  mov     [rbp+var_18], 0
0x1400aefd7  call    TcpBuildMdlChain
0x1400aefdc  mov     rcx, [rbp+var_38]
0x1400aefe0  mov     [rcx], rax
0x1400aefe3  test    rax, rax
0x1400aefe6  jz      short loc_1400AF035
0x1400aefe8  mov     rax, [rbp+var_18]
0x1400aefec  mov     rdx, [rbp+var_8]
0x1400aeff0  jmp     loc_1400AECE8
0x1400aeff5  mov     rax, [rax]
0x1400aeff8  mov     rdx, rcx
0x1400aeffb  mov     ecx, r9d
0x1400aeffe  call    _guard_dispatch_icall
0x1400af003  mov     [r13+0], rax
0x1400af007  mov     rsi, rax
0x1400af00a  test    rax, rax
0x1400af00d  jz      short loc_1400AF04B
0x1400af00f  sub     edi, 1000h
0x1400af015  jmp     loc_1400AEF77
0x1400af01a  mov     dl, 1
0x1400af01c  mov     rcx, r15
0x1400af01f  call    cs:__imp_NetioDereferenceNetBufferList
0x1400af026  nop     dword ptr [rax+rax+00h]
0x1400af02b  mov     eax, 0C0000001h
0x1400af030  jmp     loc_1400AEE45
0x1400af035  mov     dl, 1
0x1400af037  mov     rcx, r15
0x1400af03a  call    cs:__imp_NetioDereferenceNetBufferList
0x1400af041  nop     dword ptr [rax+rax+00h]
0x1400af046  jmp     loc_1400AEFB1
0x1400af04b  mov     rcx, [rbp+var_28]
0x1400af04f  test    rcx, rcx
0x1400af052  jz      loc_1400AEFA3
0x1400af058  mov     edx, [rbp+arg_20]
0x1400af05b  call    TcpDestroyMdlChain
0x1400af060  jmp     loc_1400AEFA3
0x1400af065  mov     ecx, [rbp+var_40]
0x1400af068  test    rsi, rsi
0x1400af06b  jz      loc_1401C99D0
0x1400af071  test    ecx, ecx
0x1400af073  jz      loc_1401C99B8
0x1400af079  mov     rax, [r15+70h]
0x1400af07d  mov     [rax+28h], ecx
0x1400af080  jmp     loc_1401C99B8
0x1401c99b8  mov     edx, [rbp+arg_20]
0x1401c99bb  mov     rcx, rdi
0x1401c99be  call    TcpDestroyMdlChain
0x1401c99c3  mov     rax, [r15+70h]
0x1401c99c7  mov     qword ptr [rax], 0
0x1401c99ce  jmp     short loc_1401C99D7
0x1401c99d0  mov     rax, [r15+70h]
0x1401c99d4  mov     [rax+28h], ecx
0x1401c99d7  mov     eax, 0C0000001h
0x1401c99dc  jmp     loc_1400AEE45
0x1401c99e1  mov     rdx, [rcx+350h]
0x1401c99e8  mov     ecx, r14d
0x1401c99eb  mov     rax, [r8]
  ... truncated ...
```
