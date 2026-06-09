# DllGetClassObject

- ea: `0x18000ac80`
- end: `0x18000ae7a`
- name: `DllGetClassObject`
- size: `506`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000ac80`
- `0x18000ba04`
- `0x180017010`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000ae5b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000ae5b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000acbb`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000ad0f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000ad63`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000adb7`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000ae08`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000acbb`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000ad0f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000ad63`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000adb7`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000ae08`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v5; // rax
  CCFDyn *v6; // rax
  CCFDyn *v7; // rbx
  _QWORD *v8; // rcx
  __int64 v9; // rax
  CCFDyn *v10; // rax
  _QWORD *v11; // rcx
  __int64 v12; // rax
  CCFDyn *v13; // rax
  _QWORD *v14; // rcx
  __int64 v15; // rax
  CCFDyn *v16; // rax
  _QWORD *v17; // rcx
  __int64 v18; // rax
  CCFDyn *v19; // rax
  _QWORD *v20; // rcx
  HRESULT v22; // edi

  *ppv = 0;
  v5 = *(_QWORD *)&CLSID_RegProvider.Data1 - *(_QWORD *)&rclsid->Data1;
  if ( *(_QWORD *)&CLSID_RegProvider.Data1 == *(_QWORD *)&rclsid->Data1 )
    v5 = *(_QWORD *)CLSID_RegProvider.Data4 - *(_QWORD *)rclsid->Data4;
  if ( v5 )
  {
    v9 = *(_QWORD *)&CLSID_RegPropProv.Data1 - *(_QWORD *)&rclsid->Data1;
    if ( *(_QWORD *)&CLSID_RegPropProv.Data1 == *(_QWORD *)&rclsid->Data1 )
      v9 = *(_QWORD *)CLSID_RegPropProv.Data4 - *(_QWORD *)rclsid->Data4;
    if ( v9 )
    {
      v12 = *(_QWORD *)&CLSID_PerfProvider.Data1 - *(_QWORD *)&rclsid->Data1;
      if ( *(_QWORD *)&CLSID_PerfProvider.Data1 == *(_QWORD *)&rclsid->Data1 )
        v12 = *(_QWORD *)CLSID_PerfProvider.Data4 - *(_QWORD *)rclsid->Data4;
      if ( v12 )
      {
        v15 = *(_QWORD *)&CLSID_PerfPropProv.Data1 - *(_QWORD *)&rclsid->Data1;
        if ( *(_QWORD *)&CLSID_PerfPropProv.Data1 == *(_QWORD *)&rclsid->Data1 )
          v15 = *(_QWORD *)CLSID_PerfPropProv.Data4 - *(_QWORD *)rclsid->Data4;
        if ( v15 )
        {
          v18 = *(_QWORD *)&CLSID_RegistryEventProvider.Data1 - *(_QWORD *)&rclsid->Data1;
          if ( *(_QWORD *)&CLSID_RegistryEventProvider.Data1 == *(_QWORD *)&rclsid->Data1 )
            v18 = *(_QWORD *)CLSID_RegistryEventProvider.Data4 - *(_QWORD *)rclsid->Data4;
          if ( v18 )
            return -2147467259;
          v19 = (CCFDyn *)CWin32DefaultArena::WbemMemAlloc(0x10u);
          v7 = v19;
          if ( v19 )
          {
            CCFDyn::CCFDyn(v19);
            *v20 = &CRegEventProviderFactory::`vftable';
          }
          else
          {
            v7 = 0;
          }
        }
        else
        {
          v16 = (CCFDyn *)CWin32DefaultArena::WbemMemAlloc(0x10u);
          v7 = v16;
          if ( v16 )
          {
            *(_OWORD *)v16 = 0;
            CCFDyn::CCFDyn(v16);
            *v17 = &CCFPerfProp::`vftable';
          }
          else
          {
            v7 = 0;
          }
        }
      }
      else
      {
        v13 = (CCFDyn *)CWin32DefaultArena::WbemMemAlloc(0x10u);
        v7 = v13;
        if ( v13 )
        {
          *(_OWORD *)v13 = 0;
          CCFDyn::CCFDyn(v13);
          *v14 = &CCFPerf::`vftable';
        }
        else
        {
          v7 = 0;
        }
      }
    }
    else
    {
      v10 = (CCFDyn *)CWin32DefaultArena::WbemMemAlloc(0x10u);
      v7 = v10;
      if ( v10 )
      {
        *(_OWORD *)v10 = 0;
        CCFDyn::CCFDyn(v10);
        *v11 = &CCFRegProp::`vftable';
      }
      else
      {
        v7 = 0;
      }
    }
  }
  else
  {
    v6 = (CCFDyn *)CWin32DefaultArena::WbemMemAlloc(0x10u);
    v7 = v6;
    if ( v6 )
    {
      *(_OWORD *)v6 = 0;
      CCFDyn::CCFDyn(v6);
      *v8 = &CCFReg::`vftable';
    }
    else
    {
      v7 = 0;
    }
  }
  if ( !v7 )
    return -2147024882;
  v22 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v7)(v7, riid, ppv);
  if ( v22 < 0 )
    CWin32DefaultArena::WbemMemFree(v7);
  return v22;
}

