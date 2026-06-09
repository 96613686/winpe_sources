# WriteTimeTrigger(TaskXmlWriter &,JobTriggerPtr)

- ea: `0x180013c6c`
- end: `0x180013f0d`
- name: `?WriteTimeTrigger@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z`
- size: `673`
- prototype: `int __high(struct TaskXmlWriter *, struct JobTriggerPtr)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013f20`

## callees

- `0x1800017f0`
- `0x180001f90`
- `0x180003840`
- `0x1800138e0`
- `0x180013c6c`
- `0x1800157e4`
- `0x180035794`
- `0x180054010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180013d4e`
- `OLEAUT32!__imp_SysFreeString` at `0x180013dfd`
- `OLEAUT32!__imp_SysFreeString` at `0x180013e91`
- `OLEAUT32!__imp_SysFreeString` at `0x180013d4e`
- `OLEAUT32!__imp_SysFreeString` at `0x180013dfd`
- `OLEAUT32!__imp_SysFreeString` at `0x180013e91`
- `OLEAUT32!__imp_SysStringLen` at `0x180013e2f`
- `OLEAUT32!__imp_SysStringLen` at `0x180013e64`
- `OLEAUT32!__imp_SysStringLen` at `0x180013e2f`
- `OLEAUT32!__imp_SysStringLen` at `0x180013e64`

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
  v6 = (const struct SchemaEntry * near *)&qword_18006EE10;
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
0x180013c6c  mov     [rsp-28h+arg_8], rdx
0x180013c71  push    rbp
0x180013c72  push    rbx
0x180013c73  push    rsi
0x180013c74  push    rdi
0x180013c75  push    r14
0x180013c77  mov     rbp, rsp
0x180013c7a  sub     rsp, 40h
0x180013c7e  mov     rsi, rdx
0x180013c81  mov     rbx, rcx
0x180013c84  mov     [rbp+bstrString], 0
0x180013c8c  mov     rcx, [rdx]
0x180013c8f  mov     rax, [rcx]
0x180013c92  lea     rdx, [rbp+bstrString]
0x180013c96  mov     rax, [rax+40h]
0x180013c9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c9f  mov     r14d, 1
0x180013ca5  test    eax, eax
0x180013ca7  jns     loc_180013E22
0x180013cad  mov     eax, [rbx+98h]
0x180013cb3  test    eax, eax
0x180013cb5  jnz     loc_180013F02
0x180013cbb  mov     ecx, [rbx]
0x180013cbd  sub     ecx, 10000h
0x180013cc3  jz      loc_180013EA6
0x180013cc9  sub     ecx, r14d
0x180013ccc  jz      loc_180013EA6
0x180013cd2  sub     ecx, r14d
0x180013cd5  jz      short loc_180013CEF
0x180013cd7  sub     ecx, r14d
0x180013cda  jz      short loc_180013CEF
0x180013cdc  sub     ecx, r14d
0x180013cdf  jz      short loc_180013CEF
0x180013ce1  sub     ecx, r14d
0x180013ce4  jz      short loc_180013CEF
0x180013ce6  cmp     ecx, r14d
0x180013ce9  jnz     loc_180013EDA
0x180013cef  movzx   eax, word ptr [rbx]
0x180013cf2  lea     r8, __ImageBase
0x180013cf9  mov     rdi, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r8+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180013d01  add     rdi, 0C80h
0x180013d08  mov     rax, rdi
0x180013d0b  cmp     dword ptr [rax], 0
0x180013d0e  jz      loc_180013EE6
0x180013d14  lea     rcx, [rbx+10h]
0x180013d18  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlWriter@@$1?_GUID_7279fc88_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlWriter@@XZ; _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x180013d1d  mov     r10, rax
0x180013d20  mov     rcx, [rax]
0x180013d23  mov     rax, [rcx+0D8h]
0x180013d2a  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180013d31  mov     r8, [rdi+8]
0x180013d35  lea     rdx, Src
0x180013d3c  mov     rcx, r10
0x180013d3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d44  mov     edi, eax
0x180013d46  test    edi, edi
0x180013d48  jns     short loc_180013D6A
0x180013d4a  mov     rcx, [rbp+bstrString]; bstrString
0x180013d4e  call    cs:__imp_SysFreeString
0x180013d54  nop
0x180013d55  mov     rcx, rsi
0x180013d58  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013d5d  mov     eax, edi
0x180013d5f  add     rsp, 40h
0x180013d63  pop     r14
0x180013d65  pop     rdi
0x180013d66  pop     rsi
0x180013d67  pop     rbx
0x180013d68  pop     rbp
0x180013d69  retn
0x180013d6a  mov     rcx, [rsi]
0x180013d6d  mov     [rbp+var_8], rcx
0x180013d71  test    rcx, rcx
0x180013d74  jz      short loc_180013D83
0x180013d76  mov     rax, [rcx]
0x180013d79  mov     rax, [rax+8]
0x180013d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d82  nop
0x180013d83  lea     rdx, [rbp+var_8]
0x180013d87  mov     rcx, rbx
0x180013d8a  call    ?WriteBaseTriggerProperties@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z; WriteBaseTriggerProperties(TaskXmlWriter &,JobTriggerPtr)
0x180013d8f  mov     edi, eax
0x180013d91  test    eax, eax
0x180013d93  js      short loc_180013D4A
0x180013d95  mov     rdx, rsi; struct JobTriggerPtr *
0x180013d98  lea     rcx, [rbp+var_10]; this
0x180013d9c  call    ??0TimeTriggerPtr@@QEAA@AEBVJobTriggerPtr@@@Z; TimeTriggerPtr::TimeTriggerPtr(JobTriggerPtr const &)
0x180013da1  nop
0x180013da2  mov     [rbp+pbstr], 0
0x180013daa  mov     rcx, [rbp+var_10]
0x180013dae  mov     rax, [rcx]
0x180013db1  lea     rdx, [rbp+pbstr]
0x180013db5  mov     rax, [rax+0A0h]
0x180013dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013dc1  test    eax, eax
0x180013dc3  jns     loc_180013E57
0x180013dc9  mov     rcx, [rbp+pbstr]
0x180013dcd  mov     eax, [rbx+98h]
0x180013dd3  test    eax, eax
0x180013dd5  jnz     loc_180013EF5
0x180013ddb  lea     rcx, [rbx+10h]
0x180013ddf  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlWriter@@$1?_GUID_7279fc88_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlWriter@@XZ; _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x180013de4  mov     rdx, rax
0x180013de7  mov     rcx, [rax]
0x180013dea  mov     rax, [rcx+78h]
0x180013dee  mov     rcx, rdx
0x180013df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013df6  mov     r14d, eax
0x180013df9  mov     rcx, [rbp+pbstr]; bstrString
0x180013dfd  call    cs:__imp_SysFreeString
0x180013e03  nop
0x180013e04  mov     rcx, [rbp+var_10]
0x180013e08  test    rcx, rcx
0x180013e0b  jz      short loc_180013E1A
0x180013e0d  mov     rdx, [rcx]
0x180013e10  mov     rax, [rdx+10h]
0x180013e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e19  nop
0x180013e1a  mov     edi, r14d
0x180013e1d  jmp     loc_180013D4A
0x180013e22  mov     rcx, [rbp+bstrString]; pbstr
0x180013e26  test    rcx, rcx
0x180013e29  jz      loc_180013CAD
0x180013e2f  call    cs:__imp_SysStringLen
0x180013e35  test    eax, eax
0x180013e37  jz      loc_180013CAD
0x180013e3d  mov     r9, [rbp+bstrString]
0x180013e41  mov     edx, 19h
0x180013e46  lea     r8d, [rdx+54h]
0x180013e4a  mov     rcx, rbx
0x180013e4d  call    ?StartElementWithAttribute@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@0PEBG@Z; TaskXmlWriter::StartElementWithAttribute(TaskXmlNodeId,TaskXmlNodeId,ushort const *)
0x180013e52  jmp     loc_180013D44
0x180013e57  mov     rcx, [rbp+pbstr]; pbstr
0x180013e5b  test    rcx, rcx
0x180013e5e  jz      loc_180013DCD
0x180013e64  call    cs:__imp_SysStringLen
0x180013e6a  test    eax, eax
0x180013e6c  jz      loc_180013DC9
0x180013e72  mov     r8, [rbp+pbstr]
0x180013e76  mov     edx, 1Ah
0x180013e7b  mov     rcx, rbx
0x180013e7e  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180013e83  mov     edi, eax
0x180013e85  test    eax, eax
0x180013e87  jns     loc_180013DC9
0x180013e8d  mov     rcx, [rbp+pbstr]; bstrString
0x180013e91  call    cs:__imp_SysFreeString
0x180013e97  nop
0x180013e98  lea     rcx, [rbp+var_10]
0x180013e9c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013ea1  jmp     loc_180013D4A
0x180013ea6  xor     edx, edx
0x180013ea8  movzx   r9d, word ptr [rbx]
0x180013eac  lea     r8, __ImageBase
0x180013eb3  cmp     rdx, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r8+r9*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x180013ebb  jnb     short loc_180013EDA
0x180013ebd  mov     rdi, rdx
0x180013ec0  shl     rdi, 7
0x180013ec4  add     rdi, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r8+r9*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180013ecc  cmp     dword ptr [rdi], 19h
0x180013ecf  jz      loc_180013D14
0x180013ed5  add     rdx, r14
0x180013ed8  jmp     short loc_180013EB3
0x180013eda  mov     rdi, cs:off_180059F80
0x180013ee1  jmp     loc_180013D08
0x180013ee6  mov     [rbx+98h], r14d
0x180013eed  mov     edi, r14d
0x180013ef0  jmp     loc_180013D46
0x180013ef5  dec     eax
0x180013ef7  mov     [rbx+98h], eax
0x180013efd  jmp     loc_180013DFD
0x180013f02  inc     eax
0x180013f04  mov     [rbx+98h], eax
0x180013f0a  jmp     short loc_180013EED
```
