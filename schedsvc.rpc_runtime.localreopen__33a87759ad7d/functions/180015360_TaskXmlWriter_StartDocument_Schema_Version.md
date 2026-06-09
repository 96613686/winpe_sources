# TaskXmlWriter::StartDocument(Schema::Version)

- ea: `0x180015360`
- end: `0x180015734`
- name: `?StartDocument@TaskXmlWriter@@QEAAJW4Version@Schema@@@Z`
- size: `980`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180002ae0`

## callees

- `0x180015360`
- `0x180015740`
- `0x180052118`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x18001539f`
- `XmlLite!CreateXmlWriter` at `0x18001539f`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x180015401`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x180015401`

## string_xrefs

- `0x1800155c7`: `xmlns`

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
                v17 = (const struct SchemaEntry * near *)(*((_QWORD *)&_ImageBase + v25 + 69844) + (v24 << 7));
                if ( *(_DWORD *)v17 == 1 )
                  goto LABEL_17;
                ++v24;
              }
LABEL_42:
              v17 = (const struct SchemaEntry * near *)&qword_18009D560;
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
                      v21 = (const struct SchemaEntry * near *)(*((_QWORD *)&_ImageBase + v28 + 69844) + (v27 << 7));
                      if ( *(_DWORD *)v21 == 2 )
                        goto LABEL_23;
                      ++v27;
                    }
