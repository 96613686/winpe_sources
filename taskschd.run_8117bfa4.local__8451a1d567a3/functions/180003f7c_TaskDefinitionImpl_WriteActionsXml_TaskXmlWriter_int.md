# TaskDefinitionImpl::WriteActionsXml(TaskXmlWriter &,int)

- ea: `0x180003f7c`
- end: `0x1800042f6`
- name: `?WriteActionsXml@TaskDefinitionImpl@@AEAAJAEAVTaskXmlWriter@@H@Z`
- size: `890`
- prototype: `__int64 __fastcall(TaskDefinitionImpl *__hidden this, struct TaskXmlWriter *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800052c0`

## callees

- `0x180003f7c`
- `0x180011eb8`
- `0x180014700`
- `0x1800149f8`
- `0x180016900`
- `0x180035a5c`
- `0x18003b73c`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180004098`
- `OLEAUT32!__imp_SysFreeString` at `0x180004123`
- `OLEAUT32!__imp_SysFreeString` at `0x180004098`
- `OLEAUT32!__imp_SysFreeString` at `0x180004123`
- `OLEAUT32!__imp_SysStringLen` at `0x1800041f0`
- `OLEAUT32!__imp_SysStringLen` at `0x1800041f0`

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
  v9 = (const struct SchemaEntry * near *)&qword_180072DF0;
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
0x180003f7c  mov     [rsp-28h+arg_8], rbx
0x180003f81  mov     [rsp-28h+arg_10], rsi
0x180003f86  push    rbp
0x180003f87  push    rdi
0x180003f88  push    r12
0x180003f8a  push    r14
0x180003f8c  push    r15
0x180003f8e  mov     rbp, rsp
0x180003f91  sub     rsp, 50h
0x180003f95  mov     r12d, r8d
0x180003f98  mov     rsi, rdx
0x180003f9b  mov     [rbp+bstrString], 0
0x180003fa3  mov     [rbp+arg_0], 0
0x180003fab  mov     rax, [rcx]
0x180003fae  lea     rdx, [rbp+arg_0]
0x180003fb2  mov     rax, [rax+88h]
0x180003fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fbe  mov     ebx, eax
0x180003fc0  test    eax, eax
0x180003fc2  js      loc_18000423E
0x180003fc8  mov     rcx, [rbp+arg_0]
0x180003fcc  mov     rax, [rcx]
0x180003fcf  lea     rdx, [rbp+bstrString]
0x180003fd3  mov     rax, [rax+78h]
0x180003fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fdc  test    eax, eax
0x180003fde  jns     loc_1800041E3
0x180003fe4  lea     rdi, [rsi+98h]
0x180003feb  mov     eax, [rdi]
0x180003fed  test    eax, eax
0x180003fef  jnz     loc_1800042E2
0x180003ff5  mov     ecx, [rsi]
0x180003ff7  sub     ecx, 10000h
0x180003ffd  jz      loc_180004259
0x180004003  sub     ecx, 1
0x180004006  jz      loc_180004259
0x18000400c  sub     ecx, 1
0x18000400f  jz      short loc_180004029
0x180004011  sub     ecx, 1
0x180004014  jz      short loc_180004029
0x180004016  sub     ecx, 1
0x180004019  jz      short loc_180004029
0x18000401b  sub     ecx, 1
0x18000401e  jz      short loc_180004029
0x180004020  cmp     ecx, 1
0x180004023  jnz     loc_1800042C1
0x180004029  movzx   eax, word ptr [rsi]
0x18000402c  lea     r9, __ImageBase
0x180004033  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r9+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18000403b  add     r8, 3300h
0x180004042  mov     rax, r8
0x180004045  cmp     dword ptr [rax], 0
0x180004048  jz      short loc_1800040C0
0x18000404a  mov     rcx, [rsi+10h]
0x18000404e  test    rcx, rcx
0x180004051  jz      loc_1800042EB
0x180004057  mov     rax, [rcx]
0x18000405a  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180004061  mov     r8, [r8+8]
0x180004065  lea     rdx, Src
0x18000406c  mov     rax, [rax+0D8h]
0x180004073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004078  mov     ebx, eax
0x18000407a  test    eax, eax
0x18000407c  jns     short loc_1800040C6
0x18000407e  mov     rcx, [rbp+arg_0]
0x180004082  test    rcx, rcx
0x180004085  jz      short loc_180004094
0x180004087  mov     rdx, [rcx]
0x18000408a  mov     rax, [rdx+10h]
0x18000408e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004093  nop
0x180004094  mov     rcx, [rbp+bstrString]; bstrString
0x180004098  call    cs:__imp_SysFreeString
0x18000409f  nop     dword ptr [rax+rax+00h]
0x1800040a4  mov     eax, ebx
0x1800040a6  lea     r11, [rsp+50h+var_s0]
0x1800040ab  mov     rbx, [r11+38h]
0x1800040af  mov     rsi, [r11+40h]
0x1800040b3  mov     rsp, r11
0x1800040b6  pop     r15
0x1800040b8  pop     r14
0x1800040ba  pop     r12
0x1800040bc  pop     rdi
0x1800040bd  pop     rbp
0x1800040be  retn
0x1800040c0  mov     dword ptr [rdi], 1
0x1800040c6  mov     r14d, 1
0x1800040cc  lea     rcx, [rbp+arg_0]
0x1800040d0  call    ?GetCount@?$CollectionPtr@UITaskNamedValueCollection@@UITaskNamedValuePair@@@@QEAAJXZ; CollectionPtr<ITaskNamedValueCollection,ITaskNamedValuePair>::GetCount(void)
0x1800040d5  cmp     r14d, eax
0x1800040d8  jle     short loc_180004136
0x1800040da  mov     eax, [rdi]
0x1800040dc  test    eax, eax
0x1800040de  jnz     loc_1800042CD
0x1800040e4  lea     rcx, [rsi+10h]
0x1800040e8  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlWriter@@$1?_GUID_7279fc88_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlWriter@@XZ; _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x1800040ed  mov     rdx, rax
0x1800040f0  mov     rcx, [rax]
0x1800040f3  mov     rax, [rcx+78h]
0x1800040f7  mov     rcx, rdx
0x1800040fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040ff  mov     ebx, eax
0x180004101  test    eax, eax
0x180004103  js      loc_1800041C8
0x180004109  mov     rcx, [rbp+arg_0]
0x18000410d  test    rcx, rcx
0x180004110  jz      short loc_18000411F
0x180004112  mov     rax, [rcx]
0x180004115  mov     rax, [rax+10h]
0x180004119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000411e  nop
0x18000411f  mov     rcx, [rbp+bstrString]; bstrString
0x180004123  call    cs:__imp_SysFreeString
0x18000412a  nop     dword ptr [rax+rax+00h]
0x18000412f  xor     eax, eax
0x180004131  jmp     loc_1800040A6
0x180004136  mov     r8d, r14d
0x180004139  lea     rdx, [rbp+var_18]
0x18000413d  lea     rcx, [rbp+arg_0]
0x180004141  call    ?GetItem@?$CollectionPtr@UIActionCollection@@UIAction@@@@QEAA?AV?$CComPtr@UIAction@@@ATL@@J@Z; CollectionPtr<IActionCollection,IAction>::GetItem(long)
0x180004146  mov     rbx, [rax]
0x180004149  mov     [rbp+var_10], rbx
0x18000414d  test    rbx, rbx
0x180004150  jz      short loc_180004162
0x180004152  mov     rax, [rbx]
0x180004155  mov     rcx, rbx
0x180004158  mov     rax, [rax+8]
0x18000415c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004161  nop
0x180004162  mov     rcx, [rbp+var_18]
0x180004166  test    rcx, rcx
0x180004169  jz      short loc_180004178
0x18000416b  mov     rax, [rcx]
0x18000416e  mov     rax, [rax+10h]
0x180004172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004177  nop
0x180004178  mov     [rbp+var_20], rbx
0x18000417c  test    rbx, rbx
0x18000417f  jz      short loc_180004191
0x180004181  mov     rax, [rbx]
0x180004184  mov     rcx, rbx
0x180004187  mov     rax, [rax+8]
0x18000418b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004190  nop
0x180004191  mov     r8d, r12d
0x180004194  lea     rdx, [rbp+var_20]
0x180004198  mov     rcx, rsi
0x18000419b  call    ?WriteTask@@YAJAEAVTaskXmlWriter@@VTaskPtr@@H@Z; WriteTask(TaskXmlWriter &,TaskPtr,int)
0x1800041a0  mov     r15d, eax
0x1800041a3  test    eax, eax
0x1800041a5  js      loc_18000428E
0x1800041ab  test    rbx, rbx
0x1800041ae  jz      short loc_1800041C0
0x1800041b0  mov     rax, [rbx]
0x1800041b3  mov     rcx, rbx
0x1800041b6  mov     rax, [rax+10h]
0x1800041ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041bf  nop
0x1800041c0  inc     r14d
0x1800041c3  jmp     loc_1800040CC
0x1800041c8  mov     rcx, [rbp+arg_0]
0x1800041cc  test    rcx, rcx
0x1800041cf  jz      short loc_1800041DE
0x1800041d1  mov     rdx, [rcx]
0x1800041d4  mov     rax, [rdx+10h]
0x1800041d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041dd  nop
0x1800041de  jmp     loc_180004094
0x1800041e3  mov     rcx, [rbp+bstrString]; pbstr
0x1800041e7  test    rcx, rcx
0x1800041ea  jz      loc_180003FE4
0x1800041f0  call    cs:__imp_SysStringLen
0x1800041f7  nop     dword ptr [rax+rax+00h]
0x1800041fc  test    eax, eax
0x1800041fe  jz      loc_180003FE4
0x180004204  mov     r9, [rbp+bstrString]
0x180004208  mov     edx, 66h ; 'f'
0x18000420d  lea     r8d, [rdx+8]
0x180004211  mov     rcx, rsi
0x180004214  call    ?StartElementWithAttribute@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@0PEBG@Z; TaskXmlWriter::StartElementWithAttribute(TaskXmlNodeId,TaskXmlNodeId,ushort const *)
0x180004219  mov     ebx, eax
0x18000421b  test    eax, eax
0x18000421d  jns     loc_1800042D6
0x180004223  mov     rcx, [rbp+arg_0]
0x180004227  test    rcx, rcx
0x18000422a  jz      short loc_180004239
0x18000422c  mov     rdx, [rcx]
0x18000422f  mov     rax, [rdx+10h]
0x180004233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004238  nop
0x180004239  jmp     loc_180004094
0x18000423e  mov     rcx, [rbp+arg_0]
0x180004242  test    rcx, rcx
0x180004245  jz      short loc_180004254
0x180004247  mov     rdx, [rcx]
0x18000424a  mov     rax, [rdx+10h]
0x18000424e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004253  nop
0x180004254  jmp     loc_180004094
0x180004259  xor     edx, edx
0x18000425b  movzx   r10d, word ptr [rsi]
0x18000425f  lea     r9, __ImageBase
0x180004266  cmp     rdx, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r9+r10*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x18000426e  jnb     short loc_1800042C1
0x180004270  mov     r8, rdx
0x180004273  shl     r8, 7
0x180004277  add     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r9+r10*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18000427f  cmp     dword ptr [r8], 66h ; 'f'
0x180004283  jz      loc_18000404A
0x180004289  inc     rdx
0x18000428c  jmp     short loc_180004266
0x18000428e  test    rbx, rbx
0x180004291  jz      short loc_1800042A3
0x180004293  mov     rax, [rbx]
0x180004296  mov     rcx, rbx
0x180004299  mov     rax, [rax+10h]
0x18000429d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042a2  nop
0x1800042a3  mov     rcx, [rbp+arg_0]
0x1800042a7  test    rcx, rcx
0x1800042aa  jz      short loc_1800042B9
0x1800042ac  mov     rax, [rcx]
0x1800042af  mov     rax, [rax+10h]
0x1800042b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042b8  nop
0x1800042b9  mov     ebx, r15d
0x1800042bc  jmp     loc_180004094
0x1800042c1  mov     r8, cs:off_18005DF68
0x1800042c8  jmp     loc_180004042
0x1800042cd  dec     eax
0x1800042cf  mov     [rdi], eax
0x1800042d1  jmp     loc_180004109
0x1800042d6  lea     rdi, [rsi+98h]
0x1800042dd  jmp     loc_1800040C6
0x1800042e2  inc     eax
0x1800042e4  mov     [rdi], eax
0x1800042e6  jmp     loc_1800040C6
0x1800042eb  mov     ecx, 80004003h; int
0x1800042f0  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
