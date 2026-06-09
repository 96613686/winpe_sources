# SetOleErrorInfo(_GUID const &,_TASK_XML_ERROR_INFO const *)

- ea: `0x18003977c`
- end: `0x180039912`
- name: `?SetOleErrorInfo@@YAXAEBU_GUID@@PEBU_TASK_XML_ERROR_INFO@@@Z`
- size: `406`
- prototype: `void __fastcall(const struct _GUID *, const struct _TASK_XML_ERROR_INFO *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800074d0`
- `0x18000e4f0`

## callees

- `0x180001880`
- `0x180003ea0`
- `0x18003977c`
- `0x18005260b`
- `0x180052640`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x1800398cb`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800398cb`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800397cd`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800397cd`

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
0x18003977c  test    rdx, rdx
0x18003977f  jz      locret_180039910
0x180039785  mov     [rsp-8+arg_10], rbx
0x18003978a  mov     [rsp-8+arg_18], rdi
0x18003978f  push    rbp
0x180039790  lea     rbp, [rsp-760h]
0x180039798  sub     rsp, 860h
0x18003979f  mov     rax, cs:__security_cookie
0x1800397a6  xor     rax, rsp
0x1800397a9  mov     [rbp+760h+var_10], rax
0x1800397b0  mov     rbx, rdx
0x1800397b3  mov     rdi, rcx
0x1800397b6  mov     [rsp+860h+pperrinfo], 0
0x1800397bf  mov     [rsp+860h+perrinfo], 0
0x1800397c8  lea     rcx, [rsp+860h+pperrinfo]; pperrinfo
0x1800397cd  call    cs:__imp_CreateErrorInfo
0x1800397d4  nop     dword ptr [rax+rax+00h]
0x1800397d9  test    eax, eax
0x1800397db  js      loc_1800398D8
0x1800397e1  xor     eax, eax
0x1800397e3  mov     [rsp+860h+var_810], ax
0x1800397e8  xor     edx, edx; Val
0x1800397ea  mov     r8d, 7FEh; Size
0x1800397f0  lea     rcx, [rsp+860h+var_80E]; void *
0x1800397f5  call    memset_0
0x1800397fa  lea     rcx, Src
0x180039801  mov     rax, rcx
0x180039804  cmp     qword ptr [rbx+10h], 0
0x180039809  cmovnz  rax, [rbx+10h]
0x18003980e  cmp     qword ptr [rbx+8], 0
0x180039813  cmovnz  rcx, [rbx+8]
0x180039818  mov     [rsp+860h+var_830], rax
0x18003981d  mov     [rsp+860h+var_838], rcx
0x180039822  mov     eax, [rbx+4]
0x180039825  mov     [rsp+860h+var_840], eax
0x180039829  mov     r9d, [rbx]
0x18003982c  lea     r8, aDDSS; "(%d,%d):%s:%s"
0x180039833  mov     edx, 400h; unsigned __int64
0x180039838  lea     rcx, [rsp+860h+var_810]; unsigned __int16 *
0x18003983d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180039842  mov     rcx, [rsp+860h+pperrinfo]
0x180039847  mov     rax, [rcx]
0x18003984a  lea     rdx, [rsp+860h+var_810]
0x18003984f  mov     rax, [rax+28h]
0x180039853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039858  test    eax, eax
0x18003985a  jns     short loc_18003988C
0x18003985c  mov     rcx, [rsp+860h+perrinfo]
0x180039861  test    rcx, rcx
0x180039864  jz      short loc_180039873
0x180039866  mov     rax, [rcx]
0x180039869  mov     rax, [rax+10h]
0x18003986d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039872  nop
0x180039873  mov     rcx, [rsp+860h+pperrinfo]
0x180039878  test    rcx, rcx
0x18003987b  jz      short loc_18003988A
0x18003987d  mov     rax, [rcx]
0x180039880  mov     rax, [rax+10h]
0x180039884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039889  nop
0x18003988a  jmp     short loc_1800398ED
0x18003988c  mov     rcx, [rsp+860h+pperrinfo]
0x180039891  mov     rax, [rcx]
0x180039894  mov     rdx, rdi
0x180039897  mov     rax, [rax+18h]
0x18003989b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800398a0  test    eax, eax
0x1800398a2  js      short loc_1800398D8
0x1800398a4  mov     rcx, [rsp+860h+pperrinfo]
0x1800398a9  mov     rax, [rcx]
0x1800398ac  lea     r8, [rsp+860h+perrinfo]
0x1800398b1  lea     rdx, IID_IErrorInfo
0x1800398b8  mov     rax, [rax]
0x1800398bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800398c0  test    eax, eax
0x1800398c2  js      short loc_1800398D8
0x1800398c4  mov     rdx, [rsp+860h+perrinfo]; perrinfo
0x1800398c9  xor     ecx, ecx; dwReserved
0x1800398cb  call    cs:__imp_SetErrorInfo
0x1800398d2  nop     dword ptr [rax+rax+00h]
0x1800398d7  nop
0x1800398d8  lea     rcx, [rsp+860h+perrinfo]
0x1800398dd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800398e2  nop
0x1800398e3  lea     rcx, [rsp+860h+pperrinfo]
0x1800398e8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800398ed  mov     rcx, [rbp+760h+var_10]
0x1800398f4  xor     rcx, rsp; StackCookie
0x1800398f7  call    __security_check_cookie
0x1800398fc  lea     r11, [rsp+860h+var_s0]
0x180039904  mov     rbx, [r11+20h]
0x180039908  mov     rdi, [r11+28h]
0x18003990c  mov     rsp, r11
0x18003990f  pop     rbp
0x180039910  retn
```
