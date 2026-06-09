# TaskXmlReader::ProcessComplexContent(ITaskXmlHandler *,TaskXmlNodeId,bool,bool &)

- ea: `0x1800192f0`
- end: `0x180019d08`
- name: `?ProcessComplexContent@TaskXmlReader@@AEAAJPEAUITaskXmlHandler@@W4TaskXmlNodeId@@_NAEA_N@Z`
- size: `2584`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800185f0`

## callees

- `0x1800157e4`
- `0x180015810`
- `0x180017860`
- `0x1800180f0`
- `0x1800185f0`
- `0x1800192f0`
- `0x180019d10`
- `0x180019d68`
- `0x18001a170`
- `0x180028a80`
- `0x180029350`
- `0x180038404`
- `0x18003843c`
- `0x180039484`
- `0x180039708`
- `0x18004babc`
- `0x18004e91b`
- `0x18004e950`
- `0x180054010`

## import_xrefs

- `msvcrt!free` at `0x1800199d9`
- `msvcrt!free` at `0x180019a17`
- `msvcrt!free` at `0x180019a46`
- `msvcrt!free` at `0x1800199d9`
- `msvcrt!free` at `0x180019a17`
- `msvcrt!free` at `0x180019a46`
- `OLEAUT32!__imp_SysFreeString` at `0x180019bcf`
- `OLEAUT32!__imp_SysFreeString` at `0x180019bcf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TaskXmlReader::ProcessComplexContent(__int64 a1, struct IErrorInfo *a2, int a3, char a4, _BYTE *a5)
{
  __int64 v5; // r14
  int v7; // esi
  unsigned int v8; // r12d
  char v9; // al
  __int64 v10; // rbp
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, __int64, __int64); // rdi
  int v14; // eax
  int m; // ebp
  int v16; // edx
  int v17; // eax
  __int64 *v18; // rax
  __int64 v19; // rdi
  int v20; // edx
  __int64 *v21; // rbx
  size_t v22; // r8
  struct IErrorInfo *v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r9
  __int64 result; // rax
  __int64 v27; // rcx
  unsigned int j; // r10d
  int v29; // r8d
  __int64 *v30; // rdx
  int v31; // ebx
  int v32; // r11d
  __int64 v33; // r9
  __int64 *v34; // rdx
  __int64 k; // rcx
  unsigned __int64 v36; // r8
  __int64 v37; // rax
  const unsigned __int64 near *v38; // rdx
  unsigned __int64 v39; // r8
  __int64 v40; // rax
  const unsigned __int64 near *v41; // rdx
  __int64 v42; // r9
  unsigned int i; // r10d
  int v44; // r8d
  __int64 *v45; // rdx
  int v46; // ebp
  __int64 v47; // r11
  __int64 *v48; // rdx
  __int64 Entry; // rax
  const unsigned __int64 *v50; // r9
  unsigned __int64 v51; // r11
  __int64 v52; // rax
  const unsigned __int64 near *v53; // r8
  const unsigned __int64 *v54; // r9
  unsigned __int64 v55; // r9
  __int64 v56; // rax
  const unsigned __int64 near *v57; // r8
  unsigned int v58; // eax
  unsigned int v59; // ebx
  __int64 v60; // rdi
  __int64 (__fastcall *v61)(__int64, const unsigned __int16 **, __int64); // rbx
  bool v62; // dl
  const unsigned __int16 **PString; // rax
  int RawValue; // eax
  __int64 v65; // rbx
  struct IErrorInfo *v66; // rdi
  _BYTE *v67; // rbx
  __int64 v68; // rbx
  __int64 v69; // rax
  unsigned __int16 *v70; // [rsp+20h] [rbp-178h]
  char v71; // [rsp+30h] [rbp-168h]
  unsigned int v72; // [rsp+34h] [rbp-164h]
  char v73[4]; // [rsp+38h] [rbp-160h] BYREF
  int v74; // [rsp+3Ch] [rbp-15Ch] BYREF
  struct IErrorInfo *v75; // [rsp+40h] [rbp-158h]
  _BYTE *v76; // [rsp+48h] [rbp-150h]
  _BYTE v77[48]; // [rsp+50h] [rbp-148h] BYREF
  __int64 v78; // [rsp+80h] [rbp-118h]
  void *Block; // [rsp+88h] [rbp-110h]
  _DWORD v80[44]; // [rsp+A0h] [rbp-F8h]

  v5 = a3;
  v75 = a2;
  v76 = a5;
  v7 = 0;
  if ( a4 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= 0x16 )
        return (unsigned int)v7;
      v44 = *(_DWORD *)(a1 + 1116);
      if ( v44 == 65542 )
      {
LABEL_75:
        v45 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v44][16 * v5];
        v46 = v44 - 0x10000;
      }
      else
      {
        v46 = v44 - 0x10000;
        switch ( v44 )
        {
          case 65536:
          case 65537:
            v54 = 0;
            break;
          case 65538:
          case 65539:
          case 65540:
          case 65541:
            goto LABEL_75;
          default:
            goto LABEL_108;
        }
        while ( v54 < (&Schema::schemaEntriesCount)[(unsigned __int16)v44] )
        {
          v45 = (__int64 *)(*((_QWORD *)&_ImageBase + (unsigned __int16)v44 + 46058) + ((_QWORD)v54 << 7));
          if ( *(_DWORD *)v45 == (_DWORD)v5 )
            goto LABEL_76;
          v54 = (const unsigned __int64 *)((char *)v54 + 1);
        }
LABEL_108:
        v45 = &qword_18006EE10;
      }
