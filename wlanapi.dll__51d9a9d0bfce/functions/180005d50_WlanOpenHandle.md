# WlanOpenHandle

- ea: `0x180005d50`
- end: `0x1800060f8`
- name: `WlanOpenHandle`
- size: `936`
- prototype: `DWORD __stdcall(DWORD dwClientVersion, PVOID pReserved, PDWORD pdwNegotiatedVersion, PHANDLE phClientHandle)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1800056e0`
- `0x18002eac0`
- `0x18002ee10`

## callees

- `0x180005d50`
- `0x180006100`
- `0x1800063a0`
- `0x180006934`
- `0x18000be60`
- `0x180017ccc`

## import_xrefs

- `RPCRT4!RpcSsDestroyClientContext` at `0x1800060d6`
- `RPCRT4!RpcSsDestroyClientContext` at `0x1800060d6`
- `RPCRT4!NdrClientCall3` at `0x180005dfb`
- `RPCRT4!NdrClientCall3` at `0x180005dfb`
- `RPCRT4!RpcExceptionFilter` at `0x1800603ee`
- `RPCRT4!RpcExceptionFilter` at `0x18006040a`
- `RPCRT4!RpcExceptionFilter` at `0x1800603ee`
- `RPCRT4!RpcExceptionFilter` at `0x18006040a`
- `MobileNetworking!HtNewHandle` at `0x180005eeb`
- `MobileNetworking!HtNewHandle` at `0x180005eeb`

## pseudocode

```c
DWORD __stdcall WlanOpenHandle(
        DWORD dwClientVersion,
        PVOID pReserved,
        PDWORD pdwNegotiatedVersion,
        PHANDLE phClientHandle)
{
  _DWORD *v8; // r15
  union DOT11_OUI_HEADER *v9; // rcx
  CLIENT_CALL_RETURN v10; // rax
  DWORD Pointer; // ebx
  DWORD Context; // eax
  DWORD v13; // eax
  void *v14; // rax
  DWORD v16; // [rsp+44h] [rbp-54h] BYREF
  void *lpMem; // [rsp+48h] [rbp-50h] BYREF
  void *ContextHandle; // [rsp+50h] [rbp-48h] BYREF
  void *v19; // [rsp+58h] [rbp-40h] BYREF
  CLIENT_CALL_RETURN v20; // [rsp+60h] [rbp-38h]

  ContextHandle = 0;
  v19 = 0;
  v16 = 0;
  v8 = 0;
  lpMem = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 47, WPP_797f1b088bb039a5f91226960c081484_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  if ( pdwNegotiatedVersion && phClientHandle && !pReserved )
  {
    v20.Simple = 0;
    v10.Pointer = NdrClientCall3(
                    (MIDL_STUBLESS_PROXY_INFO *)&winwlan_ProxyInfo,
                    0,
                    0,
                    &g_strBinding,
                    dwClientVersion,
                    &v16,
                    &ContextHandle).Pointer;
    Pointer = (DWORD)v10.Pointer;
    v20.Pointer = v10.Pointer;
    v9 = WPP_GLOBAL_Control;
    if ( LODWORD(v10.Pointer) )
    {
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          49,
          WPP_797f1b088bb039a5f91226960c081484_Traceguids,
          LODWORD(v10.Pointer));
        v9 = WPP_GLOBAL_Control;
      }
      if ( Pointer == 1717 || Pointer == 1702 || Pointer == 1726 || Pointer == 1753 )
        Pointer = 1062;
    }
    else
    {
      Context = ClientCreateContext((struct _WLAN_CLIENT_CONTEXT **)&lpMem);
      Pointer = Context;
      if ( Context )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 50, WPP_797f1b088bb039a5f91226960c081484_Traceguids, Context);
          v8 = lpMem;
          goto LABEL_10;
        }
        v8 = lpMem;
      }
      else
      {
        v8 = lpMem;
        *((_QWORD *)lpMem + 8) = lpMem;
        v8[21] = 2;
        *((_QWORD *)v8 + 11) = ClientRpcCallback;
        *(_QWORD *)v8 = ContextHandle;
        v8[4] = v16;
        v13 = HtNewHandle(g_hHandleTable, v8, 1129074260, ClientDestroyContext, 1, &v19);
        Pointer = v13;
        if ( !v13 )
        {
          *pdwNegotiatedVersion = v16;
          v14 = v19;
          *phClientHandle = v19;
          *((_QWORD *)v8 + 1) = v14;
LABEL_10:
          v9 = WPP_GLOBAL_Control;
          goto LABEL_11;
        }
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 51, WPP_797f1b088bb039a5f91226960c081484_Traceguids, v13);
          goto LABEL_10;
        }
      }
    }
LABEL_11:
    if ( !Pointer )
      goto LABEL_12;
    goto LABEL_22;
  }
  Pointer = 87;
LABEL_22:
  if ( ContextHandle )
  {
    RpcWlanCloseHandle(&ContextHandle);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v8 )
  {
    ClientDestroyContext((char *)v8);
    v9 = WPP_GLOBAL_Control;
  }
LABEL_12:
  if ( v9 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v9 + 105) >= 4u
    && (*((_BYTE *)v9 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v9 + 12), 52, WPP_797f1b088bb039a5f91226960c081484_Traceguids, Pointer);
  }
  return Pointer;
}

```

