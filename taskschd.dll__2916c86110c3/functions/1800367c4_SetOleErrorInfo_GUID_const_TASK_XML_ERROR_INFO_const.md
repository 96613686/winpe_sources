# SetOleErrorInfo(_GUID const &,_TASK_XML_ERROR_INFO const *)

- ea: `0x1800367c4`
- end: `0x18003694d`
- name: `?SetOleErrorInfo@@YAXAEBU_GUID@@PEBU_TASK_XML_ERROR_INFO@@@Z`
- size: `393`
- prototype: `void __fastcall(const struct _GUID *, const struct _TASK_XML_ERROR_INFO *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007100`
- `0x18000e4d0`

## callees

- `0x1800017f0`
- `0x180003c90`
- `0x1800367c4`
- `0x18004e90f`
- `0x18004e950`
- `0x180054010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x18003690d`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18003690d`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180036815`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180036815`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall SetOleErrorInfo(const struct _GUID *a1, const struct _TASK_XML_ERROR_INFO *a2)
{
  const unsigned __int16 *v4; // rcx
  const unsigned __int16 *v5; // rax
  int v6; // [rsp+20h] [rbp-E0h]
  ICreateErrorInfo *pperrinfo; // [rsp+40h] [rbp-C0h] BYREF
  IErrorInfo *perrinfo; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v9; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v10[2046]; // [rsp+52h] [rbp-AEh] BYREF

  if ( !a2 )
    return;
  pperrinfo = 0;
  perrinfo = 0;
  if ( CreateErrorInfo(&pperrinfo) < 0 )
  {
LABEL_16:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&perrinfo);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pperrinfo);
    return;
  }
  v9 = 0;
  memset_0(v10, 0, sizeof(v10));
  v4 = &Src;
  v5 = &Src;
  if ( *((_QWORD *)a2 + 2) )
    v5 = (const unsigned __int16 *)*((_QWORD *)a2 + 2);
  if ( *((_QWORD *)a2 + 1) )
    v4 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
  v6 = *((_DWORD *)a2 + 1);
  StringCchPrintfW(&v9, 0x400u, L"(%d,%d):%s:%s", *(unsigned int *)a2, v6, v4, v5);
  if ( ((int (__fastcall *)(ICreateErrorInfo *, unsigned __int16 *))pperrinfo->lpVtbl->SetDescription)(pperrinfo, &v9) >= 0 )
  {
    if ( ((int (__fastcall *)(ICreateErrorInfo *, const struct _GUID *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, a1) >= 0
      && ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
           pperrinfo,
           &IID_IErrorInfo,
           &perrinfo) >= 0 )
    {
      SetErrorInfo(0, perrinfo);
    }
    goto LABEL_16;
  }
  if ( perrinfo )
    ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
  if ( pperrinfo )
    ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
}

```

## disassembly

```asm
0x1800367c4  test    rdx, rdx
0x1800367c7  jz      locret_18003694C
0x1800367cd  mov     [rsp-8+arg_10], rbx
0x1800367d2  mov     [rsp-8+arg_18], rdi
0x1800367d7  push    rbp
0x1800367d8  lea     rbp, [rsp-760h]
0x1800367e0  sub     rsp, 860h
0x1800367e7  mov     rax, cs:__security_cookie
0x1800367ee  xor     rax, rsp
0x1800367f1  mov     [rbp+760h+var_10], rax
0x1800367f8  mov     rbx, rdx
0x1800367fb  mov     rdi, rcx
0x1800367fe  mov     [rsp+860h+pperrinfo], 0
0x180036807  mov     [rsp+860h+perrinfo], 0
0x180036810  lea     rcx, [rsp+860h+pperrinfo]; pperrinfo
0x180036815  call    cs:__imp_CreateErrorInfo
0x18003681b  test    eax, eax
0x18003681d  js      loc_180036914
0x180036823  xor     eax, eax
0x180036825  mov     [rsp+860h+var_810], ax
0x18003682a  xor     edx, edx; Val
0x18003682c  mov     r8d, 7FEh; Size
0x180036832  lea     rcx, [rsp+860h+var_80E]; void *
0x180036837  call    memset_0
0x18003683c  lea     rcx, Src
0x180036843  mov     rax, rcx
0x180036846  cmp     qword ptr [rbx+10h], 0
0x18003684b  cmovnz  rax, [rbx+10h]
0x180036850  cmp     qword ptr [rbx+8], 0
0x180036855  cmovnz  rcx, [rbx+8]
0x18003685a  mov     [rsp+860h+var_830], rax
0x18003685f  mov     [rsp+860h+var_838], rcx
0x180036864  mov     eax, [rbx+4]
0x180036867  mov     [rsp+860h+var_840], eax
0x18003686b  mov     r9d, [rbx]
0x18003686e  lea     r8, aDDSS; "(%d,%d):%s:%s"
0x180036875  mov     edx, 400h; unsigned __int64
0x18003687a  lea     rcx, [rsp+860h+var_810]; unsigned __int16 *
0x18003687f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180036884  mov     rcx, [rsp+860h+pperrinfo]
0x180036889  mov     rax, [rcx]
0x18003688c  lea     rdx, [rsp+860h+var_810]
0x180036891  mov     rax, [rax+28h]
0x180036895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003689a  test    eax, eax
0x18003689c  jns     short loc_1800368CE
0x18003689e  mov     rcx, [rsp+860h+perrinfo]
0x1800368a3  test    rcx, rcx
0x1800368a6  jz      short loc_1800368B5
0x1800368a8  mov     rax, [rcx]
0x1800368ab  mov     rax, [rax+10h]
0x1800368af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368b4  nop
0x1800368b5  mov     rcx, [rsp+860h+pperrinfo]
0x1800368ba  test    rcx, rcx
0x1800368bd  jz      short loc_1800368CC
0x1800368bf  mov     rax, [rcx]
0x1800368c2  mov     rax, [rax+10h]
0x1800368c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368cb  nop
0x1800368cc  jmp     short loc_180036929
0x1800368ce  mov     rcx, [rsp+860h+pperrinfo]
0x1800368d3  mov     rax, [rcx]
0x1800368d6  mov     rdx, rdi
0x1800368d9  mov     rax, [rax+18h]
0x1800368dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368e2  test    eax, eax
0x1800368e4  js      short loc_180036914
0x1800368e6  mov     rcx, [rsp+860h+pperrinfo]
0x1800368eb  mov     rax, [rcx]
0x1800368ee  lea     r8, [rsp+860h+perrinfo]
0x1800368f3  lea     rdx, IID_IErrorInfo
0x1800368fa  mov     rax, [rax]
0x1800368fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036902  test    eax, eax
0x180036904  js      short loc_180036914
0x180036906  mov     rdx, [rsp+860h+perrinfo]; perrinfo
0x18003690b  xor     ecx, ecx; dwReserved
0x18003690d  call    cs:__imp_SetErrorInfo
0x180036913  nop
0x180036914  lea     rcx, [rsp+860h+perrinfo]
0x180036919  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003691e  nop
0x18003691f  lea     rcx, [rsp+860h+pperrinfo]
0x180036924  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180036929  mov     rcx, [rbp+760h+var_10]
0x180036930  xor     rcx, rsp; StackCookie
0x180036933  call    __security_check_cookie
0x180036938  lea     r11, [rsp+860h+var_s0]
0x180036940  mov     rbx, [r11+20h]
0x180036944  mov     rdi, [r11+28h]
0x180036948  mov     rsp, r11
0x18003694b  pop     rbp
0x18003694c  retn
```
