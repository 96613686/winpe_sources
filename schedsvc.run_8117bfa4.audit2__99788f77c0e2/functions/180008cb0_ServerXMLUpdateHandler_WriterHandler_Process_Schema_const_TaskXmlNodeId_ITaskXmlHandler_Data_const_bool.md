# ServerXMLUpdateHandler::WriterHandler::Process(Schema const &,TaskXmlNodeId,ITaskXmlHandler::Data const *,bool)

- ea: `0x180008cb0`
- end: `0x180009644`
- name: `?Process@WriterHandler@ServerXMLUpdateHandler@@UEAAJAEBUSchema@@W4TaskXmlNodeId@@PEBUData@ITaskXmlHandler@@_N@Z`
- size: `2452`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180008cb0`
- `0x180009d60`
- `0x18000a460`
- `0x180042604`
- `0x180042e10`
- `0x180054824`
- `0x18005a2bc`
- `0x1800826e8`
- `0x180082a40`
- `0x180088010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008e44`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008e44`
- `XmlLite!CreateXmlWriter` at `0x180008ece`
- `XmlLite!CreateXmlWriter` at `0x180008ece`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x180008f41`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x180008f41`

## string_xrefs

- `0x180009216`: `xmlns`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ServerXMLUpdateHandler::WriterHandler::Process(__int64 a1, _DWORD *a2, int a3, __int64 a4, char a5)
{
  __int64 v6; // rbx
  __int64 v9; // rbp
  unsigned int v10; // r12d
  __int64 result; // rax
  int v12; // edx
  unsigned __int64 v13; // rdx
  __int64 v14; // rax
  unsigned int *v15; // rdi
  __int64 v16; // rcx
  struct IErrorInfo *v17; // rdx
  int lpVtbl; // eax
  int v19; // r8d
  __int64 *v20; // r8
  int v21; // eax
  struct IErrorInfoVtbl *v22; // rcx
  _QWORD *v23; // r13
  __int64 v24; // rcx
  int *v25; // r13
  HRESULT v26; // edi
  void *v27; // rcx
  void *v28; // rdi
  struct IErrorInfo *v29; // rdx
  __int64 v30; // rcx
  struct IErrorInfo *v31; // rdx
  __int64 v32; // rcx
  struct IErrorInfo *v33; // rdx
  __int64 v34; // rcx
  struct IErrorInfo *v35; // rdx
  __int64 v36; // r10
  int v37; // edx
  const struct SchemaEntry * near *v38; // r8
  struct IErrorInfo *v39; // rdx
  __int64 v40; // r10
  int v41; // edx
  const struct SchemaEntry * near *v42; // r8
  __int64 v43; // rax
  __int64 v44; // rsi
  unsigned int v45; // eax
  __int64 *v46; // r8
  int v47; // eax
  __int64 v48; // rcx
  __int64 v49; // rcx
  unsigned int v50; // eax
  __int64 v51; // rcx
  __int64 v52; // rax
  unsigned __int64 v53; // r8
  const unsigned __int64 near *v54; // r9
  __int64 v55; // r10
  unsigned __int64 v56; // r9
  const unsigned __int64 near *v57; // r10
  const struct SchemaEntry * near **v58; // r11
  unsigned __int64 v59; // r9
  __int64 v60; // rax
  const unsigned __int64 near *v61; // rdx
  unsigned __int64 v62; // r9
  __int64 v63; // rax
  __int64 v64; // r10
  unsigned __int64 v65; // r9
  __int64 v66; // rax
  const unsigned __int64 near *v67; // rdx
  __int64 v68; // r8
  void *ppvObject; // [rsp+30h] [rbp-98h] BYREF
  int *v70; // [rsp+38h] [rbp-90h]
  IXmlWriterOutput *ppOutput; // [rsp+40h] [rbp-88h] BYREF
  __int64 v72; // [rsp+48h] [rbp-80h]
  void **pExceptionObject; // [rsp+50h] [rbp-78h] BYREF
  char v74; // [rsp+58h] [rbp-70h]
  const unsigned __int16 *v75; // [rsp+60h] [rbp-68h]
  __int64 v76; // [rsp+68h] [rbp-60h]
  __int64 v77; // [rsp+70h] [rbp-58h]
  int v78; // [rsp+78h] [rbp-50h]
  __int64 v79; // [rsp+7Ch] [rbp-4Ch]

  v6 = a3;
  v9 = *(_QWORD *)(a1 + 8);
  v10 = 1;
  if ( *(_QWORD *)(v9 + 1048) )
    goto LABEL_2;
  if ( a3 == 1 )
    return 0;
  v23 = HeapAlloc(g_PrivateHeap, 0, 0xA0u);
  if ( !v23 )
  {
    v74 = 0;
    v75 = &qword_1800A8718;
    v76 = 0;
    v77 = 0;
    v78 = 14;
    v79 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  *(_DWORD *)v23 = *a2;
  v24 = *(_QWORD *)(v9 + 1064);
  v23[1] = v24;
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
  v23[2] = 0;
  *((_DWORD *)v23 + 38) = 0;
  std::unique_ptr<TaskXmlWriter>::reset(v9 + 1048, v23);
  v25 = *(int **)(v9 + 1048);
  v70 = v25;
  v72 = (unsigned int)*a2;
  ppvObject = 0;
  v26 = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( v26 < 0 )
    goto LABEL_48;
  v27 = ppvObject;
  v28 = (void *)*((_QWORD *)v25 + 2);
  if ( v28 != ppvObject )
  {
    *((_QWORD *)v25 + 2) = ppvObject;
    if ( v27 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v27 + 8LL))(v27);
      v27 = ppvObject;
    }
    if ( v28 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v28 + 16LL))(v28);
      v27 = ppvObject;
    }
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)v27 + 16LL))(v27);
  ppOutput = 0;
  v26 = CreateXmlWriterOutputWithEncodingName(*((IUnknown **)v70 + 1), 0, L"UTF-16", &ppOutput);
  if ( v26 < 0 )
    goto LABEL_48;
  v30 = *((_QWORD *)v25 + 2);
  if ( !v30 )
    _com_raise_error(-2147467261, v29);
  v26 = (*(__int64 (__fastcall **)(__int64, IXmlWriterOutput *))(*(_QWORD *)v30 + 24LL))(v30, ppOutput);
  ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
  if ( v26 >= 0 )
  {
    v32 = *((_QWORD *)v25 + 2);
    if ( !v32 )
      _com_raise_error(-2147467261, v31);
    v26 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v32 + 40LL))(v32, 1, 1);
    if ( v26 >= 0 )
    {
      v34 = *((_QWORD *)v25 + 2);
      if ( !v34 )
        _com_raise_error(-2147467261, v33);
      v26 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v34 + 208LL))(v34, 0);
      if ( v26 >= 0 )
      {
        v36 = *((_QWORD *)v25 + 2);
        if ( !v36 )
          _com_raise_error(-2147467261, v35);
        v37 = *v70;
        if ( *v70 == 65542 )
        {
LABEL_39:
          v38 = (&Schema::schemaEntries)[(unsigned __int16)v37] + 16;
        }
        else
        {
          switch ( v37 )
          {
            case 65536:
            case 65537:
              v59 = 0;
              v60 = (unsigned __int16)v37;
              v61 = (&Schema::schemaEntriesCount)[(unsigned __int16)v37];
              break;
            case 65538:
            case 65539:
            case 65540:
            case 65541:
              goto LABEL_39;
            default:
              goto LABEL_98;
          }
          while ( v59 < (unsigned __int64)v61 )
          {
            v38 = &(&Schema::schemaEntries)[v60][16 * v59];
            if ( *(_DWORD *)v38 == 1 )
              goto LABEL_40;
            ++v59;
          }
LABEL_98:
          v38 = (const struct SchemaEntry * near *)&qword_1800A1560;
        }
LABEL_40:
        v26 = (*(__int64 (__fastcall **)(_QWORD, const OLECHAR *, const struct SchemaEntry *, unsigned __int16 *const))(*(_QWORD *)v36 + 216LL))(
                *((_QWORD *)v25 + 2),
                &ChannelPath,
                v38[1],
                Schema::namespaceUri);
        if ( v26 >= 0 )
        {
          if ( !(_DWORD)v72 )
            goto LABEL_49;
          v26 = StringCchPrintfW(
                  (unsigned __int16 *)&pExceptionObject,
                  0x16u,
                  L"%d.%d",
                  HIWORD(*v70),
                  (unsigned __int16)*v70);
          if ( v26 >= 0 )
          {
            v40 = *((_QWORD *)v25 + 2);
            if ( !v40 )
              _com_raise_error(-2147467261, v39);
            v41 = *v70;
            if ( *v70 == 65542 )
            {
LABEL_45:
              v42 = (&Schema::schemaEntries)[(unsigned __int16)v41] + 32;
            }
            else
            {
              switch ( v41 )
              {
                case 65536:
                case 65537:
                  v65 = 0;
                  v66 = (unsigned __int16)v41;
                  v67 = (&Schema::schemaEntriesCount)[(unsigned __int16)v41];
                  break;
                case 65538:
                case 65539:
                case 65540:
                case 65541:
                  goto LABEL_45;
                default:
                  goto LABEL_100;
              }
              while ( v65 < (unsigned __int64)v67 )
              {
                v42 = &(&Schema::schemaEntries)[v66][16 * v65];
                if ( *(_DWORD *)v42 == 2 )
                  goto LABEL_46;
                ++v65;
              }
LABEL_100:
              v42 = (const struct SchemaEntry * near *)&qword_1800A1560;
            }
LABEL_46:
            v26 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, const struct SchemaEntry *, _QWORD, void ***))(*(_QWORD *)v40 + 56LL))(
                    v40,
                    &ChannelPath,
                    v42[1],
                    0,
                    &pExceptionObject);
            if ( v26 >= 0 )
            {
              v52 = _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(v25 + 4);
              v26 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, const unsigned __int16 *, _QWORD, unsigned __int16 *const))(*(_QWORD *)v52 + 56LL))(
                      v52,
                      &ChannelPath,
                      L"xmlns",
                      0,
                      Schema::namespaceUri);
            }
          }
        }
      }
    }