LABEL_44:
                    v21 = (const struct SchemaEntry * near *)&qword_18009D560;
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
0x180015360  mov     [rsp+arg_8], rbx
0x180015365  mov     [rsp+arg_10], rbp
0x18001536a  push    rsi
0x18001536b  push    rdi
0x18001536c  push    r14
0x18001536e  sub     rsp, 80h
0x180015375  mov     rax, cs:__security_cookie
0x18001537c  xor     rax, rsp
0x18001537f  mov     [rsp+98h+var_28], rax
0x180015384  mov     esi, edx
0x180015386  mov     rbx, rcx
0x180015389  xor     ebp, ebp
0x18001538b  mov     [rsp+98h+ppvObject], rbp
0x180015390  xor     r8d, r8d; pMalloc
0x180015393  lea     rdx, [rsp+98h+ppvObject]; ppvObject
0x180015398  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x18001539f  call    cs:__imp_CreateXmlWriter
0x1800153a5  test    eax, eax
0x1800153a7  js      loc_180015583
0x1800153ad  mov     rcx, [rsp+98h+ppvObject]
0x1800153b2  mov     rdi, [rbx+10h]
0x1800153b6  cmp     rdi, rcx
0x1800153b9  jz      short loc_1800153DE
0x1800153bb  mov     [rbx+10h], rcx
0x1800153bf  test    rcx, rcx
0x1800153c2  jz      short loc_1800153D5
0x1800153c4  mov     rax, [rcx]
0x1800153c7  mov     rax, [rax+8]
0x1800153cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153d0  mov     rcx, [rsp+98h+ppvObject]
0x1800153d5  test    rdi, rdi
0x1800153d8  jnz     loc_18001568A
0x1800153de  mov     rax, [rcx]
0x1800153e1  mov     rax, [rax+10h]
0x1800153e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153ea  mov     [rsp+98h+ppOutput], rbp
0x1800153ef  lea     r9, [rsp+98h+ppOutput]; ppOutput
0x1800153f4  lea     r8, pwszEncodingName; "UTF-16"
0x1800153fb  xor     edx, edx; pMalloc
0x1800153fd  mov     rcx, [rbx+8]; pOutputStream
0x180015401  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x180015407  test    eax, eax
0x180015409  js      loc_180015583
0x18001540f  mov     rcx, [rbx+10h]
0x180015413  test    rcx, rcx
0x180015416  jz      loc_1800156A3
0x18001541c  mov     rax, [rcx]
0x18001541f  mov     rdx, [rsp+98h+ppOutput]
0x180015424  mov     rax, [rax+18h]
0x180015428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001542d  mov     edi, eax
0x18001542f  mov     rcx, [rsp+98h+ppOutput]
0x180015434  mov     rdx, [rcx]
0x180015437  mov     rax, [rdx+10h]
0x18001543b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015440  test    edi, edi
0x180015442  js      loc_1800156AE
0x180015448  mov     rcx, [rbx+10h]
0x18001544c  test    rcx, rcx
0x18001544f  jz      loc_1800156B5
0x180015455  mov     rax, [rcx]
0x180015458  mov     edx, 1
0x18001545d  mov     r8d, edx
0x180015460  mov     rax, [rax+28h]
0x180015464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015469  test    eax, eax
0x18001546b  js      loc_180015583
0x180015471  mov     rcx, [rbx+10h]
0x180015475  test    rcx, rcx
0x180015478  jz      loc_1800156C0
0x18001547e  mov     rax, [rcx]
0x180015481  xor     edx, edx
0x180015483  mov     rax, [rax+0D0h]
0x18001548a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001548f  test    eax, eax
0x180015491  js      loc_180015583
0x180015497  mov     r10, [rbx+10h]
0x18001549b  test    r10, r10
0x18001549e  jz      loc_1800156CB
0x1800154a4  mov     rax, [r10]
0x1800154a7  mov     r11, [rax+0D8h]
0x1800154ae  mov     edx, [rbx]
0x1800154b0  lea     r14, __ImageBase
0x1800154b7  cmp     edx, 10006h
0x1800154bd  jnz     loc_1800155E0
0x1800154c3  movzx   edx, dx; jumptable 00000001800155FC cases 65538-65541
0x1800154c6  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r14+rdx*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x1800154ce  sub     r8, 0FFFFFFFFFFFFFF80h
0x1800154d2  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x1800154d9  mov     r8, [r8+8]
0x1800154dd  lea     rdx, ChannelPath
0x1800154e4  mov     rcx, r10
0x1800154e7  mov     rax, r11
0x1800154ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154ef  test    eax, eax
0x1800154f1  js      loc_180015583
0x1800154f7  test    esi, esi
0x1800154f9  jz      loc_180015583
0x1800154ff  mov     r9d, [rbx]
0x180015502  movzx   eax, r9w
0x180015506  shr     r9d, 10h
0x18001550a  mov     [rsp+98h+var_78], eax
0x18001550e  lea     r8, aDD; "%d.%d"
0x180015515  mov     edx, 16h; unsigned __int64
0x18001551a  lea     rcx, [rsp+98h+var_58]; unsigned __int16 *
0x18001551f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015524  test    eax, eax
0x180015526  js      short loc_180015583
0x180015528  mov     r10, [rbx+10h]
0x18001552c  test    r10, r10
0x18001552f  jz      loc_1800156E2
0x180015535  mov     rax, [r10]
0x180015538  mov     r11, [rax+38h]
0x18001553c  mov     edx, [rbx]
0x18001553e  cmp     edx, 10006h
0x180015544  jnz     loc_180015637
0x18001554a  movzx   edx, dx; jumptable 0000000180015653 cases 65538-65541
0x18001554d  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r14+rdx*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180015555  add     r8, 100h
0x18001555c  lea     rax, [rsp+98h+var_58]
0x180015561  mov     qword ptr [rsp+98h+var_78], rax
0x180015566  xor     r9d, r9d
0x180015569  mov     r8, [r8+8]
0x18001556d  lea     rdx, ChannelPath
0x180015574  mov     rcx, r10
0x180015577  mov     rax, r11
0x18001557a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001557f  test    eax, eax
0x180015581  jns     short loc_1800155A8
0x180015583  mov     rcx, [rsp+98h+var_28]
0x180015588  xor     rcx, rsp; StackCookie
0x18001558b  call    __security_check_cookie
0x180015590  lea     r11, [rsp+98h+var_18]
0x180015598  mov     rbx, [r11+28h]
0x18001559c  mov     rbp, [r11+30h]
0x1800155a0  mov     rsp, r11
0x1800155a3  pop     r14
0x1800155a5  pop     rdi
0x1800155a6  pop     rsi
0x1800155a7  retn
0x1800155a8  mov     rcx, [rbx+10h]
0x1800155ac  test    rcx, rcx
0x1800155af  jz      loc_1800156F9
0x1800155b5  mov     r8, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x1800155bc  mov     rax, [rcx]
0x1800155bf  mov     qword ptr [rsp+98h+var_78], r8
0x1800155c4  xor     r9d, r9d
0x1800155c7  lea     r8, aXmlns; "xmlns"
0x1800155ce  lea     rdx, ChannelPath
0x1800155d5  mov     rax, [rax+38h]
0x1800155d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155de  jmp     short loc_180015583
0x1800155e0  lea     eax, [rdx-10000h]; switch 6 cases
0x1800155e6  cmp     eax, 5
0x1800155e9  ja      def_1800155FC; jumptable 00000001800155FC default case
0x1800155ef  cdqe
0x1800155f1  mov     ecx, ds:(jpt_1800155FC - 180000000h)[r14+rax*4]
0x1800155f9  add     rcx, r14
0x1800155fc  jmp     rcx; switch jump
0x1800155fe  mov     r9, rbp; jumptable 00000001800155FC cases 65536,65537
0x180015601  movzx   eax, dx
0x180015604  mov     rdx, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r14+rax*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x18001560c  lea     rdi, ds:886A0h[rax*8]
0x180015614  cmp     r9, rdx
0x180015617  jnb     def_1800155FC; jumptable 00000001800155FC default case
0x18001561d  mov     r8, r9
0x180015620  shl     r8, 7
0x180015624  add     r8, [rdi+r14]
0x180015628  cmp     dword ptr [r8], 1
0x18001562c  jz      loc_1800154D2
0x180015632  inc     r9
0x180015635  jmp     short loc_180015614
0x180015637  lea     eax, [rdx-10000h]; switch 6 cases
0x18001563d  cmp     eax, 5
0x180015640  ja      def_180015653; jumptable 0000000180015653 default case
0x180015646  cdqe
0x180015648  mov     ecx, ds:(jpt_180015653 - 180000000h)[r14+rax*4]
0x180015650  add     rcx, r14
0x180015653  jmp     rcx; switch jump
0x180015655  mov     r9, rbp; jumptable 0000000180015653 cases 65536,65537
0x180015658  movzx   eax, dx
0x18001565b  mov     rdx, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r14+rax*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x180015663  lea     rdi, ds:886A0h[rax*8]
0x18001566b  cmp     r9, rdx
0x18001566e  jnb     short def_180015653; jumptable 0000000180015653 default case
0x180015670  mov     r8, r9
0x180015673  shl     r8, 7
0x180015677  add     r8, [rdi+r14]
0x18001567b  cmp     dword ptr [r8], 2
0x18001567f  jz      loc_18001555C
0x180015685  inc     r9
0x180015688  jmp     short loc_18001566B
0x18001568a  mov     rax, [rdi]
0x18001568d  mov     rcx, rdi
0x180015690  mov     rax, [rax+10h]
0x180015694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015699  mov     rcx, [rsp+98h+ppvObject]
0x18001569e  jmp     loc_1800153DE
0x1800156a3  mov     ecx, 80004003h; int
0x1800156a8  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x1800156ae  mov     eax, edi
0x1800156b0  jmp     loc_180015583
0x1800156b5  mov     ecx, 80004003h; int
0x1800156ba  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x1800156c0  mov     ecx, 80004003h; int
0x1800156c5  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x1800156cb  mov     ecx, 80004003h; int
0x1800156d0  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x1800156d6  mov     r8, cs:off_1800886D0; jumptable 00000001800155FC default case
0x1800156dd  jmp     loc_1800154D2
0x1800156e2  mov     ecx, 80004003h; int
0x1800156e7  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x1800156ed  mov     r8, cs:off_1800886D0; jumptable 0000000180015653 default case
0x1800156f4  jmp     loc_18001555C
0x1800156f9  mov     ecx, 80004003h; int
0x1800156fe  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
