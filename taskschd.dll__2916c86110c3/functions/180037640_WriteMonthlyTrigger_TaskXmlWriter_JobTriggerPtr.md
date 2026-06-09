# WriteMonthlyTrigger(TaskXmlWriter &,JobTriggerPtr)

- ea: `0x180037640`
- end: `0x18003780b`
- name: `?WriteMonthlyTrigger@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013f20`

## callees

- `0x1800017f0`
- `0x1800018f4`
- `0x180001f90`
- `0x180003840`
- `0x180003d1c`
- `0x1800136e0`
- `0x1800138e0`
- `0x1800366f8`
- `0x180037640`
- `0x180038220`
- `0x18003dc14`
- `0x18004b494`
- `0x180054010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800377da`
- `OLEAUT32!__imp_SysFreeString` at `0x1800377ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800377da`
- `OLEAUT32!__imp_SysFreeString` at `0x1800377ef`
- `OLEAUT32!__imp_SysStringLen` at `0x18003767f`
- `OLEAUT32!__imp_SysStringLen` at `0x18003770c`
- `OLEAUT32!__imp_SysStringLen` at `0x18003767f`
- `OLEAUT32!__imp_SysStringLen` at `0x18003770c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WriteMonthlyTrigger(unsigned int *a1, const struct JobTriggerPtr *a2)
{
  int started; // eax
  int v5; // esi
  __int64 *v6; // rax
  unsigned int DaysOfMonth; // esi
  BSTR pbstr; // [rsp+20h] [rbp-20h] BYREF
  __int64 v10; // [rsp+28h] [rbp-18h] BYREF
  BSTR bstrString; // [rsp+30h] [rbp-10h] BYREF
  _BYTE v12[8]; // [rsp+38h] [rbp-8h] BYREF
  __int16 v13; // [rsp+80h] [rbp+40h] BYREF
  __int16 v14; // [rsp+88h] [rbp+48h] BYREF

  pbstr = 0;
  if ( (*(int (__fastcall **)(_QWORD, BSTR *))(**(_QWORD **)a2 + 64LL))(*(_QWORD *)a2, &pbstr) >= 0
    && pbstr
    && SysStringLen(pbstr) )
  {
    started = TaskXmlWriter::StartElementWithAttribute(a1, 39, 109, (__int64)pbstr);
  }
  else
  {
    started = TaskXmlWriter::StartElement((int *)a1, (struct IErrorInfo *)0x27);
  }
  v5 = started;
  if ( started >= 0 )
  {
    v6 = (__int64 *)JobTriggerPtr::JobTriggerPtr((JobTriggerPtr *)v12, a2);
    v5 = WriteBaseTriggerProperties((int *)a1, v6);
    if ( v5 >= 0 )
    {
      MonthlyTriggerPtr::MonthlyTriggerPtr((MonthlyTriggerPtr *)&v10, a2);
      bstrString = 0;
      if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v10 + 208LL))(v10, &bstrString) < 0
        || !bstrString
        || !SysStringLen(bstrString)
        || (v5 = TaskXmlWriter::Element(a1, 26, (__int64)bstrString), v5 >= 0) )
      {
        v5 = TaskXmlWriter::StartElement((int *)a1, (struct IErrorInfo *)0x34);
        if ( v5 >= 0 )
        {
          DaysOfMonth = MonthlyTriggerPtr::GetDaysOfMonth((MonthlyTriggerPtr *)&v10);
          v13 = 0;
          (*(void (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v10 + 192LL))(v10, &v13);
          if ( v13 )
            DaysOfMonth |= 0x80000000;
          v5 = TaskXmlWriter::SectionDaysOfMonth((TaskXmlWriter *)a1, DaysOfMonth);
          if ( v5 >= 0 )
          {
            v14 = 0;
            v5 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v10 + 176LL))(v10, &v14);
            if ( v5 >= 0 )
            {
              v5 = TaskXmlWriter::SectionMonths((TaskXmlWriter *)a1, v14);
              if ( v5 >= 0 )
              {
                v5 = TaskXmlWriter::EndElement((__int64)a1);
                if ( v5 >= 0 )
                  v5 = TaskXmlWriter::EndElement((__int64)a1);
              }
            }
          }
        }
      }
      SysFreeString(bstrString);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
    }
  }
  SysFreeString(pbstr);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)a2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180037640  mov     [rsp-28h+arg_8], rdx
0x180037645  push    rbp
0x180037646  push    rbx
0x180037647  push    rsi
0x180037648  push    rdi
0x180037649  push    r14
0x18003764b  mov     rbp, rsp
0x18003764e  sub     rsp, 40h
0x180037652  mov     rbx, rdx
0x180037655  mov     rdi, rcx
0x180037658  xor     r14d, r14d
0x18003765b  mov     [rbp+pbstr], r14
0x18003765f  mov     rcx, [rdx]
0x180037662  mov     rax, [rcx]
0x180037665  lea     rdx, [rbp+pbstr]
0x180037669  mov     rax, [rax+40h]
0x18003766d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037672  test    eax, eax
0x180037674  js      short loc_18003769F
0x180037676  mov     rcx, [rbp+pbstr]; pbstr
0x18003767a  test    rcx, rcx
0x18003767d  jz      short loc_18003769F
0x18003767f  call    cs:__imp_SysStringLen
0x180037685  test    eax, eax
0x180037687  jz      short loc_18003769F
0x180037689  mov     r9, [rbp+pbstr]
0x18003768d  lea     edx, [r14+27h]
0x180037691  lea     r8d, [r14+6Dh]
0x180037695  mov     rcx, rdi
0x180037698  call    ?StartElementWithAttribute@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@0PEBG@Z; TaskXmlWriter::StartElementWithAttribute(TaskXmlNodeId,TaskXmlNodeId,ushort const *)
0x18003769d  jmp     short loc_1800376AC
0x18003769f  mov     edx, 27h ; '''
0x1800376a4  mov     rcx, rdi
0x1800376a7  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x1800376ac  mov     esi, eax
0x1800376ae  test    eax, eax
0x1800376b0  js      loc_1800377EB
0x1800376b6  mov     rdx, rbx; struct JobTriggerPtr *
0x1800376b9  lea     rcx, [rbp+var_8]; this
0x1800376bd  call    ??0JobTriggerPtr@@QEAA@AEBV0@@Z; JobTriggerPtr::JobTriggerPtr(JobTriggerPtr const &)
0x1800376c2  mov     rdx, rax
0x1800376c5  mov     rcx, rdi
0x1800376c8  call    ?WriteBaseTriggerProperties@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z; WriteBaseTriggerProperties(TaskXmlWriter &,JobTriggerPtr)
0x1800376cd  mov     esi, eax
0x1800376cf  test    eax, eax
0x1800376d1  js      loc_1800377EB
0x1800376d7  mov     rdx, rbx; struct JobTriggerPtr *
0x1800376da  lea     rcx, [rbp+var_18]; this
0x1800376de  call    ??0MonthlyTriggerPtr@@QEAA@AEBVJobTriggerPtr@@@Z; MonthlyTriggerPtr::MonthlyTriggerPtr(JobTriggerPtr const &)
0x1800376e3  nop
0x1800376e4  mov     [rbp+bstrString], r14
0x1800376e8  mov     rcx, [rbp+var_18]
0x1800376ec  mov     rax, [rcx]
0x1800376ef  lea     rdx, [rbp+bstrString]
0x1800376f3  mov     rax, [rax+0D0h]
0x1800376fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376ff  test    eax, eax
0x180037701  js      short loc_180037731
0x180037703  mov     rcx, [rbp+bstrString]; pbstr
0x180037707  test    rcx, rcx
0x18003770a  jz      short loc_180037731
0x18003770c  call    cs:__imp_SysStringLen
0x180037712  test    eax, eax
0x180037714  jz      short loc_180037731
0x180037716  mov     r8, [rbp+bstrString]
0x18003771a  mov     edx, 1Ah
0x18003771f  mov     rcx, rdi
0x180037722  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180037727  mov     esi, eax
0x180037729  test    eax, eax
0x18003772b  js      loc_1800377D6
0x180037731  mov     edx, 34h ; '4'
0x180037736  mov     rcx, rdi
0x180037739  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x18003773e  mov     esi, eax
0x180037740  test    eax, eax
0x180037742  js      loc_1800377D6
0x180037748  lea     rcx, [rbp+var_18]; this
0x18003774c  call    ?GetDaysOfMonth@MonthlyTriggerPtr@@QEAAJXZ; MonthlyTriggerPtr::GetDaysOfMonth(void)
0x180037751  mov     esi, eax
0x180037753  mov     [rbp+arg_10], r14w
0x180037758  mov     rcx, [rbp+var_18]
0x18003775c  mov     rdx, [rcx]
0x18003775f  mov     rax, [rdx+0C0h]
0x180037766  lea     rdx, [rbp+arg_10]
0x18003776a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003776f  cmp     [rbp+arg_10], r14w
0x180037774  jz      short loc_18003777A
0x180037776  bts     esi, 1Fh
0x18003777a  mov     edx, esi; unsigned int
0x18003777c  mov     rcx, rdi; this
0x18003777f  call    ?SectionDaysOfMonth@TaskXmlWriter@@QEAAJK@Z; TaskXmlWriter::SectionDaysOfMonth(ulong)
0x180037784  mov     esi, eax
0x180037786  test    eax, eax
0x180037788  js      short loc_1800377D6
0x18003778a  mov     [rbp+arg_18], r14w
0x18003778f  mov     rcx, [rbp+var_18]
0x180037793  mov     rax, [rcx]
0x180037796  lea     rdx, [rbp+arg_18]
0x18003779a  mov     rax, [rax+0B0h]
0x1800377a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377a6  mov     esi, eax
0x1800377a8  test    eax, eax
0x1800377aa  js      short loc_1800377D6
0x1800377ac  movsx   edx, [rbp+arg_18]; unsigned int
0x1800377b0  mov     rcx, rdi; this
0x1800377b3  call    ?SectionMonths@TaskXmlWriter@@QEAAJK@Z; TaskXmlWriter::SectionMonths(ulong)
0x1800377b8  mov     esi, eax
0x1800377ba  test    eax, eax
0x1800377bc  js      short loc_1800377D6
0x1800377be  mov     rcx, rdi
0x1800377c1  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x1800377c6  mov     esi, eax
0x1800377c8  test    eax, eax
0x1800377ca  js      short loc_1800377D6
0x1800377cc  mov     rcx, rdi
0x1800377cf  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x1800377d4  mov     esi, eax
0x1800377d6  mov     rcx, [rbp+bstrString]; bstrString
0x1800377da  call    cs:__imp_SysFreeString
0x1800377e0  nop
0x1800377e1  lea     rcx, [rbp+var_18]
0x1800377e5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800377ea  nop
0x1800377eb  mov     rcx, [rbp+pbstr]; bstrString
0x1800377ef  call    cs:__imp_SysFreeString
0x1800377f5  nop
0x1800377f6  mov     rcx, rbx
0x1800377f9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800377fe  mov     eax, esi
0x180037800  add     rsp, 40h
0x180037804  pop     r14
0x180037806  pop     rdi
0x180037807  pop     rsi
0x180037808  pop     rbx
0x180037809  pop     rbp
0x18003780a  retn
```
