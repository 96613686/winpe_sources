# PAC_EncodeValidationInformation(_NETLOGON_VALIDATION_SAM_INFO3 *,uchar * *,ulong *)

- ea: `0x180036c10`
- end: `0x180036d8e`
- name: `?PAC_EncodeValidationInformation@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO3@@PEAPEAEPEAK@Z`
- size: `382`
- prototype: `__int64 __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO3 *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800370b8`
- `0x1800372bc`

## callees

- `0x180009770`
- `0x180023f80`
- `0x180036c10`

## import_xrefs

- `RPCRT4!NdrMesTypeAlignSize3` at `0x180036ca3`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x180036ca3`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x180036c5d`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x180036c5d`
- `RPCRT4!MesHandleFree` at `0x180036d7a`
- `RPCRT4!MesHandleFree` at `0x180036d7a`
- `RPCRT4!MesIncrementalHandleReset` at `0x180036ceb`
- `RPCRT4!MesIncrementalHandleReset` at `0x180036ceb`
- `RPCRT4!NdrMesTypeEncode3` at `0x180036d33`
- `RPCRT4!NdrMesTypeEncode3` at `0x180036d33`
- `RPCRT4!I_RpcMapWin32Status` at `0x180036cf7`
- `RPCRT4!I_RpcMapWin32Status` at `0x180036cf7`

## pseudocode

```c
__int64 __fastcall PAC_EncodeValidationInformation(
        struct _NETLOGON_VALIDATION_SAM_INFO3 *a1,
        unsigned __int8 **a2,
        unsigned int *a3)
{
  unsigned __int8 *v5; // rbx
  unsigned int v6; // edi
  unsigned int v7; // esi
  unsigned __int8 *v8; // rax
  RPC_STATUS v9; // eax
  __int128 v11; // [rsp+38h] [rbp-40h] BYREF
  struct _NETLOGON_VALIDATION_SAM_INFO3 *pObject; // [rsp+80h] [rbp+8h] BYREF
  handle_t Handle; // [rsp+88h] [rbp+10h] BYREF
  unsigned __int8 *v14; // [rsp+90h] [rbp+18h]

  pObject = a1;
  Handle = 0;
  v11 = 0;
  v5 = 0;
  v14 = 0;
  *a2 = 0;
  *a3 = 0;
  if ( MesEncodeIncrementalHandleCreate(
         &v11,
         PacReadFcn,
         wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
         &Handle)
    || (v7 = NdrMesTypeAlignSize3(
               Handle,
               &pPicklingInfo,
               &pProxyInfo,
               (const unsigned int **)&ArrTypeOffset,
               1u,
               &pObject),
        v8 = (unsigned __int8 *)MIDL_user_allocate(v7),
        v5 = v8,
        (v14 = v8) == 0) )
  {
    v6 = -1073741670;
  }
  else
  {
    v6 = 0;
    DWORD2(v11) = v7;
    *(_QWORD *)&v11 = v8;
    v9 = MesIncrementalHandleReset(Handle, 0, 0, 0, 0, MES_ENCODE);
    if ( v9 )
    {
      v6 = I_RpcMapWin32Status(v9);
    }
    else
    {
      NdrMesTypeEncode3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 1u, &pObject);
      *a2 = v5;
      *a3 = v7;
      v5 = 0;
    }
  }
  if ( v5 )
    DigestFreeMemory(v5);
  if ( Handle )
    MesHandleFree(Handle);
  return v6;
}

