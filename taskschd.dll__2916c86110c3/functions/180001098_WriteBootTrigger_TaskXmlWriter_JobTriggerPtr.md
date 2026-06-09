# WriteBootTrigger(TaskXmlWriter &,JobTriggerPtr)

- ea: `0x180001098`
- end: `0x1800011f0`
- name: `?WriteBootTrigger@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z`
- size: `344`
- prototype: `int __high(struct TaskXmlWriter *, struct JobTriggerPtr)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013f20`

## callees

- `0x180001008`
- `0x180001098`
- `0x1800017f0`
- `0x1800018f4`
- `0x180001f90`
- `0x180003840`
- `0x180003d1c`
- `0x1800136e0`
- `0x1800138e0`
- `0x180054010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180001191`
- `OLEAUT32!__imp_SysFreeString` at `0x1800011b1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800011d2`
- `OLEAUT32!__imp_SysFreeString` at `0x180001191`
- `OLEAUT32!__imp_SysFreeString` at `0x1800011b1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800011d2`
- `OLEAUT32!__imp_SysStringLen` at `0x1800010da`
- `OLEAUT32!__imp_SysStringLen` at `0x18000116c`
- `OLEAUT32!__imp_SysStringLen` at `0x1800010da`
- `OLEAUT32!__imp_SysStringLen` at `0x18000116c`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WriteBootTrigger(unsigned int *a1, const struct JobTriggerPtr *a2)
{
  int started; // eax
  int v5; // edi
  __int64 *v6; // rax
  __int64 v8; // [rsp+20h] [rbp-10h] BYREF
  _BYTE v9[8]; // [rsp+28h] [rbp-8h] BYREF
  BSTR pbstr; // [rsp+60h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF

  pbstr = 0;
  if ( (*(int (__fastcall **)(_QWORD, BSTR *))(**(_QWORD **)a2 + 64LL))(*(_QWORD *)a2, &pbstr) >= 0
    && pbstr
    && SysStringLen(pbstr) )
  {
    started = TaskXmlWriter::StartElementWithAttribute(a1, 21, 109, (__int64)pbstr);
  }
  else
  {
    started = TaskXmlWriter::StartElement((int *)a1, (struct IErrorInfo *)0x15);
  }
  v5 = started;
  if ( started >= 0 )
  {
    v6 = (__int64 *)JobTriggerPtr::JobTriggerPtr((JobTriggerPtr *)v9, a2);
    v5 = WriteBaseTriggerProperties((int *)a1, v6);
    if ( v5 >= 0 )
    {
      BootTriggerPtr::BootTriggerPtr((BootTriggerPtr *)&v8, a2);
      bstrString = 0;
      if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v8 + 160LL))(v8, &bstrString) >= 0
        && bstrString
        && SysStringLen(bstrString)
        && (v5 = TaskXmlWriter::Element(a1, 22, (__int64)bstrString), v5 < 0) )
      {
        SysFreeString(bstrString);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v8);
      }
      else
      {
        v5 = TaskXmlWriter::EndElement((__int64)a1);
        SysFreeString(bstrString);
        if ( v8 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
    }
  }
  SysFreeString(pbstr);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)a2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180001098  mov     [rsp-18h+arg_0], rbx
