# WriteWeeklyTrigger(TaskXmlWriter &,JobTriggerPtr)

- ea: `0x1800374a8`
- end: `0x180037639`
- name: `?WriteWeeklyTrigger@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013f20`

## callees

- `0x1800017f0`
- `0x1800018f4`
- `0x180001f90`
- `0x18000247c`
- `0x180003840`
- `0x180003d1c`
- `0x1800136e0`
- `0x1800138e0`
- `0x18003701c`
- `0x1800374a8`
- `0x180037814`
- `0x18003dc94`
- `0x18004b430`
- `0x180054010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180037606`
- `OLEAUT32!__imp_SysFreeString` at `0x18003761b`
- `OLEAUT32!__imp_SysFreeString` at `0x180037606`
- `OLEAUT32!__imp_SysFreeString` at `0x18003761b`
- `OLEAUT32!__imp_SysStringLen` at `0x1800374ea`
- `OLEAUT32!__imp_SysStringLen` at `0x18003757c`
- `OLEAUT32!__imp_SysStringLen` at `0x1800374ea`
- `OLEAUT32!__imp_SysStringLen` at `0x18003757c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WriteWeeklyTrigger(unsigned int *a1, const struct JobTriggerPtr *a2)
{
  int started; // eax
  int v5; // esi
  __int64 *v6; // rax
  __int16 DaysOfWeek; // ax
  __int16 WeeksInterval; // ax
  __int64 v10; // [rsp+20h] [rbp-10h] BYREF
  _BYTE v11[8]; // [rsp+28h] [rbp-8h] BYREF
  BSTR pbstr; // [rsp+60h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF

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
    v6 = (__int64 *)JobTriggerPtr::JobTriggerPtr((JobTriggerPtr *)v11, a2);
    v5 = WriteBaseTriggerProperties((int *)a1, v6);
    if ( v5 >= 0 )
    {
      WeeklyTriggerPtr::WeeklyTriggerPtr((WeeklyTriggerPtr *)&v10, a2);
      bstrString = 0;
      if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v10 + 192LL))(v10, &bstrString) < 0
        || !bstrString
        || !SysStringLen(bstrString)
        || (v5 = TaskXmlWriter::Element(a1, 26, (__int64)bstrString), v5 >= 0) )
      {
        v5 = TaskXmlWriter::StartElement((int *)a1, (struct IErrorInfo *)0x2A);
        if ( v5 >= 0 )
        {
          DaysOfWeek = WeeklyTriggerPtr::GetDaysOfWeek((WeeklyTriggerPtr *)&v10);
          v5 = TaskXmlWriter::SectionDaysOfWeek((TaskXmlWriter *)a1, DaysOfWeek);
          if ( v5 >= 0 )
          {
            WeeksInterval = WeeklyTriggerPtr::GetWeeksInterval((WeeklyTriggerPtr *)&v10);
            v5 = TaskXmlWriter::ElementInt(a1, 43, (unsigned int)WeeksInterval);
            if ( v5 >= 0 )
            {
              v5 = TaskXmlWriter::EndElement((__int64)a1);
              if ( v5 >= 0 )
                v5 = TaskXmlWriter::EndElement((__int64)a1);
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
0x1800374a8  mov     [rsp-18h+arg_0], rbx
0x1800374ad  mov     [rsp-18h+arg_8], rdx
0x1800374b2  push    rbp
0x1800374b3  push    rsi
0x1800374b4  push    rdi
0x1800374b5  mov     rbp, rsp
0x1800374b8  sub     rsp, 30h
0x1800374bc  mov     rbx, rdx
0x1800374bf  mov     rdi, rcx
0x1800374c2  mov     [rbp+pbstr], 0
0x1800374ca  mov     rcx, [rdx]
0x1800374cd  mov     rax, [rcx]
0x1800374d0  lea     rdx, [rbp+pbstr]
0x1800374d4  mov     rax, [rax+40h]
0x1800374d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800374dd  test    eax, eax
0x1800374df  js      short loc_18003750B
0x1800374e1  mov     rcx, [rbp+pbstr]; pbstr
0x1800374e5  test    rcx, rcx
0x1800374e8  jz      short loc_18003750B
0x1800374ea  call    cs:__imp_SysStringLen
0x1800374f0  test    eax, eax
0x1800374f2  jz      short loc_18003750B
0x1800374f4  mov     r9, [rbp+pbstr]
0x1800374f8  mov     edx, 27h ; '''
0x1800374fd  lea     r8d, [rdx+46h]
0x180037501  mov     rcx, rdi
0x180037504  call    ?StartElementWithAttribute@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@0PEBG@Z; TaskXmlWriter::StartElementWithAttribute(TaskXmlNodeId,TaskXmlNodeId,ushort const *)
0x180037509  jmp     short loc_180037518
0x18003750b  mov     edx, 27h ; '''
0x180037510  mov     rcx, rdi
0x180037513  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x180037518  mov     esi, eax
0x18003751a  test    eax, eax
0x18003751c  js      loc_180037617
0x180037522  mov     rdx, rbx; struct JobTriggerPtr *
0x180037525  lea     rcx, [rbp+var_8]; this
0x180037529  call    ??0JobTriggerPtr@@QEAA@AEBV0@@Z; JobTriggerPtr::JobTriggerPtr(JobTriggerPtr const &)
0x18003752e  mov     rdx, rax
0x180037531  mov     rcx, rdi
0x180037534  call    ?WriteBaseTriggerProperties@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z; WriteBaseTriggerProperties(TaskXmlWriter &,JobTriggerPtr)
0x180037539  mov     esi, eax
0x18003753b  test    eax, eax
0x18003753d  js      loc_180037617
0x180037543  mov     rdx, rbx; struct JobTriggerPtr *
0x180037546  lea     rcx, [rbp+var_10]; this
0x18003754a  call    ??0WeeklyTriggerPtr@@QEAA@AEBVJobTriggerPtr@@@Z; WeeklyTriggerPtr::WeeklyTriggerPtr(JobTriggerPtr const &)
0x18003754f  nop
0x180037550  mov     [rbp+bstrString], 0
0x180037558  mov     rcx, [rbp+var_10]
0x18003755c  mov     rax, [rcx]
0x18003755f  lea     rdx, [rbp+bstrString]
0x180037563  mov     rax, [rax+0C0h]
0x18003756a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003756f  test    eax, eax
0x180037571  js      short loc_18003759D
0x180037573  mov     rcx, [rbp+bstrString]; pbstr
0x180037577  test    rcx, rcx
0x18003757a  jz      short loc_18003759D
0x18003757c  call    cs:__imp_SysStringLen
0x180037582  test    eax, eax
0x180037584  jz      short loc_18003759D
0x180037586  mov     r8, [rbp+bstrString]
0x18003758a  mov     edx, 1Ah
0x18003758f  mov     rcx, rdi
0x180037592  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180037597  mov     esi, eax
0x180037599  test    eax, eax
0x18003759b  js      short loc_180037602
0x18003759d  mov     edx, 2Ah ; '*'
0x1800375a2  mov     rcx, rdi
0x1800375a5  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x1800375aa  mov     esi, eax
0x1800375ac  test    eax, eax
0x1800375ae  js      short loc_180037602
0x1800375b0  lea     rcx, [rbp+var_10]; this
0x1800375b4  call    ?GetDaysOfWeek@WeeklyTriggerPtr@@QEAAFXZ; WeeklyTriggerPtr::GetDaysOfWeek(void)
0x1800375b9  movsx   edx, ax; unsigned int
0x1800375bc  mov     rcx, rdi; this
0x1800375bf  call    ?SectionDaysOfWeek@TaskXmlWriter@@QEAAJK@Z; TaskXmlWriter::SectionDaysOfWeek(ulong)
0x1800375c4  mov     esi, eax
0x1800375c6  test    eax, eax
0x1800375c8  js      short loc_180037602
0x1800375ca  lea     rcx, [rbp+var_10]; this
0x1800375ce  call    ?GetWeeksInterval@WeeklyTriggerPtr@@QEAAFXZ; WeeklyTriggerPtr::GetWeeksInterval(void)
0x1800375d3  movsx   r8d, ax
0x1800375d7  mov     edx, 2Bh ; '+'
0x1800375dc  mov     rcx, rdi
0x1800375df  call    ?ElementInt@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@H@Z; TaskXmlWriter::ElementInt(TaskXmlNodeId,int)
0x1800375e4  mov     esi, eax
0x1800375e6  test    eax, eax
0x1800375e8  js      short loc_180037602
0x1800375ea  mov     rcx, rdi
0x1800375ed  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x1800375f2  mov     esi, eax
0x1800375f4  test    eax, eax
0x1800375f6  js      short loc_180037602
0x1800375f8  mov     rcx, rdi
0x1800375fb  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x180037600  mov     esi, eax
0x180037602  mov     rcx, [rbp+bstrString]; bstrString
0x180037606  call    cs:__imp_SysFreeString
0x18003760c  nop
0x18003760d  lea     rcx, [rbp+var_10]
0x180037611  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180037616  nop
0x180037617  mov     rcx, [rbp+pbstr]; bstrString
0x18003761b  call    cs:__imp_SysFreeString
0x180037621  nop
0x180037622  mov     rcx, rbx
0x180037625  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003762a  mov     eax, esi
0x18003762c  mov     rbx, [rsp+30h+arg_0]
0x180037631  add     rsp, 30h
0x180037635  pop     rdi
0x180037636  pop     rsi
0x180037637  pop     rbp
0x180037638  retn
```
