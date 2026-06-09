# RpcAutoImpersonate::RpcAutoImpersonate(ushort const *,int)

- ea: `0x180009afc`
- end: `0x180009b9a`
- name: `??0RpcAutoImpersonate@@QEAA@PEBGH@Z`
- size: `158`
- prototype: `RpcAutoImpersonate *__fastcall(RpcAutoImpersonate *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180004820`
- `0x18000ac28`
- `0x18000d414`

## callees

- `0x1800053b8`
- `0x18000878c`
- `0x180009afc`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180009b19`
- `RPCRT4!RpcImpersonateClient` at `0x180009b19`

## pseudocode

```c
RpcAutoImpersonate *__fastcall RpcAutoImpersonate::RpcAutoImpersonate(
        RpcAutoImpersonate *this,
        const unsigned __int16 *a2)
{
  RPC_STATUS v4; // eax
  EventManager *v5; // rcx
  RPC_STATUS v6; // edi
  void *v8; // [rsp+20h] [rbp-58h]
  const struct _GUID *v9; // [rsp+28h] [rbp-50h]
  void **pExceptionObject; // [rsp+30h] [rbp-48h] BYREF
  char v11; // [rsp+38h] [rbp-40h]
  char *v12; // [rsp+40h] [rbp-38h]
  __int64 v13; // [rsp+48h] [rbp-30h]
  __int64 v14; // [rsp+50h] [rbp-28h]
  RPC_STATUS v15; // [rsp+58h] [rbp-20h]
  __int64 v16; // [rsp+5Ch] [rbp-1Ch]

  *(_DWORD *)this = 1;
  v4 = RpcImpersonateClient(0);
  v6 = v4;
  if ( v4 )
  {
    EventManager::EvtReport(v5, &IMPERSONATION_FAILURE, a2, v4, v8, v9);
    v11 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v13 = 0;
    v12 = byte_1800505F8;
    v14 = 0;
    v15 = v6;
    v16 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x180009afc  mov     [rsp+arg_0], rbx
0x180009b01  mov     [rsp+arg_8], rsi
0x180009b06  push    rdi
0x180009b07  sub     rsp, 70h
0x180009b0b  mov     rbx, rcx
0x180009b0e  mov     dword ptr [rcx], 1
0x180009b14  xor     ecx, ecx; BindingHandle
0x180009b16  mov     rsi, rdx
0x180009b19  call    cs:__imp_RpcImpersonateClient
0x180009b1f  mov     edi, eax
0x180009b21  test    eax, eax
0x180009b23  jz      short loc_180009B85
0x180009b25  mov     r9d, eax; unsigned int
0x180009b28  lea     rdx, IMPERSONATION_FAILURE; struct _EVENT_DESCRIPTOR *
0x180009b2f  mov     r8, rsi; unsigned __int16 *
0x180009b32  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x180009b37  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180009b3e  mov     [rsp+78h+var_40], 0
0x180009b43  mov     [rsp+78h+pExceptionObject], rax
0x180009b48  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180009b4f  lea     rax, byte_1800505F8
0x180009b56  mov     [rsp+78h+var_30], 0
0x180009b5f  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180009b64  mov     [rsp+78h+var_38], rax
0x180009b69  mov     [rsp+78h+var_28], 0
0x180009b72  mov     [rsp+78h+var_20], edi
0x180009b76  mov     [rsp+78h+var_1C], 0FFFFFFFFFFFFFFFFh
0x180009b7f  call    _CxxThrowException_0
0x180009b85  lea     r11, [rsp+78h+var_8]
0x180009b8a  mov     rax, rbx
0x180009b8d  mov     rbx, [r11+10h]
0x180009b91  mov     rsi, [r11+18h]
0x180009b95  mov     rsp, r11
0x180009b98  pop     rdi
0x180009b99  retn
```