LABEL_48:
    if ( v26 >= 0 )
      goto LABEL_49;
  }
  if ( *(int *)(v9 + 1072) >= 0 )
    *(_DWORD *)(v9 + 1072) = v26;
LABEL_49:
  result = *(unsigned int *)(v9 + 1072);
  if ( (int)result < 0 )
    return result;
LABEL_2:
  if ( (_DWORD)v6 == 2 )
    return 0;
  if ( !a4 )
  {
    v17 = *(struct IErrorInfo **)(*(_QWORD *)(a1 + 8) + 1048LL);
    lpVtbl = (int)v17[19].lpVtbl;
    if ( lpVtbl )
    {
      LODWORD(v17[19].lpVtbl) = lpVtbl + 1;
    }
    else
    {
      v19 = (int)v17->lpVtbl;
      if ( LODWORD(v17->lpVtbl) == 65542 )
      {
LABEL_14:
        v20 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v19][16 * v6];
      }
      else
      {
        switch ( v19 )
        {
          case 65536:
          case 65537:
            v56 = 0;
            v57 = (&Schema::schemaEntriesCount)[(unsigned __int16)v19];
            v58 = &(&Schema::schemaEntries)[(unsigned __int16)v19];
            break;
          case 65538:
          case 65539:
          case 65540:
          case 65541:
            goto LABEL_14;
          default:
            goto LABEL_104;
        }
        while ( v56 < (unsigned __int64)v57 )
        {
          v20 = (__int64 *)&(*v58)[16 * v56];
          v21 = *(_DWORD *)v20;
          if ( *(_DWORD *)v20 == (_DWORD)v6 )
            goto LABEL_16;
          ++v56;
        }
LABEL_104:
        v20 = &qword_1800A1560;
      }
      v21 = *(_DWORD *)v20;
LABEL_16:
      if ( v21 )
      {
        v22 = v17[2].lpVtbl;
        if ( !v22 )
          _com_raise_error(-2147467261, v17);
        return (*((unsigned int (__fastcall **)(struct IErrorInfoVtbl *, const OLECHAR *, __int64, unsigned __int16 *const))v22->QueryInterface
                + 27))(
                 v22,
                 &ChannelPath,
                 v20[1],
                 Schema::namespaceUri);
      }
      else
      {
        LODWORD(v17[19].lpVtbl) = 1;
      }
    }
    return v10;
  }
  v12 = *a2;
  if ( *a2 == 65542 )
  {
LABEL_7:
    v13 = (unsigned __int64)&(&Schema::schemaEntries)[(unsigned __int16)v12][16 * v6];
  }
  else
  {
    switch ( v12 )
    {
      case 65536:
      case 65537:
        v53 = 0;
        v54 = (&Schema::schemaEntriesCount)[(unsigned __int16)v12];
        v55 = 8LL * (unsigned __int16)v12 + 575136;
        break;
      case 65538:
      case 65539:
      case 65540:
      case 65541:
        goto LABEL_7;
      default:
        goto LABEL_107;
    }
    while ( v53 < (unsigned __int64)v54 )
    {
      v13 = *(_QWORD *)((char *)&_ImageBase + v55) + (v53 << 7);
      if ( *(_DWORD *)v13 == (_DWORD)v6 )
        goto LABEL_8;
      ++v53;
    }
LABEL_107:
    v13 = (unsigned __int64)&qword_1800A1560;
  }
