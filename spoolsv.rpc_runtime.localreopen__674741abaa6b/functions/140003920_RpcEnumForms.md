# RpcEnumForms

- ea: `0x140003920`
- end: `0x140003d55`
- name: `RpcEnumForms`
- size: `1077`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1400028e0`
- `0x140003920`
- `0x140003d60`
- `0x140004790`
- `0x14001748c`
- `0x140080828`
- `0x140080834`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003d27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003d27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003a12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ad4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ccb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003cdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003a12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ad4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ccb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003cdc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003a06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003ac6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003af0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003c64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003cba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003a06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003ac6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003af0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003c64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003cba`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000396a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140003a28`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000396a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140003a28`
- `RPCRT4!RpcRevertToSelf` at `0x140003ae2`
- `RPCRT4!RpcRevertToSelf` at `0x140003ae2`
- `RPCRT4!RpcImpersonateClient` at `0x1400039f4`
- `RPCRT4!RpcImpersonateClient` at `0x1400039f4`
- `RPCRT4!RpcServerInqBindingHandle` at `0x14000394b`
- `RPCRT4!RpcServerInqBindingHandle` at `0x14000394b`

## string_xrefs

- `0x14000398c`: `Rpc call is access denied.`

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
0x140003920  push    rbx
0x140003922  push    rbp
0x140003923  push    rsi
0x140003924  push    rdi
0x140003925  push    r12
0x140003927  push    r13
0x140003929  push    r14
0x14000392b  push    r15
0x14000392d  sub     rsp, 78h
0x140003931  mov     rsi, rcx
0x140003934  xor     edi, edi
0x140003936  lea     rcx, [rsp+0B8h+Binding]; Binding
0x14000393b  mov     [rsp+0B8h+Binding], rdi
0x140003940  mov     ebx, edi
0x140003942  mov     r13d, r9d
0x140003945  mov     r15, r8
0x140003948  mov     r12d, edx
0x14000394b  call    cs:__imp_RpcServerInqBindingHandle
0x140003952  nop     dword ptr [rax+rax+00h]
0x140003957  test    eax, eax
0x140003959  jnz     loc_140003A34
0x14000395f  mov     rdx, [rsp+0B8h+Binding]; lpTlsValue
0x140003964  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14000396a  call    cs:__imp_TlsSetValue
0x140003971  nop     dword ptr [rax+rax+00h]
0x140003976  test    eax, eax
0x140003978  jz      loc_140003A34
0x14000397e  mov     rcx, [rsp+0B8h+Binding]; void *
0x140003983  call    ?RpcApiValidSecurityLevel@@YAJPEAX@Z; RpcApiValidSecurityLevel(void *)
0x140003988  test    eax, eax
0x14000398a  jz      short loc_1400039A7
0x14000398c  lea     rdx, aRpcCallIsAcces; "Rpc call is access denied."
0x140003993  lea     rcx, aRpcenumforms; "RpcEnumForms"
0x14000399a  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000399f  lea     eax, [rdi+5]
0x1400039a2  jmp     loc_140003A36
0x1400039a7  mov     rbx, [rsp+0B8h+arg_20]
0x1400039af  mov     eax, r12d
0x1400039b2  mov     r14, [rsp+0B8h+arg_28]
0x1400039ba  mov     [rbx], edi
0x1400039bc  mov     [r14], edi
0x1400039bf  sub     eax, 1
0x1400039c2  jz      short loc_1400039E2
0x1400039c4  cmp     eax, 1
0x1400039c7  jz      short loc_1400039D0
0x1400039c9  mov     ebx, 7Ch ; '|'
0x1400039ce  jmp     short loc_140003A20
0x1400039d0  lea     rbp, ?FormInfo2Fields@@3QBU_FieldInfo@@B; _FieldInfo const near * const FormInfo2Fields
0x1400039d7  mov     [rsp+0B8h+var_60], 58h ; 'X'
0x1400039e0  jmp     short loc_1400039F2
0x1400039e2  lea     rbp, ?FormInfo1Fields@@3QBU_FieldInfo@@B; _FieldInfo const near * const FormInfo1Fields
0x1400039e9  mov     [rsp+0B8h+var_60], 28h ; '('
0x1400039f2  xor     ecx, ecx; BindingHandle
0x1400039f4  call    cs:__imp_RpcImpersonateClient
0x1400039fb  nop     dword ptr [rax+rax+00h]
0x140003a00  test    eax, eax
0x140003a02  jz      short loc_140003A48
0x140003a04  mov     ecx, eax; dwErrCode
0x140003a06  call    cs:__imp_SetLastError
0x140003a0d  nop     dword ptr [rax+rax+00h]
0x140003a12  call    cs:__imp_GetLastError
0x140003a19  nop     dword ptr [rax+rax+00h]
0x140003a1e  mov     ebx, eax
0x140003a20  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140003a26  xor     edx, edx; lpTlsValue
0x140003a28  call    cs:__imp_TlsSetValue
0x140003a2f  nop     dword ptr [rax+rax+00h]
0x140003a34  mov     eax, ebx
0x140003a36  add     rsp, 78h
0x140003a3a  pop     r15
0x140003a3c  pop     r14
0x140003a3e  pop     r13
0x140003a40  pop     r12
0x140003a42  pop     rdi
0x140003a43  pop     rsi
0x140003a44  pop     rbp
0x140003a45  pop     rbx
0x140003a46  retn
0x140003a48  lea     rdi, [r15+7]
0x140003a4c  and     r13d, 0FFFFFFF8h
0x140003a50  and     rdi, 0FFFFFFFFFFFFFFF8h
0x140003a54  cmp     rdi, r15
0x140003a57  jz      short loc_140003A64
0x140003a59  mov     ecx, r13d; dwBytes
0x140003a5c  call    DllAllocSplMem
0x140003a61  mov     rdi, rax
0x140003a64  test    r15, r15
0x140003a67  jz      short loc_140003A78
0x140003a69  test    rdi, rdi
0x140003a6c  jnz     short loc_140003A78
0x140003a6e  lea     ecx, [rdi+1]
0x140003a71  call    ?YRevertToSelf@@YAJW4Call_Route@@@Z; YRevertToSelf(Call_Route)
0x140003a76  jmp     short loc_140003A12
0x140003a78  test    rsi, rsi
0x140003a7b  jz      short loc_140003AC1
0x140003a7d  cmp     dword ptr [rsi], 6060h
0x140003a83  jnz     short loc_140003AC1
0x140003a85  test    rdi, rdi
0x140003a88  jnz     short loc_140003A96
0x140003a8a  test    r13d, r13d
0x140003a8d  jz      short loc_140003A96
0x140003a8f  mov     ecx, 6F8h
0x140003a94  jmp     short loc_140003AC6
0x140003a96  mov     rax, [rsi+8]
0x140003a9a  mov     r9d, r13d
0x140003a9d  mov     rcx, [rsi+10h]
0x140003aa1  mov     r8, rdi
0x140003aa4  mov     [rsp+0B8h+var_90], r14
0x140003aa9  mov     edx, r12d
0x140003aac  mov     [rsp+0B8h+var_98], rbx
0x140003ab1  mov     rax, [rax+140h]
0x140003ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003abd  mov     esi, eax
0x140003abf  jmp     short loc_140003AD4
0x140003ac1  mov     ecx, 6; dwErrCode
0x140003ac6  call    cs:__imp_SetLastError
0x140003acd  nop     dword ptr [rax+rax+00h]
0x140003ad2  xor     esi, esi
0x140003ad4  call    cs:__imp_GetLastError
0x140003adb  nop     dword ptr [rax+rax+00h]
0x140003ae0  mov     ebx, eax
0x140003ae2  call    cs:__imp_RpcRevertToSelf
0x140003ae9  nop     dword ptr [rax+rax+00h]
0x140003aee  mov     ecx, ebx; dwErrCode
0x140003af0  call    cs:__imp_SetLastError
0x140003af7  nop     dword ptr [rax+rax+00h]
0x140003afc  test    esi, esi
0x140003afe  jz      loc_140003CC8
0x140003b04  mov     edx, [r14]
0x140003b07  mov     [rsp+0B8h+var_70], edx
0x140003b0b  test    edx, edx
0x140003b0d  jz      loc_140003CAD
0x140003b13  xor     r12d, r12d
0x140003b16  test    rdi, rdi
0x140003b19  jz      loc_140003CB5
0x140003b1f  xor     r14d, r14d
0x140003b22  lea     r11d, [r12+4]
0x140003b27  xor     r8d, r8d
0x140003b2a  mov     r10d, 0FFFFFFFFh
0x140003b30  mov     ecx, r8d
0x140003b33  shl     rcx, 5
0x140003b37  cmp     [rcx+rbp], r10d
0x140003b3b  jz      short loc_140003B8E
0x140003b3d  mov     edx, [rcx+rbp+18h]
0x140003b41  lea     eax, [rdx-1]
0x140003b44  cmp     eax, 8
0x140003b47  jbe     short loc_140003B5D
0x140003b49  test    edx, edx
0x140003b4b  jnz     loc_140003CB5
0x140003b51  mov     rdx, [rcx+rbp+8]
0x140003b56  mov     rax, [rcx+rbp+10h]
0x140003b5b  jmp     short loc_140003B63
0x140003b5d  mov     rdx, r11
0x140003b60  mov     rax, r11
0x140003b63  lea     rcx, [rax-1]
0x140003b67  neg     rax
0x140003b6a  add     rcx, r14
0x140003b6d  and     rcx, rax
0x140003b70  mov     rax, r10
0x140003b73  sub     rax, rdx
0x140003b76  cmp     rcx, rax
0x140003b79  ja      short loc_140003B84
0x140003b7b  lea     r14, [rcx+rdx]
0x140003b7f  inc     r8d
0x140003b82  jmp     short loc_140003B30
0x140003b84  mov     ecx, 216h
0x140003b89  jmp     loc_140003CBA
0x140003b8e  add     r14, 3
0x140003b92  and     r14, 0FFFFFFFFFFFFFFFCh
0x140003b96  cmp     r14, [rsp+0B8h+var_60]
0x140003b9b  jbe     short loc_140003BA7
0x140003b9d  mov     ecx, 0Dh
0x140003ba2  jmp     loc_140003CBA
0x140003ba7  xor     eax, eax
0x140003ba9  mov     rsi, rdi
0x140003bac  mov     r9, rdi
0x140003baf  mov     [rsp+0B8h+var_58], r9
0x140003bb4  mov     [rsp+0B8h+var_74], eax
0x140003bb8  cmp     eax, [rsp+0B8h+var_70]
0x140003bbc  jnb     loc_140003CAD
0x140003bc2  test    rsi, rsi
0x140003bc5  jz      loc_140003CB5
0x140003bcb  xor     eax, eax
0x140003bcd  mov     r8, rsi
0x140003bd0  mov     ecx, eax
0x140003bd2  shl     rcx, 5
0x140003bd6  mov     [rsp+0B8h+var_78], eax
0x140003bda  cmp     [rcx+rbp], r10d
0x140003bde  jz      loc_140003C72
0x140003be4  mov     edx, [rcx+rbp+18h]
0x140003be8  mov     r10d, [rcx+rbp]
0x140003bec  add     r10, rsi
0x140003bef  lea     eax, [rdx-1]
0x140003bf2  cmp     eax, 8
0x140003bf5  jbe     short loc_140003C07
0x140003bf7  test    edx, edx
0x140003bf9  jnz     short loc_140003C5F
0x140003bfb  mov     rdx, [rcx+rbp+8]
0x140003c00  mov     rax, [rcx+rbp+10h]
0x140003c05  jmp     short loc_140003C1B
0x140003c07  mov     rax, [r10]
0x140003c0a  test    rax, rax
0x140003c0d  jz      short loc_140003C15
0x140003c0f  sub     rax, r9
0x140003c12  mov     [r10], rax
0x140003c15  mov     rdx, r11
0x140003c18  mov     rax, r11
0x140003c1b  lea     rbx, [r8-1]
0x140003c1f  mov     [rsp+0B8h+var_50], rdx
0x140003c24  add     rbx, rax
0x140003c27  mov     r8, rdx; Size
0x140003c2a  neg     rax
0x140003c2d  mov     rdx, r10; Src
0x140003c30  and     rbx, rax
0x140003c33  mov     rcx, rbx; void *
0x140003c36  call    memmove_0
0x140003c3b  mov     r8, [rsp+0B8h+var_50]
0x140003c40  mov     r11d, 4
0x140003c46  mov     eax, [rsp+0B8h+var_78]
0x140003c4a  add     r8, rbx
0x140003c4d  mov     r9, [rsp+0B8h+var_58]
0x140003c52  inc     eax
0x140003c54  mov     r10d, 0FFFFFFFFh
0x140003c5a  jmp     loc_140003BD0
0x140003c5f  xor     ebx, ebx
0x140003c61  lea     ecx, [rbx+57h]; dwErrCode
0x140003c64  call    cs:__imp_SetLastError
0x140003c6b  nop     dword ptr [rax+rax+00h]
0x140003c70  jmp     short loc_140003C85
0x140003c72  mov     r8, r14; Size
0x140003c75  mov     rdx, rsi; Src
0x140003c78  mov     rcx, r9; void *
0x140003c7b  call    memmove_0
0x140003c80  mov     ebx, 1
0x140003c85  test    ebx, ebx
0x140003c87  jz      short loc_140003CFE
0x140003c89  mov     eax, [rsp+0B8h+var_74]
0x140003c8d  mov     r11d, 4
0x140003c93  add     rsi, [rsp+0B8h+var_60]
0x140003c98  inc     eax
0x140003c9a  mov     r9, [rsp+0B8h+var_58]
0x140003c9f  mov     r10d, 0FFFFFFFFh
0x140003ca5  add     r9, r14
0x140003ca8  jmp     loc_140003BAF
0x140003cad  mov     r12d, 1
0x140003cb3  jmp     short loc_140003CFE
0x140003cb5  mov     ecx, 57h ; 'W'; dwErrCode
0x140003cba  call    cs:__imp_SetLastError
0x140003cc1  nop     dword ptr [rax+rax+00h]
0x140003cc6  jmp     short loc_140003CFE
0x140003cc8  xor     r12d, r12d
0x140003ccb  call    cs:__imp_GetLastError
0x140003cd2  nop     dword ptr [rax+rax+00h]
0x140003cd7  cmp     eax, 7Ah ; 'z'
0x140003cda  jz      short loc_140003CFE
0x140003cdc  call    cs:__imp_GetLastError
0x140003ce3  nop     dword ptr [rax+rax+00h]
0x140003ce8  mov     r8d, eax
0x140003ceb  lea     rdx, aFailedErrorD_1; "Failed. Error %d"
0x140003cf2  lea     rcx, aYenumforms; "YEnumForms"
0x140003cf9  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140003cfe  cmp     r15, rdi
0x140003d01  jz      short loc_140003D33
0x140003d03  test    r15, r15
0x140003d06  jz      short loc_140003D1B
0x140003d08  test    rdi, rdi
0x140003d0b  jz      short loc_140003D1B
0x140003d0d  mov     r8d, r13d; Size
0x140003d10  mov     rdx, rdi; Src
0x140003d13  mov     rcx, r15; void *
0x140003d16  call    memcpy_0
0x140003d1b  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140003d22  mov     r8, rdi; lpMem
0x140003d25  xor     edx, edx; dwFlags
0x140003d27  call    cs:__imp_HeapFree
0x140003d2e  nop     dword ptr [rax+rax+00h]
0x140003d33  mov     rcx, [rsp+0B8h+arg_20]
0x140003d3b  mov     eax, [rcx]
0x140003d3d  add     eax, 7
0x140003d40  and     eax, 0FFFFFFF8h
0x140003d43  mov     [rcx], eax
0x140003d45  test    r12d, r12d
0x140003d48  jz      loc_140003A12
0x140003d4e  xor     ebx, ebx
0x140003d50  jmp     loc_140003A20
```
