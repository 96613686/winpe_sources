# WriteIdleSettings(TaskXmlWriter &,JobSettingsPtr)

- ea: `0x180003be8`
- end: `0x180003e98`
- name: `?WriteIdleSettings@@YAJAEAVTaskXmlWriter@@VJobSettingsPtr@@@Z`
- size: `688`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180002db0`

## callees

- `0x180001880`
- `0x180003a30`
- `0x180003be8`
- `0x180003f30`
- `0x1800145c0`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180003cd2`
- `OLEAUT32!__imp_SysFreeString` at `0x180003ce3`
- `OLEAUT32!__imp_SysFreeString` at `0x180003cd2`
- `OLEAUT32!__imp_SysFreeString` at `0x180003ce3`
- `OLEAUT32!__imp_SysStringLen` at `0x180003d2c`
- `OLEAUT32!__imp_SysStringLen` at `0x180003e17`
- `OLEAUT32!__imp_SysStringLen` at `0x180003d2c`
- `OLEAUT32!__imp_SysStringLen` at `0x180003e17`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WriteIdleSettings(int *a1, __int64 *a2)
{
  int started; // ebx
  const wchar_t *v6; // r14
  const wchar_t *v7; // r8
  __int64 v8; // [rsp+20h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-18h] BYREF
  BSTR pbstr[2]; // [rsp+30h] [rbp-10h] BYREF
  __int16 v11; // [rsp+80h] [rbp+40h] BYREF
  __int16 v12; // [rsp+88h] [rbp+48h] BYREF

  pbstr[0] = 0;
  bstrString = 0;
  v11 = 0;
  v12 = 0;
  v8 = 0;
  started = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a2 + 312LL))(*a2, &v8);
  if ( started < 0 )
    goto LABEL_27;
  started = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v8 + 56LL))(v8, pbstr);
  if ( started < 0 )
  {
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  else
  {
    started = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v8 + 72LL))(v8, &bstrString);
    if ( started < 0 )
      goto LABEL_27;
    started = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v8 + 88LL))(v8, &v11);
    if ( started < 0 )
      goto LABEL_27;
    started = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v8 + 104LL))(v8, &v12);
    if ( started < 0 )
    {
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      goto LABEL_8;
    }
    started = TaskXmlWriter::StartElement(a1, (struct IErrorInfo *)0x55);
    if ( started < 0
      || pbstr[0]
      && SysStringLen(pbstr[0])
      && (started = TaskXmlWriter::Element((unsigned int *)a1, 86, (__int64)pbstr[0]), started < 0) )
    {
LABEL_27:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v8);
      goto LABEL_8;
    }
    if ( bstrString
      && SysStringLen(bstrString)
      && (started = TaskXmlWriter::Element((unsigned int *)a1, 87, (__int64)bstrString), started < 0) )
    {
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    else
    {
      v6 = L"true";
      v7 = L"true";
      if ( v11 != -1 )
        v7 = L"false";
      started = TaskXmlWriter::Element((unsigned int *)a1, 88, (__int64)v7);
      if ( started >= 0 )
      {
        if ( !v12 )
          v6 = L"false";
        started = TaskXmlWriter::Element((unsigned int *)a1, 89, (__int64)v6);
        if ( started < 0 )
        {
          if ( v8 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        }
        else
        {
          started = TaskXmlWriter::EndElement((__int64)a1);
          if ( started >= 0 )
            goto LABEL_27;
          if ( v8 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        }
      }
      else if ( v8 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
    }
  }
LABEL_8:
  SysFreeString(bstrString);
  SysFreeString(pbstr[0]);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(a2);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180003be8  mov     [rsp-28h+arg_0], rbx
0x180003bed  mov     [rsp-28h+arg_8], rdx
0x180003bf2  push    rbp
0x180003bf3  push    rsi
0x180003bf4  push    rdi
0x180003bf5  push    r12
0x180003bf7  push    r14
0x180003bf9  mov     rbp, rsp
0x180003bfc  sub     rsp, 40h
0x180003c00  mov     rdi, rdx
0x180003c03  mov     rsi, rcx
0x180003c06  mov     [rbp+pbstr], 0
0x180003c0e  mov     [rbp+bstrString], 0
0x180003c16  xor     eax, eax
0x180003c18  mov     [rbp+arg_10], ax
0x180003c1c  mov     [rbp+arg_18], ax
0x180003c20  mov     [rbp+var_20], rax
0x180003c24  mov     rcx, [rdx]
0x180003c27  mov     rax, [rcx]
0x180003c2a  lea     rdx, [rbp+var_20]
0x180003c2e  mov     rax, [rax+138h]
0x180003c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c3a  mov     ebx, eax
0x180003c3c  test    eax, eax
0x180003c3e  js      loc_180003E09
0x180003c44  mov     rcx, [rbp+var_20]
0x180003c48  mov     rax, [rcx]
0x180003c4b  lea     rdx, [rbp+pbstr]
0x180003c4f  mov     rax, [rax+38h]
0x180003c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c58  mov     ebx, eax
0x180003c5a  test    eax, eax
0x180003c5c  js      loc_180003E7C
0x180003c62  mov     rcx, [rbp+var_20]
0x180003c66  mov     rax, [rcx]
0x180003c69  lea     rdx, [rbp+bstrString]
0x180003c6d  mov     rax, [rax+48h]
0x180003c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c76  mov     ebx, eax
0x180003c78  test    eax, eax
0x180003c7a  js      loc_180003E09
0x180003c80  mov     rcx, [rbp+var_20]
0x180003c84  mov     rax, [rcx]
0x180003c87  lea     rdx, [rbp+arg_10]
0x180003c8b  mov     rax, [rax+58h]
0x180003c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c94  mov     ebx, eax
0x180003c96  test    eax, eax
0x180003c98  js      loc_180003E09
0x180003c9e  mov     rcx, [rbp+var_20]
0x180003ca2  mov     rax, [rcx]
0x180003ca5  lea     rdx, [rbp+arg_18]
0x180003ca9  mov     rax, [rax+68h]
0x180003cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cb2  mov     ebx, eax
0x180003cb4  test    eax, eax
0x180003cb6  jns     short loc_180003D0C
0x180003cb8  mov     rcx, [rbp+var_20]
0x180003cbc  test    rcx, rcx
0x180003cbf  jz      short loc_180003CCE
0x180003cc1  mov     rdx, [rcx]
0x180003cc4  mov     rax, [rdx+10h]
0x180003cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ccd  nop
0x180003cce  mov     rcx, [rbp+bstrString]; bstrString
0x180003cd2  call    cs:__imp_SysFreeString
0x180003cd9  nop     dword ptr [rax+rax+00h]
0x180003cde  nop
0x180003cdf  mov     rcx, [rbp+pbstr]; bstrString
0x180003ce3  call    cs:__imp_SysFreeString
0x180003cea  nop     dword ptr [rax+rax+00h]
0x180003cef  nop
0x180003cf0  mov     rcx, rdi
0x180003cf3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180003cf8  mov     eax, ebx
0x180003cfa  mov     rbx, [rsp+40h+arg_0]
0x180003cff  add     rsp, 40h
0x180003d03  pop     r14
0x180003d05  pop     r12
0x180003d07  pop     rdi
0x180003d08  pop     rsi
0x180003d09  pop     rbp
0x180003d0a  retn
0x180003d0c  mov     edx, 55h ; 'U'
0x180003d11  mov     rcx, rsi
0x180003d14  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x180003d19  mov     ebx, eax
0x180003d1b  test    eax, eax
0x180003d1d  js      loc_180003E09
0x180003d23  mov     rcx, [rbp+pbstr]; pbstr
0x180003d27  test    rcx, rcx
0x180003d2a  jz      short loc_180003D40
0x180003d2c  call    cs:__imp_SysStringLen
0x180003d33  nop     dword ptr [rax+rax+00h]
0x180003d38  test    eax, eax
0x180003d3a  jnz     loc_180003DEE
0x180003d40  mov     rcx, [rbp+bstrString]; pbstr
0x180003d44  test    rcx, rcx
0x180003d47  jnz     loc_180003E17
0x180003d4d  or      eax, 0FFFFFFFFh
0x180003d50  cmp     ax, [rbp+arg_10]
0x180003d54  setz    al
0x180003d57  lea     r12, aFalse; "false"
0x180003d5e  lea     r14, aTrue; "true"
0x180003d65  mov     r8, r14
0x180003d68  test    al, al
0x180003d6a  cmovz   r8, r12
0x180003d6e  mov     edx, 58h ; 'X'
0x180003d73  mov     rcx, rsi
0x180003d76  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180003d7b  mov     ebx, eax
0x180003d7d  test    eax, eax
0x180003d7f  jns     short loc_180003D9C
0x180003d81  mov     rcx, [rbp+var_20]
0x180003d85  test    rcx, rcx
0x180003d88  jz      short loc_180003D97
0x180003d8a  mov     rdx, [rcx]
0x180003d8d  mov     rax, [rdx+10h]
0x180003d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d96  nop
0x180003d97  jmp     loc_180003CCE
0x180003d9c  xor     eax, eax
0x180003d9e  cmp     ax, [rbp+arg_18]
0x180003da2  setnz   al
0x180003da5  test    al, al
0x180003da7  cmovz   r14, r12
0x180003dab  mov     r8, r14
0x180003dae  mov     edx, 59h ; 'Y'
0x180003db3  mov     rcx, rsi
0x180003db6  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180003dbb  mov     ebx, eax
0x180003dbd  test    eax, eax
0x180003dbf  js      loc_180003E61
0x180003dc5  mov     rcx, rsi
0x180003dc8  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x180003dcd  mov     ebx, eax
0x180003dcf  test    eax, eax
0x180003dd1  jns     short loc_180003E09
0x180003dd3  mov     rcx, [rbp+var_20]
0x180003dd7  test    rcx, rcx
0x180003dda  jz      short loc_180003DE9
0x180003ddc  mov     rdx, [rcx]
0x180003ddf  mov     rax, [rdx+10h]
0x180003de3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003de8  nop
0x180003de9  jmp     loc_180003CCE
0x180003dee  mov     r8, [rbp+pbstr]
0x180003df2  mov     edx, 56h ; 'V'
0x180003df7  mov     rcx, rsi
0x180003dfa  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180003dff  mov     ebx, eax
0x180003e01  test    eax, eax
0x180003e03  jns     loc_180003D40
0x180003e09  lea     rcx, [rbp+var_20]
0x180003e0d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180003e12  jmp     loc_180003CCE
0x180003e17  call    cs:__imp_SysStringLen
0x180003e1e  nop     dword ptr [rax+rax+00h]
0x180003e23  test    eax, eax
0x180003e25  jz      loc_180003D4D
0x180003e2b  mov     r8, [rbp+bstrString]
0x180003e2f  mov     edx, 57h ; 'W'
0x180003e34  mov     rcx, rsi
0x180003e37  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180003e3c  mov     ebx, eax
0x180003e3e  test    eax, eax
0x180003e40  jns     loc_180003D4D
0x180003e46  mov     rcx, [rbp+var_20]
0x180003e4a  test    rcx, rcx
0x180003e4d  jz      short loc_180003E5C
0x180003e4f  mov     rdx, [rcx]
0x180003e52  mov     rax, [rdx+10h]
0x180003e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e5b  nop
0x180003e5c  jmp     loc_180003CCE
0x180003e61  mov     rcx, [rbp+var_20]
0x180003e65  test    rcx, rcx
0x180003e68  jz      short loc_180003E77
0x180003e6a  mov     rdx, [rcx]
0x180003e6d  mov     rax, [rdx+10h]
0x180003e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e76  nop
0x180003e77  jmp     loc_180003CCE
0x180003e7c  mov     rcx, [rbp+var_20]
0x180003e80  test    rcx, rcx
0x180003e83  jz      short loc_180003E92
0x180003e85  mov     rdx, [rcx]
0x180003e88  mov     rax, [rdx+10h]
0x180003e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e91  nop
0x180003e92  jmp     loc_180003CCE
```
