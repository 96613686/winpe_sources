# WriteSessionStateChangeTrigger(TaskXmlWriter &,JobTriggerPtr)

- ea: `0x1800015e0`
- end: `0x180001861`
- name: `?WriteSessionStateChangeTrigger@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z`
- size: `641`
- prototype: `int __high(struct TaskXmlWriter *, struct JobTriggerPtr)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014df0`

## callees

- `0x180001550`
- `0x1800015e0`
- `0x180001880`
- `0x180001938`
- `0x180001fe4`
- `0x180003a30`
- `0x180003f30`
- `0x1800145c0`
- `0x180014700`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800017cd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800017de`
- `OLEAUT32!__imp_SysFreeString` at `0x180001804`
- `OLEAUT32!__imp_SysFreeString` at `0x180001815`
- `OLEAUT32!__imp_SysFreeString` at `0x18000183c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800017cd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800017de`
- `OLEAUT32!__imp_SysFreeString` at `0x180001804`
- `OLEAUT32!__imp_SysFreeString` at `0x180001815`
- `OLEAUT32!__imp_SysFreeString` at `0x18000183c`
- `OLEAUT32!__imp_SysStringLen` at `0x180001622`
- `OLEAUT32!__imp_SysStringLen` at `0x18000174f`
- `OLEAUT32!__imp_SysStringLen` at `0x1800017a2`
- `OLEAUT32!__imp_SysStringLen` at `0x180001622`
- `OLEAUT32!__imp_SysStringLen` at `0x18000174f`
- `OLEAUT32!__imp_SysStringLen` at `0x1800017a2`

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
0x1800015e0  mov     [rsp-18h+arg_0], rbx
0x1800015e5  mov     [rsp-18h+arg_8], rdx
0x1800015ea  push    rbp
0x1800015eb  push    rsi
0x1800015ec  push    rdi
0x1800015ed  mov     rbp, rsp
0x1800015f0  sub     rsp, 40h
0x1800015f4  mov     rsi, rdx
0x1800015f7  mov     rdi, rcx
0x1800015fa  mov     [rbp+pbstr], 0
0x180001602  mov     rcx, [rdx]
0x180001605  mov     rax, [rcx]
0x180001608  lea     rdx, [rbp+pbstr]
0x18000160c  mov     rax, [rax+40h]
0x180001610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001615  test    eax, eax
0x180001617  js      short loc_180001649
0x180001619  mov     rcx, [rbp+pbstr]; pbstr
0x18000161d  test    rcx, rcx
0x180001620  jz      short loc_180001649
0x180001622  call    cs:__imp_SysStringLen
0x180001629  nop     dword ptr [rax+rax+00h]
0x18000162e  test    eax, eax
0x180001630  jz      short loc_180001649
0x180001632  mov     r9, [rbp+pbstr]
0x180001636  mov     edx, 25h ; '%'
0x18000163b  lea     r8d, [rdx+48h]
0x18000163f  mov     rcx, rdi
0x180001642  call    ?StartElementWithAttribute@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@0PEBG@Z; TaskXmlWriter::StartElementWithAttribute(TaskXmlNodeId,TaskXmlNodeId,ushort const *)
0x180001647  jmp     short loc_180001656
0x180001649  mov     edx, 25h ; '%'
0x18000164e  mov     rcx, rdi
0x180001651  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x180001656  mov     ebx, eax
0x180001658  test    eax, eax
0x18000165a  js      loc_180001838
0x180001660  mov     rdx, rsi; struct JobTriggerPtr *
0x180001663  lea     rcx, [rbp+var_8]; this
0x180001667  call    ??0JobTriggerPtr@@QEAA@AEBV0@@Z; JobTriggerPtr::JobTriggerPtr(JobTriggerPtr const &)
0x18000166c  mov     rdx, rax
0x18000166f  mov     rcx, rdi
0x180001672  call    ?WriteBaseTriggerProperties@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z; WriteBaseTriggerProperties(TaskXmlWriter &,JobTriggerPtr)
0x180001677  mov     ebx, eax
0x180001679  test    eax, eax
0x18000167b  js      loc_180001838
0x180001681  mov     rdx, rsi; struct JobTriggerPtr *
0x180001684  lea     rcx, [rbp+var_10]; this
0x180001688  call    ??0SessionStateChangeTriggerPtr@@QEAA@AEBVJobTriggerPtr@@@Z; SessionStateChangeTriggerPtr::SessionStateChangeTriggerPtr(JobTriggerPtr const &)
0x18000168d  nop
0x18000168e  mov     [rbp+arg_10], 0
0x180001695  mov     rcx, [rbp+var_10]
0x180001699  mov     rax, [rcx]
0x18000169c  lea     rdx, [rbp+arg_10]
0x1800016a0  mov     rax, [rax+0C0h]
0x1800016a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016ac  mov     ebx, eax
0x1800016ae  test    eax, eax
0x1800016b0  js      loc_1800017EB
0x1800016b6  mov     ecx, [rbp+arg_10]
0x1800016b9  sub     ecx, 1
0x1800016bc  jz      short loc_180001704
0x1800016be  sub     ecx, 1
0x1800016c1  jz      short loc_1800016FB
0x1800016c3  sub     ecx, 1
0x1800016c6  jz      short loc_1800016F2
0x1800016c8  sub     ecx, 1
0x1800016cb  jz      short loc_1800016E9
0x1800016cd  sub     ecx, 3
0x1800016d0  jz      short loc_1800016E0
0x1800016d2  cmp     ecx, 1
0x1800016d5  jnz     short loc_180001704
0x1800016d7  lea     r8, aSessionunlock; "SessionUnlock"
0x1800016de  jmp     short loc_18000170B
0x1800016e0  lea     r8, aSessionlock; "SessionLock"
0x1800016e7  jmp     short loc_18000170B
0x1800016e9  lea     r8, aRemotedisconne; "RemoteDisconnect"
0x1800016f0  jmp     short loc_18000170B
0x1800016f2  lea     r8, aRemoteconnect; "RemoteConnect"
0x1800016f9  jmp     short loc_18000170B
0x1800016fb  lea     r8, aConsoledisconn; "ConsoleDisconnect"
0x180001702  jmp     short loc_18000170B
0x180001704  lea     r8, aConsoleconnect; "ConsoleConnect"
0x18000170b  mov     edx, 26h ; '&'
0x180001710  mov     rcx, rdi
0x180001713  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180001718  test    eax, eax
0x18000171a  jns     short loc_180001723
0x18000171c  mov     ebx, eax
0x18000171e  jmp     loc_1800017EB
0x180001723  mov     [rbp+arg_18], 0
0x18000172b  mov     rcx, [rbp+var_10]
0x18000172f  mov     rax, [rcx]
0x180001732  lea     rdx, [rbp+arg_18]
0x180001736  mov     rax, [rax+0B0h]
0x18000173d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001742  test    eax, eax
0x180001744  js      short loc_180001776
0x180001746  mov     rcx, [rbp+arg_18]; pbstr
0x18000174a  test    rcx, rcx
0x18000174d  jz      short loc_180001776
0x18000174f  call    cs:__imp_SysStringLen
0x180001756  nop     dword ptr [rax+rax+00h]
0x18000175b  test    eax, eax
0x18000175d  jz      short loc_180001776
0x18000175f  mov     r8, [rbp+arg_18]
0x180001763  mov     edx, 24h ; '$'
0x180001768  mov     rcx, rdi
0x18000176b  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180001770  mov     ebx, eax
0x180001772  test    eax, eax
0x180001774  js      short loc_1800017DA
0x180001776  mov     [rbp+bstrString], 0
0x18000177e  mov     rcx, [rbp+var_10]
0x180001782  mov     rax, [rcx]
0x180001785  lea     rdx, [rbp+bstrString]
0x180001789  mov     rax, [rax+0A0h]
0x180001790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001795  test    eax, eax
0x180001797  js      short loc_1800017F6
0x180001799  mov     rcx, [rbp+bstrString]; pbstr
0x18000179d  test    rcx, rcx
0x1800017a0  jz      short loc_1800017F6
0x1800017a2  call    cs:__imp_SysStringLen
0x1800017a9  nop     dword ptr [rax+rax+00h]
0x1800017ae  test    eax, eax
0x1800017b0  jz      short loc_1800017F6
0x1800017b2  mov     r8, [rbp+bstrString]
0x1800017b6  mov     edx, 16h
0x1800017bb  mov     rcx, rdi
0x1800017be  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x1800017c3  mov     ebx, eax
0x1800017c5  test    eax, eax
0x1800017c7  jns     short loc_1800017F6
0x1800017c9  mov     rcx, [rbp+bstrString]; bstrString
0x1800017cd  call    cs:__imp_SysFreeString
0x1800017d4  nop     dword ptr [rax+rax+00h]
0x1800017d9  nop
0x1800017da  mov     rcx, [rbp+arg_18]; bstrString
0x1800017de  call    cs:__imp_SysFreeString
0x1800017e5  nop     dword ptr [rax+rax+00h]
0x1800017ea  nop
0x1800017eb  lea     rcx, [rbp+var_10]
0x1800017ef  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800017f4  jmp     short loc_180001838
0x1800017f6  mov     rcx, rdi
0x1800017f9  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x1800017fe  mov     ebx, eax
0x180001800  mov     rcx, [rbp+bstrString]; bstrString
0x180001804  call    cs:__imp_SysFreeString
0x18000180b  nop     dword ptr [rax+rax+00h]
0x180001810  nop
0x180001811  mov     rcx, [rbp+arg_18]; bstrString
0x180001815  call    cs:__imp_SysFreeString
0x18000181c  nop     dword ptr [rax+rax+00h]
0x180001821  nop
0x180001822  mov     rcx, [rbp+var_10]
0x180001826  test    rcx, rcx
0x180001829  jz      short loc_180001838
0x18000182b  mov     rdx, [rcx]
0x18000182e  mov     rax, [rdx+10h]
0x180001832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001837  nop
0x180001838  mov     rcx, [rbp+pbstr]; bstrString
0x18000183c  call    cs:__imp_SysFreeString
0x180001843  nop     dword ptr [rax+rax+00h]
0x180001848  nop
0x180001849  mov     rcx, rsi
0x18000184c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001851  mov     eax, ebx
0x180001853  mov     rbx, [rsp+40h+arg_0]
0x180001858  add     rsp, 40h
0x18000185c  pop     rdi
0x18000185d  pop     rsi
0x18000185e  pop     rbp
0x18000185f  retn
```
