# WriteIdleSettings(TaskXmlWriter &,JobSettingsPtr)

- ea: `0x1800039f0`
- end: `0x180003c87`
- name: `?WriteIdleSettings@@YAJAEAVTaskXmlWriter@@VJobSettingsPtr@@@Z`
- size: `663`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180002c10`

## callees

- `0x1800017f0`
- `0x180003840`
- `0x1800039f0`
- `0x180003d1c`
- `0x1800136e0`
- `0x180054010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180003ada`
- `OLEAUT32!__imp_SysFreeString` at `0x180003ae5`
- `OLEAUT32!__imp_SysFreeString` at `0x180003ada`
- `OLEAUT32!__imp_SysFreeString` at `0x180003ae5`
- `OLEAUT32!__imp_SysStringLen` at `0x180003b27`
- `OLEAUT32!__imp_SysStringLen` at `0x180003c0c`
- `OLEAUT32!__imp_SysStringLen` at `0x180003b27`
- `OLEAUT32!__imp_SysStringLen` at `0x180003c0c`

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
0x1800039f0  mov     [rsp-28h+arg_0], rbx
0x1800039f5  mov     [rsp-28h+arg_8], rdx
0x1800039fa  push    rbp
0x1800039fb  push    rsi
0x1800039fc  push    rdi
0x1800039fd  push    r12
0x1800039ff  push    r14
0x180003a01  mov     rbp, rsp
0x180003a04  sub     rsp, 40h
0x180003a08  mov     rdi, rdx
0x180003a0b  mov     rsi, rcx
0x180003a0e  mov     [rbp+pbstr], 0
0x180003a16  mov     [rbp+bstrString], 0
0x180003a1e  xor     eax, eax
0x180003a20  mov     [rbp+arg_10], ax
0x180003a24  mov     [rbp+arg_18], ax
0x180003a28  mov     [rbp+var_20], rax
0x180003a2c  mov     rcx, [rdx]
0x180003a2f  mov     rax, [rcx]
0x180003a32  lea     rdx, [rbp+var_20]
0x180003a36  mov     rax, [rax+138h]
0x180003a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a42  mov     ebx, eax
0x180003a44  test    eax, eax
0x180003a46  js      loc_180003BFE
0x180003a4c  mov     rcx, [rbp+var_20]
0x180003a50  mov     rax, [rcx]
0x180003a53  lea     rdx, [rbp+pbstr]
0x180003a57  mov     rax, [rax+38h]
0x180003a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a60  mov     ebx, eax
0x180003a62  test    eax, eax
0x180003a64  js      loc_180003C6B
0x180003a6a  mov     rcx, [rbp+var_20]
0x180003a6e  mov     rax, [rcx]
0x180003a71  lea     rdx, [rbp+bstrString]
0x180003a75  mov     rax, [rax+48h]
0x180003a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a7e  mov     ebx, eax
0x180003a80  test    eax, eax
0x180003a82  js      loc_180003BFE
0x180003a88  mov     rcx, [rbp+var_20]
0x180003a8c  mov     rax, [rcx]
0x180003a8f  lea     rdx, [rbp+arg_10]
0x180003a93  mov     rax, [rax+58h]
0x180003a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a9c  mov     ebx, eax
0x180003a9e  test    eax, eax
0x180003aa0  js      loc_180003BFE
0x180003aa6  mov     rcx, [rbp+var_20]
0x180003aaa  mov     rax, [rcx]
0x180003aad  lea     rdx, [rbp+arg_18]
0x180003ab1  mov     rax, [rax+68h]
0x180003ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aba  mov     ebx, eax
0x180003abc  test    eax, eax
0x180003abe  jns     short loc_180003B07
0x180003ac0  mov     rcx, [rbp+var_20]
0x180003ac4  test    rcx, rcx
0x180003ac7  jz      short loc_180003AD6
0x180003ac9  mov     rdx, [rcx]
0x180003acc  mov     rax, [rdx+10h]
0x180003ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ad5  nop
0x180003ad6  mov     rcx, [rbp+bstrString]; bstrString
0x180003ada  call    cs:__imp_SysFreeString
0x180003ae0  nop
0x180003ae1  mov     rcx, [rbp+pbstr]; bstrString
0x180003ae5  call    cs:__imp_SysFreeString
0x180003aeb  nop
0x180003aec  mov     rcx, rdi
0x180003aef  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180003af4  mov     eax, ebx
0x180003af6  mov     rbx, [rsp+40h+arg_0]
0x180003afb  add     rsp, 40h
0x180003aff  pop     r14
0x180003b01  pop     r12
0x180003b03  pop     rdi
0x180003b04  pop     rsi
0x180003b05  pop     rbp
0x180003b06  retn
0x180003b07  mov     edx, 55h ; 'U'
0x180003b0c  mov     rcx, rsi
0x180003b0f  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x180003b14  mov     ebx, eax
0x180003b16  test    eax, eax
0x180003b18  js      loc_180003BFE
0x180003b1e  mov     rcx, [rbp+pbstr]; pbstr
0x180003b22  test    rcx, rcx
0x180003b25  jz      short loc_180003B35
0x180003b27  call    cs:__imp_SysStringLen
0x180003b2d  test    eax, eax
0x180003b2f  jnz     loc_180003BE3
0x180003b35  mov     rcx, [rbp+bstrString]; pbstr
0x180003b39  test    rcx, rcx
0x180003b3c  jnz     loc_180003C0C
0x180003b42  or      eax, 0FFFFFFFFh
0x180003b45  cmp     ax, [rbp+arg_10]
0x180003b49  setz    al
0x180003b4c  lea     r12, aFalse; "false"
0x180003b53  lea     r14, aTrue; "true"
0x180003b5a  mov     r8, r14
0x180003b5d  test    al, al
0x180003b5f  cmovz   r8, r12
0x180003b63  mov     edx, 58h ; 'X'
0x180003b68  mov     rcx, rsi
0x180003b6b  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180003b70  mov     ebx, eax
0x180003b72  test    eax, eax
0x180003b74  jns     short loc_180003B91
0x180003b76  mov     rcx, [rbp+var_20]
0x180003b7a  test    rcx, rcx
0x180003b7d  jz      short loc_180003B8C
0x180003b7f  mov     rdx, [rcx]
0x180003b82  mov     rax, [rdx+10h]
0x180003b86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b8b  nop
0x180003b8c  jmp     loc_180003AD6
0x180003b91  xor     eax, eax
0x180003b93  cmp     ax, [rbp+arg_18]
0x180003b97  setnz   al
0x180003b9a  test    al, al
0x180003b9c  cmovz   r14, r12
0x180003ba0  mov     r8, r14
0x180003ba3  mov     edx, 59h ; 'Y'
0x180003ba8  mov     rcx, rsi
0x180003bab  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180003bb0  mov     ebx, eax
0x180003bb2  test    eax, eax
0x180003bb4  js      loc_180003C50
0x180003bba  mov     rcx, rsi
0x180003bbd  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x180003bc2  mov     ebx, eax
0x180003bc4  test    eax, eax
0x180003bc6  jns     short loc_180003BFE
0x180003bc8  mov     rcx, [rbp+var_20]
0x180003bcc  test    rcx, rcx
0x180003bcf  jz      short loc_180003BDE
0x180003bd1  mov     rdx, [rcx]
0x180003bd4  mov     rax, [rdx+10h]
0x180003bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bdd  nop
0x180003bde  jmp     loc_180003AD6
0x180003be3  mov     r8, [rbp+pbstr]
0x180003be7  mov     edx, 56h ; 'V'
0x180003bec  mov     rcx, rsi
0x180003bef  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180003bf4  mov     ebx, eax
0x180003bf6  test    eax, eax
0x180003bf8  jns     loc_180003B35
0x180003bfe  lea     rcx, [rbp+var_20]
0x180003c02  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180003c07  jmp     loc_180003AD6
0x180003c0c  call    cs:__imp_SysStringLen
0x180003c12  test    eax, eax
0x180003c14  jz      loc_180003B42
0x180003c1a  mov     r8, [rbp+bstrString]
0x180003c1e  mov     edx, 57h ; 'W'
0x180003c23  mov     rcx, rsi
0x180003c26  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180003c2b  mov     ebx, eax
0x180003c2d  test    eax, eax
0x180003c2f  jns     loc_180003B42
0x180003c35  mov     rcx, [rbp+var_20]
0x180003c39  test    rcx, rcx
0x180003c3c  jz      short loc_180003C4B
0x180003c3e  mov     rdx, [rcx]
0x180003c41  mov     rax, [rdx+10h]
0x180003c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c4a  nop
0x180003c4b  jmp     loc_180003AD6
0x180003c50  mov     rcx, [rbp+var_20]
0x180003c54  test    rcx, rcx
0x180003c57  jz      short loc_180003C66
0x180003c59  mov     rdx, [rcx]
0x180003c5c  mov     rax, [rdx+10h]
0x180003c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c65  nop
0x180003c66  jmp     loc_180003AD6
0x180003c6b  mov     rcx, [rbp+var_20]
0x180003c6f  test    rcx, rcx
0x180003c72  jz      short loc_180003C81
0x180003c74  mov     rdx, [rcx]
0x180003c77  mov     rax, [rdx+10h]
0x180003c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c80  nop
0x180003c81  jmp     loc_180003AD6
```
