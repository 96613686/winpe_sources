# RpcEnumForms

- ea: `0x1400033f0`
- end: `0x1400037c7`
- name: `RpcEnumForms`
- size: `983`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x140002a70`
- `0x1400033f0`
- `0x1400037d0`
- `0x1400041c0`
- `0x1400160a0`
- `0x140079338`
- `0x140079344`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000379f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000379f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400034c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003576`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000374f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000375a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400034c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003576`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000374f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000375a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400034c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000356e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003586`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400036f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003744`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400034c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000356e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003586`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400036f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003744`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140003434`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400034d7`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140003434`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400034d7`
- `RPCRT4!RpcRevertToSelf` at `0x14000357e`
- `RPCRT4!RpcRevertToSelf` at `0x14000357e`
- `RPCRT4!RpcImpersonateClient` at `0x1400034b5`
- `RPCRT4!RpcImpersonateClient` at `0x1400034b5`
- `RPCRT4!RpcServerInqBindingHandle` at `0x14000341b`
- `RPCRT4!RpcServerInqBindingHandle` at `0x14000341b`

## string_xrefs

- `0x140003450`: `Rpc call is access denied.`

## pseudocode

```c
__int64 __fastcall RpcEnumForms(__int64 a1, unsigned int a2, char *a3, int a4, unsigned int *a5, unsigned int *a6)
{
  DWORD LastError; // ebx
  const struct _FieldInfo near *const *v12; // rbp
  RPC_STATUS v13; // eax
  unsigned int v14; // r13d
  char *v15; // rdi
  DWORD v16; // ecx
  int v17; // esi
  DWORD v18; // ebx
  int v19; // r12d
  unsigned __int64 v20; // r14
  unsigned int i; // r8d
  __int64 v22; // rcx
  int v23; // edx
  __int64 v24; // rdx
  __int64 v25; // rax
  unsigned __int64 v26; // rcx
  DWORD v27; // ecx
  size_t v28; // r14
  unsigned int v29; // eax
  char *v30; // rsi
  char *j; // r9
  unsigned int v32; // eax
  char *v33; // r8
  __int64 v34; // rcx
  int v35; // edx
  char *v36; // r10
  size_t v37; // rdx
  __int64 v38; // rax
  char *v39; // rbx
  int v40; // ebx
  DWORD v41; // eax
  unsigned int v42; // [rsp+40h] [rbp-78h]
  unsigned int v43; // [rsp+44h] [rbp-74h]
  unsigned int v44; // [rsp+48h] [rbp-70h]
  RPC_BINDING_HANDLE Binding; // [rsp+50h] [rbp-68h] BYREF
  unsigned __int64 v46; // [rsp+58h] [rbp-60h]
  char *v47; // [rsp+60h] [rbp-58h]
  size_t v48; // [rsp+68h] [rbp-50h]

  Binding = 0;
  LastError = 0;
  if ( RpcServerInqBindingHandle(&Binding) || !TlsSetValue(gdwTlsBindingHandle, Binding) )
    return LastError;
  if ( (unsigned int)RpcApiValidSecurityLevel(Binding) )
  {
    SpoolerServiceTelemetry::WriteDbgTraceError("RpcEnumForms", L"Rpc call is access denied.");
    return 5;
  }
  *a5 = 0;
  *a6 = 0;
  if ( a2 == 1 )
  {
    v12 = &FormInfo1Fields;
    v46 = 40;
LABEL_10:
    v13 = RpcImpersonateClient(0);
    if ( v13 )
    {
      SetLastError(v13);
LABEL_12:
      LastError = GetLastError();
      goto LABEL_13;
    }
    v14 = a4 & 0xFFFFFFF8;
    v15 = (char *)((unsigned __int64)(a3 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
    if ( v15 != a3 )
      v15 = (char *)DllAllocSplMem(v14);
    if ( a3 && !v15 )
    {
      YRevertToSelf(1);
      goto LABEL_12;
    }
    if ( a1 && *(_DWORD *)a1 == 24672 )
    {
      if ( v15 || !v14 )
      {
        v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *, _QWORD, unsigned int *, unsigned int *))(*(_QWORD *)(a1 + 8) + 320LL))(
                *(_QWORD *)(a1 + 16),
                a2,
                v15,
                v14,
                a5,
                a6);
        goto LABEL_28;
      }
      v16 = 1784;
    }
    else
    {
      v16 = 6;
    }
    SetLastError(v16);
    v17 = 0;
LABEL_28:
    v18 = GetLastError();
    RpcRevertToSelf();
    SetLastError(v18);
    if ( !v17 )
    {
      v19 = 0;
      if ( GetLastError() != 122 )
      {
        v41 = GetLastError();
        SpoolerServiceTelemetry::WriteDbgTraceError("YEnumForms", L"Failed. Error %d", v41);
      }
LABEL_63:
      if ( a3 != v15 )
      {
        if ( a3 )
        {
          if ( v15 )
            memcpy_0(a3, v15, v14);
        }
        HeapFree(g_hSpoolssHeap, 0, v15);
      }
      *a5 = (*a5 + 7) & 0xFFFFFFF8;
      if ( v19 )
      {
        LastError = 0;
        goto LABEL_13;
      }
      goto LABEL_12;
    }
    v44 = *a6;
    if ( *a6 )
    {
      v19 = 0;
      if ( !v15 )
      {
LABEL_59:
        v27 = 87;
        goto LABEL_60;
      }
      v20 = 0;
      for ( i = 0; ; ++i )
      {
        v22 = 4LL * i;
        if ( LODWORD(v12[v22]) == -1 )
          break;
        v23 = (int)v12[v22 + 3];
        if ( (unsigned int)(v23 - 1) <= 8 )
        {
          v24 = 4;
          v25 = 4;
        }
        else
        {
          if ( v23 )
            goto LABEL_59;
          v24 = (__int64)v12[v22 + 1];
          v25 = (__int64)v12[v22 + 2];
        }
        v26 = -v25 & (v20 + v25 - 1);
        if ( v26 > 0xFFFFFFFFLL - v24 )
        {
          v27 = 534;
          goto LABEL_60;
        }
        v20 = v26 + v24;
      }
      v28 = (v20 + 3) & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v28 > v46 )
      {
        v27 = 13;
LABEL_60:
        SetLastError(v27);
        goto LABEL_63;
      }
      v29 = 0;
      v30 = v15;
      for ( j = v15; ; j = &v47[v28] )
      {
        v47 = j;
        v43 = v29;
        if ( v29 >= v44 )
          break;
        if ( !v30 )
          goto LABEL_59;
        v32 = 0;
        v33 = v30;
        while ( 1 )
        {
          v34 = 4LL * v32;
          v42 = v32;
          if ( LODWORD(v12[v34]) == -1 )
            break;
          v35 = (int)v12[v34 + 3];
          v36 = &v30[LODWORD(v12[v34])];
          if ( (unsigned int)(v35 - 1) <= 8 )
          {
            if ( *(_QWORD *)v36 )
              *(_QWORD *)v36 -= j;
            v37 = 4;
            v38 = 4;
          }
          else
          {
            if ( v35 )
            {
              v40 = 0;
              SetLastError(0x57u);
              goto LABEL_56;
            }
            v37 = (size_t)v12[v34 + 1];
            v38 = (__int64)v12[v34 + 2];
          }
          v48 = v37;
          v39 = (char *)(-v38 & (unsigned __int64)&v33[v38 - 1]);
          memmove_0(v39, v36, v37);
          v33 = &v39[v48];
          j = v47;
          v32 = v42 + 1;
        }
        memmove_0(j, v30, v28);
        v40 = 1;
LABEL_56:
        if ( !v40 )
          goto LABEL_63;
        v30 += v46;
        v29 = v43 + 1;
      }
    }
    v19 = 1;
    goto LABEL_63;
  }
  if ( a2 == 2 )
  {
    v12 = &FormInfo2Fields;
    v46 = 88;
    goto LABEL_10;
  }
  LastError = 124;
