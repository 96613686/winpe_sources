# CRpcClientBinding::RcInitialize(CMachineId const &,ushort const *,ushort const *,RC_AUTHENTICATE)

- ea: `0x18000add0`
- end: `0x18000aebd`
- name: `?RcInitialize@CRpcClientBinding@@QEAAXAEBUCMachineId@@PEBG1W4RC_AUTHENTICATE@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004f90`

## callees

- `0x18000add0`
- `0x18000aec4`
- `0x18000d038`
- `0x180011000`

## import_xrefs

- `msvcrt!mbstowcs_s` at `0x18000ae27`
- `msvcrt!mbstowcs_s` at `0x18000ae27`
- `RPCRT4!RpcStringFreeW` at `0x18000ae71`
- `RPCRT4!RpcStringFreeW` at `0x18000ae71`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000ae51`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000ae51`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000ae64`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000ae64`

## pseudocode

```c
__int64 __fastcall CRpcClientBinding::RcInitialize(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 *a4)
{
  bool v4; // zf
  __int64 v7; // rax
  RPC_STATUS v8; // eax
  RPC_STATUS v9; // ebx
  __int64 result; // rax
  RPC_WSTR String; // [rsp+30h] [rbp-38h] BYREF
  wchar_t DstBuf[16]; // [rsp+38h] [rbp-30h] BYREF

  v4 = *(_BYTE *)(a2 + 15) == 0;
  String = 0;
  if ( !v4 )
    TrkRaiseWin32Error(1210);
  v7 = -1;
  do
    ++v7;
  while ( *(_BYTE *)(a2 + v7) );
  mbstowcs_s(0, DstBuf, 0x10u, (const char *)a2, v7 + 1);
  v8 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_np", DstBuf, a4, 0, &String);
  if ( v8 )
    TrkRaiseWin32Error(v8);
  v9 = RpcBindingFromStringBindingW(String, (RPC_BINDING_HANDLE *)(a1 + 40));
  RpcStringFreeW(&String);
  if ( v9 )
    TrkRaiseWin32Error(v9);
  result = CTrkRpcConfig::RpcSecurityEnabled();
  *(_DWORD *)(a1 + 32) = 1;
  return result;
}

```

## disassembly

```asm
0x18000add0  mov     [rsp+arg_10], rbx
0x18000add5  push    rdi
0x18000add6  sub     rsp, 60h
0x18000adda  mov     rax, cs:__security_cookie
0x18000ade1  xor     rax, rsp
0x18000ade4  mov     [rsp+68h+var_10], rax
0x18000ade9  cmp     byte ptr [rdx+0Fh], 0
0x18000aded  mov     rbx, r9
0x18000adf0  mov     rdi, rcx
0x18000adf3  mov     [rsp+68h+String], 0
0x18000adfc  jnz     loc_18000AEA2
0x18000ae02  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ae06  inc     rax
0x18000ae09  cmp     byte ptr [rdx+rax], 0
0x18000ae0d  jnz     short loc_18000AE06
0x18000ae0f  inc     rax
0x18000ae12  mov     r9, rdx; SrcBuf
0x18000ae15  lea     rdx, [rsp+68h+DstBuf]; DstBuf
0x18000ae1a  mov     [rsp+68h+MaxCount], rax; MaxCount
0x18000ae1f  mov     r8d, 10h; SizeInWords
0x18000ae25  xor     ecx, ecx; PtNumOfCharConverted
0x18000ae27  call    cs:__imp_mbstowcs_s
0x18000ae2d  lea     rax, [rsp+68h+String]
0x18000ae32  mov     r9, rbx; Endpoint
0x18000ae35  mov     [rsp+68h+StringBinding], rax; StringBinding
0x18000ae3a  lea     r8, [rsp+68h+DstBuf]; NetworkAddr
0x18000ae3f  lea     rdx, ?s_tszTrkWksRemoteRpcProtocol@@3QBGB; "ncacn_np"
0x18000ae46  mov     [rsp+68h+MaxCount], 0; Options
0x18000ae4f  xor     ecx, ecx; ObjUuid
0x18000ae51  call    cs:__imp_RpcStringBindingComposeW
0x18000ae57  test    eax, eax
0x18000ae59  jnz     short loc_18000AEAD
0x18000ae5b  mov     rcx, [rsp+68h+String]; StringBinding
0x18000ae60  lea     rdx, [rdi+28h]; Binding
0x18000ae64  call    cs:__imp_RpcBindingFromStringBindingW
0x18000ae6a  lea     rcx, [rsp+68h+String]; String
0x18000ae6f  mov     ebx, eax
0x18000ae71  call    cs:__imp_RpcStringFreeW
0x18000ae77  test    ebx, ebx
0x18000ae79  jnz     short loc_18000AEB5
0x18000ae7b  call    ?RpcSecurityEnabled@CTrkRpcConfig@@SAHXZ; CTrkRpcConfig::RpcSecurityEnabled(void)
0x18000ae80  mov     dword ptr [rdi+20h], 1
0x18000ae87  mov     rcx, [rsp+68h+var_10]
0x18000ae8c  xor     rcx, rsp; StackCookie
0x18000ae8f  call    __security_check_cookie
0x18000ae94  mov     rbx, [rsp+68h+arg_10]
0x18000ae9c  add     rsp, 60h
0x18000aea0  pop     rdi
0x18000aea1  retn
0x18000aea2  mov     ecx, 4BAh; int
0x18000aea7  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000aead  mov     ecx, eax; int
0x18000aeaf  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000aeb5  mov     ecx, ebx; int
0x18000aeb7  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
```
