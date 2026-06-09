# TaskDefinitionImpl::WritePropIdentificationXml(TaskXmlWriter &,int)

- ea: `0x1800025b0`
- end: `0x180002da0`
- name: `?WritePropIdentificationXml@TaskDefinitionImpl@@AEAAJAEAVTaskXmlWriter@@H@Z`
- size: `2032`
- prototype: `__int64 __fastcall(TaskDefinitionImpl *__hidden this, struct TaskXmlWriter *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800052c0`

## callees

- `0x180001f1c`
- `0x1800025b0`
- `0x180003a30`
- `0x180003f30`
- `0x180011054`
- `0x18001126c`
- `0x18001186c`
- `0x180016900`
- `0x18003b74c`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800027fd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000280e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000281f`
- `OLEAUT32!__imp_SysFreeString` at `0x180002830`
- `OLEAUT32!__imp_SysFreeString` at `0x180002841`
- `OLEAUT32!__imp_SysFreeString` at `0x180002852`
- `OLEAUT32!__imp_SysFreeString` at `0x180002863`
- `OLEAUT32!__imp_SysFreeString` at `0x18000288c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000289d`
- `OLEAUT32!__imp_SysFreeString` at `0x180002a16`
- `OLEAUT32!__imp_SysFreeString` at `0x180002a27`
- `OLEAUT32!__imp_SysFreeString` at `0x180002a38`
- `OLEAUT32!__imp_SysFreeString` at `0x180002a49`
- `OLEAUT32!__imp_SysFreeString` at `0x180002a5a`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c68`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c79`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c8a`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c9b`
- `OLEAUT32!__imp_SysFreeString` at `0x180002cac`
- `OLEAUT32!__imp_SysFreeString` at `0x180002cbd`
- `OLEAUT32!__imp_SysFreeString` at `0x180002cce`
- `OLEAUT32!__imp_SysFreeString` at `0x1800027fd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000280e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000281f`
- `OLEAUT32!__imp_SysFreeString` at `0x180002830`
- `OLEAUT32!__imp_SysFreeString` at `0x180002841`
- `OLEAUT32!__imp_SysFreeString` at `0x180002852`
- `OLEAUT32!__imp_SysFreeString` at `0x180002863`
- `OLEAUT32!__imp_SysFreeString` at `0x18000288c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000289d`
- `OLEAUT32!__imp_SysFreeString` at `0x180002a16`
- `OLEAUT32!__imp_SysFreeString` at `0x180002a27`
- `OLEAUT32!__imp_SysFreeString` at `0x180002a38`
- `OLEAUT32!__imp_SysFreeString` at `0x180002a49`
- `OLEAUT32!__imp_SysFreeString` at `0x180002a5a`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c68`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c79`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c8a`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c9b`
- `OLEAUT32!__imp_SysFreeString` at `0x180002cac`
- `OLEAUT32!__imp_SysFreeString` at `0x180002cbd`
- `OLEAUT32!__imp_SysFreeString` at `0x180002cce`
- `OLEAUT32!__imp_SysStringLen` at `0x1800028d1`
- `OLEAUT32!__imp_SysStringLen` at `0x180002901`
- `OLEAUT32!__imp_SysStringLen` at `0x1800029e3`
- `OLEAUT32!__imp_SysStringLen` at `0x180002a78`
- `OLEAUT32!__imp_SysStringLen` at `0x180002aa8`
- `OLEAUT32!__imp_SysStringLen` at `0x180002ae5`
- `OLEAUT32!__imp_SysStringLen` at `0x180002b26`
- `OLEAUT32!__imp_SysStringLen` at `0x1800028d1`
- `OLEAUT32!__imp_SysStringLen` at `0x180002901`
- `OLEAUT32!__imp_SysStringLen` at `0x1800029e3`
- `OLEAUT32!__imp_SysStringLen` at `0x180002a78`
- `OLEAUT32!__imp_SysStringLen` at `0x180002aa8`
- `OLEAUT32!__imp_SysStringLen` at `0x180002ae5`
- `OLEAUT32!__imp_SysStringLen` at `0x180002b26`
- `OLEAUT32!__imp_VariantInit` at `0x180002779`
- `OLEAUT32!__imp_VariantInit` at `0x180002779`
- `OLEAUT32!__imp_VariantClear` at `0x1800027ec`
- `OLEAUT32!__imp_VariantClear` at `0x180002b75`
- `OLEAUT32!__imp_VariantClear` at `0x180002c57`
- `OLEAUT32!__imp_VariantClear` at `0x1800027ec`
- `OLEAUT32!__imp_VariantClear` at `0x180002b75`
- `OLEAUT32!__imp_VariantClear` at `0x180002c57`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall TaskDefinitionImpl::WritePropIdentificationXml(
        TaskDefinitionImpl *this,
        unsigned __int64 a2,
        int a3)
{
  struct TaskXmlWriter *v4; // rbx
  RegistrationInfoImpl *v6; // r13
  int v7; // eax
  int v8; // r8d
  const struct SchemaEntry * near *v9; // r8
  __int64 v10; // rcx
  __int64 result; // rax
  int RawSource; // eax
  int RawAuthor; // eax
  int RawDescription; // eax
  int RawDocumentation; // eax
  int v16; // eax
  __int64 v17; // rax
  int v18; // ebx
  int v19; // edi
  int v20; // eax
  unsigned __int64 v21; // rdx
  const struct SchemaEntry * near *v22; // r8
  __int64 v23; // rcx
  BSTR v24; // r15
  int v25; // eax
  __int64 v26; // rax
  const unsigned __int64 near *v27; // r9
  __int64 v28; // r10
  unsigned __int64 v29; // r9
  __int64 v30; // rax
  BSTR v31; // [rsp+30h] [rbp-40h] BYREF
  BSTR v32; // [rsp+38h] [rbp-38h] BYREF
  BSTR v33; // [rsp+40h] [rbp-30h] BYREF
  BSTR v34; // [rsp+48h] [rbp-28h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-18h] BYREF
  BSTR pbstr; // [rsp+B0h] [rbp+40h] BYREF
  BSTR v38; // [rsp+C8h] [rbp+58h] BYREF

  v4 = (struct TaskXmlWriter *)a2;
  v6 = (RegistrationInfoImpl *)*((_QWORD *)this + 9);
  if ( !v6 )
    return 0;
  v7 = *(_DWORD *)(a2 + 152);
  if ( v7 )
  {
    *(_DWORD *)(a2 + 152) = v7 + 1;
    goto LABEL_8;
  }
  v8 = *(_DWORD *)a2;
  if ( *(_DWORD *)a2 == 65542 )
  {
LABEL_4:
    v9 = (&Schema::schemaEntries)[(unsigned __int16)v8] + 48;
  }
  else
  {
    switch ( v8 )
    {
      case 65536:
      case 65537:
        a2 = 0;
        v27 = (&Schema::schemaEntriesCount)[(unsigned __int16)v8];
        v28 = 8LL * (unsigned __int16)v8 + 384824;
        break;
      case 65538:
      case 65539:
      case 65540:
      case 65541:
        goto LABEL_4;
      default:
        goto LABEL_89;
    }
    while ( a2 < (unsigned __int64)v27 )
    {
      v9 = (const struct SchemaEntry * near *)(*(_QWORD *)((char *)&_ImageBase + v28) + (a2 << 7));
      if ( *(_DWORD *)v9 == 3 )
        goto LABEL_6;
      ++a2;
    }
LABEL_89:
    v9 = (const struct SchemaEntry * near *)&qword_180072DF0;
  }
  if ( !*(_DWORD *)v9 )
  {
    *((_DWORD *)v4 + 38) = 1;
    goto LABEL_8;
  }
LABEL_6:
  v10 = *((_QWORD *)v4 + 2);
  if ( !v10 )
    _com_raise_error(-2147467261, (struct IErrorInfo *)a2);
  result = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const struct SchemaEntry *, wchar_t *const))(*(_QWORD *)v10 + 216LL))(
             v10,
             &Src,
             v9[1],
             Schema::namespaceUri);
  if ( (int)result >= 0 )
  {
LABEL_8:
    pbstr = 0;
    if ( a3 )
      RawSource = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)this + 9) + 184LL))(
                    *((_QWORD *)this + 9),
                    &pbstr);
    else
      RawSource = RegistrationInfoImpl::get_RawSource(v6, &pbstr);
    if ( RawSource >= 0 )
    {
      if ( pbstr )
      {
        if ( SysStringLen(pbstr) )
        {
          v19 = TaskXmlWriter::Element((unsigned int *)v4, 6, (__int64)pbstr);
          if ( v19 < 0 )
            goto LABEL_34;
        }
      }
    }
    v31 = 0;
    if ( (*(int (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)this + 9) + 104LL))(*((_QWORD *)this + 9), &v31) >= 0
      && v31
      && SysStringLen(v31) )
    {
      v20 = *((_DWORD *)v4 + 38);
      if ( v20 )
      {
        *((_DWORD *)v4 + 38) = v20 + 1;
      }
      else
      {
        v21 = *(unsigned int *)v4;
        if ( (_DWORD)v21 == 65542 )
        {
LABEL_43:
          v22 = (&Schema::schemaEntries)[(unsigned __int16)v21] + 112;
        }
        else
        {
          switch ( (int)v21 )
          {
            case 65536:
            case 65537:
              v29 = 0;
              v30 = (unsigned __int16)v21;
              v21 = (unsigned __int64)(&Schema::schemaEntriesCount)[(unsigned __int16)v21];
              break;
            case 65538:
            case 65539:
            case 65540:
            case 65541:
              goto LABEL_43;
            default:
              goto LABEL_93;
          }
          while ( v29 < v21 )
          {
            v22 = (const struct SchemaEntry * near *)(*((_QWORD *)&_ImageBase + v30 + 48103) + (v29 << 7));
            if ( *(_DWORD *)v22 == 7 )
              goto LABEL_45;
            ++v29;
          }
LABEL_93:
          v22 = (const struct SchemaEntry * near *)&qword_180072DF0;
        }
        if ( *(_DWORD *)v22 )
        {
LABEL_45:
          v23 = *((_QWORD *)v4 + 2);
          if ( !v23 )
            _com_raise_error(-2147467261, (struct IErrorInfo *)v21);
          v24 = v31;
          v25 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const struct SchemaEntry *, wchar_t *const))(*(_QWORD *)v23 + 216LL))(
                  v23,
                  &Src,
                  v22[1],
                  Schema::namespaceUri);
          v19 = v25;
          if ( v25 < 0 )
            goto LABEL_33;
          if ( !v25 )
          {
            if ( v24 )
            {
              v26 = _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->((char *)v4 + 16);
              v19 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v26 + 224LL))(v26, v24);
              if ( v19 < 0 )
                goto LABEL_33;
            }
          }
        }
        else
        {
          *((_DWORD *)v4 + 38) = 1;
        }
      }
      v19 = TaskXmlWriter::EndElement((__int64)v4);
      if ( v19 < 0 )
      {
LABEL_33:
        SysFreeString(v31);
LABEL_34:
        SysFreeString(pbstr);
        return (unsigned int)v19;
      }
    }
    v38 = 0;
    if ( a3 )
      RawAuthor = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)this + 9) + 72LL))(
                    *((_QWORD *)this + 9),
                    &v38);
    else
      RawAuthor = RegistrationInfoImpl::get_RawAuthor(v6, &v38);
    if ( RawAuthor >= 0 )
    {
      if ( v38 )
      {
        if ( SysStringLen(v38) )
        {
          v19 = TaskXmlWriter::Element((unsigned int *)v4, 8, (__int64)v38);
          if ( v19 < 0 )
          {
LABEL_59:
            SysFreeString(v38);
            goto LABEL_33;
          }
        }
      }
    }
    v33 = 0;
    if ( (*(int (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)this + 9) + 88LL))(*((_QWORD *)this + 9), &v33) >= 0 )
    {
      if ( v33 )
      {
        if ( SysStringLen(v33) )
        {
          v19 = TaskXmlWriter::Element((unsigned int *)v4, 9, (__int64)v33);
          if ( v19 < 0 )
          {
LABEL_58:
            SysFreeString(v33);
            goto LABEL_59;
          }
        }
      }
    }
    v32 = 0;
    if ( a3 )
      RawDescription = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)this + 9) + 56LL))(
                         *((_QWORD *)this + 9),
                         &v32);
    else
      RawDescription = RegistrationInfoImpl::get_RawDescription(v6, &v32);
    if ( RawDescription >= 0 )
    {
      if ( v32 )
      {
        if ( SysStringLen(v32) )
        {
          v19 = TaskXmlWriter::Element((unsigned int *)v4, 10, (__int64)v32);
          if ( v19 < 0 )
          {
LABEL_57:
            SysFreeString(v32);
            goto LABEL_58;
          }
        }
      }
    }
    v34 = 0;
    if ( a3 )
      RawDocumentation = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)this + 9) + 120LL))(
                           *((_QWORD *)this + 9),
                           &v34);
    else
      RawDocumentation = RegistrationInfoImpl::get_RawDocumentation(v6, &v34);
    if ( RawDocumentation >= 0 )
    {
      if ( v34 )
      {
        if ( SysStringLen(v34) )
        {
          v19 = TaskXmlWriter::Element((unsigned int *)v4, 11, (__int64)v34);
          if ( v19 < 0 )
          {
LABEL_56:
            SysFreeString(v34);
            goto LABEL_57;
          }
        }
      }
    }
    bstrString = 0;
    if ( (*(int (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)this + 9) + 152LL))(*((_QWORD *)this + 9), &bstrString) >= 0 )
    {
      if ( bstrString )
      {
        if ( SysStringLen(bstrString) )
        {
          v19 = TaskXmlWriter::Element((unsigned int *)v4, 4, (__int64)bstrString);
          if ( v19 < 0 )
          {
LABEL_55:
            SysFreeString(bstrString);
            goto LABEL_56;
          }
        }
      }
    }
    VariantInit(&pvarg);
    if ( (*(int (__fastcall **)(_QWORD, VARIANTARG *))(**((_QWORD **)this + 9) + 168LL))(*((_QWORD *)this + 9), &pvarg) >= 0
      && pvarg.vt == 8 )
    {
      if ( pvarg.llVal )
      {
        v19 = TaskXmlWriter::Element((unsigned int *)v4, 5, pvarg.llVal);
        if ( v19 < 0 )
        {
          VariantClear(&pvarg);
          goto LABEL_55;
        }
      }
    }
    v16 = *((_DWORD *)v4 + 38);
    if ( v16 )
    {
      *((_DWORD *)v4 + 38) = v16 - 1;
    }
    else
    {
      v17 = _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->((char *)v4 + 16);
      v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 120LL))(v17);
      if ( v18 < 0 )
      {
        VariantClear(&pvarg);
        SysFreeString(bstrString);
        SysFreeString(v34);
        SysFreeString(v32);
        SysFreeString(v33);
        SysFreeString(v38);
        SysFreeString(v31);
        SysFreeString(pbstr);
        return (unsigned int)v18;
      }
    }
    VariantClear(&pvarg);
    SysFreeString(bstrString);
    SysFreeString(v34);
    SysFreeString(v32);
    SysFreeString(v33);
    SysFreeString(v38);
    SysFreeString(v31);
    SysFreeString(pbstr);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800025b0  mov     [rsp-38h+arg_8], rbx
0x1800025b5  push    rbp
0x1800025b6  push    rsi
0x1800025b7  push    rdi
0x1800025b8  push    r12
0x1800025ba  push    r13
0x1800025bc  push    r14
0x1800025be  push    r15
0x1800025c0  mov     rbp, rsp
0x1800025c3  sub     rsp, 70h
0x1800025c7  mov     r12d, r8d
0x1800025ca  mov     rbx, rdx
0x1800025cd  mov     rsi, rcx
0x1800025d0  mov     r13, [rcx+48h]
0x1800025d4  test    r13, r13
0x1800025d7  jz      loc_18000286F
0x1800025dd  mov     eax, [rdx+98h]
0x1800025e3  lea     r15, __ImageBase
0x1800025ea  xor     r14d, r14d
0x1800025ed  test    eax, eax
0x1800025ef  jnz     loc_180002D3E
0x1800025f5  mov     r8d, [rdx]
0x1800025f8  cmp     r8d, 10006h
0x1800025ff  jnz     loc_180002B93
0x180002605  movzx   eax, r8w; jumptable 0000000180002BB0 cases 65538-65541
0x180002609  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r15+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180002611  add     r8, 180h
0x180002618  mov     eax, [r8]
0x18000261b  test    eax, eax
0x18000261d  jz      loc_180002CED
0x180002623  mov     rcx, [rbx+10h]
0x180002627  test    rcx, rcx
0x18000262a  jz      loc_180002D4B
0x180002630  mov     rax, [rcx]
0x180002633  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x18000263a  mov     r8, [r8+8]
0x18000263e  lea     rdx, Src
0x180002645  mov     rax, [rax+0D8h]
0x18000264c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002651  test    eax, eax
0x180002653  js      loc_1800028AB
0x180002659  mov     [rbp+pbstr], r14
0x18000265d  lea     rdx, [rbp+pbstr]; unsigned __int16 **
0x180002661  test    r12d, r12d
0x180002664  jz      loc_180002B86
0x18000266a  mov     rcx, [rsi+48h]
0x18000266e  mov     rax, [rcx]
0x180002671  mov     rax, [rax+0B8h]
0x180002678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000267d  test    eax, eax
0x18000267f  jns     loc_1800028C4
0x180002685  mov     [rbp+var_40], r14
0x180002689  mov     rcx, [rsi+48h]
0x18000268d  mov     rax, [rcx]
0x180002690  lea     rdx, [rbp+var_40]
0x180002694  mov     rax, [rax+68h]
0x180002698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000269d  test    eax, eax
0x18000269f  js      short loc_1800026AE
0x1800026a1  mov     rcx, [rbp+var_40]; pbstr
0x1800026a5  test    rcx, rcx
0x1800026a8  jnz     loc_180002901
0x1800026ae  mov     [rbp+arg_18], r14
0x1800026b2  lea     rdx, [rbp+arg_18]; unsigned __int16 **
0x1800026b6  test    r12d, r12d
0x1800026b9  jz      loc_180002CFC
0x1800026bf  mov     rcx, [rsi+48h]
0x1800026c3  mov     rax, [rcx]
0x1800026c6  mov     rax, [rax+48h]
0x1800026ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026cf  test    eax, eax
0x1800026d1  js      short loc_1800026E0
0x1800026d3  mov     rcx, [rbp+arg_18]; pbstr
0x1800026d7  test    rcx, rcx
0x1800026da  jnz     loc_180002AA8
0x1800026e0  mov     [rbp+var_30], r14
0x1800026e4  mov     rcx, [rsi+48h]
0x1800026e8  mov     rax, [rcx]
0x1800026eb  lea     rdx, [rbp+var_30]
0x1800026ef  mov     rax, [rax+58h]
0x1800026f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026f8  test    eax, eax
0x1800026fa  jns     loc_180002B19
0x180002700  mov     [rbp+var_38], r14
0x180002704  lea     rdx, [rbp+var_38]; unsigned __int16 **
0x180002708  test    r12d, r12d
0x18000270b  jz      loc_1800029C9
0x180002711  mov     rcx, [rsi+48h]
0x180002715  mov     rax, [rcx]
0x180002718  mov     rax, [rax+38h]
0x18000271c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002721  test    eax, eax
0x180002723  jns     loc_180002AD8
0x180002729  mov     [rbp+var_28], r14
0x18000272d  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x180002731  test    r12d, r12d
0x180002734  jz      loc_180002D09
0x18000273a  mov     rcx, [rsi+48h]
0x18000273e  mov     rax, [rcx]
0x180002741  mov     rax, [rax+78h]
0x180002745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000274a  test    eax, eax
0x18000274c  jns     loc_180002A6B
0x180002752  mov     [rbp+bstrString], r14
0x180002756  mov     rcx, [rsi+48h]
0x18000275a  mov     rax, [rcx]
0x18000275d  lea     rdx, [rbp+bstrString]
0x180002761  mov     rax, [rax+98h]
0x180002768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000276d  test    eax, eax
0x18000276f  jns     loc_1800029D6
0x180002775  lea     rcx, [rbp+pvarg]; pvarg
0x180002779  call    cs:__imp_VariantInit
0x180002780  nop     dword ptr [rax+rax+00h]
0x180002785  nop
0x180002786  mov     rcx, [rsi+48h]
0x18000278a  mov     rax, [rcx]
0x18000278d  lea     rdx, [rbp+pvarg]
0x180002791  mov     rax, [rax+0A8h]
0x180002798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000279d  test    eax, eax
0x18000279f  js      short loc_1800027B5
0x1800027a1  cmp     word ptr [rbp+pvarg], 8
0x1800027a6  jnz     short loc_1800027B5
0x1800027a8  mov     r8, qword ptr [rbp+pvarg+8]
0x1800027ac  test    r8, r8
0x1800027af  jnz     loc_180002B5A
0x1800027b5  mov     eax, [rbx+98h]
0x1800027bb  test    eax, eax
0x1800027bd  jnz     loc_180002D31
0x1800027c3  lea     rcx, [rbx+10h]
0x1800027c7  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlWriter@@$1?_GUID_7279fc88_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlWriter@@XZ; _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x1800027cc  mov     rdx, rax
0x1800027cf  mov     rcx, [rax]
0x1800027d2  mov     rax, [rcx+78h]
0x1800027d6  mov     rcx, rdx
0x1800027d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027de  mov     ebx, eax
0x1800027e0  test    eax, eax
0x1800027e2  js      loc_180002C53
0x1800027e8  lea     rcx, [rbp+pvarg]; pvarg
0x1800027ec  call    cs:__imp_VariantClear
0x1800027f3  nop     dword ptr [rax+rax+00h]
0x1800027f8  nop
0x1800027f9  mov     rcx, [rbp+bstrString]; bstrString
0x1800027fd  call    cs:__imp_SysFreeString
0x180002804  nop     dword ptr [rax+rax+00h]
0x180002809  nop
0x18000280a  mov     rcx, [rbp+var_28]; bstrString
0x18000280e  call    cs:__imp_SysFreeString
0x180002815  nop     dword ptr [rax+rax+00h]
0x18000281a  nop
0x18000281b  mov     rcx, [rbp+var_38]; bstrString
0x18000281f  call    cs:__imp_SysFreeString
0x180002826  nop     dword ptr [rax+rax+00h]
0x18000282b  nop
0x18000282c  mov     rcx, [rbp+var_30]; bstrString
0x180002830  call    cs:__imp_SysFreeString
0x180002837  nop     dword ptr [rax+rax+00h]
0x18000283c  nop
0x18000283d  mov     rcx, [rbp+arg_18]; bstrString
0x180002841  call    cs:__imp_SysFreeString
0x180002848  nop     dword ptr [rax+rax+00h]
0x18000284d  nop
0x18000284e  mov     rcx, [rbp+var_40]; bstrString
0x180002852  call    cs:__imp_SysFreeString
0x180002859  nop     dword ptr [rax+rax+00h]
0x18000285e  nop
0x18000285f  mov     rcx, [rbp+pbstr]; bstrString
0x180002863  call    cs:__imp_SysFreeString
0x18000286a  nop     dword ptr [rax+rax+00h]
0x18000286f  xor     eax, eax
0x180002871  jmp     short loc_1800028AB
0x180002873  xor     r14d, r14d
0x180002876  mov     rcx, rbx
0x180002879  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x18000287e  mov     edi, eax
0x180002880  test    eax, eax
0x180002882  jns     loc_1800026AE
0x180002888  mov     rcx, [rbp+var_40]; bstrString
0x18000288c  call    cs:__imp_SysFreeString
0x180002893  nop     dword ptr [rax+rax+00h]
0x180002898  nop
0x180002899  mov     rcx, [rbp+pbstr]; bstrString
0x18000289d  call    cs:__imp_SysFreeString
0x1800028a4  nop     dword ptr [rax+rax+00h]
0x1800028a9  mov     eax, edi
0x1800028ab  mov     rbx, [rsp+70h+arg_8]
0x1800028b3  add     rsp, 70h
0x1800028b7  pop     r15
0x1800028b9  pop     r14
0x1800028bb  pop     r13
0x1800028bd  pop     r12
0x1800028bf  pop     rdi
0x1800028c0  pop     rsi
0x1800028c1  pop     rbp
0x1800028c2  retn
0x1800028c4  mov     rcx, [rbp+pbstr]; pbstr
0x1800028c8  test    rcx, rcx
0x1800028cb  jz      loc_180002685
0x1800028d1  call    cs:__imp_SysStringLen
0x1800028d8  nop     dword ptr [rax+rax+00h]
0x1800028dd  test    eax, eax
0x1800028df  jz      loc_180002685
0x1800028e5  mov     r8, [rbp+pbstr]
0x1800028e9  mov     edx, 6
0x1800028ee  mov     rcx, rbx
0x1800028f1  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x1800028f6  mov     edi, eax
0x1800028f8  test    eax, eax
0x1800028fa  js      short loc_180002899
0x1800028fc  jmp     loc_180002685
0x180002901  call    cs:__imp_SysStringLen
0x180002908  nop     dword ptr [rax+rax+00h]
0x18000290d  test    eax, eax
0x18000290f  jz      loc_1800026AE
0x180002915  mov     eax, [rbx+98h]
0x18000291b  test    eax, eax
0x18000291d  jnz     loc_180002D56
0x180002923  mov     edx, [rbx]; struct IErrorInfo *
0x180002925  cmp     edx, 10006h
0x18000292b  jnz     loc_180002BF3
0x180002931  movzx   eax, dx; jumptable 0000000180002C0F cases 65538-65541
0x180002934  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r15+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18000293c  add     r8, 380h
0x180002943  mov     eax, [r8]
0x180002946  test    eax, eax
0x180002948  jz      loc_180002D22
0x18000294e  mov     rcx, [rbx+10h]
0x180002952  test    rcx, rcx
0x180002955  jz      loc_180002D63
0x18000295b  mov     r15, [rbp+var_40]
0x18000295f  mov     rax, [rcx]
0x180002962  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180002969  mov     r8, [r8+8]
0x18000296d  lea     rdx, Src
0x180002974  mov     rax, [rax+0D8h]
0x18000297b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002980  mov     edi, eax
0x180002982  test    eax, eax
0x180002984  js      loc_180002888
0x18000298a  jnz     loc_180002873
0x180002990  test    r15, r15
0x180002993  jz      loc_180002873
0x180002999  lea     rcx, [rbx+10h]
0x18000299d  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlWriter@@$1?_GUID_7279fc88_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlWriter@@XZ; _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x1800029a2  mov     r8, rax
0x1800029a5  mov     rcx, [rax]
0x1800029a8  mov     rax, [rcx+0E0h]
0x1800029af  mov     rdx, r15
0x1800029b2  mov     rcx, r8
0x1800029b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029ba  mov     edi, eax
0x1800029bc  test    eax, eax
0x1800029be  js      loc_180002888
0x1800029c4  jmp     loc_180002873
0x1800029c9  mov     rcx, r13; this
0x1800029cc  call    ?get_RawDescription@RegistrationInfoImpl@@QEAAJPEAPEAG@Z; RegistrationInfoImpl::get_RawDescription(ushort * *)
0x1800029d1  jmp     loc_180002721
0x1800029d6  mov     rcx, [rbp+bstrString]; pbstr
0x1800029da  test    rcx, rcx
0x1800029dd  jz      loc_180002775
0x1800029e3  call    cs:__imp_SysStringLen
0x1800029ea  nop     dword ptr [rax+rax+00h]
0x1800029ef  test    eax, eax
0x1800029f1  jz      loc_180002775
0x1800029f7  mov     r8, [rbp+bstrString]
0x1800029fb  mov     edx, 4
0x180002a00  mov     rcx, rbx
0x180002a03  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180002a08  mov     edi, eax
0x180002a0a  test    eax, eax
0x180002a0c  jns     loc_180002775
0x180002a12  mov     rcx, [rbp+bstrString]; bstrString
0x180002a16  call    cs:__imp_SysFreeString
0x180002a1d  nop     dword ptr [rax+rax+00h]
0x180002a22  nop
0x180002a23  mov     rcx, [rbp+var_28]; bstrString
0x180002a27  call    cs:__imp_SysFreeString
0x180002a2e  nop     dword ptr [rax+rax+00h]
0x180002a33  nop
0x180002a34  mov     rcx, [rbp+var_38]; bstrString
0x180002a38  call    cs:__imp_SysFreeString
0x180002a3f  nop     dword ptr [rax+rax+00h]
0x180002a44  nop
0x180002a45  mov     rcx, [rbp+var_30]; bstrString
0x180002a49  call    cs:__imp_SysFreeString
0x180002a50  nop     dword ptr [rax+rax+00h]
0x180002a55  nop
0x180002a56  mov     rcx, [rbp+arg_18]; bstrString
0x180002a5a  call    cs:__imp_SysFreeString
0x180002a61  nop     dword ptr [rax+rax+00h]
0x180002a66  jmp     loc_180002888
0x180002a6b  mov     rcx, [rbp+var_28]; pbstr
0x180002a6f  test    rcx, rcx
0x180002a72  jz      loc_180002752
0x180002a78  call    cs:__imp_SysStringLen
0x180002a7f  nop     dword ptr [rax+rax+00h]
0x180002a84  test    eax, eax
0x180002a86  jz      loc_180002752
  ... truncated ...
```
