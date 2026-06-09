# WFDOpenHandleLib(ulong,ulong *,void * *)

- ea: `0x1800038fc`
- end: `0x180003c73`
- name: `?WFDOpenHandleLib@@YAKKPEAKPEAPEAX@Z`
- size: `887`
- prototype: `unsigned int __fastcall(unsigned int, unsigned int *, void **)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180003680`
- `0x180038938`

## callees

- `0x1800038d0`
- `0x1800038fc`
- `0x180003c7c`
- `0x1800063a0`
- `0x180006934`
- `0x180006f80`
- `0x180017ccc`

## import_xrefs

- `RPCRT4!RpcSsDestroyClientContext` at `0x180003c39`
- `RPCRT4!RpcSsDestroyClientContext` at `0x180003c39`
- `RPCRT4!NdrClientCall3` at `0x1800039a0`
- `RPCRT4!NdrClientCall3` at `0x1800039a0`
- `RPCRT4!RpcExceptionFilter` at `0x180060322`
- `RPCRT4!RpcExceptionFilter` at `0x18006033e`
- `RPCRT4!RpcExceptionFilter` at `0x180060322`
- `RPCRT4!RpcExceptionFilter` at `0x18006033e`
- `MobileNetworking!HtNewHandle` at `0x180003a96`
- `MobileNetworking!HtNewHandle` at `0x180003a96`

## pseudocode

