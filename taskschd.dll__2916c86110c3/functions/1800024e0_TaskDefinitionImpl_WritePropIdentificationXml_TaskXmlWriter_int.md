# TaskDefinitionImpl::WritePropIdentificationXml(TaskXmlWriter &,int)

- ea: `0x1800024e0`
- end: `0x180002c08`
- name: `?WritePropIdentificationXml@TaskDefinitionImpl@@AEAAJAEAVTaskXmlWriter@@H@Z`
- size: `1832`
- prototype: `__int64 __fastcall(TaskDefinitionImpl *__hidden this, struct TaskXmlWriter *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004fd0`

## callees

- `0x180001e60`
- `0x1800024e0`
- `0x180003840`
- `0x180003d1c`
- `0x1800108e0`
- `0x180010a98`
- `0x180011018`
- `0x1800157e4`
- `0x180038404`
- `0x180054010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180002721`
- `OLEAUT32!__imp_SysFreeString` at `0x18000272c`
- `OLEAUT32!__imp_SysFreeString` at `0x180002737`
- `OLEAUT32!__imp_SysFreeString` at `0x180002742`
- `OLEAUT32!__imp_SysFreeString` at `0x18000274d`
- `OLEAUT32!__imp_SysFreeString` at `0x180002758`
- `OLEAUT32!__imp_SysFreeString` at `0x180002763`
- `OLEAUT32!__imp_SysFreeString` at `0x180002786`
- `OLEAUT32!__imp_SysFreeString` at `0x180002791`
- `OLEAUT32!__imp_SysFreeString` at `0x1800028f1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800028fc`
- `OLEAUT32!__imp_SysFreeString` at `0x180002907`
- `OLEAUT32!__imp_SysFreeString` at `0x180002912`
- `OLEAUT32!__imp_SysFreeString` at `0x18000291d`
- `OLEAUT32!__imp_SysFreeString` at `0x180002af9`
- `OLEAUT32!__imp_SysFreeString` at `0x180002b04`
- `OLEAUT32!__imp_SysFreeString` at `0x180002b0f`
- `OLEAUT32!__imp_SysFreeString` at `0x180002b1a`
- `OLEAUT32!__imp_SysFreeString` at `0x180002b25`
- `OLEAUT32!__imp_SysFreeString` at `0x180002b30`
- `OLEAUT32!__imp_SysFreeString` at `0x180002b3b`
- `OLEAUT32!__imp_SysFreeString` at `0x180002721`
- `OLEAUT32!__imp_SysFreeString` at `0x18000272c`
- `OLEAUT32!__imp_SysFreeString` at `0x180002737`
- `OLEAUT32!__imp_SysFreeString` at `0x180002742`
- `OLEAUT32!__imp_SysFreeString` at `0x18000274d`
- `OLEAUT32!__imp_SysFreeString` at `0x180002758`
- `OLEAUT32!__imp_SysFreeString` at `0x180002763`
- `OLEAUT32!__imp_SysFreeString` at `0x180002786`
- `OLEAUT32!__imp_SysFreeString` at `0x180002791`
- `OLEAUT32!__imp_SysFreeString` at `0x1800028f1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800028fc`
- `OLEAUT32!__imp_SysFreeString` at `0x180002907`
- `OLEAUT32!__imp_SysFreeString` at `0x180002912`
- `OLEAUT32!__imp_SysFreeString` at `0x18000291d`
- `OLEAUT32!__imp_SysFreeString` at `0x180002af9`
- `OLEAUT32!__imp_SysFreeString` at `0x180002b04`
- `OLEAUT32!__imp_SysFreeString` at `0x180002b0f`
- `OLEAUT32!__imp_SysFreeString` at `0x180002b1a`
- `OLEAUT32!__imp_SysFreeString` at `0x180002b25`
- `OLEAUT32!__imp_SysFreeString` at `0x180002b30`
- `OLEAUT32!__imp_SysFreeString` at `0x180002b3b`
- `OLEAUT32!__imp_SysStringLen` at `0x1800027be`
- `OLEAUT32!__imp_SysStringLen` at `0x1800027e8`
- `OLEAUT32!__imp_SysStringLen` at `0x1800028c4`
- `OLEAUT32!__imp_SysStringLen` at `0x180002935`
- `OLEAUT32!__imp_SysStringLen` at `0x18000295f`
- `OLEAUT32!__imp_SysStringLen` at `0x180002996`
- `OLEAUT32!__imp_SysStringLen` at `0x1800029d1`
- `OLEAUT32!__imp_SysStringLen` at `0x1800027be`
- `OLEAUT32!__imp_SysStringLen` at `0x1800027e8`
- `OLEAUT32!__imp_SysStringLen` at `0x1800028c4`
- `OLEAUT32!__imp_SysStringLen` at `0x180002935`
- `OLEAUT32!__imp_SysStringLen` at `0x18000295f`
- `OLEAUT32!__imp_SysStringLen` at `0x180002996`
- `OLEAUT32!__imp_SysStringLen` at `0x1800029d1`
- `OLEAUT32!__imp_VariantInit` at `0x1800026a9`
- `OLEAUT32!__imp_VariantInit` at `0x1800026a9`
- `OLEAUT32!__imp_VariantClear` at `0x180002716`
- `OLEAUT32!__imp_VariantClear` at `0x180002a1a`
- `OLEAUT32!__imp_VariantClear` at `0x180002aee`
- `OLEAUT32!__imp_VariantClear` at `0x180002716`
- `OLEAUT32!__imp_VariantClear` at `0x180002a1a`
- `OLEAUT32!__imp_VariantClear` at `0x180002aee`

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
        v28 = 8LL * (unsigned __int16)v8 + 368464;
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
    v9 = (const struct SchemaEntry * near *)&qword_18006EE10;
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
            v22 = (const struct SchemaEntry * near *)(*((_QWORD *)&_ImageBase + v30 + 46058) + (v29 << 7));
            if ( *(_DWORD *)v22 == 7 )
              goto LABEL_45;
            ++v29;
          }
