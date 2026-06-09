# RPC_SERVER::InquireBindings(_RPC_BINDING_VECTOR * *,RPCP_INTERFACE_GROUP *,void *)

- ea: `0x18006b768`
- end: `0x18006b948`
- name: `?InquireBindings@RPC_SERVER@@QEAAJPEAPEAU_RPC_BINDING_VECTOR@@PEAVRPCP_INTERFACE_GROUP@@PEAX@Z`
- size: `480`
- prototype: `__int64 __fastcall(PRTL_CRITICAL_SECTION CriticalSection, struct _RPC_BINDING_VECTOR **, struct RPCP_INTERFACE_GROUP *, void *)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006b720`
- `0x18006cddc`
- `0x18009cb30`
- `0x1800a9c60`
- `0x1800b35d8`

## callees

- `0x180021e70`
- `0x18006abf0`
- `0x18006b768`
- `0x18006b950`
- `0x180087a10`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18006b8d2`
- `ntdll!RtlLeaveCriticalSection` at `0x18006b8d2`
- `ntdll!RtlEnterCriticalSection` at `0x18006b795`
- `ntdll!RtlEnterCriticalSection` at `0x18006b795`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18006b928`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18006b928`

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
0x18006b768  mov     rax, rsp
0x18006b76b  mov     [rax+18h], rbx
0x18006b76f  mov     [rax+20h], r9
0x18006b773  mov     [rax+10h], rdx
0x18006b777  push    rbp
0x18006b778  push    rsi
0x18006b779  push    rdi
0x18006b77a  push    r12
0x18006b77c  push    r13
0x18006b77e  push    r14
0x18006b780  push    r15
0x18006b782  sub     rsp, 30h
0x18006b786  xor     edi, edi
0x18006b788  mov     r12, r9
0x18006b78b  mov     [rax-48h], rdi
0x18006b78f  mov     r13, r8
0x18006b792  mov     rsi, rcx
0x18006b795  call    cs:__imp_RtlEnterCriticalSection
0x18006b79b  cmp     [rsi+54h], edi
0x18006b79e  jz      loc_18006B912
0x18006b7a4  test    r13, r13
0x18006b7a7  jnz     loc_18006B8FD
0x18006b7ad  test    r12, r12
0x18006b7b0  jnz     loc_18006B925
0x18006b7b6  xor     ebp, ebp
0x18006b7b8  xor     ebx, ebx
0x18006b7ba  cmp     ebp, [rsi+50h]
0x18006b7bd  jnb     short loc_18006B7FD
0x18006b7bf  mov     rax, [rsi+48h]
0x18006b7c3  lea     r15d, [rbp+1]
0x18006b7c7  mov     ecx, ebp
0x18006b7c9  mov     ebp, r15d
0x18006b7cc  mov     r14, [rax+rcx*8]
0x18006b7d0  test    r14, r14
0x18006b7d3  jz      short loc_18006B7BA
0x18006b7d5  mov     r8, r12; void *
0x18006b7d8  mov     rdx, r13; struct RPCP_INTERFACE_GROUP *
0x18006b7db  mov     rcx, r14; struct RPC_ADDRESS *
0x18006b7de  call    ?InquireBindingSkipRpcAddress@@YAHPEAVRPC_ADDRESS@@PEAVRPCP_INTERFACE_GROUP@@PEAX@Z; InquireBindingSkipRpcAddress(RPC_ADDRESS *,RPCP_INTERFACE_GROUP *,void *)
0x18006b7e3  test    eax, eax
0x18006b7e5  jnz     short loc_18006B7BA
0x18006b7e7  mov     rax, [r14]
0x18006b7ea  mov     rcx, r14
0x18006b7ed  mov     rax, [rax+88h]
0x18006b7f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b7f9  add     ebx, [rax]
0x18006b7fb  jmp     short loc_18006B7BA
0x18006b7fd  test    ebx, ebx
0x18006b7ff  jz      loc_18006B91E
0x18006b805  movsxd  rcx, ebx
0x18006b808  lea     rcx, ds:8[rcx*8]; dwBytes
0x18006b810  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18006b815  mov     [rsp+68h+BindingVector], rax
0x18006b81a  mov     rdi, rax
0x18006b81d  test    rax, rax
0x18006b820  jz      loc_18006B8F6
0x18006b826  xor     ecx, ecx
0x18006b828  mov     [rax], ebx
0x18006b82a  test    ebx, ebx
0x18006b82c  jz      short loc_18006B83D
0x18006b82e  mov     qword ptr [rax+rcx*8+8], 0
0x18006b837  inc     ecx
0x18006b839  cmp     ecx, [rax]
0x18006b83b  jb      short loc_18006B82E
0x18006b83d  mov     [rsp+68h+arg_0], 0
0x18006b845  xor     ebx, ebx
0x18006b847  cmp     ebx, [rsi+50h]
0x18006b84a  jnb     short loc_18006B8C5
0x18006b84c  mov     rax, [rsi+48h]
0x18006b850  lea     r15d, [rbx+1]
0x18006b854  mov     ecx, ebx
0x18006b856  mov     ebx, r15d
0x18006b859  mov     r14, [rax+rcx*8]
0x18006b85d  test    r14, r14
0x18006b860  jz      short loc_18006B847
0x18006b862  mov     r8, r12; void *
0x18006b865  mov     rdx, r13; struct RPCP_INTERFACE_GROUP *
0x18006b868  mov     rcx, r14; struct RPC_ADDRESS *
0x18006b86b  call    ?InquireBindingSkipRpcAddress@@YAHPEAVRPC_ADDRESS@@PEAVRPCP_INTERFACE_GROUP@@PEAX@Z; InquireBindingSkipRpcAddress(RPC_ADDRESS *,RPCP_INTERFACE_GROUP *,void *)
0x18006b870  test    eax, eax
0x18006b872  jnz     short loc_18006B847
0x18006b874  mov     rax, [r14]
0x18006b877  mov     rcx, r14
0x18006b87a  mov     rax, [rax+88h]
0x18006b881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b886  mov     r12, rax
0x18006b889  test    rax, rax
0x18006b88c  jz      short loc_18006B8F6
0x18006b88e  xor     ebp, ebp
0x18006b890  cmp     ebp, [r12]
0x18006b894  jnb     short loc_18006B8BB
0x18006b896  mov     rdx, [r12+rbp*8+8]; unsigned __int16 *
0x18006b89b  mov     rcx, r14; this
0x18006b89e  call    ?InquireBinding@RPC_ADDRESS@@QEAAPEAVBINDING_HANDLE@@PEAG@Z; RPC_ADDRESS::InquireBinding(ushort *)
0x18006b8a3  test    rax, rax
0x18006b8a6  jz      short loc_18006B8F6
0x18006b8a8  mov     edx, [rsp+68h+arg_0]
0x18006b8ac  mov     [rdi+rdx*8+8], rax
0x18006b8b1  inc     edx
0x18006b8b3  mov     [rsp+68h+arg_0], edx
0x18006b8b7  inc     ebp
0x18006b8b9  jmp     short loc_18006B890
0x18006b8bb  mov     r12, [rsp+68h+arg_18]
0x18006b8c3  jmp     short loc_18006B847
0x18006b8c5  mov     rax, [rsp+68h+arg_8]
0x18006b8ca  xor     ebx, ebx
0x18006b8cc  mov     [rax], rdi
0x18006b8cf  mov     rcx, rsi; CriticalSection
0x18006b8d2  call    cs:__imp_RtlLeaveCriticalSection
0x18006b8d8  test    ebx, ebx
0x18006b8da  jnz     short loc_18006B937
0x18006b8dc  mov     eax, ebx
0x18006b8de  mov     rbx, [rsp+68h+arg_10]
0x18006b8e6  add     rsp, 30h
0x18006b8ea  pop     r15
0x18006b8ec  pop     r14
0x18006b8ee  pop     r13
0x18006b8f0  pop     r12
0x18006b8f2  pop     rdi
0x18006b8f3  pop     rsi
0x18006b8f4  pop     rbp
0x18006b8f5  retn
0x18006b8f6  mov     ebx, 0Eh
0x18006b8fb  jmp     short loc_18006B8CF
0x18006b8fd  cmp     dword ptr [r13+28h], 27C1F620h
0x18006b905  jz      loc_18006B7AD
0x18006b90b  mov     ebx, 57h ; 'W'
0x18006b910  jmp     short loc_18006B8CF
0x18006b912  cmp     [rsi+8Ch], edi
0x18006b918  jnz     loc_18006B7A4
0x18006b91e  mov     ebx, 6B6h
0x18006b923  jmp     short loc_18006B8CF
0x18006b925  mov     rcx, r12; pSecurityDescriptor
0x18006b928  call    cs:__imp_IsValidSecurityDescriptor
0x18006b92e  test    eax, eax
0x18006b930  jz      short loc_18006B90B
0x18006b932  jmp     loc_18006B7B6
0x18006b937  test    rdi, rdi
0x18006b93a  jz      short loc_18006B8DC
0x18006b93c  lea     rcx, [rsp+68h+BindingVector]; BindingVector
0x18006b941  call    RpcBindingVectorFree
0x18006b946  jmp     short loc_18006B8DC
```
