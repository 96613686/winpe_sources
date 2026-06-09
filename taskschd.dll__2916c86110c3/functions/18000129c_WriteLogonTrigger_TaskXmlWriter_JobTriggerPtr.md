# WriteLogonTrigger(TaskXmlWriter &,JobTriggerPtr)

- ea: `0x18000129c`
- end: `0x18000145f`
- name: `?WriteLogonTrigger@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z`
- size: `451`
- prototype: `int __high(struct TaskXmlWriter *, struct JobTriggerPtr)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013f20`

## callees

- `0x1800011f8`
- `0x18000129c`
- `0x180001468`
- `0x1800017f0`
- `0x1800018f4`
- `0x180001f90`
- `0x180003840`
- `0x180003d1c`
- `0x1800136e0`
- `0x1800138e0`
- `0x180054010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180001314`
- `OLEAUT32!__imp_SysFreeString` at `0x1800013ec`
- `OLEAUT32!__imp_SysFreeString` at `0x1800013f6`
- `OLEAUT32!__imp_SysFreeString` at `0x180001417`
- `OLEAUT32!__imp_SysFreeString` at `0x180001421`
- `OLEAUT32!__imp_SysFreeString` at `0x180001442`
- `OLEAUT32!__imp_SysFreeString` at `0x180001314`
- `OLEAUT32!__imp_SysFreeString` at `0x1800013ec`
- `OLEAUT32!__imp_SysFreeString` at `0x1800013f6`
- `OLEAUT32!__imp_SysFreeString` at `0x180001417`
- `OLEAUT32!__imp_SysFreeString` at `0x180001421`
- `OLEAUT32!__imp_SysFreeString` at `0x180001442`
- `OLEAUT32!__imp_SysStringLen` at `0x1800012dc`
- `OLEAUT32!__imp_SysStringLen` at `0x180001379`
- `OLEAUT32!__imp_SysStringLen` at `0x1800013c6`
- `OLEAUT32!__imp_SysStringLen` at `0x1800012dc`
- `OLEAUT32!__imp_SysStringLen` at `0x180001379`
- `OLEAUT32!__imp_SysStringLen` at `0x1800013c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WriteLogonTrigger(unsigned int *a1, __int64 *a2)
{
  int started; // eax
  int v5; // ebx
  __int64 *v7; // rax
  int UnresolvedUserId; // eax
  OLECHAR *v9; // rbx
  int v10; // r14d
  __int64 v11; // [rsp+20h] [rbp-10h] BYREF
  BSTR v12; // [rsp+28h] [rbp-8h] BYREF
  BSTR pbstr; // [rsp+70h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp+48h] BYREF

  pbstr = 0;
  if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)*a2 + 64LL))(*a2, &pbstr) >= 0
    && pbstr
    && SysStringLen(pbstr) )
  {
    started = TaskXmlWriter::StartElementWithAttribute(a1, 35, 109, (__int64)pbstr);
  }
  else
  {
    started = TaskXmlWriter::StartElement((int *)a1, (struct IErrorInfo *)0x23);
  }
  v5 = started;
  if ( started < 0
    || (v7 = (__int64 *)JobTriggerPtr::JobTriggerPtr((JobTriggerPtr *)&v12, (const struct JobTriggerPtr *)a2),
        v5 = WriteBaseTriggerProperties((int *)a1, v7),
        v5 < 0) )
  {
    SysFreeString(pbstr);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(a2);
    return (unsigned int)v5;
  }
  LogonTriggerPtr::LogonTriggerPtr((LogonTriggerPtr *)&v11, (const struct JobTriggerPtr *)a2);
  v12 = 0;
  UnresolvedUserId = LogonTriggerImpl<ILogonTrigger,9>::get_UnresolvedUserId(v11, &v12);
  v9 = v12;
  if ( UnresolvedUserId < 0
    || !v12
    || !SysStringLen(v12)
    || (v10 = TaskXmlWriter::Element(a1, 36, (__int64)v9), v10 >= 0) )
  {
    bstrString = 0;
    if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v11 + 160LL))(v11, &bstrString) < 0
      || !bstrString
      || !SysStringLen(bstrString)
      || (v10 = TaskXmlWriter::Element(a1, 22, (__int64)bstrString), v10 >= 0) )
    {
      v10 = TaskXmlWriter::EndElement((__int64)a1);
      SysFreeString(bstrString);
      SysFreeString(v9);
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      goto LABEL_21;
    }
    SysFreeString(bstrString);
  }
  SysFreeString(v9);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
LABEL_21:
  SysFreeString(pbstr);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(a2);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000129c  mov     [rsp-28h+arg_8], rdx
0x1800012a1  push    rbp
0x1800012a2  push    rbx
0x1800012a3  push    rsi
0x1800012a4  push    rdi
0x1800012a5  push    r14
0x1800012a7  mov     rbp, rsp
0x1800012aa  sub     rsp, 30h
0x1800012ae  mov     rdi, rdx
0x1800012b1  mov     rsi, rcx
0x1800012b4  mov     [rbp+pbstr], 0
0x1800012bc  mov     rcx, [rdx]
0x1800012bf  mov     rax, [rcx]
0x1800012c2  lea     rdx, [rbp+pbstr]
0x1800012c6  mov     rax, [rax+40h]
0x1800012ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012cf  test    eax, eax
0x1800012d1  js      short loc_1800012FD
0x1800012d3  mov     rcx, [rbp+pbstr]; pbstr
0x1800012d7  test    rcx, rcx
0x1800012da  jz      short loc_1800012FD
0x1800012dc  call    cs:__imp_SysStringLen
0x1800012e2  test    eax, eax
0x1800012e4  jz      short loc_1800012FD
0x1800012e6  mov     r9, [rbp+pbstr]
0x1800012ea  mov     edx, 23h ; '#'
0x1800012ef  lea     r8d, [rdx+4Ah]
0x1800012f3  mov     rcx, rsi
0x1800012f6  call    ?StartElementWithAttribute@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@0PEBG@Z; TaskXmlWriter::StartElementWithAttribute(TaskXmlNodeId,TaskXmlNodeId,ushort const *)
0x1800012fb  jmp     short loc_18000130A
0x1800012fd  mov     edx, 23h ; '#'
0x180001302  mov     rcx, rsi
0x180001305  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x18000130a  mov     ebx, eax
0x18000130c  test    eax, eax
0x18000130e  jns     short loc_18000132A
0x180001310  mov     rcx, [rbp+pbstr]; bstrString
0x180001314  call    cs:__imp_SysFreeString
0x18000131a  nop
0x18000131b  mov     rcx, rdi
0x18000131e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001323  mov     eax, ebx
0x180001325  jmp     loc_180001454
0x18000132a  mov     rdx, rdi; struct JobTriggerPtr *
0x18000132d  lea     rcx, [rbp+var_8]; this
0x180001331  call    ??0JobTriggerPtr@@QEAA@AEBV0@@Z; JobTriggerPtr::JobTriggerPtr(JobTriggerPtr const &)
0x180001336  mov     rdx, rax
0x180001339  mov     rcx, rsi
0x18000133c  call    ?WriteBaseTriggerProperties@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z; WriteBaseTriggerProperties(TaskXmlWriter &,JobTriggerPtr)
0x180001341  mov     ebx, eax
0x180001343  test    eax, eax
0x180001345  js      short loc_180001310
0x180001347  mov     rdx, rdi; struct JobTriggerPtr *
0x18000134a  lea     rcx, [rbp+var_10]; this
0x18000134e  call    ??0LogonTriggerPtr@@QEAA@AEBVJobTriggerPtr@@@Z; LogonTriggerPtr::LogonTriggerPtr(JobTriggerPtr const &)
0x180001353  nop
0x180001354  mov     [rbp+var_8], 0
0x18000135c  lea     rdx, [rbp+var_8]
0x180001360  mov     rcx, [rbp+var_10]
0x180001364  call    ?get_UnresolvedUserId@?$LogonTriggerImpl@UILogonTrigger@@$08@@QEAAJPEAPEAG@Z; LogonTriggerImpl<ILogonTrigger,9>::get_UnresolvedUserId(ushort * *)
0x180001369  mov     rbx, [rbp+var_8]
0x18000136d  test    eax, eax
0x18000136f  js      short loc_18000139A
0x180001371  test    rbx, rbx
0x180001374  jz      short loc_18000139A
0x180001376  mov     rcx, rbx; pbstr
0x180001379  call    cs:__imp_SysStringLen
0x18000137f  test    eax, eax
0x180001381  jz      short loc_18000139A
0x180001383  mov     r8, rbx
0x180001386  mov     edx, 24h ; '$'
0x18000138b  mov     rcx, rsi
0x18000138e  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180001393  mov     r14d, eax
0x180001396  test    eax, eax
0x180001398  js      short loc_1800013F3
0x18000139a  mov     [rbp+bstrString], 0
0x1800013a2  mov     rcx, [rbp+var_10]
0x1800013a6  mov     rax, [rcx]
0x1800013a9  lea     rdx, [rbp+bstrString]
0x1800013ad  mov     rax, [rax+0A0h]
0x1800013b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013b9  test    eax, eax
0x1800013bb  js      short loc_180001408
0x1800013bd  mov     rcx, [rbp+bstrString]; pbstr
0x1800013c1  test    rcx, rcx
0x1800013c4  jz      short loc_180001408
0x1800013c6  call    cs:__imp_SysStringLen
0x1800013cc  test    eax, eax
0x1800013ce  jz      short loc_180001408
0x1800013d0  mov     r8, [rbp+bstrString]
0x1800013d4  mov     edx, 16h
0x1800013d9  mov     rcx, rsi
0x1800013dc  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x1800013e1  mov     r14d, eax
0x1800013e4  test    eax, eax
0x1800013e6  jns     short loc_180001408
0x1800013e8  mov     rcx, [rbp+bstrString]; bstrString
0x1800013ec  call    cs:__imp_SysFreeString
0x1800013f2  nop
0x1800013f3  mov     rcx, rbx; bstrString
0x1800013f6  call    cs:__imp_SysFreeString
0x1800013fc  nop
0x1800013fd  lea     rcx, [rbp+var_10]
0x180001401  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001406  jmp     short loc_18000143E
0x180001408  mov     rcx, rsi
0x18000140b  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x180001410  mov     r14d, eax
0x180001413  mov     rcx, [rbp+bstrString]; bstrString
0x180001417  call    cs:__imp_SysFreeString
0x18000141d  nop
0x18000141e  mov     rcx, rbx; bstrString
0x180001421  call    cs:__imp_SysFreeString
0x180001427  nop
0x180001428  mov     rcx, [rbp+var_10]
0x18000142c  test    rcx, rcx
0x18000142f  jz      short loc_18000143E
0x180001431  mov     rdx, [rcx]
0x180001434  mov     rax, [rdx+10h]
0x180001438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000143d  nop
0x18000143e  mov     rcx, [rbp+pbstr]; bstrString
0x180001442  call    cs:__imp_SysFreeString
0x180001448  nop
0x180001449  mov     rcx, rdi
0x18000144c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001451  mov     eax, r14d
0x180001454  add     rsp, 30h
0x180001458  pop     r14
0x18000145a  pop     rdi
0x18000145b  pop     rsi
0x18000145c  pop     rbx
0x18000145d  pop     rbp
0x18000145e  retn
```