LABEL_76:
      v47 = *((int *)v45 + (int)i + 10);
      if ( !(_DWORD)v47 )
        return (unsigned int)v7;
      if ( v44 == 65542 )
      {
LABEL_78:
        v48 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v44][16 * v47];
      }
      else
      {
        switch ( v46 )
        {
          case 0:
          case 1:
            v55 = 0;
            v56 = (unsigned __int16)v44;
            v57 = (&Schema::schemaEntriesCount)[(unsigned __int16)v44];
            break;
          case 2:
          case 3:
          case 4:
          case 5:
            goto LABEL_78;
          default:
            goto LABEL_109;
        }
        while ( v55 < (unsigned __int64)v57 )
        {
          v48 = (__int64 *)(*((_QWORD *)&_ImageBase + v56 + 46058) + (v55 << 7));
          if ( *(_DWORD *)v48 == (_DWORD)v47 )
            goto LABEL_79;
          ++v55;
        }
LABEL_109:
        v48 = &qword_18006EE10;
      }
LABEL_79:
      if ( *((_DWORD *)v48 + 6) == 2 )
      {
        if ( *((_DWORD *)v48 + 8) )
        {
LABEL_82:
          Entry = Schema::GetEntry(a1 + 1116, (unsigned int)v47);
          return (unsigned int)TaskXmlReader::SetErrorInfo(
                                 (TaskXmlReader *)a1,
                                 -2147216615,
                                 *(const unsigned __int16 **)(Entry + 8),
                                 *(_DWORD *)(Entry + 16),
                                 0,
                                 0);
        }
      }
      else if ( *((_DWORD *)v48 + 8) )
      {
        goto LABEL_82;
      }
    }
  }
  v74 = 0;
  v8 = 0;
  v72 = 0;
  v9 = 1;
  v10 = a1 + 64;
