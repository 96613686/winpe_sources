# RpcAutoImpersonate::RpcAutoImpersonate(ushort const *,int)

- ea: `0x18000a044`
- end: `0x18000a0e9`
- name: `??0RpcAutoImpersonate@@QEAA@PEBGH@Z`
- size: `165`
- prototype: `RpcAutoImpersonate *(RpcAutoImpersonate *__hidden this, const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180004a40`
- `0x18000b218`
- `0x18000dca8`

## callees

- `0x180005650`
- `0x180008c4c`
- `0x18000a044`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18000a061`
- `RPCRT4!RpcImpersonateClient` at `0x18000a061`

## pseudocode

```c
RpcAutoImpersonate *__fastcall RpcAutoImpersonate::RpcAutoImpersonate(
        RpcAutoImpersonate *this,
        const unsigned __int16 *a2)
{
  RPC_STATUS v4; // eax
  EventManager *v5; // rcx
  RPC_STATUS v6; // edi
  void **pExceptionObject; // [rsp+30h] [rbp-48h] BYREF
  char v9; // [rsp+38h] [rbp-40h]
  char *v10; // [rsp+40h] [rbp-38h]
  __int64 v11; // [rsp+48h] [rbp-30h]
  __int64 v12; // [rsp+50h] [rbp-28h]
  RPC_STATUS v13; // [rsp+58h] [rbp-20h]
  __int64 v14; // [rsp+5Ch] [rbp-1Ch]

  *(_DWORD *)this = 1;
  v4 = RpcImpersonateClient(0);
  v6 = v4;
  if ( v4 )
  {
    EventManager::EvtReport(v5, &IMPERSONATION_FAILURE, a2, v4);
    v9 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v11 = 0;
    v10 = byte_180052608;
    v12 = 0;
    v13 = v6;
    v14 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x18000a044  mov     [rsp+arg_0], rbx
0x18000a049  mov     [rsp+arg_8], rsi
0x18000a04e  push    rdi
0x18000a04f  sub     rsp, 70h
0x18000a053  mov     rbx, rcx
0x18000a056  mov     dword ptr [rcx], 1
0x18000a05c  xor     ecx, ecx; BindingHandle
0x18000a05e  mov     rsi, rdx
0x18000a061  call    cs:__imp_RpcImpersonateClient
0x18000a068  nop     dword ptr [rax+rax+00h]
0x18000a06d  mov     edi, eax
0x18000a06f  test    eax, eax
0x18000a071  jz      short loc_18000A0D3
0x18000a073  mov     r9d, eax; unsigned int
0x18000a076  lea     rdx, IMPERSONATION_FAILURE; struct _EVENT_DESCRIPTOR *
0x18000a07d  mov     r8, rsi; unsigned __int16 *
0x18000a080  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x18000a085  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000a08c  mov     [rsp+78h+var_40], 0
0x18000a091  mov     [rsp+78h+pExceptionObject], rax
0x18000a096  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000a09d  lea     rax, byte_180052608
0x18000a0a4  mov     [rsp+78h+var_30], 0
0x18000a0ad  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000a0b2  mov     [rsp+78h+var_38], rax
0x18000a0b7  mov     [rsp+78h+var_28], 0
0x18000a0c0  mov     [rsp+78h+var_20], edi
0x18000a0c4  mov     [rsp+78h+var_1C], 0FFFFFFFFFFFFFFFFh
0x18000a0cd  call    _CxxThrowException_0
0x18000a0d3  lea     r11, [rsp+78h+var_8]
0x18000a0d8  mov     rax, rbx
0x18000a0db  mov     rbx, [r11+10h]
0x18000a0df  mov     rsi, [r11+18h]
0x18000a0e3  mov     rsp, r11
0x18000a0e6  pop     rdi
0x18000a0e7  retn
```
