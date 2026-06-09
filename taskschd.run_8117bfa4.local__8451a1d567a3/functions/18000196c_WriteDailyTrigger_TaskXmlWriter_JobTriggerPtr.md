# WriteDailyTrigger(TaskXmlWriter &,JobTriggerPtr)

- ea: `0x18000196c`
- end: `0x180001b6a`
- name: `?WriteDailyTrigger@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z`
- size: `510`
- prototype: `int __high(struct TaskXmlWriter *, struct JobTriggerPtr)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014df0`

## callees

- `0x180001880`
- `0x1800018a8`
- `0x180001938`
- `0x18000196c`
- `0x180001fe4`
- `0x180002554`
- `0x180003a30`
- `0x180003f30`
- `0x1800145c0`
- `0x180014700`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180001a69`
- `OLEAUT32!__imp_SysFreeString` at `0x180001af9`
- `OLEAUT32!__imp_SysFreeString` at `0x180001b2c`
- `OLEAUT32!__imp_SysFreeString` at `0x180001b47`
- `OLEAUT32!__imp_SysFreeString` at `0x180001a69`
- `OLEAUT32!__imp_SysFreeString` at `0x180001af9`
- `OLEAUT32!__imp_SysFreeString` at `0x180001b2c`
- `OLEAUT32!__imp_SysFreeString` at `0x180001b47`
- `OLEAUT32!__imp_SysStringLen` at `0x1800019ab`
- `OLEAUT32!__imp_SysStringLen` at `0x180001a3e`
- `OLEAUT32!__imp_SysStringLen` at `0x1800019ab`
- `OLEAUT32!__imp_SysStringLen` at `0x180001a3e`

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
0x18000196c  mov     [rsp-28h+arg_8], rdx
0x180001971  push    rbp
0x180001972  push    rbx
0x180001973  push    rsi
0x180001974  push    rdi
0x180001975  push    r14
0x180001977  mov     rbp, rsp
0x18000197a  sub     rsp, 40h
0x18000197e  mov     rdi, rdx
0x180001981  mov     rbx, rcx
0x180001984  xor     r14d, r14d
0x180001987  mov     [rbp+pbstr], r14
0x18000198b  mov     rcx, [rdx]
0x18000198e  mov     rax, [rcx]
0x180001991  lea     rdx, [rbp+pbstr]
0x180001995  mov     rax, [rax+40h]
0x180001999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000199e  test    eax, eax
0x1800019a0  js      short loc_1800019D1
0x1800019a2  mov     rcx, [rbp+pbstr]; pbstr
0x1800019a6  test    rcx, rcx
0x1800019a9  jz      short loc_1800019D1
0x1800019ab  call    cs:__imp_SysStringLen
0x1800019b2  nop     dword ptr [rax+rax+00h]
0x1800019b7  test    eax, eax
0x1800019b9  jz      short loc_1800019D1
0x1800019bb  mov     r9, [rbp+pbstr]
0x1800019bf  lea     edx, [r14+27h]
0x1800019c3  lea     r8d, [r14+6Dh]
0x1800019c7  mov     rcx, rbx
0x1800019ca  call    ?StartElementWithAttribute@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@0PEBG@Z; TaskXmlWriter::StartElementWithAttribute(TaskXmlNodeId,TaskXmlNodeId,ushort const *)
0x1800019cf  jmp     short loc_1800019DE
0x1800019d1  mov     edx, 27h ; '''
0x1800019d6  mov     rcx, rbx
0x1800019d9  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x1800019de  mov     esi, eax
0x1800019e0  test    eax, eax
0x1800019e2  js      loc_180001B43
0x1800019e8  mov     rdx, rdi; struct JobTriggerPtr *
0x1800019eb  lea     rcx, [rbp+var_10]; this
0x1800019ef  call    ??0JobTriggerPtr@@QEAA@AEBV0@@Z; JobTriggerPtr::JobTriggerPtr(JobTriggerPtr const &)
0x1800019f4  mov     rdx, rax
0x1800019f7  mov     rcx, rbx
0x1800019fa  call    ?WriteBaseTriggerProperties@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z; WriteBaseTriggerProperties(TaskXmlWriter &,JobTriggerPtr)
0x1800019ff  mov     esi, eax
0x180001a01  test    eax, eax
0x180001a03  js      loc_180001B43
0x180001a09  mov     rdx, rdi; struct JobTriggerPtr *
0x180001a0c  lea     rcx, [rbp+var_18]; this
0x180001a10  call    ??0DailyTriggerPtr@@QEAA@AEBVJobTriggerPtr@@@Z; DailyTriggerPtr::DailyTriggerPtr(JobTriggerPtr const &)
0x180001a15  nop
0x180001a16  mov     [rbp+bstrString], r14
0x180001a1a  mov     rcx, [rbp+var_18]
0x180001a1e  mov     rax, [rcx]
0x180001a21  lea     rdx, [rbp+bstrString]
0x180001a25  mov     rax, [rax+0B0h]
0x180001a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a31  test    eax, eax
0x180001a33  js      short loc_180001A91
0x180001a35  mov     rcx, [rbp+bstrString]; pbstr
0x180001a39  test    rcx, rcx
0x180001a3c  jz      short loc_180001A91
0x180001a3e  call    cs:__imp_SysStringLen
0x180001a45  nop     dword ptr [rax+rax+00h]
0x180001a4a  test    eax, eax
0x180001a4c  jz      short loc_180001A91
0x180001a4e  mov     r8, [rbp+bstrString]
0x180001a52  mov     edx, 1Ah
0x180001a57  mov     rcx, rbx
0x180001a5a  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180001a5f  mov     esi, eax
0x180001a61  test    eax, eax
0x180001a63  jns     short loc_180001A91
0x180001a65  mov     rcx, [rbp+bstrString]; bstrString
0x180001a69  call    cs:__imp_SysFreeString
0x180001a70  nop     dword ptr [rax+rax+00h]
0x180001a75  nop
0x180001a76  mov     rcx, [rbp+var_18]
0x180001a7a  test    rcx, rcx
0x180001a7d  jz      short loc_180001A8C
0x180001a7f  mov     rdx, [rcx]
0x180001a82  mov     rax, [rdx+10h]
0x180001a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a8b  nop
0x180001a8c  jmp     loc_180001B43
0x180001a91  mov     edx, 28h ; '('
0x180001a96  mov     rcx, rbx
0x180001a99  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x180001a9e  mov     esi, eax
0x180001aa0  test    eax, eax
0x180001aa2  js      loc_180001B28
0x180001aa8  mov     [rbp+arg_10], r14w
0x180001aad  mov     rcx, [rbp+var_18]
0x180001ab1  mov     rax, [rcx]
0x180001ab4  lea     rdx, [rbp+arg_10]
0x180001ab8  mov     rax, [rax+0A0h]
0x180001abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ac4  test    eax, eax
0x180001ac6  js      short loc_180001AE7
0x180001ac8  movsx   eax, [rbp+arg_10]
0x180001acc  test    ax, ax
0x180001acf  jle     short loc_180001AE7
0x180001ad1  mov     r8d, eax
0x180001ad4  mov     edx, 29h ; ')'
0x180001ad9  mov     rcx, rbx
0x180001adc  call    ?ElementInt@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@H@Z; TaskXmlWriter::ElementInt(TaskXmlNodeId,int)
0x180001ae1  mov     esi, eax
0x180001ae3  test    eax, eax
0x180001ae5  js      short loc_180001B28
0x180001ae7  mov     rcx, rbx
0x180001aea  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x180001aef  mov     esi, eax
0x180001af1  test    eax, eax
0x180001af3  jns     short loc_180001B1E
0x180001af5  mov     rcx, [rbp+bstrString]; bstrString
0x180001af9  call    cs:__imp_SysFreeString
0x180001b00  nop     dword ptr [rax+rax+00h]
0x180001b05  nop
0x180001b06  mov     rcx, [rbp+var_18]
0x180001b0a  test    rcx, rcx
0x180001b0d  jz      short loc_180001B1C
0x180001b0f  mov     rdx, [rcx]
0x180001b12  mov     rax, [rdx+10h]
0x180001b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b1b  nop
0x180001b1c  jmp     short loc_180001B43
0x180001b1e  mov     rcx, rbx
0x180001b21  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x180001b26  mov     esi, eax
0x180001b28  mov     rcx, [rbp+bstrString]; bstrString
0x180001b2c  call    cs:__imp_SysFreeString
0x180001b33  nop     dword ptr [rax+rax+00h]
0x180001b38  nop
0x180001b39  lea     rcx, [rbp+var_18]
0x180001b3d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001b42  nop
0x180001b43  mov     rcx, [rbp+pbstr]; bstrString
0x180001b47  call    cs:__imp_SysFreeString
0x180001b4e  nop     dword ptr [rax+rax+00h]
0x180001b53  nop
0x180001b54  mov     rcx, rdi
0x180001b57  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001b5c  mov     eax, esi
0x180001b5e  add     rsp, 40h
0x180001b62  pop     r14
0x180001b64  pop     rdi
0x180001b65  pop     rsi
0x180001b66  pop     rbx
0x180001b67  pop     rbp
0x180001b68  retn
```
