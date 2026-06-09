# TaskXmlReader::ProcessComplexContent(ITaskXmlHandler *,TaskXmlNodeId,bool,bool &)

- ea: `0x18001a460`
- end: `0x18001aeb8`
- name: `?ProcessComplexContent@TaskXmlReader@@AEAAJPEAUITaskXmlHandler@@W4TaskXmlNodeId@@_NAEA_N@Z`
- size: `2648`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180019730`

## callees

- `0x180016900`
- `0x180016930`
- `0x180018940`
- `0x180019228`
- `0x180019730`
- `0x18001a460`
- `0x18001aec0`
- `0x18001af18`
- `0x18001b340`
- `0x18002a6f0`
- `0x18002b570`
- `0x18003b514`
- `0x18003b74c`
- `0x18003c590`
- `0x18003c85c`
- `0x18004f6dc`
- `0x180052617`
- `0x180052640`
- `0x180058010`

## import_xrefs

- `msvcrt!free` at `0x18001ab6b`
- `msvcrt!free` at `0x18001abaf`
- `msvcrt!free` at `0x18001abe4`
- `msvcrt!free` at `0x18001ab6b`
- `msvcrt!free` at `0x18001abaf`
- `msvcrt!free` at `0x18001abe4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ad77`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ad77`

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
          v45 = (__int64 *)(*((_QWORD *)&_ImageBase + (unsigned __int16)v44 + 48103) + ((_QWORD)v54 << 7));
          if ( *(_DWORD *)v45 == (_DWORD)v5 )
            goto LABEL_76;
          v54 = (const unsigned __int64 *)((char *)v54 + 1);
        }
LABEL_108:
        v45 = &qword_180072DF0;
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
          v48 = (__int64 *)(*((_QWORD *)&_ImageBase + v56 + 48103) + (v55 << 7));
          if ( *(_DWORD *)v48 == (_DWORD)v47 )
            goto LABEL_79;
          ++v55;
        }
LABEL_109:
        v48 = &qword_180072DF0;
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
            v30 = (__int64 *)(*((_QWORD *)&_ImageBase + (unsigned __int16)v29 + 48103) + ((_QWORD)v50 << 7));
            if ( *(_DWORD *)v30 == (_DWORD)v5 )
              goto LABEL_50;
            v50 = (const unsigned __int64 *)((char *)v50 + 1);
          }
LABEL_106:
          v30 = &qword_180072DF0;
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
            v34 = (__int64 *)(*((_QWORD *)&_ImageBase + v52 + 48103) + (v51 << 7));
            if ( *(_DWORD *)v34 == (_DWORD)v33 )
              goto LABEL_53;
            ++v51;
          }
LABEL_107:
          v34 = &qword_180072DF0;
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
          v42 = 8 * v40 + 384824;
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
      v18 = &qword_180072DF0;
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
        v21 = (__int64 *)(*((_QWORD *)&_ImageBase + v37 + 48103) + (v36 << 7));
        if ( *(_DWORD *)v21 == (_DWORD)v19 )
          goto LABEL_25;
        ++v36;
      }
