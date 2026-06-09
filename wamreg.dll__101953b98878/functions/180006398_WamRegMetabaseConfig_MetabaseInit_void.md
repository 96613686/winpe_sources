# WamRegMetabaseConfig::MetabaseInit(void)

- ea: `0x180006398`
- end: `0x180006400`
- name: `?MetabaseInit@WamRegMetabaseConfig@@SAJXZ`
- size: `104`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180004540`

## callees

- `0x180006398`
- `0x180007010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800063c9`
- `ole32!CoCreateInstance` at `0x1800063c9`

## pseudocode

```c
__int64 WamRegMetabaseConfig::MetabaseInit(void)
{
  HRESULT Instance; // ebx

  WamRegMetabaseConfig::m_pMetabase = 0;
  Instance = CoCreateInstance(&CLSID_MSAdminBase_W, 0, 0x15u, &IID_IMSAdminBase_W, &WamRegMetabaseConfig::m_pMetabase);
  if ( Instance < 0 && WamRegMetabaseConfig::m_pMetabase )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase + 16LL))(WamRegMetabaseConfig::m_pMetabase);
    WamRegMetabaseConfig::m_pMetabase = 0;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180006398  push    rbx
0x18000639a  sub     rsp, 30h
0x18000639e  xor     edx, edx; pUnkOuter
0x1800063a0  mov     cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA, 0; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x1800063ab  lea     rax, ?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x1800063b2  lea     r9, IID_IMSAdminBase_W; riid
0x1800063b9  mov     [rsp+38h+ppv], rax; ppv
0x1800063be  lea     rcx, CLSID_MSAdminBase_W; rclsid
0x1800063c5  lea     r8d, [rdx+15h]; dwClsContext
0x1800063c9  call    cs:__imp_CoCreateInstance
0x1800063cf  mov     ebx, eax
0x1800063d1  test    eax, eax
0x1800063d3  jns     short loc_1800063F8
0x1800063d5  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x1800063dc  test    rcx, rcx
0x1800063df  jz      short loc_1800063F8
0x1800063e1  mov     rdx, [rcx]
0x1800063e4  mov     rax, [rdx+10h]
0x1800063e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063ed  mov     cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA, 0; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x1800063f8  mov     eax, ebx
0x1800063fa  add     rsp, 30h
0x1800063fe  pop     rbx
0x1800063ff  retn
```