LABEL_8:
  v14 = *(_QWORD *)(a1 + 8);
  if ( *(_DWORD *)(v13 + 24) == 2 )
  {
    v68 = *(_QWORD *)(a4 + 48);
    if ( v68 )
      v68 = *(_QWORD *)(v68 + 8);
    return TaskXmlWriter::WriteAttribute(*(_QWORD *)(v14 + 1048), (unsigned int)v6, v68);
  }
  v15 = *(unsigned int **)(v14 + 1048);
  if ( a5 )
  {
    v16 = *((_QWORD *)v15 + 2);
    if ( !v16 )
      _com_raise_error(-2147467261, (struct IErrorInfo *)v13);
    return (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v16 + 224LL))(
             v16,
             *(_QWORD *)(*(_QWORD *)(a4 + 48) + 8LL));
  }
  v43 = *(_QWORD *)(a4 + 48);
  if ( (_DWORD)v6 == 96 )
    return TaskXmlWriter::ElementCData(v15, 96);
  if ( v43 )
    v44 = *(_QWORD *)(v43 + 8);
  else
    v44 = 0;
  v45 = v15[38];
  if ( v45 )
  {
    v15[38] = v45 + 1;
    goto LABEL_65;
  }
  v13 = *v15;
  if ( (_DWORD)v13 == 65542 )
  {
LABEL_56:
    v46 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v13][16 * v6];
  }
  else
  {
    switch ( (int)v13 )
    {
      case 65536:
      case 65537:
        v62 = 0;
        v63 = (unsigned __int16)v13;
        v13 = (unsigned __int64)(&Schema::schemaEntriesCount)[(unsigned __int16)v13];
        v64 = 8 * v63 + 575136;
        break;
      case 65538:
      case 65539:
      case 65540:
      case 65541:
        goto LABEL_56;
      default:
        goto LABEL_115;
    }
    while ( v62 < v13 )
    {
      v46 = (__int64 *)(*(_QWORD *)((char *)&_ImageBase + v64) + (v62 << 7));
      v47 = *(_DWORD *)v46;
      if ( *(_DWORD *)v46 == (_DWORD)v6 )
        goto LABEL_58;
      ++v62;
    }
LABEL_115:
    v46 = &qword_1800A1560;
  }
  v47 = *(_DWORD *)v46;
