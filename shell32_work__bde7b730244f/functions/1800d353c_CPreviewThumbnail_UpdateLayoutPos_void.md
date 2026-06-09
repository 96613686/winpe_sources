# CPreviewThumbnail::_UpdateLayoutPos(void)

- ea: `0x1800d353c`
- end: `0x1800d36c5`
- name: `?_UpdateLayoutPos@CPreviewThumbnail@@AEAAJXZ`
- size: `393`
- prototype: `__int64 __fastcall(CPreviewThumbnail *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d28f0`
- `0x180109de0`

## callees

- `0x1800d353c`
- `0x1800d3df4`
- `0x1800d3e3c`
- `0x1800d4390`
- `0x180233280`
- `0x180571010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800d357a`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800d357a`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800d35a9`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800d35a9`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800d35bb`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800d35bb`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800d35e6`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800d3680`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800d36a7`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800d35e6`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800d3680`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800d36a7`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x1800d35f6`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x1800d3606`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x1800d35f6`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x1800d3606`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800d359d`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800d359d`
- `DUI70!?HeightProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800d35ec`
- `DUI70!?HeightProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800d3699`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x1800d3693`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x1800d3693`
- `DUI70!?SetHeight@Element@DirectUI@@QEAAJH@Z` at `0x1800d36ba`
- `DUI70!?SetHeight@Element@DirectUI@@QEAAJH@Z` at `0x1800d36ba`
- `DUI70!?WidthProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800d35fc`
- `PROPSYS!PSPropertyBag_ReadBOOL` at `0x1800d3653`
- `PROPSYS!PSPropertyBag_ReadBOOL` at `0x1800d3653`

## pseudocode

```c
__int64 __fastcall CPreviewThumbnail::_UpdateLayoutPos(IUnknown **this)
{
  HRESULT v2; // esi
  BOOL v3; // edi
  DirectUI::Value *v4; // rbp
  const WCHAR *String; // rax
  int MaxThumbSize; // ebp
  int FixedThumbSize; // eax
  int v8; // edx
  DirectUI::Element *v9; // rcx
  const struct DirectUI::PropertyInfo *(*v10)(void); // rdx
  int v12; // eax
  int v13; // eax
  void *ppvOut; // [rsp+20h] [rbp-48h] BYREF
  BOOL value; // [rsp+28h] [rbp-40h] BYREF

  ppvOut = 0;
  v2 = IUnknown_QueryService(
         this[27],
         (const GUID *const)&SID_PerLayoutPropertyBag,
         &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
         &ppvOut);
  if ( v2 >= 0 )
  {
    v3 = 0;
    v4 = DirectUI::Element::GetValue((DirectUI::Element *)this, CPreviewThumbnail::HidePropertyProp, 2, 0);
    String = DirectUI::Value::GetString(v4);
    if ( String )
    {
      value = 0;
      if ( PSPropertyBag_ReadBOOL((IPropertyBag *)ppvOut, String, &value) >= 0 )
        v3 = value;
    }
    DirectUI::Value::Release(v4);
    MaxThumbSize = CPreviewThumbnail::GetMaxThumbSize((CPreviewThumbnail *)this);
    FixedThumbSize = CPreviewThumbnail::GetFixedThumbSize((CPreviewThumbnail *)this);
    if ( v3 )
    {
      v8 = -3;
    }
    else
    {
      if ( FixedThumbSize == -1 )
      {
        v9 = (DirectUI::Element *)this;
        if ( MaxThumbSize != -1 )
        {
          if ( CPreviewThumbnail::GetVertical((CPreviewThumbnail *)this) )
          {
            DirectUI::Element::SetLayoutPos((DirectUI::Element *)this, 1);
            v12 = CPreviewThumbnail::GetMaxThumbSize((CPreviewThumbnail *)this);
            DirectUI::Element::SetWidth((DirectUI::Element *)this, v12);
            v10 = (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::HeightProp;
            goto LABEL_9;
          }
          DirectUI::Element::SetLayoutPos((DirectUI::Element *)this, 0);
          v13 = CPreviewThumbnail::GetMaxThumbSize((CPreviewThumbnail *)this);
          DirectUI::Element::SetHeight((DirectUI::Element *)this, v13);
LABEL_8:
          v10 = (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::WidthProp;
LABEL_9:
          DirectUI::Element::RemoveLocalValue((DirectUI::Element *)this, v10);
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
          return (unsigned int)v2;
        }
        v8 = 4;
LABEL_7:
        DirectUI::Element::SetLayoutPos(v9, v8);
        DirectUI::Element::RemoveLocalValue(
          (DirectUI::Element *)this,
          (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::HeightProp);
        goto LABEL_8;
      }
      v8 = 1;
    }
    v9 = (DirectUI::Element *)this;
    goto LABEL_7;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800d353c  push    rbx
0x1800d353e  push    rbp
0x1800d353f  push    rsi
0x1800d3540  push    rdi
0x1800d3541  sub     rsp, 48h
0x1800d3545  mov     rax, cs:__security_cookie
0x1800d354c  xor     rax, rsp
0x1800d354f  mov     [rsp+68h+var_38], rax
0x1800d3554  mov     rbx, rcx
0x1800d3557  mov     [rsp+68h+ppvOut], 0
0x1800d3560  mov     rcx, [rcx+0D8h]; punk
0x1800d3567  lea     r9, [rsp+68h+ppvOut]; ppvOut
0x1800d356c  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x1800d3573  lea     rdx, SID_PerLayoutPropertyBag; guidService
0x1800d357a  call    cs:__imp_IUnknown_QueryService
0x1800d3580  mov     esi, eax
0x1800d3582  test    eax, eax
0x1800d3584  js      loc_1800D361D
0x1800d358a  xor     edi, edi
0x1800d358c  lea     rdx, ?HidePropertyProp@CPreviewThumbnail@@SAPEBUPropertyInfo@DirectUI@@XZ; CPreviewThumbnail::HidePropertyProp(void)
0x1800d3593  xor     r9d, r9d
0x1800d3596  mov     rcx, rbx
0x1800d3599  lea     r8d, [rdi+2]
0x1800d359d  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800d35a3  mov     rcx, rax
0x1800d35a6  mov     rbp, rax
0x1800d35a9  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x1800d35af  test    rax, rax
0x1800d35b2  jnz     loc_1800D3642
0x1800d35b8  mov     rcx, rbp
0x1800d35bb  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800d35c1  mov     rcx, rbx; this
0x1800d35c4  call    ?GetMaxThumbSize@CPreviewThumbnail@@QEAAHXZ; CPreviewThumbnail::GetMaxThumbSize(void)
0x1800d35c9  mov     rcx, rbx; this
0x1800d35cc  mov     ebp, eax
0x1800d35ce  call    ?GetFixedThumbSize@CPreviewThumbnail@@QEAAHXZ; CPreviewThumbnail::GetFixedThumbSize(void)
0x1800d35d3  test    edi, edi
0x1800d35d5  jnz     loc_1800D3665
0x1800d35db  cmp     eax, 0FFFFFFFFh
0x1800d35de  jz      short loc_1800D3635
0x1800d35e0  lea     edx, [rdi+1]
0x1800d35e3  mov     rcx, rbx
0x1800d35e6  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x1800d35ec  mov     rdx, cs:__imp_?HeightProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::HeightProp(void)
0x1800d35f3  mov     rcx, rbx
0x1800d35f6  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x1800d35fc  mov     rdx, cs:__imp_?WidthProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::WidthProp(void)
0x1800d3603  mov     rcx, rbx
0x1800d3606  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x1800d360c  mov     rcx, [rsp+68h+ppvOut]
0x1800d3611  mov     rax, [rcx]
0x1800d3614  mov     rax, [rax+10h]
0x1800d3618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d361d  mov     eax, esi
0x1800d361f  mov     rcx, [rsp+68h+var_38]
0x1800d3624  xor     rcx, rsp; StackCookie
0x1800d3627  call    __security_check_cookie
0x1800d362c  add     rsp, 48h
0x1800d3630  pop     rdi
0x1800d3631  pop     rsi
0x1800d3632  pop     rbp
0x1800d3633  pop     rbx
0x1800d3634  retn
0x1800d3635  mov     rcx, rbx; this
0x1800d3638  cmp     ebp, 0FFFFFFFFh
0x1800d363b  jnz     short loc_1800D366F
0x1800d363d  lea     edx, [rbp+5]
0x1800d3640  jmp     short loc_1800D35E6
0x1800d3642  mov     rcx, [rsp+68h+ppvOut]; propBag
0x1800d3647  lea     r8, [rsp+68h+value]; value
0x1800d364c  mov     rdx, rax; propName
0x1800d364f  mov     [rsp+68h+value], edi
0x1800d3653  call    cs:__imp_PSPropertyBag_ReadBOOL
0x1800d3659  test    eax, eax
0x1800d365b  cmovns  edi, [rsp+68h+value]
0x1800d3660  jmp     loc_1800D35B8
0x1800d3665  mov     edx, 0FFFFFFFDh
0x1800d366a  jmp     loc_1800D35E3
0x1800d366f  call    ?GetVertical@CPreviewThumbnail@@QEAA_NXZ; CPreviewThumbnail::GetVertical(void)
0x1800d3674  mov     rcx, rbx
0x1800d3677  test    al, al
0x1800d3679  jz      short loc_1800D36A5
0x1800d367b  mov     edx, 1
0x1800d3680  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x1800d3686  mov     rcx, rbx; this
0x1800d3689  call    ?GetMaxThumbSize@CPreviewThumbnail@@QEAAHXZ; CPreviewThumbnail::GetMaxThumbSize(void)
0x1800d368e  mov     edx, eax
0x1800d3690  mov     rcx, rbx
0x1800d3693  call    cs:__imp_?SetWidth@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetWidth(int)
0x1800d3699  mov     rdx, cs:__imp_?HeightProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::HeightProp(void)
0x1800d36a0  jmp     loc_1800D3603
0x1800d36a5  xor     edx, edx
0x1800d36a7  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x1800d36ad  mov     rcx, rbx; this
0x1800d36b0  call    ?GetMaxThumbSize@CPreviewThumbnail@@QEAAHXZ; CPreviewThumbnail::GetMaxThumbSize(void)
0x1800d36b5  mov     edx, eax
0x1800d36b7  mov     rcx, rbx
0x1800d36ba  call    cs:__imp_?SetHeight@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetHeight(int)
0x1800d36c0  jmp     loc_1800D35FC
```
