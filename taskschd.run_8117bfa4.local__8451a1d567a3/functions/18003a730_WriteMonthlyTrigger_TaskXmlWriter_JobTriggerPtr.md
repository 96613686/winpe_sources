# WriteMonthlyTrigger(TaskXmlWriter &,JobTriggerPtr)

- ea: `0x18003a730`
- end: `0x18003a914`
- name: `?WriteMonthlyTrigger@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014df0`

## callees

- `0x180001880`
- `0x180001938`
- `0x180001fe4`
- `0x180003a30`
- `0x180003f30`
- `0x1800145c0`
- `0x180014700`
- `0x18003966c`
- `0x18003a730`
- `0x18003b2c0`
- `0x18004110c`
- `0x18004f080`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18003a8d6`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a8f1`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a8d6`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a8f1`
- `OLEAUT32!__imp_SysStringLen` at `0x18003a76f`
- `OLEAUT32!__imp_SysStringLen` at `0x18003a802`
- `OLEAUT32!__imp_SysStringLen` at `0x18003a76f`
- `OLEAUT32!__imp_SysStringLen` at `0x18003a802`

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
0x18003a730  mov     [rsp-28h+arg_8], rdx
0x18003a735  push    rbp
0x18003a736  push    rbx
0x18003a737  push    rsi
0x18003a738  push    rdi
0x18003a739  push    r14
0x18003a73b  mov     rbp, rsp
0x18003a73e  sub     rsp, 40h
0x18003a742  mov     rbx, rdx
0x18003a745  mov     rdi, rcx
0x18003a748  xor     r14d, r14d
0x18003a74b  mov     [rbp+pbstr], r14
0x18003a74f  mov     rcx, [rdx]
0x18003a752  mov     rax, [rcx]
0x18003a755  lea     rdx, [rbp+pbstr]
0x18003a759  mov     rax, [rax+40h]
0x18003a75d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a762  test    eax, eax
0x18003a764  js      short loc_18003A795
0x18003a766  mov     rcx, [rbp+pbstr]; pbstr
0x18003a76a  test    rcx, rcx
0x18003a76d  jz      short loc_18003A795
0x18003a76f  call    cs:__imp_SysStringLen
0x18003a776  nop     dword ptr [rax+rax+00h]
0x18003a77b  test    eax, eax
0x18003a77d  jz      short loc_18003A795
0x18003a77f  mov     r9, [rbp+pbstr]
0x18003a783  lea     edx, [r14+27h]
0x18003a787  lea     r8d, [r14+6Dh]
0x18003a78b  mov     rcx, rdi
0x18003a78e  call    ?StartElementWithAttribute@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@0PEBG@Z; TaskXmlWriter::StartElementWithAttribute(TaskXmlNodeId,TaskXmlNodeId,ushort const *)
0x18003a793  jmp     short loc_18003A7A2
0x18003a795  mov     edx, 27h ; '''
0x18003a79a  mov     rcx, rdi
0x18003a79d  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x18003a7a2  mov     esi, eax
0x18003a7a4  test    eax, eax
0x18003a7a6  js      loc_18003A8ED
0x18003a7ac  mov     rdx, rbx; struct JobTriggerPtr *
0x18003a7af  lea     rcx, [rbp+var_8]; this
0x18003a7b3  call    ??0JobTriggerPtr@@QEAA@AEBV0@@Z; JobTriggerPtr::JobTriggerPtr(JobTriggerPtr const &)
0x18003a7b8  mov     rdx, rax
0x18003a7bb  mov     rcx, rdi
0x18003a7be  call    ?WriteBaseTriggerProperties@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z; WriteBaseTriggerProperties(TaskXmlWriter &,JobTriggerPtr)
0x18003a7c3  mov     esi, eax
0x18003a7c5  test    eax, eax
0x18003a7c7  js      loc_18003A8ED
0x18003a7cd  mov     rdx, rbx; struct JobTriggerPtr *
0x18003a7d0  lea     rcx, [rbp+var_18]; this
0x18003a7d4  call    ??0MonthlyTriggerPtr@@QEAA@AEBVJobTriggerPtr@@@Z; MonthlyTriggerPtr::MonthlyTriggerPtr(JobTriggerPtr const &)
0x18003a7d9  nop
0x18003a7da  mov     [rbp+bstrString], r14
0x18003a7de  mov     rcx, [rbp+var_18]
0x18003a7e2  mov     rax, [rcx]
0x18003a7e5  lea     rdx, [rbp+bstrString]
0x18003a7e9  mov     rax, [rax+0D0h]
0x18003a7f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a7f5  test    eax, eax
0x18003a7f7  js      short loc_18003A82D
0x18003a7f9  mov     rcx, [rbp+bstrString]; pbstr
0x18003a7fd  test    rcx, rcx
0x18003a800  jz      short loc_18003A82D
0x18003a802  call    cs:__imp_SysStringLen
0x18003a809  nop     dword ptr [rax+rax+00h]
0x18003a80e  test    eax, eax
0x18003a810  jz      short loc_18003A82D
0x18003a812  mov     r8, [rbp+bstrString]
0x18003a816  mov     edx, 1Ah
0x18003a81b  mov     rcx, rdi
0x18003a81e  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18003a823  mov     esi, eax
0x18003a825  test    eax, eax
0x18003a827  js      loc_18003A8D2
0x18003a82d  mov     edx, 34h ; '4'
0x18003a832  mov     rcx, rdi
0x18003a835  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x18003a83a  mov     esi, eax
0x18003a83c  test    eax, eax
0x18003a83e  js      loc_18003A8D2
0x18003a844  lea     rcx, [rbp+var_18]; this
0x18003a848  call    ?GetDaysOfMonth@MonthlyTriggerPtr@@QEAAJXZ; MonthlyTriggerPtr::GetDaysOfMonth(void)
0x18003a84d  mov     esi, eax
0x18003a84f  mov     [rbp+arg_10], r14w
0x18003a854  mov     rcx, [rbp+var_18]
0x18003a858  mov     rdx, [rcx]
0x18003a85b  mov     rax, [rdx+0C0h]
0x18003a862  lea     rdx, [rbp+arg_10]
0x18003a866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a86b  cmp     [rbp+arg_10], r14w
0x18003a870  jz      short loc_18003A876
0x18003a872  bts     esi, 1Fh
0x18003a876  mov     edx, esi; unsigned int
0x18003a878  mov     rcx, rdi; this
0x18003a87b  call    ?SectionDaysOfMonth@TaskXmlWriter@@QEAAJK@Z; TaskXmlWriter::SectionDaysOfMonth(ulong)
0x18003a880  mov     esi, eax
0x18003a882  test    eax, eax
0x18003a884  js      short loc_18003A8D2
0x18003a886  mov     [rbp+arg_18], r14w
0x18003a88b  mov     rcx, [rbp+var_18]
0x18003a88f  mov     rax, [rcx]
0x18003a892  lea     rdx, [rbp+arg_18]
0x18003a896  mov     rax, [rax+0B0h]
0x18003a89d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a8a2  mov     esi, eax
0x18003a8a4  test    eax, eax
0x18003a8a6  js      short loc_18003A8D2
0x18003a8a8  movsx   edx, [rbp+arg_18]; unsigned int
0x18003a8ac  mov     rcx, rdi; this
0x18003a8af  call    ?SectionMonths@TaskXmlWriter@@QEAAJK@Z; TaskXmlWriter::SectionMonths(ulong)
0x18003a8b4  mov     esi, eax
0x18003a8b6  test    eax, eax
0x18003a8b8  js      short loc_18003A8D2
0x18003a8ba  mov     rcx, rdi
0x18003a8bd  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x18003a8c2  mov     esi, eax
0x18003a8c4  test    eax, eax
0x18003a8c6  js      short loc_18003A8D2
0x18003a8c8  mov     rcx, rdi
0x18003a8cb  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x18003a8d0  mov     esi, eax
0x18003a8d2  mov     rcx, [rbp+bstrString]; bstrString
0x18003a8d6  call    cs:__imp_SysFreeString
0x18003a8dd  nop     dword ptr [rax+rax+00h]
0x18003a8e2  nop
0x18003a8e3  lea     rcx, [rbp+var_18]
0x18003a8e7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003a8ec  nop
0x18003a8ed  mov     rcx, [rbp+pbstr]; bstrString
0x18003a8f1  call    cs:__imp_SysFreeString
0x18003a8f8  nop     dword ptr [rax+rax+00h]
0x18003a8fd  nop
0x18003a8fe  mov     rcx, rbx
0x18003a901  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003a906  mov     eax, esi
0x18003a908  add     rsp, 40h
0x18003a90c  pop     r14
0x18003a90e  pop     rdi
0x18003a90f  pop     rsi
0x18003a910  pop     rbx
0x18003a911  pop     rbp
0x18003a912  retn
```
