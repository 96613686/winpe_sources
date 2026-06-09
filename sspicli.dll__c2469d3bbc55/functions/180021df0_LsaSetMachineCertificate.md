# LsaSetMachineCertificate

- ea: `0x180021df0`
- end: `0x180021f1f`
- name: `LsaSetMachineCertificate`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180021df0`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180021e97`
- `RPCRT4!RpcStringFreeW` at `0x180021e97`
- `RPCRT4!I_RpcExceptionFilter` at `0x180022563`
- `RPCRT4!I_RpcExceptionFilter` at `0x180022563`
- `RPCRT4!I_RpcMapWin32Status` at `0x180021eeb`
- `RPCRT4!I_RpcMapWin32Status` at `0x180021eeb`
- `RPCRT4!RpcStringBindingComposeW` at `0x180021e60`
- `RPCRT4!RpcStringBindingComposeW` at `0x180021e60`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180021e8a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180021e8a`
- `RPCRT4!RpcBindingFree` at `0x180021f04`
- `RPCRT4!RpcBindingFree` at `0x18002257e`
- `RPCRT4!RpcBindingFree` at `0x180021f04`
- `RPCRT4!RpcBindingFree` at `0x18002257e`
- `RPCRT4!NdrClientCall3` at `0x180021ed5`
- `RPCRT4!NdrClientCall3` at `0x180021ed5`

## pseudocode

```c
__int64 __fastcall LsaSetMachineCertificate(int a1, __int64 a2, int a3, __int64 a4)
{
  RPC_STATUS v8; // eax
  RPC_STATUS Pointer; // ebx
  CLIENT_CALL_RETURN v10; // rax
  __int64 v12; // [rsp+20h] [rbp-68h]
  int v13; // [rsp+30h] [rbp-58h]
  RPC_BINDING_HANDLE Binding; // [rsp+48h] [rbp-40h] BYREF
  RPC_WSTR StringBinding; // [rsp+50h] [rbp-38h] BYREF
  CLIENT_CALL_RETURN v16; // [rsp+58h] [rbp-30h]

  Binding = 0;
  StringBinding = 0;
  if ( a1 && a2 && a3 && a4 )
  {
    v8 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)L"LSA_IUM_MK_ENDPOINT", 0, &StringBinding);
    Pointer = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
      {
        Pointer = (unsigned __int16)v8;
LABEL_8:
        Pointer |= 0xC0070000;
      }
    }
    else
    {
      Pointer = RpcBindingFromStringBindingW(StringBinding, &Binding);
      RpcStringFreeW(&StringBinding);
      if ( !Pointer )
      {
        v16.Simple = 0;
        v13 = a3;
        LODWORD(v12) = a1;
        v10.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180030B70, 0, 0, Binding, v12, a2, v13, a4).Pointer;
        Pointer = (RPC_STATUS)v10.Pointer;
        v16.Pointer = v10.Pointer;
        RpcBindingFree(&Binding);
        return (unsigned int)Pointer;
      }
      if ( Pointer > 0 )
      {
        Pointer = (unsigned __int16)Pointer;
        goto LABEL_8;
      }
    }
    return (unsigned int)Pointer;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x180021df0  mov     r11, rsp
