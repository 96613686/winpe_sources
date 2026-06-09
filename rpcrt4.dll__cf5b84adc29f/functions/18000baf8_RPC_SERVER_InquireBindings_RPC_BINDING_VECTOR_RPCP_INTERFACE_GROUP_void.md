# RPC_SERVER::InquireBindings(_RPC_BINDING_VECTOR * *,RPCP_INTERFACE_GROUP *,void *)

- ea: `0x18000baf8`
- end: `0x18000bceb`
- name: `?InquireBindings@RPC_SERVER@@QEAAJPEAPEAU_RPC_BINDING_VECTOR@@PEAVRPCP_INTERFACE_GROUP@@PEAX@Z`
- size: `499`
- prototype: `__int64 __fastcall(PRTL_CRITICAL_SECTION CriticalSection, struct _RPC_BINDING_VECTOR **, struct RPCP_INTERFACE_GROUP *, void *)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000bab0`
- `0x18008f2fc`
- `0x1800a0370`
- `0x1800ad5c0`
- `0x1800b7510`

## callees

- `0x18000aea0`
- `0x18000baf8`
- `0x18000bcf4`
- `0x180023020`
- `0x180088af0`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18000bc68`
- `ntdll!RtlLeaveCriticalSection` at `0x18000bc68`
- `ntdll!RtlEnterCriticalSection` at `0x18000bb25`
- `ntdll!RtlEnterCriticalSection` at `0x18000bb25`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18000bcc5`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18000bcc5`

## pseudocode

```c
__int64 __fastcall RPC_SERVER::InquireBindings(
        PRTL_CRITICAL_SECTION CriticalSection,
        struct _RPC_BINDING_VECTOR **a2,
        struct RPCP_INTERFACE_GROUP *a3,
        void *a4)
{
  struct _RPC_BINDING_VECTOR *v4; // rdi
  void *v5; // r12
  unsigned int v8; // ebp
  signed int v9; // ebx
  ULONG_PTR SpinCount; // rax
  __int64 v11; // rcx
  __int64 v12; // r14
  RPC_BINDING_VECTOR *v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // ebx
  ULONG_PTR v16; // rax
  __int64 v17; // rcx
  RPC_ADDRESS *v18; // r14
  _DWORD *v19; // r12
  __int64 i; // rbp
  struct BINDING_HANDLE *v21; // rax
  unsigned int v22; // ebx
  RPC_BINDING_VECTOR *BindingVector; // [rsp+20h] [rbp-48h] BYREF
  int v25; // [rsp+70h] [rbp+8h]

  v4 = 0;
  v5 = a4;
  BindingVector = 0;
  RtlEnterCriticalSection(CriticalSection);
  if ( !HIDWORD(CriticalSection[2].DebugInfo) && !HIDWORD(CriticalSection[3].OwningThread) )
  {
LABEL_30:
    v22 = 1718;
    goto LABEL_24;
  }
  if ( a3 && *((_DWORD *)a3 + 10) != 667022880 || v5 && !IsValidSecurityDescriptor(v5) )
  {
    v22 = 87;
  }
  else
  {
    v8 = 0;
    v9 = 0;
    while ( v8 < LODWORD(CriticalSection[2].DebugInfo) )
    {
      SpinCount = CriticalSection[1].SpinCount;
      v11 = v8++;
      v12 = *(_QWORD *)(SpinCount + 8 * v11);
      if ( v12 )
      {
        if ( !InquireBindingSkipRpcAddress(*(struct RPC_ADDRESS **)(SpinCount + 8 * v11), a3, v5) )
          v9 += *(_DWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 136LL))(v12);
      }
    }
    if ( !v9 )
      goto LABEL_30;
    v13 = (RPC_BINDING_VECTOR *)AllocWrapper(8LL * v9 + 8);
    BindingVector = v13;
    v4 = v13;
    if ( v13 )
    {
      v14 = 0;
      v13->Count = v9;
      do
      {
        v13->BindingH[v14] = 0;
        v14 = (unsigned int)(v14 + 1);
      }
      while ( (unsigned int)v14 < v13->Count );
      v25 = 0;
      v15 = 0;
      while ( v15 < LODWORD(CriticalSection[2].DebugInfo) )
      {
        v16 = CriticalSection[1].SpinCount;
        v17 = v15++;
        v18 = *(RPC_ADDRESS **)(v16 + 8 * v17);
        if ( v18 && !InquireBindingSkipRpcAddress(*(struct RPC_ADDRESS **)(v16 + 8 * v17), a3, v5) )
        {
          v19 = (_DWORD *)(*(__int64 (__fastcall **)(RPC_ADDRESS *))(*(_QWORD *)v18 + 136LL))(v18);
          if ( !v19 )
            goto LABEL_26;
          for ( i = 0; (unsigned int)i < *v19; i = (unsigned int)(i + 1) )
          {
            v21 = RPC_ADDRESS::InquireBinding(v18, *(unsigned __int16 **)&v19[2 * i + 2]);
            if ( !v21 )
              goto LABEL_26;
            v4->BindingH[v25++] = v21;
          }
          v5 = a4;
        }
      }
      v22 = 0;
      *a2 = v4;
    }
    else
    {
LABEL_26:
      v22 = 14;
    }
  }