```c
__int64 __fastcall WFDOpenHandleLib(int a1, unsigned int *a2, void **a3)
{
  struct _WFD_CLIENT_CONTEXT *v6; // rdi
  union DOT11_OUI_HEADER *v7; // r10
  CLIENT_CALL_RETURN v8; // rax
  unsigned int Pointer; // ebx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  unsigned int v12; // eax
  void *v13; // rax
  struct _WFD_CLIENT_CONTEXT *v15; // [rsp+48h] [rbp-50h] BYREF
  void *ContextHandle; // [rsp+50h] [rbp-48h] BYREF
  void *v17; // [rsp+58h] [rbp-40h] BYREF
  CLIENT_CALL_RETURN v18; // [rsp+60h] [rbp-38h]
  unsigned int v19; // [rsp+B8h] [rbp+20h] BYREF

  ContextHandle = 0;
  v17 = 0;
  v19 = 0;
  v6 = 0;
  v15 = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 67, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( a2 && a3 )
  {
    v18.Simple = 0;
    v8.Pointer = NdrClientCall3(
                   (MIDL_STUBLESS_PROXY_INFO *)&winwlan_ProxyInfo,
                   0x4Cu,
                   0,
                   &g_strBinding,
                   a1,
                   &v19,
                   &ContextHandle).Pointer;
    Pointer = (unsigned int)v8.Pointer;
    v18.Pointer = v8.Pointer;
    if ( LODWORD(v8.Pointer) )
    {
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          69,
          WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids,
          LODWORD(v8.Pointer));
      }
      v11 = ServiceStatus(Pointer);
    }
    else
    {
      v10 = wfdClientCreateContext(&v15);
      v11 = v10;
      if ( v10 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 70, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, v10);
          v6 = v15;
          goto LABEL_9;
        }
        v6 = v15;
      }
      else
      {
        v6 = v15;
        *((_QWORD *)v15 + 8) = v15;
        *((_DWORD *)v6 + 21) = 2;
        *((_QWORD *)v6 + 11) = wfdClientRpcCallback;
        *(_QWORD *)v6 = ContextHandle;
        *((_DWORD *)v6 + 4) = v19;
        v12 = HtNewHandle(g_hHandleTable, v6, 1466525252, wfdClientDestroyContext, 1, &v17);
        v11 = v12;
        if ( !v12 )
        {
          *a2 = v19;
          v13 = v17;
          *a3 = v17;
          *((_QWORD *)v6 + 1) = v13;
LABEL_9:
          v7 = WPP_GLOBAL_Control;
          goto LABEL_10;
        }
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 71, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, v12);
          goto LABEL_9;
        }
      }
    }
  }
  else
  {
    v11 = 87;
  }
LABEL_10:
  if ( v11 )
  {
    if ( ContextHandle )
    {
      RpcWlanCloseHandle(&ContextHandle);
      v7 = WPP_GLOBAL_Control;
    }
    if ( v6 )
    {
      wfdClientDestroyContext(v6);
      v7 = WPP_GLOBAL_Control;
    }
  }
  if ( v7 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v7 + 105) >= 4u
    && (*((_BYTE *)v7 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v7 + 12), 72, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x1800038fc  mov     rax, rsp
0x1800038ff  mov     [rax+18h], r8
0x180003903  mov     [rax+10h], rdx
0x180003907  push    rbx
0x180003908  push    rsi
0x180003909  push    rdi
0x18000390a  push    r14
0x18000390c  push    r15
0x18000390e  sub     rsp, 70h
0x180003912  mov     r14, r8
0x180003915  mov     r15, rdx
0x180003918  mov     ebx, ecx
0x18000391a  mov     qword ptr [rax-48h], 0
0x180003922  mov     qword ptr [rax-40h], 0
0x18000392a  mov     dword ptr [rax+20h], 0
0x180003931  xor     edi, edi
0x180003933  mov     [rax-50h], rdi
0x180003937  lea     rsi, WPP_GLOBAL_Control
0x18000393e  mov     r10, cs:WPP_GLOBAL_Control
0x180003945  cmp     r10, rsi
0x180003948  jz      short loc_180003955
0x18000394a  cmp     byte ptr [r10+69h], 4
0x18000394f  jnb     loc_180003B29
0x180003955  test    r15, r15
0x180003958  jz      loc_180003B1E
0x18000395e  test    r14, r14
0x180003961  jz      loc_180003B1E
0x180003967  mov     [rsp+98h+var_38], 0
0x180003970  lea     rax, [rsp+98h+ContextHandle]
0x180003975  mov     [rsp+98h+var_68], rax
0x18000397a  lea     rax, [rsp+98h+arg_18]
0x180003982  mov     [rsp+98h+var_70], rax
0x180003987  mov     [rsp+98h+var_78], ebx
0x18000398b  lea     r9, ?g_strBinding@@3PAGA; ushort near * g_strBinding
0x180003992  xor     r8d, r8d; pReturnValue
0x180003995  lea     edx, [r8+4Ch]; nProcNum
0x180003999  lea     rcx, ?winwlan_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800039a0  call    cs:__imp_NdrClientCall3
0x1800039a6  mov     rbx, rax
0x1800039a9  mov     [rsp+98h+var_38], rax
0x1800039ae  mov     [rsp+98h+var_58], eax
0x1800039b2  mov     r10, cs:WPP_GLOBAL_Control
0x1800039b9  jmp     short loc_180003A20
0x1800039bb  mov     ebx, eax
0x1800039bd  mov     [rsp+98h+var_58], eax
0x1800039c1  lea     rcx, WPP_GLOBAL_Control
0x1800039c8  mov     r10, cs:WPP_GLOBAL_Control
0x1800039cf  cmp     r10, rcx
0x1800039d2  jz      short loc_180003A04
0x1800039d4  cmp     byte ptr [r10+69h], 1
0x1800039d9  jb      short loc_180003A04
0x1800039db  test    dword ptr [r10+6Ch], 1000h
0x1800039e3  jz      short loc_180003A04
0x1800039e5  mov     edx, 44h ; 'D'
0x1800039ea  mov     r9d, eax
0x1800039ed  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x1800039f4  mov     rcx, [r10+60h]
0x1800039f8  call    WPP_SF_d
0x1800039fd  mov     r10, cs:WPP_GLOBAL_Control
0x180003a04  lea     rsi, WPP_GLOBAL_Control
0x180003a0b  mov     r14, [rsp+98h+arg_10]
0x180003a13  mov     r15, [rsp+98h+arg_8]
0x180003a1b  mov     rdi, [rsp+98h+var_50]
0x180003a20  test    ebx, ebx
0x180003a22  jnz     loc_180003AE2
0x180003a28  lea     rcx, [rsp+98h+var_50]; struct _WFD_CLIENT_CONTEXT **
0x180003a2d  call    ?wfdClientCreateContext@@YAKPEAPEAU_WFD_CLIENT_CONTEXT@@@Z; wfdClientCreateContext(_WFD_CLIENT_CONTEXT * *)
0x180003a32  mov     ebx, eax
0x180003a34  mov     [rsp+98h+var_58], eax
0x180003a38  test    eax, eax
0x180003a3a  jnz     loc_180003B8A
0x180003a40  mov     rdi, [rsp+98h+var_50]
0x180003a45  mov     [rdi+40h], rdi
0x180003a49  mov     dword ptr [rdi+54h], 2
0x180003a50  lea     rax, ?wfdClientRpcCallback@@YAXPEAU_RPC_ASYNC_STATE@@PEAXW4_RPC_ASYNC_EVENT@@@Z; wfdClientRpcCallback(_RPC_ASYNC_STATE *,void *,_RPC_ASYNC_EVENT)
0x180003a57  mov     [rdi+58h], rax
0x180003a5b  mov     rax, [rsp+98h+ContextHandle]
0x180003a60  mov     [rdi], rax
0x180003a63  mov     eax, [rsp+98h+arg_18]
0x180003a6a  mov     [rdi+10h], eax
0x180003a6d  lea     rax, [rsp+98h+var_40]
0x180003a72  mov     [rsp+98h+var_70], rax
0x180003a77  mov     [rsp+98h+var_78], 1
0x180003a7f  lea     r9, ?wfdClientDestroyContext@@YAKPEAU_WFD_CLIENT_CONTEXT@@@Z; wfdClientDestroyContext(_WFD_CLIENT_CONTEXT *)
0x180003a86  mov     r8d, 57696644h
0x180003a8c  mov     rdx, rdi
0x180003a8f  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x180003a96  call    cs:__imp_HtNewHandle
0x180003a9c  mov     ebx, eax
0x180003a9e  mov     [rsp+98h+var_58], eax
0x180003aa2  test    eax, eax
0x180003aa4  jnz     loc_180003BD3
0x180003aaa  mov     eax, [rsp+98h+arg_18]
0x180003ab1  mov     [r15], eax
0x180003ab4  mov     rax, [rsp+98h+var_40]
0x180003ab9  mov     [r14], rax
0x180003abc  mov     [rdi+8], rax
0x180003ac0  mov     r10, cs:WPP_GLOBAL_Control
0x180003ac7  test    ebx, ebx
0x180003ac9  jnz     loc_180003C19
0x180003acf  cmp     r10, rsi
0x180003ad2  jnz     short loc_180003AF6
0x180003ad4  mov     eax, ebx
0x180003ad6  add     rsp, 70h
0x180003ada  pop     r15
0x180003adc  pop     r14
0x180003ade  pop     rdi
0x180003adf  pop     rsi
0x180003ae0  pop     rbx
0x180003ae1  retn
0x180003ae2  cmp     r10, rsi
0x180003ae5  jnz     short loc_180003B55
0x180003ae7  mov     ecx, ebx; unsigned int
0x180003ae9  call    ?ServiceStatus@@YAKK@Z; ServiceStatus(ulong)
0x180003aee  mov     ebx, eax
0x180003af0  mov     [rsp+98h+var_58], eax
0x180003af4  jmp     short loc_180003AC7
0x180003af6  cmp     byte ptr [r10+69h], 4
0x180003afb  jb      short loc_180003AD4
0x180003afd  test    byte ptr [r10+6Ch], 2
0x180003b02  jz      short loc_180003AD4
0x180003b04  mov     edx, 48h ; 'H'
0x180003b09  mov     r9d, ebx
0x180003b0c  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180003b13  mov     rcx, [r10+60h]
0x180003b17  call    WPP_SF_d
0x180003b1c  jmp     short loc_180003AD4
0x180003b1e  mov     ebx, 57h ; 'W'
0x180003b23  mov     [rsp+98h+var_58], ebx
0x180003b27  jmp     short loc_180003AC7
0x180003b29  test    byte ptr [r10+6Ch], 2
0x180003b2e  jz      loc_180003955
0x180003b34  mov     edx, 43h ; 'C'
0x180003b39  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180003b40  mov     rcx, [r10+60h]
0x180003b44  call    WPP_SF_
0x180003b49  mov     r10, cs:WPP_GLOBAL_Control
0x180003b50  jmp     loc_180003955
0x180003b55  cmp     byte ptr [r10+69h], 1
0x180003b5a  jb      short loc_180003AE7
0x180003b5c  test    dword ptr [r10+6Ch], 1000h
0x180003b64  jz      short loc_180003AE7
0x180003b66  mov     edx, 45h ; 'E'
0x180003b6b  mov     r9d, ebx
0x180003b6e  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180003b75  mov     rcx, [r10+60h]
0x180003b79  call    WPP_SF_d
0x180003b7e  mov     r10, cs:WPP_GLOBAL_Control
0x180003b85  jmp     loc_180003AE7
0x180003b8a  mov     r10, cs:WPP_GLOBAL_Control
0x180003b91  cmp     r10, rsi
0x180003b94  jz      short loc_180003BC9
0x180003b96  cmp     byte ptr [r10+69h], 1
0x180003b9b  jb      short loc_180003BC9
0x180003b9d  test    dword ptr [r10+6Ch], 1000h
0x180003ba5  jz      short loc_180003BC9
0x180003ba7  mov     edx, 46h ; 'F'
0x180003bac  mov     r9d, eax
0x180003baf  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180003bb6  mov     rcx, [r10+60h]
0x180003bba  call    WPP_SF_d
0x180003bbf  mov     rdi, [rsp+98h+var_50]
0x180003bc4  jmp     loc_180003AC0
0x180003bc9  mov     rdi, [rsp+98h+var_50]
0x180003bce  jmp     loc_180003AC7
0x180003bd3  mov     r10, cs:WPP_GLOBAL_Control
0x180003bda  cmp     r10, rsi
0x180003bdd  jz      loc_180003AC7
0x180003be3  cmp     byte ptr [r10+69h], 1
0x180003be8  jb      loc_180003AC7
0x180003bee  test    dword ptr [r10+6Ch], 1000h
0x180003bf6  jz      loc_180003AC7
0x180003bfc  mov     edx, 47h ; 'G'
0x180003c01  mov     r9d, eax
0x180003c04  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180003c0b  mov     rcx, [r10+60h]
0x180003c0f  call    WPP_SF_d
0x180003c14  jmp     loc_180003AC0
0x180003c19  cmp     [rsp+98h+ContextHandle], 0
0x180003c1f  jz      short loc_180003C56
0x180003c21  lea     rcx, [rsp+98h+ContextHandle]
0x180003c26  call    RpcWlanCloseHandle
0x180003c2b  mov     r10, cs:WPP_GLOBAL_Control
0x180003c32  jmp     short loc_180003C56
0x180003c34  lea     rcx, [rsp+98h+ContextHandle]; ContextHandle
0x180003c39  call    cs:__imp_RpcSsDestroyClientContext
0x180003c3f  lea     rsi, WPP_GLOBAL_Control
0x180003c46  mov     ebx, [rsp+98h+var_58]
0x180003c4a  mov     rdi, [rsp+98h+var_50]
0x180003c4f  mov     r10, cs:WPP_GLOBAL_Control
0x180003c56  test    rdi, rdi
0x180003c59  jz      loc_180003ACF
0x180003c5f  mov     rcx, rdi; struct _WFD_CLIENT_CONTEXT *
0x180003c62  call    ?wfdClientDestroyContext@@YAKPEAU_WFD_CLIENT_CONTEXT@@@Z; wfdClientDestroyContext(_WFD_CLIENT_CONTEXT *)
0x180003c67  mov     r10, cs:WPP_GLOBAL_Control
0x180003c6e  jmp     loc_180003ACF
0x180060314  push    rbp
0x180060316  sub     rsp, 40h
0x18006031a  mov     rbp, rdx
0x18006031d  mov     rcx, [rcx]
0x180060320  mov     ecx, [rcx]; ExceptionCode
0x180060322  call    cs:__imp_RpcExceptionFilter
0x180060328  nop
0x180060329  add     rsp, 40h
0x18006032d  pop     rbp
0x18006032e  retn
0x180060330  push    rbp
0x180060332  sub     rsp, 40h
0x180060336  mov     rbp, rdx
0x180060339  mov     rcx, [rcx]
0x18006033c  mov     ecx, [rcx]; ExceptionCode
0x18006033e  call    cs:__imp_RpcExceptionFilter
0x180060344  nop
0x180060345  add     rsp, 40h
0x180060349  pop     rbp
0x18006034a  retn
```
