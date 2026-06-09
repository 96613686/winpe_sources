# CWLIDFDProv::BuildInstance(ushort *,ushort *,IFunctionDiscoveryProvider *,IFunctionDiscoveryProviderFactory *,IFunctionInstance * *)

- ea: `0x180005d3c`
- end: `0x180005f0e`
- name: `?BuildInstance@CWLIDFDProv@@SAJPEAG0PEAUIFunctionDiscoveryProvider@@PEAUIFunctionDiscoveryProviderFactory@@PEAPEAUIFunctionInstance@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(unsigned __int16 *Source, unsigned __int16 *, struct IFunctionDiscoveryProvider *, struct IFunctionDiscoveryProviderFactory *, struct IFunctionInstance **)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180007b00`
- `0x18000a3e8`

## callees

- `0x180003728`
- `0x1800054dc`
- `0x180005d3c`
- `0x180007094`
- `0x180008edc`
- `0x18000f4cc`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005e35`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005ed8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005e35`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005ed8`

## string_xrefs

- `0x180005ead`: `Failed to create fd instance. (0x%x)`

## pseudocode

```c
__int64 __fastcall CWLIDFDProv::BuildInstance(
        unsigned __int16 *Source,
        unsigned __int16 *a2,
        struct IFunctionDiscoveryProvider *a3,
        struct IFunctionDiscoveryProviderFactory *a4,
        struct IFunctionInstance **a5)
{
  int v9; // eax
  unsigned int v10; // ebx
  const unsigned __int16 *v12; // [rsp+20h] [rbp-60h]
  __int64 v13; // [rsp+20h] [rbp-60h]
  __int64 v14; // [rsp+40h] [rbp-40h] BYREF
  PROPVARIANT pvar; // [rsp+48h] [rbp-38h] BYREF
  _QWORD v16[4]; // [rsp+60h] [rbp-20h] BYREF
  int inited; // [rsp+A0h] [rbp+20h] BYREF

  inited = 0;
  v14 = 0;
  v16[0] = "CWLIDFDProv::BuildInstance";
  v16[1] = &inited;
  v16[2] = 0;
  v16[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"\\fdprov.cpp",
    "CWLIDFDProv::BuildInstance",
    (const char *)0x1BB,
    (unsigned int)a4,
    v12);
  memset(&pvar, 0, sizeof(pvar));
  if ( Source && a4 && a3 )
  {
    inited = ((__int64 (__fastcall *)(struct IFunctionDiscoveryProviderFactory *, __int64 *))a4->lpVtbl->CreatePropertyStore)(
               a4,
               &v14);
    if ( inited >= 0 )
    {
      inited = InitPropVariantFromString(Source, &pvar);
      if ( inited >= 0 )
      {
        inited = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v14 + 48LL))(
                   v14,
                   PKEY_DeviceDisplay_NetworkName,
                   &pvar);
        if ( inited >= 0 )
        {
          PropVariantClear(&pvar);
          inited = InitPropVariantFromString(a2, &pvar);
          if ( inited >= 0 )
          {
            inited = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v14 + 48LL))(
                       v14,
                       &PKEY_DeviceDisplay_FriendlyName,
                       &pvar);
            if ( inited >= 0 )
            {
              v9 = ((__int64 (__fastcall *)(struct IFunctionDiscoveryProviderFactory *, _QWORD, unsigned __int16 *, _QWORD, __int64, struct IFunctionDiscoveryProvider *, struct IFunctionInstance **))a4->lpVtbl->CreateInstance)(
                     a4,
                     0,
                     Source,
                     0,
                     v14,
                     a3,
                     a5);
              inited = v9;
              if ( v9 < 0 )
              {
                LODWORD(v13) = v9;
                TracePrintW(2u, "\\fdprov.cpp", 0x1FEu, L"Failed to create fd instance. (0x%x)", v13);
              }
            }
          }
        }
      }
    }
  }
  else
  {
    inited = -2147024809;
  }
  PropVariantClear(&pvar);
  v10 = inited;
  CTraceFuncW<long>::~CTraceFuncW<long>(v16);
  ATL::CComPtrBase<IFunctionInstanceCollection>::~CComPtrBase<IFunctionInstanceCollection>(&v14);
  return v10;
}

