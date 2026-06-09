# ATL::CComObject<CWMPRichPreviewRemoteService>::~CComObject<CWMPRichPreviewRemoteService>(void)

- ea: `0x140002190`
- end: `0x140002231`
- name: `??1?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@QEAA@XZ`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1400039b0`
- `0x140007b20`

## callees

- `0x140002190`
- `0x14000c818`
- `0x14000d978`
- `0x14000f010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1400021dc`
- `KERNEL32!DeleteFileW` at `0x1400021dc`

## pseudocode

```c
void __fastcall ATL::CComObject<CWMPRichPreviewRemoteService>::~CComObject<CWMPRichPreviewRemoteService>(__int64 a1)
{
  unsigned __int16 **v1; // rdi
  WCHAR *v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  *(_DWORD *)(a1 + 24) = 1;
  *(_QWORD *)a1 = &ATL::CComObject<CWMPRichPreviewRemoteService>::`vftable'{for `ATL::IDispatchImpl<IWMPRichPreviewLauncher,&__s_GUID const _GUID_f826a914_4075_4672_8312_5f91cdf3c69e,&__s_GUID const _GUID_fa258721_cf24_45d7_a9cb_80047d7fec35,1,0,ATL::CComTypeInfoHolder>'};
  v1 = (unsigned __int16 **)(a1 + 56);
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<CWMPRichPreviewRemoteService>::`vftable'{for `ATL::IServiceProviderImpl<CWMPRichPreviewRemoteService>'};
  *(_QWORD *)(a1 + 16) = &ATL::CComObject<CWMPRichPreviewRemoteService>::`vftable'{for `IWMPRemoteMediaServices'};
  v3 = *(WCHAR **)(a1 + 56);
  if ( v3 && *v3 )
  {
    DeleteFileW(v3);
    WString::DeleteString(v1);
  }
  CExeModule::Unlock((CExeModule *)v3);
  WString::DeleteString(v1);
  v4 = *(_QWORD *)(a1 + 48);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *(_QWORD *)(a1 + 40);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
}

```

## disassembly

```asm
0x140002190  mov     [rsp+arg_0], rbx
0x140002195  mov     [rsp+arg_8], rsi
0x14000219a  push    rdi
0x14000219b  sub     rsp, 20h
0x14000219f  lea     rax, ??_7?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@6B?$IDispatchImpl@UIWMPRichPreviewLauncher@@$1?_GUID_f826a914_4075_4672_8312_5f91cdf3c69e@@3U__s_GUID@@B$1?_GUID_fa258721_cf24_45d7_a9cb_80047d7fec35@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CWMPRichPreviewRemoteService>::`vftable'{for `ATL::IDispatchImpl<IWMPRichPreviewLauncher,&__s_GUID const _GUID_f826a914_4075_4672_8312_5f91cdf3c69e,&__s_GUID const _GUID_fa258721_cf24_45d7_a9cb_80047d7fec35,1,0,ATL::CComTypeInfoHolder>'}
0x1400021a6  mov     dword ptr [rcx+18h], 1
0x1400021ad  mov     [rcx], rax
0x1400021b0  lea     rdi, [rcx+38h]
0x1400021b4  lea     rax, ??_7?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@6B?$IServiceProviderImpl@VCWMPRichPreviewRemoteService@@@1@@; const ATL::CComObject<CWMPRichPreviewRemoteService>::`vftable'{for `ATL::IServiceProviderImpl<CWMPRichPreviewRemoteService>'}
0x1400021bb  mov     rbx, rcx
0x1400021be  mov     [rcx+8], rax
0x1400021c2  xor     esi, esi
0x1400021c4  lea     rax, ??_7?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@6BIWMPRemoteMediaServices@@@; const ATL::CComObject<CWMPRichPreviewRemoteService>::`vftable'{for `IWMPRemoteMediaServices'}
0x1400021cb  mov     [rcx+10h], rax
0x1400021cf  mov     rcx, [rdi]; lpFileName
0x1400021d2  test    rcx, rcx
0x1400021d5  jz      short loc_1400021EA
0x1400021d7  cmp     [rcx], si
0x1400021da  jz      short loc_1400021EA
0x1400021dc  call    cs:__imp_DeleteFileW
0x1400021e2  mov     rcx, rdi; this
0x1400021e5  call    ?DeleteString@WString@@QEAAXXZ; WString::DeleteString(void)
0x1400021ea  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x1400021ef  mov     rcx, rdi; this
0x1400021f2  call    ?DeleteString@WString@@QEAAXXZ; WString::DeleteString(void)
0x1400021f7  mov     rcx, [rbx+30h]
0x1400021fb  test    rcx, rcx
0x1400021fe  jz      short loc_14000220C
0x140002200  mov     rax, [rcx]
0x140002203  mov     rax, [rax+10h]
0x140002207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000220c  mov     rcx, [rbx+28h]
0x140002210  test    rcx, rcx
0x140002213  jz      short loc_140002221
0x140002215  mov     rax, [rcx]
0x140002218  mov     rax, [rax+10h]
0x14000221c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002221  mov     rbx, [rsp+28h+arg_0]
0x140002226  mov     rsi, [rsp+28h+arg_8]
0x14000222b  add     rsp, 20h
0x14000222f  pop     rdi
0x140002230  retn
```
