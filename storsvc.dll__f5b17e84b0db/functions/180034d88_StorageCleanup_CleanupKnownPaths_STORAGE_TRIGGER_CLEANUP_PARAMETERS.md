# StorageCleanup::CleanupKnownPaths(_STORAGE_TRIGGER_CLEANUP_PARAMETERS *)

- ea: `0x180034d88`
- end: `0x180034ed3`
- name: `?CleanupKnownPaths@StorageCleanup@@AEAAJPEAU_STORAGE_TRIGGER_CLEANUP_PARAMETERS@@@Z`
- size: `331`
- prototype: `__int64 __fastcall(StorageCleanup *__hidden this, struct _STORAGE_TRIGGER_CLEANUP_PARAMETERS *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180035128`

## callees

- `0x180019d4c`
- `0x180019d94`
- `0x18001c3d8`
- `0x18001dcf4`
- `0x18001fcac`
- `0x180034a50`
- `0x180034bbc`
- `0x180034d88`
- `0x180035688`
- `0x180039208`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180034e30`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180034e30`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180034e46`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180034e46`
- `RPCRT4!RpcRevertToSelf` at `0x180034e95`
- `RPCRT4!RpcRevertToSelf` at `0x180034e95`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall StorageCleanup::CleanupKnownPaths(
        StorageCleanup *this,
        struct _STORAGE_TRIGGER_CLEANUP_PARAMETERS *a2)
{
  unsigned __int64 i; // rdi
  unsigned int v4; // r15d
  int v5; // r12d
  unsigned int v6; // r13d
  char v7; // r14
  __int64 v8; // rcx
  HANDLE CurrentThread; // rax
  __int64 v10; // rcx
  char v11; // al
  _BYTE v13[8]; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v14; // [rsp+38h] [rbp-18h] BYREF
  KNOWNFOLDERID rfid; // [rsp+40h] [rbp-10h] BYREF
  void *TokenHandle; // [rsp+90h] [rbp+40h] BYREF
  __int64 v17; // [rsp+A0h] [rbp+50h] BYREF

  TokenHandle = this;
  for ( i = 0; i < 0xA; ++i )
  {
    v14 = 0;
    v4 = *((_DWORD *)&xmmword_1800BF450 + 10 * i + 6);
    v5 = *((_DWORD *)&xmmword_1800BF450 + 10 * i + 8);
    v6 = *((_DWORD *)&xmmword_1800BF450 + 10 * i + 7);
    v7 = *((_BYTE *)&xmmword_1800BF450 + 40 * i + 36);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v14,
      0);
    rfid = *(KNOWNFOLDERID *)((char *)&xmmword_1800BF450 + 40 * i);
    if ( (int)GetPath(&rfid, *((const unsigned __int16 **)&xmmword_1800BF450 + 5 * i + 2), &v14) >= 0 )
    {
      AutoRpcImpersonateClient(v13);
      v17 = -1;
      if ( !v7 )
      {
        TokenHandle = 0;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &TokenHandle,
          0);
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
          wil::impersonate_token_nothrow(v10, (void **)&v17);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      }
      StorageCleanup::CleanupKnownPath(v8, a2, v4, v6, v5, v14);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v17);
      v11 = v13[0];
      v13[0] = 0;
      if ( v11 )
        RpcRevertToSelf();
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
  }
  return 0;
}

