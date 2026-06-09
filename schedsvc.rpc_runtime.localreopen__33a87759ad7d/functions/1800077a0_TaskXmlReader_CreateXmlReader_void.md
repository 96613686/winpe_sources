# TaskXmlReader::CreateXmlReader(void)

- ea: `0x1800077a0`
- end: `0x180007dd4`
- name: `?CreateXmlReader@TaskXmlReader@@AEAAJXZ`
- size: `1588`
- prototype: `__int64 __fastcall(TaskXmlWriter **this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008330`

## callees

- `0x1800077a0`
- `0x180008010`
- `0x180015740`
- `0x180016160`
- `0x180040958`
- `0x1800411b4`
- `0x180042578`
- `0x18004e7fc`
- `0x180052118`
- `0x18005790c`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800078be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007996`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800078be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007996`
- `XmlLite!CreateXmlWriter` at `0x180007a5d`
- `XmlLite!CreateXmlWriter` at `0x180007a5d`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x180007acc`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x180007acc`
- `XmlLite!CreateXmlReader` at `0x1800077e4`
- `XmlLite!CreateXmlReader` at `0x1800077e4`

## string_xrefs

- `0x180007d39`: `xmlns`

## pseudocode

```c
__int64 __fastcall TaskXmlReader::CreateXmlReader(TaskXmlWriter **this)
{
  HRESULT XmlReader; // eax
  void *v4; // rcx
  TaskXmlWriter *v5; // rbx
  struct IErrorInfo *v6; // rdx
  int v7; // eax
  unsigned int v8; // edi
  TaskXmlWriter *v9; // rsi
  IXmlWriterOutput *v10; // rax
  unsigned int v11; // edx
  CBstrWriter *v12; // rsi
  CBstrWriter **v13; // r14
  TaskXmlWriter *v14; // rcx
  void *v15; // rax
  void *v16; // rsi
  __int64 v17; // r14
  HRESULT v18; // edi
  void *v19; // rcx
  void *v20; // rdi
  struct IErrorInfo *v21; // rdx
  __int64 v22; // rcx
  struct IErrorInfo *v23; // rdx
  __int64 v24; // rcx
  struct IErrorInfo *v25; // rdx
  __int64 v26; // rcx
  struct IErrorInfo *v27; // rdx
  __int64 v28; // r10
  int v29; // edx
  unsigned __int64 v30; // r9
  __int64 v31; // rax
  const unsigned __int64 near *v32; // rdx
  const struct SchemaEntry * near *v33; // r8
  struct IErrorInfo *v34; // rdx
  __int64 v35; // r10
  int v36; // edx
  unsigned __int64 v37; // r9
  __int64 v38; // rax
  const unsigned __int64 near *v39; // rdx
  const struct SchemaEntry * near *v40; // r8
  __int64 v41; // rax
  void *v42; // [rsp+30h] [rbp-39h] BYREF
  IXmlWriterOutput *ppOutput; // [rsp+38h] [rbp-31h] BYREF
  void *ppvObject[3]; // [rsp+40h] [rbp-29h] BYREF
  void **pExceptionObject; // [rsp+58h] [rbp-11h] BYREF
  char v46; // [rsp+60h] [rbp-9h]
  const unsigned __int16 *v47; // [rsp+68h] [rbp-1h]
  __int64 v48; // [rsp+70h] [rbp+7h]
  __int64 v49; // [rsp+78h] [rbp+Fh]
  int v50; // [rsp+80h] [rbp+17h]
  __int64 v51; // [rsp+84h] [rbp+1Bh]

  ppvObject[0] = 0;
  XmlReader = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, ppvObject, 0);
  if ( XmlReader < 0 )
    return TaskXmlReader::SetErrorInfoXmlLite((TaskXmlReader *)this, XmlReader);
  v4 = ppvObject[0];
  v5 = (TaskXmlWriter *)ppvObject[0];
  ppvObject[1] = ppvObject[0];
  if ( ppvObject[0] )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject[0] + 8LL))(ppvObject[0]);
    v4 = ppvObject[0];
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 16LL))(v4);
  if ( !v5 )
    _com_raise_error(-2147467261, v6);
  v7 = (*(__int64 (__fastcall **)(TaskXmlWriter *, TaskXmlWriter *))(*(_QWORD *)v5 + 24LL))(v5, this[4]);
  if ( v7 < 0 )
  {
    v8 = TaskXmlReader::SetErrorInfoXmlLite((TaskXmlReader *)this, v7);
    (*(void (__fastcall **)(TaskXmlWriter *))(*(_QWORD *)v5 + 16LL))(v5);
    return v8;
  }
  v9 = this[7];
  if ( v9 != v5 )
  {
    this[7] = v5;
    (*(void (__fastcall **)(TaskXmlWriter *))(*(_QWORD *)v5 + 8LL))(v5);
    if ( v9 )
      (*(void (__fastcall **)(TaskXmlWriter *))(*(_QWORD *)v9 + 16LL))(v9);
  }
  if ( *((_BYTE *)this + 40) )
  {
    v10 = (IXmlWriterOutput *)HeapAlloc(g_PrivateHeap, 0, 0x28u);
    if ( !v10 )
    {
      v46 = 0;
      v47 = &qword_1800A4718;
      v48 = 0;
      v49 = 0;
      v50 = 14;
      v51 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    ppOutput = v10;
    v12 = CBstrWriter::CBstrWriter((CBstrWriter *)v10);
    v13 = this + 3;
    if ( this[3] == v12 || this == (TaskXmlWriter **)-24LL )
    {
      v12 = this[3];
    }
    else
    {
      if ( v12 )
        (*(void (__fastcall **)(CBstrWriter *))(*(_QWORD *)v12 + 8LL))(v12);
      if ( *v13 )
        (*(void (__fastcall **)(CBstrWriter *))(*(_QWORD *)*v13 + 16LL))(*v13);
      *v13 = v12;
    }
    if ( !v12 )
    {
      (*(void (__fastcall **)(TaskXmlWriter *))(*(_QWORD *)v5 + 16LL))(v5);
      return 2147942414LL;
    }
    v14 = this[2];
    if ( v14 )
      TaskXmlWriter::`scalar deleting destructor'(v14, v11);
    v15 = HeapAlloc(g_PrivateHeap, 0, 0xA0u);
    v16 = v15;
    if ( !v15 )
    {
      v46 = 0;
      v47 = &qword_1800A4718;
      v48 = 0;
      v49 = 0;
      v50 = 14;
      v51 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    ppvObject[2] = v15;
    LODWORD(v42) = 65542;
    _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>(
      &ppOutput,
      this + 3);
    v17 = TaskXmlWriter::TaskXmlWriter(v16, &ppOutput, &v42);
    this[2] = (TaskXmlWriter *)v17;
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      v17 = (__int64)this[2];
    }
    if ( !v17 )
    {
      (*(void (__fastcall **)(TaskXmlWriter *))(*(_QWORD *)v5 + 16LL))(v5);
      return 2147942414LL;
    }
    v42 = 0;
    v18 = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &v42, 0);
    if ( v18 >= 0 )
    {
      v19 = v42;
      v20 = *(void **)(v17 + 16);
      if ( v20 != v42 )
      {
        *(_QWORD *)(v17 + 16) = v42;
        if ( v19 )
        {
          (*(void (__fastcall **)(void *))(*(_QWORD *)v19 + 8LL))(v19);
          v19 = v42;
        }
        if ( v20 )
        {
          (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
          v19 = v42;
        }
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)v19 + 16LL))(v19);
      ppOutput = 0;
      v18 = CreateXmlWriterOutputWithEncodingName(*(IUnknown **)(v17 + 8), 0, L"UTF-16", &ppOutput);
      if ( v18 >= 0 )
      {
        v22 = *(_QWORD *)(v17 + 16);
        if ( !v22 )
          _com_raise_error(-2147467261, v21);
        v18 = (*(__int64 (__fastcall **)(__int64, IXmlWriterOutput *))(*(_QWORD *)v22 + 24LL))(v22, ppOutput);
        ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
        if ( v18 < 0 )
          goto LABEL_74;
        v24 = *(_QWORD *)(v17 + 16);
        if ( !v24 )
          _com_raise_error(-2147467261, v23);
        v18 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v24 + 40LL))(v24, 1, 1);
        if ( v18 >= 0 )
        {
          v26 = *(_QWORD *)(v17 + 16);
          if ( !v26 )
            _com_raise_error(-2147467261, v25);
          v18 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v26 + 208LL))(v26, 0);
          if ( v18 >= 0 )
          {
            v28 = *(_QWORD *)(v17 + 16);
            if ( !v28 )
              _com_raise_error(-2147467261, v27);
            v29 = *(_DWORD *)v17;
            if ( *(_DWORD *)v17 == 65542 )
            {
LABEL_58:
              v33 = (&Schema::schemaEntries)[(unsigned __int16)v29] + 16;
            }
            else
            {
              switch ( v29 )
              {
                case 65536:
                case 65537:
                  v30 = 0;
                  v31 = (unsigned __int16)v29;
                  v32 = (&Schema::schemaEntriesCount)[(unsigned __int16)v29];
                  break;
                case 65538:
                case 65539:
                case 65540:
                case 65541:
                  goto LABEL_58;
                default:
                  goto LABEL_57;
              }
              while ( v30 < (unsigned __int64)v32 )
              {
                v33 = (const struct SchemaEntry * near *)(*((_QWORD *)&_ImageBase + v31 + 69844) + (v30 << 7));
                if ( *(_DWORD *)v33 == 1 )
                  goto LABEL_59;
                ++v30;
              }
LABEL_57:
              v33 = (const struct SchemaEntry * near *)&qword_18009D560;
            }
LABEL_59:
            v18 = (*(__int64 (__fastcall **)(_QWORD, const OLECHAR *, const struct SchemaEntry *, unsigned __int16 *const))(*(_QWORD *)v28 + 216LL))(
                    *(_QWORD *)(v17 + 16),
                    &ChannelPath,
                    v33[1],
                    Schema::namespaceUri);
            if ( v18 >= 0 )
            {
              v18 = StringCchPrintfW(
                      (unsigned __int16 *)&pExceptionObject,
                      0x16u,
                      L"%d.%d",
                      HIWORD(*(_DWORD *)v17),
                      (unsigned __int16)*(_DWORD *)v17);
              if ( v18 >= 0 )
              {
                v35 = *(_QWORD *)(v17 + 16);
                if ( !v35 )
                  _com_raise_error(-2147467261, v34);
                v36 = *(_DWORD *)v17;
                if ( *(_DWORD *)v17 == 65542 )
                {
LABEL_70:
                  v40 = (&Schema::schemaEntries)[(unsigned __int16)v36] + 32;
                }
                else
                {
                  switch ( v36 )
                  {
                    case 65536:
                    case 65537:
                      v37 = 0;
                      v38 = (unsigned __int16)v36;
                      v39 = (&Schema::schemaEntriesCount)[(unsigned __int16)v36];
                      break;
                    case 65538:
                    case 65539:
                    case 65540:
                    case 65541:
                      goto LABEL_70;
                    default:
                      goto LABEL_69;
                  }
                  while ( v37 < (unsigned __int64)v39 )
                  {
                    v40 = (const struct SchemaEntry * near *)(*((_QWORD *)&_ImageBase + v38 + 69844) + (v37 << 7));
                    if ( *(_DWORD *)v40 == 2 )
                      goto LABEL_71;
                    ++v37;
                  }
LABEL_69:
                  v40 = (const struct SchemaEntry * near *)&qword_18009D560;
                }
LABEL_71:
                v18 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, const struct SchemaEntry *, _QWORD, void ***))(*(_QWORD *)v35 + 56LL))(
                        v35,
                        &ChannelPath,
                        v40[1],
                        0,
                        &pExceptionObject);
                if ( v18 >= 0 )
                {
                  v41 = _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(v17 + 16);
                  v18 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, const unsigned __int16 *, _QWORD, unsigned __int16 *const))(*(_QWORD *)v41 + 56LL))(
                          v41,
                          &ChannelPath,
                          L"xmlns",
                          0,
                          Schema::namespaceUri);
                }
              }
            }
          }
        }
      }
    }
    if ( v18 < 0 )
    {
LABEL_74:
      (*(void (__fastcall **)(TaskXmlWriter *))(*(_QWORD *)v5 + 16LL))(v5);
      return (unsigned int)v18;
    }
  }
  (*(void (__fastcall **)(TaskXmlWriter *))(*(_QWORD *)v5 + 16LL))(v5);
  return 0;
}

