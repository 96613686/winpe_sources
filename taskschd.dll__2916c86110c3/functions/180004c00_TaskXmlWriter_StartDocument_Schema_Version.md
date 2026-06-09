# TaskXmlWriter::StartDocument(Schema::Version)

- ea: `0x180004c00`
- end: `0x180004fc0`
- name: `?StartDocument@TaskXmlWriter@@QEAAJW4Version@Schema@@@Z`
- size: `960`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004fd0`
- `0x180019de0`
- `0x180038e58`
- `0x180048cb0`

## callees

- `0x180003c90`
- `0x180004c00`
- `0x1800157e4`
- `0x180038404`
- `0x18004e950`
- `0x180054010`

## import_xrefs

- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x180004c9d`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x180004c9d`
- `XmlLite!CreateXmlWriter` at `0x180004c3b`
- `XmlLite!CreateXmlWriter` at `0x180004c3b`

## string_xrefs

- `0x180004e61`: `xmlns`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall TaskXmlWriter::StartDocument(int *a1, int a2)
{
  HRESULT result; // eax
  void *v5; // rcx
  void *v6; // rdi
  struct IErrorInfo *v7; // rdx
  __int64 v8; // rcx
  int v9; // edi
  struct IErrorInfo *v10; // rdx
  __int64 v11; // rcx
  struct IErrorInfo *v12; // rdx
  __int64 v13; // rcx
  struct IErrorInfo *v14; // rdx
  __int64 v15; // r10
  int v16; // edx
  const struct SchemaEntry * near *v17; // r8
  struct IErrorInfo *v18; // rdx
  __int64 v19; // r10
  int v20; // r8d
  const struct SchemaEntry * near *v21; // r8
  __int64 v22; // rax
  unsigned __int64 v23; // r9
  __int64 v24; // rax
  const unsigned __int64 near *v25; // rdx
  unsigned __int64 v26; // rdx
  const unsigned __int64 near *v27; // r9
  __int64 v28; // rdi
  int v29; // [rsp+20h] [rbp-98h]
  void *ppvObject; // [rsp+30h] [rbp-88h] BYREF
  IXmlWriterOutput *ppOutput; // [rsp+38h] [rbp-80h] BYREF
  unsigned __int16 v32[24]; // [rsp+40h] [rbp-78h] BYREF

  ppvObject = 0;
  result = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( result >= 0 )
  {
    v5 = ppvObject;
    v6 = (void *)*((_QWORD *)a1 + 2);
    if ( v6 != ppvObject )
    {
      *((_QWORD *)a1 + 2) = ppvObject;
      if ( v5 )
      {
        (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 8LL))(v5);
        v5 = ppvObject;
      }
      if ( v6 )
      {
        (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
        v5 = ppvObject;
      }
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
    ppOutput = 0;
    result = CreateXmlWriterOutputWithEncodingName(*((IUnknown **)a1 + 1), 0, L"UTF-16", &ppOutput);
    if ( result >= 0 )
    {
      v8 = *((_QWORD *)a1 + 2);
      if ( !v8 )
        _com_raise_error(-2147467261, v7);
      v9 = (*(__int64 (__fastcall **)(__int64, IXmlWriterOutput *))(*(_QWORD *)v8 + 24LL))(v8, ppOutput);
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      if ( v9 < 0 )
      {
        return v9;
      }
      else
      {
        v11 = *((_QWORD *)a1 + 2);
        if ( !v11 )
          _com_raise_error(-2147467261, v10);
        result = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v11 + 40LL))(v11, 1, 1);
        if ( result >= 0 )
        {
          v13 = *((_QWORD *)a1 + 2);
          if ( !v13 )
            _com_raise_error(-2147467261, v12);
          result = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 208LL))(v13, 0);
          if ( result >= 0 )
          {
            v15 = *((_QWORD *)a1 + 2);
            if ( !v15 )
              _com_raise_error(-2147467261, v14);
            v16 = *a1;
            if ( *a1 == 65542 )
            {
LABEL_16:
              v17 = (&Schema::schemaEntries)[(unsigned __int16)v16] + 16;
            }
            else
            {
              switch ( v16 )
              {
                case 65536:
                case 65537:
                  v23 = 0;
                  v24 = (unsigned __int16)v16;
                  v25 = (&Schema::schemaEntriesCount)[(unsigned __int16)v16];
                  break;
                case 65538:
                case 65539:
                case 65540:
                case 65541:
                  goto LABEL_16;
                default:
                  goto LABEL_36;
              }
              while ( v23 < (unsigned __int64)v25 )
              {
                v17 = (const struct SchemaEntry * near *)(*((_QWORD *)&_ImageBase + v24 + 46058) + (v23 << 7));
                if ( *(_DWORD *)v17 == 1 )
                  goto LABEL_17;
                ++v23;
              }
LABEL_36:
              v17 = (const struct SchemaEntry * near *)&qword_18006EE10;
            }
LABEL_17:
            result = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, const struct SchemaEntry *, wchar_t *const))(*(_QWORD *)v15 + 216LL))(
                       *((_QWORD *)a1 + 2),
                       &Src,
                       v17[1],
                       Schema::namespaceUri);
            if ( result >= 0 )
            {
              if ( a2 )
              {
                v29 = (unsigned __int16)*a1;
                result = StringCchPrintfW(v32, 0x16u, L"%d.%d", HIWORD(*a1), v29);
                if ( result >= 0 )
                {
                  v19 = *((_QWORD *)a1 + 2);
                  if ( !v19 )
                    _com_raise_error(-2147467261, v18);
                  v20 = *a1;
                  if ( *a1 == 65542 )
                  {
LABEL_22:
                    v21 = (&Schema::schemaEntries)[(unsigned __int16)v20] + 32;
                  }
                  else
                  {
                    switch ( v20 )
                    {
                      case 65536:
                      case 65537:
                        v26 = 0;
                        v27 = (&Schema::schemaEntriesCount)[(unsigned __int16)v20];
                        v28 = 8LL * (unsigned __int16)v20 + 368464;
                        break;
                      case 65538:
                      case 65539:
                      case 65540:
                      case 65541:
                        goto LABEL_22;
                      default:
                        goto LABEL_37;
                    }
                    while ( v26 < (unsigned __int64)v27 )
                    {
                      v21 = (const struct SchemaEntry * near *)(*(_QWORD *)((char *)&_ImageBase + v28) + (v26 << 7));
                      if ( *(_DWORD *)v21 == 2 )
                        goto LABEL_23;
                      ++v26;
                    }
LABEL_37:
                    v21 = (const struct SchemaEntry * near *)&qword_18006EE10;
                  }
LABEL_23:
                  result = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const struct SchemaEntry *, _QWORD, unsigned __int16 *))(*(_QWORD *)v19 + 56LL))(
                             v19,
                             &Src,
                             v21[1],
                             0,
                             v32);
                  if ( result >= 0 )
                  {
                    v22 = _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(a1 + 4);
                    return (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const wchar_t *, _QWORD, wchar_t *const))(*(_QWORD *)v22 + 56LL))(
                             v22,
                             &Src,
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
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004c00  push    rbx
0x180004c02  push    rbp
0x180004c03  push    rsi
0x180004c04  push    rdi
0x180004c05  push    r14
0x180004c07  push    r15
0x180004c09  sub     rsp, 88h
0x180004c10  mov     rax, cs:__security_cookie
0x180004c17  xor     rax, rsp
0x180004c1a  mov     [rsp+0B8h+var_48], rax
0x180004c1f  mov     ebp, edx
0x180004c21  mov     rsi, rcx
0x180004c24  xor     r15d, r15d
0x180004c27  mov     [rsp+0B8h+ppvObject], r15
0x180004c2c  xor     r8d, r8d; pMalloc
0x180004c2f  lea     rdx, [rsp+0B8h+ppvObject]; ppvObject
0x180004c34  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180004c3b  call    cs:__imp_CreateXmlWriter
0x180004c41  test    eax, eax
0x180004c43  js      loc_180004E22
0x180004c49  mov     rcx, [rsp+0B8h+ppvObject]
0x180004c4e  mov     rdi, [rsi+10h]
0x180004c52  cmp     rdi, rcx
0x180004c55  jz      short loc_180004C7A
0x180004c57  mov     [rsi+10h], rcx
0x180004c5b  test    rcx, rcx
0x180004c5e  jz      short loc_180004C71
0x180004c60  mov     rax, [rcx]
0x180004c63  mov     rax, [rax+8]
0x180004c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c6c  mov     rcx, [rsp+0B8h+ppvObject]
0x180004c71  test    rdi, rdi
0x180004c74  jnz     loc_180004F38
0x180004c7a  mov     rax, [rcx]
0x180004c7d  mov     rax, [rax+10h]
0x180004c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c86  mov     [rsp+0B8h+ppOutput], r15
0x180004c8b  lea     r9, [rsp+0B8h+ppOutput]; ppOutput
0x180004c90  lea     r8, pwszEncodingName; "UTF-16"
0x180004c97  xor     edx, edx; pMalloc
0x180004c99  mov     rcx, [rsi+8]; pOutputStream
0x180004c9d  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x180004ca3  test    eax, eax
0x180004ca5  js      loc_180004E22
0x180004cab  mov     rcx, [rsi+10h]
0x180004caf  test    rcx, rcx
0x180004cb2  jz      loc_180004F51
0x180004cb8  mov     rax, [rcx]
0x180004cbb  mov     rdx, [rsp+0B8h+ppOutput]
0x180004cc0  mov     rax, [rax+18h]
0x180004cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cc9  mov     edi, eax
0x180004ccb  mov     rcx, [rsp+0B8h+ppOutput]
0x180004cd0  mov     rdx, [rcx]
0x180004cd3  mov     rax, [rdx+10h]
0x180004cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cdc  test    edi, edi
0x180004cde  js      loc_180004F5C
0x180004ce4  mov     rcx, [rsi+10h]
0x180004ce8  test    rcx, rcx
0x180004ceb  jz      loc_180004F63
0x180004cf1  mov     rax, [rcx]
0x180004cf4  mov     edx, 1
0x180004cf9  mov     r8d, edx
0x180004cfc  mov     rax, [rax+28h]
0x180004d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d05  test    eax, eax
0x180004d07  js      loc_180004E22
0x180004d0d  mov     rcx, [rsi+10h]
0x180004d11  test    rcx, rcx
0x180004d14  jz      loc_180004F6E
0x180004d1a  mov     rax, [rcx]
0x180004d1d  xor     edx, edx
0x180004d1f  mov     rax, [rax+0D0h]
0x180004d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d2b  test    eax, eax
0x180004d2d  js      loc_180004E22
0x180004d33  mov     r10, [rsi+10h]
0x180004d37  test    r10, r10
0x180004d3a  jz      loc_180004F79
0x180004d40  mov     rax, [r10]
0x180004d43  mov     r11, [rax+0D8h]
0x180004d4a  mov     edx, [rsi]
0x180004d4c  lea     r14, __ImageBase
0x180004d53  cmp     edx, 10006h
0x180004d59  jnz     loc_180004E79
0x180004d5f  movzx   edx, dx; jumptable 0000000180004E95 cases 65538-65541
0x180004d62  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r14+rdx*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180004d6a  sub     r8, 0FFFFFFFFFFFFFF80h
0x180004d6e  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180004d75  mov     r8, [r8+8]
0x180004d79  lea     rdx, Src
0x180004d80  mov     rcx, r10
0x180004d83  mov     rax, r11
0x180004d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d8b  test    eax, eax
0x180004d8d  js      loc_180004E22
0x180004d93  test    ebp, ebp
0x180004d95  jz      loc_180004E22
0x180004d9b  mov     r9d, [rsi]
0x180004d9e  movzx   eax, r9w
0x180004da2  shr     r9d, 10h
0x180004da6  mov     [rsp+0B8h+var_98], eax
0x180004daa  lea     r8, aDD; "%d.%d"
0x180004db1  mov     edx, 16h; unsigned __int64
0x180004db6  lea     rcx, [rsp+0B8h+var_78]; unsigned __int16 *
0x180004dbb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004dc0  test    eax, eax
0x180004dc2  js      short loc_180004E22
0x180004dc4  mov     r10, [rsi+10h]
0x180004dc8  test    r10, r10
0x180004dcb  jz      loc_180004F84
0x180004dd1  mov     rax, [r10]
0x180004dd4  mov     r11, [rax+38h]
0x180004dd8  mov     r8d, [rsi]
0x180004ddb  cmp     r8d, 10006h
0x180004de2  jnz     loc_180004ECF
0x180004de8  movzx   edx, r8w; jumptable 0000000180004EE8 cases 65538-65541
0x180004dec  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r14+rdx*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180004df4  add     r8, 100h
0x180004dfb  lea     rax, [rsp+0B8h+var_78]
0x180004e00  mov     qword ptr [rsp+0B8h+var_98], rax
0x180004e05  xor     r9d, r9d
0x180004e08  mov     r8, [r8+8]
0x180004e0c  lea     rdx, Src
0x180004e13  mov     rcx, r10
0x180004e16  mov     rax, r11
0x180004e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e1e  test    eax, eax
0x180004e20  jns     short loc_180004E3F
0x180004e22  mov     rcx, [rsp+0B8h+var_48]
0x180004e27  xor     rcx, rsp; StackCookie
0x180004e2a  call    __security_check_cookie
0x180004e2f  add     rsp, 88h
0x180004e36  pop     r15
0x180004e38  pop     r14
0x180004e3a  pop     rdi
0x180004e3b  pop     rsi
0x180004e3c  pop     rbp
0x180004e3d  pop     rbx
0x180004e3e  retn
0x180004e3f  lea     rcx, [rsi+10h]
0x180004e43  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlWriter@@$1?_GUID_7279fc88_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlWriter@@XZ; _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x180004e48  mov     r10, rax
0x180004e4b  mov     r8, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180004e52  mov     rcx, [rax]
0x180004e55  mov     rax, [rcx+38h]
0x180004e59  mov     qword ptr [rsp+0B8h+var_98], r8
0x180004e5e  xor     r9d, r9d
0x180004e61  lea     r8, aXmlns; "xmlns"
0x180004e68  lea     rdx, Src
0x180004e6f  mov     rcx, r10
0x180004e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e77  jmp     short loc_180004E22
0x180004e79  lea     eax, [rdx-10000h]; switch 6 cases
0x180004e7f  cmp     eax, 5
0x180004e82  ja      def_180004E95; jumptable 0000000180004E95 default case
0x180004e88  cdqe
0x180004e8a  mov     ecx, ds:(jpt_180004E95 - 180000000h)[r14+rax*4]
0x180004e92  add     rcx, r14
0x180004e95  jmp     rcx; switch jump
0x180004e97  mov     r9, r15; jumptable 0000000180004E95 cases 65536,65537
0x180004e9a  movzx   eax, dx
0x180004e9d  mov     rdx, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r14+rax*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x180004ea5  lea     rdi, ds:59F50h[rax*8]
0x180004ead  nop     dword ptr [rax]
0x180004eb0  cmp     r9, rdx
0x180004eb3  jnb     short def_180004E95; jumptable 0000000180004E95 default case
0x180004eb5  mov     r8, r9
0x180004eb8  shl     r8, 7
0x180004ebc  add     r8, [rdi+r14]
0x180004ec0  cmp     dword ptr [r8], 1
0x180004ec4  jz      loc_180004D6E
0x180004eca  inc     r9
0x180004ecd  jmp     short loc_180004EB0
0x180004ecf  lea     eax, [r8-10000h]; switch 6 cases
0x180004ed6  cmp     eax, 5
0x180004ed9  ja      short def_180004EE8; jumptable 0000000180004EE8 default case
0x180004edb  cdqe
0x180004edd  mov     ecx, ds:(jpt_180004EE8 - 180000000h)[r14+rax*4]
0x180004ee5  add     rcx, r14
0x180004ee8  jmp     rcx; switch jump
0x180004eea  mov     rdx, r15; jumptable 0000000180004EE8 cases 65536,65537
0x180004eed  movzx   eax, r8w
0x180004ef1  mov     r9, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r14+rax*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x180004ef9  lea     rdi, ds:59F50h[rax*8]
0x180004f01  cmp     rdx, r9
0x180004f04  jnb     short def_180004EE8; jumptable 0000000180004EE8 default case
0x180004f06  mov     r8, rdx
0x180004f09  shl     r8, 7
0x180004f0d  add     r8, [rdi+r14]
0x180004f11  cmp     dword ptr [r8], 2
0x180004f15  jz      loc_180004DFB
0x180004f1b  inc     rdx
0x180004f1e  jmp     short loc_180004F01
0x180004f20  mov     r8, cs:off_180059F80; jumptable 0000000180004E95 default case
0x180004f27  jmp     loc_180004D6E
0x180004f2c  mov     r8, cs:off_180059F80; jumptable 0000000180004EE8 default case
0x180004f33  jmp     loc_180004DFB
0x180004f38  mov     rax, [rdi]
0x180004f3b  mov     rcx, rdi
0x180004f3e  mov     rax, [rax+10h]
0x180004f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f47  mov     rcx, [rsp+0B8h+ppvObject]
0x180004f4c  jmp     loc_180004C7A
0x180004f51  mov     ecx, 80004003h; int
0x180004f56  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180004f5c  mov     eax, edi
0x180004f5e  jmp     loc_180004E22
0x180004f63  mov     ecx, 80004003h; int
0x180004f68  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180004f6e  mov     ecx, 80004003h; int
0x180004f73  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180004f79  mov     ecx, 80004003h; int
0x180004f7e  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180004f84  mov     ecx, 80004003h; int
0x180004f89  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
