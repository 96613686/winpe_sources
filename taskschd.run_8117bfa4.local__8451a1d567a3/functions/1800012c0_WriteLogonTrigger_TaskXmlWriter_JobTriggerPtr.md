# WriteLogonTrigger(TaskXmlWriter &,JobTriggerPtr)

- ea: `0x1800012c0`
- end: `0x1800014ba`
- name: `?WriteLogonTrigger@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z`
- size: `506`
- prototype: `int __high(struct TaskXmlWriter *, struct JobTriggerPtr)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014df0`

## callees

- `0x180001218`
- `0x1800012c0`
- `0x1800014c0`
- `0x180001880`
- `0x180001938`
- `0x180001fe4`
- `0x180003a30`
- `0x180003f30`
- `0x1800145c0`
- `0x180014700`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000133e`
- `OLEAUT32!__imp_SysFreeString` at `0x180001428`
- `OLEAUT32!__imp_SysFreeString` at `0x180001438`
- `OLEAUT32!__imp_SysFreeString` at `0x18000145f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000146f`
- `OLEAUT32!__imp_SysFreeString` at `0x180001496`
- `OLEAUT32!__imp_SysFreeString` at `0x18000133e`
- `OLEAUT32!__imp_SysFreeString` at `0x180001428`
- `OLEAUT32!__imp_SysFreeString` at `0x180001438`
- `OLEAUT32!__imp_SysFreeString` at `0x18000145f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000146f`
- `OLEAUT32!__imp_SysFreeString` at `0x180001496`
- `OLEAUT32!__imp_SysStringLen` at `0x180001300`
- `OLEAUT32!__imp_SysStringLen` at `0x1800013a9`
- `OLEAUT32!__imp_SysStringLen` at `0x1800013fc`
- `OLEAUT32!__imp_SysStringLen` at `0x180001300`
- `OLEAUT32!__imp_SysStringLen` at `0x1800013a9`
- `OLEAUT32!__imp_SysStringLen` at `0x1800013fc`

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
0x1800012c0  mov     [rsp-28h+arg_8], rdx
0x1800012c5  push    rbp
0x1800012c6  push    rbx
0x1800012c7  push    rsi
0x1800012c8  push    rdi
0x1800012c9  push    r14
0x1800012cb  mov     rbp, rsp
0x1800012ce  sub     rsp, 30h
0x1800012d2  mov     rdi, rdx
0x1800012d5  mov     rsi, rcx
0x1800012d8  mov     [rbp+pbstr], 0
0x1800012e0  mov     rcx, [rdx]
0x1800012e3  mov     rax, [rcx]
0x1800012e6  lea     rdx, [rbp+pbstr]
0x1800012ea  mov     rax, [rax+40h]
0x1800012ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012f3  test    eax, eax
0x1800012f5  js      short loc_180001327
0x1800012f7  mov     rcx, [rbp+pbstr]; pbstr
0x1800012fb  test    rcx, rcx
0x1800012fe  jz      short loc_180001327
0x180001300  call    cs:__imp_SysStringLen
0x180001307  nop     dword ptr [rax+rax+00h]
0x18000130c  test    eax, eax
0x18000130e  jz      short loc_180001327
0x180001310  mov     r9, [rbp+pbstr]
0x180001314  mov     edx, 23h ; '#'
0x180001319  lea     r8d, [rdx+4Ah]
0x18000131d  mov     rcx, rsi
0x180001320  call    ?StartElementWithAttribute@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@0PEBG@Z; TaskXmlWriter::StartElementWithAttribute(TaskXmlNodeId,TaskXmlNodeId,ushort const *)
0x180001325  jmp     short loc_180001334
0x180001327  mov     edx, 23h ; '#'
0x18000132c  mov     rcx, rsi
0x18000132f  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x180001334  mov     ebx, eax
0x180001336  test    eax, eax
0x180001338  jns     short loc_18000135A
0x18000133a  mov     rcx, [rbp+pbstr]; bstrString
0x18000133e  call    cs:__imp_SysFreeString
0x180001345  nop     dword ptr [rax+rax+00h]
0x18000134a  nop
0x18000134b  mov     rcx, rdi
0x18000134e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001353  mov     eax, ebx
0x180001355  jmp     loc_1800014AE
0x18000135a  mov     rdx, rdi; struct JobTriggerPtr *
0x18000135d  lea     rcx, [rbp+var_8]; this
0x180001361  call    ??0JobTriggerPtr@@QEAA@AEBV0@@Z; JobTriggerPtr::JobTriggerPtr(JobTriggerPtr const &)
0x180001366  mov     rdx, rax
0x180001369  mov     rcx, rsi
0x18000136c  call    ?WriteBaseTriggerProperties@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z; WriteBaseTriggerProperties(TaskXmlWriter &,JobTriggerPtr)
0x180001371  mov     ebx, eax
0x180001373  test    eax, eax
0x180001375  js      short loc_18000133A
0x180001377  mov     rdx, rdi; struct JobTriggerPtr *
0x18000137a  lea     rcx, [rbp+var_10]; this
0x18000137e  call    ??0LogonTriggerPtr@@QEAA@AEBVJobTriggerPtr@@@Z; LogonTriggerPtr::LogonTriggerPtr(JobTriggerPtr const &)
0x180001383  nop
0x180001384  mov     [rbp+var_8], 0
0x18000138c  lea     rdx, [rbp+var_8]
0x180001390  mov     rcx, [rbp+var_10]
0x180001394  call    ?get_UnresolvedUserId@?$LogonTriggerImpl@UILogonTrigger@@$08@@QEAAJPEAPEAG@Z; LogonTriggerImpl<ILogonTrigger,9>::get_UnresolvedUserId(ushort * *)
0x180001399  mov     rbx, [rbp+var_8]
0x18000139d  test    eax, eax
0x18000139f  js      short loc_1800013D0
0x1800013a1  test    rbx, rbx
0x1800013a4  jz      short loc_1800013D0
0x1800013a6  mov     rcx, rbx; pbstr
0x1800013a9  call    cs:__imp_SysStringLen
0x1800013b0  nop     dword ptr [rax+rax+00h]
0x1800013b5  test    eax, eax
0x1800013b7  jz      short loc_1800013D0
0x1800013b9  mov     r8, rbx
0x1800013bc  mov     edx, 24h ; '$'
0x1800013c1  mov     rcx, rsi
0x1800013c4  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x1800013c9  mov     r14d, eax
0x1800013cc  test    eax, eax
0x1800013ce  js      short loc_180001435
0x1800013d0  mov     [rbp+bstrString], 0
0x1800013d8  mov     rcx, [rbp+var_10]
0x1800013dc  mov     rax, [rcx]
0x1800013df  lea     rdx, [rbp+bstrString]
0x1800013e3  mov     rax, [rax+0A0h]
0x1800013ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013ef  test    eax, eax
0x1800013f1  js      short loc_180001450
0x1800013f3  mov     rcx, [rbp+bstrString]; pbstr
0x1800013f7  test    rcx, rcx
0x1800013fa  jz      short loc_180001450
0x1800013fc  call    cs:__imp_SysStringLen
0x180001403  nop     dword ptr [rax+rax+00h]
0x180001408  test    eax, eax
0x18000140a  jz      short loc_180001450
0x18000140c  mov     r8, [rbp+bstrString]
0x180001410  mov     edx, 16h
0x180001415  mov     rcx, rsi
0x180001418  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18000141d  mov     r14d, eax
0x180001420  test    eax, eax
0x180001422  jns     short loc_180001450
0x180001424  mov     rcx, [rbp+bstrString]; bstrString
0x180001428  call    cs:__imp_SysFreeString
0x18000142f  nop     dword ptr [rax+rax+00h]
0x180001434  nop
0x180001435  mov     rcx, rbx; bstrString
0x180001438  call    cs:__imp_SysFreeString
0x18000143f  nop     dword ptr [rax+rax+00h]
0x180001444  nop
0x180001445  lea     rcx, [rbp+var_10]
0x180001449  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000144e  jmp     short loc_180001492
0x180001450  mov     rcx, rsi
0x180001453  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x180001458  mov     r14d, eax
0x18000145b  mov     rcx, [rbp+bstrString]; bstrString
0x18000145f  call    cs:__imp_SysFreeString
0x180001466  nop     dword ptr [rax+rax+00h]
0x18000146b  nop
0x18000146c  mov     rcx, rbx; bstrString
0x18000146f  call    cs:__imp_SysFreeString
0x180001476  nop     dword ptr [rax+rax+00h]
0x18000147b  nop
0x18000147c  mov     rcx, [rbp+var_10]
0x180001480  test    rcx, rcx
0x180001483  jz      short loc_180001492
0x180001485  mov     rdx, [rcx]
0x180001488  mov     rax, [rdx+10h]
0x18000148c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001491  nop
0x180001492  mov     rcx, [rbp+pbstr]; bstrString
0x180001496  call    cs:__imp_SysFreeString
0x18000149d  nop     dword ptr [rax+rax+00h]
0x1800014a2  nop
0x1800014a3  mov     rcx, rdi
0x1800014a6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800014ab  mov     eax, r14d
0x1800014ae  add     rsp, 30h
0x1800014b2  pop     r14
0x1800014b4  pop     rdi
0x1800014b5  pop     rsi
0x1800014b6  pop     rbx
0x1800014b7  pop     rbp
0x1800014b8  retn
```
