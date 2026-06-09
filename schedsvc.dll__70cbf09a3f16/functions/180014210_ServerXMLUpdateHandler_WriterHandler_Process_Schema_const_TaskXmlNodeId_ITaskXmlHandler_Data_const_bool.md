# ServerXMLUpdateHandler::WriterHandler::Process(Schema const &,TaskXmlNodeId,ITaskXmlHandler::Data const *,bool)

- ea: `0x180014210`
- end: `0x180014b7c`
- name: `?Process@WriterHandler@ServerXMLUpdateHandler@@UEAAJAEBUSchema@@W4TaskXmlNodeId@@PEBUData@ITaskXmlHandler@@_N@Z`
- size: `2412`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180014210`
- `0x180015740`
- `0x180016160`
- `0x180016abc`
- `0x1800409a0`
- `0x180052118`
- `0x18005790c`
- `0x18007e3a4`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800143a3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800143a3`
- `XmlLite!CreateXmlWriter` at `0x180014427`
- `XmlLite!CreateXmlWriter` at `0x180014427`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x180014494`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x180014494`

## string_xrefs

- `0x180014763`: `xmlns`

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
  struct IErrorInfo *v43; // rdx
  __int64 v44; // rax
  __int64 v45; // rsi
  unsigned int v46; // eax
  __int64 *v47; // r8
  int v48; // eax
  __int64 v49; // rcx
  __int64 v50; // rcx
  unsigned int v51; // eax
  __int64 v52; // rcx
  __int64 v53; // rax
  unsigned __int64 v54; // r8
  const unsigned __int64 near *v55; // r9
  __int64 v56; // r10
  unsigned __int64 v57; // r9
  const unsigned __int64 near *v58; // r10
  const struct SchemaEntry * near **v59; // r11
  unsigned __int64 v60; // r9
  __int64 v61; // rax
  const unsigned __int64 near *v62; // rdx
  unsigned __int64 v63; // r9
  __int64 v64; // rax
  __int64 v65; // r10
  unsigned __int64 v66; // r9
  __int64 v67; // rax
  const unsigned __int64 near *v68; // rdx
  __int64 v69; // r8
  void *ppvObject; // [rsp+30h] [rbp-98h] BYREF
  int *v71; // [rsp+38h] [rbp-90h]
  IXmlWriterOutput *ppOutput; // [rsp+40h] [rbp-88h] BYREF
  __int64 v73; // [rsp+48h] [rbp-80h]
  void **pExceptionObject; // [rsp+50h] [rbp-78h] BYREF
  char v75; // [rsp+58h] [rbp-70h]
  const unsigned __int16 *v76; // [rsp+60h] [rbp-68h]
  __int64 v77; // [rsp+68h] [rbp-60h]
  __int64 v78; // [rsp+70h] [rbp-58h]
  int v79; // [rsp+78h] [rbp-50h]
  __int64 v80; // [rsp+7Ch] [rbp-4Ch]

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
    v75 = 0;
    v76 = &qword_1800A4718;
    v77 = 0;
    v78 = 0;
    v79 = 14;
    v80 = -1;
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
  v71 = v25;
  v73 = (unsigned int)*a2;
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
  v26 = CreateXmlWriterOutputWithEncodingName(*((IUnknown **)v71 + 1), 0, L"UTF-16", &ppOutput);
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
        v37 = *v71;
        if ( *v71 == 65542 )
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
              v60 = 0;
              v61 = (unsigned __int16)v37;
              v62 = (&Schema::schemaEntriesCount)[(unsigned __int16)v37];
              break;
            case 65538:
            case 65539:
            case 65540:
            case 65541:
              goto LABEL_39;
            default:
              goto LABEL_98;
          }
          while ( v60 < (unsigned __int64)v62 )
          {
            v38 = &(&Schema::schemaEntries)[v61][16 * v60];
            if ( *(_DWORD *)v38 == 1 )
              goto LABEL_40;
            ++v60;
          }
LABEL_98:
          v38 = (const struct SchemaEntry * near *)&qword_18009D560;
        }
