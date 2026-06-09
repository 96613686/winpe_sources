# WriteDailyTrigger(TaskXmlWriter &,JobTriggerPtr)

- ea: `0x180001924`
- end: `0x180001af9`
- name: `?WriteDailyTrigger@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z`
- size: `469`
- prototype: `int __high(struct TaskXmlWriter *, struct JobTriggerPtr)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013f20`

## callees

- `0x1800017f0`
- `0x180001864`
- `0x1800018f4`
- `0x180001924`
- `0x180001f90`
- `0x18000247c`
- `0x180003840`
- `0x180003d1c`
- `0x1800136e0`
- `0x1800138e0`
- `0x180054010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180001a15`
- `OLEAUT32!__imp_SysFreeString` at `0x180001a9b`
- `OLEAUT32!__imp_SysFreeString` at `0x180001ac8`
- `OLEAUT32!__imp_SysFreeString` at `0x180001add`
- `OLEAUT32!__imp_SysFreeString` at `0x180001a15`
- `OLEAUT32!__imp_SysFreeString` at `0x180001a9b`
- `OLEAUT32!__imp_SysFreeString` at `0x180001ac8`
- `OLEAUT32!__imp_SysFreeString` at `0x180001add`
- `OLEAUT32!__imp_SysStringLen` at `0x180001963`
- `OLEAUT32!__imp_SysStringLen` at `0x1800019f0`
- `OLEAUT32!__imp_SysStringLen` at `0x180001963`
- `OLEAUT32!__imp_SysStringLen` at `0x1800019f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WriteDailyTrigger(unsigned int *a1, const struct JobTriggerPtr *a2)
{
  int started; // eax
  int v5; // esi
  __int64 *v6; // rax
  BSTR bstrString; // [rsp+20h] [rbp-20h] BYREF
  __int64 v9; // [rsp+28h] [rbp-18h] BYREF
  _BYTE v10[16]; // [rsp+30h] [rbp-10h] BYREF
  __int16 v11; // [rsp+80h] [rbp+40h] BYREF
  BSTR pbstr; // [rsp+88h] [rbp+48h] BYREF

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
    v6 = (__int64 *)JobTriggerPtr::JobTriggerPtr((JobTriggerPtr *)v10, a2);
    v5 = WriteBaseTriggerProperties((int *)a1, v6);
    if ( v5 >= 0 )
    {
      DailyTriggerPtr::DailyTriggerPtr((DailyTriggerPtr *)&v9, a2);
      bstrString = 0;
      if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v9 + 176LL))(v9, &bstrString) >= 0 )
      {
        if ( bstrString )
        {
          if ( SysStringLen(bstrString) )
          {
            v5 = TaskXmlWriter::Element(a1, 26, (__int64)bstrString);
            if ( v5 < 0 )
            {
              SysFreeString(bstrString);
              if ( v9 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
              goto LABEL_25;
            }
          }
        }
      }
      v5 = TaskXmlWriter::StartElement((int *)a1, (struct IErrorInfo *)0x28);
      if ( v5 >= 0 )
      {
        v11 = 0;
        if ( (*(int (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v9 + 160LL))(v9, &v11) < 0
          || v11 <= 0
          || (v5 = TaskXmlWriter::ElementInt(a1, 41, (unsigned int)v11), v5 >= 0) )
        {
          v5 = TaskXmlWriter::EndElement((__int64)a1);
          if ( v5 < 0 )
          {
            SysFreeString(bstrString);
            if ( v9 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
            goto LABEL_25;
          }
          v5 = TaskXmlWriter::EndElement((__int64)a1);
        }
      }
      SysFreeString(bstrString);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
    }
  }
LABEL_25:
  SysFreeString(pbstr);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)a2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180001924  mov     [rsp-28h+arg_8], rdx
0x180001929  push    rbp
0x18000192a  push    rbx
0x18000192b  push    rsi
0x18000192c  push    rdi
0x18000192d  push    r14
0x18000192f  mov     rbp, rsp
0x180001932  sub     rsp, 40h
0x180001936  mov     rdi, rdx
0x180001939  mov     rbx, rcx
0x18000193c  xor     r14d, r14d
0x18000193f  mov     [rbp+pbstr], r14
0x180001943  mov     rcx, [rdx]
0x180001946  mov     rax, [rcx]
0x180001949  lea     rdx, [rbp+pbstr]
0x18000194d  mov     rax, [rax+40h]
0x180001951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001956  test    eax, eax
0x180001958  js      short loc_180001983
0x18000195a  mov     rcx, [rbp+pbstr]; pbstr
0x18000195e  test    rcx, rcx
0x180001961  jz      short loc_180001983
0x180001963  call    cs:__imp_SysStringLen
0x180001969  test    eax, eax
0x18000196b  jz      short loc_180001983
0x18000196d  mov     r9, [rbp+pbstr]
0x180001971  lea     edx, [r14+27h]
0x180001975  lea     r8d, [r14+6Dh]
0x180001979  mov     rcx, rbx
0x18000197c  call    ?StartElementWithAttribute@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@0PEBG@Z; TaskXmlWriter::StartElementWithAttribute(TaskXmlNodeId,TaskXmlNodeId,ushort const *)
0x180001981  jmp     short loc_180001990
0x180001983  mov     edx, 27h ; '''
0x180001988  mov     rcx, rbx
0x18000198b  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x180001990  mov     esi, eax
0x180001992  test    eax, eax
0x180001994  js      loc_180001AD9
0x18000199a  mov     rdx, rdi; struct JobTriggerPtr *
0x18000199d  lea     rcx, [rbp+var_10]; this
0x1800019a1  call    ??0JobTriggerPtr@@QEAA@AEBV0@@Z; JobTriggerPtr::JobTriggerPtr(JobTriggerPtr const &)
0x1800019a6  mov     rdx, rax
0x1800019a9  mov     rcx, rbx
0x1800019ac  call    ?WriteBaseTriggerProperties@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z; WriteBaseTriggerProperties(TaskXmlWriter &,JobTriggerPtr)
0x1800019b1  mov     esi, eax
0x1800019b3  test    eax, eax
0x1800019b5  js      loc_180001AD9
0x1800019bb  mov     rdx, rdi; struct JobTriggerPtr *
0x1800019be  lea     rcx, [rbp+var_18]; this
0x1800019c2  call    ??0DailyTriggerPtr@@QEAA@AEBVJobTriggerPtr@@@Z; DailyTriggerPtr::DailyTriggerPtr(JobTriggerPtr const &)
0x1800019c7  nop
0x1800019c8  mov     [rbp+bstrString], r14
0x1800019cc  mov     rcx, [rbp+var_18]
0x1800019d0  mov     rax, [rcx]
0x1800019d3  lea     rdx, [rbp+bstrString]
0x1800019d7  mov     rax, [rax+0B0h]
0x1800019de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019e3  test    eax, eax
0x1800019e5  js      short loc_180001A37
0x1800019e7  mov     rcx, [rbp+bstrString]; pbstr
0x1800019eb  test    rcx, rcx
0x1800019ee  jz      short loc_180001A37
0x1800019f0  call    cs:__imp_SysStringLen
0x1800019f6  test    eax, eax
0x1800019f8  jz      short loc_180001A37
0x1800019fa  mov     r8, [rbp+bstrString]
0x1800019fe  mov     edx, 1Ah
0x180001a03  mov     rcx, rbx
0x180001a06  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180001a0b  mov     esi, eax
0x180001a0d  test    eax, eax
0x180001a0f  jns     short loc_180001A37
0x180001a11  mov     rcx, [rbp+bstrString]; bstrString
0x180001a15  call    cs:__imp_SysFreeString
0x180001a1b  nop
0x180001a1c  mov     rcx, [rbp+var_18]
0x180001a20  test    rcx, rcx
0x180001a23  jz      short loc_180001A32
0x180001a25  mov     rdx, [rcx]
0x180001a28  mov     rax, [rdx+10h]
0x180001a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a31  nop
0x180001a32  jmp     loc_180001AD9
0x180001a37  mov     edx, 28h ; '('
0x180001a3c  mov     rcx, rbx
0x180001a3f  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x180001a44  mov     esi, eax
0x180001a46  test    eax, eax
0x180001a48  js      short loc_180001AC4
0x180001a4a  mov     [rbp+arg_10], r14w
0x180001a4f  mov     rcx, [rbp+var_18]
0x180001a53  mov     rax, [rcx]
0x180001a56  lea     rdx, [rbp+arg_10]
0x180001a5a  mov     rax, [rax+0A0h]
0x180001a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a66  test    eax, eax
0x180001a68  js      short loc_180001A89
0x180001a6a  movsx   eax, [rbp+arg_10]
0x180001a6e  test    ax, ax
0x180001a71  jle     short loc_180001A89
0x180001a73  mov     r8d, eax
0x180001a76  mov     edx, 29h ; ')'
0x180001a7b  mov     rcx, rbx
0x180001a7e  call    ?ElementInt@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@H@Z; TaskXmlWriter::ElementInt(TaskXmlNodeId,int)
0x180001a83  mov     esi, eax
0x180001a85  test    eax, eax
0x180001a87  js      short loc_180001AC4
0x180001a89  mov     rcx, rbx
0x180001a8c  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x180001a91  mov     esi, eax
0x180001a93  test    eax, eax
0x180001a95  jns     short loc_180001ABA
0x180001a97  mov     rcx, [rbp+bstrString]; bstrString
0x180001a9b  call    cs:__imp_SysFreeString
0x180001aa1  nop
0x180001aa2  mov     rcx, [rbp+var_18]
0x180001aa6  test    rcx, rcx
0x180001aa9  jz      short loc_180001AB8
0x180001aab  mov     rdx, [rcx]
0x180001aae  mov     rax, [rdx+10h]
0x180001ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ab7  nop
0x180001ab8  jmp     short loc_180001AD9
0x180001aba  mov     rcx, rbx
0x180001abd  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x180001ac2  mov     esi, eax
0x180001ac4  mov     rcx, [rbp+bstrString]; bstrString
0x180001ac8  call    cs:__imp_SysFreeString
0x180001ace  nop
0x180001acf  lea     rcx, [rbp+var_18]
0x180001ad3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001ad8  nop
0x180001ad9  mov     rcx, [rbp+pbstr]; bstrString
0x180001add  call    cs:__imp_SysFreeString
0x180001ae3  nop
0x180001ae4  mov     rcx, rdi
0x180001ae7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001aec  mov     eax, esi
0x180001aee  add     rsp, 40h
0x180001af2  pop     r14
0x180001af4  pop     rdi
0x180001af5  pop     rsi
0x180001af6  pop     rbx
0x180001af7  pop     rbp
0x180001af8  retn
```
