# TaskXmlReader::CreateXmlReader(void)

- ea: `0x18001e83c`
- end: `0x18001ea36`
- name: `?CreateXmlReader@TaskXmlReader@@AEAAJXZ`
- size: `506`
- prototype: `__int64 __fastcall(TaskXmlReader *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180021710`

## callees

- `0x180007948`
- `0x180009aa8`
- `0x180009bc8`
- `0x18000a1f0`
- `0x18000a274`
- `0x18000a5b4`
- `0x18000a868`
- `0x18000cf58`
- `0x18001da84`
- `0x18001e0fc`
- `0x18001e83c`
- `0x180021bc8`
- `0x180033010`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x18001e86b`
- `XmlLite!CreateXmlReader` at `0x18001e86b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall TaskXmlReader::CreateXmlReader(TaskXmlWriter **this)
{
  char v2; // r15
  HRESULT v3; // eax
  TaskXmlWriter *v5; // rbx
  __int64 v6; // rax
  int v7; // eax
  HRESULT started; // edi
  TaskXmlWriter **v9; // rcx
  TaskXmlWriter *v10; // rsi
  CBstrWriter *v11; // rax
  unsigned int v12; // edx
  TaskXmlWriter *v13; // rcx
  void *v14; // rax
  void *v15; // r14
  __int64 v16; // rcx
  char v17[8]; // [rsp+20h] [rbp-10h] BYREF
  void *v18; // [rsp+28h] [rbp-8h]
  CBstrWriter *v19; // [rsp+68h] [rbp+38h] BYREF
  void *ppvObject; // [rsp+70h] [rbp+40h] BYREF
  void *v21; // [rsp+78h] [rbp+48h] BYREF

  v2 = 0;
  LODWORD(v19) = 0;
  ppvObject = 0;
  v3 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( v3 < 0 )
    return TaskXmlReader::SetErrorInfoXmlLite((TaskXmlReader *)this, v3);
  v5 = (TaskXmlWriter *)ppvObject;
  v21 = ppvObject;
  _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::_AddRef(&v21);
  (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  v6 = _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(&v21);
  v7 = (*(__int64 (__fastcall **)(__int64, TaskXmlWriter *))(*(_QWORD *)v6 + 24LL))(v6, this[4]);
  if ( v7 < 0 )
  {
    started = TaskXmlReader::SetErrorInfoXmlLite((TaskXmlReader *)this, v7);
    if ( v5 )
      (*(void (__fastcall **)(TaskXmlWriter *))(*(_QWORD *)v5 + 16LL))(v5);
    return (unsigned int)started;
  }
  v9 = this + 7;
  v10 = this[7];
  if ( v10 != v5 )
  {
    *v9 = v5;
    _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::_AddRef(v9);
    if ( v10 )
      (*(void (__fastcall **)(TaskXmlWriter *))(*(_QWORD *)v10 + 16LL))(v10);
  }
  if ( *((_BYTE *)this + 40) )
  {
    v11 = (CBstrWriter *)operator new(0x28u);
    v19 = v11;
    if ( v11 )
      v11 = CBstrWriter::CBstrWriter(v11);
    ATL::CComPtr<IStream>::operator=(this + 3, v11);
    if ( !this[3] )
      goto LABEL_21;
    v13 = this[2];
    if ( v13 )
      TaskXmlWriter::`scalar deleting destructor'(v13, v12);
    v14 = operator new(0xA0u);
    v15 = v14;
    v18 = v14;
    if ( v14 )
    {
      LODWORD(v19) = 65542;
      _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>(
        v17,
        this + 3);
      v2 = 1;
      v14 = (void *)TaskXmlWriter::TaskXmlWriter(v15, v17, &v19);
    }
    this[2] = (TaskXmlWriter *)v14;
    if ( (v2 & 1) != 0 )
      ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(v17);
    v16 = (__int64)this[2];
    if ( !v16 )
    {
LABEL_21:
      if ( v5 )
        (*(void (__fastcall **)(TaskXmlWriter *))(*(_QWORD *)v5 + 16LL))(v5);
      return 2147942414LL;
    }
    started = TaskXmlWriter::StartDocument(v16, 65542);
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
0x18001e83c  mov     [rsp-28h+arg_0], rbx
0x18001e841  push    rbp
0x18001e842  push    rsi
0x18001e843  push    rdi
0x18001e844  push    r14
0x18001e846  push    r15
0x18001e848  mov     rbp, rsp
0x18001e84b  sub     rsp, 30h
0x18001e84f  mov     rdi, rcx
0x18001e852  xor     r15d, r15d
0x18001e855  mov     dword ptr [rbp+arg_8], r15d
0x18001e859  mov     [rbp+ppvObject], r15
0x18001e85d  xor     r8d, r8d; pMalloc
0x18001e860  lea     rdx, [rbp+ppvObject]; ppvObject
0x18001e864  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18001e86b  call    cs:__imp_CreateXmlReader
0x18001e872  nop     dword ptr [rax+rax+00h]
0x18001e877  test    eax, eax
0x18001e879  jns     short loc_18001E88A
0x18001e87b  mov     edx, eax; int
0x18001e87d  mov     rcx, rdi; this
0x18001e880  call    ?SetErrorInfoXmlLite@TaskXmlReader@@AEAAJJ@Z; TaskXmlReader::SetErrorInfoXmlLite(long)
0x18001e885  jmp     loc_18001EA24
0x18001e88a  mov     rbx, [rbp+ppvObject]
0x18001e88e  mov     [rbp+arg_18], rbx
0x18001e892  lea     rcx, [rbp+arg_18]
0x18001e896  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::_AddRef(void)
0x18001e89b  nop
0x18001e89c  mov     rcx, [rbp+ppvObject]
0x18001e8a0  mov     rax, [rcx]
0x18001e8a3  mov     rax, [rax+10h]
0x18001e8a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8ac  lea     rcx, [rbp+arg_18]
0x18001e8b0  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@QEBAPEAUIXmlReader@@XZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(void)
0x18001e8b5  mov     r8, rax
0x18001e8b8  mov     rcx, [rax]
0x18001e8bb  mov     rax, [rcx+18h]
0x18001e8bf  mov     rdx, [rdi+20h]
0x18001e8c3  mov     rcx, r8
0x18001e8c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8cb  test    eax, eax
0x18001e8cd  jns     short loc_18001E8F7
0x18001e8cf  mov     edx, eax; int
0x18001e8d1  mov     rcx, rdi; this
0x18001e8d4  call    ?SetErrorInfoXmlLite@TaskXmlReader@@AEAAJJ@Z; TaskXmlReader::SetErrorInfoXmlLite(long)
0x18001e8d9  mov     edi, eax
0x18001e8db  test    rbx, rbx
0x18001e8de  jz      short loc_18001E8F0
0x18001e8e0  mov     rcx, [rbx]
0x18001e8e3  mov     rax, [rcx+10h]
0x18001e8e7  mov     rcx, rbx
0x18001e8ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8ef  nop
0x18001e8f0  mov     eax, edi
0x18001e8f2  jmp     loc_18001EA24
0x18001e8f7  lea     rcx, [rdi+38h]
0x18001e8fb  mov     rsi, [rcx]
0x18001e8fe  cmp     rsi, rbx
0x18001e901  jz      short loc_18001E920
0x18001e903  mov     [rcx], rbx
0x18001e906  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::_AddRef(void)
0x18001e90b  test    rsi, rsi
0x18001e90e  jz      short loc_18001E920
0x18001e910  mov     rax, [rsi]
0x18001e913  mov     rcx, rsi
0x18001e916  mov     rax, [rax+10h]
0x18001e91a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e91f  nop
0x18001e920  cmp     byte ptr [rdi+28h], 0
0x18001e924  jz      loc_18001EA0D
0x18001e92a  mov     ecx, 28h ; '('; Size
0x18001e92f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e934  mov     [rbp+arg_8], rax
0x18001e938  test    rax, rax
0x18001e93b  jz      short loc_18001E946
0x18001e93d  mov     rcx, rax; this
0x18001e940  call    ??0CBstrWriter@@QEAA@XZ; CBstrWriter::CBstrWriter(void)
0x18001e945  nop
0x18001e946  lea     rsi, [rdi+18h]
0x18001e94a  mov     rdx, rax
0x18001e94d  mov     rcx, rsi
0x18001e950  call    ??4?$CComPtr@UIStream@@@ATL@@QEAAPEAUIStream@@PEAU2@@Z; ATL::CComPtr<IStream>::operator=(IStream *)
0x18001e955  cmp     qword ptr [rsi], 0
0x18001e959  jnz     short loc_18001E95D
0x18001e95b  jmp     short loc_18001E9C7
0x18001e95d  mov     rcx, [rdi+10h]; this
0x18001e961  test    rcx, rcx
0x18001e964  jz      short loc_18001E96B
0x18001e966  call    ??_GTaskXmlWriter@@QEAAPEAXI@Z; TaskXmlWriter::`scalar deleting destructor'(uint)
0x18001e96b  mov     ecx, 0A0h; Size
0x18001e970  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e975  mov     r14, rax
0x18001e978  mov     [rbp+var_8], rax
0x18001e97c  test    rax, rax
0x18001e97f  jz      short loc_18001E9AB
0x18001e981  mov     dword ptr [rbp+arg_8], 10006h
0x18001e988  mov     rdx, rsi
0x18001e98b  lea     rcx, [rbp+var_10]
0x18001e98f  call    ??$?0V?$CComPtr@UIStream@@@ATL@@@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@AEBV?$CComPtr@UIStream@@@ATL@@@Z; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>(ATL::CComPtr<IStream> const &)
0x18001e994  mov     r15d, 1
0x18001e99a  lea     r8, [rbp+arg_8]
0x18001e99e  lea     rdx, [rbp+var_10]
0x18001e9a2  mov     rcx, r14
0x18001e9a5  call    ??0TaskXmlWriter@@QEAA@AEBV?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEBUSchema@@@Z; TaskXmlWriter::TaskXmlWriter(_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>> const &,Schema const &)
0x18001e9aa  nop
0x18001e9ab  mov     [rdi+10h], rax
0x18001e9af  test    r15b, 1
0x18001e9b3  jz      short loc_18001E9BE
0x18001e9b5  lea     rcx, [rbp+var_10]
0x18001e9b9  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x18001e9be  mov     rcx, [rdi+10h]
0x18001e9c2  test    rcx, rcx
0x18001e9c5  jnz     short loc_18001E9E3
0x18001e9c7  test    rbx, rbx
0x18001e9ca  jz      short loc_18001E9DC
0x18001e9cc  mov     rax, [rbx]
0x18001e9cf  mov     rcx, rbx
0x18001e9d2  mov     rax, [rax+10h]
0x18001e9d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9db  nop
0x18001e9dc  mov     eax, 8007000Eh
0x18001e9e1  jmp     short loc_18001EA24
0x18001e9e3  mov     edx, 10006h
0x18001e9e8  call    ?StartDocument@TaskXmlWriter@@QEAAJW4Version@Schema@@@Z; TaskXmlWriter::StartDocument(Schema::Version)
0x18001e9ed  mov     edi, eax
0x18001e9ef  test    eax, eax
0x18001e9f1  jns     short loc_18001EA0D
0x18001e9f3  test    rbx, rbx
0x18001e9f6  jz      short loc_18001EA08
0x18001e9f8  mov     rcx, [rbx]
0x18001e9fb  mov     rax, [rcx+10h]
0x18001e9ff  mov     rcx, rbx
0x18001ea02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea07  nop
0x18001ea08  jmp     loc_18001E8F0
0x18001ea0d  test    rbx, rbx
0x18001ea10  jz      short loc_18001EA22
0x18001ea12  mov     rax, [rbx]
0x18001ea15  mov     rcx, rbx
0x18001ea18  mov     rax, [rax+10h]
0x18001ea1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea21  nop
0x18001ea22  xor     eax, eax
0x18001ea24  mov     rbx, [rsp+30h+arg_0]
0x18001ea29  add     rsp, 30h
0x18001ea2d  pop     r15
0x18001ea2f  pop     r14
0x18001ea31  pop     rdi
0x18001ea32  pop     rsi
0x18001ea33  pop     rbp
0x18001ea34  retn
```
