# CWebWizardPage::OnSetActive(void)

- ea: `0x18003da40`
- end: `0x18003dc5a`
- name: `?OnSetActive@CWebWizardPage@@UEAAJXZ`
- size: `538`
- prototype: `__int64 __fastcall(CWebWizardPage *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000d9a4`
- `0x18003d010`
- `0x18003da40`
- `0x18003df18`
- `0x18003e03c`
- `0x18003e7c4`
- `0x180074f14`
- `0x18007510c`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dbc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dbc7`
- `OLEAUT32!__imp_SysAllocString` at `0x18003db07`
- `OLEAUT32!__imp_SysAllocString` at `0x18003db07`
- `OLEAUT32!__imp_VariantClear` at `0x18003db41`
- `OLEAUT32!__imp_VariantClear` at `0x18003db41`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003db8b`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003db97`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003dc20`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003dc2e`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003db8b`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003db97`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003dc20`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003dc2e`

## pseudocode

```c
__int64 __fastcall CWebWizardPage::OnSetActive(CWebWizardPage *this)
{
  DirectUI::Element **v1; // rsi
  int WebWizardControl; // ebx
  struct DirectUI::Element *Element; // rax
  DirectUI::Element *v5; // r14
  __int64 v6; // rcx
  const OLECHAR *v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rcx
  DirectUI::Element *v11; // rcx
  __int64 v12; // rdx
  DirectUI::Element *v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // r8
  VARIANTARG pvarg; // [rsp+30h] [rbp-30h] BYREF
  OLECHAR *psz[2]; // [rsp+48h] [rbp-18h] BYREF

  v1 = (DirectUI::Element **)((char *)this - 8);
  WebWizardControl = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 1) + 112LL))((char *)this - 8);
  if ( WebWizardControl < 0 )
    return (unsigned int)WebWizardControl;
  *((_WORD *)this + 64) = 0;
  Element = CBaseTaskFlowPage::_FindElement((CBaseTaskFlowPage *)v1, L"idWebErrorMsg");
  v5 = (DirectUI::Element *)element_cast<DirectUI::RichText>(Element);
  WebWizardControl = CWebWizardPage::_CreateWebWizardControl((CWebWizardPage *)v1);
  if ( WebWizardControl < 0 )
    goto LABEL_13;
  *((_BYTE *)this + 130) = 0;
  v6 = *((_QWORD *)this + 13);
  psz[0] = 0;
  if ( (*(int (__fastcall **)(__int64, OLECHAR **))(*(_QWORD *)v6 + 40LL))(v6, psz) >= 0 )
  {
    v7 = &Class;
    pvarg.vt = 8;
    memset(&pvarg.decVal.scale, 0, 22);
    if ( psz[0] )
      v7 = psz[0];
    pvarg.llVal = (LONGLONG)SysAllocString(v7);
    if ( pvarg.llVal )
    {
      v8 = *(_QWORD *)(*((_QWORD *)this + 14) + 376LL);
      if ( v8 )
        (*(void (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v8 + 32LL))(v8, L"Username", &pvarg);
      VariantClear(&pvarg);
    }
    CoTaskMemFree(psz[0]);
  }
  v9 = *((_QWORD *)this + 14);
  v10 = *(_QWORD *)(v9 + 376);
  if ( v10 )
  {
    WebWizardControl = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 88LL))(v10);
    if ( WebWizardControl < 0 )
    {
LABEL_13:
      v11 = v1[15];
      *((_BYTE *)v1 + 138) = 1;
      DirectUI::Element::SetLayoutPos(v11, -3);
      DirectUI::Element::SetLayoutPos(v5, -1);
      psz[0] = 0;
      if ( (int)CWebWizardPage::_GenerateErrorString((CWebWizardPage *)v1, WebWizardControl, psz) >= 0 )
      {
        SetElementContentStringAndAccName(v5, psz[0]);
        CoTaskMemFree(psz[0]);
      }
      CWebWizardPage::_SetWizardButtons((CWebWizardPage *)v1, v12, 0, 0);
      WebWizardControl = 0;
      *((_BYTE *)v1 + 137) = 1;
      return (unsigned int)WebWizardControl;
    }
  }
  else
  {
    *(_BYTE *)(v9 + 360) = 1;
    WebWizardControl = 0;
  }
  v14 = (DirectUI::Element *)*((_QWORD *)this + 14);
  *((_BYTE *)this + 130) = 0;
  DirectUI::Element::SetLayoutPos(v14, 1);
  DirectUI::Element::SetLayoutPos(v5, -3);
  if ( (Microsoft_Windows_User_ControlPanelEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v15, UserAccount_Taskflow_WebWizardPage_Active, v16, 1, psz);
  return (unsigned int)WebWizardControl;
}

