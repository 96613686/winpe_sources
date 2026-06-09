# SamiFindOrCreateShadowAdminAccount

- ea: `0x180013980`
- end: `0x180013b5e`
- name: `SamiFindOrCreateShadowAdminAccount`
- size: `478`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005ca0`
- `0x18000807c`
- `0x180013980`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013afb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013b06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013afb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013b06`
- `RPCRT4!NdrClientCall3` at `0x180013a48`
- `RPCRT4!NdrClientCall3` at `0x180013a48`
- `RPCRT4!I_RpcMapWin32Status` at `0x180013a8b`
- `RPCRT4!I_RpcMapWin32Status` at `0x180013a8b`
- `RPCRT4!RpcBindingFree` at `0x180013b19`
- `RPCRT4!RpcBindingFree` at `0x180013b19`

## pseudocode

```c
__int64 __fastcall SamiFindOrCreateShadowAdminAccount(__int64 a1, HLOCAL *a2, HLOCAL *a3)
{
  int v6; // eax
  unsigned int Pointer; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 Pointer_low; // r9
  CLIENT_CALL_RETURN v11; // rax
  HLOCAL v13; // [rsp+48h] [rbp-30h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+50h] [rbp-28h] BYREF
  CLIENT_CALL_RETURN v15; // [rsp+58h] [rbp-20h]
  HLOCAL hMem; // [rsp+98h] [rbp+20h] BYREF

  Binding = 0;
  hMem = 0;
  v13 = 0;
  *a2 = 0;
  *a3 = 0;
  v6 = SampCreateBindingHandle(0, &Binding);
  Pointer = v6;
  if ( v6 >= 0 )
  {
    v15.Simple = 0;
    v11.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0x4Eu, 0, Binding, a1, &hMem, &v13).Pointer;
    Pointer = (unsigned int)v11.Pointer;
    v15.Pointer = v11.Pointer;
    if ( SLODWORD(v11.Simple) >= 0 )
    {
      *a2 = hMem;
      hMem = 0;
      *a3 = v13;
      v13 = 0;
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 404;
        Pointer_low = LODWORD(v11.Pointer);
        goto LABEL_5;
      }
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 402;
      Pointer_low = (unsigned int)v6;
LABEL_5:
      WPP_SF_D(v8[2], v9, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, Pointer_low);
    }
  }
  LocalFree(hMem);
  LocalFree(v13);
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 405, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x180013980  mov     rax, rsp
0x180013983  mov     [rax+8], rbx
0x180013987  mov     [rax+18h], r8
0x18001398b  mov     [rax+10h], rdx
0x18001398f  push    rsi
0x180013990  push    r14
0x180013992  push    r15
0x180013994  sub     rsp, 60h
0x180013998  mov     rsi, r8
0x18001399b  mov     r14, rdx
0x18001399e  mov     r15, rcx
0x1800139a1  mov     qword ptr [rax-28h], 0
0x1800139a9  mov     qword ptr [rax+20h], 0
0x1800139b1  mov     qword ptr [rax-30h], 0
0x1800139b9  mov     qword ptr [rdx], 0
0x1800139c0  mov     qword ptr [r8], 0
0x1800139c7  lea     rdx, [rax-28h]; Binding
0x1800139cb  xor     ecx, ecx; ServiceName
0x1800139cd  call    ?SampCreateBindingHandle@@YAJPEAGPEAPEAX@Z; SampCreateBindingHandle(ushort *,void * *)
0x1800139d2  mov     ebx, eax
0x1800139d4  test    eax, eax
0x1800139d6  jns     short loc_180013A10
0x1800139d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800139df  test    byte ptr [rcx+1Ch], 2
0x1800139e3  jz      loc_180013AF3
0x1800139e9  cmp     byte ptr [rcx+19h], 2
0x1800139ed  jb      loc_180013AF3
0x1800139f3  mov     edx, 192h
0x1800139f8  mov     r9d, eax
0x1800139fb  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180013a02  mov     rcx, [rcx+10h]
0x180013a06  call    WPP_SF_D
0x180013a0b  jmp     loc_180013AF3
0x180013a10  mov     [rsp+78h+var_20], 0
0x180013a19  lea     rax, [rsp+78h+var_30]
0x180013a1e  mov     [rsp+78h+var_48], rax
0x180013a23  lea     rax, [rsp+78h+hMem]
0x180013a2b  mov     [rsp+78h+var_50], rax
0x180013a30  mov     [rsp+78h+var_58], r15
0x180013a35  mov     r9, [rsp+78h+Binding]
0x180013a3a  xor     r8d, r8d; pReturnValue
0x180013a3d  lea     edx, [r8+4Eh]; nProcNum
0x180013a41  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180013a48  call    cs:__imp_NdrClientCall3
0x180013a4e  mov     rbx, rax
0x180013a51  mov     [rsp+78h+var_20], rax
0x180013a56  mov     [rsp+78h+var_38], eax
0x180013a5a  jmp     short loc_180013AA7
0x180013a5c  mov     ebx, eax
0x180013a5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a65  test    byte ptr [rcx+1Ch], 2
0x180013a69  jz      short loc_180013A89
0x180013a6b  cmp     byte ptr [rcx+19h], 3
0x180013a6f  jb      short loc_180013A89
0x180013a71  mov     r9d, eax
0x180013a74  mov     edx, 193h
0x180013a79  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180013a80  mov     rcx, [rcx+10h]
0x180013a84  call    WPP_SF_D
0x180013a89  mov     ecx, ebx; Status
0x180013a8b  call    cs:__imp_I_RpcMapWin32Status
0x180013a91  mov     ebx, eax
0x180013a93  mov     [rsp+78h+var_38], eax
0x180013a97  mov     rsi, [rsp+78h+arg_10]
0x180013a9f  mov     r14, [rsp+78h+arg_8]
0x180013aa7  test    ebx, ebx
0x180013aa9  jns     short loc_180013ACB
0x180013aab  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ab2  test    byte ptr [rcx+1Ch], 2
0x180013ab6  jz      short loc_180013AF3
0x180013ab8  cmp     byte ptr [rcx+19h], 2
0x180013abc  jb      short loc_180013AF3
0x180013abe  mov     edx, 194h
0x180013ac3  mov     r9d, ebx
0x180013ac6  jmp     loc_1800139FB
0x180013acb  mov     rax, [rsp+78h+hMem]
0x180013ad3  mov     [r14], rax
0x180013ad6  mov     [rsp+78h+hMem], 0
0x180013ae2  mov     rax, [rsp+78h+var_30]
0x180013ae7  mov     [rsi], rax
0x180013aea  mov     [rsp+78h+var_30], 0
0x180013af3  mov     rcx, [rsp+78h+hMem]; hMem
0x180013afb  call    cs:__imp_LocalFree
0x180013b01  mov     rcx, [rsp+78h+var_30]; hMem
0x180013b06  call    cs:__imp_LocalFree
0x180013b0c  cmp     [rsp+78h+Binding], 0
0x180013b12  jz      short loc_180013B1F
0x180013b14  lea     rcx, [rsp+78h+Binding]; Binding
0x180013b19  call    cs:__imp_RpcBindingFree
0x180013b1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b26  test    byte ptr [rcx+1Ch], 2
0x180013b2a  jz      short loc_180013B4A
0x180013b2c  cmp     byte ptr [rcx+19h], 4
0x180013b30  jb      short loc_180013B4A
0x180013b32  mov     edx, 195h
0x180013b37  mov     r9d, ebx
0x180013b3a  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180013b41  mov     rcx, [rcx+10h]
0x180013b45  call    WPP_SF_D
0x180013b4a  mov     eax, ebx
0x180013b4c  mov     rbx, [rsp+78h+arg_0]
0x180013b54  add     rsp, 60h
0x180013b58  pop     r15
0x180013b5a  pop     r14
0x180013b5c  pop     rsi
0x180013b5d  retn
0x180017cf0  push    rbp
0x180017cf2  sub     rsp, 40h
0x180017cf6  mov     rbp, rdx
0x180017cf9  mov     rcx, [rcx]
0x180017cfc  mov     ecx, [rcx]; ExceptionCode
0x180017cfe  call    cs:__imp_I_RpcExceptionFilter
0x180017d04  nop
0x180017d05  add     rsp, 40h
0x180017d09  pop     rbp
0x180017d0a  retn
```
