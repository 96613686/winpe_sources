# TaskXmlReader::CreateXmlReader(void)

- ea: `0x18001d2a8`
- end: `0x18001d49b`
- name: `?CreateXmlReader@TaskXmlReader@@AEAAJXZ`
- size: `499`
- prototype: `__int64 __fastcall(TaskXmlWriter **this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180020118`

## callees

- `0x180007488`
- `0x1800095c8`
- `0x1800096e4`
- `0x180009c94`
- `0x180009d18`
- `0x18000a00c`
- `0x18000a298`
- `0x18000c73c`
- `0x18001c534`
- `0x18001cb98`
- `0x18001d2a8`
- `0x1800205cc`
- `0x180031010`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x18001d2d7`
- `XmlLite!CreateXmlReader` at `0x18001d2d7`

## pseudocode

```c
__int64 __fastcall TaskXmlReader::CreateXmlReader(TaskXmlWriter **this)
{
  char v2; // r15
  HRESULT v3; // eax
  TaskXmlWriter *v5; // rbx
  __int64 v6; // rax
  int v7; // eax
  int started; // edi
  __int64 *v9; // rcx
  TaskXmlWriter *v10; // rsi
  CBstrWriter *v11; // rax
  TaskXmlWriter *v12; // rcx
  TaskXmlWriter *v13; // rax
  __int64 v14; // r14
  TaskXmlWriter *v15; // rcx
  __int64 v16[2]; // [rsp+20h] [rbp-10h] BYREF
  CBstrWriter *v17; // [rsp+68h] [rbp+38h] BYREF
  void *ppvObject; // [rsp+70h] [rbp+40h] BYREF
  void *v19; // [rsp+78h] [rbp+48h] BYREF

  v2 = 0;
  LODWORD(v17) = 0;
  ppvObject = 0;
  v3 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( v3 < 0 )
    return TaskXmlReader::SetErrorInfoXmlLite((TaskXmlReader *)this, v3);
  v5 = (TaskXmlWriter *)ppvObject;
  v19 = ppvObject;
  _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::_AddRef((__int64 *)&v19);
  (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  v6 = _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->((__int64 *)&v19);
  v7 = (*(__int64 (__fastcall **)(__int64, TaskXmlWriter *))(*(_QWORD *)v6 + 24LL))(v6, this[4]);
  if ( v7 < 0 )
  {
    started = TaskXmlReader::SetErrorInfoXmlLite((TaskXmlReader *)this, v7);
    if ( v5 )
      (*(void (__fastcall **)(TaskXmlWriter *))(*(_QWORD *)v5 + 16LL))(v5);
    return (unsigned int)started;
  }
  v9 = (__int64 *)(this + 7);
  v10 = this[7];
  if ( v10 != v5 )
  {
    *v9 = (__int64)v5;
    _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::_AddRef(v9);
    if ( v10 )
      (*(void (__fastcall **)(TaskXmlWriter *))(*(_QWORD *)v10 + 16LL))(v10);
  }
  if ( *((_BYTE *)this + 40) )
  {
    v11 = (CBstrWriter *)operator new(0x28u);
    v17 = v11;
    if ( v11 )
      v11 = CBstrWriter::CBstrWriter(v11);
    ATL::CComPtr<IStream>::operator=(this + 3, (__int64)v11);
    if ( !this[3] )
      goto LABEL_21;
    v12 = this[2];
    if ( v12 )
      TaskXmlWriter::`scalar deleting destructor'(v12);
    v13 = (TaskXmlWriter *)operator new(0xA0u);
    v14 = (__int64)v13;
    v16[1] = (__int64)v13;
    if ( v13 )
    {
      LODWORD(v17) = 65542;
      _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>(
        v16,
        (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3);
      v2 = 1;
      v13 = (TaskXmlWriter *)TaskXmlWriter::TaskXmlWriter(v14, v16, &v17);
    }
    this[2] = v13;
    if ( (v2 & 1) != 0 )
      ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(v16);
    v15 = this[2];
    if ( !v15 )
    {
LABEL_21:
      if ( v5 )
        (*(void (__fastcall **)(TaskXmlWriter *))(*(_QWORD *)v5 + 16LL))(v5);
      return 2147942414LL;
    }
    started = TaskXmlWriter::StartDocument(v15, 65542);
    if ( started < 0 )
    {
      if ( v5 )
        (*(void (__fastcall **)(TaskXmlWriter *))(*(_QWORD *)v5 + 16LL))(v5);
      return (unsigned int)started;
    }
  }
  if ( v5 )
    (*(void (__fastcall **)(TaskXmlWriter *))(*(_QWORD *)v5 + 16LL))(v5);
  return 0;
}

```

## disassembly

```asm
0x18001d2a8  mov     [rsp-28h+arg_0], rbx
0x18001d2ad  push    rbp
0x18001d2ae  push    rsi
0x18001d2af  push    rdi
0x18001d2b0  push    r14
0x18001d2b2  push    r15
0x18001d2b4  mov     rbp, rsp
0x18001d2b7  sub     rsp, 30h
0x18001d2bb  mov     rdi, rcx
0x18001d2be  xor     r15d, r15d
0x18001d2c1  mov     dword ptr [rbp+arg_8], r15d
0x18001d2c5  mov     [rbp+ppvObject], r15
0x18001d2c9  xor     r8d, r8d; pMalloc
0x18001d2cc  lea     rdx, [rbp+ppvObject]; ppvObject
0x18001d2d0  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18001d2d7  call    cs:__imp_CreateXmlReader
0x18001d2dd  test    eax, eax
0x18001d2df  jns     short loc_18001D2F0
0x18001d2e1  mov     edx, eax; int
0x18001d2e3  mov     rcx, rdi; this
0x18001d2e6  call    ?SetErrorInfoXmlLite@TaskXmlReader@@AEAAJJ@Z; TaskXmlReader::SetErrorInfoXmlLite(long)
0x18001d2eb  jmp     loc_18001D48A
0x18001d2f0  mov     rbx, [rbp+ppvObject]
0x18001d2f4  mov     [rbp+arg_18], rbx
0x18001d2f8  lea     rcx, [rbp+arg_18]
0x18001d2fc  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::_AddRef(void)
0x18001d301  nop
0x18001d302  mov     rcx, [rbp+ppvObject]
0x18001d306  mov     rax, [rcx]
0x18001d309  mov     rax, [rax+10h]
0x18001d30d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d312  lea     rcx, [rbp+arg_18]
0x18001d316  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlReader@@XZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x18001d31b  mov     r8, rax
0x18001d31e  mov     rcx, [rax]
0x18001d321  mov     rax, [rcx+18h]
0x18001d325  mov     rdx, [rdi+20h]
0x18001d329  mov     rcx, r8
0x18001d32c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d331  test    eax, eax
0x18001d333  jns     short loc_18001D35D
0x18001d335  mov     edx, eax; int
0x18001d337  mov     rcx, rdi; this
0x18001d33a  call    ?SetErrorInfoXmlLite@TaskXmlReader@@AEAAJJ@Z; TaskXmlReader::SetErrorInfoXmlLite(long)
0x18001d33f  mov     edi, eax
0x18001d341  test    rbx, rbx
0x18001d344  jz      short loc_18001D356
0x18001d346  mov     rcx, [rbx]
0x18001d349  mov     rax, [rcx+10h]
0x18001d34d  mov     rcx, rbx
0x18001d350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d355  nop
0x18001d356  mov     eax, edi
0x18001d358  jmp     loc_18001D48A
0x18001d35d  lea     rcx, [rdi+38h]
0x18001d361  mov     rsi, [rcx]
0x18001d364  cmp     rsi, rbx
0x18001d367  jz      short loc_18001D386
0x18001d369  mov     [rcx], rbx
0x18001d36c  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::_AddRef(void)
0x18001d371  test    rsi, rsi
0x18001d374  jz      short loc_18001D386
0x18001d376  mov     rax, [rsi]
0x18001d379  mov     rcx, rsi
0x18001d37c  mov     rax, [rax+10h]
0x18001d380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d385  nop
0x18001d386  cmp     byte ptr [rdi+28h], 0
0x18001d38a  jz      loc_18001D473
0x18001d390  mov     ecx, 28h ; '('; Size
0x18001d395  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d39a  mov     [rbp+arg_8], rax
0x18001d39e  test    rax, rax
0x18001d3a1  jz      short loc_18001D3AC
0x18001d3a3  mov     rcx, rax; this
0x18001d3a6  call    ??0CBstrWriter@@QEAA@XZ; CBstrWriter::CBstrWriter(void)
0x18001d3ab  nop
0x18001d3ac  lea     rsi, [rdi+18h]
0x18001d3b0  mov     rdx, rax
0x18001d3b3  mov     rcx, rsi
0x18001d3b6  call    ??4?$CComPtr@UIStream@@@ATL@@QEAAPEAUIStream@@PEAU2@@Z; ATL::CComPtr<IStream>::operator=(IStream *)
0x18001d3bb  cmp     qword ptr [rsi], 0
0x18001d3bf  jnz     short loc_18001D3C3
0x18001d3c1  jmp     short loc_18001D42D
0x18001d3c3  mov     rcx, [rdi+10h]; this
0x18001d3c7  test    rcx, rcx
0x18001d3ca  jz      short loc_18001D3D1
0x18001d3cc  call    ??_GTaskXmlWriter@@QEAAPEAXI@Z; TaskXmlWriter::`scalar deleting destructor'(uint)
0x18001d3d1  mov     ecx, 0A0h; Size
0x18001d3d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d3db  mov     r14, rax
0x18001d3de  mov     [rbp+var_8], rax
0x18001d3e2  test    rax, rax
0x18001d3e5  jz      short loc_18001D411
0x18001d3e7  mov     dword ptr [rbp+arg_8], 10006h
0x18001d3ee  mov     rdx, rsi
0x18001d3f1  lea     rcx, [rbp+var_10]
0x18001d3f5  call    ??$?0V?$CComPtr@UIStream@@@ATL@@@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@AEBV?$CComPtr@UIStream@@@ATL@@@Z; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>(ATL::CComPtr<IStream> const &)
0x18001d3fa  mov     r15d, 1
0x18001d400  lea     r8, [rbp+arg_8]
0x18001d404  lea     rdx, [rbp+var_10]
0x18001d408  mov     rcx, r14
0x18001d40b  call    ??0TaskXmlWriter@@QEAA@AEBV?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEBUSchema@@@Z; TaskXmlWriter::TaskXmlWriter(_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>> const &,Schema const &)
0x18001d410  nop
0x18001d411  mov     [rdi+10h], rax
0x18001d415  test    r15b, 1
0x18001d419  jz      short loc_18001D424
0x18001d41b  lea     rcx, [rbp+var_10]
0x18001d41f  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x18001d424  mov     rcx, [rdi+10h]
0x18001d428  test    rcx, rcx
0x18001d42b  jnz     short loc_18001D449
0x18001d42d  test    rbx, rbx
0x18001d430  jz      short loc_18001D442
0x18001d432  mov     rax, [rbx]
0x18001d435  mov     rcx, rbx
0x18001d438  mov     rax, [rax+10h]
0x18001d43c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d441  nop
0x18001d442  mov     eax, 8007000Eh
0x18001d447  jmp     short loc_18001D48A
0x18001d449  mov     edx, 10006h
0x18001d44e  call    ?StartDocument@TaskXmlWriter@@QEAAJW4Version@Schema@@@Z; TaskXmlWriter::StartDocument(Schema::Version)
0x18001d453  mov     edi, eax
0x18001d455  test    eax, eax
0x18001d457  jns     short loc_18001D473
0x18001d459  test    rbx, rbx
0x18001d45c  jz      short loc_18001D46E
0x18001d45e  mov     rcx, [rbx]
0x18001d461  mov     rax, [rcx+10h]
0x18001d465  mov     rcx, rbx
0x18001d468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d46d  nop
0x18001d46e  jmp     loc_18001D356
0x18001d473  test    rbx, rbx
0x18001d476  jz      short loc_18001D488
0x18001d478  mov     rax, [rbx]
0x18001d47b  mov     rcx, rbx
0x18001d47e  mov     rax, [rax+10h]
0x18001d482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d487  nop
0x18001d488  xor     eax, eax
0x18001d48a  mov     rbx, [rsp+30h+arg_0]
0x18001d48f  add     rsp, 30h
0x18001d493  pop     r15
0x18001d495  pop     r14
0x18001d497  pop     rdi
0x18001d498  pop     rsi
0x18001d499  pop     rbp
0x18001d49a  retn
```
