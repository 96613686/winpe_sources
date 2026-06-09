# DllGetClassObject

- ea: `0x180029550`
- end: `0x1800295b8`
- name: `DllGetClassObject`
- size: `104`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180012260`
- `0x1800275a8`
- `0x180029550`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180029592`
- `RPCRT4!NdrDllGetClassObject` at `0x180029592`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  Microsoft::WRL::Details *v6; // rbp
  HRESULT result; // eax

  v6 = (Microsoft::WRL::Details *)Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  result = NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)&aProxyFileList,
             &CLSID_PSFactoryBuffer,
             &gPFactory);
  if ( result < 0 )
    return Microsoft::WRL::Details::GetClassObject<1>(v6, ppv);
  return result;
}

```

## disassembly

```asm
0x180029550  push    rbx
0x180029552  push    rbp
0x180029553  push    rsi
0x180029554  push    rdi
0x180029555  sub     rsp, 38h
0x180029559  mov     rbx, r8
0x18002955c  mov     rdi, rdx
0x18002955f  mov     rsi, rcx
0x180029562  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x180029567  mov     rbp, rax
0x18002956a  lea     r9, aProxyFileList; pProxyFileList
0x180029571  lea     rax, gPFactory
0x180029578  mov     r8, rbx; ppv
0x18002957b  mov     [rsp+58h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180029580  mov     rdx, rdi; riid
0x180029583  lea     rax, CLSID_PSFactoryBuffer
0x18002958a  mov     rcx, rsi; rclsid
0x18002958d  mov     [rsp+58h+pclsid], rax; pclsid
0x180029592  call    cs:__imp_NdrDllGetClassObject
0x180029598  test    eax, eax
0x18002959a  jns     short loc_1800295AF
0x18002959c  mov     r9, rdi
0x18002959f  mov     [rsp+58h+pclsid], rbx; PVOID
0x1800295a4  mov     r8, rsi
0x1800295a7  mov     rcx, rbp; this
0x1800295aa  call    ??$GetClassObject@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGAEBU_GUID@@2PEAPEAX@Z; Microsoft::WRL::Details::GetClassObject<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,_GUID const &,_GUID const &,void * *)
0x1800295af  add     rsp, 38h
0x1800295b3  pop     rdi
0x1800295b4  pop     rsi
0x1800295b5  pop     rbp
0x1800295b6  pop     rbx
0x1800295b7  retn
```
