# WriteNetworkSettings(TaskXmlWriter &,JobSettingsPtr)

- ea: `0x180001cb8`
- end: `0x180001e59`
- name: `?WriteNetworkSettings@@YAJAEAVTaskXmlWriter@@VJobSettingsPtr@@@Z`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180002c10`

## callees

- `0x1800017f0`
- `0x180001cb8`
- `0x180003840`
- `0x180003d1c`
- `0x1800136e0`
- `0x180054010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180001d7b`
- `OLEAUT32!__imp_SysFreeString` at `0x180001d86`
- `OLEAUT32!__imp_SysFreeString` at `0x180001e38`
- `OLEAUT32!__imp_SysFreeString` at `0x180001e43`
- `OLEAUT32!__imp_SysFreeString` at `0x180001d7b`
- `OLEAUT32!__imp_SysFreeString` at `0x180001d86`
- `OLEAUT32!__imp_SysFreeString` at `0x180001e38`
- `OLEAUT32!__imp_SysFreeString` at `0x180001e43`
- `OLEAUT32!__imp_SysStringLen` at `0x180001d42`
- `OLEAUT32!__imp_SysStringLen` at `0x180001db1`
- `OLEAUT32!__imp_SysStringLen` at `0x180001d42`
- `OLEAUT32!__imp_SysStringLen` at `0x180001db1`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WriteNetworkSettings(int *a1, __int64 *a2)
{
  int started; // edi
  int v6; // r14d
  OLECHAR *v7; // rcx
  BSTR bstrString[2]; // [rsp+20h] [rbp-10h] BYREF
  __int64 v9; // [rsp+70h] [rbp+40h] BYREF
  BSTR pbstr; // [rsp+78h] [rbp+48h] BYREF

  v9 = 0;
  started = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a2 + 360LL))(*a2, &v9);
  if ( started < 0 )
  {
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    goto LABEL_4;
  }
  v6 = 0;
  pbstr = 0;
  if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v9 + 56LL))(v9, &pbstr) >= 0 )
  {
    if ( SysStringLen(pbstr) )
    {
      started = TaskXmlWriter::StartElement(a1, (struct IErrorInfo *)0x5A);
      if ( started < 0
        || (v6 = 1, started = TaskXmlWriter::Element((unsigned int *)a1, 91, (__int64)pbstr), started < 0) )
      {
LABEL_24:
        SysFreeString(pbstr);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
        goto LABEL_4;
      }
    }
  }
  bstrString[0] = 0;
  started = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v9 + 72LL))(v9, bstrString);
  if ( started < 0 )
    goto LABEL_8;
  v7 = bstrString[0];
  if ( !bstrString[0] )
  {
LABEL_9:
    if ( !v6 )
      goto LABEL_10;
    goto LABEL_18;
  }
  if ( !SysStringLen(bstrString[0]) )
  {
LABEL_8:
    v7 = bstrString[0];
    goto LABEL_9;
  }
  if ( !v6 )
  {
    started = TaskXmlWriter::StartElement(a1, (struct IErrorInfo *)0x5A);
    if ( started < 0 )
      goto LABEL_23;
  }
  started = TaskXmlWriter::Element((unsigned int *)a1, 92, (__int64)bstrString[0]);
  if ( started < 0 )
    goto LABEL_23;
LABEL_18:
  started = TaskXmlWriter::EndElement((__int64)a1);
  if ( started < 0 )
  {
LABEL_23:
    SysFreeString(bstrString[0]);
    goto LABEL_24;
  }
  v7 = bstrString[0];
LABEL_10:
  SysFreeString(v7);
  SysFreeString(pbstr);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
LABEL_4:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(a2);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180001cb8  mov     [rsp-28h+arg_8], rdx
0x180001cbd  push    rbp
0x180001cbe  push    rbx
0x180001cbf  push    rsi
0x180001cc0  push    rdi
0x180001cc1  push    r14
0x180001cc3  mov     rbp, rsp
0x180001cc6  sub     rsp, 30h
0x180001cca  mov     rbx, rdx
0x180001ccd  mov     rsi, rcx
0x180001cd0  mov     [rbp+arg_10], 0
0x180001cd8  mov     rcx, [rdx]
0x180001cdb  mov     rax, [rcx]
0x180001cde  lea     rdx, [rbp+arg_10]
0x180001ce2  mov     rax, [rax+168h]
0x180001ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cee  mov     edi, eax
0x180001cf0  test    eax, eax
0x180001cf2  jns     short loc_180001D1F
0x180001cf4  mov     rcx, [rbp+arg_10]
0x180001cf8  test    rcx, rcx
0x180001cfb  jz      short loc_180001D0A
0x180001cfd  mov     rdx, [rcx]
0x180001d00  mov     rax, [rdx+10h]
0x180001d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d09  nop
0x180001d0a  mov     rcx, rbx
0x180001d0d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001d12  mov     eax, edi
0x180001d14  add     rsp, 30h
0x180001d18  pop     r14
0x180001d1a  pop     rdi
0x180001d1b  pop     rsi
0x180001d1c  pop     rbx
0x180001d1d  pop     rbp
0x180001d1e  retn
0x180001d1f  xor     r14d, r14d
0x180001d22  mov     [rbp+pbstr], r14
0x180001d26  mov     rcx, [rbp+arg_10]
0x180001d2a  mov     rax, [rcx]
0x180001d2d  lea     rdx, [rbp+pbstr]
0x180001d31  mov     rax, [rax+38h]
0x180001d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d3a  test    eax, eax
0x180001d3c  js      short loc_180001D50
0x180001d3e  mov     rcx, [rbp+pbstr]; pbstr
0x180001d42  call    cs:__imp_SysStringLen
0x180001d48  test    eax, eax
0x180001d4a  jnz     loc_180001E00
0x180001d50  mov     [rbp+bstrString], 0
0x180001d58  mov     rcx, [rbp+arg_10]
0x180001d5c  mov     rax, [rcx]
0x180001d5f  lea     rdx, [rbp+bstrString]
0x180001d63  mov     rax, [rax+48h]
0x180001d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d6c  mov     edi, eax
0x180001d6e  test    eax, eax
0x180001d70  jns     short loc_180001DA8
0x180001d72  mov     rcx, [rbp+bstrString]; bstrString
0x180001d76  test    r14d, r14d
0x180001d79  jnz     short loc_180001DE9
0x180001d7b  call    cs:__imp_SysFreeString
0x180001d81  nop
0x180001d82  mov     rcx, [rbp+pbstr]; bstrString
0x180001d86  call    cs:__imp_SysFreeString
0x180001d8c  nop
0x180001d8d  mov     rcx, [rbp+arg_10]
0x180001d91  test    rcx, rcx
0x180001d94  jz      short loc_180001DA3
0x180001d96  mov     rax, [rcx]
0x180001d99  mov     rax, [rax+10h]
0x180001d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001da2  nop
0x180001da3  jmp     loc_180001D0A
0x180001da8  mov     rcx, [rbp+bstrString]; pbstr
0x180001dac  test    rcx, rcx
0x180001daf  jz      short loc_180001D76
0x180001db1  call    cs:__imp_SysStringLen
0x180001db7  test    eax, eax
0x180001db9  jz      short loc_180001D72
0x180001dbb  test    r14d, r14d
0x180001dbe  jnz     short loc_180001DD2
0x180001dc0  lea     edx, [r14+5Ah]
0x180001dc4  mov     rcx, rsi
0x180001dc7  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x180001dcc  mov     edi, eax
0x180001dce  test    eax, eax
0x180001dd0  js      short loc_180001E34
0x180001dd2  mov     r8, [rbp+bstrString]
0x180001dd6  mov     edx, 5Ch ; '\'
0x180001ddb  mov     rcx, rsi
0x180001dde  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180001de3  mov     edi, eax
0x180001de5  test    eax, eax
0x180001de7  js      short loc_180001E34
0x180001de9  mov     rcx, rsi
0x180001dec  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x180001df1  mov     edi, eax
0x180001df3  test    eax, eax
0x180001df5  js      short loc_180001E34
0x180001df7  mov     rcx, [rbp+bstrString]
0x180001dfb  jmp     loc_180001D7B
0x180001e00  mov     edx, 5Ah ; 'Z'
0x180001e05  mov     rcx, rsi
0x180001e08  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x180001e0d  mov     edi, eax
0x180001e0f  test    eax, eax
0x180001e11  js      short loc_180001E3F
0x180001e13  mov     r14d, 1
0x180001e19  mov     r8, [rbp+pbstr]
0x180001e1d  lea     edx, [r14+5Ah]
0x180001e21  mov     rcx, rsi
0x180001e24  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180001e29  mov     edi, eax
0x180001e2b  test    eax, eax
0x180001e2d  js      short loc_180001E3F
0x180001e2f  jmp     loc_180001D50
0x180001e34  mov     rcx, [rbp+bstrString]; bstrString
0x180001e38  call    cs:__imp_SysFreeString
0x180001e3e  nop
0x180001e3f  mov     rcx, [rbp+pbstr]; bstrString
0x180001e43  call    cs:__imp_SysFreeString
0x180001e49  nop
0x180001e4a  lea     rcx, [rbp+arg_10]
0x180001e4e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001e53  jmp     loc_180001D0A
```