LABEL_3:
  v71 = v9;
  while ( 1 )
  {
LABEL_4:
    if ( !v9 )
      goto LABEL_44;
    v11 = *(_QWORD *)(a1 + 56);
    if ( !v11 )
      _com_raise_error(-2147467261, a2);
    v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v11 + 48LL))(v11, &v74);
    if ( v7 )
    {
      v8 = v72;
LABEL_44:
      if ( v7 < 0 )
        return TaskXmlReader::SetErrorInfoXmlLite((TaskXmlReader *)a1, v7);
      for ( j = 0; j < 0x16; ++j )
      {
        v29 = *(_DWORD *)(a1 + 1116);
        if ( v29 == 65542 )
        {
LABEL_48:
          v30 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v29][16 * v5];
          v31 = v29 - 0x10000;
        }
        else
        {
          v31 = v29 - 0x10000;
          switch ( v29 )
          {
            case 65536:
            case 65537:
              v50 = 0;
              v32 = *(_DWORD *)(a1 + 1116);
              break;
            case 65538:
            case 65539:
            case 65540:
            case 65541:
              goto LABEL_48;
            default:
              goto LABEL_106;
          }
          while ( v50 < (&Schema::schemaEntriesCount)[(unsigned __int16)v29] )
          {
            v30 = (__int64 *)(*((_QWORD *)&_ImageBase + (unsigned __int16)v29 + 46058) + ((_QWORD)v50 << 7));
            if ( *(_DWORD *)v30 == (_DWORD)v5 )
              goto LABEL_50;
            v50 = (const unsigned __int64 *)((char *)v50 + 1);
          }
LABEL_106:
          v30 = &qword_18006EE10;
        }
        v32 = *(_DWORD *)(a1 + 1116);
LABEL_50:
        v33 = *((int *)v30 + (int)j + 10);
        if ( !(_DWORD)v33 )
          break;
        if ( v29 == 65542 )
        {
LABEL_52:
          v34 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v32][16 * v33];
        }
        else
        {
          switch ( v31 )
          {
            case 0:
            case 1:
              v51 = 0;
              v52 = (unsigned __int16)v29;
              v53 = (&Schema::schemaEntriesCount)[(unsigned __int16)v29];
              break;
            case 2:
            case 3:
            case 4:
            case 5:
              goto LABEL_52;
            default:
              goto LABEL_107;
          }
          while ( v51 < (unsigned __int64)v53 )
          {
            v34 = (__int64 *)(*((_QWORD *)&_ImageBase + v52 + 46058) + (v51 << 7));
            if ( *(_DWORD *)v34 == (_DWORD)v33 )
              goto LABEL_53;
            ++v51;
          }
LABEL_107:
          v34 = &qword_18006EE10;
        }