LABEL_40:
        v26 = (*(__int64 (__fastcall **)(_QWORD, const OLECHAR *, const struct SchemaEntry *, unsigned __int16 *const))(*(_QWORD *)v36 + 216LL))(
                *((_QWORD *)v25 + 2),
                &ChannelPath,
                v38[1],
                Schema::namespaceUri);
        if ( v26 >= 0 )
        {
          if ( !(_DWORD)v73 )
            goto LABEL_49;
          v26 = StringCchPrintfW(
                  (unsigned __int16 *)&pExceptionObject,
                  0x16u,
                  L"%d.%d",
                  HIWORD(*v71),
                  (unsigned __int16)*v71);
          if ( v26 >= 0 )
          {
            v40 = *((_QWORD *)v25 + 2);
            if ( !v40 )
              _com_raise_error(-2147467261, v39);
            v41 = *v71;
            if ( *v71 == 65542 )
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
                  v66 = 0;
                  v67 = (unsigned __int16)v41;
                  v68 = (&Schema::schemaEntriesCount)[(unsigned __int16)v41];
                  break;
                case 65538:
                case 65539:
                case 65540:
                case 65541:
                  goto LABEL_45;
                default:
                  goto LABEL_100;
              }
              while ( v66 < (unsigned __int64)v68 )
              {
                v42 = &(&Schema::schemaEntries)[v67][16 * v66];
                if ( *(_DWORD *)v42 == 2 )
                  goto LABEL_46;
                ++v66;
              }
LABEL_100:
              v42 = (const struct SchemaEntry * near *)&qword_18009D560;
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
              v53 = _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(
                      (__int64 *)v25 + 2,
                      v43);
              v26 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, const unsigned __int16 *, _QWORD, unsigned __int16 *const))(*(_QWORD *)v53 + 56LL))(
                      v53,
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
            v57 = 0;
            v58 = (&Schema::schemaEntriesCount)[(unsigned __int16)v19];
            v59 = &(&Schema::schemaEntries)[(unsigned __int16)v19];
            break;
          case 65538:
          case 65539:
          case 65540:
          case 65541:
            goto LABEL_14;
          default:
            goto LABEL_104;
        }
        while ( v57 < (unsigned __int64)v58 )
        {
          v20 = (__int64 *)&(*v59)[16 * v57];
          v21 = *(_DWORD *)v20;
          if ( *(_DWORD *)v20 == (_DWORD)v6 )
            goto LABEL_16;
          ++v57;
        }
LABEL_104:
        v20 = &qword_18009D560;
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
        v54 = 0;
        v55 = (&Schema::schemaEntriesCount)[(unsigned __int16)v12];
        v56 = 8LL * (unsigned __int16)v12 + 558752;
        break;
      case 65538:
      case 65539:
      case 65540:
      case 65541:
        goto LABEL_7;
      default:
        goto LABEL_107;
    }
    while ( v54 < (unsigned __int64)v55 )
    {
      v13 = *(_QWORD *)((char *)&_ImageBase + v56) + (v54 << 7);
      if ( *(_DWORD *)v13 == (_DWORD)v6 )
        goto LABEL_8;
      ++v54;
    }
LABEL_107:
    v13 = (unsigned __int64)&qword_18009D560;
  }
LABEL_8:
  v14 = *(_QWORD *)(a1 + 8);
  if ( *(_DWORD *)(v13 + 24) == 2 )
  {
    v69 = *(_QWORD *)(a4 + 48);
    if ( v69 )
      v69 = *(_QWORD *)(v69 + 8);
    return TaskXmlWriter::WriteAttribute(*(_QWORD *)(v14 + 1048), (unsigned int)v6, v69);
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
  v44 = *(_QWORD *)(a4 + 48);
  if ( (_DWORD)v6 == 96 )
    return TaskXmlWriter::ElementCData(v15, 96);
  if ( v44 )
    v45 = *(_QWORD *)(v44 + 8);
  else
    v45 = 0;
  v46 = v15[38];
  if ( v46 )
  {
    v15[38] = v46 + 1;
    goto LABEL_65;
  }
  v13 = *v15;
  if ( (_DWORD)v13 == 65542 )
  {
LABEL_56:
    v47 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v13][16 * v6];
  }
  else
  {
    switch ( (int)v13 )
    {
      case 65536:
      case 65537:
        v63 = 0;
        v64 = (unsigned __int16)v13;
        v13 = (unsigned __int64)(&Schema::schemaEntriesCount)[(unsigned __int16)v13];
        v65 = 8 * v64 + 558752;
        break;
      case 65538:
      case 65539:
      case 65540:
      case 65541:
        goto LABEL_56;
      default:
        goto LABEL_115;
    }
    while ( v63 < v13 )
    {
      v47 = (__int64 *)(*(_QWORD *)((char *)&_ImageBase + v65) + (v63 << 7));
      v48 = *(_DWORD *)v47;
      if ( *(_DWORD *)v47 == (_DWORD)v6 )
        goto LABEL_58;
      ++v63;
    }
LABEL_115:
    v47 = &qword_18009D560;
  }
  v48 = *(_DWORD *)v47;
