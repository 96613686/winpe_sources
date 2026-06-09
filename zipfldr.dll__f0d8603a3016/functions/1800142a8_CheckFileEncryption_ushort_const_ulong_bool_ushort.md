# CheckFileEncryption(ushort const *,ulong,bool *,ushort * *)

- ea: `0x1800142a8`
- end: `0x1800143c6`
- name: `?CheckFileEncryption@@YAJPEBGKPEA_NPEAPEAG@Z`
- size: `286`
- prototype: `__int64 __fastcall(PCWSTR pszPath, unsigned int, bool *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013db8`

## callees

- `0x18001367c`
- `0x1800142a8`
- `0x180024a24`
- `0x180031e94`
- `0x180036f50`
- `0x18003c824`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x180014371`
- `SHELL32!SHCreateItemFromParsingName` at `0x180014371`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001431b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001431b`

## pseudocode

```c
__int64 __fastcall CheckFileEncryption(PCWSTR pszPath, __int16 a2, bool *a3, unsigned __int16 **a4)
{
  unsigned __int16 *v8; // rax
  HRESULT v9; // eax
  unsigned int v10; // ebx
  int EnterpriseId; // eax
  LPVOID pv; // [rsp+20h] [rbp-20h] BYREF
  void *ppv; // [rsp+28h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]

  *a3 = 0;
  *a4 = 0;
  if ( (a2 & 0x4000) == 0 )
    return 0;
  ppv = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  v9 = SHCreateItemFromParsingName(pszPath, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
  v10 = v9;
  if ( v9 >= 0 )
  {
    pv = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pv,
      0);
    EnterpriseId = IShellItem_GetEnterpriseId((struct IShellItem *)ppv, (unsigned __int16 **)&pv);
    v10 = EnterpriseId;
    if ( EnterpriseId >= 0 )
    {
      v8 = (unsigned __int16 *)pv;
      if ( !pv )
        *a3 = 1;
      pv = 0;
      *a4 = v8;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E3,
      (unsigned int)"shell\\ext\\zip\\dropin.cpp",
      (const char *)(unsigned int)EnterpriseId,
      (int)pv);
    if ( pv )
      CoTaskMemFree(pv);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E0,
      (unsigned int)"shell\\ext\\zip\\dropin.cpp",
      (const char *)(unsigned int)v9,
      (int)pv);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return v10;
}

```

## disassembly

```asm
0x1800142a8  mov     [rsp-18h+arg_8], rbx
0x1800142ad  push    rbp
0x1800142ae  push    rsi
0x1800142af  push    rdi
0x1800142b0  mov     rbp, rsp
0x1800142b3  sub     rsp, 40h
0x1800142b7  mov     rax, cs:__security_cookie
0x1800142be  xor     rax, rsp
0x1800142c1  mov     [rbp+var_10], rax
0x1800142c5  mov     byte ptr [r8], 0
0x1800142c9  mov     rsi, r9
0x1800142cc  mov     qword ptr [r9], 0
0x1800142d3  mov     rdi, r8
0x1800142d6  mov     rbx, rcx
0x1800142d9  bt      edx, 0Eh
0x1800142dd  jb      short loc_180014350
0x1800142df  xor     eax, eax
0x1800142e1  mov     rcx, [rbp+var_10]
0x1800142e5  xor     rcx, rsp; StackCookie
0x1800142e8  call    __security_check_cookie
0x1800142ed  mov     rbx, [rsp+40h+arg_8]
0x1800142f2  add     rsp, 40h
0x1800142f6  pop     rdi
0x1800142f7  pop     rsi
0x1800142f8  pop     rbp
0x1800142f9  retn
0x1800142fa  mov     rcx, [rbp+18h]; this
0x1800142fe  lea     r8, aShellExtZipDro; "shell\\ext\\zip\\dropin.cpp"
0x180014305  mov     r9d, eax; char *
0x180014308  mov     edx, 5E3h; void *
0x18001430d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014312  mov     rcx, [rbp+pv]; pv
0x180014316  test    rcx, rcx
0x180014319  jz      short loc_180014321
0x18001431b  call    cs:__imp_CoTaskMemFree
0x180014321  lea     rcx, [rbp+ppv]
0x180014325  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001432a  mov     eax, ebx
0x18001432c  jmp     short loc_1800142E1
0x18001432e  mov     rax, [rbp+pv]
0x180014332  test    rax, rax
0x180014335  jnz     short loc_18001433A
0x180014337  mov     byte ptr [rdi], 1
0x18001433a  lea     rcx, [rbp+ppv]
0x18001433e  mov     [rbp+pv], 0
0x180014346  mov     [rsi], rax
0x180014349  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001434e  jmp     short loc_1800142DF
0x180014350  lea     rcx, [rbp+ppv]
0x180014354  mov     [rbp+ppv], 0
0x18001435c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014361  lea     r9, [rbp+ppv]; ppv
0x180014365  xor     edx, edx; pbc
0x180014367  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18001436e  mov     rcx, rbx; pszPath
0x180014371  call    cs:__imp_SHCreateItemFromParsingName
0x180014377  mov     ebx, eax
0x180014379  test    eax, eax
0x18001437b  jns     short loc_180014397
0x18001437d  mov     rcx, [rbp+18h]; this
0x180014381  lea     r8, aShellExtZipDro; "shell\\ext\\zip\\dropin.cpp"
0x180014388  mov     r9d, eax; char *
0x18001438b  mov     edx, 5E0h; void *
0x180014390  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014395  jmp     short loc_180014321
0x180014397  xor     edx, edx
0x180014399  mov     [rbp+pv], 0
0x1800143a1  lea     rcx, [rbp+pv]
0x1800143a5  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800143aa  mov     rcx, [rbp+ppv]; struct IShellItem *
0x1800143ae  lea     rdx, [rbp+pv]; unsigned __int16 **
0x1800143b2  call    ?IShellItem_GetEnterpriseId@@YAJPEAUIShellItem@@PEAPEAG@Z; IShellItem_GetEnterpriseId(IShellItem *,ushort * *)
0x1800143b7  mov     ebx, eax
0x1800143b9  test    eax, eax
0x1800143bb  jns     loc_18001432E
0x1800143c1  jmp     loc_1800142FA
```