0x180021df3  push    rbx
0x180021df4  push    rsi
0x180021df5  push    rdi
0x180021df6  push    r14
0x180021df8  push    r15
0x180021dfa  sub     rsp, 60h
0x180021dfe  mov     rdi, r9
0x180021e01  mov     esi, r8d
0x180021e04  mov     r14, rdx
0x180021e07  mov     r15d, ecx
0x180021e0a  mov     qword ptr [r11-40h], 0
0x180021e12  mov     qword ptr [r11-38h], 0
0x180021e1a  test    ecx, ecx
0x180021e1c  jz      loc_180021F0E
0x180021e22  test    rdx, rdx
0x180021e25  jz      loc_180021F0E
0x180021e2b  test    r8d, r8d
0x180021e2e  jz      loc_180021F0E
0x180021e34  test    r9, r9
0x180021e37  jz      loc_180021F0E
0x180021e3d  lea     rax, [r11-38h]
0x180021e41  mov     [r11-60h], rax
0x180021e45  mov     qword ptr [r11-68h], 0
0x180021e4d  lea     r9, aLsaIumMkEndpoi; "LSA_IUM_MK_ENDPOINT"
0x180021e54  xor     r8d, r8d; NetworkAddr
0x180021e57  lea     rdx, ProtSeq; "ncalrpc"
0x180021e5e  xor     ecx, ecx; ObjUuid
0x180021e60  call    cs:__imp_RpcStringBindingComposeW
0x180021e66  mov     ebx, eax
0x180021e68  test    eax, eax
0x180021e6a  jz      short loc_180021E80
0x180021e6c  jle     loc_180021F0A
0x180021e72  movzx   ebx, ax
0x180021e75  or      ebx, 0C0070000h
0x180021e7b  jmp     loc_180021F0A
0x180021e80  lea     rdx, [rsp+88h+Binding]; Binding
0x180021e85  mov     rcx, [rsp+88h+StringBinding]; StringBinding
0x180021e8a  call    cs:__imp_RpcBindingFromStringBindingW
0x180021e90  mov     ebx, eax
0x180021e92  lea     rcx, [rsp+88h+StringBinding]; String
0x180021e97  call    cs:__imp_RpcStringFreeW
0x180021e9d  test    ebx, ebx
0x180021e9f  jz      short loc_180021EA8
0x180021ea1  jle     short loc_180021F0A
0x180021ea3  movzx   ebx, bx
0x180021ea6  jmp     short loc_180021E75
0x180021ea8  mov     [rsp+88h+var_30], 0
0x180021eb1  mov     [rsp+88h+var_50], rdi
0x180021eb6  mov     [rsp+88h+var_58], esi
0x180021eba  mov     [rsp+88h+var_60], r14
0x180021ebf  mov     dword ptr [rsp+88h+var_68], r15d
0x180021ec4  mov     r9, [rsp+88h+Binding]
0x180021ec9  xor     r8d, r8d; pReturnValue
0x180021ecc  xor     edx, edx; nProcNum
0x180021ece  lea     rcx, stru_180030B70; pProxyInfo
0x180021ed5  call    cs:__imp_NdrClientCall3
0x180021edb  mov     rbx, rax
0x180021ede  mov     [rsp+88h+var_30], rax
0x180021ee3  mov     [rsp+88h+var_48], eax
0x180021ee7  jmp     short loc_180021EFF
0x180021ee9  mov     ecx, eax; Status
0x180021eeb  call    cs:__imp_I_RpcMapWin32Status
0x180021ef1  mov     ebx, 0C0000001h
0x180021ef6  test    eax, eax
0x180021ef8  cmovs   ebx, eax
0x180021efb  mov     [rsp+88h+var_48], ebx
0x180021eff  lea     rcx, [rsp+88h+Binding]; Binding
0x180021f04  call    cs:__imp_RpcBindingFree
0x180021f0a  mov     eax, ebx
0x180021f0c  jmp     short loc_180021F13
0x180021f0e  mov     eax, 0C000000Dh
0x180021f13  add     rsp, 60h
0x180021f17  pop     r15
0x180021f19  pop     r14
0x180021f1b  pop     rdi
0x180021f1c  pop     rsi
0x180021f1d  pop     rbx
0x180021f1e  retn
0x180022555  push    rbp
0x180022557  sub     rsp, 40h
0x18002255b  mov     rbp, rdx
0x18002255e  mov     rcx, [rcx]
0x180022561  mov     ecx, [rcx]; ExceptionCode
0x180022563  call    cs:__imp_I_RpcExceptionFilter
0x180022569  nop
0x18002256a  add     rsp, 40h
0x18002256e  pop     rbp
0x18002256f  retn
0x180022571  push    rbp
0x180022573  sub     rsp, 40h
0x180022577  mov     rbp, rdx
0x18002257a  lea     rcx, [rbp+48h]; Binding
0x18002257e  call    cs:__imp_RpcBindingFree
0x180022584  nop
0x180022585  add     rsp, 40h
0x180022589  pop     rbp
0x18002258a  retn
```
