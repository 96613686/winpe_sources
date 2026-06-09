# TaskXmlWriter::StartDocument(Schema::Version)

- ea: `0x18000a060`
- end: `0x18000a44c`
- name: `?StartDocument@TaskXmlWriter@@QEAAJW4Version@Schema@@@Z`
- size: `1004`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180018100`

## callees

- `0x18000a060`
- `0x18000a460`
- `0x180054824`
- `0x180082a40`
- `0x180088010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x18000a09f`
- `XmlLite!CreateXmlWriter` at `0x18000a09f`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x18000a107`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x18000a107`

## string_xrefs

- `0x18000a2d4`: `xmlns`

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
  int v20; // edx
  const struct SchemaEntry * near *v21; // r8
  struct IErrorInfo *v22; // rdx
  __int64 v23; // rcx
  unsigned __int64 v24; // r9
  __int64 v25; // rax
  const unsigned __int64 near *v26; // rdx
  unsigned __int64 v27; // r9
  __int64 v28; // rax
  const unsigned __int64 near *v29; // rdx
  int v30; // [rsp+20h] [rbp-78h]
  void *ppvObject; // [rsp+30h] [rbp-68h] BYREF
  IXmlWriterOutput *ppOutput; // [rsp+38h] [rbp-60h] BYREF
  unsigned __int16 v33[24]; // [rsp+40h] [rbp-58h] BYREF

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
                  v24 = 0;
                  v25 = (unsigned __int16)v16;
                  v26 = (&Schema::schemaEntriesCount)[(unsigned __int16)v16];
                  break;
                case 65538:
                case 65539:
                case 65540:
                case 65541:
                  goto LABEL_16;
                default:
                  goto LABEL_42;
              }
              while ( v24 < (unsigned __int64)v26 )
              {
                v17 = (const struct SchemaEntry * near *)(*((_QWORD *)&_ImageBase + v25 + 71892) + (v24 << 7));
                if ( *(_DWORD *)v17 == 1 )
                  goto LABEL_17;
                ++v24;
              }
LABEL_42:
              v17 = (const struct SchemaEntry * near *)&qword_1800A1560;
            }
LABEL_17:
            result = (*(__int64 (__fastcall **)(_QWORD, const OLECHAR *, const struct SchemaEntry *, unsigned __int16 *const))(*(_QWORD *)v15 + 216LL))(
                       *((_QWORD *)a1 + 2),
                       &ChannelPath,
                       v17[1],
                       Schema::namespaceUri);
            if ( result >= 0 )
            {
              if ( a2 )
              {
                v30 = (unsigned __int16)*a1;
                result = StringCchPrintfW(v33, 0x16u, L"%d.%d", HIWORD(*a1), v30);
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
                        v27 = 0;
                        v28 = (unsigned __int16)v20;
                        v29 = (&Schema::schemaEntriesCount)[(unsigned __int16)v20];
                        break;
                      case 65538:
                      case 65539:
                      case 65540:
                      case 65541:
                        goto LABEL_22;
                      default:
                        goto LABEL_44;
                    }
                    while ( v27 < (unsigned __int64)v29 )
                    {
                      v21 = (const struct SchemaEntry * near *)(*((_QWORD *)&_ImageBase + v28 + 71892) + (v27 << 7));
                      if ( *(_DWORD *)v21 == 2 )
                        goto LABEL_23;
                      ++v27;
                    }
LABEL_44:
                    v21 = (const struct SchemaEntry * near *)&qword_1800A1560;
                  }
LABEL_23:
                  result = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, const struct SchemaEntry *, _QWORD, unsigned __int16 *))(*(_QWORD *)v19 + 56LL))(
                             v19,
                             &ChannelPath,
                             v21[1],
                             0,
                             v33);
                  if ( result >= 0 )
                  {
                    v23 = *((_QWORD *)a1 + 2);
                    if ( !v23 )
                      _com_raise_error(-2147467261, v22);
                    return (*(__int64 (__fastcall **)(__int64, const OLECHAR *, const unsigned __int16 *, _QWORD, unsigned __int16 *const))(*(_QWORD *)v23 + 56LL))(
                             v23,
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
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000a060  mov     [rsp+arg_8], rbx
0x18000a065  mov     [rsp+arg_10], rbp
0x18000a06a  push    rsi
0x18000a06b  push    rdi
0x18000a06c  push    r14
0x18000a06e  sub     rsp, 80h
0x18000a075  mov     rax, cs:__security_cookie
0x18000a07c  xor     rax, rsp
0x18000a07f  mov     [rsp+98h+var_28], rax
0x18000a084  mov     esi, edx
0x18000a086  mov     rbx, rcx
0x18000a089  xor     ebp, ebp
0x18000a08b  mov     [rsp+98h+ppvObject], rbp
0x18000a090  xor     r8d, r8d; pMalloc
0x18000a093  lea     rdx, [rsp+98h+ppvObject]; ppvObject
0x18000a098  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x18000a09f  call    cs:__imp_CreateXmlWriter
0x18000a0a6  nop     dword ptr [rax+rax+00h]
0x18000a0ab  test    eax, eax
0x18000a0ad  js      loc_18000A28F
0x18000a0b3  mov     rcx, [rsp+98h+ppvObject]
0x18000a0b8  mov     rdi, [rbx+10h]
0x18000a0bc  cmp     rdi, rcx
0x18000a0bf  jz      short loc_18000A0E4
0x18000a0c1  mov     [rbx+10h], rcx
0x18000a0c5  test    rcx, rcx
0x18000a0c8  jz      short loc_18000A0DB
0x18000a0ca  mov     rax, [rcx]
0x18000a0cd  mov     rax, [rax+8]
0x18000a0d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0d6  mov     rcx, [rsp+98h+ppvObject]
0x18000a0db  test    rdi, rdi
0x18000a0de  jnz     loc_18000A39F
0x18000a0e4  mov     rax, [rcx]
0x18000a0e7  mov     rax, [rax+10h]
0x18000a0eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0f0  mov     [rsp+98h+ppOutput], rbp
0x18000a0f5  lea     r9, [rsp+98h+ppOutput]; ppOutput
0x18000a0fa  lea     r8, pwszEncodingName; "UTF-16"
0x18000a101  xor     edx, edx; pMalloc
0x18000a103  mov     rcx, [rbx+8]; pOutputStream
0x18000a107  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x18000a10e  nop     dword ptr [rax+rax+00h]
0x18000a113  test    eax, eax
0x18000a115  js      loc_18000A28F
0x18000a11b  mov     rcx, [rbx+10h]
0x18000a11f  test    rcx, rcx
0x18000a122  jz      loc_18000A3B8
0x18000a128  mov     rax, [rcx]
0x18000a12b  mov     rdx, [rsp+98h+ppOutput]
0x18000a130  mov     rax, [rax+18h]
0x18000a134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a139  mov     edi, eax
0x18000a13b  mov     rcx, [rsp+98h+ppOutput]
0x18000a140  mov     rdx, [rcx]
0x18000a143  mov     rax, [rdx+10h]
0x18000a147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a14c  test    edi, edi
0x18000a14e  js      loc_18000A3C3
0x18000a154  mov     rcx, [rbx+10h]
0x18000a158  test    rcx, rcx
0x18000a15b  jz      loc_18000A3CA
0x18000a161  mov     rax, [rcx]
0x18000a164  mov     edx, 1
0x18000a169  mov     r8d, edx
0x18000a16c  mov     rax, [rax+28h]
0x18000a170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a175  test    eax, eax
0x18000a177  js      loc_18000A28F
0x18000a17d  mov     rcx, [rbx+10h]
0x18000a181  test    rcx, rcx
0x18000a184  jz      loc_18000A3D5
0x18000a18a  mov     rax, [rcx]
0x18000a18d  xor     edx, edx
0x18000a18f  mov     rax, [rax+0D0h]
0x18000a196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a19b  test    eax, eax
0x18000a19d  js      loc_18000A28F
0x18000a1a3  mov     r10, [rbx+10h]
0x18000a1a7  test    r10, r10
0x18000a1aa  jz      loc_18000A3E0
0x18000a1b0  mov     rax, [r10]
0x18000a1b3  mov     r11, [rax+0D8h]
0x18000a1ba  mov     edx, [rbx]
0x18000a1bc  lea     r14, __ImageBase
0x18000a1c3  cmp     edx, 10006h
0x18000a1c9  jnz     loc_18000A2ED
0x18000a1cf  movzx   edx, dx; jumptable 000000018000A309 cases 65538-65541
0x18000a1d2  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r14+rdx*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18000a1da  sub     r8, 0FFFFFFFFFFFFFF80h
0x18000a1de  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x18000a1e5  mov     r8, [r8+8]
0x18000a1e9  lea     rdx, ChannelPath
0x18000a1f0  mov     rcx, r10
0x18000a1f3  mov     rax, r11
0x18000a1f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1fb  test    eax, eax
0x18000a1fd  js      loc_18000A28F
0x18000a203  test    esi, esi
0x18000a205  jz      loc_18000A28F
0x18000a20b  mov     r9d, [rbx]
0x18000a20e  movzx   eax, r9w
0x18000a212  shr     r9d, 10h
0x18000a216  mov     [rsp+98h+var_78], eax
0x18000a21a  lea     r8, aDD; "%d.%d"
0x18000a221  mov     edx, 16h; unsigned __int64
0x18000a226  lea     rcx, [rsp+98h+var_58]; unsigned __int16 *
0x18000a22b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a230  test    eax, eax
0x18000a232  js      short loc_18000A28F
0x18000a234  mov     r10, [rbx+10h]
0x18000a238  test    r10, r10
0x18000a23b  jz      loc_18000A3F7
0x18000a241  mov     rax, [r10]
0x18000a244  mov     r11, [rax+38h]
0x18000a248  mov     edx, [rbx]
0x18000a24a  cmp     edx, 10006h
0x18000a250  jnz     loc_18000A348
0x18000a256  movzx   edx, dx; jumptable 000000018000A364 cases 65538-65541
0x18000a259  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r14+rdx*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x18000a261  add     r8, 100h
0x18000a268  lea     rax, [rsp+98h+var_58]
0x18000a26d  mov     qword ptr [rsp+98h+var_78], rax
0x18000a272  xor     r9d, r9d
0x18000a275  mov     r8, [r8+8]
0x18000a279  lea     rdx, ChannelPath
0x18000a280  mov     rcx, r10
0x18000a283  mov     rax, r11
0x18000a286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a28b  test    eax, eax
0x18000a28d  jns     short loc_18000A2B5
0x18000a28f  mov     rcx, [rsp+98h+var_28]
0x18000a294  xor     rcx, rsp; StackCookie
0x18000a297  call    __security_check_cookie
0x18000a29c  lea     r11, [rsp+98h+var_18]
0x18000a2a4  mov     rbx, [r11+28h]
0x18000a2a8  mov     rbp, [r11+30h]
0x18000a2ac  mov     rsp, r11
0x18000a2af  pop     r14
0x18000a2b1  pop     rdi
0x18000a2b2  pop     rsi
0x18000a2b3  retn
0x18000a2b5  mov     rcx, [rbx+10h]
0x18000a2b9  test    rcx, rcx
0x18000a2bc  jz      loc_18000A40E
0x18000a2c2  mov     r8, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x18000a2c9  mov     rax, [rcx]
0x18000a2cc  mov     qword ptr [rsp+98h+var_78], r8
0x18000a2d1  xor     r9d, r9d
0x18000a2d4  lea     r8, aXmlns; "xmlns"
0x18000a2db  lea     rdx, ChannelPath
0x18000a2e2  mov     rax, [rax+38h]
0x18000a2e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2eb  jmp     short loc_18000A28F
0x18000a2ed  lea     eax, [rdx-10000h]; switch 6 cases
0x18000a2f3  cmp     eax, 5
0x18000a2f6  ja      def_18000A309; jumptable 000000018000A309 default case
0x18000a2fc  cdqe
0x18000a2fe  mov     ecx, ds:(jpt_18000A309 - 180000000h)[r14+rax*4]
0x18000a306  add     rcx, r14
0x18000a309  jmp     rcx; switch jump
0x18000a30f  mov     r9, rbp; jumptable 000000018000A309 cases 65536,65537
0x18000a312  movzx   eax, dx
0x18000a315  mov     rdx, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r14+rax*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x18000a31d  lea     rdi, ds:8C6A0h[rax*8]
0x18000a325  cmp     r9, rdx
0x18000a328  jnb     def_18000A309; jumptable 000000018000A309 default case
0x18000a32e  mov     r8, r9
0x18000a331  shl     r8, 7
0x18000a335  add     r8, [rdi+r14]
0x18000a339  cmp     dword ptr [r8], 1
0x18000a33d  jz      loc_18000A1DE
0x18000a343  inc     r9
0x18000a346  jmp     short loc_18000A325
0x18000a348  lea     eax, [rdx-10000h]; switch 6 cases
0x18000a34e  cmp     eax, 5
0x18000a351  ja      def_18000A364; jumptable 000000018000A364 default case
0x18000a357  cdqe
0x18000a359  mov     ecx, ds:(jpt_18000A364 - 180000000h)[r14+rax*4]
0x18000a361  add     rcx, r14
0x18000a364  jmp     rcx; switch jump
0x18000a36a  mov     r9, rbp; jumptable 000000018000A364 cases 65536,65537
0x18000a36d  movzx   eax, dx
0x18000a370  mov     rdx, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r14+rax*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x18000a378  lea     rdi, ds:8C6A0h[rax*8]
0x18000a380  cmp     r9, rdx
0x18000a383  jnb     short def_18000A364; jumptable 000000018000A364 default case
0x18000a385  mov     r8, r9
0x18000a388  shl     r8, 7
0x18000a38c  add     r8, [rdi+r14]
0x18000a390  cmp     dword ptr [r8], 2
0x18000a394  jz      loc_18000A268
0x18000a39a  inc     r9
0x18000a39d  jmp     short loc_18000A380
0x18000a39f  mov     rax, [rdi]
0x18000a3a2  mov     rcx, rdi
0x18000a3a5  mov     rax, [rax+10h]
0x18000a3a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3ae  mov     rcx, [rsp+98h+ppvObject]
0x18000a3b3  jmp     loc_18000A0E4
0x18000a3b8  mov     ecx, 80004003h; int
0x18000a3bd  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18000a3c3  mov     eax, edi
0x18000a3c5  jmp     loc_18000A28F
0x18000a3ca  mov     ecx, 80004003h; int
0x18000a3cf  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18000a3d5  mov     ecx, 80004003h; int
0x18000a3da  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18000a3e0  mov     ecx, 80004003h; int
0x18000a3e5  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18000a3eb  mov     r8, cs:off_18008C6D0; jumptable 000000018000A309 default case
0x18000a3f2  jmp     loc_18000A1DE
0x18000a3f7  mov     ecx, 80004003h; int
0x18000a3fc  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18000a402  mov     r8, cs:off_18008C6D0; jumptable 000000018000A364 default case
0x18000a409  jmp     loc_18000A268
0x18000a40e  mov     ecx, 80004003h; int
0x18000a413  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