LABEL_53:
        if ( *((_DWORD *)v34 + 6) != 2 && *((_DWORD *)v34 + 8) )
        {
          for ( k = 0; ; k = (unsigned int)(k + 1) )
          {
            if ( (unsigned int)k >= v8 )
              return TaskXmlReader::SetErrorInfo(a1, 2147750681LL, (unsigned int)v33);
            if ( v80[2 * k] == (_DWORD)v33 )
              break;
          }
        }
      }
      return 0;
    }
    if ( v74 == 1 )
      break;
    if ( v74 == 3 )
    {
      v60 = _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(a1 + 56);
      v61 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 **, __int64))(*(_QWORD *)v60 + 128LL);
      PString = XmlParserTempString::GetPString((XmlParserTempString *)v10, v62);
      v14 = v61(v60, PString, v10);
      if ( v14 < 0 )
        return TaskXmlReader::SetErrorInfoXmlLite((TaskXmlReader *)a1, v14);
      v7 = XmlParserTempString::Trim((XmlParserTempString *)v10);
      if ( v7 < 0 )
        return TaskXmlReader::SetErrorInfo(a1, 2147750680LL, (unsigned int)v5, v10);
      v8 = v72;
      v9 = v71;
      if ( *(_DWORD *)v10 )
      {
        if ( (_DWORD)v5 != 33 )
          return TaskXmlReader::SetErrorInfo(a1, 2147750680LL, (unsigned int)v5, v10);
        XmlParserTempString::~XmlParserTempString((XmlParserTempString *)v10);
        RawValue = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (struct XmlParserTempString *)v10);
        v7 = RawValue;
        if ( RawValue >= 0 )
        {
          ITaskXmlHandler::Data::Data((ITaskXmlHandler::Data *)v77);
          v65 = v10;
          v78 = v10;
          v66 = v75;
          if ( v75 )
          {
            v67 = v76;
            LOBYTE(v70) = *v76;
            v7 = ((__int64 (__fastcall *)(struct IErrorInfo *, __int64, __int64, _BYTE *, unsigned __int16 *))v75->lpVtbl->AddRef)(
                   v75,
                   a1 + 1116,
                   33,
                   v77,
                   v70);
            *v67 = 1;
            if ( v7 < 0 )
            {
              if ( ((unsigned int (__fastcall *)(struct IErrorInfo *))v66->lpVtbl->GetGUID)(v66) )
              {
                v58 = ((__int64 (__fastcall *)(struct IErrorInfo *))v66->lpVtbl->GetGUID)(v66);
                v59 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v7, v58, v10);
                if ( Block )
                  free(Block);
              }
              else
              {
                v59 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v7, 33, v10);
                if ( Block )
                {
                  free(Block);
                  return v59;
                }
              }
              return v59;
            }
            v65 = v78;
          }
          if ( *(_BYTE *)(a1 + 40) )
          {
            v68 = *(_QWORD *)(v65 + 8);
            v69 = _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(*(_QWORD *)(a1 + 16) + 16LL);
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v69 + 224LL))(v69, v68);
          }
          v8 = v72;
          v9 = v71;
          if ( Block )
          {
            free(Block);
            v9 = v71;
          }
        }
        else
        {
          v7 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)RawValue, 33);
          v9 = v71;
        }
      }
    }
    else
    {
      v8 = v72;
      v9 = v71;
      if ( v74 != 7 && v74 != 8 && v74 != 13 )
      {
        if ( v74 != 15 )
          return TaskXmlReader::SetErrorInfo((TaskXmlReader *)a1, -2147216618, (struct XmlParserTempString *)v10);
        v9 = 0;
        goto LABEL_3;
      }
    }
  }
  v12 = *(_QWORD *)(a1 + 56);
  if ( !v12 )
    _com_raise_error(-2147467261, a2);
  v13 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v12 + 112LL);
  if ( (*(_BYTE *)(v10 + 1042) & 1) != 0 )
    SysFreeString(*(BSTR *)(v10 + 8));
  *(_DWORD *)v10 = 0;
  *(_QWORD *)(v10 + 8) = 0;
  *(_BYTE *)(v10 + 1042) &= 0xFCu;
  *(_WORD *)(v10 + 16) = 0;
  v14 = v13(v12, v10 + 8, v10);
  if ( v14 < 0 )
    return TaskXmlReader::SetErrorInfoXmlLite((TaskXmlReader *)a1, v14);
  for ( m = 0; ; ++m )
  {
    if ( (unsigned __int64)m >= 0x16 || !(_DWORD)v5 )
      return TaskXmlReader::SetErrorInfo((TaskXmlReader *)a1, -2147216618, (struct XmlParserTempString *)(a1 + 64));
    v16 = *(_DWORD *)(a1 + 1116);
    if ( v16 == 65538 )
      goto LABEL_18;
    if ( v16 != 65542 )
    {
      if ( v16 != 0x10000 && v16 != 65537 )
      {
        switch ( v16 )
        {
          case 65539:
            v17 = 136;
            break;
          case 65540:
            v17 = 145;
            break;
          case 65541:
            v17 = 148;
            break;
          default:
            v17 = 0;
            break;
        }
        goto LABEL_19;
      }
LABEL_18:
      v17 = 131;
      goto LABEL_19;
    }
    v17 = 149;
LABEL_19:
    if ( (int)v5 >= v17 )
      return TaskXmlReader::SetErrorInfo((TaskXmlReader *)a1, -2147216618, (struct XmlParserTempString *)(a1 + 64));
    if ( v16 == 65542 )
    {
LABEL_21:
      v18 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v16][16 * v5];
    }
    else
    {
      switch ( v16 )
      {
        case 65536:
        case 65537:
          v39 = 0;
          v40 = (unsigned __int16)v16;
          v41 = (&Schema::schemaEntriesCount)[(unsigned __int16)v16];
          v42 = 8 * v40 + 368464;
          break;
        case 65538:
        case 65539:
        case 65540:
        case 65541:
          goto LABEL_21;
        default:
          goto LABEL_94;
      }
      while ( v39 < (unsigned __int64)v41 )
      {
        v18 = (__int64 *)((v39 << 7) + *(_QWORD *)((char *)&_ImageBase + v42));
        if ( *(_DWORD *)v18 == (_DWORD)v5 )
          goto LABEL_22;
        ++v39;
      }
LABEL_94:
      v18 = &qword_18006EE10;
    }
LABEL_22:
    v19 = *((int *)v18 + m + 10);
    if ( !(_DWORD)v19 )
      return TaskXmlReader::SetErrorInfo((TaskXmlReader *)a1, -2147216618, (struct XmlParserTempString *)(a1 + 64));
    v20 = *(_DWORD *)(a1 + 1116);
    if ( v20 == 65542 )
    {
LABEL_24:
      v21 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v20][16 * v19];
    }
    else
    {
      switch ( v20 )
      {
        case 65536:
        case 65537:
          v36 = 0;
          v37 = (unsigned __int16)v20;
          v38 = (&Schema::schemaEntriesCount)[(unsigned __int16)v20];
          break;
        case 65538:
        case 65539:
        case 65540:
        case 65541:
          goto LABEL_24;
        default:
          goto LABEL_95;
      }
      while ( v36 < (unsigned __int64)v38 )
      {
        v21 = (__int64 *)(*((_QWORD *)&_ImageBase + v37 + 46058) + (v36 << 7));
        if ( *(_DWORD *)v21 == (_DWORD)v19 )
          goto LABEL_25;
        ++v36;
      }
LABEL_95:
      v21 = &qword_18006EE10;
    }
