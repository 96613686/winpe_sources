# TaskDefinitionImpl::WriteActionsXml(TaskXmlWriter &,int)

- ea: `0x180003d68`
- end: `0x1800040cf`
- name: `?WriteActionsXml@TaskDefinitionImpl@@AEAAJAEAVTaskXmlWriter@@H@Z`
- size: `871`
- prototype: `__int64 __fastcall(TaskDefinitionImpl *__hidden this, struct TaskXmlWriter *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004fd0`

## callees

- `0x180001f14`
- `0x180003d68`
- `0x180011594`
- `0x1800138e0`
- `0x1800157e4`
- `0x180032d24`
- `0x1800383f4`
- `0x180054010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180003e84`
- `OLEAUT32!__imp_SysFreeString` at `0x180003f08`
- `OLEAUT32!__imp_SysFreeString` at `0x180003e84`
- `OLEAUT32!__imp_SysFreeString` at `0x180003f08`
- `OLEAUT32!__imp_SysStringLen` at `0x180003fcf`
- `OLEAUT32!__imp_SysStringLen` at `0x180003fcf`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall TaskDefinitionImpl::WriteActionsXml(TaskDefinitionImpl *this, struct TaskXmlWriter *a2, int a3)
{
  int started; // ebx
  unsigned __int64 *v6; // rdx
  _DWORD *v7; // rdi
  int v8; // eax
  const struct SchemaEntry * near *v9; // r8
  __int64 v10; // rcx
  int i; // r14d
  __int64 v13; // rax
  __int64 v14; // rbx
  int v15; // r15d
  __int64 v16; // r10
  __int64 v17; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v18[3]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v19; // [rsp+80h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp+48h] BYREF

  bstrString = 0;
  v19 = 0;
  started = (*(__int64 (__fastcall **)(TaskDefinitionImpl *, __int64 *))(*(_QWORD *)this + 136LL))(this, &v19);
  if ( started < 0 )
  {
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    goto LABEL_16;
  }
  if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v19 + 120LL))(v19, &bstrString) >= 0
    && bstrString
    && SysStringLen(bstrString) )
  {
    started = TaskXmlWriter::StartElementWithAttribute((unsigned int *)a2, 102, 110, (__int64)bstrString);
    if ( started < 0 )
    {
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      goto LABEL_16;
    }
    v7 = (_DWORD *)((char *)a2 + 152);
LABEL_18:
    for ( i = 1; i <= (int)CollectionPtr<ITaskNamedValueCollection,ITaskNamedValuePair>::GetCount(&v19); ++i )
    {
      v14 = *(_QWORD *)CollectionPtr<IActionCollection,IAction>::GetItem(&v19, v18, (unsigned int)i);
      v18[1] = v14;
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
      if ( v18[0] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v18[0] + 16LL))(v18[0]);
      v17 = v14;
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
      v15 = WriteTask((__int64)a2, (struct TaskPtr *)&v17, a3);
      if ( v15 < 0 )
      {
        if ( v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        if ( v19 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        started = v15;
        goto LABEL_16;
      }
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    if ( *v7 )
    {
      --*v7;
    }
    else
    {
      v13 = _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->((__int64 *)a2 + 2);
      started = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 120LL))(v13);
      if ( started < 0 )
      {
        if ( v19 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        goto LABEL_16;
      }
    }
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    SysFreeString(bstrString);
    return 0;
  }
  v7 = (_DWORD *)((char *)a2 + 152);
  v8 = *((_DWORD *)a2 + 38);
  if ( v8 )
  {
    *v7 = v8 + 1;
    goto LABEL_18;
  }
  if ( *(_DWORD *)a2 == 0x10000 || *(_DWORD *)a2 == 65537 )
  {
    v6 = 0;
    v16 = *(unsigned __int16 *)a2;
    while ( v6 < (&Schema::schemaEntriesCount)[v16] )
    {
      v9 = &(&Schema::schemaEntries)[v16][16 * (_QWORD)v6];
      if ( *(_DWORD *)v9 == 102 )
        goto LABEL_12;
      v6 = (unsigned __int64 *)((char *)v6 + 1);
    }
  }
  else if ( *(_DWORD *)a2 == 65538
         || *(_DWORD *)a2 == 65539
         || *(_DWORD *)a2 == 65540
         || (unsigned int)(*(_DWORD *)a2 - 65541) <= 1 )
  {
    v9 = (&Schema::schemaEntries)[*(unsigned __int16 *)a2] + 1632;
    goto LABEL_11;
  }
  v9 = (const struct SchemaEntry * near *)&qword_18006EE10;
LABEL_11:
  if ( !*(_DWORD *)v9 )
  {
    *v7 = 1;
    goto LABEL_18;
  }
LABEL_12:
  v10 = *((_QWORD *)a2 + 2);
  if ( !v10 )
    _com_issue_error(-2147467261, (struct IErrorInfo *)v6);
  started = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const struct SchemaEntry *, wchar_t *const))(*(_QWORD *)v10 + 216LL))(
              v10,
              &Src,
              v9[1],
              Schema::namespaceUri);
  if ( started >= 0 )
    goto LABEL_18;
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
LABEL_16:
  SysFreeString(bstrString);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180003d68  mov     [rsp-28h+arg_8], rbx
