# GetPath(_GUID,ushort const *,ushort * *)

- ea: `0x180039208`
- end: `0x180039345`
- name: `?GetPath@@YAJU_GUID@@PEBGPEAPEAG@Z`
- size: `317`
- prototype: `__int64 __fastcall(KNOWNFOLDERID *rfid, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180034d88`

## callees

- `0x180019d4c`
- `0x180019d94`
- `0x18001c3d8`
- `0x18001dcf4`
- `0x18001fcac`
- `0x18002ebe8`
- `0x180038380`
- `0x180039208`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003923b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003923b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180039251`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180039251`
- `RPCRT4!RpcRevertToSelf` at `0x18003927c`
- `RPCRT4!RpcRevertToSelf` at `0x1800392cc`
- `RPCRT4!RpcRevertToSelf` at `0x180039332`
- `RPCRT4!RpcRevertToSelf` at `0x18003927c`
- `RPCRT4!RpcRevertToSelf` at `0x1800392cc`
- `RPCRT4!RpcRevertToSelf` at `0x180039332`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800392a4`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800392a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall GetPath(KNOWNFOLDERID *rfid, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  char v6; // bl
  HANDLE CurrentThread; // rax
  __int64 v8; // rax
  char v9; // al
  HRESULT v10; // edi
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rax
  char v14; // [rsp+20h] [rbp-30h] BYREF
  _BYTE v15[7]; // [rsp+21h] [rbp-2Fh] BYREF
  PWSTR ppszPath; // [rsp+28h] [rbp-28h] BYREF
  void *TokenHandle; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v18[2]; // [rsp+38h] [rbp-18h] BYREF
  const unsigned __int16 *v19; // [rsp+48h] [rbp-8h] BYREF

  v19 = a2;
  v6 = 0;
  v14 = 0;
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    v8 = AutoRpcImpersonateClient(v15);
    wil::unique_call<long (*)(void),&long RpcRevertToSelf(void),1>::operator=(&v14, v8);
    v9 = v15[0];
    v15[0] = 0;
    if ( v9 )
      RpcRevertToSelf();
    v6 = v14;
  }
  ppszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  v10 = SHGetKnownFolderPath(rfid, 0, 0, &ppszPath);
  if ( v10 >= 0 )
  {
    if ( a2 )
    {
      wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>> &,unsigned short const * &>(
        v18,
        &ppszPath,
        &v19);
      v12 = (unsigned __int16 *)v18[0];
      v18[0] = 0;
      *a3 = v12;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v18);
    }
    else
    {
      v13 = ppszPath;
      ppszPath = 0;
      *a3 = v13;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPath);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    v14 = 0;
    if ( v6 )
      RpcRevertToSelf();
    return 0;
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPath);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    v14 = 0;
    if ( v6 )
      RpcRevertToSelf();
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x180039208  push    rbp
0x18003920a  push    rbx
0x18003920b  push    rsi
0x18003920c  push    rdi
0x18003920d  push    r14
0x18003920f  mov     rbp, rsp
0x180039212  sub     rsp, 50h
0x180039216  mov     rsi, r8
0x180039219  mov     r14, rdx
0x18003921c  mov     rdi, rcx
0x18003921f  mov     [rbp+var_8], rdx
0x180039223  xor     bl, bl
0x180039225  mov     [rbp+var_30], bl
0x180039228  mov     [rbp+TokenHandle], 0
0x180039230  xor     edx, edx
0x180039232  lea     rcx, [rbp+TokenHandle]
0x180039236  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003923b  call    cs:__imp_GetCurrentThread
0x180039241  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180039245  mov     edx, 0Ch; DesiredAccess
0x18003924a  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18003924e  mov     rcx, rax; ThreadHandle
0x180039251  call    cs:__imp_OpenThreadToken
0x180039257  test    eax, eax
0x180039259  jnz     short loc_180039285
0x18003925b  lea     rcx, [rbp+var_2F]
0x18003925f  call    ?AutoRpcImpersonateClient@@YA?AV?$unique_call@P6AJXZ$1?RpcRevertToSelf@@YAJXZ$00@wil@@XZ; AutoRpcImpersonateClient(void)
0x180039264  nop
0x180039265  mov     rdx, rax
0x180039268  lea     rcx, [rbp+var_30]
0x18003926c  call    ??4?$unique_call@P6AJXZ$1?RpcRevertToSelf@@YAJXZ$00@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_call<long (*)(void),&RpcRevertToSelf(void),1>::operator=(wil::unique_call<long (*)(void),&RpcRevertToSelf(void),1> &&)
0x180039271  nop
0x180039272  mov     al, [rbp+var_2F]
0x180039275  mov     [rbp+var_2F], bl
0x180039278  test    al, al
0x18003927a  jz      short loc_180039282
0x18003927c  call    cs:__imp_RpcRevertToSelf
0x180039282  mov     bl, [rbp+var_30]
0x180039285  mov     [rbp+ppszPath], 0
0x18003928d  xor     edx, edx
0x18003928f  lea     rcx, [rbp+ppszPath]
0x180039293  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180039298  lea     r9, [rbp+ppszPath]; ppszPath
0x18003929c  xor     r8d, r8d; hToken
0x18003929f  xor     edx, edx; dwFlags
0x1800392a1  mov     rcx, rdi; rfid
0x1800392a4  call    cs:__imp_SHGetKnownFolderPath
0x1800392aa  mov     edi, eax
0x1800392ac  test    eax, eax
0x1800392ae  jns     short loc_1800392D6
0x1800392b0  lea     rcx, [rbp+ppszPath]
0x1800392b4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800392b9  nop
0x1800392ba  lea     rcx, [rbp+TokenHandle]
0x1800392be  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800392c3  nop
0x1800392c4  mov     [rbp+var_30], 0
0x1800392c8  test    bl, bl
0x1800392ca  jz      short loc_1800392D2
0x1800392cc  call    cs:__imp_RpcRevertToSelf
0x1800392d2  mov     eax, edi
0x1800392d4  jmp     short loc_18003933A
0x1800392d6  test    r14, r14
0x1800392d9  jz      short loc_180039307
0x1800392db  lea     r8, [rbp+var_8]
0x1800392df  lea     rdx, [rbp+ppszPath]
0x1800392e3  lea     rcx, [rbp+var_18]
0x1800392e7  call    ??$str_concat@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV12@AEAPEBG@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEAV10@AEAPEBG@Z; wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * &)
0x1800392ec  nop
0x1800392ed  mov     rax, [rbp+var_18]
0x1800392f1  mov     [rbp+var_18], 0
0x1800392f9  mov     [rsi], rax
0x1800392fc  lea     rcx, [rbp+var_18]
0x180039300  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180039305  jmp     short loc_180039316
0x180039307  mov     rax, [rbp+ppszPath]
0x18003930b  mov     [rbp+ppszPath], 0
0x180039313  mov     [rsi], rax
0x180039316  lea     rcx, [rbp+ppszPath]
0x18003931a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003931f  nop
0x180039320  lea     rcx, [rbp+TokenHandle]
0x180039324  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180039329  nop
0x18003932a  mov     [rbp+var_30], 0
0x18003932e  test    bl, bl
0x180039330  jz      short loc_180039338
0x180039332  call    cs:__imp_RpcRevertToSelf
0x180039338  xor     eax, eax
0x18003933a  add     rsp, 50h
0x18003933e  pop     r14
0x180039340  pop     rdi
0x180039341  pop     rsi
0x180039342  pop     rbx
0x180039343  pop     rbp
0x180039344  retn
```
