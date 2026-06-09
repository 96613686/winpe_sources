# PAC_EncodeValidationInformation(_NETLOGON_VALIDATION_SAM_INFO3 *,uchar * *,ulong *)

- ea: `0x180087edc`
- end: `0x18008805a`
- name: `?PAC_EncodeValidationInformation@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO3@@PEAPEAEPEAK@Z`
- size: `382`
- prototype: `__int64 __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO3 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180088278`

## callees

- `0x1800696e0`
- `0x180069710`
- `0x180087edc`

## import_xrefs

- `RPCRT4!MesHandleFree` at `0x180088046`
- `RPCRT4!MesHandleFree` at `0x180088046`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x180087f29`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x180087f29`
- `RPCRT4!MesIncrementalHandleReset` at `0x180087fb7`
- `RPCRT4!MesIncrementalHandleReset` at `0x180087fb7`
- `RPCRT4!I_RpcMapWin32Status` at `0x180087fc3`
- `RPCRT4!I_RpcMapWin32Status` at `0x180087fc3`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x180087f6f`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x180087f6f`
- `RPCRT4!NdrMesTypeEncode3` at `0x180087fff`
- `RPCRT4!NdrMesTypeEncode3` at `0x180087fff`

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
    MIDL_user_free(v5);
  if ( Handle )
    MesHandleFree(Handle);
  return v6;
}

```

## disassembly

```asm
0x180087edc  mov     rax, rsp
0x180087edf  mov     [rax+8], rcx
0x180087ee3  push    rbx
0x180087ee4  push    rsi
0x180087ee5  push    rdi
0x180087ee6  push    r14
0x180087ee8  push    r15
0x180087eea  sub     rsp, 50h
0x180087eee  mov     r14, r8
0x180087ef1  mov     r15, rdx
0x180087ef4  mov     qword ptr [rax+10h], 0
0x180087efc  xorps   xmm0, xmm0
0x180087eff  movups  xmmword ptr [rax-40h], xmm0
0x180087f03  xor     ebx, ebx
0x180087f05  mov     [rsp+78h+arg_10], rbx
0x180087f0d  mov     [rdx], rbx
0x180087f10  mov     [r8], ebx
0x180087f13  lea     r9, [rax+10h]; pHandle
0x180087f17  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; WriteFn
0x180087f1e  lea     rdx, ?PacReadFcn@@YAXPEAXPEAPEADPEAI@Z; AllocFn
0x180087f25  lea     rcx, [rax-40h]; UserState
0x180087f29  call    cs:__imp_MesEncodeIncrementalHandleCreate
0x180087f2f  test    eax, eax
0x180087f31  jz      short loc_180087F3D
0x180087f33  mov     edi, 0C000009Ah
0x180087f38  jmp     loc_18008802C
0x180087f3d  lea     rax, [rsp+78h+arg_0]
0x180087f45  mov     [rsp+78h+pObject], rax; pObject
0x180087f4a  mov     [rsp+78h+nTypeIndex], 1; nTypeIndex
0x180087f52  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180087f59  lea     r8, pProxyInfo; pProxyInfo
0x180087f60  lea     rdx, pPicklingInfo; pPicklingInfo
0x180087f67  mov     rcx, [rsp+78h+Handle]; Handle
0x180087f6f  call    cs:__imp_NdrMesTypeAlignSize3
0x180087f75  mov     rsi, rax
0x180087f78  mov     [rsp+78h+var_48], esi
0x180087f7c  mov     ecx, esi; size
0x180087f7e  call    MIDL_user_allocate
0x180087f83  mov     rbx, rax
0x180087f86  mov     [rsp+78h+arg_10], rax
0x180087f8e  test    rax, rax
0x180087f91  jz      short loc_180087F33
0x180087f93  xor     edi, edi
0x180087f95  mov     [rsp+78h+var_38], esi
0x180087f99  mov     [rsp+78h+var_40], rax
0x180087f9e  mov     dword ptr [rsp+78h+pObject], edi; Operation
0x180087fa2  mov     qword ptr [rsp+78h+nTypeIndex], rdi; ReadFn
0x180087fa7  xor     r9d, r9d; WriteFn
0x180087faa  xor     r8d, r8d; AllocFn
0x180087fad  xor     edx, edx; UserState
0x180087faf  mov     rcx, [rsp+78h+Handle]; Handle
0x180087fb7  call    cs:__imp_MesIncrementalHandleReset
0x180087fbd  test    eax, eax
0x180087fbf  jz      short loc_180087FCD
0x180087fc1  mov     ecx, eax; Status
0x180087fc3  call    cs:__imp_I_RpcMapWin32Status
0x180087fc9  mov     edi, eax
0x180087fcb  jmp     short loc_18008802C
0x180087fcd  lea     rax, [rsp+78h+arg_0]
0x180087fd5  mov     [rsp+78h+pObject], rax; pObject
0x180087fda  mov     [rsp+78h+nTypeIndex], 1; nTypeIndex
0x180087fe2  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180087fe9  lea     r8, pProxyInfo; pProxyInfo
0x180087ff0  lea     rdx, pPicklingInfo; pPicklingInfo
0x180087ff7  mov     rcx, [rsp+78h+Handle]; Handle
0x180087fff  call    cs:__imp_NdrMesTypeEncode3
0x180088005  nop
0x180088006  mov     [r15], rbx
0x180088009  mov     [r14], esi
0x18008800c  xor     ebx, ebx
0x18008800e  jmp     short loc_18008802C
0x180088010  mov     edi, 0C000000Dh
0x180088015  mov     rbx, [rsp+78h+arg_10]
0x18008801d  jmp     short loc_18008802C
0x18008801f  mov     edi, 0C000000Dh
0x180088024  mov     rbx, [rsp+78h+arg_10]
0x18008802c  test    rbx, rbx
0x18008802f  jz      short loc_180088039
0x180088031  mov     rcx, rbx; void *
0x180088034  call    MIDL_user_free
0x180088039  mov     rcx, [rsp+78h+Handle]; Handle
0x180088041  test    rcx, rcx
0x180088044  jz      short loc_18008804C
0x180088046  call    cs:__imp_MesHandleFree
0x18008804c  mov     eax, edi
0x18008804e  add     rsp, 50h
0x180088052  pop     r15
0x180088054  pop     r14
0x180088056  pop     rdi
0x180088057  pop     rsi
0x180088058  pop     rbx
0x180088059  retn
```
