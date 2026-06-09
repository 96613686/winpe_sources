# HTTP2ClientChannel::ClientOpen(HTTPResolverHint *,char const *,ulong,int,int,_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *,ulong,ulong,HTTP2WinHttpTransportChannel *,ulong,uchar const *,ulong)

- ea: `0x180005d50`
- end: `0x180006048`
- name: `?ClientOpen@HTTP2ClientChannel@@QEAAJPEAVHTTPResolverHint@@PEBDKHHPEAU_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W@@KKPEAVHTTP2WinHttpTransportChannel@@KPEBEK@Z`
- size: `760`
- prototype: `__int64 __fastcall(HTTP2ClientChannel *__hidden this, struct HTTPResolverHint *, const char *, unsigned int, int, int, struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *, DWORD, DWORD, struct HTTP2WinHttpTransportChannel *, unsigned int, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180006050`

## callees

- `0x180005d50`
- `0x18000f74c`
- `0x180024640`
- `0x180025010`

## import_xrefs

- `ntdll!RtlIntegerToChar` at `0x180005dd9`
- `ntdll!RtlIntegerToChar` at `0x180005dd9`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180005e77`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180005f46`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180005f82`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180005e77`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180005f46`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180005f82`
- `RPCRT4!I_RpcFree` at `0x180005ec7`
- `RPCRT4!I_RpcFree` at `0x180006002`
- `RPCRT4!I_RpcFree` at `0x180005ec7`
- `RPCRT4!I_RpcFree` at `0x180006002`
- `RPCRT4!I_RpcAllocate` at `0x180005e4d`
- `RPCRT4!I_RpcAllocate` at `0x180005e4d`

## string_xrefs

- `0x180005f03`: `/rpc/rpcproxy.dll?`
- `0x180005ed3`: `/RpcWithCert/rpcproxy.dll?`

## pseudocode

```c
__int64 __fastcall HTTP2ClientChannel::ClientOpen(
        HTTP2ClientChannel *this,
        struct HTTPResolverHint *a2,
        const char *a3,
        unsigned int a4,
        int a5,
        int a6,
        struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *a7,
        DWORD a8,
        DWORD AuthScheme,
        struct HTTP2WinHttpTransportChannel *a10,
        unsigned int Buffer,
        unsigned __int8 *a12,
        unsigned int a13)
{
  unsigned __int8 *v14; // r13
  __int64 v15; // rbp
  __int64 v17; // r15
  unsigned int Value; // esi
  int v19; // r14d
  unsigned int v20; // eax
  WCHAR *v21; // rax
  WCHAR *v22; // r12
  __int64 v23; // rax
  unsigned __int16 *v24; // rbp
  __int64 v25; // rax
  __int64 v26; // rbx
  unsigned __int16 *v27; // rdi
  __int64 v28; // rcx
  unsigned __int16 *v29; // rbx
  CHAR String[8]; // [rsp+90h] [rbp-48h] BYREF

  v14 = a12;
  v15 = a4;
  if ( *((_DWORD *)a2 + 22) > 0x7FFFu )
    return 87;
  RtlIntegerToChar(*((unsigned __int16 *)a2 + 46), 0xAu, 6u, String);
  v17 = -1;
  do
    ++v17;
  while ( String[v17] );
  if ( a12 )
  {
    Value = a13;
    v19 = 1;
    if ( a12 == (unsigned __int8 *)-1LL )
      v14 = 0;
  }
  else
  {
    if ( a5 )
      Value = DefaultChannelLifetime;
    else
      Value = a6 != 0 ? 120 : 76;
    v19 = 0;
  }
  v20 = 2 * (v15 + 1);
  if ( !is_mul_ok((unsigned int)(v15 + 1), 2u) )
    v20 = -1;
  v21 = (WCHAR *)I_RpcAllocate(v20);
  v22 = v21;
  if ( !v21 )
    return 14;
  RtlMultiByteToUnicodeN(v21, 2 * (v15 + 1), 0, a3, v15 + 1);
  v22[v15] = 0;
  v23 = (*(__int64 (__fastcall **)(__int64))pRuntimeImportTable)(2LL * (*((_DWORD *)a2 + 22)
                                                                      + 20
                                                                      + (unsigned int)v17
                                                                      + 8 * (((a8 - 0x20000) & 0xFFFDFFFF) == 0)));
  v24 = (unsigned __int16 *)v23;
  if ( !v23 )
  {
    I_RpcFree(v22);
    return 14;
  }
  if ( ((a8 - 0x20000) & 0xFFFDFFFF) != 0 )
  {
    *(_OWORD *)v23 = *(_OWORD *)L"/rpc/rpcproxy.dll?";
    *(_OWORD *)(v23 + 16) = *(_OWORD *)L"proxy.dll?";
    *(_DWORD *)(v23 + 32) = *(_DWORD *)L"l?";
    v25 = 18;
  }
  else
  {
    *(_OWORD *)v23 = *(_OWORD *)L"/RpcWithCert/rpcproxy.dll?";
    *(_OWORD *)(v23 + 16) = *(_OWORD *)L"Cert/rpcproxy.dll?";
    *(_OWORD *)(v23 + 32) = *(_OWORD *)L"proxy.dll?";
    *(_DWORD *)(v23 + 48) = *(_DWORD *)L"l?";
    v25 = 26;
  }
  v26 = *((unsigned int *)a2 + 22);
  v27 = &v24[v25];
  RtlMultiByteToUnicodeN(&v24[v25], 2 * (v26 + 1), 0, *((const CHAR **)a2 + 5), v26 + 1);
  v27[v26] = 0;
  v28 = *((unsigned int *)a2 + 22);
  v27[v28] = asc_1800281BC[0];
  v29 = &v27[v28];
  RtlMultiByteToUnicodeN(v29 + 1, 2 * (v17 + 1), 0, String, v17 + 1);
  v29[(unsigned int)v17 + 1] = 0;
  LODWORD(v29) = HTTP2WinHttpTransportChannel::Open(
                   a10,
                   a2,
                   v22,
                   v24,
                   L"application/rpc",
                   Value,
                   Buffer,
                   a7,
                   a8,
                   AuthScheme,
                   v14,
                   v19,
                   a6);
  I_RpcFree(v22);
  (*((void (__fastcall **)(unsigned __int16 *))pRuntimeImportTable + 1))(v24);
  return (unsigned int)v29;
}

```