```

## disassembly

```asm
0x180005d3c  mov     [rsp-18h+arg_8], rbx
0x180005d41  mov     [rsp-18h+arg_10], rsi
0x180005d46  push    rbp
0x180005d47  push    rdi
0x180005d48  push    r14
0x180005d4a  mov     rbp, rsp
0x180005d4d  sub     rsp, 80h
0x180005d54  mov     rbx, r9
0x180005d57  mov     rsi, r8
0x180005d5a  mov     r14, rdx
0x180005d5d  mov     rdi, rcx
0x180005d60  mov     [rbp+arg_0], 0
0x180005d67  xorps   xmm0, xmm0
0x180005d6a  xor     eax, eax
0x180005d6c  movups  xmmword ptr [rbp+pvar], xmm0
0x180005d70  mov     qword ptr [rbp+pvar+10h], rax
0x180005d74  mov     [rbp+var_40], rax
0x180005d78  lea     rdx, aCwlidfdprovBui; "CWLIDFDProv::BuildInstance"
0x180005d7f  mov     [rbp+var_20], rdx
0x180005d83  lea     rax, [rbp+arg_0]
0x180005d87  mov     [rbp+var_18], rax
0x180005d8b  mov     [rbp+var_10], 0
0x180005d93  mov     [rbp+var_8], 0
0x180005d9b  mov     r8d, 1BBh; char *
0x180005da1  lea     rcx, aFdprovCpp; "\\fdprov.cpp"
0x180005da8  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180005dad  nop
0x180005dae  xorps   xmm0, xmm0
0x180005db1  xor     eax, eax
0x180005db3  movups  xmmword ptr [rbp+pvar], xmm0
0x180005db7  mov     qword ptr [rbp+pvar+10h], rax
0x180005dbb  test    rdi, rdi
0x180005dbe  jz      loc_180005ECD
0x180005dc4  test    rbx, rbx
0x180005dc7  jz      loc_180005ECD
0x180005dcd  test    rsi, rsi
0x180005dd0  jz      loc_180005ECD
0x180005dd6  mov     rax, [rbx]
0x180005dd9  lea     rdx, [rbp+var_40]
0x180005ddd  mov     rcx, rbx
0x180005de0  mov     rax, [rax+18h]
0x180005de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005de9  mov     [rbp+arg_0], eax
0x180005dec  test    eax, eax
0x180005dee  js      loc_180005ED4
0x180005df4  lea     rdx, [rbp+pvar]; struct tagPROPVARIANT *
0x180005df8  mov     rcx, rdi; Source
0x180005dfb  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x180005e00  mov     [rbp+arg_0], eax
0x180005e03  test    eax, eax
0x180005e05  js      loc_180005ED4
0x180005e0b  mov     rcx, [rbp+var_40]
0x180005e0f  mov     rax, [rcx]
0x180005e12  lea     r8, [rbp+pvar]
0x180005e16  lea     rdx, PKEY_DeviceDisplay_NetworkName
0x180005e1d  mov     rax, [rax+30h]
0x180005e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e26  mov     [rbp+arg_0], eax
0x180005e29  test    eax, eax
0x180005e2b  js      loc_180005ED4
0x180005e31  lea     rcx, [rbp+pvar]; pvar
0x180005e35  call    cs:__imp_PropVariantClear
0x180005e3b  lea     rdx, [rbp+pvar]; struct tagPROPVARIANT *
0x180005e3f  mov     rcx, r14; Source
0x180005e42  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x180005e47  mov     [rbp+arg_0], eax
0x180005e4a  test    eax, eax
0x180005e4c  js      loc_180005ED4
0x180005e52  mov     rcx, [rbp+var_40]
0x180005e56  mov     rax, [rcx]
0x180005e59  lea     r8, [rbp+pvar]
0x180005e5d  lea     rdx, PKEY_DeviceDisplay_FriendlyName
0x180005e64  mov     rax, [rax+30h]
0x180005e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e6d  mov     [rbp+arg_0], eax
0x180005e70  test    eax, eax
0x180005e72  js      short loc_180005ED4
0x180005e74  mov     rax, [rbx]
0x180005e77  mov     rcx, [rbp+arg_20]
0x180005e7b  mov     [rsp+80h+var_50], rcx
0x180005e80  mov     [rsp+80h+var_58], rsi
0x180005e85  mov     rcx, [rbp+var_40]
0x180005e89  mov     [rsp+80h+var_60], rcx
0x180005e8e  xor     r9d, r9d
0x180005e91  mov     r8, rdi
0x180005e94  xor     edx, edx
0x180005e96  mov     rcx, rbx
0x180005e99  mov     rax, [rax+20h]
0x180005e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ea2  mov     [rbp+arg_0], eax
0x180005ea5  test    eax, eax
0x180005ea7  jns     short loc_180005ED4
0x180005ea9  mov     dword ptr [rsp+80h+var_60], eax
0x180005ead  lea     r9, aFailedToCreate; "Failed to create fd instance. (0x%x)"
0x180005eb4  mov     r8d, 1FEh; unsigned int
0x180005eba  lea     rdx, aFdprovCpp; "\\fdprov.cpp"
0x180005ec1  mov     ecx, 2; unsigned __int8
0x180005ec6  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180005ecb  jmp     short loc_180005ED4
0x180005ecd  mov     [rbp+arg_0], 80070057h
0x180005ed4  lea     rcx, [rbp+pvar]; pvar
0x180005ed8  call    cs:__imp_PropVariantClear
0x180005ede  mov     ebx, [rbp+arg_0]
0x180005ee1  lea     rcx, [rbp+var_20]
0x180005ee5  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180005eea  nop
0x180005eeb  lea     rcx, [rbp+var_40]
0x180005eef  call    ??1?$CComPtrBase@UIFunctionInstanceCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFunctionInstanceCollection>::~CComPtrBase<IFunctionInstanceCollection>(void)
0x180005ef4  mov     eax, ebx
0x180005ef6  lea     r11, [rsp+80h+var_s0]
0x180005efe  mov     rbx, [r11+28h]
0x180005f02  mov     rsi, [r11+30h]
0x180005f06  mov     rsp, r11
0x180005f09  pop     r14
0x180005f0b  pop     rdi
0x180005f0c  pop     rbp
0x180005f0d  retn
```
