# TaskXmlWriter::StartDocument(Schema::Version)

- ea: `0x18001cb98`
- end: `0x18001ce03`
- name: `?StartDocument@TaskXmlWriter@@QEAAJW4Version@Schema@@@Z`
- size: `619`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000a4b4`
- `0x18001d2a8`
- `0x18001dfb8`

## callees

- `0x180003250`
- `0x180005f7c`
- `0x18001c534`
- `0x18001cb98`
- `0x18002e5b0`
- `0x180031010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x18001cbd8`
- `XmlLite!CreateXmlWriter` at `0x18001cbd8`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x18001cc50`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x18001cc50`

## string_xrefs

- `0x18001cdc8`: `xmlns`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall TaskXmlWriter::StartDocument(__int64 a1, int a2)
{
  HRESULT result; // eax
  void *v5; // rcx
  void *v6; // rbx
  __int64 v7; // rax
  int v8; // ebx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 *v11; // rdi
  __int64 v12; // rbx
  __int64 *Entry; // rax
  __int64 *v14; // rdi
  __int64 v15; // rbx
  __int64 *v16; // rax
  __int64 v17; // rax
  int v18; // [rsp+20h] [rbp-78h]
  void *v19; // [rsp+30h] [rbp-68h] BYREF
  IXmlWriterOutput *ppOutput; // [rsp+38h] [rbp-60h] BYREF
  unsigned __int16 v21[24]; // [rsp+40h] [rbp-58h] BYREF

  v19 = 0;
  result = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &v19, 0);
  if ( result >= 0 )
  {
    v5 = v19;
    v6 = *(void **)(a1 + 16);
    if ( v6 != v19 )
    {
      *(_QWORD *)(a1 + 16) = v19;
      if ( v5 )
      {
        (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 8LL))(v5);
        v5 = v19;
      }
      if ( v6 )
      {
        (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
        v5 = v19;
      }
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
    ppOutput = 0;
    result = CreateXmlWriterOutputWithEncodingName(*(IUnknown **)(a1 + 8), 0, L"UTF-16", &ppOutput);
    if ( result >= 0 )
    {
      v7 = _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->((__int64 *)(a1 + 16));
      v8 = (*(__int64 (__fastcall **)(__int64, IXmlWriterOutput *))(*(_QWORD *)v7 + 24LL))(v7, ppOutput);
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      if ( v8 >= 0 )
      {
        v9 = _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->((__int64 *)(a1 + 16));
        result = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v9 + 40LL))(v9, 1, 1);
        if ( result >= 0 )
        {
          v10 = _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->((__int64 *)(a1 + 16));
          result = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 208LL))(v10, 0);
          if ( result >= 0 )
          {
            v11 = (__int64 *)_com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->((__int64 *)(a1 + 16));
            v12 = *v11;
            Entry = Schema::GetEntry((int *)a1, 1);
            result = (*(__int64 (__fastcall **)(__int64 *, int *, __int64, unsigned __int16 *const))(v12 + 216))(
                       v11,
                       &dword_1800505FC,
                       Entry[1],
                       Schema::namespaceUri);
            if ( result >= 0 )
            {
              if ( a2 )
              {
                v18 = (unsigned __int16)*(_DWORD *)a1;
                result = StringCchPrintfW(v21, 0x16u, L"%d.%d", HIWORD(*(_DWORD *)a1), v18);
                if ( result >= 0 )
                {
                  v14 = (__int64 *)_com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->((__int64 *)(a1 + 16));
                  v15 = *v14;
                  v16 = Schema::GetEntry((int *)a1, 2);
                  result = (*(__int64 (__fastcall **)(__int64 *, int *, __int64, _QWORD, unsigned __int16 *))(v15 + 56))(
                             v14,
                             &dword_1800505FC,
                             v16[1],
                             0,
                             v21);
                  if ( result >= 0 )
                  {
                    v17 = _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->((__int64 *)(a1 + 16));
                    return (*(__int64 (__fastcall **)(__int64, int *, const wchar_t *, _QWORD, unsigned __int16 *const))(*(_QWORD *)v17 + 56LL))(
                             v17,
                             &dword_1800505FC,
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
      else
      {
        return v8;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001cb98  mov     r11, rsp
0x18001cb9b  mov     [r11+10h], rbx
0x18001cb9f  mov     [r11+18h], rbp
0x18001cba3  push    rsi
0x18001cba4  push    rdi
0x18001cba5  push    r14
0x18001cba7  sub     rsp, 80h
0x18001cbae  mov     rax, cs:__security_cookie
0x18001cbb5  xor     rax, rsp
0x18001cbb8  mov     [rsp+98h+var_28], rax
0x18001cbbd  mov     ebp, edx
0x18001cbbf  mov     r14, rcx
0x18001cbc2  mov     qword ptr [r11-68h], 0
0x18001cbca  xor     r8d, r8d; pMalloc
0x18001cbcd  lea     rdx, [r11-68h]; ppvObject
0x18001cbd1  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x18001cbd8  call    cs:__imp_CreateXmlWriter
0x18001cbde  test    eax, eax
0x18001cbe0  js      loc_18001CDDE
0x18001cbe6  mov     rcx, [rsp+98h+var_68]
0x18001cbeb  lea     rsi, [r14+10h]
0x18001cbef  mov     rbx, [rsi]
0x18001cbf2  cmp     rbx, rcx
0x18001cbf5  jz      short loc_18001CC29
0x18001cbf7  mov     [rsi], rcx
0x18001cbfa  test    rcx, rcx
0x18001cbfd  jz      short loc_18001CC10
0x18001cbff  mov     rax, [rcx]
0x18001cc02  mov     rax, [rax+8]
0x18001cc06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc0b  mov     rcx, [rsp+98h+var_68]
0x18001cc10  test    rbx, rbx
0x18001cc13  jz      short loc_18001CC29
0x18001cc15  mov     rax, [rbx]
0x18001cc18  mov     rcx, rbx
0x18001cc1b  mov     rax, [rax+10h]
0x18001cc1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc24  mov     rcx, [rsp+98h+var_68]
0x18001cc29  mov     rax, [rcx]
0x18001cc2c  mov     rax, [rax+10h]
0x18001cc30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc35  mov     [rsp+98h+ppOutput], 0
0x18001cc3e  lea     r9, [rsp+98h+ppOutput]; ppOutput
0x18001cc43  lea     r8, pwszEncodingName; "UTF-16"
0x18001cc4a  xor     edx, edx; pMalloc
0x18001cc4c  mov     rcx, [r14+8]; pOutputStream
0x18001cc50  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x18001cc56  test    eax, eax
0x18001cc58  js      loc_18001CDDE
0x18001cc5e  mov     rcx, rsi
0x18001cc61  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlReader@@XZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x18001cc66  mov     r8, rax
0x18001cc69  mov     rcx, [rax]
0x18001cc6c  mov     rax, [rcx+18h]
0x18001cc70  mov     rdx, [rsp+98h+ppOutput]
0x18001cc75  mov     rcx, r8
0x18001cc78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc7d  mov     ebx, eax
0x18001cc7f  mov     rdx, [rsp+98h+ppOutput]
0x18001cc84  mov     rcx, [rdx]
0x18001cc87  mov     rax, [rcx+10h]
0x18001cc8b  mov     rcx, rdx
0x18001cc8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc93  test    ebx, ebx
0x18001cc95  jns     short loc_18001CC9E
0x18001cc97  mov     eax, ebx
0x18001cc99  jmp     loc_18001CDDE
0x18001cc9e  mov     rcx, rsi
0x18001cca1  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlReader@@XZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x18001cca6  mov     r9, rax
0x18001cca9  mov     rcx, [rax]
0x18001ccac  mov     rax, [rcx+28h]
0x18001ccb0  mov     edx, 1
0x18001ccb5  mov     r8d, edx
0x18001ccb8  mov     rcx, r9
0x18001ccbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccc0  test    eax, eax
0x18001ccc2  js      loc_18001CDDE
0x18001ccc8  mov     rcx, rsi
0x18001cccb  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlReader@@XZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x18001ccd0  mov     r8, rax
0x18001ccd3  mov     rcx, [rax]
0x18001ccd6  mov     rax, [rcx+0D0h]
0x18001ccdd  xor     edx, edx
0x18001ccdf  mov     rcx, r8
0x18001cce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cce7  test    eax, eax
0x18001cce9  js      loc_18001CDDE
0x18001ccef  mov     rcx, rsi
0x18001ccf2  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlReader@@XZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x18001ccf7  mov     rdi, rax
0x18001ccfa  mov     rbx, [rax]
0x18001ccfd  mov     edx, 1
0x18001cd02  mov     rcx, r14
0x18001cd05  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x18001cd0a  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x18001cd11  mov     r8, [rax+8]
0x18001cd15  lea     rdx, dword_1800505FC
0x18001cd1c  mov     rcx, rdi
0x18001cd1f  mov     rax, [rbx+0D8h]
0x18001cd26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd2b  test    eax, eax
0x18001cd2d  js      loc_18001CDDE
0x18001cd33  test    ebp, ebp
0x18001cd35  jz      loc_18001CDDE
0x18001cd3b  mov     r9d, [r14]
0x18001cd3e  movzx   eax, r9w
0x18001cd42  shr     r9d, 10h
0x18001cd46  mov     [rsp+98h+var_78], eax
0x18001cd4a  lea     r8, aDD; "%d.%d"
0x18001cd51  mov     edx, 16h; unsigned __int64
0x18001cd56  lea     rcx, [rsp+98h+var_58]; unsigned __int16 *
0x18001cd5b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001cd60  test    eax, eax
0x18001cd62  js      short loc_18001CDDE
0x18001cd64  mov     rcx, rsi
0x18001cd67  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlReader@@XZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x18001cd6c  mov     rdi, rax
0x18001cd6f  mov     rbx, [rax]
0x18001cd72  mov     edx, 2
0x18001cd77  mov     rcx, r14
0x18001cd7a  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x18001cd7f  lea     rcx, [rsp+98h+var_58]
0x18001cd84  mov     qword ptr [rsp+98h+var_78], rcx
0x18001cd89  xor     r9d, r9d
0x18001cd8c  mov     r8, [rax+8]
0x18001cd90  lea     rdx, dword_1800505FC
0x18001cd97  mov     rcx, rdi
0x18001cd9a  mov     rax, [rbx+38h]
0x18001cd9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cda3  test    eax, eax
0x18001cda5  js      short loc_18001CDDE
0x18001cda7  mov     rcx, rsi
0x18001cdaa  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlReader@@XZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x18001cdaf  mov     r10, rax
0x18001cdb2  mov     r8, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x18001cdb9  mov     rcx, [rax]
0x18001cdbc  mov     rax, [rcx+38h]
0x18001cdc0  mov     qword ptr [rsp+98h+var_78], r8
0x18001cdc5  xor     r9d, r9d
0x18001cdc8  lea     r8, aXmlns; "xmlns"
0x18001cdcf  lea     rdx, dword_1800505FC
0x18001cdd6  mov     rcx, r10
0x18001cdd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdde  mov     rcx, [rsp+98h+var_28]
0x18001cde3  xor     rcx, rsp; StackCookie
0x18001cde6  call    __security_check_cookie
0x18001cdeb  lea     r11, [rsp+98h+var_18]
0x18001cdf3  mov     rbx, [r11+28h]
0x18001cdf7  mov     rbp, [r11+30h]
0x18001cdfb  mov     rsp, r11
0x18001cdfe  pop     r14
0x18001ce00  pop     rdi
0x18001ce01  pop     rsi
0x18001ce02  retn
```
