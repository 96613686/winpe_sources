# SampSecureBind(ushort *,ulong,ulong)

- ea: `0x180016288`
- end: `0x1800163c0`
- name: `?SampSecureBind@@YAPEAXPEAGKK@Z`
- size: `312`
- prototype: `void *__fastcall(LPCWSTR ServiceName, unsigned int AuthnLevel, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b3b4`
- `0x180013060`
- `0x180013490`
- `0x1800142a0`

## callees

- `0x180005630`
- `0x180015d48`
- `0x180016288`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016390`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016390`
- `RPCRT4!RpcBindingFree` at `0x1800163a9`
- `RPCRT4!RpcBindingFree` at `0x1800163a9`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800162db`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800162db`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800162ed`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800162ed`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x180016385`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x180016385`
- `RPCRT4!RpcStringFreeW` at `0x1800162f9`
- `RPCRT4!RpcStringFreeW` at `0x1800162f9`

## pseudocode

```c
RPC_BINDING_HANDLE __fastcall SampSecureBind(char *ServiceName, __int64 AuthnLevel, int a3, unsigned __int16 a4)
{
  RPC_STATUS v4; // esi
  unsigned int v5; // r15d
  __int64 v7; // r8
  unsigned __int16 *v8; // r8
  unsigned __int16 *v9; // r9
  unsigned __int16 *v10; // rdx
  unsigned __int16 *v11; // r8
  int SpnW; // edi
  unsigned __int16 *v14; // rbx
  unsigned __int16 *Options; // [rsp+20h] [rbp-28h]
  RPC_WSTR String; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int16 *v17; // [rsp+38h] [rbp-10h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+98h] [rbp+50h] BYREF

  v4 = 0;
  Binding = 0;
  String = 0;
  v5 = AuthnLevel;
  v7 = (unsigned int)(a3 - 1);
  if ( (_DWORD)v7 )
  {
    v8 = (unsigned __int16 *)(unsigned int)(v7 - 1);
    if ( (_DWORD)v8 )
    {
      if ( (_DWORD)v8 != 1 )
        goto LABEL_10;
      v9 = 0;
      v10 = L"ncacn_ip_tcp";
      v11 = (unsigned __int16 *)ServiceName;
    }
    else
    {
      v9 = L"samss lpc";
      v11 = 0;
      v10 = L"ncalrpc";
    }
    if ( RpcStringBindingComposeW(0, v10, v11, v9, 0, &String) )
      return 0;
    v4 = RpcBindingFromStringBindingW(String, &Binding);
    RpcStringFreeW(&String);
  }
  else
  {
    RpcpBindRpc(ServiceName, AuthnLevel, v7, &Binding);
  }
LABEL_10:
  if ( Binding )
  {
    SpnW = 0;
    if ( v5 != 1 )
    {
      v14 = 0;
      v17 = 0;
      if ( !ServiceName )
      {
LABEL_15:
        v4 = RpcBindingSetAuthInfoW(Binding, v14, v5, 9u, 0, 2u);
        LocalFree(v14);
        goto LABEL_16;
      }
      SpnW = SampDsMakeSpnW(L"host", (LPCWSTR)ServiceName, v8, a4, Options, &v17);
      if ( SpnW >= 0 )
      {
        v14 = v17;
        goto LABEL_15;
      }
    }
LABEL_16:
    if ( Binding && (v4 || SpnW < 0) )
      RpcBindingFree(&Binding);
  }
  return Binding;
}

```

## disassembly