LABEL_58:
  if ( !v48 )
  {
    v15[38] = 1;
LABEL_65:
    v51 = v15[38];
    if ( v51 )
    {
      v15[38] = v51 - 1;
      return 1;
    }
    else
    {
      v52 = *((_QWORD *)v15 + 2);
      if ( !v52 )
        _com_raise_error(-2147467261, (struct IErrorInfo *)v13);
      return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v52 + 120LL))(v52);
    }
  }
  v49 = *((_QWORD *)v15 + 2);
  if ( !v49 )
    _com_raise_error(-2147467261, (struct IErrorInfo *)v13);
  result = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, __int64, unsigned __int16 *const))(*(_QWORD *)v49 + 216LL))(
             v49,
             &ChannelPath,
             v47[1],
             Schema::namespaceUri);
  if ( (int)result >= 0 )
  {
    if ( (_DWORD)result || !v45 )
      goto LABEL_65;
    v50 = *((_QWORD *)v15 + 2);
    if ( !v50 )
      _com_raise_error(-2147467261, (struct IErrorInfo *)v13);
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v50 + 224LL))(v50, v45);
    if ( (int)result >= 0 )
      goto LABEL_65;
  }
  return result;
}

```

## disassembly

```asm
0x180014210  mov     [rsp+arg_8], rbx
0x180014215  push    rbp
0x180014216  push    rsi
0x180014217  push    rdi
0x180014218  push    r12
0x18001421a  push    r13
0x18001421c  push    r14
0x18001421e  push    r15
0x180014220  sub     rsp, 90h
0x180014227  mov     rax, cs:__security_cookie
0x18001422e  xor     rax, rsp
0x180014231  mov     [rsp+0C8h+var_40], rax
0x180014239  mov     r15, r9
0x18001423c  movsxd  rbx, r8d
0x18001423f  mov     r14, rdx
0x180014242  mov     rsi, rcx
0x180014245  mov     rbp, [rcx+8]
0x180014249  mov     r12d, 1
0x18001424f  lea     r11, __ImageBase
0x180014256  cmp     qword ptr [rbp+418h], 0
0x18001425e  jz      loc_18001438B
0x180014264  cmp     ebx, 2
0x180014267  jnz     short loc_180014296
0x180014269  xor     eax, eax
0x18001426b  mov     rcx, [rsp+0C8h+var_40]
0x180014273  xor     rcx, rsp; StackCookie
0x180014276  call    __security_check_cookie
0x18001427b  mov     rbx, [rsp+0C8h+arg_8]
0x180014283  add     rsp, 90h
0x18001428a  pop     r15
0x18001428c  pop     r14
0x18001428e  pop     r13
0x180014290  pop     r12
0x180014292  pop     rdi
0x180014293  pop     rsi
0x180014294  pop     rbp
0x180014295  retn
0x180014296  test    r15, r15
0x180014299  jz      short loc_180014308
0x18001429b  mov     edx, [r14]
0x18001429e  cmp     edx, 10006h
0x1800142a4  jnz     loc_180014784
0x1800142aa  movzx   eax, dx; jumptable 00000001800147A0 cases 65538-65541
0x1800142ad  mov     rdx, rbx
0x1800142b0  shl     rdx, 7
0x1800142b4  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r11+rax*8]; struct IErrorInfo *
0x1800142bc  mov     rax, [rsi+8]
0x1800142c0  cmp     dword ptr [rdx+18h], 2
0x1800142c4  jz      loc_180014A5B
0x1800142ca  mov     rdi, [rax+418h]
0x1800142d1  cmp     [rsp+0C8h+arg_20], 0
0x1800142d9  jz      loc_18001465F
0x1800142df  mov     rcx, [rdi+10h]
0x1800142e3  test    rcx, rcx
0x1800142e6  jz      loc_180014A7B
0x1800142ec  mov     rax, [rcx]
0x1800142ef  mov     rdx, [r15+30h]
0x1800142f3  mov     rdx, [rdx+8]
0x1800142f7  mov     rax, [rax+0E0h]
0x1800142fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014303  jmp     loc_18001426B
0x180014308  mov     rax, [rsi+8]
0x18001430c  mov     rdx, [rax+418h]; struct IErrorInfo *
0x180014313  mov     eax, [rdx+98h]
0x180014319  test    eax, eax
0x18001431b  jnz     loc_180014A1F
0x180014321  mov     r8d, [rdx]
0x180014324  cmp     r8d, 10006h
0x18001432b  jnz     loc_1800147D9
0x180014331  movzx   eax, r8w; jumptable 00000001800147F6 cases 65538-65541
0x180014335  mov     rcx, rbx
0x180014338  shl     rcx, 7
0x18001433c  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r11+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180014344  add     r8, rcx
0x180014347  mov     eax, [r8]
0x18001434a  test    eax, eax
0x18001434c  jz      loc_180014A38
0x180014352  mov     rcx, [rdx+10h]
0x180014356  test    rcx, rcx
0x180014359  jz      loc_180014A44
0x18001435f  mov     rax, [rcx]
0x180014362  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180014369  mov     r8, [r8+8]
0x18001436d  lea     rdx, ChannelPath
0x180014374  mov     rax, [rax+0D8h]
0x18001437b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014380  mov     r12d, eax
0x180014383  mov     eax, r12d
0x180014386  jmp     loc_18001426B
0x18001438b  cmp     ebx, r12d
0x18001438e  jz      loc_180014269
0x180014394  xor     edx, edx; dwFlags
0x180014396  mov     r8d, 0A0h; dwBytes
0x18001439c  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800143a3  call    cs:__imp_HeapAlloc
0x1800143a9  mov     r13, rax
0x1800143ac  test    rax, rax
0x1800143af  jz      loc_18001494D
0x1800143b5  mov     eax, [r14]
0x1800143b8  mov     [r13+0], eax
0x1800143bc  mov     rcx, [rbp+428h]
0x1800143c3  mov     [r13+8], rcx
0x1800143c7  test    rcx, rcx
0x1800143ca  jz      short loc_1800143D9
0x1800143cc  mov     rax, [rcx]
0x1800143cf  mov     rax, [rax+8]
0x1800143d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143d8  nop
0x1800143d9  mov     qword ptr [r13+10h], 0
0x1800143e1  mov     dword ptr [r13+98h], 0
0x1800143ec  mov     rdx, r13
0x1800143ef  lea     rcx, [rbp+418h]
0x1800143f6  call    ?reset@?$unique_ptr@VTaskXmlWriter@@U?$default_delete@VTaskXmlWriter@@@std@@@std@@QEAAXPEAVTaskXmlWriter@@@Z; std::unique_ptr<TaskXmlWriter>::reset(TaskXmlWriter *)
0x1800143fb  mov     r13, [rbp+418h]
0x180014402  mov     [rsp+0C8h+var_90], r13
0x180014407  mov     eax, [r14]
0x18001440a  mov     [rsp+0C8h+var_80], rax
0x18001440f  mov     [rsp+0C8h+ppvObject], 0
0x180014418  xor     r8d, r8d; pMalloc
0x18001441b  lea     rdx, [rsp+0C8h+ppvObject]; ppvObject
0x180014420  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180014427  call    cs:__imp_CreateXmlWriter
0x18001442d  mov     edi, eax
0x18001442f  test    eax, eax
0x180014431  js      loc_18001463D
0x180014437  mov     rcx, [rsp+0C8h+ppvObject]
0x18001443c  mov     rdi, [r13+10h]
0x180014440  cmp     rdi, rcx
0x180014443  jz      short loc_180014468
0x180014445  mov     [r13+10h], rcx
0x180014449  test    rcx, rcx
0x18001444c  jz      short loc_18001445F
0x18001444e  mov     rax, [rcx]
0x180014451  mov     rax, [rax+8]
0x180014455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001445a  mov     rcx, [rsp+0C8h+ppvObject]
0x18001445f  test    rdi, rdi
0x180014462  jnz     loc_18001499F
0x180014468  mov     rax, [rcx]
0x18001446b  mov     rax, [rax+10h]
0x18001446f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014474  mov     [rsp+0C8h+ppOutput], 0
0x18001447d  lea     r9, [rsp+0C8h+ppOutput]; ppOutput
0x180014482  lea     r8, pwszEncodingName; "UTF-16"
0x180014489  xor     edx, edx; pMalloc
0x18001448b  mov     rcx, [rsp+0C8h+var_90]
0x180014490  mov     rcx, [rcx+8]; pOutputStream
0x180014494  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x18001449a  mov     edi, eax
0x18001449c  test    eax, eax
0x18001449e  js      loc_18001463D
0x1800144a4  mov     rcx, [r13+10h]
0x1800144a8  test    rcx, rcx
0x1800144ab  jz      loc_1800149B8
0x1800144b1  mov     rax, [rcx]
0x1800144b4  mov     rdx, [rsp+0C8h+ppOutput]
0x1800144b9  mov     rax, [rax+18h]
0x1800144bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144c2  mov     edi, eax
0x1800144c4  mov     rcx, [rsp+0C8h+ppOutput]
0x1800144c9  mov     rax, [rcx]
0x1800144cc  mov     rax, [rax+10h]
0x1800144d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144d5  test    edi, edi
0x1800144d7  js      loc_180014A07
0x1800144dd  mov     rcx, [r13+10h]
0x1800144e1  test    rcx, rcx
0x1800144e4  jz      loc_1800149C3
0x1800144ea  mov     rax, [rcx]
0x1800144ed  mov     r8, r12
0x1800144f0  mov     edx, r12d
0x1800144f3  mov     rax, [rax+28h]
0x1800144f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144fc  mov     edi, eax
0x1800144fe  test    eax, eax
0x180014500  js      loc_18001463D
0x180014506  mov     rcx, [r13+10h]
0x18001450a  test    rcx, rcx
0x18001450d  jz      loc_1800149CE
0x180014513  mov     rax, [rcx]
0x180014516  xor     edx, edx
0x180014518  mov     rax, [rax+0D0h]
0x18001451f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014524  mov     edi, eax
0x180014526  test    eax, eax
0x180014528  js      loc_18001463D
0x18001452e  mov     r10, [r13+10h]
0x180014532  test    r10, r10
0x180014535  jz      loc_1800149D9
0x18001453b  mov     rax, [r10]
0x18001453e  mov     r11, [rax+0D8h]
0x180014545  mov     rax, [rsp+0C8h+var_90]
0x18001454a  mov     edx, [rax]
0x18001454c  cmp     edx, 10006h
0x180014552  jnz     loc_180014835
0x180014558  lea     r8, __ImageBase
0x18001455f  movzx   eax, dx; jumptable 0000000180014858 cases 65538-65541
0x180014562  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r8+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18001456a  sub     r8, 0FFFFFFFFFFFFFF80h
0x18001456e  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180014575  mov     r8, [r8+8]
0x180014579  lea     rdx, ChannelPath
0x180014580  mov     rcx, r10
0x180014583  mov     rax, r11
0x180014586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001458b  mov     edi, eax
0x18001458d  test    eax, eax
0x18001458f  js      loc_18001463D
0x180014595  cmp     dword ptr [rsp+0C8h+var_80], 0
0x18001459a  jz      loc_180014645
0x1800145a0  mov     rax, [rsp+0C8h+var_90]
0x1800145a5  mov     r9d, [rax]
0x1800145a8  movzx   eax, r9w
0x1800145ac  shr     r9d, 10h
0x1800145b0  mov     dword ptr [rsp+0C8h+var_A8], eax
0x1800145b4  lea     r8, aDD; "%d.%d"
0x1800145bb  mov     edx, 16h; unsigned __int64
0x1800145c0  lea     rcx, [rsp+0C8h+pExceptionObject]; unsigned __int16 *
0x1800145c5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800145ca  mov     edi, eax
0x1800145cc  test    eax, eax
0x1800145ce  js      short loc_18001463D
0x1800145d0  mov     r10, [r13+10h]
0x1800145d4  test    r10, r10
0x1800145d7  jz      loc_1800149F0
0x1800145dd  mov     rax, [r10]
0x1800145e0  mov     r11, [rax+38h]
0x1800145e4  mov     rax, [rsp+0C8h+var_90]
0x1800145e9  mov     edx, [rax]
0x1800145eb  cmp     edx, 10006h
0x1800145f1  jnz     loc_1800148ED
0x1800145f7  lea     r8, __ImageBase
0x1800145fe  movzx   eax, dx; jumptable 0000000180014910 cases 65538-65541
0x180014601  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r8+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180014609  add     r8, 100h
0x180014610  lea     rax, [rsp+0C8h+pExceptionObject]
0x180014615  mov     [rsp+0C8h+var_A8], rax
0x18001461a  xor     r9d, r9d
0x18001461d  mov     r8, [r8+8]
0x180014621  lea     rdx, ChannelPath
0x180014628  mov     rcx, r10
0x18001462b  mov     rax, r11
0x18001462e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014633  mov     edi, eax
0x180014635  test    eax, eax
0x180014637  jns     loc_180014745
0x18001463d  test    edi, edi
0x18001463f  js      loc_180014A07
0x180014645  mov     eax, [rbp+430h]
0x18001464b  test    eax, eax
0x18001464d  js      loc_18001426B
0x180014653  lea     r11, __ImageBase
0x18001465a  jmp     loc_180014264
0x18001465f  mov     rax, [r15+30h]
0x180014663  cmp     ebx, 60h ; '`'
0x180014666  jz      loc_180014A86
0x18001466c  test    rax, rax
0x18001466f  jz      loc_180014AA6
0x180014675  mov     rsi, [rax+8]
0x180014679  mov     eax, [rdi+98h]
0x18001467f  test    eax, eax
0x180014681  jnz     loc_180014AAD
0x180014687  mov     edx, [rdi]; struct IErrorInfo *
0x180014689  cmp     edx, 10006h
0x18001468f  jnz     loc_180014895
0x180014695  movzx   eax, dx; jumptable 00000001800148B1 cases 65538-65541
0x180014698  mov     rcx, rbx
0x18001469b  shl     rcx, 7
0x18001469f  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r11+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x1800146a7  add     r8, rcx
0x1800146aa  mov     eax, [r8]
0x1800146ad  test    eax, eax
0x1800146af  jz      loc_180014AC6
0x1800146b5  mov     rcx, [rdi+10h]
0x1800146b9  test    rcx, rcx
0x1800146bc  jz      loc_180014AD2
0x1800146c2  mov     rax, [rcx]
0x1800146c5  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x1800146cc  mov     r8, [r8+8]
0x1800146d0  lea     rdx, ChannelPath
0x1800146d7  mov     rax, [rax+0D8h]
0x1800146de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146e3  test    eax, eax
0x1800146e5  js      loc_18001426B
0x1800146eb  jnz     short loc_180014719
0x1800146ed  test    rsi, rsi
0x1800146f0  jz      short loc_180014719
0x1800146f2  mov     rcx, [rdi+10h]
0x1800146f6  test    rcx, rcx
0x1800146f9  jz      loc_180014ADD
0x1800146ff  mov     rax, [rcx]
0x180014702  mov     rdx, rsi
0x180014705  mov     rax, [rax+0E0h]
0x18001470c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014711  test    eax, eax
0x180014713  js      loc_18001426B
0x180014719  mov     eax, [rdi+98h]
0x18001471f  test    eax, eax
0x180014721  jnz     loc_180014AE8
0x180014727  mov     rcx, [rdi+10h]
  ... truncated ...
```