```

## disassembly

```asm
0x180034d88  mov     [rsp-38h+arg_8], rbx
0x180034d8d  mov     [rsp-38h+TokenHandle], rcx
0x180034d92  push    rbp
0x180034d93  push    rsi
0x180034d94  push    rdi
0x180034d95  push    r12
0x180034d97  push    r13
0x180034d99  push    r14
0x180034d9b  push    r15
0x180034d9d  mov     rbp, rsp
0x180034da0  sub     rsp, 50h
0x180034da4  mov     rsi, rdx
0x180034da7  xor     edi, edi
0x180034da9  lea     rax, xmmword_1800BF450
0x180034db0  mov     [rbp+var_18], 0
0x180034db8  lea     rbx, [rdi+rdi*4]
0x180034dbc  mov     r15d, [rax+rbx*8+18h]
0x180034dc1  mov     r12d, [rax+rbx*8+20h]
0x180034dc6  mov     r13d, [rax+rbx*8+1Ch]
0x180034dcb  mov     r14b, [rax+rbx*8+24h]
0x180034dd0  xor     edx, edx
0x180034dd2  lea     rcx, [rbp+var_18]
0x180034dd6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180034ddb  lea     rdx, xmmword_1800BF450
0x180034de2  movups  xmm0, xmmword ptr [rdx+rbx*8]
0x180034de6  movdqu  xmmword ptr [rbp+rfid.Data1], xmm0
0x180034deb  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180034def  mov     rdx, [rdx+rbx*8+10h]; unsigned __int16 *
0x180034df4  lea     rcx, [rbp+rfid]; rfid
0x180034df8  call    ?GetPath@@YAJU_GUID@@PEBGPEAPEAG@Z; GetPath(_GUID,ushort const *,ushort * *)
0x180034dfd  test    eax, eax
0x180034dff  jns     short loc_180034E06
0x180034e01  jmp     loc_180034E9C
0x180034e06  lea     rcx, [rbp+var_20]
0x180034e0a  call    ?AutoRpcImpersonateClient@@YA?AV?$unique_call@P6AJXZ$1?RpcRevertToSelf@@YAJXZ$00@wil@@XZ; AutoRpcImpersonateClient(void)
0x180034e0f  nop
0x180034e10  mov     [rbp+arg_10], 0FFFFFFFFFFFFFFFFh
0x180034e18  test    r14b, r14b
0x180034e1b  jnz     short loc_180034E63
0x180034e1d  mov     [rbp+TokenHandle], 0
0x180034e25  xor     edx, edx
0x180034e27  lea     rcx, [rbp+TokenHandle]
0x180034e2b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180034e30  call    cs:__imp_GetCurrentThread
0x180034e36  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180034e3a  mov     edx, 0Ch; DesiredAccess
0x180034e3f  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x180034e43  mov     rcx, rax; ThreadHandle
0x180034e46  call    cs:__imp_OpenThreadToken
0x180034e4c  test    eax, eax
0x180034e4e  jz      short loc_180034E5A
0x180034e50  lea     rdx, [rbp+arg_10]
0x180034e54  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x180034e59  nop
0x180034e5a  lea     rcx, [rbp+TokenHandle]
0x180034e5e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180034e63  mov     rax, [rbp+var_18]
0x180034e67  mov     [rsp+50h+var_28], rax
0x180034e6c  mov     [rsp+50h+var_30], r12d
0x180034e71  mov     r9d, r13d
0x180034e74  mov     r8d, r15d
0x180034e77  mov     rdx, rsi
0x180034e7a  call    ?CleanupKnownPath@StorageCleanup@@AEAAJPEAU_STORAGE_TRIGGER_CLEANUP_PARAMETERS@@W4_STORAGE_DEVICE_TYPE@@W4_STORAGE_CLEANUP_LEVEL@@W4__MIDL___MIDL_itf_storagetypes_0000_0000_0001@@PEAG@Z; StorageCleanup::CleanupKnownPath(_STORAGE_TRIGGER_CLEANUP_PARAMETERS *,_STORAGE_DEVICE_TYPE,_STORAGE_CLEANUP_LEVEL,__MIDL___MIDL_itf_storagetypes_0000_0000_0001,ushort *)
0x180034e7f  nop
0x180034e80  lea     rcx, [rbp+arg_10]
0x180034e84  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180034e89  nop
0x180034e8a  mov     al, [rbp+var_20]
0x180034e8d  mov     [rbp+var_20], 0
0x180034e91  test    al, al
0x180034e93  jz      short loc_180034E9C
0x180034e95  call    cs:__imp_RpcRevertToSelf
0x180034e9b  nop
0x180034e9c  lea     rcx, [rbp+var_18]
0x180034ea0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180034ea5  inc     rdi
0x180034ea8  cmp     rdi, 0Ah
0x180034eac  lea     rax, xmmword_1800BF450
0x180034eb3  jb      loc_180034DB0
0x180034eb9  xor     eax, eax
0x180034ebb  mov     rbx, [rsp+50h+arg_8]
0x180034ec3  add     rsp, 50h
0x180034ec7  pop     r15
0x180034ec9  pop     r14
0x180034ecb  pop     r13
0x180034ecd  pop     r12
0x180034ecf  pop     rdi
0x180034ed0  pop     rsi
0x180034ed1  pop     rbp
0x180034ed2  retn
```
