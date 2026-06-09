# WriteTimeTrigger(TaskXmlWriter &,JobTriggerPtr)

- ea: `0x180014b1c`
- end: `0x180014ddc`
- name: `?WriteTimeTrigger@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z`
- size: `704`
- prototype: `int __high(struct TaskXmlWriter *, struct JobTriggerPtr)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014df0`

## callees

- `0x180001880`
- `0x180001fe4`
- `0x180003a30`
- `0x180014700`
- `0x180014b1c`
- `0x180016900`
- `0x1800387b4`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180014bfe`
- `OLEAUT32!__imp_SysFreeString` at `0x180014cb4`
- `OLEAUT32!__imp_SysFreeString` at `0x180014d5a`
- `OLEAUT32!__imp_SysFreeString` at `0x180014bfe`
- `OLEAUT32!__imp_SysFreeString` at `0x180014cb4`
- `OLEAUT32!__imp_SysFreeString` at `0x180014d5a`
- `OLEAUT32!__imp_SysStringLen` at `0x180014cec`
- `OLEAUT32!__imp_SysStringLen` at `0x180014d27`
- `OLEAUT32!__imp_SysStringLen` at `0x180014cec`
- `OLEAUT32!__imp_SysStringLen` at `0x180014d27`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WriteTimeTrigger(unsigned __int16 *a1, const struct JobTriggerPtr *a2)
{
  int v4; // r14d
  int v5; // eax
  const struct SchemaEntry * near *v6; // rdi
  __int64 v7; // rax
  int started; // eax
  int v9; // edi
  __int64 v11; // rcx
  OLECHAR *v12; // rcx
  int v13; // eax
  __int64 v14; // rax
  const unsigned __int64 *v15; // rdx
  __int64 v16; // r9
  __int64 v17; // [rsp+30h] [rbp-10h] BYREF
  __int64 v18; // [rsp+38h] [rbp-8h] BYREF
  BSTR pbstr; // [rsp+80h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+48h] BYREF

  bstrString = 0;
  v4 = 1;
  if ( (*(int (__fastcall **)(_QWORD, BSTR *))(**(_QWORD **)a2 + 64LL))(*(_QWORD *)a2, &bstrString) >= 0
    && bstrString
    && SysStringLen(bstrString) )
  {
    started = TaskXmlWriter::StartElementWithAttribute((unsigned int *)a1, 25, 109, (__int64)bstrString);
    goto LABEL_12;
  }
  v5 = *((_DWORD *)a1 + 38);
  if ( v5 )
  {
    *((_DWORD *)a1 + 38) = v5 + 1;
    goto LABEL_38;
  }
  if ( *(_DWORD *)a1 == 0x10000 || *(_DWORD *)a1 == 65537 )
  {
    v15 = 0;
    v16 = *a1;
    while ( v15 < (&Schema::schemaEntriesCount)[v16] )
    {
      v6 = &(&Schema::schemaEntries)[v16][16 * (_QWORD)v15];
      if ( *(_DWORD *)v6 == 25 )
        goto LABEL_11;
      v15 = (const unsigned __int64 *)((char *)v15 + 1);
    }
  }
  else if ( *(_DWORD *)a1 == 65538
         || *(_DWORD *)a1 == 65539
         || *(_DWORD *)a1 == 65540
         || (unsigned int)(*(_DWORD *)a1 - 65541) <= 1 )
  {
    v6 = (&Schema::schemaEntries)[*a1] + 400;
    goto LABEL_10;
  }
  v6 = (const struct SchemaEntry * near *)&qword_180072DF0;
LABEL_10:
  if ( !*(_DWORD *)v6 )
  {
    *((_DWORD *)a1 + 38) = 1;
LABEL_38:
    v9 = 1;
    goto LABEL_13;
  }
LABEL_11:
  v7 = _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->((__int64 *)a1 + 2);
  started = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const struct SchemaEntry *, wchar_t *const))(*(_QWORD *)v7 + 216LL))(
              v7,
              &Src,
              v6[1],
              Schema::namespaceUri);
LABEL_12:
  v9 = started;
LABEL_13:
  if ( v9 >= 0 )
  {
    v11 = *(_QWORD *)a2;
    v18 = v11;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    v9 = WriteBaseTriggerProperties((int *)a1, &v18);
    if ( v9 >= 0 )
    {
      TimeTriggerPtr::TimeTriggerPtr((TimeTriggerPtr *)&v17, a2);
      pbstr = 0;
      if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v17 + 160LL))(v17, &pbstr) >= 0 )
      {
        v12 = pbstr;
        if ( !pbstr )
          goto LABEL_20;
        if ( SysStringLen(pbstr) )
        {
          v9 = TaskXmlWriter::Element((unsigned int *)a1, 26, (__int64)pbstr);
          if ( v9 < 0 )
          {
            SysFreeString(pbstr);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
            goto LABEL_14;
          }
        }
      }
      v12 = pbstr;
LABEL_20:
      v13 = *((_DWORD *)a1 + 38);
      if ( v13 )
      {
        *((_DWORD *)a1 + 38) = v13 - 1;
      }
      else
      {
        v14 = _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->((__int64 *)a1 + 2);
        v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 120LL))(v14);
        v12 = pbstr;
      }
      SysFreeString(v12);
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      v9 = v4;
    }
  }
LABEL_14:
  SysFreeString(bstrString);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)a2);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180014b1c  mov     [rsp-28h+arg_8], rdx
0x180014b21  push    rbp
0x180014b22  push    rbx
0x180014b23  push    rsi
0x180014b24  push    rdi
0x180014b25  push    r14
0x180014b27  mov     rbp, rsp
0x180014b2a  sub     rsp, 40h
0x180014b2e  mov     rsi, rdx
0x180014b31  mov     rbx, rcx
0x180014b34  mov     [rbp+bstrString], 0
0x180014b3c  mov     rcx, [rdx]
0x180014b3f  mov     rax, [rcx]
0x180014b42  lea     rdx, [rbp+bstrString]
0x180014b46  mov     rax, [rax+40h]
0x180014b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b4f  mov     r14d, 1
0x180014b55  test    eax, eax
0x180014b57  jns     loc_180014CDF
0x180014b5d  mov     eax, [rbx+98h]
0x180014b63  test    eax, eax
0x180014b65  jnz     loc_180014DD1
0x180014b6b  mov     ecx, [rbx]
0x180014b6d  sub     ecx, 10000h
0x180014b73  jz      loc_180014D75
0x180014b79  sub     ecx, r14d
0x180014b7c  jz      loc_180014D75
0x180014b82  sub     ecx, r14d
0x180014b85  jz      short loc_180014B9F
0x180014b87  sub     ecx, r14d
0x180014b8a  jz      short loc_180014B9F
0x180014b8c  sub     ecx, r14d
0x180014b8f  jz      short loc_180014B9F
0x180014b91  sub     ecx, r14d
0x180014b94  jz      short loc_180014B9F
0x180014b96  cmp     ecx, r14d
0x180014b99  jnz     loc_180014DA9
0x180014b9f  movzx   eax, word ptr [rbx]
0x180014ba2  lea     r8, __ImageBase
0x180014ba9  mov     rdi, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r8+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180014bb1  add     rdi, 0C80h
0x180014bb8  mov     rax, rdi
0x180014bbb  cmp     dword ptr [rax], 0
0x180014bbe  jz      loc_180014DB5
0x180014bc4  lea     rcx, [rbx+10h]
0x180014bc8  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlWriter@@$1?_GUID_7279fc88_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlWriter@@XZ; _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x180014bcd  mov     r10, rax
0x180014bd0  mov     rcx, [rax]
0x180014bd3  mov     rax, [rcx+0D8h]
0x180014bda  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180014be1  mov     r8, [rdi+8]
0x180014be5  lea     rdx, Src
0x180014bec  mov     rcx, r10
0x180014bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bf4  mov     edi, eax
0x180014bf6  test    edi, edi
0x180014bf8  jns     short loc_180014C21
0x180014bfa  mov     rcx, [rbp+bstrString]; bstrString
0x180014bfe  call    cs:__imp_SysFreeString
0x180014c05  nop     dword ptr [rax+rax+00h]
0x180014c0a  nop
0x180014c0b  mov     rcx, rsi
0x180014c0e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014c13  mov     eax, edi
0x180014c15  add     rsp, 40h
0x180014c19  pop     r14
0x180014c1b  pop     rdi
0x180014c1c  pop     rsi
0x180014c1d  pop     rbx
0x180014c1e  pop     rbp
0x180014c1f  retn
0x180014c21  mov     rcx, [rsi]
0x180014c24  mov     [rbp+var_8], rcx
0x180014c28  test    rcx, rcx
0x180014c2b  jz      short loc_180014C3A
0x180014c2d  mov     rax, [rcx]
0x180014c30  mov     rax, [rax+8]
0x180014c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c39  nop
0x180014c3a  lea     rdx, [rbp+var_8]
0x180014c3e  mov     rcx, rbx
0x180014c41  call    ?WriteBaseTriggerProperties@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z; WriteBaseTriggerProperties(TaskXmlWriter &,JobTriggerPtr)
0x180014c46  mov     edi, eax
0x180014c48  test    eax, eax
0x180014c4a  js      short loc_180014BFA
0x180014c4c  mov     rdx, rsi; struct JobTriggerPtr *
0x180014c4f  lea     rcx, [rbp+var_10]; this
0x180014c53  call    ??0TimeTriggerPtr@@QEAA@AEBVJobTriggerPtr@@@Z; TimeTriggerPtr::TimeTriggerPtr(JobTriggerPtr const &)
0x180014c58  nop
0x180014c59  mov     [rbp+pbstr], 0
0x180014c61  mov     rcx, [rbp+var_10]
0x180014c65  mov     rax, [rcx]
0x180014c68  lea     rdx, [rbp+pbstr]
0x180014c6c  mov     rax, [rax+0A0h]
0x180014c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c78  test    eax, eax
0x180014c7a  jns     loc_180014D1A
0x180014c80  mov     rcx, [rbp+pbstr]
0x180014c84  mov     eax, [rbx+98h]
0x180014c8a  test    eax, eax
0x180014c8c  jnz     loc_180014DC4
0x180014c92  lea     rcx, [rbx+10h]
0x180014c96  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlWriter@@$1?_GUID_7279fc88_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlWriter@@XZ; _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x180014c9b  mov     rdx, rax
0x180014c9e  mov     rcx, [rax]
0x180014ca1  mov     rax, [rcx+78h]
0x180014ca5  mov     rcx, rdx
0x180014ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cad  mov     r14d, eax
0x180014cb0  mov     rcx, [rbp+pbstr]; bstrString
0x180014cb4  call    cs:__imp_SysFreeString
0x180014cbb  nop     dword ptr [rax+rax+00h]
0x180014cc0  nop
0x180014cc1  mov     rcx, [rbp+var_10]
0x180014cc5  test    rcx, rcx
0x180014cc8  jz      short loc_180014CD7
0x180014cca  mov     rdx, [rcx]
0x180014ccd  mov     rax, [rdx+10h]
0x180014cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cd6  nop
0x180014cd7  mov     edi, r14d
0x180014cda  jmp     loc_180014BFA
0x180014cdf  mov     rcx, [rbp+bstrString]; pbstr
0x180014ce3  test    rcx, rcx
0x180014ce6  jz      loc_180014B5D
0x180014cec  call    cs:__imp_SysStringLen
0x180014cf3  nop     dword ptr [rax+rax+00h]
0x180014cf8  test    eax, eax
0x180014cfa  jz      loc_180014B5D
0x180014d00  mov     r9, [rbp+bstrString]
0x180014d04  mov     edx, 19h
0x180014d09  lea     r8d, [rdx+54h]
0x180014d0d  mov     rcx, rbx
0x180014d10  call    ?StartElementWithAttribute@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@0PEBG@Z; TaskXmlWriter::StartElementWithAttribute(TaskXmlNodeId,TaskXmlNodeId,ushort const *)
0x180014d15  jmp     loc_180014BF4
0x180014d1a  mov     rcx, [rbp+pbstr]; pbstr
0x180014d1e  test    rcx, rcx
0x180014d21  jz      loc_180014C84
0x180014d27  call    cs:__imp_SysStringLen
0x180014d2e  nop     dword ptr [rax+rax+00h]
0x180014d33  test    eax, eax
0x180014d35  jz      loc_180014C80
0x180014d3b  mov     r8, [rbp+pbstr]
0x180014d3f  mov     edx, 1Ah
0x180014d44  mov     rcx, rbx
0x180014d47  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180014d4c  mov     edi, eax
0x180014d4e  test    eax, eax
0x180014d50  jns     loc_180014C80
0x180014d56  mov     rcx, [rbp+pbstr]; bstrString
0x180014d5a  call    cs:__imp_SysFreeString
0x180014d61  nop     dword ptr [rax+rax+00h]
0x180014d66  nop
0x180014d67  lea     rcx, [rbp+var_10]
0x180014d6b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014d70  jmp     loc_180014BFA
0x180014d75  xor     edx, edx
0x180014d77  movzx   r9d, word ptr [rbx]
0x180014d7b  lea     r8, __ImageBase
0x180014d82  cmp     rdx, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r8+r9*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x180014d8a  jnb     short loc_180014DA9
0x180014d8c  mov     rdi, rdx
0x180014d8f  shl     rdi, 7
0x180014d93  add     rdi, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r8+r9*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180014d9b  cmp     dword ptr [rdi], 19h
0x180014d9e  jz      loc_180014BC4
0x180014da4  add     rdx, r14
0x180014da7  jmp     short loc_180014D82
0x180014da9  mov     rdi, cs:off_18005DF68
0x180014db0  jmp     loc_180014BB8
0x180014db5  mov     [rbx+98h], r14d
0x180014dbc  mov     edi, r14d
0x180014dbf  jmp     loc_180014BF6
0x180014dc4  dec     eax
0x180014dc6  mov     [rbx+98h], eax
0x180014dcc  jmp     loc_180014CB4
0x180014dd1  inc     eax
0x180014dd3  mov     [rbx+98h], eax
0x180014dd9  jmp     short loc_180014DBC
```
