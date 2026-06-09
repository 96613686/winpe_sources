# CXWizard::HrEnsureRegistryInformationLoaded(void)

- ea: `0x180016d24`
- end: `0x180016dce`
- name: `?HrEnsureRegistryInformationLoaded@CXWizard@@AEAAJXZ`
- size: `170`
- prototype: `__int64 __fastcall(CXWizard *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180016a30`
- `0x180016af0`
- `0x180017c40`
- `0x180017e20`
- `0x180017f90`
- `0x1800180f0`
- `0x180018260`
- `0x1800183c0`

## callees

- `0x18000ae04`
- `0x180016d24`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016d5a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016d5a`

## pseudocode

```c
__int64 __fastcall CXWizard::HrEnsureRegistryInformationLoaded(CXWizard *this)
{
  LPVOID *ppv; // rcx
  HRESULT Instance; // eax
  unsigned int v4; // ebx
  PVOID *v5; // rcx

  ppv = (LPVOID *)((char *)this + 112);
  if ( *ppv )
    return 0;
  Instance = CoCreateInstance(&CLSID_CPXWizardRegistryInfo, 0, 0x401u, &IID_IPXWizardRegistryInfo, ppv);
  v4 = Instance;
  if ( Instance >= 0 )
    goto LABEL_7;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_8;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_f05614902d2b35c2540f8a05e236bf04_Traceguids,
      (unsigned int)Instance);
LABEL_7:
    v5 = (PVOID *)WPP_GLOBAL_Control;
LABEL_8:
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x10) != 0 )
      WPP_SF_d(v5[2], 13, WPP_f05614902d2b35c2540f8a05e236bf04_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x180016d24  mov     [rsp+arg_0], rbx
0x180016d29  push    rdi
0x180016d2a  sub     rsp, 30h
0x180016d2e  add     rcx, 70h ; 'p'
0x180016d32  cmp     qword ptr [rcx], 0
0x180016d36  jz      short loc_180016D3F
0x180016d38  xor     eax, eax
0x180016d3a  jmp     loc_180016DC3
0x180016d3f  mov     [rsp+38h+ppv], rcx; ppv
0x180016d44  lea     r9, IID_IPXWizardRegistryInfo; riid
0x180016d4b  lea     rcx, CLSID_CPXWizardRegistryInfo; rclsid
0x180016d52  xor     edx, edx; pUnkOuter
0x180016d54  mov     r8d, 401h; dwClsContext
0x180016d5a  call    cs:__imp_CoCreateInstance
0x180016d60  lea     rdi, WPP_GLOBAL_Control
0x180016d67  mov     ebx, eax
0x180016d69  test    eax, eax
0x180016d6b  jns     short loc_180016D97
0x180016d6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d74  cmp     rcx, rdi
0x180016d77  jz      short loc_180016DC1
0x180016d79  test    byte ptr [rcx+1Ch], 4
0x180016d7d  jz      short loc_180016D9E
0x180016d7f  mov     rcx, [rcx+10h]
0x180016d83  lea     r8, WPP_f05614902d2b35c2540f8a05e236bf04_Traceguids
0x180016d8a  mov     edx, 0Ch
0x180016d8f  mov     r9d, eax
0x180016d92  call    WPP_SF_d
0x180016d97  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d9e  cmp     rcx, rdi
0x180016da1  jz      short loc_180016DC1
0x180016da3  test    byte ptr [rcx+1Ch], 10h
0x180016da7  jz      short loc_180016DC1
0x180016da9  mov     rcx, [rcx+10h]
0x180016dad  lea     r8, WPP_f05614902d2b35c2540f8a05e236bf04_Traceguids
0x180016db4  mov     edx, 0Dh
0x180016db9  mov     r9d, ebx
0x180016dbc  call    WPP_SF_d
0x180016dc1  mov     eax, ebx
0x180016dc3  mov     rbx, [rsp+38h+arg_0]
0x180016dc8  add     rsp, 30h
0x180016dcc  pop     rdi
0x180016dcd  retn
```
