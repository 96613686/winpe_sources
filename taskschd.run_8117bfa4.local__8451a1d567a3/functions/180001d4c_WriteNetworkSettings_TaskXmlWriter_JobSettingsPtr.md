# WriteNetworkSettings(TaskXmlWriter &,JobSettingsPtr)

- ea: `0x180001d4c`
- end: `0x180001f16`
- name: `?WriteNetworkSettings@@YAJAEAVTaskXmlWriter@@VJobSettingsPtr@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180002db0`

## callees

- `0x180001880`
- `0x180001d4c`
- `0x180003a30`
- `0x180003f30`
- `0x1800145c0`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180001e1a`
- `OLEAUT32!__imp_SysFreeString` at `0x180001e2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180001ee9`
- `OLEAUT32!__imp_SysFreeString` at `0x180001efa`
- `OLEAUT32!__imp_SysFreeString` at `0x180001e1a`
- `OLEAUT32!__imp_SysFreeString` at `0x180001e2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180001ee9`
- `OLEAUT32!__imp_SysFreeString` at `0x180001efa`
- `OLEAUT32!__imp_SysStringLen` at `0x180001dd7`
- `OLEAUT32!__imp_SysStringLen` at `0x180001e5c`
- `OLEAUT32!__imp_SysStringLen` at `0x180001dd7`
- `OLEAUT32!__imp_SysStringLen` at `0x180001e5c`

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
0x180001d4c  mov     [rsp-28h+arg_8], rdx
0x180001d51  push    rbp
0x180001d52  push    rbx
0x180001d53  push    rsi
0x180001d54  push    rdi
0x180001d55  push    r14
0x180001d57  mov     rbp, rsp
0x180001d5a  sub     rsp, 30h
0x180001d5e  mov     rbx, rdx
0x180001d61  mov     rsi, rcx
0x180001d64  mov     [rbp+arg_10], 0
0x180001d6c  mov     rcx, [rdx]
0x180001d6f  mov     rax, [rcx]
0x180001d72  lea     rdx, [rbp+arg_10]
0x180001d76  mov     rax, [rax+168h]
0x180001d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d82  mov     edi, eax
0x180001d84  test    eax, eax
0x180001d86  jns     short loc_180001DB4
0x180001d88  mov     rcx, [rbp+arg_10]
0x180001d8c  test    rcx, rcx
0x180001d8f  jz      short loc_180001D9E
0x180001d91  mov     rdx, [rcx]
0x180001d94  mov     rax, [rdx+10h]
0x180001d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d9d  nop
0x180001d9e  mov     rcx, rbx
0x180001da1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001da6  mov     eax, edi
0x180001da8  add     rsp, 30h
0x180001dac  pop     r14
0x180001dae  pop     rdi
0x180001daf  pop     rsi
0x180001db0  pop     rbx
0x180001db1  pop     rbp
0x180001db2  retn
0x180001db4  xor     r14d, r14d
0x180001db7  mov     [rbp+pbstr], r14
0x180001dbb  mov     rcx, [rbp+arg_10]
0x180001dbf  mov     rax, [rcx]
0x180001dc2  lea     rdx, [rbp+pbstr]
0x180001dc6  mov     rax, [rax+38h]
0x180001dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dcf  test    eax, eax
0x180001dd1  js      short loc_180001DEB
0x180001dd3  mov     rcx, [rbp+pbstr]; pbstr
0x180001dd7  call    cs:__imp_SysStringLen
0x180001dde  nop     dword ptr [rax+rax+00h]
0x180001de3  test    eax, eax
0x180001de5  jnz     loc_180001EB1
0x180001deb  mov     [rbp+bstrString], 0
0x180001df3  mov     rcx, [rbp+arg_10]
0x180001df7  mov     rax, [rcx]
0x180001dfa  lea     rdx, [rbp+bstrString]
0x180001dfe  mov     rax, [rax+48h]
0x180001e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e07  mov     edi, eax
0x180001e09  test    eax, eax
0x180001e0b  jns     short loc_180001E53
0x180001e0d  mov     rcx, [rbp+bstrString]; bstrString
0x180001e11  test    r14d, r14d
0x180001e14  jnz     loc_180001E9A
0x180001e1a  call    cs:__imp_SysFreeString
0x180001e21  nop     dword ptr [rax+rax+00h]
0x180001e26  nop
0x180001e27  mov     rcx, [rbp+pbstr]; bstrString
0x180001e2b  call    cs:__imp_SysFreeString
0x180001e32  nop     dword ptr [rax+rax+00h]
0x180001e37  nop
0x180001e38  mov     rcx, [rbp+arg_10]
0x180001e3c  test    rcx, rcx
0x180001e3f  jz      short loc_180001E4E
0x180001e41  mov     rax, [rcx]
0x180001e44  mov     rax, [rax+10h]
0x180001e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e4d  nop
0x180001e4e  jmp     loc_180001D9E
0x180001e53  mov     rcx, [rbp+bstrString]; pbstr
0x180001e57  test    rcx, rcx
0x180001e5a  jz      short loc_180001E11
0x180001e5c  call    cs:__imp_SysStringLen
0x180001e63  nop     dword ptr [rax+rax+00h]
0x180001e68  test    eax, eax
0x180001e6a  jz      short loc_180001E0D
0x180001e6c  test    r14d, r14d
0x180001e6f  jnz     short loc_180001E83
0x180001e71  lea     edx, [r14+5Ah]
0x180001e75  mov     rcx, rsi
0x180001e78  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x180001e7d  mov     edi, eax
0x180001e7f  test    eax, eax
0x180001e81  js      short loc_180001EE5
0x180001e83  mov     r8, [rbp+bstrString]
0x180001e87  mov     edx, 5Ch ; '\'
0x180001e8c  mov     rcx, rsi
0x180001e8f  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180001e94  mov     edi, eax
0x180001e96  test    eax, eax
0x180001e98  js      short loc_180001EE5
0x180001e9a  mov     rcx, rsi
0x180001e9d  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x180001ea2  mov     edi, eax
0x180001ea4  test    eax, eax
0x180001ea6  js      short loc_180001EE5
0x180001ea8  mov     rcx, [rbp+bstrString]
0x180001eac  jmp     loc_180001E1A
0x180001eb1  mov     edx, 5Ah ; 'Z'
0x180001eb6  mov     rcx, rsi
0x180001eb9  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x180001ebe  mov     edi, eax
0x180001ec0  test    eax, eax
0x180001ec2  js      short loc_180001EF6
0x180001ec4  mov     r14d, 1
0x180001eca  mov     r8, [rbp+pbstr]
0x180001ece  lea     edx, [r14+5Ah]
0x180001ed2  mov     rcx, rsi
0x180001ed5  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180001eda  mov     edi, eax
0x180001edc  test    eax, eax
0x180001ede  js      short loc_180001EF6
0x180001ee0  jmp     loc_180001DEB
0x180001ee5  mov     rcx, [rbp+bstrString]; bstrString
0x180001ee9  call    cs:__imp_SysFreeString
0x180001ef0  nop     dword ptr [rax+rax+00h]
0x180001ef5  nop
0x180001ef6  mov     rcx, [rbp+pbstr]; bstrString
0x180001efa  call    cs:__imp_SysFreeString
0x180001f01  nop     dword ptr [rax+rax+00h]
0x180001f06  nop
0x180001f07  lea     rcx, [rbp+arg_10]
0x180001f0b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001f10  jmp     loc_180001D9E
```