## disassembly

```asm
0x180005d50  mov     [rsp+arg_0], rbx
0x180005d55  push    rbp
0x180005d56  push    rsi
0x180005d57  push    rdi
0x180005d58  push    r12
0x180005d5a  push    r13
0x180005d5c  push    r14
0x180005d5e  push    r15
0x180005d60  sub     rsp, 0A0h
0x180005d67  mov     rax, cs:__security_cookie
0x180005d6e  xor     rax, rsp
0x180005d71  mov     [rsp+0D8h+var_40], rax
0x180005d79  cmp     dword ptr [rdx+58h], 7FFFh
0x180005d80  mov     rbx, rdx
0x180005d83  mov     rax, [rsp+0D8h+arg_30]
0x180005d8b  mov     r13, [rsp+0D8h+arg_58]
0x180005d93  mov     [rsp+0D8h+var_58], rax
0x180005d9b  mov     rax, [rsp+0D8h+arg_48]
0x180005da3  mov     [rsp+0D8h+var_50], rax
0x180005dab  mov     ebp, r9d
0x180005dae  mov     [rsp+0D8h+MultiByteString], r8
0x180005db3  mov     [rsp+0D8h+var_68], rdx
0x180005db8  jbe     short loc_180005DC4
0x180005dba  mov     eax, 57h ; 'W'
0x180005dbf  jmp     loc_18000601D
0x180005dc4  movzx   ecx, word ptr [rdx+5Ch]; Value
0x180005dc8  lea     r9, [rsp+0D8h+String]; String
0x180005dd0  mov     edx, 0Ah; Base
0x180005dd5  lea     r8d, [rdx-4]; Length
0x180005dd9  call    cs:__imp_RtlIntegerToChar
0x180005ddf  or      r8, 0FFFFFFFFFFFFFFFFh
0x180005de3  lea     rax, [rsp+0D8h+String]
0x180005deb  mov     r15, r8
0x180005dee  inc     r15
0x180005df1  cmp     byte ptr [rax+r15], 0
0x180005df6  jnz     short loc_180005DEE
0x180005df8  test    r13, r13
0x180005dfb  jnz     short loc_180005E25
0x180005dfd  cmp     [rsp+0D8h+arg_20], r13d
0x180005e05  jnz     short loc_180005E1A
0x180005e07  mov     eax, [rsp+0D8h+arg_28]
0x180005e0e  neg     eax
0x180005e10  sbb     esi, esi
0x180005e12  and     esi, 2Ch
0x180005e15  add     esi, 4Ch ; 'L'
0x180005e18  jmp     short loc_180005E20
0x180005e1a  mov     esi, cs:?DefaultChannelLifetime@@3KA; ulong DefaultChannelLifetime
0x180005e20  xor     r14d, r14d
0x180005e23  jmp     short loc_180005E3A
0x180005e25  mov     esi, [rsp+0D8h+arg_60]
0x180005e2c  mov     r14d, 1
0x180005e32  cmp     r13, r8
0x180005e35  jnz     short loc_180005E3A
0x180005e37  xor     r13d, r13d
0x180005e3a  lea     edi, [rbp+1]
0x180005e3d  mov     eax, 2
0x180005e42  mov     ecx, edi
0x180005e44  mul     rcx
0x180005e47  cmovb   rax, r8
0x180005e4b  mov     ecx, eax; Size
0x180005e4d  call    cs:__imp_I_RpcAllocate
0x180005e53  mov     r12, rax
0x180005e56  test    rax, rax
0x180005e59  jnz     short loc_180005E65
0x180005e5b  mov     eax, 0Eh
0x180005e60  jmp     loc_18000601D
0x180005e65  mov     r9, [rsp+0D8h+MultiByteString]; MultiByteString
0x180005e6a  lea     edx, [rdi+rdi]; MaxBytesInUnicodeString
0x180005e6d  xor     r8d, r8d; BytesInUnicodeString
0x180005e70  mov     [rsp+0D8h+BytesInMultiByteString], edi; BytesInMultiByteString
0x180005e74  mov     rcx, r12; UnicodeString
0x180005e77  call    cs:__imp_RtlMultiByteToUnicodeN
0x180005e7d  xor     eax, eax
0x180005e7f  mov     edi, 0
0x180005e84  mov     [r12+rbp*2], ax
0x180005e89  mov     eax, [rsp+0D8h+arg_38]
0x180005e90  add     eax, 0FFFE0000h
0x180005e95  test    eax, 0FFFDFFFFh
0x180005e9a  mov     eax, [rbx+58h]
0x180005e9d  setz    dil
0x180005ea1  add     eax, 14h
0x180005ea4  lea     ecx, [r15+rdi*8]
0x180005ea8  add     ecx, eax
0x180005eaa  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180005eb1  add     rcx, rcx
0x180005eb4  mov     rax, [rax]
0x180005eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ebc  mov     rbp, rax
0x180005ebf  test    rax, rax
0x180005ec2  jnz     short loc_180005ECF
0x180005ec4  mov     rcx, r12; Object
0x180005ec7  call    cs:__imp_I_RpcFree
0x180005ecd  jmp     short loc_180005E5B
0x180005ecf  test    edi, edi
0x180005ed1  jz      short loc_180005F03
0x180005ed3  movups  xmm0, xmmword ptr cs:aRpcwithcertRpc; "/RpcWithCert/rpcproxy.dll?"
0x180005eda  movups  xmmword ptr [rax], xmm0
0x180005edd  movups  xmm1, xmmword ptr cs:aRpcwithcertRpc+10h; "Cert/rpcproxy.dll?"
0x180005ee4  movups  xmmword ptr [rax+10h], xmm1
0x180005ee8  movups  xmm0, xmmword ptr cs:aRpcwithcertRpc+20h; "proxy.dll?"
0x180005eef  movups  xmmword ptr [rax+20h], xmm0
0x180005ef3  mov     eax, dword ptr cs:aRpcwithcertRpc+30h; "l?"
0x180005ef9  mov     [rbp+30h], eax
0x180005efc  mov     eax, 34h ; '4'
0x180005f01  jmp     short loc_180005F26
0x180005f03  movups  xmm0, xmmword ptr cs:aRpcRpcproxyDll; "/rpc/rpcproxy.dll?"
0x180005f0a  movups  xmmword ptr [rax], xmm0
0x180005f0d  movups  xmm1, xmmword ptr cs:aRpcRpcproxyDll+10h; "proxy.dll?"
0x180005f14  movups  xmmword ptr [rax+10h], xmm1
0x180005f18  mov     eax, dword ptr cs:aRpcRpcproxyDll+20h; "l?"
0x180005f1e  mov     [rbp+20h], eax
0x180005f21  mov     eax, 24h ; '$'
0x180005f26  mov     ebx, [rbx+58h]
0x180005f29  lea     rdi, [rax+rbp]
0x180005f2d  mov     r9, [rsp+0D8h+var_68]
0x180005f32  xor     r8d, r8d; BytesInUnicodeString
0x180005f35  mov     rcx, rdi; UnicodeString
0x180005f38  lea     eax, [rbx+1]
0x180005f3b  mov     r9, [r9+28h]; MultiByteString
0x180005f3f  lea     edx, [rax+rax]; MaxBytesInUnicodeString
0x180005f42  mov     [rsp+0D8h+BytesInMultiByteString], eax; BytesInMultiByteString
0x180005f46  call    cs:__imp_RtlMultiByteToUnicodeN
0x180005f4c  xor     eax, eax
0x180005f4e  lea     r9, [rsp+0D8h+String]; MultiByteString
0x180005f56  mov     [rdi+rbx*2], ax
0x180005f5a  xor     r8d, r8d; BytesInUnicodeString
0x180005f5d  mov     rax, [rsp+0D8h+var_68]
0x180005f62  mov     ecx, [rax+58h]
0x180005f65  mov     eax, dword ptr cs:asc_1800281BC; ":"
0x180005f6b  mov     [rdi+rcx*2], ax
0x180005f6f  lea     rbx, [rdi+rcx*2]
0x180005f73  lea     eax, [r15+1]
0x180005f77  lea     edx, [rax+rax]; MaxBytesInUnicodeString
0x180005f7a  mov     [rsp+0D8h+BytesInMultiByteString], eax; BytesInMultiByteString
0x180005f7e  lea     rcx, [rbx+2]; UnicodeString
0x180005f82  call    cs:__imp_RtlMultiByteToUnicodeN
0x180005f88  mov     rdx, [rsp+0D8h+var_68]; struct HTTPResolverHint *
0x180005f8d  xor     eax, eax
0x180005f8f  mov     ecx, r15d
0x180005f92  mov     r9, rbp; unsigned __int16 *
0x180005f95  mov     r8, r12; unsigned __int16 *
0x180005f98  mov     [rbx+rcx*2+2], ax
0x180005f9d  mov     eax, [rsp+0D8h+arg_28]
0x180005fa4  mov     rcx, [rsp+0D8h+var_50]; this
0x180005fac  mov     [rsp+0D8h+var_78], eax; int
0x180005fb0  mov     eax, [rsp+0D8h+arg_40]
0x180005fb7  mov     [rsp+0D8h+var_80], r14d; int
0x180005fbc  mov     [rsp+0D8h+var_88], r13; unsigned __int8 *
0x180005fc1  mov     [rsp+0D8h+AuthScheme], eax; AuthScheme
0x180005fc5  mov     eax, [rsp+0D8h+arg_38]
0x180005fcc  mov     [rsp+0D8h+var_98], eax; DWORD
0x180005fd0  mov     rax, [rsp+0D8h+var_58]
0x180005fd8  mov     [rsp+0D8h+var_A0], rax; struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *
0x180005fdd  mov     eax, [rsp+0D8h+arg_50]
0x180005fe4  mov     [rsp+0D8h+Buffer], eax; Buffer
0x180005fe8  lea     rax, aApplicationRpc; "application/rpc"
0x180005fef  mov     [rsp+0D8h+Value], esi; Value
0x180005ff3  mov     qword ptr [rsp+0D8h+BytesInMultiByteString], rax; unsigned __int16 *
0x180005ff8  call    ?Open@HTTP2WinHttpTransportChannel@@QEAAJPEAVHTTPResolverHint@@QEAG11KKPEAU_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W@@KKPEBEHH@Z; HTTP2WinHttpTransportChannel::Open(HTTPResolverHint *,ushort * const,ushort * const,ushort * const,ulong,ulong,_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *,ulong,ulong,uchar const *,int,int)
0x180005ffd  mov     rcx, r12; Object
0x180006000  mov     ebx, eax
0x180006002  call    cs:__imp_I_RpcFree
0x180006008  mov     rcx, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000600f  mov     rax, [rcx+8]
0x180006013  mov     rcx, rbp
0x180006016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000601b  mov     eax, ebx
0x18000601d  mov     rcx, [rsp+0D8h+var_40]
0x180006025  xor     rcx, rsp; StackCookie
0x180006028  call    __security_check_cookie
0x18000602d  mov     rbx, [rsp+0D8h+arg_0]
0x180006035  add     rsp, 0A0h
0x18000603c  pop     r15
0x18000603e  pop     r14
0x180006040  pop     r13
0x180006042  pop     r12
0x180006044  pop     rdi
0x180006045  pop     rsi
0x180006046  pop     rbp
0x180006047  retn
```
