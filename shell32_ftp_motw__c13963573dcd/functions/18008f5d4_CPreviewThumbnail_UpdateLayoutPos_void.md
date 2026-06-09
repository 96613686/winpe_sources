# CPreviewThumbnail::_UpdateLayoutPos(void)

- ea: `0x18008f5d4`
- end: `0x18008f7a6`
- name: `?_UpdateLayoutPos@CPreviewThumbnail@@AEAAJXZ`
- size: `466`
- prototype: `__int64 __fastcall(CPreviewThumbnail *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800913d0`
- `0x180117a50`

## callees

- `0x18008f5d4`
- `0x18008ff80`
- `0x18008ffdc`
- `0x18009059c`
- `0x180249490`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18008f612`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18008f612`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18008f64d`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18008f64d`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18008f665`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18008f665`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18008f696`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18008f749`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18008f77c`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18008f696`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18008f749`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18008f77c`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x18008f6ac`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x18008f6c2`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x18008f6ac`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x18008f6c2`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18008f63b`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18008f63b`
- `DUI70!?HeightProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18008f6a2`
- `DUI70!?HeightProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18008f76e`
- `DUI70!?WidthProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18008f6b8`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x18008f762`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x18008f762`
- `DUI70!?SetHeight@Element@DirectUI@@QEAAJH@Z` at `0x18008f795`
- `DUI70!?SetHeight@Element@DirectUI@@QEAAJH@Z` at `0x18008f795`
- `PROPSYS!PSPropertyBag_ReadBOOL` at `0x18008f716`
- `PROPSYS!PSPropertyBag_ReadBOOL` at `0x18008f716`

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
0x18008f5d4  push    rbx
0x18008f5d6  push    rbp
0x18008f5d7  push    rsi
0x18008f5d8  push    rdi
0x18008f5d9  sub     rsp, 48h
0x18008f5dd  mov     rax, cs:__security_cookie
0x18008f5e4  xor     rax, rsp
0x18008f5e7  mov     [rsp+68h+var_38], rax
0x18008f5ec  mov     rbx, rcx
0x18008f5ef  mov     [rsp+68h+ppvOut], 0
0x18008f5f8  mov     rcx, [rcx+0D8h]; punk
0x18008f5ff  lea     r9, [rsp+68h+ppvOut]; ppvOut
0x18008f604  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18008f60b  lea     rdx, SID_PerLayoutPropertyBag; guidService
0x18008f612  call    cs:__imp_IUnknown_QueryService
0x18008f619  nop     dword ptr [rax+rax+00h]
0x18008f61e  mov     esi, eax
0x18008f620  test    eax, eax
0x18008f622  js      loc_18008F6DF
0x18008f628  xor     edi, edi
0x18008f62a  lea     rdx, ?HidePropertyProp@CPreviewThumbnail@@SAPEBUPropertyInfo@DirectUI@@XZ; CPreviewThumbnail::HidePropertyProp(void)
0x18008f631  xor     r9d, r9d
0x18008f634  mov     rcx, rbx
0x18008f637  lea     r8d, [rdi+2]
0x18008f63b  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18008f642  nop     dword ptr [rax+rax+00h]
0x18008f647  mov     rcx, rax
0x18008f64a  mov     rbp, rax
0x18008f64d  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18008f654  nop     dword ptr [rax+rax+00h]
0x18008f659  test    rax, rax
0x18008f65c  jnz     loc_18008F705
0x18008f662  mov     rcx, rbp
0x18008f665  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18008f66c  nop     dword ptr [rax+rax+00h]
0x18008f671  mov     rcx, rbx; this
0x18008f674  call    ?GetMaxThumbSize@CPreviewThumbnail@@QEAAHXZ; CPreviewThumbnail::GetMaxThumbSize(void)
0x18008f679  mov     rcx, rbx; this
0x18008f67c  mov     ebp, eax
0x18008f67e  call    ?GetFixedThumbSize@CPreviewThumbnail@@QEAAHXZ; CPreviewThumbnail::GetFixedThumbSize(void)
0x18008f683  test    edi, edi
0x18008f685  jnz     loc_18008F72E
0x18008f68b  cmp     eax, 0FFFFFFFFh
0x18008f68e  jz      short loc_18008F6F8
0x18008f690  lea     edx, [rdi+1]
0x18008f693  mov     rcx, rbx
0x18008f696  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18008f69d  nop     dword ptr [rax+rax+00h]
0x18008f6a2  mov     rdx, cs:__imp_?HeightProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::HeightProp(void)
0x18008f6a9  mov     rcx, rbx
0x18008f6ac  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x18008f6b3  nop     dword ptr [rax+rax+00h]
0x18008f6b8  mov     rdx, cs:__imp_?WidthProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::WidthProp(void)
0x18008f6bf  mov     rcx, rbx
0x18008f6c2  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x18008f6c9  nop     dword ptr [rax+rax+00h]
0x18008f6ce  mov     rcx, [rsp+68h+ppvOut]
0x18008f6d3  mov     rax, [rcx]
0x18008f6d6  mov     rax, [rax+10h]
0x18008f6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f6df  mov     eax, esi
0x18008f6e1  mov     rcx, [rsp+68h+var_38]
0x18008f6e6  xor     rcx, rsp; StackCookie
0x18008f6e9  call    __security_check_cookie
0x18008f6ee  add     rsp, 48h
0x18008f6f2  pop     rdi
0x18008f6f3  pop     rsi
0x18008f6f4  pop     rbp
0x18008f6f5  pop     rbx
0x18008f6f6  retn
0x18008f6f8  mov     rcx, rbx; this
0x18008f6fb  cmp     ebp, 0FFFFFFFFh
0x18008f6fe  jnz     short loc_18008F738
0x18008f700  lea     edx, [rbp+5]
0x18008f703  jmp     short loc_18008F696
0x18008f705  mov     rcx, [rsp+68h+ppvOut]; propBag
0x18008f70a  lea     r8, [rsp+68h+value]; value
0x18008f70f  mov     rdx, rax; propName
0x18008f712  mov     [rsp+68h+value], edi
0x18008f716  call    cs:__imp_PSPropertyBag_ReadBOOL
0x18008f71d  nop     dword ptr [rax+rax+00h]
0x18008f722  test    eax, eax
0x18008f724  cmovns  edi, [rsp+68h+value]
0x18008f729  jmp     loc_18008F662
0x18008f72e  mov     edx, 0FFFFFFFDh
0x18008f733  jmp     loc_18008F693
0x18008f738  call    ?GetVertical@CPreviewThumbnail@@QEAA_NXZ; CPreviewThumbnail::GetVertical(void)
0x18008f73d  mov     rcx, rbx
0x18008f740  test    al, al
0x18008f742  jz      short loc_18008F77A
0x18008f744  mov     edx, 1
0x18008f749  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18008f750  nop     dword ptr [rax+rax+00h]
0x18008f755  mov     rcx, rbx; this
0x18008f758  call    ?GetMaxThumbSize@CPreviewThumbnail@@QEAAHXZ; CPreviewThumbnail::GetMaxThumbSize(void)
0x18008f75d  mov     edx, eax
0x18008f75f  mov     rcx, rbx
0x18008f762  call    cs:__imp_?SetWidth@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetWidth(int)
0x18008f769  nop     dword ptr [rax+rax+00h]
0x18008f76e  mov     rdx, cs:__imp_?HeightProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::HeightProp(void)
0x18008f775  jmp     loc_18008F6BF
0x18008f77a  xor     edx, edx
0x18008f77c  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18008f783  nop     dword ptr [rax+rax+00h]
0x18008f788  mov     rcx, rbx; this
0x18008f78b  call    ?GetMaxThumbSize@CPreviewThumbnail@@QEAAHXZ; CPreviewThumbnail::GetMaxThumbSize(void)
0x18008f790  mov     edx, eax
0x18008f792  mov     rcx, rbx
0x18008f795  call    cs:__imp_?SetHeight@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetHeight(int)
0x18008f79c  nop     dword ptr [rax+rax+00h]
0x18008f7a1  jmp     loc_18008F6B8
```