## disassembly

```asm
0x180005d50  mov     rax, rsp
0x180005d53  mov     [rax+8], rbx
0x180005d57  mov     [rax+10h], rsi
0x180005d5b  mov     [rax+20h], r9
0x180005d5f  mov     [rax+18h], r8
0x180005d63  push    rdi
0x180005d64  push    r12
0x180005d66  push    r13
0x180005d68  push    r14
0x180005d6a  push    r15
0x180005d6c  sub     rsp, 70h
0x180005d70  mov     rsi, r9
0x180005d73  mov     r14, r8
0x180005d76  mov     rbx, rdx
0x180005d79  mov     r12d, ecx
0x180005d7c  xor     r13d, r13d
0x180005d7f  mov     [rax-48h], r13
0x180005d83  mov     [rax-40h], r13
0x180005d87  mov     [rax-54h], r13d
0x180005d8b  mov     r15d, r13d
0x180005d8e  mov     [rax-50h], r13
0x180005d92  lea     rdi, WPP_GLOBAL_Control
0x180005d99  mov     rcx, cs:WPP_GLOBAL_Control
0x180005da0  cmp     rcx, rdi
0x180005da3  jz      short loc_180005DAF
0x180005da5  cmp     byte ptr [rcx+69h], 4
0x180005da9  jnb     loc_180006021
0x180005daf  test    r14, r14
0x180005db2  jz      loc_180005F80
0x180005db8  test    rsi, rsi
0x180005dbb  jz      loc_180005F80
0x180005dc1  test    rbx, rbx
0x180005dc4  jnz     loc_180005F80
0x180005dca  mov     [rsp+98h+var_38], r13
0x180005dcf  lea     rax, [rsp+98h+ContextHandle]
0x180005dd4  mov     [rsp+98h+var_68], rax
0x180005dd9  lea     rax, [rsp+98h+var_54]
0x180005dde  mov     [rsp+98h+var_70], rax
0x180005de3  mov     [rsp+98h+var_78], r12d
0x180005de8  lea     r9, ?g_strBinding@@3PAGA; ushort near * g_strBinding
0x180005def  xor     r8d, r8d; pReturnValue
0x180005df2  xor     edx, edx; nProcNum
0x180005df4  lea     rcx, ?winwlan_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180005dfb  call    cs:__imp_NdrClientCall3
0x180005e01  mov     rbx, rax
0x180005e04  mov     [rsp+98h+var_38], rax
0x180005e09  mov     [rsp+98h+var_58], eax
0x180005e0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e14  jmp     short loc_180005E76
0x180005e16  mov     ebx, eax
0x180005e18  mov     [rsp+98h+var_58], eax
0x180005e1c  lea     rdx, WPP_GLOBAL_Control
0x180005e23  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e2a  cmp     rcx, rdx
0x180005e2d  jz      short loc_180005E5A
0x180005e2f  cmp     byte ptr [rcx+69h], 1
0x180005e33  jb      short loc_180005E5A
0x180005e35  test    byte ptr [rcx+6Ch], 2
0x180005e39  jz      short loc_180005E5A
0x180005e3b  mov     edx, 30h ; '0'
0x180005e40  mov     r9d, eax
0x180005e43  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x180005e4a  mov     rcx, [rcx+60h]
0x180005e4e  call    WPP_SF_d
0x180005e53  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e5a  lea     rdi, WPP_GLOBAL_Control
0x180005e61  mov     rsi, [rsp+98h+arg_18]
0x180005e69  mov     r14, [rsp+98h+arg_10]
0x180005e71  mov     r15, [rsp+98h+lpMem]
0x180005e76  test    ebx, ebx
0x180005e78  jnz     loc_180005F64
0x180005e7e  lea     rcx, [rsp+98h+lpMem]; struct _WLAN_CLIENT_CONTEXT **
0x180005e83  call    ?ClientCreateContext@@YAKPEAPEAU_WLAN_CLIENT_CONTEXT@@@Z; ClientCreateContext(_WLAN_CLIENT_CONTEXT * *)
0x180005e88  mov     ebx, eax
0x180005e8a  mov     [rsp+98h+var_58], eax
0x180005e8e  test    eax, eax
0x180005e90  jnz     loc_180005FDB
0x180005e96  mov     r15, [rsp+98h+lpMem]
0x180005e9b  mov     [r15+40h], r15
0x180005e9f  mov     dword ptr [r15+54h], 2
0x180005ea7  lea     rax, ?ClientRpcCallback@@YAXPEAU_RPC_ASYNC_STATE@@PEAXW4_RPC_ASYNC_EVENT@@@Z; ClientRpcCallback(_RPC_ASYNC_STATE *,void *,_RPC_ASYNC_EVENT)
0x180005eae  mov     [r15+58h], rax
0x180005eb2  mov     rax, [rsp+98h+ContextHandle]
0x180005eb7  mov     [r15], rax
0x180005eba  mov     eax, [rsp+98h+var_54]
0x180005ebe  mov     [r15+10h], eax
0x180005ec2  lea     rax, [rsp+98h+var_40]
0x180005ec7  mov     [rsp+98h+var_70], rax
0x180005ecc  mov     [rsp+98h+var_78], 1
0x180005ed4  lea     r9, ?ClientDestroyContext@@YAXPEAX@Z; ClientDestroyContext(void *)
0x180005edb  mov     r8d, 434C4E54h
0x180005ee1  mov     rdx, r15
0x180005ee4  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x180005eeb  call    cs:__imp_HtNewHandle
0x180005ef1  mov     ebx, eax
0x180005ef3  mov     [rsp+98h+var_58], eax
0x180005ef7  test    eax, eax
0x180005ef9  jnz     loc_18000604C
0x180005eff  mov     eax, [rsp+98h+var_54]
0x180005f03  mov     [r14], eax
0x180005f06  mov     rax, [rsp+98h+var_40]
0x180005f0b  mov     [rsi], rax
0x180005f0e  mov     [r15+8], rax
0x180005f12  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f19  test    ebx, ebx
0x180005f1b  jnz     short loc_180005F89
0x180005f1d  cmp     rcx, rdi
0x180005f20  jnz     short loc_180005F3E
0x180005f22  mov     eax, ebx
0x180005f24  lea     r11, [rsp+98h+var_28]
0x180005f29  mov     rbx, [r11+30h]
0x180005f2d  mov     rsi, [r11+38h]
0x180005f31  mov     rsp, r11
0x180005f34  pop     r15
0x180005f36  pop     r14
0x180005f38  pop     r13
0x180005f3a  pop     r12
0x180005f3c  pop     rdi
0x180005f3d  retn
0x180005f3e  cmp     byte ptr [rcx+69h], 4
0x180005f42  jb      short loc_180005F22
0x180005f44  test    byte ptr [rcx+6Ch], 2
0x180005f48  jz      short loc_180005F22
0x180005f4a  mov     edx, 34h ; '4'
0x180005f4f  mov     r9d, ebx
0x180005f52  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x180005f59  mov     rcx, [rcx+60h]
0x180005f5d  call    WPP_SF_d
0x180005f62  jmp     short loc_180005F22
0x180005f64  cmp     rcx, rdi
0x180005f67  jnz     short loc_180005FAE
0x180005f69  cmp     ebx, 6B5h
0x180005f6f  jnz     loc_180006097
0x180005f75  mov     ebx, 426h
0x180005f7a  mov     [rsp+98h+var_58], ebx
0x180005f7e  jmp     short loc_180005F19
0x180005f80  mov     ebx, 57h ; 'W'
0x180005f85  mov     [rsp+98h+var_58], ebx
0x180005f89  cmp     [rsp+98h+ContextHandle], 0
0x180005f8f  jnz     loc_1800060BB
0x180005f95  test    r15, r15
0x180005f98  jz      short loc_180005F1D
0x180005f9a  mov     rcx, r15; lpMem
0x180005f9d  call    ?ClientDestroyContext@@YAXPEAX@Z; ClientDestroyContext(void *)
0x180005fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fa9  jmp     loc_180005F1D
0x180005fae  cmp     byte ptr [rcx+69h], 1
0x180005fb2  jb      short loc_180005F69
0x180005fb4  test    byte ptr [rcx+6Ch], 2
0x180005fb8  jz      short loc_180005F69
0x180005fba  mov     edx, 31h ; '1'
0x180005fbf  mov     r9d, ebx
0x180005fc2  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x180005fc9  mov     rcx, [rcx+60h]
0x180005fcd  call    WPP_SF_d
0x180005fd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fd9  jmp     short loc_180005F69
0x180005fdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fe2  cmp     rcx, rdi
0x180005fe5  jz      loc_18000608D
0x180005feb  cmp     byte ptr [rcx+69h], 1
0x180005fef  jb      loc_18000608D
0x180005ff5  test    byte ptr [rcx+6Ch], 2
0x180005ff9  jz      loc_18000608D
0x180005fff  mov     edx, 32h ; '2'
0x180006004  mov     r9d, eax
0x180006007  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x18000600e  mov     rcx, [rcx+60h]
0x180006012  call    WPP_SF_d
0x180006017  mov     r15, [rsp+98h+lpMem]
0x18000601c  jmp     loc_180005F12
0x180006021  test    byte ptr [rcx+6Ch], 2
0x180006025  jz      loc_180005DAF
0x18000602b  mov     edx, 2Fh ; '/'
0x180006030  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x180006037  mov     rcx, [rcx+60h]
0x18000603b  call    WPP_SF_
0x180006040  mov     rcx, cs:WPP_GLOBAL_Control
0x180006047  jmp     loc_180005DAF
0x18000604c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006053  cmp     rcx, rdi
0x180006056  jz      loc_180005F19
0x18000605c  cmp     byte ptr [rcx+69h], 1
0x180006060  jb      loc_180005F19
0x180006066  test    byte ptr [rcx+6Ch], 2
0x18000606a  jz      loc_180005F19
0x180006070  mov     edx, 33h ; '3'
0x180006075  mov     r9d, eax
0x180006078  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x18000607f  mov     rcx, [rcx+60h]
0x180006083  call    WPP_SF_d
0x180006088  jmp     loc_180005F12
0x18000608d  mov     r15, [rsp+98h+lpMem]
0x180006092  jmp     loc_180005F19
0x180006097  mov     eax, ebx
0x180006099  sub     eax, 6A6h
0x18000609e  jz      loc_180005F75
0x1800060a4  sub     eax, 18h
0x1800060a7  jz      loc_180005F75
0x1800060ad  cmp     eax, 1Bh
0x1800060b0  jnz     loc_180005F7A
0x1800060b6  jmp     loc_180005F75
0x1800060bb  lea     rcx, [rsp+98h+ContextHandle]
0x1800060c0  call    RpcWlanCloseHandle
0x1800060c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060cc  jmp     loc_180005F95
0x1800060d1  lea     rcx, [rsp+98h+ContextHandle]; ContextHandle
0x1800060d6  call    cs:__imp_RpcSsDestroyClientContext
0x1800060dc  lea     rdi, WPP_GLOBAL_Control
0x1800060e3  mov     ebx, [rsp+98h+var_58]
0x1800060e7  mov     r15, [rsp+98h+lpMem]
0x1800060ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060f3  jmp     loc_180005F95
0x1800603e0  push    rbp
0x1800603e2  sub     rsp, 40h
0x1800603e6  mov     rbp, rdx
0x1800603e9  mov     rcx, [rcx]
0x1800603ec  mov     ecx, [rcx]; ExceptionCode
0x1800603ee  call    cs:__imp_RpcExceptionFilter
0x1800603f4  nop
0x1800603f5  add     rsp, 40h
0x1800603f9  pop     rbp
0x1800603fa  retn
0x1800603fc  push    rbp
0x1800603fe  sub     rsp, 40h
0x180060402  mov     rbp, rdx
0x180060405  mov     rcx, [rcx]
0x180060408  mov     ecx, [rcx]; ExceptionCode
0x18006040a  call    cs:__imp_RpcExceptionFilter
0x180060410  nop
0x180060411  add     rsp, 40h
0x180060415  pop     rbp
0x180060416  retn
```
