# WriteMonthlyDOWTrigger(TaskXmlWriter &,JobTriggerPtr)

- ea: `0x180041d90`
- end: `0x180042106`
- name: `?WriteMonthlyDOWTrigger@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z`
- size: `886`
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
- `0x18003e88c`
- `0x180041d90`
- `0x18004f018`
- `0x18004f080`
- `0x18004f0e8`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180041e0c`
- `OLEAUT32!__imp_SysFreeString` at `0x180041ef8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800420c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800420e3`
- `OLEAUT32!__imp_SysFreeString` at `0x180041e0c`
- `OLEAUT32!__imp_SysFreeString` at `0x180041ef8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800420c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800420e3`
- `OLEAUT32!__imp_SysStringLen` at `0x180041dcf`
- `OLEAUT32!__imp_SysStringLen` at `0x180041ecd`
- `OLEAUT32!__imp_SysStringLen` at `0x180041dcf`
- `OLEAUT32!__imp_SysStringLen` at `0x180041ecd`

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
    v19 = &qword_18007B2F0;
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
    v19 = &qword_18007B2F0;
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
    v19 = &qword_18007B2F0;
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
    v19 = &qword_18007B2F0;
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
0x180041d90  mov     [rsp-28h+arg_8], rdx
0x180041d95  push    rbp
0x180041d96  push    rbx
0x180041d97  push    rsi
0x180041d98  push    rdi
0x180041d99  push    r14
0x180041d9b  mov     rbp, rsp
0x180041d9e  sub     rsp, 70h
0x180041da2  mov     rdi, rdx
0x180041da5  mov     rbx, rcx
0x180041da8  xor     r14d, r14d
0x180041dab  mov     [rbp+pbstr], r14
0x180041daf  mov     rcx, [rdx]
0x180041db2  mov     rax, [rcx]
0x180041db5  lea     rdx, [rbp+pbstr]
0x180041db9  mov     rax, [rax+40h]
0x180041dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041dc2  test    eax, eax
0x180041dc4  js      short loc_180041DF5
0x180041dc6  mov     rcx, [rbp+pbstr]; pbstr
0x180041dca  test    rcx, rcx
0x180041dcd  jz      short loc_180041DF5
0x180041dcf  call    cs:__imp_SysStringLen
0x180041dd6  nop     dword ptr [rax+rax+00h]
0x180041ddb  test    eax, eax
0x180041ddd  jz      short loc_180041DF5
0x180041ddf  mov     r9, [rbp+pbstr]
0x180041de3  lea     edx, [r14+27h]
0x180041de7  lea     r8d, [r14+6Dh]
0x180041deb  mov     rcx, rbx
0x180041dee  call    ?StartElementWithAttribute@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@0PEBG@Z; TaskXmlWriter::StartElementWithAttribute(TaskXmlNodeId,TaskXmlNodeId,ushort const *)
0x180041df3  jmp     short loc_180041E02
0x180041df5  mov     edx, 27h ; '''
0x180041dfa  mov     rcx, rbx
0x180041dfd  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x180041e02  mov     esi, eax
0x180041e04  test    eax, eax
0x180041e06  jns     short loc_180041E28
0x180041e08  mov     rcx, [rbp+pbstr]; bstrString
0x180041e0c  call    cs:__imp_SysFreeString
0x180041e13  nop     dword ptr [rax+rax+00h]
0x180041e18  nop
0x180041e19  mov     rcx, rdi
0x180041e1c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180041e21  mov     eax, esi
0x180041e23  jmp     loc_1800420FA
0x180041e28  mov     rdx, rdi; struct JobTriggerPtr *
0x180041e2b  lea     rcx, [rbp+arg_10]; this
0x180041e2f  call    ??0JobTriggerPtr@@QEAA@AEBV0@@Z; JobTriggerPtr::JobTriggerPtr(JobTriggerPtr const &)
0x180041e34  mov     rdx, rax
0x180041e37  mov     rcx, rbx
0x180041e3a  call    ?WriteBaseTriggerProperties@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z; WriteBaseTriggerProperties(TaskXmlWriter &,JobTriggerPtr)
0x180041e3f  mov     esi, eax
0x180041e41  test    eax, eax
0x180041e43  js      short loc_180041E08
0x180041e45  mov     [rbp+var_50], r14
0x180041e49  mov     rcx, [rdi]
0x180041e4c  mov     rax, [rcx]
0x180041e4f  lea     r8, [rbp+var_50]
0x180041e53  lea     rdx, _GUID_77d025a3_90fa_43aa_b52e_cda5499b946a
0x180041e5a  mov     rax, [rax]
0x180041e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e62  nop
0x180041e63  test    eax, eax
0x180041e65  jns     short loc_180041EA5
0x180041e67  mov     [rbp+var_30], r14b
0x180041e6b  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180041e72  mov     [rbp+pExceptionObject], rcx
0x180041e76  lea     rcx, qword_18007B2F0
0x180041e7d  mov     [rbp+var_28], rcx
0x180041e81  mov     [rbp+var_20], r14
0x180041e85  mov     [rbp+var_18], r14
0x180041e89  mov     [rbp+var_10], eax
0x180041e8c  mov     [rbp+var_C], 0FFFFFFFFFFFFFFFFh
0x180041e94  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180041e9b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180041e9f  call    _CxxThrowException_0
0x180041ea5  mov     [rbp+bstrString], r14
0x180041ea9  mov     rcx, [rbp+var_50]
0x180041ead  mov     rax, [rcx]
0x180041eb0  lea     rdx, [rbp+bstrString]
0x180041eb4  mov     rax, [rax+0E0h]
0x180041ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041ec0  test    eax, eax
0x180041ec2  js      short loc_180041F13
0x180041ec4  mov     rcx, [rbp+bstrString]; pbstr
0x180041ec8  test    rcx, rcx
0x180041ecb  jz      short loc_180041F13
0x180041ecd  call    cs:__imp_SysStringLen
0x180041ed4  nop     dword ptr [rax+rax+00h]
0x180041ed9  test    eax, eax
0x180041edb  jz      short loc_180041F13
0x180041edd  mov     r8, [rbp+bstrString]
0x180041ee1  mov     edx, 1Ah
0x180041ee6  mov     rcx, rbx
0x180041ee9  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180041eee  mov     esi, eax
0x180041ef0  test    eax, eax
0x180041ef2  jns     short loc_180041F13
0x180041ef4  mov     rcx, [rbp+bstrString]; bstrString
0x180041ef8  call    cs:__imp_SysFreeString
0x180041eff  nop     dword ptr [rax+rax+00h]
0x180041f04  nop
0x180041f05  lea     rcx, [rbp+var_50]
0x180041f09  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180041f0e  jmp     loc_180041E08
0x180041f13  mov     edx, 36h ; '6'
0x180041f18  mov     rcx, rbx
0x180041f1b  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x180041f20  mov     esi, eax
0x180041f22  test    eax, eax
0x180041f24  js      short loc_180041EF4
0x180041f26  mov     [rbp+arg_18], r14w
0x180041f2b  mov     rcx, [rbp+var_50]
0x180041f2f  mov     rax, [rcx]
0x180041f32  lea     rdx, [rbp+arg_18]
0x180041f36  mov     rax, [rax+0D0h]
0x180041f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f42  mov     [rbp+arg_10], r14w
0x180041f47  mov     rcx, [rbp+var_50]
0x180041f4b  mov     rax, [rcx]
0x180041f4e  lea     rdx, [rbp+arg_10]
0x180041f52  mov     rax, [rax+0B0h]
0x180041f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f5e  test    eax, eax
0x180041f60  jns     short loc_180041FA0
0x180041f62  mov     [rbp+var_30], r14b
0x180041f66  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180041f6d  mov     [rbp+pExceptionObject], rcx
0x180041f71  lea     rcx, qword_18007B2F0
0x180041f78  mov     [rbp+var_28], rcx
0x180041f7c  mov     [rbp+var_20], r14
0x180041f80  mov     [rbp+var_18], r14
0x180041f84  mov     [rbp+var_10], eax
0x180041f87  mov     [rbp+var_C], 0FFFFFFFFFFFFFFFFh
0x180041f8f  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180041f96  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180041f9a  call    _CxxThrowException_0
0x180041fa0  movsx   edx, [rbp+arg_10]
0x180041fa4  cmp     [rbp+arg_18], r14w
0x180041fa9  jz      short loc_180041FAE
0x180041fab  or      edx, 10h; unsigned int
0x180041fae  mov     rcx, rbx; this
0x180041fb1  call    ?SectionWeeks@TaskXmlWriter@@QEAAJK@Z; TaskXmlWriter::SectionWeeks(ulong)
0x180041fb6  mov     esi, eax
0x180041fb8  test    eax, eax
0x180041fba  js      loc_180041EF4
0x180041fc0  mov     [rbp+arg_10], r14w
0x180041fc5  mov     rcx, [rbp+var_50]
0x180041fc9  mov     rax, [rcx]
0x180041fcc  lea     rdx, [rbp+arg_10]
0x180041fd0  mov     rax, [rax+0A0h]
0x180041fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041fdc  test    eax, eax
0x180041fde  jns     short loc_18004201E
0x180041fe0  mov     [rbp+var_30], r14b
0x180041fe4  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180041feb  mov     [rbp+pExceptionObject], rcx
0x180041fef  lea     rcx, qword_18007B2F0
0x180041ff6  mov     [rbp+var_28], rcx
0x180041ffa  mov     [rbp+var_20], r14
0x180041ffe  mov     [rbp+var_18], r14
0x180042002  mov     [rbp+var_10], eax
0x180042005  mov     [rbp+var_C], 0FFFFFFFFFFFFFFFFh
0x18004200d  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180042014  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180042018  call    _CxxThrowException_0
0x18004201e  movsx   edx, [rbp+arg_10]; unsigned int
0x180042022  mov     rcx, rbx; this
0x180042025  call    ?SectionDaysOfWeek@TaskXmlWriter@@QEAAJK@Z; TaskXmlWriter::SectionDaysOfWeek(ulong)
0x18004202a  mov     esi, eax
0x18004202c  test    eax, eax
0x18004202e  js      loc_180041EF4
0x180042034  mov     [rbp+arg_10], r14w
0x180042039  mov     rcx, [rbp+var_50]
0x18004203d  mov     rax, [rcx]
0x180042040  lea     rdx, [rbp+arg_10]
0x180042044  mov     rax, [rax+0C0h]
0x18004204b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042050  test    eax, eax
0x180042052  jns     short loc_180042092
0x180042054  mov     [rbp+var_30], r14b
0x180042058  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18004205f  mov     [rbp+pExceptionObject], rcx
0x180042063  lea     rcx, qword_18007B2F0
0x18004206a  mov     [rbp+var_28], rcx
0x18004206e  mov     [rbp+var_20], r14
0x180042072  mov     [rbp+var_18], r14
0x180042076  mov     [rbp+var_10], eax
0x180042079  mov     [rbp+var_C], 0FFFFFFFFFFFFFFFFh
0x180042081  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180042088  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004208c  call    _CxxThrowException_0
0x180042092  movsx   edx, [rbp+arg_10]; unsigned int
0x180042096  mov     rcx, rbx; this
0x180042099  call    ?SectionMonths@TaskXmlWriter@@QEAAJK@Z; TaskXmlWriter::SectionMonths(ulong)
0x18004209e  mov     esi, eax
0x1800420a0  test    eax, eax
0x1800420a2  js      loc_180041EF4
0x1800420a8  mov     rcx, rbx
0x1800420ab  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x1800420b0  mov     esi, eax
0x1800420b2  test    eax, eax
0x1800420b4  js      loc_180041EF4
0x1800420ba  mov     rcx, rbx
0x1800420bd  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x1800420c2  mov     ebx, eax
0x1800420c4  mov     rcx, [rbp+bstrString]; bstrString
0x1800420c8  call    cs:__imp_SysFreeString
0x1800420cf  nop     dword ptr [rax+rax+00h]
0x1800420d4  nop
0x1800420d5  lea     rcx, [rbp+var_50]
0x1800420d9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800420de  nop
0x1800420df  mov     rcx, [rbp+pbstr]; bstrString
0x1800420e3  call    cs:__imp_SysFreeString
0x1800420ea  nop     dword ptr [rax+rax+00h]
0x1800420ef  nop
0x1800420f0  mov     rcx, rdi
0x1800420f3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800420f8  mov     eax, ebx
0x1800420fa  add     rsp, 70h
0x1800420fe  pop     r14
0x180042100  pop     rdi
0x180042101  pop     rsi
0x180042102  pop     rbx
0x180042103  pop     rbp
0x180042104  retn
```
