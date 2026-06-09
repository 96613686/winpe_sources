# CXWizardUIPageBase<CProfileExistsPage,&_GUID const CLSID_ProfileExistsPage,10609,10108>::~CXWizardUIPageBase<CProfileExistsPage,&_GUID const CLSID_ProfileExistsPage,10609,10108>(void)

- ea: `0x180003514`
- end: `0x180003536`
- name: `??1?$CXWizardUIPageBase@VCProfileExistsPage@@$1?CLSID_ProfileExistsPage@@3U_GUID@@B$0CJHB@$0CHHM@@@UEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180002e68`
- `0x180002eac`
- `0x180002ef0`
- `0x180002f48`
- `0x180002f8c`
- `0x1800031a0`
- `0x1800031ec`
- `0x180003238`
- `0x180003340`
- `0x18000338c`
- `0x1800035d8`
- `0x180003b70`
- `0x180003ba8`
- `0x180020a10`
- `0x180023e74`

## callees

- `0x1800034d8`
- `0x18000356c`

## pseudocode

```c
__int64 __fastcall CXWizardUIPageBase<CProfileExistsPage,&_GUID const CLSID_ProfileExistsPage,10609,10108>::~CXWizardUIPageBase<CProfileExistsPage,&_GUID const CLSID_ProfileExistsPage,10609,10108>(
        __int64 a1)
{
  ATL::CDynamicStdCallThunk2::~CDynamicStdCallThunk2((ATL::CDynamicStdCallThunk2 *)(a1 + 136));
  return CXWizardPageBase<CInfraSetupPage,&_GUID const CLSID_InfraSetupPage,10602>::~CXWizardPageBase<CInfraSetupPage,&_GUID const CLSID_InfraSetupPage,10602>(a1);
}

```

## disassembly

```asm
0x180003514  push    rbx
0x180003516  sub     rsp, 20h
0x18000351a  mov     rbx, rcx
0x18000351d  add     rcx, 88h; this
0x180003524  call    ??1CDynamicStdCallThunk2@ATL@@QEAA@XZ; ATL::CDynamicStdCallThunk2::~CDynamicStdCallThunk2(void)
0x180003529  mov     rcx, rbx
0x18000352c  add     rsp, 20h
0x180003530  pop     rbx
0x180003531  jmp     ??1?$CXWizardPageBase@VCInfraSetupPage@@$1?CLSID_InfraSetupPage@@3U_GUID@@B$0CJGK@@@QEAA@XZ; CXWizardPageBase<CInfraSetupPage,&_GUID const CLSID_InfraSetupPage,10602>::~CXWizardPageBase<CInfraSetupPage,&_GUID const CLSID_InfraSetupPage,10602>(void)
```