0x18000109d  mov     [rsp-18h+arg_8], rdx
0x1800010a2  push    rbp
0x1800010a3  push    rsi
0x1800010a4  push    rdi
0x1800010a5  mov     rbp, rsp
0x1800010a8  sub     rsp, 30h
0x1800010ac  mov     rbx, rdx
0x1800010af  mov     rsi, rcx
0x1800010b2  mov     [rbp+pbstr], 0
0x1800010ba  mov     rcx, [rdx]
0x1800010bd  mov     rax, [rcx]
0x1800010c0  lea     rdx, [rbp+pbstr]
0x1800010c4  mov     rax, [rax+40h]
0x1800010c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010cd  test    eax, eax
0x1800010cf  js      short loc_1800010FB
0x1800010d1  mov     rcx, [rbp+pbstr]; pbstr
0x1800010d5  test    rcx, rcx
0x1800010d8  jz      short loc_1800010FB
0x1800010da  call    cs:__imp_SysStringLen
0x1800010e0  test    eax, eax
0x1800010e2  jz      short loc_1800010FB
0x1800010e4  mov     r9, [rbp+pbstr]
0x1800010e8  mov     edx, 15h
0x1800010ed  lea     r8d, [rdx+58h]
0x1800010f1  mov     rcx, rsi
0x1800010f4  call    ?StartElementWithAttribute@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@0PEBG@Z; TaskXmlWriter::StartElementWithAttribute(TaskXmlNodeId,TaskXmlNodeId,ushort const *)
0x1800010f9  jmp     short loc_180001108
0x1800010fb  mov     edx, 15h
0x180001100  mov     rcx, rsi
0x180001103  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x180001108  mov     edi, eax
0x18000110a  test    eax, eax
0x18000110c  js      loc_1800011CE
0x180001112  mov     rdx, rbx; struct JobTriggerPtr *
0x180001115  lea     rcx, [rbp+var_8]; this
0x180001119  call    ??0JobTriggerPtr@@QEAA@AEBV0@@Z; JobTriggerPtr::JobTriggerPtr(JobTriggerPtr const &)
0x18000111e  mov     rdx, rax
0x180001121  mov     rcx, rsi
0x180001124  call    ?WriteBaseTriggerProperties@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z; WriteBaseTriggerProperties(TaskXmlWriter &,JobTriggerPtr)
0x180001129  mov     edi, eax
0x18000112b  test    eax, eax
0x18000112d  js      loc_1800011CE
0x180001133  mov     rdx, rbx; struct JobTriggerPtr *
0x180001136  lea     rcx, [rbp+var_10]; this
0x18000113a  call    ??0BootTriggerPtr@@QEAA@AEBVJobTriggerPtr@@@Z; BootTriggerPtr::BootTriggerPtr(JobTriggerPtr const &)
0x18000113f  nop
0x180001140  mov     [rbp+bstrString], 0
0x180001148  mov     rcx, [rbp+var_10]
0x18000114c  mov     rax, [rcx]
0x18000114f  lea     rdx, [rbp+bstrString]
0x180001153  mov     rax, [rax+0A0h]
0x18000115a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000115f  test    eax, eax
0x180001161  js      short loc_1800011A3
0x180001163  mov     rcx, [rbp+bstrString]; pbstr
0x180001167  test    rcx, rcx
0x18000116a  jz      short loc_1800011A3
0x18000116c  call    cs:__imp_SysStringLen
0x180001172  test    eax, eax
0x180001174  jz      short loc_1800011A3
0x180001176  mov     r8, [rbp+bstrString]
0x18000117a  mov     edx, 16h
0x18000117f  mov     rcx, rsi
0x180001182  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180001187  mov     edi, eax
0x180001189  test    eax, eax
0x18000118b  jns     short loc_1800011A3
0x18000118d  mov     rcx, [rbp+bstrString]; bstrString
0x180001191  call    cs:__imp_SysFreeString
0x180001197  nop
0x180001198  lea     rcx, [rbp+var_10]
0x18000119c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800011a1  jmp     short loc_1800011CE
0x1800011a3  mov     rcx, rsi
0x1800011a6  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x1800011ab  mov     edi, eax
0x1800011ad  mov     rcx, [rbp+bstrString]; bstrString
0x1800011b1  call    cs:__imp_SysFreeString
0x1800011b7  nop
0x1800011b8  mov     rcx, [rbp+var_10]
0x1800011bc  test    rcx, rcx
0x1800011bf  jz      short loc_1800011CE
0x1800011c1  mov     rdx, [rcx]
0x1800011c4  mov     rax, [rdx+10h]
0x1800011c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011cd  nop
0x1800011ce  mov     rcx, [rbp+pbstr]; bstrString
0x1800011d2  call    cs:__imp_SysFreeString
0x1800011d8  nop
0x1800011d9  mov     rcx, rbx
0x1800011dc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800011e1  mov     eax, edi
0x1800011e3  mov     rbx, [rsp+30h+arg_0]
0x1800011e8  add     rsp, 30h
0x1800011ec  pop     rdi
0x1800011ed  pop     rsi
0x1800011ee  pop     rbp
0x1800011ef  retn
```