LABEL_13:
  TlsSetValue(gdwTlsBindingHandle, 0);
  return LastError;
}

```

## disassembly

```asm
0x1400033f0  push    rbx
0x1400033f2  push    rbp
0x1400033f3  push    rsi
0x1400033f4  push    rdi
0x1400033f5  push    r12
0x1400033f7  push    r13
0x1400033f9  push    r14
0x1400033fb  push    r15
0x1400033fd  sub     rsp, 78h
0x140003401  mov     rsi, rcx
0x140003404  xor     edi, edi
0x140003406  lea     rcx, [rsp+0B8h+Binding]; Binding
0x14000340b  mov     [rsp+0B8h+Binding], rdi
0x140003410  mov     ebx, edi
0x140003412  mov     r13d, r9d
0x140003415  mov     r15, r8
0x140003418  mov     r12d, edx
0x14000341b  call    cs:__imp_RpcServerInqBindingHandle
0x140003421  test    eax, eax
0x140003423  jnz     loc_1400034DD
0x140003429  mov     rdx, [rsp+0B8h+Binding]; lpTlsValue
0x14000342e  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140003434  call    cs:__imp_TlsSetValue
0x14000343a  test    eax, eax
0x14000343c  jz      loc_1400034DD
0x140003442  mov     rcx, [rsp+0B8h+Binding]; void *
0x140003447  call    ?RpcApiValidSecurityLevel@@YAJPEAX@Z; RpcApiValidSecurityLevel(void *)
0x14000344c  test    eax, eax
0x14000344e  jz      short loc_140003468
0x140003450  lea     rdx, aRpcCallIsAcces; "Rpc call is access denied."
0x140003457  lea     rcx, aRpcenumforms; "RpcEnumForms"
0x14000345e  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140003463  lea     eax, [rdi+5]
0x140003466  jmp     short loc_1400034DF
0x140003468  mov     rbx, [rsp+0B8h+arg_20]
0x140003470  mov     eax, r12d
0x140003473  mov     r14, [rsp+0B8h+arg_28]
0x14000347b  mov     [rbx], edi
0x14000347d  mov     [r14], edi
0x140003480  sub     eax, 1
0x140003483  jz      short loc_1400034A3
0x140003485  cmp     eax, 1
0x140003488  jz      short loc_140003491
0x14000348a  mov     ebx, 7Ch ; '|'
0x14000348f  jmp     short loc_1400034CF
0x140003491  lea     rbp, ?FormInfo2Fields@@3QBU_FieldInfo@@B; _FieldInfo const near * const FormInfo2Fields
0x140003498  mov     [rsp+0B8h+var_60], 58h ; 'X'
0x1400034a1  jmp     short loc_1400034B3
0x1400034a3  lea     rbp, ?FormInfo1Fields@@3QBU_FieldInfo@@B; _FieldInfo const near * const FormInfo1Fields
0x1400034aa  mov     [rsp+0B8h+var_60], 28h ; '('
0x1400034b3  xor     ecx, ecx; BindingHandle
0x1400034b5  call    cs:__imp_RpcImpersonateClient
0x1400034bb  test    eax, eax
0x1400034bd  jz      short loc_1400034F0
0x1400034bf  mov     ecx, eax; dwErrCode
0x1400034c1  call    cs:__imp_SetLastError
0x1400034c7  call    cs:__imp_GetLastError
0x1400034cd  mov     ebx, eax
0x1400034cf  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400034d5  xor     edx, edx; lpTlsValue
0x1400034d7  call    cs:__imp_TlsSetValue
0x1400034dd  mov     eax, ebx
0x1400034df  add     rsp, 78h
0x1400034e3  pop     r15
0x1400034e5  pop     r14
0x1400034e7  pop     r13
0x1400034e9  pop     r12
0x1400034eb  pop     rdi
0x1400034ec  pop     rsi
0x1400034ed  pop     rbp
0x1400034ee  pop     rbx
0x1400034ef  retn
0x1400034f0  lea     rdi, [r15+7]
0x1400034f4  and     r13d, 0FFFFFFF8h
0x1400034f8  and     rdi, 0FFFFFFFFFFFFFFF8h
0x1400034fc  cmp     rdi, r15
0x1400034ff  jz      short loc_14000350C
0x140003501  mov     ecx, r13d; dwBytes
0x140003504  call    DllAllocSplMem
0x140003509  mov     rdi, rax
0x14000350c  test    r15, r15
0x14000350f  jz      short loc_140003520
0x140003511  test    rdi, rdi
0x140003514  jnz     short loc_140003520
0x140003516  lea     ecx, [rdi+1]
0x140003519  call    ?YRevertToSelf@@YAJW4Call_Route@@@Z; YRevertToSelf(Call_Route)
0x14000351e  jmp     short loc_1400034C7
0x140003520  test    rsi, rsi
0x140003523  jz      short loc_140003569
0x140003525  cmp     dword ptr [rsi], 6060h
0x14000352b  jnz     short loc_140003569
0x14000352d  test    rdi, rdi
0x140003530  jnz     short loc_14000353E
0x140003532  test    r13d, r13d
0x140003535  jz      short loc_14000353E
0x140003537  mov     ecx, 6F8h
0x14000353c  jmp     short loc_14000356E
0x14000353e  mov     rax, [rsi+8]
0x140003542  mov     r9d, r13d
0x140003545  mov     rcx, [rsi+10h]
0x140003549  mov     r8, rdi
0x14000354c  mov     [rsp+0B8h+var_90], r14
0x140003551  mov     edx, r12d
0x140003554  mov     [rsp+0B8h+var_98], rbx
0x140003559  mov     rax, [rax+140h]
0x140003560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003565  mov     esi, eax
0x140003567  jmp     short loc_140003576
0x140003569  mov     ecx, 6; dwErrCode
0x14000356e  call    cs:__imp_SetLastError
0x140003574  xor     esi, esi
0x140003576  call    cs:__imp_GetLastError
0x14000357c  mov     ebx, eax
0x14000357e  call    cs:__imp_RpcRevertToSelf
0x140003584  mov     ecx, ebx; dwErrCode
0x140003586  call    cs:__imp_SetLastError
0x14000358c  test    esi, esi
0x14000358e  jz      loc_14000374C
0x140003594  mov     edx, [r14]
0x140003597  mov     [rsp+0B8h+var_70], edx
0x14000359b  test    edx, edx
0x14000359d  jz      loc_140003737
0x1400035a3  xor     r12d, r12d
0x1400035a6  test    rdi, rdi
0x1400035a9  jz      loc_14000373F
0x1400035af  xor     r14d, r14d
0x1400035b2  lea     r11d, [r12+4]
0x1400035b7  xor     r8d, r8d
0x1400035ba  mov     r10d, 0FFFFFFFFh
0x1400035c0  mov     ecx, r8d
0x1400035c3  shl     rcx, 5
0x1400035c7  cmp     [rcx+rbp], r10d
0x1400035cb  jz      short loc_14000361E
0x1400035cd  mov     edx, [rcx+rbp+18h]
0x1400035d1  lea     eax, [rdx-1]
0x1400035d4  cmp     eax, 8
0x1400035d7  jbe     short loc_1400035ED
0x1400035d9  test    edx, edx
0x1400035db  jnz     loc_14000373F
0x1400035e1  mov     rdx, [rcx+rbp+8]
0x1400035e6  mov     rax, [rcx+rbp+10h]
0x1400035eb  jmp     short loc_1400035F3
0x1400035ed  mov     rdx, r11
0x1400035f0  mov     rax, r11
0x1400035f3  lea     rcx, [rax-1]
0x1400035f7  neg     rax
0x1400035fa  add     rcx, r14
0x1400035fd  and     rcx, rax
0x140003600  mov     rax, r10
0x140003603  sub     rax, rdx
0x140003606  cmp     rcx, rax
0x140003609  ja      short loc_140003614
0x14000360b  lea     r14, [rcx+rdx]
0x14000360f  inc     r8d
0x140003612  jmp     short loc_1400035C0
0x140003614  mov     ecx, 216h
0x140003619  jmp     loc_140003744
0x14000361e  add     r14, 3
0x140003622  and     r14, 0FFFFFFFFFFFFFFFCh
0x140003626  cmp     r14, [rsp+0B8h+var_60]
0x14000362b  jbe     short loc_140003637
0x14000362d  mov     ecx, 0Dh
0x140003632  jmp     loc_140003744
0x140003637  xor     eax, eax
0x140003639  mov     rsi, rdi
0x14000363c  mov     r9, rdi
0x14000363f  mov     [rsp+0B8h+var_58], r9
0x140003644  mov     [rsp+0B8h+var_74], eax
0x140003648  cmp     eax, [rsp+0B8h+var_70]
0x14000364c  jnb     loc_140003737
0x140003652  test    rsi, rsi
0x140003655  jz      loc_14000373F
0x14000365b  xor     eax, eax
0x14000365d  mov     r8, rsi
0x140003660  mov     ecx, eax
0x140003662  shl     rcx, 5
0x140003666  mov     [rsp+0B8h+var_78], eax
0x14000366a  cmp     [rcx+rbp], r10d
0x14000366e  jz      loc_1400036FC
0x140003674  mov     edx, [rcx+rbp+18h]
0x140003678  mov     r10d, [rcx+rbp]
0x14000367c  add     r10, rsi
0x14000367f  lea     eax, [rdx-1]
0x140003682  cmp     eax, 8
0x140003685  jbe     short loc_140003697
0x140003687  test    edx, edx
0x140003689  jnz     short loc_1400036EF
0x14000368b  mov     rdx, [rcx+rbp+8]
0x140003690  mov     rax, [rcx+rbp+10h]
0x140003695  jmp     short loc_1400036AB
0x140003697  mov     rax, [r10]
0x14000369a  test    rax, rax
0x14000369d  jz      short loc_1400036A5
0x14000369f  sub     rax, r9
0x1400036a2  mov     [r10], rax
0x1400036a5  mov     rdx, r11
0x1400036a8  mov     rax, r11
0x1400036ab  lea     rbx, [r8-1]
0x1400036af  mov     [rsp+0B8h+var_50], rdx
0x1400036b4  add     rbx, rax
0x1400036b7  mov     r8, rdx; Size
0x1400036ba  neg     rax
0x1400036bd  mov     rdx, r10; Src
0x1400036c0  and     rbx, rax
0x1400036c3  mov     rcx, rbx; void *
0x1400036c6  call    memmove_0
0x1400036cb  mov     r8, [rsp+0B8h+var_50]
0x1400036d0  mov     r11d, 4
0x1400036d6  mov     eax, [rsp+0B8h+var_78]
0x1400036da  add     r8, rbx
0x1400036dd  mov     r9, [rsp+0B8h+var_58]
0x1400036e2  inc     eax
0x1400036e4  mov     r10d, 0FFFFFFFFh
0x1400036ea  jmp     loc_140003660
0x1400036ef  xor     ebx, ebx
0x1400036f1  lea     ecx, [rbx+57h]; dwErrCode
0x1400036f4  call    cs:__imp_SetLastError
0x1400036fa  jmp     short loc_14000370F
0x1400036fc  mov     r8, r14; Size
0x1400036ff  mov     rdx, rsi; Src
0x140003702  mov     rcx, r9; void *
0x140003705  call    memmove_0
0x14000370a  mov     ebx, 1
0x14000370f  test    ebx, ebx
0x140003711  jz      short loc_140003776
0x140003713  mov     eax, [rsp+0B8h+var_74]
0x140003717  mov     r11d, 4
0x14000371d  add     rsi, [rsp+0B8h+var_60]
0x140003722  inc     eax
0x140003724  mov     r9, [rsp+0B8h+var_58]
0x140003729  mov     r10d, 0FFFFFFFFh
0x14000372f  add     r9, r14
0x140003732  jmp     loc_14000363F
0x140003737  mov     r12d, 1
0x14000373d  jmp     short loc_140003776
0x14000373f  mov     ecx, 57h ; 'W'; dwErrCode
0x140003744  call    cs:__imp_SetLastError
0x14000374a  jmp     short loc_140003776
0x14000374c  xor     r12d, r12d
0x14000374f  call    cs:__imp_GetLastError
0x140003755  cmp     eax, 7Ah ; 'z'
0x140003758  jz      short loc_140003776
0x14000375a  call    cs:__imp_GetLastError
0x140003760  mov     r8d, eax
0x140003763  lea     rdx, aFailedErrorD_1; "Failed. Error %d"
0x14000376a  lea     rcx, aYenumforms; "YEnumForms"
0x140003771  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140003776  cmp     r15, rdi
0x140003779  jz      short loc_1400037A5
0x14000377b  test    r15, r15
0x14000377e  jz      short loc_140003793
0x140003780  test    rdi, rdi
0x140003783  jz      short loc_140003793
0x140003785  mov     r8d, r13d; Size
0x140003788  mov     rdx, rdi; Src
0x14000378b  mov     rcx, r15; void *
0x14000378e  call    memcpy_0
0x140003793  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14000379a  mov     r8, rdi; lpMem
0x14000379d  xor     edx, edx; dwFlags
0x14000379f  call    cs:__imp_HeapFree
0x1400037a5  mov     rcx, [rsp+0B8h+arg_20]
0x1400037ad  mov     eax, [rcx]
0x1400037af  add     eax, 7
0x1400037b2  and     eax, 0FFFFFFF8h
0x1400037b5  mov     [rcx], eax
0x1400037b7  test    r12d, r12d
0x1400037ba  jz      loc_1400034C7
0x1400037c0  xor     ebx, ebx
0x1400037c2  jmp     loc_1400034CF
```