LABEL_93:
          v22 = (const struct SchemaEntry * near *)&qword_18006EE10;
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
0x1800024e0  mov     [rsp-38h+arg_8], rbx
0x1800024e5  push    rbp
0x1800024e6  push    rsi
0x1800024e7  push    rdi
0x1800024e8  push    r12
0x1800024ea  push    r13
0x1800024ec  push    r14
0x1800024ee  push    r15
0x1800024f0  mov     rbp, rsp
0x1800024f3  sub     rsp, 70h
0x1800024f7  mov     r12d, r8d
0x1800024fa  mov     rbx, rdx
0x1800024fd  mov     rsi, rcx
0x180002500  mov     r13, [rcx+48h]
0x180002504  test    r13, r13
0x180002507  jz      loc_180002769
0x18000250d  mov     eax, [rdx+98h]
0x180002513  lea     r15, __ImageBase
0x18000251a  xor     r14d, r14d
0x18000251d  test    eax, eax
0x18000251f  jnz     loc_180002BA5
0x180002525  mov     r8d, [rdx]
0x180002528  cmp     r8d, 10006h
0x18000252f  jnz     loc_180002A32
0x180002535  movzx   eax, r8w; jumptable 0000000180002A4F cases 65538-65541
0x180002539  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r15+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180002541  add     r8, 180h
0x180002548  mov     eax, [r8]
0x18000254b  test    eax, eax
0x18000254d  jz      loc_180002B54
0x180002553  mov     rcx, [rbx+10h]
0x180002557  test    rcx, rcx
0x18000255a  jz      loc_180002BB2
0x180002560  mov     rax, [rcx]
0x180002563  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x18000256a  mov     r8, [r8+8]
0x18000256e  lea     rdx, Src
0x180002575  mov     rax, [rax+0D8h]
0x18000257c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002581  test    eax, eax
0x180002583  js      loc_180002799
0x180002589  mov     [rbp+pbstr], r14
0x18000258d  lea     rdx, [rbp+pbstr]; unsigned __int16 **
0x180002591  test    r12d, r12d
0x180002594  jz      loc_180002A25
0x18000259a  mov     rcx, [rsi+48h]
0x18000259e  mov     rax, [rcx]
0x1800025a1  mov     rax, [rax+0B8h]
0x1800025a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025ad  test    eax, eax
0x1800025af  jns     loc_1800027B1
0x1800025b5  mov     [rbp+var_40], r14
0x1800025b9  mov     rcx, [rsi+48h]
0x1800025bd  mov     rax, [rcx]
0x1800025c0  lea     rdx, [rbp+var_40]
0x1800025c4  mov     rax, [rax+68h]
0x1800025c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025cd  test    eax, eax
0x1800025cf  js      short loc_1800025DE
0x1800025d1  mov     rcx, [rbp+var_40]; pbstr
0x1800025d5  test    rcx, rcx
0x1800025d8  jnz     loc_1800027E8
0x1800025de  mov     [rbp+arg_18], r14
0x1800025e2  lea     rdx, [rbp+arg_18]; unsigned __int16 **
0x1800025e6  test    r12d, r12d
0x1800025e9  jz      loc_180002B63
0x1800025ef  mov     rcx, [rsi+48h]
0x1800025f3  mov     rax, [rcx]
0x1800025f6  mov     rax, [rax+48h]
0x1800025fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025ff  test    eax, eax
0x180002601  js      short loc_180002610
0x180002603  mov     rcx, [rbp+arg_18]; pbstr
0x180002607  test    rcx, rcx
0x18000260a  jnz     loc_18000295F
0x180002610  mov     [rbp+var_30], r14
0x180002614  mov     rcx, [rsi+48h]
0x180002618  mov     rax, [rcx]
0x18000261b  lea     rdx, [rbp+var_30]
0x18000261f  mov     rax, [rax+58h]
0x180002623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002628  test    eax, eax
0x18000262a  jns     loc_1800029C4
0x180002630  mov     [rbp+var_38], r14
0x180002634  lea     rdx, [rbp+var_38]; unsigned __int16 **
0x180002638  test    r12d, r12d
0x18000263b  jz      loc_1800028AA
0x180002641  mov     rcx, [rsi+48h]
0x180002645  mov     rax, [rcx]
0x180002648  mov     rax, [rax+38h]
0x18000264c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002651  test    eax, eax
0x180002653  jns     loc_180002989
0x180002659  mov     [rbp+var_28], r14
0x18000265d  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x180002661  test    r12d, r12d
0x180002664  jz      loc_180002B70
0x18000266a  mov     rcx, [rsi+48h]
0x18000266e  mov     rax, [rcx]
0x180002671  mov     rax, [rax+78h]
0x180002675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000267a  test    eax, eax
0x18000267c  jns     loc_180002928
0x180002682  mov     [rbp+bstrString], r14
0x180002686  mov     rcx, [rsi+48h]
0x18000268a  mov     rax, [rcx]
0x18000268d  lea     rdx, [rbp+bstrString]
0x180002691  mov     rax, [rax+98h]
0x180002698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000269d  test    eax, eax
0x18000269f  jns     loc_1800028B7
0x1800026a5  lea     rcx, [rbp+pvarg]; pvarg
0x1800026a9  call    cs:__imp_VariantInit
0x1800026af  nop
0x1800026b0  mov     rcx, [rsi+48h]
0x1800026b4  mov     rax, [rcx]
0x1800026b7  lea     rdx, [rbp+pvarg]
0x1800026bb  mov     rax, [rax+0A8h]
0x1800026c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026c7  test    eax, eax
0x1800026c9  js      short loc_1800026DF
0x1800026cb  cmp     word ptr [rbp+pvarg], 8
0x1800026d0  jnz     short loc_1800026DF
0x1800026d2  mov     r8, qword ptr [rbp+pvarg+8]
0x1800026d6  test    r8, r8
0x1800026d9  jnz     loc_1800029FF
0x1800026df  mov     eax, [rbx+98h]
0x1800026e5  test    eax, eax
0x1800026e7  jnz     loc_180002B98
0x1800026ed  lea     rcx, [rbx+10h]
0x1800026f1  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlWriter@@$1?_GUID_7279fc88_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlWriter@@XZ; _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x1800026f6  mov     rdx, rax
0x1800026f9  mov     rcx, [rax]
0x1800026fc  mov     rax, [rcx+78h]
0x180002700  mov     rcx, rdx
0x180002703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002708  mov     ebx, eax
0x18000270a  test    eax, eax
0x18000270c  js      loc_180002AEA
0x180002712  lea     rcx, [rbp+pvarg]; pvarg
0x180002716  call    cs:__imp_VariantClear
0x18000271c  nop
0x18000271d  mov     rcx, [rbp+bstrString]; bstrString
0x180002721  call    cs:__imp_SysFreeString
0x180002727  nop
0x180002728  mov     rcx, [rbp+var_28]; bstrString
0x18000272c  call    cs:__imp_SysFreeString
0x180002732  nop
0x180002733  mov     rcx, [rbp+var_38]; bstrString
0x180002737  call    cs:__imp_SysFreeString
0x18000273d  nop
0x18000273e  mov     rcx, [rbp+var_30]; bstrString
0x180002742  call    cs:__imp_SysFreeString
0x180002748  nop
0x180002749  mov     rcx, [rbp+arg_18]; bstrString
0x18000274d  call    cs:__imp_SysFreeString
0x180002753  nop
0x180002754  mov     rcx, [rbp+var_40]; bstrString
0x180002758  call    cs:__imp_SysFreeString
0x18000275e  nop
0x18000275f  mov     rcx, [rbp+pbstr]; bstrString
0x180002763  call    cs:__imp_SysFreeString
0x180002769  xor     eax, eax
0x18000276b  jmp     short loc_180002799
0x18000276d  xor     r14d, r14d
0x180002770  mov     rcx, rbx
0x180002773  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x180002778  mov     edi, eax
0x18000277a  test    eax, eax
0x18000277c  jns     loc_1800025DE
0x180002782  mov     rcx, [rbp+var_40]; bstrString
0x180002786  call    cs:__imp_SysFreeString
0x18000278c  nop
0x18000278d  mov     rcx, [rbp+pbstr]; bstrString
0x180002791  call    cs:__imp_SysFreeString
0x180002797  mov     eax, edi
0x180002799  mov     rbx, [rsp+70h+arg_8]
0x1800027a1  add     rsp, 70h
0x1800027a5  pop     r15
0x1800027a7  pop     r14
0x1800027a9  pop     r13
0x1800027ab  pop     r12
0x1800027ad  pop     rdi
0x1800027ae  pop     rsi
0x1800027af  pop     rbp
0x1800027b0  retn
0x1800027b1  mov     rcx, [rbp+pbstr]; pbstr
0x1800027b5  test    rcx, rcx
0x1800027b8  jz      loc_1800025B5
0x1800027be  call    cs:__imp_SysStringLen
0x1800027c4  test    eax, eax
0x1800027c6  jz      loc_1800025B5
0x1800027cc  mov     r8, [rbp+pbstr]
0x1800027d0  mov     edx, 6
0x1800027d5  mov     rcx, rbx
0x1800027d8  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x1800027dd  mov     edi, eax
0x1800027df  test    eax, eax
0x1800027e1  js      short loc_18000278D
0x1800027e3  jmp     loc_1800025B5
0x1800027e8  call    cs:__imp_SysStringLen
0x1800027ee  test    eax, eax
0x1800027f0  jz      loc_1800025DE
0x1800027f6  mov     eax, [rbx+98h]
0x1800027fc  test    eax, eax
0x1800027fe  jnz     loc_180002BBD
0x180002804  mov     edx, [rbx]; struct IErrorInfo *
0x180002806  cmp     edx, 10006h
0x18000280c  jnz     loc_180002A93
0x180002812  movzx   eax, dx; jumptable 0000000180002AAF cases 65538-65541
0x180002815  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r15+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18000281d  add     r8, 380h
0x180002824  mov     eax, [r8]
0x180002827  test    eax, eax
0x180002829  jz      loc_180002B89
0x18000282f  mov     rcx, [rbx+10h]
0x180002833  test    rcx, rcx
0x180002836  jz      loc_180002BCA
0x18000283c  mov     r15, [rbp+var_40]
0x180002840  mov     rax, [rcx]
0x180002843  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x18000284a  mov     r8, [r8+8]
0x18000284e  lea     rdx, Src
0x180002855  mov     rax, [rax+0D8h]
0x18000285c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002861  mov     edi, eax
0x180002863  test    eax, eax
0x180002865  js      loc_180002782
0x18000286b  jnz     loc_18000276D
0x180002871  test    r15, r15
0x180002874  jz      loc_18000276D
0x18000287a  lea     rcx, [rbx+10h]
0x18000287e  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlWriter@@$1?_GUID_7279fc88_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlWriter@@XZ; _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x180002883  mov     r8, rax
0x180002886  mov     rcx, [rax]
0x180002889  mov     rax, [rcx+0E0h]
0x180002890  mov     rdx, r15
0x180002893  mov     rcx, r8
0x180002896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000289b  mov     edi, eax
0x18000289d  test    eax, eax
0x18000289f  js      loc_180002782
0x1800028a5  jmp     loc_18000276D
0x1800028aa  mov     rcx, r13; this
0x1800028ad  call    ?get_RawDescription@RegistrationInfoImpl@@QEAAJPEAPEAG@Z; RegistrationInfoImpl::get_RawDescription(ushort * *)
0x1800028b2  jmp     loc_180002651
0x1800028b7  mov     rcx, [rbp+bstrString]; pbstr
0x1800028bb  test    rcx, rcx
0x1800028be  jz      loc_1800026A5
0x1800028c4  call    cs:__imp_SysStringLen
0x1800028ca  test    eax, eax
0x1800028cc  jz      loc_1800026A5
0x1800028d2  mov     r8, [rbp+bstrString]
0x1800028d6  mov     edx, 4
0x1800028db  mov     rcx, rbx
0x1800028de  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x1800028e3  mov     edi, eax
0x1800028e5  test    eax, eax
0x1800028e7  jns     loc_1800026A5
0x1800028ed  mov     rcx, [rbp+bstrString]; bstrString
0x1800028f1  call    cs:__imp_SysFreeString
0x1800028f7  nop
0x1800028f8  mov     rcx, [rbp+var_28]; bstrString
0x1800028fc  call    cs:__imp_SysFreeString
0x180002902  nop
0x180002903  mov     rcx, [rbp+var_38]; bstrString
0x180002907  call    cs:__imp_SysFreeString
0x18000290d  nop
0x18000290e  mov     rcx, [rbp+var_30]; bstrString
0x180002912  call    cs:__imp_SysFreeString
0x180002918  nop
0x180002919  mov     rcx, [rbp+arg_18]; bstrString
0x18000291d  call    cs:__imp_SysFreeString
0x180002923  jmp     loc_180002782
0x180002928  mov     rcx, [rbp+var_28]; pbstr
0x18000292c  test    rcx, rcx
0x18000292f  jz      loc_180002682
0x180002935  call    cs:__imp_SysStringLen
0x18000293b  test    eax, eax
0x18000293d  jz      loc_180002682
0x180002943  mov     r8, [rbp+var_28]
0x180002947  mov     edx, 0Bh
0x18000294c  mov     rcx, rbx
0x18000294f  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180002954  mov     edi, eax
0x180002956  test    eax, eax
0x180002958  js      short loc_1800028F8
0x18000295a  jmp     loc_180002682
0x18000295f  call    cs:__imp_SysStringLen
0x180002965  test    eax, eax
0x180002967  jz      loc_180002610
0x18000296d  mov     r8, [rbp+arg_18]
0x180002971  mov     edx, 8
0x180002976  mov     rcx, rbx
0x180002979  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18000297e  mov     edi, eax
0x180002980  test    eax, eax
0x180002982  js      short loc_180002919
0x180002984  jmp     loc_180002610
0x180002989  mov     rcx, [rbp+var_38]; pbstr
  ... truncated ...
```