LABEL_24:
  RtlLeaveCriticalSection(CriticalSection);
  if ( v22 && v4 )
    RpcBindingVectorFree(&BindingVector);
  return v22;
}

```

## disassembly

```asm
0x18000baf8  mov     rax, rsp
0x18000bafb  mov     [rax+18h], rbx
0x18000baff  mov     [rax+20h], r9
0x18000bb03  mov     [rax+10h], rdx
0x18000bb07  push    rbp
0x18000bb08  push    rsi
0x18000bb09  push    rdi
0x18000bb0a  push    r12
0x18000bb0c  push    r13
0x18000bb0e  push    r14
0x18000bb10  push    r15
0x18000bb12  sub     rsp, 30h
0x18000bb16  xor     edi, edi
0x18000bb18  mov     r12, r9
0x18000bb1b  mov     [rax-48h], rdi
0x18000bb1f  mov     r13, r8
0x18000bb22  mov     rsi, rcx
0x18000bb25  call    cs:__imp_RtlEnterCriticalSection
0x18000bb2c  nop     dword ptr [rax+rax+00h]
0x18000bb31  cmp     [rsi+54h], edi
0x18000bb34  jz      loc_18000BCAF
0x18000bb3a  test    r13, r13
0x18000bb3d  jnz     loc_18000BC9A
0x18000bb43  test    r12, r12
0x18000bb46  jnz     loc_18000BCC2
0x18000bb4c  xor     ebp, ebp
0x18000bb4e  xor     ebx, ebx
0x18000bb50  cmp     ebp, [rsi+50h]
0x18000bb53  jnb     short loc_18000BB93
0x18000bb55  mov     rax, [rsi+48h]
0x18000bb59  lea     r15d, [rbp+1]
0x18000bb5d  mov     ecx, ebp
0x18000bb5f  mov     ebp, r15d
0x18000bb62  mov     r14, [rax+rcx*8]
0x18000bb66  test    r14, r14
0x18000bb69  jz      short loc_18000BB50
0x18000bb6b  mov     r8, r12; void *
0x18000bb6e  mov     rdx, r13; struct RPCP_INTERFACE_GROUP *
0x18000bb71  mov     rcx, r14; struct RPC_ADDRESS *
0x18000bb74  call    ?InquireBindingSkipRpcAddress@@YAHPEAVRPC_ADDRESS@@PEAVRPCP_INTERFACE_GROUP@@PEAX@Z; InquireBindingSkipRpcAddress(RPC_ADDRESS *,RPCP_INTERFACE_GROUP *,void *)
0x18000bb79  test    eax, eax
0x18000bb7b  jnz     short loc_18000BB50
0x18000bb7d  mov     rax, [r14]
0x18000bb80  mov     rcx, r14
0x18000bb83  mov     rax, [rax+88h]
0x18000bb8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb8f  add     ebx, [rax]
0x18000bb91  jmp     short loc_18000BB50
0x18000bb93  test    ebx, ebx
0x18000bb95  jz      loc_18000BCBB
0x18000bb9b  movsxd  rcx, ebx
0x18000bb9e  lea     rcx, ds:8[rcx*8]; dwBytes
0x18000bba6  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18000bbab  mov     [rsp+68h+BindingVector], rax
0x18000bbb0  mov     rdi, rax
0x18000bbb3  test    rax, rax
0x18000bbb6  jz      loc_18000BC93
0x18000bbbc  xor     ecx, ecx
0x18000bbbe  mov     [rax], ebx
0x18000bbc0  test    ebx, ebx
0x18000bbc2  jz      short loc_18000BBD3
0x18000bbc4  mov     qword ptr [rax+rcx*8+8], 0
0x18000bbcd  inc     ecx
0x18000bbcf  cmp     ecx, [rax]
0x18000bbd1  jb      short loc_18000BBC4
0x18000bbd3  mov     [rsp+68h+arg_0], 0
0x18000bbdb  xor     ebx, ebx
0x18000bbdd  cmp     ebx, [rsi+50h]
0x18000bbe0  jnb     short loc_18000BC5B
0x18000bbe2  mov     rax, [rsi+48h]
0x18000bbe6  lea     r15d, [rbx+1]
0x18000bbea  mov     ecx, ebx
0x18000bbec  mov     ebx, r15d
0x18000bbef  mov     r14, [rax+rcx*8]
0x18000bbf3  test    r14, r14
0x18000bbf6  jz      short loc_18000BBDD
0x18000bbf8  mov     r8, r12; void *
0x18000bbfb  mov     rdx, r13; struct RPCP_INTERFACE_GROUP *
0x18000bbfe  mov     rcx, r14; struct RPC_ADDRESS *
0x18000bc01  call    ?InquireBindingSkipRpcAddress@@YAHPEAVRPC_ADDRESS@@PEAVRPCP_INTERFACE_GROUP@@PEAX@Z; InquireBindingSkipRpcAddress(RPC_ADDRESS *,RPCP_INTERFACE_GROUP *,void *)
0x18000bc06  test    eax, eax
0x18000bc08  jnz     short loc_18000BBDD
0x18000bc0a  mov     rax, [r14]
0x18000bc0d  mov     rcx, r14
0x18000bc10  mov     rax, [rax+88h]
0x18000bc17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc1c  mov     r12, rax
0x18000bc1f  test    rax, rax
0x18000bc22  jz      short loc_18000BC93
0x18000bc24  xor     ebp, ebp
0x18000bc26  cmp     ebp, [r12]
0x18000bc2a  jnb     short loc_18000BC51
0x18000bc2c  mov     rdx, [r12+rbp*8+8]; unsigned __int16 *
0x18000bc31  mov     rcx, r14; this
0x18000bc34  call    ?InquireBinding@RPC_ADDRESS@@QEAAPEAVBINDING_HANDLE@@PEAG@Z; RPC_ADDRESS::InquireBinding(ushort *)
0x18000bc39  test    rax, rax
0x18000bc3c  jz      short loc_18000BC93
0x18000bc3e  mov     edx, [rsp+68h+arg_0]
0x18000bc42  mov     [rdi+rdx*8+8], rax
0x18000bc47  inc     edx
0x18000bc49  mov     [rsp+68h+arg_0], edx
0x18000bc4d  inc     ebp
0x18000bc4f  jmp     short loc_18000BC26
0x18000bc51  mov     r12, [rsp+68h+arg_18]
0x18000bc59  jmp     short loc_18000BBDD
0x18000bc5b  mov     rax, [rsp+68h+arg_8]
0x18000bc60  xor     ebx, ebx
0x18000bc62  mov     [rax], rdi
0x18000bc65  mov     rcx, rsi; CriticalSection
0x18000bc68  call    cs:__imp_RtlLeaveCriticalSection
0x18000bc6f  nop     dword ptr [rax+rax+00h]
0x18000bc74  test    ebx, ebx
0x18000bc76  jnz     short loc_18000BCDA
0x18000bc78  mov     eax, ebx
0x18000bc7a  mov     rbx, [rsp+68h+arg_10]
0x18000bc82  add     rsp, 30h
0x18000bc86  pop     r15
0x18000bc88  pop     r14
0x18000bc8a  pop     r13
0x18000bc8c  pop     r12
0x18000bc8e  pop     rdi
0x18000bc8f  pop     rsi
0x18000bc90  pop     rbp
0x18000bc91  retn
0x18000bc93  mov     ebx, 0Eh
0x18000bc98  jmp     short loc_18000BC65
0x18000bc9a  cmp     dword ptr [r13+28h], 27C1F620h
0x18000bca2  jz      loc_18000BB43
0x18000bca8  mov     ebx, 57h ; 'W'
0x18000bcad  jmp     short loc_18000BC65
0x18000bcaf  cmp     [rsi+8Ch], edi
0x18000bcb5  jnz     loc_18000BB3A
0x18000bcbb  mov     ebx, 6B6h
0x18000bcc0  jmp     short loc_18000BC65
0x18000bcc2  mov     rcx, r12; pSecurityDescriptor
0x18000bcc5  call    cs:__imp_IsValidSecurityDescriptor
0x18000bccc  nop     dword ptr [rax+rax+00h]
0x18000bcd1  test    eax, eax
0x18000bcd3  jz      short loc_18000BCA8
0x18000bcd5  jmp     loc_18000BB4C
0x18000bcda  test    rdi, rdi
0x18000bcdd  jz      short loc_18000BC78
0x18000bcdf  lea     rcx, [rsp+68h+BindingVector]; BindingVector
0x18000bce4  call    RpcBindingVectorFree
0x18000bce9  jmp     short loc_18000BC78
```
