# WriteMonthlyDOWTrigger(TaskXmlWriter &,JobTriggerPtr)

- ea: `0x18003e830`
- end: `0x18003eb81`
- name: `?WriteMonthlyDOWTrigger@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z`
- size: `849`
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
- `0x18003b51c`
- `0x18003e830`
- `0x18004b430`
- `0x18004b494`
- `0x18004b4f8`
- `0x180054010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18003e8a6`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e986`
- `OLEAUT32!__imp_SysFreeString` at `0x18003eb50`
- `OLEAUT32!__imp_SysFreeString` at `0x18003eb65`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e8a6`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e986`
- `OLEAUT32!__imp_SysFreeString` at `0x18003eb50`
- `OLEAUT32!__imp_SysFreeString` at `0x18003eb65`
- `OLEAUT32!__imp_SysStringLen` at `0x18003e86f`
- `OLEAUT32!__imp_SysStringLen` at `0x18003e961`
- `OLEAUT32!__imp_SysStringLen` at `0x18003e86f`
- `OLEAUT32!__imp_SysStringLen` at `0x18003e961`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WriteMonthlyDOWTrigger(unsigned int *a1, const struct JobTriggerPtr *a2)
{
  int started; // eax
  int v5; // esi
  __int64 *v7; // rax
  int v8; // eax
  int v9; // eax
  unsigned int v10; // edx
  int v11; // eax
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // [rsp+20h] [rbp-50h] BYREF
  BSTR pbstr; // [rsp+28h] [rbp-48h] BYREF
  BSTR bstrString; // [rsp+30h] [rbp-40h] BYREF
  void **pExceptionObject; // [rsp+38h] [rbp-38h] BYREF
  char v18; // [rsp+40h] [rbp-30h]
  __int64 *v19; // [rsp+48h] [rbp-28h]
  __int64 v20; // [rsp+50h] [rbp-20h]
  __int64 v21; // [rsp+58h] [rbp-18h]
  int v22; // [rsp+60h] [rbp-10h]
  __int64 v23; // [rsp+64h] [rbp-Ch]
  __int16 v24; // [rsp+B0h] [rbp+40h] BYREF
  __int16 v25; // [rsp+B8h] [rbp+48h] BYREF

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
  if ( started < 0 )
    goto LABEL_7;
  v7 = (__int64 *)JobTriggerPtr::JobTriggerPtr((JobTriggerPtr *)&v24, a2);
  v5 = WriteBaseTriggerProperties((int *)a1, v7);
  if ( v5 < 0 )
    goto LABEL_7;
  v14 = 0;
  v8 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))a2)(
         *(_QWORD *)a2,
         &GUID_77d025a3_90fa_43aa_b52e_cda5499b946a,
         &v14);
  if ( v8 < 0 )
  {
    v18 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v19 = &qword_180077320;
    v20 = 0;
    v21 = 0;
    v22 = v8;
    v23 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  bstrString = 0;
  if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v14 + 224LL))(v14, &bstrString) >= 0 )
  {
    if ( bstrString )
    {
      if ( SysStringLen(bstrString) )
      {
        v5 = TaskXmlWriter::Element(a1, 26, (__int64)bstrString);
        if ( v5 < 0 )
          goto LABEL_15;
      }
    }
  }
  v5 = TaskXmlWriter::StartElement((int *)a1, (struct IErrorInfo *)0x36);
  if ( v5 < 0 )
    goto LABEL_15;
  v25 = 0;
  (*(void (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v14 + 208LL))(v14, &v25);
  v24 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v14 + 176LL))(v14, &v24);
  if ( v9 < 0 )
  {
    v18 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v19 = &qword_180077320;
    v20 = 0;
    v21 = 0;
    v22 = v9;
    v23 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v10 = v24;
  if ( v25 )
    v10 = v24 | 0x10;
  v5 = TaskXmlWriter::SectionWeeks((TaskXmlWriter *)a1, v10);
  if ( v5 < 0 )
    goto LABEL_15;
  v24 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v14 + 160LL))(v14, &v24);
  if ( v11 < 0 )
  {
    v18 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v19 = &qword_180077320;
    v20 = 0;
    v21 = 0;
    v22 = v11;
    v23 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v5 = TaskXmlWriter::SectionDaysOfWeek((TaskXmlWriter *)a1, v24);
  if ( v5 < 0 )
    goto LABEL_15;
  v24 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v14 + 192LL))(v14, &v24);
  if ( v12 < 0 )
  {
    v18 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v19 = &qword_180077320;
    v20 = 0;
    v21 = 0;
    v22 = v12;
    v23 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v5 = TaskXmlWriter::SectionMonths((TaskXmlWriter *)a1, v24);
  if ( v5 < 0 || (v5 = TaskXmlWriter::EndElement((__int64)a1), v5 < 0) )
  {
LABEL_15:
    SysFreeString(bstrString);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
LABEL_7:
    SysFreeString(pbstr);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)a2);
    return (unsigned int)v5;
  }
  v13 = TaskXmlWriter::EndElement((__int64)a1);
  SysFreeString(bstrString);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
  SysFreeString(pbstr);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)a2);
  return v13;
}

```

