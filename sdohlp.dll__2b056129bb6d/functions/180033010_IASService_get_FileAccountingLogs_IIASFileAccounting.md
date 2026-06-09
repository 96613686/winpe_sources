# IASService::get_FileAccountingLogs(IIASFileAccounting * *)

- ea: `0x180033010`
- end: `0x180033225`
- name: `?get_FileAccountingLogs@IASService@@UEAAJPEAPEAUIIASFileAccounting@@@Z`
- size: `533`
- prototype: `__int64 __fastcall(IASService *__hidden this, struct IIASFileAccounting **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180024cac`
- `0x18002cd00`
- `0x18002f240`
- `0x180032304`
- `0x18003233c`
- `0x180033010`
- `0x180042a80`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180033049`
- `OLEAUT32!__imp_VariantInit` at `0x180033049`

## string_xrefs

- `0x1800330b0`: `Could not copy FileAccountLogs to output pointer: 0x%x`
- `0x1800331b6`: `Could not copy FileAccountLogs to output pointer: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IASService::get_FileAccountingLogs(IASService *this, struct IIASFileAccounting **a2)
{
  int AccountingLogs; // ebx
  char *v5; // rdi
  int v6; // edx
  __int64 v8; // [rsp+30h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-18h] BYREF
  __int64 (__fastcall ***v10)(_QWORD, GUID *, char *); // [rsp+78h] [rbp+28h] BYREF
  __int64 v11; // [rsp+80h] [rbp+30h] BYREF
  __int64 v12; // [rsp+88h] [rbp+38h] BYREF

  v10 = 0;
  v8 = 0;
  v12 = 0;
  v11 = 0;
  VariantInit(&pvarg);
  if ( !a2 )
  {
    AccountingLogs = -2147467261;
    goto LABEL_25;
  }
  v5 = (char *)this + 160;
  if ( *((_QWORD *)this + 20) )
  {
    AccountingLogs = ATL::CComPtrBase<IIASItemsCollection>::CopyTo((char *)this + 160, a2);
    if ( AccountingLogs < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("Could not copy FileAccountLogs to output pointer: 0x%x");
      v6 = 39;
LABEL_24:
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        (unsigned int)WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids,
        (unsigned int)"NPSSDO",
        AccountingLogs);
    }
  }
  else
  {
    AccountingLogs = IASService::GetAccountingLogs(this, 7, &v10);
    if ( AccountingLogs >= 0 )
    {
      AccountingLogs = (**v10)(v10, &IID_IIASFileAccounting, v5);
      if ( AccountingLogs >= 0 )
      {
        AccountingLogs = ATL::CComPtrBase<IIASItemsCollection>::CopyTo(v5, a2);
        if ( AccountingLogs < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("Could not copy FileAccountLogs to output pointer: 0x%x");
          v6 = 42;
          goto LABEL_24;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("pItemAcct->QI(IID_IIASFileAccounting) returned 0x%x");
        v6 = 41;
        goto LABEL_24;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("GetAccountingLogs(IASFILEACCOUNTING) returned 0x%x");
      v6 = 40;
      goto LABEL_24;
    }
  }
LABEL_25:
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v8);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
  return (unsigned int)AccountingLogs;
}