LABEL_25:
    if ( *((_DWORD *)v21 + 6) == 1 )
    {
      v22 = *((unsigned int *)v21 + 4);
      if ( *(_DWORD *)(a1 + 64) == (_DWORD)v22 && !wcsncmp_0(*(const wchar_t **)(a1 + 72), (const wchar_t *)v21[1], v22) )
        break;
    }
  }
  v73[0] = 0;
  v24 = *(_QWORD *)(a1 + 56);
  if ( !v24 )
    _com_raise_error(-2147467261, v23);
  LOBYTE(v25) = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v24 + 160LL))(v24) != 0;
  result = TaskXmlReader::ProcessElement(a1, v75, (unsigned int)v19, v25, v73);
  v7 = result;
  if ( (int)result >= 0 )
  {
    v27 = 0;
    v8 = v72;
    if ( v72 )
    {
      while ( v80[2 * v27] != (_DWORD)v19 )
      {
        v27 = (unsigned int)(v27 + 1);
        if ( (unsigned int)v27 >= v72 )
          goto LABEL_34;
      }
    }
    else
    {
LABEL_34:
      if ( (_DWORD)v27 == v72 )
      {
        v80[2 * v72] = v19;
        v80[2 * v72 + 1] = 1;
        v8 = ++v72;
        v10 = a1 + 64;
        v9 = v71;
        goto LABEL_4;
      }
    }
    if ( ++v80[2 * v27 + 1] <= *((_DWORD *)v21 + 9) )
    {
      v10 = a1 + 64;
      v9 = v71;
      goto LABEL_4;
    }
    return TaskXmlReader::SetErrorInfo(a1, 2147750685LL, (unsigned int)v19);
  }
  return result;
}

