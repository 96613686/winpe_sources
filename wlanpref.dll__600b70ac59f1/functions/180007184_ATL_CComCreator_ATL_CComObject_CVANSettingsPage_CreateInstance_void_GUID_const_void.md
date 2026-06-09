# ATL::CComCreator<ATL::CComObject<CVANSettingsPage>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180007184`
- end: `0x180007281`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCVANSettingsPage@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005a00`

## callees

- `0x18000130c`
- `0x180002bf0`
- `0x180007184`
- `0x1800080a0`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CVANSettingsPage>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  CVANSettingsPage *v7; // rax
  CVANSettingsPage *v8; // rbx
  int v9; // eax
  int v10; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CVANSettingsPage *)operator new(0x118u);
  v8 = v7;
  if ( v7 )
  {
    CVANSettingsPage::CVANSettingsPage(v7);
    *(_QWORD *)v8 = &ATL::CComObject<CVANSettingsPage>::`vftable'{for `CXWizardPageBase<CVANSettingsPage,&_GUID const CLSID_VANSettingsPage,10608>'};
    *((_QWORD *)v8 + 12) = &ATL::CComObject<CVANSettingsPage>::`vftable'{for `WTL::CPropertyPageImpl<CVANSettingsPage,WTL::CPropertyPageWindow>'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  if ( v8 )
  {
    v9 = ATL::CComSafeDeleteCriticalSection::Init((CVANSettingsPage *)((char *)v8 + 16));
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CVANSettingsPage *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*((_QWORD *)v8 + 12) + 8LL))((_QWORD *)v8 + 12, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180007184  mov     [rsp+arg_10], r8
0x180007189  mov     [rsp+arg_8], rdx
0x18000718e  mov     [rsp+arg_0], rcx
0x180007193  push    rbx
0x180007194  push    rsi
0x180007195  push    rdi
0x180007196  push    r14
0x180007198  sub     rsp, 28h
0x18000719c  mov     rsi, r8
0x18000719f  mov     r14, rdx
0x1800071a2  test    r8, r8
0x1800071a5  jnz     short loc_1800071B1
0x1800071a7  mov     eax, 80004003h
0x1800071ac  jmp     loc_180007277
0x1800071b1  mov     qword ptr [r8], 0
0x1800071b8  mov     edi, 8007000Eh
0x1800071bd  mov     dword ptr [rsp+48h+arg_0], edi
0x1800071c1  mov     [rsp+48h+arg_18], 0
0x1800071ca  mov     ecx, 118h; Size
0x1800071cf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800071d4  mov     rbx, rax
0x1800071d7  test    rbx, rbx
0x1800071da  jz      short loc_18000720C
0x1800071dc  mov     rcx, rax; this
0x1800071df  call    ??0CVANSettingsPage@@QEAA@XZ; CVANSettingsPage::CVANSettingsPage(void)
0x1800071e4  lea     rax, ??_7?$CComObject@VCVANSettingsPage@@@ATL@@6B?$CXWizardPageBase@VCVANSettingsPage@@$1?CLSID_VANSettingsPage@@3U_GUID@@B$0CJHA@@@@; const ATL::CComObject<CVANSettingsPage>::`vftable'{for `CXWizardPageBase<CVANSettingsPage,&_GUID const CLSID_VANSettingsPage,10608>'}
0x1800071eb  mov     [rbx], rax
0x1800071ee  lea     rax, ??_7?$CComObject@VCVANSettingsPage@@@ATL@@6B?$CPropertyPageImpl@VCVANSettingsPage@@VCPropertyPageWindow@WTL@@@WTL@@@; const ATL::CComObject<CVANSettingsPage>::`vftable'{for `WTL::CPropertyPageImpl<CVANSettingsPage,WTL::CPropertyPageWindow>'}
0x1800071f5  mov     [rbx+60h], rax
0x1800071f9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007200  mov     rax, [rcx]
0x180007203  mov     rax, [rax+8]
0x180007207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000720c  mov     [rsp+48h+arg_18], rbx
0x180007211  jmp     short loc_180007226
0x180007213  mov     rsi, [rsp+48h+arg_10]
0x180007218  mov     r14, [rsp+48h+arg_8]
0x18000721d  mov     edi, dword ptr [rsp+48h+arg_0]
0x180007221  mov     rbx, [rsp+48h+arg_18]
0x180007226  test    rbx, rbx
0x180007229  jz      short loc_180007275
0x18000722b  lea     rcx, [rbx+10h]; this
0x18000722f  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180007234  xor     ecx, ecx
0x180007236  test    eax, eax
0x180007238  cmovs   ecx, eax
0x18000723b  xor     edi, edi
0x18000723d  test    ecx, ecx
0x18000723f  cmovs   edi, ecx
0x180007242  test    edi, edi
0x180007244  jnz     short loc_180007260
0x180007246  mov     rax, [rbx]
0x180007249  mov     r8, rsi
0x18000724c  mov     rdx, r14
0x18000724f  mov     rcx, rbx
0x180007252  mov     rax, [rax]
0x180007255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000725a  mov     edi, eax
0x18000725c  test    eax, eax
0x18000725e  jz      short loc_180007275
0x180007260  lea     rcx, [rbx+60h]
0x180007264  mov     rdx, [rcx]
0x180007267  mov     rax, [rdx+8]
0x18000726b  mov     edx, 1
0x180007270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007275  mov     eax, edi
0x180007277  add     rsp, 28h
0x18000727b  pop     r14
0x18000727d  pop     rdi
0x18000727e  pop     rsi
0x18000727f  pop     rbx
0x180007280  retn
```
