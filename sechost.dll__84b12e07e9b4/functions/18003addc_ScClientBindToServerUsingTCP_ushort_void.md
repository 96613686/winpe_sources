# ScClientBindToServerUsingTCP(ushort *,void * *)

- ea: `0x18003addc`
- end: `0x18003af8e`
- name: `?ScClientBindToServerUsingTCP@@YAKPEAGPEAPEAX@Z`
- size: `434`
- prototype: `unsigned int __fastcall(LPCWCH lpString2, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b9a0`
- `0x18003ac6c`

## callees

- `0x180016bc0`
- `0x18003addc`
- `0x18003b3a0`
- `0x18003b434`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x18003ae25`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18003ae25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aebf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aebf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003aeb1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003aeb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003af52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003af52`
- `RPCRT4!RpcStringFreeW` at `0x18003af62`
- `RPCRT4!RpcStringFreeW` at `0x18003af62`
- `RPCRT4!RpcBindingFree` at `0x18003af72`
- `RPCRT4!RpcBindingFree` at `0x18003af72`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18003af21`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18003af21`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18003ae83`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18003ae83`
- `RPCRT4!RpcStringBindingComposeW` at `0x18003ae6b`
- `RPCRT4!RpcStringBindingComposeW` at `0x18003ae6b`
- `RPCRT4!RpcBindingSetOption` at `0x18003af3b`
- `RPCRT4!RpcBindingSetOption` at `0x18003af3b`

## pseudocode

```c
__int64 __fastcall ScClientBindToServerUsingTCP(unsigned __int16 *lpString2, void **a2)
{
  DWORD LastError; // ebx
  const unsigned __int16 *v5; // rsi
  __int64 v6; // rax
  SIZE_T v7; // rbx
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rdi
  RPC_SECURITY_QOS SecurityQOS; // [rsp+40h] [rbp-30h] BYREF
  __int128 v12; // [rsp+50h] [rbp-20h]
  __int64 v13; // [rsp+60h] [rbp-10h]
  RPC_BINDING_HANDLE Binding; // [rsp+B0h] [rbp+40h] BYREF
  RPC_WSTR String; // [rsp+B8h] [rbp+48h] BYREF

  String = 0;
  v13 = 0;
  Binding = 0;
  SecurityQOS = 0;
  v12 = 0;
  RtlRunOnceExecuteOnce(&g_TcpConnectTimeoutRunOnce, ScClientRetrieveTCPConnectTimeoutOnceCallback, 0, 0);
  if ( dword_18007C5FC || (unsigned int)ScLookupServerName(lpString2) )
  {
    LastError = 1235;
  }
  else
  {
    v5 = lpString2 + 2;
    LastError = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_ip_tcp", lpString2 + 2, 0, 0, &String);
    if ( !LastError )
    {
      LastError = RpcBindingFromStringBindingW(String, &Binding);
      if ( !LastError )
      {
        v6 = -1;
        do
          ++v6;
        while ( v5[v6] );
        v7 = (unsigned int)(2 * v6 + 12);
        v8 = (unsigned __int16 *)LocalAlloc(0x40u, v7);
        v9 = v8;
        if ( v8 )
        {
          StringCbCopyW(v8, v7, L"HOST/");
          StringCbCatW(v9, v7, v5);
          SecurityQOS.Capabilities = 1;
          SecurityQOS.IdentityTracking = 1;
          SecurityQOS.Version = 3;
          SecurityQOS.ImpersonationType = 3;
          LastError = RpcBindingSetAuthInfoExW(Binding, v9, 6u, 9u, 0, 1u, &SecurityQOS);
          if ( !LastError )
          {
            RpcBindingSetOption(Binding, 0xCu, (unsigned int)optionValue);
            LastError = 0;
            *a2 = Binding;
            Binding = 0;
          }
          LocalFree(v9);
        }
        else
        {
          LastError = GetLastError();
        }
      }
    }
  }
  if ( String )
    RpcStringFreeW(&String);
  if ( Binding )
    RpcBindingFree(&Binding);
  return LastError;
}

```

## disassembly

