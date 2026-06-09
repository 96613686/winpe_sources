# TaskXmlWriter::StartDocument(Schema::Version)

- ea: `0x180004ee0`
- end: `0x1800052b4`
- name: `?StartDocument@TaskXmlWriter@@QEAAJW4Version@Schema@@@Z`
- size: `980`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800052c0`
- `0x18001af90`
- `0x18003bf68`
- `0x18004c7d8`

## callees

- `0x180003ea0`
- `0x180004ee0`
- `0x180016900`
- `0x18003b74c`
- `0x180052640`
- `0x180058010`

## import_xrefs

- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x180004f83`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x180004f83`
- `XmlLite!CreateXmlWriter` at `0x180004f1b`
- `XmlLite!CreateXmlWriter` at `0x180004f1b`

## string_xrefs

- `0x18000514e`: `xmlns`

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
                v17 = (const struct SchemaEntry * near *)(*((_QWORD *)&_ImageBase + v24 + 48103) + (v23 << 7));
                if ( *(_DWORD *)v17 == 1 )
                  goto LABEL_17;
                ++v23;
              }
LABEL_36:
              v17 = (const struct SchemaEntry * near *)&qword_180072DF0;
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
                        v28 = 8LL * (unsigned __int16)v20 + 384824;
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
                    v21 = (const struct SchemaEntry * near *)&qword_180072DF0;
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
0x180004ee0  push    rbx
0x180004ee2  push    rbp
0x180004ee3  push    rsi
0x180004ee4  push    rdi
0x180004ee5  push    r14
0x180004ee7  push    r15
0x180004ee9  sub     rsp, 88h
0x180004ef0  mov     rax, cs:__security_cookie
0x180004ef7  xor     rax, rsp
0x180004efa  mov     [rsp+0B8h+var_48], rax
0x180004eff  mov     ebp, edx
0x180004f01  mov     rsi, rcx
0x180004f04  xor     r15d, r15d
0x180004f07  mov     [rsp+0B8h+ppvObject], r15
0x180004f0c  xor     r8d, r8d; pMalloc
0x180004f0f  lea     rdx, [rsp+0B8h+ppvObject]; ppvObject
0x180004f14  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180004f1b  call    cs:__imp_CreateXmlWriter
0x180004f22  nop     dword ptr [rax+rax+00h]
0x180004f27  test    eax, eax
0x180004f29  js      loc_18000510E
0x180004f2f  mov     rcx, [rsp+0B8h+ppvObject]
0x180004f34  mov     rdi, [rsi+10h]
0x180004f38  cmp     rdi, rcx
0x180004f3b  jz      short loc_180004F60
0x180004f3d  mov     [rsi+10h], rcx
0x180004f41  test    rcx, rcx
0x180004f44  jz      short loc_180004F57
0x180004f46  mov     rax, [rcx]
0x180004f49  mov     rax, [rax+8]
0x180004f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f52  mov     rcx, [rsp+0B8h+ppvObject]
0x180004f57  test    rdi, rdi
0x180004f5a  jnz     loc_18000522C
0x180004f60  mov     rax, [rcx]
0x180004f63  mov     rax, [rax+10h]
0x180004f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f6c  mov     [rsp+0B8h+ppOutput], r15
0x180004f71  lea     r9, [rsp+0B8h+ppOutput]; ppOutput
0x180004f76  lea     r8, pwszEncodingName; "UTF-16"
0x180004f7d  xor     edx, edx; pMalloc
0x180004f7f  mov     rcx, [rsi+8]; pOutputStream
0x180004f83  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x180004f8a  nop     dword ptr [rax+rax+00h]
0x180004f8f  test    eax, eax
0x180004f91  js      loc_18000510E
0x180004f97  mov     rcx, [rsi+10h]
0x180004f9b  test    rcx, rcx
0x180004f9e  jz      loc_180005245
0x180004fa4  mov     rax, [rcx]
0x180004fa7  mov     rdx, [rsp+0B8h+ppOutput]
0x180004fac  mov     rax, [rax+18h]
0x180004fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fb5  mov     edi, eax
0x180004fb7  mov     rcx, [rsp+0B8h+ppOutput]
0x180004fbc  mov     rdx, [rcx]
0x180004fbf  mov     rax, [rdx+10h]
0x180004fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fc8  test    edi, edi
0x180004fca  js      loc_180005250
0x180004fd0  mov     rcx, [rsi+10h]
0x180004fd4  test    rcx, rcx
0x180004fd7  jz      loc_180005257
0x180004fdd  mov     rax, [rcx]
0x180004fe0  mov     edx, 1
0x180004fe5  mov     r8d, edx
0x180004fe8  mov     rax, [rax+28h]
0x180004fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ff1  test    eax, eax
0x180004ff3  js      loc_18000510E
0x180004ff9  mov     rcx, [rsi+10h]
0x180004ffd  test    rcx, rcx
0x180005000  jz      loc_180005262
0x180005006  mov     rax, [rcx]
0x180005009  xor     edx, edx
0x18000500b  mov     rax, [rax+0D0h]
0x180005012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005017  test    eax, eax
0x180005019  js      loc_18000510E
0x18000501f  mov     r10, [rsi+10h]
0x180005023  test    r10, r10
0x180005026  jz      loc_18000526D
0x18000502c  mov     rax, [r10]
0x18000502f  mov     r11, [rax+0D8h]
0x180005036  mov     edx, [rsi]
0x180005038  lea     r14, __ImageBase
0x18000503f  cmp     edx, 10006h
0x180005045  jnz     loc_180005166
0x18000504b  movzx   edx, dx; jumptable 0000000180005182 cases 65538-65541
0x18000504e  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r14+rdx*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180005056  sub     r8, 0FFFFFFFFFFFFFF80h
0x18000505a  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180005061  mov     r8, [r8+8]
0x180005065  lea     rdx, Src
0x18000506c  mov     rcx, r10
0x18000506f  mov     rax, r11
0x180005072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005077  test    eax, eax
0x180005079  js      loc_18000510E
0x18000507f  test    ebp, ebp
0x180005081  jz      loc_18000510E
0x180005087  mov     r9d, [rsi]
0x18000508a  movzx   eax, r9w
0x18000508e  shr     r9d, 10h
0x180005092  mov     [rsp+0B8h+var_98], eax
0x180005096  lea     r8, aDD; "%d.%d"
0x18000509d  mov     edx, 16h; unsigned __int64
0x1800050a2  lea     rcx, [rsp+0B8h+var_78]; unsigned __int16 *
0x1800050a7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800050ac  test    eax, eax
0x1800050ae  js      short loc_18000510E
0x1800050b0  mov     r10, [rsi+10h]
0x1800050b4  test    r10, r10
0x1800050b7  jz      loc_180005278
0x1800050bd  mov     rax, [r10]
0x1800050c0  mov     r11, [rax+38h]
0x1800050c4  mov     r8d, [rsi]
0x1800050c7  cmp     r8d, 10006h
0x1800050ce  jnz     loc_1800051BF
0x1800050d4  movzx   edx, r8w; jumptable 00000001800051D8 cases 65538-65541
0x1800050d8  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r14+rdx*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x1800050e0  add     r8, 100h
0x1800050e7  lea     rax, [rsp+0B8h+var_78]
0x1800050ec  mov     qword ptr [rsp+0B8h+var_98], rax
0x1800050f1  xor     r9d, r9d
0x1800050f4  mov     r8, [r8+8]
0x1800050f8  lea     rdx, Src
0x1800050ff  mov     rcx, r10
0x180005102  mov     rax, r11
0x180005105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000510a  test    eax, eax
0x18000510c  jns     short loc_18000512C
0x18000510e  mov     rcx, [rsp+0B8h+var_48]
0x180005113  xor     rcx, rsp; StackCookie
0x180005116  call    __security_check_cookie
0x18000511b  add     rsp, 88h
0x180005122  pop     r15
0x180005124  pop     r14
0x180005126  pop     rdi
0x180005127  pop     rsi
0x180005128  pop     rbp
0x180005129  pop     rbx
0x18000512a  retn
0x18000512c  lea     rcx, [rsi+10h]
0x180005130  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlWriter@@$1?_GUID_7279fc88_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlWriter@@XZ; _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x180005135  mov     r10, rax
0x180005138  mov     r8, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x18000513f  mov     rcx, [rax]
0x180005142  mov     rax, [rcx+38h]
0x180005146  mov     qword ptr [rsp+0B8h+var_98], r8
0x18000514b  xor     r9d, r9d
0x18000514e  lea     r8, aXmlns; "xmlns"
0x180005155  lea     rdx, Src
0x18000515c  mov     rcx, r10
0x18000515f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005164  jmp     short loc_18000510E
0x180005166  lea     eax, [rdx-10000h]; switch 6 cases
0x18000516c  cmp     eax, 5
0x18000516f  ja      def_180005182; jumptable 0000000180005182 default case
0x180005175  cdqe
0x180005177  mov     ecx, ds:(jpt_180005182 - 180000000h)[r14+rax*4]
0x18000517f  add     rcx, r14
0x180005182  jmp     rcx; switch jump
0x180005188  mov     r9, r15; jumptable 0000000180005182 cases 65536,65537
0x18000518b  movzx   eax, dx
0x18000518e  mov     rdx, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r14+rax*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x180005196  lea     rdi, ds:5DF38h[rax*8]
0x18000519e  xchg    ax, ax
0x1800051a0  cmp     r9, rdx
0x1800051a3  jnb     short def_180005182; jumptable 0000000180005182 default case
0x1800051a5  mov     r8, r9
0x1800051a8  shl     r8, 7
0x1800051ac  add     r8, [rdi+r14]
0x1800051b0  cmp     dword ptr [r8], 1
0x1800051b4  jz      loc_18000505A
0x1800051ba  inc     r9
0x1800051bd  jmp     short loc_1800051A0
0x1800051bf  lea     eax, [r8-10000h]; switch 6 cases
0x1800051c6  cmp     eax, 5
0x1800051c9  ja      short def_1800051D8; jumptable 00000001800051D8 default case
0x1800051cb  cdqe
0x1800051cd  mov     ecx, ds:(jpt_1800051D8 - 180000000h)[r14+rax*4]
0x1800051d5  add     rcx, r14
0x1800051d8  jmp     rcx; switch jump
0x1800051de  mov     rdx, r15; jumptable 00000001800051D8 cases 65536,65537
0x1800051e1  movzx   eax, r8w
0x1800051e5  mov     r9, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r14+rax*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x1800051ed  lea     rdi, ds:5DF38h[rax*8]
0x1800051f5  cmp     rdx, r9
0x1800051f8  jnb     short def_1800051D8; jumptable 00000001800051D8 default case
0x1800051fa  mov     r8, rdx
0x1800051fd  shl     r8, 7
0x180005201  add     r8, [rdi+r14]
0x180005205  cmp     dword ptr [r8], 2
0x180005209  jz      loc_1800050E7
0x18000520f  inc     rdx
0x180005212  jmp     short loc_1800051F5
0x180005214  mov     r8, cs:off_18005DF68; jumptable 0000000180005182 default case
0x18000521b  jmp     loc_18000505A
0x180005220  mov     r8, cs:off_18005DF68; jumptable 00000001800051D8 default case
0x180005227  jmp     loc_1800050E7
0x18000522c  mov     rax, [rdi]
0x18000522f  mov     rcx, rdi
0x180005232  mov     rax, [rax+10h]
0x180005236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000523b  mov     rcx, [rsp+0B8h+ppvObject]
0x180005240  jmp     loc_180004F60
0x180005245  mov     ecx, 80004003h; int
0x18000524a  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180005250  mov     eax, edi
0x180005252  jmp     loc_18000510E
0x180005257  mov     ecx, 80004003h; int
0x18000525c  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180005262  mov     ecx, 80004003h; int
0x180005267  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18000526d  mov     ecx, 80004003h; int
0x180005272  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180005278  mov     ecx, 80004003h; int
0x18000527d  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