```

## disassembly

```asm
0x1800192f0  mov     [rsp+arg_18], rbx
0x1800192f5  push    rbp
0x1800192f6  push    rsi
0x1800192f7  push    rdi
0x1800192f8  push    r12
0x1800192fa  push    r13
0x1800192fc  push    r14
0x1800192fe  push    r15
0x180019300  sub     rsp, 160h
0x180019307  mov     rax, cs:__security_cookie
0x18001930e  xor     rax, rsp
0x180019311  mov     [rsp+198h+var_48], rax
0x180019319  movsxd  r14, r8d
0x18001931c  mov     [rsp+198h+var_158], rdx
0x180019321  mov     r13, rcx
0x180019324  mov     rax, [rsp+198h+arg_20]
0x18001932c  mov     [rsp+198h+var_150], rax
0x180019331  xor     esi, esi
0x180019333  lea     r15, __ImageBase
0x18001933a  test    r9b, r9b
0x18001933d  jnz     loc_18001972A
0x180019343  mov     [rsp+198h+var_15C], esi
0x180019347  xor     r12d, r12d
0x18001934a  mov     [rsp+198h+var_164], r12d
0x18001934f  mov     al, 1
0x180019351  lea     rbp, [rcx+40h]
0x180019355  mov     [rsp+198h+var_168], al
0x180019359  test    al, al
0x18001935b  jz      loc_1800195A1
0x180019361  mov     rcx, [r13+38h]
0x180019365  test    rcx, rcx
0x180019368  jz      loc_180019C5E
0x18001936e  mov     rax, [rcx]
0x180019371  lea     rdx, [rsp+198h+var_15C]
0x180019376  mov     rax, [rax+30h]
0x18001937a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001937f  mov     esi, eax
0x180019381  test    eax, eax
0x180019383  jnz     loc_18001959C
0x180019389  mov     ecx, [rsp+198h+var_15C]
0x18001938d  cmp     ecx, 1
0x180019390  jnz     loc_180019A61
0x180019396  mov     rbx, [r13+38h]
0x18001939a  test    rbx, rbx
0x18001939d  jz      loc_180019C53
0x1800193a3  mov     rax, [rbx]
0x1800193a6  mov     rdi, [rax+70h]
0x1800193aa  test    [rbp+412h], cl
0x1800193b0  jnz     loc_180019BCB
0x1800193b6  xor     esi, esi
0x1800193b8  mov     [rbp+0], esi
0x1800193bb  lea     rdx, [rbp+8]
0x1800193bf  mov     [rdx], rsi
0x1800193c2  and     byte ptr [rbp+412h], 0FCh
0x1800193c9  mov     [rbp+10h], si
0x1800193cd  mov     r8, rbp
0x1800193d0  mov     rcx, rbx
0x1800193d3  mov     rax, rdi
0x1800193d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193db  test    eax, eax
0x1800193dd  js      loc_180019C39
0x1800193e3  mov     ebp, esi
0x1800193e5  nop     word ptr [rax+rax+00000000h]
0x1800193f0  movsxd  rdi, ebp
0x1800193f3  cmp     rdi, 16h
0x1800193f7  jnb     loc_18001997E
0x1800193fd  test    r14d, r14d
0x180019400  jz      loc_18001997E
0x180019406  mov     edx, [r13+45Ch]
0x18001940d  cmp     edx, 10002h
0x180019413  jz      short loc_180019428
0x180019415  cmp     edx, 10006h
0x18001941b  jnz     loc_180019544
0x180019421  mov     eax, 95h
0x180019426  jmp     short loc_18001942D
0x180019428  mov     eax, 83h
0x18001942d  cmp     r14d, eax
0x180019430  jge     loc_18001997E
0x180019436  cmp     edx, 10006h
0x18001943c  jnz     loc_1800196D1
0x180019442  movzx   ecx, dx; jumptable 00000001800196ED cases 65538-65541
0x180019445  mov     rax, r14
0x180019448  shl     rax, 7
0x18001944c  add     rax, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r15+rcx*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180019454  movsxd  rdi, dword ptr [rax+rdi*4+28h]
0x180019459  test    edi, edi
0x18001945b  jz      loc_18001997E
0x180019461  mov     edx, [r13+45Ch]
0x180019468  cmp     edx, 10006h
0x18001946e  jnz     loc_180019675
0x180019474  movzx   eax, dx; jumptable 0000000180019691 cases 65538-65541
0x180019477  mov     rbx, rdi
0x18001947a  shl     rbx, 7
0x18001947e  add     rbx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r15+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180019486  cmp     dword ptr [rbx+18h], 1
0x18001948a  jz      short loc_180019493
0x18001948c  inc     ebp
0x18001948e  jmp     loc_1800193F0
0x180019493  mov     r8d, [rbx+10h]; MaxCount
0x180019497  cmp     [r13+40h], r8d
0x18001949b  jnz     short loc_18001948C
0x18001949d  mov     rdx, [rbx+8]; String2
0x1800194a1  mov     rcx, [r13+48h]; String1
0x1800194a5  call    wcsncmp_0
0x1800194aa  test    eax, eax
0x1800194ac  jnz     short loc_18001948C
0x1800194ae  mov     [rsp+198h+var_160], sil
0x1800194b3  mov     rcx, [r13+38h]
0x1800194b7  test    rcx, rcx
0x1800194ba  jz      loc_180019C48
0x1800194c0  mov     rax, [rcx]
0x1800194c3  mov     rax, [rax+0A0h]
0x1800194ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194cf  test    eax, eax
0x1800194d1  setnz   r9b
0x1800194d5  lea     rax, [rsp+198h+var_160]
0x1800194da  mov     [rsp+198h+var_178], rax
0x1800194df  mov     r8d, edi
0x1800194e2  mov     rdx, [rsp+198h+var_158]
0x1800194e7  mov     rcx, r13
0x1800194ea  call    ?ProcessElement@TaskXmlReader@@AEAAJPEAUITaskXmlHandler@@W4TaskXmlNodeId@@_NAEA_N@Z; TaskXmlReader::ProcessElement(ITaskXmlHandler *,TaskXmlNodeId,bool,bool &)
0x1800194ef  mov     esi, eax
0x1800194f1  test    eax, eax
0x1800194f3  js      loc_180019640
0x1800194f9  xor     ecx, ecx
0x1800194fb  mov     r12d, [rsp+198h+var_164]
0x180019500  test    r12d, r12d
0x180019503  jz      short loc_180019515
0x180019505  cmp     [rsp+rcx*8+198h+var_F8], edi
0x18001950c  jz      short loc_180019577
0x18001950e  inc     ecx
0x180019510  cmp     ecx, r12d
0x180019513  jb      short loc_180019505
0x180019515  cmp     ecx, r12d
0x180019518  jnz     short loc_180019577
0x18001951a  mov     [rsp+r12*8+198h+var_F8], edi
0x180019522  mov     [rsp+r12*8+198h+var_F4], 1
0x18001952e  inc     r12d
0x180019531  mov     [rsp+198h+var_164], r12d
0x180019536  lea     rbp, [r13+40h]
0x18001953a  movzx   eax, [rsp+198h+var_168]
0x18001953f  jmp     loc_180019359
0x180019544  mov     ecx, edx
0x180019546  sub     ecx, 10000h
0x18001954c  jz      loc_180019428
0x180019552  sub     ecx, 1
0x180019555  jz      loc_180019428
0x18001955b  sub     ecx, 2
0x18001955e  jz      loc_18001966B
0x180019564  sub     ecx, 1
0x180019567  jnz     loc_180019BDA
0x18001956d  mov     eax, 91h
0x180019572  jmp     loc_18001942D
0x180019577  inc     [rsp+rcx*8+198h+var_F4]
0x18001957e  mov     eax, [rsp+rcx*8+198h+var_F4]
0x180019585  cmp     eax, [rbx+24h]
0x180019588  ja      loc_180019994
0x18001958e  lea     rbp, [r13+40h]
0x180019592  movzx   eax, [rsp+198h+var_168]
0x180019597  jmp     loc_180019359
0x18001959c  mov     r12d, [rsp+198h+var_164]
0x1800195a1  test    esi, esi
0x1800195a3  js      loc_180019C69
0x1800195a9  xor     r10d, r10d
0x1800195ac  cmp     r10d, 16h
0x1800195b0  jnb     short loc_180019621
0x1800195b2  mov     r8d, [r13+45Ch]
0x1800195b9  cmp     r8d, 10006h
0x1800195c0  jnz     loc_1800197E1
0x1800195c6  movzx   eax, r8w; jumptable 00000001800197FF cases 65538-65541
0x1800195ca  mov     rdx, r14
0x1800195cd  shl     rdx, 7
0x1800195d1  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r15+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x1800195d9  lea     ebx, [r8-10000h]
0x1800195e0  mov     r11, r8
0x1800195e3  movsxd  rax, r10d
0x1800195e6  movsxd  r9, dword ptr [rdx+rax*4+28h]
0x1800195eb  test    r9d, r9d
0x1800195ee  jz      short loc_180019621
0x1800195f0  cmp     r8d, 10006h
0x1800195f7  jnz     loc_180019842
0x1800195fd  movzx   eax, r11w; jumptable 0000000180019859 cases 2-5
0x180019601  mov     rdx, r9
0x180019604  shl     rdx, 7
0x180019608  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r15+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180019610  cmp     dword ptr [rdx+18h], 2
0x180019614  jz      short loc_18001961C
0x180019616  cmp     dword ptr [rdx+20h], 0
0x18001961a  jnz     short loc_180019625
0x18001961c  inc     r10d
0x18001961f  jmp     short loc_1800195AC
0x180019621  xor     eax, eax
0x180019623  jmp     short loc_180019640
0x180019625  xor     ecx, ecx
0x180019627  cmp     ecx, r12d
0x18001962a  jb      loc_1800199A9
0x180019630  mov     r8d, r9d
0x180019633  mov     edx, 80041319h
0x180019638  mov     rcx, r13
0x18001963b  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId)
0x180019640  mov     rcx, [rsp+198h+var_48]
0x180019648  xor     rcx, rsp; StackCookie
0x18001964b  call    __security_check_cookie
0x180019650  mov     rbx, [rsp+198h+arg_18]
0x180019658  add     rsp, 160h
0x18001965f  pop     r15
0x180019661  pop     r14
0x180019663  pop     r13
0x180019665  pop     r12
0x180019667  pop     rdi
0x180019668  pop     rsi
0x180019669  pop     rbp
0x18001966a  retn
0x18001966b  mov     eax, 88h
0x180019670  jmp     loc_18001942D
0x180019675  lea     eax, [rdx-10000h]; switch 6 cases
0x18001967b  cmp     eax, 5
0x18001967e  ja      def_180019691; jumptable 0000000180019691 default case
0x180019684  cdqe
0x180019686  mov     ecx, ds:(jpt_180019691 - 180000000h)[r15+rax*4]
0x18001968e  add     rcx, r15
0x180019691  jmp     rcx; switch jump
0x180019693  xor     r8d, r8d; jumptable 0000000180019691 cases 65536,65537
0x180019696  movzx   eax, dx
0x180019699  mov     rdx, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r15+rax*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x1800196a1  lea     r9, ds:59F50h[rax*8]
0x1800196a9  nop     dword ptr [rax+00000000h]
0x1800196b0  cmp     r8, rdx
0x1800196b3  jnb     def_180019691; jumptable 0000000180019691 default case
0x1800196b9  mov     rbx, r8
0x1800196bc  shl     rbx, 7
0x1800196c0  add     rbx, [r9+r15]
0x1800196c4  cmp     [rbx], edi
0x1800196c6  jz      loc_180019486
0x1800196cc  inc     r8
0x1800196cf  jmp     short loc_1800196B0
0x1800196d1  lea     eax, [rdx-10000h]; switch 6 cases
0x1800196d7  cmp     eax, 5
0x1800196da  ja      def_1800196ED; jumptable 00000001800196ED default case
0x1800196e0  cdqe
0x1800196e2  mov     ecx, ds:(jpt_1800196ED - 180000000h)[r15+rax*4]
0x1800196ea  add     rcx, r15
0x1800196ed  jmp     rcx; switch jump
0x1800196ef  xor     r8d, r8d; jumptable 00000001800196ED cases 65536,65537
0x1800196f2  movzx   eax, dx
0x1800196f5  mov     rdx, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r15+rax*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x1800196fd  lea     r9, ds:59F50h[rax*8]
0x180019705  cmp     r8, rdx
0x180019708  jnb     def_1800196ED; jumptable 00000001800196ED default case
0x18001970e  mov     rcx, r8
0x180019711  shl     rcx, 7
0x180019715  mov     rax, [r9+r15]
0x180019719  add     rax, rcx
0x18001971c  cmp     [rax], r14d
0x18001971f  jz      loc_180019454
0x180019725  inc     r8
0x180019728  jmp     short loc_180019705
0x18001972a  xor     r10d, r10d
0x18001972d  nop     dword ptr [rax]
0x180019730  cmp     r10d, 16h
0x180019734  jnb     loc_1800197DA
0x18001973a  mov     r8d, [r13+45Ch]
0x180019741  cmp     r8d, 10006h
0x180019748  jnz     loc_1800198AC
0x18001974e  movzx   eax, r8w; jumptable 00000001800198CA cases 65538-65541
0x180019752  mov     rdx, r14
0x180019755  shl     rdx, 7
0x180019759  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r15+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180019761  lea     ebp, [r8-10000h]
0x180019768  movsxd  rax, r10d
0x18001976b  movsxd  r11, dword ptr [rdx+rax*4+28h]
0x180019770  test    r11d, r11d
0x180019773  jz      short loc_1800197DA
0x180019775  cmp     r8d, 10006h
0x18001977c  jnz     loc_180019901
0x180019782  movzx   eax, r8w; jumptable 0000000180019914 cases 2-5
0x180019786  mov     rdx, r11
0x180019789  shl     rdx, 7
0x18001978d  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r15+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180019795  cmp     dword ptr [rdx+18h], 2
0x180019799  jz      loc_180019A53
0x18001979f  cmp     [rdx+20h], esi
0x1800197a2  jnz     short loc_1800197A9
0x1800197a4  inc     r10d
0x1800197a7  jmp     short loc_180019730
0x1800197a9  mov     edx, r11d
0x1800197ac  lea     rcx, [r13+45Ch]
0x1800197b3  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x1800197b8  xor     ecx, ecx
0x1800197ba  mov     [rsp+198h+var_170], ecx; unsigned int
0x1800197be  mov     [rsp+198h+var_178], rcx; unsigned __int16 *
0x1800197c3  mov     r9d, [rax+10h]; unsigned int
0x1800197c7  mov     r8, [rax+8]; unsigned __int16 *
0x1800197cb  mov     edx, 80041319h; int
0x1800197d0  mov     rcx, r13; this
0x1800197d3  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJPEBGK0K@Z; TaskXmlReader::SetErrorInfo(long,ushort const *,ulong,ushort const *,ulong)
0x1800197d8  mov     esi, eax
0x1800197da  mov     eax, esi
0x1800197dc  jmp     loc_180019640
0x1800197e1  lea     ebx, [r8-10000h]; switch 6 cases
  ... truncated ...
```
