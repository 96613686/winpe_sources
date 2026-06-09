# TaskXmlWriter::StartDocument(Schema::Version)

- ea: `0x18001e0fc`
- end: `0x18001e374`
- name: `?StartDocument@TaskXmlWriter@@QEAAJW4Version@Schema@@@Z`
- size: `632`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000aa9c`
- `0x18001e83c`
- `0x18001f594`

## callees

- `0x1800033d0`
- `0x180006314`
- `0x18001da84`
- `0x18001e0fc`
- `0x180030700`
- `0x180033010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x18001e13c`
- `XmlLite!CreateXmlWriter` at `0x18001e13c`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x18001e1ba`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x18001e1ba`

## string_xrefs

- `0x18001e338`: `xmlns`

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
  __int64 Entry; // rax
  __int64 *v14; // rdi
  __int64 v15; // rbx
  __int64 v16; // rax
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
      v7 = _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(a1 + 16);
      v8 = (*(__int64 (__fastcall **)(__int64, IXmlWriterOutput *))(*(_QWORD *)v7 + 24LL))(v7, ppOutput);
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      if ( v8 >= 0 )
      {
        v9 = _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(a1 + 16);
        result = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v9 + 40LL))(v9, 1, 1);
        if ( result >= 0 )
        {
          v10 = _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(a1 + 16);
          result = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 208LL))(v10, 0);
          if ( result >= 0 )
          {
            v11 = (__int64 *)_com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(a1 + 16);
            v12 = *v11;
            Entry = Schema::GetEntry(a1, 1);
            result = (*(__int64 (__fastcall **)(__int64 *, int *, _QWORD, unsigned __int16 *const))(v12 + 216))(
                       v11,
                       &dword_18005260C,
                       *(_QWORD *)(Entry + 8),
                       Schema::namespaceUri);
            if ( result >= 0 )
            {
              if ( a2 )
              {
                v18 = (unsigned __int16)*(_DWORD *)a1;
                result = StringCchPrintfW(v21, 0x16u, L"%d.%d", HIWORD(*(_DWORD *)a1), v18);
                if ( result >= 0 )
                {
                  v14 = (__int64 *)_com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(a1 + 16);
                  v15 = *v14;
                  v16 = Schema::GetEntry(a1, 2);
                  result = (*(__int64 (__fastcall **)(__int64 *, int *, _QWORD, _QWORD, unsigned __int16 *))(v15 + 56))(
                             v14,
                             &dword_18005260C,
                             *(_QWORD *)(v16 + 8),
                             0,
                             v21);
                  if ( result >= 0 )
                  {
                    v17 = _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(a1 + 16);
                    return (*(__int64 (__fastcall **)(__int64, int *, const wchar_t *, _QWORD, unsigned __int16 *const))(*(_QWORD *)v17 + 56LL))(
                             v17,
                             &dword_18005260C,
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
0x18001e0fc  mov     r11, rsp
0x18001e0ff  mov     [r11+10h], rbx
0x18001e103  mov     [r11+18h], rbp
0x18001e107  push    rsi
0x18001e108  push    rdi
0x18001e109  push    r14
0x18001e10b  sub     rsp, 80h
0x18001e112  mov     rax, cs:__security_cookie
0x18001e119  xor     rax, rsp
0x18001e11c  mov     [rsp+98h+var_28], rax
0x18001e121  mov     ebp, edx
0x18001e123  mov     r14, rcx
0x18001e126  mov     qword ptr [r11-68h], 0
0x18001e12e  xor     r8d, r8d; pMalloc
0x18001e131  lea     rdx, [r11-68h]; ppvObject
0x18001e135  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x18001e13c  call    cs:__imp_CreateXmlWriter
0x18001e143  nop     dword ptr [rax+rax+00h]
0x18001e148  test    eax, eax
0x18001e14a  js      loc_18001E34E
0x18001e150  mov     rcx, [rsp+98h+var_68]
0x18001e155  lea     rsi, [r14+10h]
0x18001e159  mov     rbx, [rsi]
0x18001e15c  cmp     rbx, rcx
0x18001e15f  jz      short loc_18001E193
0x18001e161  mov     [rsi], rcx
0x18001e164  test    rcx, rcx
0x18001e167  jz      short loc_18001E17A
0x18001e169  mov     rax, [rcx]
0x18001e16c  mov     rax, [rax+8]
0x18001e170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e175  mov     rcx, [rsp+98h+var_68]
0x18001e17a  test    rbx, rbx
0x18001e17d  jz      short loc_18001E193
0x18001e17f  mov     rax, [rbx]
0x18001e182  mov     rcx, rbx
0x18001e185  mov     rax, [rax+10h]
0x18001e189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e18e  mov     rcx, [rsp+98h+var_68]
0x18001e193  mov     rax, [rcx]
0x18001e196  mov     rax, [rax+10h]
0x18001e19a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e19f  mov     [rsp+98h+ppOutput], 0
0x18001e1a8  lea     r9, [rsp+98h+ppOutput]; ppOutput
0x18001e1ad  lea     r8, pwszEncodingName; "UTF-16"
0x18001e1b4  xor     edx, edx; pMalloc
0x18001e1b6  mov     rcx, [r14+8]; pOutputStream
0x18001e1ba  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x18001e1c1  nop     dword ptr [rax+rax+00h]
0x18001e1c6  test    eax, eax
0x18001e1c8  js      loc_18001E34E
0x18001e1ce  mov     rcx, rsi
0x18001e1d1  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlReader@@XZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x18001e1d6  mov     r8, rax
0x18001e1d9  mov     rcx, [rax]
0x18001e1dc  mov     rax, [rcx+18h]
0x18001e1e0  mov     rdx, [rsp+98h+ppOutput]
0x18001e1e5  mov     rcx, r8
0x18001e1e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1ed  mov     ebx, eax
0x18001e1ef  mov     rdx, [rsp+98h+ppOutput]
0x18001e1f4  mov     rcx, [rdx]
0x18001e1f7  mov     rax, [rcx+10h]
0x18001e1fb  mov     rcx, rdx
0x18001e1fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e203  test    ebx, ebx
0x18001e205  jns     short loc_18001E20E
0x18001e207  mov     eax, ebx
0x18001e209  jmp     loc_18001E34E
0x18001e20e  mov     rcx, rsi
0x18001e211  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlReader@@XZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x18001e216  mov     r9, rax
0x18001e219  mov     rcx, [rax]
0x18001e21c  mov     rax, [rcx+28h]
0x18001e220  mov     edx, 1
0x18001e225  mov     r8d, edx
0x18001e228  mov     rcx, r9
0x18001e22b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e230  test    eax, eax
0x18001e232  js      loc_18001E34E
0x18001e238  mov     rcx, rsi
0x18001e23b  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlReader@@XZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x18001e240  mov     r8, rax
0x18001e243  mov     rcx, [rax]
0x18001e246  mov     rax, [rcx+0D0h]
0x18001e24d  xor     edx, edx
0x18001e24f  mov     rcx, r8
0x18001e252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e257  test    eax, eax
0x18001e259  js      loc_18001E34E
0x18001e25f  mov     rcx, rsi
0x18001e262  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlReader@@XZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x18001e267  mov     rdi, rax
0x18001e26a  mov     rbx, [rax]
0x18001e26d  mov     edx, 1
0x18001e272  mov     rcx, r14
0x18001e275  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x18001e27a  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x18001e281  mov     r8, [rax+8]
0x18001e285  lea     rdx, dword_18005260C
0x18001e28c  mov     rcx, rdi
0x18001e28f  mov     rax, [rbx+0D8h]
0x18001e296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e29b  test    eax, eax
0x18001e29d  js      loc_18001E34E
0x18001e2a3  test    ebp, ebp
0x18001e2a5  jz      loc_18001E34E
0x18001e2ab  mov     r9d, [r14]
0x18001e2ae  movzx   eax, r9w
0x18001e2b2  shr     r9d, 10h
0x18001e2b6  mov     [rsp+98h+var_78], eax
0x18001e2ba  lea     r8, aDD; "%d.%d"
0x18001e2c1  mov     edx, 16h; unsigned __int64
0x18001e2c6  lea     rcx, [rsp+98h+var_58]; unsigned __int16 *
0x18001e2cb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e2d0  test    eax, eax
0x18001e2d2  js      short loc_18001E34E
0x18001e2d4  mov     rcx, rsi
0x18001e2d7  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlReader@@XZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x18001e2dc  mov     rdi, rax
0x18001e2df  mov     rbx, [rax]
0x18001e2e2  mov     edx, 2
0x18001e2e7  mov     rcx, r14
0x18001e2ea  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x18001e2ef  lea     rcx, [rsp+98h+var_58]
0x18001e2f4  mov     qword ptr [rsp+98h+var_78], rcx
0x18001e2f9  xor     r9d, r9d
0x18001e2fc  mov     r8, [rax+8]
0x18001e300  lea     rdx, dword_18005260C
0x18001e307  mov     rcx, rdi
0x18001e30a  mov     rax, [rbx+38h]
0x18001e30e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e313  test    eax, eax
0x18001e315  js      short loc_18001E34E
0x18001e317  mov     rcx, rsi
0x18001e31a  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlReader@@XZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x18001e31f  mov     r10, rax
0x18001e322  mov     r8, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x18001e329  mov     rcx, [rax]
0x18001e32c  mov     rax, [rcx+38h]
0x18001e330  mov     qword ptr [rsp+98h+var_78], r8
0x18001e335  xor     r9d, r9d
0x18001e338  lea     r8, aXmlns; "xmlns"
0x18001e33f  lea     rdx, dword_18005260C
0x18001e346  mov     rcx, r10
0x18001e349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e34e  mov     rcx, [rsp+98h+var_28]
0x18001e353  xor     rcx, rsp; StackCookie
0x18001e356  call    __security_check_cookie
0x18001e35b  lea     r11, [rsp+98h+var_18]
0x18001e363  mov     rbx, [r11+28h]
0x18001e367  mov     rbp, [r11+30h]
0x18001e36b  mov     rsp, r11
0x18001e36e  pop     r14
0x18001e370  pop     rdi
0x18001e371  pop     rsi
0x18001e372  retn
```
