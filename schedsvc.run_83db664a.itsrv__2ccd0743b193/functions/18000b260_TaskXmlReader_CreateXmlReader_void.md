# TaskXmlReader::CreateXmlReader(void)

- ea: `0x18000b260`
- end: `0x18000b8bc`
- name: `?CreateXmlReader@TaskXmlReader@@AEAAJXZ`
- size: `1628`
- prototype: `__int64 __fastcall(TaskXmlReader *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ce30`

## callees

- `0x180009d60`
- `0x18000a460`
- `0x18000b260`
- `0x18000c9d0`
- `0x180042d54`
- `0x180043778`
- `0x180044818`
- `0x180050c24`
- `0x180054824`
- `0x18005a2bc`
- `0x180082a40`
- `0x180088010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b384`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b462`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b384`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b462`
- `XmlLite!CreateXmlWriter` at `0x18000b52f`
- `XmlLite!CreateXmlWriter` at `0x18000b52f`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x18000b5a4`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x18000b5a4`
- `XmlLite!CreateXmlReader` at `0x18000b2a4`
- `XmlLite!CreateXmlReader` at `0x18000b2a4`

## string_xrefs

- `0x18000b81f`: `xmlns`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
      v47 = &qword_1800A8718;
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
      v47 = &qword_1800A8718;
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
                v33 = (const struct SchemaEntry * near *)(*((_QWORD *)&_ImageBase + v31 + 71892) + (v30 << 7));
                if ( *(_DWORD *)v33 == 1 )
                  goto LABEL_59;
                ++v30;
              }
LABEL_57:
              v33 = (const struct SchemaEntry * near *)&qword_1800A1560;
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
                    v40 = (const struct SchemaEntry * near *)(*((_QWORD *)&_ImageBase + v38 + 71892) + (v37 << 7));
                    if ( *(_DWORD *)v40 == 2 )
                      goto LABEL_71;
                    ++v37;
                  }
LABEL_69:
                  v40 = (const struct SchemaEntry * near *)&qword_1800A1560;
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
0x18000b260  mov     [rsp-8+arg_8], rbx
0x18000b265  mov     [rsp-8+arg_10], rsi
0x18000b26a  push    rbp
0x18000b26b  push    rdi
0x18000b26c  push    r12
0x18000b26e  push    r14
0x18000b270  push    r15
0x18000b272  lea     rbp, [rsp-37h]
0x18000b277  sub     rsp, 0A0h
0x18000b27e  mov     rax, cs:__security_cookie
0x18000b285  xor     rax, rsp
0x18000b288  mov     [rbp+57h+var_30], rax
0x18000b28c  mov     rdi, rcx
0x18000b28f  xor     r15d, r15d
0x18000b292  mov     [rbp+57h+ppvObject], r15
0x18000b296  xor     r8d, r8d; pMalloc
0x18000b299  lea     rdx, [rbp+57h+ppvObject]; ppvObject
0x18000b29d  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18000b2a4  call    cs:__imp_CreateXmlReader
0x18000b2ab  nop     dword ptr [rax+rax+00h]
0x18000b2b0  test    eax, eax
0x18000b2b2  jns     short loc_18000B2C3
0x18000b2b4  mov     edx, eax; int
0x18000b2b6  mov     rcx, rdi; this
0x18000b2b9  call    ?SetErrorInfoXmlLite@TaskXmlReader@@AEAAJJ@Z; TaskXmlReader::SetErrorInfoXmlLite(long)
0x18000b2be  jmp     loc_18000B861
0x18000b2c3  mov     rcx, [rbp+57h+ppvObject]
0x18000b2c7  mov     rbx, rcx
0x18000b2ca  mov     [rbp+57h+var_78], rcx
0x18000b2ce  test    rcx, rcx
0x18000b2d1  jz      short loc_18000B2E3
0x18000b2d3  mov     rax, [rcx]
0x18000b2d6  mov     rax, [rax+8]
0x18000b2da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2df  mov     rcx, [rbp+57h+ppvObject]
0x18000b2e3  mov     rax, [rcx]
0x18000b2e6  mov     rax, [rax+10h]
0x18000b2ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2ef  test    rbx, rbx
0x18000b2f2  jnz     short loc_18000B2FF
0x18000b2f4  mov     ecx, 80004003h; int
0x18000b2f9  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18000b2ff  mov     rax, [rbx]
0x18000b302  mov     rdx, [rdi+20h]
0x18000b306  mov     rcx, rbx
0x18000b309  mov     rax, [rax+18h]
0x18000b30d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b312  test    eax, eax
0x18000b314  jns     short loc_18000B339
0x18000b316  mov     edx, eax; int
0x18000b318  mov     rcx, rdi; this
0x18000b31b  call    ?SetErrorInfoXmlLite@TaskXmlReader@@AEAAJJ@Z; TaskXmlReader::SetErrorInfoXmlLite(long)
0x18000b320  mov     edi, eax
0x18000b322  mov     rcx, [rbx]
0x18000b325  mov     rax, [rcx+10h]
0x18000b329  mov     rcx, rbx
0x18000b32c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b331  nop
0x18000b332  mov     eax, edi
0x18000b334  jmp     loc_18000B861
0x18000b339  mov     rsi, [rdi+38h]
0x18000b33d  cmp     rsi, rbx
0x18000b340  jz      short loc_18000B36B
0x18000b342  mov     [rdi+38h], rbx
0x18000b346  mov     rax, [rbx]
0x18000b349  mov     rcx, rbx
0x18000b34c  mov     rax, [rax+8]
0x18000b350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b355  nop
0x18000b356  test    rsi, rsi
0x18000b359  jz      short loc_18000B36B
0x18000b35b  mov     rax, [rsi]
0x18000b35e  mov     rcx, rsi
0x18000b361  mov     rax, [rax+10h]
0x18000b365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b36a  nop
0x18000b36b  cmp     byte ptr [rdi+28h], 0
0x18000b36f  jz      loc_18000B84F
0x18000b375  xor     edx, edx; dwFlags
0x18000b377  mov     r8d, 28h ; '('; dwBytes
0x18000b37d  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18000b384  call    cs:__imp_HeapAlloc
0x18000b38b  nop     dword ptr [rax+rax+00h]
0x18000b390  test    rax, rax
0x18000b393  jnz     short loc_18000B3D6
0x18000b395  mov     [rbp+57h+var_60], al
0x18000b398  lea     rax, qword_1800A8718
0x18000b39f  mov     [rbp+57h+var_58], rax
0x18000b3a3  mov     [rbp+57h+var_50], r15
0x18000b3a7  mov     [rbp+57h+var_48], r15
0x18000b3ab  mov     [rbp+57h+var_40], 0Eh
0x18000b3b2  mov     [rbp+57h+var_3C], 0FFFFFFFFFFFFFFFFh
0x18000b3ba  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000b3c1  mov     [rbp+57h+pExceptionObject], rax
0x18000b3c5  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18000b3cc  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000b3d0  call    _CxxThrowException_0
0x18000b3d6  mov     [rbp+57h+ppOutput], rax
0x18000b3da  mov     rcx, rax; this
0x18000b3dd  call    ??0CBstrWriter@@QEAA@XZ; CBstrWriter::CBstrWriter(void)
0x18000b3e2  mov     rsi, rax
0x18000b3e5  lea     r14, [rdi+18h]
0x18000b3e9  mov     rax, [r14]
0x18000b3ec  cmp     rax, rsi
0x18000b3ef  jz      short loc_18000B423
0x18000b3f1  test    r14, r14
0x18000b3f4  jz      short loc_18000B423
0x18000b3f6  test    rsi, rsi
0x18000b3f9  jz      short loc_18000B40A
0x18000b3fb  mov     rcx, [rsi]
0x18000b3fe  mov     rax, [rcx+8]
0x18000b402  mov     rcx, rsi
0x18000b405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b40a  mov     rcx, [r14]
0x18000b40d  test    rcx, rcx
0x18000b410  jz      short loc_18000B41E
0x18000b412  mov     rax, [rcx]
0x18000b415  mov     rax, [rax+10h]
0x18000b419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b41e  mov     [r14], rsi
0x18000b421  jmp     short loc_18000B426
0x18000b423  mov     rsi, rax
0x18000b426  test    rsi, rsi
0x18000b429  jnz     short loc_18000B445
0x18000b42b  mov     rax, [rbx]
0x18000b42e  mov     rcx, rbx
0x18000b431  mov     rax, [rax+10h]
0x18000b435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b43a  nop
0x18000b43b  mov     eax, 8007000Eh
0x18000b440  jmp     loc_18000B861
0x18000b445  mov     rcx, [rdi+10h]; this
0x18000b449  test    rcx, rcx
0x18000b44c  jz      short loc_18000B453
0x18000b44e  call    ??_GTaskXmlWriter@@QEAAPEAXI@Z; TaskXmlWriter::`scalar deleting destructor'(uint)
0x18000b453  xor     edx, edx; dwFlags
0x18000b455  mov     r8d, 0A0h; dwBytes
0x18000b45b  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18000b462  call    cs:__imp_HeapAlloc
0x18000b469  nop     dword ptr [rax+rax+00h]
0x18000b46e  mov     rsi, rax
0x18000b471  test    rax, rax
0x18000b474  jnz     short loc_18000B4B7
0x18000b476  mov     [rbp+57h+var_60], al
0x18000b479  lea     rax, qword_1800A8718
0x18000b480  mov     [rbp+57h+var_58], rax
0x18000b484  mov     [rbp+57h+var_50], r15
0x18000b488  mov     [rbp+57h+var_48], r15
0x18000b48c  mov     [rbp+57h+var_40], 0Eh
0x18000b493  mov     [rbp+57h+var_3C], 0FFFFFFFFFFFFFFFFh
0x18000b49b  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000b4a2  mov     [rbp+57h+pExceptionObject], rax
0x18000b4a6  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18000b4ad  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000b4b1  call    _CxxThrowException_0
0x18000b4b7  mov     [rbp+57h+var_70], rsi
0x18000b4bb  mov     dword ptr [rbp+57h+var_90], 10006h
0x18000b4c2  mov     rdx, r14
0x18000b4c5  lea     rcx, [rbp+57h+ppOutput]
0x18000b4c9  call    ??$?0V?$CComPtr@UIStream@@@ATL@@@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@AEBV?$CComPtr@UIStream@@@ATL@@@Z; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>(ATL::CComPtr<IStream> const &)
0x18000b4ce  lea     r8, [rbp+57h+var_90]
0x18000b4d2  lea     rdx, [rbp+57h+ppOutput]
0x18000b4d6  mov     rcx, rsi
0x18000b4d9  call    ??0TaskXmlWriter@@QEAA@AEBV?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEBUSchema@@@Z; TaskXmlWriter::TaskXmlWriter(_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>> const &,Schema const &)
0x18000b4de  mov     r14, rax
0x18000b4e1  mov     [rdi+10h], rax
0x18000b4e5  mov     rcx, [rbp+57h+ppOutput]
0x18000b4e9  test    rcx, rcx
0x18000b4ec  jz      short loc_18000B4FE
0x18000b4ee  mov     rax, [rcx]
0x18000b4f1  mov     rax, [rax+10h]
0x18000b4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4fa  mov     r14, [rdi+10h]
0x18000b4fe  test    r14, r14
0x18000b501  jnz     short loc_18000B51D
0x18000b503  mov     rax, [rbx]
0x18000b506  mov     rcx, rbx
0x18000b509  mov     rax, [rax+10h]
0x18000b50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b512  nop
0x18000b513  mov     eax, 8007000Eh
0x18000b518  jmp     loc_18000B861
0x18000b51d  mov     [rbp+57h+var_90], r15
0x18000b521  xor     r8d, r8d; pMalloc
0x18000b524  lea     rdx, [rbp+57h+var_90]; ppvObject
0x18000b528  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x18000b52f  call    cs:__imp_CreateXmlWriter
0x18000b536  nop     dword ptr [rax+rax+00h]
0x18000b53b  mov     edi, eax
0x18000b53d  test    eax, eax
0x18000b53f  js      loc_18000B837
0x18000b545  mov     rcx, [rbp+57h+var_90]
0x18000b549  mov     rdi, [r14+10h]
0x18000b54d  cmp     rdi, rcx
0x18000b550  jz      short loc_18000B583
0x18000b552  mov     [r14+10h], rcx
0x18000b556  test    rcx, rcx
0x18000b559  jz      short loc_18000B56B
0x18000b55b  mov     rax, [rcx]
0x18000b55e  mov     rax, [rax+8]
0x18000b562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b567  mov     rcx, [rbp+57h+var_90]
0x18000b56b  test    rdi, rdi
0x18000b56e  jz      short loc_18000B583
0x18000b570  mov     rax, [rdi]
0x18000b573  mov     rcx, rdi
0x18000b576  mov     rax, [rax+10h]
0x18000b57a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b57f  mov     rcx, [rbp+57h+var_90]
0x18000b583  mov     rax, [rcx]
0x18000b586  mov     rax, [rax+10h]
0x18000b58a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b58f  mov     [rbp+57h+ppOutput], r15
0x18000b593  lea     r9, [rbp+57h+ppOutput]; ppOutput
0x18000b597  lea     r8, pwszEncodingName; "UTF-16"
0x18000b59e  xor     edx, edx; pMalloc
0x18000b5a0  mov     rcx, [r14+8]; pOutputStream
0x18000b5a4  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x18000b5ab  nop     dword ptr [rax+rax+00h]
0x18000b5b0  mov     edi, eax
0x18000b5b2  test    eax, eax
0x18000b5b4  js      loc_18000B837
0x18000b5ba  mov     rcx, [r14+10h]
0x18000b5be  test    rcx, rcx
0x18000b5c1  jnz     short loc_18000B5CE
0x18000b5c3  mov     ecx, 80004003h; int
0x18000b5c8  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18000b5ce  mov     rax, [rcx]
0x18000b5d1  mov     rdx, [rbp+57h+ppOutput]
0x18000b5d5  mov     rax, [rax+18h]
0x18000b5d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5de  mov     edi, eax
0x18000b5e0  mov     rcx, [rbp+57h+ppOutput]
0x18000b5e4  mov     rax, [rcx]
0x18000b5e7  mov     rax, [rax+10h]
0x18000b5eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5f0  test    edi, edi
0x18000b5f2  js      loc_18000B83B
0x18000b5f8  mov     rcx, [r14+10h]
0x18000b5fc  test    rcx, rcx
0x18000b5ff  jnz     short loc_18000B60C
0x18000b601  mov     ecx, 80004003h; int
0x18000b606  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18000b60c  mov     rax, [rcx]
0x18000b60f  mov     edx, 1
0x18000b614  mov     r8d, edx
0x18000b617  mov     rax, [rax+28h]
0x18000b61b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b620  mov     edi, eax
0x18000b622  test    eax, eax
0x18000b624  js      loc_18000B837
0x18000b62a  mov     rcx, [r14+10h]
0x18000b62e  test    rcx, rcx
0x18000b631  jnz     short loc_18000B63E
0x18000b633  mov     ecx, 80004003h; int
0x18000b638  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18000b63e  mov     rax, [rcx]
0x18000b641  xor     edx, edx
0x18000b643  mov     rax, [rax+0D0h]
0x18000b64a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b64f  mov     edi, eax
0x18000b651  test    eax, eax
0x18000b653  js      loc_18000B837
0x18000b659  mov     r10, [r14+10h]
0x18000b65d  test    r10, r10
0x18000b660  jnz     short loc_18000B66D
0x18000b662  mov     ecx, 80004003h; int
0x18000b667  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18000b66d  mov     rax, [r10]
0x18000b670  mov     r11, [rax+0D8h]
0x18000b677  mov     edx, [r14]
0x18000b67a  lea     r12, __ImageBase
0x18000b681  cmp     edx, 10006h
0x18000b687  jz      short loc_18000B6E1; jumptable 000000018000B6A1 cases 65538-65541
0x18000b689  lea     eax, [rdx-10000h]; switch 6 cases
0x18000b68f  cmp     eax, 5
0x18000b692  ja      short def_18000B6A1; jumptable 000000018000B6A1 default case
0x18000b694  cdqe
0x18000b696  mov     ecx, ds:(jpt_18000B6A1 - 180000000h)[r12+rax*4]
0x18000b69e  add     rcx, r12
0x18000b6a1  jmp     rcx; switch jump
0x18000b6a7  mov     r9, r15; jumptable 000000018000B6A1 cases 65536,65537
0x18000b6aa  movzx   eax, dx
0x18000b6ad  mov     rdx, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r12+rax*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x18000b6b5  lea     rdi, ds:8C6A0h[rax*8]
0x18000b6bd  cmp     r9, rdx
0x18000b6c0  jnb     short def_18000B6A1; jumptable 000000018000B6A1 default case
0x18000b6c2  mov     r8, r9
0x18000b6c5  shl     r8, 7
0x18000b6c9  add     r8, [rdi+r12]
0x18000b6cd  cmp     dword ptr [r8], 1
0x18000b6d1  jz      short loc_18000B6F0
0x18000b6d3  inc     r9
0x18000b6d6  jmp     short loc_18000B6BD
0x18000b6d8  mov     r8, cs:off_18008C6D0; jumptable 000000018000B6A1 default case
0x18000b6df  jmp     short loc_18000B6F0
0x18000b6e1  movzx   edx, dx; jumptable 000000018000B6A1 cases 65538-65541
0x18000b6e4  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r12+rdx*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18000b6ec  sub     r8, 0FFFFFFFFFFFFFF80h
0x18000b6f0  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
  ... truncated ...
```