LABEL_95:
      v21 = &qword_180072DF0;
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
0x18001a460  mov     [rsp+arg_18], rbx
0x18001a465  push    rbp
0x18001a466  push    rsi
0x18001a467  push    rdi
0x18001a468  push    r12
0x18001a46a  push    r13
0x18001a46c  push    r14
0x18001a46e  push    r15
0x18001a470  sub     rsp, 160h
0x18001a477  mov     rax, cs:__security_cookie
0x18001a47e  xor     rax, rsp
0x18001a481  mov     [rsp+198h+var_48], rax
0x18001a489  movsxd  r14, r8d
0x18001a48c  mov     [rsp+198h+var_158], rdx
0x18001a491  mov     r13, rcx
0x18001a494  mov     rax, [rsp+198h+arg_20]
0x18001a49c  mov     [rsp+198h+var_150], rax
0x18001a4a1  xor     esi, esi
0x18001a4a3  lea     r15, __ImageBase
0x18001a4aa  test    r9b, r9b
0x18001a4ad  jnz     loc_18001A8A5
0x18001a4b3  mov     [rsp+198h+var_15C], esi
0x18001a4b7  xor     r12d, r12d
0x18001a4ba  mov     [rsp+198h+var_164], r12d
0x18001a4bf  mov     al, 1
0x18001a4c1  lea     rbp, [rcx+40h]
0x18001a4c5  mov     [rsp+198h+var_168], al
0x18001a4c9  test    al, al
0x18001a4cb  jz      loc_18001A711
0x18001a4d1  mov     rcx, [r13+38h]
0x18001a4d5  test    rcx, rcx
0x18001a4d8  jz      loc_18001AE0C
0x18001a4de  mov     rax, [rcx]
0x18001a4e1  lea     rdx, [rsp+198h+var_15C]
0x18001a4e6  mov     rax, [rax+30h]
0x18001a4ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4ef  mov     esi, eax
0x18001a4f1  test    eax, eax
0x18001a4f3  jnz     loc_18001A70C
0x18001a4f9  mov     ecx, [rsp+198h+var_15C]
0x18001a4fd  cmp     ecx, 1
0x18001a500  jnz     loc_18001AC05
0x18001a506  mov     rbx, [r13+38h]
0x18001a50a  test    rbx, rbx
0x18001a50d  jz      loc_18001AE01
0x18001a513  mov     rax, [rbx]
0x18001a516  mov     rdi, [rax+70h]
0x18001a51a  test    [rbp+412h], cl
0x18001a520  jnz     loc_18001AD73
0x18001a526  xor     esi, esi
0x18001a528  mov     [rbp+0], esi
0x18001a52b  lea     rdx, [rbp+8]
0x18001a52f  mov     [rdx], rsi
0x18001a532  and     byte ptr [rbp+412h], 0FCh
0x18001a539  mov     [rbp+10h], si
0x18001a53d  mov     r8, rbp
0x18001a540  mov     rcx, rbx
0x18001a543  mov     rax, rdi
0x18001a546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a54b  test    eax, eax
0x18001a54d  js      loc_18001ADE7
0x18001a553  mov     ebp, esi
0x18001a555  nop     word ptr [rax+rax+00000000h]
0x18001a560  movsxd  rdi, ebp
0x18001a563  cmp     rdi, 16h
0x18001a567  jnb     loc_18001AB10
0x18001a56d  test    r14d, r14d
0x18001a570  jz      loc_18001AB10
0x18001a576  mov     edx, [r13+45Ch]
0x18001a57d  cmp     edx, 10002h
0x18001a583  jz      short loc_18001A598
0x18001a585  cmp     edx, 10006h
0x18001a58b  jnz     loc_18001A6B4
0x18001a591  mov     eax, 95h
0x18001a596  jmp     short loc_18001A59D
0x18001a598  mov     eax, 83h
0x18001a59d  cmp     r14d, eax
0x18001a5a0  jge     loc_18001AB10
0x18001a5a6  cmp     edx, 10006h
0x18001a5ac  jnz     loc_18001A841
0x18001a5b2  movzx   ecx, dx; jumptable 000000018001A85D cases 65538-65541
0x18001a5b5  mov     rax, r14
0x18001a5b8  shl     rax, 7
0x18001a5bc  add     rax, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r15+rcx*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18001a5c4  movsxd  rdi, dword ptr [rax+rdi*4+28h]
0x18001a5c9  test    edi, edi
0x18001a5cb  jz      loc_18001AB10
0x18001a5d1  mov     edx, [r13+45Ch]
0x18001a5d8  cmp     edx, 10006h
0x18001a5de  jnz     loc_18001A7E6
0x18001a5e4  movzx   eax, dx; jumptable 000000018001A802 cases 65538-65541
0x18001a5e7  mov     rbx, rdi
0x18001a5ea  shl     rbx, 7
0x18001a5ee  add     rbx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r15+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18001a5f6  cmp     dword ptr [rbx+18h], 1
0x18001a5fa  jz      short loc_18001A603
0x18001a5fc  inc     ebp
0x18001a5fe  jmp     loc_18001A560
0x18001a603  mov     r8d, [rbx+10h]; MaxCount
0x18001a607  cmp     [r13+40h], r8d
0x18001a60b  jnz     short loc_18001A5FC
0x18001a60d  mov     rdx, [rbx+8]; String2
0x18001a611  mov     rcx, [r13+48h]; String1
0x18001a615  call    wcsncmp_0
0x18001a61a  test    eax, eax
0x18001a61c  jnz     short loc_18001A5FC
0x18001a61e  mov     [rsp+198h+var_160], sil
0x18001a623  mov     rcx, [r13+38h]
0x18001a627  test    rcx, rcx
0x18001a62a  jz      loc_18001ADF6
0x18001a630  mov     rax, [rcx]
0x18001a633  mov     rax, [rax+0A0h]
0x18001a63a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a63f  test    eax, eax
0x18001a641  setnz   r9b
0x18001a645  lea     rax, [rsp+198h+var_160]
0x18001a64a  mov     [rsp+198h+var_178], rax
0x18001a64f  mov     r8d, edi
0x18001a652  mov     rdx, [rsp+198h+var_158]
0x18001a657  mov     rcx, r13
0x18001a65a  call    ?ProcessElement@TaskXmlReader@@AEAAJPEAUITaskXmlHandler@@W4TaskXmlNodeId@@_NAEA_N@Z; TaskXmlReader::ProcessElement(ITaskXmlHandler *,TaskXmlNodeId,bool,bool &)
0x18001a65f  mov     esi, eax
0x18001a661  test    eax, eax
0x18001a663  js      loc_18001A7B0
0x18001a669  xor     ecx, ecx
0x18001a66b  mov     r12d, [rsp+198h+var_164]
0x18001a670  test    r12d, r12d
0x18001a673  jz      short loc_18001A685
0x18001a675  cmp     [rsp+rcx*8+198h+var_F8], edi
0x18001a67c  jz      short loc_18001A6E7
0x18001a67e  inc     ecx
0x18001a680  cmp     ecx, r12d
0x18001a683  jb      short loc_18001A675
0x18001a685  cmp     ecx, r12d
0x18001a688  jnz     short loc_18001A6E7
0x18001a68a  mov     [rsp+r12*8+198h+var_F8], edi
0x18001a692  mov     [rsp+r12*8+198h+var_F4], 1
0x18001a69e  inc     r12d
0x18001a6a1  mov     [rsp+198h+var_164], r12d
0x18001a6a6  lea     rbp, [r13+40h]
0x18001a6aa  movzx   eax, [rsp+198h+var_168]
0x18001a6af  jmp     loc_18001A4C9
0x18001a6b4  mov     ecx, edx
0x18001a6b6  sub     ecx, 10000h
0x18001a6bc  jz      loc_18001A598
0x18001a6c2  sub     ecx, 1
0x18001a6c5  jz      loc_18001A598
0x18001a6cb  sub     ecx, 2
0x18001a6ce  jz      loc_18001A7DC
0x18001a6d4  sub     ecx, 1
0x18001a6d7  jnz     loc_18001AD88
0x18001a6dd  mov     eax, 91h
0x18001a6e2  jmp     loc_18001A59D
0x18001a6e7  inc     [rsp+rcx*8+198h+var_F4]
0x18001a6ee  mov     eax, [rsp+rcx*8+198h+var_F4]
0x18001a6f5  cmp     eax, [rbx+24h]
0x18001a6f8  ja      loc_18001AB26
0x18001a6fe  lea     rbp, [r13+40h]
0x18001a702  movzx   eax, [rsp+198h+var_168]
0x18001a707  jmp     loc_18001A4C9
0x18001a70c  mov     r12d, [rsp+198h+var_164]
0x18001a711  test    esi, esi
0x18001a713  js      loc_18001AE17
0x18001a719  xor     r10d, r10d
0x18001a71c  cmp     r10d, 16h
0x18001a720  jnb     short loc_18001A791
0x18001a722  mov     r8d, [r13+45Ch]
0x18001a729  cmp     r8d, 10006h
0x18001a730  jnz     loc_18001A961
0x18001a736  movzx   eax, r8w; jumptable 000000018001A97F cases 65538-65541
0x18001a73a  mov     rdx, r14
0x18001a73d  shl     rdx, 7
0x18001a741  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r15+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18001a749  lea     ebx, [r8-10000h]
0x18001a750  mov     r11, r8
0x18001a753  movsxd  rax, r10d
0x18001a756  movsxd  r9, dword ptr [rdx+rax*4+28h]
0x18001a75b  test    r9d, r9d
0x18001a75e  jz      short loc_18001A791
0x18001a760  cmp     r8d, 10006h
0x18001a767  jnz     loc_18001A9C2
0x18001a76d  movzx   eax, r11w; jumptable 000000018001A9D9 cases 2-5
0x18001a771  mov     rdx, r9
0x18001a774  shl     rdx, 7
0x18001a778  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r15+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18001a780  cmp     dword ptr [rdx+18h], 2
0x18001a784  jz      short loc_18001A78C
0x18001a786  cmp     dword ptr [rdx+20h], 0
0x18001a78a  jnz     short loc_18001A795
0x18001a78c  inc     r10d
0x18001a78f  jmp     short loc_18001A71C
0x18001a791  xor     eax, eax
0x18001a793  jmp     short loc_18001A7B0
0x18001a795  xor     ecx, ecx
0x18001a797  cmp     ecx, r12d
0x18001a79a  jb      loc_18001AB3B
0x18001a7a0  mov     r8d, r9d
0x18001a7a3  mov     edx, 80041319h
0x18001a7a8  mov     rcx, r13
0x18001a7ab  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJW4TaskXmlNodeId@@@Z; TaskXmlReader::SetErrorInfo(long,TaskXmlNodeId)
0x18001a7b0  mov     rcx, [rsp+198h+var_48]
0x18001a7b8  xor     rcx, rsp; StackCookie
0x18001a7bb  call    __security_check_cookie
0x18001a7c0  mov     rbx, [rsp+198h+arg_18]
0x18001a7c8  add     rsp, 160h
0x18001a7cf  pop     r15
0x18001a7d1  pop     r14
0x18001a7d3  pop     r13
0x18001a7d5  pop     r12
0x18001a7d7  pop     rdi
0x18001a7d8  pop     rsi
0x18001a7d9  pop     rbp
0x18001a7da  retn
0x18001a7dc  mov     eax, 88h
0x18001a7e1  jmp     loc_18001A59D
0x18001a7e6  lea     eax, [rdx-10000h]; switch 6 cases
0x18001a7ec  cmp     eax, 5
0x18001a7ef  ja      def_18001A802; jumptable 000000018001A802 default case
0x18001a7f5  cdqe
0x18001a7f7  mov     ecx, ds:(jpt_18001A802 - 180000000h)[r15+rax*4]
0x18001a7ff  add     rcx, r15
0x18001a802  jmp     rcx; switch jump
0x18001a808  xor     r8d, r8d; jumptable 000000018001A802 cases 65536,65537
0x18001a80b  movzx   eax, dx
0x18001a80e  mov     rdx, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r15+rax*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x18001a816  lea     r9, ds:5DF38h[rax*8]
0x18001a81e  xchg    ax, ax
0x18001a820  cmp     r8, rdx
0x18001a823  jnb     def_18001A802; jumptable 000000018001A802 default case
0x18001a829  mov     rbx, r8
0x18001a82c  shl     rbx, 7
0x18001a830  add     rbx, [r9+r15]
0x18001a834  cmp     [rbx], edi
0x18001a836  jz      loc_18001A5F6
0x18001a83c  inc     r8
0x18001a83f  jmp     short loc_18001A820
0x18001a841  lea     eax, [rdx-10000h]; switch 6 cases
0x18001a847  cmp     eax, 5
0x18001a84a  ja      def_18001A85D; jumptable 000000018001A85D default case
0x18001a850  cdqe
0x18001a852  mov     ecx, ds:(jpt_18001A85D - 180000000h)[r15+rax*4]
0x18001a85a  add     rcx, r15
0x18001a85d  jmp     rcx; switch jump
0x18001a863  xor     r8d, r8d; jumptable 000000018001A85D cases 65536,65537
0x18001a866  movzx   eax, dx
0x18001a869  mov     rdx, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r15+rax*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x18001a871  lea     r9, ds:5DF38h[rax*8]
0x18001a879  nop     dword ptr [rax+00000000h]
0x18001a880  cmp     r8, rdx
0x18001a883  jnb     def_18001A85D; jumptable 000000018001A85D default case
0x18001a889  mov     rcx, r8
0x18001a88c  shl     rcx, 7
0x18001a890  mov     rax, [r9+r15]
0x18001a894  add     rax, rcx
0x18001a897  cmp     [rax], r14d
0x18001a89a  jz      loc_18001A5C4
0x18001a8a0  inc     r8
0x18001a8a3  jmp     short loc_18001A880
0x18001a8a5  xor     r10d, r10d
0x18001a8a8  nop     dword ptr [rax+rax+00000000h]
0x18001a8b0  cmp     r10d, 16h
0x18001a8b4  jnb     loc_18001A95A
0x18001a8ba  mov     r8d, [r13+45Ch]
0x18001a8c1  cmp     r8d, 10006h
0x18001a8c8  jnz     loc_18001AA30
0x18001a8ce  movzx   eax, r8w; jumptable 000000018001AA4E cases 65538-65541
0x18001a8d2  mov     rdx, r14
0x18001a8d5  shl     rdx, 7
0x18001a8d9  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r15+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18001a8e1  lea     ebp, [r8-10000h]
0x18001a8e8  movsxd  rax, r10d
0x18001a8eb  movsxd  r11, dword ptr [rdx+rax*4+28h]
0x18001a8f0  test    r11d, r11d
0x18001a8f3  jz      short loc_18001A95A
0x18001a8f5  cmp     r8d, 10006h
0x18001a8fc  jnz     loc_18001AA92
0x18001a902  movzx   eax, r8w; jumptable 000000018001AAA5 cases 2-5
0x18001a906  mov     rdx, r11
0x18001a909  shl     rdx, 7
0x18001a90d  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r15+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18001a915  cmp     dword ptr [rdx+18h], 2
0x18001a919  jz      loc_18001ABF7
0x18001a91f  cmp     [rdx+20h], esi
0x18001a922  jnz     short loc_18001A929
0x18001a924  inc     r10d
0x18001a927  jmp     short loc_18001A8B0
0x18001a929  mov     edx, r11d
0x18001a92c  lea     rcx, [r13+45Ch]
0x18001a933  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x18001a938  xor     ecx, ecx
0x18001a93a  mov     [rsp+198h+var_170], ecx; unsigned int
0x18001a93e  mov     [rsp+198h+var_178], rcx; unsigned __int16 *
0x18001a943  mov     r9d, [rax+10h]; unsigned int
0x18001a947  mov     r8, [rax+8]; unsigned __int16 *
0x18001a94b  mov     edx, 80041319h; int
0x18001a950  mov     rcx, r13; this
0x18001a953  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJPEBGK0K@Z; TaskXmlReader::SetErrorInfo(long,ushort const *,ulong,ushort const *,ulong)
0x18001a958  mov     esi, eax
0x18001a95a  mov     eax, esi
0x18001a95c  jmp     loc_18001A7B0
  ... truncated ...
```