```

## disassembly

```asm
0x1800077a0  mov     [rsp-8+arg_8], rbx
0x1800077a5  mov     [rsp-8+arg_10], rsi
0x1800077aa  push    rbp
0x1800077ab  push    rdi
0x1800077ac  push    r12
0x1800077ae  push    r14
0x1800077b0  push    r15
0x1800077b2  lea     rbp, [rsp-37h]
0x1800077b7  sub     rsp, 0A0h
0x1800077be  mov     rax, cs:__security_cookie
0x1800077c5  xor     rax, rsp
0x1800077c8  mov     [rbp+57h+var_30], rax
0x1800077cc  mov     rdi, rcx
0x1800077cf  xor     r15d, r15d
0x1800077d2  mov     [rbp+57h+ppvObject], r15
0x1800077d6  xor     r8d, r8d; pMalloc
0x1800077d9  lea     rdx, [rbp+57h+ppvObject]; ppvObject
0x1800077dd  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1800077e4  call    cs:__imp_CreateXmlReader
0x1800077ea  test    eax, eax
0x1800077ec  jns     short loc_1800077FD
0x1800077ee  mov     edx, eax; int
0x1800077f0  mov     rcx, rdi; this
0x1800077f3  call    ?SetErrorInfoXmlLite@TaskXmlReader@@AEAAJJ@Z; TaskXmlReader::SetErrorInfoXmlLite(long)
0x1800077f8  jmp     loc_180007D7B
0x1800077fd  mov     rcx, [rbp+57h+ppvObject]
0x180007801  mov     rbx, rcx
0x180007804  mov     [rbp+57h+var_78], rcx
0x180007808  test    rcx, rcx
0x18000780b  jz      short loc_18000781D
0x18000780d  mov     rax, [rcx]
0x180007810  mov     rax, [rax+8]
0x180007814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007819  mov     rcx, [rbp+57h+ppvObject]
0x18000781d  mov     rax, [rcx]
0x180007820  mov     rax, [rax+10h]
0x180007824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007829  test    rbx, rbx
0x18000782c  jnz     short loc_180007839
0x18000782e  mov     ecx, 80004003h; int
0x180007833  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180007839  mov     rax, [rbx]
0x18000783c  mov     rdx, [rdi+20h]
0x180007840  mov     rcx, rbx
0x180007843  mov     rax, [rax+18h]
0x180007847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000784c  test    eax, eax
0x18000784e  jns     short loc_180007873
0x180007850  mov     edx, eax; int
0x180007852  mov     rcx, rdi; this
0x180007855  call    ?SetErrorInfoXmlLite@TaskXmlReader@@AEAAJJ@Z; TaskXmlReader::SetErrorInfoXmlLite(long)
0x18000785a  mov     edi, eax
0x18000785c  mov     rcx, [rbx]
0x18000785f  mov     rax, [rcx+10h]
0x180007863  mov     rcx, rbx
0x180007866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000786b  nop
0x18000786c  mov     eax, edi
0x18000786e  jmp     loc_180007D7B
0x180007873  mov     rsi, [rdi+38h]
0x180007877  cmp     rsi, rbx
0x18000787a  jz      short loc_1800078A5
0x18000787c  mov     [rdi+38h], rbx
0x180007880  mov     rax, [rbx]
0x180007883  mov     rcx, rbx
0x180007886  mov     rax, [rax+8]
0x18000788a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000788f  nop
0x180007890  test    rsi, rsi
0x180007893  jz      short loc_1800078A5
0x180007895  mov     rax, [rsi]
0x180007898  mov     rcx, rsi
0x18000789b  mov     rax, [rax+10h]
0x18000789f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078a4  nop
0x1800078a5  cmp     byte ptr [rdi+28h], 0
0x1800078a9  jz      loc_180007D69
0x1800078af  xor     edx, edx; dwFlags
0x1800078b1  mov     r8d, 28h ; '('; dwBytes
0x1800078b7  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800078be  call    cs:__imp_HeapAlloc
0x1800078c4  test    rax, rax
0x1800078c7  jnz     short loc_18000790A
0x1800078c9  mov     [rbp+57h+var_60], al
0x1800078cc  lea     rax, qword_1800A4718
0x1800078d3  mov     [rbp+57h+var_58], rax
0x1800078d7  mov     [rbp+57h+var_50], r15
0x1800078db  mov     [rbp+57h+var_48], r15
0x1800078df  mov     [rbp+57h+var_40], 0Eh
0x1800078e6  mov     [rbp+57h+var_3C], 0FFFFFFFFFFFFFFFFh
0x1800078ee  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800078f5  mov     [rbp+57h+pExceptionObject], rax
0x1800078f9  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180007900  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180007904  call    _CxxThrowException_0
0x18000790a  mov     [rbp+57h+ppOutput], rax
0x18000790e  mov     rcx, rax; this
0x180007911  call    ??0CBstrWriter@@QEAA@XZ; CBstrWriter::CBstrWriter(void)
0x180007916  mov     rsi, rax
0x180007919  lea     r14, [rdi+18h]
0x18000791d  mov     rax, [r14]
0x180007920  cmp     rax, rsi
0x180007923  jz      short loc_180007957
0x180007925  test    r14, r14
0x180007928  jz      short loc_180007957
0x18000792a  test    rsi, rsi
0x18000792d  jz      short loc_18000793E
0x18000792f  mov     rcx, [rsi]
0x180007932  mov     rax, [rcx+8]
0x180007936  mov     rcx, rsi
0x180007939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000793e  mov     rcx, [r14]
0x180007941  test    rcx, rcx
0x180007944  jz      short loc_180007952
0x180007946  mov     rax, [rcx]
0x180007949  mov     rax, [rax+10h]
0x18000794d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007952  mov     [r14], rsi
0x180007955  jmp     short loc_18000795A
0x180007957  mov     rsi, rax
0x18000795a  test    rsi, rsi
0x18000795d  jnz     short loc_180007979
0x18000795f  mov     rax, [rbx]
0x180007962  mov     rcx, rbx
0x180007965  mov     rax, [rax+10h]
0x180007969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000796e  nop
0x18000796f  mov     eax, 8007000Eh
0x180007974  jmp     loc_180007D7B
0x180007979  mov     rcx, [rdi+10h]; this
0x18000797d  test    rcx, rcx
0x180007980  jz      short loc_180007987
0x180007982  call    ??_GTaskXmlWriter@@QEAAPEAXI@Z; TaskXmlWriter::`scalar deleting destructor'(uint)
0x180007987  xor     edx, edx; dwFlags
0x180007989  mov     r8d, 0A0h; dwBytes
0x18000798f  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180007996  call    cs:__imp_HeapAlloc
0x18000799c  mov     rsi, rax
0x18000799f  test    rax, rax
0x1800079a2  jnz     short loc_1800079E5
0x1800079a4  mov     [rbp+57h+var_60], al
0x1800079a7  lea     rax, qword_1800A4718
0x1800079ae  mov     [rbp+57h+var_58], rax
0x1800079b2  mov     [rbp+57h+var_50], r15
0x1800079b6  mov     [rbp+57h+var_48], r15
0x1800079ba  mov     [rbp+57h+var_40], 0Eh
0x1800079c1  mov     [rbp+57h+var_3C], 0FFFFFFFFFFFFFFFFh
0x1800079c9  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800079d0  mov     [rbp+57h+pExceptionObject], rax
0x1800079d4  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x1800079db  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800079df  call    _CxxThrowException_0
0x1800079e5  mov     [rbp+57h+var_70], rsi
0x1800079e9  mov     dword ptr [rbp+57h+var_90], 10006h
0x1800079f0  mov     rdx, r14
0x1800079f3  lea     rcx, [rbp+57h+ppOutput]
0x1800079f7  call    ??$?0V?$CComPtr@UIStream@@@ATL@@@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@AEBV?$CComPtr@UIStream@@@ATL@@@Z; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>(ATL::CComPtr<IStream> const &)
0x1800079fc  lea     r8, [rbp+57h+var_90]
0x180007a00  lea     rdx, [rbp+57h+ppOutput]
0x180007a04  mov     rcx, rsi
0x180007a07  call    ??0TaskXmlWriter@@QEAA@AEBV?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEBUSchema@@@Z; TaskXmlWriter::TaskXmlWriter(_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>> const &,Schema const &)
0x180007a0c  mov     r14, rax
0x180007a0f  mov     [rdi+10h], rax
0x180007a13  mov     rcx, [rbp+57h+ppOutput]
0x180007a17  test    rcx, rcx
0x180007a1a  jz      short loc_180007A2C
0x180007a1c  mov     rax, [rcx]
0x180007a1f  mov     rax, [rax+10h]
0x180007a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a28  mov     r14, [rdi+10h]
0x180007a2c  test    r14, r14
0x180007a2f  jnz     short loc_180007A4B
0x180007a31  mov     rax, [rbx]
0x180007a34  mov     rcx, rbx
0x180007a37  mov     rax, [rax+10h]
0x180007a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a40  nop
0x180007a41  mov     eax, 8007000Eh
0x180007a46  jmp     loc_180007D7B
0x180007a4b  mov     [rbp+57h+var_90], r15
0x180007a4f  xor     r8d, r8d; pMalloc
0x180007a52  lea     rdx, [rbp+57h+var_90]; ppvObject
0x180007a56  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180007a5d  call    cs:__imp_CreateXmlWriter
0x180007a63  mov     edi, eax
0x180007a65  test    eax, eax
0x180007a67  js      loc_180007D51
0x180007a6d  mov     rcx, [rbp+57h+var_90]
0x180007a71  mov     rdi, [r14+10h]
0x180007a75  cmp     rdi, rcx
0x180007a78  jz      short loc_180007AAB
0x180007a7a  mov     [r14+10h], rcx
0x180007a7e  test    rcx, rcx
0x180007a81  jz      short loc_180007A93
0x180007a83  mov     rax, [rcx]
0x180007a86  mov     rax, [rax+8]
0x180007a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a8f  mov     rcx, [rbp+57h+var_90]
0x180007a93  test    rdi, rdi
0x180007a96  jz      short loc_180007AAB
0x180007a98  mov     rax, [rdi]
0x180007a9b  mov     rcx, rdi
0x180007a9e  mov     rax, [rax+10h]
0x180007aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aa7  mov     rcx, [rbp+57h+var_90]
0x180007aab  mov     rax, [rcx]
0x180007aae  mov     rax, [rax+10h]
0x180007ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ab7  mov     [rbp+57h+ppOutput], r15
0x180007abb  lea     r9, [rbp+57h+ppOutput]; ppOutput
0x180007abf  lea     r8, pwszEncodingName; "UTF-16"
0x180007ac6  xor     edx, edx; pMalloc
0x180007ac8  mov     rcx, [r14+8]; pOutputStream
0x180007acc  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x180007ad2  mov     edi, eax
0x180007ad4  test    eax, eax
0x180007ad6  js      loc_180007D51
0x180007adc  mov     rcx, [r14+10h]
0x180007ae0  test    rcx, rcx
0x180007ae3  jnz     short loc_180007AF0
0x180007ae5  mov     ecx, 80004003h; int
0x180007aea  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180007af0  mov     rax, [rcx]
0x180007af3  mov     rdx, [rbp+57h+ppOutput]
0x180007af7  mov     rax, [rax+18h]
0x180007afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b00  mov     edi, eax
0x180007b02  mov     rcx, [rbp+57h+ppOutput]
0x180007b06  mov     rax, [rcx]
0x180007b09  mov     rax, [rax+10h]
0x180007b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b12  test    edi, edi
0x180007b14  js      loc_180007D55
0x180007b1a  mov     rcx, [r14+10h]
0x180007b1e  test    rcx, rcx
0x180007b21  jnz     short loc_180007B2E
0x180007b23  mov     ecx, 80004003h; int
0x180007b28  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180007b2e  mov     rax, [rcx]
0x180007b31  mov     edx, 1
0x180007b36  mov     r8d, edx
0x180007b39  mov     rax, [rax+28h]
0x180007b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b42  mov     edi, eax
0x180007b44  test    eax, eax
0x180007b46  js      loc_180007D51
0x180007b4c  mov     rcx, [r14+10h]
0x180007b50  test    rcx, rcx
0x180007b53  jnz     short loc_180007B60
0x180007b55  mov     ecx, 80004003h; int
0x180007b5a  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180007b60  mov     rax, [rcx]
0x180007b63  xor     edx, edx
0x180007b65  mov     rax, [rax+0D0h]
0x180007b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b71  mov     edi, eax
0x180007b73  test    eax, eax
0x180007b75  js      loc_180007D51
0x180007b7b  mov     r10, [r14+10h]
0x180007b7f  test    r10, r10
0x180007b82  jnz     short loc_180007B8F
0x180007b84  mov     ecx, 80004003h; int
0x180007b89  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180007b8f  mov     rax, [r10]
0x180007b92  mov     r11, [rax+0D8h]
0x180007b99  mov     edx, [r14]
0x180007b9c  lea     r12, __ImageBase
0x180007ba3  cmp     edx, 10006h
0x180007ba9  jz      short loc_180007BFF; jumptable 0000000180007BC3 cases 65538-65541
0x180007bab  lea     eax, [rdx-10000h]; switch 6 cases
0x180007bb1  cmp     eax, 5
0x180007bb4  ja      short def_180007BC3; jumptable 0000000180007BC3 default case
0x180007bb6  cdqe
0x180007bb8  mov     ecx, ds:(jpt_180007BC3 - 180000000h)[r12+rax*4]
0x180007bc0  add     rcx, r12
0x180007bc3  jmp     rcx; switch jump
0x180007bc5  mov     r9, r15; jumptable 0000000180007BC3 cases 65536,65537
0x180007bc8  movzx   eax, dx
0x180007bcb  mov     rdx, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r12+rax*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x180007bd3  lea     rdi, ds:886A0h[rax*8]
0x180007bdb  cmp     r9, rdx
0x180007bde  jnb     short def_180007BC3; jumptable 0000000180007BC3 default case
0x180007be0  mov     r8, r9
0x180007be3  shl     r8, 7
0x180007be7  add     r8, [rdi+r12]
0x180007beb  cmp     dword ptr [r8], 1
0x180007bef  jz      short loc_180007C0E
0x180007bf1  inc     r9
0x180007bf4  jmp     short loc_180007BDB
0x180007bf6  mov     r8, cs:off_1800886D0; jumptable 0000000180007BC3 default case
0x180007bfd  jmp     short loc_180007C0E
0x180007bff  movzx   edx, dx; jumptable 0000000180007BC3 cases 65538-65541
0x180007c02  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r12+rdx*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180007c0a  sub     r8, 0FFFFFFFFFFFFFF80h
0x180007c0e  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180007c15  mov     r8, [r8+8]
0x180007c19  lea     rdx, ChannelPath
0x180007c20  mov     rcx, r10
0x180007c23  mov     rax, r11
0x180007c26  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