```

## disassembly

```asm
0x180033010  mov     [rsp-18h+arg_0], rbx
0x180033015  push    rbp
0x180033016  push    rsi
0x180033017  push    rdi
0x180033018  mov     rbp, rsp
0x18003301b  sub     rsp, 50h
0x18003301f  mov     rsi, rdx
0x180033022  mov     rbx, rcx
0x180033025  mov     [rbp+arg_8], 0
0x18003302d  mov     [rbp+var_20], 0
0x180033035  mov     [rbp+arg_18], 0
0x18003303d  mov     [rbp+arg_10], 0
0x180033045  lea     rcx, [rbp+pvarg]; pvarg
0x180033049  call    cs:__imp_VariantInit
0x18003304f  test    rsi, rsi
0x180033052  jnz     short loc_18003305E
0x180033054  mov     ebx, 80004003h
0x180033059  jmp     loc_1800331E9
0x18003305e  lea     rdi, [rbx+0A0h]
0x180033065  cmp     qword ptr [rdi], 0
0x180033069  jz      short loc_1800330C6
0x18003306b  mov     rdx, rsi
0x18003306e  mov     rcx, rdi
0x180033071  call    ?CopyTo@?$CComPtrBase@UIIASItemsCollection@@@ATL@@QEAAJPEAPEAUIIASItemsCollection@@@Z; ATL::CComPtrBase<IIASItemsCollection>::CopyTo(IIASItemsCollection * *)
0x180033076  mov     ebx, eax
0x180033078  test    eax, eax
0x18003307a  jns     loc_1800331E9
0x180033080  lea     rax, WPP_GLOBAL_Control
0x180033087  mov     rcx, cs:WPP_GLOBAL_Control
0x18003308e  cmp     rcx, rax
0x180033091  jz      loc_1800331E9
0x180033097  cmp     byte ptr [rcx+19h], 2
0x18003309b  jb      loc_1800331E9
0x1800330a1  test    dword ptr [rcx+1Ch], 400h
0x1800330a8  jz      loc_1800331E9
0x1800330ae  mov     edx, ebx
0x1800330b0  lea     rcx, aCouldNotCopyFi; "Could not copy FileAccountLogs to outpu"...
0x1800330b7  call    WppDbgPrint
0x1800330bc  mov     edx, 27h ; '''
0x1800330c1  jmp     loc_1800331C7
0x1800330c6  lea     r8, [rbp+arg_8]
0x1800330ca  mov     edx, 7
0x1800330cf  mov     rcx, rbx
0x1800330d2  call    ?GetAccountingLogs@IASService@@QEAAJW4_ITEMTYPE@@PEAPEAUIIASItem@@@Z; IASService::GetAccountingLogs(_ITEMTYPE,IIASItem * *)
0x1800330d7  mov     ebx, eax
0x1800330d9  test    eax, eax
0x1800330db  jns     short loc_180033123
0x1800330dd  lea     rax, WPP_GLOBAL_Control
0x1800330e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800330eb  cmp     rcx, rax
0x1800330ee  jz      loc_1800331E9
0x1800330f4  cmp     byte ptr [rcx+19h], 2
0x1800330f8  jb      loc_1800331E9
0x1800330fe  test    dword ptr [rcx+1Ch], 400h
0x180033105  jz      loc_1800331E9
0x18003310b  mov     edx, ebx
0x18003310d  lea     rcx, aGetaccountingl_0; "GetAccountingLogs(IASFILEACCOUNTING) re"...
0x180033114  call    WppDbgPrint
0x180033119  mov     edx, 28h ; '('
0x18003311e  jmp     loc_1800331C7
0x180033123  mov     rcx, [rbp+arg_8]
0x180033127  mov     rax, [rcx]
0x18003312a  mov     r8, rdi
0x18003312d  lea     rdx, IID_IIASFileAccounting
0x180033134  mov     rax, [rax]
0x180033137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003313c  mov     ebx, eax
0x18003313e  test    eax, eax
0x180033140  jns     short loc_180033181
0x180033142  lea     rax, WPP_GLOBAL_Control
0x180033149  mov     rcx, cs:WPP_GLOBAL_Control
0x180033150  cmp     rcx, rax
0x180033153  jz      loc_1800331E9
0x180033159  cmp     byte ptr [rcx+19h], 2
0x18003315d  jb      loc_1800331E9
0x180033163  test    dword ptr [rcx+1Ch], 400h
0x18003316a  jz      short loc_1800331E9
0x18003316c  mov     edx, ebx
0x18003316e  lea     rcx, aPitemacctQiIid_0; "pItemAcct->QI(IID_IIASFileAccounting) r"...
0x180033175  call    WppDbgPrint
0x18003317a  mov     edx, 29h ; ')'
0x18003317f  jmp     short loc_1800331C7
0x180033181  mov     rdx, rsi
0x180033184  mov     rcx, rdi
0x180033187  call    ?CopyTo@?$CComPtrBase@UIIASItemsCollection@@@ATL@@QEAAJPEAPEAUIIASItemsCollection@@@Z; ATL::CComPtrBase<IIASItemsCollection>::CopyTo(IIASItemsCollection * *)
0x18003318c  mov     ebx, eax
0x18003318e  test    eax, eax
0x180033190  jns     short loc_1800331E9
0x180033192  lea     rax, WPP_GLOBAL_Control
0x180033199  mov     rcx, cs:WPP_GLOBAL_Control
0x1800331a0  cmp     rcx, rax
0x1800331a3  jz      short loc_1800331E9
0x1800331a5  cmp     byte ptr [rcx+19h], 2
0x1800331a9  jb      short loc_1800331E9
0x1800331ab  test    dword ptr [rcx+1Ch], 400h
0x1800331b2  jz      short loc_1800331E9
0x1800331b4  mov     edx, ebx
0x1800331b6  lea     rcx, aCouldNotCopyFi; "Could not copy FileAccountLogs to outpu"...
0x1800331bd  call    WppDbgPrint
0x1800331c2  mov     edx, 2Ah ; '*'
0x1800331c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800331ce  mov     [rsp+50h+var_30], ebx
0x1800331d2  lea     r9, aNpssdo; "NPSSDO"
0x1800331d9  lea     r8, WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids
0x1800331e0  mov     rcx, [rcx+10h]
0x1800331e4  call    WPP_SF_sd
0x1800331e9  lea     rcx, [rbp+pvarg]; this
0x1800331ed  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800331f2  lea     rcx, [rbp+arg_10]
0x1800331f6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800331fb  lea     rcx, [rbp+arg_18]
0x1800331ff  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180033204  lea     rcx, [rbp+var_20]
0x180033208  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003320d  lea     rcx, [rbp+arg_8]
0x180033211  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180033216  mov     eax, ebx
0x180033218  mov     rbx, [rsp+50h+arg_0]
0x18003321d  add     rsp, 50h
0x180033221  pop     rdi
0x180033222  pop     rsi
0x180033223  pop     rbp
0x180033224  retn
```