```asm
0x180016288  push    rbp
0x18001628a  push    rbx
0x18001628b  push    rsi
0x18001628c  push    rdi
0x18001628d  push    r14
0x18001628f  push    r15
0x180016291  mov     rbp, rsp
0x180016294  sub     rsp, 48h
0x180016298  xor     esi, esi
0x18001629a  mov     [rbp+Binding], 0
0x1800162a2  mov     [rbp+String], rsi
0x1800162a6  mov     r15d, edx
0x1800162a9  mov     r14, rcx
0x1800162ac  sub     r8d, 1
0x1800162b0  jz      short loc_18001631B
0x1800162b2  sub     r8d, 1
0x1800162b6  jz      short loc_180016301
0x1800162b8  cmp     r8d, 1
0x1800162bc  jnz     short loc_180016324
0x1800162be  xor     r9d, r9d; Endpoint
0x1800162c1  lea     rdx, aNcacnIpTcp; "ncacn_ip_tcp"
0x1800162c8  mov     r8, rcx; NetworkAddr
0x1800162cb  lea     rax, [rbp+String]
0x1800162cf  xor     ecx, ecx; ObjUuid
0x1800162d1  mov     [rsp+48h+StringBinding], rax; StringBinding
0x1800162d6  mov     [rsp+48h+Options], rsi; Options
0x1800162db  call    cs:__imp_RpcStringBindingComposeW
0x1800162e1  test    eax, eax
0x1800162e3  jnz     short loc_180016314
0x1800162e5  mov     rcx, [rbp+String]; StringBinding
0x1800162e9  lea     rdx, [rbp+Binding]; Binding
0x1800162ed  call    cs:__imp_RpcBindingFromStringBindingW
0x1800162f3  lea     rcx, [rbp+String]; String
0x1800162f7  mov     esi, eax
0x1800162f9  call    cs:__imp_RpcStringFreeW
0x1800162ff  jmp     short loc_180016324
0x180016301  lea     r9, Endpoint; "samss lpc"
0x180016308  xor     r8d, r8d
0x18001630b  lea     rdx, aNcalrpc; "ncalrpc"
0x180016312  jmp     short loc_1800162CB
0x180016314  xor     eax, eax
0x180016316  jmp     loc_1800163B3
0x18001631b  lea     r9, [rbp+Binding]
0x18001631f  call    RpcpBindRpc
0x180016324  cmp     [rbp+Binding], 0
0x180016329  jz      loc_1800163AF
0x18001632f  xor     edi, edi
0x180016331  cmp     r15d, 1
0x180016335  jz      short loc_180016396
0x180016337  xor     ebx, ebx
0x180016339  mov     [rbp+var_10], rbx
0x18001633d  test    r14, r14
0x180016340  jz      short loc_180016364
0x180016342  lea     rax, [rbp+var_10]
0x180016346  mov     rdx, r14; ServiceName
0x180016349  lea     rcx, aHost_0; "host"
0x180016350  mov     [rsp+48h+StringBinding], rax; unsigned __int16 **
0x180016355  call    ?SampDsMakeSpnW@@YAJPEAG00G0PEAPEAG@Z; SampDsMakeSpnW(ushort *,ushort *,ushort *,ushort,ushort *,ushort * *)
0x18001635a  mov     edi, eax
0x18001635c  test    eax, eax
0x18001635e  js      short loc_180016396
0x180016360  mov     rbx, [rbp+var_10]
0x180016364  mov     rcx, [rbp+Binding]; Binding
0x180016368  mov     r9d, 9; AuthnSvc
0x18001636e  mov     dword ptr [rsp+48h+StringBinding], 2; AuthzSvc
0x180016376  mov     r8d, r15d; AuthnLevel
0x180016379  mov     rdx, rbx; ServerPrincName
0x18001637c  mov     [rsp+48h+Options], 0; AuthIdentity
0x180016385  call    cs:__imp_RpcBindingSetAuthInfoW
0x18001638b  mov     rcx, rbx; hMem
0x18001638e  mov     esi, eax
0x180016390  call    cs:__imp_LocalFree
0x180016396  cmp     [rbp+Binding], 0
0x18001639b  jz      short loc_1800163AF
0x18001639d  test    esi, esi
0x18001639f  jnz     short loc_1800163A5
0x1800163a1  test    edi, edi
0x1800163a3  jns     short loc_1800163AF
0x1800163a5  lea     rcx, [rbp+Binding]; Binding
0x1800163a9  call    cs:__imp_RpcBindingFree
0x1800163af  mov     rax, [rbp+Binding]
0x1800163b3  add     rsp, 48h
0x1800163b7  pop     r15
0x1800163b9  pop     r14
0x1800163bb  pop     rdi
0x1800163bc  pop     rsi
0x1800163bd  pop     rbx
0x1800163be  pop     rbp
0x1800163bf  retn
```