```

## disassembly

```asm
0x18000ac80  mov     [rsp+arg_0], rbx
0x18000ac85  mov     [rsp+arg_8], rsi
0x18000ac8a  push    rdi
0x18000ac8b  sub     rsp, 20h
0x18000ac8f  mov     rdi, r8
0x18000ac92  mov     rsi, rdx
0x18000ac95  mov     qword ptr [r8], 0
0x18000ac9c  mov     rax, qword ptr cs:CLSID_RegProvider.Data1
0x18000aca3  sub     rax, [rcx]
0x18000aca6  jnz     short loc_18000ACB3
0x18000aca8  mov     rax, qword ptr cs:CLSID_RegProvider.Data4
0x18000acaf  sub     rax, [rcx+8]
0x18000acb3  test    rax, rax
0x18000acb6  jnz     short loc_18000ACF0
0x18000acb8  lea     ecx, [rax+10h]
0x18000acbb  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000acc1  mov     rbx, rax
0x18000acc4  mov     [rsp+28h+arg_10], rax
0x18000acc9  test    rax, rax
0x18000accc  jz      short loc_18000ACE9
0x18000acce  xorps   xmm0, xmm0
0x18000acd1  movups  xmmword ptr [rax], xmm0
0x18000acd4  mov     rcx, rax; this
0x18000acd7  call    ??0CCFDyn@@QEAA@XZ; CCFDyn::CCFDyn(void)
0x18000acdc  nop
0x18000acdd  lea     rax, ??_7CCFReg@@6B@; const CCFReg::`vftable'
0x18000ace4  mov     [rcx], rax
0x18000ace7  jmp     short loc_18000ACEB
0x18000ace9  xor     ebx, ebx
0x18000aceb  jmp     loc_18000AE32
0x18000acf0  mov     rax, qword ptr cs:CLSID_RegPropProv.Data1
0x18000acf7  sub     rax, [rcx]
0x18000acfa  jnz     short loc_18000AD07
0x18000acfc  mov     rax, qword ptr cs:CLSID_RegPropProv.Data4
0x18000ad03  sub     rax, [rcx+8]
0x18000ad07  test    rax, rax
0x18000ad0a  jnz     short loc_18000AD44
0x18000ad0c  lea     ecx, [rax+10h]
0x18000ad0f  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000ad15  mov     rbx, rax
0x18000ad18  mov     [rsp+28h+arg_10], rax
0x18000ad1d  test    rax, rax
0x18000ad20  jz      short loc_18000AD3D
0x18000ad22  xorps   xmm0, xmm0
0x18000ad25  movups  xmmword ptr [rax], xmm0
0x18000ad28  mov     rcx, rax; this
0x18000ad2b  call    ??0CCFDyn@@QEAA@XZ; CCFDyn::CCFDyn(void)
0x18000ad30  nop
0x18000ad31  lea     rax, ??_7CCFRegProp@@6B@; const CCFRegProp::`vftable'
0x18000ad38  mov     [rcx], rax
0x18000ad3b  jmp     short loc_18000AD3F
0x18000ad3d  xor     ebx, ebx
0x18000ad3f  jmp     loc_18000AE32
0x18000ad44  mov     rax, qword ptr cs:CLSID_PerfProvider.Data1
0x18000ad4b  sub     rax, [rcx]
0x18000ad4e  jnz     short loc_18000AD5B
0x18000ad50  mov     rax, qword ptr cs:CLSID_PerfProvider.Data4
0x18000ad57  sub     rax, [rcx+8]
0x18000ad5b  test    rax, rax
0x18000ad5e  jnz     short loc_18000AD98
0x18000ad60  lea     ecx, [rax+10h]
0x18000ad63  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000ad69  mov     rbx, rax
0x18000ad6c  mov     [rsp+28h+arg_10], rax
0x18000ad71  test    rax, rax
0x18000ad74  jz      short loc_18000AD91
0x18000ad76  xorps   xmm0, xmm0
0x18000ad79  movups  xmmword ptr [rax], xmm0
0x18000ad7c  mov     rcx, rax; this
0x18000ad7f  call    ??0CCFDyn@@QEAA@XZ; CCFDyn::CCFDyn(void)
0x18000ad84  nop
0x18000ad85  lea     rax, ??_7CCFPerf@@6B@; const CCFPerf::`vftable'
0x18000ad8c  mov     [rcx], rax
0x18000ad8f  jmp     short loc_18000AD93
0x18000ad91  xor     ebx, ebx
0x18000ad93  jmp     loc_18000AE32
0x18000ad98  mov     rax, qword ptr cs:CLSID_PerfPropProv.Data1
0x18000ad9f  sub     rax, [rcx]
0x18000ada2  jnz     short loc_18000ADAF
0x18000ada4  mov     rax, qword ptr cs:CLSID_PerfPropProv.Data4
0x18000adab  sub     rax, [rcx+8]
0x18000adaf  test    rax, rax
0x18000adb2  jnz     short loc_18000ADE9
0x18000adb4  lea     ecx, [rax+10h]
0x18000adb7  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000adbd  mov     rbx, rax
0x18000adc0  mov     [rsp+28h+arg_10], rax
0x18000adc5  test    rax, rax
0x18000adc8  jz      short loc_18000ADE5
0x18000adca  xorps   xmm0, xmm0
0x18000adcd  movups  xmmword ptr [rax], xmm0
0x18000add0  mov     rcx, rax; this
0x18000add3  call    ??0CCFDyn@@QEAA@XZ; CCFDyn::CCFDyn(void)
0x18000add8  nop
0x18000add9  lea     rax, ??_7CCFPerfProp@@6B@; const CCFPerfProp::`vftable'
0x18000ade0  mov     [rcx], rax
0x18000ade3  jmp     short loc_18000ADE7
0x18000ade5  xor     ebx, ebx
0x18000ade7  jmp     short loc_18000AE32
0x18000ade9  mov     rax, qword ptr cs:?CLSID_RegistryEventProvider@@3U_GUID@@B.Data1; _GUID const CLSID_RegistryEventProvider ...
0x18000adf0  sub     rax, [rcx]
0x18000adf3  jnz     short loc_18000AE00
0x18000adf5  mov     rax, qword ptr cs:?CLSID_RegistryEventProvider@@3U_GUID@@B.Data4; _GUID const CLSID_RegistryEventProvider ...
0x18000adfc  sub     rax, [rcx+8]
0x18000ae00  test    rax, rax
0x18000ae03  jnz     short loc_18000AE65
0x18000ae05  lea     ecx, [rax+10h]
0x18000ae08  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000ae0e  mov     rbx, rax
0x18000ae11  mov     [rsp+28h+arg_10], rax
0x18000ae16  test    rax, rax
0x18000ae19  jz      short loc_18000AE30
0x18000ae1b  mov     rcx, rax; this
0x18000ae1e  call    ??0CCFDyn@@QEAA@XZ; CCFDyn::CCFDyn(void)
0x18000ae23  nop
0x18000ae24  lea     rax, ??_7CRegEventProviderFactory@@6B@; const CRegEventProviderFactory::`vftable'
0x18000ae2b  mov     [rcx], rax
0x18000ae2e  jmp     short loc_18000AE32
0x18000ae30  xor     ebx, ebx
0x18000ae32  test    rbx, rbx
0x18000ae35  jnz     short loc_18000AE3E
0x18000ae37  mov     eax, 8007000Eh
0x18000ae3c  jmp     short loc_18000AE6A
0x18000ae3e  mov     rax, [rbx]
0x18000ae41  mov     r8, rdi
0x18000ae44  mov     rdx, rsi
0x18000ae47  mov     rcx, rbx
0x18000ae4a  mov     rax, [rax]
0x18000ae4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae52  mov     edi, eax
0x18000ae54  test    eax, eax
0x18000ae56  jns     short loc_18000AE61
0x18000ae58  mov     rcx, rbx
0x18000ae5b  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000ae61  mov     eax, edi
0x18000ae63  jmp     short loc_18000AE6A
0x18000ae65  mov     eax, 80004005h
0x18000ae6a  mov     rbx, [rsp+28h+arg_0]
0x18000ae6f  mov     rsi, [rsp+28h+arg_8]
0x18000ae74  add     rsp, 20h
0x18000ae78  pop     rdi
0x18000ae79  retn
```
