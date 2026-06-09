# CEventUI::UploadUIThread(void)

- ea: `0x180008cd0`
- end: `0x180008df5`
- name: `?UploadUIThread@CEventUI@@AEAAXXZ`
- size: `293`
- prototype: `void __fastcall(CEventUI *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007cc0`

## callees

- `0x180003604`
- `0x180005c80`
- `0x180006440`
- `0x180008cd0`
- `0x180009580`
- `0x180016c1e`

## import_xrefs

- `COMCTL32!TaskDialogIndirect` at `0x180008da0`
- `COMCTL32!TaskDialogIndirect` at `0x180008da0`

## pseudocode

```c
void __fastcall CEventUI::UploadUIThread(CEventUI *this)
{
  __int64 v2; // rax
  HRESULT v3; // eax
  int v4; // [rsp+20h] [rbp-79h] BYREF
  __int64 v5; // [rsp+24h] [rbp-75h]
  _QWORD v6[4]; // [rsp+30h] [rbp-69h] BYREF
  TASKDIALOGCONFIG pTaskConfig; // [rsp+50h] [rbp-49h] BYREF
  int pnButton; // [rsp+100h] [rbp+67h] BYREF

  memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
  pnButton = 0;
  v5 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v6);
  CEventUI::GetDiagosingHeaderText(this, v6);
  v4 = 1112;
  pTaskConfig.hInstance = &_ImageBase;
  pTaskConfig.pszMainInstruction = (PCWSTR)v6[0];
  v2 = *((_QWORD *)this + 3);
  v5 = 283;
  pTaskConfig.pszWindowTitle = (PCWSTR)(v2 + 400);
  pTaskConfig.pButtons = (const TASKDIALOG_BUTTON *)&v4;
  pTaskConfig.pfCallback = (PFTASKDIALOGCALLBACK)CEventUI::Static_UploadDlgProc;
  pTaskConfig.cbSize = 160;
  pTaskConfig.hwndParent = 0;
  pTaskConfig.pszContent = (PCWSTR)3016;
  pTaskConfig.cButtons = 1;
  pTaskConfig.dwFlags = 33288;
  pTaskConfig.lpCallbackData = (LONG_PTR)this;
  pTaskConfig.cxWidth = 0;
  v3 = TaskDialogIndirect(&pTaskConfig, &pnButton, 0, 0);
  if ( v3 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      45,
      &WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids,
      (unsigned int)v3);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v6);
}

```

## disassembly

```asm
0x180008cd0  mov     [rsp-8+arg_8], rbx
0x180008cd5  push    rbp
0x180008cd6  lea     rbp, [rsp-57h]
0x180008cdb  sub     rsp, 0F0h
0x180008ce2  mov     rbx, rcx
0x180008ce5  xor     edx, edx; Val
0x180008ce7  lea     rcx, [rbp+57h+pTaskConfig]; void *
0x180008ceb  mov     r8d, 0A0h; Size
0x180008cf1  call    memset_0
0x180008cf6  xor     eax, eax
0x180008cf8  mov     [rbp+57h+pnButton], 0
0x180008cff  lea     rcx, [rbp+57h+var_C0]; void *
0x180008d03  mov     [rbp+57h+var_CC], rax
0x180008d07  mov     [rbp+57h+var_D0], 0
0x180008d0e  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x180008d13  lea     rdx, [rbp+57h+var_C0]
0x180008d17  mov     rcx, rbx
0x180008d1a  call    ?GetDiagosingHeaderText@CEventUI@@AEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; CEventUI::GetDiagosingHeaderText(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180008d1f  lea     rax, __ImageBase
0x180008d26  mov     [rbp+57h+var_D0], 458h
0x180008d2d  mov     [rbp+57h+pTaskConfig.hInstance], rax
0x180008d31  lea     rdx, [rbp+57h+pnButton]; pnButton
0x180008d35  mov     rax, [rbp+57h+var_C0]
0x180008d39  lea     rcx, [rbp+57h+pTaskConfig]; pTaskConfig
0x180008d3d  mov     [rbp+57h+pTaskConfig.pszMainInstruction], rax
0x180008d41  xor     r9d, r9d; pfVerificationFlagChecked
0x180008d44  mov     rax, [rbx+18h]
0x180008d48  xor     r8d, r8d; pnRadioButton
0x180008d4b  add     rax, 190h
0x180008d51  mov     [rbp+57h+var_CC], 11Bh
0x180008d59  mov     [rbp+57h+pTaskConfig.pszWindowTitle], rax
0x180008d5d  lea     rax, [rbp+57h+var_D0]
0x180008d61  mov     [rbp+57h+pTaskConfig.pButtons], rax
0x180008d65  lea     rax, ?Static_UploadDlgProc@CEventUI@@CAJPEAUHWND__@@I_K_J2@Z; CEventUI::Static_UploadDlgProc(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x180008d6c  mov     [rbp+57h+pTaskConfig.pfCallback], rax
0x180008d70  mov     [rbp+57h+pTaskConfig.cbSize], 0A0h
0x180008d77  mov     [rbp+57h+pTaskConfig.hwndParent], 0
0x180008d7f  mov     [rbp+57h+pTaskConfig.pszContent], 0BC8h
0x180008d87  mov     [rbp+57h+pTaskConfig.cButtons], 1
0x180008d8e  mov     [rbp+57h+pTaskConfig.dwFlags], 8208h
0x180008d95  mov     [rbp+57h+pTaskConfig.lpCallbackData], rbx
0x180008d99  mov     [rbp+57h+pTaskConfig.cxWidth], 0
0x180008da0  call    cs:__imp_TaskDialogIndirect
0x180008da6  test    eax, eax
0x180008da8  jns     short loc_180008DDB
0x180008daa  mov     rcx, cs:WPP_GLOBAL_Control
0x180008db1  lea     rdx, WPP_GLOBAL_Control
0x180008db8  cmp     rcx, rdx
0x180008dbb  jz      short loc_180008DDB
0x180008dbd  test    byte ptr [rcx+1Ch], 1
0x180008dc1  jz      short loc_180008DDB
0x180008dc3  mov     rcx, [rcx+10h]
0x180008dc7  lea     r8, WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids
0x180008dce  mov     edx, 2Dh ; '-'
0x180008dd3  mov     r9d, eax
0x180008dd6  call    WPP_SF_d
0x180008ddb  lea     rcx, [rbp+57h+var_C0]
0x180008ddf  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180008de4  mov     rbx, [rsp+0F0h+arg_8]
0x180008dec  add     rsp, 0F0h
0x180008df3  pop     rbp
0x180008df4  retn
```