```

## disassembly

```asm
0x18003da40  mov     [rsp-18h+arg_8], rbx
0x18003da45  mov     [rsp-18h+arg_10], rsi
0x18003da4a  push    rbp
0x18003da4b  push    rdi
0x18003da4c  push    r14
0x18003da4e  mov     rbp, rsp
0x18003da51  sub     rsp, 60h
0x18003da55  mov     rax, cs:__security_cookie
0x18003da5c  xor     rax, rsp
0x18003da5f  mov     [rbp+var_8], rax
0x18003da63  lea     rsi, [rcx-8]
0x18003da67  mov     rdi, rcx
0x18003da6a  mov     rax, [rsi]
0x18003da6d  mov     rcx, rsi
0x18003da70  mov     rax, [rax+70h]
0x18003da74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da79  mov     ebx, eax
0x18003da7b  test    eax, eax
0x18003da7d  js      loc_18003DBE4
0x18003da83  lea     rdx, aIdweberrormsg; "idWebErrorMsg"
0x18003da8a  mov     word ptr [rdi+80h], 0
0x18003da93  mov     rcx, rsi; this
0x18003da96  call    ?_FindElement@CBaseTaskFlowPage@@IEAAPEAVElement@DirectUI@@PEBG@Z; CBaseTaskFlowPage::_FindElement(ushort const *)
0x18003da9b  mov     rcx, rax
0x18003da9e  call    ??$element_cast@VRichText@DirectUI@@@@YAPEAVRichText@DirectUI@@PEAVElement@1@@Z; element_cast<DirectUI::RichText>(DirectUI::Element *)
0x18003daa3  mov     rcx, rsi; this
0x18003daa6  mov     r14, rax
0x18003daa9  call    ?_CreateWebWizardControl@CWebWizardPage@@AEAAJXZ; CWebWizardPage::_CreateWebWizardControl(void)
0x18003daae  mov     ebx, eax
0x18003dab0  test    eax, eax
0x18003dab2  js      loc_18003DB7B
0x18003dab8  mov     byte ptr [rdi+82h], 0
0x18003dabf  mov     rcx, [rdi+68h]
0x18003dac3  mov     [rbp+psz], 0
0x18003dacb  mov     rdx, [rcx]
0x18003dace  mov     rax, [rdx+28h]
0x18003dad2  lea     rdx, [rbp+psz]
0x18003dad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dadb  test    eax, eax
0x18003dadd  js      short loc_18003DB51
0x18003dadf  mov     eax, 8
0x18003dae4  lea     rcx, Class
0x18003daeb  mov     word ptr [rbp+pvarg], ax
0x18003daef  xorps   xmm0, xmm0
0x18003daf2  xor     eax, eax
0x18003daf4  movups  xmmword ptr [rbp+pvarg+2], xmm0
0x18003daf8  mov     qword ptr [rbp+pvarg+10h], rax
0x18003dafc  mov     rax, [rbp+psz]
0x18003db00  test    rax, rax
0x18003db03  cmovnz  rcx, rax; psz
0x18003db07  call    cs:__imp_SysAllocString
0x18003db0d  mov     qword ptr [rbp+pvarg+8], rax
0x18003db11  test    rax, rax
0x18003db14  jz      short loc_18003DB47
0x18003db16  mov     rax, [rdi+70h]
0x18003db1a  mov     rcx, [rax+178h]
0x18003db21  test    rcx, rcx
0x18003db24  jz      short loc_18003DB3D
0x18003db26  mov     rax, [rcx]
0x18003db29  lea     r8, [rbp+pvarg]
0x18003db2d  lea     rdx, aUsername_0; "Username"
0x18003db34  mov     rax, [rax+20h]
0x18003db38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db3d  lea     rcx, [rbp+pvarg]; pvarg
0x18003db41  call    cs:__imp_VariantClear
0x18003db47  mov     rcx, [rbp+psz]; pv
0x18003db4b  call    cs:__imp_CoTaskMemFree
0x18003db51  mov     rax, [rdi+70h]
0x18003db55  mov     rcx, [rax+178h]
0x18003db5c  test    rcx, rcx
0x18003db5f  jz      loc_18003DC07
0x18003db65  mov     rax, [rcx]
0x18003db68  mov     rax, [rax+58h]
0x18003db6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db71  mov     ebx, eax
0x18003db73  test    eax, eax
0x18003db75  jns     loc_18003DC10
0x18003db7b  mov     rcx, [rsi+78h]
0x18003db7f  mov     edx, 0FFFFFFFDh
0x18003db84  mov     byte ptr [rsi+8Ah], 1
0x18003db8b  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18003db91  or      edx, 0FFFFFFFFh
0x18003db94  mov     rcx, r14
0x18003db97  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18003db9d  lea     r8, [rbp+psz]; unsigned __int16 **
0x18003dba1  mov     [rbp+psz], 0
0x18003dba9  mov     edx, ebx; int
0x18003dbab  mov     rcx, rsi; this
0x18003dbae  call    ?_GenerateErrorString@CWebWizardPage@@AEAAJJPEAPEAG@Z; CWebWizardPage::_GenerateErrorString(long,ushort * *)
0x18003dbb3  test    eax, eax
0x18003dbb5  js      short loc_18003DBCD
0x18003dbb7  mov     rdx, [rbp+psz]; unsigned __int16 *
0x18003dbbb  mov     rcx, r14; struct DirectUI::Element *
0x18003dbbe  call    ?SetElementContentStringAndAccName@@YAXPEAVElement@DirectUI@@PEBG@Z; SetElementContentStringAndAccName(DirectUI::Element *,ushort const *)
0x18003dbc3  mov     rcx, [rbp+psz]; pv
0x18003dbc7  call    cs:__imp_CoTaskMemFree
0x18003dbcd  xor     r9d, r9d; __int16
0x18003dbd0  xor     r8d, r8d; __int16
0x18003dbd3  mov     rcx, rsi; this
0x18003dbd6  call    ?_SetWizardButtons@CWebWizardPage@@AEAAJFFF@Z; CWebWizardPage::_SetWizardButtons(short,short,short)
0x18003dbdb  xor     ebx, ebx
0x18003dbdd  mov     byte ptr [rsi+89h], 1
0x18003dbe4  mov     eax, ebx
0x18003dbe6  mov     rcx, [rbp+var_8]
0x18003dbea  xor     rcx, rsp; StackCookie
0x18003dbed  call    __security_check_cookie
0x18003dbf2  lea     r11, [rsp+60h+var_s0]
0x18003dbf7  mov     rbx, [r11+28h]
0x18003dbfb  mov     rsi, [r11+30h]
0x18003dbff  mov     rsp, r11
0x18003dc02  pop     r14
0x18003dc04  pop     rdi
0x18003dc05  pop     rbp
0x18003dc06  retn
0x18003dc07  mov     byte ptr [rax+168h], 1
0x18003dc0e  xor     ebx, ebx
0x18003dc10  mov     rcx, [rdi+70h]
0x18003dc14  mov     edx, 1
0x18003dc19  mov     byte ptr [rdi+82h], 0
0x18003dc20  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18003dc26  mov     edx, 0FFFFFFFDh
0x18003dc2b  mov     rcx, r14
0x18003dc2e  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18003dc34  test    cs:Microsoft_Windows_User_ControlPanelEnableBits, 2
0x18003dc3b  jz      short loc_18003DBE4
0x18003dc3d  lea     rax, [rbp+psz]
0x18003dc41  mov     r9d, 1
0x18003dc47  lea     rdx, UserAccount_Taskflow_WebWizardPage_Active
0x18003dc4e  mov     [rsp+60h+var_40], rax
0x18003dc53  call    McGenEventWrite_EventWriteTransfer
0x18003dc58  jmp     short loc_18003DBE4
```
