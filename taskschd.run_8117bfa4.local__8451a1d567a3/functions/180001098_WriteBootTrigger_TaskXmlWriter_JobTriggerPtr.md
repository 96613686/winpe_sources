# WriteBootTrigger(TaskXmlWriter &,JobTriggerPtr)

- ea: `0x180001098`
- end: `0x18000120f`
- name: `?WriteBootTrigger@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z`
- size: `375`
- prototype: `int __high(struct TaskXmlWriter *, struct JobTriggerPtr)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014df0`

## callees

- `0x180001008`
- `0x180001098`
- `0x180001880`
- `0x180001938`
- `0x180001fe4`
- `0x180003a30`
- `0x180003f30`
- `0x1800145c0`
- `0x180014700`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000119d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800011c3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800011ea`
- `OLEAUT32!__imp_SysFreeString` at `0x18000119d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800011c3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800011ea`
- `OLEAUT32!__imp_SysStringLen` at `0x1800010da`
- `OLEAUT32!__imp_SysStringLen` at `0x180001172`
- `OLEAUT32!__imp_SysStringLen` at `0x1800010da`
- `OLEAUT32!__imp_SysStringLen` at `0x180001172`

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
0x1800010cf  js      short loc_180001101
0x1800010d1  mov     rcx, [rbp+pbstr]; pbstr
0x1800010d5  test    rcx, rcx
0x1800010d8  jz      short loc_180001101
0x1800010da  call    cs:__imp_SysStringLen
0x1800010e1  nop     dword ptr [rax+rax+00h]
0x1800010e6  test    eax, eax
0x1800010e8  jz      short loc_180001101
0x1800010ea  mov     r9, [rbp+pbstr]
0x1800010ee  mov     edx, 15h
0x1800010f3  lea     r8d, [rdx+58h]
0x1800010f7  mov     rcx, rsi
0x1800010fa  call    ?StartElementWithAttribute@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@0PEBG@Z; TaskXmlWriter::StartElementWithAttribute(TaskXmlNodeId,TaskXmlNodeId,ushort const *)
0x1800010ff  jmp     short loc_18000110E
0x180001101  mov     edx, 15h
0x180001106  mov     rcx, rsi
0x180001109  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x18000110e  mov     edi, eax
0x180001110  test    eax, eax
0x180001112  js      loc_1800011E6
0x180001118  mov     rdx, rbx; struct JobTriggerPtr *
0x18000111b  lea     rcx, [rbp+var_8]; this
0x18000111f  call    ??0JobTriggerPtr@@QEAA@AEBV0@@Z; JobTriggerPtr::JobTriggerPtr(JobTriggerPtr const &)
0x180001124  mov     rdx, rax
0x180001127  mov     rcx, rsi
0x18000112a  call    ?WriteBaseTriggerProperties@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z; WriteBaseTriggerProperties(TaskXmlWriter &,JobTriggerPtr)
0x18000112f  mov     edi, eax
0x180001131  test    eax, eax
0x180001133  js      loc_1800011E6
0x180001139  mov     rdx, rbx; struct JobTriggerPtr *
0x18000113c  lea     rcx, [rbp+var_10]; this
0x180001140  call    ??0BootTriggerPtr@@QEAA@AEBVJobTriggerPtr@@@Z; BootTriggerPtr::BootTriggerPtr(JobTriggerPtr const &)
0x180001145  nop
0x180001146  mov     [rbp+bstrString], 0
0x18000114e  mov     rcx, [rbp+var_10]
0x180001152  mov     rax, [rcx]
0x180001155  lea     rdx, [rbp+bstrString]
0x180001159  mov     rax, [rax+0A0h]
0x180001160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001165  test    eax, eax
0x180001167  js      short loc_1800011B5
0x180001169  mov     rcx, [rbp+bstrString]; pbstr
0x18000116d  test    rcx, rcx
0x180001170  jz      short loc_1800011B5
0x180001172  call    cs:__imp_SysStringLen
0x180001179  nop     dword ptr [rax+rax+00h]
0x18000117e  test    eax, eax
0x180001180  jz      short loc_1800011B5
0x180001182  mov     r8, [rbp+bstrString]
0x180001186  mov     edx, 16h
0x18000118b  mov     rcx, rsi
0x18000118e  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180001193  mov     edi, eax
0x180001195  test    eax, eax
0x180001197  jns     short loc_1800011B5
0x180001199  mov     rcx, [rbp+bstrString]; bstrString
0x18000119d  call    cs:__imp_SysFreeString
0x1800011a4  nop     dword ptr [rax+rax+00h]
0x1800011a9  nop
0x1800011aa  lea     rcx, [rbp+var_10]
0x1800011ae  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800011b3  jmp     short loc_1800011E6
0x1800011b5  mov     rcx, rsi
0x1800011b8  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x1800011bd  mov     edi, eax
0x1800011bf  mov     rcx, [rbp+bstrString]; bstrString
0x1800011c3  call    cs:__imp_SysFreeString
0x1800011ca  nop     dword ptr [rax+rax+00h]
0x1800011cf  nop
0x1800011d0  mov     rcx, [rbp+var_10]
0x1800011d4  test    rcx, rcx
0x1800011d7  jz      short loc_1800011E6
0x1800011d9  mov     rdx, [rcx]
0x1800011dc  mov     rax, [rdx+10h]
0x1800011e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011e5  nop
0x1800011e6  mov     rcx, [rbp+pbstr]; bstrString
0x1800011ea  call    cs:__imp_SysFreeString
0x1800011f1  nop     dword ptr [rax+rax+00h]
0x1800011f6  nop
0x1800011f7  mov     rcx, rbx
0x1800011fa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800011ff  mov     eax, edi
0x180001201  mov     rbx, [rsp+30h+arg_0]
0x180001206  add     rsp, 30h
0x18000120a  pop     rdi
0x18000120b  pop     rsi
0x18000120c  pop     rbp
0x18000120d  retn
```
