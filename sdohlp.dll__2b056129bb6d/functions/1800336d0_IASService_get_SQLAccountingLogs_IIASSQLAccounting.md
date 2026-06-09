# IASService::get_SQLAccountingLogs(IIASSQLAccounting * *)

- ea: `0x1800336d0`
- end: `0x1800338e5`
- name: `?get_SQLAccountingLogs@IASService@@UEAAJPEAPEAUIIASSQLAccounting@@@Z`
- size: `533`
- prototype: `__int64 __fastcall(IASService *__hidden this, struct IIASSQLAccounting **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180024cac`
- `0x18002cd00`
- `0x18002f240`
- `0x180032304`
- `0x18003233c`
- `0x1800336d0`
- `0x180042a80`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180033709`
- `OLEAUT32!__imp_VariantInit` at `0x180033709`

## string_xrefs

- `0x180033770`: `Could not copy SQLAccountLogs to output pointer: 0x%x`
- `0x180033876`: `Could not copy SQLAccountLogs to output pointer: 0x%x`

## pseudocode

```c
__int64 __fastcall IASService::get_SQLAccountingLogs(IASService *this, struct IIASSQLAccounting **a2)
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
  v5 = (char *)this + 168;
  if ( *((_QWORD *)this + 21) )
  {
    AccountingLogs = ATL::CComPtrBase<IIASItemsCollection>::CopyTo((char *)this + 168, a2);
    if ( AccountingLogs < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("Could not copy SQLAccountLogs to output pointer: 0x%x");
      v6 = 43;
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
    AccountingLogs = IASService::GetAccountingLogs(this, 8, &v10);
    if ( AccountingLogs >= 0 )
    {
      AccountingLogs = (**v10)(v10, &IID_IIASSQLAccounting, v5);
      if ( AccountingLogs >= 0 )
      {
        AccountingLogs = ATL::CComPtrBase<IIASItemsCollection>::CopyTo(v5, a2);
        if ( AccountingLogs < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("Could not copy SQLAccountLogs to output pointer: 0x%x");
          v6 = 46;
          goto LABEL_24;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("pItemAcct->QI(IID_IIASSQLAccounting) returned 0x%x");
        v6 = 45;
        goto LABEL_24;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("GetAccountingLogs(IASSQLACCOUNTING) returned 0x%x");
      v6 = 44;
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
0x1800336d0  mov     [rsp-18h+arg_0], rbx
0x1800336d5  push    rbp
0x1800336d6  push    rsi
0x1800336d7  push    rdi
0x1800336d8  mov     rbp, rsp
0x1800336db  sub     rsp, 50h
0x1800336df  mov     rsi, rdx
0x1800336e2  mov     rbx, rcx
0x1800336e5  mov     [rbp+arg_8], 0
0x1800336ed  mov     [rbp+var_20], 0
0x1800336f5  mov     [rbp+arg_18], 0
0x1800336fd  mov     [rbp+arg_10], 0
0x180033705  lea     rcx, [rbp+pvarg]; pvarg
0x180033709  call    cs:__imp_VariantInit
0x18003370f  test    rsi, rsi
0x180033712  jnz     short loc_18003371E
0x180033714  mov     ebx, 80004003h
0x180033719  jmp     loc_1800338A9
0x18003371e  lea     rdi, [rbx+0A8h]
0x180033725  cmp     qword ptr [rdi], 0
0x180033729  jz      short loc_180033786
0x18003372b  mov     rdx, rsi
0x18003372e  mov     rcx, rdi
0x180033731  call    ?CopyTo@?$CComPtrBase@UIIASItemsCollection@@@ATL@@QEAAJPEAPEAUIIASItemsCollection@@@Z; ATL::CComPtrBase<IIASItemsCollection>::CopyTo(IIASItemsCollection * *)
0x180033736  mov     ebx, eax
0x180033738  test    eax, eax
0x18003373a  jns     loc_1800338A9
0x180033740  lea     rax, WPP_GLOBAL_Control
0x180033747  mov     rcx, cs:WPP_GLOBAL_Control
0x18003374e  cmp     rcx, rax
0x180033751  jz      loc_1800338A9
0x180033757  cmp     byte ptr [rcx+19h], 2
0x18003375b  jb      loc_1800338A9
0x180033761  test    dword ptr [rcx+1Ch], 400h
0x180033768  jz      loc_1800338A9
0x18003376e  mov     edx, ebx
0x180033770  lea     rcx, aCouldNotCopySq; "Could not copy SQLAccountLogs to output"...
0x180033777  call    WppDbgPrint
0x18003377c  mov     edx, 2Bh ; '+'
0x180033781  jmp     loc_180033887
0x180033786  lea     r8, [rbp+arg_8]
0x18003378a  mov     edx, 8
0x18003378f  mov     rcx, rbx
0x180033792  call    ?GetAccountingLogs@IASService@@QEAAJW4_ITEMTYPE@@PEAPEAUIIASItem@@@Z; IASService::GetAccountingLogs(_ITEMTYPE,IIASItem * *)
0x180033797  mov     ebx, eax
0x180033799  test    eax, eax
0x18003379b  jns     short loc_1800337E3
0x18003379d  lea     rax, WPP_GLOBAL_Control
0x1800337a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800337ab  cmp     rcx, rax
0x1800337ae  jz      loc_1800338A9
0x1800337b4  cmp     byte ptr [rcx+19h], 2
0x1800337b8  jb      loc_1800338A9
0x1800337be  test    dword ptr [rcx+1Ch], 400h
0x1800337c5  jz      loc_1800338A9
0x1800337cb  mov     edx, ebx
0x1800337cd  lea     rcx, aGetaccountingl; "GetAccountingLogs(IASSQLACCOUNTING) ret"...
0x1800337d4  call    WppDbgPrint
0x1800337d9  mov     edx, 2Ch ; ','
0x1800337de  jmp     loc_180033887
0x1800337e3  mov     rcx, [rbp+arg_8]
0x1800337e7  mov     rax, [rcx]
0x1800337ea  mov     r8, rdi
0x1800337ed  lea     rdx, IID_IIASSQLAccounting
0x1800337f4  mov     rax, [rax]
0x1800337f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337fc  mov     ebx, eax
0x1800337fe  test    eax, eax
0x180033800  jns     short loc_180033841
0x180033802  lea     rax, WPP_GLOBAL_Control
0x180033809  mov     rcx, cs:WPP_GLOBAL_Control
0x180033810  cmp     rcx, rax
0x180033813  jz      loc_1800338A9
0x180033819  cmp     byte ptr [rcx+19h], 2
0x18003381d  jb      loc_1800338A9
0x180033823  test    dword ptr [rcx+1Ch], 400h
0x18003382a  jz      short loc_1800338A9
0x18003382c  mov     edx, ebx
0x18003382e  lea     rcx, aPitemacctQiIid; "pItemAcct->QI(IID_IIASSQLAccounting) re"...
0x180033835  call    WppDbgPrint
0x18003383a  mov     edx, 2Dh ; '-'
0x18003383f  jmp     short loc_180033887
0x180033841  mov     rdx, rsi
0x180033844  mov     rcx, rdi
0x180033847  call    ?CopyTo@?$CComPtrBase@UIIASItemsCollection@@@ATL@@QEAAJPEAPEAUIIASItemsCollection@@@Z; ATL::CComPtrBase<IIASItemsCollection>::CopyTo(IIASItemsCollection * *)
0x18003384c  mov     ebx, eax
0x18003384e  test    eax, eax
0x180033850  jns     short loc_1800338A9
0x180033852  lea     rax, WPP_GLOBAL_Control
0x180033859  mov     rcx, cs:WPP_GLOBAL_Control
0x180033860  cmp     rcx, rax
0x180033863  jz      short loc_1800338A9
0x180033865  cmp     byte ptr [rcx+19h], 2
0x180033869  jb      short loc_1800338A9
0x18003386b  test    dword ptr [rcx+1Ch], 400h
0x180033872  jz      short loc_1800338A9
0x180033874  mov     edx, ebx
0x180033876  lea     rcx, aCouldNotCopySq; "Could not copy SQLAccountLogs to output"...
0x18003387d  call    WppDbgPrint
0x180033882  mov     edx, 2Eh ; '.'
0x180033887  mov     rcx, cs:WPP_GLOBAL_Control
0x18003388e  mov     [rsp+50h+var_30], ebx
0x180033892  lea     r9, aNpssdo; "NPSSDO"
0x180033899  lea     r8, WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids
0x1800338a0  mov     rcx, [rcx+10h]
0x1800338a4  call    WPP_SF_sd
0x1800338a9  lea     rcx, [rbp+pvarg]; this
0x1800338ad  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800338b2  lea     rcx, [rbp+arg_10]
0x1800338b6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800338bb  lea     rcx, [rbp+arg_18]
0x1800338bf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800338c4  lea     rcx, [rbp+var_20]
0x1800338c8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800338cd  lea     rcx, [rbp+arg_8]
0x1800338d1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800338d6  mov     eax, ebx
0x1800338d8  mov     rbx, [rsp+50h+arg_0]
0x1800338dd  add     rsp, 50h
0x1800338e1  pop     rdi
0x1800338e2  pop     rsi
0x1800338e3  pop     rbp
0x1800338e4  retn
```
