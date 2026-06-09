# WriteSessionStateChangeTrigger(TaskXmlWriter &,JobTriggerPtr)

- ea: `0x180001588`
- end: `0x1800017d8`
- name: `?WriteSessionStateChangeTrigger@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z`
- size: `592`
- prototype: `int __high(struct TaskXmlWriter *, struct JobTriggerPtr)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013f20`

## callees

- `0x1800014f8`
- `0x180001588`
- `0x1800017f0`
- `0x1800018f4`
- `0x180001f90`
- `0x180003840`
- `0x180003d1c`
- `0x1800136e0`
- `0x1800138e0`
- `0x180054010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180001763`
- `OLEAUT32!__imp_SysFreeString` at `0x18000176e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000178e`
- `OLEAUT32!__imp_SysFreeString` at `0x180001799`
- `OLEAUT32!__imp_SysFreeString` at `0x1800017ba`
- `OLEAUT32!__imp_SysFreeString` at `0x180001763`
- `OLEAUT32!__imp_SysFreeString` at `0x18000176e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000178e`
- `OLEAUT32!__imp_SysFreeString` at `0x180001799`
- `OLEAUT32!__imp_SysFreeString` at `0x1800017ba`
- `OLEAUT32!__imp_SysStringLen` at `0x1800015ca`
- `OLEAUT32!__imp_SysStringLen` at `0x1800016f1`
- `OLEAUT32!__imp_SysStringLen` at `0x18000173e`
- `OLEAUT32!__imp_SysStringLen` at `0x1800015ca`
- `OLEAUT32!__imp_SysStringLen` at `0x1800016f1`
- `OLEAUT32!__imp_SysStringLen` at `0x18000173e`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WriteSessionStateChangeTrigger(unsigned int *a1, const struct JobTriggerPtr *a2)
{
  int started; // eax
  int v5; // ebx
  __int64 *v6; // rax
  const wchar_t *v7; // r8
  int v8; // eax
  BSTR pbstr; // [rsp+20h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-18h] BYREF
  __int64 v12; // [rsp+30h] [rbp-10h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-8h] BYREF
  int v14; // [rsp+70h] [rbp+30h] BYREF
  BSTR v15; // [rsp+78h] [rbp+38h] BYREF

  pbstr = 0;
  if ( (*(int (__fastcall **)(_QWORD, BSTR *))(**(_QWORD **)a2 + 64LL))(*(_QWORD *)a2, &pbstr) >= 0
    && pbstr
    && SysStringLen(pbstr) )
  {
    started = TaskXmlWriter::StartElementWithAttribute(a1, 37, 109, (__int64)pbstr);
  }
  else
  {
    started = TaskXmlWriter::StartElement((int *)a1, (struct IErrorInfo *)0x25);
  }
  v5 = started;
  if ( started < 0 )
    goto LABEL_36;
  v6 = (__int64 *)JobTriggerPtr::JobTriggerPtr((JobTriggerPtr *)v13, a2);
  v5 = WriteBaseTriggerProperties((int *)a1, v6);
  if ( v5 < 0 )
    goto LABEL_36;
  SessionStateChangeTriggerPtr::SessionStateChangeTriggerPtr((SessionStateChangeTriggerPtr *)&v12, a2);
  v14 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 192LL))(v12, &v14);
  if ( v5 < 0 )
  {
LABEL_33:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
    goto LABEL_36;
  }
  switch ( v14 )
  {
    case 1:
      goto LABEL_20;
    case 2:
      v7 = L"ConsoleDisconnect";
      goto LABEL_21;
    case 3:
      v7 = L"RemoteConnect";
      goto LABEL_21;
    case 4:
      v7 = L"RemoteDisconnect";
      goto LABEL_21;
    case 7:
      v7 = L"SessionLock";
      goto LABEL_21;
  }
  if ( v14 != 8 )
  {
LABEL_20:
    v7 = L"ConsoleConnect";
    goto LABEL_21;
  }
  v7 = L"SessionUnlock";
LABEL_21:
  v8 = TaskXmlWriter::Element(a1, 38, (__int64)v7);
  if ( v8 < 0 )
  {
    v5 = v8;
    goto LABEL_33;
  }
  v15 = 0;
  if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v12 + 176LL))(v12, &v15) >= 0 )
  {
    if ( v15 )
    {
      if ( SysStringLen(v15) )
      {
        v5 = TaskXmlWriter::Element(a1, 36, (__int64)v15);
        if ( v5 < 0 )
        {
LABEL_32:
          SysFreeString(v15);
          goto LABEL_33;
        }
      }
    }
  }
  bstrString = 0;
  if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v12 + 160LL))(v12, &bstrString) >= 0 )
  {
    if ( bstrString )
    {
      if ( SysStringLen(bstrString) )
      {
        v5 = TaskXmlWriter::Element(a1, 22, (__int64)bstrString);
        if ( v5 < 0 )
        {
          SysFreeString(bstrString);
          goto LABEL_32;
        }
      }
    }
  }
  v5 = TaskXmlWriter::EndElement((__int64)a1);
  SysFreeString(bstrString);
  SysFreeString(v15);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
