# CSWbemObject::DeleteAsync_(IDispatch *,long,IDispatch *,IDispatch *)

- ea: `0x18002a990`
- end: `0x18002aa45`
- name: `?DeleteAsync_@CSWbemObject@@UEAAJPEAUIDispatch@@J00@Z`
- size: `181`
- prototype: `__int64 __fastcall(CSWbemObject *__hidden this, struct IDispatch *, int, struct IDispatch *, struct IDispatch *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006300`
- `0x180019980`
- `0x180024774`
- `0x18002a990`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002aa16`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aa16`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSWbemObject::DeleteAsync_(
        CSWbemObject *this,
        struct IDispatch *a2,
        unsigned int a3,
        struct IDispatch *a4,
        struct IDispatch *a5)
{
  int v9; // ebx
  struct IWbemClassObject *v10; // rcx
  CWbemDispatchMgr *v11; // rcx
  BSTR bstrString; // [rsp+60h] [rbp+8h] BYREF

  v9 = -2147217407;
  ResetLastErrors();
  if ( !*((_QWORD *)this + 7) )
    goto LABEL_6;
  v10 = (struct IWbemClassObject *)*((_QWORD *)this + 8);
  if ( !v10 )
    goto LABEL_6;
  bstrString = 0;
  if ( CSWbemObjectPath::GetObjectPath(v10, (struct ATL::CComBSTR *)&bstrString) )
    v9 = (*(__int64 (__fastcall **)(_QWORD, struct IDispatch *, BSTR, _QWORD, struct IDispatch *, struct IDispatch *))(**((_QWORD **)this + 7) + 80LL))(
           *((_QWORD *)this + 7),
           a2,
           bstrString,
           a3,
           a4,
           a5);
  SysFreeString(bstrString);
  if ( v9 < 0 )
  {
LABEL_6:
    v11 = (CWbemDispatchMgr *)*((_QWORD *)this + 9);
    if ( v11 )
      CWbemDispatchMgr::RaiseException(v11, v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002a990  mov     [rsp+arg_8], rbx
0x18002a995  mov     [rsp+arg_10], rbp
0x18002a99a  push    rsi
0x18002a99b  push    rdi
0x18002a99c  push    r14
0x18002a99e  sub     rsp, 40h
0x18002a9a2  mov     rsi, r9
0x18002a9a5  mov     ebp, r8d
0x18002a9a8  mov     r14, rdx
0x18002a9ab  mov     rdi, rcx
0x18002a9ae  mov     ebx, 80041001h
0x18002a9b3  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18002a9b8  cmp     qword ptr [rdi+38h], 0
0x18002a9bd  jz      short loc_18002AA20
0x18002a9bf  mov     rcx, [rdi+40h]; struct IWbemClassObject *
0x18002a9c3  test    rcx, rcx
0x18002a9c6  jz      short loc_18002AA20
0x18002a9c8  mov     [rsp+58h+bstrString], 0
0x18002a9d1  lea     rdx, [rsp+58h+bstrString]; struct ATL::CComBSTR *
0x18002a9d6  call    ?GetObjectPath@CSWbemObjectPath@@SA_NPEAUIWbemClassObject@@AEAVCComBSTR@ATL@@@Z; CSWbemObjectPath::GetObjectPath(IWbemClassObject *,ATL::CComBSTR &)
0x18002a9db  test    al, al
0x18002a9dd  jz      short loc_18002AA11
0x18002a9df  mov     rcx, [rdi+38h]
0x18002a9e3  mov     rax, [rcx]
0x18002a9e6  mov     r10, [rax+50h]
0x18002a9ea  mov     rax, [rsp+58h+arg_20]
0x18002a9f2  mov     [rsp+58h+var_30], rax
0x18002a9f7  mov     [rsp+58h+var_38], rsi
0x18002a9fc  mov     r9d, ebp
0x18002a9ff  mov     r8, [rsp+58h+bstrString]
0x18002aa04  mov     rdx, r14
0x18002aa07  mov     rax, r10
0x18002aa0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa0f  mov     ebx, eax
0x18002aa11  mov     rcx, [rsp+58h+bstrString]; bstrString
0x18002aa16  call    cs:__imp_SysFreeString
0x18002aa1c  test    ebx, ebx
0x18002aa1e  jns     short loc_18002AA30
0x18002aa20  mov     rcx, [rdi+48h]; this
0x18002aa24  test    rcx, rcx
0x18002aa27  jz      short loc_18002AA30
0x18002aa29  mov     edx, ebx; int
0x18002aa2b  call    ?RaiseException@CWbemDispatchMgr@@QEAAXJ@Z; CWbemDispatchMgr::RaiseException(long)
0x18002aa30  mov     eax, ebx
0x18002aa32  mov     rbx, [rsp+58h+arg_8]
0x18002aa37  mov     rbp, [rsp+58h+arg_10]
0x18002aa3c  add     rsp, 40h
0x18002aa40  pop     r14
0x18002aa42  pop     rdi
0x18002aa43  pop     rsi
0x18002aa44  retn
```