```

## disassembly

```asm
0x180036c10  mov     rax, rsp
0x180036c13  mov     [rax+8], rcx
0x180036c17  push    rbx
0x180036c18  push    rsi
0x180036c19  push    rdi
0x180036c1a  push    r14
0x180036c1c  push    r15
0x180036c1e  sub     rsp, 50h
0x180036c22  mov     r14, r8
0x180036c25  mov     r15, rdx
0x180036c28  mov     qword ptr [rax+10h], 0
0x180036c30  xorps   xmm0, xmm0
0x180036c33  movups  xmmword ptr [rax-40h], xmm0
0x180036c37  xor     ebx, ebx
0x180036c39  mov     [rsp+78h+arg_10], rbx
0x180036c41  mov     [rdx], rbx
0x180036c44  mov     [r8], ebx
0x180036c47  lea     r9, [rax+10h]; pHandle
0x180036c4b  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; WriteFn
0x180036c52  lea     rdx, ?PacReadFcn@@YAXPEAXPEAPEADPEAI@Z; AllocFn
0x180036c59  lea     rcx, [rax-40h]; UserState
0x180036c5d  call    cs:__imp_MesEncodeIncrementalHandleCreate
0x180036c63  test    eax, eax
0x180036c65  jz      short loc_180036C71
0x180036c67  mov     edi, 0C000009Ah
0x180036c6c  jmp     loc_180036D60
0x180036c71  lea     rax, [rsp+78h+arg_0]
0x180036c79  mov     [rsp+78h+pObject], rax; pObject
0x180036c7e  mov     [rsp+78h+nTypeIndex], 1; nTypeIndex
0x180036c86  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180036c8d  lea     r8, pProxyInfo; pProxyInfo
0x180036c94  lea     rdx, pPicklingInfo; pPicklingInfo
0x180036c9b  mov     rcx, [rsp+78h+Handle]; Handle
0x180036ca3  call    cs:__imp_NdrMesTypeAlignSize3
0x180036ca9  mov     rsi, rax
0x180036cac  mov     [rsp+78h+var_48], esi
0x180036cb0  mov     ecx, esi; size
0x180036cb2  call    MIDL_user_allocate
0x180036cb7  mov     rbx, rax
0x180036cba  mov     [rsp+78h+arg_10], rax
0x180036cc2  test    rax, rax
0x180036cc5  jz      short loc_180036C67
0x180036cc7  xor     edi, edi
0x180036cc9  mov     [rsp+78h+var_38], esi
0x180036ccd  mov     [rsp+78h+var_40], rax
0x180036cd2  mov     dword ptr [rsp+78h+pObject], edi; Operation
0x180036cd6  mov     qword ptr [rsp+78h+nTypeIndex], rdi; ReadFn
0x180036cdb  xor     r9d, r9d; WriteFn
0x180036cde  xor     r8d, r8d; AllocFn
0x180036ce1  xor     edx, edx; UserState
0x180036ce3  mov     rcx, [rsp+78h+Handle]; Handle
0x180036ceb  call    cs:__imp_MesIncrementalHandleReset
0x180036cf1  test    eax, eax
0x180036cf3  jz      short loc_180036D01
0x180036cf5  mov     ecx, eax; Status
0x180036cf7  call    cs:__imp_I_RpcMapWin32Status
0x180036cfd  mov     edi, eax
0x180036cff  jmp     short loc_180036D60
0x180036d01  lea     rax, [rsp+78h+arg_0]
0x180036d09  mov     [rsp+78h+pObject], rax; pObject
0x180036d0e  mov     [rsp+78h+nTypeIndex], 1; nTypeIndex
0x180036d16  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180036d1d  lea     r8, pProxyInfo; pProxyInfo
0x180036d24  lea     rdx, pPicklingInfo; pPicklingInfo
0x180036d2b  mov     rcx, [rsp+78h+Handle]; Handle
0x180036d33  call    cs:__imp_NdrMesTypeEncode3
0x180036d39  nop
0x180036d3a  mov     [r15], rbx
0x180036d3d  mov     [r14], esi
0x180036d40  xor     ebx, ebx
0x180036d42  jmp     short loc_180036D60
0x180036d44  mov     edi, 0C000000Dh
0x180036d49  mov     rbx, [rsp+78h+arg_10]
0x180036d51  jmp     short loc_180036D60
0x180036d53  mov     edi, 0C000000Dh
0x180036d58  mov     rbx, [rsp+78h+arg_10]
0x180036d60  test    rbx, rbx
0x180036d63  jz      short loc_180036D6D
0x180036d65  mov     rcx, rbx; hMem
0x180036d68  call    DigestFreeMemory
0x180036d6d  mov     rcx, [rsp+78h+Handle]; Handle
0x180036d75  test    rcx, rcx
0x180036d78  jz      short loc_180036D80
0x180036d7a  call    cs:__imp_MesHandleFree
0x180036d80  mov     eax, edi
0x180036d82  add     rsp, 50h
0x180036d86  pop     r15
0x180036d88  pop     r14
0x180036d8a  pop     rdi
0x180036d8b  pop     rsi
0x180036d8c  pop     rbx
0x180036d8d  retn
```
