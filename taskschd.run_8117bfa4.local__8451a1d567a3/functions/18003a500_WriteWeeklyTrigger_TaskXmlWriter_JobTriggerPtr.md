# WriteWeeklyTrigger(TaskXmlWriter &,JobTriggerPtr)

- ea: `0x18003a500`
- end: `0x18003a6aa`
- name: `?WriteWeeklyTrigger@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014df0`

## callees

- `0x180001880`
- `0x180001938`
- `0x180001fe4`
- `0x180002554`
- `0x180003a30`
- `0x180003f30`
- `0x1800145c0`
- `0x180014700`
- `0x180039fe8`
- `0x18003a500`
- `0x18003a6b0`
- `0x18004118c`
- `0x18004f018`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18003a66a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a685`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a66a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a685`
- `OLEAUT32!__imp_SysStringLen` at `0x18003a542`
- `OLEAUT32!__imp_SysStringLen` at `0x18003a5da`
- `OLEAUT32!__imp_SysStringLen` at `0x18003a542`
- `OLEAUT32!__imp_SysStringLen` at `0x18003a5da`

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
0x18003a500  mov     [rsp-18h+arg_0], rbx
0x18003a505  mov     [rsp-18h+arg_8], rdx
0x18003a50a  push    rbp
0x18003a50b  push    rsi
0x18003a50c  push    rdi
0x18003a50d  mov     rbp, rsp
0x18003a510  sub     rsp, 30h
0x18003a514  mov     rbx, rdx
0x18003a517  mov     rdi, rcx
0x18003a51a  mov     [rbp+pbstr], 0
0x18003a522  mov     rcx, [rdx]
0x18003a525  mov     rax, [rcx]
0x18003a528  lea     rdx, [rbp+pbstr]
0x18003a52c  mov     rax, [rax+40h]
0x18003a530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a535  test    eax, eax
0x18003a537  js      short loc_18003A569
0x18003a539  mov     rcx, [rbp+pbstr]; pbstr
0x18003a53d  test    rcx, rcx
0x18003a540  jz      short loc_18003A569
0x18003a542  call    cs:__imp_SysStringLen
0x18003a549  nop     dword ptr [rax+rax+00h]
0x18003a54e  test    eax, eax
0x18003a550  jz      short loc_18003A569
0x18003a552  mov     r9, [rbp+pbstr]
0x18003a556  mov     edx, 27h ; '''
0x18003a55b  lea     r8d, [rdx+46h]
0x18003a55f  mov     rcx, rdi
0x18003a562  call    ?StartElementWithAttribute@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@0PEBG@Z; TaskXmlWriter::StartElementWithAttribute(TaskXmlNodeId,TaskXmlNodeId,ushort const *)
0x18003a567  jmp     short loc_18003A576
0x18003a569  mov     edx, 27h ; '''
0x18003a56e  mov     rcx, rdi
0x18003a571  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x18003a576  mov     esi, eax
0x18003a578  test    eax, eax
0x18003a57a  js      loc_18003A681
0x18003a580  mov     rdx, rbx; struct JobTriggerPtr *
0x18003a583  lea     rcx, [rbp+var_8]; this
0x18003a587  call    ??0JobTriggerPtr@@QEAA@AEBV0@@Z; JobTriggerPtr::JobTriggerPtr(JobTriggerPtr const &)
0x18003a58c  mov     rdx, rax
0x18003a58f  mov     rcx, rdi
0x18003a592  call    ?WriteBaseTriggerProperties@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z; WriteBaseTriggerProperties(TaskXmlWriter &,JobTriggerPtr)
0x18003a597  mov     esi, eax
0x18003a599  test    eax, eax
0x18003a59b  js      loc_18003A681
0x18003a5a1  mov     rdx, rbx; struct JobTriggerPtr *
0x18003a5a4  lea     rcx, [rbp+var_10]; this
0x18003a5a8  call    ??0WeeklyTriggerPtr@@QEAA@AEBVJobTriggerPtr@@@Z; WeeklyTriggerPtr::WeeklyTriggerPtr(JobTriggerPtr const &)
0x18003a5ad  nop
0x18003a5ae  mov     [rbp+bstrString], 0
0x18003a5b6  mov     rcx, [rbp+var_10]
0x18003a5ba  mov     rax, [rcx]
0x18003a5bd  lea     rdx, [rbp+bstrString]
0x18003a5c1  mov     rax, [rax+0C0h]
0x18003a5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a5cd  test    eax, eax
0x18003a5cf  js      short loc_18003A601
0x18003a5d1  mov     rcx, [rbp+bstrString]; pbstr
0x18003a5d5  test    rcx, rcx
0x18003a5d8  jz      short loc_18003A601
0x18003a5da  call    cs:__imp_SysStringLen
0x18003a5e1  nop     dword ptr [rax+rax+00h]
0x18003a5e6  test    eax, eax
0x18003a5e8  jz      short loc_18003A601
0x18003a5ea  mov     r8, [rbp+bstrString]
0x18003a5ee  mov     edx, 1Ah
0x18003a5f3  mov     rcx, rdi
0x18003a5f6  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18003a5fb  mov     esi, eax
0x18003a5fd  test    eax, eax
0x18003a5ff  js      short loc_18003A666
0x18003a601  mov     edx, 2Ah ; '*'
0x18003a606  mov     rcx, rdi
0x18003a609  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x18003a60e  mov     esi, eax
0x18003a610  test    eax, eax
0x18003a612  js      short loc_18003A666
0x18003a614  lea     rcx, [rbp+var_10]; this
0x18003a618  call    ?GetDaysOfWeek@WeeklyTriggerPtr@@QEAAFXZ; WeeklyTriggerPtr::GetDaysOfWeek(void)
0x18003a61d  movsx   edx, ax; unsigned int
0x18003a620  mov     rcx, rdi; this
0x18003a623  call    ?SectionDaysOfWeek@TaskXmlWriter@@QEAAJK@Z; TaskXmlWriter::SectionDaysOfWeek(ulong)
0x18003a628  mov     esi, eax
0x18003a62a  test    eax, eax
0x18003a62c  js      short loc_18003A666
0x18003a62e  lea     rcx, [rbp+var_10]; this
0x18003a632  call    ?GetWeeksInterval@WeeklyTriggerPtr@@QEAAFXZ; WeeklyTriggerPtr::GetWeeksInterval(void)
0x18003a637  movsx   r8d, ax
0x18003a63b  mov     edx, 2Bh ; '+'
0x18003a640  mov     rcx, rdi
0x18003a643  call    ?ElementInt@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@H@Z; TaskXmlWriter::ElementInt(TaskXmlNodeId,int)
0x18003a648  mov     esi, eax
0x18003a64a  test    eax, eax
0x18003a64c  js      short loc_18003A666
0x18003a64e  mov     rcx, rdi
0x18003a651  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x18003a656  mov     esi, eax
0x18003a658  test    eax, eax
0x18003a65a  js      short loc_18003A666
0x18003a65c  mov     rcx, rdi
0x18003a65f  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x18003a664  mov     esi, eax
0x18003a666  mov     rcx, [rbp+bstrString]; bstrString
0x18003a66a  call    cs:__imp_SysFreeString
0x18003a671  nop     dword ptr [rax+rax+00h]
0x18003a676  nop
0x18003a677  lea     rcx, [rbp+var_10]
0x18003a67b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003a680  nop
0x18003a681  mov     rcx, [rbp+pbstr]; bstrString
0x18003a685  call    cs:__imp_SysFreeString
0x18003a68c  nop     dword ptr [rax+rax+00h]
0x18003a691  nop
0x18003a692  mov     rcx, rbx
0x18003a695  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003a69a  mov     eax, esi
0x18003a69c  mov     rbx, [rsp+30h+arg_0]
0x18003a6a1  add     rsp, 30h
0x18003a6a5  pop     rdi
0x18003a6a6  pop     rsi
0x18003a6a7  pop     rbp
0x18003a6a8  retn
```