LABEL_58:
  if ( !v47 )
  {
    v15[38] = 1;
LABEL_65:
    v50 = v15[38];
    if ( v50 )
    {
      v15[38] = v50 - 1;
      return 1;
    }
    else
    {
      v51 = *((_QWORD *)v15 + 2);
      if ( !v51 )
        _com_raise_error(-2147467261, (struct IErrorInfo *)v13);
      return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v51 + 120LL))(v51);
    }
  }
  v48 = *((_QWORD *)v15 + 2);
  if ( !v48 )
    _com_raise_error(-2147467261, (struct IErrorInfo *)v13);
  result = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, __int64, unsigned __int16 *const))(*(_QWORD *)v48 + 216LL))(
             v48,
             &ChannelPath,
             v46[1],
             Schema::namespaceUri);
  if ( (int)result >= 0 )
  {
    if ( (_DWORD)result || !v44 )
      goto LABEL_65;
    v49 = *((_QWORD *)v15 + 2);
    if ( !v49 )
      _com_raise_error(-2147467261, (struct IErrorInfo *)v13);
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 224LL))(v49, v44);
    if ( (int)result >= 0 )
      goto LABEL_65;
  }
  return result;
}

```

## disassembly

```asm
0x180008cb0  mov     [rsp+arg_8], rbx
0x180008cb5  push    rbp
0x180008cb6  push    rsi
0x180008cb7  push    rdi
0x180008cb8  push    r12
0x180008cba  push    r13
0x180008cbc  push    r14
0x180008cbe  push    r15
0x180008cc0  sub     rsp, 90h
0x180008cc7  mov     rax, cs:__security_cookie
0x180008cce  xor     rax, rsp
0x180008cd1  mov     [rsp+0C8h+var_40], rax
0x180008cd9  mov     r15, r9
0x180008cdc  movsxd  rbx, r8d
0x180008cdf  mov     r14, rdx
0x180008ce2  mov     rsi, rcx
0x180008ce5  mov     rbp, [rcx+8]
0x180008ce9  mov     r12d, 1
0x180008cef  lea     r11, __ImageBase
0x180008cf6  cmp     qword ptr [rbp+418h], 0
0x180008cfe  jz      loc_180008E2C
0x180008d04  cmp     ebx, 2
0x180008d07  jnz     short loc_180008D37
0x180008d09  xor     eax, eax
0x180008d0b  mov     rcx, [rsp+0C8h+var_40]
0x180008d13  xor     rcx, rsp; StackCookie
0x180008d16  call    __security_check_cookie
0x180008d1b  mov     rbx, [rsp+0C8h+arg_8]
0x180008d23  add     rsp, 90h
0x180008d2a  pop     r15
0x180008d2c  pop     r14
0x180008d2e  pop     r13
0x180008d30  pop     r12
0x180008d32  pop     rdi
0x180008d33  pop     rsi
0x180008d34  pop     rbp
0x180008d35  retn
0x180008d37  test    r15, r15
0x180008d3a  jz      short loc_180008DA9
0x180008d3c  mov     edx, [r14]
0x180008d3f  cmp     edx, 10006h
0x180008d45  jnz     loc_180009237
0x180008d4b  movzx   eax, dx; jumptable 0000000180009253 cases 65538-65541
0x180008d4e  mov     rdx, rbx
0x180008d51  shl     rdx, 7
0x180008d55  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r11+rax*8]; struct IErrorInfo *
0x180008d5d  mov     rax, [rsi+8]
0x180008d61  cmp     dword ptr [rdx+18h], 2
0x180008d65  jz      loc_180009522
0x180008d6b  mov     rdi, [rax+418h]
0x180008d72  cmp     [rsp+0C8h+arg_20], 0
0x180008d7a  jz      loc_180009112
0x180008d80  mov     rcx, [rdi+10h]
0x180008d84  test    rcx, rcx
0x180008d87  jz      loc_180009542
0x180008d8d  mov     rax, [rcx]
0x180008d90  mov     rdx, [r15+30h]
0x180008d94  mov     rdx, [rdx+8]
0x180008d98  mov     rax, [rax+0E0h]
0x180008d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008da4  jmp     loc_180008D0B
0x180008da9  mov     rax, [rsi+8]
0x180008dad  mov     rdx, [rax+418h]; struct IErrorInfo *
0x180008db4  mov     eax, [rdx+98h]
0x180008dba  test    eax, eax
0x180008dbc  jnz     loc_1800094E6
0x180008dc2  mov     r8d, [rdx]
0x180008dc5  cmp     r8d, 10006h
0x180008dcc  jnz     loc_180009290
0x180008dd2  movzx   eax, r8w; jumptable 00000001800092AD cases 65538-65541
0x180008dd6  mov     rcx, rbx
0x180008dd9  shl     rcx, 7
0x180008ddd  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r11+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180008de5  add     r8, rcx
0x180008de8  mov     eax, [r8]
0x180008deb  test    eax, eax
0x180008ded  jz      loc_1800094FF
0x180008df3  mov     rcx, [rdx+10h]
0x180008df7  test    rcx, rcx
0x180008dfa  jz      loc_18000950B
0x180008e00  mov     rax, [rcx]
0x180008e03  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180008e0a  mov     r8, [r8+8]
0x180008e0e  lea     rdx, ChannelPath
0x180008e15  mov     rax, [rax+0D8h]
0x180008e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e21  mov     r12d, eax
0x180008e24  mov     eax, r12d
0x180008e27  jmp     loc_180008D0B
0x180008e2c  cmp     ebx, r12d
0x180008e2f  jz      loc_180008D09
0x180008e35  xor     edx, edx; dwFlags
0x180008e37  mov     r8d, 0A0h; dwBytes
0x180008e3d  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180008e44  call    cs:__imp_HeapAlloc
0x180008e4b  nop     dword ptr [rax+rax+00h]
0x180008e50  mov     r13, rax
0x180008e53  test    rax, rax
0x180008e56  jz      loc_180009414
0x180008e5c  mov     eax, [r14]
0x180008e5f  mov     [r13+0], eax
0x180008e63  mov     rcx, [rbp+428h]
0x180008e6a  mov     [r13+8], rcx
0x180008e6e  test    rcx, rcx
0x180008e71  jz      short loc_180008E80
0x180008e73  mov     rax, [rcx]
0x180008e76  mov     rax, [rax+8]
0x180008e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e7f  nop
0x180008e80  mov     qword ptr [r13+10h], 0
0x180008e88  mov     dword ptr [r13+98h], 0
0x180008e93  mov     rdx, r13
0x180008e96  lea     rcx, [rbp+418h]
0x180008e9d  call    ?reset@?$unique_ptr@VTaskXmlWriter@@U?$default_delete@VTaskXmlWriter@@@std@@@std@@QEAAXPEAVTaskXmlWriter@@@Z; std::unique_ptr<TaskXmlWriter>::reset(TaskXmlWriter *)
0x180008ea2  mov     r13, [rbp+418h]
0x180008ea9  mov     [rsp+0C8h+var_90], r13
0x180008eae  mov     eax, [r14]
0x180008eb1  mov     [rsp+0C8h+var_80], rax
0x180008eb6  mov     [rsp+0C8h+ppvObject], 0
0x180008ebf  xor     r8d, r8d; pMalloc
0x180008ec2  lea     rdx, [rsp+0C8h+ppvObject]; ppvObject
0x180008ec7  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180008ece  call    cs:__imp_CreateXmlWriter
0x180008ed5  nop     dword ptr [rax+rax+00h]
0x180008eda  mov     edi, eax
0x180008edc  test    eax, eax
0x180008ede  js      loc_1800090F0
0x180008ee4  mov     rcx, [rsp+0C8h+ppvObject]
0x180008ee9  mov     rdi, [r13+10h]
0x180008eed  cmp     rdi, rcx
0x180008ef0  jz      short loc_180008F15
0x180008ef2  mov     [r13+10h], rcx
0x180008ef6  test    rcx, rcx
0x180008ef9  jz      short loc_180008F0C
0x180008efb  mov     rax, [rcx]
0x180008efe  mov     rax, [rax+8]
0x180008f02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f07  mov     rcx, [rsp+0C8h+ppvObject]
0x180008f0c  test    rdi, rdi
0x180008f0f  jnz     loc_180009466
0x180008f15  mov     rax, [rcx]
0x180008f18  mov     rax, [rax+10h]
0x180008f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f21  mov     [rsp+0C8h+ppOutput], 0
0x180008f2a  lea     r9, [rsp+0C8h+ppOutput]; ppOutput
0x180008f2f  lea     r8, pwszEncodingName; "UTF-16"
0x180008f36  xor     edx, edx; pMalloc
0x180008f38  mov     rcx, [rsp+0C8h+var_90]
0x180008f3d  mov     rcx, [rcx+8]; pOutputStream
0x180008f41  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x180008f48  nop     dword ptr [rax+rax+00h]
0x180008f4d  mov     edi, eax
0x180008f4f  test    eax, eax
0x180008f51  js      loc_1800090F0
0x180008f57  mov     rcx, [r13+10h]
0x180008f5b  test    rcx, rcx
0x180008f5e  jz      loc_18000947F
0x180008f64  mov     rax, [rcx]
0x180008f67  mov     rdx, [rsp+0C8h+ppOutput]
0x180008f6c  mov     rax, [rax+18h]
0x180008f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f75  mov     edi, eax
0x180008f77  mov     rcx, [rsp+0C8h+ppOutput]
0x180008f7c  mov     rax, [rcx]
0x180008f7f  mov     rax, [rax+10h]
0x180008f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f88  test    edi, edi
0x180008f8a  js      loc_1800094CE
0x180008f90  mov     rcx, [r13+10h]
0x180008f94  test    rcx, rcx
0x180008f97  jz      loc_18000948A
0x180008f9d  mov     rax, [rcx]
0x180008fa0  mov     r8, r12
0x180008fa3  mov     edx, r12d
0x180008fa6  mov     rax, [rax+28h]
0x180008faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008faf  mov     edi, eax
0x180008fb1  test    eax, eax
0x180008fb3  js      loc_1800090F0
0x180008fb9  mov     rcx, [r13+10h]
0x180008fbd  test    rcx, rcx
0x180008fc0  jz      loc_180009495
0x180008fc6  mov     rax, [rcx]
0x180008fc9  xor     edx, edx
0x180008fcb  mov     rax, [rax+0D0h]
0x180008fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fd7  mov     edi, eax
0x180008fd9  test    eax, eax
0x180008fdb  js      loc_1800090F0
0x180008fe1  mov     r10, [r13+10h]
0x180008fe5  test    r10, r10
0x180008fe8  jz      loc_1800094A0
0x180008fee  mov     rax, [r10]
0x180008ff1  mov     r11, [rax+0D8h]
0x180008ff8  mov     rax, [rsp+0C8h+var_90]
0x180008ffd  mov     edx, [rax]
0x180008fff  cmp     edx, 10006h
0x180009005  jnz     loc_1800092F0
0x18000900b  lea     r8, __ImageBase
0x180009012  movzx   eax, dx; jumptable 0000000180009313 cases 65538-65541
0x180009015  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r8+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18000901d  sub     r8, 0FFFFFFFFFFFFFF80h
0x180009021  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180009028  mov     r8, [r8+8]
0x18000902c  lea     rdx, ChannelPath
0x180009033  mov     rcx, r10
0x180009036  mov     rax, r11
0x180009039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000903e  mov     edi, eax
0x180009040  test    eax, eax
0x180009042  js      loc_1800090F0
0x180009048  cmp     dword ptr [rsp+0C8h+var_80], 0
0x18000904d  jz      loc_1800090F8
0x180009053  mov     rax, [rsp+0C8h+var_90]
0x180009058  mov     r9d, [rax]
0x18000905b  movzx   eax, r9w
0x18000905f  shr     r9d, 10h
0x180009063  mov     dword ptr [rsp+0C8h+var_A8], eax
0x180009067  lea     r8, aDD; "%d.%d"
0x18000906e  mov     edx, 16h; unsigned __int64
0x180009073  lea     rcx, [rsp+0C8h+pExceptionObject]; unsigned __int16 *
0x180009078  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000907d  mov     edi, eax
0x18000907f  test    eax, eax
0x180009081  js      short loc_1800090F0
0x180009083  mov     r10, [r13+10h]
0x180009087  test    r10, r10
0x18000908a  jz      loc_1800094B7
0x180009090  mov     rax, [r10]
0x180009093  mov     r11, [rax+38h]
0x180009097  mov     rax, [rsp+0C8h+var_90]
0x18000909c  mov     edx, [rax]
0x18000909e  cmp     edx, 10006h
0x1800090a4  jnz     loc_1800093B0
0x1800090aa  lea     r8, __ImageBase
0x1800090b1  movzx   eax, dx; jumptable 00000001800093D3 cases 65538-65541
0x1800090b4  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r8+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x1800090bc  add     r8, 100h
0x1800090c3  lea     rax, [rsp+0C8h+pExceptionObject]
0x1800090c8  mov     [rsp+0C8h+var_A8], rax
0x1800090cd  xor     r9d, r9d
0x1800090d0  mov     r8, [r8+8]
0x1800090d4  lea     rdx, ChannelPath
0x1800090db  mov     rcx, r10
0x1800090de  mov     rax, r11
0x1800090e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090e6  mov     edi, eax
0x1800090e8  test    eax, eax
0x1800090ea  jns     loc_1800091F8
0x1800090f0  test    edi, edi
0x1800090f2  js      loc_1800094CE
0x1800090f8  mov     eax, [rbp+430h]
0x1800090fe  test    eax, eax
0x180009100  js      loc_180008D0B
0x180009106  lea     r11, __ImageBase
0x18000910d  jmp     loc_180008D04
0x180009112  mov     rax, [r15+30h]
0x180009116  cmp     ebx, 60h ; '`'
0x180009119  jz      loc_18000954D
0x18000911f  test    rax, rax
0x180009122  jz      loc_18000956D
0x180009128  mov     rsi, [rax+8]
0x18000912c  mov     eax, [rdi+98h]
0x180009132  test    eax, eax
0x180009134  jnz     loc_180009574
0x18000913a  mov     edx, [rdi]; struct IErrorInfo *
0x18000913c  cmp     edx, 10006h
0x180009142  jnz     loc_180009354
0x180009148  movzx   eax, dx; jumptable 0000000180009370 cases 65538-65541
0x18000914b  mov     rcx, rbx
0x18000914e  shl     rcx, 7
0x180009152  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r11+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18000915a  add     r8, rcx
0x18000915d  mov     eax, [r8]
0x180009160  test    eax, eax
0x180009162  jz      loc_18000958D
0x180009168  mov     rcx, [rdi+10h]
0x18000916c  test    rcx, rcx
0x18000916f  jz      loc_180009599
0x180009175  mov     rax, [rcx]
0x180009178  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x18000917f  mov     r8, [r8+8]
0x180009183  lea     rdx, ChannelPath
0x18000918a  mov     rax, [rax+0D8h]
0x180009191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009196  test    eax, eax
0x180009198  js      loc_180008D0B
0x18000919e  jnz     short loc_1800091CC
0x1800091a0  test    rsi, rsi
0x1800091a3  jz      short loc_1800091CC
0x1800091a5  mov     rcx, [rdi+10h]
0x1800091a9  test    rcx, rcx
0x1800091ac  jz      loc_1800095A4
0x1800091b2  mov     rax, [rcx]
0x1800091b5  mov     rdx, rsi
0x1800091b8  mov     rax, [rax+0E0h]
0x1800091bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091c4  test    eax, eax
0x1800091c6  js      loc_180008D0B
0x1800091cc  mov     eax, [rdi+98h]
  ... truncated ...
```