0x180003d6d  mov     [rsp-28h+arg_10], rsi
0x180003d72  push    rbp
0x180003d73  push    rdi
0x180003d74  push    r12
0x180003d76  push    r14
0x180003d78  push    r15
0x180003d7a  mov     rbp, rsp
0x180003d7d  sub     rsp, 50h
0x180003d81  mov     r12d, r8d
0x180003d84  mov     rsi, rdx
0x180003d87  mov     [rbp+bstrString], 0
0x180003d8f  mov     [rbp+arg_0], 0
0x180003d97  mov     rax, [rcx]
0x180003d9a  lea     rdx, [rbp+arg_0]
0x180003d9e  mov     rax, [rax+88h]
0x180003da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003daa  mov     ebx, eax
0x180003dac  test    eax, eax
0x180003dae  js      loc_180004017
0x180003db4  mov     rcx, [rbp+arg_0]
0x180003db8  mov     rax, [rcx]
0x180003dbb  lea     rdx, [rbp+bstrString]
0x180003dbf  mov     rax, [rax+78h]
0x180003dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dc8  test    eax, eax
0x180003dca  jns     loc_180003FC2
0x180003dd0  lea     rdi, [rsi+98h]
0x180003dd7  mov     eax, [rdi]
0x180003dd9  test    eax, eax
0x180003ddb  jnz     loc_1800040BB
0x180003de1  mov     ecx, [rsi]
0x180003de3  sub     ecx, 10000h
0x180003de9  jz      loc_180004032
0x180003def  sub     ecx, 1
0x180003df2  jz      loc_180004032
0x180003df8  sub     ecx, 1
0x180003dfb  jz      short loc_180003E15
0x180003dfd  sub     ecx, 1
0x180003e00  jz      short loc_180003E15
0x180003e02  sub     ecx, 1
0x180003e05  jz      short loc_180003E15
0x180003e07  sub     ecx, 1
0x180003e0a  jz      short loc_180003E15
0x180003e0c  cmp     ecx, 1
0x180003e0f  jnz     loc_18000409A
0x180003e15  movzx   eax, word ptr [rsi]
0x180003e18  lea     r9, __ImageBase
0x180003e1f  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r9+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180003e27  add     r8, 3300h
0x180003e2e  mov     rax, r8
0x180003e31  cmp     dword ptr [rax], 0
0x180003e34  jz      short loc_180003EA5
0x180003e36  mov     rcx, [rsi+10h]
0x180003e3a  test    rcx, rcx
0x180003e3d  jz      loc_1800040C4
0x180003e43  mov     rax, [rcx]
0x180003e46  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180003e4d  mov     r8, [r8+8]
0x180003e51  lea     rdx, Src
0x180003e58  mov     rax, [rax+0D8h]
0x180003e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e64  mov     ebx, eax
0x180003e66  test    eax, eax
0x180003e68  jns     short loc_180003EAB
0x180003e6a  mov     rcx, [rbp+arg_0]
0x180003e6e  test    rcx, rcx
0x180003e71  jz      short loc_180003E80
0x180003e73  mov     rdx, [rcx]
0x180003e76  mov     rax, [rdx+10h]
0x180003e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e7f  nop
0x180003e80  mov     rcx, [rbp+bstrString]; bstrString
0x180003e84  call    cs:__imp_SysFreeString
0x180003e8a  mov     eax, ebx
0x180003e8c  lea     r11, [rsp+50h+var_s0]
0x180003e91  mov     rbx, [r11+38h]
0x180003e95  mov     rsi, [r11+40h]
0x180003e99  mov     rsp, r11
0x180003e9c  pop     r15
0x180003e9e  pop     r14
0x180003ea0  pop     r12
0x180003ea2  pop     rdi
0x180003ea3  pop     rbp
0x180003ea4  retn
0x180003ea5  mov     dword ptr [rdi], 1
0x180003eab  mov     r14d, 1
0x180003eb1  lea     rcx, [rbp+arg_0]
0x180003eb5  call    ?GetCount@?$CollectionPtr@UITaskNamedValueCollection@@UITaskNamedValuePair@@@@QEAAJXZ; CollectionPtr<ITaskNamedValueCollection,ITaskNamedValuePair>::GetCount(void)
0x180003eba  cmp     r14d, eax
0x180003ebd  jle     short loc_180003F15
0x180003ebf  mov     eax, [rdi]
0x180003ec1  test    eax, eax
0x180003ec3  jnz     loc_1800040A6
0x180003ec9  lea     rcx, [rsi+10h]
0x180003ecd  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlWriter@@$1?_GUID_7279fc88_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlWriter@@XZ; _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x180003ed2  mov     rdx, rax
0x180003ed5  mov     rcx, [rax]
0x180003ed8  mov     rax, [rcx+78h]
0x180003edc  mov     rcx, rdx
0x180003edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ee4  mov     ebx, eax
0x180003ee6  test    eax, eax
0x180003ee8  js      loc_180003FA7
0x180003eee  mov     rcx, [rbp+arg_0]
0x180003ef2  test    rcx, rcx
0x180003ef5  jz      short loc_180003F04
0x180003ef7  mov     rax, [rcx]
0x180003efa  mov     rax, [rax+10h]
0x180003efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f03  nop
0x180003f04  mov     rcx, [rbp+bstrString]; bstrString
0x180003f08  call    cs:__imp_SysFreeString
0x180003f0e  xor     eax, eax
0x180003f10  jmp     loc_180003E8C
0x180003f15  mov     r8d, r14d
0x180003f18  lea     rdx, [rbp+var_18]
0x180003f1c  lea     rcx, [rbp+arg_0]
0x180003f20  call    ?GetItem@?$CollectionPtr@UIActionCollection@@UIAction@@@@QEAA?AV?$CComPtr@UIAction@@@ATL@@J@Z; CollectionPtr<IActionCollection,IAction>::GetItem(long)
0x180003f25  mov     rbx, [rax]
0x180003f28  mov     [rbp+var_10], rbx
0x180003f2c  test    rbx, rbx
0x180003f2f  jz      short loc_180003F41
0x180003f31  mov     rax, [rbx]
0x180003f34  mov     rcx, rbx
0x180003f37  mov     rax, [rax+8]
0x180003f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f40  nop
0x180003f41  mov     rcx, [rbp+var_18]
0x180003f45  test    rcx, rcx
0x180003f48  jz      short loc_180003F57
0x180003f4a  mov     rax, [rcx]
0x180003f4d  mov     rax, [rax+10h]
0x180003f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f56  nop
0x180003f57  mov     [rbp+var_20], rbx
0x180003f5b  test    rbx, rbx
0x180003f5e  jz      short loc_180003F70
0x180003f60  mov     rax, [rbx]
0x180003f63  mov     rcx, rbx
0x180003f66  mov     rax, [rax+8]
0x180003f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f6f  nop
0x180003f70  mov     r8d, r12d
0x180003f73  lea     rdx, [rbp+var_20]
0x180003f77  mov     rcx, rsi
0x180003f7a  call    ?WriteTask@@YAJAEAVTaskXmlWriter@@VTaskPtr@@H@Z; WriteTask(TaskXmlWriter &,TaskPtr,int)
0x180003f7f  mov     r15d, eax
0x180003f82  test    eax, eax
0x180003f84  js      loc_180004067
0x180003f8a  test    rbx, rbx
0x180003f8d  jz      short loc_180003F9F
0x180003f8f  mov     rax, [rbx]
0x180003f92  mov     rcx, rbx
0x180003f95  mov     rax, [rax+10h]
0x180003f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f9e  nop
0x180003f9f  inc     r14d
0x180003fa2  jmp     loc_180003EB1
0x180003fa7  mov     rcx, [rbp+arg_0]
0x180003fab  test    rcx, rcx
0x180003fae  jz      short loc_180003FBD
0x180003fb0  mov     rdx, [rcx]
0x180003fb3  mov     rax, [rdx+10h]
0x180003fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fbc  nop
0x180003fbd  jmp     loc_180003E80
0x180003fc2  mov     rcx, [rbp+bstrString]; pbstr
0x180003fc6  test    rcx, rcx
0x180003fc9  jz      loc_180003DD0
0x180003fcf  call    cs:__imp_SysStringLen
0x180003fd5  test    eax, eax
0x180003fd7  jz      loc_180003DD0
0x180003fdd  mov     r9, [rbp+bstrString]
0x180003fe1  mov     edx, 66h ; 'f'
0x180003fe6  lea     r8d, [rdx+8]
0x180003fea  mov     rcx, rsi
0x180003fed  call    ?StartElementWithAttribute@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@0PEBG@Z; TaskXmlWriter::StartElementWithAttribute(TaskXmlNodeId,TaskXmlNodeId,ushort const *)
0x180003ff2  mov     ebx, eax
0x180003ff4  test    eax, eax
0x180003ff6  jns     loc_1800040AF
0x180003ffc  mov     rcx, [rbp+arg_0]
0x180004000  test    rcx, rcx
0x180004003  jz      short loc_180004012
0x180004005  mov     rdx, [rcx]
0x180004008  mov     rax, [rdx+10h]
0x18000400c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004011  nop
0x180004012  jmp     loc_180003E80
0x180004017  mov     rcx, [rbp+arg_0]
0x18000401b  test    rcx, rcx
0x18000401e  jz      short loc_18000402D
0x180004020  mov     rdx, [rcx]
0x180004023  mov     rax, [rdx+10h]
0x180004027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000402c  nop
0x18000402d  jmp     loc_180003E80
0x180004032  xor     edx, edx
0x180004034  movzx   r10d, word ptr [rsi]
0x180004038  lea     r9, __ImageBase
0x18000403f  cmp     rdx, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r9+r10*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x180004047  jnb     short loc_18000409A
0x180004049  mov     r8, rdx
0x18000404c  shl     r8, 7
0x180004050  add     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r9+r10*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180004058  cmp     dword ptr [r8], 66h ; 'f'
0x18000405c  jz      loc_180003E36
0x180004062  inc     rdx
0x180004065  jmp     short loc_18000403F
0x180004067  test    rbx, rbx
0x18000406a  jz      short loc_18000407C
0x18000406c  mov     rax, [rbx]
0x18000406f  mov     rcx, rbx
0x180004072  mov     rax, [rax+10h]
0x180004076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000407b  nop
0x18000407c  mov     rcx, [rbp+arg_0]
0x180004080  test    rcx, rcx
0x180004083  jz      short loc_180004092
0x180004085  mov     rax, [rcx]
0x180004088  mov     rax, [rax+10h]
0x18000408c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004091  nop
0x180004092  mov     ebx, r15d
0x180004095  jmp     loc_180003E80
0x18000409a  mov     r8, cs:off_180059F80
0x1800040a1  jmp     loc_180003E2E
0x1800040a6  dec     eax
0x1800040a8  mov     [rdi], eax
0x1800040aa  jmp     loc_180003EEE
0x1800040af  lea     rdi, [rsi+98h]
0x1800040b6  jmp     loc_180003EAB
0x1800040bb  inc     eax
0x1800040bd  mov     [rdi], eax
0x1800040bf  jmp     loc_180003EAB
0x1800040c4  mov     ecx, 80004003h; int
0x1800040c9  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