LABEL_36:
  SysFreeString(pbstr);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)a2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180001588  mov     [rsp-18h+arg_0], rbx
0x18000158d  mov     [rsp-18h+arg_8], rdx
0x180001592  push    rbp
0x180001593  push    rsi
0x180001594  push    rdi
0x180001595  mov     rbp, rsp
0x180001598  sub     rsp, 40h
0x18000159c  mov     rsi, rdx
0x18000159f  mov     rdi, rcx
0x1800015a2  mov     [rbp+pbstr], 0
0x1800015aa  mov     rcx, [rdx]
0x1800015ad  mov     rax, [rcx]
0x1800015b0  lea     rdx, [rbp+pbstr]
0x1800015b4  mov     rax, [rax+40h]
0x1800015b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015bd  test    eax, eax
0x1800015bf  js      short loc_1800015EB
0x1800015c1  mov     rcx, [rbp+pbstr]; pbstr
0x1800015c5  test    rcx, rcx
0x1800015c8  jz      short loc_1800015EB
0x1800015ca  call    cs:__imp_SysStringLen
0x1800015d0  test    eax, eax
0x1800015d2  jz      short loc_1800015EB
0x1800015d4  mov     r9, [rbp+pbstr]
0x1800015d8  mov     edx, 25h ; '%'
0x1800015dd  lea     r8d, [rdx+48h]
0x1800015e1  mov     rcx, rdi
0x1800015e4  call    ?StartElementWithAttribute@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@0PEBG@Z; TaskXmlWriter::StartElementWithAttribute(TaskXmlNodeId,TaskXmlNodeId,ushort const *)
0x1800015e9  jmp     short loc_1800015F8
0x1800015eb  mov     edx, 25h ; '%'
0x1800015f0  mov     rcx, rdi
0x1800015f3  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x1800015f8  mov     ebx, eax
0x1800015fa  test    eax, eax
0x1800015fc  js      loc_1800017B6
0x180001602  mov     rdx, rsi; struct JobTriggerPtr *
0x180001605  lea     rcx, [rbp+var_8]; this
0x180001609  call    ??0JobTriggerPtr@@QEAA@AEBV0@@Z; JobTriggerPtr::JobTriggerPtr(JobTriggerPtr const &)
0x18000160e  mov     rdx, rax
0x180001611  mov     rcx, rdi
0x180001614  call    ?WriteBaseTriggerProperties@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z; WriteBaseTriggerProperties(TaskXmlWriter &,JobTriggerPtr)
0x180001619  mov     ebx, eax
0x18000161b  test    eax, eax
0x18000161d  js      loc_1800017B6
0x180001623  mov     rdx, rsi; struct JobTriggerPtr *
0x180001626  lea     rcx, [rbp+var_10]; this
0x18000162a  call    ??0SessionStateChangeTriggerPtr@@QEAA@AEBVJobTriggerPtr@@@Z; SessionStateChangeTriggerPtr::SessionStateChangeTriggerPtr(JobTriggerPtr const &)
0x18000162f  nop
0x180001630  mov     [rbp+arg_10], 0
0x180001637  mov     rcx, [rbp+var_10]
0x18000163b  mov     rax, [rcx]
0x18000163e  lea     rdx, [rbp+arg_10]
0x180001642  mov     rax, [rax+0C0h]
0x180001649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000164e  mov     ebx, eax
0x180001650  test    eax, eax
0x180001652  js      loc_180001775
0x180001658  mov     ecx, [rbp+arg_10]
0x18000165b  sub     ecx, 1
0x18000165e  jz      short loc_1800016A6
0x180001660  sub     ecx, 1
0x180001663  jz      short loc_18000169D
0x180001665  sub     ecx, 1
0x180001668  jz      short loc_180001694
0x18000166a  sub     ecx, 1
0x18000166d  jz      short loc_18000168B
0x18000166f  sub     ecx, 3
0x180001672  jz      short loc_180001682
0x180001674  cmp     ecx, 1
0x180001677  jnz     short loc_1800016A6
0x180001679  lea     r8, aSessionunlock; "SessionUnlock"
0x180001680  jmp     short loc_1800016AD
0x180001682  lea     r8, aSessionlock; "SessionLock"
0x180001689  jmp     short loc_1800016AD
0x18000168b  lea     r8, aRemotedisconne; "RemoteDisconnect"
0x180001692  jmp     short loc_1800016AD
0x180001694  lea     r8, aRemoteconnect; "RemoteConnect"
0x18000169b  jmp     short loc_1800016AD
0x18000169d  lea     r8, aConsoledisconn; "ConsoleDisconnect"
0x1800016a4  jmp     short loc_1800016AD
0x1800016a6  lea     r8, aConsoleconnect; "ConsoleConnect"
0x1800016ad  mov     edx, 26h ; '&'
0x1800016b2  mov     rcx, rdi
0x1800016b5  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x1800016ba  test    eax, eax
0x1800016bc  jns     short loc_1800016C5
0x1800016be  mov     ebx, eax
0x1800016c0  jmp     loc_180001775
0x1800016c5  mov     [rbp+arg_18], 0
0x1800016cd  mov     rcx, [rbp+var_10]
0x1800016d1  mov     rax, [rcx]
0x1800016d4  lea     rdx, [rbp+arg_18]
0x1800016d8  mov     rax, [rax+0B0h]
0x1800016df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016e4  test    eax, eax
0x1800016e6  js      short loc_180001712
0x1800016e8  mov     rcx, [rbp+arg_18]; pbstr
0x1800016ec  test    rcx, rcx
0x1800016ef  jz      short loc_180001712
0x1800016f1  call    cs:__imp_SysStringLen
0x1800016f7  test    eax, eax
0x1800016f9  jz      short loc_180001712
0x1800016fb  mov     r8, [rbp+arg_18]
0x1800016ff  mov     edx, 24h ; '$'
0x180001704  mov     rcx, rdi
0x180001707  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18000170c  mov     ebx, eax
0x18000170e  test    eax, eax
0x180001710  js      short loc_18000176A
0x180001712  mov     [rbp+bstrString], 0
0x18000171a  mov     rcx, [rbp+var_10]
0x18000171e  mov     rax, [rcx]
0x180001721  lea     rdx, [rbp+bstrString]
0x180001725  mov     rax, [rax+0A0h]
0x18000172c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001731  test    eax, eax
0x180001733  js      short loc_180001780
0x180001735  mov     rcx, [rbp+bstrString]; pbstr
0x180001739  test    rcx, rcx
0x18000173c  jz      short loc_180001780
0x18000173e  call    cs:__imp_SysStringLen
0x180001744  test    eax, eax
0x180001746  jz      short loc_180001780
0x180001748  mov     r8, [rbp+bstrString]
0x18000174c  mov     edx, 16h
0x180001751  mov     rcx, rdi
0x180001754  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180001759  mov     ebx, eax
0x18000175b  test    eax, eax
0x18000175d  jns     short loc_180001780
0x18000175f  mov     rcx, [rbp+bstrString]; bstrString
0x180001763  call    cs:__imp_SysFreeString
0x180001769  nop
0x18000176a  mov     rcx, [rbp+arg_18]; bstrString
0x18000176e  call    cs:__imp_SysFreeString
0x180001774  nop
0x180001775  lea     rcx, [rbp+var_10]
0x180001779  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000177e  jmp     short loc_1800017B6
0x180001780  mov     rcx, rdi
0x180001783  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x180001788  mov     ebx, eax
0x18000178a  mov     rcx, [rbp+bstrString]; bstrString
0x18000178e  call    cs:__imp_SysFreeString
0x180001794  nop
0x180001795  mov     rcx, [rbp+arg_18]; bstrString
0x180001799  call    cs:__imp_SysFreeString
0x18000179f  nop
0x1800017a0  mov     rcx, [rbp+var_10]
0x1800017a4  test    rcx, rcx
0x1800017a7  jz      short loc_1800017B6
0x1800017a9  mov     rdx, [rcx]
0x1800017ac  mov     rax, [rdx+10h]
0x1800017b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017b5  nop
0x1800017b6  mov     rcx, [rbp+pbstr]; bstrString
0x1800017ba  call    cs:__imp_SysFreeString
0x1800017c0  nop
0x1800017c1  mov     rcx, rsi
0x1800017c4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800017c9  mov     eax, ebx
0x1800017cb  mov     rbx, [rsp+40h+arg_0]
0x1800017d0  add     rsp, 40h
0x1800017d4  pop     rdi
0x1800017d5  pop     rsi
0x1800017d6  pop     rbp
0x1800017d7  retn
```