```asm
0x18003addc  mov     [rsp-28h+arg_0], rbx
0x18003ade1  push    rbp
0x18003ade2  push    rsi
0x18003ade3  push    rdi
0x18003ade4  push    r14
0x18003ade6  push    r15
0x18003ade8  mov     rbp, rsp
0x18003adeb  sub     rsp, 70h
0x18003adef  xorps   xmm0, xmm0
0x18003adf2  mov     r14, rdx
0x18003adf5  mov     rbx, rcx
0x18003adf8  lea     rdx, ?ScClientRetrieveTCPConnectTimeoutOnceCallback@@YAKPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; ScClientRetrieveTCPConnectTimeoutOnceCallback(_RTL_RUN_ONCE *,void *,void * *)
0x18003adff  xor     r15d, r15d
0x18003ae02  lea     rcx, ?g_TcpConnectTimeoutRunOnce@@3T_RTL_RUN_ONCE@@A; _RTL_RUN_ONCE g_TcpConnectTimeoutRunOnce
0x18003ae09  xor     eax, eax
0x18003ae0b  mov     [rbp+String], r15
0x18003ae0f  xor     r9d, r9d
0x18003ae12  mov     [rbp+var_10], rax
0x18003ae16  xor     r8d, r8d
0x18003ae19  mov     [rbp+Binding], r15
0x18003ae1d  movups  xmmword ptr [rbp+var_30.Version], xmm0
0x18003ae21  movups  [rbp+var_20], xmm0
0x18003ae25  call    cs:__imp_RtlRunOnceExecuteOnce
0x18003ae2b  cmp     cs:dword_18007C5FC, r15d
0x18003ae32  jz      short loc_18003AE3E
0x18003ae34  mov     ebx, 4D3h
0x18003ae39  jmp     loc_18003AF58
0x18003ae3e  mov     rcx, rbx; lpString2
0x18003ae41  call    ?ScLookupServerName@@YAHPEBG@Z; ScLookupServerName(ushort const *)
0x18003ae46  test    eax, eax
0x18003ae48  jnz     short loc_18003AE34
0x18003ae4a  lea     rax, [rbp+String]
0x18003ae4e  xor     r9d, r9d; Endpoint
0x18003ae51  mov     [rsp+70h+StringBinding], rax; StringBinding
0x18003ae56  lea     rsi, [rbx+4]
0x18003ae5a  mov     r8, rsi; NetworkAddr
0x18003ae5d  mov     [rsp+70h+Options], r15; Options
0x18003ae62  lea     rdx, aNcacnIpTcp; "ncacn_ip_tcp"
0x18003ae69  xor     ecx, ecx; ObjUuid
0x18003ae6b  call    cs:__imp_RpcStringBindingComposeW
0x18003ae71  mov     ebx, eax
0x18003ae73  test    eax, eax
0x18003ae75  jnz     loc_18003AF58
0x18003ae7b  mov     rcx, [rbp+String]; StringBinding
0x18003ae7f  lea     rdx, [rbp+Binding]; Binding
0x18003ae83  call    cs:__imp_RpcBindingFromStringBindingW
0x18003ae89  mov     ebx, eax
0x18003ae8b  test    eax, eax
0x18003ae8d  jnz     loc_18003AF58
0x18003ae93  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003ae97  inc     rax
0x18003ae9a  cmp     [rsi+rax*2], r15w
0x18003ae9f  jnz     short loc_18003AE97
0x18003aea1  lea     eax, ds:0Ch[rax*2]
0x18003aea8  mov     ecx, 40h ; '@'; uFlags
0x18003aead  mov     edx, eax; uBytes
0x18003aeaf  mov     ebx, eax
0x18003aeb1  call    cs:__imp_LocalAlloc
0x18003aeb7  mov     rdi, rax
0x18003aeba  test    rax, rax
0x18003aebd  jnz     short loc_18003AECC
0x18003aebf  call    cs:__imp_GetLastError
0x18003aec5  mov     ebx, eax
0x18003aec7  jmp     loc_18003AF58
0x18003aecc  lea     r8, aHost; "HOST/"
0x18003aed3  mov     rdx, rbx; unsigned __int64
0x18003aed6  mov     rcx, rdi; unsigned __int16 *
0x18003aed9  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18003aede  mov     r8, rsi; unsigned __int16 *
0x18003aee1  mov     rdx, rbx; unsigned __int64
0x18003aee4  mov     rcx, rdi; unsigned __int16 *
0x18003aee7  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18003aeec  mov     ecx, 1
0x18003aef1  mov     rdx, rdi; ServerPrincName
0x18003aef4  mov     [rbp+var_30.Capabilities], ecx
0x18003aef7  mov     [rbp+var_30.IdentityTracking], ecx
0x18003aefa  lea     eax, [rcx+2]
0x18003aefd  mov     [rbp+var_30.Version], eax
0x18003af00  lea     r9d, [rcx+8]; AuthnSvc
0x18003af04  mov     [rbp+var_30.ImpersonationType], eax
0x18003af07  lea     r8d, [rcx+5]; AuthnLevel
0x18003af0b  lea     rax, [rbp+var_30]
0x18003af0f  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x18003af14  mov     dword ptr [rsp+70h+StringBinding], ecx; AuthzSvc
0x18003af18  mov     rcx, [rbp+Binding]; Binding
0x18003af1c  mov     [rsp+70h+Options], r15; AuthIdentity
0x18003af21  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18003af27  mov     ebx, eax
0x18003af29  test    eax, eax
0x18003af2b  jnz     short loc_18003AF4F
0x18003af2d  mov     r8d, cs:optionValue; optionValue
0x18003af34  lea     edx, [rax+0Ch]; option
0x18003af37  mov     rcx, [rbp+Binding]; hBinding
0x18003af3b  call    cs:__imp_RpcBindingSetOption
0x18003af41  mov     rax, [rbp+Binding]
0x18003af45  mov     ebx, r15d
0x18003af48  mov     [r14], rax
0x18003af4b  mov     [rbp+Binding], r15
0x18003af4f  mov     rcx, rdi; hMem
0x18003af52  call    cs:__imp_LocalFree
0x18003af58  cmp     [rbp+String], r15
0x18003af5c  jz      short loc_18003AF68
0x18003af5e  lea     rcx, [rbp+String]; String
0x18003af62  call    cs:__imp_RpcStringFreeW
0x18003af68  cmp     [rbp+Binding], r15
0x18003af6c  jz      short loc_18003AF78
0x18003af6e  lea     rcx, [rbp+Binding]; Binding
0x18003af72  call    cs:__imp_RpcBindingFree
0x18003af78  mov     eax, ebx
0x18003af7a  mov     rbx, [rsp+70h+arg_0]
0x18003af82  add     rsp, 70h
0x18003af86  pop     r15
0x18003af88  pop     r14
0x18003af8a  pop     rdi
0x18003af8b  pop     rsi
0x18003af8c  pop     rbp
0x18003af8d  retn
```