## disassembly

```asm
0x18003e830  mov     [rsp-28h+arg_8], rdx
0x18003e835  push    rbp
0x18003e836  push    rbx
0x18003e837  push    rsi
0x18003e838  push    rdi
0x18003e839  push    r14
0x18003e83b  mov     rbp, rsp
0x18003e83e  sub     rsp, 70h
0x18003e842  mov     rdi, rdx
0x18003e845  mov     rbx, rcx
0x18003e848  xor     r14d, r14d
0x18003e84b  mov     [rbp+pbstr], r14
0x18003e84f  mov     rcx, [rdx]
0x18003e852  mov     rax, [rcx]
0x18003e855  lea     rdx, [rbp+pbstr]
0x18003e859  mov     rax, [rax+40h]
0x18003e85d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e862  test    eax, eax
0x18003e864  js      short loc_18003E88F
0x18003e866  mov     rcx, [rbp+pbstr]; pbstr
0x18003e86a  test    rcx, rcx
0x18003e86d  jz      short loc_18003E88F
0x18003e86f  call    cs:__imp_SysStringLen
0x18003e875  test    eax, eax
0x18003e877  jz      short loc_18003E88F
0x18003e879  mov     r9, [rbp+pbstr]
0x18003e87d  lea     edx, [r14+27h]
0x18003e881  lea     r8d, [r14+6Dh]
0x18003e885  mov     rcx, rbx
0x18003e888  call    ?StartElementWithAttribute@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@0PEBG@Z; TaskXmlWriter::StartElementWithAttribute(TaskXmlNodeId,TaskXmlNodeId,ushort const *)
0x18003e88d  jmp     short loc_18003E89C
0x18003e88f  mov     edx, 27h ; '''
0x18003e894  mov     rcx, rbx
0x18003e897  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x18003e89c  mov     esi, eax
0x18003e89e  test    eax, eax
0x18003e8a0  jns     short loc_18003E8BC
0x18003e8a2  mov     rcx, [rbp+pbstr]; bstrString
0x18003e8a6  call    cs:__imp_SysFreeString
0x18003e8ac  nop
0x18003e8ad  mov     rcx, rdi
0x18003e8b0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003e8b5  mov     eax, esi
0x18003e8b7  jmp     loc_18003EB76
0x18003e8bc  mov     rdx, rdi; struct JobTriggerPtr *
0x18003e8bf  lea     rcx, [rbp+arg_10]; this
0x18003e8c3  call    ??0JobTriggerPtr@@QEAA@AEBV0@@Z; JobTriggerPtr::JobTriggerPtr(JobTriggerPtr const &)
0x18003e8c8  mov     rdx, rax
0x18003e8cb  mov     rcx, rbx
0x18003e8ce  call    ?WriteBaseTriggerProperties@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z; WriteBaseTriggerProperties(TaskXmlWriter &,JobTriggerPtr)
0x18003e8d3  mov     esi, eax
0x18003e8d5  test    eax, eax
0x18003e8d7  js      short loc_18003E8A2
0x18003e8d9  mov     [rbp+var_50], r14
0x18003e8dd  mov     rcx, [rdi]
0x18003e8e0  mov     rax, [rcx]
0x18003e8e3  lea     r8, [rbp+var_50]
0x18003e8e7  lea     rdx, _GUID_77d025a3_90fa_43aa_b52e_cda5499b946a
0x18003e8ee  mov     rax, [rax]
0x18003e8f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e8f6  nop
0x18003e8f7  test    eax, eax
0x18003e8f9  jns     short loc_18003E939
0x18003e8fb  mov     [rbp+var_30], r14b
0x18003e8ff  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18003e906  mov     [rbp+pExceptionObject], rcx
0x18003e90a  lea     rcx, qword_180077320
0x18003e911  mov     [rbp+var_28], rcx
0x18003e915  mov     [rbp+var_20], r14
0x18003e919  mov     [rbp+var_18], r14
0x18003e91d  mov     [rbp+var_10], eax
0x18003e920  mov     [rbp+var_C], 0FFFFFFFFFFFFFFFFh
0x18003e928  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18003e92f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003e933  call    _CxxThrowException_0
0x18003e939  mov     [rbp+bstrString], r14
0x18003e93d  mov     rcx, [rbp+var_50]
0x18003e941  mov     rax, [rcx]
0x18003e944  lea     rdx, [rbp+bstrString]
0x18003e948  mov     rax, [rax+0E0h]
0x18003e94f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e954  test    eax, eax
0x18003e956  js      short loc_18003E99B
0x18003e958  mov     rcx, [rbp+bstrString]; pbstr
0x18003e95c  test    rcx, rcx
0x18003e95f  jz      short loc_18003E99B
0x18003e961  call    cs:__imp_SysStringLen
0x18003e967  test    eax, eax
0x18003e969  jz      short loc_18003E99B
0x18003e96b  mov     r8, [rbp+bstrString]
0x18003e96f  mov     edx, 1Ah
0x18003e974  mov     rcx, rbx
0x18003e977  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18003e97c  mov     esi, eax
0x18003e97e  test    eax, eax
0x18003e980  jns     short loc_18003E99B
0x18003e982  mov     rcx, [rbp+bstrString]; bstrString
0x18003e986  call    cs:__imp_SysFreeString
0x18003e98c  nop
0x18003e98d  lea     rcx, [rbp+var_50]
0x18003e991  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003e996  jmp     loc_18003E8A2
0x18003e99b  mov     edx, 36h ; '6'
0x18003e9a0  mov     rcx, rbx
0x18003e9a3  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x18003e9a8  mov     esi, eax
0x18003e9aa  test    eax, eax
0x18003e9ac  js      short loc_18003E982
0x18003e9ae  mov     [rbp+arg_18], r14w
0x18003e9b3  mov     rcx, [rbp+var_50]
0x18003e9b7  mov     rax, [rcx]
0x18003e9ba  lea     rdx, [rbp+arg_18]
0x18003e9be  mov     rax, [rax+0D0h]
0x18003e9c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e9ca  mov     [rbp+arg_10], r14w
0x18003e9cf  mov     rcx, [rbp+var_50]
0x18003e9d3  mov     rax, [rcx]
0x18003e9d6  lea     rdx, [rbp+arg_10]
0x18003e9da  mov     rax, [rax+0B0h]
0x18003e9e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e9e6  test    eax, eax
0x18003e9e8  jns     short loc_18003EA28
0x18003e9ea  mov     [rbp+var_30], r14b
0x18003e9ee  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18003e9f5  mov     [rbp+pExceptionObject], rcx
0x18003e9f9  lea     rcx, qword_180077320
0x18003ea00  mov     [rbp+var_28], rcx
0x18003ea04  mov     [rbp+var_20], r14
0x18003ea08  mov     [rbp+var_18], r14
0x18003ea0c  mov     [rbp+var_10], eax
0x18003ea0f  mov     [rbp+var_C], 0FFFFFFFFFFFFFFFFh
0x18003ea17  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18003ea1e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003ea22  call    _CxxThrowException_0
0x18003ea28  movsx   edx, [rbp+arg_10]
0x18003ea2c  cmp     [rbp+arg_18], r14w
0x18003ea31  jz      short loc_18003EA36
0x18003ea33  or      edx, 10h; unsigned int
0x18003ea36  mov     rcx, rbx; this
0x18003ea39  call    ?SectionWeeks@TaskXmlWriter@@QEAAJK@Z; TaskXmlWriter::SectionWeeks(ulong)
0x18003ea3e  mov     esi, eax
0x18003ea40  test    eax, eax
0x18003ea42  js      loc_18003E982
0x18003ea48  mov     [rbp+arg_10], r14w
0x18003ea4d  mov     rcx, [rbp+var_50]
0x18003ea51  mov     rax, [rcx]
0x18003ea54  lea     rdx, [rbp+arg_10]
0x18003ea58  mov     rax, [rax+0A0h]
0x18003ea5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea64  test    eax, eax
0x18003ea66  jns     short loc_18003EAA6
0x18003ea68  mov     [rbp+var_30], r14b
0x18003ea6c  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18003ea73  mov     [rbp+pExceptionObject], rcx
0x18003ea77  lea     rcx, qword_180077320
0x18003ea7e  mov     [rbp+var_28], rcx
0x18003ea82  mov     [rbp+var_20], r14
0x18003ea86  mov     [rbp+var_18], r14
0x18003ea8a  mov     [rbp+var_10], eax
0x18003ea8d  mov     [rbp+var_C], 0FFFFFFFFFFFFFFFFh
0x18003ea95  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18003ea9c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003eaa0  call    _CxxThrowException_0
0x18003eaa6  movsx   edx, [rbp+arg_10]; unsigned int
0x18003eaaa  mov     rcx, rbx; this
0x18003eaad  call    ?SectionDaysOfWeek@TaskXmlWriter@@QEAAJK@Z; TaskXmlWriter::SectionDaysOfWeek(ulong)
0x18003eab2  mov     esi, eax
0x18003eab4  test    eax, eax
0x18003eab6  js      loc_18003E982
0x18003eabc  mov     [rbp+arg_10], r14w
0x18003eac1  mov     rcx, [rbp+var_50]
0x18003eac5  mov     rax, [rcx]
0x18003eac8  lea     rdx, [rbp+arg_10]
0x18003eacc  mov     rax, [rax+0C0h]
0x18003ead3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ead8  test    eax, eax
0x18003eada  jns     short loc_18003EB1A
0x18003eadc  mov     [rbp+var_30], r14b
0x18003eae0  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18003eae7  mov     [rbp+pExceptionObject], rcx
0x18003eaeb  lea     rcx, qword_180077320
0x18003eaf2  mov     [rbp+var_28], rcx
0x18003eaf6  mov     [rbp+var_20], r14
0x18003eafa  mov     [rbp+var_18], r14
0x18003eafe  mov     [rbp+var_10], eax
0x18003eb01  mov     [rbp+var_C], 0FFFFFFFFFFFFFFFFh
0x18003eb09  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18003eb10  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003eb14  call    _CxxThrowException_0
0x18003eb1a  movsx   edx, [rbp+arg_10]; unsigned int
0x18003eb1e  mov     rcx, rbx; this
0x18003eb21  call    ?SectionMonths@TaskXmlWriter@@QEAAJK@Z; TaskXmlWriter::SectionMonths(ulong)
0x18003eb26  mov     esi, eax
0x18003eb28  test    eax, eax
0x18003eb2a  js      loc_18003E982
0x18003eb30  mov     rcx, rbx
0x18003eb33  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x18003eb38  mov     esi, eax
0x18003eb3a  test    eax, eax
0x18003eb3c  js      loc_18003E982
0x18003eb42  mov     rcx, rbx
0x18003eb45  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x18003eb4a  mov     ebx, eax
0x18003eb4c  mov     rcx, [rbp+bstrString]; bstrString
0x18003eb50  call    cs:__imp_SysFreeString
0x18003eb56  nop
0x18003eb57  lea     rcx, [rbp+var_50]
0x18003eb5b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003eb60  nop
0x18003eb61  mov     rcx, [rbp+pbstr]; bstrString
0x18003eb65  call    cs:__imp_SysFreeString
0x18003eb6b  nop
0x18003eb6c  mov     rcx, rdi
0x18003eb6f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003eb74  mov     eax, ebx
0x18003eb76  add     rsp, 70h
0x18003eb7a  pop     r14
0x18003eb7c  pop     rdi
0x18003eb7d  pop     rsi
0x18003eb7e  pop     rbx
0x18003eb7f  pop     rbp
0x18003eb80  retn
```
